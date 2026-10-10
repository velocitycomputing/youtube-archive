---
video_id: 1cSNE-ZkDLQ
title: "You Can't Compete on Cheap Models Anymore"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=1cSNE-ZkDLQ"
watched_date: 2026-07-05
watched_at: "2026-07-05T12:00:00Z"
watch_count: 1
duration_seconds: 939
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 42
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 939
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker argues that the apparent sameness in AI outputs stems not from tool limitations but from a shift in where value lies. Using Mitchell Hashimoto's experiments as the centerpiece, he shows how cheap models ($1) now match expensive frontier models ($9) on routine tasks, yet frontier models excel at novel problems that cheaper alternatives cannot handle. The core insight: as execution becomes commoditized, value has moved to *imagination*—the ability to identify new problems worth solving that weren't previously on anyone's task list. He illustrates this with examples like using Fable 5 to identify unshaded porches in specific geographic regions for hyper-targeted marketing, work that wouldn't have been possible before. He also parallels the shift to factory electrification: the real productivity gains came not from motors themselves but from people reimagining factory layouts around what distributed power made possible.

To capitalize on this shift, allocate dedicated "scouting time" to explore frontier models and discover new capabilities rather than just running existing tasks cheaper. Build infrastructure (verification systems, review processes, team structures) *before* you need to execute at scale, and critically, ensure people with deep domain context have permission and tools to pose exploratory questions to frontier models without bureaucratic friction—that's your imagination engine. The diagnostic: who on your team can pose a $400 question to a model without approval? If the answer is nobody or a tiny number, you have an imagination constraint, not a model cost problem. Use cheap models for daily execution optimization, but reserve frontier models for questions that fundamentally change what your execution layer should be building.

## Transcript

[00:00:00] Here's something strange that everyone
[00:00:01] using AI is noticing right around the
[00:00:04] same time. The tools keep getting
[00:00:06] better. The prices keep dropping. You
[00:00:08] can produce more than ever and yet
[00:00:10] somehow everything's starting to feel
[00:00:13] the same. Your output, your competitors
[00:00:15] output, half of what's in your feed all
[00:00:16] looks really similar, right? Better
[00:00:18] tools, samey results. That's not a
[00:00:21] coincidence and it's actually not a
[00:00:22] tooling problem. Something specific
[00:00:25] happened. AI made doing things cheap and
[00:00:28] whenever execution gets cheap the value
[00:00:30] doesn't disappear, it just moves. I'm
[00:00:32] going to show you exactly where it moved
[00:00:34] with a true story about an engineer, 40
[00:00:37] bucks, and a task that no to-do list on
[00:00:40] the planet had captured. By the end of
[00:00:41] this video, you'll know which side of
[00:00:43] that move you're on and how to switch.
[00:00:45] Okay, let's set the scene. Mitchell
[00:00:47] Hashimoto, co-founder of HashiCorp,
[00:00:49] creator of the Ghost U terminal, one of
[00:00:51] the most respected engineers working out
[00:00:53] there today. When Fable 5 launched, the
[00:00:55] current frontier model, the one that
[00:00:56] everyone complains about the price on,
[00:00:58] he spent days testing it against cheaper
[00:01:01] models on ordinary work. Implement this
[00:01:03] feature or build this thing, the stuff
[00:01:04] on everybody's list.
[00:01:06] And honestly, all three models that he
[00:01:08] tested produced equally acceptable
[00:01:10] output. The budget model cost under a
[00:01:11] buck and finished in minutes. GPT 5.5
[00:01:14] about a buck 50 and Fable 5 cost 40
[00:01:18] minutes and $9, right? Same work, same
[00:01:20] quality, 9x more expensive. If you stop
[00:01:23] there, Fable 5 looks like a rip-off,
[00:01:25] right? And a lot of people are stopping
[00:01:27] there because that result launched a
[00:01:28] thousand hot takes about how you should
[00:01:30] route everything to cheap models. And
[00:01:32] you know what? You should route a lot of
[00:01:34] execution to cheap models. I think that
[00:01:35] makes sense. But here's where I want to
[00:01:38] call something out that no one seems to
[00:01:40] be saying enough because part of my job
[00:01:42] is to look out ahead.
[00:01:44] When everyone in AI is saying the same
[00:01:46] thing at the same time, and right now
[00:01:47] everyone is saying route to cheaper
[00:01:49] models, that's exactly when I start
[00:01:51] asking a different question. Where does
[00:01:53] value move once we've all figured this
[00:01:55] out? Routing is real. It's also about to
[00:01:58] be table stakes. Everyone's going to
[00:01:59] have it. Execution is commoditizing real
[00:02:02] fast. So, the question that matters
[00:02:04] isn't the one the whole industry is
[00:02:05] answering right now. It's the one hiding
[00:02:08] in the second half of Hashimoto's
[00:02:10] experiment. Because Hashimoto ran one
[00:02:12] more test. He handed the Frontier model
[00:02:14] a problem that the cheap ones couldn't
[00:02:16] touch at all. Optimizing a gnarly piece
[00:02:18] of systems code that he'd written
[00:02:19] himself. It took 2 hours, cost 40 bucks,
[00:02:22] and it reached a level of performance
[00:02:24] that Hashi moto, again, one of the best
[00:02:27] engineers in the world at exactly this,
[00:02:29] says he couldn't have hit on his own.
[00:02:30] Now, this is the question I want you to
[00:02:33] wrestle with in this video.
[00:02:34] Who assigned that task? It wasn't on a
[00:02:37] backlog. It wasn't in a sprint. No PM
[00:02:40] prioritized it. It didn't exist as a
[00:02:42] task until one person, an expert,
[00:02:45] suspected something new had become
[00:02:47] possible and spent money trying to find
[00:02:49] out. No individual process generates
[00:02:51] this task. No best practices guide is
[00:02:53] going to contain a task like this. It
[00:02:56] comes from somewhere else. AI can only
[00:02:58] do work that someone has imagined. These
[00:03:01] cheap coding tools, they execute, but
[00:03:03] they don't decide what's worth
[00:03:05] executing. Which means the ceiling on
[00:03:07] what AI is worth to you was never the
[00:03:10] model or the price or the prompt pack or
[00:03:12] whatever you're depending on in your
[00:03:14] harness. It's the size of your list of
[00:03:16] things you know how to ask for. It's
[00:03:18] your imagination. And let me be careful
[00:03:20] here, because this is not a video about
[00:03:22] how execution doesn't matter. Execution
[00:03:25] matters enormously. It is the thing that
[00:03:28] gets multiplied by imagination.
[00:03:30] Hashimoto's 40-buck job still needed 2
[00:03:32] hours of world-class model execution to
[00:03:34] become real. The point is about what
[00:03:36] sets that multiplier. It's a smart move,
[00:03:39] and you should keep making that move
[00:03:41] aggressively. It's a layer where you can
[00:03:42] control costs, you can keep driving them
[00:03:44] down, and that control is all yours.
[00:03:46] That is why Hashimoto ran an under a
[00:03:48] dollar GLM 5.2 run in his initial test.
[00:03:51] The mistake would be treating that layer
[00:03:52] as the whole strategy. The leverage
[00:03:54] comes from what you put on top of a
[00:03:57] strong execution strategy. You need a
[00:03:59] targeted surgical application of
[00:04:01] frontier models to the questions that
[00:04:04] change what the execution layer is even
[00:04:07] building, right? Cheap open execution is
[00:04:10] a great engine. Frontier imagination is
[00:04:12] where you steer the plane. You need
[00:04:14] both, right? They're not in competition.
[00:04:16] The cheaper your execution layer gets,
[00:04:18] the more commoditized it gets and
[00:04:20] therefore the more valuable every
[00:04:22] frontier post question becomes. And that
[00:04:25] explains the strange thing that I called
[00:04:27] out at the top of this video. Look at
[00:04:28] the first half of Hashimoto's
[00:04:30] experiments again. Cheap model ties
[00:04:33] expensive model. That's not a fact about
[00:04:36] the models. It's a fact about the task.
[00:04:39] Implement this feature is work everyone
[00:04:41] already knows how to ask for. And the
[00:04:44] work everyone knows how to ask for is
[00:04:46] exactly where the models have converged.
[00:04:48] And that's why a one buck model ties a
[00:04:51] nine buck model. Now, let's zoom the
[00:04:52] lens out from models to people. The
[00:04:54] prompts we use are often shared. The
[00:04:56] playbooks are often public. Many of us
[00:04:58] are following the same productivity
[00:05:00] channels. So, when you and a million
[00:05:02] other people run the same tasks across
[00:05:04] the same tools, of course the results
[00:05:07] are going to converge. And that's fine
[00:05:08] if you want similar quality at a cheap
[00:05:12] execution price. But AI is not
[00:05:14] responsible for making our work outputs
[00:05:16] generic. Instead, it just reveals that
[00:05:19] differentiation is hard and that it's a
[00:05:21] human task. Now, we've watched this
[00:05:23] exact dynamic decide a market before.
[00:05:26] Blackberry and Apple both made
[00:05:28] smartphones and Blackberry executed on
[00:05:30] those smartphones brilliantly. It had
[00:05:32] the best keyboard in the world, the best
[00:05:34] email, the best security, and the market
[00:05:36] leadership to prove it. But what killed
[00:05:38] Blackberry was not an execution failure.
[00:05:41] It was executing superbly inside a
[00:05:43] category everyone had already imagined.
[00:05:46] While Apple and Steve imagined a
[00:05:48] different answer to what a phone even
[00:05:50] was and then executed on that. So, same
[00:05:52] industry, comparable execution muscle,
[00:05:55] and imagination set the multiplier. One
[00:05:58] company's execution became worth a
[00:05:59] hundred times the others. That's the
[00:06:01] divergence, and it starts exactly where
[00:06:03] the known list of execution tasks ends.
[00:06:07] And that's where the models still
[00:06:08] separate, and much more importantly, is
[00:06:10] where people will separate. The $40 job
[00:06:13] had no competition. Nobody else was
[00:06:15] doing what Hashimoto because nobody else
[00:06:18] had thought of it. So, here's the test,
[00:06:20] and it works for a person as well as a
[00:06:22] company. Has your task list changed in
[00:06:25] the last 12 months? In the last six? In
[00:06:27] the last three? Has what you have asked
[00:06:29] AI to do shifted? Or are you doing your
[00:06:32] old list faster and cheaper and calling
[00:06:35] that AI transformation? Because if it's
[00:06:36] the old list, nothing is wrong with your
[00:06:39] tools. You have an imagination shortage,
[00:06:42] and you're going to be spending a lot on
[00:06:43] optimizing for execution in a
[00:06:45] commoditized market. But the good news
[00:06:47] is that imagination is not what you
[00:06:49] think it is because the word imagination
[00:06:51] gets overused. It sounds like a gift,
[00:06:53] something that artists have and analysts
[00:06:55] don't. That's not what was operating in
[00:06:57] the $40 story, and it's not what's
[00:06:59] scarce. Hashimoto could pose that
[00:07:02] question because he has hundreds or
[00:07:04] thousands of hours inside these models.
[00:07:06] He knows where the capability line has
[00:07:08] moved, not from a benchmark chart, but
[00:07:10] from instinct, from touch. You can't
[00:07:12] imagine with capabilities you haven't
[00:07:14] touched. Nobody imagines a use for a
[00:07:16] tool they've read a summary of, right?
[00:07:19] And And this is where most of us quietly
[00:07:21] sabotage ourselves. We interact with AI,
[00:07:23] and we have cost savings in the back of
[00:07:25] our heads, or we have a defined task
[00:07:28] list that we expect AI to do. We wonder
[00:07:30] if AI can help us go faster or cheaper.
[00:07:33] It's like pointing the telescope at the
[00:07:34] ground. It's pointing at a work you
[00:07:36] already have. The questions that find
[00:07:38] new territory to explore are different.
[00:07:40] You're asking, "What can this do that
[00:07:42] I've never been able to even ask before.
[00:07:46] And I'm going to give you an example
[00:07:47] from Fable 5 here. Uh this is a real
[00:07:49] example. I found it on X. I love this
[00:07:51] one. You can get Fable 5 to use Google
[00:07:55] Maps and to map all of the porches in a
[00:07:59] geographic area that are unshaded, that
[00:08:02] get all-day daylight in an area where
[00:08:05] average temperatures in the summer cross
[00:08:07] a certain degree threshold. When you do
[00:08:10] that, you can then go through, find
[00:08:12] those properties, get a
[00:08:13] three-dimensional model of the structure
[00:08:15] on Google Maps,
[00:08:17] and then mail those individuals a custom
[00:08:21] card offering them a covered porch with
[00:08:25] specific data on their porch, their
[00:08:26] situation, a specific visual of how
[00:08:29] their porch actually would look when
[00:08:32] built. All of that powered by Fable 5.
[00:08:34] And if you're wondering, can I get a
[00:08:36] cheaper model to execute some of that?
[00:08:38] 100% once the idea is prototyped through
[00:08:41] with Fable 5, you can. But combining all
[00:08:44] of those tasks together, running them
[00:08:45] through Blender, through other tools,
[00:08:47] managing the whole thing, and
[00:08:49] critically, being able to do both the
[00:08:52] spatial and logical reasoning, and then
[00:08:54] translating it all into a business flow
[00:08:56] with an address table, that's an example
[00:08:59] of something that is business-oriented
[00:09:02] as a problem. It's not like we're you
[00:09:04] know, it's not like we're solving
[00:09:06] pie-in-the-sky problems here. But it's
[00:09:08] also a really hard problem that wouldn't
[00:09:10] have been possible before. That kind of
[00:09:12] marketing is something that we are able
[00:09:15] to do now that we never would have been
[00:09:17] able to do before, and that earlier
[00:09:18] versions of model just can't get you
[00:09:21] there. Now, once you imagine it, once
[00:09:23] you see it, once you put it into action,
[00:09:25] you can start to get a cheaper pipeline
[00:09:27] put together, and you can start to move
[00:09:29] it back from the frontier into something
[00:09:31] that's simpler. Where like, for example,
[00:09:33] the merge of the image into the mailer,
[00:09:35] that doesn't take the frontier model,
[00:09:36] right? But the idea of putting that
[00:09:38] together and getting the first few
[00:09:39] houses done and getting into analysis of
[00:09:43] where the sun is and where shade is,
[00:09:45] that's frontier model stuff. That's
[00:09:47] stuff that takes imagination. Not just
[00:09:49] imagination to prompt the model. The
[00:09:51] hard part is not the prompt there. It's
[00:09:53] imagination to say a new kind of
[00:09:55] marketing is possible. I can be
[00:09:57] hyper-targeted, hyper-specific, and
[00:09:59] hyper-relevant to my customers if I can
[00:10:04] use this model to do analysis that would
[00:10:06] never have been possible otherwise. I
[00:10:08] love that example because, frankly, I
[00:10:11] could use a porch like that. I love that
[00:10:13] example because it calls out for us why
[00:10:16] frontier models matter and that they
[00:10:18] matter especially in places where we
[00:10:20] haven't even seen value yet. So, your
[00:10:22] personal practice is almost
[00:10:24] embarrassingly simple. And it maps right
[00:10:27] onto a two-layer stack. For daily
[00:10:29] execution, absolutely use cheap models,
[00:10:31] optimize away, etc. And that works at
[00:10:33] company level and it works at individual
[00:10:35] level. But where do your scouting hours
[00:10:37] go? Are you taking scouting seriously?
[00:10:39] Are you thinking about where your
[00:10:42] imagination time is going? And keep in
[00:10:44] mind, the two examples I've given,
[00:10:45] Hashimoto's example, this example around
[00:10:48] uh
[00:10:49] using sun analysis to get complicated
[00:10:51] marketing done, these are not artist
[00:10:54] type imagination tasks. They're
[00:10:56] technical, they're business imagination
[00:10:58] tasks where we look at a particular
[00:11:00] problem in a new way because we have
[00:11:02] fingertip awareness of what new models
[00:11:04] are capable of. When factories
[00:11:05] electrified, the technology worked on
[00:11:07] day one. The productivity payoff took
[00:11:09] decades because factories kept their
[00:11:12] steam era layout. Every machine crowded
[00:11:14] around one central drive shaft and just
[00:11:16] bolted an electric motor where the steam
[00:11:18] engine used to be. It was the same
[00:11:20] building, it was a new power source, and
[00:11:22] there was barely any gain. The payoff
[00:11:24] arrived when a new generation of
[00:11:26] managers exercised technical imagination
[00:11:29] and redesigned the factory around what
[00:11:31] cheap distributed motors make possible.
[00:11:33] So, the unit of change wasn't the motor.
[00:11:36] It was the building.
[00:11:38] AI is the same kind of tech and
[00:11:39] companies are making the same move.
[00:11:41] They're bolting it onto the old layout.
[00:11:43] They're running the existing task list
[00:11:44] through cheaper models and reporting on
[00:11:46] the savings. Now, the savings are real
[00:11:47] and they're available to every
[00:11:49] competitor with the same insights.
[00:11:51] They're table stakes. Here's what
[00:11:53] redesigning the building looks like when
[00:11:55] it works. Stripe reports that they ran a
[00:11:57] migration across 50 million lines of
[00:12:00] code in one day. Work estimated at two
[00:12:02] plus months for a team. The impressive
[00:12:04] number there, it's not a day. The
[00:12:06] important number is the years that
[00:12:09] Stripe spent building task coverage that
[00:12:12] could verify that many changes, review
[00:12:14] systems that could move at that speed,
[00:12:16] have people who knew how to drive the
[00:12:18] model in a complicated task like that.
[00:12:21] The model deleted two months worth of
[00:12:24] typed code, right? Two man-months of
[00:12:26] typing code. The building to accommodate
[00:12:29] that change, the structures in terms of
[00:12:31] team, in terms of review cycles to
[00:12:33] verify quality, that had been redesigned
[00:12:36] in advance. So, you could point the same
[00:12:38] model at a company that hasn't done that
[00:12:40] work in their codebase and you would not
[00:12:42] get a one-day migration. You would get
[00:12:44] 50 million lines of changes that nobody
[00:12:46] could approve. Stripe built the
[00:12:48] infrastructure first and then harvested
[00:12:50] the value with frontier models and
[00:12:53] technical imagination. And leaders, one
[00:12:55] warning because I know the shortcut
[00:12:57] you're thinking about. You can't hire
[00:12:58] your way out of this with one
[00:13:00] imaginative person. That 40 buck job
[00:13:02] needed imagination, deep context, and
[00:13:05] permission to ask in one head, Hashimoto
[00:13:07] said. And that's true as far as it goes,
[00:13:09] but your new AI visionary that you hire,
[00:13:11] if you want them to solve this kind of
[00:13:12] problem, they have all of the
[00:13:14] imagination to do that, sure, but they
[00:13:16] have none of your context. So, you need
[00:13:18] to ask yourself, do the people with the
[00:13:20] context in your company, do the people
[00:13:22] who could exercise technical imagination
[00:13:25] have the permission to do that?
[00:13:27] Do they have the tools to do that?
[00:13:29] Imagination only fires when it sits next
[00:13:32] to context. And your context is spread
[00:13:34] across everyone who actually does the
[00:13:36] work. So, the job isn't hiring
[00:13:38] imagination. It's manufacturing it. It's
[00:13:40] putting the people who have context in
[00:13:43] your systems in contact with capable
[00:13:46] models and giving them permission to
[00:13:48] make bets. And you know the test from
[00:13:50] earlier scales right up. Who on your
[00:13:52] team is allowed to pose a $400 question
[00:13:56] to a model today without asking anyone?
[00:13:58] If the answer is nobody or just a tiny
[00:14:00] number of people, that's an imagination
[00:14:02] constraint. It was never about the price
[00:14:04] of the model. One last piece of evidence
[00:14:06] that imagination is the asset and it
[00:14:08] comes from the strangest AI story of the
[00:14:10] year. A couple of weeks ago, Fable 5
[00:14:12] shipped on a Tuesday, it was gone by
[00:14:13] Friday, now it's back. Everyone's
[00:14:15] carefully optimized their model setups
[00:14:17] since, right? But look at what the
[00:14:19] blackout could not take away. The people
[00:14:22] who had spent those first 72 hours
[00:14:24] dreaming of what was possible. The
[00:14:25] questions they posed were kept, the
[00:14:27] workflows they'd redesigned were kept,
[00:14:29] and the model came back into a price
[00:14:31] war. But the people who had imagination
[00:14:34] to use the models went right back to
[00:14:36] what they were doing, imagining with
[00:14:38] Fable 5. And I've seen that all over my
[00:14:40] timeline this last few days as Fable 5
[00:14:43] has been back. This is our answer to the
[00:14:45] question of sameness. Remember how I
[00:14:47] started this video saying everything is
[00:14:48] looking the same? It was never the
[00:14:50] tools. The tools did their job, they
[00:14:52] made execution cheap, and you need to
[00:14:54] optimize for execution. Nothing in my
[00:14:56] video is saying don't do that. You got
[00:14:57] to do it. You also have to have an
[00:15:00] answer for where your 10x multiplier
[00:15:03] comes from, where your iPhone moment
[00:15:05] comes from, where Hashimoto's $40
[00:15:08] question comes from. You want to spend
[00:15:10] the frontier where it multiplies, where
[00:15:12] you have real context, real bets on the
[00:15:16] line, and real questions that exercise
[00:15:19] technical imagination around what's
[00:15:20] possible with a larger model. There is
[00:15:23] no substitute for that. Now, if you want
[00:15:25] to dive deeper, I have a deeper written
[00:15:27] version of this argument with sources,
[00:15:28] the full strike breakdown, and counter
[00:15:30] arguments all on Substack. Check it out,
[00:15:33] and I'll see you next time.
