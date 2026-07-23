---
video_id: uCKhOmth2ms
title: The best AI agents are simpler than you think
channel: LangChain
url: "https://www.youtube.com/watch?v=uCKhOmth2ms"
watched_date: 2026-07-08
watched_at: "2026-07-08T22:23:09Z"
watch_count: 1
duration_seconds: 5246
source: youtube-history-browser
added_date: 
history_label: Today
history_order: 7
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 525
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Zack Wedeen, head of product at Sierra, discusses how the company builds customer experience agents for Fortune 20 companies by treating agents as full engagement platforms across the customer lifecycle—not just support. Sierra's architecture parallelizes thinking, listening, and talking using 10-15 models per conversation turn, with a declarative "journeys" no-code layer that compiles deterministically to code, enabling non-technical operations teams to build agents. The platform optimizes for voice (1-2 second response times), supports agent-to-agent communication via APIs and MCP protocols, and invests in isolated payment infrastructure (PCI DSS Level 1 certified) because agentic commerce will exceed traditional e-commerce.

For builders: leverage existing model strengths rather than forcing new abstractions—80% of the time, materialize agent knowledge into file systems and Git structures that LLMs already excel at, reserving custom training only for truly novel domains. If building voice or real-time agents, parallelize inference across multiple models (e.g., run transcription in parallel with classification and response generation) for reliability and latency. If enabling transactions, invest early in isolated payment infrastructure separate from your LLM calls, since no major LLM provider is PCI certified for direct payment handling.

## Transcript

[00:00:00] Agentic commerce will be bigger than
[00:00:02] e-commerce. There are cases where the
[00:00:04] Sierra agent is actually getting paid a
[00:00:06] commission on a sale.
[00:00:08] >> Today, I'm talking to Zack Reno Wedeen,
[00:00:10] head of product at Sierra, the platform
[00:00:13] powering customer experience agents for
[00:00:15] most of the Fortune 20.
[00:00:16] >> Coding agents are really good at file
[00:00:17] systems, they're really good at Git,
[00:00:19] they're really good at grep. Let's
[00:00:21] materialize everything into those
[00:00:23] structures so that coding agents can
[00:00:25] just, [music] you know, cook.
[00:00:26] >> He breaks down how Sierra builds for
[00:00:28] voice and why the architecture looks
[00:00:30] nothing like a standard agent harness.
[00:00:32] >> One of the big unlocks for Sierra agents
[00:00:34] was how to parallelize thinking,
[00:00:36] listening, and talking. And if this
[00:00:38] model says it's silent, you trust it. If
[00:00:40] this model does not say it's silent, you
[00:00:42] trust this one.
[00:00:42] >> We get into why a Sierra conversation is
[00:00:45] unlike a typical LLM call.
[00:00:46] >> You know, 10 or 15 different models
[00:00:48] might be invoked for a given
[00:00:49] conversation turn. So, sometimes you're
[00:00:51] classifying and you're responding at the
[00:00:54] same time.
[00:00:54] >> And Zack explains how and why Sierra
[00:00:57] built an entirely separate
[00:00:58] infrastructure layer for payments.
[00:00:59] >> We have isolated infrastructure where
[00:01:02] payment info doesn't go to an external
[00:01:04] large language model because none of the
[00:01:05] LLM providers are PCI certified in that
[00:01:07] way.
[00:01:08] >> Welcome to Max Agency, the podcast
[00:01:10] [music] that goes deep into how the best
[00:01:11] agents are being built by builders like
[00:01:14] you.
[00:01:15] >> [music]
[00:01:17] >> Most people are probably familiar with
[00:01:18] Sierra as a customer support platform.
[00:01:21] But, from what I understand, recently
[00:01:22] you guys are going broader than that.
[00:01:24] Could you talk a little bit about the
[00:01:25] types of agents that you help people
[00:01:27] build?
[00:01:28] >> Yeah, so this has been the vision since
[00:01:30] the beginning. I think because many
[00:01:31] companies have an RFP process where
[00:01:34] they're very specific about, "Hey, we
[00:01:36] want to solve customer service." That is
[00:01:39] often where we start, but we think of
[00:01:41] Sierra as the full engagement platform
[00:01:44] across all of the moments that matter
[00:01:46] for your customers. So, if you're an
[00:01:48] airline, that might be browsing for a
[00:01:50] flight, might be booking the flight,
[00:01:52] might be choosing your seat, might be in
[00:01:54] my case, I have a small dog, so adding a
[00:01:57] pet in cabin, then the flight might get
[00:01:59] rescheduled or delayed or
[00:02:02] cancelled, etc. etc. You need to get
[00:02:04] your bags there. There are just so many
[00:02:06] different things across that process.
[00:02:08] Some of them are sort of sales, some of
[00:02:10] them are more service, some of them are
[00:02:12] more loyalty, but they all kind of
[00:02:14] ladder up to the relationship between a
[00:02:16] business and its customers. And Sierra
[00:02:19] agents are present at all of these
[00:02:21] different parts of the customer life
[00:02:22] cycle. So, as an example,
[00:02:25] there are cases where the Sierra agent
[00:02:27] is actually, because of our
[00:02:29] outcome-based pricing model, getting
[00:02:31] paid a commission on a sale, which I
[00:02:34] think is quite different from how most
[00:02:35] people would imagine service. And so, we
[00:02:37] get really excited about those more
[00:02:40] exotic opportunities because they also
[00:02:41] give us an opportunity to push the
[00:02:43] platform forward and, you know, continue
[00:02:45] adding to what the platform can do, and
[00:02:48] kind of turn that into a product,
[00:02:50] package it up nicely, and bring more to
[00:02:52] all of our existing and future
[00:02:54] customers.
[00:02:54] >> How similar is the platform between
[00:02:57] these different use cases?
[00:02:58] >> I would say that
[00:03:01] it's very extensible, and so you can
[00:03:03] kind of take it in different directions.
[00:03:06] We like to say, I think it's originally
[00:03:08] attributed to the
[00:03:09] one of the creators of the programming
[00:03:11] language Pearl, but we try to make the
[00:03:13] easy things easy and the hard things
[00:03:15] possible. So, out of the box, pretty
[00:03:17] similar, the starting point, but you can
[00:03:20] kind of take it in any direction that
[00:03:21] you want. So, it's not that, oh, there's
[00:03:23] like a separate product for, you know,
[00:03:25] one company versus another, but the
[00:03:28] agents that you can build on it, and
[00:03:30] we'd like to think of these agents as
[00:03:32] products onto themselves, can be
[00:03:34] arbitrarily customized.
[00:03:36] >> What does it look like to build on the
[00:03:38] Sierra platform?
[00:03:40] >> So, we have a It's basically a web app.
[00:03:42] There's three main sections. There's
[00:03:44] analyze, build, and then there's
[00:03:46] release.
[00:03:47] Within the analyze section, you have
[00:03:49] things like our explorer agent, which is
[00:03:53] kind of the long-running ChatGPT deep
[00:03:55] research for all of your customer
[00:03:57] conversations and data. You have
[00:04:00] reports, you have monitors, which are
[00:04:02] kind of always-on evaluators of
[00:04:04] conversation data as well.
[00:04:06] And then within build, you have
[00:04:08] ghostwriter, which is the agent similar
[00:04:10] to Codex or Claude code for building
[00:04:12] agents.
[00:04:14] You also have journeys, kind of the
[00:04:15] underlying source code layer, although
[00:04:17] it's not really code. It's more like
[00:04:19] natural language or standard operating
[00:04:21] procedures. As well as kind of different
[00:04:24] variables
[00:04:26] and everything like that. On the release
[00:04:28] side, you have all of the collaboration
[00:04:31] and change management and governance
[00:04:33] procedures. And so Sierra, I think at
[00:04:35] this point we're working with most of
[00:04:37] the Fortune 20, something like 40 or 50%
[00:04:41] of the Fortune 50 or Fortune 100. So
[00:04:43] very much
[00:04:45] with a lot of the largest companies in
[00:04:46] the world. And they have needs around
[00:04:49] governance and release processes and
[00:04:51] change management that have just pushed
[00:04:54] us to develop from the very beginning,
[00:04:56] you know, very buttoned-up procedures
[00:04:58] and collaboration and review and all of
[00:05:00] this stuff. That's basically what it's
[00:05:02] like, I think, on the surface, but
[00:05:04] probably similar to a lot of other, you
[00:05:06] know, places that you go to build
[00:05:08] things, whether that's
[00:05:09] Figma or Claude code or these different
[00:05:12] places, but just very much optimized
[00:05:14] around no-code agent building and um
[00:05:18] giving you all those capabilities.
[00:05:20] >> And are those different steps intended
[00:05:23] to be done in that order? Like analyze,
[00:05:24] build, release. Can you analyze
[00:05:26] basically human transcripts before you
[00:05:28] build the AI agent? Or does analyze
[00:05:30] really come after you build and release
[00:05:31] the first version of the agent and now
[00:05:32] you're iterating on it?
[00:05:34] >> It's both. So, typically, you'll come in
[00:05:38] with some sort of resource of how you
[00:05:40] want the agent to be structured and
[00:05:43] architected, how you want it to behave.
[00:05:45] Maybe that's transcripts, maybe that's
[00:05:47] standard operating procedure, maybe
[00:05:49] that's a conversation that you have with
[00:05:51] Ghostwriter.
[00:05:52] And that will typically be how you build
[00:05:54] the agent. So, I'd say most people will
[00:05:56] start with build, but then once your
[00:05:58] agent is live and production
[00:06:01] conversations are happening, your daily
[00:06:04] routine probably starts more with
[00:06:06] analysis. You're probably thinking, how
[00:06:08] can I optimize the metric that I care
[00:06:10] about, whether that's customer
[00:06:11] satisfaction or resolution rate or in
[00:06:15] the case of the customer I mentioned,
[00:06:16] like sales converted.
[00:06:18] And so, you get those insights and then
[00:06:21] you want to make improvements to the
[00:06:23] agent, whether it's, you know, fixing an
[00:06:25] issue or finding a new opportunity to
[00:06:27] hill climb on a metric or please
[00:06:30] customers in one one more way.
[00:06:32] And so, that typically involves, you
[00:06:34] know, working with Ghostwriter. Often,
[00:06:37] Ghostwriter will actually proactively
[00:06:38] suggest an improvement on the insights
[00:06:41] to kind of close that loop and build
[00:06:42] that flywheel.
[00:06:44] Um, but I would say the day to day is
[00:06:45] more analyze, build, release.
[00:06:47] >> Who is doing that analyzing and that
[00:06:50] iterative improvement? Is this is this
[00:06:52] engineers? Is this product folks?
[00:06:54] >> It's primarily people that have the most
[00:06:58] depth and insight about the ideal
[00:07:00] customer experience, which tends to be
[00:07:03] operations uh people, so customer
[00:07:05] experience managers,
[00:07:07] um folks in that department at our
[00:07:09] customer companies.
[00:07:11] It's also a number of engineering teams
[00:07:15] will build either other agents that
[00:07:17] interface with Sierra agent or they can
[00:07:20] extend the platform
[00:07:22] uh via basically tools and packages that
[00:07:25] you can then kind of see and introspect
[00:07:26] on Sierra. So, it's very much kind of
[00:07:29] the same way that you have the person
[00:07:31] that knows everything about your
[00:07:33] knowledge base, we want them to be able
[00:07:34] to come in and self-serve on day one and
[00:07:36] just, you know, make the perfect
[00:07:38] instantiation of knowledge. The person
[00:07:40] who knows everything about the standard
[00:07:42] operating procedures should be able to
[00:07:44] just do that in the product. And so
[00:07:45] we're constantly kind of trying to sand
[00:07:47] down all of the barriers between the
[00:07:50] people with the most context and their
[00:07:52] ability to contribute directly to the
[00:07:53] platform.
[00:07:54] >> You've said no code a few times. So,
[00:07:57] what does this agent building experience
[00:07:59] look like? Is it truly no code? And And
[00:08:01] I'm assuming it's maybe something like
[00:08:04] quad code where you talk to it and it
[00:08:06] generates something under the hood. Is
[00:08:07] it generating code? Is it generating a
[00:08:09] custom DSL?
[00:08:11] >> Yeah, good question. So, the layers of
[00:08:12] the stack, you have kind of what we call
[00:08:14] Agent OS, which has our constellation of
[00:08:17] models. So, translating the tasks that
[00:08:20] need to be done on the platform
[00:08:22] into prompts, uh into data injection
[00:08:26] across, you know, 10 or 15 different
[00:08:28] models that might be invoked for a given
[00:08:30] conversation turn. Some of those might
[00:08:32] be frontier models that need to do, you
[00:08:35] know, top-tier reasoning. Some of them
[00:08:37] might be in-house models that are very
[00:08:39] good at a specific task, and some of
[00:08:41] them might be just, you know, classifier
[00:08:43] models that run really well on a
[00:08:46] uh a model that's a little bit cheaper
[00:08:47] and more performant. And so, that's kind
[00:08:49] of the base layer. On top of that, you
[00:08:52] have the Agent SDK, which is the
[00:08:56] code-based layer of agent orchestration
[00:08:59] and context management.
[00:09:01] That's kind of where Sierra started, but
[00:09:03] over the last 18 months, most of the
[00:09:06] agent development, um pretty much all of
[00:09:08] the agent development has shifted to our
[00:09:10] no code layer that we call journeys.
[00:09:13] It compiles down to Agent SDK code
[00:09:16] deterministically
[00:09:17] and uh isomorphically, which is a fancy
[00:09:19] word for you can turn it one way and
[00:09:21] then turn it back and it's the same. And
[00:09:23] so, you can have uh code that you
[00:09:26] transition over to no code, you can have
[00:09:27] no code that you transition over to
[00:09:29] code, but the language of specifying it
[00:09:32] is very much
[00:09:34] declarative. Here's how I want the agent
[00:09:36] behavior to be Uh when customers ask
[00:09:39] about this. We want to unlock these
[00:09:41] conditions and kind of flow in this
[00:09:42] direction and we find that that's pretty
[00:09:44] intuitive cuz it maps the type of
[00:09:46] document that we would write for someone
[00:09:48] joining the team in a customer
[00:09:50] experience role or sales role. You would
[00:09:52] explain to them how to do the job and
[00:09:54] that's kind of what you're doing here as
[00:09:56] well. But there is some DSL for
[00:09:58] journeys. It's not pure raw kind of like
[00:10:01] text.
[00:10:01] >> Correct.
[00:10:03] And it's very hard. I'm not sure we
[00:10:05] could get into a discussion about it. If
[00:10:07] you're just doing text, you have to
[00:10:09] choose between
[00:10:11] this is non-deterministically compiled,
[00:10:14] which all of the experiments we've done
[00:10:16] in that direction,
[00:10:18] you end up I think with more harm than
[00:10:19] good.
[00:10:20] Or this is a prompt engineering task,
[00:10:23] which then puts you in the realm of
[00:10:25] engineering teams. And we, you know, are
[00:10:27] very proud to be more in the realm of
[00:10:30] operations teams where a lot of that
[00:10:32] domain specific knowledge resides. The
[00:10:34] other big piece of it is that
[00:10:35] Ghostwriter has totally changed the
[00:10:37] learning curve for building agents. So
[00:10:39] you come in and you just say, "Hey, you
[00:10:41] know, I want to orchestrate order
[00:10:42] returns or I want to do flight booking
[00:10:45] or I want to do car rental or
[00:10:47] referral from primary care provider to a
[00:10:49] specialist." And Ghostwriter just kind
[00:10:52] of already knows those concepts and is
[00:10:54] an expert in journeys. But Ghostwriter
[00:10:56] is using the journeys product. So it's
[00:10:58] not writing code, it's writing journeys
[00:11:01] directly so that you can go inspect that
[00:11:03] after the fact as well.
[00:11:05] >> I imagine there's some there's some
[00:11:07] format that these journeys have to have
[00:11:09] to adhere to and I imagine that's not in
[00:11:11] the models training data at all. Was it
[00:11:13] hard to teach it that format or was it
[00:11:15] pretty easy?
[00:11:16] >> That's a really good question because at
[00:11:18] every point there's this conflict
[00:11:20] between here are the perfect
[00:11:22] abstractions for me
[00:11:23] and here are the abstractions that the
[00:11:25] models are most familiar with. And
[00:11:26] similar to in math how you're often
[00:11:29] taking one problem and reframing it in
[00:11:31] another problem to do a proof or
[00:11:32] something like that. You have to decide
[00:11:34] if you want to reframe this problem into
[00:11:36] something the models understand or build
[00:11:38] a skill and inject context in the right
[00:11:40] way so that the models can understand
[00:11:42] your way of thinking.
[00:11:44] The truth is that we do both. So there
[00:11:47] are cases where we'll say you know,
[00:11:49] coding agents are really good at file
[00:11:50] systems. They're really good at get.
[00:11:52] They're really good at grep. Let's
[00:11:54] materialize everything into those
[00:11:56] structures so that coding agents can
[00:11:59] just you know, cook. Then there are
[00:12:01] other cases where it's like, "No, no,
[00:12:02] no. Our way of thinking about this is
[00:12:05] the correct way of thinking about this
[00:12:07] and there's not really a way to shoehorn
[00:12:09] it into what it models are already good
[00:12:11] at. So let's do the investment to make
[00:12:13] the models good at this. My personal
[00:12:15] perspective is that 80% of the time you
[00:12:18] want to do the first thing
[00:12:20] and just meet the models of where they
[00:12:22] are on their turf and you should reserve
[00:12:24] the second one for that really special
[00:12:27] case. I'm curious uh if that's what been
[00:12:29] your experience as well.
[00:12:30] >> I think recently it's probably gotten to
[00:12:33] be we see a lot of people using the file
[00:12:35] system as an abstraction and so I think
[00:12:37] recently there's been a lot of talk
[00:12:38] especially as the labs talk about how
[00:12:40] they're RL-ing the models to be really
[00:12:41] good for their hardness to try to fit
[00:12:43] everything into a file system or this
[00:12:45] particular like edit file tool or things
[00:12:48] like that. I also think that the models
[00:12:50] are really good at writing certain
[00:12:52] packages. Like if you're in the training
[00:12:53] data, I think I think a lot of LangGraph
[00:12:55] is in the training data. So I think at
[00:12:57] least Anthropic models recommend
[00:12:58] LangGraph for a lot of use cases and
[00:12:59] that's great.
[00:13:00] But for newer things like deep agents,
[00:13:02] which is a new package we have, it's not
[00:13:03] in the training data at all. We spend a
[00:13:05] little bit of time, not maybe not as
[00:13:06] much as we should, but we spend a little
[00:13:07] bit of time thinking about what makes
[00:13:09] these models good at writing certain
[00:13:10] things. We really have no clue how to
[00:13:12] like affect know how to affect what goes
[00:13:13] in the training data, but it's a really
[00:13:15] interesting thing and so I think there's
[00:13:16] definitely been cases where we see that
[00:13:19] people choose technology because the
[00:13:21] models are really good at writing it.
[00:13:23] And so one question I was also going to
[00:13:25] ask for the agent SDK, I imagine that's
[00:13:27] you know, your own custom kind of like
[00:13:28] framework built in house. I don't know
[00:13:30] if you experimented with having It
[00:13:32] sounds like you didn't you you're not
[00:13:34] having Ghostwriter write that directly,
[00:13:36] but like that's obviously much more
[00:13:37] closer to code and so I was curious if
[00:13:39] you experimented with Ghostwriter or any
[00:13:41] model like writing agent SDK versus just
[00:13:43] writing like raw code. So, yes, um
[00:13:48] one of the things too is if you almost
[00:13:50] do the abstraction that the models are
[00:13:52] really good at, it can be overconfident
[00:13:54] or it can be familiar and successful.
[00:13:56] And so you have to be very thoughtful
[00:13:58] about going either all the way there or
[00:14:00] just not going there at all.
[00:14:02] >> Like you're saying agent SDK is
[00:14:03] somewhere in the middle and that might
[00:14:04] actually confuse it.
[00:14:05] >> Exactly. Exactly. Um
[00:14:07] we have kind of reinvented the agent SDK
[00:14:10] two or three times as models improve. So
[00:14:13] it used to be you had to have more
[00:14:15] deterministic guardrails in order to get
[00:14:17] the behavior that you want. Now there's
[00:14:19] more room for reasoning at each
[00:14:22] individual step and you can kind of push
[00:14:23] out the frontier of that reliability
[00:14:26] versus reasoning trade-off. So that's
[00:14:29] been very interesting. The reason for
[00:14:31] Ghostwriter primarily or entirely
[00:14:34] editing no code is just that that's
[00:14:36] where the vast majority of activity is
[00:14:39] on the platform today. So that's what
[00:14:41] our customers know and so making
[00:14:43] Ghostwriter good at it is really where
[00:14:45] all of the payoff is.
[00:14:47] I think if we tried to do it for code,
[00:14:49] it would be a a similarly scoped task,
[00:14:51] but it would be hard to get it to be
[00:14:53] really good at both at the same time.
[00:14:54] There's always going to be some
[00:14:55] trade-off.
[00:14:56] >> Do you still let users edit the agent
[00:14:58] SDK code if they want or is that now
[00:15:01] like completely abstracted away from
[00:15:02] them in terms of just pitch journeys?
[00:15:05] >> So the core agent SDK is part of the
[00:15:07] Sierra platform,
[00:15:08] but building agents in code is totally
[00:15:11] something you can do. One example is a
[00:15:13] number of our customers have CI/CD a
[00:15:16] continuous integration pipelines that
[00:15:18] they want to make sure their agent is
[00:15:20] released on. And so they need to get
[00:15:23] repository, which is where their agent
[00:15:25] lives. Another example is sometimes you
[00:15:27] have a particularly complex tool that
[00:15:29] has interacts with a streaming API or
[00:15:31] something in a way that is just easier
[00:15:33] to model in code than in no code. And
[00:15:36] so, the way that these work is because
[00:15:38] no code compiles down to code, you can
[00:15:41] kind of import or under the hood it will
[00:15:43] import code files and compiled no code
[00:15:45] files kind of all as though they're the
[00:15:46] same thing because they are.
[00:15:48] So, I think this is a benefit of
[00:15:50] starting out as a code-based platform is
[00:15:52] that we still support it. We have a
[00:15:54] number of customers that have dozens or
[00:15:56] in a few cases 100-plus developers
[00:15:59] building on the platform. And
[00:16:01] sometimes for that, you know, they work
[00:16:03] in Git, they release in Git. And so,
[00:16:05] being part of their enterprise change
[00:16:07] management protocol just means
[00:16:09] supporting Git.
[00:16:10] >> You mentioned that the agent SDK has
[00:16:12] changed over over the past few years as
[00:16:14] everything in the space has. Um,
[00:16:16] what does it look like now and how has
[00:16:18] it changed? What does that evolution
[00:16:20] look like?
[00:16:21] >> So, it started out we call this now
[00:16:23] flow-based, very much like, you know, do
[00:16:26] this. And it wasn't just like do these
[00:16:28] things. I think I'm a big fan of your
[00:16:30] not another workflow builder blog post.
[00:16:32] So, it wasn't that rigid, but it would
[00:16:34] be hey, you know, make sure you collect
[00:16:36] their email before you say that you're
[00:16:40] going to send them a confirmation email,
[00:16:42] right? Very clear to us, but you would
[00:16:45] want to do those things in that order.
[00:16:47] Now, I think if you think about just the
[00:16:49] way that agents can reason through tool
[00:16:51] calling,
[00:16:52] instead of having to specify that in the
[00:16:54] actual structure of your agent, you
[00:16:56] might just give it the context that in
[00:16:59] order to call this tool, you know, as a
[00:17:01] prerequisite you should have their
[00:17:02] email.
[00:17:03] And it will know how to ask for it. So,
[00:17:05] it's really like you'll just say that in
[00:17:06] the prompt. Yes.
[00:17:08] Or, you know, eventually all things end
[00:17:10] up in prompts, but it would be in the
[00:17:12] journey.
[00:17:13] And so, as you're kind of writing it
[00:17:15] out, you would specify that that's one
[00:17:16] of the rules or policies of the journey.
[00:17:19] And then the agent can take care of the
[00:17:22] rest. I think it's a mix of the models
[00:17:24] getting better and our orchestration
[00:17:26] platform becoming even more
[00:17:28] sophisticated and robust. So, when I
[00:17:29] talk about that constellation of models,
[00:17:32] there's a lot of We talked a little bit
[00:17:34] before about Linnaeus and Darwin.
[00:17:36] There's post-training that goes into
[00:17:37] that. There's model selection and eval
[00:17:40] and prompt engineering as well. And so,
[00:17:43] I think it's it's kind of equal parts
[00:17:45] model improvements and platform
[00:17:47] improvements.
[00:17:47] >> I want to talk about this model in a
[00:17:48] second, but I want to stay on the
[00:17:49] harness for a little bit. How similar
[00:17:51] does it look like in its current form to
[00:17:53] a coding agent harness? Does it have
[00:17:55] access to skills and sub-agents in the
[00:17:57] same way that someone using Claude code
[00:17:59] would would have?
[00:18:00] >> So, the one
[00:18:02] constraint we have that Claude code
[00:18:05] doesn't have is latency. Majority of
[00:18:07] Sierra conversations are voice. And if
[00:18:10] you're not responding in 1 or 2 seconds,
[00:18:12] then people wonder where you went. And
[00:18:15] so,
[00:18:16] we are highly optimized for these low
[00:18:17] latency use cases. There's a ton of
[00:18:19] parallelism.
[00:18:21] That being said, at a high level, it is
[00:18:23] using a lot of the same models. It has
[00:18:26] access to tools. Um so, there's a lot of
[00:18:28] similarities. There are also, you know,
[00:18:31] you can invoke other agents from the
[00:18:33] Sierra agent. So, the core What's best
[00:18:34] for the core conversation loop isn't
[00:18:37] typically what's best for software
[00:18:39] development. But you might want to say,
[00:18:41] "Hey, let me actually give you a
[00:18:43] callback in 20 minutes after I figure
[00:18:45] this out." And then you would have a
[00:18:47] type of loop that runs, you know, more
[00:18:48] like Claude code.
[00:18:49] >> And for those for those longer loops
[00:18:51] that might happen in the background, are
[00:18:53] those also built on the Sierra platform
[00:18:55] and are just a separate type of agent
[00:18:57] that remove the latency constraint?
[00:18:58] >> You can do it either way. So, you could
[00:19:00] have a Sierra agent calling out to
[00:19:03] another Sierra agent or you could also
[00:19:05] have a Sierra agent calling out to an
[00:19:07] in-house platform. And because so many
[00:19:09] of our customers have their own
[00:19:11] technology teams and a robust array of
[00:19:15] different AI projects internally.
[00:19:17] They might be experts in a particular
[00:19:20] area. Like they might have document
[00:19:22] generation handled themselves and that
[00:19:24] might be a long-running agent and then
[00:19:25] the Sierra agent can call out to it and
[00:19:28] wait for a response. So it's kind of up
[00:19:29] to you to choose and we find that
[00:19:32] enterprises are varied enough that they
[00:19:34] appreciate kind of having choice.
[00:19:35] >> When you do these agent-to-agent
[00:19:37] communications, are you are you using
[00:19:40] A2A or one of the protocols specifically
[00:19:42] for that or MCP or just an in-house, I
[00:19:45] don't know, REST API call?
[00:19:47] >> The most common is an API call. When you
[00:19:49] know who you're talking to in advance,
[00:19:51] often times you can save a lot of tokens
[00:19:54] and make sure that you're 100% accurate
[00:19:56] that way. That being said, Sierra agents
[00:19:59] support the MCP and agent-to-agent
[00:20:02] protocols. You can kind of install that
[00:20:04] integration and then your agent can be
[00:20:06] an MCP client. You can also set up your
[00:20:08] agent to be an MCP server. So this is
[00:20:10] how we support ChatGPT apps
[00:20:13] uh which rely on MCP servers. Basically,
[00:20:16] the tools of the agent can be made
[00:20:18] available to ChatGPT and then you can
[00:20:20] at-reference a Sierra agent. The example
[00:20:23] uh that would be most familiar is
[00:20:24] Redfin.
[00:20:26] Um if you do if you go to redfin.com and
[00:20:28] do their AI search, uh under the hood,
[00:20:31] it is a Sierra agent that is returning
[00:20:33] the home listings and having the
[00:20:35] conversation with you and that agent is
[00:20:37] also, I believe, available in ChatGPT.
[00:20:40] >> Interesting. I I didn't realize that
[00:20:42] Sierra agents could be ChatGPT apps. Is
[00:20:45] that the right terminology for them?
[00:20:46] >> It is. Yeah, exactly.
[00:20:48] >> Do you have Do you have an opinion or
[00:20:50] hot take on in the future, do you think
[00:20:52] people will be interacting with the
[00:20:55] agents that represent brands on
[00:20:57] dedicated chatbot websites or in uh
[00:21:00] ChatGPT or central chat engine?
[00:21:03] >> I think that agentic commerce will be
[00:21:06] bigger than e-commerce.
[00:21:08] So, if I think about how I get things
[00:21:10] done today, it used to be that I went to
[00:21:12] websites and clicked around. Now, I ask
[00:21:16] Codex or Claude to do things for me.
[00:21:19] And I don't see why I won't do that to
[00:21:21] manage my subscriptions, to order
[00:21:23] supplies to my home, to make dinner
[00:21:25] reservations. It just feels like that's
[00:21:28] where we're headed.
[00:21:29] And so, if that's happening, I think
[00:21:31] brands will want to be ready on the
[00:21:33] other side of that. So, we're very much
[00:21:35] planning for that world. We were
[00:21:37] investing in payments before it made
[00:21:40] sense, I think, and it's a long process,
[00:21:43] but a few months ago, we announced, you
[00:21:46] know, we're uh fully PCI DSS level one
[00:21:49] certified.
[00:21:50] >> no clue what that means. What does that
[00:21:51] mean?
[00:21:52] >> payment card industry.
[00:21:54] >> Okay.
[00:21:54] >> Um oh, man, you stump me on DSS. Uh
[00:21:57] [laughter]
[00:21:58] I have uh some of the other acronyms um
[00:22:00] in my head, but um
[00:22:01] >> We'll We'll put it in in post.
[00:22:03] >> Okay. Okay, thanks. Oh, man, it must be
[00:22:05] like digital
[00:22:07] I don't know. I know that the We were uh
[00:22:09] certified by a QSA, which is a qualified
[00:22:11] security assessor. And uh what that
[00:22:14] means is we're able to do the only voice
[00:22:17] payments platform, certainly at launch,
[00:22:19] I think still this is the case, where
[00:22:21] you don't need to transfer to another
[00:22:23] platform. So, it's a co- cohesive
[00:22:25] experience throughout checkout. And all
[00:22:28] the work that went into that, we have
[00:22:29] isolated infrastructure where the
[00:22:32] payment info doesn't go to a large
[00:22:34] language model, doesn't go to an
[00:22:36] external large language model, because
[00:22:37] we have none of the LLM providers are uh
[00:22:39] PCI certified in that way.
[00:22:41] And so, putting that all together is
[00:22:43] like spinning up a separate cluster, you
[00:22:45] know, getting certified, um making sure
[00:22:47] all of our operational rituals, you
[00:22:49] know, conform to what the security
[00:22:51] assessor is looking for.
[00:22:53] And we put in that work because we
[00:22:55] believe in this future where agentic
[00:22:56] commerce is actually bigger than
[00:22:59] e-commerce. And I think e-commerce is in
[00:23:01] the hundreds of billions of dollars at
[00:23:03] this point, couple percentage points of
[00:23:04] GDP or something like that just in the
[00:23:06] US. And so if you think about that
[00:23:09] space, um it's pretty big.
[00:23:11] >> And by agentic commerce, do you mean
[00:23:13] like chat GPT talking to uh Sierra agent
[00:23:17] that represents Redfin, or do you mean
[00:23:19] someone going to Redfin's agent no
[00:23:21] matter where it is and talking with it
[00:23:23] there?
[00:23:24] >> Both, both. I do think that the majority
[00:23:27] of this will be from personal agents.
[00:23:30] Just looking at user behavior, we spend
[00:23:33] so much time in Claude and chat GPT and
[00:23:36] Codex
[00:23:38] that you have to think that's where a
[00:23:39] lot of that behavior will accrue.
[00:23:42] >> And do you think those agents will
[00:23:43] interact with another agent? Why not
[00:23:46] just the raw APIs themselves?
[00:23:48] >> I do. I think that as you think about
[00:23:51] being ready for that world,
[00:23:53] um the same way that you might want to
[00:23:57] use Shopify or you might want to use
[00:24:01] certain software on your website to do
[00:24:03] product recommendations, to do checkout,
[00:24:07] uh you might want to use Stripe.
[00:24:08] Similarly, you'll want to use a platform
[00:24:11] that can make sure that you're
[00:24:12] presenting your products in the right
[00:24:15] way, that you're making checkout as easy
[00:24:16] as possible, and that you're showing up
[00:24:19] at your best, whether it's for a
[00:24:21] customer that's browsing or for an agent
[00:24:23] that's browsing. The one thing that I
[00:24:24] think is pretty different is the
[00:24:26] attention
[00:24:28] isn't necessarily valuable in the same
[00:24:30] way.
[00:24:31] Like our eyeballs are more valuable than
[00:24:34] an agent just, you know, spewing out
[00:24:36] tokens assuming that no one's ever going
[00:24:37] to look at it. At least I think that's
[00:24:39] true for now. At some point it lands up
[00:24:41] in some future training run and maybe
[00:24:43] has value, but I think that's de minimis
[00:24:45] relative to getting us to look at
[00:24:47] things. And so I do feel like maybe
[00:24:49] that's a bit different, but the
[00:24:50] presenting yourself in the right way,
[00:24:52] making it easy to check out, making it
[00:24:54] easy to understand what products are
[00:24:55] available, to express the preferences of
[00:24:58] whoever is responsible for that agent
[00:25:01] going off and doing something
[00:25:02] commercial. That all still feels
[00:25:04] relevant to me. I've seen some dev tools
[00:25:06] provider, I think Sentry, doing a
[00:25:08] similar thing where they have a bunch of
[00:25:10] APIs, obviously, for the underlying
[00:25:11] platform, but they also have an endpoint
[00:25:14] to just ask questions of the agent
[00:25:15] directly. And I think you could make a
[00:25:17] counterargument that like, great, brands
[00:25:18] should absolutely care about how the
[00:25:20] platform's being used and how it's being
[00:25:22] presented, but you could do that with
[00:25:23] skills or or some other mechanism to
[00:25:25] expose that to the agent. And I I
[00:25:26] honestly don't know which one's right,
[00:25:28] but it it has been interesting to see
[00:25:30] the whole space is so new, but
[00:25:31] increasingly so companies exposing
[00:25:32] agents as endpoints to interact with
[00:25:34] rather than the endpoints themselves.
[00:25:36] >> I agree. I think that all of this stuff
[00:25:39] you could try to do it yourself. It
[00:25:40] might be that certain companies, that's
[00:25:42] the best option.
[00:25:44] What we've seen is that because there's
[00:25:47] often tens or hundreds of millions of
[00:25:49] dollars on the line, in some cases
[00:25:51] billions of dollars on the line, you
[00:25:53] really want to make sure you're getting
[00:25:54] the best solution. And so if you're
[00:25:56] going to be 90% as good at it as you
[00:25:59] could be partnering with a company like
[00:26:01] Sierra,
[00:26:02] it still makes sense to partner and, you
[00:26:05] know, get that extra few billion
[00:26:07] dollars.
[00:26:08] >> One last question on this fun side
[00:26:10] tangent, payments. How early are we?
[00:26:12] >> I think we're really early.
[00:26:13] I personally still don't order paper
[00:26:17] towels with Codex. I don't know if you
[00:26:20] do.
[00:26:20] >> No, and that's why I asked. I'm glad
[00:26:21] that you said that cuz I know I'm not
[00:26:23] close to doing that. And so I was
[00:26:24] wondering how far behind I was.
[00:26:26] >> I mean, yeah, like
[00:26:28] I also didn't do it with Alexa. You
[00:26:30] know, I think for some of that really
[00:26:31] easy stuff, you could probably have done
[00:26:33] it already.
[00:26:34] The one that I think will definitely
[00:26:36] become a thing is there are a lot of
[00:26:38] apps that claim they can, you know, go
[00:26:40] through all of your subscriptions and
[00:26:41] cancel the ones that you're not using.
[00:26:44] That feels like as a consumer, that's a
[00:26:45] useful service. I'm definitely closer to
[00:26:48] doing that with Codex than I am
[00:26:51] with an app. You know, it would it would
[00:26:53] be so much work to tell it all the
[00:26:55] things and try to tell it which ones to
[00:26:57] cancel. It's a very manual process.
[00:27:00] If I gave Codex or Cloud Co-worker or
[00:27:02] something just access to my browser and
[00:27:04] said,
[00:27:05] "Hey, you know, go to all of the
[00:27:06] streaming apps and like the ones that
[00:27:08] I'm not logging into,
[00:27:11] just, you know, cancel those and let me
[00:27:13] know if you need my password." And
[00:27:15] obviously you have to figure out how to
[00:27:16] make that secure and everything. But I
[00:27:18] feel like that I would have demand for
[00:27:20] that product.
[00:27:21] >> Going back to the harness for a little
[00:27:23] bit, you said something earlier about
[00:27:25] things running in parallel. Is that like
[00:27:26] guardrails that you're running or
[00:27:28] retrieval steps or what's running in
[00:27:30] parallel in in this process?
[00:27:32] >> So many things. One example, knowledge.
[00:27:35] We will
[00:27:37] often look up answers before we know if
[00:27:40] we want them.
[00:27:41] So you'll, you know, before you decide
[00:27:43] whether this question needs an answer,
[00:27:45] you'll at least have the answer ready or
[00:27:47] in parallel with deciding. So sometimes
[00:27:49] you're classifying and you're responding
[00:27:52] at the same time. Basically speculative
[00:27:53] execution.
[00:27:55] Another example would be transcription,
[00:27:57] what we call ensembling.
[00:27:59] Um I think we might have published a
[00:28:01] blog post on this today, which is great.
[00:28:03] Go read it. We've learned so many things
[00:28:06] from being a
[00:28:08] uh modular architecture on voice. This
[00:28:11] was an early decision we made that I
[00:28:13] think has totally played out to our
[00:28:15] advantage where we have the ability for
[00:28:18] any language, for any customer, for any
[00:28:21] use case to multi-home providers
[00:28:25] uh across transcription, across
[00:28:27] synthesis, and across native uh
[00:28:29] voice-to-voice models. And so on the
[00:28:31] transcription side, for example, it just
[00:28:33] turns out uh when you have a thick UK
[00:28:36] accent from northern UK or at least
[00:28:39] parts of northern UK. I don't know
[00:28:40] exactly the region.
[00:28:42] There is one model that has the highest
[00:28:44] quality transcription,
[00:28:46] but it hallucinates during silence more
[00:28:48] than other models.
[00:28:50] So, we run two models in parallel.
[00:28:52] And if this model says it's silent, you
[00:28:54] trust it. If this model does not say
[00:28:56] it's silent, you trust this one. And so,
[00:28:58] that's just an example where we're
[00:29:00] running those in parallel. Uh we have
[00:29:02] logic for when you take the right one,
[00:29:04] and it's very specific. And if you had,
[00:29:07] you know, all your chips in with one
[00:29:09] provider or one system, uh or you
[00:29:12] weren't doing things in parallel, you
[00:29:14] would inevitably hit the limits of what
[00:29:16] that provider can do. So, the same way
[00:29:18] we use Claude and Gemini and the
[00:29:20] GPT-class models, we're also able to use
[00:29:23] all of the leading players on the
[00:29:25] transcription and synthesis and
[00:29:27] speech-to-speech side as well.
[00:29:28] >> You mentioned you have some in-house
[00:29:29] models as well. What do those models do,
[00:29:32] and why did you guys decide to build
[00:29:34] those in-house?
[00:29:35] >> So, uh knowledge is a great example. I
[00:29:38] think whenever we are pushing the limits
[00:29:40] of what's possible, we always consider
[00:29:43] whether we should build this in-house
[00:29:45] whenever it's limiting our ability to
[00:29:47] deliver more for our customers.
[00:29:49] So, an example where we're probably not
[00:29:52] the company is these, you know, many
[00:29:54] millions of dollar training runs that
[00:29:56] produce the GPT-5.5 class models. And,
[00:30:00] you know, Mythos, I'm sure is a many,
[00:30:02] many millions or tens or hundreds of
[00:30:04] millions of dollars training run um to
[00:30:06] get that produced. And that's stuff that
[00:30:08] OpenAI and Anthropic are just the best
[00:30:10] in the world at.
[00:30:11] I think what we're the best in the world
[00:30:13] at is going really deep with customers,
[00:30:15] understanding all of the process
[00:30:17] knowledge uh specific to their industry,
[00:30:20] specific to their company, specific to
[00:30:22] their customer base.
[00:30:24] And then having the products that can
[00:30:26] allow them to serve those customers as
[00:30:28] best as possible. And so, an example
[00:30:30] like knowledge where we were hitting the
[00:30:32] limits of the retrieval and reranking
[00:30:35] that we could do with out-of-the-box
[00:30:36] models, we asked the question of, you
[00:30:39] know, should we create our own models
[00:30:40] here
[00:30:41] um and eval them. And we have a research
[00:30:43] team that's pretty sizable and tightly
[00:30:46] integrated with our product teams. And
[00:30:48] so, we can flex that muscle when we need
[00:30:50] to, but we try not to be doing it just
[00:30:52] for the sake of doing it.
[00:30:54] >> You mentioned something like every run
[00:30:55] of the agent would have 10 to 15
[00:30:57] different model calls. If you had to
[00:30:59] guestimate like how many of those are
[00:31:01] frontier model calls versus like
[00:31:02] in-house fine-tune versus not frontier
[00:31:05] model but but third party?
[00:31:07] >> So, for a typical, um, turn of a
[00:31:09] conversation, I would guess that and
[00:31:13] this is just ballpark, but, you know,
[00:31:15] being, uh, precise rather than being
[00:31:17] accurate. Uh, I think maybe a couple
[00:31:20] frontier model, a handful of classifiers
[00:31:24] that probably don't require that, a
[00:31:26] handful of speculative execution in the
[00:31:28] case of voice in particular to make sure
[00:31:30] that it's low latency. Um, sometimes
[00:31:33] there will be an interim response that's
[00:31:34] generated to, you know, the same way
[00:31:36] you'd say, "Hold on a minute, I'm just
[00:31:37] pulling up your account." Like that kind
[00:31:39] of thing. Roughly like a third a third a
[00:31:41] third or a quarter quarter quarter, but
[00:31:43] I would say the frontier models just
[00:31:45] because they might be slower or more
[00:31:49] expensive would probably be, you know,
[00:31:52] more doing the bulk of the reasoning but
[00:31:54] in one or two inferences for a given
[00:31:56] conversation turn.
[00:31:57] >> Do you ever end up training models
[00:31:59] specific to a customer?
[00:32:01] >> It's not something that would be out of
[00:32:02] the question, but I can't think of a
[00:32:04] specific example. The reason I pause is
[00:32:07] because we do have our agent data
[00:32:09] platform
[00:32:11] and there are machine learning models
[00:32:13] that power strategies that are specific
[00:32:16] to customers. But in terms of like a,
[00:32:18] uh,
[00:32:19] you know, language model or generative
[00:32:21] model, we don't have cases of that.
[00:32:23] >> What's the agent data platform and what
[00:32:25] does it power?
[00:32:26] >> Basically, one thing we realized pretty
[00:32:28] early on is large language models are
[00:32:30] really good at in the moment empathy.
[00:32:32] Oftentimes better than we are of
[00:32:33] understanding, okay, you You I
[00:32:35] understand you're having a hard time.
[00:32:36] I'm really sorry about that. And it's
[00:32:38] the same way when you walk into
[00:32:40] a restaurant that has amazing service or
[00:32:43] a hotel that has amazing service, they
[00:32:45] recognize the moment you walk in, okay,
[00:32:48] this person just got off a really long
[00:32:49] flight or this person's 10 minutes late
[00:32:52] to their reservation and they were stuck
[00:32:54] in traffic and I'm just going to let
[00:32:55] them know that that is not a problem.
[00:32:57] Their table is ready.
[00:32:59] And large language models have that,
[00:33:01] especially on a platform like Sierra.
[00:33:03] But they don't necessarily know what you
[00:33:05] care about at a level deeper than that.
[00:33:08] And oftentimes the previous generation
[00:33:10] of AI or recommender systems have a
[00:33:13] better understanding of some of those
[00:33:14] things.
[00:33:16] And so what Agent Data Platform does is
[00:33:18] it can either integrate with your
[00:33:20] customer data platform, all your
[00:33:21] internal systems, or you know, you can
[00:33:24] have it just on Sierra or you can do
[00:33:25] sort of a zero copy integration.
[00:33:28] And it can take that structured data
[00:33:31] that knows what to recommend along with
[00:33:33] the here and now and now in the use
[00:33:34] those to
[00:33:38] generate uh better conversations, better
[00:33:42] uh orchestrations around how you want
[00:33:44] customers to feel and what you want to
[00:33:46] do for them.
[00:33:47] Um so that all sounds maybe a little bit
[00:33:49] abstract. Uh one example would be during
[00:33:52] sales. Oftentimes there's structured
[00:33:54] data that knows the right offer to
[00:33:55] present, but doing it just with that
[00:33:58] structured data with the previous
[00:34:00] generation of AI and before Sierra feels
[00:34:02] very stilted or it feels like you know,
[00:34:05] I don't know why you're doing this. And
[00:34:07] so large language models can really
[00:34:09] understand how to present an offer,
[00:34:12] uh how to attribute it, weigh two
[00:34:14] different offers based on conversation
[00:34:16] context and pick the right one for the
[00:34:17] moment and that kind of thing. So we see
[00:34:19] it a lot with sales, with loyalty and
[00:34:21] retention, those types of conversations.
[00:34:23] >> One of the last agents we haven't talked
[00:34:25] about too much is Explorer.
[00:34:27] >> Yes.
[00:34:27] >> What is Explorer? What does it look like
[00:34:29] under the hood?
[00:34:30] >> I've described it as chat GPT deep
[00:34:32] research uh for all of your customer
[00:34:34] context and conversations and all of the
[00:34:36] data on Sierra. And so what it allows
[00:34:38] you to do
[00:34:39] is basically instead of having to go
[00:34:41] spelunking for the specific insight in
[00:34:44] reports or in monitors, you can just ask
[00:34:47] the question. You can say, "Hey,
[00:34:49] I noticed my resolution rate dipped, you
[00:34:51] know, why was that?" Or "How can I
[00:34:53] generate more sales?" Or
[00:34:55] "I wish that more people were converting
[00:34:57] from trial to, you know, full-time paid
[00:35:00] plan. How come that's not happening?"
[00:35:03] And then more than that, you can set up
[00:35:04] automations so that, you know, on a
[00:35:06] daily basis, for example, Explorer can
[00:35:09] ask the same questions proactively.
[00:35:11] And then partner with Ghostwriter. We
[00:35:14] currently think of these as kind of two
[00:35:15] separate agents, the analysis agent and
[00:35:18] the authoring agent,
[00:35:20] to say, "Oh, here are some fixes that
[00:35:22] are suggested to improve." And you can
[00:35:23] chat with Ghostwriter and kind of pick
[00:35:25] it up from there. Under the hood where
[00:35:27] this is converging, I think is a shared
[00:35:29] harness that is an expert at using Agent
[00:35:31] Studio,
[00:35:33] Sierra's platform. Um and so that's kind
[00:35:35] of what we've been setting up in terms
[00:35:37] of what we talked about at the
[00:35:38] beginning, like,
[00:35:39] you know, figuring out the file system
[00:35:41] architecture that maps to the product.
[00:35:44] Um and so as we've exposed more and more
[00:35:47] tools,
[00:35:48] um you know, like building knowledge
[00:35:49] bases to these agents, they get more and
[00:35:52] more powerful and we see a lot of
[00:35:54] emergent behavior between both.
[00:35:55] >> Does this harness end up looking more
[00:35:58] similar to like a coding agent harness
[00:36:00] than the the harness that's part of
[00:36:02] Agent OS or Agent SDK?
[00:36:04] >> Yes. Um so this is less of a quick-turn
[00:36:07] conversational agent and more of a
[00:36:09] longer-term deep analysis agent. And so
[00:36:13] it ends up looking a lot more like a
[00:36:15] cloud coder or Codex.
[00:36:16] >> One of the things I've been thinking
[00:36:17] about, I'm curious if you have a take
[00:36:18] here.
[00:36:19] In a year, two years, three years, will
[00:36:22] there be the split just in terms of
[00:36:24] harness? Ones that's optimized for kind
[00:36:26] of like, yeah, lower latency, external
[00:36:28] facing, customer experience type things.
[00:36:31] Voice is maybe heavily involved. And
[00:36:33] another that's really focused on these
[00:36:34] deep research, maybe coding, like you're
[00:36:36] running in a sandbox, things like that.
[00:36:38] Or will just end up converging into one
[00:36:39] harness that, you know, depending on how
[00:36:41] you prompt it or, you know, has these
[00:36:43] async sub-agents in the background that
[00:36:45] can maybe run for longer periods of
[00:36:46] time.
[00:36:47] >> I think there will always be latency,
[00:36:49] performance, cost tradeoffs and
[00:36:52] different architectures that emerge
[00:36:54] because of that.
[00:36:55] I've actually been surprised by how many
[00:36:58] different types of model companies there
[00:37:00] still are.
[00:37:01] And when I talk to people who are
[00:37:03] particularly AGI filled about it and I
[00:37:05] say, "Hey, what's like a cool model
[00:37:08] opportunity that's not flying like so
[00:37:10] close to the sun that the labs will do
[00:37:12] it?" They'll say, "Oh, well, you'll just
[00:37:14] ask, you know, GPT-12 to make that
[00:37:16] model, so it's actually not a big
[00:37:17] opportunity." But I think in reality, at
[00:37:20] least up until now, I'll probably look
[00:37:23] dumb when AGI comes out.
[00:37:25] >> [laughter]
[00:37:26] >> You do see a lot of success in areas
[00:37:29] like voice models from transcription to
[00:37:32] synthesis. You don't always see
[00:37:34] leadership from the model labs. You see
[00:37:36] the model labs actually trying to focus
[00:37:38] more on specific problems. For
[00:37:40] Anthropic, I think it's coding. For
[00:37:42] OpenAI, it's been consumer, now maybe
[00:37:44] shifting a little bit more to
[00:37:45] enterprise. Um for Google, definitely
[00:37:48] consumer as well. And it really does
[00:37:50] feel like there are still tradeoffs to
[00:37:52] me. So, I expect there will still be
[00:37:54] multiple architectures up until that
[00:37:57] event horizon of AGI's here, so all bets
[00:37:59] are off.
[00:38:00] >> As you guys build your core agent
[00:38:02] harnesses, and I'm assuming one to build
[00:38:04] them in a model agnostic way, what do
[00:38:06] you need to change to go from an OpenAI
[00:38:08] model to an Anthropic model?
[00:38:10] >> Usually, you have the evals that are
[00:38:12] designed to work across both. So, if you
[00:38:13] have really good evals and a really good
[00:38:15] harness, a really good architecture,
[00:38:18] then you should be able to kind of hill
[00:38:19] climb toward eval performance without
[00:38:22] too much effort. Often what will happen
[00:38:24] is you'll learn the first time you're
[00:38:26] switching one task from one to another
[00:38:28] or making it possible to run on multiple
[00:38:30] systems that your eval wasn't quite as
[00:38:33] good as you thought. And so then you
[00:38:34] make your eval better and you continue
[00:38:36] to improve. But the short answer is that
[00:38:38] it's pretty simple for a given
[00:38:42] intelligence level of a model
[00:38:44] to run a task on one or the other. And
[00:38:48] so again it's that basically latency
[00:38:50] quality cost trade-off, but not more
[00:38:52] than that. And because we have customers
[00:38:54] that have very specific requirements
[00:38:56] around what clouds they can run in, what
[00:38:59] models they can use, and our
[00:39:02] company approach is to meet them, you
[00:39:04] know, on their terms. You don't serve
[00:39:07] most of the Fortune 20 without that
[00:39:08] approach. It's not really a choice.
[00:39:11] And so because that's our approach and
[00:39:13] we've built a lot of products around
[00:39:14] that, we also have made sure that we can
[00:39:16] kind of move between models of
[00:39:18] comparable intelligence without too much
[00:39:20] heartburn.
[00:39:21] >> And what do you end up changing when you
[00:39:22] hill climb? Is it just the prompts? Do
[00:39:24] you also change out some of the tools
[00:39:26] themselves?
[00:39:27] >> It depends on the case. And I might not
[00:39:29] be the expert on the exact history of
[00:39:32] each. I would I think that if you change
[00:39:34] the tools,
[00:39:36] it's pretty hard not to have downstream
[00:39:38] effects of that. And there might be
[00:39:39] certain tasks that can only run on
[00:39:41] certain models
[00:39:43] and other tasks that can run on other
[00:39:45] models. And so there's always kind of a
[00:39:47] set of eligible models for specific
[00:39:49] tasks. I don't know exactly how tools
[00:39:52] change, but I know the eval getting more
[00:39:54] robust and the prompt, you know,
[00:39:56] conforming to the quirks of each model
[00:39:58] is definitely part of the development.
[00:40:01] >> You guys recently wrote a blog around
[00:40:03] context engineering and I think you said
[00:40:05] it was the key to great agent building
[00:40:07] or something like that. How do you guys
[00:40:09] think about context engineering and and
[00:40:11] and what, you know, tips or tricks would
[00:40:12] you have for others?
[00:40:14] >> I think it's showing agents everything
[00:40:16] they need to do the right thing, but
[00:40:18] nothing more.
[00:40:20] And as models get smarter, you can be
[00:40:24] a little bit less precise with
[00:40:26] everything they need, and certainly less
[00:40:27] precise with nothing more. So, early on
[00:40:30] it was
[00:40:31] the agent SDK was really about only
[00:40:33] giving the model exactly what it needed
[00:40:35] and kind of spoon-feeding the context.
[00:40:37] Now, to extend the uh meal analogy, it's
[00:40:40] probably more like, you know, putting
[00:40:42] out the right dish. And maybe in the
[00:40:43] future, it might be something that is
[00:40:46] even less structured. One concept that I
[00:40:48] think is in that blog post is kind of
[00:40:50] progressive disclosure. You'll probably
[00:40:52] know more about this than I do, but
[00:40:54] when you bring something into the
[00:40:56] prompt,
[00:40:58] you don't want to do it before it's
[00:40:59] relevant, and then you also risk
[00:41:02] incoherence if you then yank it out of
[00:41:04] the prompt. So, when you do things like
[00:41:06] prompt compaction, you just want to be
[00:41:08] really thoughtful about not making it
[00:41:10] lossy, because if you keep something in
[00:41:12] the history that is
[00:41:14] incoherent with the rest of the system
[00:41:16] prompt, it's not going to end well. And
[00:41:19] so, I think to the degree, you know,
[00:41:21] when we're fixing uh
[00:41:24] issues, or when when we've seen
[00:41:25] hallucinations, it's often because one
[00:41:28] part of the prompt was this, and the
[00:41:29] other part was this. And actually, one
[00:41:31] of my main learnings from Sierra is
[00:41:34] anytime you think the model's being
[00:41:36] dumb, it's probably you.
[00:41:39] >> I like that. I think that I I think a
[00:41:40] lot of people have learned similar
[00:41:42] lessons from doubting the model.
[00:41:43] >> the model's too dumb, the model's
[00:41:45] actually too smart.
[00:41:46] >> How much you guys care about prompt
[00:41:48] caching and maintaining that cache? I've
[00:41:50] heard I've heard kind of like two
[00:41:52] mindsets on it. One is like, yeah, do
[00:41:54] everything you can to maintain the
[00:41:55] cache, like don't invalidate it until
[00:41:57] you like absolutely need to. And then
[00:41:59] I've heard another theory that's
[00:42:00] basically like, yeah, prompt caching's
[00:42:01] great, but like what matters most is
[00:42:03] like performance, and sometimes you need
[00:42:05] to just like break the cache in order to
[00:42:07] insert the right context, or give it a
[00:42:09] system reminder, or something like that.
[00:42:11] How how strictly do you guys try to
[00:42:13] adhere to prompt caching?
[00:42:15] >> Is the purpose for those who are prompt
[00:42:17] caching loyalists for uh speed or cost
[00:42:22] or quality?
[00:42:23] >> I think the first two mostly speed and
[00:42:25] cost.
[00:42:25] >> Speed and cost.
[00:42:26] >> Yeah. I haven't I haven't heard anyone
[00:42:28] argue that it's for quality, but maybe
[00:42:30] maybe it works better.
[00:42:32] >> It's a nice to have.
[00:42:33] Um we definitely don't want to
[00:42:36] invalidate a cache for no good reason,
[00:42:38] but quality comes first.
[00:42:40] So, we aren't uh zealots about it at
[00:42:43] all. I would also say that when the
[00:42:46] outcomes that your agents are delivering
[00:42:49] are very valuable, you have the luxury
[00:42:51] of not being extremely focused on cost
[00:42:54] in particular.
[00:42:56] Uh and so, that probably is part of the
[00:42:59] reason for that is that, you know,
[00:43:01] a conversation with a customer could
[00:43:03] sell a
[00:43:05] $100 product or a $1,000 lifetime value
[00:43:09] plan. And so, those are valuable enough
[00:43:12] that quality almost always comes first.
[00:43:14] >> We've talked a bunch about the agent
[00:43:16] itself. There's two topics that we were
[00:43:17] discussing earlier, and I'm curious
[00:43:19] We've talked a little bit about them,
[00:43:20] but I'm curious if you have any more
[00:43:21] thoughts. First being RL. When is RL
[00:43:24] good? When is it bad? How much have you
[00:43:25] guys explored it?
[00:43:26] >> We've explored it a lot, in part because
[00:43:29] it has two great promises, you know,
[00:43:31] increasing the ceiling of the quality of
[00:43:33] models, and then also making it so that
[00:43:35] you can do a similar task on more
[00:43:38] models.
[00:43:39] I'm curious for your take, but in
[00:43:40] practice I've seen a little bit more of
[00:43:42] the second one when it comes to like
[00:43:44] enterprise RL. It's taking an open model
[00:43:47] or open weights model and saying, "How
[00:43:48] can we get similar performance to a
[00:43:51] frontier model?" The two things that
[00:43:53] make it hard are, number one, uh the way
[00:43:55] that that gets delivered is
[00:43:57] non-deterministic and might include um
[00:44:00] you can't include any data that you
[00:44:02] don't want the model to regurgitate. So,
[00:44:04] we basically would never fine-tune a
[00:44:05] model on something when it could lead to
[00:44:08] regurgitation risk. That's just a
[00:44:10] non-starter. And then also uh in
[00:44:12] general, just the way that uh you would
[00:44:16] train the model, you have to think about
[00:44:17] preparing all of that data.
[00:44:19] The other big one is that the frontier
[00:44:21] models are improving so fast that you
[00:44:24] want to remain as agile as possible.
[00:44:28] And so in many cases, doing something
[00:44:30] like RL makes a ton of sense for
[00:44:32] something like knowledge where we feel
[00:44:34] like we are pushing the state of the
[00:44:35] art. But if we're not pushing the state
[00:44:38] of the art, we really want to be
[00:44:39] thinking about what's going to be true 3
[00:44:41] months from now, 6 months from now, and
[00:44:43] oftentimes RL is a rounding error
[00:44:45] against that.
[00:44:46] >> Yeah, I feel like to your point earlier,
[00:44:47] we've started to hear it a little bit
[00:44:49] more recently. I think because of cost.
[00:44:51] So I think like most people are
[00:44:53] interested in it when they're using
[00:44:54] these frontier models and the
[00:44:55] performance is good. But now, whether
[00:44:58] it's coding or other things, their cost
[00:45:00] is just going through the roof. I think
[00:45:02] the and we're starting to investigate
[00:45:04] this more, but I think the places where
[00:45:05] we're hearing it most are basically in
[00:45:07] those where performance is good, cost
[00:45:09] too high. How can I bring it down? Let's
[00:45:10] see if I can I can train a model to get
[00:45:12] similar cost at a fraction of the cost.
[00:45:14] Or similar performance, fraction of the
[00:45:15] cost.
[00:45:16] >> Yeah.
[00:45:17] Interestingly enough, a lot of our
[00:45:19] progress here has been driven by
[00:45:20] capacity, not cost. Where
[00:45:24] you know, we have a lot of customers
[00:45:25] that are in the retail space. And when
[00:45:27] we go into Black Friday, Cyber Monday,
[00:45:30] for example, you need a lot of capacity
[00:45:32] to deal with the spikes that they face.
[00:45:35] Uh we've also done load tests that are
[00:45:37] on the order of you know, if you were to
[00:45:39] have that rate of conversation over a
[00:45:42] year, it would be billions of
[00:45:44] conversations. And so that level of
[00:45:46] concurrency and those spikes just mean
[00:45:49] that we need to be resilient to downtime
[00:45:53] with a particular provider and ready
[00:45:56] for, you know, using whoever has the
[00:45:58] capacity to serve us. And so
[00:46:00] it's funny because it's useful in so
[00:46:02] many ways, but a lot of the reason why
[00:46:04] we have such good support for multiple
[00:46:07] providers is specifically preparing for
[00:46:10] Black Friday Cyber Monday and running
[00:46:11] load tests for really large customers.
[00:46:13] >> One other
[00:46:15] harness agent engineering topic,
[00:46:17] multi-agent systems. Where do you think
[00:46:19] they're useful, where they're not
[00:46:20] useful?
[00:46:21] >> I think they are often not as useful as
[00:46:24] people think. My thoughts on this would
[00:46:26] be people should be really thoughtful
[00:46:28] about why they want a multi-agent
[00:46:30] system. If you want a multi-agent system
[00:46:33] so that one team can work on one agent
[00:46:35] and one team can work on another agent,
[00:46:37] then you're shipping your org chart. If
[00:46:38] you want a multi-agent system because
[00:46:40] it's just makes you more comfortable to
[00:46:42] think about this problem over here and
[00:46:44] this other problem over here,
[00:46:46] then you're also not optimizing around
[00:46:49] impact.
[00:46:50] If, for example, you had an agent that
[00:46:52] does triage and another agent that does
[00:46:54] a task, by building it as a multi-agent
[00:46:57] system,
[00:46:58] you're often
[00:47:00] depriving of the agent doing the task of
[00:47:02] the information from the triage and
[00:47:05] depriving the agent doing the triage of
[00:47:06] all of the procedural information from
[00:47:09] the task. And that's typically
[00:47:11] destructive of value. And so, we are
[00:47:14] often just want to make sure that we're
[00:47:16] doing multi-agent systems for the right
[00:47:18] reason. If you're kicking off even a
[00:47:20] sub-agent, you want to make sure that it
[00:47:22] has everything it needs to do that task
[00:47:25] and that there's no reason why it
[00:47:26] shouldn't just be part of the main
[00:47:28] agent. Um and so, I think I've seen a
[00:47:30] lot of cases where people are reaching
[00:47:34] for multi-agent systems the same way you
[00:47:36] might reach for microservices
[00:47:39] uh before you're necessarily ready for
[00:47:41] that level of optimization and also for
[00:47:44] reasons that might not be just about
[00:47:46] building the best possible agent. And
[00:47:48] so, Sierra agents tend to be kind of one
[00:47:52] agent representing the brand. You
[00:47:54] certainly can have multiple agents and
[00:47:56] build a multi-agent system, but be if
[00:47:59] you're managing context correctly, if
[00:48:00] you're doing really really good context
[00:48:02] engineering, then typically it's just
[00:48:04] not a problem because you're not
[00:48:05] exposing the wrong context to the wrong
[00:48:08] agent.
[00:48:08] >> Is there a right time to build a
[00:48:10] multi-agent system?
[00:48:11] >> I think if you have truly separable
[00:48:13] jobs, right? Where there's not any
[00:48:15] purpose of the first context being part
[00:48:17] of the second context.
[00:48:19] I will say that
[00:48:21] in my personal opinion with you know,
[00:48:24] May 18th, 2026,
[00:48:27] there not a lot of great times for it.
[00:48:29] There might be times where it actually
[00:48:31] the organizational difficulties are
[00:48:33] worth the quality drop, but if you're
[00:48:36] doing it specifically for quality, I
[00:48:38] think it's it's
[00:48:39] pretty rare that you can't just solve it
[00:48:41] with better context engineering and I'm
[00:48:43] kind of a monolith loyalist on that.
[00:48:45] >> I feel like voice is one of the things
[00:48:48] that is getting more and more popular,
[00:48:49] but there still aren't a ton of people
[00:48:52] doing a lot of, but you guys are. Can
[00:48:54] you give me a voice 101 or 201? What
[00:48:56] what should I and other agent builders
[00:48:57] know about voice compared to just
[00:48:59] building, you know, simple chat agents?
[00:49:02] >> Voice has been maybe the most fun
[00:49:04] project that I've worked on in my whole
[00:49:05] career.
[00:49:06] So, and and I for context, I joined
[00:49:09] Sierra as an agent PM working on
[00:49:12] building agents specifically with
[00:49:13] customers in a forward deployed role.
[00:49:16] And one of the first customers I worked
[00:49:17] on
[00:49:18] is SiriusXM, the in-car streaming radio
[00:49:21] service. And so, I'm big SiriusXM fan
[00:49:25] before that and as a result. And they
[00:49:29] have a ton of volume over voice, even
[00:49:32] more than they have over chat. And so,
[00:49:34] many of their touchpoints with customers
[00:49:36] are over the phone. And so, early on it
[00:49:37] was very obvious that voice was going to
[00:49:39] be impactful for the business.
[00:49:41] And we got to think from first
[00:49:42] principles, basically from the ground
[00:49:44] up, what makes a voice experience great?
[00:49:47] How is that similar to chat? How is that
[00:49:49] similar How is that different from chat?
[00:49:51] And so, latency is probably the most
[00:49:53] obvious one.
[00:49:55] You need to be really thoughtful about
[00:49:58] parallelism. You need to be really
[00:49:59] thoughtful about what we call progress
[00:50:01] indicators, which is where you
[00:50:03] say, you know, hang on a second while I
[00:50:05] look up your account.
[00:50:07] That's number one. Number two is
[00:50:08] naturalism. This is a combination of a
[00:50:10] number of different things. So,
[00:50:12] oftentimes when something sounds a
[00:50:14] little bit robotic,
[00:50:16] I'll I'll read what the agent said, and
[00:50:18] I'm like, "Well, I sound robotic, too."
[00:50:20] So, it's a combination of what the agent
[00:50:22] is reading and then also the quality of
[00:50:23] the voice itself.
[00:50:25] Um there's multilingualism. It's very
[00:50:27] easy to speak different languages over
[00:50:29] chat using large language models. It's a
[00:50:31] lot harder to be fluent in I think it's
[00:50:36] almost about 60 languages on Sierra
[00:50:38] platform um and
[00:50:41] you know, than it is on chat. And each
[00:50:42] of those languages, you know, sometimes
[00:50:44] the very best transcription provider
[00:50:47] might have a 20% word error rate. I
[00:50:49] think that's true for a language like
[00:50:51] Hungarian, for example. And so, it's
[00:50:52] like, how can we ensemble multiple
[00:50:54] transcription providers in order to get
[00:50:56] that down and kind of be better than a
[00:50:58] single model is on its own. The other
[00:51:01] big factor is I think we all believe
[00:51:03] that a few years from now
[00:51:06] most voice agents will be running voice
[00:51:08] native models. So, you know, real time I
[00:51:11] think it they might be up to 2.5 at this
[00:51:13] point. They've had like three big
[00:51:15] real-time launches at OpenAI this year
[00:51:17] already. There was the really cool demo
[00:51:19] from Thinking Machines Labs as well. So,
[00:51:22] there's been a lot of increased momentum
[00:51:24] here.
[00:51:25] And as of a few months ago, we now have
[00:51:28] production agents live with the
[00:51:30] voice-to-voice models. Um and so,
[00:51:32] they're you know, it's you know, fully
[00:51:34] end-to-end doing that. You still need
[00:51:35] the transcript in order to like make API
[00:51:37] calls and that sort of thing, but the
[00:51:39] agent is responding you know,
[00:51:41] with audio as the input. The other big
[00:51:44] piece of it, I think the The Machines
[00:51:45] demo was a really good example.
[00:51:48] Up until now, we basically had like 50
[00:51:51] lines of Python. I think Silero is the
[00:51:54] most popular voice activity detection
[00:51:56] library
[00:51:57] deciding when to speak.
[00:51:59] And then a trillion parameters deciding
[00:52:02] what to say. And that balance feels very
[00:52:04] off to me. If you think about the
[00:52:06] conversation we're having right now,
[00:52:09] I'm actually using a lot of my brain
[00:52:10] power to decide when to speak
[00:52:12] uh in addition to decide what deciding
[00:52:14] what to say. And it's probably more like
[00:52:15] 50/50.
[00:52:17] And so the one of the big unlocks for
[00:52:19] Sierra agents was deciding to think
[00:52:23] about not only how to parallelize a
[00:52:24] task, but how to parallelize thinking,
[00:52:27] listening, and talking.
[00:52:29] So that when I'm listening, I'm already
[00:52:31] thinking about what I might say next.
[00:52:33] When I'm talking, I'm listening for
[00:52:35] interruptions. And so that was a big
[00:52:37] unlock uh in terms of the product
[00:52:38] design. The other one I would say is
[00:52:40] just modularity, like I said earlier.
[00:52:42] Um no one is the best at everything in
[00:52:44] this space. And when there are, you
[00:52:46] know, 100-plus languages uh worldwide
[00:52:49] that, you know, really deliver
[00:52:50] meaningful results, when many of our
[00:52:51] customers are global brands, global
[00:52:54] companies, you need that flexibility to
[00:52:57] use one provider here and another
[00:52:58] provider there and to ensemble them
[00:53:01] together in a specific place as well.
[00:53:03] >> How much of that modularity and that
[00:53:06] parallelism and thinking about different
[00:53:08] things goes away when it's like a native
[00:53:11] voice-to-voice model?
[00:53:13] >> In one specific conversation,
[00:53:16] it goes away.
[00:53:18] But if you think about the businesses we
[00:53:19] serve, the voice-to-voice models today
[00:53:22] are just reaching a level of reliability
[00:53:24] where you would trust them for English.
[00:53:27] And so if you still want to support all
[00:53:28] the different languages, you need that
[00:53:30] modularity for the foreseeable future.
[00:53:34] Um the other thing is they're still
[00:53:36] almost an order of magnitude more
[00:53:37] expensive. They aren't quite as good at
[00:53:40] reasoning yet.
[00:53:42] And so the cases where they are live in
[00:53:44] production, they're not quite as
[00:53:45] reliable with tool calling and
[00:53:46] instruction following. The cases where
[00:53:48] they're live in production, it's cases
[00:53:50] where we know in advance that the
[00:53:52] journey is a little bit simpler.
[00:53:54] And where the naturalism matters even
[00:53:57] more than usual.
[00:53:59] And the procedure is not as complex as
[00:54:01] some other cases. And so it's still I
[00:54:04] would say a fraction of our market that
[00:54:06] we can use voice-to-voice models for.
[00:54:09] >> My perception also, and I I have never
[00:54:11] built a voice agent. So I know truly
[00:54:13] nothing here. But my perception here is
[00:54:15] for the voice-to-voice models, you you
[00:54:17] probably you have less control over what
[00:54:18] goes on inside of the loop basically of
[00:54:21] of tool calling and reasoning. Is that
[00:54:23] correct or are there pretty good
[00:54:24] controls for for what happens inside?
[00:54:27] >> You may not have built a voice model,
[00:54:28] but you're an expert in developer
[00:54:30] ergonomics. And I would say early on
[00:54:33] the APIs missed the mark on the
[00:54:37] ergonomics. And so they got the uh
[00:54:40] integration points wrong. And they were
[00:54:42] it was exactly what you said. It was
[00:54:43] hey, if you want our model
[00:54:45] you need our voice activity detection
[00:54:47] and you need the whole thing. There was
[00:54:49] still an underlying model that was
[00:54:50] available. So I'm, you know, dating
[00:54:53] myself in AI, but the GPT-4 audio model
[00:54:56] was extremely exciting. It did things
[00:54:59] that no model before it could do. I
[00:55:00] think maybe like people that are real AI
[00:55:03] OGs would say this about like GPT-2 or
[00:55:06] something. And so you could see that
[00:55:08] this was coming. And I think we all
[00:55:10] would have said 5 years from now this is
[00:55:11] where we're going to be.
[00:55:13] But the way that we wired that up in our
[00:55:16] system was basically
[00:55:18] using the entire Sierra pipeline.
[00:55:21] And then holding on to the input audio.
[00:55:24] And piping that in with all of the
[00:55:27] prompt context into the audio model to
[00:55:30] do the last mile. So we were basically
[00:55:32] still doing everything ourselves and
[00:55:33] using it for the last mile. I think
[00:55:35] you're right that over time there's more
[00:55:37] and that you can do with the audio model
[00:55:39] the same way there's more that you can
[00:55:41] do with the text models. The fallacy
[00:55:44] would be that okay, so then you don't
[00:55:45] need the harness or you don't need all
[00:55:47] of the orchestration and simulations and
[00:55:49] everything because
[00:55:51] you can make that choice. You can either
[00:55:52] do the same thing a little bit more
[00:55:55] easily or you can set your sights on new
[00:55:58] and more impressive things. Which I
[00:56:00] think not to get too philosophical, but
[00:56:02] that's kind of the direction of the
[00:56:03] industry in general. It's like are we
[00:56:06] all obsolete or are we going to find new
[00:56:08] things to do that raise our horizons
[00:56:11] even farther?
[00:56:11] >> If you had to guestimate a time, we're
[00:56:14] big into guestimating on the podcast
[00:56:15] apparently.
[00:56:16] >> Great.
[00:56:16] >> Um, when do you when do you think more
[00:56:18] than 50% of your either traffic or
[00:56:21] customers will be served by a
[00:56:23] voice-to-voice model as opposed to this
[00:56:25] this speech-to-text text-to-speech
[00:56:27] pipeline?
[00:56:28] >> I will be surprised if it happens in the
[00:56:30] next 18 months. I've been surprised
[00:56:32] before. I was surprised by Opus 4.5
[00:56:36] uh, late last year. Um, certainly
[00:56:38] surprised by ChatGPT. Like vividly
[00:56:40] remember the first time
[00:56:42] staying up till 3:00 a.m. just, you
[00:56:44] know,
[00:56:45] trying to jailbreak the prompt.
[00:56:47] >> [laughter]
[00:56:47] >> And so, you know, I I know you're a
[00:56:50] sports fan, too. So, if we're doing
[00:56:51] over/unders, it would be like 24 months
[00:56:55] and 1 day or something like that. You
[00:56:56] know, like or over/under 24 months would
[00:56:59] be probably my my personal guess.
[00:57:02] Demation.
[00:57:03] >> How, if at all, do you guys think about
[00:57:06] memory? Specifically long-term memory,
[00:57:08] specific It sounds like you've got users
[00:57:10] potentially interacting with multiple
[00:57:12] different agents that your your that a
[00:57:14] single brand can can be building. How do
[00:57:16] you think about the memory that's shared
[00:57:18] across them?
[00:57:19] >> Memory is very important to the
[00:57:20] platform.
[00:57:21] So, I mentioned the agent data platform
[00:57:23] earlier, which kind of brings together
[00:57:26] uh,
[00:57:27] machine learning data or, you know, big
[00:57:29] data as you might say about about
[00:57:32] customers and then marries that with in
[00:57:35] the moment context. That can only happen
[00:57:38] if you have a sense of identity and can
[00:57:40] also bring in
[00:57:42] memory from the past. So, in every
[00:57:44] Sierra conversation, there's the
[00:57:47] possibility of
[00:57:49] identifying the customer, saving
[00:57:51] memories either implicitly automatically
[00:57:54] or explicitly, and then extracting those
[00:57:56] memories at a future date for use in the
[00:57:59] agent. So, it's very much first-class
[00:58:01] primitive on the platform.
[00:58:02] I think you'll see that happen more and
[00:58:04] more over time as well. Just as these
[00:58:07] journeys get more complex, as we see
[00:58:09] more and more wins from the personal
[00:58:11] touch. We already have a number of cases
[00:58:13] where resolution rate has gone up
[00:58:16] meaningfully from memory, whether it's
[00:58:18] just greeting you by name, remembering
[00:58:20] what you called about last time, knowing
[00:58:22] that yesterday you were on the phone for
[00:58:24] an hour and it was really frustrating.
[00:58:26] And so,
[00:58:27] early on we had that memory through
[00:58:30] customer systems only, but we found just
[00:58:33] from customers asking over and over,
[00:58:34] "Hey, can you just have this first-class
[00:58:36] on the platform?" that it's helpful to
[00:58:38] have both. Seamless integrations with a
[00:58:40] CRM
[00:58:41] as well as on platform memory that
[00:58:43] really understands AI better than most
[00:58:46] CRM software does.
[00:58:47] >> How do you guys think about memory? I
[00:58:49] feel like you've got agents, multiple
[00:58:51] agents interacting with customers
[00:58:53] throughout various stages of their
[00:58:56] buying experience life cycle. So, I
[00:58:58] imagine memory must be important. How
[00:59:00] How do you guys think about it?
[00:59:01] >> So, memory is extremely important to the
[00:59:02] platform and since the agent data
[00:59:05] platform introduction, which we launched
[00:59:07] back in early November,
[00:59:09] it's been a first-class primitive on
[00:59:12] Sierra. So, if you call, for example, my
[00:59:15] wife lived in Hawaii for a year and so I
[00:59:17] was flying Hawaiian Airlines back and
[00:59:19] forth quite a bit and on a couple
[00:59:21] occasions, for anyone who's brought a
[00:59:23] dog to Hawaii, there's a lot of
[00:59:25] paperwork involved. I'm excited for the
[00:59:26] Sierra agent that can help with that.
[00:59:29] But, I would often add a pet in cabin,
[00:59:31] not that often, a couple times. And if I
[00:59:33] call back, you know, it's nice for them
[00:59:35] to remember why I'm calling, to know
[00:59:37] about me, to know I prefer aisle seats.
[00:59:40] I'm a big user of the in-flight
[00:59:42] internet. Hawaiian has Starlink back and
[00:59:45] forth from Hawaii.
[00:59:46] And so,
[00:59:47] these things just what we've seen in
[00:59:49] practice is that if you know who someone
[00:59:51] is, you greet them by name, you remember
[00:59:53] what's important to them, and you show
[00:59:56] empathy in the moment, it increases all
[00:59:59] of the metrics that are most important
[01:00:00] to businesses, from resolution rate to
[01:00:02] conversion rate, etc. And so, we've made
[01:00:05] memory first class on the Sierra
[01:00:07] platform, where during a conversation,
[01:00:10] implicitly or explicitly, you can
[01:00:11] basically store memories.
[01:00:13] And then, the agent, if the same person
[01:00:16] calls back, can extract those memories.
[01:00:19] The one thing to be aware of is you have
[01:00:21] to be really thoughtful about
[01:00:23] authentication, because often times, if
[01:00:26] someone calls over the phone,
[01:00:28] you don't necessarily know 100% from
[01:00:31] their phone number that it is this
[01:00:32] person. You know, some office networks
[01:00:35] all have the same phone number, maybe
[01:00:36] it's a family line, etc. And so, every
[01:00:39] business has to think about what the
[01:00:41] policy is for allowing the extraction of
[01:00:43] memories, and which memories are
[01:00:45] sensitive versus not so sensitive.
[01:00:47] Saying, "Hey Harrison, thanks for
[01:00:49] calling again." You know, that's
[01:00:50] probably fine. But, if it's like, "Hey
[01:00:52] Harrison, and are you calling about your
[01:00:54] social security number or the you know,
[01:00:55] that's like a definitely a different
[01:00:56] standard. Um and so, we try to be very
[01:00:59] thoughtful about that with our customers
[01:01:00] as well.
[01:01:01] >> When you say you can implicitly or
[01:01:03] explicitly save memories, what what
[01:01:05] exactly does that mean?
[01:01:06] >> So, there's kind of three layers of it.
[01:01:08] Number one is on a given conversation
[01:01:11] turn, you could say, "I want to save
[01:01:13] this to memory."
[01:01:14] Number two would be at the beginning of
[01:01:16] a conversation, you could say, "These
[01:01:18] are the things that are important to
[01:01:20] remember." You know, "Remember their
[01:01:21] birthday." That's always nice. Uh I
[01:01:23] remember Cold Stone Creamery growing up,
[01:01:25] they would give you a free scoop on your
[01:01:27] birthday. You know, it's a great
[01:01:28] opportunity for a brand loyalty.
[01:01:30] >> you could say, so would the brand say,
[01:01:32] would the customer say this in the
[01:01:34] system prompt, or would this be the end
[01:01:36] customer talking to the agent saying,
[01:01:38] "Hey, remember for future things that my
[01:01:41] birthday is on XYZ."
[01:01:42] >> So, the first one you said would be an
[01:01:44] example of journey building. An example
[01:01:45] of what I just said, and you would do it
[01:01:47] in journey building. You'd say, "I care
[01:01:48] about birthdays as an agent developer."
[01:01:51] Or an agent builder at any one of our
[01:01:52] customer companies. The second thing you
[01:01:54] said would be the third category of
[01:01:56] memory, which would be just sort of
[01:01:58] remember important things, and it would
[01:02:00] be an important thing if the customer
[01:02:01] said, "Hey, I want you to remember this
[01:02:03] when I call back in the future."
[01:02:05] Um so, whether you're deciding something
[01:02:06] in the moment this is important as an
[01:02:08] agent builder, I care about these
[01:02:09] things, or you know, let the agent
[01:02:12] decide. Uh those are kind of three ways
[01:02:14] to structure uh memory storage.
[01:02:17] >> And when you think about the structure
[01:02:18] of memory itself, do you guys think
[01:02:20] about it as a knowledge graph, a vector
[01:02:22] store, a file system, TBD?
[01:02:24] >> It's not super important. Um I guess I
[01:02:28] would say you want to optimize around
[01:02:30] retrieval.
[01:02:32] But, the reason why I said it's not
[01:02:33] super important is that typically your
[01:02:35] knowledge base is three orders of
[01:02:36] magnitude larger than the memories for
[01:02:38] an individual customer.
[01:02:40] And so,
[01:02:42] the retrieval and ranking problem is
[01:02:43] pretty simple, and I don't think it
[01:02:45] matters what structure you use, at least
[01:02:47] in our system today.
[01:02:48] >> I feel like memory is this really hot
[01:02:51] topic, and everyone loves to talk about
[01:02:52] it. And And there have been memory
[01:02:54] startups now for like 2 years, but but I
[01:02:56] don't see any of them
[01:02:59] being massive breakout successful. Why
[01:03:02] is that? Is Is memory not that important
[01:03:04] in the grand scheme of things? Is it so
[01:03:06] bespoke? Is it just too early on? Is it
[01:03:08] Is it really hard? Like why why isn't
[01:03:10] there a more established memory company
[01:03:13] or memory pattern?
[01:03:14] >> Do you have it turned on with Claude or
[01:03:16] ChatGPT?
[01:03:16] >> Not on purpose, although I think it is
[01:03:18] accidentally.
[01:03:19] >> And do you find it useful with your
[01:03:21] accidental turning it on?
[01:03:22] >> I don't really there.
[01:03:23] >> Okay. I ask because I would say that
[01:03:25] those are useful to me. I think what I
[01:03:27] said earlier about how when you're
[01:03:29] trusting us with memory, you're trusting
[01:03:31] us with authentication. That's part of
[01:03:32] it is that actually in order to pull off
[01:03:35] memory,
[01:03:36] you need to be trusted with something
[01:03:39] that has higher risk, you know, as well.
[01:03:42] And so, the reason I mentioned ChatGPT
[01:03:45] and Claude is those are products that
[01:03:48] you are already trusting. And so, I
[01:03:50] think they have more freedom than a B2B
[01:03:53] player would have where it's like, "Hey,
[01:03:55] if I want to buy memory from you,
[01:03:57] I also need to buy authentication or
[01:04:00] verification at least or identification
[01:04:02] at least from you. And I don't know
[01:04:05] exactly what the startups are in the
[01:04:06] space, but I would imagine like
[01:04:08] you're biting off more than you think
[01:04:10] when you sell memory."
[01:04:12] >> Talking about observability and evals
[01:04:14] for a bit. You guys have an interesting
[01:04:16] problem, I presume, where you have evals
[01:04:18] for your internal agents and for the
[01:04:20] maybe like general purpose agent SDK,
[01:04:23] but then I'm assuming your customers
[01:04:24] want to do evals themselves as well. Are
[01:04:25] those the same? Do you use the same
[01:04:27] tools for both? Or if they're different,
[01:04:29] why and how are they different?
[01:04:31] >> Typically not exactly the same. So,
[01:04:34] internally, um the Agent OS, you know,
[01:04:37] if you think about it as a series of
[01:04:39] tasks and some of those tasks might be
[01:04:41] very complex and some of those tasks
[01:04:43] might be more simple.
[01:04:44] The eval problem is more similar to the
[01:04:48] eval problem that any applied AI company
[01:04:50] has.
[01:04:51] When you think about our customers,
[01:04:53] I think the eval problem is much more
[01:04:57] complicated and involves things like
[01:05:00] what happens when there's background
[01:05:01] noise in voice and uh what if I have an
[01:05:04] adversarial user and I want to save
[01:05:06] these 20 personas and run all of my
[01:05:08] simulations against all 20 of the
[01:05:10] personas and make sure that it works.
[01:05:13] And so, you end up with just a more
[01:05:15] complicated topography because a
[01:05:17] conversation by nature is very
[01:05:19] complicated and can go in so many
[01:05:21] different directions. And so, we built a
[01:05:23] product specifically for our customers
[01:05:25] to eval agents called simulations. And
[01:05:28] it supports all of these different
[01:05:29] things. I think it is probably you can
[01:05:32] tell when someone's building an agent if
[01:05:35] they have good simulations, it's such a
[01:05:37] great unlock because you can make
[01:05:39] changes in a way that is constantly
[01:05:42] improving the agent and being sure that
[01:05:44] you're not regressing, especially as you
[01:05:45] get into big teams with complex agents
[01:05:48] that are doing so many things. I mean, I
[01:05:49] know you see this at LangChain as well.
[01:05:51] Like, having really good evals is such a
[01:05:54] great unlock. And so, we pride
[01:05:56] ourselves, in addition to, you know,
[01:05:59] government governance and collaboration
[01:06:02] and review and making sure that, you
[01:06:04] know, you have workspaces, so you can
[01:06:06] let Ghostwriter run free but still
[01:06:08] review it before you make any changes.
[01:06:11] We also have that simulation layer, so
[01:06:14] that every change you make is tested
[01:06:16] against all the assumptions of the
[01:06:17] platform across voice and chat and many
[01:06:19] languages and many personas in this
[01:06:21] high-dimensional space that you're going
[01:06:23] to experience in production.
[01:06:24] >> Going out from evals for just a second
[01:06:26] because you said something around
[01:06:28] continually improving the agent. I want
[01:06:30] to talk about continual learning. That
[01:06:31] also ties into memory, I guess, a little
[01:06:33] bit. Like, how do you how do you think
[01:06:35] about continual learning in general?
[01:06:36] Does the Sierra platform support it in a
[01:06:39] fully I'm assuming not like completely
[01:06:41] automated way, but like how how far
[01:06:44] along are you guys and and and what do
[01:06:46] you think the future in continual
[01:06:47] learning holds?
[01:06:48] >> Where we are today is
[01:06:51] you can automatically detect an issue
[01:06:53] with a monitor. Ghostwriter can
[01:06:55] automatically suggest a fix to an issue.
[01:06:58] And you can review that issue and push
[01:07:01] it to your agent. And so, you're still
[01:07:04] in the loop or people are still in the
[01:07:05] loop in all of the cases.
[01:07:07] But, it's
[01:07:09] as automated as it can be with still
[01:07:11] giving you authority over that.
[01:07:13] I think in the near future, you will
[01:07:15] start to see the first cases of Sierra
[01:07:18] agents improving themselves where they
[01:07:20] have a confidence level to the fix. For
[01:07:22] example, if there's an error in a
[01:07:25] knowledge article and it can tell that
[01:07:26] there's a contradiction and it can go
[01:07:28] check the website and, you know, for
[01:07:30] whatever reason, it's very clear what
[01:07:32] the true answer is, it could it could
[01:07:34] give you an FYI instead of needing
[01:07:36] approval. Same way, I do some work, I
[01:07:39] ask for approval, I do some other work,
[01:07:40] I give FYI. And so, all of the
[01:07:42] primitives are there, it's just around
[01:07:45] the confidence that people have in the
[01:07:46] level of control that they want to have.
[01:07:49] And so, we also don't want to get ahead
[01:07:50] of our skis there. Most of our
[01:07:52] customers, they want to review every
[01:07:53] change that goes into the agent. This is
[01:07:55] a really important part of their
[01:07:56] business. We don't want to pull the
[01:07:58] future forward too quickly. Um, we want
[01:08:00] to move at the pace our customers are
[01:08:02] excited about.
[01:08:03] >> One of the things you mentioned, going
[01:08:04] back to the eval's is monitors. What are
[01:08:06] monitors? And then you guys also wrote a
[01:08:08] blog called monitoring the monitors or
[01:08:10] something like that. I'd be curious to
[01:08:11] hear about that.
[01:08:12] >> Yeah, we have a saying in the company
[01:08:14] that the solution to all problems with
[01:08:16] AI is more AI. And so, often times, you
[01:08:18] have something that's 90% accurate and
[01:08:20] you figure out how to verify it 90% of
[01:08:23] the time. Figure out how to verify that
[01:08:25] 90% of the time. And and so on and so on
[01:08:28] and you have something that's, you know,
[01:08:29] three or four nines of reliability. And
[01:08:32] I think with non-deterministic systems,
[01:08:33] that's just quite a bit about how it
[01:08:35] works. And so, similarly,
[01:08:37] uh, with a conversation platform, you
[01:08:40] can set up monitors that run on every
[01:08:43] conversation and look out for the things
[01:08:45] that you want to flag either for review
[01:08:48] or to create issues from, uh, etc. And
[01:08:51] it just basically gives you peace of
[01:08:53] mind, narrows the set of, "Hey, I don't
[01:08:55] have to wake up every morning and try to
[01:08:57] read 10,000 conversations. I can read
[01:08:59] five. And I can say, 'Okay, these five
[01:09:01] look good. I feel comfortable going on
[01:09:03] with my day."
[01:09:04] And so, that frees up a lot of our
[01:09:06] customers to think about how do I
[01:09:09] actually improve customer satisfaction
[01:09:11] or resolution rate or some of these more
[01:09:13] strategic levers
[01:09:15] as opposed to feeling like they need to
[01:09:17] review everything. So, I think that's
[01:09:19] why it's one of our more popular
[01:09:20] features.
[01:09:21] >> You guys released TaoBench, which is an
[01:09:24] eval for a few different agentic use
[01:09:27] cases. And I think you released a few
[01:09:29] other benches as well. Why do you guys
[01:09:32] invest in these and why should people
[01:09:33] check them out?
[01:09:34] >> So, I mentioned we have a research team
[01:09:35] and
[01:09:37] it's very exciting when you're building
[01:09:40] something to also think about how other
[01:09:41] people could use it. I mean, the
[01:09:44] distance that the AI space has come and
[01:09:47] how we've benefited just from all of the
[01:09:50] contributions to open source, you know,
[01:09:52] our knowledge engine as as I mentioned
[01:09:54] runs on open models that we fine-tuned.
[01:09:58] It has felt like one of the areas where
[01:09:59] we can contribute because we actually
[01:10:02] know a lot about what it takes to build
[01:10:05] a good voice agent. I don't think anyone
[01:10:06] knows more than we do. We know a lot
[01:10:08] about knowledge retrieval, we know a lot
[01:10:10] about tool calling and following
[01:10:12] process.
[01:10:13] Um and we know a lot about
[01:10:15] transcription. Um and so, we've released
[01:10:17] I think those are the four areas. There
[01:10:19] might be another one where we release
[01:10:21] benchmarks in the sort of Tao cinematic
[01:10:23] universe. There's TaoVoice,
[01:10:25] TaoKnowledge, TaoBench, and MuBench,
[01:10:28] which is the multilingual transcription
[01:10:29] benchmark.
[01:10:30] And so,
[01:10:32] it really just started because the first
[01:10:34] TaoBench was a lot more popular than we
[01:10:35] expected. We're like, "Oh, people trust
[01:10:38] us to kind of say what good looks like
[01:10:40] in this space." And so, we've continued
[01:10:42] to do more and more, and our research
[01:10:44] team has grown, and there's appetite. I
[01:10:46] think it also has this ancillary benefit
[01:10:47] of causing us to think about these
[01:10:49] problems
[01:10:50] in a very principled way. And you know,
[01:10:52] from kind of the first principles of
[01:10:54] what good looks like.
[01:10:56] And then we can evaluate our agents that
[01:10:58] way as well. So, I think it has that
[01:10:59] benefit, but it is very path dependent
[01:11:01] on Tow bench being a hit and you know,
[01:11:04] Tow is squared being the sequel being a
[01:11:07] hit as well and then us just deciding,
[01:11:08] okay, let's do more of this. People seem
[01:11:10] to like it.
[01:11:11] >> How much does the core agent team use
[01:11:15] these to guide their harness choices?
[01:11:17] >> Most of the benchmarks we use to
[01:11:19] evaluate providers
[01:11:22] more than to evaluate agents. And so,
[01:11:25] for example, we had there's a really
[01:11:27] exciting new transcription model that
[01:11:29] came by the office and presented it to
[01:11:31] us.
[01:11:32] And so, we were able to say, this looks
[01:11:34] really exciting, but we'd like you to
[01:11:36] run it against Mu bench and then it will
[01:11:38] be really exciting. And so, it really
[01:11:40] helps in the modular approach that we've
[01:11:43] taken. Like, the reason we discovered
[01:11:45] that this model works really well when
[01:11:48] there's silence in northern United
[01:11:51] Kingdom, but this other model works
[01:11:53] really well when there's speech is
[01:11:54] because of things like Mu bench in
[01:11:56] particular for that one. Internally,
[01:11:59] simulations is the main way that we eval
[01:12:02] the actual agents that are going out to
[01:12:03] production. So, it's just too customer
[01:12:06] specific for us to rely on something as
[01:12:08] general as a benchmark.
[01:12:10] >> How do you create these benchmarks? Are
[01:12:11] they synthetically generated? Do you do
[01:12:13] a lot of data labeling internally? Do
[01:12:15] you outsource it?
[01:12:16] >> I think it's a mix of all three.
[01:12:19] I don't know all of the details for all
[01:12:21] of the benchmarks, but I know that we
[01:12:24] do a lot of stuff internally just in
[01:12:27] terms of especially when you're kind of
[01:12:30] in the zero to one phase, just figuring
[01:12:32] out what the right shape of the data is.
[01:12:34] Even when you work with external
[01:12:35] companies, they often want to see some
[01:12:37] number of examples from you. And then I
[01:12:39] think also
[01:12:41] being able to synthesize data when scale
[01:12:43] matters a lot especially if you can do
[01:12:46] it in a reliable way, is very helpful,
[01:12:48] too.
[01:12:49] It's harder for something like
[01:12:51] transcription where audio synthesis
[01:12:53] might be, you know, already in the
[01:12:55] training set of the transcription and
[01:12:56] that kind of thing.
[01:12:58] Um, but for things like text, I think
[01:12:59] it's easier.
[01:13:00] >> One of the things that I think is pretty
[01:13:01] underrated in building agents is UX. So,
[01:13:04] we've already talked about voice as a
[01:13:05] modality. We've talked about actually
[01:13:07] showing up as a chat GPT app. How else
[01:13:10] do you guys think about modalities or
[01:13:12] UX's? Do you have you experimented with
[01:13:14] generative UI in any form?
[01:13:17] >> We have quite a bit. I think it's pretty
[01:13:19] vertical dependent as well.
[01:13:22] To give you an example, when you're
[01:13:23] checking in for a flight,
[01:13:25] if you have a hypothetically 12-letter
[01:13:28] last name with a hyphen in the middle of
[01:13:30] it, um, and a first name that's hard to
[01:13:32] spell as well,
[01:13:33] hypothetically, then it might be helpful
[01:13:36] to type that in while you're on the
[01:13:37] phone. And so, we see in industries like
[01:13:40] airlines appetite for multimodal
[01:13:42] experiences, especially when there's a
[01:13:45] lot of reservation retrieval or input.
[01:13:48] For something like retail, we see
[01:13:50] exactly what you described, where really
[01:13:52] polished UI around product discovery,
[01:13:55] um, and around recommendation moves the
[01:13:57] needle and makes a difference.
[01:13:59] I think where Sierra is particularly
[01:14:01] differentiated is going really deep with
[01:14:03] customers, especially in specific areas,
[01:14:07] and learning, you know, what does it
[01:14:09] mean to build an amazing
[01:14:11] retail discovery experience, and then
[01:14:13] just from first principles, what's the
[01:14:15] agent that could help drive that? versus
[01:14:18] what does it mean to build a great
[01:14:20] airline check-in experience or flight
[01:14:22] disruption experience, um, to the degree
[01:14:25] that can be great, it can be not
[01:14:26] terrible, I guess. Then, you know,
[01:14:29] what's the right form factor for that?
[01:14:31] We've seen, and I think one of the
[01:14:32] reasons vertical companies have been
[01:14:35] pretty successful lately is that
[01:14:38] understanding the contours of each
[01:14:40] industry and each company really makes a
[01:14:42] difference.
[01:14:43] >> One of the things that I think you guys
[01:14:44] are actually best known for is your
[01:14:45] revenue model, and charging for
[01:14:47] outcome-based pricing.
[01:14:49] How do you actually do that? How do you
[01:14:51] estimate the the value that an
[01:14:53] interaction has? And And is it specific
[01:14:54] to each customer?
[01:14:56] >> This, I think, is maybe the number one
[01:15:00] operational reason or business reason
[01:15:02] why ICR has been successful. It aligns
[01:15:05] the incentives between
[01:15:07] our company and our customers. And I
[01:15:10] think the phrase I like to use, which is
[01:15:12] a little bit cheeky, probably, is if you
[01:15:15] don't understand the value of
[01:15:16] outcome-based pricing, your outcomes are
[01:15:19] probably not that valuable. Because when
[01:15:21] you're delivering, you know, $100
[01:15:23] outcomes, and you get to keep a portion
[01:15:26] of it,
[01:15:27] everyone wants to row in the same
[01:15:29] direction, and it cuts through all of
[01:15:31] the prioritization and decision-making
[01:15:34] that often will cloud and resource
[01:15:36] allocation that often will will cloud
[01:15:38] enterprise partnerships. So, it's
[01:15:39] extremely valuable, and I think it's a
[01:15:41] big reason why we've been successful. I
[01:15:42] think it will just become the norm for
[01:15:45] companies that are doing differentiated
[01:15:48] high-value activities. If your product
[01:15:50] really like feels a little bit more like
[01:15:52] a commodity,
[01:15:54] you'll start to see more usage-based and
[01:15:57] seat-based pricing, cuz it's just
[01:15:58] simpler. An area, for example,
[01:16:01] knowledge-based lookups are a little bit
[01:16:03] more that way, just question answering.
[01:16:06] And so, in the case of question
[01:16:08] answering, that's not an area where you
[01:16:10] would have a high premium for an outcome
[01:16:13] of any particular sort. But if it's
[01:16:16] making a sale on a membership, or you
[01:16:18] know, selling someone a car,
[01:16:20] that's a really big outcome. Um, and so,
[01:16:22] companies will be more than happy to pay
[01:16:24] for that.
[01:16:25] Uh, I think where we're seeing things
[01:16:27] going is intra-conversation outcomes, to
[01:16:31] also thinking about more, you know, as I
[01:16:33] mentioned, kind of the moments that
[01:16:34] matter across the customer life cycle,
[01:16:37] and driving outcomes on top of our agent
[01:16:39] data platform that kind of span that
[01:16:42] whole life cycle. I think that's
[01:16:44] particularly interesting.
[01:16:45] >> You guys support multiple different
[01:16:47] outcomes. So, you've got customer
[01:16:48] support and you've got sales. How
[01:16:50] different is the pricing between those
[01:16:52] and how many different of these like
[01:16:53] categories or templates do you guys end
[01:16:56] up having?
[01:16:56] >> It really depends on the value. So, you
[01:16:58] asked if it was customer specific. The
[01:17:01] answer ends up being that it sort of has
[01:17:02] to be. In certain cases, you are
[01:17:06] troubleshooting very complex setup to a
[01:17:10] device or something and you have to try
[01:17:12] 15 different things to get it to work
[01:17:14] and the average conversation might take
[01:17:15] 20 turns and the amount of, you know,
[01:17:18] context engineering to make that work
[01:17:20] might be very high.
[01:17:21] In other cases, you might have something
[01:17:23] where, you know, you're just resetting
[01:17:26] the signal on your TV and it's very
[01:17:28] quick and easy or you're checking your
[01:17:29] balance with the bank and that's very
[01:17:32] easy. And so, you know, one outcome is
[01:17:35] very valuable and drives a lot of
[01:17:37] loyalty and one outcome is somewhat
[01:17:39] commoditized. You might have some cases
[01:17:41] where there's, you know, an outcome
[01:17:44] that's tens of dollars
[01:17:47] and in terms of the, you know, money
[01:17:49] that the agent would earn
[01:17:51] and then you might have some cases where
[01:17:52] it's, you know, much, much lower than
[01:17:54] that.
[01:17:54] >> And does that ever differ
[01:17:57] within a customer? So, like in your
[01:17:59] example, I could imagine you you could
[01:18:01] have an agent doing a really simple task
[01:18:03] of, oh, tell them to unplug the computer
[01:18:05] and plug it back in or something like
[01:18:06] that. And there's another one where
[01:18:08] like, oh my god, who knows what's going
[01:18:09] wrong and and it like is a miracle that
[01:18:11] it solves it at all. If it's the same
[01:18:13] customer, will it be charged the same
[01:18:15] amount or do you differentiate even
[01:18:16] within those different types of
[01:18:18] requests?
[01:18:19] >> There are cases where we differentiate.
[01:18:21] We're not dogmatic about it. What we
[01:18:24] found is that often times the benefits
[01:18:27] of having our incentives aligned
[01:18:30] are so high that it's not worth
[01:18:33] negotiating every detail of what counts
[01:18:36] for what and it kind of even out over
[01:18:40] time and you do right by your customers
[01:18:42] over time and you build trust and
[01:18:44] contracts aren't infinite and you want
[01:18:46] to have a really high renewal rate and
[01:18:48] have them trust you with more use cases
[01:18:50] and these kinds of things. So we make
[01:18:52] sure that incentives are deeply aligned.
[01:18:55] And then on top of that I think you can
[01:18:58] get really pedantic about the
[01:18:59] engineering of specific outcomes and
[01:19:01] maybe over time the market will move in
[01:19:03] that direction. But I think you're
[01:19:05] missing the forest for the trees in that
[01:19:08] case because of just how powerful the
[01:19:10] concept is. And so most of our customers
[01:19:12] are eager to find something simple that
[01:19:14] we all understand that feels fair. As
[01:19:16] opposed to trying to engineer like the
[01:19:18] perfect value for the for each outcome.
[01:19:21] >> Why don't you think there's more outcome
[01:19:23] based pricing right now? Is it because
[01:19:24] there's not enough agents doing valuable
[01:19:26] things or because it's so operationally
[01:19:28] intensive for now cuz it's early on that
[01:19:31] you guys have just a built up muscle of
[01:19:32] doing it and that's what allows you guys
[01:19:34] to do it so effectively.
[01:19:35] >> I think it's probably a bit of both. I
[01:19:37] think that there are a lot of products
[01:19:40] that
[01:19:41] probably as models have improved find
[01:19:45] themselves in a position of being more
[01:19:47] similar to
[01:19:48] what you could just buy tokens and
[01:19:51] create and then also there's just we're
[01:19:53] very early here.
[01:19:55] If I had to say though I would guess
[01:19:58] that the second one is more important
[01:20:00] and there will be a lot more of this the
[01:20:03] same way someone doesn't care how many
[01:20:07] hours I work as long as I produce you
[01:20:10] know new products that are good.
[01:20:12] And I think that that will become true
[01:20:14] of agents as well. There will be a mix
[01:20:17] of building agents in house on platforms
[01:20:20] like LangGraph and then there will be
[01:20:22] also
[01:20:23] you know buying
[01:20:25] products like Sierra to build agents on.
[01:20:27] >> Maybe switching to the last topic which
[01:20:28] is just the type of people that thrive
[01:20:31] at Sierra. I think you guys are also
[01:20:33] pretty famously known for your forward
[01:20:35] deployed engineering or agent builder
[01:20:36] approach. Could you talk a little bit
[01:20:38] about that both in terms of what those
[01:20:40] people do as well as the right persona
[01:20:42] to grow into that role?
[01:20:44] >> I joined Sierra about 2 and 1/2 years
[01:20:46] ago and it was my first B2B job ever.
[01:20:48] I'd only worked in consumer products and
[01:20:51] I love building consumer products. I
[01:20:52] love being like, oh, I could imagine,
[01:20:54] you know, my friends using this or my
[01:20:56] parents using this, but I'd never really
[01:20:58] loved growth
[01:21:00] uh and the idea of figuring out how to
[01:21:02] drive a couple percentage points of
[01:21:06] attention or a couple percentage points
[01:21:08] of usage. And what I learned when I
[01:21:10] joined Sierra is I love enterprise
[01:21:12] sales.
[01:21:14] Uh
[01:21:15] >> [laughter]
[01:21:16] >> I got a tattoo.
[01:21:17] Um so, basically, the the process of
[01:21:20] caring about each customer individually,
[01:21:23] saying one customer is upset, I'm going
[01:21:25] to call them right now and find out why
[01:21:27] and see how I can help. Just felt very
[01:21:30] empowering as a builder in a way where
[01:21:33] building for a billion users on Google
[01:21:36] Search, for example, you know, it was
[01:21:38] exciting in other ways, but it didn't
[01:21:40] feel like you could listen to each user
[01:21:41] and help them. And in many cases, we
[01:21:44] have customers of Sierra that have, you
[01:21:45] know, gotten promoted in their
[01:21:47] organizations. They're building careers
[01:21:49] because of the agents that they built on
[01:21:51] Sierra and so it's just feels very deep
[01:21:54] in terms of those relationships.
[01:21:56] What I love as well though is that the
[01:21:57] end user of a Sierra agent is still a
[01:21:59] consumer in the vast majority of cases.
[01:22:01] And I think it's pretty rare to have a
[01:22:04] product that needs to be consumer grade
[01:22:07] where the product that you're building,
[01:22:09] it's a it's a platform, but then the end
[01:22:11] user is really a consumer and you have
[01:22:13] to have them in your mind the whole
[01:22:14] time, but where you have kind of the
[01:22:16] enterprise sales process of building
[01:22:19] trust, of solving problems, of
[01:22:21] discovering value, and then delivering
[01:22:23] that value for people.
[01:22:25] Um and so, I think the people that
[01:22:27] really appreciate those two things, the
[01:22:30] customer obsession and the
[01:22:32] craftsmanship,
[01:22:33] uh, do very well.
[01:22:35] I think we've also discovered just with
[01:22:37] the rise of coding agents, certain
[01:22:40] things are more important than they used
[01:22:41] to be. Deep customer intuition, GPT-5.5
[01:22:45] doesn't really have that.
[01:22:46] Um, agency, the ability to say, "Why
[01:22:49] can't I do this?" Um, one of our uh,
[01:22:52] engineers that has really high degree of
[01:22:54] agency, her status message is just like,
[01:22:56] "Why not today?"
[01:22:57] Um, and so, yeah, having that mindset, I
[01:23:00] think is really important. And then the
[01:23:02] other thing just as someone with a
[01:23:03] product background is I think we kind of
[01:23:06] have
[01:23:07] a faster car than you need more pit
[01:23:10] stops, kind of thing. So, like a a
[01:23:12] Formula 1 car needs to get its tires
[01:23:14] changed more often than my Hyundai Kona.
[01:23:17] Uh, and the reason for that is, you
[01:23:19] know, it's driving faster, it's burning
[01:23:21] more rubber, uh, etc. And I think we
[01:23:23] have a similar thing building products
[01:23:25] as well now where coding agents have
[01:23:27] allowed us to write code a lot faster
[01:23:30] and even to review it faster now. But
[01:23:32] certain things like product judgment and
[01:23:34] customer intuition are therefore
[01:23:36] actually needed more often, not less
[01:23:38] often. And so, uh, people that can bring
[01:23:41] that to the table themselves are in this
[01:23:44] amazing loop of moving fast, but people
[01:23:47] where it's one person's job to bring
[01:23:49] that and another person's job to do
[01:23:51] engineering, they need even tighter
[01:23:53] collaboration and, you know, more daily
[01:23:55] stand-ups and that kind of thing to be
[01:23:56] successful.
[01:23:57] >> I really like that car analogy. I hadn't
[01:23:59] heard that before and totally resonates
[01:24:00] with what what what I'm seeing where
[01:24:02] product is becoming the bottleneck
[01:24:04] because it's so easy to code and you can
[01:24:06] make so much of things, but that doesn't
[01:24:07] mean you should. Who ends up fitting
[01:24:10] this agent builder profile the best? Is
[01:24:12] this product people then? Is this
[01:24:13] engineers with good product intuition?
[01:24:16] Like what does it look like practically?
[01:24:17] We're still figuring it out.
[01:24:19] >> I will say that people that have done
[01:24:22] both roles are often successful in the
[01:24:24] company. Our head of engineering, Arya,
[01:24:26] has been a product manager in the past.
[01:24:28] We have a number of engineers that have
[01:24:29] been product managers. I think those
[01:24:32] skills, knowing how to talk to
[01:24:34] customers, not just like what to say
[01:24:36] when you're in front of a customer, but
[01:24:38] how to find your way into the right
[01:24:40] conversations, having a high degree of
[01:24:42] agency, being really strong with
[01:24:44] communication, so that you're getting,
[01:24:46] you know, product isn't the bottleneck
[01:24:48] anymore. Uh those are really important
[01:24:50] skills.
[01:24:51] I still think kind of knowing the right
[01:24:53] questions to ask and the right things to
[01:24:56] tell coding agents is really important.
[01:24:57] So, the systems thinking and the
[01:24:59] architecture design are really
[01:25:01] important. And so, if you
[01:25:03] have not been an engineer before, uh it
[01:25:05] can be difficult. And so, I I think that
[01:25:07] the multi-disciplinary approach is more
[01:25:10] important than ever. My own personal
[01:25:12] rubric, which is like very much in beta,
[01:25:15] is kind of this customer intuition,
[01:25:18] agency, product judgment,
[01:25:21] technical depth,
[01:25:23] communication, intensity. Because when
[01:25:26] the car, you know, you need to be really
[01:25:28] locked in when you're driving a Formula
[01:25:30] 1 car. Um and then one which is a little
[01:25:33] harder to pin down, but it's just kind
[01:25:34] of leadership, where when there's more
[01:25:36] activity going on, the ability to to
[01:25:39] draw it into the correct direction is
[01:25:41] really important as well. So, this is
[01:25:43] kind of the working framework in my
[01:25:45] head, um but I'm sure there are lots of
[01:25:47] other things, too.
[01:25:48] >> How do you interview for agency? And I
[01:25:50] asked this because I think the the guest
[01:25:52] we had on in the previous episode said
[01:25:54] the exact same word agency for one of
[01:25:56] the traits that they look at. And I
[01:25:58] asked him the same question. So, now I'm
[01:25:59] going to ask you the same question. How
[01:26:00] do you How do you interview for agency?
[01:26:02] >> So, the most concrete way that we've
[01:26:04] changed our interviewing process is we
[01:26:06] have this AI native interview.
[01:26:08] >> And you wrote a great blog on it the
[01:26:10] other week.
[01:26:10] >> Yes. And so,
[01:26:11] you, by the way, is Vijay and Arya and
[01:26:13] our uh engineering leaders. But I've
[01:26:16] seen it done and participated in the
[01:26:18] interview panels. And basically it
[01:26:21] involves building a product end-to-end
[01:26:24] over the course of a few hours and then
[01:26:26] reviewing it with the team.
[01:26:28] I think in that environment you can see
[01:26:31] what people think is off-limits or
[01:26:33] what's their job and what's not their
[01:26:34] job and how far they extend sort of what
[01:26:37] they're allowed to do.
[01:26:38] And if they're able to
[01:26:41] find opportunities that you would have
[01:26:43] thought, oh, maybe that they would think
[01:26:44] that's out of scope, bring them into
[01:26:46] scope and build build great products on
[01:26:47] top of it. You kind of see agency. You
[01:26:50] see that they have a sense that a lot is
[01:26:52] in their control instead of feeling like
[01:26:54] certain things are not in their control.
[01:26:56] And if you think about coding agents,
[01:26:58] they bring so much more into I think the
[01:27:02] like the locus of control, right? And so
[01:27:05] you can do more things and if you
[01:27:06] appreciate that, I think it comes
[01:27:09] through in that AI-native interview.
[01:27:11] >> Thanks for listening to Max Agency.
[01:27:13] If you liked this episode, leave a
[01:27:15] review and subscribe. Send feedback or
[01:27:17] questions to maxagency@langchain.dev.
[01:27:18] [music]
[01:27:21] We want to hear from you.
