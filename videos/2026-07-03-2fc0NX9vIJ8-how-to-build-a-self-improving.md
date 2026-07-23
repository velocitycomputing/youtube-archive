---
video_id: 2fc0NX9vIJ8
title: How to Build A Self-Improving System with Claude
channel: Austin Marchese
url: "https://www.youtube.com/watch?v=2fc0NX9vIJ8"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 1006
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 73
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 101
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video presents a five-step framework for building self-improving systems with Claude. Step 1 (Base) establishes a knowledge base structure with raw and wiki folders, plus reusable skills for repetitive tasks like "add new resource." Step 2 (Upload) involves bulk-ingesting historical data from three sources: your Claude conversation history, personal ecosystem data (email, files, recordings), and documented life goals. Step 3 (Inflow) sets up four continuous data pipelines: syncing Claude sessions, ecosystem data capture (meetings, Slack, YouTube), curated content (newsletters), and periodic voice-recorded learnings. Step 4 (Loop) implements improvement loops using an "improve system" skill that categorizes changes into three buckets—auto-approve (low-risk fixes), need sign-off (high-stakes edits), and more context required—then automates execution via Claude Code routines running Tuesday and Friday mornings. Step 5 (Drive) emphasizes execution over perfection, iterating through reps rather than planning.

To get started immediately: (1) Create a `/raw` and `/wiki` folder structure in your project; (2) Run the provided prompts to analyze your Claude session history and extract improvement suggestions; (3) Pull your email via Google Takeout or Outlook Export, and record a voice memo about your goals, then upload both to Claude for ingestion; (4) Set up at least one data pipeline—start with syncing Claude sessions using the "sync Claude sessions" skill; (5) Create two Claude Code desktop routines: one to run your data ingestion skills every Tuesday and Friday at 9:00 a.m., and another to run "improve system" at end-of-day those same days; (6) Commit to reviewing improvement suggestions weekly using the checkbox system, and don't overthink folder names or timing—just start building and let the system improve through actual use.

## Transcript

[00:00:00] I've been obsessed with building my own
[00:00:01] self-improving system with Claude code.
[00:00:03] And after studying Andrej Karpathy, the
[00:00:05] Anthropic team, and running my own
[00:00:06] system, I've identified a five-step
[00:00:09] build framework that lets anyone create
[00:00:11] a self-improving system with Claude
[00:00:13] code. Today, I'm walking through all
[00:00:14] five steps, exactly how to implement
[00:00:16] them, and the lessons I've learned from
[00:00:17] teaching hundreds of people the same
[00:00:19] system. Step one is base, create the
[00:00:21] framework for improving. Before you do
[00:00:23] anything, you need to create a project.
[00:00:24] This is where you store all the data so
[00:00:26] you can enhance it over time. To create
[00:00:27] this project, there are two parts. One,
[00:00:29] a knowledge base where you store the
[00:00:30] data, and two, the skills that let you
[00:00:33] work 10 times faster. So, part one, the
[00:00:35] knowledge base. Andrej Karpathy went
[00:00:37] viral for his concept called LLM
[00:00:39] knowledge base. I have videos on my
[00:00:41] channel diving deep into this, but the
[00:00:42] concept is fairly simple. You have a raw
[00:00:44] folder, which includes any raw resources
[00:00:46] you ingest. For example, this could be a
[00:00:48] call transcript you record. And then you
[00:00:50] have a wiki folder, which references
[00:00:52] files in your raw folder to help AI know
[00:00:54] where to look. Think of this like a
[00:00:56] table of contents in a book, so AI can
[00:00:57] locate information without reading the
[00:00:59] entire book. Here's a prompt, which will
[00:01:01] help you set this up from scratch or in
[00:01:03] an existing project that you're
[00:01:04] currently working on. And to enforce
[00:01:06] this, we'll update the claude.md file to
[00:01:08] explain how it's all set up. This file
[00:01:10] essentially serves as a consistent
[00:01:12] reminder to Claude about the framework.
[00:01:13] Part two is skills for repetitive tasks.
[00:01:16] If you're doing the same thing twice
[00:01:18] with Claude, you should create a skill.
[00:01:19] And a skill is your way of telling
[00:01:21] Claude exactly how to handle a task.
[00:01:23] It's the same process every single time,
[00:01:25] so you don't have to go back and forth.
[00:01:27] The first skill that I set up with every
[00:01:28] person I work with is add new resource.
[00:01:30] This tells Claude exactly how to add a
[00:01:32] new file into the system. It will take a
[00:01:34] raw file, ingest it into raw, and then
[00:01:36] Claude will analyze it and update or
[00:01:38] create any wiki entries that should
[00:01:40] reference it. These utility skills will
[00:01:42] come into play later when I go through
[00:01:44] orchestration skills, which call
[00:01:45] multiple utility skills together to
[00:01:48] create a bigger output. To set up both
[00:01:49] parts, both the knowledge and the
[00:01:51] skills, here is a single prompt that
[00:01:52] combines the two. This prompt will help
[00:01:54] you create the project, which will set
[00:01:55] the foundation for the entire system.
[00:01:57] Now you have the project set up, but
[00:01:58] step two is about creating your own data
[00:02:00] lake. Step two, upload, identify your
[00:02:03] data plus bulk ingest. Before creating a
[00:02:05] self-improving system, you need to
[00:02:07] ingest everything you've already done.
[00:02:08] We want to work smarter, not harder. So
[00:02:10] let's look at all of our historical
[00:02:12] training data that's already exists and
[00:02:14] bring that all together in one place. To
[00:02:16] do this, we're going to look in three
[00:02:17] places. Place one is your AI inputs.
[00:02:19] This is the data you generate just by
[00:02:21] using AI. So this is your conversation
[00:02:24] history and in my eyes, this is the most
[00:02:26] relevant training data that you'll ever
[00:02:28] find because it's literally you inside
[00:02:31] the terminal asking the AI ecosystem
[00:02:33] questions. And the beauty of this is
[00:02:35] that Claude already saves all of its
[00:02:37] session history locally. So there's a
[00:02:38] file that you can analyze historical
[00:02:40] conversations with. Here's a prompt that
[00:02:42] you can run that will analyze your
[00:02:43] session history for you and provide your
[00:02:44] project with clear learnings and skill
[00:02:46] suggestions. The key part here is the
[00:02:48] phrase suggest ways we can improve my
[00:02:50] system. The second place is personal
[00:02:52] ecosystem data. Everywhere you interact
[00:02:54] online, you create your own data
[00:02:56] footprint. So this is the process of
[00:02:58] grabbing as much data from those
[00:03:00] footprints as possible and bringing it
[00:03:02] into the system. Now there are a lot of
[00:03:03] ways that you can do this, but two
[00:03:05] specific ways to do this that apply to
[00:03:06] everyone watching this video is the
[00:03:08] first, which is use Claude to mine your
[00:03:10] own computer. Open Claude code and say
[00:03:12] analyze my computer and identify any
[00:03:14] files you think would be helpful to
[00:03:16] ingest into the system. This will
[00:03:17] surface any information you already have
[00:03:19] on your machine that will be valuable
[00:03:20] for the system you're building. And the
[00:03:21] second is to pull your email history. If
[00:03:23] you use Google, there's a feature called
[00:03:25] Google Takeout. If you use Outlook,
[00:03:27] there's a feature called Outlook Export.
[00:03:29] You can then take this export and bring
[00:03:30] it into Claude to analyze your writing
[00:03:32] style and any potential places to use AI
[00:03:34] that you're not already using it. And if
[00:03:36] you are concerned with data privacy,
[00:03:38] okay, just skip this part. This prompt
[00:03:40] will help you ingest these two data
[00:03:41] sets. The third place to look is your
[00:03:43] life story and project goals. This one
[00:03:46] is simple and most people don't think to
[00:03:47] do it. Just sit down and record yourself
[00:03:49] talking about your life, your project
[00:03:50] goals, and what you want to accomplish.
[00:03:52] Then upload that recording to Claude and
[00:03:54] say, "Analyze this recording and
[00:03:55] interview me to fill in anything I may
[00:03:57] have missed, and once finalized, add
[00:04:00] this as training data to my project."
[00:04:01] Claude will then interview you, and by
[00:04:03] the end you have a file that you can
[00:04:04] bring anywhere with you that gives
[00:04:06] context to AI that it probably didn't
[00:04:08] already have. Here is a prompt that will
[00:04:10] run the entire bulk ingest in one
[00:04:12] session. At this point, we've set up our
[00:04:14] system, we've ingested historical data,
[00:04:16] and created custom skills based on what
[00:04:18] we actually do, not hypothetical skills.
[00:04:21] Now, this next step is the most
[00:04:22] important thing to get right so that we
[00:04:24] can create a self-improving system. Step
[00:04:26] three is inflow. This is about setting
[00:04:28] up your data pipelines. Think of your
[00:04:30] system like a lake. In step two, we
[00:04:32] filled the lake up, but the problem is
[00:04:34] if there's no new water keeping the lake
[00:04:36] full, it will evaporate and no longer be
[00:04:39] useful. So, in this step, we create data
[00:04:41] pipelines, which will act as rivers for
[00:04:43] our lake. And these rivers will
[00:04:44] automatically flow into the lake, and
[00:04:46] you won't have to think about it. The
[00:04:47] way we'll do this is what I call
[00:04:48] skill-driven data ingestion. For each
[00:04:51] pipeline, we first need to set up a
[00:04:53] skill that is well tested that we know
[00:04:55] processes raw data exactly how we want
[00:04:58] it. In step four, we'll use this to
[00:04:59] create our automated improvement loops,
[00:05:01] but you can't do that without this
[00:05:03] because this is a step where 99% of
[00:05:05] people get it wrong. There are four
[00:05:06] different types of data pipelines that
[00:05:08] you want to set up. Pipeline one is your
[00:05:09] own inputs. Like I said earlier, there's
[00:05:12] really no better training data than your
[00:05:13] own conversation history with Claude.
[00:05:15] And we process that as part of the
[00:05:16] initial data dump, but we need to
[00:05:18] continuously process this to get
[00:05:20] learnings from our conversation history.
[00:05:22] So, to do this, we're going to create a
[00:05:23] skill called sync Claude sessions. The
[00:05:26] skill is pretty simple. It'll take your
[00:05:27] past conversation history, bring it into
[00:05:29] your project, and then ingest it into a
[00:05:31] process folder. Here's a prompt that
[00:05:33] will create this sync Claude session
[00:05:35] skill. And with every one of these
[00:05:36] prompts, when you do create these
[00:05:38] skills, it's super important that you
[00:05:40] actually test the skill. Make sure it
[00:05:42] works on your machine, please. The
[00:05:43] second pipeline that you'll set up is
[00:05:45] your personal ecosystem data capture.
[00:05:47] Again, a lot like the bulk upload, you
[00:05:49] need to figure out the places where
[00:05:51] you're creating data on a recurring
[00:05:52] basis. So, for me, I hop on client and
[00:05:55] team calls, I write Slack messages, and
[00:05:57] I post videos on YouTube. I'm really a
[00:05:59] simple man. So, to set this up for
[00:06:01] myself, here's how I would do it. First,
[00:06:03] for meetings, I would use Grainola
[00:06:05] because it records in the background
[00:06:06] without an AI bot sitting on the call,
[00:06:08] which feels a little too intrusive for
[00:06:10] me. And I use their MCP to pull the full
[00:06:12] transcripts from that call and then
[00:06:14] ingest it into my project. For Slack, I
[00:06:16] can set up a direct Slack connection in
[00:06:18] Claude to pull chat history. For
[00:06:19] YouTube, I post videos publicly with
[00:06:21] transcripts enabled. So, I can reference
[00:06:23] the final product to see what was
[00:06:25] actually said and pull that into my
[00:06:27] system. The most important thing when
[00:06:28] you're thinking about all of these
[00:06:29] different nodes for data capture is make
[00:06:32] sure that you're actually capturing the
[00:06:33] content. If you can't figure out the
[00:06:35] connection today, that doesn't matter as
[00:06:36] long as the raw information is there,
[00:06:38] and eventually you'll figure out the
[00:06:39] connection. Now, I went through the
[00:06:40] three of those pretty quickly, but on
[00:06:42] screen, this will showcase three unique
[00:06:44] ways to connect to external data
[00:06:46] sources. Now, this may sound
[00:06:48] complicated, but you can just lean on
[00:06:49] Claude to help with this connection.
[00:06:51] Here is a prompt that will create a sync
[00:06:53] ecosystem data skill based on whatever
[00:06:56] you're trying to connect. This will go
[00:06:57] through each connection source, pull
[00:06:59] anything that's new, and then process it
[00:07:01] into our actual project. Pipeline number
[00:07:03] three is your curated content pipeline.
[00:07:05] This is data from external resources
[00:07:07] that can help you create a better
[00:07:09] output. For example, this could be a
[00:07:10] book, a blog, or a YouTube video. Now,
[00:07:12] there are a lot of ways to do this, but
[00:07:13] my favorite is using newsletters because
[00:07:16] no matter what niche you're in, there is
[00:07:18] somebody writing a newsletter with a ton
[00:07:21] of valuable information about your
[00:07:23] specific topic. And the best part is
[00:07:25] everyone watching this has an email. So,
[00:07:26] if you don't want to get flooded with
[00:07:28] topic-specific newsletters, what you can
[00:07:30] do is add an alias domain. So, whatever
[00:07:32] your normal email is, let's say it's
[00:07:34] Brad, shout out all the Brads out there,
[00:07:36] you would do Brad plus newsletter at
[00:07:38] gmail.com where the plus newsletter
[00:07:40] creates an email alias that lets you
[00:07:42] easily filter for emails to that
[00:07:44] specific location. So, for example, if
[00:07:46] you're looking for AI best practices,
[00:07:48] you would click the link below, which
[00:07:50] has my email newsletter, which has a ton
[00:07:52] of juice, and then you would ingest that
[00:07:54] into your pipeline, and you would get
[00:07:56] better insight in how to best use AI.
[00:07:58] And if needed, you can create that alias
[00:08:00] domain to help you with filtering. Now,
[00:08:01] the skill that will power all of this is
[00:08:03] sync curated content. This will pull
[00:08:05] newsletters from alias inbox, extract
[00:08:07] the key claims from each one, and then
[00:08:09] process it into our wiki. This is
[00:08:11] specific for email, but it's similar for
[00:08:12] other resources. You just need to
[00:08:13] configure it based on where you want to
[00:08:15] gather the information. Now, when you're
[00:08:17] gathering the information, be careful
[00:08:18] not to just pump it with everything. At
[00:08:20] the end of the day, less is more here.
[00:08:23] Be very selective with what you're
[00:08:24] ingesting, because you only want
[00:08:26] high-signal resources. Pipeline number
[00:08:28] four is periodic data dumps. Similar to
[00:08:30] the life story step earlier, I try and
[00:08:33] end my day or my weeks talking through
[00:08:35] any lessons that I learned. And this is
[00:08:37] just me downloading my lived experience
[00:08:39] into Claude to help get more context
[00:08:41] about what I'm doing. So, I'll just rant
[00:08:43] into Claude code using Hex or Whisper
[00:08:45] Flow, which are voice-to-text tools, and
[00:08:47] then I'll run the add new resource
[00:08:49] skill, which we already created to
[00:08:51] ingest this information. Now, putting
[00:08:53] that all together, here is a single
[00:08:54] prompt that will create all three of
[00:08:56] these sync skills that I've mentioned.
[00:08:58] This helps create a constant stream of
[00:08:59] data into the data lake that you're
[00:09:01] creating. Now, one question you may be
[00:09:03] asking is how do we make it so that it
[00:09:04] automatically improves over time? We'll
[00:09:06] get to that in the next step. Before we
[00:09:08] get to that, if this is your first video
[00:09:10] mine, welcome the channel. But if it's
[00:09:11] your second or more, here is our
[00:09:12] anti-slop agreement. The visuals, the
[00:09:14] testing, the hours of research that went
[00:09:16] into this video, this is entirely built
[00:09:18] for humans, not for these AI robot
[00:09:21] scrapers. So, all that I ask is you
[00:09:23] subscribe as part of this agreement to
[00:09:25] help this content reach more people.
[00:09:26] Also, every video I give away a Claude
[00:09:28] Max subscription. This video's winner is
[00:09:30] Gregory Horn, who's building an AI
[00:09:32] native video studio for his Hermes
[00:09:34] agent. Now, for this video, comment
[00:09:36] below with what you're building to
[00:09:37] enter. Now to step four, which is where
[00:09:39] most people get self-improving wrong,
[00:09:41] and I'm going to show you why. Step
[00:09:42] four, loop. Determine and set up the
[00:09:44] improvement loop. Most people think
[00:09:46] self-improving means the system runs
[00:09:48] entirely on its own without any human
[00:09:51] input. And yes, that is possible, and
[00:09:53] I'm going to show you how you can do
[00:09:54] that, but I do want to explain the
[00:09:56] downside of this. Let me give you a
[00:09:58] workout analogy that might hit home a
[00:10:00] little too hard for some people. Imagine
[00:10:02] a system that was automatically
[00:10:03] improving your fitness. So the scenario
[00:10:05] one, a fully automated system. This
[00:10:07] system will work out for you. You don't
[00:10:09] have to lift a finger, and you get
[00:10:10] jacked without any effort. Now that
[00:10:12] sounds amazing, but what if the system
[00:10:14] only ever trains chest? Six months from
[00:10:16] now, your chest is huge, and your legs
[00:10:18] are toothpicks. The system thought it
[00:10:20] was improving you, but it was actually
[00:10:22] breaking you. Now scenario two,
[00:10:23] augmented. You get a workout plan, but
[00:10:25] before it runs it for you, you sign off
[00:10:28] on what the workout is. Then it does the
[00:10:29] workout without you lifting a finger.
[00:10:31] Both these scenarios handle the heavy
[00:10:32] lifting, but the first one just removes
[00:10:34] your judgment, which in some cases,
[00:10:36] unless you love working out only chest,
[00:10:39] you just can't afford to lose this. So
[00:10:41] when should you automate and when should
[00:10:42] you review? Now I'll cover that, but
[00:10:44] first, how do we actually analyze the
[00:10:46] ingested data and propose improvements?
[00:10:49] I like having a single skill called
[00:10:51] improve system. Here's a prompt to set
[00:10:53] it up, which once set up will categorize
[00:10:55] any improvement that you do into three
[00:10:57] buckets. Bucket one, auto approve. This
[00:10:59] is low-risk stuff like data bloat,
[00:11:01] missed linkages, obvious fixes and
[00:11:03] improvements. This is what we'll have
[00:11:05] Claude automatically apply as part of
[00:11:07] the skill. It puts it in a change log,
[00:11:08] and you don't see any of these changes
[00:11:09] unless you want to. Bucket number two is
[00:11:11] need sign off. This is higher-stakes
[00:11:13] stuff like editing a scale or creating a
[00:11:15] new skill. Anything where the wrong
[00:11:16] choice could degrade the output quality
[00:11:19] of your system. These will get written
[00:11:20] to output/review with the date.md. And
[00:11:23] within the file itself, there will be a
[00:11:24] checkbox with one of three options:
[00:11:27] approve, reject, or approve and don't
[00:11:29] ask again. Bucket number three is more
[00:11:30] context required. This is stuff that's
[00:11:33] analyzed, but the skill can't decide on
[00:11:35] its own how to handle it. Essentially,
[00:11:36] it's just things that you need to
[00:11:37] provide more information on. In both
[00:11:39] buckets two and bucket three, what needs
[00:11:41] approval and what needs more context,
[00:11:43] get added to the same file, so you can
[00:11:45] review it all at once. On screen, you
[00:11:46] can see what an example review file
[00:11:48] looks like as the system suggests
[00:11:50] improvements, which I use in Obsidian to
[00:11:52] view it. And now you may be asking, what
[00:11:54] if I want to automatically approve
[00:11:56] everything? And you can, you can just
[00:11:57] adjust the skill accordingly, but I do
[00:11:59] want you to be aware of the spectrum and
[00:12:01] the pros and cons of it. On one end of
[00:12:03] the spectrum, you have full automation.
[00:12:05] This is where you auto approve anything,
[00:12:06] and it requires the least amount of
[00:12:08] work, but it's the most likely to lead
[00:12:10] to system drift. And then on the other
[00:12:12] end is review every change. This is
[00:12:15] safe, but it's too much work and you're
[00:12:17] likely just not going to do it. The
[00:12:18] bucketing strategy, which is what I just
[00:12:20] went through, is exactly where I sit,
[00:12:22] and it's in the middle of the spectrum.
[00:12:23] AI handles the low stake work on its
[00:12:25] own, and you only handle what is
[00:12:26] considered high stakes calls. And over
[00:12:28] the time, the system will learn what is
[00:12:30] high stakes and what isn't. We're having
[00:12:31] AI make the easy calls, and I prefer
[00:12:34] making the hard ones. So at this point,
[00:12:35] we understand the tradeoffs, and we've
[00:12:37] decided to go with a bucketed approach.
[00:12:39] But how do we begin and start automating
[00:12:41] the entire thing? We're going to use
[00:12:42] Claude Code's desktop app to create
[00:12:44] routines. Routine one is data ingestion.
[00:12:47] Routines are how you schedule things to
[00:12:49] run inside the desktop app. We're going
[00:12:51] to set up local routines because this
[00:12:53] gives it direct access to your file
[00:12:55] system, so you can easily edit and
[00:12:57] manage files without worrying about
[00:12:59] version control. To get to this, you can
[00:13:00] go to routines and then click the
[00:13:02] drop-down and then select local. To help
[00:13:04] simplify all the data ingestion into a
[00:13:06] single routine, I create a skill called
[00:13:08] /dataingestion.
[00:13:09] This is an orchestration skill that runs
[00:13:11] the three skills that we created
[00:13:12] earlier, sync Claude sessions, sync
[00:13:14] ecosystem data, and sync curated content
[00:13:17] skills. Using this prompt, which will
[00:13:18] create it, I then create a new routine
[00:13:21] and have it run this data ingestion
[00:13:23] skill on Tuesdays, and then another one
[00:13:25] for Fridays at 9:00 a.m. And the actual
[00:13:27] routine is super simple. I just have it
[00:13:30] reference the skill I've already
[00:13:31] created. The key to any successful
[00:13:33] routine is you want to reference skills
[00:13:35] so that it's easy to update. And so if
[00:13:37] you update the skill directly through
[00:13:38] Claude code, it'll automatically update
[00:13:40] the routine. The second routine we'll
[00:13:42] create is system improvements. I then do
[00:13:44] the same thing for the slash improve
[00:13:46] system skill. This will run at the end
[00:13:48] of the day on Tuesday and on Fridays,
[00:13:50] where it will review the data ingested
[00:13:52] earlier in the day and suggest
[00:13:53] improvements. The reason I've separated
[00:13:55] these two is I feel like they're two
[00:13:56] distinct processes, [music] and I think
[00:13:58] of routines as an individual process. So
[00:14:01] rather than bucketing, I have
[00:14:02] individual, and that way if something
[00:14:04] fails, I know which part of the process
[00:14:06] failed. And the third routine is human
[00:14:08] review. This is your human process, and
[00:14:10] this is so important because you are
[00:14:11] driving the system. And we've already
[00:14:13] created a very simple way to do this
[00:14:15] where you just have to check boxes on
[00:14:17] what you actually want to be improved
[00:14:19] and what you don't want to be improved.
[00:14:21] If you want, you can make a slash human
[00:14:22] improve system skill, which will help
[00:14:24] you walk through the process or notify
[00:14:27] you through Slack if you are getting
[00:14:29] lazy or I forgot to provide feedback.
[00:14:31] The important part here is that you are
[00:14:33] part of the process because this is your
[00:14:35] system and you need to own it. So far,
[00:14:37] we've covered the first four steps and
[00:14:39] how this will transform how you work.
[00:14:40] But the reality is that you are the one
[00:14:42] putting this thing together, which is
[00:14:44] why the fifth step matters the most.
[00:14:46] Step five, drive. Run it, don't
[00:14:49] over-engineer it. This step is the
[00:14:51] mindset you need to actually run the
[00:14:52] system you just built. From first-hand
[00:14:54] experience, you can have all the skills
[00:14:56] and knowledge, but if you don't apply
[00:14:57] these four strategies, you are
[00:14:59] absolutely cooked. The first is slow is
[00:15:01] smooth, smooth is fast. Don't try and do
[00:15:03] everything at once. Move slow, move
[00:15:06] methodical. Everything in this video is
[00:15:08] teed up for you. Just go one step at a
[00:15:09] time and don't be discouraged. Two is
[00:15:12] you're the leader, the system serves
[00:15:13] you. If a piece of the system isn't
[00:15:15] actively making it better, just get rid
[00:15:17] of it. You don't have to have it. If you
[00:15:18] added a skill and you don't like it,
[00:15:20] just delete it. You don't have to wait
[00:15:21] for someone's permission to do
[00:15:22] something, just do it. Three, compress
[00:15:25] your feedback loops. Self-improving
[00:15:26] systems are valuable because they
[00:15:28] compress feedback loops, but the loops
[00:15:30] only learn if you're actually using the
[00:15:31] tools, and even though it's
[00:15:33] automatically improving, don't wait for
[00:15:35] it to automatically improve. If a skill
[00:15:37] didn't work the way you wanted and you
[00:15:39] already went back and forth with Claude
[00:15:40] to actually fix the final output, just
[00:15:43] say, "Based on this conversation,
[00:15:44] improve this skill." You are pushing the
[00:15:46] system forward, so continuously do it.
[00:15:48] Four, it is not that serious, buy is to
[00:15:50] action. People always ask me, "What tool
[00:15:51] should I use? Should I make it
[00:15:53] raw/inputs? Should I make it
[00:15:55] raw/sessions folder? Should I run these
[00:15:56] things at 6:00 a.m. or 9:00 a.m.?" The
[00:15:58] honest answer for any of those smaller
[00:16:00] things, it just doesn't matter. The only
[00:16:02] choice that's genuinely wrong is
[00:16:04] overthinking it. AI is really good, so
[00:16:07] just use it and build things. These
[00:16:09] systems sharpen through reps, not
[00:16:12] whiteboard sessions. One of my favorite
[00:16:13] quotes of all time is from Brian
[00:16:15] Armstrong, the CEO of Coinbase. He said,
[00:16:17] "Action produces information." If you're
[00:16:19] not sure if something works, just do it,
[00:16:22] and you'll learn faster, and you'll have
[00:16:23] more confidence about the answer because
[00:16:26] you've already done it and you've seen
[00:16:27] it through. And that's exactly what
[00:16:29] we're doing with the build framework
[00:16:30] here. It's all about action over
[00:16:32] analysis, so just start doing. Now, if
[00:16:33] you like this video, you'll love this
[00:16:35] video where I dive into loop
[00:16:36] engineering, a process that you can use
[00:16:39] in parallel with what we discussed here
[00:16:41] to make your self-improving system go
[00:16:43] from good to great. I'll see you in the
[00:16:45] next one. Peace.
