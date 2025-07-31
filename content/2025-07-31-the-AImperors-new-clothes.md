+++
title = "How about the AImperor's new clothes?"
date = "2025-07-31"
draft = true

[taxonomies]
tags = ["GenAI"]
+++

# The Difficulty of Discourse

Generative AI, particularly LLMs, is very difficult to converse about,
unless you managed to find a rare group of people open to discourse.

If you imply they have any value rather than outright condemning them,
the people fundamentally opposed to them will throw you in with the
hypists and slopsters.

If you you want to discuss their limits and constraints instead of
praising them, you will be seen as a naysayer, a fossil, and probably
called a luddite (as an insult).

There is also an elephant in the room — the harm and associated with
generative AI and LLMs. For now, I will do the unspeakable *and ignore
it*. But I promise I'll get back to it before this blog is done.

## Denial Is Not a Strategy

I will start by first talking to the side I feel most closely aligned
with: those of us who are critical of GenAI and LLMs in particular.
(I'll mostly limit myself to LLMs here; while I believe the general
thoughts apply more broadly, I'm not as familiar with the use for a
lot of other content.)

Denigrating all use of generative AI as pointless is not constructive.
Why?

Because it's a claim that flies in the face of the lived experience of
everyone who has ever sincerely played and experimented with it.

Everyone who has played with it (and taken at least a wee bit of time to
get familiar with a new and different tool) will have found that there
are scenarios where LLMs are mind-blowing in comparison to what we had
before.

For breaking through the "staring at a blank page" stage of any sort of
project, translations, the most powerful computer translation we've seen
so far, a thesaurus and brain-storming tool with no equal, proximity
search, to, yes, "vibe coding" of random prototypes for whatever, the
list goes on: it can be both useful *and* fun.

### Learning Curve

And no, not all examples of prompts LLMs generated bad responses to are
useful. You've got to take into account how the tool works when you use
it.

Yes, I also laugh when they seemingly can't count the letter "r" in the
word "strawberry".

It's only a good example if you pair it with an explanation as to why,
and how to wield the tool to actually achieve the goal: ask it to write
a python script to do it; it can probably write MMIX better than you.

If you stop at laughing, folks will assume you've never tried in
earnest.

### Admit it!

Sorry, but you can't tell me it is not technically rather amazing what
we can achieve with what is, at the heart of it, probabilistic text
transformation with a pinch of RNJesus.

Plus, as an engineer, I find the sheer scale of the deployments and
operations incredible.

If you want to reach people, you have to acknowledge this experience
instead of denying it; denying it means you are easy to dismiss. That is
not the way to a constructive discourse.

## On the other hand ...

On the other hand, everyone who has sincerely experimented with LLMs in
an area they're confident in knows they have severe limitations.

Honestly? I'd not know where to start with my own anecdotes regarding
this. I have so many.

### Our intuition fails us

And I am not surprised, because I (at the most high-level, admittedly)
understand how they work. And I understand why many people who are not
themselves tech experts do not grasp this well:

We all (except for the youngest of us) have an intuition about what
computers are good at: they're good and fast at math, they can retrieve
factual data from large sets, and they are reliable, even
reproducible. Once you got a response, you could likely trust it.

LLMs *suck* at all of these, and largely don't do any of this when you
throw them a query. (Yes, RAG non-withstanding.)

They are not fast. They do not look-up facts. They are not reliable. And
they are so non-reproducible that Monte Carlo multi-shot is a viable
tactic. You can't trust the response.

### The limitations are glaring

At the time of this writing, even the latest and expensive "frontier"
models available, such as provided by OpenAI or Claude.ai, "fail" in
fairly spectacular ways that no human would, unless severely
incapacitated.

### Hallucination?

And, look, when Claude.ai's expensive to train and expensive to use Opus
4 model with extended thinking and "deep research" generates a "report"
in response to a well-crafted prompt asking for a reasonable question
about a product includes a long reasoning why it couldn't find the
required facts to answer even though the response and progress reports
extensively having "researched" both the vendor's web site, user-forums,
and the web at large (citing multiple sources no less!), and then
proceeds from this assumption to generate the rest of the response —

This *might* be reasonable and certainly reads as such, who of us hasn't
made well-reasoned assumptions yet in the absence of facts? —

But the very fact the response implied just wasn't communicated anywhere
was clearly stated in the very link of the product page provided as part
of the prompt itself?

That is not surprising if you understand how they work at all, of
course.

But that's not hallucination, either.

That's failure.

### If everything you have is an LLM ...

... then everything must be a conversation, right?

This is why even my bank's very reasonable request for me to check my
contact details suggests only the path of "ask our AI chat bot for your
address and chat with it to correct it if needed" — instead of just
pointing me at a simple form to click "OK" on.

(I will allow that some people prefer conversation over other forms of
interactions, regardless of efficiency, but we see this shoved into
every system at the cost of the other approaches.)

### And the operators know:

Support chats now almost always include the disclaimer of "this is an AI
model. It can make mistakes.".

When I reach to support, I want a correct answer. Or at least one I can
hold the company who I'm in contact with to account for.

### Facts can't be trusted

You have got to double-check every thing the generated response claims,
because you only get back a statistically likely answer relative to the
data the system was trained on, plus some intentional randomness.

(This may be particularly annoying to people in whose work and interests
facts very much do matter, and if I may be so snarky, I think a lot of
the LLM hype is generated by people who operate in spheres that are more
subject to negotiation.)

The same is pretty much true for most other (generative) AI use cases,
from image generation to text transcripts and voice: that they appear
plausible to casual human inspection is not the same thing as them being
*correct*.

### Not Fit For Purpose

Simply put: the models are *not* fit for the purpose they're marketed
and sold for.

And we have no known strategy to overcome these limitations.

Because they've suddenly developed these apparent capabilities at a
certain complexity and scale, we keep mostly throwing more scale at
it, while crossing our fingers.

We have sunk trillions into this by now, and yet the systems keep
generating vastly incorrect responses.

# The elephant in the room

Let's come back to the elephant in the room: the harm.

- Generative AI incurs massive environmental costs.
- A lot of the labelling is done by underpaid and exploited workers.
- A lot of the content they're trained can only be considered IP theft
(and would be, if it wasn't done by billionaires).
- Generative AI is marketed with dishonest claims.
- Generative AI is used as what can only be described a massive
denial-of-service attack against our collective minds.

The problem with all of these?

They are appeals to morality, ethics, or external costs.

These only ever matter to businesses when politics creates policies and
regulations that are actually enforced by the judiciary and executive.

So yes, I agree. These and more are excellent reasons to oppose the use
of generative AI.

But if you make any of these arguments to a leader in *business*,
they'll shrug, even if they agree, if it looks like they
create more profits for their shareholders with fewer pesky humans in
the loop.

## The genie is out of the bottle

At the same time, I believe it is impossible to put the genie back into
the bottle. Yes, all these harms are real and horrible. And yet.

If knowing that was enough, none of us would ever fly. None of us would
ever eat meat. We'd not drive combustion cars. And a lot more even more
sever actions. Looms are still automated.

There is no going back. LLMs will be around, even if folks realize their
limits. Because they *are* useful.

## Systemic Action Is Needed

These are arguments you need to make to politicians and as part of your
labour unions.

At a business level, even an individual, these have insufficient
traction. Neither individuals nor organizations are good enough™ for
this.

And they'd also have too little impact, unless we address them
systemically.

# In conclusion

*No, the emperor is not naked.* We must acknowledge this if we want to
have a meaningful conversation.

*The emperor is wearing bloodied rags.* We must acknowledge this if we
want to move forward.

# Quo vadis?

This leaves us, and especially my own industry, in a risky quandary.

While useful, I have doubts that what these models can actually achieve
and deliver is worth their current level of investment.

Much less so if we do eventually end up factoring in what the vendors
currently get to consider "external costs" through regulation.

## The optimists could be right:

There is, of course, a nonzero chance that someone does find the holy
grail - not for "General Purpose AI", but just merely, you know, for
generative AI that doesn't make stuff up; or at least at a statistically
irrelevant level.

#### Is there a middle ground?

I wish we could find a way to just ... stop growing, and let the
usefulness catch up with the investment.

The harms are not inherent in LLMs; we could build and operate them
differently.

## But ...

Should neither occur in the short- or mid-term, I suspect the bubble
will collapse **spectacularly**.

Right now, nobody in the industry can afford for this to happen.

Just like the real-estate-investors need Return-to-Office mandates so
the value of their office spaces doesn't collapse and make the subprime
crisis look tame, all the large investors in the tech world need us to
shove LLMs into everything to keep expanding; and pretend, hope, pray
that there is a path to success — and that we will find it.

The dotcom bubble burst in the first few years of my career. It all went
great — until it didn't.

## Brace:

My best guess? LLMs will still be around in a decade or two, and we'll
all use them for what they can do. (And yes, people will still oversell
them, just like with everything else.)

But *somewhen* between then and today, there'll be a supremely
uncomfortable half-decade or so.

