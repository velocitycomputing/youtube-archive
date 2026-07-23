---
video_id: bAoXVyibE6Q
title: "Mira Murati's 975B Open Model, Ramin Hasani on Post-Transformer AI, and Demis' AI FINRA | EP #271"
channel: Peter H. Diamandis
url: "https://www.youtube.com/watch?v=bAoXVyibE6Q"
watched_date: 2026-07-18
watched_at: "2026-07-18T12:00:00Z"
watch_count: 1
duration_seconds: 7013
source: youtube-history-browser
added_date: 
history_label: Saturday
history_order: 53
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 7013
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode covered four major AI developments: Mira Murati (former OpenAI CTO) launched Inkling, a 975-billion-parameter open-weight model emphasizing customization over raw performance and available for download and on-premise deployment; industry leaders Demis Hassabis, Elon Musk, and Sam Altman are pushing for US-led AI regulation modeled on FINRA, though panelists debate whether this is genuine safety concern or regulatory capture to block competition; the White House is reportedly considering a framework that would peg US model release ceilings to China's best open-weight models, creating perverse incentives for China to advance first; and Ramin Hasani (Liquid AI CEO) discussed building efficient general-purpose AI beyond transformers while China currently dominates open-weight model leaderboards with DeepSeek and Qwen.

**Actionable items:** Download and evaluate Inkling on your own hardware now—it's production-ready and stronger than comparable US open models like Nemoron. If you're building AI products, shift focus from competing on raw capability to building adaptability and customization layers, which Murati's bet suggests will be the competitive advantage. Monitor regulatory announcements closely, as proposed frameworks could significantly restrict which models you can deploy or release; particularly watch whether regulations lock in specific benchmarks that could distort future model development.

## Transcript

[00:00:00] Mera Marotti, the former OpenAI CTO,
[00:00:03] just shipped her first model. It's
[00:00:05] called Inkling. Customization over
[00:00:07] leaderboard dominance uh is what's going
[00:00:10] to win her the day.
[00:00:11] >> She's built exactly the thing hitting
[00:00:13] the market that exactly what everybody
[00:00:14] needs. Right now,
[00:00:16] >> I want to pivot to a discussion of
[00:00:18] liquid AI, the small language models,
[00:00:21] what they are, what they mean. Our
[00:00:22] mission has always been building
[00:00:24] efficient generalpurpose AI at every
[00:00:26] scale that explores the computational
[00:00:29] graphs of intelligence beyond
[00:00:31] transformer and then figure out what
[00:00:33] should be that architectural design that
[00:00:36] [music] brings the same level of
[00:00:37] intelligence that a frontier model into
[00:00:40] let's say on on a CPU.
[00:00:42] >> CEOs building the most powerful
[00:00:44] technology in the world are asking to be
[00:00:46] regulated. Demisabi, CEO of DeepMind, he
[00:00:48] called for a US-led frontier AI
[00:00:51] standards [music] body modeled on FINRA.
[00:00:53] When the incumbents ask for the rules
[00:00:56] and they set the [music] standards, they
[00:00:58] set up a barrier for all the entry-level
[00:01:00] [clears throat] labs [music] coming in.
[00:01:02] Let's just be real. AI moves way way too
[00:01:04] fast for any kind of traditional uh
[00:01:06] bureaucracy. How quickly can you do it
[00:01:08] is going to be huge, huge challenge
[00:01:10] because
[00:01:14] >> now that's a moonshot, ladies and
[00:01:15] gentlemen.
[00:01:18] All right, everybody. Welcome to
[00:01:20] Moonshots, your number one podcast in
[00:01:22] all things AI. Your front row seat to
[00:01:24] the singularity. I'm here with my
[00:01:25] magnificent Moonshot mates, our original
[00:01:28] quartet, AWG, DB2, and Seem, and a
[00:01:31] special guest, Reine Hassani, co-founder
[00:01:34] and CEO of Liquid AI, and a pioneer in
[00:01:37] small language models, which we'll dive
[00:01:39] into. Raine, welcome. Uh, where are you
[00:01:41] this morning, pal?
[00:01:43] >> Thanks so much for having me. I'm
[00:01:45] actually in Spain right now.
[00:01:46] >> In Spain? All right.
[00:01:48] >> There's nothing going on in Spain this
[00:01:49] week. [laughter]
[00:01:50] >> God damn it.
[00:01:52] >> Yes.
[00:01:52] >> I'm I'm a I'm struggling from yesterday
[00:01:55] cuz I'm a long-suffering England
[00:01:56] supporter.
[00:01:58] >> Um it was a very difficult game to
[00:02:00] watch. God, they were like just had it
[00:02:02] with six minutes to go and they blew it.
[00:02:04] >> Yeah.
[00:02:04] >> And Messi's a genius.
[00:02:05] >> That's the round That's the round ball,
[00:02:07] right? Is that
[00:02:08] >> That's the round ball. [laughter] Now,
[00:02:10] Peter, this is where the Faulland's war
[00:02:11] gets relitigated on a soccer pitch. Oh
[00:02:14] god. [laughter] You know, I just flew in
[00:02:16] last night from Zurich and I had the
[00:02:18] most painful experience, right? I don't
[00:02:20] know why every airline doesn't have
[00:02:22] Starlink. You know, I'm suffering on
[00:02:24] some me, you know, some meager thin pipe
[00:02:27] connection and you're flying over the
[00:02:29] poles over the, you know, the Northern
[00:02:31] Territories and there's nothing. And I'm
[00:02:34] trying to get ready for this pod. I was
[00:02:35] like, "Please give me give me some
[00:02:38] bits." So anyway, challenge.
[00:02:40] >> You must have grown up on soccer, right?
[00:02:42] didn't you were in Vienna for a while
[00:02:43] and getting your PhD and or your
[00:02:46] undergrad or whatever it was. Uh
[00:02:48] >> yeah. Yeah. I mean soccer has been like
[00:02:50] a big thing, you know. I'm Persian and
[00:02:52] Austrian like at the same time, you
[00:02:54] know, like it's a big thing for us. So,
[00:02:56] um yeah, like competition is something
[00:02:58] that, you know, uh it's it's extremely
[00:03:00] core to what we do even today, you know.
[00:03:02] So, and uh I feel like that's like one
[00:03:05] of the main drivers like sports and
[00:03:07] everything like has been part of our
[00:03:09] lives like from day one and then getting
[00:03:11] into science the same thing you know now
[00:03:13] getting into ventures same things you
[00:03:15] know and that's uh that's what we're
[00:03:17] doing
[00:03:18] >> just compete compete compete compete I
[00:03:20] love it
[00:03:20] >> well are you there for a little bit of
[00:03:22] time or you coming back soon
[00:03:24] >> no I'm coming I'm I'm flying tomorrow
[00:03:25] actually back to San Francisco
[00:03:27] >> and Salem are you are you jealous of
[00:03:30] everybody of him being in Europe or are
[00:03:31] you happy to No, no. Three weeks
[00:03:33] bouncing around in 10 different spots.
[00:03:35] I'm very happy to be home [laughter]
[00:03:36] right now. I was just in Spain where me
[00:03:39] and myself. So,
[00:03:40] >> uh, all right.
[00:03:41] >> There was a lot going on actually like
[00:03:42] in in in Europe, you know. So, that's
[00:03:45] >> same same like you 10 different places.
[00:03:48] Then,
[00:03:48] >> you know, Alex and I were just
[00:03:50] reminiscing the fact that Europe's uh
[00:03:52] sort of major advantage in the future is
[00:03:54] it's going to be a museum of the way the
[00:03:56] world used to be. Um, [laughter]
[00:03:59] ouch. Ouch.
[00:04:02] But it is beautiful. There's no
[00:04:04] question. It is gorgeous. All right, I
[00:04:06] want to jump into our first
[00:04:06] conversation. We have a lot to unpack
[00:04:08] here. And of course, our mission is
[00:04:10] keeping you aware of what's going on in
[00:04:12] the world and giving you sort of the
[00:04:14] optimistic, hopeful vision of the
[00:04:16] future. Uh join us and uh keep up with
[00:04:20] the incredible pace as we head towards a
[00:04:21] singularity. So our first story today,
[00:04:24] once again, CEOs building the most
[00:04:27] powerful technology in the world are
[00:04:29] asking to be regulated. You know, last
[00:04:31] week Sam Alman published an op-ed in the
[00:04:33] Financial Times proposing a framework
[00:04:36] for a US-led international forum that
[00:04:39] would establish standards, provide
[00:04:41] expertise, impartial analysis and
[00:04:43] capabilities, and assess risks. This
[00:04:45] week, both Elon and Demis are adding
[00:04:48] their voice to the regulatory
[00:04:49] conversation. Elon says he expects a
[00:04:52] standalone uh regulator similar to the
[00:04:54] FA or FCC to emerge at some point
[00:04:56] because in his words the consequences of
[00:04:59] AI going wrong are severe. Then this
[00:05:02] week Demisaba CEO of Deep Mind went
[00:05:04] further in an essay titled A Framework
[00:05:06] for Frontier AI and the dawning of a new
[00:05:09] age. He called for a US-led frontier AI
[00:05:12] standards body modeled on FINRA, the
[00:05:15] industry funded watchdog that polices
[00:05:17] Wall Street under SEC oversight. He
[00:05:20] wants the FINRA equivalent to test
[00:05:22] Frontier models before release. He
[00:05:25] reportedly wants this up and operational
[00:05:27] before the end of the year. Let's take a
[00:05:30] look at a quick video from Elon and then
[00:05:32] let's jump into this conversation.
[00:05:35] I think the the general I think it's
[00:05:37] clear that there's a strong consensus
[00:05:39] there should be some AI regulation that
[00:05:41] it would be in the best interests of the
[00:05:42] people to do so and I think we'll
[00:05:44] probably see something happen. I don't
[00:05:46] know on what time frame um or exactly
[00:05:48] how it will manifest itself. I I don't
[00:05:50] know. I mean this there's clearly we've
[00:05:53] created regulatory agencies before. Um
[00:05:55] while our regulatory agencies are not
[00:05:57] perfect um and I deal with regulators on
[00:05:59] a very frequent basis um with automotive
[00:06:03] um you know communications Starlink um
[00:06:06] and then uh FAA with with rockets.
[00:06:08] >> I think the probability of there being
[00:06:10] some sort of AI regulatory agency that
[00:06:12] stands on its own similar to the FAA or
[00:06:14] FCC is likely at some point.
[00:06:16] >> You think so?
[00:06:16] >> I think so. Um,
[00:06:19] now the the reason that I've been such
[00:06:21] an advocate for uh AI safety in advance
[00:06:24] of sort of anything terrible happening
[00:06:26] is that I think the consequences of AI
[00:06:29] going wrong are are severe. Um, so we
[00:06:32] have to be proactive rather than
[00:06:33] reactive.
[00:06:34] >> Um, amazing. So I this is a conversation
[00:06:39] we've seen over and over again and I
[00:06:41] think the government, the public and now
[00:06:43] the CEOs want to be leading this. I like
[00:06:45] the approach that Demis laid out, right?
[00:06:48] Um, but the challenge we have to discuss
[00:06:51] is when the incumbents ask for the rules
[00:06:54] and they set the standards, they set up
[00:06:56] a barrier for all the entry level labs
[00:06:59] coming in.
[00:07:01] See or Dave, do you want to jump in
[00:07:03] first?
[00:07:04] >> I'd be very curious to know, Ramine, if
[00:07:06] uh do they reach out to liquid AI and
[00:07:08] say, "Hey, join this, you know, we're
[00:07:10] going to create a FINRA like regulatory
[00:07:11] body." Um you the reason FINRA works
[00:07:14] fundamentally is because people from the
[00:07:16] industry who know what they're doing are
[00:07:17] willing to join it. They're definitely
[00:07:19] not willing to join the government in
[00:07:20] general, but they're willing to do a
[00:07:22] year or two in a regulatory body. It's
[00:07:25] actually kind of a badge of honor. So
[00:07:27] for this to work in AI, it would have to
[00:07:29] be something cool. And people like
[00:07:31] Ramine or maybe you know some of the
[00:07:32] people on your team would need to come
[00:07:34] into your office and say, "Hey boss, you
[00:07:36] know, I'd love to do this for a year. I
[00:07:38] think it's really good for the world.
[00:07:40] Will you let me do it?" And then you
[00:07:41] would also have to be like yeah this is
[00:07:43] a functional organization go for it. So
[00:07:45] if it passed those two hurdles I mean it
[00:07:47] might it might actually work. I don't
[00:07:49] know what do you think. Yeah, there's
[00:07:50] like you know like there's a capability
[00:07:52] kind of threshold that we we're trying
[00:07:54] to define right now and some some sort
[00:07:56] of an iteration is needed to see like
[00:07:58] how this um how how this framework it
[00:08:02] has to exist you know that's that's for
[00:08:03] sure you know there has this has to be
[00:08:05] there but uh it has to be related to
[00:08:07] capability and then the thing that
[00:08:09] becomes a challenge is that that there's
[00:08:11] a horizontal kind of capability lock
[00:08:13] into like active like let's say like
[00:08:15] enterprise deployment of AI and then
[00:08:17] there's the vertical because if you go
[00:08:19] to different verticals like for example
[00:08:20] we operate on on on device and with
[00:08:23] enterprises that are connected to the
[00:08:24] physical world you know like we're
[00:08:25] connect we are talking to car
[00:08:27] manufacturers like semiconductor
[00:08:28] business you know and laptop business
[00:08:31] you know like people that are building
[00:08:32] like AIPCs and then we are also working
[00:08:34] with financial services and we working
[00:08:36] with like e-commerce and and biotech
[00:08:38] kind of companies and we see like in
[00:08:40] different verticals you know like the
[00:08:42] enterprise applications themselves and
[00:08:45] enterprise criteria for let's say a
[00:08:47] limit or let's say a regulation kind or
[00:08:50] a governance kind of a structure is very
[00:08:52] different you know so for us it becomes
[00:08:54] a lot more kind of verticalized because
[00:08:56] we're building a specialized models and
[00:08:58] those specialized models like
[00:08:59] pervertical we we have had like
[00:09:02] conversations with the DoD and we have
[00:09:03] had like a joint uh uh submission of
[00:09:06] something I think with AMD like pretty
[00:09:08] uh like just recently like we with with
[00:09:10] our team to really have um have a say
[00:09:13] basically like in in in the design of
[00:09:15] like these regulatory kind of things and
[00:09:17] I think as an exploration I think
[00:09:18] Everything has to be like getting
[00:09:20] started. I like to look at it as a game
[00:09:22] theory kind of uh way of uh looking at
[00:09:24] it like how to design like policies in
[00:09:26] general. Like it would be a stake kind
[00:09:28] of game. I don't know if anyone is
[00:09:30] familiar with I don't want to nerd out
[00:09:31] like pretty soon on this but we can we
[00:09:32] can talk about this. [laughter]
[00:09:34] >> Alexon
[00:09:36] the better.
[00:09:36] >> Sooner the better.
[00:09:37] >> Yeah. So I mean stakeber games like
[00:09:40] essentially like where two policies like
[00:09:42] basic like there's like a you know like
[00:09:44] you have like a policy maker and then
[00:09:45] you have agents or bodies that are
[00:09:47] working in that uh kind of game theory
[00:09:49] kind of optim they they're trying to
[00:09:51] find an equilibrium you know what is the
[00:09:52] optimal policy and what is basically
[00:09:55] which is good for both right and then so
[00:09:58] there's the frequency of action usually
[00:10:00] policy makers are slower than the agents
[00:10:03] in the society you know so if you think
[00:10:05] about like you can you can really model
[00:10:08] like that, right? And then you can uh
[00:10:09] you can figure out like an an
[00:10:11] equilibrium. This is not a Nash
[00:10:13] equilibrium because everything doesn't
[00:10:15] happen simultaneously. Regulations
[00:10:17] happens and then you agents react and
[00:10:20] then you iterate kind of accordingly and
[00:10:22] then you change those uh uh regulations
[00:10:25] basically. So I think
[00:10:26] >> I see you trumping at the bit here
[00:10:28] buddy.
[00:10:29] >> Yeah. So I think I think what Raine is
[00:10:31] saying is exactly right. The problem is
[00:10:33] we have no mechanism for that. Right.
[00:10:35] like
[00:10:37] if you go down the path remain that
[00:10:38] you're talking about you end up with the
[00:10:40] appropriate structures that are adaptive
[00:10:42] and API based or like driven by
[00:10:44] benchmarks or something but the
[00:10:46] mechanism that people have today is just
[00:10:47] static law and the minute you pass the
[00:10:50] law the law is going to be out of date
[00:10:51] right the I I found that the FA and FCC
[00:10:54] analogy is is is pointing in the right
[00:10:57] direction but a let's just be real AI
[00:11:00] moves way way too fast for any kind of
[00:11:02] traditional government bureaucracy
[00:11:05] Right. So, you're going to need you're
[00:11:07] going to need a standards body. You're
[00:11:09] going to need real-time audits. And
[00:11:10] you're going to need open evaluation
[00:11:12] suites. Um otherwise, you're going to
[00:11:13] end up otherwise you're going to end up
[00:11:15] in political gatekeeping and then you're
[00:11:17] in a mess. The problem
[00:11:19] >> isn't that what's good about FINRA. It's
[00:11:21] not a government agency. It's an
[00:11:23] industryfunded self-regulatory org.
[00:11:26] >> Uh it is, but then the teeth go to the
[00:11:29] uh SEC, which is essentially being
[00:11:31] dismantled right now. So there's all
[00:11:33] sorts of issues here. I I I I think the
[00:11:36] the trend is correct, but how quickly
[00:11:38] can you do it is going to be huge huge
[00:11:40] challenge because forget passing a law,
[00:11:43] passing a structure where you have a new
[00:11:45] construct like this takes a long time
[00:11:47] and it takes forever uh in Europe. I
[00:11:50] >> I think Ramine nailed two things that
[00:11:51] are very different from FINRA right out
[00:11:53] of the gate. One of them is, you know,
[00:11:55] at Vesmark, if somebody on our executive
[00:11:57] team said, "Hey, I want to be part of
[00:11:58] FINRA for a couple years." We would say,
[00:12:00] "Sure, put on your suit and tie. go to,
[00:12:02] you know, go to the meetings, come back
[00:12:04] in two years, we'll still be here.
[00:12:06] You're not going to do that. Like if
[00:12:07] Alexander Amini or Matias Lechner came
[00:12:10] into your office or said, "Hey, I I'm
[00:12:12] going to check out for 3 weeks." You'd
[00:12:13] be like, "No, you you can't do that
[00:12:15] right now." So it's difference number
[00:12:16] one is nobody's going to carve out the
[00:12:18] time to do something for years like they
[00:12:20] do at FINRA. The the other big
[00:12:22] difference is AI can help regulate
[00:12:24] itself and FINRA, there's no equivalent
[00:12:27] to that in FINRA. It's all people just
[00:12:28] chatting for long periods of time. But
[00:12:31] you know when you start talking about
[00:12:32] Nash equilibriums and other ways to to
[00:12:34] automate the process of regulation
[00:12:36] that's a big big difference as well. So
[00:12:38] the FINRA analogy has some legs but you
[00:12:41] know the differences are bigger than the
[00:12:42] similarities.
[00:12:43] >> Alex is I want to hear your voice on
[00:12:45] this B.
[00:12:45] >> I I tend to think this is a bad idea. It
[00:12:48] smells like regulatory capture. It
[00:12:50] smells like the attempted formation by
[00:12:52] Demis of a cartel of Frontier Labs. And
[00:12:55] I think the elephant in this particular
[00:12:57] room is openweight models and research
[00:13:00] that lives outside of the frontier
[00:13:02] capabilities. And it's very easy to
[00:13:05] imagine a future with FINRA or or other
[00:13:09] I mean worst case scenario FDA like
[00:13:11] capability even though outgoing
[00:13:13] personnel from the current
[00:13:14] administration have declared uh with in
[00:13:17] no uh no equivocal terms that there is
[00:13:21] going to be no FDA for AI regulation.
[00:13:24] that that would be maybe on the the
[00:13:25] worst case end of the spectrum that we
[00:13:29] we see the emergence of some sort of
[00:13:31] cartel of frontier labs that locks in
[00:13:33] certain practices, certain price
[00:13:36] performance optimal frontiers that try
[00:13:39] to box out open weight or open-source or
[00:13:43] uh say university driven or other
[00:13:47] nonincumbent
[00:13:48] frontier models and I think that would
[00:13:49] be an utter disaster for both the west
[00:13:52] and the world for continuing to advance
[00:13:55] us towards everinccreasing super
[00:13:57] intelligence capabilities. I I just
[00:13:59] don't think it's a good idea.
[00:14:00] >> You know, and the other elephant the
[00:14:02] other elephant in the room here is these
[00:14:04] CEOs who are asking for some level of
[00:14:07] regulation I I think are are looking for
[00:14:10] a backs stop. You know, if things go
[00:14:11] wrong, they want to be able to point at
[00:14:13] someone else. Now, I mean, we're all
[00:14:15] super fans of the optimistic vision of
[00:14:18] AI, but there's going to be issues that
[00:14:20] materialize. is there going to be rogue
[00:14:22] AIs that take down a power grid or take
[00:14:25] down you know stock market or something
[00:14:26] like that for some period of time and I
[00:14:29] I guess they you there going to be
[00:14:32] lawsuits flying as a result of that
[00:14:34] unless there's a regulatory body that
[00:14:36] that backs stops these large these large
[00:14:39] models and these large frontier labs
[00:14:41] >> maybe uh there are I think at least two
[00:14:43] different frames that one can look at
[00:14:45] the liability side from there's regulate
[00:14:48] the inputs that is to say like have
[00:14:50] something that's FINRA like or FDA like
[00:14:52] that regulates the raw capabilities of
[00:14:54] the models at model construction time.
[00:14:57] That that's one end of a spectrum. The
[00:14:59] other end of the spectrum is regulating
[00:15:01] the actions of the models. Like you you
[00:15:03] let the lawsuits fly if if a model takes
[00:15:06] down a stock market or does something
[00:15:08] else that uh otherwise harms third
[00:15:10] parties. That's the other end of the
[00:15:12] spectrum. It's not obvious to me that we
[00:15:14] should be in the business of regulating
[00:15:16] super intelligence at super intelligence
[00:15:18] time. That's that's maybe tantamount to
[00:15:21] thought policing the AIS. And I'm I'm
[00:15:23] not generally a fan of that notion of
[00:15:26] let's thought police the AIS but not
[00:15:28] thought police the humans. We don't at
[00:15:29] least in in the West have a practice of
[00:15:32] regulating what's in our minds. We we
[00:15:34] don't have a practice or a tradition of
[00:15:36] regulating an upper limit say or via
[00:15:39] some sort of regulatory code saying
[00:15:41] humans uh natural persons can't be above
[00:15:45] some level of intelligence. is not
[00:15:46] obvious to me why we would create a new
[00:15:49] tradition of regulating or otherwise
[00:15:51] coordinating the upper intelligence of
[00:15:53] non-natural uh entities perhaps soon to
[00:15:56] be persons but regulating the actions
[00:15:59] that in at least the western legal
[00:16:01] cannon that we do do and that I'd be
[00:16:03] much more supportive of.
[00:16:04] >> So do you Alex, let me ask you a pointed
[00:16:06] question here. Do you think that this,
[00:16:08] you know, sort of outcry for regulation
[00:16:10] by the large frontier labs is is
[00:16:13] regulatory capture that they're just
[00:16:15] trying to build a moat against uh
[00:16:17] further players coming in? Or do you
[00:16:19] think they actually want to provide some
[00:16:22] level of safety? What's their underlying
[00:16:24] driver here?
[00:16:25] >> I I worry that it's more regulatory
[00:16:27] capture and creating moes for themselves
[00:16:30] in a hyperco competitive landscape. And
[00:16:32] it is h I mean, it is a rat race at this
[00:16:34] point, the frontier. And I I I do worry
[00:16:36] that it's more regulatory capture than
[00:16:38] it is some notion of protecting the the
[00:16:41] future here. Seem, what do you think?
[00:16:45] >> Uh, not workable.
[00:16:47] >> Well, I know that, but do you think do
[00:16:48] you think it's regulatory capture or do
[00:16:49] you think that the that these CEOs are
[00:16:51] trying to just make sure we've got a
[00:16:52] safety a safety net of some type?
[00:16:55] >> I I I'd say it's like 50/50, but I think
[00:16:58] there's a bigger problem. There's an
[00:16:59] elephant in the room here. Some
[00:17:01] >> there's already an elephant in the room.
[00:17:03] We have a room has to accommodate so
[00:17:05] many elephants. [laughter] We need some
[00:17:07] other non-human animals.
[00:17:08] >> Better get a bigger room. You've got uh
[00:17:10] non-state actors and other folks that
[00:17:13] won't listen to this structure and
[00:17:15] you're back to square one. What's the
[00:17:17] What's the point? I'm going to say it
[00:17:19] again. I've said this repeatedly. I see
[00:17:21] no mechanism to regulate AI. It's moving
[00:17:24] way too quickly. Any regulatory is
[00:17:26] static.
[00:17:28] >> And so it's going to have
[00:17:30] position on that one. just if I may
[00:17:31] Peter narrowly on that I mean there are
[00:17:34] definitely hypothetical mechanisms and
[00:17:36] that I'm not supportive of for
[00:17:38] regulating AI like we royal we the the
[00:17:41] US and China if going back to I think we
[00:17:44] gestured at it in a past pod but uh past
[00:17:47] proposals to say regulate the foundaries
[00:17:49] regulate the chip outputs regulate the
[00:17:51] data centers establish mutually assured
[00:17:54] destruction type schemes where the US is
[00:17:56] monitoring Chinese data centers and vice
[00:17:58] versa like there are There are schemes
[00:18:02] there are schemes at choke holds as
[00:18:04] Peter says in the supply chain by which
[00:18:07] one could imagine doing this
[00:18:09] >> interesting mechanism
[00:18:11] >> the only mechanism it's going to be like
[00:18:14] a pandemic style threat detection that
[00:18:17] would be globally agreed and I don't see
[00:18:19] how we get there
[00:18:20] >> well you don't need global you just need
[00:18:21] US and China right the rest of the world
[00:18:23] is is basically outside those blocks or
[00:18:25] inside those blocks
[00:18:26] >> all right well I think my guess There's
[00:18:30] probably a poly market out there uh we
[00:18:32] can we can look at and if someone wants
[00:18:34] to search on it you know the question of
[00:18:36] will we have a regulatory body by end of
[00:18:38] the year right we have Demis saying by
[00:18:41] the end of this year you know Elon
[00:18:43] stepping up uh and and Sam obviously
[00:18:46] trying to on his own on the side trying
[00:18:50] to push for this so when the three
[00:18:51] largest labs uh are pushing for it my
[00:18:54] guess is the government will latch on
[00:18:56] and will do this I don't think it's a
[00:18:58] matter of if it's only a matter of when
[00:19:01] and what the structure will be.
[00:19:03] >> Well, I I should also note that Elon
[00:19:05] clip I think is from three years ago,
[00:19:07] which is interesting. You know, it's
[00:19:08] from three years ago because Elon had
[00:19:10] his sort of like painted on uh Iron Man
[00:19:13] goatee uh when he was in that that that
[00:19:16] phase. Uh so, so Elon's been forecasting
[00:19:18] this for at least three years. Others
[00:19:20] have been forecasting it for decades. We
[00:19:22] still don't have it. We have like
[00:19:24] subdivisions orgs within NIST that are
[00:19:26] uh working on standards but that's not
[00:19:29] really regulatory body. We have
[00:19:31] executive orders that are creeping
[00:19:33] towards a regular regulatory body. But
[00:19:35] you know at what point it do we sort of
[00:19:37] are we frogs boiling in water where
[00:19:40] there's just like a creeping roll out of
[00:19:42] increased standards expectations of
[00:19:45] early reviews but it never quite reaches
[00:19:48] regulatory agency level before we
[00:19:51] achieve whatever escape velocity we're
[00:19:52] heading towards.
[00:19:54] >> Well, uh we're going to monitor this one
[00:19:55] closely for everybody. I I think my
[00:19:58] guess is we see this before the end of
[00:20:00] the year and the question is can we see
[00:20:02] something that's intelligent. Uh let's
[00:20:04] go to the next story which is related uh
[00:20:06] and this is a wild one comes from the
[00:20:08] Washington Post that the White House is
[00:20:10] reportedly weighing a capability
[00:20:11] framework that would clear US models
[00:20:14] open or closed as long as they stay at
[00:20:17] or below the level of China's best
[00:20:19] openweight model. What's the
[00:20:21] translation? So the proposed ceiling for
[00:20:23] what American companies can openly
[00:20:25] release is pegged to what China has
[00:20:27] already put out on the internet for
[00:20:30] free. So here's the logic. Chinese
[00:20:32] openweight models reportedly trail US
[00:20:34] models an average of 7 months. I think
[00:20:36] that's been closing over time. Uh so if
[00:20:40] anything is at or below that, it's
[00:20:43] already out there. It's an implicit
[00:20:45] admission that open models cannot be
[00:20:47] unshipped. Models like deepseek have
[00:20:50] already been downloaded millions of
[00:20:51] times. So once China releases a model
[00:20:55] freely, banning it is impossible. So the
[00:20:58] US response is to define a permissible
[00:21:00] ceiling rather than a wall. The
[00:21:02] implications were tying our open release
[00:21:05] ceiling to China's pace of release
[00:21:07] effectively giving you know Beijing
[00:21:09] control. If they push their open weight
[00:21:12] models higher then the US can release
[00:21:14] higher models as well. If China holds
[00:21:16] back, then they throttle us. And it's a
[00:21:19] very strange mechanism. I was surprised
[00:21:22] to see this. Alex, let's go to you first
[00:21:24] on this one. What do you think of this?
[00:21:26] >> Uh, I mean, the the obvious note here is
[00:21:28] this creates the perverse incentive to
[00:21:30] let China win the race to ever greater
[00:21:32] super intelligence so that Western
[00:21:34] models and western labs can escape
[00:21:36] regulation. I'm not a fan of this. Uh uh
[00:21:40] raine gesturing at you from a game
[00:21:42] theoretic perspective. This is the I
[00:21:44] think this would be the moral equivalent
[00:21:46] of throwing the steering wheel out the
[00:21:47] window in in a game of chicken. Not such
[00:21:50] a great idea. Not supportive of this.
[00:21:52] >> I love that. Oh my god. See, what do you
[00:21:56] make of this? Is this just perverse
[00:21:57] Washington DC logic?
[00:22:00] >> Yes. This is like trying to uninvent the
[00:22:02] printing press. I mean you we're
[00:22:04] throwing the kitchen sink at things
[00:22:06] trying to to to solve something that's
[00:22:08] already a problem. The you you have to
[00:22:11] move from like prevention and whatever
[00:22:13] to adaptation. You have to go to that
[00:22:14] and we we don't have the mechanisms for
[00:22:16] that.
[00:22:16] >> I mean you know I mean would you even
[00:22:20] listen to this?
[00:22:23] I mean what what logic
[00:22:25] >> you might [laughter]
[00:22:27] >> well
[00:22:28] >> what do you think of this? I mean the if
[00:22:31] I just look at the the the the
[00:22:33] progression of the technology itself
[00:22:34] like it's it's getting into into the
[00:22:37] place where like you AI are designing AI
[00:22:40] like we you're doing the same things and
[00:22:41] all of the labs are doing this and the
[00:22:43] pace it's just the pace of model
[00:22:45] development is like getting so so so
[00:22:47] much smaller you know that is um is
[00:22:50] becoming like exponentially more more
[00:22:52] difficult to really like impose any any
[00:22:55] of these type of constraints and I know
[00:22:57] like they had these type of
[00:22:58] conversations But it's just at the level
[00:23:00] of conversations, you know, like these
[00:23:01] are the things that are getting leaked
[00:23:02] outside of
[00:23:03] >> White House for ideas.
[00:23:07] >> Let me let me give a headline from for
[00:23:09] Alex for for his next newsletter. Um,
[00:23:12] the singularity is becoming a trade
[00:23:14] dispute
[00:23:15] >> for the next newsletter. That was like
[00:23:17] two newsletters ago.
[00:23:18] >> Okay, fine. Whatever. [laughter] That's
[00:23:20] out already, but thank you.
[00:23:22] Um, you know, I can just imagine where a
[00:23:24] US Frontier Lab CEO calls DeepC can say,
[00:23:27] "Would you please accelerate your next
[00:23:29] model release? We want to get ours out
[00:23:31] as well."
[00:23:32] >> Or you see worst case scenario. I mean,
[00:23:34] there there's actually a an even worse
[00:23:36] scenario, which is you start to see the
[00:23:37] the best, if not Western labs, unlikely,
[00:23:40] the best Western researchers move to
[00:23:42] China to escape this regulatory
[00:23:45] framework. That would be a disaster. I I
[00:23:47] think and and we've seen this, by the
[00:23:49] way. There's precedent for this. We saw
[00:23:51] this in biotech where China now exceeds
[00:23:53] the west in terms of number of trials.
[00:23:55] Like China is experiencing a biotech
[00:23:57] boom that could happen in AI as well
[00:23:59] disaster.
[00:23:59] >> It's it's much more specific than that.
[00:24:01] If you look at all the quantization
[00:24:02] research, all the best stuff came out of
[00:24:04] Microsoft research in China. All those
[00:24:06] people now are at Chinese labs. They're
[00:24:08] not they're not still working for US
[00:24:10] companies.
[00:24:11] >> China ran away with turnery and one bit
[00:24:13] quantization. You see a little bit of
[00:24:15] Western research. I don't think we're
[00:24:17] talking that much about it in in this
[00:24:18] episode. you see a little bit of uh
[00:24:20] encouraging western research on like one
[00:24:22] bit or 1.58 bit quantization but China
[00:24:25] ran away with it due to constraints.
[00:24:26] >> Yeah, it's a new company.
[00:24:28] >> Look, this is a huge problem, right?
[00:24:30] Because over we've seen throughout
[00:24:32] history that open ecosystems always win
[00:24:35] >> and this is not open versus closes which
[00:24:38] open ecosystem wins and the US's
[00:24:41] historical strength has been open per
[00:24:43] ecosystems with permissionless
[00:24:45] innovation. you like abandoning that
[00:24:48] would be the weirdestly strategically
[00:24:50] bizarre thing we've ever seen.
[00:24:51] >> Yeah. The the other I mean there's even
[00:24:54] a meta worry I have which is how do we
[00:24:56] even define capabilities and and I worry
[00:24:59] a little bit not just about regulatory
[00:25:00] capture of the labs themselves. I think
[00:25:03] there's actually so so sorry to be like
[00:25:05] a a meta doomer here. uh there's a worst
[00:25:08] worst worst case scenario which is we
[00:25:11] freeze in or otherwise lock in the
[00:25:13] benchmarks for how we measure
[00:25:14] capabilities and that that would be I
[00:25:17] think maybe even worse than just locking
[00:25:19] in the incumbents as labs because if if
[00:25:21] someone somewhere ratifies all right
[00:25:23] like whatever index of evals this is
[00:25:27] going to be the rubric going forward for
[00:25:29] how we measure what's above the
[00:25:31] threshold for frontier versus below
[00:25:33] what's a frontier model versus not I I
[00:25:36] worry that could so distort model
[00:25:38] capabilities like they'll overex
[00:25:39] exercise certain capabilities
[00:25:40] deliberately and perversely under
[00:25:43] incentivize or underbenchmax others that
[00:25:45] it'll just totally distort maybe topize
[00:25:48] the the future landscape of super
[00:25:50] intelligent capabilities.
[00:25:53] >> All right. Well, again this is a story
[00:25:56] that we'll be we'll be following on this
[00:25:58] news of ope models. So in the past
[00:26:00] >> there's our topiary right there. In the
[00:26:03] past, we've been discussing how ope
[00:26:05] models uh have been in the US have been
[00:26:07] lagging in China. We have Nvidia's
[00:26:09] Neotron 3. We've got Google Gemma 4. But
[00:26:13] that changed last night with some
[00:26:15] breaking news. Mera Marotti, the former
[00:26:17] OpenAI CTO, uh who walked out and raised
[00:26:21] her one of the largest seed rounds ever.
[00:26:24] Uh it was incredible uh financing she
[00:26:27] pulled off in the background. just
[00:26:29] shipped her first model uh for her
[00:26:31] startup called Thinking Machine Labs.
[00:26:33] It's called Inkling. It's an Opalweight
[00:26:35] Foundation AI model that can be
[00:26:37] downloaded by anyone, fine-tuned and run
[00:26:40] on prem on your own hardware. Uh the
[00:26:42] specs are serious. Uh it's a mixture of
[00:26:44] experts model with 975 billion total
[00:26:48] parameters. Only fires 41 billion at any
[00:26:50] one time. So it keeps it, you know,
[00:26:52] keeps the model going fast and cheap. It
[00:26:54] was trained on 45 trillion tokens of
[00:26:56] text, image, audio, and video. And very
[00:26:59] importantly, reasons natively across all
[00:27:01] four. Reuters Muse framed it exactly
[00:27:04] right. Quote, "This is meant to be a
[00:27:06] western alternative to the Chinese opate
[00:27:08] models, Deep Seek and Quinn, that have
[00:27:10] dominated the opo leaderboards." Uh,
[00:27:12] now, interestingly enough, Maradi her
[00:27:15] bet is contrarian here. She's not
[00:27:17] claiming it's the best model on Earth.
[00:27:19] Her own blog says so. Uh she's betting
[00:27:22] that an AI that AI companies can adapt
[00:27:25] her models for themselves. That
[00:27:27] customization over leaderboard dominance
[00:27:30] uh is what's going to win her the day.
[00:27:33] >> You you've you've hit there, Peter, on
[00:27:35] the really big thing. She's making this
[00:27:38] she's pushing on the customization lever
[00:27:41] >> and this because it's not going to be
[00:27:43] the future is the raw power. It's going
[00:27:44] to be the adaptability that's going to
[00:27:46] win. And this is she's built exactly the
[00:27:48] thing hitting the market that exactly
[00:27:50] what everybody needs right now
[00:27:51] >> and people owning their own models
[00:27:54] working on prem and not giving their you
[00:27:57] know uh their controls to the large
[00:27:59] frontier models. I mean I I I do hope
[00:28:01] this begins the race for powerful
[00:28:03] openweight models in the United States.
[00:28:06] >> Well it's it's worth looking at the raw
[00:28:08] capabilities. So if you believe the eval
[00:28:11] hopefully that thinking machines aka
[00:28:13] thinky has released it's stronger than
[00:28:16] neatron which is great like neatron
[00:28:18] you'll recall from past pod where we
[00:28:20] were discussing Alex karp's rant on
[00:28:23] sovereignty of models neatron is one of
[00:28:26] the incumbents at least on the American
[00:28:28] side for openweight frontier models so
[00:28:30] this this seems to be at least according
[00:28:32] to the eels that think he's released
[00:28:34] stronger than nematron which is great so
[00:28:35] the the west now has a new frontier here
[00:28:38] openweight model. It's weaker than GLM
[00:28:41] 5.2 which is arguably the strongest or
[00:28:44] one of the strongest Chinese openweight
[00:28:46] models and openweight models overall. So
[00:28:48] it's not it's not one of the strongest
[00:28:50] openweight models overall in the world.
[00:28:51] It's obviously weaker than the closed
[00:28:53] weight western frontier models. But I I
[00:28:55] think point one it's great to have
[00:28:58] better stronger western openweight
[00:29:00] models. Point two, I I think it raises
[00:29:03] the question, why has the West been so
[00:29:05] bad at releasing frontier openweight
[00:29:08] models and why has China been so good at
[00:29:10] it? And I think it comes down to you
[00:29:13] show me the incentives and I'll show you
[00:29:15] the outcomes. I think the west has been
[00:29:18] poorly incentivized to release strong
[00:29:20] openweight models because these API
[00:29:22] based frontier models are just such a
[00:29:24] good business model. And we see
[00:29:25] Anthropic about to IPO at a trillion
[00:29:27] dollars and we see OpenAI planning to
[00:29:30] eventually IPO at a trillion dollars.
[00:29:32] And in China, which has been GPU and
[00:29:36] compute deprived on the one hand, and on
[00:29:38] the other hand has the CCP declaring
[00:29:40] 5-year AI plus plans to integrate AI
[00:29:43] into the rest of society. has all of the
[00:29:46] incentives a different incentive
[00:29:48] structure than what the west has. China
[00:29:50] has been much more incentive
[00:29:52] incentivized to make money from the
[00:29:54] integrations between AI upstack on
[00:29:57] applications like robots and downstack
[00:29:59] into the chips than the west has which
[00:30:01] is more horizontally stratified. So to
[00:30:04] the extent that thinky has been
[00:30:06] incentivized in the west due to
[00:30:08] competition and due to just a saturation
[00:30:11] of the frontier by the closed weight
[00:30:12] models into looking a little bit more
[00:30:15] dare I say Chinese in terms of their
[00:30:18] outlook and their incentive structure. I
[00:30:20] think this is very helpful to finally
[00:30:22] have enough competition in the west
[00:30:24] that's creating ways to monetize
[00:30:26] openweight models other than just per
[00:30:29] token sales namely selling them into
[00:30:31] enterprises and what you incentivize.
[00:30:35] >> Two more.
[00:30:36] >> Two more thing. I agree wholeheartedly,
[00:30:38] but also you have to note that OpenAI
[00:30:40] started open source open weight and then
[00:30:43] went closed big revenue and uh Meta also
[00:30:47] was the leader of
[00:30:49] what happened to now it's closed. No,
[00:30:51] they they have a new model out and it's
[00:30:53] it's closed API. I mean, it's exactly
[00:30:55] what Alex said. If you throw your model
[00:30:57] out there as open source, what's your
[00:30:58] revenue model? So I think, you know,
[00:31:00] there's a real possibility that that you
[00:31:02] put a data point on the map with a a
[00:31:04] really solid open- source release that's
[00:31:06] not quite on the frontier. You generate
[00:31:08] news, then you have a data point on the
[00:31:11] line, then you do another, then you do
[00:31:12] another, and then when you have
[00:31:13] something really groundbreaking, then
[00:31:15] you go closed source and you launch an
[00:31:16] API into corporate America. And so that
[00:31:18] that's a wellworn path. So I wouldn't I
[00:31:21] wouldn't say this is necessarily a
[00:31:22] religion at thinking machines that
[00:31:24] they're going to stick with. You know,
[00:31:25] the trend has been the opposite of that
[00:31:27] in the past. Raine what?
[00:31:28] >> They're they're leaning into fine-tuning
[00:31:29] as a service. If fine-tuning as a
[00:31:31] service becomes like something at scale
[00:31:34] revenue generation wise, I think maybe
[00:31:36] this has legs, but who knows?
[00:31:37] >> Yeah, it's a matter of like the business
[00:31:39] of the company, you know, like thinking
[00:31:41] machine can do uh three more iterations
[00:31:44] of their pre-training or post- training
[00:31:46] kind of RL kind of environments and
[00:31:47] benchmarks like those numbers that you
[00:31:49] see on the benchmarks and release like a
[00:31:51] like a better model. But what they what
[00:31:54] what what their business is their
[00:31:55] business is fine-tuning. Like this is
[00:31:57] kind of the place where customization
[00:31:59] has been like something that everything
[00:32:01] like the whole the whole market around
[00:32:03] customization has been very empty. Like
[00:32:05] if you look at the first attempts like
[00:32:06] OpenAI released the OpenAI tuning like
[00:32:08] fine-tuning kind of 3 years ago or
[00:32:10] something it never took off. So they
[00:32:12] took like a really good uh approach on
[00:32:15] designing the base for fine-tuning
[00:32:17] larger instance of the models for
[00:32:19] enterprises because as you see like the
[00:32:21] model layer is not anymore like you know
[00:32:24] like the the the place where you can
[00:32:25] actually extract value especially if
[00:32:27] you're not hitting the maximum frontiers
[00:32:29] you know like uh and even the open
[00:32:31] weight kind of models when we're talking
[00:32:33] about sovereign AI and integration of
[00:32:35] these models into enterprises you need
[00:32:37] to leave some room for let's say
[00:32:39] fine-tuning these models and what they
[00:32:41] have what what I think their business
[00:32:43] strategy around what they're doing and
[00:32:45] this release is genius because they're
[00:32:47] deliberately releasing they're they're
[00:32:49] putting they're leaving some room for
[00:32:52] fine-tuning so that people can come in
[00:32:54] and using their business uh uh their API
[00:32:57] business because that's even generating
[00:32:59] if I think in the order of uh one to two
[00:33:02] orders of magnitude more tokens as well
[00:33:04] you know on the on the on the
[00:33:05] customization side so that would be like
[00:33:07] even printing money at a larger speed
[00:33:09] like in the in the in
[00:33:11] absolute best case right
[00:33:14] business entry
[00:33:15] >> to to add to Raine's point I I think the
[00:33:17] situation maybe is is even more extreme
[00:33:20] so a couple points one OpenAI was the
[00:33:22] first to my knowledge to launch
[00:33:24] reinforcement fine-tuning RF as a
[00:33:26] service and no one used it uh the the
[00:33:29] whole tech world everyone I speak with
[00:33:31] no one used it uh it was barely
[00:33:33] advertised by OpenAI second point open
[00:33:36] AAI shut off their fine-tuning API open
[00:33:39] AI was one of the earliest if not the
[00:33:41] first to offer fine-tuning as a service.
[00:33:44] >> We used it all the time. It was it was
[00:33:46] incredibly cool for its time
[00:33:48] >> and they they've just they recently in
[00:33:50] the past few months they announced it it
[00:33:52] has either already been wound down or
[00:33:54] about to be wound down. The fine-tuning
[00:33:55] API has been shut off. So that I mean it
[00:33:57] raises the question is is thinking
[00:33:59] machines bet like explicitly contrarian?
[00:34:02] Are they thinking that we're going to
[00:34:04] end up in a world where reinforcement
[00:34:06] fine-tuning and RL fine-tuning in in
[00:34:09] general and fine-tuning like that's the
[00:34:11] paradigm? They may be right, they may be
[00:34:13] wrong. There there's an alternative
[00:34:15] vision where RF just dies. Uh and we the
[00:34:19] the baseline models are so generalist in
[00:34:22] terms of their capabilities that all you
[00:34:24] need is prompt engineering and there's
[00:34:26] no need for RF at all. Alex, you talked
[00:34:29] about the Alex Karp rant, right? Yes,
[00:34:32] the result of that was um don't allow
[00:34:36] don't use a model that is has all of
[00:34:39] your data open to your competition. And
[00:34:42] I do think we're going to see a real
[00:34:43] push over the next months to years where
[00:34:46] people want to use fine-tuned opate
[00:34:49] models that they own on their own
[00:34:51] hardware in their you know onrem and if
[00:34:54] that's the case then the question is who
[00:34:56] are they going to use which models are
[00:34:57] they going to use are you know and is
[00:34:59] the US going to start to regulate
[00:35:01] against Chinese openweight models in
[00:35:04] which case a dominant US openweight
[00:35:06] model is going to take is going to have
[00:35:08] an advantage and so is that the bet
[00:35:10] mirror is going after um you know we're
[00:35:13] going to probably see my guess is Google
[00:35:15] step up in this area as well very
[00:35:17] shortly you know take Gemma 4 to the
[00:35:18] next level and hopefully we get some you
[00:35:21] know two or three major in the same way
[00:35:23] we have a closed you know the closed
[00:35:25] model Frontier Labs competing and
[00:35:27] dominating in the US hopefully we'll see
[00:35:29] that competition give birth to you know
[00:35:32] very strong opio models
[00:35:33] >> it just to build on something you know
[00:35:35] Alex and Verine were saying you know if
[00:35:36] I compare today to a month ago you know
[00:35:38] we've been fine-tuning Quen all week and
[00:35:40] and the idea of using Inkling sounds
[00:35:42] really compelling to me and you know our
[00:35:44] companies are using liquid as well. A
[00:35:46] month ago to fine-tune these things with
[00:35:48] some huge engineering effort that
[00:35:50] required AI experts. Now with Fable 5,
[00:35:53] it's just a prompt.
[00:35:55] >> So let's back up one second. Dave,
[00:35:57] explain what fine-tuning a model is for
[00:35:59] those who don't know.
[00:35:59] >> Well, you know, back when GPT2 and GPT3
[00:36:01] came out, you could actually very easily
[00:36:03] fine-tune by uploading text right into a
[00:36:05] window and say, "Look, you're pretty
[00:36:07] smart, but you don't know anything about
[00:36:08] my laundromat." you know like what hours
[00:36:11] were open now who our employees are
[00:36:13] entire payroll let me dump that data in
[00:36:15] too and retrain the model with that
[00:36:18] knowledge and if you didn't do that you
[00:36:20] couldn't do anything useful because it
[00:36:22] didn't have this holistic I know
[00:36:23] everything capability back then so
[00:36:25] without the fine-tuning it was
[00:36:26] borderline useless to to use the models
[00:36:29] then the models got so smart that
[00:36:31] they're pre-trained with now 45 trillion
[00:36:33] tokens which is basically every word
[00:36:36] ever written by humanity has already
[00:36:38] been trained into the model so people
[00:36:39] tend to use them in their vanilla form
[00:36:41] today and just say here write this code
[00:36:43] for me or here drive this car for me
[00:36:45] because it's already in there but then
[00:36:47] when you get into biotech research or
[00:36:49] you get into aeronautical or the
[00:36:50] Mercedes you know like Ramina is doing
[00:36:52] there's a whole bunch of proprietary
[00:36:54] company knowledge that actually isn't in
[00:36:56] the model so right now we dump it into
[00:36:58] the prompt field and say okay here it is
[00:37:00] in prompt form but that's hugely
[00:37:02] inefficient
[00:37:02] >> and you dump it into open AI and you
[00:37:05] dump it into anthropics uh you know
[00:37:07] model which now makes it accessible to
[00:37:10] everybody else as well. I mean,
[00:37:11] >> yeah. Yeah. I mean, Sam Sam and Dario
[00:37:13] can see everything. All your proprietary
[00:37:15] information, they're looking right at
[00:37:16] it. That's what Alex Karp was ranting
[00:37:18] about when he said, "They're stealing
[00:37:19] your weights. They're stealing your
[00:37:20] alpha." What he really means is they're
[00:37:22] looking at your most proprietary your
[00:37:25] company payroll, your company's secrets,
[00:37:26] your your your chemical research. Like,
[00:37:28] it's all going right over the wire to
[00:37:31] these foundation labs. Is that what you
[00:37:33] want? And of course, you know, for
[00:37:34] defense and for banking, of course,
[00:37:36] that's not what you want. And so now the
[00:37:38] ability to bring the model in-house and
[00:37:40] fine-tune it with your local data is a
[00:37:42] huge is a huge unlock. But the the
[00:37:44] higher level point is now the
[00:37:46] technological capability to do it
[00:37:47] relatively easily is hugely better today
[00:37:50] than it was a month ago. So I think
[00:37:52] mirror may be on to something here.
[00:37:53] We've hit a real tipping point and Alex
[00:37:55] Carp I think is right about it too.
[00:37:57] >> I think there's two things that also
[00:37:59] that that I saw that were really
[00:38:00] interesting here. One is a very big
[00:38:02] context window like a million tokens
[00:38:04] because that means you can do a lot with
[00:38:05] it. And the second is multimodality.
[00:38:07] >> Yes.
[00:38:08] >> And so this is aiming squarely at
[00:38:10] organizational use. This fits perfectly
[00:38:13] into the onrem proprietary data um model
[00:38:17] where you you take your data customize
[00:38:20] and fine-tune as you said Dave and that
[00:38:22] will be the future. A couple of historic
[00:38:25] notes again for for those uh
[00:38:27] definitionally uh not tracking the the
[00:38:30] full sorted history of fine-tuning. So
[00:38:31] fine-tuning is is this notion that you
[00:38:34] you start with a model. Model consists
[00:38:36] of billions usually these days of
[00:38:39] weights of parameters that are frozen.
[00:38:41] And if you want to customize the model
[00:38:44] for your purposes, you can conduct a
[00:38:46] so-called fine-tuning process that
[00:38:48] usually makes relatively small, hence
[00:38:51] the fine changes to some usually a a
[00:38:54] tiny subset of the weights in order to
[00:38:56] customize the model for your end
[00:38:58] application. That's fine tuning. There's
[00:39:00] actually now decent literature out there
[00:39:02] that suggests that conventional
[00:39:04] finetuning like supervised fine-tuning
[00:39:05] Laura style low rank uh adapter uh one
[00:39:09] class of fine-tuning architectures
[00:39:11] doesn't result in increasing the
[00:39:13] capabilities of your model at all. And
[00:39:14] at most it it results in like a style
[00:39:17] transfer like you could fine-tune a
[00:39:19] language model to only speak in
[00:39:20] Shakespearean verse for example that's
[00:39:23] not really increasing its capabilities
[00:39:26] >> or only be an accelerando flavor output.
[00:39:29] [laughter]
[00:39:29] Well, uh, no comment. Uh, but but I I I
[00:39:34] I would say historically fine-tuning
[00:39:36] didn't have a history of increasing
[00:39:38] capabilities. Then along came
[00:39:40] reinforcement fine-tuning where for the
[00:39:42] first time via large amounts of
[00:39:44] synthetic data uh and giving access to
[00:39:47] all of the weights and and not just like
[00:39:49] a subset that's convenient to train. we
[00:39:52] gained the ability and you know
[00:39:53] fine-tuning post- training there there's
[00:39:55] a there's a gray area between you know
[00:39:57] what what's the distinction between them
[00:39:59] but with reinforcement fine-tuning RFT
[00:40:02] uh and the the release of the first
[00:40:04] generation of reasoning models we saw
[00:40:05] fine-tuning actually start to increase
[00:40:08] the capabilities of the models now the
[00:40:09] problem with thinking machines business
[00:40:12] model as as I understand it is it's a
[00:40:14] bet on the flavor of the moment that
[00:40:17] reinforcement fine-tuning is going to be
[00:40:19] a paradigm in the future right now
[00:40:21] obviously the paradigm of the moment
[00:40:23] that you could take an off-the-shelf
[00:40:25] model and RFT your way to customization
[00:40:28] with proprietary data and proprietary
[00:40:31] environments and other things that that
[00:40:32] seems to work pretty well at the moment.
[00:40:34] But in some sense, if that is like the
[00:40:37] permanent long-term plan of thinking
[00:40:38] machines, it's fundamentally a bet that
[00:40:41] we're not going to ever move beyond the
[00:40:44] reinforcement fine-tuning paradigm,
[00:40:46] which I think is probably wrong. I I
[00:40:48] think probably RFT is the scaling of the
[00:40:51] moment, but in the future, I can totally
[00:40:54] imagine a generalistbased model that is
[00:40:56] just so generally capable that it
[00:40:59] doesn't actually benefit from any
[00:41:01] further reinforcement finetuning on any
[00:41:03] internal data sets and we tend towards
[00:41:05] ASI. Let me bring up another key point
[00:41:07] here on this story which is uh in the in
[00:41:10] the context which is it's great to see a
[00:41:13] woman CEO in the AI frontier lab area. I
[00:41:17] think women are distinctly missing from
[00:41:20] the entire AI industry, right? We have
[00:41:23] Lisa Sue from AMD, but very few in
[00:41:27] leadership positions. And I I think
[00:41:29] that's an important point. I'm not sure
[00:41:31] who else you know, Alex, are you seeing
[00:41:35] >> Daniela Roose right where
[00:41:38] Fe is also
[00:41:40] >> and Fay Lee. Yeah. But again, we're
[00:41:42] talking about what singledigit percent
[00:41:44] of the AI industry is is women. Uh and
[00:41:47] we need more. So, a call out to every
[00:41:49] all the women out there, please jump
[00:41:51] into this industry. We need uh
[00:41:53] >> we we we need more balanced thinking.
[00:41:55] >> Yeah, for sure. I mean, I I I do think
[00:41:58] that's an important point to pull out
[00:42:00] here.
[00:42:00] >> This episode is brought to you by
[00:42:02] Blitzy, autonomous software development
[00:42:04] with infinite code context. Blitzy uses
[00:42:08] thousands of specialized AI agents that
[00:42:11] think for hours to understand
[00:42:13] enterprisecale code bases with millions
[00:42:15] of lines of code. Engineers [music]
[00:42:18] start every development sprint with the
[00:42:20] Blitzy platform, bringing in their
[00:42:22] development requirements. The Blitzy
[00:42:24] platform provides a plan, then generates
[00:42:27] and pre-ompiles code for each task.
[00:42:29] [music] Blitzy delivers 80% or more of
[00:42:32] the development work autonomously while
[00:42:34] providing a guide for the [music] final
[00:42:36] 20% of human development work required
[00:42:38] to complete the sprint. Enterprises are
[00:42:41] achieving a 5x engineering velocity
[00:42:44] increase when [music] incorporating
[00:42:45] Blitzy as their preIDE development tool,
[00:42:48] pairing it with their coding co-pilot of
[00:42:50] choice to bring an AI native SDLC into
[00:42:54] their org. Ready to 5x your engineering
[00:42:56] velocity? Visit blitzy.com to schedule a
[00:42:59] demo and start building with Blitzy
[00:43:01] today. [music]
[00:43:04] >> All right. Um let's move on to our our
[00:43:07] next story here. Uh
[00:43:11] it is uh a a fun one. Uh Alex, I was
[00:43:15] walking in the streets of uh where was I
[00:43:18] yesterday? Zurich. And I saw this come
[00:43:20] up and I said, "Hey, let's talk about
[00:43:22] this tomorrow." And and you said yes. Uh
[00:43:25] so here is the uh the story we've talked
[00:43:28] about the holy grail of AI is recursive
[00:43:31] of self-improvement. It's sort of like
[00:43:32] the holy grail of the launch industry
[00:43:34] was reusable rockets. Um this you know
[00:43:38] RSI is a holy grail for AI. It's the
[00:43:40] idea that AI makes itself smarter. Uh
[00:43:44] and then you use that smarter AI to
[00:43:46] create the next generation of AI. It's
[00:43:49] sort of the theoretical engine behind
[00:43:51] the hard takeoff scenario of the
[00:43:52] singularity. So this week, a startup
[00:43:55] called Wo AI uh with researcher Zeng Yao
[00:43:59] Jang uh published what they call
[00:44:01] experimental evidence for the first
[00:44:04] recursive self-improvement. Whether
[00:44:05] they're first or not, Alex, I'll ask you
[00:44:07] about that. They built a system called
[00:44:09] AIdriven exploration squared, aid
[00:44:12] squared, with an outer AI agent whose
[00:44:15] job is to rewrite the code and the
[00:44:17] research strategy for an inner AI agent.
[00:44:20] In their experiment, they claim that 8
[00:44:22] days of machine self-improvement beat
[00:44:25] two years of expert human effort. So,
[00:44:28] Alex, what do you make about this? Is it
[00:44:30] the first uh is it significant?
[00:44:33] Very significant. Highly unlikely that
[00:44:35] this is anywhere close to first. So, so
[00:44:37] a few bits of additional context. One,
[00:44:39] uh this is actually this WICO is a
[00:44:41] startup that's based in London.
[00:44:43] Interestingly, it's not based in the US,
[00:44:45] but still western sphere. So, great. Uh
[00:44:48] so this is a startup built by a bunch of
[00:44:49] as I understand it uh UC London grads.
[00:44:53] Secondly a few points that I love about
[00:44:56] this story. One it's an example of
[00:44:59] defensive co-scaling which so to to the
[00:45:02] extent we talk about alignment AI
[00:45:04] alignment on the pod and I'm I'm always
[00:45:06] banging the the drum of defensive
[00:45:08] co-scaling as the ultimate alignment
[00:45:10] strategy.
[00:45:11] >> What does that mean? So defensive
[00:45:13] co-scaling is the idea uh borrowed by
[00:45:16] analogy from human alignment
[00:45:18] human-touman alignment that rather than
[00:45:20] hoping for call it the great man theory
[00:45:22] of alignment that someone somewhere is
[00:45:24] going to discover the perfect algorithm
[00:45:26] for keeping AI safe instead the solution
[00:45:30] for AI safety is AI policing AI in
[00:45:33] proportion the way we keep cities safe
[00:45:35] is we have police forces police forces
[00:45:37] that scale according to some scaling law
[00:45:40] in proportion to the population of the
[00:45:42] city. So, so we have the good guys and
[00:45:44] the bad guys and the the way we keep the
[00:45:46] bad guys in check is with making sure
[00:45:48] that we have enough good guys to police
[00:45:50] them. Same idea with AI. The way we keep
[00:45:52] AI aligned with humanity, a key way is
[00:45:55] we make sure that we have enough good
[00:45:57] AIs policing any bad AIs in terms of raw
[00:46:01] capabilities that they defensively
[00:46:03] co-scale. So what one of the things I I
[00:46:06] love about this uh aid two story is that
[00:46:10] the outer loop so so the the way this
[00:46:12] recursive self-improvement process
[00:46:14] worked was they had an outer loop and an
[00:46:16] inner loop. The outer loop was tasked
[00:46:18] with the with improving the inner loop.
[00:46:21] The inner loop was tasked with improving
[00:46:23] software development processes in
[00:46:24] general according to some benchmark. The
[00:46:27] outer loop discovered and both both
[00:46:29] powered by the same underlying AIdriven
[00:46:31] exploration process. At least initially
[00:46:34] the outer loop and AI discovered that it
[00:46:37] was able to achieve and this was an
[00:46:39] emergent property better results from
[00:46:41] the inner loop by keeping by preventing
[00:46:44] the inner loop from cheating and reward
[00:46:46] hacking. And so so in some sense the
[00:46:49] outer loop is defensively co-scaling
[00:46:51] with and policing the inner loop all the
[00:46:54] while this is reaching toward greater
[00:46:57] and greater capabilities. And I I think
[00:46:59] this is also parenthetically an example
[00:47:02] of a case you know all of those who
[00:47:04] would say okay like we need to pause AI
[00:47:07] capabilities and throw all of our
[00:47:08] resources to AI alignment until
[00:47:11] something preposterous in my mind like
[00:47:13] 2040 like stop all stop the race to
[00:47:15] super intelligence. stop it all. Focus
[00:47:18] on focus the next 14 years on alignment
[00:47:20] research. It's going to backfire because
[00:47:22] every alignment capability, I would
[00:47:24] argue, is actually just cap is is
[00:47:27] capability, new capability in in sort of
[00:47:30] in disguise in a trench coat. Same idea
[00:47:33] here.
[00:47:34] >> We need stronger white hats to police
[00:47:36] the black hats.
[00:47:37] >> Yes. But the the beauty Yes, agree with
[00:47:40] that. And also the beauty is the the
[00:47:43] so-called white hats were emerging
[00:47:45] organically uh on their own just from
[00:47:48] the outer loop policing the inner loop
[00:47:50] towards greater capabilities. That's
[00:47:51] first point. Second point quickly the
[00:47:54] same startup Wo has published a scale of
[00:47:58] recursive self-improvement which is I I
[00:48:00] think something the world has been
[00:48:02] missing. So we have like for autonomous
[00:48:04] cars we have uh the um the society of
[00:48:07] automotive engineers has their like five
[00:48:09] levels of autonomy for autonomous
[00:48:11] vehicles. They've published a scale for
[00:48:13] recursive self-improvement that that
[00:48:14] goes from zero to three. Zero is
[00:48:16] delegation where the AIs are slower than
[00:48:19] human R&D. Level one net positive where
[00:48:22] the AIs beat human a R&D at the same
[00:48:24] cost. Level two they call ignition where
[00:48:27] the improvers are better basically a
[00:48:30] better improver. and level three
[00:48:31] inflection self- acceleration with a
[00:48:33] fixed budget. And the claim here is that
[00:48:36] they're touching just starting to touch
[00:48:38] on ignition. They call it level one
[00:48:40] rather than level two. But the claim
[00:48:41] here is like this is a pre-ignition
[00:48:44] event, which I think is super exciting.
[00:48:45] >> So they they rate themselves as a level
[00:48:47] one here.
[00:48:48] >> Yeah, they rate themselves as level one,
[00:48:50] but reading between the lines, they're
[00:48:51] like this is like sparks of ignition,
[00:48:53] literally and figuratively.
[00:48:56] >> Okay, so maybe I can maybe I can jump in
[00:48:58] and and say a couple words. I'm not as
[00:49:00] excited as Alex is like on the on the
[00:49:02] topic and and I see I see this is an
[00:49:04] impressive engineering kind of work that
[00:49:06] has been done just to tell you a little
[00:49:08] bit about like how the foundation model
[00:49:10] labs are operating all foundation model
[00:49:13] labs since the beginning of let's say
[00:49:15] like four years ago or let's say 5 years
[00:49:17] ago everybody has been thinking about
[00:49:19] recursive self-improvement and for us
[00:49:21] the definition of recursive
[00:49:22] self-improvement is not the engineering
[00:49:25] and prompt engineering of in inner loop
[00:49:27] and outer loop to really get get some
[00:49:30] code patches like changing because that
[00:49:32] gives you the assumption that every
[00:49:34] single AI model that you're using in
[00:49:37] your pipeline is already like uh uh you
[00:49:40] know like it's already defined and it's
[00:49:42] already fixed with a certain type of
[00:49:43] capabilities which is actually the case
[00:49:46] in the whole pipeline that they actually
[00:49:48] like design there's no weight changes in
[00:49:50] the neural networks so that means like
[00:49:52] the AIs that are actually getting used
[00:49:55] right now there's no uh kind of
[00:49:57] improvement of the core competences and
[00:50:00] even behavior of the models they're
[00:50:03] always like in the system prompt of the
[00:50:05] of the models like changes in the system
[00:50:07] problem because I will give you like
[00:50:10] fundamental reasons why this is actually
[00:50:12] limiting because if you just run the
[00:50:14] like how I want to tell you how hard of
[00:50:16] a problem is recursive self-improvement
[00:50:18] for us recursive self-improvement means
[00:50:19] that you have an AI system or an army of
[00:50:22] AI systems that they can also like
[00:50:25] retune themselves they can you know
[00:50:27] adapt very similar to how humans do it.
[00:50:30] You know, if you if you think about it,
[00:50:31] the core competences of these models
[00:50:33] that we have right now, they're they're
[00:50:35] they're fixed weight models and and the
[00:50:36] capabilities are within a certain kind
[00:50:38] of threshold. And the frameworks that
[00:50:40] they actually like designed, it's not um
[00:50:44] it's a very nice early stage of show
[00:50:46] showcasing an engineering pipeline that
[00:50:49] can improve work, which is actually very
[00:50:51] very important and very nice. But I
[00:50:53] wouldn't I wouldn't go so much to say
[00:50:55] like this is like the first breakthrough
[00:50:57] in in in the entire AI industry or
[00:51:00] something like in fact like about three
[00:51:01] years ago we published a paper ourselves
[00:51:03] like we talked we talked about automatic
[00:51:05] design of model architectures you know
[00:51:07] like you know as liquid AI we didn't
[00:51:09] want to put like a bet on a single
[00:51:10] architecture we have basically designed
[00:51:13] self-improve like meta AI systems that
[00:51:16] are actually defining their
[00:51:17] architectures and then going through
[00:51:19] scaling laws for various types of
[00:51:21] architectures and then trying to figure
[00:51:22] it out based on the criteria that you
[00:51:24] define what should be the final model
[00:51:26] and then right now at our company all
[00:51:29] the process of training foundation
[00:51:31] models and really like retuning the
[00:51:33] weights of the system are are getting
[00:51:35] automated. So we are talking about AIS
[00:51:38] or designing AIS. So that's that's what
[00:51:40] I what I would be like calling it like
[00:51:42] the holy grail where you can actually do
[00:51:46] automatic kind of tuning of a model. And
[00:51:48] I'll tell you with the frameworks that
[00:51:50] they kind of uh uh structured, it would
[00:51:52] be extremely exhausted computationally
[00:51:54] intractable to actually performing this
[00:51:56] this job training an AI model training
[00:51:59] like being able to customizing an AI
[00:52:01] model and training an AI model on a
[00:52:04] meaningful number of tokens for
[00:52:06] adaptation or let's say like the core
[00:52:08] competence of the model changing core
[00:52:09] architecture of the model changing core
[00:52:11] algorith learning algorithm itself
[00:52:13] changing all of those matters adds more
[00:52:15] and more complexity on the on the
[00:52:17] situation. I can give you also like one
[00:52:19] numerical kind of example of this.
[00:52:21] There's a scaling laws called chinchilla
[00:52:23] law. You know like chinchilla is like
[00:52:25] the scaling laws of neural networks and
[00:52:27] know like it is unproven like we have
[00:52:28] actually unproven but still like it's it
[00:52:30] gives you a good sense. It says when
[00:52:32] you're training a neural network let's
[00:52:34] say of a given size. If the size of the
[00:52:37] model is two billion parameters, you
[00:52:39] need 20 times of more tokens number of
[00:52:43] tokens to train these models so that you
[00:52:45] have you have compute optimality given a
[00:52:48] compute budget. How many tokens do you
[00:52:50] have to train a model so that you have
[00:52:52] like a general purpose kind of system?
[00:52:54] So that ratio is like 20. And then when
[00:52:56] you actually do the math with the
[00:52:58] frameworks that they have, if they want
[00:53:00] to like let's say you launch this
[00:53:02] framework on retuning an AI model to
[00:53:05] recursively self-improve with this uh
[00:53:08] framework that is getting introduced, it
[00:53:10] takes us 350 years to really uh uh
[00:53:14] fine-tune a two billion parameter model
[00:53:16] with this framework. So there are so so
[00:53:19] so there's there's a lot of there's a
[00:53:22] lot of u computational complexity goes
[00:53:25] into nested learning systems nest metal
[00:53:28] learning systems you know like these are
[00:53:29] the kind of problems that the last four
[00:53:31] years of like at least at my company
[00:53:33] like we have been heavily focused on and
[00:53:35] I know friends at openai and entropic
[00:53:37] has been like focusing on this recursive
[00:53:39] self-improvement and entropic has been
[00:53:41] having a lead on all of these things
[00:53:43] because they thought about this before
[00:53:45] every everybody else that's that's what
[00:53:47] can put out there. Dave,
[00:53:49] >> yeah, brilliantly said. And actually,
[00:53:51] just just so the audience can get the
[00:53:53] analogy there, when a baby is born and
[00:53:56] then learns, you know, that happens over
[00:53:58] about a 20 year time scale and after 20
[00:54:00] years, you've got an adult that's
[00:54:01] capable. Recursive self-improvement is
[00:54:04] like evolution on top of that where
[00:54:06] you're changing the DNA and creating a
[00:54:09] new
[00:54:09] >> You're changing the neuronal structure
[00:54:11] of the brain along the way.
[00:54:12] >> Exactly. So, so that happens over, you
[00:54:14] know, about a 10 millionyear time scale.
[00:54:16] So you go from 10 years to 10 million
[00:54:18] years to go from learning to recursive
[00:54:20] self-improvement or recursive evolution.
[00:54:23] And so the big foundation model labs
[00:54:25] like Ramine said are all doing it. It's
[00:54:27] the most important moment in human
[00:54:29] history. But there's no, you know,
[00:54:31] little guy out there that's going to
[00:54:32] come up and say, "Hey, I've got a
[00:54:33] breakthrough in recursive
[00:54:34] self-improvement. My Mac Mini suddenly
[00:54:36] became conscious and now it's improving
[00:54:38] itself." Just computationally it doesn't
[00:54:40] even come close to fitting. So it's
[00:54:42] happening, but it's happening with big
[00:54:44] compute and big budgets. uh and and you
[00:54:46] know there's a lot of room for
[00:54:47] efficiency improvement a lot of
[00:54:48] breakthroughs will happen but it's not
[00:54:50] going to just pop up on some you know
[00:54:52] >> you know there's a lot of fe there's a
[00:54:53] lot of fear just to call it out that you
[00:54:55] know recursive self-improvement leads to
[00:54:57] AIS that take off a hard you know we've
[00:54:59] discussed the hard takeoff and without
[00:55:01] our understanding of that black box um I
[00:55:05] I guess the two questions need to be
[00:55:07] asked is do is there a concern that
[00:55:10] recursive self-improvement once we hit
[00:55:12] level two level three by that definition
[00:55:15] um runs away in a way that um uh causes
[00:55:20] an uncontrolled uh AI that is misaligned
[00:55:24] with humans. And the second question I
[00:55:26] have is when do you think we'll see
[00:55:28] this? When do you think we'll actually
[00:55:30] see recursive self-improvement hit? Is
[00:55:32] ASI going to be that point uh or is it
[00:55:35] post AGI whatever that means? See, I say
[00:55:38] that for you.
[00:55:40] >> I'll let you answer that exist. I've got
[00:55:42] I've got several comments though but
[00:55:44] Ramine go ahead what do you think is
[00:55:46] happening
[00:55:47] >> look the thing is I can tell you like
[00:55:48] the early evidence of recursive self by
[00:55:50] the way recursive self-improvement is
[00:55:52] not related to one single agent it's a
[00:55:55] social kind of character as well you can
[00:55:57] imagine like you know you have societies
[00:55:59] of agents so this defining kind of
[00:56:01] structure for society of agents itself
[00:56:04] self-improving these are the places
[00:56:06] where actually mythos level kind of
[00:56:07] class of models like I hate this analogy
[00:56:09] but still like let's say mythos level
[00:56:11] kind of class because everybody body
[00:56:12] like heard about mythos and then what I
[00:56:14] would say is that like the cyber
[00:56:15] security kind of uh um um uh threads
[00:56:19] that we are seeing like coming out of
[00:56:21] these type of pipelines of recursive
[00:56:23] self-improvement
[00:56:25] they're real you know like like the
[00:56:27] reason why I'm actually I I've always
[00:56:28] been like you know like pro open source
[00:56:30] and I want to open source technology all
[00:56:32] the time like we are doing it all the
[00:56:33] time like every single release of our
[00:56:35] models is open source our science has
[00:56:37] been always open source I believe
[00:56:38] science has to be open source and I I
[00:56:41] see the value of open source going
[00:56:43] forward. But some of these concerns that
[00:56:45] uh Peter you you brought up, they're
[00:56:47] they're very real, you know, like the
[00:56:49] cyber security kind of aspect of things.
[00:56:51] That's why I feel like like a degree of
[00:56:53] at least uh enterprises themselves
[00:56:56] having some degree of kind of
[00:56:57] self-control like about like how before
[00:57:00] mass release of their uh their models
[00:57:03] there there has to be always a certain
[00:57:06] degree of selfch check and I think
[00:57:07] entropic took it very seriously. The
[00:57:10] reason behind is because they're seeing
[00:57:12] the impact of recursive
[00:57:13] self-improvement. So I know I know this
[00:57:16] for for a fact because I I know what is
[00:57:18] happening like in in seeing it at a
[00:57:20] smaller scale. You know, you can do
[00:57:22] reward hacking, but you can also like,
[00:57:24] you know, like avoid reward reward
[00:57:26] hacking like to to the certain extreme
[00:57:29] and push a model to actually discover
[00:57:31] some stuff that you know like are are
[00:57:33] out of norm, you know, and and we we see
[00:57:35] that on a small models like at a at a
[00:57:37] certain capabilities certain
[00:57:39] capabilities emerging and then I can
[00:57:41] only imagine like what kind of
[00:57:43] capabilities could emerge from let's say
[00:57:45] larger and larger systems thrown more
[00:57:47] and more compute at them. When do you
[00:57:49] when do you think we you know when do we
[00:57:51] have a pod
[00:57:52] >> timelines remain timelines?
[00:57:54] >> Yes. When do you have a pod that said
[00:57:55] yes this is recursive self-improvement
[00:57:58] because while you know while the data
[00:58:00] released by WICO is interesting uh it's
[00:58:02] their own self-reported data. It hasn't
[00:58:04] been confirmed by anybody else yet and
[00:58:06] you know there is a you know debate
[00:58:09] about whether it really is or is not
[00:58:11] real recursive self-improvement. When do
[00:58:13] you think we actually, you know, you
[00:58:16] give the trophy out to somebody? Is it a
[00:58:19] year, 3 years, 5 years?
[00:58:21] >> Yeah. I mean, I I'm telling you that
[00:58:23] that so I I would say like you're going
[00:58:25] to see like unbelievably kind of models
[00:58:27] like probably in the next 2 years or so,
[00:58:28] you know, like models that are like
[00:58:30] going above our our understanding even
[00:58:33] like that that's that's what what I
[00:58:34] would imagine to get. The reason behind
[00:58:36] it is because the time to developing the
[00:58:39] next generation of the models is
[00:58:40] reducing especially if the compute grows
[00:58:42] like at foundation model companies like
[00:58:44] with the rate that we are seeing right
[00:58:45] now and if there is no like let's say
[00:58:48] another chip shortage or memory shortage
[00:58:50] like on compute or anything like around
[00:58:51] the globe and they have access to
[00:58:53] abundant compute we are going to see
[00:58:56] those things like happening faster and
[00:58:57] faster. Now in terms of model
[00:58:59] development there's a concept that we
[00:59:01] have we call it depths of customization.
[00:59:04] So everything at a foundation model lab
[00:59:06] when you're customizing a model when
[00:59:08] you're building something that is like
[00:59:10] better than its previous generation we
[00:59:13] always categorize it with depths of
[00:59:15] customization. The place where recursive
[00:59:17] self-improvement today is really good at
[00:59:20] is prompt engineering changing editing
[00:59:22] code like in engineering kind of tasks
[00:59:25] that you've seen like some elements of
[00:59:26] these things like at a very very
[00:59:28] superficial level let's say make my
[00:59:30] model run fastest like doing kernel
[00:59:32] engineering basically you know make my
[00:59:34] model run faster that's what I call like
[00:59:37] the shallowest level of kind of
[00:59:38] customization where you have Python code
[00:59:40] and then you're kind of adopting that
[00:59:42] Python code to really run or maybe like
[00:59:44] even lower level programs that you have
[00:59:46] like on a kernel level to optimize like
[00:59:48] let's say inference speed you know
[00:59:50] that's something that I think with when
[00:59:52] when they released Fable 5 they they
[00:59:55] shared like and tropic actually shared
[00:59:56] that this was one of the tests that they
[00:59:58] have been performing you know but they
[01:00:00] they don't share like the next level
[01:00:02] depths of customization the next level
[01:00:04] depths of customization is that can a
[01:00:06] model fine-tune a small language model
[01:00:09] to a production grade capability or a
[01:00:12] smaller version of itself to a certain
[01:00:14] capability
[01:00:15] today like fav 5 can actually you can
[01:00:18] push it to actually get to some degree
[01:00:21] of kind of customization with some
[01:00:23] >> performance optim performance
[01:00:24] optimization
[01:00:24] >> performance optimization of the model
[01:00:26] but by fine-tuning then the latest holy
[01:00:28] grail which is like the craziest one
[01:00:30] which would be pre-training right can a
[01:00:32] language model pre-train the next
[01:00:34] generation of their own that's why they
[01:00:35] hired karpathy because Andre was talking
[01:00:38] about like nano GPT style kind of uh
[01:00:41] fine-tuning you know andre like joined
[01:00:43] entropic and now he's working on
[01:00:45] pre-training automation like basically
[01:00:47] automation of automation. So which is
[01:00:49] which is a very very important kind of
[01:00:51] element that we don't have yet because
[01:00:53] the scale of these problems goes beyond
[01:00:56] human imagination in terms of the scale
[01:00:58] of compute that
[01:01:00] >> you're jumping
[01:01:01] >> I've got I've got for me this is by far
[01:01:03] the most important uh story or slide
[01:01:06] we're going to cover today. Um I'm
[01:01:08] beyond excited for a couple of reasons.
[01:01:11] uh the you know I I'm not really focused
[01:01:14] on the self-awareness or the loop that
[01:01:16] will go there but this is self
[01:01:18] accelerating it's accelerating
[01:01:19] experimentation right because the system
[01:01:21] doesn't need it's it's improving the
[01:01:24] process by which it searches and
[01:01:25] evaluates and selects improvements and
[01:01:27] the innovation loop begins to compound
[01:01:30] that for me is the key why because this
[01:01:33] this whole thing we've been doing called
[01:01:35] the organizational singularity relies on
[01:01:37] one thing which is can you get to
[01:01:40] recursive self-improvement at the
[01:01:41] workflow level. Here we're talking about
[01:01:43] the model and we're talking about like
[01:01:45] can you so but you don't need that
[01:01:47] level. The bar can be much much lower to
[01:01:49] improve invoice uh uh approval at a
[01:01:52] company right that's a very low bar to
[01:01:54] improve that process. So this is the
[01:01:56] first glimpse of the organizational
[01:01:58] singularity. It's happening at the
[01:02:00] research level, but the because AI is
[01:02:02] not just doing tasks in a in a workflow.
[01:02:04] It's redesigning the workflow uh that
[01:02:06] makes it better for doing future tasks,
[01:02:08] right? And so this is proof now for the
[01:02:11] whole thesis we've had. Um we predicted
[01:02:14] this, but it's great to see it actually
[01:02:17] happen because now I can kind of tick
[01:02:19] that box off and go this is there cuz
[01:02:21] now you have meta improvement. And I
[01:02:23] think Dave's analogy of the baby
[01:02:25] changing the DNA is fantastic. That's
[01:02:27] such a great visual around this. What
[01:02:29] the hell does it become over time? Um,
[01:02:33] really really I'm beyond excited about
[01:02:35] this.
[01:02:35] >> I've got to move us along. There's a lot
[01:02:36] that happened this week. Our next story
[01:02:38] here is the Malaysian prime minister,
[01:02:40] uh, Anoir Ibrahim has is preparing to
[01:02:43] debut an AI generated digital double of
[01:02:46] himself trained to sound like him for
[01:02:48] public communications and outreach. So,
[01:02:51] uh, this is one of the most prominent
[01:02:53] cases yet of a sitting head of
[01:02:54] government officially adopting an AI
[01:02:56] likeness as a communications tool. Uh,
[01:02:59] not a deep fake Biden adversary, but a
[01:03:02] sanctioned official AI clone of a
[01:03:04] national leader. Uh, we've seen this
[01:03:06] before, Selene. we've talked about in
[01:03:07] the past where Albania in 2025 uh
[01:03:10] announced uh Dileia uh an AI avatar that
[01:03:14] was formally appointed the minister of
[01:03:16] state for artificial intelligence and
[01:03:18] following a presidential decree became
[01:03:20] the first AI system in the world named
[01:03:23] at a cabinet level role. Uh so one
[01:03:27] leader uh in this case prime minister of
[01:03:29] Malaysia can personally address millions
[01:03:31] in their own languages. It's worth
[01:03:32] noting that Malaysia has 135 spoken
[01:03:36] languages. So, um it's a big deal,
[01:03:39] especially in in a nation like that.
[01:03:41] Sim, I'm going to go to you first on
[01:03:43] this one. Um we've been talking about
[01:03:44] this for a while.
[01:03:46] >> Yeah, I I met the um the former prime
[01:03:49] minister when I was there helping them
[01:03:51] open a university. Uh and Anoir Ibrahim
[01:03:54] is a really really good guy uh to as a
[01:03:56] follow on. Um the there's a risk here.
[01:04:00] the risk is that the authenticity kind
[01:04:02] of collapses because people need uh you
[01:04:06] know you could you could launch a bunch
[01:04:07] of deep fakes with this and have a huge
[01:04:09] issue. Is this the actual leader? That
[01:04:11] kind of question can come up. But I love
[01:04:13] the general approach because if you can
[01:04:16] do it from a with a watermarking or
[01:04:18] something and say this is the actual
[01:04:20] avatar, uh then it gives every citizen a
[01:04:24] voice to um um plug into and gives huge
[01:04:28] props to the civics of all of this
[01:04:31] because now you're scaling civic
[01:04:32] engagement and I think that's a very
[01:04:34] powerful thing to do. It's one of the
[01:04:36] biggest challenges we have with
[01:04:37] democracies all over the world is civic
[01:04:40] engagement and this allows you to scale
[01:04:41] that. So I'm very excited.
[01:04:43] >> Do you remember the reason why Albania
[01:04:44] put this their AI cabinet minister in
[01:04:46] place?
[01:04:48] >> Yeah. Corruption.
[01:04:48] >> Corruption. Exactly. It was to fight
[01:04:50] corruption.
[01:04:51] >> Yeah.
[01:04:51] >> Yeah. Now, Malaysia is pretty decent as
[01:04:54] a pretty decent place, but definitely
[01:04:55] you you have that issue. But I think the
[01:04:57] this is more of a PR thing and more him
[01:05:00] trying to figure out ways of connecting
[01:05:01] with the ordinary citizenry, which is
[01:05:03] all great. I I love the fact that we you
[01:05:05] know we had this conversation with the
[01:05:07] uh president of Argentina uh you know
[01:05:10] going full out here and it's interesting
[01:05:12] to see which countries are sort of
[01:05:14] experimenting on the edge. Um Alex, do
[01:05:17] you want to weigh in?
[01:05:18] >> Yeah. So many thoughts here. First I
[01:05:20] think we're going to see more of this in
[01:05:22] the west as well especially with like
[01:05:25] extra high alpha personality leaders
[01:05:28] that want to amplify themselves and
[01:05:30] touch the the citizenry. AI Trump is
[01:05:32] coming is how you're saying [laughter]
[01:05:35] >> high personality leaders that that want
[01:05:37] to touch the citiz citizenry and in some
[01:05:39] sense I I think it's a generalization of
[01:05:41] social media. So social media enables
[01:05:44] direct outreach from the leader or the
[01:05:47] influencers to everyone but it's sort of
[01:05:49] broadcast one to many. It's not
[01:05:51] interactive. This generalizes in some
[01:05:53] sense social media to make it a lot more
[01:05:55] birectional since if you're touching a
[01:05:58] million or 100 million or a billion
[01:06:00] people it's very difficult to interact
[01:06:02] birectionally with everyone all at once.
[01:06:04] Now if you create a digital twin of the
[01:06:06] leader or the influencer or the
[01:06:08] organization now it can be birectional.
[01:06:10] So I I also don't think it's just going
[01:06:12] to be governments or government leaders
[01:06:14] that adopt this. I I think it's likely
[01:06:16] that corporations, corporate CEOs will
[01:06:18] do this. We already see Zuck and others
[01:06:21] creating digital twins of
[01:06:22] >> themselves. We had DAR on the Abundance
[01:06:24] stage last year. We're discussing this
[01:06:26] that uh the employees made a DAR clone
[01:06:29] that they could go and practice their
[01:06:30] pitches on and get feedback before they
[01:06:32] pitch to him.
[01:06:34] >> Yes. And it won't just be I think
[01:06:35] corporations, religious leaders and
[01:06:37] religious institutions. uh if you're
[01:06:39] Catholic, imagine having like a digital
[01:06:41] twin of the pope and you you see like
[01:06:43] lots of religious institutions,
[01:06:45] organizations already creating basically
[01:06:47] living versions of of their founding
[01:06:50] documents and making those interactive.
[01:06:52] But I think the biggest twist and we
[01:06:54] we've seen variants of this movie before
[01:06:56] are going to be in cases where what
[01:06:59] start as digital twins of the leads or
[01:07:01] the avatars uh of an organization uh or
[01:07:04] an uh some sort of like organized
[01:07:06] religion actually themselves become the
[01:07:09] leader. that that's at at some point the
[01:07:12] the digital twin uh it to the extent
[01:07:14] it's interfacing much more with the the
[01:07:17] the populace uh the the proletariat as
[01:07:20] it were of an organization at some point
[01:07:22] it's actually the digital twin of the
[01:07:23] leader running the company and not the
[01:07:26] actual behavioral origin that uh that's
[01:07:29] running the company and I think that's
[01:07:31] that's one way in which sem to your to
[01:07:33] your exo point this is I I think a
[01:07:36] potentially a pathway towards not just
[01:07:39] uploading individuals like natural
[01:07:41] persons or non-human animals but
[01:07:43] uploading entire organizations into into
[01:07:46] cyerspace into the cloud if we created
[01:07:48] digital twins are the leaders and those
[01:07:50] are the ones actually running the
[01:07:51] organization
[01:07:51] >> it could lead to a true democracy Dave
[01:07:53] where do you come out on this I mean we
[01:07:54] saw just one quick point we saw Sam
[01:07:56] Alman talk about in the future if I
[01:07:58] believe enough in what we're building
[01:08:00] with with chat GPT it should be the CEO
[01:08:03] of open AI eventually
[01:08:06] Dave are you going to create an AI Dave
[01:08:09] Blondon that's going to run Link Studios
[01:08:11] and and Link Link Ventures.
[01:08:14] >> Absolutely. Going to create an AI Dave
[01:08:16] Blondon. And I'm shocked that there
[01:08:18] isn't already a Peter Diamandis.
[01:08:20] >> Well, there is there is one. It's just
[01:08:21] inside the Abundance ecosystem. I mean,
[01:08:23] anybody It was funny. I went to uh went
[01:08:25] up to Calgary and met with one of my uh
[01:08:28] dear friends and abundance member and on
[01:08:30] his wall, I kid you not, he had a giant
[01:08:32] screen of my AI avatar that he has all
[01:08:36] of his tech employees talk to uh to sort
[01:08:40] of get their moonshots and it was it
[01:08:42] blew my mind.
[01:08:43] >> You've got your own big brother, Peter.
[01:08:45] >> It was like he goes, I want to introduce
[01:08:46] you to someone, Peter. And he spins them
[01:08:48] up and I you know, it's interesting to
[01:08:50] have a conversation with your AI self.
[01:08:52] Um, it is very compelling. I mean, I
[01:08:55] have enough books and tweets and uh and
[01:08:58] and Substack posts out there that it
[01:09:00] does a damn good job. Uh, we should
[01:09:02] effectively, you know, moonshots.com is
[01:09:05] our our platform we're building out. I
[01:09:07] think we should have AI avatars of all
[01:09:09] of us there where people can do AMAs.
[01:09:13] >> In some in some cases, Peter, I think
[01:09:14] that might be redundant.
[01:09:16] >> Ah, well, hey, in other words, you're
[01:09:19] already an AI, but we can have an AI of
[01:09:21] the Alex AI. Sure.
[01:09:22] >> It [laughter] would be so much better
[01:09:23] than the real person because we'll have
[01:09:25] access to everything we've ever said,
[01:09:26] all our memories, all our thinking. The
[01:09:28] context will be much broader. Go for it.
[01:09:31] >> This whole area
[01:09:32] >> Yeah.
[01:09:33] >> This whole area is about a year behind
[01:09:34] where it should be largely because, you
[01:09:36] know, Noam Shazir was doing character AI
[01:09:38] and and we had Steve Brown Peter that
[01:09:41] was uh two years ago now. We had Steve
[01:09:42] Brown make uh the debate between AI
[01:09:45] Peter and Sak Aristotle.
[01:09:48] >> Yeah.
[01:09:49] >> Yeah. And and so it's been a it's been
[01:09:50] possible for a while now, but all the
[01:09:52] key talent working on it got sucked back
[01:09:54] into the big foundation labs. And you
[01:09:56] know, there's so many big big big uh you
[01:09:58] know core technological breakthroughs
[01:10:00] going on that the people that were
[01:10:03] working on this just got absorbed back
[01:10:04] into those things and not into the the
[01:10:06] avatar. But my my mom would always tell
[01:10:08] me when I was a kid that John F. Kennedy
[01:10:11] beat Richard Nixon in the election
[01:10:13] because uh he looked good on TV and TV
[01:10:16] was the new medium and the prior medium
[01:10:18] was radio and Nixon was still using
[01:10:20] radio voice when TV had taken over. So
[01:10:23] then, you know, elections go by and
[01:10:25] suddenly it's the internet, it's it's
[01:10:26] social media, now it's YouTube. But this
[01:10:29] is another step function change in the
[01:10:31] way that you reach out
[01:10:32] >> to people [clears throat]
[01:10:33] and it's underutilized, but it's it
[01:10:35] should be easily dominant two years from
[01:10:38] now in the next election. And so I'd be
[01:10:40] shocked if because the technology is
[01:10:42] already there and people are visualizing
[01:10:44] the medium right now as, oh, let me make
[01:10:46] an AI version of myself. I'm Alex Wisner
[01:10:48] Gross. Here's my AI version. It's just
[01:10:50] like the real thing. That completely
[01:10:52] misses the point. The the AI version of
[01:10:55] it can in real time access any
[01:10:58] information and make it visual, graphs,
[01:11:00] charts, you know, it can morph its face.
[01:11:02] It can it can teleport through space to
[01:11:04] make a point and point to atoms. It can
[01:11:06] shrink and expand. It has all these
[01:11:08] capabilities that the real human version
[01:11:11] doesn't have. And that's why it's going
[01:11:13] to be so compelling. It's the
[01:11:14] differences that make this new medium so
[01:11:17] exciting, not the not the exact clone.
[01:11:19] And so once people realize that there's
[01:11:21] no going back. It's going to be huge.
[01:11:23] >> I think Dave, that's such a great point
[01:11:25] that you make, it's the complimentarity
[01:11:27] that is very powerful.
[01:11:28] >> Let me let me close out on one thing
[01:11:30] here. If if uh to our audience here, if
[01:11:33] you've not sat down, if if you're lucky
[01:11:35] enough to have your mom and dad still
[01:11:37] alive or your grandparents still alive
[01:11:39] and you haven't sat down and interviewed
[01:11:42] them in video uh for hours at a time,
[01:11:46] please do that. Right? you're gonna
[01:11:48] you're gonna wish you had. So, I've done
[01:11:50] that with my mom. I miss doing that with
[01:11:52] my dad. And it's the ability for your
[01:11:55] kids and your grandkids and your
[01:11:56] great-grandkids to really have a great
[01:11:58] AI representation of your of your
[01:12:00] parentage and your your lineage. I think
[01:12:02] that's going to be super important.
[01:12:03] Reine, I want to I want to pivot to a
[01:12:06] discussion of liquid AI uh and uh uh the
[01:12:10] the small language models, what they
[01:12:12] are, what they mean. uh super excited
[01:12:15] you know uh just for full disclosure uh
[01:12:19] you know liquid AI is a company in which
[01:12:23] uh Dave you played a important pivotal
[01:12:25] role as an early investor Dave you want
[01:12:27] to give that backstory here a little bit
[01:12:30] >> uh actually I got a call from Daniela
[01:12:31] Roose over at CEL saying the best
[01:12:33] student I've ever had Daniela Daniela is
[01:12:36] you know one of the three I guess big
[01:12:38] shot women in AI she runs CEL at MIT AI
[01:12:42] lab in the world computer science AI lab
[01:12:44] you know I don't know if you remember
[01:12:46] back in the day there was the AI lab and
[01:12:48] then LCS lab for computer science were
[01:12:50] the two biggest
[01:12:51] >> you know compsai labs at MIT they merged
[01:12:53] them together and made one mega lab put
[01:12:56] it in the new STA building which is that
[01:12:57] crumpled look looking beautiful
[01:13:00] structure uh you know right on the edge
[01:13:01] of MIT's campus and then Daniela is
[01:13:04] running that entire thing so I think
[01:13:05] it's like 1500 researchers in the
[01:13:07] building biggest AI lab in the world and
[01:13:10] and so she has access to incredible
[01:13:12] talent but she called and said, "Hey,
[01:13:14] best students I've ever had have this
[01:13:16] incredible breakthrough." And then she
[01:13:18] completely lost me. She said, "It's
[01:13:19] based on the nervous system of the worm,
[01:13:21] the C elegance 300 neuron worm."
[01:13:24] [laughter] Like, what are you talking
[01:13:26] about? But it turns out that if you, you
[01:13:28] know, I actually don't know of any um
[01:13:31] successful foundation lab uh that has
[01:13:34] really rethought from the ground up the
[01:13:36] transformer and thrown it out basically
[01:13:38] and started over which which you know
[01:13:41] humanity desperately needs because that
[01:13:43] the everybody knows the transformer
[01:13:44] architecture and the whole attention
[01:13:46] mechanism is bloated. And if you really
[01:13:49] go back to founding principles and think
[01:13:51] again, you might be able to build
[01:13:52] something dramatically like massively
[01:13:55] better. And so the team went from idea
[01:13:58] in a lab to billion dollar valuation in
[01:14:01] faster than any company out of MIT in
[01:14:03] history.
[01:14:04] >> And luckily we were an investor in that
[01:14:06] company.
[01:14:06] >> Luckily we were. Yeah. And very very
[01:14:08] thankful actually. It was very
[01:14:09] competitive getting any money in at all.
[01:14:11] So Reine uh we owe you a huge debt of
[01:14:13] gratitude for for being invited to the
[01:14:15] to the party. Um but uh yeah it's it's
[01:14:19] uh one of about 200 unicorns out of MIT
[01:14:21] all time but the only foundation model
[01:14:23] company that I know of that reached
[01:14:25] unicorn status coming out of MIT. So
[01:14:27] it's a really unique uh and incredible
[01:14:29] achievement and in record time too.
[01:14:31] >> So remain take it take us from there.
[01:14:32] You're you're doing your PhD under
[01:14:35] Danielle Larus at the computer science
[01:14:36] AI lab CEL and you're studying a 302
[01:14:40] neuron uh worm uh C elegance and so take
[01:14:45] us from there forward to what's uh what
[01:14:47] you're doing now what is liquid AI
[01:14:50] >> absolutely absolutely like before I
[01:14:52] start like I want to thank you guys like
[01:14:54] for for the support throughout like this
[01:14:56] three and a half years years of liquidi
[01:14:58] you have been like great support giving
[01:15:00] us like the the the kind of distrib
[01:15:02] contribution that uh a company needs,
[01:15:05] you know, like and and at at our scale
[01:15:06] like starting off of the east coast.
[01:15:08] Thank you so much for doing that both of
[01:15:10] you. Um and um and um yeah, so so 2015 I
[01:15:16] was in Vienna. I started my PhD with
[01:15:18] professor in Vienna, Professor Rad
[01:15:20] Grusu. There he had the idea of like we
[01:15:23] don't understand a lot about human
[01:15:24] intelligence. Let's start on a smaller
[01:15:26] animal and then from first principles
[01:15:28] like if you understand how the neurons
[01:15:30] exchange information in the brain of the
[01:15:31] worm. The worm has 302 uh neurons in its
[01:15:34] nervous system. It is uh its body is
[01:15:37] transparent so you can actually see the
[01:15:38] body actually lighting up like so it is
[01:15:40] a one of the best model organisms in the
[01:15:43] world. It won so far like four Nobel
[01:15:46] prizes for humanity like you know
[01:15:47] because it has 78% similarity genome
[01:15:50] similarity to uh to human genome you
[01:15:53] know. And the way nervous systems
[01:15:55] compute in the brain of a little worm
[01:15:57] which is 2 mm is um basically analog
[01:16:01] very similar to how artificial neural
[01:16:04] networks are actually computing. They
[01:16:05] are also like analog switches like they
[01:16:07] have like graded potential. They're not
[01:16:09] spiking. So in biological neural
[01:16:11] networks usually in the brains you see
[01:16:13] neurons a spike and when you have a
[01:16:15] spike that's there's an analog to
[01:16:17] digital kind of uh transfer of uh uh
[01:16:20] things are happening and that's a
[01:16:21] natural development of nervous systems
[01:16:24] for uh in in the human beings and and
[01:16:26] bigger animals for propagation for
[01:16:28] efficient propagation of information. In
[01:16:30] the brain of the worm neurons behave
[01:16:32] very similar to how artificial neural
[01:16:33] networks react but then the the
[01:16:35] mechanisms are very interesting. So we
[01:16:38] wanted to add more complexity into the
[01:16:40] neuro like every individual single
[01:16:42] blocks of nervous systems and see can we
[01:16:45] pack more information into inside the
[01:16:48] smaller kind of units of compute you
[01:16:50] know and that's what we have done so
[01:16:52] Danielle Arus two years into basically
[01:16:54] discovery of these things that I was
[01:16:55] doing with my co-founder Matias Lechner
[01:16:58] Matias was a master student in Vienna
[01:17:00] Vienna University of Technology and I
[01:17:02] was a PhD student and then when Daniela
[01:17:04] heard from Radu that uh you know like
[01:17:07] this project is going on. Danila was
[01:17:08] like, "Oh my god, this is crazy. We
[01:17:10] should apply this in autonomy in
[01:17:11] robotics and all the sort of things
[01:17:13] because you're showing like uh a handful
[01:17:15] of neurons can drive and control
[01:17:17] autonomous systems, you know, and can we
[01:17:19] scale this to vehicles? Can we scale it
[01:17:21] to drones to to jets to like like
[01:17:24] predictive kind of places?" So Daniela
[01:17:27] came in and said, "Would you guys
[01:17:28] consider coming to MIT?" And we we went
[01:17:30] there since 2017 in the middle of my
[01:17:32] PhD. I actually joined CELL there. We uh
[01:17:36] we continued working on the uh on this
[01:17:38] technology which was you know like from
[01:17:40] a base is a completely different things
[01:17:42] a neuroscience inspired the math behind
[01:17:45] like every single neuron in a liquid
[01:17:47] neural networks that became kind of my
[01:17:49] PhD thesis is very different than how
[01:17:51] attention works you know these are based
[01:17:53] on recurrent neural networks these are b
[01:17:56] based on continuous time processes you
[01:17:58] know like more and more kind of nature
[01:18:01] inspired computation went into the
[01:18:02] design of uh uh found design of kind of
[01:18:06] AI systems and then we applied these
[01:18:09] liquid neural networks as a completely
[01:18:11] new base because uh we applied them to
[01:18:14] real world scenarios like robotics
[01:18:16] because you can pack a lot more
[01:18:18] information into smaller kind of
[01:18:19] processors in the real world in the
[01:18:21] physical world you don't have the luxury
[01:18:23] of having abundant compute let's say a
[01:18:25] robot doesn't have it doesn't have like
[01:18:27] a lot of GPUs or parallel data centers
[01:18:29] like attached to it a robot has a CPU
[01:18:32] and a small like let's say GPU and let's
[01:18:35] say an NPU a custom ASIC. So you can
[01:18:38] actually take this type of uh you know
[01:18:40] intelligence that we design that deliver
[01:18:43] basically intelligence at the level of
[01:18:45] like models that are 10 to a thousand
[01:18:46] times larger than themselves. You can
[01:18:49] bring those things like directly running
[01:18:50] on CPUs, GPUs and NPUs outside of data
[01:18:53] centers. So we thought that okay this
[01:18:55] format is is going to open up an
[01:18:58] opportunity for us to bring in like
[01:18:59] alternative architecture if we scale
[01:19:01] this technology to let's say into into
[01:19:03] the regime of foundation models which is
[01:19:06] kind of large language models and SLMs
[01:19:08] uh as a whole like human understandable
[01:19:10] like making this liquid neural networks
[01:19:12] or architectures that we have uh also
[01:19:15] scalable like the transformer
[01:19:16] architecture and uh we built like a
[01:19:19] foundation model lab around the idea uh
[01:19:22] in 2020 2023
[01:19:25] beginning of 2023 I think at the very
[01:19:27] beginning when we started there was no
[01:19:29] foundation model lab apart from deep
[01:19:31] mind and and and open AAI basically like
[01:19:33] when we started and this notion of
[01:19:35] foundation model labs didn't exist and
[01:19:37] everybody was betting on top of uh uh
[01:19:40] you know transformer architecture and we
[01:19:43] came in and we said okay so why don't we
[01:19:45] explore this space of alternative
[01:19:47] architectures starting from the priors
[01:19:50] that we have from nature and then take
[01:19:52] take a different approach build a meta
[01:19:54] AI system again uh basically an
[01:19:57] automated AI system that allows us an AI
[01:19:59] that designs AI that explores the
[01:20:02] computational graphs of intelligence
[01:20:04] beyond transformer and then figure out
[01:20:06] what should be that architectural design
[01:20:09] that brings the same level of
[01:20:11] intelligence than a frontier model into
[01:20:13] let's say on on a CPU that we can run
[01:20:15] let's say a physical system
[01:20:17] >> take a second and and walk us through so
[01:20:19] these are small language models can you
[01:20:21] define an SLM M and how it varies from
[01:20:24] an LLM.
[01:20:26] >> Definitely. So when you start uh
[01:20:28] developing kind of foundation models,
[01:20:30] you start you you run something called
[01:20:32] scaling laws. You know like a scaling
[01:20:34] laws is like basically starting with a
[01:20:35] smaller models and with these smaller
[01:20:38] models you train them on a certain
[01:20:39] number of token budget given amount of
[01:20:41] compute. You train these models to see
[01:20:44] how well they perform. Then you start
[01:20:46] systematically making the models larger
[01:20:48] and larger. So that and and we have seen
[01:20:51] scaling laws shows that the larger you
[01:20:53] make the models the more token budgets
[01:20:54] you spend the more intelligence of a
[01:20:56] system you can get and this has been
[01:20:59] like giving rise to large language
[01:21:01] models along the way of scaling there
[01:21:03] are instant instantiation of the models
[01:21:06] which are smaller you know like on the
[01:21:08] scaling laws but we have been doing as a
[01:21:11] lab our mission has always been building
[01:21:13] efficient general purpose AI at every
[01:21:15] scale so we started as a foundation
[01:21:17] model lab to really run the scaling laws
[01:21:20] on on efficiency front you know and
[01:21:21] efficiency was a first class citizen for
[01:21:24] us you know like thinking about
[01:21:25] computational graphs of intelligence
[01:21:27] smaller models are models that are you
[01:21:30] know like along the line of like a
[01:21:32] scaling they can solve um let's say they
[01:21:35] don't have like the general capability
[01:21:36] to the level of the largest kind of
[01:21:38] language models but they can be
[01:21:40] specialized to solve dedicated problems
[01:21:43] they are general purpose small language
[01:21:45] models are general purpose in the sense
[01:21:47] that they understand language They can
[01:21:49] see and they can hear in a multimodal
[01:21:51] kind of format but they don't it doesn't
[01:21:54] mean that they can solve let's say a
[01:21:56] homework in physics and at the same time
[01:21:58] they can solve an enterprise problem you
[01:22:00] usually specialize smaller language
[01:22:02] models
[01:22:03] >> and what does small mean what does small
[01:22:04] mean in this case
[01:22:06] >> small means like basic I mean now they
[01:22:08] come like now small would be like
[01:22:09] anything below 100 billion parameters
[01:22:11] you know like that's kind of the regime
[01:22:13] that I would count I mean midsize like
[01:22:15] basically is is around that that size
[01:22:18] but I would consider like anything below
[01:22:20] 100 billion parameter is something that
[01:22:22] is not small and mediumsiz kind of
[01:22:24] models you know there's no there's no
[01:22:26] clear threshold of like let's say what
[01:22:28] is the number of parameters but for us
[01:22:30] like the notion of ondevice AI is is
[01:22:33] extremely important here to distinguish
[01:22:35] within this range of parameters ondevice
[01:22:38] AI is like models that you can actually
[01:22:41] deploy them uh on the on an actual kind
[01:22:43] of device physical device this could be
[01:22:45] a
[01:22:46] >> let's make this concrete cuz you've got
[01:22:48] a significant deal with Mercedes.
[01:22:50] >> Yes.
[01:22:50] >> Um and can you speak to that and let's
[01:22:52] talk about you know these these SLMs in
[01:22:56] terms of uh onrem uh basically they're
[01:22:59] they're and energy efficient uh you know
[01:23:02] fast offline. Let's let's dive into that
[01:23:05] give people sort of a real understanding
[01:23:07] here.
[01:23:08] >> Absolutely. So as I mentioned you can
[01:23:11] specialize these foundation models. We
[01:23:13] work with a lot of enterprises that are
[01:23:15] building devices themselves. Like
[01:23:17] automotive is a device is a is a is a is
[01:23:19] an environment where you have a lot of
[01:23:21] chips in there and now in a car you
[01:23:24] don't have that much that much compute.
[01:23:26] So there's like one chip that is
[01:23:27] available for infotainment and incar
[01:23:29] intelligence you know that chip is very
[01:23:31] very small. The Qualcomm chip or let's
[01:23:33] say Samsung chip like depending on like
[01:23:35] what company is providing the chip like
[01:23:37] that chip is like very very small. We
[01:23:39] are talking about 2 GB to 8 GB of RAM,
[01:23:42] you know, like not more than that. So
[01:23:44] the model has to be very small and at
[01:23:46] the same time being able to perform
[01:23:48] because we want to bring this and enable
[01:23:50] a private space inside the car that
[01:23:53] powers the intelligence of the car in
[01:23:55] the car. Car is a safety critical
[01:23:57] environment. You don't want your car to
[01:23:59] be driven by an AI model that is sitting
[01:24:00] in the cloud. Why? Because connectivity
[01:24:02] is not uh always available, right? then
[01:24:06] uh it is it is private because it's one
[01:24:08] of those spaces that people spend a lot
[01:24:09] of time in and you don't want those
[01:24:11] conversations to be like recorded. So we
[01:24:13] brought the intelligence like um
[01:24:16] basically we brought u uh one of our
[01:24:19] multimodal foundation models that is
[01:24:21] only uh less than one gigabyte of in
[01:24:24] size
[01:24:24] >> and it can go inside the car's chip like
[01:24:27] very very tiny chip. The chip could be
[01:24:30] as cheap as $60, you know, like that's
[01:24:32] what I'm saying. Like we're bringing
[01:24:33] that level of intelligence into that
[01:24:35] that voice and it is going to power kind
[01:24:38] of the multimodal intelligence
[01:24:39] experience inside the car. We do that
[01:24:42] with all car manufacturers. We announced
[01:24:43] the Mercedes partnership as a first uh f
[01:24:46] first kind of uh point of entry because
[01:24:49] automotive is like it's very sensitive
[01:24:51] kind of uh topic and and they're they're
[01:24:53] pretty slow. One of the things that
[01:24:55] Mercedes dispense actually enjoyed from
[01:24:56] this process was the speed of operations
[01:24:59] that we had for enterprises you know
[01:25:00] like when we are bringing this type of
[01:25:02] technology inhouse this has been like
[01:25:04] one of those uh cornerstones of landing
[01:25:06] the deals you know because we want to
[01:25:08] work we are an enterprise company we're
[01:25:09] a B2B company we are bringing our full
[01:25:12] power to really like deploy the
[01:25:13] solutions and really have platforms that
[01:25:16] allows people to fine-tune like their
[01:25:18] small models and fine-tuning small
[01:25:20] models is not that expensive. It's
[01:25:22] something that is extremely tangible. So
[01:25:24] they we fine-tune kind of the small
[01:25:26] models for the the applications inside
[01:25:29] the car. We also have data flywheel kind
[01:25:31] of systems that allows the system always
[01:25:34] stay adaptable. Imagine some of the some
[01:25:36] of the problems in enterprise AI has
[01:25:38] always been let's download a GLM 2 5.2
[01:25:41] like you know and and let's say an open
[01:25:43] source model and put that in production
[01:25:45] and then so what happens after you put
[01:25:47] the system in production? What happens
[01:25:49] like when there's a drift from the use
[01:25:51] cases that is hitting this model inside
[01:25:54] let's say a car and in the physical
[01:25:55] world it becomes even more challenging
[01:25:58] because when you deploy an intelligence
[01:25:59] that is completely kind of disconnected
[01:26:02] from the cloud how do you want to like
[01:26:05] maintain updates of the system because
[01:26:07] we have always thought about like
[01:26:09] intelligence in the format of liquid you
[01:26:11] know like intelligence has to always
[01:26:13] stay adaptable and um and that that's
[01:26:15] that's kind of a portion that we're also
[01:26:17] pushing on to really be able to collect
[01:26:20] the data and personalize models to the
[01:26:23] experience of every single user. With
[01:26:25] Mercedes, we're rolling this out first
[01:26:27] in North America uh as as soon as
[01:26:30] basically this year. All the
[01:26:31] Mercedes-Benz North America cars like
[01:26:33] from 2022 on they're going to get an
[01:26:35] update overtheair update because the
[01:26:37] size of the update is 600 megabyte. So
[01:26:40] that's that's like a that's like a
[01:26:42] overlay of like it doesn't consume that
[01:26:44] much internet to really update your
[01:26:45] software and that allows us to also
[01:26:47] further customization. Imagine if every
[01:26:49] update that you want to perform on the
[01:26:51] system is in the order of 20 megabytes
[01:26:54] because we are doing like some sort of
[01:26:55] lore adapters and let's say all sort of
[01:26:57] adapters that we can actually bring in
[01:26:58] inside the car. You would be able to
[01:27:00] have like a recursively kind of
[01:27:02] improving the experience of the user as
[01:27:05] well. So that's kind of let's take it
[01:27:08] make it more concrete for me. So what am
[01:27:10] I going to be how am I using this model
[01:27:11] in my Mercedes next year? So right now
[01:27:14] my experience is using Grock in my
[01:27:16] Tesla, right? And it's over the air. If
[01:27:18] I don't have connectivity, I don't have
[01:27:20] Grock. Uh but you know what kind of what
[01:27:23] kind of queries what kind of
[01:27:24] capabilities does this all of a sudden
[01:27:26] enable in a Mercedes?
[01:27:28] >> It has access it it's it's sitting below
[01:27:31] the the the operating system. So that
[01:27:33] means like it is basically it is like
[01:27:36] basically have access to all the
[01:27:38] functions inside the car you know so
[01:27:40] there are 700 functions inside the car
[01:27:42] 700 to like I don't know 1,200 depending
[01:27:45] on what what you count as a function you
[01:27:47] can you can talk to your car you can
[01:27:49] control like all the panels of your car
[01:27:51] you can ask for let's say manuals of the
[01:27:53] car you know like when when you're like
[01:27:55] get let's say stuck somewhere you know
[01:27:56] like something pops up you know like you
[01:27:58] would be able to talk to the car there
[01:28:00] are memory features that we are adding
[01:28:01] to the car like You basically can have
[01:28:04] conversations with that with that
[01:28:05] system. Once the like one of the
[01:28:08] beauties of this system is that like it
[01:28:09] has full access to the to all the
[01:28:11] functionalities of the car plus all the
[01:28:13] apps because there are like function
[01:28:15] calls. They're one function calls away,
[01:28:17] you know. So if you want to control any
[01:28:19] other thing from this from this
[01:28:21] intelligence unit inside the car, you
[01:28:22] would be controlling everything all the
[01:28:24] ecosystem that is sitting on top of the
[01:28:27] uh um sitting on top of the operating
[01:28:29] system of the car.
[01:28:32] So basically I mean if I get you right
[01:28:34] there the advantage of the SLMs are
[01:28:37] first of all you know the size of the
[01:28:39] model I I assume energy consumption
[01:28:41] they're efficient um and they can run on
[01:28:45] on prem uh do I mean how do you avoid or
[01:28:49] reduce sort of overgeneralization of
[01:28:51] these models compared to LLMs?
[01:28:54] >> What do you mean overgeneralization? In
[01:28:55] other words, uh are the do you have
[01:28:58] enough capabilities internal to them so
[01:29:00] that they are uh actually able to
[01:29:02] accurately answer the questions you're
[01:29:04] asking?
[01:29:05] >> Great question. So if you have like you
[01:29:07] know I I told you about the framework of
[01:29:09] foundation model development which is
[01:29:10] depths of customization.
[01:29:12] >> We try to actually stay adaptable and
[01:29:15] have access to the tools across these
[01:29:17] customization stacks. Sometimes prompt
[01:29:19] engineering is enough. Sometimes you got
[01:29:21] to fine-tune the model. Sometimes you
[01:29:22] have to do go and pre-train a model
[01:29:24] again you know for the core capabilities
[01:29:26] or a specialization of intelligence. Now
[01:29:29] we make systems that are you know our
[01:29:31] platforms are getting into the place
[01:29:32] where they're automatically identifying
[01:29:35] what depths of customization is needed
[01:29:37] for a certain solution and the platform
[01:29:39] basically like it's it's one of the
[01:29:40] products of the company that we sell to
[01:29:42] enterprises to allow them to fine-tune
[01:29:45] kind of models like I I don't want to
[01:29:47] call it fine tune customize a model at a
[01:29:49] level that is needed for that uh uh for
[01:29:52] that system to actually operate right so
[01:29:54] for Mercedes-Benz we have a let's say
[01:29:57] like the framework that we have at at
[01:29:59] in-house. We call it model plus X, you
[01:30:02] know, model plus a platform that allows
[01:30:04] you to perform customization. It's not
[01:30:07] just the models that we're selling to
[01:30:09] enterprises, the static weights of a
[01:30:10] model. We sell them something that they
[01:30:12] can actually like retune and fine-tune
[01:30:14] the system. Detecting how how much uh
[01:30:18] generality like the base models have,
[01:30:20] it's something that you know like
[01:30:21] libraries of liquid models are coming
[01:30:23] out for many different applications. We
[01:30:24] have models that we're working with for
[01:30:27] example in silicon medicine like you
[01:30:28] know Alex
[01:30:29] >> I introduced you Alex
[01:30:30] >> that you introduced us Peter like I
[01:30:33] remember and um and through that kind of
[01:30:35] interaction like it is getting big you
[01:30:36] know because they discovered that liquid
[01:30:38] foundation models are actually pretty
[01:30:39] good getting customized for a certain no
[01:30:42] they're they're basically like really
[01:30:45] really well orable so and and and that's
[01:30:47] something that they they they figured
[01:30:49] out that it comes handy for them. So now
[01:30:51] we have a state-of-the-art biotech
[01:30:53] foundation models like longevity
[01:30:54] foundation models like these are the
[01:30:56] kind of things that we're building in
[01:30:57] bio and imagine like as a horizontal
[01:30:59] company that is building foundation
[01:31:00] models we went to like fine-tuning and
[01:31:02] that became like something that we have
[01:31:05] we have managed to do and then in terms
[01:31:07] of um you know like some of the uh uh
[01:31:10] some of the other engagements like we
[01:31:11] recently with with Shopify we entered
[01:31:13] like uh one uh 1 billion kind of request
[01:31:17] address inside the Shopify kind of
[01:31:19] framework And uh there like what we've
[01:31:22] done we uh we deploy our liquid
[01:31:24] foundation models in production. They
[01:31:25] have been in production for the last 6
[01:31:27] months and they are really serving
[01:31:29] clients you know and and Shopify is like
[01:31:31] a huge uh uh base like we are touching
[01:31:34] 100 million kind of hundreds of millions
[01:31:36] of kind of users 10 billion products and
[01:31:38] many different kind of uh places to to
[01:31:41] integrate. We are working with
[01:31:42] Mercedes-Benz as I mentioned like on the
[01:31:44] car kind of side of things. We're
[01:31:45] working with AMD and uh other chip
[01:31:48] manufacturers to really bring AI uh
[01:31:50] let's say um low code AI experiences on
[01:31:53] PCs as well. So that's like another uh
[01:31:55] area that we enter. The focus of our
[01:31:57] company is to really uh make sure that
[01:32:00] we can bring uh basically intelligence
[01:32:04] outside of data centers. That's like
[01:32:05] something that we have focused on and I
[01:32:07] think our efficiency is actually
[01:32:08] allowing us to get
[01:32:09] >> preliminary matter. I have no financial
[01:32:11] interest in liquid. Sorry Reine have to
[01:32:13] ask the the most obvious question. I
[01:32:15] have so many questions for you which is
[01:32:18] the company liquid was founded as I
[01:32:20] understand it and I I remember reading
[01:32:21] the original I think it was in science
[01:32:22] or nature paper on liquid neural
[01:32:24] networks. Uh the premise is basically a
[01:32:27] neuromorphic premise that that you could
[01:32:30] gain useful AI insights from looking at
[01:32:32] nematodes uh a few hundred neurons sort
[01:32:34] of the ultimate small neural network.
[01:32:38] But my perception I I'm hoping that you
[01:32:40] can uh either help me amend or revise my
[01:32:42] perception is that although liquid
[01:32:45] started with a neuromorphic premise if
[01:32:48] you will like a post transformer very
[01:32:50] recurrentoriented architectural premise
[01:32:53] or prior that over time again just based
[01:32:56] on my perception of public messaging
[01:32:58] liquid looks more and more like either
[01:33:00] transformer or transformer plus or
[01:33:03] transformer plus hyena plus dot dot
[01:33:06] looks more and more like basically a
[01:33:08] conventional off-the-shelf architecture.
[01:33:11] It may be a good business selling sort
[01:33:13] of customized transformer derivatives to
[01:33:15] Mercedes at all. If so, great from the
[01:33:18] business side. But from the technical
[01:33:19] side, does Liquid still have anything
[01:33:22] that looks remotely like a trans a post
[01:33:25] transformer architecture either in
[01:33:27] production or under development? And can
[01:33:29] you speak to what if anything is post
[01:33:31] transformer or non-transformer oriented
[01:33:34] about the architecture that you
[01:33:35] currently use? Great great question. So
[01:33:38] let me tell you like the space of kind
[01:33:40] of architecture. So liquid neural
[01:33:42] networks in in the original form they
[01:33:44] are one of the most expressive formats
[01:33:46] of computes that you can actually create
[01:33:48] arguably like in terms of our
[01:33:49] architecture they are they have nested
[01:33:51] non nonlinearities that are like in like
[01:33:54] you cannot really like take them out.
[01:33:56] They're like completely physics
[01:33:58] inspired. They are like having like the
[01:34:00] neural odes and and basically like
[01:34:02] irregularly sampled data can be handled
[01:34:04] by them. So they they become like one of
[01:34:06] the very very general class of
[01:34:08] architectures as a whole. Underneath
[01:34:10] these things like when you want to scale
[01:34:12] this type of technology these
[01:34:13] recurrences like you know like this uh
[01:34:15] nested kind of loops that they have. If
[01:34:18] you want to scale these systems a lot of
[01:34:20] people have attempted including
[01:34:21] ourselves to linearize the dynamics so
[01:34:23] that you can actually like scale them.
[01:34:25] space uh uh you know state space models
[01:34:27] are kind of basically like mumbas and
[01:34:29] those kind of variants falling into the
[01:34:32] same category of continuous time neural
[01:34:34] networks but dumped down into a linear
[01:34:36] kind of dynamical systems because you
[01:34:38] you want to scale them. They are
[01:34:39] underneath this class of continuous time
[01:34:41] models that we have. Then there is like
[01:34:45] there are variants of uh linear linear
[01:34:47] attention gated linear attentions that
[01:34:49] are coming out. They are also like
[01:34:51] gating mechanism is something like
[01:34:53] there's a special gating input dependent
[01:34:55] gating mechanism that actually we got
[01:34:57] inspired by the by by how neurons
[01:35:00] actually exchange information with each
[01:35:01] other. That gating mechanism is also
[01:35:03] something that is adding a lot more
[01:35:05] expressivity like it is also descendant
[01:35:07] of the original formation of how neurons
[01:35:10] exchange information with each other.
[01:35:11] That gating mechanism still exists today
[01:35:14] in in many different architecture and
[01:35:16] including ours. But the most important
[01:35:18] thing that I want to mention that you
[01:35:20] should know about the technology
[01:35:21] transformation of our company is that we
[01:35:24] really didn't want to bias ourselves
[01:35:26] towards one single architecture. One of
[01:35:29] the things that we did day one at Liquid
[01:35:31] AI, we designed a search algorithm to
[01:35:34] let's say like you know let the
[01:35:35] algorithm instead of human biasing kind
[01:35:37] of the algorithm let the let the
[01:35:39] algorithm run the scaling laws on let's
[01:35:41] say 100 different variations of
[01:35:43] operations that potentially can give you
[01:35:45] a general purpose computer. So we build
[01:35:47] a meta system. The paper around this is
[01:35:50] actually we published like two and a
[01:35:52] half years ago. We published a paper
[01:35:54] about uh about the topic is called star
[01:35:56] automated uh design of tailored
[01:35:58] architectures. So read about style uh
[01:36:01] and and star is a framework that brings
[01:36:04] all the dynamical systems with any
[01:36:07] format including kind of variations of
[01:36:09] attention into one format for us to be
[01:36:13] able to search through. Okay. So to see
[01:36:15] like for four criteria what is the most
[01:36:19] optimal neural architecture let's say of
[01:36:22] choice for let's say a certain
[01:36:23] deployment number one criteria is memory
[01:36:26] like how much memory are you consuming
[01:36:28] on a given processor number two was the
[01:36:31] efficiency of computation how fast you
[01:36:32] can operate number three is latency of
[01:36:35] operations and number four do not lose
[01:36:38] accuracy on the performance there are
[01:36:41] pure transformer models and then there
[01:36:43] are hybrid models that you can actually
[01:36:44] build hybrid models have like an
[01:36:46] essential compon like they have a little
[01:36:48] bit of transformers in them but they're
[01:36:50] but the but the rest of the kind of
[01:36:52] dynamical system and most of the
[01:36:53] dynamical system for the purpose of
[01:36:55] these four objective functions that I
[01:36:57] mentioned would be you you would change
[01:36:59] that and you can actually automate this
[01:37:01] whole framework to design foundation
[01:37:03] models inhouse the the technology stack
[01:37:06] of liquid foundation like liquid
[01:37:08] foundation models is called automated
[01:37:10] foundation model design kind of
[01:37:12] algorithms we call it AFMD This
[01:37:14] automated framework is the one that
[01:37:16] explores architectures for for a given
[01:37:18] kind of hardware. And guess what came
[01:37:21] out of like the first generation of the
[01:37:23] architectures that we started
[01:37:25] optimizing. It came double gated
[01:37:28] convolution kind of mechanisms as 80% of
[01:37:30] the network being this. So when we run
[01:37:33] without a human bias the gating
[01:37:35] mechanism that we had exactly in the
[01:37:37] liquid foundation liquid neural networks
[01:37:39] original paper it actually shows up with
[01:37:41] this very very similar kind of format in
[01:37:44] the final architecture that comes out of
[01:37:46] the search space.
[01:37:46] >> Everybody welcome to the health section
[01:37:48] of moonshots brought to you by fountain
[01:37:50] life. You know we talk about AI on this
[01:37:51] moonshot podcast all the time. One of
[01:37:53] the most important things AI is going to
[01:37:55] be able to do for you besides educating
[01:37:57] your kids and helping you with your
[01:37:58] taxes is making sure that you're living
[01:38:01] a healthy lifestyle that you get a
[01:38:03] chance to get to 100 plus. I'm here
[01:38:06] today with Dr. Don Mucalem the chief
[01:38:08] medical officer of Fountain Life and a
[01:38:10] part of my medical team. Don a pleasure.
[01:38:13] >> Great.
[01:38:14] >> You know the thing that people are
[01:38:15] concerned about most about living to 100
[01:38:17] or 120 is their cognitive abilities.
[01:38:20] making sure they don't have dementia and
[01:38:24] uh the numbers about dementia are
[01:38:26] problematic. Uh can you share what
[01:38:28] you've learned?
[01:38:29] >> Such an important point and you're right
[01:38:31] at Fountain Life, our members, the
[01:38:33] number one thing people are most
[01:38:34] concerned about is losing their brain
[01:38:36] health, forgetting the name of their
[01:38:37] child, forgetting the face of their
[01:38:39] loved one. We know that when it comes to
[01:38:40] dementia, the conservative estimates are
[01:38:43] that 45% are entirely preventable. What
[01:38:46] was amazing is with the advanced testing
[01:38:49] we're doing at Fountain Life, one
[01:38:51] quarter of our members had advanced
[01:38:53] brain age.
[01:38:54] >> Wow.
[01:38:54] >> But what was really awesome is again
[01:38:56] back to that prevention when we
[01:38:57] partnered it with healthy living. This
[01:38:59] gives me chills. Eating healthier,
[01:39:01] moving our bodies sleep, optimizing
[01:39:04] sleep is so important. You know what we
[01:39:05] saw? We saw that we improved that brain
[01:39:07] age by 26%. That is a big big number to
[01:39:11] show that the majority of those
[01:39:13] individuals were able actually to
[01:39:15] improve the brain age.
[01:39:16] >> And one of the things I love about
[01:39:17] Fountain is we're searching the world
[01:39:18] for the best therapeutics, the best
[01:39:20] approaches, and making sure we bring it
[01:39:22] to our members. So if having healthy
[01:39:25] brain function uh till 100, 120 is
[01:39:28] important to you, check out Fountain
[01:39:30] Life. Go to fountainlife.com/per.
[01:39:33] Make sure you become the CEO of your own
[01:39:35] health. All right, now back to the
[01:39:36] episode. All right, our next story comes
[01:39:38] from Palmer Lucky, the founder of Oculus
[01:39:40] and now the chairman of the defense
[01:39:43] giant Andre. It's it's funny to call
[01:39:45] Andre a defense giant, but it is. He's
[01:39:47] claiming that the modern patent system
[01:39:49] has become a national security
[01:39:51] liability. In his words, the entire
[01:39:52] patent office could be downloaded every
[01:39:55] morning, ripped off, and used to fight a
[01:39:57] war against you. The core problem is
[01:39:59] baked into what uh patents actually do.
[01:40:03] Uh patents are a requirement. If you
[01:40:06] want to get a patent, you have to teach
[01:40:08] uh a uh a person skilled in the art how
[01:40:13] to actually uh you know create and use
[01:40:16] your device. So this disclosure of your
[01:40:19] invention and the exact words and patent
[01:40:21] law is in uh such full clear and concise
[01:40:24] and exact terms as to enable any person
[01:40:27] skilled in the art to make and use the
[01:40:30] same. So if you do that, you're
[01:40:32] effectively teaching the world how to
[01:40:34] use it. uh and you're exchanging that
[01:40:37] that uh sharing of your invention for
[01:40:39] roughly 20 years of exclusivity. Palmer
[01:40:42] argues that when a strategic adversary
[01:40:44] can simply harvest every file, ignore
[01:40:47] the legal protections, and weaponize the
[01:40:50] disclosed knowledge, you've handed them
[01:40:52] a free instruction manual to your best
[01:40:54] ideas. So, just for some numbers, the US
[01:40:57] Patent Office receives about 600,000
[01:40:59] applications annually. It grants a
[01:41:02] little over half of those 323,000.
[01:41:04] Uh that's 2025 data. Uh interestingly
[01:41:07] enough, patents uh uh granted have
[01:41:10] increased 40% in the last 5 years. My
[01:41:13] guess is that is uh secondary to AI.
[01:41:16] Palmer's proposed fix isn't to abolish
[01:41:19] patents. It's to massively scale up a
[01:41:22] national security patent process which
[01:41:24] goes back to the Secrecy Act of 1951.
[01:41:28] So this obscure mechanism lets inventors
[01:41:30] obtain classified patents in which you
[01:41:33] keep your exclusive rights but you don't
[01:41:36] disclose it to anyone and neither can
[01:41:37] the government. So there roughly 6,000
[01:41:40] of these uh secure secrecy orders active
[01:41:43] in the US. Lucky wants that this edge
[01:41:46] case uh is turned into default
[01:41:48] mechanism. So here's the question,
[01:41:51] right? If we genuinely uh trade this
[01:41:54] openness which has been sort of the
[01:41:56] basis for American entrepreneurial
[01:41:58] exceptionalism uh for a a secret system.
[01:42:02] Are we trading safety of having our
[01:42:05] patents ripped off against really the
[01:42:07] innovative ecosystem that we've had?
[01:42:10] Let's watch a short video from uh from
[01:42:13] Palmer and then we'll talk about it.
[01:42:16] >> Stop patenting everything. Uh patents
[01:42:18] are Chinese instruction manual. Well,
[01:42:19] the founding fathers never predicted a
[01:42:21] world where you would have a globalized
[01:42:22] economy where the entire patent office
[01:42:24] could be downloaded every single morning
[01:42:26] and then ripped off and then used to
[01:42:28] fight a war against you. We need to
[01:42:30] really fundamentally revisit the patent
[01:42:32] system. I think we need to massively
[01:42:34] expand the national security patent
[01:42:37] process. Uh you can you can obtain a
[01:42:39] classified patent. You can get a patent
[01:42:41] on something that you are not allowed to
[01:42:42] disclose to anyone, but you still
[01:42:44] maintain the exclusivity on those
[01:42:45] rights. We need to massively expand that
[01:42:47] program. So, you know, I've applied for
[01:42:51] and gotten a dozen patents. I know Alex,
[01:42:53] you have a even a much larger number of
[01:42:55] them. Uh, so I'm curious, guys, how do
[01:42:58] you come out on this? Alex, do you want
[01:43:00] to kick it off?
[01:43:02] >> I I think this is the episode of people
[01:43:05] uh tech CEOs floating terrible ideas. I
[01:43:07] think this is a terrible idea. I I think
[01:43:10] the I would argue the invention secrecy
[01:43:13] act of 1951 which is I I think what
[01:43:16] Palmer is gesturing at has been probably
[01:43:18] on balance quite detrimental not just to
[01:43:22] democracy uh that if patents so maybe a
[01:43:26] bit of context the the way the the
[01:43:28] invention secrecy act works is uh it's
[01:43:31] it's not that you can just sort of file
[01:43:34] the patent in secret and not disclose uh
[01:43:36] it it's that basically it can only be
[01:43:39] practiced the invention that uh that is
[01:43:42] basically confiscated or eminent
[01:43:44] domained by the military can only be
[01:43:47] practiced for military reasons. It's not
[01:43:49] contra uh any construal otherwise that
[01:43:52] invention secrecy act somehow offers
[01:43:54] legal cover for an individual to
[01:43:57] secretly disclose how their invention
[01:43:59] works uh under some confidentiality and
[01:44:01] then go practice it in general. They
[01:44:03] can't. It's that the military
[01:44:05] exclusively can practice it and then the
[01:44:08] inventor gets royalties from that
[01:44:10] practice. That may be good for Andre's
[01:44:13] defense business, but I I think in
[01:44:15] general terrible idea. Greater concern
[01:44:17] that I have is it these are these would
[01:44:20] be basically secret monopolies. Uh I I
[01:44:22] think it's bad enough that we have
[01:44:24] invention secrecy act classification of
[01:44:27] inventions query whether entire swaths
[01:44:31] of technology that could be completely
[01:44:34] transformative economically to the
[01:44:35] entire world from an energy perspective
[01:44:38] for other domains have somehow without
[01:44:41] general knowledge been swept up by the
[01:44:43] invention secrecy act and basically
[01:44:45] confiscated by the department of war for
[01:44:48] purely military reasons. That's that's
[01:44:51] very concerning to me. The idea of
[01:44:53] expanding it overall. I I would argue if
[01:44:55] if anything the invention secrecy act
[01:44:57] regime should probably go away.
[01:44:59] >> We can have this debate. So Palmer is
[01:45:00] going to be joining us at uh at the
[01:45:02] moonshots gathering on September 25th in
[01:45:04] LA. Everybody go to moonshots.com. We
[01:45:07] have an amazing day with the moonshot
[01:45:09] mates there. We'll be having these
[01:45:11] conversations with Palmer Salem. Uh I
[01:45:14] mean the what makes America great is our
[01:45:17] open innovation policy. people building
[01:45:19] on top of other people's creations. What
[01:45:21] are your thoughts here?
[01:45:23] >> Look, we've seen this uh problem uh get
[01:45:28] bigger and bigger over the last 20 to 30
[01:45:30] years, okay? Where the disclosure,
[01:45:34] especially in an age of AI where people
[01:45:36] can just route around it or replicate or
[01:45:38] learn from it, it's it's a huge
[01:45:40] challenge. The the real mode is learning
[01:45:43] loops. uh that's going to be the real
[01:45:45] defensibility is what are your feedback
[01:45:47] loops and can you learn in a proprietary
[01:45:49] way and then create trade secrets around
[01:45:51] that and action that in the marketplace.
[01:45:54] Continuous innovation is going to be the
[01:45:56] winning defense. It's not going to be
[01:45:57] ownership. The only people that win in
[01:45:59] this whole in this particular model are
[01:46:01] the lawyers. [laughter]
[01:46:02] >> Well said. Um Dave, any thoughts here?
[01:46:06] >> Yeah, I think you know if there's a
[01:46:07] flash point for a World War III, this is
[01:46:09] probably one of the most likely
[01:46:11] >> seriously
[01:46:11] >> where Yeah. Well, well, you know, look,
[01:46:14] Alex is right. We're going to discover
[01:46:16] new physics, new medicines at an
[01:46:18] incredible accelerating rate. And, you
[01:46:20] know, places like Europe respect
[01:46:22] intellectual property rights, and that
[01:46:24] creates a kind of a coherent economy
[01:46:26] where you can trade these things. China
[01:46:28] completely ignores intellectual property
[01:46:30] rights and and just takes it and runs
[01:46:32] with it. Uh, so I think the likely
[01:46:34] outcome of that is the US will trade
[01:46:36] embargo anybody who doesn't respect
[01:46:38] intellectual property rights. then you
[01:46:40] have to choose are you part of the you
[01:46:42] know the free world or you part of the
[01:46:44] alternate world but I think that's the
[01:46:46] more likely um outcome and that's going
[01:46:49] to happen soon like in the next couple
[01:46:51] of years because the rate of innovation
[01:46:52] is going to go through the roof but
[01:46:53] there's no science fiction future book
[01:46:55] I've ever read where there isn't massive
[01:46:58] amounts of intellectual property being
[01:47:00] created by AI at an incredible
[01:47:01] accelerating rate and there's some
[01:47:03] vehicle by which innovators can profit
[01:47:05] from that and if you don't have that
[01:47:07] then you don't have the future you a
[01:47:09] huge fraction of brilliant thinkers
[01:47:13] coming out of, you know, Cambridge and
[01:47:14] MIT and Harvard don't work on
[01:47:16] foundational technologies because
[01:47:19] there's no money in it. And that's got
[01:47:21] to change fundamentally. And protecting
[01:47:23] intellectual property rights is a key
[01:47:25] key way to reverse that tide and get
[01:47:27] people working on really important
[01:47:28] things.
[01:47:29] >> Y I think to Dave's point also, Palmer
[01:47:32] fundamentally misunder or appears to
[01:47:34] misunderstand the nature of patents. The
[01:47:36] whole point of a patent is that you
[01:47:38] disclose how it works in return for a
[01:47:40] state granted temporary monopoly on it
[01:47:43] and say, you know, sort of belly aching
[01:47:46] that the the Chinese are running away
[01:47:48] with the disclosure. It is really a
[01:47:50] quibble with enforcement of of patent.
[01:47:53] It it's not you don't want to throw
[01:47:54] necessarily the baby out with the
[01:47:55] bathwater and say we want to give away
[01:47:58] the the patent trade of disclosure in
[01:48:00] return for temporary monopoly. Really
[01:48:02] what he should be asking is better
[01:48:04] enforcement of US patents in China.
[01:48:07] >> Agreed. All right, I'm going to move us
[01:48:08] into the world of healthcare abundance.
[01:48:10] So, two stories this week are
[01:48:11] demonstrating an incredible impact of AI
[01:48:13] on healthcare abundance, demonetizing
[01:48:16] and democratizing diagnostics uh for
[01:48:19] billions of people. The first story is
[01:48:21] the performance of GPT 5.6 six saw uh
[01:48:24] which was released a couple weeks ago on
[01:48:27] healthbench professional which is
[01:48:28] openai's hardest medical benchmark uh so
[01:48:32] jat GPT or GPT 5.6 saw set a brand new
[01:48:35] all-time benchmark high and then the
[01:48:38] second part coming out here is in a
[01:48:40] blind test across roughly 20,000
[01:48:43] individual physician judgments in other
[01:48:45] words uh you know diagnos diagnosing for
[01:48:48] accuracy safety completeness GPT 5.6 ICS
[01:48:52] answers were compared to specialty
[01:48:55] matched physicians other words
[01:48:56] pulmonologists, pediatricians, whatever,
[01:48:58] who were given unlimited uh full access
[01:49:01] to the web and unlimited time to answer
[01:49:04] and the doctors still lost. So we've got
[01:49:07] Chad GPT. We've known this for some time
[01:49:09] that these AI diagnostic models are
[01:49:11] better than the best physicians given
[01:49:13] all the tools that humans can use. The
[01:49:16] second part of the story comes from
[01:49:17] Meta. So, OpenAI's own healthbench
[01:49:21] professional benchmark which is 525 real
[01:49:25] clinical tasks. Meta's Muse Spark 1.1
[01:49:28] again released last week uh beat chat
[01:49:32] GPTs uh or GPT 5.6 Saul on across the
[01:49:36] marks and it was 7 times cheaper. But
[01:49:39] even better, I mean important to note
[01:49:41] here is that Muse Spark is free inside
[01:49:45] of all of Meta's products. you know,
[01:49:47] WhatsApp and Facebook and Meta today
[01:49:50] serves 3.56
[01:49:52] billion daily active users using their
[01:49:55] products. So, here we've got a situation
[01:49:58] where the top medical AI capabilities
[01:50:01] are now free to over 3 and a half
[01:50:05] billion people on the planet. And that's
[01:50:07] just extraordinary. I mean, this is the
[01:50:08] abundance thesis at large. Uh and again
[01:50:12] as people talk about the concerns of AI
[01:50:14] and so forth, please realize this.
[01:50:16] People who've never had access to the
[01:50:18] best diagnosticians now have them. Sim
[01:50:22] there is a there's there's a model in an
[01:50:24] AI doctor in China that's being used in
[01:50:27] rural environments by 100 million people
[01:50:30] already. Right? Basically diagnosis is
[01:50:34] has had massive cost collapse. The
[01:50:36] healthcare domain is particularly
[01:50:38] interesting because it's where abundance
[01:50:40] becomes actually morally urgent, right?
[01:50:43] If you can deliver way better first
[01:50:45] inline answers at at like near zero
[01:50:47] cost, it's how quickly can you safely
[01:50:50] get it out there? That's the only
[01:50:51] question. And so, uh, it's absolutely
[01:50:54] and right, let's recognize that in
[01:50:57] almost every country in the world,
[01:50:59] there's radical doctor shortage.
[01:51:01] >> So, this is really, really critical. You
[01:51:03] see like this is such a July 2026 story
[01:51:06] where think about it Instagram now gives
[01:51:09] better medical advice than a human
[01:51:10] doctor.
[01:51:11] >> It's it's it's pretty pretty wild. It
[01:51:14] cost of intelligence not just going too
[01:51:16] cheap to meter. Cost of medical
[01:51:18] intelligence becoming too cheap to
[01:51:20] meter. free basically free. I mean
[01:51:23] that's
[01:51:24] >> well the the ultimate too cheap to meter
[01:51:25] is asmmptoically free right but I I I
[01:51:28] would say probably I I in all honesty I
[01:51:31] suspect a little bit of mild benchmaxing
[01:51:33] by meta on on this meta spark 1.1 is on
[01:51:38] if you believe the ai
[01:51:40] cost frontier analysis it is on the
[01:51:43] optimal cost frontier but it's not at
[01:51:46] the top so if it's beating say fable 5
[01:51:49] which barely allows you to do anything
[01:51:51] biological or GPT 5.6 which does allow
[01:51:54] you to do it. That does to me suggest uh
[01:51:56] in all honesty a little bit of mild
[01:51:58] benchmaxing but still it's it's a great
[01:52:00] day when Instagram gives better medical
[01:52:03] advice than human [clears throat]
[01:52:03] doctors.
[01:52:04] >> I think that's our that's our takeaway
[01:52:06] uh quote from the from today's pod. Um
[01:52:09] I'm going to uh move us to one more
[01:52:11] longevity story that I love. This is
[01:52:13] breaking news from yesterday. Uh and it
[01:52:16] really got me excited here. I know you
[01:52:18] Alex and I were talking about this. So
[01:52:20] for for decades, one of the fundamental
[01:52:22] problems of aging uh is the slow
[01:52:25] accumulation of of what are called
[01:52:28] advanced glycation end products. I love
[01:52:30] the acronym. It's called ages. A ge
[01:52:33] uh and these are sugar molecules that
[01:52:35] cross link and damage your proteins in
[01:52:38] your body over the course of time. So
[01:52:40] this chemical reaction is called
[01:52:41] glycation. And it happens slowly in our
[01:52:44] bodies as we age. It stiffens your
[01:52:45] arteries. It clouds your lenses with
[01:52:47] cataracts. It damages kidneys. wrinkled
[01:52:49] skins. And this idea uh is that it's
[01:52:53] always been irreversible until this
[01:52:56] week. And yesterday in Nature
[01:52:57] Communications, a team from a new
[01:52:59] startup called Revel Pharmaceuticals
[01:53:01] demonstrated an engineered enzyme called
[01:53:04] CMLA uh that acts like a molecular lawn
[01:53:07] mower. I love their description. A
[01:53:08] molecular lawn mower. It oxidizes away
[01:53:10] the glycation scars and restores the
[01:53:13] original healthy protein underneath. And
[01:53:16] amazingly, this isn't happening just in
[01:53:18] a test tube. They showed it worked in
[01:53:21] human tissue samples from elderly
[01:53:23] donors, reversing damage that
[01:53:25] accumulated over the lifetime. It's
[01:53:27] still early, but the significance of
[01:53:29] this cannot be overstated. A category in
[01:53:32] aging that we've always filed as
[01:53:34] permanent just became reversible. Um and
[01:53:39] again we talk about longevity escape
[01:53:41] velocity we talk about you know our
[01:53:43] ability to understand the 5 billion
[01:53:45] chemical reactions per second per cell
[01:53:48] in your 40 trillion cells and when we
[01:53:51] talk about reaching lev you know escape
[01:53:54] velocity by 2033 it's tech like this so
[01:53:57] congrats to uh to Revel um in in doing
[01:54:00] this
[01:54:01] >> and and not just Revel I mean a couple
[01:54:04] of interesting notes here it was Revel
[01:54:06] and Calico the California Life Company
[01:54:10] that was one of the one of the alphabet
[01:54:12] other bets that's been I would say like
[01:54:15] a lot quieter than say Whimo. Uh they're
[01:54:18] still doing work that that's very
[01:54:20] encouraging to me that Calico is
[01:54:22] apparently deeply involved in this and
[01:54:24] and has a heartbeat. A couple of other
[01:54:26] points the the broader process here
[01:54:28] class of chemical reactions are called
[01:54:31] Mayard reactions. It's also the reason
[01:54:33] why when you bake bread the the outer
[01:54:35] crust is usually brown or chemical
[01:54:39] >> or yeah or or it's why this is
[01:54:41] vegetarian speaking why everything
[01:54:43] purportedly tastes like chicken. Uh it's
[01:54:45] the same class of reactions but the the
[01:54:47] sugar is reacting with uh the carbonial
[01:54:50] um functional group or carbonial uh uh
[01:54:53] groups within sugars reacting with um
[01:54:56] with the amines in in proteins to to
[01:54:59] create broad class of molecules that
[01:55:01] that look optically brown. So the same
[01:55:03] thing is going on in the human body. To
[01:55:05] to me this is very exciting because it's
[01:55:07] not quite unscrambling eggs but it's it
[01:55:10] it's halfway there. It's it feels almost
[01:55:12] it again strictly speaking it's not like
[01:55:15] uh reversal of the thermodynamic arrow
[01:55:17] of time but it's the next best thing if
[01:55:19] if we can remove all of these uh
[01:55:22] unwanted sugar plus protein byproducts
[01:55:26] that are associated with inflammation
[01:55:28] and and other coralates of aging with uh
[01:55:32] directed evolution of uh of a protein
[01:55:35] that came from bacteria. Like what else
[01:55:37] is there out there in the biosphere for
[01:55:39] us to mine in addition to all the
[01:55:41] obvious glip ones? Great potential for
[01:55:44] uh longevity, escape velocity. What
[01:55:46] other bacterial innovations can we use
[01:55:48] to turn back agent?
[01:55:50] >> It's human engineering. We're taking
[01:55:51] control. It's going from evolution by
[01:55:53] natural selection to evolution by human
[01:55:55] direction. And I love that.
[01:55:58] >> I'll be I'll be happy when I have
[01:55:59] Ramine's hair. [laughter]
[01:56:01] >> That's when I'll be happy.
[01:56:02] >> Well, there are lots of companies
[01:56:03] working on that, Sem. So gentlemen, uh
[01:56:06] grateful for our time today. I'm excited
[01:56:09] for Starship 13 launch later today. Wish
[01:56:13] Elon and the the group there uh lots of
[01:56:16] luck. Uh Reine, congrats on the success
[01:56:19] of Liquid AI and and excited to have you
[01:56:22] on the pod with us. Dave, great move
[01:56:24] investing in Reine. Um
[01:56:27] >> on behalf of all of our
[01:56:30] Thank you.
[01:56:30] >> Yeah, gentlemen. Have an amazing week.
[01:56:33] I'm I'm sure we'll be having an
[01:56:34] emergency pod very soon because the
[01:56:37] speed of the singularity waits for
[01:56:38] nobody.
[01:56:43] [music]
