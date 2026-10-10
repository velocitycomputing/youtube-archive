---
video_id: DzbqeO_diOQ
title: "PLANS For Fable 5: Rebuilding My /Plan Skill for Mythos Class Models"
channel: IndyDevDan
url: "https://www.youtube.com/watch?v=DzbqeO_diOQ"
watched_date: 2026-07-02
watched_at: "2026-07-02T12:00:00Z"
watch_count: 1
duration_seconds: 3769
source: youtube-history-browser
added_date: 
history_label: Thursday
history_order: 79
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 377
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker rebuilds his /plan meta skill from scratch to leverage Fable 5 and Mythos class models' enhanced planning capabilities. He argues that great planning is great engineering and that engineers must own planning rather than outsource it to AI agents. After defining the skill's properties, he designs Plan F3—a new template optimized for Mythos models that trades speed and cost for maximum performance. The format includes HTML-first output with embedded images, metadata tracking (creation/modification dates, commits, agent names, session IDs), live checklists per task and phase, Q&A sections, validation loops, and separate "existing vs. new files" sections. He treats the plan as a living artifact maintained across multiple workflows: create, update, update references, build, and image generation. Throughout, he emphasizes writing specifications upfront before involving agents, using property-based engineering to define desired outputs, and designing for three audiences simultaneously—the engineer, the team, and AI agents.

To apply this approach: adopt an upfront specification phase before delegating work to agents; list the properties and outcomes you want, then write them out in raw markdown before automation. Build templated plan formats that agents consistently mirror, structured as purpose/problem/solution + phased implementation with embedded checklists. Design for performance over speed/cost when working with capable models. Treat plans as updateable living documents with agent-maintained back and forward references. Use rich HTML and images in your specs rather than plain text, because this aids both human review and agent comprehension. Start every significant project by writing, not coding—this is where differentiation happens.

## Transcript

[00:00:00] What's up engineers? Any devdan here.
[00:00:02] Today, I'll be rewriting my plan meta
[00:00:05] skill from the ground up. Why is that?
[00:00:07] It's because the recently banned Fable
[00:00:10] five and Mythos class models enable a
[00:00:13] whole new level of planning and great
[00:00:16] planning is great engineering. Now, who
[00:00:18] cares about the plan skill? Why is
[00:00:20] planning so important? Your planning
[00:00:22] skill is one of the most important tools
[00:00:25] you and your agent [music] have. Most
[00:00:27] engineers hand this off to the model,
[00:00:29] they hand it off to their agent to
[00:00:30] coding tool, their cloud code, open
[00:00:32] code, codex, which [music] I see as a
[00:00:34] massive mistake because it assumes the
[00:00:37] model knows what you're looking [music]
[00:00:38] for. This is part of the mass
[00:00:40] deprecation of raw engineering talent
[00:00:43] and skill we're seeing across the
[00:00:45] industry. This is an example of
[00:00:47] engineers becoming too reliant on models
[00:00:50] and agents. [music] You should not
[00:00:51] outsource your thinking. You should not
[00:00:53] outsource your planning [music] because
[00:00:55] great planning is great engineering.
[00:00:58] This is going to be a slow in-depth
[00:01:00] agentic engineering dev vlog. So, if
[00:01:03] you're waiting for some get-rich-quick
[00:01:04] [music] five coding hack or a flashy
[00:01:07] multi-agent demo, it's time for you to
[00:01:09] click away. This is for agentic
[00:01:11] engineers who know [music] that knowing
[00:01:13] what their agents are doing is key for
[00:01:16] success at scale. Let's start where all
[00:01:19] the best work starts. [music]
[00:01:21] Let's think, plan, and build a
[00:01:23] next-generation Fable five and Mythos
[00:01:25] [music] class level planning skill.
[00:01:33] First things first here, we're going to
[00:01:34] spin up a brand new directory. I'm going
[00:01:36] to pull in some existing resources.
[00:01:38] [music] Uh we're just going to start
[00:01:39] from scratch here. So, I'm going to move
[00:01:40] into my projects directory. I'm going to
[00:01:42] make a new directory called [music] plan
[00:01:44] F3. And I'll explain this in a moment.
[00:01:47] We're going to break out VS [music] code
[00:01:49] here. I am no longer using cursor. For
[00:01:52] quite some time, I was using cursor for
[00:01:53] their [music] tab completion model. They
[00:01:55] have abandoned that, as far as I know,
[00:01:57] and they've gone all in on agents.
[00:01:59] [music]
[00:01:59] Everything's an agent. Everything's an
[00:02:00] agent interface. That was really the
[00:02:02] last reason I was using Cursor. The
[00:02:04] first thing I like to do when I'm
[00:02:05] building an important, critical meta
[00:02:07] skill, a [music] skill that's going to
[00:02:09] be reused over and over and over, and a
[00:02:11] skill that outputs other documents,
[00:02:14] right? [music] This is why it's a meta
[00:02:15] skill. The first thing I like to do is
[00:02:16] just write. This is probably going to
[00:02:18] surprise some engineers watching the
[00:02:20] channel. It won't surprise many [music]
[00:02:22] senior engineers. I'm just going to open
[00:02:23] up a document called raw. md and just
[00:02:25] start writing about what I'm going to
[00:02:28] do. This is going to serve as [music]
[00:02:29] context for not just my agents, but for
[00:02:31] myself as well. So, this is plan F3
[00:02:34] Mythos class planning meta skill. And
[00:02:37] plan F3 stands for [music] plans for
[00:02:41] Fable thoughts. So, that's what the F3
[00:02:43] is. It's three F's, FFF. The whole idea
[00:02:46] here is a brand new slash [music] plan
[00:02:48] F3 skill that we'll be able to use, and
[00:02:50] we take in a user prompt. This is our
[00:02:52] API. Let me go ahead and bump up the
[00:02:54] screen size here [music] a little bit.
[00:02:55] And I actually want to add one more
[00:02:56] thing here, questionable, which lets us
[00:02:59] uh kick off an interactive question
[00:03:01] session [music] with our agent. That's
[00:03:03] the API, and we're actually skipping a
[00:03:04] couple steps here. Let's go ahead and
[00:03:05] just talk about what [music] is this? As
[00:03:08] I mentioned, like great planning is
[00:03:10] great engineering. And with these brand
[00:03:12] new Mythos class models being released
[00:03:15] >> [music]
[00:03:15] >> and banned and unbanned,
[00:03:17] there is a new level of capability that
[00:03:20] is unlocked by these models. As we
[00:03:22] talked about in our previous video, the
[00:03:23] more upfront [music] investment you put
[00:03:26] into your planning, the less reviewing
[00:03:28] you have to do. And with every new
[00:03:30] Mythos class model, [music]
[00:03:32] this will become more and more true, and
[00:03:34] more capability will be in your hands,
[00:03:37] but only if you know how to extract
[00:03:39] [music] it. So, uh what is this? We are
[00:03:41] pushing against the two constraints of
[00:03:42] agentic engineering, planning and
[00:03:44] reviewing. Initial investment in a great
[00:03:47] plan is the difference
[00:03:49] >> [music]
[00:03:49] >> between a great engineer and a mid
[00:03:51] engineer. By investing
[00:03:53] more effort up front in planning,
[00:03:54] [music] we improve on both constraints.
[00:03:57] Because as mentioned, great planning is
[00:03:59] great engineering.
[00:04:01] And when you have a great plan and you
[00:04:03] communicate what you want done, you are
[00:04:05] doing less reviewing.
[00:04:07] Great planning also yields less
[00:04:09] reviewing as model capability increases.
[00:04:13] So, a lot of engineers just hand off
[00:04:15] planning [music]
[00:04:16] to their model, to their agent with no
[00:04:17] structure attached. This forces the
[00:04:20] model to work and compensate and guess
[00:04:23] at what you're looking for. It also
[00:04:25] forces your agent to coding tool. For
[00:04:27] instance, if you use Cloud Code, this
[00:04:29] {slash} plan, who knows what's happening
[00:04:31] here. You actually don't know. And
[00:04:33] that's okay for the kind of surface
[00:04:35] level results, but if you really want to
[00:04:38] agent engineer and control the results
[00:04:40] [music] end to end, you must write your
[00:04:42] planning skill, your planning prompt,
[00:04:44] your planning template. And so, let's
[00:04:46] talk about the models. We've been
[00:04:47] planning and we've been writing specs
[00:04:49] for a long time now. What's really
[00:04:50] changed here
[00:04:51] >> [music]
[00:04:51] >> is the new Mythos class models. So, the
[00:04:53] recently banned April 5 and Mythos class
[00:04:56] models unlock next level of
[00:04:59] >> [music]
[00:04:59] >> planning ability, which lets us reach
[00:05:02] new heights to specify the exact
[00:05:05] outcomes we're looking for. Something
[00:05:07] like that. You get what I'm trying to
[00:05:08] say. These new models unlock a new level
[00:05:10] of planning accuracy, [music]
[00:05:11] planning ability, which lets us specify
[00:05:14] the exact outcomes we're looking for.
[00:05:16] So, that's the idea here. And whenever
[00:05:18] you're planning, whenever you're working
[00:05:19] with agents, you're trading off three
[00:05:21] things. And I just want to make this
[00:05:22] super clear of the trade-off trifecta.
[00:05:25] We talk about this a lot on the channel.
[00:05:26] This is perf, speed, cost. This new plan
[00:05:29] template trades [music] speed and cost
[00:05:31] for optimal performance. I think this is
[00:05:34] a good mindset to be in in general
[00:05:36] [music] when you're using state of the
[00:05:37] art technology. Just make the sacrifices
[00:05:39] you need to get state of the art
[00:05:41] results. Usually that means sacrificing
[00:05:42] speed and cost. [music] So, we're
[00:05:44] spending to win here. We're not holding
[00:05:46] back. And we're spending both time and
[00:05:48] cost, and of course cost comes in the
[00:05:50] form of tokens. And yeah, just to make
[00:05:52] it super clear, cost tokens. [music]
[00:05:54] Priorities, performance greater than
[00:05:56] speed greater than equal to cost. Now we
[00:05:59] kind of understand the setup. Whatever
[00:06:01] work you're doing and whatever work I
[00:06:03] like to do, I like to just sit down and
[00:06:04] just type it out, right? Like think
[00:06:06] through why we're doing this, what we're
[00:06:08] doing. We're building a new plan skill
[00:06:10] for this new class of models that's
[00:06:13] [music] emerging. And they unlock the
[00:06:15] next level of planning ability, which
[00:06:17] lets us specify the exact outcomes we're
[00:06:19] looking for. This is the hallmark of
[00:06:21] these new state-of-the-art models. You
[00:06:22] can ask for a very specific thing, and
[00:06:25] if you know how to ask for it, if you
[00:06:26] can write [music] big enough specs,
[00:06:28] complex enough specs, if you're doing
[00:06:29] interesting enough work, these models
[00:06:31] can [music] get the job done, but only
[00:06:34] when you ask them the right way, only
[00:06:36] when you present them with the right
[00:06:38] information. So this [music] is our API.
[00:06:40] We're going to run any coding agent. I
[00:06:41] like to use the PyCoding agent, and
[00:06:43] [music] I like to use Claude code, but
[00:06:45] use your favorite, use Open Code, use
[00:06:46] Codex, use whatever. You'll notice
[00:06:48] something weird here as we start working
[00:06:49] through this. You can already see that I
[00:06:51] am actually [music] typing. I'm not
[00:06:53] talking into the work flow, I'm not
[00:06:54] having an agent do all this work for me
[00:06:56] right away, and reuse a bunch of skills.
[00:06:59] We are going to do that, we're going to
[00:07:00] of course move at the agentic speed, but
[00:07:02] only after we have the foundation up.
[00:07:04] And this is one of the ideas I wanted to
[00:07:05] bring to you here. The more you're going
[00:07:07] to be using a skill or a resource or an
[00:07:10] agent harness, the more time and
[00:07:12] investment you should be putting into
[00:07:14] it. And the plan prompt is one of the
[00:07:16] most important [music] tools you and
[00:07:18] your agents have. It details how good
[00:07:21] your results are going to be up front.
[00:07:24] As these models progress, your plans
[00:07:26] that detail the work to be done are
[00:07:28] potentially the most important context
[00:07:30] your agents can and will write and read.
[00:07:34] And so what I like to do with my work is
[00:07:37] I like to do something called
[00:07:38] property-based engineering. What I'm
[00:07:39] going to do do is we have our
[00:07:40] priorities, now we're going to jump into
[00:07:42] our property. So, let me just copy in my
[00:07:44] kind of V1 spec. If you've been
[00:07:46] following the channel, you've seen this
[00:07:48] format a million times already. I've
[00:07:50] used this prompt thousands of times.
[00:07:51] It's quite simple. We have a plan, we
[00:07:53] have our purpose at the top, we have our
[00:07:55] variables, which are just the user
[00:07:56] prompt, we have our output, some
[00:07:58] instructions, just bullet points to
[00:08:00] guide the agent. We then have our
[00:08:01] workflow. This is the step-by-step
[00:08:03] actions our agents take to get the job
[00:08:04] done. We then have the most important
[00:08:06] piece, [music] the plan format. Now,
[00:08:08] this plan format changes my results
[00:08:11] completely across every execution. So,
[00:08:13] this is not just an ordinary prompt or
[00:08:15] skill. As I mentioned, this is what's
[00:08:17] called a meta skill. It is a skill or
[00:08:20] prompt that creates another prompt or
[00:08:22] skill. And in this case, we have
[00:08:24] templated our engineering into this plan
[00:08:26] format. These are the same ideas we've
[00:08:28] been talking about on the channel for a
[00:08:29] year now. They're still equally as
[00:08:31] relevant because the information system
[00:08:33] around them has not changed. It's only
[00:08:35] that we can push this plan format, as
[00:08:37] you'll see in this video, a lot further.
[00:08:39] You can just see this, you know, I have
[00:08:40] created a dedicated format, and [music]
[00:08:43] the model must do two things. It must
[00:08:45] fill in the template sections, and then
[00:08:47] it must leave everything that's not
[00:08:48] templated where it is. So, what this
[00:08:50] does is, it's going to give us this
[00:08:52] exact format. [music] And this is what
[00:08:54] it really means to template your
[00:08:55] engineering. We're teaching the agent
[00:08:56] how we engineer. So, this is the V1
[00:08:59] plan. I wrote this spec over a year ago
[00:09:01] now, and it's paid me dividends and
[00:09:04] dividends and dividends. Of course, I
[00:09:05] have enhanced versions, I've created
[00:09:07] some YAML specs, I've created some HTML
[00:09:09] specs, [music] some image-based specs,
[00:09:11] but this is the core format. 80% of this
[00:09:14] has not changed, and today we're going
[00:09:15] to enhance it for the [music] new Mythos
[00:09:18] class level models to get more value out
[00:09:20] of our plans. And so, what are the
[00:09:22] properties we want this new plan to
[00:09:24] have? Let's just go through this piece
[00:09:26] by piece, and then we'll order it. This
[00:09:27] is going to be the structure that makes
[00:09:29] up our new plan template, the format
[00:09:32] that our agent is going to reproduce
[00:09:33] over and over and over to to us that
[00:09:35] consistent set of results. So, uh let's
[00:09:38] just talk about the properties really
[00:09:39] briefly here. I'm just going to say to
[00:09:40] capture intelligence sealing of Mythos
[00:09:43] class models, we need to improve our
[00:09:46] planned skill / template to have
[00:09:48] specific properties, aka sections. It's
[00:09:51] always important to talk about your
[00:09:52] audience. So, the output of our plan
[00:09:55] will be created, updated, and consumed
[00:09:58] by the agent drive factor. And this is
[00:10:00] the audience for who we're building
[00:10:02] everything for now, which is the
[00:10:04] engineer, so your I, the engineering
[00:10:06] team, so all your co-workers, and then
[00:10:08] finally AI agents. So, this is who we're
[00:10:10] building for. And it's important to know
[00:10:12] who's reading this because a lot of
[00:10:13] engineers using the technology, they're
[00:10:15] just building for the AI agents. Others
[00:10:17] are over-indexing on their engineering
[00:10:20] team. Others are over-indexing on
[00:10:22] themselves. It's important to emphasize
[00:10:23] that this is for the trifecta. It's for
[00:10:25] you, it's for your engineering team, and
[00:10:27] it's for your AI agents. And we'll just
[00:10:29] make that super clear. So, let's list
[00:10:30] our property. So, what do we want inside
[00:10:33] of this plan format? What are we putting
[00:10:34] in plan F3 [music] skill, plans for
[00:10:37] Fable 5. Let's just walk through it. So,
[00:10:39] I've been thinking about this for a
[00:10:40] while. I'm really happy to be taking
[00:10:42] some time [music] with you to kind of
[00:10:43] walk through this process. My spec
[00:10:45] prompt and its variants [music] have
[00:10:47] been super, super valuable, but they
[00:10:49] haven't really changed that much. Here,
[00:10:50] we're going to update it for this new
[00:10:53] class of [music] models, the Mythos
[00:10:54] class models, Fable 5 being the first
[00:10:56] one of them. The whole idea here is we
[00:10:58] can really push the token usage of these
[00:11:00] models. The way we're thinking about
[00:11:02] this is we're not worried about tokens,
[00:11:04] not worried about speed. We want
[00:11:05] performance over everything. I want the
[00:11:07] best possible plans. I want the agent to
[00:11:09] internalize every single fact about the
[00:11:12] codebase, about the work, about the
[00:11:14] upcoming spec that we're writing. Let's
[00:11:16] just think through like, what is the
[00:11:17] best possible version of that from first
[00:11:20] principles? How can we spend tokens to
[00:11:23] get the best possible results? We're
[00:11:25] scaling our compute to scale our impact.
[00:11:27] So, let's think through these sections.
[00:11:29] I want a embedded checklist per task and
[00:11:33] per phase. And before that, we'll want a
[00:11:35] per phase and per task per phase
[00:11:39] breakdown of work. So, we're using HTML
[00:11:42] again. This is going to be good for the
[00:11:44] agent trifecta, you, your engineering
[00:11:46] team, and AI agents because you'll be
[00:11:48] able to open this up and see visual rich
[00:11:50] HTML. And we also want images embedded.
[00:11:53] An image is worth a thousand words.
[00:11:54] Let's put that into action. Great great
[00:11:56] plans with images and HTML. I want to
[00:11:59] give my agents the ability to be
[00:12:00] absolutely clear on what's getting
[00:12:01] built. So, I want a questions and
[00:12:03] answers section. We want to make sure
[00:12:05] we're not over indexing to human in the
[00:12:07] loop. We're always pushing towards ZTE,
[00:12:10] zero touch engineering. We want to get
[00:12:11] out the loop, but we want to be able to
[00:12:13] step in the loop when the work isn't
[00:12:15] intense enough and when the time is
[00:12:16] right. So, I'm going to say this is
[00:12:18] togglable. I want a rich updatable
[00:12:21] header metadata. And what do I mean
[00:12:23] exactly by that? So, I want created,
[00:12:25] modified, I want commits, [music] I want
[00:12:27] the agent name, I want the session ID of
[00:12:30] that agent. I want back references and
[00:12:33] forward references. And let me make it
[00:12:35] super clear which one of these are a
[00:12:38] list because this could be potentially
[00:12:40] updated several times. So, basically
[00:12:41] everything but the created date is going
[00:12:43] to be a list, right? So, a list of
[00:12:44] modified times, a list of commits, a
[00:12:46] list of agent names, so on [music] and
[00:12:47] so forth. Great. And this is all going
[00:12:49] to be updatable header metadata. So,
[00:12:52] once again, I'm leaning on the fact that
[00:12:53] these models are becoming more
[00:12:55] intelligent, more powerful, and again,
[00:12:57] I'm not optimizing for cost here. If I
[00:13:00] was optimizing for cost, we wouldn't
[00:13:02] have images getting generated in this
[00:13:03] plan. It wouldn't be HTML first. We
[00:13:05] wouldn't add all this header metadata.
[00:13:06] But what I'm doing here is I want the
[00:13:08] best performance. I want my plans to
[00:13:10] look forward, to look backward, to
[00:13:11] existing documents. I want this agent to
[00:13:14] work and build the best possible plan.
[00:13:16] That's what we're doing here. Of course,
[00:13:17] we want [music] validation and testing
[00:13:19] sections that prevent completion [music]
[00:13:22] until done. You know, this is your
[00:13:24] classic loop that everyone's all of a
[00:13:26] sudden so obsessed with. We've been
[00:13:27] talking about this for over a year now.
[00:13:29] This is a closed-loop structure. You
[00:13:30] want your agent to have very, very clear
[00:13:32] outcomes to loop on if the work is not
[00:13:35] completed. We want our new [music]
[00:13:37] versus existing file section. Very
[00:13:39] powerful. I want synced HTML and image
[00:13:43] [music] styles. Speaking of images, I
[00:13:45] want focused images embedded. Probably
[00:13:48] have to break this down a little bit
[00:13:49] more. We'll just keep it high-level for
[00:13:50] now. Yeah, classic stuff. Purpose,
[00:13:52] problem, solution. So, let's add a
[00:13:54] little bit more detail we can move on to
[00:13:55] actually writing this new skill. So,
[00:13:58] this is all preamble, right? This is
[00:13:59] just raw information dump. I'm priming
[00:14:02] my context and I'm letting agents that
[00:14:04] will be working on this with us
[00:14:05] understand what we're doing and why
[00:14:07] we're doing it. Once again, like we're
[00:14:08] thinking. Great engineering is planning.
[00:14:11] Great engineering is thinking. What do
[00:14:13] you want to see? Why do you want to see
[00:14:15] it? What's [music] enabling this thing
[00:14:17] that you're trying to do? What are your
[00:14:18] priorities? What are you willing to give
[00:14:20] up to get the job done? Make things
[00:14:22] crystal clear in your work. And the best
[00:14:24] way to do that is just by sitting down
[00:14:26] to write.
[00:14:27] >> [music]
[00:14:27] >> Write, type. Usually, I'll have my, you
[00:14:28] know, I have a whole stack of a bunch of
[00:14:30] notebooks here. Often times, I don't
[00:14:32] even [music] start with a markdown file.
[00:14:33] I just write. Like I I literally just
[00:14:35] like write things out. Which I know is
[00:14:37] probably mind-blowing for some engineers
[00:14:39] who are like blasting off 500 agents and
[00:14:41] using [music] every framework and
[00:14:43] workflow and
[00:14:45] parallelizing scheme under the sun.
[00:14:47] That's great. I feel you. Go for that. I
[00:14:49] do think that [music] the true
[00:14:51] differentiation for engineering is this
[00:14:54] now. It is sitting down, thinking of
[00:14:56] interesting, [music] novel problems and
[00:14:58] interesting, novel solutions, and then
[00:14:59] being able to write about it clearly and
[00:15:01] concisely, and then build it with your
[00:15:03] agents and iterate with it with your
[00:15:05] agents. [music] And of course, one of
[00:15:07] the most important pieces of that that
[00:15:08] can really improve your review
[00:15:11] constraint is where it all begins. It's
[00:15:13] planning. [music] Great planning is
[00:15:15] great engineering. I'm going to say it
[00:15:16] again and again, and I want you to be
[00:15:18] tired of me saying it
[00:15:19] >> [laughter]
[00:15:20] >> by the end of this video, but, you know,
[00:15:21] I want to nail this point home. [music]
[00:15:23] The future is created by those who plan
[00:15:26] it, not those who vibe code it.
[00:15:27] >> [laughter]
[00:15:28] >> And I know this is probably
[00:15:29] controversial. Don't care. That's how it
[00:15:31] is. What I'm going to do here is just do
[00:15:32] a quick ordering. So, I just want to
[00:15:33] order the sections and mention to the
[00:15:35] agent this will roughly be the new
[00:15:38] prompt template for the new plan F3 meta
[00:15:42] skill. We want our headers come to the
[00:15:45] top. Purpose, problem, solution comes
[00:15:46] next. I'll just be super clear here.
[00:15:48] Title, H1 title. We want our phases HTML
[00:15:52] [music] first. I'm just going to leave
[00:15:53] this as properties and just organize
[00:15:55] this a little bit first. Go to the
[00:15:57] bottom. Sync images [music] and style,
[00:15:59] that can go further up. Validation
[00:16:00] section, new file section. Okay, tasks
[00:16:03] here. [music] Sync. Okay, that's good
[00:16:05] enough. Let's start writing this plan.
[00:16:06] Now, we're going to boot up an agent.
[00:16:07] So, for the first time, 30 minutes for
[00:16:09] me, probably less for you. I'm going to
[00:16:10] try to cut this video down to make it as
[00:16:12] concise as possible for you. Now, we're
[00:16:13] going to start bringing agent into the
[00:16:15] picture once we have a vision. And now
[00:16:16] our agent is going to [music] help us a
[00:16:17] little bit. So, I'm going to use my meta
[00:16:19] skill. So, this is my skill that creates
[00:16:21] other skills. And I'm just [music] going
[00:16:22] to say create plan F3 as an empty uh
[00:16:26] templated [music] plan. Leave all
[00:16:28] sections blank, but include each section
[00:16:31] templated skill. This is on high
[00:16:33] thinking mode. We're running Opus 4.8.
[00:16:35] Again, hopefully by the time you're
[00:16:36] watching this, you'll have access to
[00:16:37] Fable. Really looking forward to that
[00:16:39] being re-released. The kind of noise
[00:16:42] around this has been really interesting.
[00:16:44] It looks like, you know already, right?
[00:16:45] I don't need to re-explain this or
[00:16:47] update to you. You're in the future. You
[00:16:48] probably have more information than me.
[00:16:50] interesting part here is that apparently
[00:16:52] the jailbreak isn't sophisticated.
[00:16:53] [music]
[00:16:53] This was reported to the US government
[00:16:55] by an Amazon employee, apparently the
[00:16:57] Amazon CEO. So, that doesn't look good.
[00:16:59] Someone here is either very
[00:17:01] inexperienced with what's going on, or
[00:17:03] they're just lying. I do believe here
[00:17:05] that the US government is acting a
[00:17:06] little fishy, but I don't want to say
[00:17:08] too much here. I don't want to get too
[00:17:09] political. I hate mixing engineering and
[00:17:11] politics, but um you know, we're at this
[00:17:13] really interesting place. I don't really
[00:17:14] see anything that Anthropic has done
[00:17:16] wrong here with this model. In fact, the
[00:17:18] guardrails are too strong [music] for
[00:17:20] good reason. They have good reason for
[00:17:22] this. Anyway, you'll likely have access
[00:17:23] to this by the time this video is
[00:17:25] released. If not, then things are
[00:17:27] probably getting interesting. [music]
[00:17:28] And by interesting, I mean political and
[00:17:30] annoying. So anyway, we have our new F3
[00:17:33] skill. [music] Create this locally. By
[00:17:35] default, my agent just throws this into
[00:17:37] my global directory. Right now, we just
[00:17:39] want this in our local directory just so
[00:17:41] we can see it, observe it, operate on
[00:17:43] it. There we go. So let's go ahead and
[00:17:44] crack this open. [music] So we're going
[00:17:45] to simplify a lot of this. It is
[00:17:47] definitely overdone. We have a lot of
[00:17:49] header hooks and information here. And
[00:17:51] let's just go ahead and start [music]
[00:17:53] using what we have before here. Plan F3
[00:17:56] looks good. And then we have our blank
[00:17:58] [music] sections. Okay, I'm going to say
[00:18:00] add variable section and argument hint
[00:18:04] user prompt. And we want [music]
[00:18:06] questionable. This is one of those funny
[00:18:07] cases where using Opus is complete
[00:18:10] overkill. As we talked about in our
[00:18:12] previous video with Fable 5 getting
[00:18:14] banned, that level applies to all levels
[00:18:16] of models. This is overkill for Fable.
[00:18:19] This [music] is relatively stupid work
[00:18:20] for Fable to be doing. But anyway, not
[00:18:22] super concerned about that. It's part of
[00:18:23] our subscription plan here. So we have
[00:18:25] this great write-up. Let's
[00:18:26] >> [music]
[00:18:26] >> start building this into our skill. So
[00:18:28] we have our variables. What I'm doing
[00:18:30] right now is just [music] dialing in and
[00:18:33] copying in some information from our
[00:18:34] previous specs because a lot of that
[00:18:35] upfront structure [music] is the same.
[00:18:37] So plan three, questionable, dollar sign
[00:18:40] two. Output directory is going to be, of
[00:18:42] course, that specs directory. And now we
[00:18:44] have our classic structure. Purpose goes
[00:18:46] at the top, [music] and then we have
[00:18:48] instructions. We're going to get rid of
[00:18:50] examples and report format. And we're
[00:18:51] going to focus on these key sections
[00:18:53] [music] here. I like to use QQQ as my
[00:18:56] primary search markers to jump to.
[00:18:59] [music] So we're just kind of filling
[00:19:00] that out here before we start filling in
[00:19:02] our sections. Fantastic. This is all
[00:19:05] clear. And now I want my agent to just
[00:19:06] get updated here. You know, we have a
[00:19:08] little bit of context [music] for it to
[00:19:10] work with. What we've done here by also
[00:19:12] writing out all the properties we want
[00:19:13] our system to have, we've also kind of
[00:19:14] detailed the work that needs to be
[00:19:16] [music] done. This plan format needs to
[00:19:17] be in HTML. We need an image generator,
[00:19:20] right? So, we need to pull in some type
[00:19:21] of image generation. We're going to be
[00:19:23] using Chat GPT images, [music] too. This
[00:19:25] is the best image generation model on
[00:19:27] the market right now. It gives you
[00:19:28] exactly what you're looking for. So,
[00:19:30] we're going to use that to generate our
[00:19:31] images. And then we're just going to,
[00:19:33] for all of our output plans, the thing
[00:19:35] that gets generated from our meta
[00:19:37] planning skill, we will output
[00:19:39] structured HTML. And then we have
[00:19:40] existing sections, much like our
[00:19:43] existing spec prompt. I'm just going to
[00:19:44] copy our previous version here for our
[00:19:46] purpose, and just kind of write out what
[00:19:48] this is doing. Create a detailed
[00:19:50] implementation plan based on the user's
[00:19:52] request. We're going to dial this in a
[00:19:53] little bit based on the user prompt
[00:19:56] variable. Analyze the request, think
[00:19:57] through the implementation approach, and
[00:20:00] save the output document to this. And
[00:20:03] this is workflow information, so I'm
[00:20:04] going to go ahead and cut this. And
[00:20:06] [music] there we go. Follow the
[00:20:08] instructions and work through the
[00:20:10] workflow to create the plan. Great. So,
[00:20:12] I'm going to refer to these exactly.
[00:20:14] With these powerful models, this is
[00:20:15] unnecessary, but I'm doing this not just
[00:20:17] for the agents, I'm doing it for my team
[00:20:20] and myself. So, that's the purpose of
[00:20:22] this. Create a detailed implementation
[00:20:23] plan based on the user prompt variable.
[00:20:26] This is great. Now we can go ahead and
[00:20:28] start putting through our instructions.
[00:20:30] So, the instructions are like high-level
[00:20:31] information. They'll oftentimes overlap
[00:20:33] with the workflow, so you can see here
[00:20:35] in our V1 spec, the workflow is the
[00:20:37] actual [music] steps, but the uh
[00:20:39] instructions kind of aid the steps. So,
[00:20:41] this just gives us a free-form spot
[00:20:43] [music] to work piece by piece. So,
[00:20:45] we're going to start with that. And the
[00:20:46] whole time here, as I am reusing the key
[00:20:48] pieces, updating it, I'm thinking about
[00:20:51] the next generation capability of the
[00:20:53] Mythos class models, okay? I'm thinking
[00:20:55] how far we can push [music] this, and
[00:20:57] how we want to organize the skill so
[00:20:58] that the skill is, in fact, a unified
[00:21:00] stand-alone skill. I don't like having
[00:21:02] cross-dependencies in my skills. [music]
[00:21:04] And so, we're going to have image
[00:21:05] generation, we're going to have our
[00:21:07] create workflow, and one more thing
[00:21:10] actually we should embed in our raw is
[00:21:12] our workflows. This isn't just going to
[00:21:15] be a make a new plan skill, it's also
[00:21:18] going to be our skill that updates our
[00:21:20] plans, our skill that builds the actual
[00:21:22] engineering work, and the skill that
[00:21:24] generates images. We're kind of
[00:21:25] overloading the skill a little bit to be
[00:21:27] everything related to writing this great
[00:21:29] plan for Fable 5 level models, right?
[00:21:32] For Mythos class models. So, the
[00:21:33] workflows we want to create plan, we
[00:21:35] want update plan, we want to update
[00:21:38] references because it's not all just
[00:21:40] about updating the plan. We want our
[00:21:42] agents to be treating this as an
[00:21:44] artifact, a living artifact in the code
[00:21:46] base. Agents are good enough now, we
[00:21:47] don't need to worry about them making
[00:21:48] mistakes here. They should be updating
[00:21:50] our back references. So, this plan
[00:21:52] referencing previous plans, [music] AI
[00:21:54] docs, so on and so forth, and forward
[00:21:56] references. So, when a plan in the
[00:21:58] future gets created or some AI docs in
[00:22:00] the future gets created, we want this
[00:22:02] updated. [music] And so, we need an
[00:22:03] update references workflow. We want a
[00:22:05] build plan workflow, and then image
[00:22:08] generation [music]
[00:22:08] workflow as well. Title skill. So, let's
[00:22:10] just like look through the instructions
[00:22:12] here. We want to make sure that this is
[00:22:13] still relevant. Uh we do not need task
[00:22:15] type here. Think deeply, ultra think.
[00:22:17] Remember the ultra think keyword? Back
[00:22:19] in the Cloud Code days, that was nice. I
[00:22:21] think now that actually still Take it
[00:22:23] rid of that. Okay, nice. It is still
[00:22:24] here. Maxes out thinking for that one
[00:22:26] execution. And that's fine for the plan,
[00:22:27] we do want to use maximum compute.
[00:22:29] [music] So, if we're using Cloud Code,
[00:22:30] this will kick that off. And what else
[00:22:32] here? Do we have Yeah, so we're not
[00:22:33] using periods at the end [music] here.
[00:22:34] Get rid of that. Explore code base,
[00:22:36] understand patterns, follow the plan
[00:22:38] format. Do not have plan format here.
[00:22:40] Yep. So, uh we're going to call [music]
[00:22:41] this plan template to make this super
[00:22:43] clear. And we are going to reference
[00:22:45] this section exactly. [music] Create a
[00:22:47] comprehensive implementation plan,
[00:22:48] include all the required sections, and
[00:22:51] conditional sections. I don't think we
[00:22:53] need this. We do want that. Another
[00:22:55] developer could follow it. Good code
[00:22:56] examples, pseudo code, make sense.
[00:22:58] Consider edge cases here. Yeah. Okay.
[00:23:00] So, that's good enough for the
[00:23:01] instructions. Right, we're basically
[00:23:02] just saying pay attention to the
[00:23:04] incoming prompt, research the entire
[00:23:05] code base, explore the code base,
[00:23:07] existing patterns, documentation,
[00:23:10] previous
[00:23:11] specs, architecture. And so this is
[00:23:13] like, you know, a great spot to do some
[00:23:15] customization where you would put your
[00:23:16] own workflows. And so plan format, this
[00:23:19] is the most important piece. So I'm
[00:23:21] going to start by writing this out in a
[00:23:22] markdown format just like our markdown
[00:23:25] version, right? You can see here we have
[00:23:26] a nice templated version. I'm just going
[00:23:28] to copy this in and make some changes to
[00:23:29] it. I'm going to paste this in and the
[00:23:31] plan format is what our agent is going
[00:23:33] to mirror and update. So you can see
[00:23:35] that everything inside of this is going
[00:23:37] to get templated and replaced. And so
[00:23:39] I'm going to add a bullet point here for
[00:23:40] that because I don't think that's
[00:23:41] actually clear here. And follow the
[00:23:43] [music] plan format below, okay, when
[00:23:46] dating format place everything [music]
[00:23:48] within the quest with the quest embedded
[00:23:52] inside. So this is the template
[00:23:54] instruction. We're making it super clear
[00:23:56] that this is when the agent should
[00:23:57] update this part of the prompt. This is
[00:23:59] also template or engineering versus
[00:24:01] leaving something [music] the same.
[00:24:02] Okay, so you can see here we have some
[00:24:03] conditionals. We have a list. For now,
[00:24:06] we're going to write this in markdown
[00:24:07] format so it's super clear and then
[00:24:08] we're going to have our agent, right,
[00:24:10] Opus 4.8 is going to update this
[00:24:12] structure for us into a HTML format cuz
[00:24:15] that's one of the properties we're going
[00:24:16] for, right? It's HTML first for
[00:24:18] ourselves, for our team, and for our
[00:24:19] agents. [music] And then if we go to the
[00:24:21] task here, I want to make a couple
[00:24:23] updates to this structure. So we don't
[00:24:25] have this complexity stuff anymore. So
[00:24:26] I'm going to get rid of solution
[00:24:28] approach here. We do want relevant
[00:24:29] files, but I want to write this out.
[00:24:31] [music] So this is existing files and
[00:24:35] then we don't need this. So where we
[00:24:37] want an existing file section and a new
[00:24:39] file section. List new files. [music]
[00:24:41] And again, we do not have this
[00:24:42] conditional. We are always going to have
[00:24:44] a phased [music] approach. I'm going to
[00:24:46] delete this and this kicks off our
[00:24:49] implementation phase section. And again,
[00:24:51] like we're just building up the exact
[00:24:52] format we want to see every single time
[00:24:54] for consistency and it's a great
[00:24:56] structure of how we would actually do
[00:24:58] our work, right? A phased approach,
[00:24:59] break it down into chunks, and this is
[00:25:01] great for a validation, as you'll see,
[00:25:03] in creating powerful closed loops,
[00:25:05] because every phase should be
[00:25:06] self-contained and validatable. So,
[00:25:09] we'll get there in a moment. Right now,
[00:25:10] we have phase one foundation. I actually
[00:25:12] want to break this up. So, this is a
[00:25:15] phase one name. I don't want to over
[00:25:16] prescribe what the agent should do here.
[00:25:19] So, I'm just going to break this up.
[00:25:20] Phase three name. And I want bullet
[00:25:22] points here so that we have a live
[00:25:24] tracking. And this is, you know, one of
[00:25:26] our properties. Here we go, embedded
[00:25:27] checklist. So, you know, another
[00:25:29] property we want this to have, because
[00:25:31] our agents are just good enough now, is
[00:25:33] that this spec is a living artifact. So,
[00:25:35] our agents are updating this spec and
[00:25:37] all the work live, as it works through
[00:25:39] it. And then, these sections, we do not
[00:25:41] want these to be separate. You see we
[00:25:42] have our H2s. I want this step-by-step
[00:25:45] task under every phase. So, every phase
[00:25:47] has step-by-step tasks. Testing
[00:25:49] strategy, this is good. I actually want
[00:25:51] to keep this, [music] but get rid of
[00:25:53] that if, and then I want to move this
[00:25:55] entire step-by-step task into our phase
[00:25:58] work. Just going to paste that there.
[00:25:59] Phase one. Move this up. Implementation
[00:26:02] phases. [music] Execute every phase and
[00:26:05] sub and task step-by-step in order,
[00:26:08] [music] top to bottom. So, this is an
[00:26:09] ordered list of execution. As needed, I
[00:26:12] want n minus [music] one, and I'm going
[00:26:15] to put this in our syntax here, right?
[00:26:17] So, the agent updates this. Testing
[00:26:19] [music] strategy. Describe the testing
[00:26:21] approach, and this is also a H3. Really
[00:26:24] paying attention [music] to the H3s
[00:26:25] here. Okay, that should be okay. Yeah,
[00:26:27] we can pull this up here. Specific
[00:26:29] commands to validate [music] work, and
[00:26:31] then continue. Specific commands to
[00:26:33] validate the completion of this phase's
[00:26:37] tasks. [music] So, that's the idea.
[00:26:38] Discuss, break down how and what
[00:26:42] technology being used to test, validate
[00:26:45] work is complete. Be sure cover edge
[00:26:48] cases as applicable. Some lightweight
[00:26:51] templating here. So, now we have our
[00:26:52] testing strategy per phase, and I'll add
[00:26:54] a description here. Describe the work to
[00:26:57] be done in this phase at a mid to high
[00:27:00] level. And then we have our step-by-step
[00:27:01] tasks, which I don't think we need. So,
[00:27:04] I'm just going to get rid of this.
[00:27:05] Continue adding additional tasks. Great.
[00:27:07] Okay, so this is our phases, right? So,
[00:27:08] we just wrote out our phase structure.
[00:27:10] So, that's pretty important. And then
[00:27:11] what I'm going to say here is repeat
[00:27:14] structure from phase one. And same thing
[00:27:16] for phase three. And then, of course,
[00:27:18] we'll do the exact same thing phase n
[00:27:20] minus one, name, right? Repeat structure
[00:27:22] from phase one. So, I'm going to get rid
[00:27:24] of acceptance criteria here. We're just
[00:27:26] going to use validation commands to
[00:27:28] validate the plan is complete. Validate
[00:27:31] the work inside [music] each phase is
[00:27:33] complete. And then continue for each
[00:27:36] valuable command to prove that each
[00:27:39] phase [music] is complete. And I'll say
[00:27:41] feel free to mirror from the testing
[00:27:44] [music] task from each phase, because it
[00:27:46] will likely be the same stuff, right?
[00:27:48] And then we have a note section that
[00:27:50] that all looks good. So, we're really
[00:27:51] just thinking through the hundreds and
[00:27:53] hundreds and thousands of times we're
[00:27:54] going to be using [music] a skill like
[00:27:55] this. We want it to be crystal clear how
[00:27:58] to output the result we're looking for.
[00:28:00] Okay, so we're putting a lot of upfront
[00:28:01] investment. Again, you know, I know some
[00:28:03] engineers watching this are thinking,
[00:28:04] "Holy crap, I could have live coded that
[00:28:05] two seconds." [music] That's not what
[00:28:06] this is about. You don't get your
[00:28:08] specific results by leaning on the agent
[00:28:11] like that. Thinking through this, right?
[00:28:12] We have task description, objective. I
[00:28:14] would like a problem and solution here.
[00:28:16] [music] I think this is a cleaner
[00:28:17] approach. Describe the problem we're
[00:28:20] going to solve. And what do we want in
[00:28:22] two to four sentences? [music] This is a
[00:28:24] what I like to call a restriction. You
[00:28:26] want to be really careful with the
[00:28:27] restrictions you're placing on the
[00:28:29] model. Maybe uh it helps a lot to have a
[00:28:31] longer breakdown here. Sometimes you
[00:28:33] don't need it. I will bump this up to
[00:28:34] two to eight. And [music] clearly state
[00:28:36] what will be accomplished when the plan
[00:28:37] is complete. And I'll do the same thing.
[00:28:39] It's four sentences. And okay. Okay,
[00:28:42] that's good. [music] Problem, solution,
[00:28:43] relevant files, existing files, new
[00:28:45] files, implementation phases. So, we can
[00:28:48] break our work into phases. We do need
[00:28:50] to nest [music]
[00:28:51] our tasks just to make it dead clear
[00:28:53] here. Great. And then we repeat from
[00:28:55] phase one. Again, we're templating, but
[00:28:57] we're also talking to an intelligent
[00:28:58] model that knows how to set this up very
[00:29:00] quickly. [music] So that's good. And
[00:29:01] then validation commands. We have notes
[00:29:04] and let's go back to raw and make sure
[00:29:05] we have everything. This is going to be
[00:29:07] a good time to bring our agent into the
[00:29:09] picture because we have our structure.
[00:29:11] Just get a [music] net and I'll do a GCP
[00:29:13] main. Just make sure that we have a
[00:29:15] starting place and I'll copy in a simple
[00:29:19] get ignore file and just [music] get
[00:29:21] something committed here. We're putting
[00:29:23] in get just to roll back anything we
[00:29:25] don't like, which is unlikely to happen,
[00:29:27] but we do it anyway. And questionable, I
[00:29:29] do want to default to false for input
[00:29:31] variable here. This is looking pretty
[00:29:32] good. I will pull the workflow just to
[00:29:35] give our agent a starting place here.
[00:29:38] Analyze the requirements, parse the user
[00:29:40] prompt to understand the core problem,
[00:29:41] desired outcome, explore the code base,
[00:29:43] design solution, document plan, generate
[00:29:46] files, save, and run the report. We do
[00:29:48] not have a report anymore, so we'll say
[00:29:51] provide us some real key [music]
[00:29:52] components. Okay, that's good for now.
[00:29:53] This gives us a working skill. So now
[00:29:56] that we have a great foundation, we can
[00:29:58] start pulling in our agent to [music]
[00:30:00] speed up our vision, our foundation, and
[00:30:03] our plan for our plan for our plans.
[00:30:06] This all looks good. We are missing some
[00:30:08] sections, so why don't I do this first?
[00:30:11] Let's go [music] HTML first because this
[00:30:13] is a key upgrade. We're spending tokens
[00:30:16] to get better results and we want to
[00:30:18] communicate for us, our inch team, and
[00:30:20] our AI agent, so let's update this. So
[00:30:23] read raw, understand [music]
[00:30:25] our vision, read our previous gen spec,
[00:30:29] and our work in progress skill.md.
[00:30:32] [music]
[00:30:32] Stand by before we start.
[00:30:35] Just reading, I wanted to ingest this
[00:30:37] [music] context. And by this, we're
[00:30:39] talking about Opus 4.8 running on Cloud
[00:30:41] Code. And we are running with high
[00:30:43] effort, if you're curious. [music]
[00:30:44] I found that this is a great level for
[00:30:46] most work, probably 90% of work. If I
[00:30:48] need more intelligence, I like to bump
[00:30:50] it up to extra high. Here we go. Yep,
[00:30:52] looks great. It's starting to identify
[00:30:53] the differences. Ready to start. Let's
[00:30:55] start by updating our plan format into
[00:30:59] HTML, our plan template, let's be super
[00:31:01] clear. We need to create a new template
[00:31:04] structure. Let's use this, update the
[00:31:07] instructions, and redesign the plan
[00:31:10] template into an HTML format.
[00:31:12] So, now we're starting the upgrade
[00:31:14] process for this plan to be wielded and
[00:31:17] used by Mythos class models. You know,
[00:31:19] to be clear, nothing's stopping you from
[00:31:21] using the meta planning skill we're
[00:31:22] going to generate plan F3 on lower class
[00:31:25] models, right? There's nothing stopping
[00:31:26] you from doing that. The whole idea here
[00:31:28] is that this plan is going to be most
[00:31:29] efficient on the top-tier,
[00:31:31] state-of-the-art, Mythos level models,
[00:31:33] right? That's the whole idea. So, we're
[00:31:34] just using some really basic agent of
[00:31:36] coding. We could pretty much throw any
[00:31:38] model we want to at
[00:31:40] but for now, we're just going to keep it
[00:31:41] simple. We're going to use a single
[00:31:43] Claude code, and since we're going to
[00:31:44] walk through this while my agent's doing
[00:31:45] this, actually, let me go ahead and pull
[00:31:47] in my image generation scripts. [music]
[00:31:50] So, this is going to help us generate
[00:31:52] images and edit images with the GPT
[00:31:55] image two model. So, you can see exactly
[00:31:56] how this works. Some 200 lines as an
[00:31:58] Astral UV single file script, nice and
[00:32:00] simple. This gives our agent the ability
[00:32:02] to create and edit images. We're just
[00:32:03] going to drag and drop this directly
[00:32:05] into the scripts directory. This is one
[00:32:07] of those nice things where after you
[00:32:08] build [music] an image generation skill,
[00:32:11] plug it up to the API, you can just kind
[00:32:12] of reuse this, okay? So, I'm embedding
[00:32:14] this right into the skill, and actually
[00:32:16] need to go one more in here. There we
[00:32:18] go. And that looks good. Now, let's go
[00:32:20] ahead and look at the update that was
[00:32:22] made. Let's make sure that it's clear
[00:32:24] and concise. [music] Placeholder,
[00:32:25] replace every HTML first, good.
[00:32:28] Sometimes these models like go off and
[00:32:30] do work I did not request. You can see
[00:32:31] it added this line on questionable. It's
[00:32:33] fine, we do [music] want this. That's
[00:32:35] good, so that's been created there. And
[00:32:37] now we have our plan format [music] in
[00:32:39] HTML. So, uh first thing I'm going to do
[00:32:42] is cut out all of this garbage. I did
[00:32:44] not ask for any styling at all. So, I'm
[00:32:46] going to tell the agent And this is the
[00:32:47] problem when you start using agent, you
[00:32:49] really want to keep it in the loop. Uh
[00:32:50] remove the styling section [music]
[00:32:52] completely. We do not have a
[00:32:54] predetermined styling. All future
[00:32:56] prompts, be [music] surgical. Do only
[00:32:59] what was asked for. Let's make our
[00:33:02] metadata header [music] a collapsible
[00:33:04] details item. Right? So, we're just
[00:33:06] going from top to bottom here, getting
[00:33:07] our key sections. [music] We do have
[00:33:09] purpose, problem, solution. And so, we
[00:33:11] also do want to have dedicated [music]
[00:33:13] workflows, which is going to be an
[00:33:14] important piece of this, cuz that tells
[00:33:16] the agent exactly how to work. Have this
[00:33:18] [music]
[00:33:18] HTML first, kind of a work in progress.
[00:33:21] Good. Let's add the questionable section
[00:33:23] [music] into our HTML uh plan template.
[00:33:26] Place this above the notes section.
[00:33:29] >> [music]
[00:33:29] >> And make it conditional only if
[00:33:32] questionable is true.
[00:33:34] And so, we have our header section here.
[00:33:37] Hero image, great [music] purpose,
[00:33:39] problem, solution, relevant files,
[00:33:41] existing files. We have this [music]
[00:33:43] repeat syntax, which is okay. Uh that
[00:33:46] should be good enough for the agent to
[00:33:47] understand. And questionables just
[00:33:49] showed up there. That looks good.
[00:33:51] Toggable [music] QA. Uh this is a
[00:33:53] duplicate.
[00:33:54] Pick one. So, we got rid of that
[00:33:55] duplicate. Definitely a weird glitch
[00:33:57] [music] coming out of that model.
[00:33:58] Usually, it's not that stupid. That's
[00:34:00] our Q&A section. Yeah, you know, I I
[00:34:02] love this and I hate this about these
[00:34:03] [music] models. They take one request,
[00:34:06] they take the context, and they just
[00:34:07] blow it up. Didn't really want to move
[00:34:08] on to this step, but it's fine. Here we
[00:34:10] are. It did [music] a decent job of
[00:34:11] this. Um I should have been more
[00:34:13] surgical with my input prompt, saying
[00:34:15] just do the one thing I requested.
[00:34:18] But it's fine. So, this is looking good.
[00:34:20] Plan file, plan output [music]
[00:34:22] directory. You know, let's work on this.
[00:34:24] So, maintain a synced visual identity
[00:34:26] between uh the HTML styling [music]
[00:34:29] and the generated images. We want a
[00:34:31] professional
[00:34:33] >> [music]
[00:34:33] >> focused I'll also just add minimal theme
[00:34:36] based on the original user prompt
[00:34:39] [music] that created
[00:34:41] the plan. And I'm also going to add a
[00:34:43] note here. We're moving into our image
[00:34:44] [music] generation. For every image
[00:34:47] created, keep them professional and
[00:34:49] focused [music] on a single on or two
[00:34:52] primary ideas. Keep text below down by
[00:34:56] minimizing
[00:34:57] the total number of words
[00:35:00] requested [music]
[00:35:01] in the image prompt. The total number of
[00:35:03] sets of words under 10. And this is so
[00:35:06] that you don't end up with image
[00:35:08] generations that have a ton of text all
[00:35:10] over the place. Goal is to build images
[00:35:13] that aid the plan and convey core
[00:35:16] information throughout the plan given
[00:35:18] the section the image was created for.
[00:35:21] And I'm just going to keep writing on
[00:35:22] this because the images is a really key
[00:35:24] part of this. Build images [music] for
[00:35:26] professional software engineers to
[00:35:29] convey exactly what is going to be
[00:35:31] built.
[00:35:33] Build, center, and space images
[00:35:35] properly. Something like that. I think
[00:35:37] that's good enough. So, that looks good.
[00:35:39] And now I think we can get rich [music]
[00:35:41] header sections, embedded images. Let's
[00:35:44] work on our dedicated workflows cuz this
[00:35:45] really puts it all together. Okay, let's
[00:35:47] work
[00:35:48] >> [music]
[00:35:48] >> through our workflows.
[00:35:50] This is similar to our meta skill
[00:35:53] cookbook pattern, except we'll call
[00:35:55] these workflows. Create five empty files
[00:35:59] inside of the
[00:36:01] workflows directory in the skill.
[00:36:05] Then create a table in our workflow
[00:36:07] section of when to call each and the
[00:36:10] file to [music] read given the incoming
[00:36:13] user prompt. So, that should be enough
[00:36:14] to get started here. I am [music] going
[00:36:16] to commit this. And so, now we're going
[00:36:17] to get our workflows directory and this
[00:36:19] is how we can really dial in the
[00:36:22] different agentic workflows that are
[00:36:23] going to run for [music] this skill. You
[00:36:25] know, normally I have a spec skill and
[00:36:27] I'll have like a build skill [music]
[00:36:29] that details exactly how other agents
[00:36:31] can build against a given plan. I want
[00:36:34] this all in one. So, I want this skill
[00:36:35] to be a unified planning skill for any
[00:36:37] code base that I can use and deploy for
[00:36:40] these next generation models. Let's go
[00:36:41] and take a look at our new workflow
[00:36:44] section. So, now the workflow is based
[00:36:46] on [music] a table and we have five
[00:36:48] workflows. So, we can generate images,
[00:36:50] we can build against a plan, we can
[00:36:52] update references because remember this
[00:36:54] planning prompt [music] is going to
[00:36:55] maintain and live over the life cycle of
[00:36:58] the code base. This is now a living
[00:36:59] artifact. We can update the plan, make
[00:37:01] changes [clears throat] to it, revise it
[00:37:02] and of course, the most important one,
[00:37:04] we can create the plan. And so, now
[00:37:06] inside of create plan, we should have
[00:37:08] had our base workflow moved into that
[00:37:11] but it looks like our agent just
[00:37:12] deleted. Create plan was the workflow we
[00:37:15] had there. Place it in the file. And I
[00:37:17] know that's [music] already in the
[00:37:19] agent's context window. So, now it wants
[00:37:20] to just recreate that there. This is
[00:37:22] fantastic. So, now uh it's super clear
[00:37:24] when to call each one of these
[00:37:25] workflows, right? And so, this is a way
[00:37:26] you can just quickly embed multiple
[00:37:29] pathways for your agents inside of a
[00:37:31] single skill. Create a workflows
[00:37:33] directory, specify the exact workflow in
[00:37:35] each one of them and then let your agent
[00:37:36] execute [music] each one of them.
[00:37:37] Fantastic. So, now let's just continue
[00:37:39] building out our workflows and I think
[00:37:41] the next most important workflow to work
[00:37:43] through is going to be our image
[00:37:44] generation. So, I'll say uh read the
[00:37:47] scripts and [music] understand how we
[00:37:49] will create and edit images and then
[00:37:52] create that workflow.
[00:37:56] >> [music]
[00:37:56] >> And I'll say KISS. KISS stands for Keep
[00:37:58] It Simple, Stupid. Uh agents know this.
[00:38:01] This is an information dense keyword
[00:38:02] that reminds the agent to simplify
[00:38:04] [music] the implementation down to the
[00:38:06] core. And so, now in our image
[00:38:07] generation, we have this fill or [music]
[00:38:10] regenerate. Okay, image generation and I
[00:38:12] want to split this up into two
[00:38:14] workflows. Let's embed [music] two
[00:38:16] workflows inside of
[00:38:19] this file. Create and update based on
[00:38:21] incoming user prompt.
[00:38:23] >> [music]
[00:38:23] >> Let's simplify this a little bit. The
[00:38:25] create will usually be during the create
[00:38:28] workflow, the prompt, and update will be
[00:38:31] explicitly requested or given a change
[00:38:34] to the plan.
[00:38:36] Okay, one thing I do want to tweak here,
[00:38:38] update create a images output output dir
[00:38:42] in the root variables variables section
[00:38:45] and reference that instead. Use I'm just
[00:38:47] going to copy this and I want these to
[00:38:49] just store underneath plan name in some
[00:38:52] directory.
[00:38:54] Yeah, so a couple important pieces here
[00:38:55] are explore code base step is a little
[00:38:58] simple. So, I want to add two variables
[00:39:00] here, add AI docs variables AI docs and
[00:39:05] app docs. These are just two directories
[00:39:07] that I like to use, reference them in
[00:39:10] the create plan step two or add steps
[00:39:13] [music]
[00:39:14] workflow.
[00:39:15] And so, these are just two additional
[00:39:17] directories that are really important
[00:39:19] for planning and gathering information.
[00:39:21] AI docs, app docs. So, I'm going to
[00:39:22] throw it inside my agent and then have
[00:39:24] it also make sure to read that for the
[00:39:26] plan and then I can use that [music] in
[00:39:28] the forward references and backward
[00:39:29] references section. Awesome. And then
[00:39:31] I'll add a add an image generation step
[00:39:34] to the create plan workflow. We'll do
[00:39:36] that [music] after step four. Also, add
[00:39:38] the conditional questionable step after
[00:39:42] this new step five. [music] I think that
[00:39:43] makes sense.
[00:39:45] You'll notice a theme as I'm working
[00:39:46] through this like I'm really paying
[00:39:47] attention to all the moving parts here.
[00:39:49] I'm separating the skill [music] into
[00:39:50] digestible pieces. We have a great plan
[00:39:53] format that we're going to use literally
[00:39:55] hundreds and thousands of times as I
[00:39:56] have used this previous generation spec
[00:39:59] format. And uh this is going to pay us
[00:40:00] back a lot because now our agents are
[00:40:02] keeping track of forward references,
[00:40:03] back references, keep track of all
[00:40:04] commits, uh modified dates. We're going
[00:40:06] to have images to aid the system. We're
[00:40:08] going to have a to-do list [music] built
[00:40:10] into the spec itself. Great planning is
[00:40:13] great engineering and we're treating our
[00:40:15] plans as artifacts. That's one of the
[00:40:17] biggest jumps [music] with this system.
[00:40:19] We're using more tokens and we're
[00:40:20] treating our plans as artifacts, living
[00:40:22] artifacts in our code base. [music] So,
[00:40:24] let's go back to raw and understand
[00:40:25] what's going on. So, we're working on
[00:40:27] our dedicated workflows. We should get
[00:40:29] image generation now and we have our
[00:40:32] updatable headers. Let's create our
[00:40:34] update references workflow. Create the
[00:40:36] workflow. This is where we update back
[00:40:39] references, forward references from
[00:40:42] another plan.
[00:40:44] Maintain structure. Subs for no reason.
[00:40:48] Okay, let's make it clear in our
[00:40:50] instructions that all metadata except
[00:40:53] for created ISO is a comma sep list that
[00:40:57] should only ever be appended [music]
[00:40:59] to.
[00:41:00] So, this is going to maintain a great
[00:41:02] log of the agent name, [music] the
[00:41:05] session ID. Should be able to get away
[00:41:07] with this. Agent name, ID. Hopefully
[00:41:09] doesn't break anything. Okay, so that's
[00:41:11] great. So, now we have that workflow,
[00:41:13] update references. What else do we need?
[00:41:15] We have image generation, update plan.
[00:41:17] Uh let's create the update plan
[00:41:20] workflow. This is to modify an existing
[00:41:22] plan. We should update [music]
[00:41:24] metadata fields. Be surgical with the
[00:41:27] change to the plan and then update
[00:41:29] [music] the amend section, which we
[00:41:31] actually might not have that yet. Yeah,
[00:41:33] which we need to add to the plan
[00:41:36] template. Amend is specifically for
[00:41:39] update plan and update references so
[00:41:41] that plan contains [music] a running
[00:41:43] history of changes that occurred after
[00:41:46] the plan was executed on. So, really
[00:41:49] important workflow here. Right, if we
[00:41:51] look at all of our workflows we run in
[00:41:53] the system, right, our workflow table.
[00:41:55] We have create, update, update
[00:41:56] references, build, and [music] image
[00:41:58] generation. Okay, good. Yep, also append
[00:42:01] only. Exactly. And now we have our
[00:42:03] update plan. [music] Yep, record amend,
[00:42:05] record change. Perfect. Okay, that looks
[00:42:07] good. So, this should be all of our
[00:42:10] workflows that this [music] plan can
[00:42:12] execute on. So, that's our dedicated
[00:42:14] workflows, that's our rich updating
[00:42:16] metadata, that's our synced HTML images,
[00:42:19] that's our per phase task breakdown of
[00:42:22] work, and that's our embedded checklist.
[00:42:25] Oh, we are missing our build. So, we do
[00:42:27] not have our embedded checklist yet.
[00:42:28] Let's go ahead and add that. We do have
[00:42:30] our validation, but we'll make sure that
[00:42:32] that's strong enough. First, let's go
[00:42:34] ahead and run build plan. So, now we
[00:42:37] need our build plan. This is for the
[00:42:40] agent that will actually build plan user
[00:42:42] prompt must contain a path to a plan, or
[00:42:45] it must be inferred, and then the agent
[00:42:48] must read all images, and we'll also
[00:42:51] have it read all back refs. We might
[00:42:52] want to change this in the future. Right
[00:42:54] now, we're going to lead toward heavy
[00:42:55] context, since this agent will have a
[00:42:57] fresh context window, since all of our
[00:42:59] agents are focused specialized agents.
[00:43:01] We're sticking to the tactic of one
[00:43:03] agent, one prompt, one purpose. Uh so,
[00:43:05] it's going to have back refs. Uh we'll
[00:43:07] read the back refs, implement [music]
[00:43:09] step-by-step, update its status, update
[00:43:12] the phase plus task status as it works,
[00:43:15] test, report, [music] and I will also
[00:43:17] say it should announce each phase and
[00:43:20] task it's working on, or actually just
[00:43:22] each phase working on.
[00:43:24] And we should have four states for
[00:43:27] tasks: [music] empty, work in progress,
[00:43:29] we'll have done, and then we'll have F
[00:43:32] for failed. F equals failed, X complete,
[00:43:35] work in progress, idle.
[00:43:37] So, now we're going to complete the
[00:43:39] build plan workflow here. Okay, yeah, so
[00:43:41] this wasn't even in the spec. This is
[00:43:43] great. That will now be included.
[00:43:45] Awesome. All right, let's take a look at
[00:43:46] what this looks like. [music] Markers,
[00:43:48] look at the plan, plan output, read
[00:43:50] absorb context, all images, and I'll say
[00:43:52] every back reference depth one, execute
[00:43:55] top to bottom, announce the phase, work
[00:43:57] in progress, implement [music] the task.
[00:43:59] Yep, loop till they pass. Okay, do not
[00:44:02] start the next phase. Final validation.
[00:44:04] Okay, yeah, after the phases. That's
[00:44:06] right. Okay, good. And update metadata.
[00:44:09] Yep, that's right. [music] Report
[00:44:10] summarized was built per phase. This
[00:44:13] looks right. Now, we should have a very
[00:44:14] powerful self-contained skill. I think
[00:44:16] image generation, [music] we need to be
[00:44:18] a little bit more clear on to go and
[00:44:20] search images. We have a really, really
[00:44:22] long instruction here. Probably want to
[00:44:24] break instructions [music] into H3s, but
[00:44:27] this is fine for now. You know, with all
[00:44:30] the plan, templates, [music] and you
[00:44:32] know, meta planning skills I create,
[00:44:34] these are just iterations. I'm going to
[00:44:35] iterate on this. But, what I want here
[00:44:37] is a really powerful first version. And
[00:44:39] I want to
[00:44:40] >> [music]
[00:44:40] >> really show and convey how much time I
[00:44:42] put into a very, very important skill
[00:44:45] like this. Your planning skill is one of
[00:44:47] the most important, if not the most
[00:44:49] important skill that you and your agents
[00:44:50] will have in contention with the meta
[00:44:52] skill or meta prompt in the prompt
[00:44:54] template. Add image slots [music] in the
[00:44:56] following sections that concisely, yeah.
[00:44:59] I guess in the following sections that
[00:45:01] represent section. I want an image for
[00:45:03] problem, solution. We don't need one for
[00:45:05] purpose, probably. We don't need one for
[00:45:07] sections. I do want one, one per phase,
[00:45:11] and optional questions if questionable,
[00:45:14] and as many as the agent wants inside of
[00:45:18] notes. And let's expand and really
[00:45:21] loosen what we're looking for. Let our
[00:45:23] planning agents [music]
[00:45:24] run free in the notes section.
[00:45:27] Yeah, many engineers, maybe yourself is
[00:45:29] included in this. One of the critiques
[00:45:30] of this approach of really templating
[00:45:32] your engineering is the idea that you
[00:45:33] might be limiting the model and limiting
[00:45:36] what the model can do with the idea
[00:45:38] being that it'll generate a better plan
[00:45:40] than this given that you let it run
[00:45:41] free. I don't think that's true. I think
[00:45:43] nine out of 10 times spelling out the
[00:45:45] exact plan format you want and then
[00:45:46] creating a section like this for the
[00:45:49] agent to run free and add all the
[00:45:51] details it wants is going to be more
[00:45:53] valuable. Because again, this is not
[00:45:54] just for your AI agents, it's for you,
[00:45:56] your team, and your AI agents. So,
[00:45:58] there's a trifecta of users, of
[00:46:00] consumers of the plans, and it needs to
[00:46:03] satisfy all three, not just one. [music]
[00:46:04] This is looking good. Author rich spoke
[00:46:07] HTML as needed. Very good. Very good.
[00:46:09] Free form. Nope, that's good. That's
[00:46:11] good. Including the image block below.
[00:46:13] So, I think this is good. Let's go ahead
[00:46:14] and just look at our raw. This is where
[00:46:16] it all started. Let's see where we're
[00:46:17] at. So, embedded checklist, validation
[00:46:20] testing, that's the one last thing we
[00:46:21] need to make sure is [music] dialed in
[00:46:23] here. We have that in our build plan.
[00:46:24] Let's make sure we have this in
[00:46:26] validation, our output spec here. Loop.
[00:46:29] Plan is not complete until every box is
[00:46:30] checked and every command passes. Yeah.
[00:46:33] If for some reason step is not possible
[00:46:36] to complete, mark it with F and move on
[00:46:38] if possible. So, we want to leave some
[00:46:40] room in for a real failure mode. And
[00:46:42] again, we're leaning on our model's
[00:46:44] capability to identify this potential
[00:46:46] reality where we have a truly blocked
[00:46:49] section, right? A truly blocked task or
[00:46:52] phase, which hopefully we won't run
[00:46:53] into, right? Because we would have
[00:46:54] thought through that, but let's see. And
[00:46:56] one more thing I want to do here, add
[00:46:58] last step to create plan, open in
[00:47:01] [music] IDE, add a variable IDE, code is
[00:47:05] the default. Static variable.
[00:47:08] This should sail us right home. And now,
[00:47:11] if we view this [music] reusable plan,
[00:47:13] this is a plan template, we should be
[00:47:15] able to get a good format here. Default
[00:47:17] false. Okay, there's our table with the
[00:47:19] file to read. I want to break this into
[00:47:21] a sub workflow so it's clear. Move into
[00:47:24] a sub workflow so it's clear. [music]
[00:47:27] This will be called in other workflows.
[00:47:31] There we go. That's clearer. [music] And
[00:47:33] we do need an environment variable file
[00:47:35] here for our OpenAI key for image
[00:47:38] generation. And uh that should be it.
[00:47:40] So, I'm going to close everything. So,
[00:47:41] now we should have a plan format [music]
[00:47:43] for Babel 3. We started out with a
[00:47:45] simple raw write-up of what we want
[00:47:47] done. We passed it to our agent. Our
[00:47:48] agent skipped some steps, but it helped
[00:47:50] us get the job done. [music] We spent a
[00:47:52] lot of time hands-on on this skill,
[00:47:54] really using our hands,
[00:47:57] typing things out, thinking things
[00:47:58] through, we created a multi-workflow
[00:48:01] skill with of course a couple of scripts
[00:48:03] to generate images. And now let's kick
[00:48:05] it off. Let's do something with it.
[00:48:07] Okay, so if we boot up our pie coding
[00:48:09] agent, you can see [music] we are
[00:48:10] reading that new skill in here. And I'm
[00:48:12] putting this up only to showcase this
[00:48:15] tool that I have. I've talked about it
[00:48:16] on the channel before. I have
[00:48:18] agent-to-agent communication. My agents
[00:48:19] can prompt each other at a moment's
[00:48:21] notice. Ping agent seven r9. dot dot on
[00:48:24] the network. [music] This is built on a
[00:48:26] simple HTTP server. You can see we're
[00:48:28] using Minimax 3. It allows my agents to
[00:48:29] communicate with each other. It's great,
[00:48:31] it's simple, it's super concise. What
[00:48:32] [music] I want to do here is play with
[00:48:34] this new piece of technology, or maybe
[00:48:36] it's not new. I'm actually not even sure
[00:48:38] when [music] this was created, but I've
[00:48:39] been checking this out, having my agents
[00:48:40] draft and look at this, and it looks
[00:48:42] pretty good. This is called Iron, and
[00:48:43] this service enables a direct connection
[00:48:46] between applications. [music]
[00:48:48] So, think Tailscale, but for
[00:48:50] application. So, embedded inside the
[00:48:52] application, right? You don't need to
[00:48:53] connect to some server or [music]
[00:48:54] anything like that. Um, it's got a bunch
[00:48:56] of nice features, secure, fast, modular,
[00:48:58] blah blah blah. And the biggest sell
[00:49:00] here for me that I'm interested in is
[00:49:01] [music] having applications,
[00:49:03] specifically, as you can imagine, agents
[00:49:05] being able to talk to each other across
[00:49:07] these networks, transferring uh large
[00:49:09] files, documentation, and all types of
[00:49:11] things across a network very, very
[00:49:13] quickly using a variety of transports
[00:49:16] [music] and encryption protocols just to
[00:49:18] make things more secure and simpler. As
[00:49:19] I scale up the number of agents I'm
[00:49:20] using on [music] different devices and
[00:49:22] in different agent harnesses, this
[00:49:24] version I have here is fantastic, but
[00:49:26] it's just the first version, simple HTTP
[00:49:28] over network. All that to say, I want a
[00:49:30] V1 of this. I'll skip through this. I'm
[00:49:32] going to write a simple input prompt.
[00:49:34] [music] Here we go. So, I have a simple
[00:49:35] input prompt to this. This is what our
[00:49:37] agent is going to write the plan
[00:49:39] against. [music]
[00:49:40] I pulled in my pie versus cloud code
[00:49:43] extension, which contains this very pie
[00:49:45] coding agent extension that I wanted to
[00:49:47] modify. I have a bunch [music] of
[00:49:48] requirements here, and then I've listed
[00:49:50] some documentation. Let's just kick it
[00:49:51] off, right? Let's see what our brand new
[00:49:53] spec [music] format comes up with. We
[00:49:55] are going to kick this off in a Claude
[00:49:57] code instance running [music] the Opus
[00:49:59] 4.8 model, not the state of the art
[00:50:01] Fable. I'm hoping that the Fable 5 model
[00:50:03] is going to be available to you, but I
[00:50:05] am planning for this to be released. I'm
[00:50:07] [music] planning to push my plans
[00:50:09] further with the Mythos class model. So,
[00:50:12] let's go ahead and [music] just run this
[00:50:14] on Opus. Opus is going to get us, you
[00:50:15] know, 80-90% of the way there. So, let's
[00:50:17] test out our brand new planning prompt.
[00:50:18] I'm going to write / plan [music] F3,
[00:50:21] plans for Fable 5, and we're going to
[00:50:24] run it against this file. So, I'm going
[00:50:26] to do a little bit of prompt
[00:50:27] engineering. [music] I'm just going to
[00:50:27] say cat, paste this in, question mode
[00:50:30] off. So, I'll just leave this off
[00:50:32] entirely so that our agent does not kick
[00:50:34] on our questionable mode, right? This is
[00:50:36] default false. So, basically, I want no
[00:50:38] human in the loop here. So, we'll kick
[00:50:40] that off, and we'll let our agent
[00:50:42] operate this top to bottom, and there it
[00:50:44] goes. It's going to understand scale.
[00:50:45] You can see it's in that create plan
[00:50:47] workflow. There you go. Now, it's in the
[00:50:49] image generation workflow. It actually
[00:50:51] picked up on the other specs that we
[00:50:53] just wrote. So, I probably should not
[00:50:54] have had those in there, but that's fine
[00:50:55] for now. There you go. So, yeah, let's
[00:50:57] just kind of walk through and see what
[00:50:58] our plan really feels [music] like to
[00:51:00] create. So, we have the requirements.
[00:51:02] We're saying, you know, temp directory,
[00:51:04] use PyCroco for research. It is pulling
[00:51:07] in the Py versus Claude code base, and
[00:51:09] this is publicly available, of course,
[00:51:11] on my GitHub repository. This is a
[00:51:13] public code base available to anyone,
[00:51:15] and it contains several PyCodingAgent
[00:51:17] custom extensions. We covered the
[00:51:19] PyCodingAgent in the past. Feel free to
[00:51:20] check this out. Link in the description.
[00:51:21] There's an extension in here that
[00:51:23] details exactly how this communication
[00:51:25] network works via HTTP. And so, what I
[00:51:28] want to do is have my agent write a
[00:51:30] brand new plan to build this against the
[00:51:34] Iron network protocol. Instead of using
[00:51:37] raw HTTP [music] and a simple server,
[00:51:39] we're going to write, using our new spec
[00:51:40] format, a brand new agent-to-agent
[00:51:42] communication plan using this new tool.
[00:51:45] So, that's the idea, right? Lightweight
[00:51:46] modular, networking. I want to
[00:51:48] re-implement my agent agent network
[00:51:49] communication using this. So, let's go
[00:51:51] ahead and see [music] what our agent
[00:51:52] does here. What I want to show you is
[00:51:53] the valuable end result of spending time
[00:51:56] on one of the most important skills
[00:51:58] [music] you'll create, which is your
[00:52:00] meta planning skill. Okay, so our agent
[00:52:02] just finished all the research. You can
[00:52:04] see it's [music] been spinning here for
[00:52:05] about 6 minutes, and now it's writing
[00:52:08] out the complete HTML plan. Just to like
[00:52:10] re-emphasize all the value of investing
[00:52:13] in your planning meta prompt. The key
[00:52:15] idea here is HTML gives your agent more
[00:52:19] tokens. [music] Anthropic put out a
[00:52:20] great piece on this. The more valuable
[00:52:22] tokens you give your agents, it gives
[00:52:24] them a slight edge on producing the
[00:52:26] result you're looking for. Now, this
[00:52:27] will use more tokens. As we discussed
[00:52:29] [music] in our moral write-up, we have a
[00:52:31] clear set of priorities. Whenever you're
[00:52:33] sitting down to build both agentic tools
[00:52:36] and raw engineering tools, product
[00:52:37] tools, whatever it is, understand your
[00:52:39] priorities. What are you willing to give
[00:52:40] up to get the result you're looking for.
[00:52:42] We are more than able and willing to
[00:52:44] spend tokens. We're using an HTML
[00:52:46] format. We're also going to generate
[00:52:47] images. Images is going to give
[00:52:49] yourself, your team, a quicker way to
[00:52:52] ingest the information, ingest the plan,
[00:52:54] but it's also going to give your agents
[00:52:56] a way to really understand the image at
[00:52:58] a deeper level. There's a whole new wave
[00:53:00] of multimodal specs right on the
[00:53:02] horizon, the agentic horizon, that is
[00:53:04] going to be available, and these new
[00:53:06] models can intake that information. And
[00:53:08] images is just kind of that first
[00:53:10] version of that where they can intake
[00:53:12] text, images, [music]
[00:53:13] and the next two things coming is of
[00:53:15] course audio and then full-on video. And
[00:53:18] so, this is going to be valuable, and
[00:53:19] again, middle-class models will be able
[00:53:21] to use all these tokens and really
[00:53:24] deeply [music]
[00:53:24] understand the problem and the space and
[00:53:28] your code base, your problems in a
[00:53:30] better, more efficient way, or a more
[00:53:31] effective way, not efficient, because
[00:53:33] they will be chewing up tons of tokens
[00:53:35] and additional time to do all these
[00:53:36] things. You can see my agent is working
[00:53:38] through the HTML [music] tokens now. We
[00:53:40] are chewing up a ton of tokens to
[00:53:42] generate HTML, but that is a cost we
[00:53:45] knew we were going to pay up front,
[00:53:46] okay? Because we thought this through
[00:53:48] completely. [music] We had a nice API
[00:53:50] design, we created specific workflows.
[00:53:52] We probably could have added more detail
[00:53:53] here, but the key thing to nail, I
[00:53:55] think, in any system [music] you're
[00:53:57] building is the properties. What do you
[00:53:59] want this thing to do? What's the
[00:54:01] advantage that each one of these things
[00:54:02] brings to your system? And so, we kind
[00:54:04] of wrote that out here to make sure that
[00:54:06] everything was clear. We're going to see
[00:54:07] the true results as this file comes out.
[00:54:10] There we go. Generate eight files in
[00:54:11] parallel. I'm glad it picked up on
[00:54:13] parallel. I don't know if we ever
[00:54:15] mentioned that anywhere. So, that's just
[00:54:17] the model being great. Let me see if we
[00:54:18] Yeah, we don't have a parallel keyword
[00:54:20] at all. So, parallelize the image
[00:54:23] generation as there's no reason to block
[00:54:25] here. Great. All images in parallel. So,
[00:54:28] hopefully this is actually in parallel.
[00:54:30] That's running in the background.
[00:54:31] Generate hero. Okay. No, that is That is
[00:54:33] working. That's good. I'm expecting this
[00:54:35] bash tool to stack up, and I'm not
[00:54:37] seeing that. So, I'm just curious if
[00:54:38] this is actually in parallel. You can
[00:54:40] also say in parallel stack up the bash
[00:54:42] protocol if you aren't already. I'll hit
[00:54:45] that, and then I'll kick this off in the
[00:54:46] background. Okay. Wow, I feel like that
[00:54:48] GPT image two generator got faster.
[00:54:50] That's way faster than before. Maybe
[00:54:52] those did not generate with a
[00:54:53] high-quality setting. We'll see.
[00:54:56] Generate [music] Yeah, we might be
[00:54:57] getting some low-quality images there.
[00:54:59] We'll see. Update to generate in wide
[00:55:02] format. Wide format always [music] in
[00:55:05] high quality. See two of files for info.
[00:55:09] Okay. Here we have our full HTML file.
[00:55:10] So, let's go ahead and see. We want this
[00:55:12] to open up in Chrome since this is going
[00:55:14] to be HTML. So, let's go ahead and
[00:55:16] document this as well. Update [music]
[00:55:18] our final step from create plan. We want
[00:55:21] this opened in browser. New variable,
[00:55:24] default Chrome.
[00:55:26] >> [music]
[00:55:26] >> I know some engineers are super against
[00:55:27] Chrome cuz they're gobbling all the data
[00:55:29] and all the memory. That's totally cool.
[00:55:31] Use whatever you want. But let's go
[00:55:32] ahead and see what we have. So, open in
[00:55:34] Chrome.
[00:55:34] >> [music]
[00:55:35] >> And let's see what our new Mythos class
[00:55:38] level planning tool has gotten us here.
[00:55:40] A couple things right away. We have a
[00:55:42] clear one-shot hero image. We have our
[00:55:45] header line purpose here. We have our
[00:55:47] metadata, which can be easily tracked.
[00:55:49] You can see there's all the back
[00:55:50] references. We have this MD file, which
[00:55:52] back reps, I guess that was just
[00:55:54] created. We have this, our public code
[00:55:57] base repository with the references
[00:55:58] there. We have the session ID, we have
[00:56:00] the agent name, [music] which we just
[00:56:01] put cloud code there. It could be doing
[00:56:02] a little more detailed. Commits modified
[00:56:05] and created. You can see the current
[00:56:06] date there. And then we have our hero.
[00:56:07] So, this looks great. And then we have
[00:56:08] our purpose. So, reporting this looks
[00:56:10] fantastic. That's exactly what we want
[00:56:12] to do. Also, our requirement, one step,
[00:56:14] one-time configuration. So, it really
[00:56:16] paid attention to this detail. That's
[00:56:17] great. As the models get better, like
[00:56:19] the key details you add to every plan is
[00:56:21] going to be emphasized even further.
[00:56:23] Let's see here. Here's the problem.
[00:56:25] Exactly, button holds everything. Server
[00:56:27] sent API. Yep, must be told where the
[00:56:29] hub is. Exactly, bunch of configuration
[00:56:31] there. You can see single point of
[00:56:33] failure. Yes, yes, yes, bound to one
[00:56:34] host. Exactly. It's It's actually
[00:56:36] explaining every problem with the
[00:56:38] current situation. And yeah, this is the
[00:56:40] exact setup for that current solution.
[00:56:41] And then here's the new solution.
[00:56:43] Replace central hub with an iron gossip
[00:56:45] swarm. Not sure what that is, but
[00:56:48] [music] we can see exactly what this
[00:56:49] looks like. This is our peer-to-peer
[00:56:51] network. And apparently, this lets us
[00:56:53] get away with a single environment
[00:56:55] variable. Love to see that. One-time
[00:56:57] config. Topic identity. I'm not going to
[00:56:59] go through this right now, but I'm
[00:57:01] curious about this implementation. Might
[00:57:02] throw this back at the code base and see
[00:57:04] what we get out. Create HTML relevant
[00:57:06] files, new files for that agent that's
[00:57:08] going to build against this.
[00:57:09] Implementation phase, execute every
[00:57:11] phase top to bottom. And this is really
[00:57:13] great. Every phase of this work has a
[00:57:15] single image to convey the information.
[00:57:18] So, foundation, iron gossip proof of
[00:57:20] concept. Great. You can see all the
[00:57:22] tasks, [music] individual tasks, very
[00:57:24] clearly. We have our closed-loop prompt.
[00:57:26] Do not exit this phase until every box
[00:57:28] above is checked. Uh, [music] if the POC
[00:57:30] cannot round trip, you know, complete
[00:57:32] that work. So, we have testing phase,
[00:57:33] two-node gossip, static resource
[00:57:35] primitives. We're really detailing
[00:57:36] everything we want done in this phase of
[00:57:38] work. Love that. Phase two, we have a
[00:57:40] nice sidecar, looks great. Phase three,
[00:57:42] again, just like HTML is great. As you
[00:57:44] can see here, right? Give your agent
[00:57:46] more useful tokens, and it will be
[00:57:47] easier to read, easier to update, and
[00:57:49] easier for other agents, your team, and
[00:57:52] you to consume. Images takes us to a
[00:57:54] whole 'nother level. We have to give
[00:57:55] huge credit to OpenAI's ChatGPT image
[00:57:57] two because the image fidelity and the
[00:57:59] instruction following is off the charts.
[00:58:01] There's a reason this is still the best
[00:58:02] image generation model. I'm really
[00:58:04] excited for the next image gen model
[00:58:05] based on the work they've done here.
[00:58:07] But, here's our per phase imagery. Phase
[00:58:10] four, this is parity verification and
[00:58:12] resilience and docs. Love to see this.
[00:58:14] Oh, we have a parity matrix document
[00:58:16] below. If we click this, we can scroll
[00:58:17] down to it in the note section. So,
[00:58:19] super, super important to give your
[00:58:21] agent room to run because a lot of great
[00:58:24] engineers, to be more specific, a lot of
[00:58:25] great agentic engineers moving at light
[00:58:28] speed, aka the agentic speed, would look
[00:58:30] at my plan template here, and they would
[00:58:32] say something very logical that I would
[00:58:34] understand. You are constricting the
[00:58:36] agent's ability to plan what they need
[00:58:38] to plan. That is true unless you do
[00:58:40] something like this, and you add a note
[00:58:42] section. Let [music] the agent say what
[00:58:43] it needs to say. Here, you can see it
[00:58:44] added a feature parity matrix between
[00:58:47] the original pod-to-pod agent
[00:58:49] communication framework we built out.
[00:58:50] I'll link that video in the description
[00:58:52] if you're interested. And this new iron
[00:58:54] version. Okay, so, really, really good
[00:58:55] stuff here. It also generated an image
[00:58:57] of exactly how this is going to work. It
[00:58:58] has some reference documentation, some
[00:59:00] dependency [music] docs, and then the
[00:59:01] amendment section for April coming to
[00:59:03] the plan after it's built and want to
[00:59:05] make some changes. So, this worked out
[00:59:07] fantastically. Of [music] course, I'm
[00:59:08] going to run an experiment on these
[00:59:10] other workflows. So, this planning
[00:59:12] document format is very, very powerful.
[00:59:15] Once again, I've templated my
[00:59:16] engineering. I'm forcing the agent to
[00:59:18] perform very well, state the problem,
[00:59:20] state the solution, break this up into
[00:59:22] all relevant files, identify all the
[00:59:24] files, existing and new, break it down
[00:59:26] into an implementation [music] phase,
[00:59:28] execute phase, and tasks top to bottom.
[00:59:31] You can see this is what we wrote, and
[00:59:32] then this was the templated portion for
[00:59:34] the agent to fill out. We are templating
[00:59:36] our engineering. Okay, [music] this is a
[00:59:38] key idea inside of tactical agent
[00:59:40] decoding that really holds up for all
[00:59:42] agentic engineering work, and it's what
[00:59:44] gives you your differentiated results,
[00:59:46] skills, and as you can see here, plans.
[00:59:49] Really really great stuff. Just to kind
[00:59:50] of jump back to the core of this, this
[00:59:52] is running on Opus. Opus is a great
[00:59:54] model. It's going to give us 80-90% of
[00:59:56] what Fable 5 and Mythos class models can
[00:59:59] do, but then there's going to be a point
[01:00:01] where it cannot do [music] what these
[01:00:02] models can do. You can imagine if you
[01:00:04] run this, which I'm going to make this
[01:00:05] new plan F3 skill available to you, link
[01:00:09] in the description, you can imagine if
[01:00:10] you run this on Fable, on whatever's
[01:00:12] coming next, the results are going to be
[01:00:14] really really cracked. I'll just leave
[01:00:16] it there. There are a bunch of
[01:00:17] improvements on top of this that can be
[01:00:20] made to this prompt. You know, one thing
[01:00:22] I want to add right away is SVG [music]
[01:00:23] support for some of the more dynamic
[01:00:25] node-based diagrams. You don't always
[01:00:27] need an image. An [music] image just
[01:00:29] takes up more time and tokens to update.
[01:00:31] There are a couple other directions to
[01:00:32] go with this, but the core value is here
[01:00:34] and ready for the next generation of
[01:00:36] Mythos class models. You know, I see a
[01:00:38] lot of hand-waving, a lot of vibe coding
[01:00:40] going on in the industry. [music]
[01:00:42] Engineers are not typing, they're not
[01:00:43] thinking anymore, they're just
[01:00:45] mindlessly prompting their agents. I can
[01:00:47] almost promise you that's going to lead
[01:00:48] to worse results over time. We stopped
[01:00:50] coding a long time ago. I stopped coding
[01:00:52] even before Cloud Code came out. Not
[01:00:55] many people are going to believe that.
[01:00:56] Um I was using a tool called Aider, and
[01:00:58] you know, I was outsourcing a lot of my
[01:01:00] raw hands-on typing [music] work. This
[01:01:02] has progressed, and a lot of us are
[01:01:04] becoming skill atrophied. This is
[01:01:06] natural. [music] This is okay. All great
[01:01:08] technology gives and takes. And as these
[01:01:11] models continue to progress, that will
[01:01:13] continue. But you do not want to
[01:01:15] outsource [music] your thinking. You do
[01:01:17] not want to outsource your thoughts. You
[01:01:19] want to be able to continue to plan
[01:01:21] work, think through exactly what you
[01:01:22] want to see because great planning is
[01:01:25] great engineering. [music] That's the
[01:01:27] one-liner, the one idea I want to leave
[01:01:28] you here with. Link in the description
[01:01:30] for my updated [music] plan F3 plans for
[01:01:33] Fable 5 skill. Just take this as a
[01:01:37] single sign, a single signal that you
[01:01:39] use to build an agentic engineer for
[01:01:42] your company, for your work, for your
[01:01:43] [music] career. Feel free to comment
[01:01:44] down below. Let me know how you're
[01:01:46] preparing and changing your agentic
[01:01:48] engineering for the next class of mythos
[01:01:51] level [music] models. I'm hyper focused
[01:01:53] on the planning and review constraints.
[01:01:55] To me, these seem like the greatest
[01:01:56] places to spend time to increase our
[01:01:59] ability to move at the agentic [music]
[01:02:01] speed while building out very, very
[01:02:03] valuable, very hand-picked,
[01:02:05] hand-structured, [music] heavily
[01:02:07] engineered foundations and fabrics and
[01:02:10] meta skills and meta prompts for our
[01:02:12] agents to use. You want to get out of
[01:02:14] the normal distribution of results by
[01:02:17] teaching your agent how you engineer by
[01:02:19] templating your engineering. It is your
[01:02:22] specific domain knowledge and expertise
[01:02:24] that differentiates you. So, you want to
[01:02:26] encode that into your work. You can see
[01:02:28] here, I'm doing it inside of the skill.
[01:02:30] This is just one example of how you can
[01:02:32] do that. If you made it to the end,
[01:02:34] definitely drop a like, drop a comment.
[01:02:36] Huge thanks to you.
[01:02:38] You know where to find me every single
[01:02:40] week with hands-on agentic engineering
[01:02:43] content like this. Stay focused and keep
[01:02:46] building.
