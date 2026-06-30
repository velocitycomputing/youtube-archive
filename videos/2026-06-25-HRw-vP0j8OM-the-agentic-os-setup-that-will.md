---
video_id: HRw-vP0j8OM
title: The Agentic OS Setup That Will 10x Claude Code
channel: Chase AI
url: "https://www.youtube.com/watch?v=HRw-vP0j8OM"
watched_date: 2026-06-25
watched_at: "2026-06-25T12:00:00Z"
watch_count: 1
duration_seconds: 1880
source: youtube-history-browser
added_date: 
history_label: Thursday
history_order: 60
watched_at_precision: date-from-history-label
watched_percent: 17
estimated_watched_seconds: 320
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video explores building an Agentic OS with Claude Code, arguing that the real value lies not in visual dashboards but in four underlying levels: (1) skills and loop engineering—codifying your repetitive workflows into reusable skills and automations; (2) memory and state management—organizing your data (via Obsidian or databases) into a clear hierarchy with index.md files so Claude can navigate efficiently; (3) a custom visual interface (web app or Obsidian plugin) wrapping these capabilities; and (4) distribution so non-technical team members can use these tools via simple buttons. The speaker emphasizes that levels 1–2 deliver 90% of the value and require no fancy UI.

To implement this, start by auditing your weekly tasks—either manually or by having Claude review your past sessions—then convert your top-repeated workflows into skills using Claude's skill creator tool. Set up an Obsidian vault with three folders (raw/unstructured data, wiki/structured data, outputs) and add index.md files to each folder to help Claude locate information quickly. Automate any skill you run weekly using Claude Desktop's routines. Document your vault structure in a CLAUDE.md file, then optionally layer a web app or Obsidian plugin on top for a cleaner interface. This foundation works entirely in the Claude terminal or desktop app without requiring custom dashboards.

## Transcript

[00:00:00] If you don't know how to build your own
[00:00:01] agentic OS, then you are falling behind.
[00:00:04] But not for the reason you think. It's
[00:00:06] not because you need some fancy
[00:00:07] dashboard or a Jarvis setup because that
[00:00:10] is not where the value of these systems
[00:00:12] lie. The value is everything under the
[00:00:14] hood. Everything you can't see. I'm
[00:00:16] talking about loop engineering, skill
[00:00:18] architecture, state management, creating
[00:00:20] a second brain, and being able to bundle
[00:00:23] it all together into a coherent
[00:00:25] customized product that works for you.
[00:00:27] That is where the value lies. And the
[00:00:29] skills required to build something like
[00:00:31] this can be applied to any project you
[00:00:33] work on with clawed code, which is why
[00:00:36] this is such a valuable thing to
[00:00:38] understand. So in this video, we are
[00:00:39] going to be breaking down the clawed
[00:00:41] agentic OS construct level by level so
[00:00:43] you can learn not only how to build one
[00:00:45] yourself, but why it's so important that
[00:00:48] you do. When we are looking at an
[00:00:49] agentic OS like this one or this
[00:00:52] Obsidianbased one, it's easy to get lost
[00:00:55] inside the visual spectacle of it all.
[00:00:58] all these buttons and moving parts and
[00:00:59] metrics, things you can't find inside
[00:01:01] the Claude Code terminal, jump out at
[00:01:03] you right away, and you kind of fall
[00:01:05] into one of two camps. The first camp is
[00:01:07] like, "Wow, this looks really cool. I
[00:01:08] want to get my hands on this. I love all
[00:01:10] these like sort of visual things I can't
[00:01:12] find elsewhere." And the other camp sees
[00:01:14] it for what it is, which is just the
[00:01:16] visual interface, and thinks, "This is
[00:01:19] just smoke and mirrors. There's nothing
[00:01:20] here that's actually moving the needle
[00:01:22] forward." And I think both camps miss
[00:01:24] something. And what they miss are the AI
[00:01:26] fundamentals that are working under the
[00:01:28] hood that turn an AIOS and just a fancy
[00:01:31] looking web app into a customized weapon
[00:01:34] you can use to attack any problem with
[00:01:36] clawed code or frankly any model. I'm
[00:01:38] going to talk about cloud code today but
[00:01:40] this can be run again with something
[00:01:42] like codeex or even a local model. And
[00:01:44] when we talk about these fundamentals we
[00:01:46] can kind of break it down into four
[00:01:47] sections when it comes to this AIOS. The
[00:01:50] first level is the backbone and that is
[00:01:52] the skills in the loop engineering in
[00:01:54] the idea that we have codified
[00:01:56] everything we do inside of cloud code
[00:01:58] and we've turned it either into a skill
[00:02:00] or some sort of automation. Level two is
[00:02:03] memory and state control. How can we
[00:02:05] make sure that our AIOS has some sort of
[00:02:08] database of information that it can draw
[00:02:10] upon when we ask it questions? And more
[00:02:13] importantly, can we use this state, this
[00:02:16] memory, whether that's obsidian or
[00:02:17] something else. You can use something
[00:02:18] like a standard database. How can we use
[00:02:20] this in combination with the skills and
[00:02:23] automation we've built to create
[00:02:25] actually properly built loop engineered
[00:02:28] constructs that are somewhat
[00:02:29] self-improving? If you watched my last
[00:02:31] video about loop engineering, you kind
[00:02:33] of know what I'm talking about. The idea
[00:02:34] that we need to be able to record things
[00:02:36] and set up loops that can see how we've
[00:02:39] done in past iterations to improve
[00:02:41] future runs. And these two levels, one
[00:02:43] and two, is where we make most of our
[00:02:45] money. This is 90% of the value of any
[00:02:48] sort of AIOS. And once you have that
[00:02:49] locked in, well, then you can move into
[00:02:52] some of the cool visual stuff. And
[00:02:53] that's sort of level three where we talk
[00:02:54] about the interface and the UI and sort
[00:02:56] of the customization aspect of this. If
[00:02:59] you want to get outside of the terminal
[00:03:00] and also sort of spread your wings
[00:03:02] versus some of these desktop
[00:03:04] applications because the claw desktop
[00:03:05] application is great, but there's only
[00:03:07] so much you can do inside of it or set
[00:03:08] it up in certain ways. And then lastly,
[00:03:10] we have level four, which is
[00:03:11] distribution. Because the cool thing
[00:03:13] about this is it doesn't have to be
[00:03:14] personal just to you. You could share
[00:03:16] your AIOS with members of your team or
[00:03:18] even clients. And it's a great way to
[00:03:20] raise the floor in your organization. A
[00:03:22] lot of what you do on level one and two
[00:03:25] can be turned into a literal button or
[00:03:28] voice command that you can implant
[00:03:30] inside of your AIOS user interface that
[00:03:33] anyone can use. They don't even need to
[00:03:35] run cloud code themselves. It can all be
[00:03:36] done for them. So those are the four
[00:03:38] levels we're going to be talking about
[00:03:39] today. I'm going to spend the vast
[00:03:40] majority of it here in levels one and
[00:03:42] two because the truth is you could still
[00:03:44] do all of this inside of your standard
[00:03:47] claude code terminal or the codec cli or
[00:03:49] the codeex desktop app if you really
[00:03:51] nail down these first two parts which is
[00:03:53] skills and loop engineering and memory
[00:03:54] and state. This applies to any and all
[00:03:57] problems not just AIOS. But before we
[00:03:59] dive into level one, a quick word from
[00:04:01] today's sponsor, me. So, I just released
[00:04:04] my cloud code master class and it is the
[00:04:05] number one way to go from zero to AI
[00:04:07] dev, especially if you don't come from a
[00:04:09] technical background. We focus on real
[00:04:11] use cases. It's updated every single
[00:04:13] week and it includes all of my personal
[00:04:15] build. So, everything you see in today's
[00:04:17] video that I'm using for my demos, you
[00:04:19] can find it here as well. So, if you
[00:04:21] want to get your hands on all that, you
[00:04:22] can find it inside of Chase AI Plus.
[00:04:24] There will be a link in the description.
[00:04:26] So, level one, skill architecture, loop
[00:04:28] engineering, all this stuff. What are we
[00:04:30] really talking about here? Well, there's
[00:04:31] sort of four subphases of level one. We
[00:04:35] have the workflow audit, we have the
[00:04:37] skill creation, we have automation, and
[00:04:39] then we have loop engineering. And so,
[00:04:41] step one is a workflow audit. Before we
[00:04:44] can create skills, we need to know what
[00:04:47] you actually need to create skills for.
[00:04:49] Because remember, why are skills
[00:04:51] arguably the most powerful thing in
[00:04:52] claude code? Well, because it allows us
[00:04:54] to get a specific output. We're telling
[00:04:56] Claude to do a specific thing in a
[00:04:58] specific way for a specific output. But
[00:05:00] what sort of specific outputs do you
[00:05:02] need constantly throughout your
[00:05:04] day-to-day and your week to week? Seems
[00:05:06] like an obvious question, yet most
[00:05:07] people cannot answer that. And even if
[00:05:09] they can answer it, they certainly
[00:05:11] haven't taken those workflows that they
[00:05:13] do manually inside of Cloud Code and
[00:05:15] turned it into skills or automated them.
[00:05:17] So this is the first thing you have to
[00:05:19] do. And this, if you do nothing else,
[00:05:21] will totally supercharge how you work
[00:05:23] with cloud code. So here's a visual
[00:05:25] representation of what I'm talking
[00:05:26] about. We have you and we have Claude
[00:05:28] code. And for most people, it stays just
[00:05:31] like this. And it's a purely manual back
[00:05:33] and forth. You open up the terminal, you
[00:05:35] open up claw desktop, and you tell it to
[00:05:37] do certain things. And inevitably,
[00:05:38] you're telling it to do the same things
[00:05:40] all the time. Well, what if instead we
[00:05:43] did an audit of everything you do
[00:05:46] dayto-day and week to week and all the
[00:05:47] ways you use Claude and we codify that
[00:05:50] into skills? You're doing the same tasks
[00:05:52] over and over. Why don't we actually
[00:05:55] consistent with the outputs and how they
[00:05:56] work? Now, if you have used skills in
[00:05:58] any capacity, the cell here is very
[00:06:00] obvious. And I'm just telling you to do
[00:06:02] what you do with skills already, but do
[00:06:04] that a hundred times more because
[00:06:06] undoubtedly the way you use Claude Code,
[00:06:08] whether it's as an individual or as a
[00:06:10] business, can be broken up into a number
[00:06:12] of different domains. For me, that
[00:06:13] includes things like research, content,
[00:06:15] my online community, my agency, my
[00:06:17] sales, on and on and on. And underneath
[00:06:20] each of those domains are different
[00:06:22] things that I do, specific tasks for
[00:06:26] content that include stuff like, hey, I
[00:06:28] need to do outlines for all my projects.
[00:06:30] I need to figure out the hooks for my
[00:06:31] videos. I need to repurpose my content.
[00:06:33] I need to create carousels. On and on
[00:06:35] and on and on. Why are those not skills?
[00:06:38] Truthfully, they should be. And yet, for
[00:06:41] most people, they probably don't have a
[00:06:43] large robust set of skills like I do
[00:06:45] right here. And this is the easiest way
[00:06:47] to improve cloud code. Now the practical
[00:06:49] question is how do you do this at scale?
[00:06:51] And there are a few different ways we
[00:06:53] can do this. Number one is we do this
[00:06:56] purely via a manual process. That means
[00:07:00] I go inside of clawed code. I already
[00:07:02] have an idea of what it is I do. I
[00:07:04] explain that task and then I turn it
[00:07:08] into
[00:07:10] can't type. We turn it into a skill. And
[00:07:12] obviously we're going to use the skill
[00:07:15] creator skill to do that, right? That's
[00:07:18] simple enough. The issue with doing
[00:07:20] this, especially if you haven't done it
[00:07:21] before, is you probably haven't
[00:07:24] validated how Claude Code should go
[00:07:26] about this. The ideal scenario is you've
[00:07:28] done this manually. You've confirmed it
[00:07:29] actually works, and then you tell Claude
[00:07:31] Code, hey, see how we just did that
[00:07:33] task? Now, I want you to turn it into a
[00:07:36] skill. And there's actually ways you can
[00:07:37] do that relatively quickly because
[00:07:39] remember, Cloud Code has access to
[00:07:42] essentially all your previous sessions.
[00:07:43] It can see the tool calls. It can see
[00:07:45] what you told it to do. It has the full
[00:07:46] back and forth. We can really get a head
[00:07:49] start on creating this sort of like
[00:07:51] skill repository by telling Claude Code,
[00:07:54] hey, I want you to take a look at our
[00:07:56] last three sessions, five sessions, 10
[00:07:59] sessions, 20 sessions. I want you to
[00:08:01] pull out everything we've done and give
[00:08:03] me a list of things that we can turn
[00:08:05] into skills that I do all the time. So
[00:08:08] that becomes option number two, which is
[00:08:10] we have it look at previous sessions and
[00:08:12] sort of pull the work out of us. This
[00:08:15] way, it's actually going off real data.
[00:08:17] You know, this isn't a guessing game of
[00:08:18] what you think you should do in Cloud
[00:08:20] Code. It's actually going to take a look
[00:08:21] at what you've done. And so, that prompt
[00:08:24] can just sound something like this.
[00:08:26] Hey, can you go through our last 10
[00:08:30] sessions that I've had back and forth
[00:08:32] with you? And I want you to sort of pull
[00:08:33] out some repeated task or things we've
[00:08:35] done over and over again that aren't
[00:08:37] skills yet, but that I want to turn into
[00:08:40] skills and create some sort of chart
[00:08:41] showing what that task is, what the
[00:08:43] output should be, and the proposed
[00:08:45] skill. So, that's pretty much it.
[00:08:47] Doesn't have to be fancy. You can talk
[00:08:48] to it in plain language. And like you
[00:08:50] can see right here, what is it doing?
[00:08:52] It's going to find our session files
[00:08:54] first. Now there's actually a third
[00:08:56] option for how we can approach this.
[00:08:59] Option number three is we have it do an
[00:09:02] interview right we have Claude code
[00:09:05] interview us and we say hey I'm just
[00:09:08] going to give you a stream of
[00:09:09] consciousness about what I do daytoday
[00:09:11] week to week and I want you to ask any
[00:09:13] questions if there's any blind spots and
[00:09:15] then I want Claude code to pull out of
[00:09:17] that conversation these sort of tasks
[00:09:19] that can be turned into skills. So, same
[00:09:22] sort of idea. It'd be the same sort of
[00:09:25] simple prompt. We'll just pull it up
[00:09:26] right now. And then I would say
[00:09:28] something like,
[00:09:31] I'm trying to turn all my daily and
[00:09:34] weekly tasks into skills when they make
[00:09:36] sense. So, I'm going to start off by
[00:09:38] giving you a stream of consciousness of
[00:09:40] sort of like what I do each day. And
[00:09:42] then I want you to sort of turn it into
[00:09:44] an interview and call out any blind
[00:09:47] spots because at the end of this I want
[00:09:48] you to have as much context as possible
[00:09:50] about what I do and sort of the outcomes
[00:09:52] I'm looking for and I want you to pull
[00:09:54] out specific tasks and I want to be able
[00:09:56] to turn these tasks into skills and
[00:09:58] eventually automations.
[00:10:02] That's pretty much it. Doesn't have to
[00:10:04] be fancier than that. The whole idea is
[00:10:07] that we are just throwing as much
[00:10:09] context as possible about our work,
[00:10:11] about our day, about our week into cloud
[00:10:13] code and codifying it. We kind of want
[00:10:16] to just turn what we do into a
[00:10:17] checklist. This is the kind of the
[00:10:19] saying, the way you should approach this
[00:10:20] is like you brought in some person to be
[00:10:22] your personal assistant. You want to
[00:10:24] offload as many tasks onto them as
[00:10:26] possible. Well, how would you do that?
[00:10:27] Well, it's pretty obvious. You would
[00:10:29] tell them what you do and then give them
[00:10:31] step-by-step instructions to do that.
[00:10:33] That's all we're doing. We're just doing
[00:10:35] it with clawed code. And yet most people
[00:10:38] don't do this. And because these are
[00:10:40] skills, these are now tangible workflows
[00:10:41] that we can look at and edit as needed
[00:10:43] until we really dial in those outputs.
[00:10:46] And right here you can see one of the
[00:10:47] repeated tasks that I pulled out from
[00:10:49] previous sessions. Things like checking
[00:10:51] for tool and repo updates for videos.
[00:10:53] And it continues to go on and on with
[00:10:54] these tasks it found. Now creating these
[00:10:57] skills is just layer number one of this,
[00:11:00] right? We've codified it. And oftentimes
[00:11:03] these are things are going to get
[00:11:04] repeated over and over. Well, if they're
[00:11:05] going to get repeated over and over, is
[00:11:07] there any reason why we don't simply
[00:11:09] turn these into automations,
[00:11:12] right? Again, we want to move away from
[00:11:13] this manual approach to everything.
[00:11:15] Well, I had this task I did manually.
[00:11:18] Now, it's a skill. It's been codified.
[00:11:19] Well, now let's just set it up into an
[00:11:21] automation if it makes sense. And this
[00:11:23] is so easy to do inside of Cloud Code.
[00:11:25] We can quite literally just prompt it,
[00:11:27] can we turn that skill into an
[00:11:28] automation? And if you want a more
[00:11:30] visual approach, you can set this up
[00:11:31] very easily inside of Claw Desktop. We
[00:11:33] just go to routines. We give it a name.
[00:11:36] So that just be like auto one. The
[00:11:39] instructions would just be run this
[00:11:42] skill. Insert the name of the skill. And
[00:11:44] then we would set it on a specific
[00:11:46] schedule. That's pretty much it. And the
[00:11:48] third level here would be setting up
[00:11:50] some level of loop engineering. Now, I'm
[00:11:53] not going to go ultra deep into loop
[00:11:54] engineering because the video I put out
[00:11:56] yesterday certainly does, but we have
[00:11:58] sort of the foundation for creating
[00:12:00] strong loops. We have the skill. We've
[00:12:03] turned it into an automation. Now, it's
[00:12:05] simply a question of well, are we taking
[00:12:08] a certain automation and are we trying
[00:12:09] to add some sort of like
[00:12:11] self-improvement loop to it? And this
[00:12:13] will tie into memory and state as well.
[00:12:15] But that's all I'm really going to
[00:12:16] mention there. Just understand if you're
[00:12:18] someone who's trying to dive into loop
[00:12:20] engineering and that whole side of the
[00:12:22] equation, you're set up very well to do
[00:12:24] this given we laid the foundation with
[00:12:26] our skills and our automations. But
[00:12:28] zooming out here for a second, this is
[00:12:31] the backbone of everything. It's
[00:12:34] codifying your life and making it so we
[00:12:37] can get consistent outputs from clawed
[00:12:39] code for the tasks we actually care
[00:12:41] about. And as you can imagine, that kind
[00:12:43] of has nothing to do with these fancy
[00:12:46] dashboards and all this other stuff that
[00:12:48] comes along within a OS. I love the
[00:12:50] fancy dashboards. I think they're really
[00:12:51] cool, but this is the power. And you can
[00:12:53] imagine applying that to any problem and
[00:12:56] any sort of use case with cloud code is
[00:12:58] is very simple and straightforward. It
[00:13:00] doesn't require any of the other levels,
[00:13:01] which is why I think it's important to
[00:13:03] sort of be able to create your own AIOS
[00:13:05] because as we stack these levels on top
[00:13:07] of one another, you can see how sort of
[00:13:09] modular and flexible this is. So
[00:13:12] workflow audit talked about the three
[00:13:13] different ways to do that, right? We can
[00:13:15] do it manually, we can have it look at
[00:13:16] our previous sessions, or we can have it
[00:13:17] run an interview. Once we've done that,
[00:13:19] we have it create the skills. Then we
[00:13:21] ask ourselves, hm, can any of these
[00:13:23] skills be automated? And then lastly, we
[00:13:25] kind of have that discussion about does
[00:13:26] loop engineering make sense for this
[00:13:28] particular use case? And speaking of
[00:13:29] loop engineering, that brings us into
[00:13:32] things like state and memory, which is
[00:13:35] level two. Now, a lot of what I'm going
[00:13:37] to talk about today will be in the
[00:13:39] context of Obsidian, but understand it
[00:13:41] doesn't have to be Obsidian. Everyone
[00:13:43] likes talking about Obsidian because
[00:13:44] it's free and it's relatively easy to
[00:13:47] understand. Everything that works with
[00:13:49] Obsidian can also be done inside of a
[00:13:51] traditional database, right? Doesn't
[00:13:53] have to be Obsidian. Obsidian is just
[00:13:55] simple to use. And really, even more so
[00:13:57] than Obsidian, it's the idea of file
[00:14:00] structures and setting up cloud code in
[00:14:03] a coherent manner. Truthfully, you could
[00:14:06] probably have no database and you could
[00:14:08] have no Obsidian. And if you just set up
[00:14:10] Cloud Code with a file structure that is
[00:14:12] coherent and makes sense, you're like
[00:14:14] 99% of the way there. Obsidian just
[00:14:17] makes it easy. And databases obviously
[00:14:19] have their own power that goes along
[00:14:20] with them. So, how should we set up this
[00:14:23] part of the equation? Well, we're going
[00:14:24] to answer that question through the lens
[00:14:26] of Obsidian and what the file structure
[00:14:28] should be doing for us. Now, Obsidian,
[00:14:30] like I mentioned before, is completely
[00:14:31] free. The idea with Obsidian is that you
[00:14:34] simply download it and then you're going
[00:14:36] to designate a folder on your computer
[00:14:39] as the vault. It can be any folder or it
[00:14:41] can be a brand new folder. Now, when
[00:14:43] you're installing Obsidian, you'll see a
[00:14:44] popup like this where again you can
[00:14:46] create a new vault or you can open a
[00:14:48] folder as a vault. Now, when we're
[00:14:50] talking about a vault, again, it's
[00:14:51] literally just a file. So, you need to
[00:14:53] ask yourself for this Agentic OS, what
[00:14:56] file should it live in? What file is
[00:14:58] going to have all the information I
[00:14:59] wanted to know about? So, if we're
[00:15:01] treating it like a personal assistant,
[00:15:03] perhaps one of the domains you're going
[00:15:05] to have it help you out with is like
[00:15:06] sales. So, you have a lot of sales data.
[00:15:08] Well, whatever file I designate as the
[00:15:10] vault, I'm going to put want to put at
[00:15:12] least a copy of all my sales data in
[00:15:14] there. That's sort of the idea. Now,
[00:15:15] once we've designated a folder as the
[00:15:17] vault, in order to connect Cloud Code to
[00:15:19] Obsidian, it's as simple as just opening
[00:15:21] Cloud Code inside Obsidian. So, I
[00:15:24] navigate inside my terminal to whatever
[00:15:27] I called that folder. In this case, I
[00:15:29] literally called my vault the vault. So,
[00:15:32] I'm now inside the vault. Next, I just
[00:15:34] open up Claude Code
[00:15:38] and boom, Claude Code for all intents
[00:15:40] and purposes is now connected to my
[00:15:42] vault. So, I now have my vault and
[00:15:45] Claude code is open and connected to it.
[00:15:47] Now, the question becomes, how do I
[00:15:50] actually set up my file structure inside
[00:15:51] the vault? This is not a trivial
[00:15:53] question. This is very important because
[00:15:56] the whole value ad for something like
[00:15:57] Obsidian is the idea that clawed code
[00:16:00] can be connected and opened inside of
[00:16:03] some folder that has a bajillion
[00:16:07] subfolders and a bajillion files inside
[00:16:09] of those folders. And you, the human
[00:16:11] being, can ask Claude Code a question
[00:16:13] about any of the files and folders
[00:16:15] inside of here and give you an accurate
[00:16:18] and quick answer. How do we do that?
[00:16:21] Well, it's going to all come down to how
[00:16:23] we sort of set this up, right? If we
[00:16:25] just have one folder with 10 million
[00:16:27] files in it and there's like no back
[00:16:29] links and nothing is connected and
[00:16:31] there's no sort of hierarchy, Cloud's
[00:16:33] going to struggle to quickly find you an
[00:16:35] answer. And when I mean it's slow, I'm
[00:16:37] also meaning it's going to use more
[00:16:39] tokens and ultimately it's going to cost
[00:16:40] you more money. So, we have to set this
[00:16:42] up in a clear manner. Your mental model
[00:16:44] here is setting up a map for Claude
[00:16:47] code. Right? We're looking at the
[00:16:48] knowledge graph of my Obsidian vault.
[00:16:50] These are all the files inside my vault
[00:16:52] and how they connect to one another. The
[00:16:54] ideal scenario is that when I tell
[00:16:57] Claude Code or ask it a question about
[00:16:59] something inside this giant morass of
[00:17:01] files, it has a very clear path to
[00:17:04] finding that file and therefore finding
[00:17:06] my answer. So think of Obsidian as
[00:17:08] essentially your filing cabinet for
[00:17:11] everything. Now there's become somewhat
[00:17:13] of a common way to set up your file
[00:17:16] structure inside of Obsidian when we're
[00:17:18] talking about cloud code. And this comes
[00:17:20] from Carpathy. This tweet from
[00:17:22] Cararpathy got over 20 million views and
[00:17:24] it was all about how he sets up his
[00:17:27] knowledge base using Obsidian so that
[00:17:29] large language models like Claude can
[00:17:32] access information quickly and
[00:17:34] effectively. And it goes something like
[00:17:36] this. We have the primary vault which
[00:17:38] you are now familiar with. And then we
[00:17:40] sort of have three subfolders. We have
[00:17:43] one subfolder which we call the slash
[00:17:47] raw folder. R A. This folder is where
[00:17:50] all unstructured data goes. Beneath that
[00:17:54] we have another subfolder called the
[00:17:57] wiki folder. The wiki folder is where we
[00:18:00] have taken the unstructured data. Think
[00:18:02] hey we just did all this research about
[00:18:05] I don't know AI agents right a bunch of
[00:18:08] unstructured data includes a bunch of
[00:18:10] articles and all that sort of stuff and
[00:18:11] we've turned it into structured data.
[00:18:13] We've now turned that into like a
[00:18:16] Wikipedia style article about AI agents.
[00:18:20] So the data and like what going on here
[00:18:22] and everything we want to know about it
[00:18:23] is very clear, right? This is instead of
[00:18:26] trying to go through, you know, 20
[00:18:27] different like source documents, we now
[00:18:29] have everything nice and neat under this
[00:18:30] wiki file. The third subfolder in the
[00:18:33] vault is essentially for outputs.
[00:18:36] So let's say I did my research about AI
[00:18:40] agents which is now in the raw folder
[00:18:42] folder number one. I then turn that into
[00:18:45] structured data into a Wikipedia article
[00:18:47] which is in folder number two. Now I
[00:18:49] want to turn that into say and let me
[00:18:51] move this over here. Let's say I now
[00:18:52] want to turn that into a I don't know a
[00:18:54] slide deck. Okay, some sort of clear
[00:18:57] deliverable. Right? We're not just
[00:18:59] talking about data here. We've actually
[00:19:00] turned it into something useful. Well
[00:19:01] that would be folder three. Okay. And so
[00:19:04] the idea is for most of the data we play
[00:19:06] around with, we can sort of set it up
[00:19:08] like this. Unstructured, structured, and
[00:19:12] then outputs. That is the Carpathy
[00:19:15] obsidian rag. And I say rag in air
[00:19:17] quotes because this is a new rag system.
[00:19:20] But that's one way to do it. Now the
[00:19:22] beauty of this Carpathy system isn't
[00:19:24] necessarily that we split it up into
[00:19:27] unstructured, structured, and outputs.
[00:19:28] The real beauty is that at every level
[00:19:31] of this, we have an index
[00:19:35] MD file, right? This is just a text
[00:19:37] document, a markdown file that is
[00:19:40] telling claude code at every level we go
[00:19:43] down what it's looking at. So, for
[00:19:45] example, if I'm talking to Claude Code,
[00:19:48] I'm talking to my AIOS and I say, "Hey,
[00:19:49] I want you to give me all the
[00:19:51] information about AI agents. Remember,
[00:19:53] we created a wiki article about AI
[00:19:56] agents."
[00:19:57] Well, first thing it's going to do is
[00:19:59] it's going to look in the vault and it's
[00:20:01] going to hit this index.md. And this
[00:20:03] index.md is going to say, hey, inside at
[00:20:06] this level of our system, we have a raw
[00:20:08] file for unstructured data, a wiki for
[00:20:10] structured data, and outputs for things
[00:20:12] like slide decks and that sort of thing.
[00:20:13] So, Claude Code knows right away, hey,
[00:20:16] he wanted information about AI agents.
[00:20:18] So, we're going to go to this wiki
[00:20:19] article. Now, inside of the wiki
[00:20:21] article, inside of the wiki folder
[00:20:23] rather, guess what's inside here? There
[00:20:25] is also an index.n MD. Now, we have one
[00:20:29] article in here. So, does it really need
[00:20:32] essentially a table of contents for a
[00:20:34] folder with one thing in it? No, of
[00:20:36] course not. But what if you've been
[00:20:37] using this for a year or two or five and
[00:20:39] you have not one or two or 10, but you
[00:20:41] have thousands of documents inside of
[00:20:43] here and potentially subfolders as well?
[00:20:45] Well, an index.md is going to make it
[00:20:47] way easier for cloud code to hit that
[00:20:49] folder and understand what it's looking
[00:20:51] at and where it needs to go. Because
[00:20:52] remember, what is the purpose of all
[00:20:54] this? is to give Claude code a map. And
[00:20:57] if it every single new room it enters,
[00:20:59] there's a clear spot it can go to and
[00:21:02] figure out what it's looking at, it's
[00:21:03] going to be faster and it's going to be
[00:21:05] cheaper. And it's important to
[00:21:06] understand that the power comes from
[00:21:08] that, not necessarily the somewhat
[00:21:10] arbitrary folders we created. It just
[00:21:13] needs to know where it's going. You
[00:21:15] don't have to do raw. You don't have to
[00:21:16] do outputs. You don't have to do any of
[00:21:18] this carpathy stuff. You just need a map
[00:21:20] for cloud code that makes sense. And
[00:21:21] it's probably going to be unique to you
[00:21:23] because your structures of your data and
[00:21:25] what you're trying to do are always
[00:21:26] going to be unique. So you have a better
[00:21:30] answer than anyone for how you should
[00:21:31] structure this. Now if you don't have
[00:21:32] that answer, guess who can help you?
[00:21:34] Claude Code. Simply tell to look at your
[00:21:36] vault and say, "Hey, what sort of
[00:21:37] structure makes sense? Oh, use
[00:21:39] Carpathy's obsidian rag setup for
[00:21:41] inspiration." That will kind of do
[00:21:44] everything you need it to do. The only
[00:21:46] other thing I would mention would be,
[00:21:47] hey, let's create a claw.md file that
[00:21:50] talks about this. In my claw.md file
[00:21:52] inside of my vault, it talks about my
[00:21:54] vault conventions, specifically the
[00:21:56] vault structure, aka what sort of files
[00:21:58] and folders it's looking at. You can see
[00:21:59] over here on the left, I don't just have
[00:22:01] three. I have several. I have content,
[00:22:02] notes, runs, inbox, ops, projects, etc.,
[00:22:05] etc. Furthermore, I have a whole thing
[00:22:07] about the navigation pattern,
[00:22:08] essentially saying, "Hey, when you're
[00:22:09] trying to find something, here's the
[00:22:11] path you should follow." And I think
[00:22:13] using that sort of template is very
[00:22:14] flexible. you can apply it to any sort
[00:22:16] of structure or any sort of data you're
[00:22:18] working with and you can come up with
[00:22:20] something that will be effective for
[00:22:22] you. So when we talk about level two
[00:22:25] that's what we're talking about. We're
[00:22:26] giving cloud code a map and it needs to
[00:22:28] make sense. Now this also plays into you
[00:22:30] know loop engineering because and skills
[00:22:33] and automations because all these
[00:22:34] outputs need to go somewhere and they
[00:22:36] need to be logged and they should be
[00:22:37] logged in a way which you know what I'm
[00:22:39] going to say makes sense for loop
[00:22:40] engineering specifically when we talk
[00:22:42] about self-improving
[00:22:44] skills and automations. Well, for that
[00:22:47] to work, we need somewhere where claude
[00:22:51] code can see what the past runs have
[00:22:52] done or really what the loop should be
[00:22:54] able to see what past runs it's done. So
[00:22:55] then it can make future improvements.
[00:22:57] And this should all be tied together in
[00:22:59] the same place. And if you master those
[00:23:01] two levels, you have 90% of the power of
[00:23:05] an AIOS already at your fingertips. And
[00:23:07] all this can be done through the
[00:23:08] terminal or the desktop app or anything
[00:23:11] because at this point you've kind of
[00:23:12] codified your workflows and now you have
[00:23:14] a way to actually see what's going on,
[00:23:16] record what's going on, sort of create
[00:23:18] your second brain and allow cloud code
[00:23:20] to pull out insights you otherwise
[00:23:22] wouldn't have in an efficient manner.
[00:23:24] Now level three is where we put a custom
[00:23:27] visual wrap around everything we've done
[00:23:28] up to this point. And we have a few
[00:23:30] options with how we do this. Obviously,
[00:23:32] it can be purely customized, but we can
[00:23:34] make this something that is purely web
[00:23:36] app based or something that is obsidian
[00:23:38] based. Now, when we talk about web
[00:23:39] appbased, we're talking about something
[00:23:41] like this. Again, this is cloud code
[00:23:43] under the hood. It's connected with
[00:23:45] Obsidian, but I now have a bunch of
[00:23:47] custom metrics that I have tuned for
[00:23:49] what I need to see. So, for me, on the
[00:23:51] left, it shows stuff related to my
[00:23:53] content creation, right? What's my
[00:23:55] YouTube subscriber count, Instagram, my
[00:23:57] latest video, my clawed 5 hour window? I
[00:23:59] have directives that are pulled from my
[00:24:01] Google calendar. I can look at documents
[00:24:03] that it's created. Over here on the
[00:24:04] right, I've taken a bunch of my
[00:24:06] automations and skills and I've turned
[00:24:08] them into just single buttons. So, if I
[00:24:11] just click on something like inbox
[00:24:12] brief, you can now see that it's cued.
[00:24:15] It's popped up right over here. And
[00:24:17] under the hood, Claude is running, going
[00:24:19] through my inbox, creating drafts, and
[00:24:21] it's going to let me know what it thinks
[00:24:22] is important. And the cool thing about
[00:24:24] this is again you can change whatever
[00:24:27] metrics are shown here to be whatever
[00:24:29] you want. The whole idea of this being a
[00:24:32] floor raising mechanism. The idea being
[00:24:34] I can now give some of the power to
[00:24:35] claude code to non-technical team
[00:24:37] members and clients. We'll talk about
[00:24:38] that in level four has a lot to do with
[00:24:41] what you see over here on the right
[00:24:42] where we've turned automations and
[00:24:43] skills into a button you can literally
[00:24:46] press. So instead of telling them, hey,
[00:24:48] learn how to use cloud code, here's a
[00:24:49] skill you need to install. Here's how
[00:24:50] you run the skill. Here's how you
[00:24:51] automate it. No, I'm just going to go
[00:24:53] ahead and I'm going to set up this AIOS
[00:24:56] for them. And now they can just click a
[00:24:58] button and it will do all that for them
[00:25:00] and it'll either dump it inside their
[00:25:01] own Obsidian or Teams Obsidian.
[00:25:04] >> Inbox brief is done. Inbox brief ready.
[00:25:08] 32 threads triaged with a Gear Up
[00:25:11] contract and the Open AI merge campaign
[00:25:14] flagged urgent.
[00:25:15] >> All right, that's enough out of you. But
[00:25:17] yeah, you can hear in this case I also
[00:25:18] have a voice model attached to it. So I
[00:25:20] can talk to it. It can talk back. And
[00:25:22] that voice model is completely local, by
[00:25:24] the way. Right? That's running on my
[00:25:26] actual computer that isn't going out to
[00:25:28] 11 Labs. So it's free. If I click on the
[00:25:30] inbox brief,
[00:25:33] it brings up the entire write up. And
[00:25:35] this too is something that I can open
[00:25:37] inside of Obsidian. And speaking of
[00:25:39] Obsidian, you can also create a command
[00:25:41] center, a visual layer inside of
[00:25:43] Obsidian itself. And that's what we see
[00:25:45] right here. So the metrics are a little
[00:25:47] bit different, but they're similar. I
[00:25:49] can see my token burn. I have, you know,
[00:25:51] the same sort of setup where I click a
[00:25:53] button and it runs skills or
[00:25:54] automations. I have different tabs. So
[00:25:57] for me, I want more insight into sort of
[00:25:59] like audience metrics that's going on
[00:26:01] the content side as well as some
[00:26:02] research stuff. So you can make this
[00:26:05] extremely customized. And again, the
[00:26:07] cell here at this point isn't the fancy
[00:26:10] visuals. It's that I can have a one-stop
[00:26:12] shop for a lot of different things that
[00:26:14] are a little harder to have visibility
[00:26:16] into when I'm strictly inside the
[00:26:18] terminal. Now, in terms of how you would
[00:26:20] create something like this, the web app
[00:26:22] is just like creating any sort of web
[00:26:25] app using cloud code. You're going to
[00:26:26] give it some sort of visual idea. I
[00:26:28] mean, obviously my exact setups you can
[00:26:30] find inside of Chase AI Plus, but you
[00:26:32] should just find some sort of, you know,
[00:26:34] website or setup you like. You can take
[00:26:36] a screenshot of this. You would dump it
[00:26:38] into clawed code and you essentially say
[00:26:39] like, hey, here's all the skills I
[00:26:42] already use. I want this connected to
[00:26:44] the vault. here are the metrics that are
[00:26:46] important to me that I want to see in
[00:26:48] one place. Let's go ahead and create
[00:26:49] this. Let's put a visual wrapper over
[00:26:51] all this. And the same deal goes for
[00:26:53] Obsidian. Obsidian runs in a plug-in
[00:26:55] system. So, you're pretty much creating
[00:26:57] an app, but it's specifically for
[00:27:00] Obsidian. And if you just tell Claude
[00:27:03] Code to hey say, hey, can you sort of
[00:27:05] take the web app we just created and
[00:27:07] create an Obsidian plug-in version of
[00:27:09] that? Again, it will give you something
[00:27:10] like this. And you just install it and
[00:27:12] run it from Obsidian. Now, a quick note
[00:27:14] about what's going on under the hood
[00:27:16] here. Now, under the hood, if I click
[00:27:18] one of these buttons, which again are
[00:27:19] related to skills. Let's say I click the
[00:27:21] morning brief skill. What's actually
[00:27:22] occurring? Well, this is essentially
[00:27:24] calling on a headless version of clawed
[00:27:27] code. So, it's just like as if I opened
[00:27:29] up my terminal and I have a version of
[00:27:32] clawed code running and it's now going
[00:27:34] to run, you know, forward slashming
[00:27:37] brief. The difference is when I click
[00:27:40] that button, it's doing a headless
[00:27:41] version of it. So, this terminal doesn't
[00:27:43] literally pop up on your computer. It's
[00:27:45] headless. It's invisible. And it uses a
[00:27:48] command called claude-p.
[00:27:51] Now, there was some drama with claude
[00:27:53] dashp not too long ago because Anthropic
[00:27:55] came out and said, "Hey, if you use
[00:27:57] claw-p, it's not going to pull from your
[00:28:00] cla subscription. It's going to pull
[00:28:02] from this $200 credit which is tied to
[00:28:04] API costs." That was kind of a problem.
[00:28:06] Although, they've sort of walked back
[00:28:08] from that and that isn't something that
[00:28:10] has occurred yet. So for now, this is
[00:28:12] still pulling from your max plan. So
[00:28:13] it's the same as if you opened up your
[00:28:15] terminal and ran it. And that's how
[00:28:16] we're able to create these sort of
[00:28:17] structures that still call on cloud
[00:28:20] code. We get all the power out of cloud
[00:28:21] code, but it's done invisibly behind the
[00:28:23] scenes. So when we talk about level
[00:28:25] three, what is this bias? Well, bias
[00:28:26] customization. We aren't locked into the
[00:28:28] terminal or the desktop app. We can have
[00:28:30] it show whatever we want. We also have
[00:28:32] the ability to give this to members of
[00:28:35] our team. This is what we talk about in
[00:28:37] level four, which is distribution. I
[00:28:39] mentioned a little bit earlier. If I
[00:28:40] hand someone this web app and it's tied
[00:28:42] to all these different skills, they're
[00:28:44] just one click away from getting a lot
[00:28:45] of power out of cloud code. Because
[00:28:46] remember, all the power comes from those
[00:28:48] skills and automations. If I make it
[00:28:50] super easy for someone to use those,
[00:28:51] well, it's kind of like spinning them up
[00:28:53] on cloud code without actually spinning
[00:28:55] them up on cloud code. The obvious
[00:28:57] question then becomes, well, how would
[00:28:58] you actually distribute to them? And
[00:29:00] there's a few options. When we're
[00:29:01] talking about something that's web-
[00:29:02] based, it's actually much easier. So
[00:29:04] giving something this somebody this
[00:29:06] versus giving them the Obsidian version
[00:29:08] is much simpler because since it's web-
[00:29:10] based I can put it on GitHub. I can, you
[00:29:12] know, create a whole zip folder. I it's
[00:29:14] very easy for me to transfer it to them
[00:29:16] and have it get get it up and running
[00:29:18] versus something like Obsidian.
[00:29:21] Obsidian is a little harder to work that
[00:29:22] way. So Obsidian would require a little
[00:29:24] more hands-on work from you. So if
[00:29:26] you're like, "Hey, I really like the
[00:29:27] sort of like Obsidian Command Center
[00:29:29] deal. How would I bring that to a member
[00:29:30] of a team?" Well, you would kind of have
[00:29:31] to set it up for them. It's not as
[00:29:33] straightforward. It's not much more
[00:29:35] difficult, but it isn't as simple as
[00:29:36] like, hey, there's a GitHub repo. Go
[00:29:38] ahead and clone it and point Cloud code
[00:29:40] edit. But again, the customization piece
[00:29:42] is a huge cell here, especially for
[00:29:44] those of you who are doing any sort of
[00:29:46] client work. I can't tell you the amount
[00:29:49] of people who want to use AI and want to
[00:29:50] use Claude, but are totally turned off
[00:29:53] or frankly just really scared of the
[00:29:55] terminal and even the desktop app. Like,
[00:29:56] it is a bridge too far for most people.
[00:29:58] If you're watching this video, you
[00:29:59] probably scoff at that. But I'm telling
[00:30:01] you, you live in a bubble that 99% of
[00:30:03] people just like won't go there no
[00:30:04] matter what you do. And being able to
[00:30:06] say, "Hey, instead I'm just going to
[00:30:07] throw you this and I'm going to set it
[00:30:09] up for you and you just either talk to
[00:30:11] it with a voice or you press a few
[00:30:12] buttons." It goes a long way. The sort
[00:30:14] of dashboard effect with a non-technical
[00:30:17] population like genuinely needs to be
[00:30:19] studied because it changes how people
[00:30:20] interpret these like technical tools.
[00:30:22] And so zooming out now that we've gone
[00:30:24] over levels three and four, you can see
[00:30:26] they're really just the cherry on top of
[00:30:28] the AIOS.
[00:30:30] Almost all the power, almost all of your
[00:30:32] time should be invested in these first
[00:30:35] two levels. The skills, the loop
[00:30:37] engineering is the automation, the
[00:30:39] codification, the memory, and the state,
[00:30:41] right? Can you do the same things with
[00:30:43] cloud code every time? Can you be
[00:30:44] consistent? and can we log those things
[00:30:46] and essentially create the second brain
[00:30:48] for cloud code that it can not only
[00:30:50] reference but use to improve upon what
[00:30:52] it already does. If you can figure out
[00:30:55] that then you're going to be well ahead
[00:30:58] of the general population when it comes
[00:30:59] to using this tool. So that is where I'm
[00:31:01] going to leave you for today's video. I
[00:31:03] hope breaking down AIOS and sort of
[00:31:05] these four levels made it a bit more
[00:31:06] clear about how these things work, where
[00:31:08] the value is, and how you can create
[00:31:10] something like this yourself. Like I
[00:31:12] mentioned earlier, if you want my exact
[00:31:14] setups, that's all inside of Chase AI
[00:31:16] Plus.
