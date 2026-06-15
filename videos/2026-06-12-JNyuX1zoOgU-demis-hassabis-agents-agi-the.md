---
video_id: JNyuX1zoOgU
title: "Demis Hassabis: Agents, AGI & The Next Big Scientific Breakthrough"
channel: Y Combinator
url: "https://www.youtube.com/watch?v=JNyuX1zoOgU"
watched_date: 2026-06-12
watched_at: "2026-06-12T12:00:00Z"
watch_count: 1
duration_seconds: 2457
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 49
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 246
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

Demis Hassabis discussed DeepMind's progress toward AGI, identifying three remaining unsolved challenges: continual learning, long-term reasoning, and memory systems. He explained that current large-scale pre-training, RLHF, and chain-of-thought techniques are likely part of AGI's final architecture, but one or two significant innovations may still be needed. He emphasized that agents—systems capable of actively solving problems and making independent decisions—are essential to reaching AGI, building on decades of reinforcement learning research from AlphaGo and AlphaStar. Hassabis also covered model distillation breakthroughs (smaller models reaching 90-95% of frontier performance at 1/10 the cost), multimodal capabilities of Gemini, the early but promising state of agent technology, and progress toward simulating biological systems like virtual cells within the next 10 years.

For developers and researchers: prioritize experimenting with agent systems now, as the field is transitioning from toy demonstrations to genuinely valuable applications (expected within 6-12 months). Deploy smaller, distilled models locally for faster iteration speed and privacy benefits—engineers are already achieving 1000x productivity gains. Explore open-source Gemma models for local experimentation. Don't wait for perfect autonomous systems; focus on human-in-the-loop workflows where you operate at 10x efficiency first. Consider multimodal inputs (vision, speech) as competitive advantages for robotics and real-world assistants. Begin building with current tools now—breakthroughs in reasoning, continual learning, and agent autonomy will arrive while you're actively developing.

## Transcript

[00:00:00] continual learning, long-term reasoning,
[00:00:02] [music] uh some aspects of memory, these
[00:00:05] are still unsolved. I think all of these
[00:00:07] are going to be required for AGI.
[00:00:09] Depending on what your AGI timeline is,
[00:00:11] you know, mine's like 2030 or something
[00:00:13] like this, then [music] if you start off
[00:00:15] on a deep tech journey today, you have
[00:00:18] to just consider AGI appearing in the
[00:00:21] middle of that journey. It's not bad
[00:00:22] necessarily, but you have to take that
[00:00:24] into account. [music] You have to have
[00:00:26] an active system uh that can actively
[00:00:29] solve problems for you to get to AGI.
[00:00:31] So, agents are that path, and I think
[00:00:33] we're just getting going.
[00:00:39] Demis Hassabis has had one of the most
[00:00:43] unusual careers in tech. He was a chess
[00:00:46] prodigy as a kid, then designed his
[00:00:49] first hit video game, Theme Park, at 17.
[00:00:53] He then went back to school, got a PhD
[00:00:56] in cognitive neuroscience, published
[00:00:58] foundational work on how memory and
[00:00:59] imagination work in the brain, and then
[00:01:02] in 2010 co-founded DeepMind with one
[00:01:05] mission, solve intelligence.
[00:01:08] And I think they've done it.
[00:01:11] Since then,
[00:01:13] uh his lab has gone on to do things most
[00:01:15] people thought were decades away.
[00:01:17] AlphaGo beat a world champion at Go.
[00:01:19] AlphaFold cracked protein structure
[00:01:21] prediction, a 50-year grand challenge in
[00:01:24] biology, and they gave it away for free
[00:01:27] to every scientist on Earth.
[00:01:29] That work won him the Nobel Prize in
[00:01:31] chemistry last year. Today, Demis leads
[00:01:34] Google DeepMind, where he's building
[00:01:37] Gemini and pushing toward the same goal
[00:01:39] he set when he was a teenager,
[00:01:42] artificial general intelligence. Please
[00:01:44] welcome Demis Hassabis.
[00:01:53] So, you've been thinking about AGI
[00:01:54] longer than almost anyone. Uh when you
[00:01:56] look at the current paradigm,
[00:01:58] large-scale pre-training, RLHF, chain of
[00:02:00] thought, how much of the final
[00:02:02] architecture for AGI do you think we
[00:02:05] already have, and what's fundamentally
[00:02:07] missing right now? Well, first of all,
[00:02:09] thank thanks, Gary, for that great
[00:02:10] introduction, and it's great to be here.
[00:02:12] Thanks for for welcoming here. It's
[00:02:13] amazing space, actually. I'll have to
[00:02:15] come back here often. Very inspiring
[00:02:17] that you all get to work in in in this
[00:02:19] space. So, the question is I think the
[00:02:22] the components that you just mentioned,
[00:02:24] I'm pretty sure will be part of the
[00:02:26] final architecture for AGI. So, I think
[00:02:29] they've come such a long way now, uh and
[00:02:32] we've proven out so many things about
[00:02:33] what they can do.
[00:02:35] Uh I can't see a world in which we'll
[00:02:37] sort of realize in a couple of years
[00:02:39] this was a dead end. That doesn't make
[00:02:40] sense to me. But, there still might be
[00:02:42] one or two things missing on top of uh
[00:02:45] of of of what you've you know, what we
[00:02:47] already know works. So, um
[00:02:50] continual learning, long-term reasoning,
[00:02:52] uh some aspects of memory, these are
[00:02:55] still unsolved. Um and how to get the
[00:02:58] systems to be more consistent across the
[00:03:00] board. Um I think all of these are going
[00:03:02] to be required for AGI. Now, it might be
[00:03:05] that the existing techniques can just
[00:03:07] scale up to that with some innovation
[00:03:09] and some incremental innovation. Um but,
[00:03:12] it could be that there's still one or
[00:03:13] two big ideas left uh that need to be
[00:03:16] cracked. I don't think it's more than
[00:03:18] one or two if there are out there. And I
[00:03:20] think, you know, my betting is uh about
[00:03:23] 50/50 if that's the case. So, of course,
[00:03:25] at DeepMind at Google DeepMind we work
[00:03:27] on both those things. I guess that's all
[00:03:29] I mean, working with a bunch of
[00:03:31] identical systems. The wildest thing to
[00:03:32] me is to what degree It's the same
[00:03:35] weights ev- over and over. So, this idea
[00:03:37] of continual learning is so interesting
[00:03:39] because like you know, right now we're
[00:03:41] sort of cobbling it together with duct
[00:03:43] tape, you know? Yes. These dream cycles
[00:03:45] at night and things like that.
[00:03:47] >> Yeah. It's pretty cool, the dream
[00:03:48] cycles, and we we used to think about
[00:03:50] this with consolidation with episodic
[00:03:52] memory. It's actually that's what I
[00:03:53] studied for my PhD is how the
[00:03:54] hippocampus works and integrates, you
[00:03:57] know, new knowledge gracefully into the
[00:04:00] existing knowledge base. So, the brain
[00:04:02] does that amazingly well. It it it does
[00:04:04] it through you know, during sleep uh
[00:04:06] especially things like REM sleep,
[00:04:08] replaying back episodes that that are
[00:04:10] important so that you can learn from it.
[00:04:12] In fact, our very first Atari program
[00:04:15] DQN, one of the ways it was able to
[00:04:17] master Atari games was by doing
[00:04:19] experience replay. So, we sort of
[00:04:21] borrowed that from from neuroscience and
[00:04:23] replayed successful trajectories
[00:04:26] uh many times, you know, that's
[00:04:28] way back in 2013 now in the in the dark
[00:04:30] ages of AI. It was uh a really important
[00:04:33] thing. And and I agree with you, we're
[00:04:34] kind of using duct tape right now. So,
[00:04:36] like shove it all in the context window.
[00:04:38] Um this but this seems a bit
[00:04:40] unsatisfying, right? And actually, even
[00:04:42] though uh we're working on machines, not
[00:04:45] biological brains, and so you
[00:04:47] potentially you could have, you know,
[00:04:49] millions or tens of millions size
[00:04:51] context window or memory, and it can be
[00:04:53] perfect, there's still a cost to looking
[00:04:56] it up and finding the right thing uh
[00:04:59] that that's actually relevant for the
[00:05:01] specific uh decision you've got to make
[00:05:03] right now. And that's non-trivial that
[00:05:05] cost, even if you can potentially store
[00:05:07] it all. I think there's actually a lot
[00:05:09] of room for innovation in in areas like
[00:05:11] memory. Yeah. I mean, the one thing is
[00:05:13] like it feels like a million
[00:05:14] token context one is actually bigger
[00:05:17] than I mean, it's plenty big, honestly.
[00:05:18] You can do so.
[00:05:20] It's plenty big for for for most things
[00:05:22] that it should be used for. I mean, if
[00:05:24] you think about the context window is
[00:05:26] sort of equivalent to working memory,
[00:05:28] you know, humans have we have like a few
[00:05:30] digits, you know, it's like a a dozen
[00:05:32] digits maybe, you know, average of
[00:05:34] seven. We got million or, you know, 10
[00:05:36] million context windows, but the problem
[00:05:38] is is that we're trying to store
[00:05:40] everything in that. You know, things
[00:05:42] that aren't in not important, things
[00:05:43] that are wrong. It's pretty brute force
[00:05:45] currently, and that doesn't seem uh
[00:05:47] right. And then the problem is if you're
[00:05:49] an agent trying to try and process live
[00:05:51] video, and you're just going to naively
[00:05:53] record all the tokens, then actually a
[00:05:56] million tokens isn't that much. It's
[00:05:58] only like 20 minutes. So, actually you
[00:06:01] need more if you want something that's
[00:06:02] going to understand your, you know, your
[00:06:05] what's going on in your life over maybe
[00:06:06] a month or two. DeepMind has
[00:06:09] historically leaned into reinforcement
[00:06:11] learning and search.
[00:06:13] AlphaGo, AlphaZero, and MuZero. How much
[00:06:16] of that philosophy is actually embedded
[00:06:17] in how you're building Gemini today? Is
[00:06:21] RL still underrated? Yeah, I think
[00:06:24] potentially it is. It sort of goes in in
[00:06:26] abs and way waves. You know, we've
[00:06:28] worked on agents since the beginning of
[00:06:30] DeepMind. In fact, we also That's what
[00:06:32] we said we were working on. And so, all
[00:06:33] of the Atari work and AlphaGo, most
[00:06:36] specifically, they're agent systems. And
[00:06:38] what we meant by that is systems that
[00:06:40] are able to, you know, accomplish goals
[00:06:42] on their own.
[00:06:43] And make active decisions and and make
[00:06:46] plans. And so, of course, we were doing
[00:06:48] it in the domain of games to to to make
[00:06:51] it tractable. And then doing
[00:06:53] increasingly complex games, things like
[00:06:55] StarCraft after AlphaGo, AlphaStar. So,
[00:06:59] we basically did all the games that are
[00:07:01] out there.
[00:07:02] And then of course, the question is can
[00:07:04] you generalize those models to be world
[00:07:06] models or models of language, not just
[00:07:08] models of simple games or even complex
[00:07:11] games. And that's what the last few
[00:07:13] years has been about. But really, you
[00:07:15] can think of a lot of the things we're
[00:07:17] doing today, all the leading models with
[00:07:19] thinking modes and chain of thought
[00:07:21] reasoning as aspects of what was sort of
[00:07:23] pioneered with AlphaGo coming back now.
[00:07:26] And I actually think there's a lot of
[00:07:28] work we did back then that is relevant
[00:07:31] today. And we're sort of re-looking at
[00:07:33] some of those old ideas
[00:07:35] at scale today in a more general way.
[00:07:38] Including things like Monte Carlo tree
[00:07:39] search and other other ways of doing
[00:07:41] augmenting the RL
[00:07:43] on top of the the reinforcement learning
[00:07:45] we're ready to do today. And I think a
[00:07:47] lot of those ideas both from AlphaGo and
[00:07:49] AlphaZero are really really relevant to
[00:07:52] to where we are with today's foundation
[00:07:54] models. And I think a lot of that is
[00:07:56] what we're going to see of the advances
[00:07:58] the next few years. One question I would
[00:08:00] have like obviously today you need
[00:08:03] bigger and bigger models to be smarter
[00:08:05] and smarter, but then we're also seeing
[00:08:07] distillation working and then smaller
[00:08:09] models can be like quite a bit faster. I
[00:08:11] think you know, you guys have incredible
[00:08:13] flash models that are like nine like
[00:08:15] you're finding that they're 95% as good
[00:08:18] as the frontier and at like 1/10 the
[00:08:21] price. Is that right? I think that's one
[00:08:23] of our core strengths is I mean you have
[00:08:25] to build the biggest models to to to to
[00:08:27] have the frontier capabilities, but I
[00:08:30] think one of our biggest strengths has
[00:08:31] been
[00:08:32] distilling and packing that power into
[00:08:34] smaller and smaller models very quickly.
[00:08:37] Obviously we we you know, we invented
[00:08:39] the kind of distillation process and and
[00:08:41] people like Jeff and Oriol and and
[00:08:43] others and we're still world experts in
[00:08:46] that. And we also have a huge need to
[00:08:50] do it because we've got to serve the
[00:08:52] biggest probably AI surfaces there are.
[00:08:56] Obviously there's search with AI
[00:08:57] overviews and AI mode and there's Gemini
[00:08:59] app and now increasingly every single
[00:09:01] product at Google has you know, maps and
[00:09:04] YouTube and so on has some aspect of
[00:09:07] Gemini or Gemini related technology in
[00:09:09] it. And so that's billions of users a
[00:09:12] dozen more than a dozen billion user
[00:09:14] products
[00:09:15] and they have to be served extremely
[00:09:16] fast, extremely efficiently and cheaply
[00:09:18] and with low latency. So that that gives
[00:09:21] us a really important incentive to to
[00:09:24] make these flash and even smaller models
[00:09:26] flashlight models extremely efficient.
[00:09:29] And hopefully that ends up then being
[00:09:30] really useful for many of the workloads
[00:09:32] that all of you use for. I'm curious
[00:09:35] about how much smarter these smaller
[00:09:38] models can actually be. Like, are there
[00:09:39] limits to the distillation process?
[00:09:41] Like, could a 50B or 400B model be as
[00:09:45] smart as like a mythos for today? Yeah,
[00:09:48] I didn't I didn't see any I don't think
[00:09:49] we've got to any kind of or at least
[00:09:51] none of us know yet if we've got to any
[00:09:53] kind of informational limit. I mean,
[00:09:55] maybe at some point that will be the
[00:09:56] case where there's just an information
[00:09:58] density that can't we can't get beyond.
[00:10:00] But, I think for now there's the
[00:10:03] assumption we make is that you know, a
[00:10:05] year later one of our
[00:10:07] leading, you know, pro models or
[00:10:09] frontier models goes out, half a year
[00:10:12] later, a year later you'll have them in
[00:10:14] the the really tiny almost edge models.
[00:10:17] And you'll also see some of that
[00:10:18] goodness in our Gemma models, which
[00:10:20] hopefully you're all enjoying our Gemma
[00:10:21] four models, which I think are really
[00:10:23] amazing power for their sizes. So,
[00:10:26] again, that uses a lot of this these
[00:10:29] distillation techniques and and the idea
[00:10:31] of how to make things really efficient
[00:10:32] in these very small models. So, I don't
[00:10:34] really see any limit yet in terms of
[00:10:36] like some kind of theoretical limit. I
[00:10:37] think we're still pretty far off of
[00:10:39] that. That's a mean I mean that is
[00:10:40] really good.
[00:10:41] >> Yes.
[00:10:42] Uh you know, one of the weirder things
[00:10:43] that we're seeing right now is like
[00:10:45] engineers can do like 500 to 1,000 times
[00:10:48] the amount of work that they were doing
[00:10:50] like 6 months ago, I guess. I mean, the
[00:10:53] people in this room there are people who
[00:10:54] are doing about like a thousand X the
[00:10:56] work that like I Steve Yegge talks about
[00:10:59] this. It's like a thousand X the work
[00:11:01] that a Google engineer from the 2000s
[00:11:03] was doing. I think it's very exciting. I
[00:11:05] mean, I think models have many uses. One
[00:11:07] is obviously cost, but the speed can
[00:11:10] allow, you know, if you think about
[00:11:11] coding even or other things, you can
[00:11:13] iterate a lot faster. Also, especially
[00:11:15] if there's if you're collaborating with
[00:11:17] the system. I think there's a there's a
[00:11:20] a lot of need for having fast systems
[00:11:23] that maybe are not quite frontier. Like
[00:11:26] you said, like 95% 90%, but that's
[00:11:28] plenty good enough and actually gain
[00:11:29] back more than the 10% on the the
[00:11:32] iteration speed. So, and then the other
[00:11:34] big thing I think is running these
[00:11:36] things on the edge. Again, for
[00:11:37] efficiency reasons, but also for privacy
[00:11:40] and security reasons, too. Um if you
[00:11:42] think about different devices that you
[00:11:44] might run these systems on that that,
[00:11:47] you know, process very personal
[00:11:48] information, can also think about
[00:11:50] robotics, as well. Um you know, robots
[00:11:52] in your house. I think you're going to
[00:11:54] want very efficient, uh very powerful,
[00:11:57] uh local models, which maybe are
[00:11:59] orchestrated
[00:12:00] you know, with some bigger models,
[00:12:02] frontier models that are in the in the
[00:12:04] cloud, but you only delegate to that in
[00:12:06] certain circumstances. And perhaps you,
[00:12:09] you know, you process all of the
[00:12:11] audio-visual feed, let's say, locally,
[00:12:13] and that stays local. I could imagine uh
[00:12:16] that would be a very good sort of um end
[00:12:18] state. Y Combinator Startup School is
[00:12:20] back. We're hand-selecting the most
[00:12:22] promising builders in the world and
[00:12:24] flying them out to San Francisco on July
[00:12:26] 25th and 26th to discuss the cutting
[00:12:29] edge of tech. Apply now for a spot.
[00:12:31] Okay, back to the video. Going back to
[00:12:34] context and memory, models currently
[00:12:36] stateless, but, you know, continue like
[00:12:38] what would the developer experience even
[00:12:40] be like for someone who's using a
[00:12:42] continual learning model? Like, you
[00:12:44] know, any idea like how you'd steer it?
[00:12:46] I think it's really interesting. I think
[00:12:48] that's one of the not having continual
[00:12:50] learning currently is one of the things
[00:12:51] holding back agents from doing full
[00:12:55] uh tasks, you know? I think they're
[00:12:56] really useful for aspects of tasks right
[00:12:59] now, and you can patch them together and
[00:13:01] do some really cool things, but they
[00:13:03] don't adapt well with the context that
[00:13:06] you're in. And I think that's the
[00:13:08] missing piece for them being really kind
[00:13:10] of fire and forget, and they'll figure
[00:13:12] it out themselves. You know, I think
[00:13:14] they need to be able to learn um about
[00:13:16] the specific context um that you're
[00:13:19] going to put them in. So, um I think we
[00:13:22] have to crack that to get full general
[00:13:25] intelligence. Where are we on reasoning?
[00:13:27] So, models can do really impressive
[00:13:28] chain of thought now, but they still
[00:13:30] fail on things a smart undergrad
[00:13:32] wouldn't. What specifically needs to
[00:13:34] change and what progress do you expect
[00:13:36] in reasoning? There's a lot of
[00:13:39] innovation left in in think the thinking
[00:13:41] paradigms, I would say. Again, I think
[00:13:43] we're fairly we're doing fairly
[00:13:44] simplistic things, fairly brute force.
[00:13:48] One could imagine
[00:13:50] I think there's a lot of scope for
[00:13:51] example in monitoring the chain of
[00:13:52] thought, maybe interjecting midway
[00:13:55] through a thought process. I often get
[00:13:57] the impression with our systems and and
[00:13:59] our competitor systems that they're
[00:14:01] almost overthinking. They're almost
[00:14:03] getting into sort of loops of things.
[00:14:05] Like one thing I sometimes like to do is
[00:14:08] is play chess against Gemini. And you
[00:14:10] know, it's the all the leading
[00:14:12] foundation models are pretty poor at
[00:14:13] games, which is quite interesting. It's
[00:14:15] very
[00:14:17] cool to kind of look at the thinking
[00:14:18] traces cuz obviously these are can be a
[00:14:20] well-understood. You know, I can tell
[00:14:22] quite quickly if it's going off on a
[00:14:24] tangent and it's very sort of provable
[00:14:26] what the what the the thinking is doing,
[00:14:29] whether it's useful or not. And so, what
[00:14:32] we see is that, you know, sometimes it
[00:14:34] will it will it will consider a move. It
[00:14:36] will realize it's a blunder, but it
[00:14:38] can't find anything better, so it kind
[00:14:39] of goes back to that move and does it
[00:14:41] anyway. So, it you know, you just
[00:14:43] shouldn't be seeing that
[00:14:45] happening in a in a very precise
[00:14:47] reasoning system. So, there's just sort
[00:14:49] of huge gaps, I think, still, but it may
[00:14:52] only be one or two tweaks that are
[00:14:53] required to fix those kind of gaps just
[00:14:55] to be clear, but I think that's pretty
[00:14:57] pretty obvious they're all there. And
[00:14:59] that's why you get this kind of jagged
[00:15:01] intelligence. You know, on the one hand,
[00:15:03] it can solve gold medal problems in IMO,
[00:15:07] which is super hard, but on the other
[00:15:08] hand, as we've all seen, it can still
[00:15:10] make basic elementary maths errors if
[00:15:13] you pose the question in a certain way,
[00:15:16] right? So, or elementary reasoning
[00:15:18] errors. So, there's just something to me
[00:15:19] about the almost an introspection about
[00:15:22] its own thought process that I feel like
[00:15:24] there's there's something maybe missing
[00:15:26] there. Agents are really big. Some would
[00:15:28] say they're hyped. I personally think
[00:15:29] they're just getting started. It's
[00:15:31] [laughter] totally insane. What does
[00:15:33] DeepMind's internal research tell you
[00:15:34] about where agent capabilities actually
[00:15:36] are right now versus, you know, sort of
[00:15:38] the hype out there? I think we are I
[00:15:40] agree with you. I think we're just at
[00:15:42] the beginning. You have to have an
[00:15:43] active system that can actively solve
[00:15:46] problems for you to get to AGI. That was
[00:15:48] always clear to us. So, agents are that
[00:15:51] path and I think we're just getting
[00:15:52] going. I think all of us are getting
[00:15:54] used to how do we best work and you're
[00:15:56] leading the way in a lot of this in your
[00:15:58] own personal experiments. I'm sure many
[00:15:59] of you are doing that. I think how do
[00:16:01] you incorporate it into your
[00:16:03] workflow in a way that isn't just sort
[00:16:06] of a nice to have, but actually starting
[00:16:09] to do fundamental things. My I think My
[00:16:10] impression is at the moment we're all
[00:16:11] experimenting we're experimenting a lot
[00:16:13] of things, but we're only in the maybe
[00:16:15] the last couple of months starting to
[00:16:16] find the really valuable places. And the
[00:16:19] technology probably only getting good
[00:16:21] enough for that to be the case, right?
[00:16:23] Where that it's not a kind of toy nice
[00:16:25] demonstration, but actually really
[00:16:27] adding value to your to your to your
[00:16:29] time and efficiency.
[00:16:31] I had often wondered I see a lot of
[00:16:33] people working on
[00:16:34] like setting off, you know, dozens of
[00:16:37] agents for like 40 hours, but I'm not
[00:16:39] sure I've seen the output that yet of
[00:16:42] that quite justify that level of input
[00:16:45] going in, but I think it will come. So,
[00:16:47] I still think we're in the
[00:16:48] experimentation phase. We haven't seen a
[00:16:50] triple-A game that tops the App Store
[00:16:53] charts that was sort of vibe coded yet,
[00:16:56] right? I've seen and I've programmed and
[00:16:58] I'm sure many we've all done little nice
[00:16:59] demonstrations and it's like amazing. I
[00:17:01] can do a prototype of theme park in half
[00:17:04] an hour now which took me six months
[00:17:06] back when I was 17. It's kind of
[00:17:08] mind-blowing and I and I wish I I got
[00:17:10] this feeling if I spent the whole summer
[00:17:12] working on it, you could make something
[00:17:14] really incredible, but it still needs
[00:17:16] craft and, you know, human sort of soul
[00:17:19] into it and taste. I think that's that's
[00:17:21] something that can that's you have to
[00:17:23] make sure you still bring that to to
[00:17:26] whatever it is you're building. And I
[00:17:27] think it still shows like it's not quite
[00:17:29] there yet because why haven't we seen
[00:17:32] a kid making a hit game that's that
[00:17:34] sells 10 million copies, right? That
[00:17:36] should be possible given the effort
[00:17:38] that's gone in. So something's still
[00:17:40] somehow missing. Maybe it's to do with
[00:17:42] the process, or maybe it's to do with
[00:17:43] the tools. I'm not quite sure. You will
[00:17:45] probably know better than me cuz I'm
[00:17:46] sure you're all experimenting on that.
[00:17:48] But I haven't seen the result yet which
[00:17:50] I would expect once this is really
[00:17:53] delivering that full value. Which I
[00:17:55] think will come in the next 6 to 12
[00:17:57] months. Some of it is like how much of
[00:17:58] it will be autonomous versus I mean, I
[00:18:00] don't think we'd see autonomous first.
[00:18:02] We would actually probably see people in
[00:18:04] this room operating at 1000X, and then
[00:18:07] That's what you should see first, and
[00:18:09] then many of you, you know, they'll be
[00:18:11] like games companies or, you know, other
[00:18:14] types of companies that have built some
[00:18:16] kind of best-selling app, best-selling
[00:18:18] game using these tools. That's what you
[00:18:21] should see first, and then more of that
[00:18:23] will get automated. I mean, some of it
[00:18:25] is like there's a human in there, and
[00:18:27] then the human doesn't want to say that
[00:18:29] the the the agents did it yet. I think
[00:18:32] part of it might be though that um this
[00:18:35] if we want to discuss like creativity,
[00:18:37] what I often say about that is like if
[00:18:39] we look at the things we've done like
[00:18:41] AlphaGo. So obviously very famously
[00:18:44] you'll all know about the move 37 in
[00:18:45] game two, and for me I was waiting for a
[00:18:47] moment like that to start the science
[00:18:49] projects like AlphaFold. We started
[00:18:51] AlphaFold like the day we got back from
[00:18:53] Seoul, which is 10 years ago now. I'm
[00:18:55] going to Korea after this to celebrate
[00:18:58] the 10-year anniversary of AlphaGo. But
[00:19:01] it's not enough to come up with move 37.
[00:19:03] Like that's pretty cool, very useful,
[00:19:06] um but can it invent go?
[00:19:08] That's what I want a system that can
[00:19:10] invent go if you give it a high-level
[00:19:12] description, you know, like a game you
[00:19:14] can learn the rules of in 5 minutes, but
[00:19:17] it takes a many lifetimes to master.
[00:19:19] It's beautiful aesthetically,
[00:19:22] um but you can play it in a few hours in
[00:19:24] an afternoon. So, you know, maybe you
[00:19:26] could imagine that would be the
[00:19:27] high-level description I would give and
[00:19:29] then I'd want the the return the thing I
[00:19:31] get back is go.
[00:19:33] Right? And um clearly today's systems, I
[00:19:36] think can't do that. So, the question is
[00:19:39] why? Um and I think there's something
[00:19:41] still missing there. Well, someone in
[00:19:43] this room might might make it.
[00:19:44] >> Then the answer would be there's nothing
[00:19:45] missing. It just was the way we were
[00:19:47] using the systems. And that might
[00:19:49] actually be the answer. It might be that
[00:19:51] today's systems are capable of that with
[00:19:53] a brilliant enough creative person using
[00:19:56] it and providing that impetus that the
[00:19:59] soul of the project and being able to
[00:20:01] probably being
[00:20:03] au fait enough with the tools to like
[00:20:06] almost be at one with the tools. I could
[00:20:07] imagine that would be happening if you
[00:20:09] experimented with the tools all day and
[00:20:11] all night like probably many of you are
[00:20:12] doing that and you combine that with
[00:20:14] proper deep creativity.
[00:20:17] Um something, you know, more incredible
[00:20:18] could be done. Switching gears to open
[00:20:20] source, I mean or open open and open
[00:20:22] weights. I mean, the recent release of
[00:20:24] Gemma, you're making highly capable open
[00:20:28] and accessible ones that can actually
[00:20:29] run locally. What do you think that
[00:20:31] means for you will AI be something that
[00:20:35] is in the hands of the users instead of
[00:20:36] primarily in the cloud? And does that
[00:20:39] change who gets to, you know, build with
[00:20:41] these models? We're huge proponents of
[00:20:44] in general of open source and open
[00:20:46] science. And you mentioned AlphaFold at
[00:20:48] the beginning, you know, we put that all
[00:20:49] out there for free. And all of our
[00:20:51] science work even still today we publish
[00:20:54] in, you know, the big journals. We
[00:20:56] wanted to create uh world-leading models
[00:20:58] for their their sizes. Right? And so,
[00:21:00] that's what we hopefully we've done with
[00:21:02] Gemma. And we're, you know, very
[00:21:03] committed to that path. And hopefully
[00:21:05] you will experiment and build and and
[00:21:07] enjoy and using Gemini. I think it's
[00:21:08] been like 40 million downloads now and
[00:21:11] uh it's just in you know 2 and 1/2
[00:21:13] weeks. So we're really excited about
[00:21:14] that. And I also think it's important
[00:21:16] for there to be Western stacks on open
[00:21:19] source. You know, obviously a lot of the
[00:21:20] Chinese models are excellent and and
[00:21:23] they're currently well well leading in
[00:21:24] open source and we think Gemini is very
[00:21:26] competitive for its sizes
[00:21:28] uh in in all those respects. And for us,
[00:21:31] I mean there is a question of resources,
[00:21:33] talent, and compute. Like nobody has
[00:21:35] enough spare compute to just make two,
[00:21:38] you know, uh frontier models at maximum
[00:21:41] size, right? With different attributes.
[00:21:43] So that's pretty difficult. But also for
[00:21:45] what for now what we've we've decided is
[00:21:47] that our edge models, the things we want
[00:21:49] to use for Android and glasses and
[00:21:52] robotics, um it's best that they're open
[00:21:54] models because they're vulnerable anyway
[00:21:57] on the once you put them out on the
[00:21:58] surfaces. So they might as well be
[00:22:00] actually fully open, right? So we've
[00:22:03] sort of made a decision to kind of unify
[00:22:05] that
[00:22:06] uh at the at the kind of we call it nano
[00:22:09] size level. So that actually works for
[00:22:11] us uh strategically as well. Um and you
[00:22:15] know, we hope as many people as possible
[00:22:16] build on it. And of course, we'll be
[00:22:18] building on that, too. Earlier uh before
[00:22:20] we came on, I got to show you a demo of
[00:22:22] uh my version of Samantha from Her,
[00:22:24] which is Yes. uh harrowing for me to try
[00:22:26] to demo something to you. Yeah, very
[00:22:28] good. Um and it worked, which is
[00:22:30] amazing. Gemini was built multimodal and
[00:22:32] I spent a lot of time with a bunch of
[00:22:34] the models and I mean the depth of the
[00:22:36] context and the tool use with speech
[00:22:40] directly to model, like there's nothing
[00:22:42] like bar none, like the best one
[00:22:44] actually.
[00:22:44] >> Yeah. Yeah, I think I think that's the
[00:22:46] sort of still a slightly
[00:22:47] underappreciated aspect of of of the
[00:22:49] Gemini series is we we started it being
[00:22:52] multimodal from the start. That made it
[00:22:54] a little bit more difficult actually to
[00:22:56] begin with cuz then just focusing on
[00:22:57] text, for example. But I we believe
[00:23:00] we're going to gain from that in the
[00:23:02] long run. And I think we're seeing that
[00:23:03] now for
[00:23:05] things like world model building, so
[00:23:08] stuff like Genie that we build on top of
[00:23:10] Gemini. I think it's going to be really
[00:23:12] important for things like robotics. So
[00:23:14] this is why Gemini robotics which many
[00:23:15] of you probably played around with, I
[00:23:17] think it's going to be built on
[00:23:18] multimodal foundation models, the
[00:23:20] robotics models. And we think we have a
[00:23:23] sort of competitive advantage with with
[00:23:25] Gemini being so strong at multimodal.
[00:23:27] We're using it increasingly in things
[00:23:29] like Waymo. Um but also if you imagine
[00:23:32] devices and assistants that digital
[00:23:35] assistants that come with you into the
[00:23:36] real world, you know, maybe on your
[00:23:38] phone or glasses or some other device,
[00:23:41] it needs to understand the physical
[00:23:43] world around you and intuitive physics
[00:23:46] and and the and the physical context
[00:23:48] you're in. And that's what our systems
[00:23:50] are extremely good at and I think you
[00:23:52] found that's why you've enjoyed using it
[00:23:53] in your setup. We're planning to
[00:23:55] continue on that and I think we're
[00:23:57] far and away the strongest models on on
[00:23:59] those types of
[00:24:01] problems. So the cost of inference is
[00:24:03] dropping fast. What becomes possible
[00:24:05] when inference is essentially free and
[00:24:07] how does that change what your team is
[00:24:09] actually optimizing for? Yeah, I'm not
[00:24:11] sure inference
[00:24:13] will ever be essentially free. I mean
[00:24:15] there's sort of Jevons' paradox and
[00:24:17] other things about like I think we'll
[00:24:18] just end up using all of us will end up
[00:24:21] using whatever we can get our hands on
[00:24:24] and you could imagine
[00:24:26] millions of agents, swarms of agents
[00:24:28] working together on things. So that's
[00:24:30] one way to use the inference or you
[00:24:32] could imagine
[00:24:33] single agents or smaller groups of
[00:24:35] agents thinking for in multiple
[00:24:38] directions and then ensembling that. So
[00:24:40] we're experimenting with all these
[00:24:41] things, probably many of you are. All of
[00:24:43] that will use up any inference I think
[00:24:46] that's available. I mean one day maybe
[00:24:48] it can be almost cost zero, certainly
[00:24:51] the energy if we solve fusion or you
[00:24:53] know, superconductors or you know,
[00:24:54] optimal batteries or some set of those
[00:24:56] things which I think we will do with
[00:24:58] material science, And energy costs will
[00:25:00] be essentially zero, but there'll still
[00:25:02] be the physical creation of the chips
[00:25:04] and other things. There'll There'll be
[00:25:06] some bottleneck um at least for the next
[00:25:09] few decades, I think. And so if that's
[00:25:11] the case, there'll still be rationing on
[00:25:14] the inference side. You still have to
[00:25:16] use it, I think, efficiently. Yeah.
[00:25:18] Well, luckily the smaller models are
[00:25:19] getting smarter and smarter, which is
[00:25:20] fantastic. Uh we got a lot of bio and
[00:25:23] biotech founders in the audience. I can
[00:25:26] see a few. AlphaFold 3 took us beyond
[00:25:28] proteins to a broad spectrum of
[00:25:29] biomolecules. Uh how close are we to
[00:25:32] modeling full cellular systems, or is
[00:25:34] that still a fundamentally harder
[00:25:36] problem in a class of its own? Well, I
[00:25:39] Isomorphic Labs, which we spun out from
[00:25:41] from from from DeepMind after we did
[00:25:44] AlphaFold 2,
[00:25:45] um it's it's which is going amazingly
[00:25:47] well. It's it's it's trying to build out
[00:25:49] uh not just AlphaFold. It's just one
[00:25:51] piece of the drug discovery process, uh
[00:25:54] as many you know, but we're trying to do
[00:25:56] the the adjacent biochemistry and
[00:25:58] chemistry to design the right compounds
[00:26:00] with the right properties and so on.
[00:26:02] We'll have some big announcements for
[00:26:03] you know, very soon to talk about on the
[00:26:05] on that front. I think that's going
[00:26:07] really well. Eventually, you want a
[00:26:09] whole virtual cell. So I've talked about
[00:26:11] this in many of my science talks about a
[00:26:13] full working simulation of a cell that
[00:26:16] you can perturb, and then the you know,
[00:26:18] the the outputs of that would be close
[00:26:21] enough to experimental that it's useful,
[00:26:23] right? You could skip out a lot of the
[00:26:25] the search steps and generate lots of
[00:26:27] synthetic data to train other models
[00:26:30] that then would predict things about,
[00:26:31] you know, real cells. And um
[00:26:34] I think we're about 10 years away
[00:26:36] probably from something like a virtual
[00:26:37] cell, like a full virtual cell. You
[00:26:39] know, we're starting out This is we're
[00:26:41] working on the DeepMind side, science
[00:26:42] side, on a you know, virtual nucleus,
[00:26:45] cell nucleus first cuz relatively
[00:26:47] self-contained. The trick with all of
[00:26:49] these things is can you pick uh a slice
[00:26:51] of the complexity, you know, eventually
[00:26:53] you want to want to model a human body,
[00:26:55] but can you model it down to the right
[00:26:57] level of detail and what slice can you
[00:27:01] take out of it that will be
[00:27:02] self-contained enough? You can kind of
[00:27:04] model and approximate the inputs and
[00:27:07] outputs into that self-contained system
[00:27:09] and then just focus on the
[00:27:10] self-contained system. So, a nucleus is
[00:27:12] quite interesting from that perspective.
[00:27:15] Um, then the other issue is just there's
[00:27:16] not enough data yet. So, you need data
[00:27:20] and I talked to various, you know, top
[00:27:22] scientists about who work on electron
[00:27:24] microscopes and other imaging things. If
[00:27:27] we could image a live cell without
[00:27:29] killing the cell, that would be
[00:27:32] game-changing obviously cuz then you
[00:27:33] could convert it into a vision problem
[00:27:35] which we would know how to solve. Right?
[00:27:37] And but at the moment, there are at
[00:27:39] least I'm not aware of any techniques
[00:27:41] that can give you a kind of, you know,
[00:27:42] nanometer resolution
[00:27:45] but without destroying but in, you know,
[00:27:48] in a live dynamic cell. So, you can see
[00:27:50] all the interactions. Right? You can
[00:27:51] take static images at that resolution
[00:27:53] obviously.
[00:27:55] Really detailed now and that's quite
[00:27:56] exciting but it's not enough to turn it
[00:27:59] just into just into a complex vision
[00:28:02] problem.
[00:28:03] So, that's one way it could be solved.
[00:28:05] So, it could be a hardware driven data
[00:28:06] driven solution or it could be that we
[00:28:09] build better
[00:28:11] learn simulators of these dynamical
[00:28:14] systems. So, that's that's the more
[00:28:15] modeling way of solving it. You've been
[00:28:18] looking at all kinds of science and not
[00:28:19] just bio. There's material science, drug
[00:28:22] discovery, climate modeling,
[00:28:23] mathematics. If you had a rank which
[00:28:26] scientific domain will transform the
[00:28:27] most dramatically the next 5 years,
[00:28:29] what's in your list?
[00:28:30] >> all sounds exciting and that's why, I
[00:28:32] mean, that that for me has been my main
[00:28:34] passion and always the reason why I've
[00:28:36] worked on AI for my whole career for 30
[00:28:38] plus years now is to use AI as the
[00:28:41] ultimate tool. I always thought AI would
[00:28:43] be the ultimate tool for science and to
[00:28:45] invite such advanced scientific
[00:28:48] scientific discovery, and things like
[00:28:49] medicine, and just our understanding of
[00:28:51] the universe around us. So, actually,
[00:28:53] when you mentioned our original way we
[00:28:55] used to articulate our mission
[00:28:56] statement, which is still the way we
[00:28:58] think about it, is there was two steps
[00:28:59] to it. One was Step one was solve
[00:29:01] intelligence, i.e. build AGI, and then
[00:29:03] step two was use it to solve everything
[00:29:05] else. We had to change that a bit over
[00:29:07] time cuz people were like, "Do you
[00:29:08] really mean solve everything else?" And
[00:29:10] we did mean that, and I think people are
[00:29:12] sort of understanding what that means
[00:29:14] today. But, specifically, I was meaning
[00:29:16] solve other what I call root node
[00:29:18] problems in science. So, areas of
[00:29:20] science that would unlock whole new
[00:29:22] branches or avenues of discovery. And
[00:29:24] AlphaFold is the prototypical example of
[00:29:26] what we want to do. So, over 3 million
[00:29:28] researchers around the world, pretty
[00:29:30] much every biology researcher in the
[00:29:31] world uses AlphaFold now. And I was told
[00:29:34] by some of my, you know, former
[00:29:36] executive friends that, you know, almost
[00:29:39] every drug discovered from now on will
[00:29:42] have used AlphaFold at some point in its
[00:29:44] in the drug discovery process. So,
[00:29:46] that's something we're very proud of,
[00:29:48] and it's the sort of impact that we hope
[00:29:50] to have with with AI. But, I do think
[00:29:52] it's just the beginning. I I don't
[00:29:54] really see any area of science or
[00:29:56] engineering that this won't be able to
[00:29:57] help be helpful with. And the ones you
[00:29:59] mentioned, I think we're almost like an
[00:30:02] AlphaFold one moment. So, it's we've got
[00:30:04] very promising results, but it's not
[00:30:05] quite solved the the grand challenge yet
[00:30:08] in that domain. But, I think we're going
[00:30:10] to have a lot to talk about in the next
[00:30:12] couple of years on all those areas you
[00:30:13] mentioned, materials, which I I think is
[00:30:15] very exciting, all the way to
[00:30:17] mathematics. In in science, I mean, it
[00:30:19] feels Promethean. It's like, here is
[00:30:21] this capability, and you I think so. I
[00:30:24] mean, of course, along with that,
[00:30:25] including including what the the the
[00:30:27] parable of Prometheus, we have to also
[00:30:29] be careful with how we use that and what
[00:30:32] we use it for, and also the misuse that
[00:30:35] can happen with those same tools. A lot
[00:30:37] of people in this room are trying to
[00:30:37] build companies applying AI to science.
[00:30:40] For them, what's the difference between
[00:30:41] a startup that actually advances the
[00:30:43] frontier in your view versus one that's
[00:30:45] just wrapping an API around a foundation
[00:30:47] model and calling it AI for science?
[00:30:49] Well, look, I think there's one of the
[00:30:51] things I would recommend. I'm trying to
[00:30:52] think about and I think you mentioned
[00:30:53] this to me before. What would I do today
[00:30:55] myself if I was sitting in your place in
[00:30:58] Y Combinator, you know, looking at
[00:30:59] things. One thing you have to do is
[00:31:01] obviously intercept where the AI tech is
[00:31:04] going. So, that's one hard part of it.
[00:31:06] But, I do think there's huge scope for
[00:31:09] combining where AI is going with some
[00:31:12] other deep technology area. I just think
[00:31:14] that that sweet spot is is whether it's
[00:31:16] materials or medicine or other really
[00:31:18] hard areas of science. I think that
[00:31:21] those kinds of interdisciplinary teams,
[00:31:24] especially if it involves the world of
[00:31:25] atoms as well,
[00:31:27] there's not going to be a shortcut to
[00:31:28] that, at least in the foreseeable
[00:31:30] future. Those areas that are pretty safe
[00:31:33] from just getting swamped by whatever
[00:31:35] the next update is to the foundation
[00:31:37] models. So, I think if you're looking
[00:31:39] for things like that, that's one of the
[00:31:41] more defensible areas I would say. And
[00:31:43] I've always loved deep tech, so I'm kind
[00:31:45] of biased towards deep tech things. I
[00:31:48] think nothing
[00:31:49] that's really long-lasting and
[00:31:51] worthwhile is easy. And so, I'm always
[00:31:54] been drawn to to deep technologies.
[00:31:57] Obviously, AI was like that back in 2010
[00:31:59] when we started out, right? It was It
[00:32:01] was thought to just we know we know it
[00:32:03] doesn't work kind of thing is what I was
[00:32:05] told by investors and even in academia
[00:32:07] it was considered to be a very niche
[00:32:10] subject that we sort of tried in the
[00:32:12] '90s and we know doesn't work. But, if
[00:32:14] you, you know, if you have belief and
[00:32:16] conviction in your idea why it's
[00:32:18] different this time or what special
[00:32:19] combination from your background that
[00:32:22] you had, ideally you're expert in both
[00:32:24] those areas, both the machine learning
[00:32:26] and the other area you're applying it to
[00:32:27] or you can create a founding team with
[00:32:29] that expertise, I think there's huge
[00:32:31] impact to be made there and huge value
[00:32:33] to be built there. That's of important
[00:32:35] message. I mean, even I mean, it's hard
[00:32:38] it's easy to forget. Like, basically,
[00:32:39] once you've done it, you've done it.
[00:32:40] But, before you've done it, people are
[00:32:42] arrayed against you. Oh, sure. I mean,
[00:32:44] no one believes in it, which is why I
[00:32:45] think you got to you've also got to work
[00:32:47] in things that you're genuinely
[00:32:49] passionate about. Like, for me, I would
[00:32:52] have worked on AI no matter what
[00:32:54] happened. I just decided from a very
[00:32:56] young age it was the thing that um could
[00:32:59] be the most consequential thing I could
[00:33:01] think of. It's turned out that way, but
[00:33:02] it might not have. Maybe we would have
[00:33:03] been 50 years too early. And it was also
[00:33:06] the most interesting thing I could think
[00:33:08] of working on. And so, I would have
[00:33:10] still be working on AI today even if we
[00:33:13] were still, you know, in a little garage
[00:33:15] somewhere and it still wasn't quite
[00:33:16] working. I would have still been trying
[00:33:18] to find Maybe I'd have been back in
[00:33:19] academia or something, but I would have
[00:33:20] found some way of of continuing to work
[00:33:23] on it. So, I mean, AlphaFold was like an
[00:33:24] example of a spike that you pursued and
[00:33:27] it worked. You know, what makes a
[00:33:29] scientific domain ripe for an AlphaFold
[00:33:31] style breakthrough? And is there a
[00:33:32] pattern, a certain objective function?
[00:33:35] >> The way I I I I should write this up at
[00:33:37] some point when I have 5 minutes spare,
[00:33:39] but the lesson I've learned from all the
[00:33:42] Alpha projects we've done, specifically
[00:33:44] AlphaGo and AlphaFold, is um I think the
[00:33:48] techniques we have and the problems I
[00:33:49] look like to look for are great in if
[00:33:52] this if the situation can be described
[00:33:54] as massive combinatorial search space.
[00:33:56] The more massive the better in some
[00:33:58] ways. So, no brute force or special case
[00:34:00] algorithm will will solve it. And that's
[00:34:02] true of Go moves and of, you know,
[00:34:04] different configurations of proteins,
[00:34:07] far more than the atoms in the universe,
[00:34:08] both of those. And then, um you have a
[00:34:11] clear objective function. So, you know,
[00:34:13] you can think of it as minimizing the
[00:34:14] free energy in the proteins or, you
[00:34:16] know, the winning the game of Go. So,
[00:34:18] you need to be able to you need to
[00:34:19] specify your objective function clearly
[00:34:21] so you can hill climb. And then, um
[00:34:24] enough data and or simulator that can
[00:34:27] generate you uh lots of uh in
[00:34:29] distribution
[00:34:31] uh uh synthetic data. If those things
[00:34:33] are true, then I think um with today's
[00:34:36] methods, you can go a long way into
[00:34:38] tackling and finding the kind of needle
[00:34:40] in the haystack that you need uh to for
[00:34:42] the solution that you're trying to look
[00:34:44] for. And I think of just drug discovery,
[00:34:45] by the way, in the same way, right?
[00:34:47] There is a compound out there that would
[00:34:49] solve this disease if one could find it,
[00:34:52] if one could only find it, right? And
[00:34:54] that wouldn't have any side effects and
[00:34:55] so on. And as long as the laws of
[00:34:57] physics allows it, then the only
[00:35:00] question is how do you find it in an
[00:35:01] efficient way, in a tractable way? I
[00:35:04] think we showed for the first time,
[00:35:05] actually, with AlphaGo, that these
[00:35:07] systems could uh find those kinds of
[00:35:10] needles in a haystack, in that case, you
[00:35:12] know, the perfect Go move. I guess uh to
[00:35:14] get a little meta, I mean, we're we're
[00:35:15] talking about humans using these methods
[00:35:18] to create AlphaFold, but then there's a
[00:35:20] meta level, which is humans using AI to
[00:35:23] explore the space of possible
[00:35:25] hypotheses. How close are we to AI
[00:35:27] systems that can do genuine scientific
[00:35:29] reasoning, not just pattern matching on
[00:35:32] data?
[00:35:32] >> we're close. Um
[00:35:35] we're working on these general systems
[00:35:36] like that like I think we we have this
[00:35:38] system called co-scientist, and we have
[00:35:41] other algorithms like AlphaFold that can
[00:35:43] go a little bit beyond what the basic
[00:35:45] Gemini will do. And obviously, all the
[00:35:47] frontier labs are experimenting in this
[00:35:49] way. I've yet to seen anything so far,
[00:35:52] and we we all tinker with the same
[00:35:53] things, you know, some math problems
[00:35:54] that are a little bit harder than IMO
[00:35:56] and so on. I haven't seen anything yet
[00:35:59] um that is a true genuine, you know,
[00:36:02] massive discovery. That's my personal
[00:36:04] opinion. I think it's coming. I think it
[00:36:07] may be related to uh this earlier
[00:36:10] this thing we discussed about
[00:36:11] creativity, and and actually going on
[00:36:14] beyond the bounds of what's known. So,
[00:36:16] clearly, that's just not pattern
[00:36:17] matching at that point, cuz there is no
[00:36:19] pattern to match to, and it's a bit more
[00:36:21] than extrapolation. It's some kind of
[00:36:23] analogical reasoning, and I don't think
[00:36:25] these systems have that, or at least
[00:36:27] we're not using them in the in the right
[00:36:29] way to do that. So, the way I often say
[00:36:31] that in science is can it come up with a
[00:36:33] hypothesis that's really interesting,
[00:36:36] not just solve one. When I say just,
[00:36:38] we're not talking about just like
[00:36:39] solving the Riemann hypothesis or
[00:36:41] something. This would be obviously
[00:36:42] amazing, or one of the Millennium Prize
[00:36:44] problems, and maybe we're a couple of
[00:36:46] years out from doing that. Um but, I'd
[00:36:48] like to solve P equals NP. That's That's
[00:36:50] my favorite one. But, can you But, even
[00:36:52] harder than that would be to come up
[00:36:54] with a new set of of Millennium Prize
[00:36:56] problems that were regarded by top
[00:36:59] mathematicians to be as, you know, deep
[00:37:01] and meaningful and worthy of lifetime of
[00:37:04] study and effort to solve. Right? I
[00:37:07] think that's another level harder. And
[00:37:10] uh we don't have um you know, I still
[00:37:12] don't think we know how to do that. I
[00:37:14] don't think it's it's magical, though. I
[00:37:16] do think these systems will be
[00:37:18] eventually be able to do that. Maybe
[00:37:20] we're missing one or two things. And
[00:37:21] then, the way we would test that is, you
[00:37:23] know, I sometimes call it my Einstein
[00:37:25] test, which is, you know, can you train
[00:37:27] a system with the knowledge of cutoff of
[00:37:29] 1901, and then will it come up with you
[00:37:33] know, what Einstein did in 1905,
[00:37:34] including special relativity, you know,
[00:37:36] his annus mirabilis. Can Can it do that,
[00:37:39] right? Uh and then, I think we could run
[00:37:42] that test. May- Maybe we should just run
[00:37:44] that test and keep seeing if that's
[00:37:46] possible. And once that is, then I think
[00:37:48] we're on the verge of these systems
[00:37:49] being able to invent something new,
[00:37:51] truly novel. So, last last question. For
[00:37:54] the people who are deeply technical in
[00:37:55] this room who want to work on something,
[00:37:59] you know, even close to the scale that
[00:38:01] what you have created with you know,
[00:38:02] it's one of the largest AI efforts in
[00:38:04] the world, and you've been a pioneer for
[00:38:06] all these years. So, for that, I think
[00:38:08] everyone in this room thanks you and the
[00:38:10] folks at DeepMind very, very deeply from
[00:38:12] the bottom of our hearts. Thank you.
[00:38:14] What's the thing that you know now about
[00:38:16] building at the frontier that you wish
[00:38:17] you'd known at 25?
[00:38:20] I think we covered some of it in terms
[00:38:22] of actually you you work out that going
[00:38:24] after hard problems and deep problems um
[00:38:28] it's no more difficult in some ways than
[00:38:29] than going after a shallower, simpler,
[00:38:32] more superficial problem. They're
[00:38:33] they're they're just differently
[00:38:34] difficult. There's different things that
[00:38:36] are hard about each of those things, but
[00:38:38] I think given life's very short and you
[00:38:41] you know, you only have so much time and
[00:38:43] energy, you might as well put your life
[00:38:45] force into something that will really
[00:38:47] make a
[00:38:48] difference if you hadn't done it, if you
[00:38:50] hadn't been there to push it. So, I
[00:38:52] would just think of it through that
[00:38:54] lens. And then the other thing is if
[00:38:56] you're if you are and then we talked
[00:38:57] about deep tech and I love
[00:38:59] interdisciplinary
[00:39:00] uh work and I think that's going to be
[00:39:02] even more prevalent in the next few
[00:39:04] years in combinations of fields and uh
[00:39:07] uh finding the the the the connections
[00:39:09] between those fields. And it's going to
[00:39:11] be even easier to do that with AI. And
[00:39:13] then the only other thing I would say is
[00:39:15] if you know, if you have your depending
[00:39:17] on what your AGI timeline is, you know,
[00:39:19] mine's like 20 30 or something like
[00:39:20] this, then if you start off on a deep
[00:39:23] tech journey today
[00:39:26] usually that you're talking about a
[00:39:27] 10-year journey for for true deep tech
[00:39:30] in my opinion. So, then now you have to
[00:39:32] just consider AGI appearing in the
[00:39:35] middle of that journey. So, what does
[00:39:37] that mean? It doesn't it's not bad
[00:39:38] necessarily, but you have to take that
[00:39:40] into account, right? To will it be able
[00:39:43] to leverage it? What will the AGI system
[00:39:45] do with it? And it goes a little bit
[00:39:47] back to what you said earlier about
[00:39:48] AlphaFold and general AI systems. So,
[00:39:51] one thing I can think see happening is
[00:39:53] Gemini, Claude, or one of these general
[00:39:55] systems making use of AlphaFold like
[00:39:58] specialized systems as tools. I don't
[00:40:00] think we're going to have it just in one
[00:40:02] giant brain cuz it will have too much
[00:40:04] regression in if I put all the proteins
[00:40:07] into you know,
[00:40:08] Gemini, that wouldn't make sense. We
[00:40:10] don't need Gemini to do protein folding.
[00:40:12] Going back to your information
[00:40:13] efficiency, it will definitely affect
[00:40:15] its language skills or something like
[00:40:16] that, right? In a bad way. So, much
[00:40:19] better I think is to have really good
[00:40:21] general purpose tool usage models that
[00:40:23] will then
[00:40:24] maybe they could even train those
[00:40:26] specific tools, but they would be in a
[00:40:27] separate
[00:40:29] system. So, I think that's kind of
[00:40:31] interesting to think through the
[00:40:32] implications of that and then what you
[00:40:33] might build today. Also, physical things
[00:40:36] too like what kinds of factories would
[00:40:37] you build, what sorts of
[00:40:40] you know, finance systems and so on. So,
[00:40:42] I just think you need to really take
[00:40:44] that seriously and and and on the one
[00:40:46] hand is like an imagine what that world
[00:40:47] would look like and then build something
[00:40:49] that would be useful if that comes in
[00:40:51] halfway through.
[00:40:53] Demis Hassabis everyone.
[00:40:54] >> [applause]
