+++
title = "How about the AImperor's new clothes?"
date = "2025-07-31"
draft = true

[taxonomies]
tags = ["GenAI"]
+++

## The Difficulty of Polarized Discourse

Generative AI, particularly LLMs, is very difficult to converse about,
unless you managed to find a rare group of people open to discourse.

If you imply they have any value rather than outright condemning them,
the people fundamentally opposed to them will throw you in with the
hypists and slopsters.

If you you want to discuss their limits and constraints instead of
praising them, you will be seen as a naysayer, a fossil, and probably
get called a luddite (as an insult).

There is also an elephant in the room — the harm and associated with
generative AI and LLMs. For now, I will do the unspeakable *and ignore
it*. But I promise I'll get back to it before this blog is done.

We need to overcome these tensions if we are to find a path forward. And we
must, since LLMs and generative AI *exist*, are part of our shared reality,
seen to be shiny by some (for various reasons), and (for complex reasons) get
shoved into everything.

As a profession, we owe it to our users, customers, and community members to
do better.

### Denial Is Not a Strategy

I will start by first talking to the side I feel most closely aligned
with: those of us who are critical of GenAI and LLMs in particular.
(I'll mostly limit myself to LLMs here; while I believe the general
thoughts apply more broadly, I'm not as familiar with the use for a
lot of other content.)

Denigrating all use of generative AI as pointless is not constructive.

Why?

**Because it's a claim that flies in the face of the lived experience of
everyone who has ever sincerely experimented with it.**

Everyone who has done so (and taken at least a wee bit of time to get
familiar with a new and different tool) will have found scenarios where
LLMs are mind-blowing in comparison to what we had before.

For breaking through the "staring at a blank page" stage of any sort of
project, translations, the most powerful computer translation we've seen
so far, a thesaurus and brain-storming tool with no equal, proximity
search, to, yes, "vibe coding" of random prototypes for whatever, the
list goes on: it can be both useful *and* fun.

#### Learning Curve

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

If you can't at least hold the tool right, people will dismiss your
opinion; that's not a credible position to argue from.

#### Perfection Is Overrated (sometimes)

Not all scenarios need perfection. The LLM may generate a response you
wouldn't merge or write yourself; doesn't mean it's not useful in the
cases it does successfully one-shot an acceptable answer, possibly with
some polishing or minimal re-prompting.

And especially to users who have a scenario where long-term
maintainability or even performance is perhaps a secondary concern, it
is more useful to have a working answer than a better one.

#### Approximate Solutions Can Rock

There are use cases that would be incredibly difficult to code
traditionally: e.g., I use LLMs to generate hash tags for web pages I
clip for linking them, or for heuristic proximity search based on their
embeddings, ... For these scenarios, it's not important it is correct or
complete.

#### Admit it:

Sorry, but you can't tell me it is not technically rather amazing what
we can achieve with what is, at the heart of it, probabilistic text
transformation with a pinch of RNJesus.

Plus, as an engineer, I find the sheer scale of the deployments and
operations incredible.

#### Acknowledge People's Experience

If you want to reach people, you have to acknowledge this experience
instead of denying it; denying it means you are easy to dismiss. That is
not the way to a constructive discourse.

### On the other hand ...

On the other hand, everyone who has sincerely experimented with LLMs in
an area they're confident in knows they have severe limitations.

Honestly? I'd not know where to start with my own anecdotes regarding
this. I have so many.

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

LLMs *suck* at all of these, and largely don't do any of this when you
throw them a query. (Yes, RAG non-withstanding.)

They are not fast. They do not look-up facts. They are not databases.
They are not reliable. And they are so non-reproducible that Monte Carlo
multi-shot (give the problem to LLMs multiple times, hoping one answer
is good enough) is a viable tactic. You can't trust the response.

Clearly, at the very least, this requires a period of adjustment,
combined with honest education and training. Both of which most of us
were not given before being exposed to it.

#### The limitations are glaring

At the time of this writing, even the latest and expensive "frontier"
models available, such as provided by OpenAI or Claude.ai, "fail" in
fairly spectacular ways that no human would, unless severely
incapacitated.

#### Hallucination?

For example, when Claude.ai's expensive to train and expensive to use
Opus 4 model with extended thinking and "deep research" generates a
"report" in response to a fairly well-crafted prompt asking for a
reasonable question about a product includes a long reasoning why it
couldn't find the required facts to answer even though the response and
progress reports extensively having "researched" both the vendor's web
site, user-forums, and the web at large (citing multiple sources no
less!), and then proceeds from this assumption to generate the rest of
the response —

This *might* be reasonable and certainly reads as such, who of us hasn't
made well-reasoned assumptions yet in the absence of facts? —

But the very fact the response implied just wasn't communicated anywhere
was clearly stated in the very link of the product page provided as part
of the prompt itself?

That is not surprising if you understand how they work at all, of
course.

But that's not hallucination, either.

From the perspective of the user, that's failure.

This is not a good use case for LLMs; but it is one they are explicitly
marketed for. I cringe whenever I see someone suggests to query an LLM
for facts or research them. (Unless, of course, they really go off and
cross-check all facts. Have you ever graded class work? Right.)

#### If everything you have is an LLM ...

... then everything must be a conversation, right?

This is why even my bank's very reasonable request for me to check my
contact details suggests only the path of "ask our AI chat bot for your
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

#### And the operators know:

Support chats now almost always include the disclaimer of "this is an AI
model. It can make mistakes.".

When I reach out to support, I want a correct answer. Or at least one I
can hold the company who I'm in contact with to account for.

[Over on LinkedIn I have argued that this is another case of holding the
tool
wrong](https://www.linkedin.com/pulse/dont-direct-your-users-chat-bots-support-lars-marowsky-br%C3%A9e-pcgoe/)
and that it can be done right, but the current common approach is simply
infuriating.

#### Facts can't be trusted

You have got to double-check every thing the generated response claims,
because you only get back a statistically likely answer relative to the
data the system was trained on, plus some intentional randomness.

(This may be particularly annoying to people in whose work and interests
facts very much do matter, and if I may be so snarky, I think a lot of
the LLM hype is generated by people who operate in spheres where the
shared reality is more subject to negotiation.)

The same is pretty much true for most other (generative) AI use cases,
from image generation to text transcripts and voice: that they appear
plausible to casual human inspection is not the same thing as them being
*correct*.

#### Not Fit For Purpose

Simply put: the models are **not** fit for the purposes they're marketed
and sold for.

And we have no known strategy to overcome these limitations.

Because they've suddenly developed these apparent capabilities at a
certain complexity and scale, we keep mostly throwing more scale at
it, while crossing our fingers.

We have collectively sunk trillions into this by now across all
dimensions, and while this yields improvements, the systems keep
generating vastly incorrect responses.

That is not the same as saying they are not useful; I kindly refer back
to the first part of this writing. And yet, there is an inflated
presentation that they do not yet deliver on.

## The Elephant in the Room

Let's come back to the elephant in the room: the harm.

- Generative AI incurs massive environmental costs.
- A lot of the labelling is done by underpaid and exploited workers.
- A lot of the content they're trained can only be considered IP theft
  (and _would_ be, if it wasn't done by billionaires).
- For Cloud-based Generative AI, the usual privacy concerns apply.
- Generative AI is marketed with dishonest, exaggerated claims.
- Generative AI is used as what can only be described a massive
  denial-of-service attack against our collective minds.

The problem with all of these?

They are appeals to morality, ethics, or external costs.

These only ever matter to businesses when politics creates policies and
regulations that are actually enforced by the judiciary and executive.

So yes, I agree. These and more are excellent reasons to oppose the use
of most generative AI.

But if you make any of these arguments to a leader in *business*,
they'll shrug, even if they agree, if it looks like they
create more profits for their shareholders with fewer pesky humans in
the loop.

(I totally respect that this is why you chose to not learn how to hold
the tool. But then be clear about this; make moral arguments if your
argument is moral, don't claim the tool doesn't and/or can't work.)

### Systemic Action Is Needed

These are arguments you need to make to politicians and as part of your
labour unions.

At a business level, even an individual, these have insufficient
traction. Neither individuals nor organizations are good enough™ for
this. And a few individuals or even organizations changing their minds
also has too little impact. We must address them systemically.

These harms are not inherent to LLMs per se. They are inherent to LLMs
driven by shareholder-first capitalism in the pre-regulation rush.

### The genie is out of the bottle

At the same time, I believe it is impossible to put the genie back into
the bottle. Yes, all these harms are real and horrible. And yet.

If knowing that was enough, most planes would be scrapped. There would
be no cars with ICE. Coal and gas power plants would have been shut off
three decades ago.

There is no going back. LLMs will be around, even if folks realize their
limits. Because they *are* useful.

We need them to be ethically and sustainably.

## In conclusion

*No, the emperor is not naked.* We must acknowledge this if we want to
have a meaningful conversation.

But.

*The emperor is wearing bloodied rags.* We must acknowledge this if we
want to move forward.

## Quo vadis?

This leaves us, and especially my own industry, in a risky quandary.

While useful, I have doubts that what these models can actually achieve
and deliver is worth their current level of investment.

Much less so if we do eventually end up factoring in what the vendors
currently get to consider "external costs" through regulation.

### The optimists could be right:

There is, of course, a nonzero chance that someone does find the holy
grail - not for "General Purpose AI", but just merely, you know, for
generative AI that doesn't make stuff up; or at least at a statistically
irrelevant level. A new algorithm, a new magic scale threshold.

### Or Else?

Should this fail to occur in the short- or mid-term, I suspect the
bubble will collapse **spectacularly**.

The dotcom bubble burst in the first few years of my career. It all went
great — until it didn't.

Right now, nobody in the industry can afford for this to happen.

Just like the real-estate-investors need Return-to-Office mandates so
the value of their office spaces doesn't collapse and make the subprime
crisis look tame, all the large investors in the tech world need us to
shove LLMs into everything to keep expanding; and pretend, hope, pray
that there is a path to success — and that we will find it.

There's a reason "AI" features are now in everything, besides people
actually believing the claims: the industry needs to show increasing
user counts. *Or else.*

## Brace.

My best guess? LLMs will still be around in a decade or two, and we'll
all use them for what they can do. (And yes, people will still oversell
them, just like with everything else.)

But *somewhen* between then and today, there'll be a supremely
uncomfortable half-decade or so.

