---
video_id: zVZotTk6ZWU
title: I Stopped Prompting Claude Code Like This
channel: Leon van Zyl
url: "https://www.youtube.com/watch?v=zVZotTk6ZWU"
watched_date: 2026-05-26
watched_at: "2026-05-26T12:00:00Z"
watch_count: 1
duration_seconds: 1186
source: youtube-history-browser
history_label: Tuesday
history_order: 44
watched_at_precision: date-from-history-label
watched_percent: 14
estimated_watched_seconds: 166
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Leon demonstrates a professional Claude Code workflow that replaces single-prompt development with structured processes for real applications. Key strategies include creating reusable agent skills to automate project setup, locking in design systems early (stored in design.md), using the checkpoint command for meaningful commits, and breaking implementation plans into phases stored in a specs folder. He shows how to leverage Claude's coordination capabilities by using the Goal command to implement specs end-to-end with parallel sub-agents, and the loop command to run recurring tasks like security audits and UI reviews every 10-15 minutes. The example builds a "second brain" app that scrapes URLs via Oxylabs, summarizes articles using Open Router, and persists data—demonstrating how multiple sessions can run simultaneously in agent view.

To implement this workflow: (1) Create a reusable agent skill that sets up your standard tech stack and install it with `npx skills` for new projects; (2) Design and lock your UI design system early, then reference it consistently in components; (3) Write detailed implementation specs broken into phases and stored in a `/specs` folder instead of trying to build everything in one session; (4) Use the Goal command with your spec folder to coordinate parallel implementation across multiple sub-agents; (5) Set up recurring loops for security audits and design enforcement that run every 10-15 minutes during development; (6) Configure external APIs (like web scrapers or LLM providers) in your .env file and let Claude coordinate their integration; (7) Use agent view to manage multiple implementation sessions simultaneously rather than serializing work.

## Transcript

[00:00:00] Most people use Claude
[00:00:01] Code one prompt at a time.
[00:00:03] That might work for toy demos, but it
[00:00:05] falls apart when
[00:00:06] you're building real apps.
[00:00:07] Real apps need structure, reusable
[00:00:10] setups, clear specs, design
[00:00:12] rules, tests, checkpoints,
[00:00:15] and a way for the agent to keep working
[00:00:17] until the job is done.
[00:00:19] How's it? I'm Leon. I'm a software
[00:00:21] engineer with nearly 20 years experience,
[00:00:23] and in this video, I'll show you the
[00:00:24] Claude Code workflow that I would use to
[00:00:27] build real applications.
[00:00:28] use to build real applications.
[00:00:29] First things first,
[00:00:30] setting up a new project.
[00:00:31] setting up a new project.
[00:00:31] Let me know down in the comments if you
[00:00:33] are guilty of this as well.
[00:00:34] are guilty of this as well.
[00:00:35] When you start a new
[00:00:35] When you start a new
[00:00:36] project, you do one of two things.
[00:00:38] You manually install your framework and
[00:00:40] all of its dependencies,
[00:00:41] all of its dependencies,
[00:00:42] or you open Claude Code, go into planning
[00:00:43] mode, and ask the agent to
[00:00:45] suggest a tech stack for you,
[00:00:46] or you give it a massive prompt
[00:00:48] describing everything
[00:00:49] you need in this project.
[00:00:51] That is a massive waste of time.
[00:00:53] I bet you that most of
[00:00:54] you watching this video
[00:00:55] reuse the exact same tech stack for
[00:00:58] pretty much every project that you build.
[00:01:00] A way more efficient alternative is to
[00:01:01] create an agent skill.
[00:01:03] create an agent skill.
[00:01:03] In this skill, you can describe your
[00:01:05] entire tech stack to the agent.
[00:01:07] entire tech stack to the agent.
[00:01:07] I can simply install the
[00:01:07] I can simply install the
[00:01:08] skill into my blank project,
[00:01:10] open up Claude Code, and ask you to set up
[00:01:12] the project on my behalf.
[00:01:13] the project on my behalf.
[00:01:13] So my recommendation is create a skill,
[00:01:14] So my recommendation is create a skill,
[00:01:16] upload it to your GitHub repository.
[00:01:18] upload it to your GitHub repository,
[00:01:18] All you have to do in your new project is
[00:01:20] run the command npx skills,
[00:01:22] run the command npx skills,
[00:01:22] followed by the name of
[00:01:22] followed by the name of
[00:01:24] your GitHub repository.
[00:01:25] This will scan your repo for any skills
[00:01:25] This will scan your repo for any skills
[00:01:27] and offer like 18
[00:01:28] skills in this repository.
[00:01:30] So I'll simply select create agentic
[00:01:32] app, then I'll select Claude Code.
[00:01:34] app, then I'll select Claude Code,
[00:01:34] and now in the agents and Claude folders,
[00:01:34] And now in the agents and Claude folders,
[00:01:37] we now have this
[00:01:37] create a genteck app skill.
[00:01:40] And of course, feel free
[00:01:40] to use my skill as well.
[00:01:42] Now when we restart Claude
[00:01:44] Code, let's run the skills command.
[00:01:46] And we can see the create a genteck app
[00:01:48] skill was installed.
[00:01:49] So some of you might be thinking that you
[00:01:51] could achieve the same thing
[00:01:52] by simply uploading a template to GitHub
[00:01:52] by simply uploading a
[00:01:54] template to GitHub and then
[00:01:55] clone it down whenever
[00:01:56] you start a new project.
[00:01:57] Now this skill basically does that,
[00:01:57] Now this skill basically does that, but
[00:02:00] the agent will then assist
[00:02:01] you in setting up everything.
[00:02:03] It will install dependencies and remove
[00:02:05] any features from the
[00:02:07] template that you don't need.
[00:02:08] that you don't need.
[00:02:08] So let's just say, please set up the
[00:02:10] border plate project.
[00:02:11] And Claude is now reading in
[00:02:12] our create a genteck app skill.
[00:02:14] our create a genteck app skill.
[00:02:14] Look, I'm going to skip
[00:02:15] through all of these questions,
[00:02:16] through all of these questions,
[00:02:16] but Claude will now ask you how you want
[00:02:18] to set up this project.
[00:02:20] So do you want to install this in a sub
[00:02:22] folder or in the root?
[00:02:23] subfolder or in the root?
[00:02:24] Do you want the database?
[00:02:25] Do you want to use an auth?
[00:02:26] It's going to ask you all
[00:02:27] of these setup questions.
[00:02:29] I'm simply going to
[00:02:29] answer these and skip ahead.
[00:02:31] answer these and skip ahead.
[00:02:31] Right, the agent is done.
[00:02:32] Right, the agent is done and it's careful
[00:02:32] And it's careful this
[00:02:33] entire project for me.
[00:02:35] this entire project for me.
[00:02:35] And by the way, this includes
[00:02:36] all of the different agents,
[00:02:38] all of the skills, everything
[00:02:38] all of the skills, everything
[00:02:40] I like to add to my projects.
[00:02:42] So this is the absolute best way to get
[00:02:44] the code running fast.
[00:02:46] If I ever want to include more skills or
[00:02:48] sub agents in my next projects,
[00:02:49] subagents in my next projects,
[00:02:50] I can simply update this
[00:02:50] I can simply update this
[00:02:51] agent skill, push it to get up,
[00:02:53] and I'm good to go in the next project.
[00:02:55] and I'm good to go in the next project.
[00:02:55] This even started up the
[00:02:55] This even started up the
[00:02:56] Postgres database for me.
[00:02:58] Postgres database for me.
[00:02:58] And if I visit localhost, I can see my
[00:03:01] starter kit over here.
[00:03:02] starter kit over here.
[00:03:02] Yes, this doesn't look very beautiful,
[00:03:04] but it does support light and dark mode.
[00:03:06] but it does support light and dark mode.
[00:03:06] This is the perfect foundation for
[00:03:08] building any web app.
[00:03:09] building any web app.
[00:03:10] Now, here's the mistake a lot of people
[00:03:10] Now, here's the mistake a lot of people
[00:03:11] make when using a genteck coding.
[00:03:13] make when using a genteck coding.
[00:03:13] Since we've got this
[00:03:13] Since we've got this
[00:03:14] foundation up and running,
[00:03:15] it's very tempting to just tell Claude to
[00:03:16] it's very tempting to just tell Claude to
[00:03:17] build our application for us.
[00:03:19] But that is a massive mistake.
[00:03:19] But that is a massive mistake.
[00:03:21] But that is a massive mistake.
[00:03:21] I recommend creating a basic landing page
[00:03:21] I recommend creating a basic landing page
[00:03:24] and to create our design system first.
[00:03:27] It's way easier to iterate
[00:03:28] and change the design system now
[00:03:30] than later in the project where we've got
[00:03:32] a lot of back-end complexity.
[00:03:33] a lot of back-end complexity.
[00:03:34] Now, there are many different ways to
[00:03:36] create design systems
[00:03:37] for your applications.
[00:03:39] One very popular tool
[00:03:40] is Stitch from Google.
[00:03:41] is Stitch from Google.
[00:03:42] You can simply prompt
[00:03:43] a design into existence
[00:03:45] and then copy the design
[00:03:45] and then copy the design
[00:03:46] system down to your app.
[00:03:48] The fact that you're watching this video
[00:03:48] The fact that you're watching this video
[00:03:49] means you do have
[00:03:50] access to Claude design.
[00:03:51] And just like with Google Stitch,
[00:03:53] And just like with Google Stitch,
[00:03:53] you can prompt an agent to create this
[00:03:53] you can prompt an agent to create this
[00:03:55] design from nothing.
[00:03:56] And once you're happy with the design,
[00:03:56] And once you're happy with
[00:03:57] the design, you can use this
[00:03:59] as your design system in your app.
[00:04:01] design system in your app.
[00:04:01] Another approach is to go through
[00:04:02] something like Gribble,
[00:04:03] something like Gribble,
[00:04:04] find the design that you
[00:04:04] find the design that you
[00:04:05] like, grab a screenshot,
[00:04:06] and then pass that to Claude in order to
[00:04:08] create a design system.
[00:04:09] create a design system.
[00:04:09] I do have videos on my channel going
[00:04:11] through each of those
[00:04:12] processes separately.
[00:04:13] For this tutorial, we'll just use the
[00:04:15] front-end design skill.
[00:04:16] This is just a way to get Claude to
[00:04:16] This is just a way to get Claude to
[00:04:17] create beautiful designs
[00:04:19] that do not look like AI slop.
[00:04:19] that do not look like AI slop.
[00:04:21] In the Claude.md file, I'm simply add
[00:04:21] In the Claude.md file, I'm simply add
[00:04:23] tagging the agents.md file.
[00:04:26] Since Claude is the only
[00:04:27] harness using the Claude.md file
[00:04:29] and everything else uses agents.md,
[00:04:32] I simply like to just
[00:04:33] include the agents.md file.
[00:04:35] And then all of my rules are actually
[00:04:37] stored in the agents file.
[00:04:39] I like to keep this file really lean.
[00:04:41] I mean, if I show you,
[00:04:42] this is like 37 lines only.
[00:04:44] this is like 37 lines only.
[00:04:44] It's super short.
[00:04:44] It's super short.
[00:04:46] I like to keep the
[00:04:46] I like to keep the
[00:04:47] responses concise and to the point.
[00:04:49] So sometimes Claude is way too chatty.
[00:04:50] So sometimes Claude is way too chatty.
[00:04:52] So sometimes Claude is way too chatty.
[00:04:52] And keep in mind, you are being built for
[00:04:52] And keep in mind, you are being bold for
[00:04:54] all of those tokens being used.
[00:04:56] all of those tokens being used.
[00:04:56] So keeping Claude's responses concise can
[00:04:56] So keeping Claude's responses
[00:04:57] concise can save you some money
[00:04:59] and you can get more
[00:05:00] usage out of your plans.
[00:05:02] In planning mode, I'm simply encouraging
[00:05:04] Claude to ask clarifying questions
[00:05:06] Claude to ask terrifying questions
[00:05:06] and not to make assumptions.
[00:05:06] and not to make assumptions.
[00:05:07] and not to make assumptions.
[00:05:08] And yes, this is all you need.
[00:05:10] You don't need a framework like
[00:05:10] You don't need a framework like
[00:05:11] Superpowers, Spec Kit or B-Mad.
[00:05:14] I've tried all of them.
[00:05:16] I've tried all of them.
[00:05:16] I've wasted hours in planning
[00:05:17] mode and it's driven me mad.
[00:05:19] In change and edit mode,
[00:05:19] In change and edit mode,
[00:05:20] I'm encouraging the agent
[00:05:22] not to make all of the changes itself,
[00:05:23] but to make use of sub-agents to
[00:05:23] but to make use of sub-agents to
[00:05:26] efficiently implement
[00:05:27] efficiently implement
[00:05:27] all of the features in parallel.
[00:05:27] all of the features in parallel.
[00:05:29] Then I've got some rules around
[00:05:30] generating the database schema,
[00:05:32] testing the application, and very
[00:05:32] testing the application,
[00:05:34] testing the application, and very
[00:05:34] and very important and
[00:05:35] relevant to this section,
[00:05:36] the design system.
[00:05:38] the design system.
[00:05:38] Always follow the UI design system when
[00:05:38] Always follow the UI design system
[00:05:40] when creating or
[00:05:41] reviewing components or pages.
[00:05:43] And for the design system, you need to
[00:05:43] And for the design system, you need to
[00:05:45] use the design in this file.
[00:05:47] And if I pull up this
[00:05:49] file, this is really detailed.
[00:05:51] file, this is really detailed.
[00:05:51] This contains everything from colors to
[00:05:53] typography, borders, padding,
[00:05:56] everything is in here.
[00:05:58] But that design system is very bland.
[00:05:58] But that design system is very bland.
[00:06:00] So let's replace it.
[00:06:01] So let's replace it.
[00:06:02] In Claude code, let's
[00:06:02] In Claude code, let's
[00:06:03] switch over to planning mode.
[00:06:05] And then I'm just
[00:06:05] going to copy this prompt.
[00:06:06] going to copy this prompt.
[00:06:06] By the way, if you want to view all the
[00:06:08] prompts used in this video,
[00:06:09] you can download them for
[00:06:10] you can download them for
[00:06:10] free from the GitHub repository
[00:06:12] linked in the description.
[00:06:13] linked in the description.
[00:06:14] But to save some time, I'm actually just
[00:06:14] But to save some time, I'm actually just
[00:06:15] going to copy the prompt.
[00:06:17] but in a nutshell, we're simply asking
[00:06:17] But in a nutshell, we're
[00:06:18] simply asking the agent
[00:06:19] to use the front in design skill
[00:06:21] to come up with something unique for our
[00:06:23] AI second brain application.
[00:06:25] AI second brain application.
[00:06:25] Then we're asking the agent to replace
[00:06:26] the border by landing page
[00:06:28] with a new page for our application.
[00:06:30] with a new page for our application.
[00:06:30] It doesn't have to be accurate.
[00:06:30] It doesn't have to be accurate.
[00:06:32] We simply want to gauge the design.
[00:06:34] So let's copy this prompt.
[00:06:35] So let's copy this prompt
[00:06:35] and let's pass it to the agent.
[00:06:36] And let's pass it to the agent.
[00:06:37] and let's pass it to the agent.
[00:06:37] All right, I've approved Claude's plan,
[00:06:37] All right, I have approved Claude's plan.
[00:06:39] And now you'll see
[00:06:39] something really interesting.
[00:06:41] The main agent is not
[00:06:41] The main agent is not
[00:06:42] making the changes itself.
[00:06:44] making the changes itself.
[00:06:44] Instead, it's kicking
[00:06:44] Instead, it's kicking
[00:06:45] off different waves.
[00:06:46] So wave one has two agents in it,
[00:06:47] So wave one has two agents in it.
[00:06:49] So wave one has two agents in it,
[00:06:50] And wave two has about
[00:06:51] three different agents in it,
[00:06:53] all running in parallel.
[00:06:54] all running in parallel.
[00:06:55] And again, this is due to the rules of
[00:06:56] the AI event agents file.
[00:06:57] the AI event agents file.
[00:06:58] We've instructed the main
[00:06:59] agent to act as a coordinator
[00:07:00] agent to act as a coordinator
[00:07:01] and to use sub-agents to
[00:07:03] implement the actual changes.
[00:07:04] implement the actual changes.
[00:07:05] This means a lot of tasks can be
[00:07:05] This means a lot of tasks can be
[00:07:06] implemented in parallel
[00:07:07] implemented in parallel
[00:07:07] instead of us waiting for the main agent
[00:07:08] instead of us waiting for the main agent
[00:07:09] to make all of these
[00:07:10] changes one at a time.
[00:07:12] And this is what Claude came up with
[00:07:12] And this is what Claude came up with
[00:07:13] using the front in design skill.
[00:07:15] Of course, you can
[00:07:15] Of course, you can
[00:07:16] make any changes you want.
[00:07:17] but at this stage, I'm going
[00:07:17] But at this stage, I'm going
[00:07:18] to lock this design system in.
[00:07:20] to lock this design system in.
[00:07:21] So what we can do is
[00:07:22] grab the design.md file.
[00:07:23] grab the design.md file,
[00:07:24] and we can simply say, "Please store the
[00:07:24] And we can simply say, please store the
[00:07:25] design system in the design.md file.
[00:07:28] design system in the design.md file."
[00:07:28] That's it.
[00:07:28] That's it.
[00:07:29] It's really that simple.
[00:07:30] It's really that simple.
[00:07:31] Now when Claude creates
[00:07:31] Now when Claude creates
[00:07:32] new components or pages,
[00:07:33] new components or pages,
[00:07:33] it will follow this design system.
[00:07:36] Stick around because I'm going to show
[00:07:36] Stick around because I'm going to show
[00:07:37] you a really cool trick
[00:07:38] for enforcing this design
[00:07:40] system during the build phase.
[00:07:42] This is something a lot
[00:07:43] of people struggle with.
[00:07:44] so you'll definitely appreciate that tip.
[00:07:44] So you'll definitely appreciate that tip.
[00:07:46] so you'll definitely appreciate that tip.
[00:07:46] All right, we've made
[00:07:47] some awesome progress.
[00:07:48] We've set up our boilerplate project,
[00:07:50] and we've locked in the design system.
[00:07:52] We've got a lot of untracked changes.
[00:07:54] We've got a lot of untracked changes.
[00:07:55] Now what I like to do is
[00:07:56] to create a reusable skill
[00:07:58] to create commits for me.
[00:07:58] to create commits for me.
[00:08:00] to create commits for me.
[00:08:00] And the comments of
[00:08:01] those commits contain a TLDR
[00:08:03] of the changes contained in that commit.
[00:08:03] of the changes contained in that commit.
[00:08:05] of the changes contained in that commit.
[00:08:05] I just called this
[00:08:05] I just called this
[00:08:06] the checkpoint command.
[00:08:07] So really, all I have to do in Claude
[00:08:07] So really all I have to do in Claude code
[00:08:09] is run the checkpoint command.
[00:08:12] And this is such a simple skill as well.
[00:08:12] And this is such a simple skill as well.
[00:08:14] And this is such a simple skill as well.
[00:08:15] You can add any of your
[00:08:16] preferences and instructions
[00:08:17] instructions for creating commits.
[00:08:18] for creating commits.
[00:08:20] So if you like very detailed comments,
[00:08:22] So if you like very detailed comments,
[00:08:22] you can tell the agent to
[00:08:24] create very detailed comments.
[00:08:25] Or in my instance, I
[00:08:26] just want like a one-liner.
[00:08:28] Now let's move on to planning mode.
[00:08:28] Now let's move on to planning mode.
[00:08:30] Now let's move on to planning mode.
[00:08:30] Natively, Claude will
[00:08:31] generate a plan for you.
[00:08:33] generate a plan for you,
[00:08:33] but we're definitely going
[00:08:33] But we're definitely going
[00:08:34] to take it a step further.
[00:08:36] We're going to create a
[00:08:37] really detailed implementation plan
[00:08:39] that's split up into phases and
[00:08:41] actionable tasks per phase.
[00:08:43] actionable tasks per phase.
[00:08:43] You're going to see the benefit of doing
[00:08:43] You're going to see the benefit of doing
[00:08:45] this in the implementation phase.
[00:08:47] And then in the interest of
[00:08:47] And in the interest of
[00:08:48] time, you can copy this prompt.
[00:08:50] but we're simply describing the app that
[00:08:50] But we're simply describing the app that
[00:08:51] we're trying to build.
[00:08:52] we're trying to build.
[00:08:53] It's a second brain app
[00:08:54] where the user can provide a URL,
[00:08:56] and will then use a web scraper to
[00:08:58] extract the contents from the page
[00:09:00] extract the contents from the page.
[00:09:00] or use an AI model to
[00:09:02] summarize and tag the articles
[00:09:03] summarize and tag the articles,
[00:09:03] and will store it in our second brain.
[00:09:06] This is also a multi-user app,
[00:09:06] This is also a multi-user app,
[00:09:07] This is also a multi-user app,
[00:09:07] so anyone can sign in and
[00:09:09] maintain their own second brain.
[00:09:11] And then I'm just giving
[00:09:12] the agent some guidance
[00:09:13] on how all of this is going to work.
[00:09:15] on how all of this is going to work.
[00:09:15] In order to summarize the
[00:09:17] article and create the tags,
[00:09:19] article and create the tags,
[00:09:19] we will use Open Router.
[00:09:21] But of course, if you want to use OpenAI
[00:09:21] But of course, if you want to use OpenAI
[00:09:23] or Anthropek or Google Gemini,
[00:09:25] you're welcome to use any model you want.
[00:09:26] you're welcome to use any model you want.
[00:09:28] It really doesn't matter.
[00:09:29] It really doesn't matter.
[00:09:29] I'll keep things
[00:09:30] simple and use Open Router.
[00:09:32] And for the model, I'll use
[00:09:32] And for the model, I'll use
[00:09:33] Anthropek and Claude Haiku 4.5.
[00:09:36] Anthropic and Claude Haiku 4.5.
[00:09:36] Now, a very important part is
[00:09:36] Now, a very important part is
[00:09:38] scraping data from websites.
[00:09:40] We should be able to provide
[00:09:41] any URL and get the data back.
[00:09:43] any URL and get the data back.
[00:09:44] By default, what is just going to try and
[00:09:45] fetch data from the page,
[00:09:47] which is definitely not correct.
[00:09:48] which is definitely not correct.
[00:09:48] Web scraping is extremely complicated.
[00:09:51] So for web scraping, we are going to use
[00:09:53] the Oxylabs WebScraper API.
[00:09:55] the Oxylabs WebScraper API.
[00:09:56] At the after-agent, I'm also giving a
[00:09:56] And to help the agent out, I'm also
[00:09:57] giving a link to the
[00:09:58] actual developer docs.
[00:10:00] I'll link to this page in
[00:10:00] I'll link to this page in
[00:10:01] the description of the video
[00:10:02] if you wanted to check it out yourself.
[00:10:02] if you wanted to check it out yourself.
[00:10:04] So I'll simply copy that entire prompt
[00:10:06] and send it to the agent.
[00:10:08] Right, Claude has created this plan,
[00:10:10] and I do encourage you to
[00:10:11] actually read through it,
[00:10:12] even if you just go
[00:10:13] over this context section.
[00:10:15] Just make sure that it covers everything
[00:10:16] that you are
[00:10:17] expecting to see in this app.
[00:10:19] Also, always scroll down
[00:10:20] to the bottom of the plan.
[00:10:22] Sometimes Claude will
[00:10:22] Sometimes Claude will
[00:10:23] actually have questions for you
[00:10:24] actually have questions for you
[00:10:24] that still needs clarifying.
[00:10:24] that still needs clarifying.
[00:10:26] In this case, though, I
[00:10:27] am happy with the plan,
[00:10:29] but I'm not going to
[00:10:30] hit bypass permissions.
[00:10:32] That is a massive mistake.
[00:10:32] That is a massive mistake.
[00:10:34] You're going to try and implement
[00:10:35] everything in a single session,
[00:10:37] which you should not be doing.
[00:10:39] What we actually want to do is grab the
[00:10:41] plan that Claude just came up with,
[00:10:43] plan that Claude just came up with,
[00:10:43] break it up into
[00:10:43] break it up into
[00:10:44] different phases or waves.
[00:10:46] and for each phase, we need a checkpoint
[00:10:46] And for each phase, we need a checkpoint
[00:10:49] list of tasks that need to be executed.
[00:10:51] list of tasks that need to be executed.
[00:10:52] And that won't make sense when we get to
[00:10:52] That will make sense when we get to the
[00:10:53] implementation phase.
[00:10:55] Now, I've already set up a
[00:10:55] Now, I've already set up a
[00:10:56] skill called createSpick.
[00:10:59] So if you are using my border plate,
[00:10:59] So if you are using my boilerplate,
[00:11:01] you can just run this Create Spec skill.
[00:11:01] you can just run this createSpick skill.
[00:11:03] you can just run this Create Spec skill.
[00:11:03] So I'm going to run it in the meantime,
[00:11:03] So I'm going to run it in the meantime,
[00:11:05] but just to explain what this does.
[00:11:07] but just to explain what this does.
[00:11:07] And you can obviously prompt Claude
[00:11:08] And you can obviously prompt Claude
[00:11:09] yourself to do the exact same thing.
[00:11:11] yourself to do the exact same thing.
[00:11:11] All we're telling Claude
[00:11:11] All we're telling Claude
[00:11:12] to do is to take this plan
[00:11:13] and then convert this into a detailed
[00:11:14] and then convert this into a detailed
[00:11:16] implementation plan.
[00:11:17] And that entire implementation plan
[00:11:17] And that entire implementation plan
[00:11:19] should be stored in the Spicks folder.
[00:11:21] should be stored in the specs folder.
[00:11:22] By the way, the reason we're doing this
[00:11:23] is we don't want Claude
[00:11:24] to implement
[00:11:25] everything in a single session.
[00:11:27] It is way more effective to actually
[00:11:27] It is way more effective to actually
[00:11:29] break up a massive plan
[00:11:31] into several components that can be
[00:11:31] into several components that can be
[00:11:33] implemented in parallel.
[00:11:35] And then we can fire off multiple Claude
[00:11:35] And then we can fire off multiple Claude
[00:11:37] sessions or sub-agents
[00:11:39] to implement the entire solution in
[00:11:39] to implement the entire solution in
[00:11:41] different waves at the same time.
[00:11:43] different waves at the same time.
[00:11:44] And this is going to pair beautifully
[00:11:44] This is going to pair beautifully with a
[00:11:46] native feature in Claude code
[00:11:47] called the Goal command.
[00:11:47] called the Goal command.
[00:11:49] All right, let's have
[00:11:50] a look at the results.
[00:11:50] a look at the results.
[00:11:51] So Claude just created this subfolder in
[00:11:53] the Spicks folder called Article Library.
[00:11:56] In here, we have a readme file that's
[00:11:56] In here, we have a readme file that's
[00:11:57] kind of like an index
[00:11:58] to all of the sub-folders or files.
[00:12:01] to all of the sub-folders or files.
[00:12:01] There's requirements of MD files,
[00:12:01] There's requirements of MD files,
[00:12:03] like a high-level overview
[00:12:04] of what we're trying to build.
[00:12:06] But the real secret sauce here are these
[00:12:06] But the real secret sauce here are these
[00:12:08] individual task files.
[00:12:09] individual task files.
[00:12:10] Claude just put up that entire
[00:12:10] Claude just built up that entire
[00:12:11] implementation plan into separate waves.
[00:12:13] implementation plan into separate waves.
[00:12:14] And each wave has a description,
[00:12:16] dependencies, and a
[00:12:17] lot of technical details.
[00:12:18] lot of technical details.
[00:12:19] Each phase also has an actual list of
[00:12:21] items or tasks that
[00:12:23] need to be implemented.
[00:12:25] So guess what?
[00:12:25] So guess what?
[00:12:25] So guess what?
[00:12:26] This is perfect for the Goal command,
[00:12:26] This is perfect for the Goal command,
[00:12:27] This is perfect for the Goal command,
[00:12:28] which takes me to the next step.
[00:12:30] Let's implement this.
[00:12:31] For the implementation, I'm going to use
[00:12:33] the Claude agent view.
[00:12:34] the Claude agent view.
[00:12:35] And you'll see why it's
[00:12:36] so convenient in a second.
[00:12:38] So to start Claude in agents
[00:12:39] view, we can run Claude agents.
[00:12:42] And optionally, we can also run it in
[00:12:44] Danger SDSKip permissions mode.
[00:12:46] And we're going to use this because we
[00:12:48] are going to kick off several sessions
[00:12:50] that will run at the same time.
[00:12:52] So what we'll do first is I'm actually
[00:12:52] So what we'll do first is I'm actually
[00:12:55] just going to create a commit.
[00:12:57] So I'm going to run
[00:12:58] the checkpoint command.
[00:12:59] the checkpoint command.
[00:12:59] And that will add all of these untracked
[00:13:01] changes to a commit.
[00:13:03] All right, cool.
[00:13:03] So that gives us a
[00:13:04] snapshot, including our spec.
[00:13:07] Now what I'm going to do-- and this is
[00:13:08] such a cool feature in Claude code--
[00:13:11] we're going to run the Goal command.
[00:13:11] we're going to run the Goal command.
[00:13:14] This is similar to the Ralph loop.
[00:13:16] It will tell the agent to run in a loop
[00:13:18] until a certain condition is met.
[00:13:20] until a certain condition is met.
[00:13:20] So we'll run the Goal command.
[00:13:20] So we'll run the Goal command.
[00:13:23] We'll then pull in this spec folder.
[00:13:25] We'll then pull in this spec folder.
[00:13:26] And then we can give it a prompt like,
[00:13:28] "Implement this
[00:13:28] implement this
[00:13:29] implementation plan in its entirety.
[00:13:31] Do not skip a thing.
[00:13:33] Do not skip a thing.
[00:13:33] Use the checkpoint skill to create
[00:13:33] Use the checkpoint skill to create
[00:13:35] commits after each phase is completed.
[00:13:38] Use the play right skill to
[00:13:40] test each feature end to end.
[00:13:42] And you know what?
[00:13:42] And you know what?
[00:13:42] That's done.
[00:13:43] We can send this command.
[00:13:44] And in agent view, we can easily go to
[00:13:46] that session by
[00:13:47] pressing the up or down arrow
[00:13:49] arrow and by pressing enter.
[00:13:49] and by pressing enter.
[00:13:51] And now we're in that session.
[00:13:53] And now we're in that session.
[00:13:53] Right, so while Claude is implementing
[00:13:54] this, let me show you this.
[00:13:56] In this subfolder file, we also have this
[00:13:58] actions required file.
[00:14:00] actions required file.
[00:14:00] I specifically asked Claude to create
[00:14:00] I specifically asked Claude to create
[00:14:02] this file whenever it creates this
[00:14:04] implementation plan.
[00:14:05] This file contains all of the manual
[00:14:06] This file contains all of the manual
[00:14:07] activities that we
[00:14:09] have to do as the users.
[00:14:10] have to do as the users.
[00:14:11] For web scraping, we do have to set our
[00:14:11] For web scraping, we do have to set our
[00:14:12] OXILabs username and password.
[00:14:15] And we also have to set
[00:14:15] And we also have to set
[00:14:16] our Open Router API key.
[00:14:18] our Open Router API key.
[00:14:18] So for Open Router, I'll
[00:14:20] just go to openrouter.ai.
[00:14:22] Then let's go to API keys.
[00:14:24] Then let's go to API Keys.
[00:14:25] I'll just create the new
[00:14:26] key and call it second brain.
[00:14:29] Let's create this.
[00:14:29] Let's create this.
[00:14:30] I'll copy the key.
[00:14:31] Then back in our project,
[00:14:31] Then back in our project,
[00:14:33] let's go to our .env file.
[00:14:35] let's go to our .env file.
[00:14:35] And I'll add the Open
[00:14:36] Router API key over here.
[00:14:39] And then we also have to set our web
[00:14:40] scraping credentials.
[00:14:42] So I'll just add a new section called web
[00:14:42] So I'll just add a new section called web
[00:14:45] scraping with these two variables.
[00:14:48] So let's just get these credentials.
[00:14:50] All right.
[00:14:50] All right, so let's set
[00:14:51] up our OXILabs credentials.
[00:14:53] We'll use the web scraper API to retrieve
[00:14:55] real-time data from the web.
[00:14:57] Then we'll pass the clean up data to our
[00:14:59] model to summarize it.
[00:15:00] And by the way, they do have pre-created
[00:15:02] web scrapers for e-commerce, real estate,
[00:15:05] search engines, you name it.
[00:15:07] And this is backed by over 175 million
[00:15:10] residential proxies across 195 countries.
[00:15:15] And they are SOC 2
[00:15:16] Type 2 compliant as well.
[00:15:18] And they were named Best
[00:15:19] Proxy Service of 2026 by PCMag.
[00:15:23] I've partnered with OXILabs to give my
[00:15:25] audience 20% off if
[00:15:26] they use my code Leon.
[00:15:27] they use my code Leon.
[00:15:28] So I'll leave a link to
[00:15:29] this page in the description.
[00:15:31] But don't worry, this is
[00:15:32] not going to cost you a thing.
[00:15:33] not going to cost you a thing.
[00:15:33] You can use the free plan to get up to
[00:15:33] You can use the free plan to get up to
[00:15:35] 2,000 scraping credits for free.
[00:15:38] And you do not need a credit card.
[00:15:40] And you do not need a credit card.
[00:15:40] So let's start by signing in.
[00:15:42] Then let's go to Scraping Solutions.
[00:15:44] Then let's go to Scraping Solutions.
[00:15:44] Let's go to WebScraper API.
[00:15:47] Then from this page,
[00:15:48] let's go to Start Free Trial.
[00:15:50] let's go to Start Free Trial.
[00:15:51] Now let's set up our WebScraper user.
[00:15:51] Now let's set up our WebScraper user.
[00:15:53] Now let's set up our WebScraper user.
[00:15:54] And let's start our free trial.
[00:15:54] And let's start our free trial.
[00:15:55] And let's start our free trial.
[00:15:56] Then back in our project, let's paste in
[00:15:58] that username and
[00:15:59] password that we just created.
[00:16:01] I am going to do that off screen as I
[00:16:01] I am going to do that off screen as I
[00:16:03] don't want to leak my credentials.
[00:16:05] don't want to leak my credentials.
[00:16:06] Right, so the Claude implementation
[00:16:07] session did stop because
[00:16:08] it couldn't get past the
[00:16:10] OXI Labs credentials.
[00:16:10] OXILabs credentials.
[00:16:11] So I simply told Claude to
[00:16:11] So I simply told Claude that we just
[00:16:13] captured those credentials.
[00:16:14] And it needs to
[00:16:15] continue with its testing.
[00:16:17] Now here's what I like
[00:16:18] to use the agent view.
[00:16:20] We don't just want to
[00:16:21] work with one session.
[00:16:22] work with one session.
[00:16:22] This is just not effective.
[00:16:22] This is just not effective.
[00:16:24] What I also like to do is to review the
[00:16:24] What I also like to do is to review the
[00:16:26] UI and to fix any UI
[00:16:28] bugs in parallel to the
[00:16:30] bugs in parallel to the
[00:16:30] implementation sessions.
[00:16:31] implementation sessions.
[00:16:32] I also like to do a security audit on the
[00:16:35] app and resolve any
[00:16:36] security related issues
[00:16:37] as well.
[00:16:38] as well.
[00:16:38] So what I want to do is actually do a
[00:16:40] security audit every, I
[00:16:42] don't know, 10 minutes and
[00:16:43] resolve any bugs.
[00:16:45] So we can use another native capability
[00:16:45] So we can use another native capability
[00:16:46] with include code
[00:16:47] called the loop command.
[00:16:49] With the loop command, we
[00:16:49] With the loop command, we
[00:16:50] can set up a recurring task.
[00:16:52] For example, we can perform the security
[00:16:52] For example, we can perform the security
[00:16:54] audit every 10 minutes.
[00:16:55] audit every 10 minutes.
[00:16:55] So I'll just say loop every 10 minutes.
[00:16:58] And then I'll pull in
[00:16:58] And then I'll pull in
[00:16:59] the security scanner skill.
[00:17:01] That's it.
[00:17:02] That's it.
[00:17:02] Then it's fired off another loop.
[00:17:02] Then it's fired off another loop.
[00:17:04] And this one we might
[00:17:05] run every 15 minutes.
[00:17:07] run every 15 minutes.
[00:17:07] And for this one, we can say, please
[00:17:07] And for this one, we can say, please
[00:17:10] review the pages and
[00:17:10] components of our app and ensure
[00:17:12] the design system is enforced.
[00:17:14] Now here's something really fun.
[00:17:16] We can also say, also identify one
[00:17:19] meaningful and low risk
[00:17:20] improvement to make to the UI
[00:17:22] and implement it.
[00:17:22] and implement it.
[00:17:23] This is fun.
[00:17:24] So this means that every 15 minutes,
[00:17:26] we'll get a brand new
[00:17:27] feature or design element
[00:17:29] added to the app.
[00:17:30] And over time, this one's
[00:17:31] a really cool difference.
[00:17:32] a really cool difference.
[00:17:32] And that's it.
[00:17:33] We now have the main thread running.
[00:17:35] And it's now implementing our app.
[00:17:35] And it's now implementing our app.
[00:17:36] And it's testing the application as well.
[00:17:39] We are also performing security audits
[00:17:39] We are also performing security audits
[00:17:41] and making any fixes.
[00:17:42] and making any fixes.
[00:17:42] And we're also making
[00:17:43] gradual changes to the UI as well.
[00:17:45] gradual changes to the UI as well.
[00:17:46] Right.
[00:17:46] Right.
[00:17:46] So while Claude is still working on our
[00:17:47] app, this is also a really fun skill, the
[00:17:50] Excalidraw diagram generator.
[00:17:53] If you ever wanted to create diagrams
[00:17:54] using Claude code,
[00:17:55] this one is a lot of fun.
[00:17:55] this one is a lot of fun.
[00:17:57] So I'll simply install that skill.
[00:18:00] So we can just say something like, I
[00:18:01] would like you to create an
[00:18:02] Excalidraw diagram visualizing
[00:18:04] the architecture of our app.
[00:18:06] Use this skill.
[00:18:07] Now this app is relatively small, so it
[00:18:09] might seem like overkill.
[00:18:10] But if you are working on complex web
[00:18:10] But if you are working on complex web
[00:18:12] apps or, you know, SaaS applications,
[00:18:15] this can be really helpful.
[00:18:15] this can be really helpful.
[00:18:17] And this can be a very fun way just to
[00:18:19] visualize all of the
[00:18:20] different components in our app.
[00:18:22] different components in our app.
[00:18:22] Like, you know, the client is a browser.
[00:18:24] Like, you know, the client is a browser.
[00:18:25] These are all the different
[00:18:25] These are all the different
[00:18:25] routes, the API endpoints.
[00:18:28] routes, the API endpoints.
[00:18:28] And externally, we're using Oxylabs and
[00:18:29] And externally, we're using
[00:18:30] Oxylabs and OpenRouter, etc.
[00:18:32] More importantly, though,
[00:18:32] More importantly, though,
[00:18:34] it looks like we are done.
[00:18:35] it looks like we are done.
[00:18:36] Right.
[00:18:36] So let's test this out.
[00:18:37] Let's see if we can sign in.
[00:18:39] Let's see if we can sign in.
[00:18:39] Right.
[00:18:39] So sign in actually works.
[00:18:41] Let's see if we can
[00:18:41] Let's see if we can
[00:18:42] find an article to scrape.
[00:18:44] find an article to scrape.
[00:18:44] We'll describe this one from OpenAI.
[00:18:46] Let's paste it in here.
[00:18:48] And let's save this.
[00:18:48] And let's save this.
[00:18:50] This should now use Oxylabs to actually
[00:18:50] This should now use Oxylabs to actually
[00:18:52] extract the data from this page.
[00:18:54] And then we'll use OpenRouter to
[00:18:56] summarize the article.
[00:18:57] summarize the article.
[00:18:58] And that's it.
[00:18:58] Our model just created the
[00:19:00] summary as well as the stacks.
[00:19:02] And if we refresh this
[00:19:03] page, the data is persisted.
[00:19:05] page, the data is persisted.
[00:19:06] Let's just click into this article.
[00:19:07] Let's just click into this article.
[00:19:08] And beautiful.
[00:19:09] I mean, we get this awesome summary back.
[00:19:11] And maybe let's try one more.
[00:19:13] Let's grab this one from Claude.
[00:19:13] Let's grab this one from Claude.
[00:19:16] Let's paste in that URL.
[00:19:17] And that just added this card as well.
[00:19:20] And by the way, while we're working on
[00:19:21] the app, we're still
[00:19:22] running the security scanner.
[00:19:24] And we're passively making UI
[00:19:25] improvements as well.
[00:19:27] improvements as well.
[00:19:27] So that is my pro
[00:19:28] workflow in Claude Code.
[00:19:30] Did I miss anything?
[00:19:31] Please let me know down in the comments.
[00:19:33] I also want to thank Oxylabs for
[00:19:34] sponsoring this video.
[00:19:35] sponsoring this video.
[00:19:36] Try it out yourself.
[00:19:37] You'll get free credits.
[00:19:38] You'll get free credits.
[00:19:38] And if you use the code
[00:19:39] Leon, you'll get 20% off.
[00:19:41] Thank you for watching.
[00:19:42] And I'll see you in the next one.
[00:19:44] Build something lacquer.
