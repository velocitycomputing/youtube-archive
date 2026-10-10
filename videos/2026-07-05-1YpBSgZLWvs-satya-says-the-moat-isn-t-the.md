---
video_id: 1YpBSgZLWvs
title: "Satya says the moat isn't the model. Is he right? | First Pass Ep. 2 with Dan Farrelly (Inngest)"
channel: Altimeter Capital
url: "https://www.youtube.com/watch?v=1YpBSgZLWvs"
watched_date: 2026-07-05
watched_at: "2026-07-05T12:00:00Z"
watch_count: 1
duration_seconds: 641
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 53
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 641
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode discusses how AI development is shifting from static prompting to autonomous loops—systems that iteratively improve themselves. Dan Farrelly breaks this into three layers: the loop (the decision-maker triggered by events), skills (the workflows it can invoke), and orchestration (the infrastructure that runs it all reliably). The core argument is that Satya Nadella's claim "the moat is the loop, not the model" is valid—success depends on building feedback systems where the model learns from its own execution, monitors its performance, and continuously improves its own tasks and goals over time, like a product team shipping, gathering feedback, and iterating.

For developers building agents: stop optimizing prompts and start building orchestration systems. You need robust infrastructure for 24/7 autonomous execution—think about failure recovery, observability, state management, and how your loop learns from its own history. Make your system "orchestration aware" so it can inspect its own logs, understand what tasks succeeded or failed, and self-modify. The real competitive advantage isn't a better base model; it's a system that compounds improvements over time by feeding execution data back into itself as training signal for better task design and execution.

## Transcript

[00:00:00] So, instead of having somebody like an
[00:00:01] engineer in the driver seat figuring out
[00:00:03] their prompt, it's more about how do I
[00:00:07] set the system up to be able to iterate
[00:00:11] on a task or goal and improve itself and
[00:00:15] just keep keep kind of rolling in set.
[00:00:21] >> Welcome back everyone to our next
[00:00:23] episode of First Pass where we aim to
[00:00:25] break down the latest trending topics in
[00:00:27] AI in short, quick, digestible videos.
[00:00:30] Today we've got Dan Fairely with us, the
[00:00:32] CTO and co-founder of Ingest to talk
[00:00:34] about loops, which is the thing
[00:00:37] everyone's talking about who's building
[00:00:38] agents. Dan, thanks for being with us
[00:00:40] today.
[00:00:40] >> Thanks, guys. Appreciate it.
[00:00:42] >> Awesome. Well, look, no one's talking
[00:00:43] about prompting anymore. Everyone's
[00:00:45] talking about writing loops, setting
[00:00:47] goal functions, letting agents iterate
[00:00:49] across themselves.
[00:00:51] Break this down for us. Like, what is is
[00:00:53] prompting dead? What is a loop?
[00:00:55] >> Yeah, so, you know, it's a buzzy thing
[00:00:57] right now and I think
[00:00:59] what it's useful to look at like just
[00:01:00] what you talked about, right?
[00:01:02] Uh
[00:01:03] in the in the early days of LLMs, people
[00:01:05] just talked about prompting and getting
[00:01:06] a response, right? These one shots. And
[00:01:08] then we started moving towards
[00:01:10] agents, right? Prompting the agent, the
[00:01:12] agent's doing some some things in a
[00:01:13] loop, not to be too confusing, but
[00:01:17] you think about still prompting. What am
[00:01:19] I giving to the agent to get my outcome,
[00:01:21] right? And I think what this recent
[00:01:23] shift towards loops is actually talking
[00:01:25] about things that at a higher level. So,
[00:01:28] how am I setting a higher level goal
[00:01:30] that a system, and that could be agents
[00:01:32] or different tasks, uh to complete that.
[00:01:35] So, it is like a a loop supervising
[00:01:37] loops in that sense.
[00:01:39] So, instead of having somebody like an
[00:01:41] engineer in the driver seat figuring out
[00:01:43] their prompt, it's more about how do I
[00:01:46] set the system up to be able to iterate
[00:01:51] on
[00:01:52] a task or goal and improve itself and
[00:01:55] just keep keep kind of rolling in say
[00:01:57] >> Will you break down the loop into three
[00:01:59] layers? The loop, the skill, and the
[00:02:01] orchestration. Would you walk us through
[00:02:03] each one?
[00:02:04] >> Yeah. Yeah, so I think what's
[00:02:06] interesting about it is that, you know,
[00:02:08] when you take this concept of loops
[00:02:10] outside of coding agents, you know,
[00:02:11] locally and you put it in production
[00:02:13] systems, it kind of means that um it has
[00:02:17] to the system has to run in a loop, it
[00:02:19] has to take the state of a
[00:02:21] of the system of whatever the goal of of
[00:02:24] the the loop is and it needs to act upon
[00:02:27] that, right? So, I think it's useful to
[00:02:28] think about these like kind of three
[00:02:30] components in the system.
[00:02:32] And one is the loop, right? That's like
[00:02:34] the decision maker, right? There's a
[00:02:36] trigger, could be a schedule, could be
[00:02:38] an event, and it needs to
[00:02:41] do do I said, it takes the inventory of
[00:02:43] what's going on, it pass into an LM and
[00:02:46] it decides, what do I do right now,
[00:02:48] right? And it continuously runs.
[00:02:50] And then when you can think about the
[00:02:52] skills, and the skills are what can it
[00:02:55] do,
[00:02:56] right? And I think this is where like in
[00:02:57] the thinking about it like a system,
[00:03:00] um these skills and not to be confused
[00:03:02] with agent skills, that's a whole other
[00:03:03] thing, it's a little confusing. I don't
[00:03:05] think we've settled upon these terms
[00:03:06] yet, but
[00:03:08] the skill itself is a workflow or a task
[00:03:11] or something higher level or a sub-agent
[00:03:13] or something that it can invoke to
[00:03:16] perform these ta- to to like, you know,
[00:03:18] work in the system.
[00:03:20] And then the
[00:03:23] orchestrator itself is basically like
[00:03:25] the brain of the system is how does the
[00:03:29] the loop actually invoke things, right?
[00:03:31] How does it call upon a skill, how does
[00:03:33] it check that the skill complete, how
[00:03:35] did it make sure that something's
[00:03:36] running, how did it run it on time,
[00:03:39] um and I think what's interesting about
[00:03:41] that is like the orchestrator is the
[00:03:44] kind of the foundational layer that
[00:03:46] that you just kind of expect to be
[00:03:48] invisible, you expect it to just work,
[00:03:51] but there's a lot that's going on there
[00:03:53] when it comes to a loop in a system is
[00:03:55] it's heavily based on this loop needs to
[00:03:57] run consistently, it needs to run
[00:03:59] durably, and it needs to be able to call
[00:04:02] upon these skills or do different tasks
[00:04:05] all the time 24 hours a day.
[00:04:07] Cuz it's basically like at that point
[00:04:08] you're you're building an autonomous
[00:04:10] system.
[00:04:11] >> It's clear that loops are becoming a
[00:04:12] more and more important part of a Gen 10
[00:04:14] architectures.
[00:04:16] But what you argue is it's not just a
[00:04:17] loop, it's what runs the loop. What do
[00:04:19] you mean by that?
[00:04:20] >> Yeah, so I I think that there's been a
[00:04:22] lot of folks recently as they've been
[00:04:24] talking about this topic that have
[00:04:25] talked about what is the loop, right?
[00:04:27] What is the pattern? What are the
[00:04:28] components? But I don't think that
[00:04:31] enough people are talking about how that
[00:04:33] actually runs the loop effectively,
[00:04:35] right? It's it's about the the system
[00:04:38] itself. And I think it shifts because
[00:04:41] teams need to stop and not necessarily
[00:04:43] focusing so much on like the model
[00:04:44] itself and start thinking about the
[00:04:46] system that runs the model, right? The
[00:04:49] whole system that that is encapsulating
[00:04:51] this. You know, what triggers the loop?
[00:04:53] When does it run? Uh what state is it
[00:04:55] evaluating? Uh what skills or other
[00:04:58] functions or agents is it invoking? Um
[00:05:01] how does it recover from failure? So I
[00:05:03] think it in those situations, you know,
[00:05:06] in my opinion, there's not enough people
[00:05:08] talking about that what are the
[00:05:10] requirements of of of what it needs to
[00:05:12] be capable of, right? The the the
[00:05:14] orchestration layer and how does it say
[00:05:18] deploy code? How does it execute
[00:05:19] something that runs something? How does
[00:05:21] it self-improve? How does it go right
[00:05:23] and iterate on these skills and improve
[00:05:25] its own system? How does it look back at
[00:05:27] history and understand what I do in the
[00:05:29] last 7 days? Did I complete this task?
[00:05:31] Did I perform it well? And I think that
[00:05:34] is a more when you shift the whole thing
[00:05:37] a layer deeper, which is like that whole
[00:05:39] system thinking side of things. And I
[00:05:41] think that's where there's a lot more
[00:05:44] interesting problems to solve, and
[00:05:46] there's I think a a lot of uh
[00:05:48] uh there's not as many people, I think,
[00:05:50] digging into that right now.
[00:05:52] >> Yeah, I mean, in in in many ways, like
[00:05:53] when I hearing you talk about this, when
[00:05:55] I think of loops, I I almost think of
[00:05:56] workflow on steroids or just uh
[00:05:59] autonomous workflows, where hey, in the
[00:06:01] past, when you had a workflow, you
[00:06:03] needed to manage state, you needed
[00:06:05] needed to manage retries and failovers.
[00:06:08] And there there's kind of like a a
[00:06:09] universe of things that you needed to
[00:06:12] manage. With a loop, that's running
[00:06:14] autonomous autonomously with kind of
[00:06:16] some end goal, the challenge the
[00:06:19] challenges become a lot harder than
[00:06:21] just, "Hey, how do I handle retries? How
[00:06:24] do I handle failovers? How long should I
[00:06:26] let a task run before I put it into a
[00:06:29] failure state?" It's And this might be
[00:06:31] in the middle of the night at 4:00 a.m.
[00:06:32] when you're sleeping, so you really want
[00:06:34] to have these things defined. How do you
[00:06:36] think about a new problem space or a new
[00:06:39] set of challenges that emerge in these
[00:06:41] loop architectures? And you've kind of
[00:06:42] hinted at it on like, "Hey, we need new
[00:06:44] things. It needs to be different." But
[00:06:46] you maybe make it a little concrete.
[00:06:47] Like, what what challenges do developers
[00:06:50] run into when building loops, and how
[00:06:52] should we think about solving those
[00:06:53] challenges?
[00:06:54] >> It becomes because there's a lot more,
[00:06:56] like, the loop has to execute a lot of
[00:06:58] different tasks and is doing a lot more
[00:07:00] on a metal level, on a higher level, I
[00:07:02] think it
[00:07:04] you have to think a little bit more
[00:07:05] about how it is executing all these
[00:07:08] different tasks, how it is managing all
[00:07:11] these different tasks, how it is
[00:07:12] improving these different tasks. Uh can
[00:07:15] the loop itself edit these things and
[00:07:17] redeploy itself, right? Or re-register
[00:07:20] these tasks within a system. How does it
[00:07:22] identify these things? Um and when this
[00:07:25] kind of comes down to this this layer,
[00:07:27] it ends up being a little bit more of
[00:07:29] thinking about, you know, how are you
[00:07:31] creating this system of which it can be
[00:07:33] successful and it can improve itself,
[00:07:36] right? It kind of shifts more closer to
[00:07:38] like this idea of instead of you
[00:07:41] delegating something to a junior
[00:07:43] engineer when you can think of a coding
[00:07:45] agent today, you're
[00:07:47] trying to create something that can
[00:07:49] replace a human in that loop, right? So,
[00:07:51] it is, you know, you're triaging
[00:07:54] the infrastructure. So, how do you run,
[00:07:56] how do you go check all the different
[00:07:58] what needs to be checked, all the
[00:07:59] different metrics, the logs, etc., and
[00:08:01] then decide, all right, given the state
[00:08:03] of the system, what do I do right now?
[00:08:04] How do I improve this? How do I do this
[00:08:06] faster? So, I think there's this whole
[00:08:08] idea of how do you learn from itself?
[00:08:11] How does it find out did this task
[00:08:14] or this this skill that I wrote, was it
[00:08:16] effective? Right? Do I have the
[00:08:18] observability? Was I able to check on
[00:08:21] did this fail? So, when you're running
[00:08:23] in the system, it needs to be able to be
[00:08:25] able to understand the system of which
[00:08:27] it's running in itself, right? So, it
[00:08:29] needs to be able to look at history, it
[00:08:32] needs to be able to invoke something, it
[00:08:35] needs to be able to kind of be
[00:08:37] orchestration aware is what I think. And
[00:08:39] I think that
[00:08:40] understanding that problem is is what
[00:08:43] will unlock the biggest capabilities for
[00:08:46] a lot of these teams designing these
[00:08:47] systems.
[00:08:48] >> Loops, it's all about a work, you know,
[00:08:49] how can we recursively make them better?
[00:08:51] >> Exactly.
[00:08:52] >> Well, on that topic, Satya says that the
[00:08:54] Mo is no longer the model, it's the
[00:08:56] loop. What's your take on that? And how
[00:08:58] should developers think about building
[00:09:00] agents with that in mind?
[00:09:01] >> It was an interesting post and it kind
[00:09:03] of really took off and I think, you
[00:09:04] know, he looked at it as like two kind
[00:09:06] of buckets of like there's human
[00:09:07] capital, right? That's judgment whatnot.
[00:09:10] And then there's token capital, what are
[00:09:11] they building and like what do you learn
[00:09:13] over the span of time, right? And I
[00:09:15] think that
[00:09:17] um
[00:09:17] when you think about these kind of
[00:09:19] systems, it's like how you're generating
[00:09:21] the feedback loop, right? And this is
[00:09:23] how like product teams
[00:09:25] exist today when you think about it.
[00:09:26] It's like you ship something, there's
[00:09:28] product, there's feedback, it comes back
[00:09:29] into the system and you iterate, you
[00:09:31] make it better, and you ship it, you
[00:09:33] ship the next thing, right? And I think
[00:09:35] what happens is like to truly
[00:09:38] um
[00:09:39] leverage the power of LLMs, I think,
[00:09:41] it's about um getting them into a way
[00:09:45] into into this loop that can improve
[00:09:48] based on all of these uh
[00:09:50] system that you set up. So, what's the
[00:09:53] signal that this workflow generated,
[00:09:55] right? Uh it's kind of more of a higher
[00:09:58] level, let me set the goals of the
[00:10:00] system and how it can evolve and grow
[00:10:02] itself. And I think that is
[00:10:06] you know, it it's feeding that capital
[00:10:08] back into the system and improving and
[00:10:10] building upon that capital over time.
[00:10:12] It's a compounding engine. And I think
[00:10:13] that's what is really interesting about
[00:10:15] it. And and I I I do agree there's some
[00:10:17] really really good valid points of of
[00:10:19] what he what he what he wrote about.
[00:10:21] >> Awesome. Well, Dan, thanks for joining
[00:10:22] us and and talking about loops. I think
[00:10:25] we're going to hear a lot more about
[00:10:26] loops over the next uh next next few
[00:10:28] months.
[00:10:29] >> Thanks, guys. Appreciate it.
[00:10:32] >> [music]
