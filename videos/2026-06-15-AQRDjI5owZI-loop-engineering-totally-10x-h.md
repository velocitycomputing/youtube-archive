---
video_id: AQRDjI5owZI
title: Loop Engineering Totally 10x Hermes agents
channel: AI LABS
url: "https://www.youtube.com/watch?v=AQRDjI5owZI"
watched_date: 2026-06-15
watched_at: "2026-06-15T12:00:00Z"
watch_count: 1
duration_seconds: 801
source: youtube-history-browser
added_date: 
history_label: Monday
history_order: 20
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 80
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Loop engineering shifts development from prompt engineering to designing self-driving agent systems that autonomously work toward goals without human intervention between steps. The approach involves five key steps: checking project state, deciding action, executing, gathering feedback, and determining task completion. Two loop types exist: deterministic loops for tasks with measurable outcomes (tests passing, code compiling) and non-deterministic loops for judgment calls (UI design, feature implementation). Success requires managing context carefully, providing quality feedback, setting verification gates, defining termination conditions, handling errors explicitly, and tracking state across turns. Modern models like Fable 5 and Hermes agents enable this because they sustain long, complex tasks autonomously.

To implement: Set up Hermes to monitor deployed apps with test cases—it auto-detects production breaks and launches Claude Code in non-interactive mode to fix them iteratively until all tests pass. For UI/feature work, use verification skills like the AI slop detector to identify and iteratively fix issues, employing different models for building versus reviewing (Claude for building, GPT for review) to create adversarial verification. Define clear end-goal metrics upfront, manage context to prevent important instructions from getting buried in chat history, and update skills based on feedback to strengthen future iterations. Access community skills from AIABS Pro to accelerate setup.

## Transcript

[00:00:00] There's a new term going around and you
[00:00:02] might have already heard it. It's called
[00:00:03] loop engineering. And just like every
[00:00:05] other hype term, everyone is talking
[00:00:07] about it like it's something new. It's
[00:00:08] not. But when you combine it with an
[00:00:10] always running agent like Hermes, it
[00:00:12] stops being hype. Most people who are
[00:00:14] trying to set these up are getting the
[00:00:15] loop right and missing the thing that
[00:00:17] actually makes it work. And if you
[00:00:19] already know there are two types of
[00:00:20] loops, there's a specific setup inside
[00:00:22] one of them that almost nobody is doing.
[00:00:24] Once you see it, the way you think about
[00:00:26] building with agents changes completely.
[00:00:28] By the end of this video, you'll
[00:00:29] understand exactly what it is, and
[00:00:31] you'll have it running on Hermes and
[00:00:33] even Claude code without you having to
[00:00:34] step in at all. With [snorts] loop
[00:00:36] engineering, the core idea is simple.
[00:00:38] You stop being the person who writes the
[00:00:40] prompt that drives the agent, and
[00:00:41] instead, you let the agent drive itself.
[00:00:43] But to see why it's a shift in the first
[00:00:45] place, you've got to compare it to what
[00:00:47] came before. The skill that used to
[00:00:48] matter was prompt engineering, where all
[00:00:50] our focus went into writing the right
[00:00:52] series of instructions to drive the
[00:00:54] coding agent properly. But loop
[00:00:56] engineering flips that around. Instead
[00:00:58] of writing the prompt yourself, you
[00:00:59] design the system that does the prompt
[00:01:01] engineering for you and drives the agent
[00:01:03] on its own. So, the focus moves away
[00:01:05] from crafting instructions and toward
[00:01:07] designing systems that run themselves.
[00:01:09] All of this started when the creator of
[00:01:11] OpenClaw said you shouldn't be prompting
[00:01:13] your coding agents anymore and that you
[00:01:15] should focus on designing loops that
[00:01:16] prompt the agent for you. And he's not
[00:01:18] the only one. Boris, who is the creator
[00:01:20] of Claude Code, also made the same claim
[00:01:22] at the Anthropics annual developer
[00:01:24] conference where he said he doesn't
[00:01:26] prompt Claude anymore. He's got loops
[00:01:28] running that prompt claude and it
[00:01:29] figures out for itself what needs to be
[00:01:31] done. So the question is how do you get
[00:01:33] started with them? All of it comes down
[00:01:34] to how well you can set up the systems
[00:01:37] where you don't have to worry about
[00:01:38] prompting the agent at all. You define
[00:01:40] what you need and the agent does the
[00:01:42] rest. That's exactly where AI powered
[00:01:44] development is heading. Before [snorts]
[00:01:46] we get into how to actually build them,
[00:01:48] you need to be clear on what a loop is.
[00:01:50] A loop is basically a process where you
[00:01:52] define the end goal and the agent
[00:01:54] figures out the steps to reach it on its
[00:01:56] own. It corrects itself along the way
[00:01:58] and works around problems until it
[00:02:00] reaches the goal you set. A few months
[00:02:02] ago, before models got capable enough to
[00:02:04] sustain long tasks. This wasn't
[00:02:06] possible. If you needed to build an app,
[00:02:08] you'd prompt the agent, monitor what it
[00:02:10] was doing, check the output yourself,
[00:02:11] find the issues, and reprompt to fix
[00:02:13] them. You were the loop. You were the
[00:02:15] part doing the error checking and course
[00:02:17] correcting between every step. That's
[00:02:19] what development still looks like for
[00:02:20] most people. And that's exactly what
[00:02:22] loop engineering is about to take off
[00:02:24] your plate. Now, this might sound like a
[00:02:26] brand new concept, but loops have
[00:02:28] actually been around for a while. Chron
[00:02:29] jobs are a good example of a loop you've
[00:02:31] probably already seen. They're just
[00:02:33] tasks scheduled to run repeatedly and
[00:02:35] automatically without you having to
[00:02:37] trigger them each time. The only real
[00:02:39] difference is that a chrome job runs at
[00:02:41] a fixed time. So, with loops in place,
[00:02:42] the work stops being about writing the
[00:02:44] prompt. Your agents performance on a
[00:02:46] task comes down to how well you define
[00:02:48] the end goal. To some of you, this
[00:02:49] process will sound a lot like
[00:02:51] reinforcement learning. If you haven't
[00:02:53] come across it, reinforcement learning
[00:02:55] is basically a way of training a model
[00:02:57] where you don't show it the right
[00:02:58] answers. Instead, you just tell it when
[00:03:00] it did well and when it didn't, and it
[00:03:02] gradually figures out how to get better
[00:03:04] on its own. The model finds the right
[00:03:05] path by trying different things. It gets
[00:03:07] a positive signal when it moves in the
[00:03:09] right direction and a negative one when
[00:03:11] it doesn't. The same idea applies here,
[00:03:13] except the model itself isn't what's
[00:03:15] being trained. Instead, the agent is
[00:03:16] working toward completing the task you
[00:03:18] want done. Iterating on it in the same
[00:03:20] way a model would improve during
[00:03:22] training. If it fails the loop you've
[00:03:23] put on, the agent doesn't mark the task
[00:03:25] is done. It tries again, keeps going,
[00:03:27] and corrects itself until it reaches the
[00:03:29] goal you set. Now, after hearing all
[00:03:31] this, you might wonder what's actually
[00:03:33] left for you to do if everything is
[00:03:35] becoming autonomous. But your role
[00:03:36] doesn't shrink. It gets more important
[00:03:38] because it's your domain knowledge and
[00:03:40] experience that define the end goal in
[00:03:42] the first place. And that ends up
[00:03:44] showing in everything you build and
[00:03:45] ship. This is exactly why the push
[00:03:47] toward autonomous loops is only speeding
[00:03:50] up and it's showing in every new feature
[00:03:52] that drops right now. Fable 5 is the
[00:03:54] clearest example yet. Anthropic dropped
[00:03:56] it even though they'd been calling for a
[00:03:58] slowdown in AI development because the
[00:04:00] models are getting capable at a pace
[00:04:02] that's hard to keep up with. And after
[00:04:03] releasing it for some time, they even
[00:04:05] pulled it. They built it for long and
[00:04:07] complex tasks. and it performs better
[00:04:09] the longer and more complex the task
[00:04:11] gets, which is basically the opposite of
[00:04:13] how models used to work. This shift
[00:04:15] really started with Opus 4.5. Once that
[00:04:17] dropped, long-running tasks got
[00:04:19] dramatically better, and you didn't need
[00:04:20] to set agents up with carefully guided
[00:04:23] harnesses anymore. Basically, structured
[00:04:25] setups that walked the agent through
[00:04:26] each step. The focus moved instead
[00:04:28] toward preparing the project to run over
[00:04:30] the long term because the models are now
[00:04:32] capable enough to handle things on their
[00:04:34] own without much step-by-step handling.
[00:04:36] But the loop isn't the only thing that
[00:04:38] matters. You also need to structure your
[00:04:40] project in a way that lets the agent
[00:04:42] work on its own for a long time without
[00:04:44] you having to step in. So, a lot of
[00:04:45] people have been building and open-
[00:04:47] sourcing systems for exactly this kind
[00:04:49] of setup. The Ralph loop was one of the
[00:04:51] first. It worked by setting the end goal
[00:04:53] and making sure the agent couldn't drift
[00:04:54] away from it. It did this through hooks,
[00:04:56] which are basically scripts that run
[00:04:58] automatically when something specific
[00:05:00] happens. So this script strictly
[00:05:02] prevents the agent from marking a task
[00:05:03] as done unless it had actually met the
[00:05:06] condition. But hooks are rigid. So
[00:05:07] Claude introduced its own goal command
[00:05:09] which did the same thing but with more
[00:05:11] flexibility. Instead of a hard-coded
[00:05:13] check, it lets another model decide
[00:05:15] whether the task is actually finished.
[00:05:17] We covered goal buddy 2 which built on
[00:05:19] that by having the agent track its
[00:05:21] progress in local files and define
[00:05:23] exactly what done looks like before it
[00:05:25] even starts so it always knows what it's
[00:05:27] working toward. The Hermes agent and
[00:05:28] Open Claw were both built on the same
[00:05:30] philosophy. They take you out of the
[00:05:32] picture entirely and let the agent
[00:05:34] handle everything on its own. Now, if
[00:05:36] you want to build these loops, we've got
[00:05:38] a simple five-step system for you. And
[00:05:40] since there are two types of loops, some
[00:05:41] of those steps work a little
[00:05:43] differently, but we'll get into both
[00:05:44] types later on. For now, we'll start in
[00:05:46] clawed code, and later in the video,
[00:05:48] we'll look at how to do the same thing
[00:05:50] in the Hermes agent. The first step is
[00:05:52] checking what state the project is in.
[00:05:53] From that, the model decides what the
[00:05:55] next action should be. Then it acts on
[00:05:57] that decision and this is where the
[00:05:59] actual work happens. The agent calls
[00:06:01] tools, writes to files and runs commands
[00:06:03] to get the task done. Once that's
[00:06:04] finished, it gathers feedback to see
[00:06:06] what actually happened. And based on
[00:06:08] that, it decides whether the task is
[00:06:10] done or not. This is also where the
[00:06:12] difference between prompt engineering
[00:06:13] and loop engineering becomes obvious.
[00:06:15] With prompt engineering, you're only
[00:06:17] ever controlling the decision step,
[00:06:18] while loop engineering handles all five
[00:06:21] together. Building a loop that works
[00:06:22] well means getting a handful of things
[00:06:24] right. And each one is there because of
[00:06:26] a specific problem it solves. The first
[00:06:28] is context management. You pay attention
[00:06:30] to what goes into the context on every
[00:06:32] turn because that's what determines what
[00:06:34] the agent actually knows at any given
[00:06:36] point. You can't rely on the chat
[00:06:37] context alone. Even with context windows
[00:06:40] as large as a million tokens, basically
[00:06:42] how much the agent can hold in memory at
[00:06:44] once. Because as the conversation grows,
[00:06:46] your system prompt and instructions get
[00:06:48] buried under recent tool outputs. The
[00:06:50] agents attention naturally pulls toward
[00:06:52] whatever is most recent. So the
[00:06:53] important stuff gets lost. That's why
[00:06:55] managing context matters so much. The
[00:06:57] next thing to get right is feedback
[00:06:59] quality. Feedback is what tells the
[00:07:01] agent how it did. And it's one of the
[00:07:02] most important signals in the whole
[00:07:04] system. It can take a lot of forms like
[00:07:06] the output of a test run or a screenshot
[00:07:08] of the UI it just built. And whatever
[00:07:10] form it takes, that's what the agent
[00:07:12] reads to figure out its next move.
[00:07:14] Verification gates are what turn that
[00:07:16] feedback into a clear verdict. They're
[00:07:18] the checkpoints that tell the agent
[00:07:19] whether a task is actually done or not.
[00:07:21] You also need a termination condition.
[00:07:23] Basically, a rule that tells the loop
[00:07:25] when to stop. And this one has to be set
[00:07:27] explicitly. Otherwise, the agent either
[00:07:29] quits too early or keeps going without
[00:07:31] making real progress. The thing people
[00:07:33] most often overlook is error handling.
[00:07:35] You have to spell out what the model
[00:07:37] should do when a tool call fails. So,
[00:07:39] the system handles it cleanly instead of
[00:07:40] leaving things in a broken state that
[00:07:42] just creates more problems. And finally,
[00:07:44] you need to manage state across turns.
[00:07:47] Basically, keep track of where the task
[00:07:48] is as the conversation grows. The
[00:07:50] context window can't hold everything
[00:07:52] forever, so you lean on external files
[00:07:54] that track information for the agent and
[00:07:56] let it keep working without losing the
[00:07:58] thread. One thing to keep in mind,
[00:08:00] though, since you're handing the job of
[00:08:01] figuring out the path over to the model
[00:08:03] instead of doing it yourself, loops get
[00:08:05] expensive in tokens. So, you need to be
[00:08:07] deliberate about when you actually use
[00:08:09] them. The more tokens a loop can work
[00:08:11] with, the better it tends to handle the
[00:08:13] task. But before we move forward, let's
[00:08:15] have a word from our sponsor, Scribba.
[00:08:17] Most Python courses are just someone
[00:08:19] talking over slides. Scribba is
[00:08:21] different. Their video player is the
[00:08:22] code editor, so you can pause anytime,
[00:08:24] edit the instructor's code directly, and
[00:08:26] see what happens. No tab switching, no
[00:08:29] copy pasting, just hands-on coding from
[00:08:31] the start. Their new learn Python course
[00:08:33] caught my attention because instead of
[00:08:35] random exercises, you actually build
[00:08:37] something real. From day one, you're
[00:08:39] building payup, a fully functional
[00:08:41] expense spplitting app, and every
[00:08:42] concept gets applied immediately. You
[00:08:44] start from absolute zero. No prior
[00:08:46] Python knowledge needed and work through
[00:08:48] variables, strings, capturing user
[00:08:50] input, arithmetic operators, type
[00:08:53] conversion, data cleaning, and number
[00:08:54] formatting, all by building features for
[00:08:56] the app. By the end, you've built a
[00:08:58] working project from scratch that proves
[00:09:00] you actually know Python. This is just
[00:09:02] part one of several that will become
[00:09:04] available over the coming weeks. And
[00:09:06] currently, it's totally free to access.
[00:09:08] Get started today with their free
[00:09:09] courses, and our users will get an extra
[00:09:11] 20% off on their pro plans. So click the
[00:09:14] link in the pinned comment or scan the
[00:09:16] QR code and start building today. As we
[00:09:18] mentioned, there are two types of loops.
[00:09:20] The first one is called the
[00:09:21] deterministic loop. You use it for tasks
[00:09:24] that have a clear definition of what
[00:09:25] done actually looks like. That could be
[00:09:27] tests passing, code compiling
[00:09:29] successfully or anything like that.
[00:09:31] These loops are fairly straightforward
[00:09:32] to work toward because the end goal is
[00:09:34] clear. So the model knows exactly what
[00:09:36] it needs to do before it can call the
[00:09:38] task done. Since Hermes is always
[00:09:40] running, it's a really good agent
[00:09:42] implement this loop on. We've created
[00:09:44] multiple workflows on it before and
[00:09:46] showed in our previous video how it
[00:09:48] handles a lot of our work on its own.
[00:09:50] The core of a deterministic loop is the
[00:09:52] clear definition of the end goal and for
[00:09:54] the apps you've hosted, that definition
[00:09:55] is your tests. So, you can point the
[00:09:57] Hermes agent at any app you've deployed
[00:09:59] with test cases and have it monitor it
[00:10:01] for you. Now, if a change or a commit
[00:10:03] ends up breaking production, you can set
[00:10:05] up an automation on Hermes to catch it.
[00:10:07] The reason it works best here is that it
[00:10:09] comes with the self-evolving skills
[00:10:10] feature. So, it automatically creates
[00:10:12] and evolves skills based on the
[00:10:14] workflow, which keeps the health of the
[00:10:15] app in check. Once you've set up that
[00:10:17] monitoring automation, you can ask it to
[00:10:19] launch Claude code in non-interactive
[00:10:21] mode. Basically, running it on its own
[00:10:23] without you having to drive it and have
[00:10:25] it fix issues in a loop until all the
[00:10:27] test cases pass. What it does from there
[00:10:29] is set up the automation workflow and
[00:10:31] load skills like the sub aentdriven
[00:10:33] development skill and the GitHub PR
[00:10:35] workflow skill which tell it how to
[00:10:37] manage the app on GitHub. It first
[00:10:39] identifies the issues that were breaking
[00:10:41] production then launches clouded code in
[00:10:43] non-interactive mode which takes the
[00:10:45] tests and commits the changes once all
[00:10:47] of them pass. After it has run every
[00:10:49] test and fixed whatever was causing
[00:10:51] production to fail, it uses the GitHub
[00:10:53] CLI to commit the changes. The app ends
[00:10:55] up running without any failures because
[00:10:57] it has confirmed that all the checks for
[00:10:59] a successful deployment are in place. If
[00:11:01] you like these breakdowns, subscribe to
[00:11:03] the channel, click the notification
[00:11:04] bell, and hit the hype button, too. On
[00:11:06] the channel, we post content that helps
[00:11:08] you learn new ways to optimize different
[00:11:10] processes in different businesses with
[00:11:12] AI. Your support, whether it's
[00:11:14] subscribing, the notification bell, or
[00:11:16] the hype button, helps us create more
[00:11:18] content like this and reach more people.
[00:11:20] It means a lot to us. Now [snorts] the
[00:11:22] second type is the non-deterministic
[00:11:24] loop and these are tasks where you can't
[00:11:26] just set a clear rule to check whether
[00:11:27] the job is done the way you can with
[00:11:29] deterministic loops. Because of that
[00:11:31] there's no clean way to verify the
[00:11:33] outcome. These are the kinds of things
[00:11:34] that we as humans can look at and judge
[00:11:37] for ourselves like building a UI or
[00:11:39] implementing a feature that needs a
[00:11:41] judgment call. So when you're working
[00:11:42] with a non-deterministic loop, the
[00:11:44] workflow is different. If you're
[00:11:45] applying AI to UI, you already know that
[00:11:48] it tends to fall back to the same
[00:11:50] patterns all the time. That's why we
[00:11:51] created a skill called AI slop detector,
[00:11:54] which holds all the instructions on how
[00:11:56] to avoid AI slop and lists the patterns
[00:11:58] that actually give it away. And the
[00:12:00] reason we're using Hermes again is the
[00:12:01] self-evolving skills. If we still find
[00:12:03] AI slop in the UI after running the
[00:12:05] skill, the skill can update itself to
[00:12:07] incorporate that feedback directly. And
[00:12:09] that's exactly why we set this workflow
[00:12:11] up on Hermes. So, we asked Hermes to use
[00:12:14] the skill and check whether the UI has
[00:12:16] any of those patterns. If it does, it
[00:12:17] fixes them and launches Claude code in
[00:12:19] non-interactive mode to run the skill
[00:12:21] and keep fixing what it finds until
[00:12:23] there's nothing left to fix. Another
[00:12:25] benefit we get out of Hermes is that the
[00:12:27] model reviewing the work is different
[00:12:28] from the one building it. We were using
[00:12:30] the GPT models which are known to be
[00:12:32] among the best for code review. So the
[00:12:34] clawed models become the builder and the
[00:12:36] other agent becomes the verifier. That's
[00:12:38] what completes the adversarial loop
[00:12:39] where the two check each other's work.
[00:12:41] Once that loop ran, it generated a much
[00:12:43] better UI than the generic output the
[00:12:45] Opus models are putting out nowadays.
[00:12:47] And if you still spot any sign of AI
[00:12:49] slop in the UI after the agent loop has
[00:12:51] ended, you can just mention it and it
[00:12:53] will update the skill for you,
[00:12:54] strengthening the verifier you already
[00:12:56] have. We've enhanced this skill to match
[00:12:58] multiple AI slop patterns that we and
[00:13:00] Hermes identified collectively. If you
[00:13:02] want to use this skill, you can get it
[00:13:04] from our community, AIABS Pro. The
[00:13:06] link's going to be in the description.
[00:13:08] That brings us to the end of this video.
[00:13:10] If you'd like to support the channel and
[00:13:11] help us keep making videos like this,
[00:13:13] you can do so by using the super thanks
[00:13:15] button below. As always, thank you for
[00:13:17] watching and I'll see you in the next
[00:13:19] one.
