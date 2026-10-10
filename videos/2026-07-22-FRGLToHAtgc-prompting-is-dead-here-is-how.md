---
video_id: FRGLToHAtgc
title: Prompting is dead. Here is how you create loops
channel: Alex Finn
url: "https://www.youtube.com/watch?v=FRGLToHAtgc"
watched_date: 2026-07-22
watched_at: "2026-07-22T12:00:00Z"
watch_count: 1
duration_seconds: 1090
source: youtube-history-browser
added_date: 
history_label: Jul 22
history_order: 163
watched_at_precision: date-from-history-label
watched_percent: 20
estimated_watched_seconds: 218
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video introduces "loop engineering"—replacing manual AI coding workflows with three automated skills: spec, build, and review. Instead of repeatedly prompting Claude Code or Codex and manually testing each iteration, users specify ideas once in the morning (spec skill interviews you about your feature), the system autonomously builds issues throughout the day (build loop), then automatically reviews and tests the completed work (review loop). Integration with Linear (issue tracking) and Slack (notifications) allows the AI to manage the entire pipeline independently; when code is ready, it posts a Slack message where the user approves by reacting with a rocket emoji. This achieves ~95% automation—work shifts from all-day manual iteration to five minutes of morning specifications and evening merge approvals.

To implement: set up two simple `/loop` commands (`/loop 5 min /build` and `/loop 5 min /review`) using prompts from a free Google Doc the speaker provides; connect Linear and Slack (or Discord/Telegram) to your coding agent using the provided setup prompts. The AI handles all configuration automatically. Allocate 30 minutes to set up the system once, then you can run multiple projects in parallel—specify ideas for all of them in the morning, and they build autonomously while you're away. The simplest approach: copy the video transcript and ask your agent to set it all up for you.

## Transcript

[00:00:00] Everyone and their mothers has been
[00:00:01] talking about vibe coding loops lately,
[00:00:04] aka loop engineering. I mean, take a
[00:00:07] look here. Everyone from Peter Steinberg
[00:00:09] has been saying, "Hey, don't prompt your
[00:00:11] agents anymore. You should be building
[00:00:13] your loops." Even Boris from Claude
[00:00:16] Code, the guy who invented Claude Code,
[00:00:18] all he's talking about is loops. "I
[00:00:21] don't prompt Claude anymore. What I
[00:00:22] mostly use now is loops. I create loops.
[00:00:25] They do my entire job." Well, I'm here
[00:00:28] to tell you they ain't lying. Here is
[00:00:31] the issue though with all this. They've
[00:00:32] all been talking about loops, but nobody
[00:00:35] is telling you how to build a loop.
[00:00:37] There's no one out there directing you
[00:00:39] on what a loop actually is. I have good
[00:00:42] news for you. I'm about to show you. I'm
[00:00:45] here to report I've built an incredible
[00:00:48] loop that's basically automated 95%
[00:00:51] of the vibe coding work I do. In this
[00:00:54] video, I'm going to show you how to
[00:00:56] build it and use it. The most
[00:00:58] beginner-friendly
[00:01:00] loop engineering video you've ever seen
[00:01:02] in your life. If you stick with me here
[00:01:04] and build out the things I'm about to
[00:01:06] show you with you. I'll include all the
[00:01:07] prompts, instructions, everything. You
[00:01:09] will produce 100x more with your vibe
[00:01:13] coding, or I'll refund you all the money
[00:01:15] you spent on this video. You are about
[00:01:17] to watch a historic first video. The
[00:01:20] first video that deep dives into
[00:01:22] building an extremely powerful vibe
[00:01:25] coding loop. This is loop engineering
[00:01:28] 101. Now, let's lock in and get into it.
[00:01:31] So, let's talk about how you vibe code
[00:01:32] before loop engineering and after loop
[00:01:35] engineering. This is how you vibe code
[00:01:37] before loop engineering. This is
[00:01:38] probably what you're doing today. You go
[00:01:41] to Claude Code, you go to Codex, you
[00:01:42] send it a prompt, you say, "Hey, build
[00:01:44] this UI, build this game, build this
[00:01:46] feature." It builds it, and then you
[00:01:48] test it, and you sit there and manually
[00:01:50] test it. When that's done, you send
[00:01:51] another prompt, "Okay, now add this
[00:01:53] button." Then adds the button, and then
[00:01:54] you test it. Every part of this is
[00:01:57] manual, right? Everything you do is
[00:01:59] completely manual. Everything you do
[00:02:00] requires either you typing a prompt or
[00:02:03] you testing it out. And here's the
[00:02:05] biggest issue with it all. If you're not
[00:02:07] at your computer and you're not actively
[00:02:10] prompting or testing, nothing's
[00:02:12] happening. Nothing's advancing. I'm
[00:02:14] juggling like six different projects at
[00:02:17] once right now. And before, if I wasn't
[00:02:20] spending time on each one of those
[00:02:21] projects, they weren't advancing. Only
[00:02:24] one project was advancing at once. You
[00:02:26] as the human being are the bottleneck.
[00:02:29] And while this was a big advancement
[00:02:31] over just manually writing code, right?
[00:02:33] That's what people were doing before a
[00:02:35] couple years ago. Insane, right? While
[00:02:36] this is a big efficiency gain over just
[00:02:39] manually writing code, it's still not
[00:02:42] maximum performance. It's still not
[00:02:44] maximum automation because you're still
[00:02:46] doing everything manually. Let me
[00:02:49] introduce you to the new age. Let me
[00:02:51] introduce you to how you will be vibe
[00:02:52] coding after you're done watching this
[00:02:54] video. We're going to go over here. This
[00:02:57] is the fin loop. That is right. I named
[00:02:59] the loop. I've Hey, I invented the loop.
[00:03:02] I'm allowed to name the loop. This is
[00:03:03] the fin loop. Here is how it works. It
[00:03:06] consists of three different skills:
[00:03:09] spec, build, review. You spend a couple
[00:03:12] minutes telling the agent exactly the
[00:03:14] ideas in your head, and then it goes in
[00:03:17] a loop and all day builds it out,
[00:03:20] reviews it, tests itself, builds it out,
[00:03:22] reviews it, tests itself over and over
[00:03:24] and over again completely autonomously.
[00:03:26] And then, at the end, you quickly click
[00:03:29] through and it all merges. Instead of
[00:03:31] having to work all day completely
[00:03:33] manually prompting your agent and
[00:03:35] testing it yourself, the only thing
[00:03:37] you're doing is kind of loosely telling
[00:03:39] it the ideas in your head, and it goes
[00:03:41] and it just builds and reviews, builds
[00:03:42] reviews tests, builds reviews tests, and
[00:03:44] merges it all. Your work goes from
[00:03:46] sitting at your computer all day to
[00:03:48] coming in, waking up in the morning,
[00:03:50] giving a couple ideas, and at the end of
[00:03:52] the day you come back to computer and
[00:03:53] they're all done and merged. 95% of your
[00:03:56] work now is completely automated. You're
[00:03:58] not sitting there and prompting over and
[00:04:00] over again. You're giving a couple ideas
[00:04:02] and the AI figures it all out on its
[00:04:03] own, builds it all out, tests it. It's
[00:04:06] constantly working even if you aren't
[00:04:08] there. So, even if you have just 5
[00:04:09] minutes free in the morning, you go into
[00:04:11] this loop, which again, I'll show you
[00:04:12] how to build out in just a second, stick
[00:04:14] around here, and it will go and work
[00:04:17] autonomously for you, knowing exactly
[00:04:19] what to build, knowing exactly how to
[00:04:20] test, knowing exactly how to merge. This
[00:04:23] can be done with any vibe coding tool on
[00:04:25] planet Earth you're using, whether it's
[00:04:26] Codex, Claude Code, whatever you prefer.
[00:04:29] Plus, there are some additional tools
[00:04:31] added on, which I'm going to show you,
[00:04:32] and they're all free. You just add them
[00:04:33] onto your coding agent and you have this
[00:04:35] really, really nice loop set up that you
[00:04:37] can manage and control from anywhere in
[00:04:39] the world. You don't even have to touch
[00:04:41] Codex or Claude Code anymore. I'll go
[00:04:42] into more details in a second. This is
[00:04:44] super simple, super easy. I'll give you
[00:04:47] the exact prompts on how to set up the
[00:04:49] skills you need to set up this loop. And
[00:04:51] now, what I'm going to do is show you
[00:04:53] how it works, then show you how to set
[00:04:55] it up. But before we do that, building
[00:04:57] loops for your agent basically just
[00:04:59] makes your agent way more reliable.
[00:05:01] There are many other ways to make your
[00:05:04] agent reliable as well, and thank God
[00:05:06] for my friends at HubSpot. They built
[00:05:09] the Claude Code Playbook, build systems
[00:05:11] that make AI reliable. Just for the
[00:05:13] subscribers of my channel, you get this
[00:05:15] playbook for free. This playbook gives
[00:05:17] you systems that help your agents go
[00:05:19] from sometimes doing what you say to
[00:05:22] always doing what you say and being
[00:05:23] incredibly reliable. In this
[00:05:26] easy-to-read playbook, you'll learn all
[00:05:28] the systems and tricks to create a
[00:05:29] really impactful, powerful Claude rules
[00:05:32] file. You'll learn how to prompt your
[00:05:33] agent better so you get better results.
[00:05:36] Hooks that make sure your agent don't go
[00:05:38] off the rail. And by the way, these all
[00:05:39] work with the loop I'm about to show
[00:05:41] you. They all integrate perfectly. It'll
[00:05:43] make the loop I'm about to show you even
[00:05:44] more reliable. Sub-agents so you can
[00:05:46] have armies of agents working for you,
[00:05:48] and so much more. It's going to improve
[00:05:50] the quality of your Claude code output
[00:05:52] by a ton. My favorite part is the
[00:05:54] section on dynamic workflows. You can
[00:05:57] have Claude write an orchestration
[00:05:58] script that runs up to 1,000 agents
[00:06:01] while keeping the lead agent's context
[00:06:03] completely clean. That's really, really
[00:06:05] relevant to if you're going to build out
[00:06:07] the coding loop we're talking about in
[00:06:08] this video cuz it all ties together.
[00:06:10] This is one of the best educational
[00:06:12] materials I've ever read about Claude
[00:06:14] code. So, make sure check it out down
[00:06:16] below. Link for this free playbook down
[00:06:18] below. You got nothing to lose. And
[00:06:20] thanks to my good friends and partner at
[00:06:21] HubSpot for supporting the channel and
[00:06:24] the Fin Fam community. So, as I talked
[00:06:26] about earlier, there are three skills
[00:06:28] involved this loop. I'm going to be
[00:06:30] doing this in Claude code. You can do
[00:06:31] this in Codex, Claude code, any tool you
[00:06:34] want as long as you can build custom
[00:06:36] skills, which basically every tool on
[00:06:37] planet Earth allows you to do right now,
[00:06:39] you can run this loop. Again, three
[00:06:41] skills involved: spec, build, and
[00:06:44] review. Mine are called him spec, him
[00:06:46] build, him review. So, I'm just doing it
[00:06:46] in my him project. But, all you need to
[00:06:48] know is spec, build, and review. First
[00:06:51] is spec. Again, spec is the first part
[00:06:53] of this loop. This is what helps the
[00:06:55] coding agent capture all of your ideas.
[00:06:58] This is what's going to kick off the
[00:07:00] entire loop you see here. Basically,
[00:07:02] what I'm about to show you is the only
[00:07:03] manual work you need to do to pump out
[00:07:06] tons and tons of high-quality code. So,
[00:07:08] you wake up in the morning, you grab
[00:07:09] your cup of coffee. Now, you want to get
[00:07:12] some things built out. So, you're
[00:07:13] basically going to your agent saying,
[00:07:15] "Hey, here's everything that's top of my
[00:07:16] mind." What you do is you use the spec
[00:07:18] skill, you give a high-level what your
[00:07:20] idea is, what the feature is, and what
[00:07:23] the spec skill is going to do is going
[00:07:25] to ask you enough questions about what
[00:07:27] your idea is until it understands it
[00:07:30] completely and can build out a ton of
[00:07:33] features for your agent to build. It's
[00:07:35] basically going to interview you, come
[00:07:37] up with a ton of details. So, To you
[00:07:40] have a game you want to build, you do
[00:07:42] {slash} spec, then say I want to build a
[00:07:44] game, then you hit enter. And now my
[00:07:47] agent's going to start asking me a bunch
[00:07:49] of questions until it feels fully
[00:07:51] confident it can spec out everything it
[00:07:53] wants to build in detail. So, I just
[00:07:55] answered about 15 questions that allows
[00:07:58] it to understand in detail exactly the
[00:08:01] feature I'm trying to build in my app,
[00:08:03] Henry. It came back and now has five
[00:08:05] issues it's going to file for me and
[00:08:07] send to the building loop. Again, the
[00:08:10] spec skill comes up with a bunch of
[00:08:12] issues. Issues are basically detailed
[00:08:15] tasks with acceptance criteria, sends it
[00:08:18] to our loop, build review test, build
[00:08:20] review test. The agent handles all this
[00:08:23] for us, and then we come back at night
[00:08:25] after all the work is done and merge it
[00:08:27] really quick. So, we did spec, it came
[00:08:29] up with five different issues it's going
[00:08:31] to send to the loop, we just need to
[00:08:33] approve it. So, as you can see here, the
[00:08:35] spec skill filed five new issues. And
[00:08:38] now if we go into Linear, which is the
[00:08:40] free app we're using to track all these
[00:08:43] issues, we can check them all out. So,
[00:08:45] here's an example one of the issues it
[00:08:47] made. The AI built out this incredibly
[00:08:50] detailed document with everything about
[00:08:54] the issue or the task the AI agent needs
[00:08:56] to build, all the acceptance criteria
[00:08:59] including the non-goals, so what it
[00:09:00] shouldn't be doing, everything about the
[00:09:02] scope, notes, and expectations on how to
[00:09:05] test it. This is all automatically built
[00:09:07] out by that spec skill. Multiple of
[00:09:10] these issues, and this is all in Linear.
[00:09:12] For those who haven't used it, I've told
[00:09:14] you to download it a million times.
[00:09:15] Completely free project management tool
[00:09:18] that basically acts as a second brain
[00:09:21] for your coding agent. As you can see
[00:09:23] here, it has all these different issues
[00:09:25] I'm tracking. It basically allows my
[00:09:27] coding agents, Codex, Claude code,
[00:09:29] whatever I'm using, to remember every
[00:09:31] task it's working on, so that when I
[00:09:33] come back or spin up new agents, it can
[00:09:35] resume from its current state. It's
[00:09:37] basically a second brain and it's
[00:09:39] awesome, free, you should download it.
[00:09:41] So, all those issues are here. Next,
[00:09:43] after those issues are built, it's time
[00:09:45] for the automated part. Our work here is
[00:09:47] done. We came in in the morning, we
[00:09:49] drank our coffee, we gave a couple
[00:09:51] ideas, answered a couple questions. Now,
[00:09:53] the AI takes it from here and now it's
[00:09:55] going to use our two other skills, build
[00:09:57] and review, to autonomously build
[00:10:00] everything out, then verify what it
[00:10:02] built works. Previously, what you were
[00:10:04] doing in Vibe Coding was you were
[00:10:06] saying, "Okay, now build this out."
[00:10:08] You're waiting there while it codes and
[00:10:09] prompts, then you were opening up
[00:10:10] localhost, testing it out, clicking
[00:10:12] around, then going back, "Hey, build
[00:10:13] this now. No, change this." Now, we have
[00:10:15] skills that describe in detail the best
[00:10:19] practices around how to build out these
[00:10:21] specs and how to review them and test
[00:10:23] them. I mean, it is doing thorough
[00:10:25] testing on its own. It's opening up
[00:10:28] browsers, it's clicking around, it's
[00:10:29] doing everything. Let me show you how
[00:10:31] this works. So, let's set up the build
[00:10:33] loop. The build loop that I'll go over
[00:10:35] and over and over again building out
[00:10:37] every single spec that is in our
[00:10:39] backlog, right? As you saw in the last
[00:10:41] screen, we had five specs built out from
[00:10:43] our spec skill. Now, the build loop will
[00:10:45] go through and over and over and over
[00:10:47] again build all of them out. In Claude
[00:10:49] Code, all we would need to do to do this
[00:10:50] is do {slash} loop five min {slash} him
[00:10:55] build. What this does, {slash} loop
[00:10:58] basically tells the chat, "Do this next
[00:11:01] thing over and over and over again."
[00:11:03] Five min tells it how often to do it.
[00:11:05] So, every five minutes it's going to do
[00:11:07] it. And what it's going to do is run him
[00:11:09] build, our new skill. Again, I'll give
[00:11:12] you the prompt in a second how to set it
[00:11:13] up that builds out any spec in our
[00:11:16] backlog inside Linear. So, those five
[00:11:19] specs that we just built out. So, it's
[00:11:20] going to every five minutes run him
[00:11:22] build. So, basically, put it on a loop
[00:11:25] all day just building, building,
[00:11:26] building, building, building for us. And
[00:11:28] again, all the build skill is is a skill
[00:11:32] that tells Claude code or Codex or
[00:11:34] whatever you're using exactly how to
[00:11:36] read and build out each one of those
[00:11:39] issues in linear. It also tells it how
[00:11:42] to move it along our pipeline, how to
[00:11:44] push it to the review skill, and how to
[00:11:45] keep our entire loop running even when
[00:11:48] we're not at our computer. So, I'm going
[00:11:50] to hit enter on that, and it is going to
[00:11:52] start building out our specs. At the
[00:11:55] same time as that, we are going to set
[00:11:58] up our review loop. So, let's do this.
[00:12:00] I'm going to open up another chat. I'm
[00:12:02] going to do the exact same thing,
[00:12:03] {slash} loop
[00:12:04] 5 min {slash} review, and I'm going to
[00:12:08] hit enter on that. This is going to set
[00:12:10] up another loop where our agent is now
[00:12:12] going to review every spec built out,
[00:12:15] every spec marked as waiting. So, when
[00:12:17] our agent is done building out each one
[00:12:20] of the specs, it gives it a label that
[00:12:23] says, "Okay, ready for review." And then
[00:12:25] our review loop waits to see that label
[00:12:27] to start reviewing everything. And all
[00:12:30] our review skill is is basically just
[00:12:32] instructs the agent how to review
[00:12:34] everything built out, so how to open it
[00:12:36] up in a browser, test it out, click
[00:12:38] around, how to apply the label once it's
[00:12:40] done being reviewed, how to spin up its
[00:12:43] own pull request with that specific code
[00:12:46] in it, how to put that pull request into
[00:12:49] a sandbox environment so you can test
[00:12:51] out just that specific change, and how
[00:12:54] to write instructions for the user on
[00:12:57] how to test it themselves. Each one of
[00:12:59] these new skills that I'm going to have
[00:13:01] you build out is really, really simple
[00:13:03] to do. It's just one prompt. All it's
[00:13:05] doing is instructing the AI how to push
[00:13:08] issues through our loop here, and how to
[00:13:11] keep everything moving, and how to save
[00:13:13] you way more time, and get you way more
[00:13:15] productive. So, the agents are
[00:13:16] autonomously building out the issues,
[00:13:19] then another agent is autonomously
[00:13:21] reviewing them. What happens when the
[00:13:23] agent reviews an issue,
[00:13:25] tests it out, sees that it works well,
[00:13:28] what it does is it takes that pull
[00:13:30] request and sends it to us in our
[00:13:32] messaging service of choice. So, for me,
[00:13:35] that messaging service is Slack. You can
[00:13:37] use anything for this. You can use
[00:13:39] Discord if you want. You can use
[00:13:40] Telegram if you want. Slack is really
[00:13:43] built for this type of workflow, but you
[00:13:44] can 100% do this in Discord as well, no
[00:13:47] big issue. One of the prompts I'll give
[00:13:49] you down below as well will instruct
[00:13:51] your AI agent on setting this all up.
[00:13:53] You don't need to set up Slack. You
[00:13:55] don't need to set up Linear. You don't
[00:13:57] need to set up the loops. The AI does it
[00:13:59] all for you with the prompts I'm going
[00:14:01] to give you. So, I have this channel
[00:14:03] merge ready. The review loop messages me
[00:14:06] here. As you can see, Henry loops. It
[00:14:08] describes the pull request. It describes
[00:14:10] the issue, what it did. It gives me a
[00:14:12] link if I want to test it myself, so I
[00:14:15] can open up this preview. It's just like
[00:14:16] a preview branch in Vercel that just has
[00:14:19] the one change the agent made. It gives
[00:14:22] me step-by-step on how to test it if I
[00:14:25] want to test it myself. And then when
[00:14:27] I'm ready, all I need to do is react
[00:14:30] with a rocket ship emoji. When I react
[00:14:32] with the rocket ship emoji, the agent
[00:14:35] goes, "Got it. I'll merge it." And then
[00:14:37] it goes, "Merged by me." and puts a nice
[00:14:39] green check mark right on that merge to
[00:14:41] say, "Yep, it's merged in. It's live in
[00:14:44] the app." And just like that, the code
[00:14:46] was built, right? All we had to do is
[00:14:48] come in at the beginning of the day,
[00:14:49] answer a bunch of questions from our
[00:14:51] agent. The agent then autonomously
[00:14:53] builds and reviews and tests everything.
[00:14:56] Then we come in and just click rocket
[00:14:57] emoji, rocket emoji, rocket emoji,
[00:14:58] rocket emoji, and it's all merged and
[00:15:00] done. Our work went from 100% manual,
[00:15:04] take all day, you have to sit at your
[00:15:06] computer, to you just come in at the
[00:15:08] beginning of the day, answer a few
[00:15:09] questions, and at the end of the day you
[00:15:11] hit merge, and you're good to go. This
[00:15:13] is the thin loop. This was what makes it
[00:15:15] so powerful. If you look down below,
[00:15:18] there is a Google Doc. The Google Doc
[00:15:21] has several prompts in it. It has
[00:15:23] prompts for setting up each of the three
[00:15:25] skills, as well as a prompt you can give
[00:15:28] to your agent, whether it's Claude,
[00:15:29] Code, Codex, or whatever, to set up the
[00:15:31] Slack, Discord, Linear, whatever you're
[00:15:34] using, and get the entire system
[00:15:36] connected in place. This isn't gate-kept
[00:15:38] behind an email or anything. It's
[00:15:40] completely free. Just click the link.
[00:15:41] You don't have to do anything. It's just
[00:15:43] a Google Doc you can copy and paste into
[00:15:44] your agent. We don't gate-keep here on
[00:15:47] the Fin Fam channel. AI, especially with
[00:15:49] stable 5 and GBT 5/6, has become so
[00:15:53] smart. There is no more need to baby-sit
[00:15:56] every step of the way. Basically, every
[00:15:59] part should be automated, right? And
[00:16:01] we're still doing manual work. I'm
[00:16:04] working on now figuring out how to
[00:16:05] automate even the manual work. How can
[00:16:07] we automate coming up with ideas? That's
[00:16:10] what I'm building out right now. I want
[00:16:12] to get the spec step even easier and
[00:16:14] even less human-intensive. And as AI
[00:16:16] becomes smarter, it might even already
[00:16:18] be at that point. We don't even need to
[00:16:20] merge it ourselves. We can probably just
[00:16:21] trust it to merge it for us. But right
[00:16:23] now, I still want these two manual
[00:16:25] steps, beginning of the day, end of the
[00:16:26] day. But all that hard work in the
[00:16:28] middle of the day, that's done. You
[00:16:29] don't have to worry about it anymore.
[00:16:30] That's all handled by the Fin loop. All
[00:16:33] the tools you need for this, completely
[00:16:35] free. I'll link them all down below. The
[00:16:38] prompts to set this up, completely free,
[00:16:40] link down below. You have nothing to
[00:16:42] lose by setting up this loop. It just
[00:16:44] saves you tons and tons of time and
[00:16:46] helps you get done way more. You take
[00:16:48] this a step further, you start five or
[00:16:50] six different projects, you just come in
[00:16:52] the morning, answer specs for all six of
[00:16:55] them, they work autonomously all day, at
[00:16:57] the end of the day you have six projects
[00:16:58] moving forward without your work all the
[00:17:01] time. Everyone on the internet's been
[00:17:03] talking about coding loops. Now you know
[00:17:05] it, now you can implement it. And if you
[00:17:07] implement this, you are ahead of like
[00:17:10] literally 99.99999%
[00:17:13] of people. I'm not even joking. Even the
[00:17:15] most hardcore vibe coders right now are
[00:17:18] not setting up loops like this. Do
[00:17:20] yourself a favor, block off half an
[00:17:22] hour, go through this again, take the
[00:17:25] prompts from down below, give them to
[00:17:26] your agent, get this set up. If you want
[00:17:29] to take it even a step further, you can
[00:17:31] copy the link of this video up above or
[00:17:33] hit share down below, give it to your
[00:17:35] agent, say, "Hey, look at the transcript
[00:17:37] of this video and set it up for me."
[00:17:38] Like that's actually probably the
[00:17:39] easiest way to set this up. If you
[00:17:41] learned anything at all, make sure to
[00:17:43] leave a like down below, turn on
[00:17:46] notifications, and subscribe because all
[00:17:48] I do is make amazing videos about AI.
[00:17:51] It's an absolute honor and a pleasure to
[00:17:53] be helping you out, to be educating you,
[00:17:55] to be working with you on these things.
[00:17:56] I'm discovering new things every day.
[00:17:58] All I do is discover things, then share
[00:18:00] it with you. So, I hope you're enjoying
[00:18:02] it. Hope you're learning something from
[00:18:03] it. I absolutely love this stuff. It is
[00:18:05] so much fun, and I hope you're having
[00:18:07] fun with it, too, and I'll see you in
[00:18:08] the next video.
