---
video_id: ntrM-erE2Xo
title: Demis Hassabis Is Right About AGI. Except for One Thing.
channel: System Cascade
url: "https://www.youtube.com/watch?v=ntrM-erE2Xo"
watched_date: 2026-05-28
watched_at: "2026-05-28T12:00:00Z"
watch_count: 1
duration_seconds: 3813
source: youtube-history-browser
history_label: Thursday
history_order: 104
watched_at_precision: date-from-history-label
watched_percent: 26
estimated_watched_seconds: 991
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Demis Hassabis presented a nuanced view of AGI progress: while current components (large-scale pre-training, RLHF, chain of thought) will likely remain part of the final architecture, he estimates a 50/50 chance that one or two fundamental ideas are still missing—specifically citing continual learning, long-term reasoning, stable memory, and cross-domain consistency as unsolved problems. He critiqued several industry narratives as oversimplified, noting that context windows are "brute force" approaches to memory that don't compare to biological consolidation, that models fail at basic chess because they can't track their own conclusions (they'll play moves they already identified as blunders), and that agents remain in early experimentation—despite thousands of companies running agent experiments, no compelling breakout product has emerged yet. He distinguished between current systems excelling at "Move 37" (finding brilliant points within known spaces) versus being unable to "invent Go" (create genuinely new domains), suggesting genuine discovery remains an open question.

For practitioners: The thousand-X productivity claims circulating in VC-land are unvalidated; Hassabis quietly refused to endorse this number and suggested actual gains cluster around iteration speed and 90-95% performance on smaller models. Plan for a future stack of local small models handling most tasks with occasional cloud model calls, not one giant oracle—this has real implications for your infrastructure and data privacy assumptions. Continual learning and reliable reasoning remain the critical missing pieces blocking "fire and forget" agents; if you're building agent systems now, expect current versions to fail on tasks requiring the model to remember and trust its own prior conclusions. The real value inflection will come when either someone ships a genuinely creative artifact (a hit game, a novel scientific insight) built mostly with these tools—which should be possible but hasn't happened yet—or when the architectural gaps around memory and reasoning get solved.

## Transcript

[00:00:00] Demis Hasabis is the closest thing the AI
[00:00:02] field has to a saint, chess prodigy,
[00:00:06] game designer at 17, neuroscience PhD,
[00:00:10] AlphaGo, AlphaFold, Nobel Prize.
[00:00:13] He runs Google DeepMind now, and when he
[00:00:16] says AGI is coming by 2030, a lot of
[00:00:19] serious people stop and listen.
[00:00:22] Most of what he says in this conversation
[00:00:25] is worth your time.
[00:00:27] Some of what he says, and almost
[00:00:29] everything his interviewer says back,
[00:00:31] deserves a closer look than it gets in the
[00:00:33] room.
[00:00:34] Let's walk through it.
[00:00:36] you've been thinking about AGI longer than
[00:00:38] almost anyone.
[00:00:39] When you look at the current paradigm,
[00:00:41] large scale pre -training, RLHF, chain of
[00:00:43] thought, how much of the final
[00:00:45] architecture for AGI do you think we
[00:00:48] already have and what's fundamentally
[00:00:50] missing right now?
[00:00:51] Well, first of all, thanks Gary for that
[00:00:53] great introduction and it's great to be
[00:00:54] here.
[00:00:55] Thanks for welcoming here.
[00:00:56] It's amazing space actually.
[00:00:58] I'm going to have to come back here often.
[00:00:59] Very inspiring that you get to work in
[00:01:01] this space.
[00:01:03] So the question is, I think the components
[00:01:06] that you just mentioned, I'm pretty sure
[00:01:08] will be part of the final architecture for
[00:01:11] AGI.
[00:01:12] So I think they've come such a long way
[00:01:14] now and we've proven out so many things
[00:01:16] about what they can do.
[00:01:18] I can't see a world in which we will sort
[00:01:20] of realize in a couple of years this was a
[00:01:22] dead end.
[00:01:23] That doesn't make sense to me.
[00:01:24] But there still might be one or two things
[00:01:26] missing on top of what
[00:01:29] you've, you know, what we already know
[00:01:30] works.
[00:01:32] So continual learning, long -term
[00:01:34] reasoning, some aspects of memory, these
[00:01:38] are still unsolved and how to get
[00:01:41] the systems to be more consistent across
[00:01:43] the board.
[00:01:44] I think all of these are going to be
[00:01:45] required for AGI.
[00:01:47] Now it might be that the existing
[00:01:49] techniques can just scale up to that with
[00:01:51] some innovation and some incremental
[00:01:53] innovation.
[00:01:54] But it could be that there's still one or
[00:01:56] two big ideas left that need to be
[00:01:59] cracked.
[00:02:00] I don't think it's more than one or two if
[00:02:02] there are out there.
[00:02:03] And I think, you know, my betting is about
[00:02:06] 50 -50 if that's the case.
[00:02:08] So of course, at DeepMind, at Google
[00:02:10] DeepMind, we work on both those things.
[00:02:12] Listen to what he just bet.
[00:02:14] 50 -50, that one or two basic ideas
[00:02:17] are still missing.
[00:02:18] Coming from the person running Google
[00:02:20] DeepMind, that's a remarkable admission.
[00:02:23] And it's the opposite of what you hear
[00:02:25] from most of his peers, who talk as if
[00:02:28] scaling is a settled question, and the
[00:02:31] rest is engineering.
[00:02:33] The plain reading of 50 -50 is that nobody
[00:02:36] knows, not Hassabis, not Altman,
[00:02:40] not a Mode.
[00:02:41] The frontier labs are running a huge
[00:02:43] experiment in public and finding out
[00:02:46] what's true as they go.
[00:02:48] That uncertainty matters because the whole
[00:02:51] infrastructure build -out, the gigawatt
[00:02:54] data centers, the trillion -dollar CAPEX
[00:02:57] projections, the geopolitics, is
[00:03:00] being justified by a confidence level that
[00:03:04] the people closest to the work don't
[00:03:06] actually hold.
[00:03:08] The other thing worth pulling out, the
[00:03:10] four things he names as unsolved,
[00:03:13] continual learning, long -term reasoning,
[00:03:16] memory, consistency, aren't side issues.
[00:03:20] They're the things that separate a
[00:03:22] powerful text predictor from anything
[00:03:24] you'd reasonably call general
[00:03:25] intelligence.
[00:03:27] Saying we have most of the architecture,
[00:03:29] while also saying the four hardest
[00:03:31] problems are unsolved, is two claims
[00:03:34] pulling in different directions.
[00:03:37] Hassabis is comfortable holding both.
[00:03:40] The room in the press cycle tend to
[00:03:42] flatten that into AGI by 2030,
[00:03:45] architecture mostly solved.
[00:03:47] That flattening is where the hype lives.
[00:03:50] I guess that's so, I mean, working with a
[00:03:52] bunch of authentic systems, the wildest
[00:03:54] thing to me is to what degree, it's the
[00:03:56] same weights over and over.
[00:03:58] So this idea of continual learning is so
[00:04:00] interesting because like, you know, right
[00:04:03] now we're sort of cobbling it together
[00:04:04] with duct tape.
[00:04:05] Yes.
[00:04:06] These dream cycles at night and things
[00:04:08] like that.
[00:04:08] Yeah.
[00:04:09] It's pretty cool, the dream cycles.
[00:04:10] And we used to think about this with
[00:04:12] consolidation with episodic memories.
[00:04:14] Actually, that's what I studied for my PhD
[00:04:15] is how the hippocampus works and
[00:04:17] integrates, you know, new knowledge
[00:04:19] gracefully into the existing knowledge
[00:04:22] base.
[00:04:23] So the brain does that amazingly well.
[00:04:25] It does it during sleep, especially things
[00:04:29] like REM sleep, replaying back episodes
[00:04:31] that are important so that you can learn
[00:04:33] from it.
[00:04:34] In fact, our very first Atari program,
[00:04:36] DQN, one of the ways it was able to master
[00:04:38] Atari games was by doing experience
[00:04:41] replay.
[00:04:42] So we sort of borrowed that from
[00:04:43] neuroscience and replayed successful
[00:04:46] trajectories many times, way
[00:04:49] back in 2013 now in the dark ages of AI.
[00:04:53] It was a really important thing.
[00:04:55] And I agree with you, we're kind of using
[00:04:56] duct tape right now.
[00:04:57] So shove it all in the context window.
[00:05:00] This seems a bit unsatisfying, right?
[00:05:02] And actually, even though we're working on
[00:05:05] machines, not biological brains, and so
[00:05:09] potentially you could have millions or
[00:05:12] tens of millions size context window or
[00:05:14] memory and it can be perfect, there's
[00:05:16] still a cost to looking it up and finding
[00:05:19] the right thing that's actually relevant
[00:05:21] for the specific decision you've got to
[00:05:24] make right now.
[00:05:26] And that's non trivial that cost, even if
[00:05:28] you can potentially store it all.
[00:05:29] I think there's actually a lot of room for
[00:05:31] innovation in areas like memory.
[00:05:33] Yeah.
[00:05:34] I mean, the wild thing is it feels like a
[00:05:35] million token context one is actually
[00:05:37] bigger than I mean, it's plenty big.
[00:05:40] Honestly, you can do so.
[00:05:41] Well, it's plenty big for most things that
[00:05:44] it should be used for.
[00:05:45] I mean, if you think about the context
[00:05:47] windows sort of equivalent to working
[00:05:48] memory, humans have, we have like a few
[00:05:52] digits.
[00:05:52] It's like a dozen digits maybe, average of
[00:05:56] seven.
[00:05:56] We've got million or 10 million context
[00:05:59] windows.
[00:06:00] But the problem is, is that we're trying
[00:06:01] to store everything in that.
[00:06:03] Things that aren't important, things that
[00:06:05] are wrong, it's pretty brute force
[00:06:07] currently.
[00:06:08] And that doesn't seem right.
[00:06:10] And then the problem is, if you're an
[00:06:11] Android or Triumph process live video, and
[00:06:14] you're just going to naively record all
[00:06:15] the tokens, then actually a million tokens
[00:06:18] isn't that much.
[00:06:19] It's only like 20 minutes.
[00:06:21] So actually you need more if you want
[00:06:23] something that's going to understand your,
[00:06:26] you know, your, what's going on in your
[00:06:27] life over maybe a month or two.
[00:06:29] Hear the gap between marketing and
[00:06:31] engineering gets visible.
[00:06:33] Every product page brags about a million
[00:06:35] -token context window.
[00:06:37] Hasabis, who runs the lab shipping those
[00:06:40] windows, calls the approach unsatisfying
[00:06:43] and brute force in the same breath.
[00:06:47] The point is more important than it
[00:06:48] sounds.
[00:06:50] A context window is not memory.
[00:06:53] It's a scratchpad you have to reread from
[00:06:55] the top every time you want to use
[00:06:57] anything in it.
[00:06:58] Humans don't work that way.
[00:07:00] We forget on purpose.
[00:07:02] We consolidate.
[00:07:04] We compress.
[00:07:05] The reason your brain can run on 20 watts
[00:07:07] and still outperform a data center on a
[00:07:09] lot of tasks is that biology figured out,
[00:07:13] somewhere in the deep past, that throwing
[00:07:15] everything into working memory and
[00:07:17] searching it line by line is a losing
[00:07:20] strategy.
[00:07:22] The honest framing is that the field has
[00:07:24] been papering over an architectural gap
[00:07:27] with raw compute.
[00:07:29] It mostly works.
[00:07:31] It's also a strong signal that whatever
[00:07:33] comes next isn't just bigger transformers
[00:07:37] with longer windows.
[00:07:38] Something has to give a model the ability
[00:07:41] to selectively forget, consolidate, and
[00:07:45] pull things back up.
[00:07:46] And nobody has shipped that yet at
[00:07:48] frontier scale.
[00:07:50] When Hasabis says there's a lot of room
[00:07:52] for innovation in memory, that's a
[00:07:54] researcher's polite way of saying the
[00:07:57] current approach is going to be looked
[00:07:59] back on as embarrassing.
[00:08:01] Deep mind has historically leaned into
[00:08:04] reinforcement learning and search, alpha
[00:08:07] go, alpha zero and mu zero.
[00:08:09] How much of that philosophy is actually
[00:08:11] embedded in how you're building Gemini
[00:08:13] today?
[00:08:15] Is RL still underrated?
[00:08:17] Yeah, I think potentially it is.
[00:08:19] It sort of goes in ebbs and waves.
[00:08:21] We've worked on agents since the beginning
[00:08:24] of DeepMind.
[00:08:25] In fact, that's what we said we were
[00:08:27] working on.
[00:08:27] So all of the Atari work and AlphaGo, most
[00:08:30] specifically, they're agent systems.
[00:08:32] And what we meant by that is systems that
[00:08:34] are able to, you know, accomplish goals on
[00:08:36] their own and make active decisions and
[00:08:39] make plans.
[00:08:41] And so of course we were doing it in the
[00:08:43] domain of games to make it
[00:08:46] tractable and then doing increasingly
[00:08:48] complex games, things like StarCraft after
[00:08:51] AlphaGo, AlphaStar.
[00:08:52] So we basically did all the games that
[00:08:55] were out there.
[00:08:56] And then of course the question is, can
[00:08:58] you generalize those models to be world
[00:09:00] models or models of language, not just
[00:09:02] models of simple games or even complex
[00:09:05] games?
[00:09:06] And that's what the last few years has
[00:09:07] been about.
[00:09:08] But really you can think of a lot of the
[00:09:10] things we're doing today, all the leading
[00:09:12] models with thinking modes and chain of
[00:09:15] thought reasoning as aspects of what was
[00:09:17] sort of pioneered with AlphaGo coming back
[00:09:20] now.
[00:09:20] And I actually think there's a lot of work
[00:09:22] we did back then that is relevant today.
[00:09:26] And we're sort of re -looking at some of
[00:09:28] those old ideas at scale today in a
[00:09:31] more general way, including things like
[00:09:33] Monte Carlo research and other ways of
[00:09:35] doing augmenting the RL on top of the
[00:09:38] reinforcement learning we're ready to do
[00:09:40] today.
[00:09:40] And I think a lot of those ideas, both
[00:09:42] from AlphaGo and AlphaZero are really,
[00:09:45] really relevant to where we are with
[00:09:47] today's foundation models.
[00:09:49] And I think a lot of that is what we're
[00:09:51] going to see of the advance over the next
[00:09:52] few years.
[00:09:53] This is one of the untold stories in
[00:09:55] modern AI.
[00:09:57] The chain of thought paradigm that Mado
[00:09:59] won and its successors famous in
[00:10:01] 2024 and 2025
[00:10:04] is structurally the AlphaGo
[00:10:07] idea applied to language.
[00:10:10] Think before you act.
[00:10:12] Search a tree of possible continuations.
[00:10:15] Use a learned scoring function to prune.
[00:10:19] Hasabis' team published the core of that
[00:10:21] approach a decade ago.
[00:10:24] What's worth noticing is what it means for
[00:10:26] who's positioned where.
[00:10:28] The story for a couple of years was that
[00:10:30] DeepMind had been left behind on language
[00:10:34] models while OpenAI and Anthropic
[00:10:37] ran ahead.
[00:10:39] Hasabis is gently pointing out that the
[00:10:41] techniques the rest of the field is now
[00:10:44] scaling were in their original form
[00:10:46] DeepMind work.
[00:10:48] Whether Gemini ultimately wins or loses
[00:10:51] the product race the intellectual lineage
[00:10:54] of where the field is going runs through
[00:10:57] Mountain View and London.
[00:10:59] The other thing to file away he says
[00:11:01] they're sort of re -looking at some of
[00:11:03] those old ideas at scale today
[00:11:06] in a more general way.
[00:11:08] What that means in plain terms is that the
[00:11:12] next two years of capability gains are
[00:11:15] likely to come from porting the planning
[00:11:17] and search machinery of AlphaZero onto
[00:11:20] general foundation models.
[00:11:24] If that works you'll see capability jumps
[00:11:27] in domains with clear objectives,
[00:11:30] math, code, science that look like
[00:11:34] sudden leaps from the outside.
[00:11:36] That's the bet he's signaling without
[00:11:39] quite saying it.
[00:11:41] One question I would have is like,
[00:11:43] obviously today you need bigger and bigger
[00:11:46] models to be smarter and smarter.
[00:11:48] But then we're also seeing distillation,
[00:11:50] and then smaller models can be quite a bit
[00:11:53] faster.
[00:11:53] I think you guys have incredible flash
[00:11:56] models that are like, you're finding that
[00:11:58] they're 95 % as good as the frontier
[00:12:02] and at one tenth the price.
[00:12:04] Is that right?
[00:12:04] I think that's one of our core strengths
[00:12:06] is, I mean, you have to build the biggest
[00:12:07] models to have the frontier
[00:12:10] capabilities.
[00:12:11] But I think one of our biggest strengths
[00:12:13] has been distilling and packing that power
[00:12:16] into smaller and smaller models very
[00:12:18] quickly.
[00:12:19] Obviously, we invented the distillation
[00:12:22] process and people like Jeff and Oriel and
[00:12:25] others.
[00:12:25] And we're still world experts in that.
[00:12:28] And we also have a huge need to
[00:12:31] do it because we've got to serve
[00:12:34] the biggest probably AI surfaces there
[00:12:37] are.
[00:12:38] Obviously, there's search with AI
[00:12:39] overviews and AI mode, and there's Gemini
[00:12:41] app.
[00:12:42] And now increasingly, every single product
[00:12:44] at Google has maps and YouTube and so on
[00:12:47] has some aspect of Gemini or Gemini
[00:12:50] related technology in it.
[00:12:52] And so that's billions of users, more than
[00:12:55] a dozen billion user products.
[00:12:56] And they have to be served extremely fast,
[00:12:59] extremely efficiently and cheaply and with
[00:13:01] low latency.
[00:13:02] So that gives us a really important
[00:13:05] incentive to make these flash and even
[00:13:07] smaller models, flashlight models
[00:13:09] extremely efficient.
[00:13:11] And hopefully that ends up then being
[00:13:12] really useful for many of the workloads
[00:13:14] that all of you did use for.
[00:13:16] I'm curious about how much smarter these
[00:13:19] smaller models can actually be.
[00:13:21] Like, are there limits to the distillation
[00:13:23] process?
[00:13:23] Like, could a 50B or 400B model be as
[00:13:27] smart as like a mythos for today?
[00:13:30] Yeah, I don't see any, I don't think we've
[00:13:31] got to any kind of, or at least none of us
[00:13:34] know yet if we've got to any kind of
[00:13:35] informational limit.
[00:13:37] I mean, maybe at some point that will be
[00:13:38] the case where there's just an information
[00:13:40] density that can't, we can't get beyond.
[00:13:42] But I think for now, there's the
[00:13:44] assumption we make is that, you know, a
[00:13:47] year later after one of our leading,
[00:13:50] you know, pro models or frontier models
[00:13:52] goes out, half a year later, a year later,
[00:13:55] you'll have them in the really tiny almost
[00:13:58] edge models.
[00:13:59] And you also see some of that goodness in
[00:14:01] our GEMMA models, which hopefully you're
[00:14:02] all enjoying our GEMMA 4 models, which I
[00:14:04] think are really amazing power for their
[00:14:07] sizes.
[00:14:08] So again, that uses a lot of these
[00:14:10] distillation techniques and the idea of
[00:14:13] how to make things really efficient in
[00:14:14] these very small models.
[00:14:16] So I didn't really see any limit yet in
[00:14:18] terms of like some kind of theoretical
[00:14:19] limit.
[00:14:19] I think we're still pretty far off There's
[00:14:21] an interesting economic claim hiding in
[00:14:24] this answer.
[00:14:25] The frontier model is becoming a loss
[00:14:27] leader.
[00:14:28] You build the biggest model partly to use
[00:14:30] it directly, but more and more to distill
[00:14:33] it down into the small, fast models that
[00:14:37] actually run its scale across your product
[00:14:39] surface.
[00:14:40] Google has to do this because Google
[00:14:43] has billions of users on search
[00:14:46] and maps and YouTube.
[00:14:49] Anthropic and open AI don't have that
[00:14:52] distribution problem in the same way,
[00:14:55] which is why their incentives around small
[00:14:57] models look different.
[00:15:00] The deeper question, which Hasabi's
[00:15:02] touches on and then moves past, is there
[00:15:06] a floor on how small a model can get
[00:15:09] while still being usefully smart?
[00:15:12] He says he doesn't know of one yet.
[00:15:15] Sit with that for a second.
[00:15:17] If a nine billion parameter model can do
[00:15:20] 95 percent of what a frontier model
[00:15:23] does on most real workloads, the
[00:15:27] long run pricing power of frontier models
[00:15:30] is much weaker than the current capex
[00:15:32] assumptions imply.
[00:15:34] Either the frontier has to keep racing far
[00:15:37] ahead of what the small models can
[00:15:40] capture, which gets harder as the small
[00:15:42] models improve, or the unit economics of
[00:15:46] the whole industry change shape in a few
[00:15:48] years.
[00:15:49] He doesn't draw that out, but every
[00:15:52] founder in that room building on top of an
[00:15:54] API should be doing the math themselves.
[00:15:57] of that.
[00:15:57] That's amazing.
[00:15:58] I mean, that is really good.
[00:16:00] You know, one of the weirder things that
[00:16:02] we're seeing right now is like engineers
[00:16:03] can do like 500 to a thousand times the
[00:16:06] amount of work that they were doing like
[00:16:09] six months ago, I guess.
[00:16:10] I mean, the people in this room, there are
[00:16:12] people who are doing about like a thousand
[00:16:14] X the work that like, Stevie Yaggy talks
[00:16:17] about this, it's like a thousand X the
[00:16:19] work that a Google engineer from the 2000s
[00:16:21] was doing.
[00:16:22] I think it's very exciting.
[00:16:23] I mean, I think the small models have many
[00:16:25] uses.
[00:16:25] One is obviously cost, but the speed can
[00:16:28] allow, you know, if you think about coding
[00:16:30] even or other things, you can iterate a
[00:16:32] lot faster.
[00:16:32] Also, especially if there's, if you're
[00:16:34] collaborating with the system, I think
[00:16:36] there's a lot of need for
[00:16:39] having fast systems that maybe are not
[00:16:43] quite front here.
[00:16:44] Like you said, like 95%, 90%, but that's
[00:16:46] plenty good enough and actually gain back
[00:16:48] more than the 10 % on the iteration speed.
[00:16:52] So, I mean, the other big thing I think is
[00:16:53] running these things on the edge, again,
[00:16:55] for efficiency reasons, but also for
[00:16:58] privacy and security reasons too.
[00:17:00] If you think about different devices that
[00:17:03] you might run these systems on that, you
[00:17:05] know, process very personal information,
[00:17:07] you can also think about robotics as well,
[00:17:10] you know, robots in your house.
[00:17:11] I think you're going to want very
[00:17:13] efficient, very powerful local
[00:17:16] models, which maybe are orchestrated, you
[00:17:19] know, with some bigger models, frontier
[00:17:21] models that are in the cloud, but you only
[00:17:23] delegate to that in certain circumstances
[00:17:26] and perhaps you, you know, you process all
[00:17:28] of the audio visual feed, let's say,
[00:17:31] locally and that stays local.
[00:17:33] I could imagine that would be a very good
[00:17:35] sort of end state.
[00:17:36] Watch this exchange carefully.
[00:17:39] The interviewer says engineers are doing
[00:17:41] 500 to a thousand times more work
[00:17:44] than they were six months ago.
[00:17:47] Hassabi's answer begins, I think models
[00:17:49] have many uses.
[00:17:51] He doesn't take the number.
[00:17:53] He doesn't agree with it.
[00:17:55] He redirects to a real modest claim.
[00:17:59] Iteration speed matters, smaller and
[00:18:02] faster, is often a better trade -off than
[00:18:05] slightly smarter and slower.
[00:18:08] This matters because the thousand X claim
[00:18:10] is one of the load -bearing myths of the
[00:18:13] current cycle.
[00:18:14] Working engineers report productivity
[00:18:17] gains in the range of noticeably helpful
[00:18:20] to maybe 50 percent on the right kinds of
[00:18:24] tasks.
[00:18:25] Three orders of magnitude isn't a
[00:18:28] measurement, it's a vibe.
[00:18:30] The Y Combinator stage is one of the
[00:18:32] places that vibe gets manufactured and
[00:18:35] amplified and what's striking is that
[00:18:38] Hassabi's, the most credentialed person in
[00:18:41] the room, quietly refuses to play.
[00:18:44] The real thing he does say is worth
[00:18:46] holding on to.
[00:18:48] The future is probably not one giant
[00:18:51] model in the cloud answering every query.
[00:18:55] It's a stack, small, fast, local models
[00:18:58] on your phone or your glasses or your
[00:19:01] robot handling most things, calling out to
[00:19:04] bigger models only when needed.
[00:19:07] That architecture has real implications
[00:19:09] for privacy, for energy, for who
[00:19:12] controls what.
[00:19:13] That get less airtime than the
[00:19:15] productivity hype, but will matter more in
[00:19:18] five years.
[00:19:20] back to context and memory models
[00:19:22] currently stateless, but you know,
[00:19:24] continue like what would the developer
[00:19:26] experience even be like for someone who's
[00:19:28] using a continual learning model?
[00:19:30] Like, you know, any idea like how you'd
[00:19:32] steer it?
[00:19:33] I think it's really interesting.
[00:19:34] I think that's one of the not having
[00:19:36] continual learning currently is one of the
[00:19:38] things holding back agents from doing full
[00:19:40] tasks.
[00:19:42] You know, I think they're really useful
[00:19:43] for aspects of tasks right now and you can
[00:19:46] patch them together and do some really
[00:19:48] cool things, but they don't adapt well
[00:19:51] with the context that you're in.
[00:19:53] And I think that's the missing piece for
[00:19:55] them being really kind of fire and forget
[00:19:58] and they'll figure it out themselves.
[00:20:00] You know, I think they need to be able to
[00:20:01] learn about the specific context
[00:20:04] that you're going to put them in.
[00:20:07] So I think we have to crack that to get
[00:20:10] full general intelligence.
[00:20:12] Where are we on reasoning?
[00:20:13] So models can do really impressive chain
[00:20:15] of thought now, but they still fail on
[00:20:17] things a smart undergrad wouldn't.
[00:20:19] What specifically needs to change and what
[00:20:21] progress do you expect in reasoning?
[00:20:24] There's a lot of innovation left in the
[00:20:27] thinking paradigms, I would say.
[00:20:28] Again, I think we're doing fairly
[00:20:31] simplistic things, fairly brute force.
[00:20:34] One could imagine, I think there's a lot
[00:20:37] of scope, for example, in monitoring the
[00:20:38] chain of thought, maybe interjecting
[00:20:40] midway through a thought process.
[00:20:43] I often get the impression with our
[00:20:45] systems and our competitor systems that
[00:20:47] they're almost overthinking, they're
[00:20:49] almost getting into sort of loops of
[00:20:51] things.
[00:20:51] One thing I sometimes like to do is play
[00:20:54] chess against Gemini.
[00:20:57] All the leading foundation models are
[00:20:59] pretty poor at games, which is quite
[00:21:01] interesting.
[00:21:01] It's very cool to kind of look at the
[00:21:04] thinking traces, because obviously these
[00:21:06] can be well understood.
[00:21:08] I can tell quite quickly if it's going off
[00:21:10] on a tangent and it's very sort of
[00:21:12] provable what the thinking is doing,
[00:21:15] whether it's useful or not.
[00:21:17] And so what we see is that sometimes it
[00:21:20] will consider a move, it will realize it's
[00:21:23] a blunder, but it can't find anything
[00:21:25] better.
[00:21:26] So it kind of goes back to that move and
[00:21:27] does it anyway.
[00:21:28] So you just shouldn't be seeing that
[00:21:31] happening in a very precise reasoning
[00:21:34] system.
[00:21:35] So there's just sort of huge gaps, I
[00:21:37] think, still.
[00:21:38] But it may only be one or two tweaks that
[00:21:39] are required to fix those kind of gaps,
[00:21:41] just to be clear.
[00:21:43] But I think that's pretty obvious there
[00:21:45] are there.
[00:21:45] And that's why you get this kind of jagged
[00:21:47] intelligence.
[00:21:49] On the one hand, it can solve gold medal
[00:21:51] problems in IMO, which is super hard.
[00:21:54] But on the other hand, as we've all seen,
[00:21:56] it can still make basic elementary math
[00:21:58] errors if you pose the question in a
[00:22:01] certain way, right?
[00:22:02] So or elementary reasoning errors.
[00:22:05] So there's just something to me about the
[00:22:06] almost an introspection about its own
[00:22:09] thought process that I feel like there's
[00:22:11] something maybe missing there.
[00:22:12] Agents This is the most useful diagnostic
[00:22:14] moment in the whole conversation.
[00:22:17] Not because the chess example is dramatic,
[00:22:20] but because it points at a specific
[00:22:22] cognitive move these systems can't
[00:22:25] reliably perform.
[00:22:28] Noticing that you've already evaluated
[00:22:30] something and trusting that evaluation
[00:22:32] enough to not redo it badly, a human
[00:22:36] chess player who realized a move was a
[00:22:38] blunder would not play the blunder.
[00:22:41] The model does because the chain of
[00:22:44] thought doesn't have stable internal
[00:22:46] state.
[00:22:47] Each step is a fresh generation
[00:22:50] conditioned on what came before, but
[00:22:53] there's no persistent self -model saying,
[00:22:55] I already concluded this is bad.
[00:22:58] It's reasoning without the connective
[00:23:00] tissue that makes reasoning hold together.
[00:23:04] This connects directly back to the memory
[00:23:06] problem from earlier.
[00:23:08] A model that can't remember what it just
[00:23:10] concluded 30 tokens ago is, in
[00:23:14] a real sense, not thinking.
[00:23:16] It's producing text that looks like
[00:23:19] thinking.
[00:23:20] Most of the time that's good enough.
[00:23:22] The text shaped like thinking lines up
[00:23:25] with actual reasoning because it was
[00:23:28] trained on actual reasoning.
[00:23:30] But the failure modes are exactly where
[00:23:32] you'd expect.
[00:23:34] Long chains, tight precision requirements,
[00:23:37] situations where the model has to hold
[00:23:39] itself to a prior commitment.
[00:23:41] The optimistic read is that this is one or
[00:23:44] two architectural tweaks away from being
[00:23:46] solved.
[00:23:48] Hasabi seems to think so.
[00:23:50] The pessimistic read is that real
[00:23:52] introspection is a much harder problem
[00:23:54] than it looks, and the current paradigm
[00:23:57] may not get there by adding more of
[00:23:59] itself.
[00:24:00] Either is plausible, neither is settled.
[00:24:04] are really big.
[00:24:05] Some would say they're hyped.
[00:24:06] I personally think they're just getting
[00:24:08] started.
[00:24:08] It's totally insane.
[00:24:10] What does DeepMind's internal research
[00:24:11] tell you about where agent capabilities
[00:24:13] actually are right now versus sort of the
[00:24:16] hype out there?
[00:24:17] I think we are, I agree with you.
[00:24:18] I think we're just at the beginning.
[00:24:20] You have to have an active system that can
[00:24:22] actively solve problems for you to get to
[00:24:25] AGI.
[00:24:26] That was always clear to us.
[00:24:27] So agents are that path.
[00:24:29] And I think we're just getting going.
[00:24:30] I think all of us are getting used to how
[00:24:32] do we best work?
[00:24:33] And you're leading the way in a lot of
[00:24:35] this in your own personal experiments.
[00:24:36] I'm sure many of you are doing that.
[00:24:38] I think how do you incorporate it into
[00:24:39] your workflow in a way that isn't just
[00:24:43] sort of a nice to have, but actually
[00:24:45] starting to do fundamental things?
[00:24:47] My impression is at the moment, we're all
[00:24:48] experimenting a lots of things, but we're
[00:24:51] only in the maybe the last couple of
[00:24:53] months starting to find the really
[00:24:54] valuable places.
[00:24:56] And the technology is probably only
[00:24:57] getting good enough for that to be the
[00:24:59] case, right?
[00:25:00] Whether it's not a kind of toy, nice
[00:25:02] demonstration, but actually really adding
[00:25:04] value to your time and efficiency.
[00:25:08] I often wonder, I see a lot of people
[00:25:10] working on like setting off dozens
[00:25:14] of agents for like 40 hours, but I'm not
[00:25:16] sure I've seen the output that yet of that
[00:25:19] quite justify that level of input going
[00:25:22] in.
[00:25:23] But I think it will come.
[00:25:24] So I still think we're in the
[00:25:26] experimentation phase.
[00:25:27] We haven't seen a triple A game that tops
[00:25:29] the app store charts that was sort of vibe
[00:25:32] coded yet, right?
[00:25:33] I've seen and I've programmed and I'm sure
[00:25:35] many we've all done little nice
[00:25:37] demonstrations and it's like amazing.
[00:25:38] I can do a prototype of theme park in half
[00:25:41] an hour now, which took me six months back
[00:25:43] when I was 17.
[00:25:44] It's kind of mind blowing.
[00:25:46] And I wish I got this feeling if I spent
[00:25:48] the whole summer working on it, you could
[00:25:50] make something really incredible, but it
[00:25:52] still needs craft and human sort of soul
[00:25:56] into it and taste.
[00:25:57] I think that's something that you have to
[00:26:00] make sure you still bring that to whatever
[00:26:03] is your building.
[00:26:04] And I think it still shows like it's not
[00:26:06] quite there yet because why haven't we
[00:26:08] seen a kid making a hit game
[00:26:11] that sells 10 million copies, right?
[00:26:13] That should be possible given the effort
[00:26:15] that's gone in.
[00:26:16] So something's still somehow missing.
[00:26:18] Maybe it's to do with the process or maybe
[00:26:20] it's to do with the tools.
[00:26:21] I'm not quite sure.
[00:26:22] You all probably know better than me
[00:26:23] because I'm sure you're all experimenting
[00:26:24] on that, but I haven't seen the result
[00:26:27] yet, which I would expect once this is
[00:26:29] really delivering that full value, which I
[00:26:32] think will come in the next six to 12
[00:26:34] months.
[00:26:34] This is the cleanest critique of Agent
[00:26:37] Hype anyone has offered from inside the
[00:26:39] field, and it came from Demis Hassabis on
[00:26:43] a Y Combinator stage.
[00:26:45] The test he proposes is falsifiable in the
[00:26:48] good sense.
[00:26:49] It's a clear, checkable threshold.
[00:26:52] If today's tools really are, as
[00:26:54] transformative as the demos suggest,
[00:26:57] somewhere on earth a teenager should
[00:26:59] already have shipped a runaway hit built
[00:27:01] mostly with them.
[00:27:03] It hasn't happened.
[00:27:05] He notices this.
[00:27:06] He's not sure why.
[00:27:08] A few hypotheses worth holding in tension.
[00:27:12] 1.
[00:27:12] The tools are genuinely close, but the
[00:27:14] missing ingredient is taste and craft,
[00:27:17] which can't be vibe -coded.
[00:27:19] A prototype is not a product.
[00:27:21] A working game loop is not a game people
[00:27:24] will play for 60 hours.
[00:27:26] 2.
[00:27:27] The bottleneck has moved, but it hasn't
[00:27:29] gone away.
[00:27:30] What used to take engineering effort now
[00:27:33] takes design and judgment effort, and
[00:27:36] there's no shortcut to that.
[00:27:39] 3.
[00:27:40] The tools really aren't as capable as the
[00:27:42] demos suggest, and the demo to ship
[00:27:45] product gap is doing a lot of marketing
[00:27:47] work.
[00:27:48] Probably all three are partly true.
[00:27:51] The thing to file away is that someone who
[00:27:53] runs one of the labs building these tools
[00:27:56] is publicly skeptical of the productivity
[00:27:59] claims being made on his behalf.
[00:28:02] That's a signal worth taking seriously the
[00:28:05] next time you hear a thousand X number.
[00:28:09] Some of it is like how much of it will be
[00:28:10] autonomous versus I mean, I don't think
[00:28:12] we'd see autonomous first.
[00:28:13] We would actually probably see people in
[00:28:15] this room operating at 1000X and then
[00:28:18] that's what you should see first.
[00:28:19] And then many of you, there'll be like
[00:28:22] games companies or other types of
[00:28:26] companies that have built some kind of
[00:28:28] best selling app, best selling game using
[00:28:31] these tools.
[00:28:32] That's what you should see first.
[00:28:34] And then more of that will get automated.
[00:28:36] I mean, some of it is like there's a human
[00:28:37] in there and then the human doesn't want
[00:28:39] to say that the agents did it yet.
[00:28:42] I think part of it might be though that
[00:28:45] this, we want to discuss like creativity.
[00:28:48] What I often say about that is like if we
[00:28:51] look at the things we've done like
[00:28:52] AlphaGo.
[00:28:53] So obviously very famously, you all know
[00:28:55] about the Move 37 in game two.
[00:28:57] And for me, I was waiting for a moment
[00:28:59] like that to start the science projects
[00:29:01] like AlphaFold.
[00:29:02] So we started AlphaFold like the day we
[00:29:04] got back from Sol, which is 10 years ago
[00:29:06] now.
[00:29:06] I'm going to career after this to
[00:29:08] celebrate the 10 year anniversary of
[00:29:10] AlphaGo.
[00:29:11] But it's not enough to come up with Move
[00:29:13] 37.
[00:29:14] That's pretty cool, very useful.
[00:29:17] But can it invent Go?
[00:29:19] That's what I want a system that can
[00:29:21] invent Go if you give it a high level
[00:29:23] description.
[00:29:24] Like a game you can learn the rules of in
[00:29:26] five minutes, but it takes many lifetimes
[00:29:29] to master.
[00:29:30] It's beautiful aesthetically, but you can
[00:29:33] play it in a few hours in an afternoon.
[00:29:36] So maybe you could imagine that would be
[00:29:38] the high level description I would give.
[00:29:40] And then I'd want the return, the thing I
[00:29:42] get back is Go.
[00:29:45] And clearly today's systems, I think,
[00:29:48] can't do that.
[00:29:49] So the question is why?
[00:29:51] And I think there's something still
[00:29:52] missing there.
[00:29:54] Well, someone in this room might make it.
[00:29:55] Then the answer would be there's nothing
[00:29:57] missing.
[00:29:57] It just was the way we were using the
[00:29:59] systems.
[00:29:59] And that might actually be the answer.
[00:30:01] It might be that our today's systems are
[00:30:03] capable of that with a brilliant enough
[00:30:05] creative person using it and providing
[00:30:08] that impetus, that the soul of the project
[00:30:11] and being able to probably being
[00:30:13] o -fay enough with the
[00:30:16] tools to almost be at one with the tools.
[00:30:18] I could imagine that would be happening if
[00:30:20] you experimented with the tools all day
[00:30:22] and all night, like probably many of you
[00:30:23] are doing.
[00:30:24] And you combine that with proper deep
[00:30:26] creativity, something more incredible
[00:30:30] could be done.
[00:30:30] Switching The Move 37 Versus Invent
[00:30:34] Go distinction is the most useful frame
[00:30:37] for thinking about AI creativity that
[00:30:40] anyone has offered in this cycle.
[00:30:42] Move 37 is filling in a very high -level
[00:30:45] pattern.
[00:30:47] It's a brilliant point inside a known
[00:30:49] space.
[00:30:50] Inventing Go is something else.
[00:30:53] It's building the space itself.
[00:30:56] What's missing in Hasabi's framing
[00:30:58] isn't pattern matching or guessing the
[00:31:01] next step.
[00:31:03] It's analogical reasoning that can leap
[00:31:05] across domains.
[00:31:07] The kind of move where someone notices
[00:31:09] that the math behind one problem is the
[00:31:12] same shape as the math behind a completely
[00:31:14] different one and uses that to build
[00:31:17] something new.
[00:31:19] Humans do this rarely and badly.
[00:31:22] The handful of people who do it well are
[00:31:25] the ones whose names end up on physics
[00:31:28] equations.
[00:31:29] He uses what he calls the Einstein test.
[00:31:33] Train a model on everything known by
[00:31:35] 1901.
[00:31:37] Does it produce special relativity in
[00:31:40] 1905?
[00:31:41] Nobody knows.
[00:31:43] Nobody has run that test cleanly.
[00:31:45] The reason the test matters is that it
[00:31:47] separates very sophisticated retrieval and
[00:31:50] recombination from genuine discovery.
[00:31:53] The current frontier sits firmly on the
[00:31:56] first side of that line.
[00:31:58] Whether it can cross is again a 50 -50
[00:32:01] kind of question, and the people who claim
[00:32:04] certainty in either direction are full of
[00:32:06] it.
[00:32:07] The honest framing.
[00:32:08] The systems can already do useful science
[00:32:11] by speeding up the parts of science that
[00:32:14] look like search.
[00:32:16] Whether they can do the parts that look
[00:32:18] like invention is the open question that
[00:32:21] defines the next decade.
[00:32:23] gears to open source, I mean, or open
[00:32:25] weights.
[00:32:27] I mean, the recent release of Gemma,
[00:32:29] you're making highly capable open and
[00:32:31] accessible ones that can actually run
[00:32:33] locally.
[00:32:34] What do you think that means for, will AI
[00:32:37] be something that is in the hands of the
[00:32:39] users instead of primarily in the cloud?
[00:32:42] And does that change who gets to build
[00:32:44] with these models?
[00:32:46] We're huge proponents of in general of
[00:32:48] open source and open science.
[00:32:50] And you mentioned Alpha Fold at the
[00:32:52] beginning.
[00:32:52] We put that all out there for free and all
[00:32:55] of our science work, even still today, we
[00:32:57] publish in the big journals.
[00:32:59] We wanted to create world leading models
[00:33:02] for their sizes.
[00:33:04] And so that's what hopefully we've done
[00:33:05] with Gemma and we're very committed to
[00:33:07] that path.
[00:33:08] And hopefully you'll experiment and build
[00:33:10] and enjoy using Gemma.
[00:33:11] I think it's been like 40 million
[00:33:13] downloads now and just in two and a half
[00:33:16] weeks.
[00:33:17] So we're really excited about that.
[00:33:18] And I also think it's important for there
[00:33:20] to be Western stacks on open source.
[00:33:23] I've seen a lot of the Chinese models are
[00:33:24] excellent and they're currently leading in
[00:33:28] open source.
[00:33:28] And we think Gemma is very competitive for
[00:33:30] its sizes in all those respects.
[00:33:34] And for us, I mean, there is a question of
[00:33:35] resources, talent and compute.
[00:33:38] Like nobody has enough spare compute to
[00:33:40] just make two frontier
[00:33:42] models at maximum size with different
[00:33:45] attributes.
[00:33:46] So that's pretty difficult.
[00:33:47] But also for now, what we've decided is
[00:33:50] that our edge models, the things we want
[00:33:53] to use for Android and glasses and
[00:33:55] robotics, it's best that they're open
[00:33:58] models because they're vulnerable anyway
[00:34:00] on the surface.
[00:34:01] Once you put them out on the surfaces, so
[00:34:03] they might as well be actually fully open.
[00:34:05] So we've sort of made a decision to kind
[00:34:08] of unify that at the kind of we call
[00:34:11] it nano size level.
[00:34:14] And so that actually works for us
[00:34:16] strategically as well.
[00:34:18] And we hope as many people as possible
[00:34:20] build There are two answers braided
[00:34:21] together here, and it's worth pulling them
[00:34:24] apart.
[00:34:25] The first is the principled answer.
[00:34:28] Open science is good.
[00:34:30] Deep mind is always published.
[00:34:32] Gemma is the continuation of that.
[00:34:36] Fine.
[00:34:37] The second is the strategic answer, and
[00:34:39] it's more interesting.
[00:34:40] Edge models are gonna be on your phone, in
[00:34:43] your glasses, in your house.
[00:34:46] Once they're out there, they're gonna be
[00:34:48] reverse engineered and fine tuned and run
[00:34:51] locally whether DeepMind likes it or not.
[00:34:54] So the rational move is to ship them open
[00:34:57] in the first place, capture the developer
[00:34:59] mind share, and make sure the open
[00:35:02] standard everyone builds on is yours
[00:35:05] rather than someone else's.
[00:35:08] It's the same logic Google used with
[00:35:10] Android against iOS.
[00:35:13] Open the layer, you can't control anyway.
[00:35:16] Close the layer where you can extract
[00:35:18] value.
[00:35:19] The Western stack's framing is the part
[00:35:22] that deserves the most pressure.
[00:35:25] China's open models, Quen, DeepSeek,
[00:35:28] are not Chinese in any meaningful sense
[00:35:31] beyond the nationality of the lab.
[00:35:34] They run anywhere, get fine tuned by
[00:35:37] anyone, and carry values that reflect
[00:35:39] their training data more than their flag.
[00:35:42] The Cold War framing flatters Western
[00:35:45] policy makers and gets export control
[00:35:48] budgets approved, but it doesn't really
[00:35:50] describe the technical reality.
[00:35:53] The world's developers will use whatever
[00:35:55] works and is cheap.
[00:35:57] That's the actual competition.
[00:35:59] Western stack is a slogan that runs faster
[00:36:02] than the underlying engineering question
[00:36:04] of which models are actually best.
[00:36:07] on it.
[00:36:08] And of course, we'll be building on that
[00:36:09] too.
[00:36:10] Earlier before we came on, I got to show
[00:36:12] you a demo of my version of Samantha from
[00:36:15] her, which is harrowing for me to try to
[00:36:18] demo something to you.
[00:36:19] And it worked, which is amazing.
[00:36:22] Gemma and I was built multimodal and I
[00:36:24] spent a lot of time with a bunch of the
[00:36:25] models and I mean, the depth of the
[00:36:27] context and the tool use with speech
[00:36:30] directly to model.
[00:36:32] There was nothing like far none like the
[00:36:34] best one.
[00:36:35] Yeah, I think that's a sort of still
[00:36:37] slightly underappreciated aspect of the
[00:36:40] Gemma and I series is we started it being
[00:36:43] multimodal from the start.
[00:36:45] That made it a little bit more difficult
[00:36:46] actually to begin with because then just
[00:36:48] focusing on text, for example.
[00:36:50] But we believe we're going to gain from
[00:36:52] that in the long run.
[00:36:53] And I think we're seeing that now for
[00:36:55] things like world model building.
[00:36:58] So stuff like Genie that we build on top
[00:37:00] of Gemma and I, I think it's going to be
[00:37:02] really important for things like robotics.
[00:37:04] So this is why Gemma and I robotics, just
[00:37:06] many of you probably played around with, I
[00:37:08] think it's going to be built on multimodal
[00:37:10] foundation models, the robotics models.
[00:37:12] And we think we have a sort of competitive
[00:37:15] advantage with Gemma and I being so strong
[00:37:17] at multimodal.
[00:37:18] We're using it increasingly in things like
[00:37:20] Waymo.
[00:37:21] But also if you imagine devices and
[00:37:24] assistance, that digital assistance that
[00:37:27] come with you into the real world, you
[00:37:28] know, maybe on your phone or glasses or
[00:37:30] some other device, it needs to understand
[00:37:33] the physical world around you and
[00:37:35] intuitive physics and the physical
[00:37:38] context you're in.
[00:37:40] And that's what our systems are extremely
[00:37:42] good at.
[00:37:42] And I think you found that's why you've
[00:37:44] enjoyed using it in your setup.
[00:37:45] We're planning to continue on that.
[00:37:47] And I think we're far and away the
[00:37:48] strongest models on those types of
[00:37:51] problems.
[00:37:52] So the cost of inference is dropping fast.
[00:37:55] What becomes possible when inference is
[00:37:56] essentially free?
[00:37:58] And how does that change what your team is
[00:38:00] actually optimizing for?
[00:38:02] Yeah, I'm not sure inference will ever be
[00:38:05] essentially free.
[00:38:06] I mean, there's sort of Jevons paradox and
[00:38:08] other things about like, I think we'll
[00:38:09] just end up using all of us will end up
[00:38:12] using whatever we can get our hands on.
[00:38:15] And you could imagine millions of agents,
[00:38:19] swarms of agents working together on
[00:38:20] things.
[00:38:21] That's one way to use the inference.
[00:38:22] Or you could imagine single agents or
[00:38:25] smaller groups of agents thinking for in
[00:38:28] multiple directions and then ensembling
[00:38:30] that.
[00:38:31] So we're experimenting with all these
[00:38:32] things, probably many of you are all of
[00:38:34] that will use up any inference, I think,
[00:38:37] that's available.
[00:38:38] I mean, one day, maybe it can be almost
[00:38:41] cost zero.
[00:38:42] Certainly the energy if we solve fusion
[00:38:43] or, you know, superconductors or, you
[00:38:45] know, optimal batteries or some set of
[00:38:47] those things, which I think we will do
[00:38:49] with material science.
[00:38:50] Energy costs will be essentially zero, but
[00:38:52] there'll still be the physical creation of
[00:38:54] the chips and other things.
[00:38:56] There'll be some bottleneck, at least for
[00:38:59] the next few decades, I think.
[00:39:02] And so if that's the case, there'll still
[00:39:03] be rationing on the inference side.
[00:39:06] We'll still have to use it, I think,
[00:39:08] efficiently.
[00:39:08] Yeah.
[00:39:09] Well, luckily, the smaller models are
[00:39:10] getting smarter and smarter, which is
[00:39:11] fantastic.
[00:39:13] We got a lot of bio and biotech founders
[00:39:15] in the audience.
[00:39:16] I can see a few.
[00:39:17] Alpha 3 took us beyond proteins to a broad
[00:39:20] spectrum of biomolecules.
[00:39:21] How close are we to modeling full cellular
[00:39:24] systems?
[00:39:25] Or is that still a fundamentally harder
[00:39:27] problem in a class of tone?
[00:39:29] Well, isomorphic labs, which we spun out
[00:39:31] from DeepMind after we did Alpha
[00:39:35] Fold 2, which is going amazingly well.
[00:39:38] It's trying to build out not just Alpha
[00:39:41] Fold, it's just one piece of the drug
[00:39:43] discovery process, as many of you know.
[00:39:46] But we're trying to do the adjacent
[00:39:48] biochemistry and chemistry to design the
[00:39:50] right compounds with the right properties
[00:39:52] and so on.
[00:39:53] We'll have some big announcements very
[00:39:54] soon to talk about on that front.
[00:39:57] I think that's going really well.
[00:39:58] Eventually, you want a whole virtual cell.
[00:40:01] I've talked about this in many of my
[00:40:03] science talks about a full working
[00:40:05] simulation of a cell that you can perturb
[00:40:07] and then the outputs of that would be
[00:40:11] close enough to experimental that it's
[00:40:13] useful.
[00:40:14] You could skip out a lot of the search
[00:40:16] steps and generate loss of synthetic data
[00:40:19] to train other models that then would
[00:40:21] predict things about real cells.
[00:40:24] I think we're about 10 years away,
[00:40:27] probably from something like a virtual
[00:40:28] cell, like a full virtual cell.
[00:40:30] We're working on the DeepMind science side
[00:40:33] on a virtual nucleus.
[00:40:36] Cell nucleus first because it's relatively
[00:40:38] self -contained.
[00:40:39] The trick with all of these things is can
[00:40:41] you pick a slice of the complexity?
[00:40:44] Eventually, you want to model a human
[00:40:45] body.
[00:40:46] But can you model it down to the right
[00:40:48] level of detail?
[00:40:50] What slice can you take out of it that
[00:40:53] will be self -contained enough?
[00:40:55] You can model and approximate the inputs
[00:40:57] and outputs into that self - contained
[00:40:59] system and then just focus on the self
[00:41:01] -contained system.
[00:41:02] A nucleus is quite interesting from that
[00:41:04] perspective.
[00:41:06] Then the other issue is just there's not
[00:41:08] enough data yet.
[00:41:09] You need data.
[00:41:11] I talked to various top scientists about
[00:41:14] who work on electron microscopes and other
[00:41:16] imaging things.
[00:41:17] If we could image a live cell without
[00:41:20] killing the cell, that would be game
[00:41:23] changing, obviously, because then you
[00:41:24] could convert it into a vision problem,
[00:41:26] which we would know how to solve.
[00:41:28] At the moment, there are at least I'm not
[00:41:30] aware of any techniques that can give you
[00:41:32] a kind of nanometer resolution but
[00:41:36] without destroying in a live
[00:41:39] dynamic cell.
[00:41:40] You can see all the interactions.
[00:41:42] You can take static images of that
[00:41:44] resolution, obviously, really detailed
[00:41:46] now.
[00:41:46] That's quite exciting, but it's not enough
[00:41:48] to turn it just into
[00:41:51] a complex vision problem.
[00:41:54] That's one way it could be solved.
[00:41:56] It could be a hardware -driven, data
[00:41:57] -driven solution, or it could be that we
[00:42:00] build better learned simulators
[00:42:03] of these dynamical systems.
[00:42:05] That's the more modeling way of solving
[00:42:08] it.
[00:42:08] The 10 -year virtual cell estimate is
[00:42:11] worth holding next to his five -year AGI
[00:42:14] estimate, because the two timelines pull
[00:42:17] in opposite directions.
[00:42:19] If general intelligence really arrives by
[00:42:21] 2030, then a virtual cell by 2035
[00:42:25] is a strange forecast.
[00:42:27] An AGI worth the name should compress
[00:42:30] that timeline dramatically.
[00:42:33] Either the AGI claim is softer than it
[00:42:36] sounds, or the cell timeline is
[00:42:39] conservative, probably both, in different
[00:42:42] ways.
[00:42:43] The real observation here is one of the
[00:42:46] most useful in the talk.
[00:42:48] Hasabi's names the actual bottleneck for
[00:42:51] biology AI, and it isn't model
[00:42:54] architecture, it's data acquisition.
[00:42:58] We cannot currently see what a cell is
[00:43:00] doing at the resolution we'd need to learn
[00:43:04] its dynamics.
[00:43:05] Static, high resolution images, yes.
[00:43:09] Live low resolution video, yes.
[00:43:12] Both at once, no.
[00:43:14] Until that changes, learned simulators
[00:43:17] will be filling in gaps the data can't
[00:43:20] directly pin down.
[00:43:22] This points at something founders in the
[00:43:24] room should hear loudly.
[00:43:26] The defensible AI for biology companies of
[00:43:29] the next decade will be the ones that
[00:43:31] solve data acquisition problems, not the
[00:43:34] ones that wrap better APIs around existing
[00:43:38] data.
[00:43:39] The bottleneck is in the world of atoms.
[00:43:41] Microscopy, sample prep, single cell,
[00:43:45] anything.
[00:43:46] Whoever cracks live cell imaging at
[00:43:49] nanometer scale gives the modeling people
[00:43:52] their alpha fold moment.
[00:43:55] The modeling people on their own can't get
[00:43:57] there.
[00:43:58] You've been looking at all kinds of
[00:43:59] science, not just bio.
[00:44:01] There's material science, drug discovery,
[00:44:03] climate modeling, mathematics.
[00:44:05] If you had to rank which scientific domain
[00:44:07] will transform the most dramatically the
[00:44:09] next five years, what's in your list?
[00:44:11] They're all so exciting.
[00:44:13] That for me has been my main passion and
[00:44:16] always the reason why I've worked on AI
[00:44:18] for my whole career for 30 plus years now
[00:44:20] is to use AI as the ultimate tool.
[00:44:23] I always thought AI would be the ultimate
[00:44:24] tool for science and to advance scientific
[00:44:27] understanding, scientific discovery, and
[00:44:30] things like medicine, and just our
[00:44:32] understanding of the universe around us.
[00:44:34] Actually, when you mentioned our original
[00:44:35] way we used to articulate our mission
[00:44:37] statement, which is still the way we think
[00:44:39] about it, there was two steps to it.
[00:44:41] Step one was solve intelligence, i .e.
[00:44:43] build AGI.
[00:44:44] Then step two was use it to solve
[00:44:46] everything else.
[00:44:47] We had to change that a bit over time
[00:44:48] because people were like, do you really
[00:44:49] mean solve everything else?
[00:44:51] We did mean that.
[00:44:52] I think people are sort of understanding
[00:44:54] what that means today, but specifically I
[00:44:56] was meaning solve other what I call root
[00:44:58] node problems in science.
[00:45:00] Areas of science that would unlock whole
[00:45:02] new branches or avenues of discovery.
[00:45:05] Alphafold is the prototypical example of
[00:45:07] what we want to do.
[00:45:08] Over 3 million researchers around the
[00:45:10] world, pretty much every biology
[00:45:12] researcher in the world uses Alphafold
[00:45:14] now.
[00:45:15] I was told by some of my farmer executive
[00:45:18] friends that almost every drug
[00:45:21] discovered from now on will have used
[00:45:24] Alphafold at some point in the drug
[00:45:26] discovery process.
[00:45:27] So that's something we're very proud of
[00:45:29] and it's the sort of impact that we hope
[00:45:31] to have with AI.
[00:45:32] But I do think it's just the beginning.
[00:45:34] I don't really see any area of science or
[00:45:37] engineering that this won't be able to
[00:45:38] help be helpful with.
[00:45:39] The ones you mentioned, I think we're
[00:45:41] almost like an Alphafold one moment.
[00:45:44] So we've got very promising results, but
[00:45:46] it's not quite solved the grand challenge
[00:45:49] yet in that domain.
[00:45:50] But I think we're going to have a lot to
[00:45:51] talk about in the next couple of years on
[00:45:53] all those areas you mentioned, materials,
[00:45:55] which I think is very exciting all the way
[00:45:57] to mathematics.
[00:45:59] In science, it feels Promethean.
[00:46:01] It's like, here is this capability.
[00:46:04] I think so.
[00:46:05] Along with that, including the parable
[00:46:08] of Prometheus, we have to also be careful
[00:46:10] with how we use that and what we use it
[00:46:13] for and also the misuse that can happen
[00:46:16] with those same tools.
[00:46:17] A lot of people in this room are trying to
[00:46:18] build companies applying AI to science.
[00:46:21] For them, what's the difference between a
[00:46:22] startup that actually advances the
[00:46:24] frontier interview versus one that's just
[00:46:26] wrapping an API around a foundation model
[00:46:28] and calling it AI for science?
[00:46:30] Well, look, I think there's one of the
[00:46:32] things I would recommend.
[00:46:32] I'm trying to think about, and I think you
[00:46:34] mentioned this to me before, what would I
[00:46:36] do today myself if I was sitting in your
[00:46:38] place and my commentator looking at
[00:46:40] things?
[00:46:41] One thing you have to do is obviously
[00:46:42] intercept where the AI tech is going.
[00:46:46] That's one hard part of it.
[00:46:47] But I do think there's huge scope for
[00:46:50] combining where AI is going with some
[00:46:53] other deep technology area.
[00:46:54] I just think that that sweet spot is
[00:46:56] whether there's materials or medicine or
[00:46:59] other really hard areas of science.
[00:47:01] I think that those kinds of
[00:47:03] interdisciplinary teams, especially if it
[00:47:05] involves the world of atoms as well,
[00:47:07] there's not going to be a shortcut to
[00:47:09] that, at least in the foreseeable future.
[00:47:12] Those are areas that are pretty safe from
[00:47:14] just getting swamped by whatever the next
[00:47:17] update is to the foundation models.
[00:47:19] I think if you're looking for things like
[00:47:21] that, that's one of the more defensible
[00:47:23] areas I would say.
[00:47:24] I've always loved deep tech.
[00:47:26] I'm kind of biased towards deep tech
[00:47:27] things.
[00:47:29] I think nothing that's really long lasting
[00:47:32] and worthwhile is easy.
[00:47:35] I'm always being drawn to deep
[00:47:37] technologies.
[00:47:38] Obviously AI was like that back in 2010
[00:47:40] when we started out.
[00:47:41] It was thought to just, we know it doesn't
[00:47:44] work kind of thing is what I was told by
[00:47:46] investors and even in academia, it was
[00:47:49] considered to be a very niche subject that
[00:47:52] we tried in the 90s and we know doesn't
[00:47:54] work.
[00:47:55] But if you have belief and conviction in
[00:47:57] your idea why it's different this time or
[00:48:00] what special combination from your
[00:48:02] background that you had, ideally your
[00:48:04] expert in both those areas, both the
[00:48:06] machine learning and the other area you're
[00:48:08] applying it to or you can create a
[00:48:09] founding team with that expertise, I think
[00:48:11] there's huge impact to be made there and
[00:48:14] huge value to be built there.
[00:48:15] That's This is genuinely good advice, and
[00:48:18] it's also a slightly awkward thing to say
[00:48:20] to a Y Combinator audience.
[00:48:22] Most of the companies in that room are
[00:48:25] software rappers and agents and vertical
[00:48:28] sass.
[00:48:29] The Hasabi's recommendation, Go Deep,
[00:48:32] Touch Adams, Combined Fields, describes
[00:48:35] maybe 5 % of what gets funded by YC,
[00:48:39] and almost none of what gets funded
[00:48:41] quickly, the reason it's good advice
[00:48:43] anyway.
[00:48:44] The moat question gets harder every year
[00:48:47] for pure software AI startups.
[00:48:50] If your defensibility is we prompted GPT
[00:48:53] cleverly, the next model release eats you.
[00:48:57] If your defensibility is we built
[00:48:59] proprietary hardware to acquire training
[00:49:02] data, nobody else has.
[00:49:05] You're a real company.
[00:49:07] The hard part is that the second kind of
[00:49:09] company takes longer to build, costs
[00:49:12] more, and doesn't fit the YC tempo as
[00:49:16] cleanly.
[00:49:17] The other thing he says, in passing, is
[00:49:20] more important than it sounds.
[00:49:22] Work on things you'd work on anyway.
[00:49:25] This is survival advice for a field whose
[00:49:28] direction nobody can predict 5 years out.
[00:49:31] If the only reason you're working on
[00:49:33] something is that it's the current hot
[00:49:35] thing, you'll quit when it stops being
[00:49:38] hot.
[00:49:38] If you're working on it because the
[00:49:40] underlying problem genuinely matters
[00:49:43] to you, you'll keep working on it through
[00:49:46] the inevitable winters and pivots.
[00:49:50] The people who built the current AI moment
[00:49:52] were mostly the people who kept working on
[00:49:55] neural networks during the decade when
[00:49:58] everyone agreed neural networks didn't
[00:50:01] work.
[00:50:01] The pattern is older than this cycle and
[00:50:04] it'll outlive it.
[00:50:06] a really important message.
[00:50:07] I mean, it's easy to forget.
[00:50:10] Basically, once you've done it, you've
[00:50:11] done it, but before you've done it, people
[00:50:13] are arrayed against you.
[00:50:14] Oh, sure.
[00:50:15] I mean, no one believes in it, which is
[00:50:16] why I think you've also got to work in
[00:50:19] things that you're genuinely passionate
[00:50:21] about.
[00:50:22] Like for me, I really worked on AI no
[00:50:25] matter what happened.
[00:50:26] I just decided from a very young age, it
[00:50:28] was the thing that could be the most
[00:50:31] consequential thing I could think of.
[00:50:33] It's turned out that way, but it might
[00:50:34] not.
[00:50:34] Maybe we would have been 50 years too
[00:50:36] early.
[00:50:36] And it was also the most interesting thing
[00:50:38] I could think of working on.
[00:50:40] And so I would still be working on AI
[00:50:42] today, even if we were still in a little
[00:50:46] garage somewhere and it still wasn't quite
[00:50:48] working.
[00:50:48] I would have still been trying to find
[00:50:49] maybe I'd have been back in academia or
[00:50:51] something, but I would have found some way
[00:50:53] of continuing to work on it.
[00:50:55] So, I mean, Alpha Fold was an example of a
[00:50:56] spike that you pursued and it worked.
[00:51:00] What makes the scientific domain ripe for
[00:51:01] an Alpha Fold style breakthrough?
[00:51:03] And is there a pattern, a certain
[00:51:05] objective function?
[00:51:07] The way I should write this up at some
[00:51:09] point when I have five minutes spare, but
[00:51:11] the lesson I've learned from all the Alpha
[00:51:14] projects we've done, specifically Alpha Go
[00:51:16] and Alpha Fold is I think the techniques
[00:51:19] we have and the problems I like to look
[00:51:22] for are great in if the situation can be
[00:51:25] described as massive combinatorial search
[00:51:27] space, the more massive, the better in
[00:51:29] some ways.
[00:51:30] So no brute force or special case
[00:51:31] algorithm will solve it.
[00:51:33] And that's true of Go moves and of
[00:51:35] different configurations of proteins, far
[00:51:38] more than the atoms in the universe, both
[00:51:40] of those.
[00:51:41] And then you have a clear objective
[00:51:43] function.
[00:51:44] So, you know, you could think of it as
[00:51:45] minimizing the free energy in the proteins
[00:51:47] or, you know, the winning the game of Go.
[00:51:49] So you need to specify your objective
[00:51:52] function clearly so you can heal time and
[00:51:54] then enough data and or simulator
[00:51:57] that can generate you lots of
[00:52:00] indistribution
[00:52:03] synthetic data.
[00:52:04] If those things are true, then I think
[00:52:06] with today's methods, you can go a long
[00:52:09] way into tackling and finding the kind of
[00:52:11] needle in the haystack that you need to
[00:52:13] for the solution that you're trying to
[00:52:15] look for.
[00:52:15] And I think of just drug discovery, by the
[00:52:17] way, in the same way, right, there is a
[00:52:19] compound out there that would solve this
[00:52:21] disease if one could find it, if one could
[00:52:24] only find it, right, and that wouldn't
[00:52:26] have any side effects and so on.
[00:52:27] And as long as the laws of physics allows
[00:52:29] it, then the only question is how do you
[00:52:32] find it in an efficient way in a tractable
[00:52:34] way?
[00:52:35] I think we showed for the first time,
[00:52:37] actually, with AlphaGo, that these systems
[00:52:39] could find those kinds of needles in a
[00:52:42] haystack, in that case, you know, the
[00:52:44] perfect Go move.
[00:52:45] I guess to get a little meta, I mean,
[00:52:46] we're talking about humans using these
[00:52:48] methods to create AlphaFold, but then
[00:52:51] there's a meta level, which is humans
[00:52:53] using AI to explore the space of possible
[00:52:56] hypotheses.
[00:52:57] How close are we to AI systems that can do
[00:52:59] genuine scientific reasoning, not just
[00:53:02] pattern matching on data?
[00:53:03] I think we're close.
[00:53:06] We're working on these general systems,
[00:53:08] like that, like, we have this system
[00:53:10] called co -scientist, and we have other
[00:53:12] algorithms like AlphaVolve that can go a
[00:53:15] little bit beyond what the basic Gemini
[00:53:16] will do.
[00:53:17] And obviously, all the frontier labs are
[00:53:19] experimenting in this way.
[00:53:20] I've yet to seen anything so far, and we
[00:53:23] all tinker with same things, you know,
[00:53:25] some math problems that are a little bit
[00:53:26] harder than IMO and so on.
[00:53:28] I haven't seen anything yet that is
[00:53:31] a true, genuine, you know, massive
[00:53:34] discovery.
[00:53:35] That's my personal opinion.
[00:53:36] I think it's coming.
[00:53:38] I think it may be related to this earlier
[00:53:41] thing we discussed about creativity and
[00:53:44] actually going on beyond the bounds of
[00:53:46] what's known.
[00:53:47] So clearly, that's just not pattern
[00:53:49] matching at that point, because there is
[00:53:50] no pattern to match to, and it's a bit
[00:53:52] more than extrapolation.
[00:53:54] It's some kind of analogical reasoning.
[00:53:56] And I don't think these systems have that,
[00:53:58] or at least we're not using them in the
[00:54:00] right way to do that.
[00:54:01] So the way I often say that in science is,
[00:54:03] can it come up with a hypothesis that's
[00:54:06] really interesting, not just solve one?
[00:54:08] When I say just, we're now talking about
[00:54:10] just like solving the Riemann hypothesis
[00:54:12] or something.
[00:54:12] This would be obviously amazing.
[00:54:14] Well, one of the Millennium Prize
[00:54:15] problems, and maybe we're a couple of
[00:54:17] years out from doing that, but I'd like to
[00:54:20] solve P equals NP.
[00:54:21] That's my favourite one.
[00:54:22] But can you, but even harder than that
[00:54:24] would be to come up with a new set of
[00:54:26] Millennium Prize problems that were
[00:54:29] regarded by top mathematicians to be as,
[00:54:32] you know, deep and meaningful and worthy
[00:54:34] of lifetime of study and effort to
[00:54:37] solve.
[00:54:38] I think that's another level harder.
[00:54:41] And we don't have, you know, I still don't
[00:54:44] think we know how to do that.
[00:54:46] I don't think it's magical, though.
[00:54:48] I do think these systems will be
[00:54:49] eventually be able to do that.
[00:54:51] Maybe we're missing one or two things.
[00:54:53] And then the way we would test that is
[00:54:54] sometimes called in my Einstein test,
[00:54:56] which is, can you train a system with the
[00:55:00] knowledge of cutoff of 1901?
[00:55:02] And then will it come up with what
[00:55:04] Einstein did in 1905, including special
[00:55:06] relativity, his Annas Mirablas?
[00:55:09] Can it do that?
[00:55:11] Right?
[00:55:11] And then I think we could run that test.
[00:55:14] Maybe we should just run that test and
[00:55:16] keep seeing if that's possible.
[00:55:18] And once that is, then I think we're on
[00:55:19] the verge of the systems being able to
[00:55:21] invent something new, truly novel.
[00:55:24] The Einstein test is the cleanest
[00:55:26] benchmark for AI discovery anyone has
[00:55:29] proposed, and it's notable that no major
[00:55:32] lab has publicly run it.
[00:55:35] The reason, probably, is that everyone
[00:55:37] suspects the answer would be embarrassing.
[00:55:41] A model trained on pre -1905 physics
[00:55:44] would with high confidence produce
[00:55:46] competent extensions of pre -1905
[00:55:50] physics.
[00:55:51] It would not produce special relativity,
[00:55:54] because special relativity required the
[00:55:57] specific human move of noticing that one
[00:56:00] of the foundational assumptions of the
[00:56:02] field, absolute simultaneity, was
[00:56:05] wrong.
[00:56:06] That's the gap.
[00:56:08] Current systems are extraordinary at
[00:56:10] producing the next plausible continuation
[00:56:14] of a body of knowledge.
[00:56:16] They are not yet at producing the specific
[00:56:19] kind of move, where someone says the
[00:56:22] foundational assumption everyone is making
[00:56:24] is wrong, and here's what the world looks
[00:56:27] like if we drop it.
[00:56:29] The harder version of the test Hasabi's
[00:56:31] proposes, generate new millennium prize
[00:56:35] problems, not just solve them, gets at the
[00:56:37] same thing.
[00:56:38] Posing a great question is, in some real
[00:56:41] sense, a deeper cognitive move than
[00:56:44] answering one.
[00:56:45] It requires holding the entire field in
[00:56:48] mind well enough to notice the shape of
[00:56:51] what's missing.
[00:56:52] We don't know how to train for that.
[00:56:55] We barely know how to evaluate it.
[00:56:57] The honest framing.
[00:56:59] AI is already a huge accelerant for
[00:57:02] science in domains that look like search.
[00:57:06] Alpha fold is the proof whether it can do
[00:57:09] the parts of science that look like
[00:57:11] invention is the question that decides
[00:57:14] whether AGI means what its loudest
[00:57:17] advocates say it means or something more
[00:57:20] modest and more useful.
[00:57:22] Hasabi's thinks the systems will
[00:57:25] eventually get there.
[00:57:27] He doesn't claim they're there yet.
[00:57:29] That precision is rarer than it should be.
[00:57:31] So last, last question for the people who
[00:57:33] are deeply technical in this room, who
[00:57:35] want to work on something, you know, even
[00:57:38] close to the scale that what you've
[00:57:40] created with, you know, it's one of the
[00:57:42] largest AI efforts in the world.
[00:57:43] And you've been a pioneer for all these
[00:57:45] years.
[00:57:46] So for that, I think everyone in this
[00:57:47] room, thanks you and the folks at DeepMind
[00:57:50] very, very deeply from the bottom of our
[00:57:52] hearts.
[00:57:52] Thank you.
[00:57:53] What's the thing that you know now about
[00:57:55] building at the frontier that you wish you
[00:57:56] known at 25?
[00:57:59] I think we covered some of it in terms of
[00:58:01] actually you work out that going after
[00:58:03] hard problems and deep problems is
[00:58:07] no more difficult in some ways than going
[00:58:09] after a shallower, simpler, more
[00:58:11] superficial problem.
[00:58:12] They're just differently difficult.
[00:58:17] There's life's very short.
[00:58:20] And you know, you only have so much time
[00:58:21] and energy, you might as well put your
[00:58:24] life force into something that will really
[00:58:26] make a difference if you hadn't done it,
[00:58:29] if you hadn't been there to push it.
[00:58:31] So I would just think of it through that
[00:58:33] lens.
[00:58:33] And then the other thing is if you're, if
[00:58:35] you are in and we talked about deep tech,
[00:58:37] and I love interdisciplinary work, and I
[00:58:40] think that's going to be even more
[00:58:41] prevalent in the next few years in
[00:58:44] combinations of fields and finding the
[00:58:47] connections between those fields.
[00:58:49] And it's going to be even easier to do
[00:58:51] that with AI.
[00:58:52] And then the only other thing I would say
[00:58:53] is if you have your, depending on what
[00:58:56] your AGI timeline is, you know, mine's
[00:58:58] like 2030 or something like this, then if
[00:59:01] you start off on a deep tech journey
[00:59:03] today, usually that you're talking about a
[00:59:06] 10 -year journey for true deep tech, in my
[00:59:09] opinion.
[00:59:10] So then now you have to just consider AGI
[00:59:12] appearing in the middle of that journey.
[00:59:15] So what does that mean?
[00:59:16] It doesn't, it's not bad necessarily, but
[00:59:18] you have to take that into account, right,
[00:59:21] to will it be able to leverage it?
[00:59:22] What will the AGI system do with it?
[00:59:25] And it goes a little bit back to what you
[00:59:27] said earlier about AlphaFold and general
[00:59:28] AI systems.
[00:59:29] So one thing I can think see happening is
[00:59:31] Gemini, Claude or one of these general
[00:59:34] systems making use of AlphaFold like
[00:59:37] specialized systems as tools.
[00:59:39] I don't think we're going to have it just
[00:59:40] in one giant brain because it will have
[00:59:42] too much regression in, if I put all the
[00:59:45] proteins into, you know, Gemini, that
[00:59:48] wouldn't make sense.
[00:59:48] We don't need Gemini to do protein
[00:59:50] folding.
[00:59:51] Going back to your information efficiency,
[00:59:52] it would definitely affect its language
[00:59:54] skills or something like that, right, in a
[00:59:56] bad way.
[00:59:57] So much better, I think, is to have really
[00:59:59] good general purpose tool usage models
[01:00:02] that will then, maybe they could even
[01:00:04] train those specific tools, but they would
[01:00:06] be in a separate system.
[01:00:09] So I think that's kind of interesting to
[01:00:10] think through the implications of that and
[01:00:12] then what you might build today.
[01:00:14] Also physical things too, like what kinds
[01:00:16] of factories would you build?
[01:00:17] What sorts of, you know, finance systems
[01:00:20] and so on.
[01:00:21] So I just think you need to really take
[01:00:23] that seriously and on the one hand is like
[01:00:25] kind of a, imagine what that world would
[01:00:26] look like and then build something that
[01:00:28] would be useful if that comes in halfway
[01:00:30] The architectural prediction at the end is
[01:00:33] the most concrete thing he says about the
[01:00:36] shape of the next decade, and it's worth
[01:00:39] pulling out.
[01:00:40] Hassabi's thinks the future is not a
[01:00:42] single monolithic AGI that does
[01:00:45] everything.
[01:00:46] It's a general purpose orchestrator,
[01:00:49] something like a future Gemini, or Claude,
[01:00:52] that calls specialized tools like Alpha
[01:00:55] Fold for the things those tools do better
[01:00:58] than any general model could.
[01:00:59] That's a more pluralistic picture than the
[01:01:03] one model to rule them all, framing, that
[01:01:05] dominates a lot of AGI talk.
[01:01:08] It also has practical implications for
[01:01:10] what's worth building.
[01:01:12] If the future stack is generalist plus
[01:01:15] specialist, then a specialist that's the
[01:01:18] best in the world at one valuable thing,
[01:01:21] protein folding, material simulation,
[01:01:25] weather prediction, anything where the
[01:01:27] data and the structure favor a dedicated
[01:01:29] system has a real seat at the table
[01:01:32] even after AGI arrives.
[01:01:35] It's not necessarily competing with the
[01:01:38] frontier model.
[01:01:39] It's getting called by it.
[01:01:41] The other thing in his closing answer that
[01:01:43] deserves attention is the timing argument.
[01:01:47] If you're building a 10 -year deep tech
[01:01:49] company starting today, and AGI shows
[01:01:52] up in year 5, you need to have thought
[01:01:55] about what your company looks like in a
[01:01:58] world where the thing you're racing toward
[01:01:59] is also being raced toward by every
[01:02:02] general system on earth.
[01:02:04] That's not a reason not to build.
[01:02:07] It's a reason to build with that future
[01:02:09] priced in.
[01:02:10] To ask on purpose what your company
[01:02:13] is uniquely positioned to do that a
[01:02:16] general AGI plus a thousand other
[01:02:19] specialists won't do for free.
[01:02:22] Most founders aren't doing that math.
[01:02:24] The ones who are will be the ones still
[01:02:27] standing when the math stops being
[01:02:29] hypothetical.
[01:02:31] through.
[01:02:32] Hassabis is the rare person in this field
[01:02:35] whose confidence is matched to what he
[01:02:37] actually knows.
[01:02:39] He says 50 -50 when he means 50
[01:02:42] -50.
[01:02:43] He won't endorse the thousand X
[01:02:45] productivity number when the interviewer
[01:02:48] hands it to him.
[01:02:49] He admits the memory problem isn't really
[01:02:52] solved.
[01:02:53] He proposes tests.
[01:02:55] You can actually fail for things his peers
[01:02:58] prefer to describe in metaphors.
[01:03:01] That precision is more valuable than any
[01:03:04] specific prediction he makes.
[01:03:07] The 2030 AGI timeline may turn out
[01:03:10] to be right or wrong.
[01:03:12] The habit of saying what you actually
[01:03:14] believe at the resolution you actually
[01:03:16] believe it is what makes the rest worth
[01:03:19] listening to.
[01:03:20] Use the specifics.
[01:03:22] Discount the slogans.
[01:03:24] That's how you listen to anyone, including
[01:03:26] him.
[01:03:26] Thanks for watching.
[01:03:28] Please like, subscribe, and let me know
[01:03:31] what you think in the comments.
