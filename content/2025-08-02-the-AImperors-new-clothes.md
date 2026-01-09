+++
title = "The AImperor is Neither Naked nor Impeccably Dressed"
date = "2025-08-02"
draft = false

[taxonomies]
tags = ["GenAI"]
+++

## The Difficulty of Polarized Discourse

Generative AI, particularly LLMs, is very difficult to converse about,
unless you managed to find a rare group of people open to dialogue.

If you imply LLMs have any value rather than outright condemning them,
the people fundamentally opposed to them will throw you in with the
hypists and slopsters.

If you want to discuss their limits and constraints instead of praising
them, you will be seen as a naysayer, a fossil, and probably get called
a Luddite (and not as the praise it should be).

There is also an elephant in the room — the harm associated with
generative AI and LLMs. For now, I will do the unspeakable *and ignore
it*. But I promise I'll get back to it before this blog is done, and
explain why.

We need to overcome these tensions if we are to find a path forward. And
we must, since LLMs and generative AI *exist*, are part of our shared
reality, seen to be shiny by some (for various reasons), and (for
complex reasons) get added to quite literally everything.

As a profession, we owe it to our users, customers, and community
members to do better.

### Denial is not a strategy

I will start by first talking to the side I feel most closely aligned
with: those of us who are critical of GenAI and LLMs in particular.
(I'll mostly limit myself to LLMs here; while I believe the general
thoughts apply more broadly, I'm not as familiar.)

Denigrating all use of generative AI as pointless is not constructive,
nor credible.

Why?

**Because it's a claim that flies in the face of the lived experience of
everyone who has ever sincerely experimented with it.**

Everyone who has done so (and taken at least a wee bit of time to get
familiar with a new and different tool) will have found scenarios where
LLMs are mind-blowing in comparison to what we had before.

For breaking through the "staring at a blank page" stage of any sort of
project, translations (of both human and programming languages, and even
between those two domains), a thesaurus and brain-storming tool with no
equal (except maybe the trusty rubber duck), approximate
summarization, proximity search, providing feedback on tone and not just
syntax, to, yes, "vibe coding" of random prototypes for whatever, the
list goes on: it can be both useful *and* fun.

Speaking of software engineering, seasoned professional engineers I
highly respect and personally know report impressive results (with, yes,
caveats; we'll get to those). It would be hubris to dismiss all of their
insights.

#### Learning curve

And no, not all examples where LLMs generate bad responses are
constructive. You have to take how the tool works into account when you
use it.

Yes, I also laugh when they seemingly can't count the number of
occurrences of the letter "r" in the word "strawberry".

This is only a good example if you pair it with [an explanation as to
*why*](https://www.runpod.io/blog/llm-tokenization-limitations), and how
to [wield the tool to actually achieve the
goal](https://deepgains.substack.com/p/why-do-llms-struggle-with-counting):
ask it to write a python script to do it; it can probably write MMIX
better than you.

If you stop at laughing, folks will assume you've never tried in
earnest.

If you can't at least hold the tool right, people will dismiss your
opinion; that's not a credible position to argue from.

#### Perfection is overrated (sometimes)

Not all scenarios need perfection. The LLM may generate a response you
wouldn't merge or write yourself; doesn't mean it's not useful in the
cases it does successfully one-shot an acceptable answer, possibly with
some polishing or minimal re-prompting.

And especially to users who have a scenario where long-term
maintainability or even performance is perhaps a secondary concern, it
is more useful to have a working answer than a better one.

AI may not raise the ceiling, but it does raise the floor. And there is
value in that.

#### Let's admit it

Sorry, but you can't tell me it is not technically rather amazing what
we can achieve with what is, at the heart of it, probabilistic text
transformation with a pinch of Lady Luck.

Plus, as an engineer, I find the sheer scale of the deployments and
operations incredible.

#### Acknowledge people's experience

If you want to reach people, you have to acknowledge this instead of
denying it; rejecting it entirely means you are easy to dismiss. That is
not the way to a constructive discourse.

Only if you — we — are also honest about what the LLMs *can* do will we
be taken seriously and be credible when we discuss their limits and
constraints.

### On the other hand ...

On the other hand, every expert who has, in their field, sincerely
experimented with LLMs also knows they have severe limitations.

And we must be honest about those if we want to model LLMs appropriately
in our minds (instead of falling into the trap of anthropomorphizing
them), which is a pre-requisite to using them where they make sense, and
make sensible use of their outputs. And avoiding their use where they
are not the right tool for the job.

Honestly? I'd not know where to start with my own anecdotes regarding
that. I have so many.

#### Our intuition fails us

And I am not surprised, because I (at the most high-level, admittedly)
understand how they work. And I understand why many people who are not
themselves tech experts do not grasp this well.

We all (except for the youngest of us) have some intuition about what
computers are good at:
- they do math fast and correctly,
- they can retrieve factual data from large sets,
- they are reliable,
- they produce reproducible outcomes.

Once you got a response, barring bugs, you could likely trust it.

LLMs *fail* at all of these, and largely don't do any of this when you
throw them a prompt. (Yes, Retrieval-Augmented Generation
non-withstanding.)

They are not fast. They do not look-up facts. They are not databases.
They are not reliable. And they are so non-reproducible that Monte Carlo
multi-shot (give the problem to LLMs multiple times, hoping one answer
is good enough) is a viable tactic. You can't trust the response.

Clearly, at the very least, this requires a period of adjustment,
combined with honest education and training: the outputs from these
tools need to be treated quite differently. Both of which most of us
were not given before being exposed to it.

And their generated responses sound very plausible and confident;
because that is what they were trained on. Few people write and publish
content when they are severely doubting themselves.

This is likely obvious to you if you found your way to my blog; but it
is *not* obvious to society at large, still.

#### The limitations are glaring

At the time of this writing, even the latest and expensive "frontier"
models available, such as provided by OpenAI or Claude.ai, "fail" in
fairly spectacular ways that no human would, unless severely
incapacitated.

#### Hallucination is a Euphemism

LLMs are non-reproducible as a fundamental design choice, since some
amount of randomness is part of their inference process. This can be
useful for brain storming, but also means that - from the point of view
of a user - they occasionally "invent" stuff that doesn't exist.

LLMs "hallucinate" facts, citations, and references because it is likely
that such sources would exist and be cited by a human. This is somewhat
well-known by now.

But the opposite also happens: they hallucinate the *absence* of
information when they don't fully and/or accurately incorporate the
sources used into their contexts.

For example, when Claude.ai's Opus 4 (an expensive to train and
expensive to use model with extended thinking and "deep research"
enabled) "report" in response to a fairly well-crafted prompt asking
about a product's specification includes a long explanation that it
couldn't find the required facts to answer the question, claiming to
have "extensively" researched the official channels, technical forums,
etc (stating to have incorporated **541** sources), and then proceeds
from that assumption to generate the rest of the response —

This *might* be reasonable and certainly reads as such, right? It
researched way more sources than any human would have.

However: the "missing" detail was clearly part of the very product page
provided as part of the prompt itself.

Yes, that should not be surprising if you understand their constraints.

But that's not hallucination, either.

From the perspective of the user, that is **failure**.

Yes. This is not a good use case for LLMs; but it is one they are
explicitly marketed for. I cringe whenever I see someone suggest to
query an LLM for facts or research. (Unless, of course, they really
cross-check all assumptions, which experience with even university-grade
work suggests is not going to happen.)

#### The Anthropomorphization Trap

Since the models present as human language conversation, humans tend to
assume they behave similarly to how a human would.

e.g., when we correct them, they apologize and produce a different
response. Humans even go so far as assuming the model was "testing" them
with its errors to see if they were paying attention.

We might assume that they are confident when their language sounds
confident. We ascribe intent, even emotions, based on the generated
outputs. We fall for it when it congratulates us or pays our prompt a
compliment.

Of course, none of that is true. But it is very difficult to talk to
LLMs without using such language, and without falling into the trap of
using mental models of humans to relate to the LLMs.

(People go as far as threatening them to get supposedly better outputs;
which, honestly, *if* those people assume they do indeed have emotions
affecting their results, is pretty screwed up.)

#### If everything you have is an LLM ...

... then everything must become a conversation.

This is why even my bank's very reasonable request for me to check my
contact details suggests only the path of "ask our chat bot for your
address and chat with it to correct it if needed" — instead of just
pointing me at a simple form to click "OK" on.

(I will allow that some people prefer conversation over other forms of
interactions, regardless of efficiency, but we see this shoved into
every system at the cost of the other approaches.)

LLMs are now used for everything, even when they're not the best answer
we have. Be it a database look-up or even different forms of ML/AI, all
the attention is on LLMs.

Due to similar dynamics, they are used to hide problems that should be
addressed at the root cause. By all means, use an LLM for heuristic
search for your documentation — but don't use the LLM to provide the
answer (with possible corruption). Instead fix your docs to be better!
(Ironically, this will make your product better to interact with by LLMs
...)

#### And the operators know

Support chats now almost always include the disclaimer of "this is an AI
model. It can make mistakes.".

When I reach out to support, I want a correct answer. Or at least one I
can hold the company who I'm in contact with to account for.

[Over on LinkedIn I have argued that this is another case of holding the
tool
wrong](https://www.linkedin.com/pulse/dont-direct-your-users-chat-bots-support-lars-marowsky-br%C3%A9e-pcgoe/)
and that it should be done better and how.

But the current common approach is simply infuriating: it focuses only
on cost reduction for the provider, at the expense of the consumer. and
not on better outcomes for the consumer.

#### Facts?

You have to double-check every thing the generated response claims,
because you only get back a statistically likely answer relative to the
data the system was trained on, plus some intentional randomness. Not
facts the system looked up in response to your query.

This may be particularly annoying to people in whose work and interests
facts and all details very much do matter. And if I may be so snarky, I
think a lot of the LLM hype is generated by people who operate in
spheres where the shared reality is more subject to negotiation.

The same is pretty much true for most other (generative) AI use cases,
from image generation to text transcripts and voice: that they appear
plausible to casual human inspection is not the same thing as them being
*correct*.

#### Not Fit For Purpose

**TL;DR**: the models are **not** fit for the purposes they're marketed and
sold for.

And we have no known strategy to overcome these limitations.

Because GPTs and LLMs have suddenly developed these apparent
capabilities at a certain complexity and scale, our answer mostly
consists of throwing more scale at the limits, and crossing our
fingers.

We have collectively sunk trillions into this. And while this yields
improvements, the systems keep generating vastly incorrect and
incomplete responses.

That is not the same as saying they are not useful; I kindly refer back
to the first part of this writing. And yet, there is an inflated
presentation that they do not deliver on.

They are an open research problem. The strategy might exist. But it
might not.

## The Elephant in the room

Let's come back to the elephant in the room: the harm.

- Generative AI incurs massive environmental costs.
- A lot of the labelling is done by underpaid and exploited workers.
- A lot of the content they're trained can only be considered IP theft
  (and _would_ be, if it wasn't done by billionaires).
- They are trained to read like confidence tricksters.
- For Cloud-based Generative AI, the usual privacy concerns apply.
- Generative AI is marketed with dishonest, exaggerated claims.
- It's often pushed with the goals of wage suppression, de-skilling, and
  lay-offs.
- LLMs reproduce and thus perpetuate biases inherent in their training
  data and labeling.
- As a consequence, they also are bad at generating output of higher
  quality than their inputs; much the opposite.
- The inability to filter Generative AI outputs from future inputs will
  likely lead to model collapse.
- The way how they present their output as "human" language actively
  undermines our ability to not anthropomorphize them and maintain
  sensible mental models.
- Generative AI is used in ways that can only be described as massive
  denial-of-service attacks against our collective minds and society.

Yes, I agree. These and more are excellent reasons to oppose the use of
most generative AI.

And yet, only some of these problems _are_ immediately (and not just
several quarters in the future) applicable to a business today.

The problem with raising the rest?

They are appeals to morality, ethics, or external costs.

These only ever matter to businesses when politics creates policies and
regulations that are actually enforced by the judiciary and executive.

But if you make any of these arguments to a leader in *business*,
they'll shrug, even if they agree, if it looks like they create more
profits for their shareholders with fewer pesky humans in the loop.
Humans mean wages, social security payments, overhead costs. Of course
they prefer automation.

I respect that this is why you chose to not learn how to hold the tool.
But then be clear about this; make moral arguments if your argument is
moral, don't claim the tool doesn't and/or can't work.

Note that Luddites were not opposed to progress as such; the arguments
brought forth against all criticism of Generative AI have similarities
with the campaigns against Luddism.

Further note that, somehow, GenAI and LLMs are almost always brought up
as tools to reduce the staffing needs for employees and individual
contributors; rarely for the CxO level.

### Systemic Action is needed

These are arguments you need to make to politicians and as part of your
labour unions.

At a business level, even an individual, these have insufficient
traction. Neither individuals nor organizations are good enough™ for
this. And a few individuals or even organizations changing their minds
also has too little impact. We must address them systemically.

These harms are not inherent to LLMs per se. They are inherent to LLMs
*driven by shareholder-first capitalism in the pre-regulation rush*.

And it works! See the EU AI Act, and even the OSI AI Definition (as much
as I criticize it). Regulation is always slower than the unrestrained
gold rush. But it will catch up; we've seen this before. Let's give it a
push, together.

### The genie is out of the bottle

At the same time, I believe it is impossible to put the genie back into
the bottle. Yes, all these harms are real and horrible. And yet.

If knowing that was enough, most planes would be scrapped. There would
be no cars with ICE. Coal and gas power plants would have been shut off
three decades ago.

There is no going back. LLMs will be around, even if folks realize their
limits. Because they *are* useful.

We need them to be ethical and sustainable.

## Is the AImperor naked?

*No, the emperor is not naked.*

We must acknowledge this if we want to have a meaningful conversation. I
found myself too frequently annoyed with the reductionist and dismissive
position taken by some critics.

But.

*The emperor is wearing bloodied rags.*

We must acknowledge this if we want to move forward. As you can probably
tell, my position isn't quite neutral. But our criticism needs to be
constructive, credible, and framed appropriately for our target audience
to have impact.

## Quo vadis?

This leaves us, and especially my own industry, in a risky quandary.

While useful, I have doubts that what these models can actually achieve
and deliver is worth their current level of investment.

Much less so if we do eventually end up factoring in what the vendors
currently get to consider "external costs" through regulation.

### The optimists could be right

There is, of course, a nonzero chance that someone does find the holy
grail - not for "General Purpose AI", but just merely, you know, for
generative AI that doesn't make stuff up; or at least at a statistically
irrelevant level. A new algorithm, a new magic scale threshold.

### Or else?

Should this fail to occur in the short- or mid-term, I suspect the
bubble will collapse **spectacularly**. And I am [not
alone](https://fortune.com/2024/02/26/nvidia-ai-bubble-apollo-asset-manager-dotcom-artificial-intelligence/)
in this prediction.

The dotcom bubble burst in the first few years of my career. It all went
great — right until it didn't.

Right now, nobody in the industry can afford for this to happen.

Just like the real-estate-investors need Return-to-Office mandates so
the value of their office spaces doesn't collapse and make the subprime
crisis look tame, all the large investors in the tech world need us to
shove LLMs into everything to keep expanding; and pretend, hope, pray
that there is a path to success — and that we will find it.

There's a reason "AI" features are now in everything, beyond the people
actually believing the claims: the industry needs to show increasing
user counts. *Or else.*

### So what will happen?

My best guess? LLMs will still be around in a decade or two, and we'll
all use them for what they can do, with varying levels of quality of
product. (And yes, people will still oversell them, just like with
everything else.)

But *somewhen* between then and today, there'll be a supremely
uncomfortable half-decade or so.

LLMs are neither useless nor magical. They succeed at certain tasks but
fail spectacularly at others. The problem isn't the technology but
shareholder capitalism without adequate regulation.

## And until then?

Until then, let's do our best. Perhaps limit their use, as far as your
job permits. Don't hate yourself or others if you decide that to stay
competitive, you have no choice. Be mindful. Strive to maintain an
appropriate mental model of the tool. Use the more ethical options. Not
everything can be offset entirely, but donate to the restoration of
swamps and other offsetting approaches. Donate to educational charities
to raise awareness. Advocate for ethical and sustainable approaches.
Write to your legislators and regulators (policy proposals are beyond
the scope of this article). Have meaningful conversations with your
corporate leadership about how to lower costs *and* improve quality. Be
realistic about what you can achieve if they are owned by investors that
are also owning AI companies. Unionize. Don't guilt-trip folks who use
them, but educate them from a position of understanding. Walk the line
between denial and hype.

Oh, and diversify your stocks.

# Addenda

## 2025-08-03

It's been brought to my attention that one assumption might be overly
optimistic: that "not fit for purpose" would lead to significantly lower
adoption (to the point of collapsing parts of the bubble, at least),
especially when it comes to factual correctness and reliability.

It's of course also a possibility that "we" collectively decide that,
for many more scenarios than I'd deem acceptable, facts and correctness
aren't all that important, because the tools are "fun and convenient".

As already evidenced by how many people replace search and references
with a chat bot (_without_ the due diligence after). And how little we
value these properties in general.

This insight depresses me, but alas, it rings plausible.

This would continue to undermine our shared reality and trust (since too
often, multiple people asking the same question would generate different
responses), and continue the erosion of quality.

I hope we'd still see improvements in the tools to the point where this
is at least less of a problem.

It might also lead to a further stratification of knowledge and tech
use; similar to how we have different qualities of many other products
available at different price points.

There is also a reasonably straightforward fix to prevent the worst:
**product liability for the generated responses** (that can't simply be
subverted by adding "use at your own risk" disclaimers).

While it might not matter that the bot got someone's birthday wrong,
I've had the chat bot suggest that it would be a "fun experiment" to use
my [espresso maker](https://9barista.com/) for pressure extraction of
vegetables (which, in technical terms, we call a "bomb"); without any
such caveats and response to an innocent prompt.

And similarly, if a company offers a chat bot as a support tool, the
company *should* be held liable and accountable for what that tool
recommends.

Regulation and enforcement thereof is key.

## 2025-08-04

Cleaned up (hopefully) the example on "negative" hallucinations.

Added the Anthropomorphization Trap section.
