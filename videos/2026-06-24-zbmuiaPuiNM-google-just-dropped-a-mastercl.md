---
video_id: zbmuiaPuiNM
title: "Google Just Dropped a Masterclass on Agentic Engineering (It's SO Good)"
channel: Cole Medin
url: "https://www.youtube.com/watch?v=zbmuiaPuiNM"
watched_date: 2026-06-24
watched_at: "2026-06-24T12:00:00Z"
watch_count: 1
duration_seconds: 1315
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 13
watched_at_precision: date-from-history-label
watched_percent: 11
estimated_watched_seconds: 145
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Google released a comprehensive masterclass on AI-driven software development that reframes how teams should approach AI-assisted coding. The key insight is that while AI has accelerated implementation from weeks to hours, the real bottlenecks remain requirements gathering and validation at the SDLC endpoints. AI coding exists on a spectrum from "vibe coding" (casual prompts with minimal verification) to "agentic engineering" (fully engineered systems with formal specs, automated tests, and CI gates). The critical realization is that the LLM model itself is only 10% of the system—the "harness" (context, rules, tools, workflows, guardrails) comprises the other 90%. This harness includes static context (core rules loaded upfront) and dynamic context (specialized skills loaded on demand), with a factory model where engineers design the system, agents produce code, and quality gates verify output before human review.

To immediately improve your AI coding workflow, invest upfront time in building a robust harness rather than relying on vibe coding, since this pays off in 3-10x better reliability and lower token costs within a short timeframe. Establish a two-stage workflow: use a planning agent to create specifications and architecture, then pass those artifacts to a separate coding agent to avoid context bloat. Implement automated testing and CI gates so the agent iterates autonomously before human review. Keep your static context lean and load specialized knowledge dynamically through skills/workflows—this allows one generalist agent to handle all tasks rather than managing multiple specialized agents. Adopt a "system evolution mindset" where you continuously refine your harness rules and workflows based on failures rather than just patching bugs, treating the harness as an engineered artifact that lives in version control alongside your code.

## Transcript

[00:00:00] So, a new master class on AI coding was
[00:00:02] just dropped by Google, and it is really
[00:00:06] good. It's a highle overview of pretty
[00:00:08] much everything that I teach on my
[00:00:10] channel. In fact, a couple of people
[00:00:11] actually sent this to me last week, and
[00:00:13] they said, "Hey, Cole, this literally
[00:00:14] looks like it could have been written by
[00:00:16] you. It's the cleanest packaging I've
[00:00:19] seen for everything that the industry is
[00:00:22] converging on right now as far as best
[00:00:24] practices and terminology for AI coding.
[00:00:27] It's very well written, definitely worth
[00:00:28] a read. So, I'll link to it in the
[00:00:30] description, but it's also 51 pages
[00:00:33] long, so it takes a while to get through
[00:00:34] this, which is why I wanted to make this
[00:00:36] video just to disseminate everything
[00:00:38] nice and quickly for you. And even if
[00:00:40] you're already pretty comfortable with
[00:00:42] agentic engineering and AI coding, it's
[00:00:44] worth going through this, right? The old
[00:00:46] adage is you don't truly understand
[00:00:48] something until you can teach it well.
[00:00:49] So, it's important to take the instincts
[00:00:51] you build over time and turn that into a
[00:00:54] clear visualization, mental model, and
[00:00:56] precise terminology. And so that's what
[00:00:58] we really get with this on everything
[00:01:00] the industry is converging on. And so
[00:01:02] I've reordered things a little bit what
[00:01:04] I'll show you here. I think there's a
[00:01:05] better ordering than what they present.
[00:01:07] But I want to go through this all with
[00:01:08] you along with a diagram that I have
[00:01:10] prepared and just give the good parts to
[00:01:13] you really fast. So let's get into the
[00:01:15] meat of it here. So the first big
[00:01:17] question we have to answer here is what
[00:01:19] the heck even is an SDLC? If you don't
[00:01:21] come from a technical background, you're
[00:01:23] probably not even familiar. And there's
[00:01:24] the new phrase AIdriven SDLC. that's
[00:01:27] being thrown around all of the time now.
[00:01:30] So, it's short for software development
[00:01:32] life cycle. And quite simply, it's the
[00:01:34] process to go from idea all the way to
[00:01:36] production. So, requirement gathering at
[00:01:38] the start all the way to review,
[00:01:40] deployment, and maintenance. And so,
[00:01:41] it's a lot more than just writing the
[00:01:43] code that sits in the middle. And with a
[00:01:46] traditional SDLC, you spend a good few
[00:01:49] days gathering requirements with your
[00:01:50] stakeholder meetings and the product
[00:01:52] manager creating the PRD, like all that
[00:01:54] documentation upfront. And then you have
[00:01:56] a couple of days of designing and then
[00:01:58] the implementation is usually what would
[00:02:00] take most of the time. The engineer
[00:02:02] spending weeks writing the actual code
[00:02:05] before you then go into the final steps
[00:02:07] of testing, reviewing, deploying and
[00:02:09] maintenance. And usually that would take
[00:02:10] a week. Obviously, it depends a lot per
[00:02:13] company. Just a general idea through uh
[00:02:15] generalization here. And so now with the
[00:02:18] AIdriven SDLC, the important thing here
[00:02:20] is that everything we do up front and at
[00:02:23] the very end, it's not actually that
[00:02:25] much faster. Now the specification
[00:02:27] quality is the new bottleneck. And that
[00:02:30] is so true because there's so much that
[00:02:32] still has to be human-driven with the
[00:02:34] validation at the end and the
[00:02:37] requirement gathering up front. And so
[00:02:39] really, it's only what's in the middle
[00:02:40] here. The implementation has gone from 1
[00:02:43] to 3 weeks to minutes or hours with AI
[00:02:47] coding assistance. The same thing is
[00:02:49] dozens of times faster, especially
[00:02:51] because agents can iterate with their
[00:02:53] own system of tests and eval.
[00:02:57] And so we have the bottleneck at the
[00:02:58] start and at the end. I firmly believe
[00:03:01] that a lot of the next $1 billion plus
[00:03:03] companies are going to be platforms that
[00:03:05] help speed up the requirements gathering
[00:03:08] and the validation because we've solved
[00:03:11] way more for what we have in the middle
[00:03:13] now. And so that's why you hear so many
[00:03:15] statistics around like AI coding
[00:03:17] assistants 10xing the engineers output
[00:03:19] but not actually 10xing the output of
[00:03:21] the business is because we're
[00:03:22] bottlenecked by other parts of software
[00:03:24] engineering. Software engineering is a
[00:03:26] lot more than just writing code. But the
[00:03:29] thing is, as much as you can, you want
[00:03:31] to remove implementation as the
[00:03:33] bottleneck because that is still going
[00:03:34] to save you a considerable amount of
[00:03:36] time. And so doing that and just
[00:03:38] generally making everything else in the
[00:03:39] AIdriven SDLC as fast as possible is
[00:03:42] what this article focuses on. And so
[00:03:44] that brings us to the first thing that I
[00:03:47] want to cover in the diagram. So I took
[00:03:48] all the big long ideas from the article,
[00:03:51] made it nice and concise for you here.
[00:03:53] And so the first thing that they talk
[00:03:55] about is that AI coding is a spectrum,
[00:03:58] not a switch. And I really appreciate
[00:04:00] that because most people think of it as
[00:04:01] something that's binary. Either you're
[00:04:03] vibe coding or you're doing agentic
[00:04:05] engineering. But it is a spectrum
[00:04:08] depending on the level of your system.
[00:04:11] And so we'll talk about the system and
[00:04:13] the harness in a bit. But vibe coding is
[00:04:16] where you send in a prompt without much
[00:04:18] planning. And then your validation is,
[00:04:20] hey, does it seem like it work? Right?
[00:04:22] like you'll test the application a
[00:04:23] little bit uh and then you'll just move
[00:04:25] on to the next iteration. With
[00:04:27] structured AI assisted, we have more
[00:04:29] detailed prompts. We're doing more
[00:04:31] spot-checking and then we get all the
[00:04:32] way to aentic engineering where we have
[00:04:34] a entire engineered set of resources and
[00:04:38] workflows for our AI coding assistant
[00:04:41] with specs and automated evals and CI
[00:04:43] gates. So, the agent has a way to really
[00:04:45] iterate and figure out things that go
[00:04:46] wrong before you have to correct it.
[00:04:49] This is where the real power comes in.
[00:04:51] And so it's not like we always need
[00:04:53] agentic engineering. Sometimes vibe
[00:04:55] coding is actually enough for proof of
[00:04:57] concepts or you just want to create an
[00:04:59] MVP. I used to just always dismiss vibe
[00:05:03] coding. But I think there is genuinely a
[00:05:04] place for it. And so the spectrum Google
[00:05:07] is saying is not just like you're
[00:05:08] evolving yourself. It's you pick the
[00:05:11] right one for the job. It's just agentic
[00:05:13] engineering is usually where you want to
[00:05:15] be because this is where you're really
[00:05:16] creating reliable code. And in the
[00:05:19] article, Google also has this table that
[00:05:21] I really appreciate. It makes things
[00:05:22] nice and concrete. So for each level,
[00:05:24] what does it look like for these
[00:05:26] different dimensions? And so for intense
[00:05:28] specification, for example, which is
[00:05:30] just how do you communicate upfront what
[00:05:32] you want. For vibe coding, it's just
[00:05:34] casual natural language prompts. So
[00:05:36] you're just describing at a very high
[00:05:38] level what you're looking for. With
[00:05:39] structured AI assisted coding, the
[00:05:41] middle of the spectrum, you're getting
[00:05:43] more detail, but you still don't really
[00:05:44] have a workflow for creating formal
[00:05:47] specs, architecture docs, like when you
[00:05:48] get to aentic engineering, this is where
[00:05:50] you really have a repeatable process and
[00:05:53] you have specifications that are
[00:05:54] actually engineered just like the code.
[00:05:57] And then for verification, like we
[00:05:58] covered this a little bit already, but
[00:06:00] for Vive coding, it's more does it just
[00:06:01] seem to work. You're not doing much of a
[00:06:03] deep dive at all. With structured AI
[00:06:05] system coding, you're getting a little
[00:06:06] bit into it with more manual testing and
[00:06:08] spa-checking of the code maybe. And then
[00:06:11] for agentic engineering, this is where
[00:06:12] you have the whole process for the agent
[00:06:14] to iterate itself with tests and CI/CD
[00:06:17] gates. Also, LLM judges, you have a
[00:06:19] separate code review process for
[00:06:20] yourself and another agent. And I don't
[00:06:23] need to cover everything here, but
[00:06:25] getting down to the risk profile with
[00:06:27] vibe coding, it's high, right? like
[00:06:29] acceptable for disposable code like I
[00:06:32] was saying earlier but then if you
[00:06:34] really want the most reliable code
[00:06:36] possible that's where you want
[00:06:38] systematic verification at every stage
[00:06:40] that comes with aentic engineering okay
[00:06:43] so if aentic engineering is the way to
[00:06:45] go most of the time how do we actually
[00:06:47] do it like what separates aentic
[00:06:50] engineering from vibe coding and really
[00:06:53] everything can be wrapped up in the
[00:06:54] harness so the harness is the set of
[00:06:58] context rules tools and workflows that
[00:07:00] you bring into the AI coding assistant.
[00:07:03] It's the layer that you control. And the
[00:07:06] big thing that Google is claiming here
[00:07:08] is that the large language model that
[00:07:10] you use for your AI coding assistant is
[00:07:13] only 10% of the system or it only
[00:07:16] matters 10%.
[00:07:18] Everything else like your instructions
[00:07:20] and tools and context and guardrails and
[00:07:22] orchestration and observability like
[00:07:24] there's so much here that makes up the
[00:07:26] other 90%. And that's actually a really
[00:07:28] good thing because the model is what we
[00:07:31] don't control. The harness is what we
[00:07:33] get to create for our specific code
[00:07:35] bases, architectures, and tech stacks.
[00:07:38] And it really is true that the industry
[00:07:40] is converging on a lot of these things.
[00:07:42] Like we have this article from Anthropic
[00:07:44] that I covered a couple of weeks ago on
[00:07:45] my channel, just best practices for
[00:07:48] using cloud code in general. And one of
[00:07:50] the headlines that they have here is
[00:07:52] that the harness matters as much as the
[00:07:54] model. And so now Google and myself as
[00:07:57] well were taking this even further to
[00:07:59] say not only does it matter as much but
[00:08:01] it actually matters more than the model.
[00:08:03] Like the model only being 10%. Clearly
[00:08:05] Google is like okay you need to put your
[00:08:07] focus on the rest of the harness here.
[00:08:10] And they also have a very similar
[00:08:12] definition of what goes into the
[00:08:14] harness. So cloud code right here they
[00:08:16] say it's your global rules. It's your
[00:08:18] hooks like the deterministic actions you
[00:08:20] want in your life cycle your skills. So,
[00:08:22] the workflows that you have packaged up,
[00:08:24] uh, your ways that you search your
[00:08:26] codebase, the MCP servers, and your sub
[00:08:28] aents, like these are all of the
[00:08:30] primitives, as I call them, for working
[00:08:32] with literally any AI coding assistant.
[00:08:35] And if we go now into Google's article
[00:08:37] here, they say the agent is the model
[00:08:39] plus the harness. And they have this
[00:08:41] diagram that lays out exactly everything
[00:08:43] that goes into the harness. And you can
[00:08:45] see this is where I got the numbers, by
[00:08:47] the way. So, the model being 10%. So you
[00:08:49] have the large language model in the
[00:08:51] middle still matters to an extent
[00:08:52] because it is the brain. It is the
[00:08:54] reasoning in your system but everything
[00:08:56] else around it is a huge deal. So you
[00:08:58] have your instructions MCP servers
[00:09:01] guardrails and hooks. I mean everything
[00:09:03] is the exact same as what anthropic
[00:09:05] presented in their article. And then the
[00:09:07] layer above is where you have all of the
[00:09:09] testing infrastructure. So the eval
[00:09:12] to iterate itself. And then the top
[00:09:14] layer is more for you and for
[00:09:16] production. So the observability and
[00:09:18] tracing, the scaling, right? Like that's
[00:09:21] pretty important when you want to take
[00:09:23] anything an AI coding assistant produces
[00:09:25] and actually take it all the way to
[00:09:26] production. The sponsor of today's video
[00:09:29] is Better DB, a self-tuning Valky/Ris
[00:09:32] caching and observability platform for
[00:09:35] AI agents, and it is open-source. So,
[00:09:38] we're talking all about the AI SDLC in
[00:09:40] this video, but not covering that much
[00:09:42] tools we can use to help us with
[00:09:44] reliability and monitoring in
[00:09:46] production, that end stage of the SDLC.
[00:09:49] And better DB is a fantastic example of
[00:09:52] an AI native tool that can help us with
[00:09:54] this. So, monitoring our database in
[00:09:56] production, using our AI coding
[00:09:58] assistant with it to suggest changes and
[00:10:01] improvements based on live production
[00:10:03] data, and a semantic cache to help us
[00:10:05] scale our database. Let me show you how
[00:10:07] these things work really quick. My
[00:10:09] favorite part of Better DB is the
[00:10:10] semantic cache. Take a look at this.
[00:10:12] You'll see how it works very quickly. If
[00:10:14] I ask what's the capital of France, it's
[00:10:16] not in my Better DB cache yet, so it's a
[00:10:18] miss. And it calls a model to get the
[00:10:19] answer. But the next time I ask
[00:10:20] something that is similar, we get a
[00:10:22] cache hit. It doesn't even have to be
[00:10:24] the exact same wording because it's
[00:10:26] semantic similarity search like
[00:10:27] traditional rags. So, we get a much
[00:10:30] faster answer. And we have an MCP server
[00:10:32] so we can connect our AI coding
[00:10:34] assistance directly to our better DB
[00:10:37] cache. So we can ask how it's doing. We
[00:10:39] can have it suggest improvements and
[00:10:40] even make those directly. So it's very
[00:10:42] easy to improve our system over time
[00:10:44] with the help of AI. And then also we
[00:10:46] have a dashboard to monitor everything.
[00:10:48] So we can see how our agent and our
[00:10:50] cache is performing in production with
[00:10:52] real user data. And the best part is
[00:10:54] better DB is open source and free to get
[00:10:56] started. So I'll have a link in the
[00:10:58] description. I'd highly recommend them
[00:10:59] as a tool to help you scale manage your
[00:11:01] costs for agents you're deploying to
[00:11:03] production. And so now Google is saying
[00:11:05] with harness engineering we have the
[00:11:07] idea of the factory. So instead of the
[00:11:09] engineer writing the code or the product
[00:11:11] manager writing the PRD by hand, instead
[00:11:14] we are responsible for designing the
[00:11:16] system, creating the harness and then
[00:11:18] the agent is the one that is actually
[00:11:20] producing our code and documentation.
[00:11:23] And so this is more of an investment
[00:11:25] upfront than vibe coding because we have
[00:11:26] to create the specs and guardrails, but
[00:11:28] then we use that to then go into this
[00:11:30] repeatable system of we plan with the
[00:11:32] agent, we have it build, and then we
[00:11:34] have our quality gates at the end for
[00:11:35] testing and evaling with an iterative
[00:11:37] loop here for the agent to improve its
[00:11:39] output autonomously and then get to the
[00:11:41] point where we have something for us to
[00:11:42] review and ship. And so this entire
[00:11:45] thing, we want to delegate all of the
[00:11:47] coding to the AI coding assistant. Even
[00:11:50] with agentic engineering, you are
[00:11:51] delegating all of the coding. So this is
[00:11:53] not a spectrum of how much do we write
[00:11:56] by hand versus trust the agent. It is
[00:11:58] just a spectrum of how evolved of a
[00:12:00] system do we actually have here. So
[00:12:02] Google does get a little bit repetitive
[00:12:04] here because when they talk about the
[00:12:06] factory model for the first time and
[00:12:07] what goes into it, it's really the same
[00:12:09] thing as what goes into building a
[00:12:10] harness or the AI layer they already
[00:12:12] talked about. So it's your your context
[00:12:14] and rules, your test and quality gates,
[00:12:16] your workflows, your guardrails and your
[00:12:17] hooks, right? They have a really good
[00:12:19] visualization for where the developer
[00:12:21] actually stands in the process. Now, so
[00:12:23] we define our specs, context, and
[00:12:25] requirements up front and you use those
[00:12:27] specs for your planning agent. So every
[00:12:29] single time you build anything with an
[00:12:31] AI coding assistant when you're doing
[00:12:33] agentic engineering is you're going to
[00:12:35] have one agent that does the plan for
[00:12:37] the bug fix, for the new feature,
[00:12:39] whatever it is. And then the guard rails
[00:12:41] that you design and like the sandboxed
[00:12:43] environment, that is what's going to be
[00:12:44] used by the actual coding agent. But
[00:12:46] it's important here that you do split
[00:12:49] this into two separate sessions because
[00:12:51] your planning agent is going to build up
[00:12:53] a lot of context. You want to avoid
[00:12:55] context rod and it's going to build up a
[00:12:57] lot of bias. And so you take the plan as
[00:12:59] an artifact. You send that into the
[00:13:01] coding agent and then you do your test
[00:13:02] and verification and iterate there. And
[00:13:04] this is also where we can come in the
[00:13:05] loop to review and approve things
[00:13:07] ourselves because you definitely fall
[00:13:09] more into vibe coding if you're not
[00:13:12] reviewing the output yourself. Even if
[00:13:14] you do have quite an autonomous system,
[00:13:16] right? Like even if it's just that pull
[00:13:17] request at the end for agentic
[00:13:19] engineering, generally you want a human
[00:13:21] to be reviewing that before you mark it
[00:13:23] as pass and you go on to the rest of the
[00:13:25] process for deployment to production.
[00:13:28] And throughout this entire workflow,
[00:13:30] that's where we have our guardrails like
[00:13:32] token limits and security policies,
[00:13:34] everything that you are engineering
[00:13:36] upfront. And the really cool thing about
[00:13:39] this whole system is that we can make it
[00:13:42] better over time. Just like we evolve
[00:13:44] our codebase over time, we can evolve
[00:13:45] our system. So I I call this the system
[00:13:47] evolution mindset. Whenever you
[00:13:49] encounter an issue with your AI coding
[00:13:51] assistant, like something comes up here
[00:13:53] where it has to iterate more than you
[00:13:55] would want or you have to step in before
[00:13:56] you ship, instead of just fixing the bug
[00:13:58] and moving on, you actually talk to your
[00:14:01] coding agent like you have it do some
[00:14:02] retrospection and say, "Hey, where could
[00:14:04] we make our workflows or our rules like
[00:14:07] any part of our AI layer better so that
[00:14:09] issue is less likely to come up again?"
[00:14:11] And so that way every single time you go
[00:14:13] through this process over and over and
[00:14:15] over again, you're making it more and
[00:14:17] more reliable. And the harness is worth
[00:14:20] investing your time into. Like it it
[00:14:22] really is the 90%. I mean, there's a lot
[00:14:24] of studies that are done like terminal
[00:14:26] bench 2.0. It's one of the biggest
[00:14:28] benchmarks we have out there. Like every
[00:14:30] single time a new model comes out, this
[00:14:32] is one of the percentages that you see.
[00:14:34] There's a lot of studies done where like
[00:14:35] they were able to take a model from
[00:14:37] outside the top 30 into the top five
[00:14:40] just by creating an AI layer of rules
[00:14:43] and workflows for it to run through the
[00:14:45] things you usually test for the
[00:14:46] benchmark. Lane chain was able to
[00:14:48] increase it 13.7 points. Like that's the
[00:14:50] difference between Sonnet and Opus. Like
[00:14:53] you can make sonnet work as well as Opus
[00:14:56] if you have the right system, the right
[00:14:58] process that you're having it go through
[00:15:00] as the harness. So if the harness is the
[00:15:03] most important part of agentic
[00:15:05] engineering, then it's clear that the
[00:15:07] most important skill within that is how
[00:15:09] do we engineer each of the individual
[00:15:11] components of the harness like our
[00:15:13] rules, workflows, and a guard rails. And
[00:15:15] so we've covered the different
[00:15:16] components already, but a key
[00:15:18] delineation that Google makes here that
[00:15:19] I really like is the static context
[00:15:22] versus dynamic context. And this is
[00:15:25] really important because it's all about
[00:15:27] context management. Context is your most
[00:15:30] precious resource when working with AI
[00:15:32] coding assistants, both for the sake of
[00:15:34] cost and avoiding context rot. We don't
[00:15:36] want to fill the window of our LLM, our
[00:15:39] coding agent, too much because LLMs get
[00:15:42] overwhelmed with information just like
[00:15:44] people do. And so nice visualization
[00:15:46] here. They talk about what goes into
[00:15:48] static versus dynamic. So static context
[00:15:51] is things like your rules and core
[00:15:53] guardrails, the system prompt. It's
[00:15:55] loaded into the coding agent session
[00:15:56] guaranteed every single time. time. That
[00:15:58] makes it reliable because the agent
[00:16:00] doesn't have to seek out this
[00:16:01] information, but it's expensive because
[00:16:03] you're filling the context window up
[00:16:05] front. And so, it's important to have at
[00:16:07] least some rules and guard rails up
[00:16:09] front, but you want to make them very
[00:16:10] lean. And then everything else goes in
[00:16:13] dynamic context so it's efficient and
[00:16:15] scalable because it's information that
[00:16:16] the agent has to actually seek out. Like
[00:16:19] you might have an an agent skill for
[00:16:21] planning like it loads that skill when
[00:16:23] you want it to do the planning workflow
[00:16:24] or you have conventions for a part of
[00:16:26] the codebase you want it to load when it
[00:16:28] operates on that part of the codebase
[00:16:29] and so it's very scalable so you're not
[00:16:31] shoving it into the context up front but
[00:16:33] the risk there is the agent might not
[00:16:35] grab for that context when it should
[00:16:38] like it might not load the skill or
[00:16:39] perform the rag search when you would
[00:16:41] hope it to or when it would be optimal
[00:16:43] to do so. But large language models are
[00:16:46] getting better and better at relying on
[00:16:49] dynamic context and loading it when it
[00:16:51] should. And so like agent skills are
[00:16:52] becoming very very important right now,
[00:16:55] right? So they say rather than embedding
[00:16:56] every piece of specialized knowledge
[00:16:58] into the agent system prompt, skills
[00:17:00] allow the agent to remain a lightweight
[00:17:03] generalist that flexes into specialist
[00:17:05] roles on demand through progressive
[00:17:07] disclosure. And this is so important
[00:17:09] because the underlying lesson here is
[00:17:12] that we really only need one agent for
[00:17:14] everything and then we can make it
[00:17:16] specialized with our skills, i.e. our
[00:17:18] workflows. And so something that people
[00:17:20] used to do way too much before is they
[00:17:22] would have these really complicated
[00:17:24] multi- aent systems with all these
[00:17:26] specialists or they use a ton of these
[00:17:27] specialized sub aents they would create.
[00:17:29] And really the industry is moving away
[00:17:31] from that because we can just have one
[00:17:34] generalist agent that we make specific
[00:17:37] with the skills that we have at load.
[00:17:39] Like we can have it become a code
[00:17:40] reviewer or become a planner. That
[00:17:42] session can turn into the specialization
[00:17:44] that you need thanks to dynamic context.
[00:17:47] So keep it simple. You really only need
[00:17:49] one agent to drive most of your agentic
[00:17:52] engineering. Okay. So the article has
[00:17:54] been very valuepacked already. There's
[00:17:56] just two more things that I want to
[00:17:57] cover with you here. I want to talk
[00:17:59] about your role as the conductor and
[00:18:00] orchestrator and then also the token
[00:18:03] economics. And so an interesting thing
[00:18:05] that Google presents here is the idea of
[00:18:07] you as the engineer are going to move
[00:18:10] between two modes as you're using your
[00:18:13] AI coding assistant. And so the
[00:18:15] conductor is more how we used AI coding
[00:18:18] assistants when generative AI was first
[00:18:20] a thing. Like we had our tab complete.
[00:18:22] We're still steering every move, working
[00:18:24] in individual files. That's the
[00:18:26] conductor. The orchestrator is a lot of
[00:18:28] what people have been focusing on more
[00:18:30] recently where we have a coding agent
[00:18:32] handling much larger tasks spanning
[00:18:34] entire code bases, maybe even multiple
[00:18:37] code bases. We're reviewing the outcomes
[00:18:39] instead of changes to individual files.
[00:18:41] We have agents running in parallel.
[00:18:43] We're really scaling our output with AI
[00:18:45] coding assistance here. And almost
[00:18:47] everybody is focusing entirely on this.
[00:18:50] And this this is like the one part of
[00:18:51] the article I don't know if I agree with
[00:18:53] Google because they're saying that you
[00:18:54] actually want to move between both. Like
[00:18:56] there's still a time and place to be
[00:18:58] micromanaging the AI coding assistant at
[00:19:01] a single file level. Honestly, I don't
[00:19:04] know if I agree with this. I think when
[00:19:06] you build the harness to be reliable
[00:19:08] enough and you're confident in your
[00:19:09] rules and workflows, you can always live
[00:19:12] at this level. But they do make some
[00:19:15] interesting arguments where it's like
[00:19:16] any kind of like deeper debugging you
[00:19:18] have to do or just initial exploration
[00:19:20] like you are going to get very granular
[00:19:22] with the coding agent because that's the
[00:19:23] times where you might need to really be
[00:19:25] in the loop and guide it. So I think
[00:19:27] there's a time and place for it but I
[00:19:29] feel like when you have the right system
[00:19:30] and it's working well for you, you don't
[00:19:32] really like you kind of graduate from
[00:19:34] being the conductor. I don't think
[00:19:35] you're always moving between the two.
[00:19:37] But it is an interesting idea you know
[00:19:39] especially as an organization when you
[00:19:41] have a lot of traditional engineers and
[00:19:43] you're first getting into aentic
[00:19:45] engineering I think it is good to have
[00:19:47] this mental model just until you have
[00:19:49] the system developed where you'd
[00:19:50] graduate to only ever staying here.
[00:19:52] Cool. And then the very last thing that
[00:19:54] I want to cover here is the token
[00:19:55] economics. I really love how they frame
[00:19:57] things here. So, like we said, vibe
[00:20:00] coding, you don't always want to avoid
[00:20:02] it, but there is a big cost that comes
[00:20:04] if you lean on it too much because at
[00:20:06] first when you're first adopting AI
[00:20:08] coding assistance for yourself or a
[00:20:10] company, Vive coding is going to be
[00:20:12] cheaper. It's lower capital expenditure
[00:20:14] because you don't have to dedicate
[00:20:15] yourself or a team to design the initial
[00:20:18] harness. But the problem is it's very
[00:20:20] high operational expenditure because you
[00:20:22] start burning through millions and
[00:20:23] millions of tokens iterating on slop
[00:20:26] code because you don't have a system for
[00:20:28] your AI coding assistant to follow your
[00:20:30] workflow and your conventions. And so
[00:20:33] agentic engineering it has that high
[00:20:35] capital expenditure because you have to
[00:20:37] dedicate your time up front or you have
[00:20:39] to like in a larger organization usually
[00:20:41] you create a smaller forward deployed
[00:20:42] engineer team to build up that harness
[00:20:45] to then scale to the entire
[00:20:46] organization. So you're dedicating
[00:20:48] manpower to build something initially,
[00:20:50] but then it scales extremely well
[00:20:52] because the output of your AI coding
[00:20:53] assistants are better and better and
[00:20:55] better over time and you have that
[00:20:57] grounding in a system that you just
[00:20:58] build once upfront and evolve over time.
[00:21:01] So high capital expenditure but then low
[00:21:04] operational expenditure and you know you
[00:21:07] have that crossover that you reach
[00:21:08] extremely quickly like you want to just
[00:21:10] take the dive and build that system up
[00:21:12] front because yeah you're going to get
[00:21:15] to the point where agentic engineering
[00:21:16] is three to 10 times more reliable and
[00:21:18] cheaper than vibe coding because you're
[00:21:20] not burning through millions of tokens.
[00:21:23] So there you go. That is everything you
[00:21:24] need to know at a high level for the new
[00:21:26] AIdriven software development life
[00:21:28] cycle. It is worth building that harness
[00:21:31] and investing in it. It is an engineered
[00:21:33] resource that lives in version control
[00:21:35] just like the code itself. So, I hope
[00:21:38] that you found this useful. Let me know
[00:21:39] in the comments what kinds of content
[00:21:41] you want me to create to expand on any
[00:21:42] of these ideas here cuz this is my bread
[00:21:45] and butter. If you appreciated this
[00:21:47] video, you're looking forward to more
[00:21:48] things on Agentic Engineering, I would
[00:21:50] really appreciate a like and a
[00:21:52] subscribe. And with that, I will see you
[00:21:54] in the next video.
