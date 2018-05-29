---
layout: post
title:  "Benchmarking Software-Defined-Storage Performance - Throughput and Latency"
date:   2018-05-22 15:42:01 +0200
categories: sds ceph
---

I published an [audio blog][audio-blog] entry for my [employer][SUSE] to
discuss two major dimensions of benchmarking Software-Defined-Storage
systems, and in particular [Ceph][ceph].

In this blog, you can find the script for the audio; or rather, what I
intended to say. In case you prefer reading text or have trouble with my
audio recording, this is for you!

I have also uploaded the slides to [Slideshare][slideshare].

# Script

## Introduction

Hello and welcome everyone to an introduction to benchmarking
software-defined-storage systems, notably Ceph. In particular, we will
look at a common conflation of two concepts that are actually orthogonal
to each other: *throughput* and *latency*.

We will conclude today's discussion by seeing how they should *properly*
meet, and how you can influence them in your system.

My name is Lars Marowsky-Brée, and it is my pleasure to be your host for
this session. Since this is the first in the series, a
quick introduction: I am the architect for SUSE's Enterprise Storage
product, which is powered by the Open Source Ceph project. I also
represent SUSE on the Ceph Advisory Board. I have been with SUSE since
2000 and with Linux and Open Source since 1994.  I am specifically
interested in distributed systems and storage.

## Disclaimer

I also must add a disclaimer; this is somewhat of a simplification.
There are many more factors that affect this and dimensions to discuss.
Here, we only pick two of them, and ignore most everything else except
in passing. Your environment might thus differ.

That said ...

## How everyone starts

So, you have built a shiny new Ceph cluster. Either as a pilot,
proof-of-concept, lab, or for production; eventually, you will want to
know how fast this thing goes!

Or in more professional terms, whether it meets the performance
requirements of your use case, your Service Level Agreements, and
whether you need to add resources or can even save some funds.

What everyone does next is to grab a client system and run a load
test against it - with a tool like Jens's fantastic [Flexible I/O
Tester][fio], that is the simplest test to run.

Perhaps you are even lucky enough to have several clients, so you start
all the runs at the same time and add up the throughput numbers they
report, and there you go - **100 Gigabytes/s**.

*Bam!* All done.

## Shock sets in

But you are more savvy than this. You know that there are two more numbers
that matter - latency and Input/Output operations per second (IOPS for
short).

And you look at that benchmark report you just got *again* and ...
**woah**, latency is really, really bad! This system ain't no good!

Now, before you rip everything apart and throw it out of the window,

## Let's take a step back.

In particular, let's look at what these dimensions mean, and that
will help us understand why you did not measure what you thought it
did.

Let's also introduce a metaphor that we are all familiar with:
transferring cargo by road.

- Throughput is the easiest one to understand. How much data did the
  cluster read or write during the time period?

  Or within our metaphor, how much cargo was transferred?

- Latency is the time it took for these individual requests to be
  completed. This is not well represented as a single number, not even
  as an average or median; you really need to look at the distribution
  here.

  After all, we need all of a transaction's data to be transferred, not
  just half of it really fast, and then forever for that last bit,
  before we can complete it.

  This has a very simple analogy in our metaphor as well - how long did
  it take for a particular piece of cargo to be delivered? How fast does
  the road allow you to go?

- Finally, IOPS provide insight into how many individual operations per
  second the cluster completed. Or put differently, how many vehicles
  did the road handle? If you multiply this number with the payload of
  the requests, you get to the throughput number; the relationship with
  latency is slightly more complicated.

## What do you want to measure?

How do you transfer as much cargo as possible over a given stretch of
road? Well, you load up the biggest trucks allowed with as much cargo as
they can handle in the largest containers, and whenever there's a free
stretch of road, you squeeze another truck in! Who cares if they have to
wait as long as the road flows.

If you're building that road, you will add as many lanes as you can, and
prioritize literal bandwidth over the speed limit.

And how would you see how quickly you can get a courier package from
point A to point B? You pick the lightest envelope, and hand it to a
courier on a blazingly fast motorcycle with no additional weight to slow
them down.

If you build and can control the road, you might even go for a single
lane - it does not need to be wide, but it needs to be absolutely
smooth, preferably straight, no intersections.

And for sure without a single truck in sight.

## Going back to our benchmark report

We now realize what happened. We ran a test that absolutely congested
our road, squeezing out the last bit of throughput, and then looked at
how long it took to transfer an individual package under those
circumstances.

Clearly, that doesn't work so well. There are many factors that play
against us then.

It takes longer to transfer a large package; yet, a large package is the
most efficient way of transferring lots of data. There's simply less
overhead relative to the payload, at all layers.

Especially with spinning hard disks, they are much better at streaming
data than many small, random IO requests. The disk head must seek, and
that causes contention and delays.

The network might have been optimized for bandwidth - and opted to go
with 40 GbE instead of 25 GbE ports. Yet in fact, 40 GbE is composed of
4 lanes of 10 GbE each; processing data at 10 GbE latencies. Whereas the
25 GbE would have been a single lane with much better individual
latency. (And 100 GbE would be the equivalent bundle.)

## Now: better benchmarks

Doing said benchmark with a single "fast courier" would not be very
realistic either. Such synthetic benchmarks are useful from a
developer's point of view, since they help us understand specific,
isolated properties of the system. Translating from these to real world
use cases however is a dark and mysterious art.

A better benchmark would be more representative of a user's actual
workload. And how to achieve this is fairly clear in the light of our
previous discussion. We need to measure the system when it is neither
fully saturated, nor unrealistically empty.

What we *actually* want to know is what load the system can sustain
*without degrading* - meaning while still achieving the latency target
we need.

### fio to the rescue

Thankfully, our Swiss Army knife [fio][fio] has two approaches of
helping us out here.

The first stop might be the obvious one that seems to achieve our goal
directly: the [latency_target
job option][http://fio.readthedocs.io/en/latest/fio_doc.html#i-o-latency].
I would recommend to lower the latency percentile to something
more real world, which is never perfect - say, 99.999 percent. Now, fio
will start the test run with finding the maximum throughput the system
can sustain while maintaining our latency target automatically.

However, this is not dynamically adjusted over the run, and if you're
running a test with multiple clients, you can get strange effects when
they all try to find that sweet spot at the very same time. The test
period is also fairly brief, which might not account for the ramp up
time of a distributed storage system well.

### rate limiting individual jobs

The second approach is to limit the IO rate of our system via the [rate
job option][http://fio.readthedocs.io/en/latest/fio_doc.html#i-o-rate].

My recommended approach here would be to run the saturation test we
started out with first. And then, knowing the maximum, run the test
again at each ten percent increment. In this way, we will also gain a
much better understanding of the performance curve of our system.

## What load factor to aim for?

Just like the autobahn, you would not run your system under maximum load
all the time. Any system needs some amount of performance buffer - you
need to maintain your SLAs even during reconstruction periods, and real
world work loads tend to have spikes.

As a rule of thumb, and depending on your price sensitivity, I would
recommend to aim for a load factor between twenty-five and fifty
percent at normal operations.

It is quite likely your initial pilot deployment did not perfectly reach
your goal - so how to adjust?

## Scaling in response

There are two key dimensions in which we can scale our system.

### Throughput

First, bandwidth. Ceph excels at *scaling out* - adding storage devices
and nodes to the system. Due to Ceph's inherent pseudo-random
distribution of data across all storage devices, as long as the
networking layers do not saturate, you get pretty much linearly more
bandwidth potential. Especially for spinning media, this also reduces
spindle contention massively.

This in turn lowers the respective saturation our system is under at a
given load factor, and thus improves the potential load our system can
take without degrading.

Yet, the performance of a single optimal request does not improve
quite as much. Which brings us to our second dimension:

### Latency

Latency. The optimal latency a system can achieve is determined by
summing up the time of all the steps a request goes through - the
network layer, CPU processing time, even RAM, busses, and finally the
low-level storage device latency.

Potential ways to improve this are swapping 10 GbE for 25 GbE
networking, going from 3 Gbit/s SAS to 12 Gbit/s bus, or
eliminating spindle contention by swapping spinning rust for all-flash;
or at least using a hybrid solution to reduce it.

These will lower the base line latency of the system, and reduce how
much it degrades under increased load.

### Buyer beware

While trying to remain clear and concise, the engineer in me reminds us
again that actual results will depend on many factors, some having a
quite counter-intuitive impact, such as possibly compression.

It is also mandatory to test the real services and applications on your
cluster, and to also test them under adverse conditions.

There are also many tuning options that can help us get more out of
existing hardware. While many Ceph distributions strive to set good
defaults, your use case might vary.

Still, understanding these two dimensions and their intersection is a
key step in designing better Ceph clusters!

## In conclusion

We have now discussed latency versus throughput, and how to merge these
two into a more representative benchmark. We have also briefly touched
on how to then leverage these numbers to improve the decisions with
regard to our system architecture.

With this in mind, we can be more confident about choosing the right
hardware and the right amount of hardware for our needs.

### Wrap up

I hope you found this podcast useful. I would love to hear your
feedback: on [Twitter][http://twitter.com/larsmb] or by reaching out to
me directly at L M B at SUSE dot com. I also very much welcome
corrections, questions, and suggestions for further instalments.

And, please, spread the word and link!

Thanks for your time and have a great day.


[audio-blog]:   http://google.com/
[SUSE]:         http://suse.com/
[ceph]:         http://ceph.com/
[slideshare]:   http://slideshare.com/xxxxxx
[fio]:          http://fio.readthedocs.io/en/latest/index.html
