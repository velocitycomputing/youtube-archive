---
video_id: 4JpwNnw0-jI
title: This “Karpathy System” could 701x your AI Workflows (86,000 GitHub Stars!)
channel: Dream Labs AI
url: "https://www.youtube.com/watch?v=4JpwNnw0-jI"
watched_date: 2026-06-10
watched_at: "2026-06-10T12:00:00Z"
watch_count: 1
duration_seconds: 1299
source: youtube-history-browser
added_date: 
history_label: Jun 10
history_order: 160
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 130
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Andrej Karpathy released Auto-Research, an open-source system (85,000+ GitHub stars) that enables AI agents to autonomously improve any optimizable asset through continuous iterative testing. The system uses a three-file architecture: a locked instructions file (human-controlled goals), an asset file (which the AI modifies), and a locked scoring mechanism (immutable metric the AI cannot manipulate). Running in 5-minute loops, it applies evolutionary principles—test variations, keep improvements, discard failures—to continuously optimize whatever you target, working 24/7 while you sleep. Real-world results include Shopify's CEO achieving 19% performance gains overnight and 53% faster code in 4 days. The approach works across domains: website speed (optimized from 800ms to 90.5ms), cold email subject lines (A/B testing across thousands), Facebook ads, YouTube thumbnails, sales scripts, and more.

To implement this for your business, copy the provided master prompt into Claude Code to auto-generate a three-file Auto-Research system for your use case. You need three criteria: an objective metric to measure (load time in milliseconds, email open rates, ad clicks), a fast feedback loop (results in minutes or hours, not weeks), and AI access to modify the asset (code files, email copy, ad variations—not published content). Ideal targets include website performance, email subject lines, ad creative, Instagram DM templates, or code optimization. The system then runs autonomously, testing variations continuously and keeping only those that improve your scoring metric, effectively running thousands of experiments while you sleep.

## Transcript

[00:00:00] Andre Kapathy, the godfather of modern
[00:00:02] AI, has just released a simple system
[00:00:05] called Auto Research, which the top AI
[00:00:07] labs in the world have been spending
[00:00:09] millions trying to create. Since
[00:00:11] releasing this auto researched, it's got
[00:00:13] over 85,000 stars on GitHub. And even
[00:00:16] Shopify CEO pointed at Shopify's code
[00:00:19] and sped it up by 53%. But here's the
[00:00:23] thing, it doesn't just work for coding.
[00:00:25] In fact, auto research can be pointed at
[00:00:27] any part of your business. Your emails,
[00:00:29] your ads, your landing pages, your AI
[00:00:31] skills, AI agents, or even your organic
[00:00:34] content. And it forces each part of your
[00:00:36] business to self-improve at the speed of
[00:00:38] light while you sleep. So, in this
[00:00:40] video, we'll break down Kapathy's simple
[00:00:43] order research system and show you
[00:00:44] exactly how to plug in any part of your
[00:00:47] business that you want to improve. And
[00:00:48] we'll do this together by going through
[00:00:50] three real world examples that you can
[00:00:52] start using today. All I ask in return
[00:00:54] is you hit that like button down below.
[00:00:56] Grab your Slovakian flag and let's jump
[00:00:58] in.
[00:01:00] Okay, so the fun started here with Andre
[00:01:02] Kapathy tweeting that got another 11
[00:01:05] million views for a highly technical
[00:01:07] tweet, which once again shows the demand
[00:01:09] and how impressive this stuff actually
[00:01:11] is. He wrote, "I packaged up the auto
[00:01:14] research project into a new
[00:01:16] self-contained minimal repo if people
[00:01:18] would like to play with it over the
[00:01:20] weekend." He says, "The human, which is
[00:01:22] me and you, will iterate on the prompt,
[00:01:24] giving the agent a set of instructions
[00:01:26] on what we want it to improve, and then
[00:01:28] the AI agent will iterate on the
[00:01:30] training code or whatever the asset it
[00:01:32] is that we want them to improve. And we
[00:01:34] give them, it's going to literally work
[00:01:36] all night trying to improve that asset
[00:01:37] while we're asleep." Let me show you
[00:01:39] where Andre Kapathy started. He says,
[00:01:41] "The goal is to engineer your AI agents
[00:01:43] to make the fastest research progress
[00:01:45] indefinitely and without any of your own
[00:01:47] human involvement, which is why we can
[00:01:49] be asleep." In the image below, which
[00:01:52] this auto research image here is his LLM
[00:01:55] getting smarter and smarter with every
[00:01:58] iteration that it was running on a
[00:02:00] 5minute loop until 83 experiments later,
[00:02:03] it was 11% faster than when Andre
[00:02:06] Kapathy left it. And he also says that
[00:02:08] he'd been working on this same LLM agent
[00:02:10] trying to make it smarter for a very
[00:02:12] long time and thought it was done. But
[00:02:13] his auto research tool found another 11%
[00:02:16] improvement in its IQ. And this
[00:02:18] paragraph below the image might be one
[00:02:20] of the most fascinating things to read
[00:02:22] in terms of a mindset shift on how
[00:02:23] powerful this system is. Kapathy wrote,
[00:02:26] "One day Frontier AI research used to be
[00:02:29] done by meat computers or humans in
[00:02:32] between eating, sleeping, and having
[00:02:34] fun. And these meat computers would
[00:02:36] synchronize with each other once in a
[00:02:38] while using soundwave interconnect which
[00:02:40] is obviously speaking inside a group
[00:02:43] meeting. It's a facicious take on how
[00:02:44] slow us humans are to do these jobs
[00:02:47] compared to something like this auto
[00:02:48] research system. He says that era is now
[00:02:50] long gone. Research is now entirely the
[00:02:53] domain of autonomous swarms of AI
[00:02:55] agents. And he says that this repo or
[00:02:57] this system right here is the story of
[00:02:59] how all of this began. And so the repo
[00:03:02] is up on GitHub which is a crazy thing.
[00:03:04] Andre Kapathy just open sourced it and
[00:03:05] made it free for anyone to use. It's
[00:03:07] called Auto Research. And you can see it
[00:03:09] has 85,000 stars at the time that I'm
[00:03:12] recording this. And so there's been
[00:03:13] hundreds of thousands of people who have
[00:03:15] been running this system, including,
[00:03:16] like I said in the intro, Toby Ludkkey,
[00:03:19] the billionaire CEO of Shopify. And he
[00:03:21] said, "Okay, this thing is totally
[00:03:23] insane." Before he goes to bed, he set
[00:03:26] it up with these experiments. And by the
[00:03:28] time he woke up, he woke up to a plus
[00:03:30] 19% score after 8 hours and 37
[00:03:34] experiment. Literally improving his code
[00:03:36] while he was asleep. And Andre Kapathy
[00:03:38] replied and said, "Who knew early
[00:03:40] singularity could be this fun?" Showing
[00:03:42] more of the work that he's had auto
[00:03:44] research doing for himself. And 4 days
[00:03:46] later, Toby Ludkkey was still playing
[00:03:48] with auto research. He says, "Okay,
[00:03:49] well, I ran auto research on the liquid
[00:03:51] codebase. It's now 53% faster with 61%
[00:03:56] fewer object allocations. He says this
[00:03:58] is probably somewhat overfit, but there
[00:04:00] are some absolutely amazing ideas in
[00:04:03] this showing the iterations of auto
[00:04:05] research without any human intervention.
[00:04:07] And even Gary Tan from Y Combinator says
[00:04:09] Kapathy just open- sourced auto
[00:04:11] research. One GPU 100 machine learning
[00:04:14] experiments overnight while you sleep.
[00:04:16] You never touch the code. Just write a
[00:04:18] markdown file or a set of instructions
[00:04:19] on what you want improved. The
[00:04:21] bottleneck no longer is compute. It is
[00:04:23] your program MD, which is the
[00:04:26] instructions you're giving your agent.
[00:04:27] But I personally don't want to apply
[00:04:28] this to code bases or AI agents. I want
[00:04:31] to apply it to my business and my
[00:04:32] marketing. Which is where we really
[00:04:34] start to see the brilliance of this auto
[00:04:36] research system. Andre Kapathy says, you
[00:04:39] don't use it directly. Talking about his
[00:04:41] GitHub and his system. It's a recipe/
[00:04:44] idea. give it to your agent and apply it
[00:04:48] to whatever you care about. Which is
[00:04:51] where our magic begins. Because even
[00:04:53] Chimath Palihapatia had a potential use
[00:04:56] case which is kind of mind-bending to
[00:04:58] think about. He said the biggest threat
[00:04:59] to today's social media apps is an
[00:05:02] incredible video model. So, something
[00:05:03] that can take text and turn it into
[00:05:05] incredible looking videos, plus TTS,
[00:05:08] plus auto research, which is where you
[00:05:11] can set up your AI agent with a Tik Tok
[00:05:13] or Instagram account, and have a
[00:05:15] constantly producing incredible quality
[00:05:17] content, learning from the results of
[00:05:20] each piece of content in this loop
[00:05:22] feature that I'm about to reveal to you,
[00:05:24] and improving and iterating a 100 times
[00:05:27] a night. Honestly, this thing in the
[00:05:28] hands of your competitors will be
[00:05:29] extremely scary. So let me show you how
[00:05:32] this system actually works. It's a three
[00:05:34] file system. Now Kapathy called these
[00:05:36] files program, train, and prepare. But
[00:05:40] to me, that's just confusing and
[00:05:41] unnecessary. We have the instructions
[00:05:43] file, which is locked to your AI agent
[00:05:45] and only used by me and you, the human
[00:05:48] actually setting the AI agent up for the
[00:05:50] task. Then we have the file or the asset
[00:05:52] that we want to optimize. This is the
[00:05:54] second file and this is the file that
[00:05:56] the AI actually gets access to because
[00:05:58] it's actually trying to optimize its
[00:05:59] performance. I'll give you a few
[00:06:00] examples in just a second. It takes that
[00:06:02] asset, tries to test a new variation of
[00:06:05] it, and then we'll compare this to the
[00:06:07] third file, which is a scoring
[00:06:09] mechanism. Again, the scoring mechanism
[00:06:11] is a file that is locked to the AI,
[00:06:14] because we don't want them tampering
[00:06:15] with it in order to score higher. We
[00:06:17] want the scoring mechanism and the set
[00:06:19] of instructions only accessible to us,
[00:06:21] the human, forcing the AI agent to
[00:06:23] actually do the task and optimize the
[00:06:25] asset. So, let's get practical. Let's
[00:06:27] use a few examples to really understand
[00:06:29] this. This is the baseline of what Andre
[00:06:31] Kapathy first tested his auto research
[00:06:33] on. So he essentially wanted to improve
[00:06:35] the intelligence of an AI agent. We're
[00:06:37] going to use IQ here. He didn't use IQ,
[00:06:39] but I've used it just to keep it simple
[00:06:40] so we can understand it first. So in the
[00:06:42] set of instructions, he says, I need you
[00:06:45] to improve the IQ of this AI agent. He
[00:06:48] gives auto research the AI file that
[00:06:51] makes up the current AI agent. And auto
[00:06:54] research will take that file and create
[00:06:56] a test variable. It'll change the code
[00:06:59] and make one test. It'll then take that
[00:07:02] test of that new AI agent and compare
[00:07:04] the IQ of it to the original file. If it
[00:07:08] is smarter, it'll keep that new file
[00:07:11] that it tested and replace the old file
[00:07:13] because you've improved IQ and it will
[00:07:15] loop it again. It will take that new
[00:07:16] improved AI file that has higher IQ,
[00:07:19] make another change to it, and test it.
[00:07:21] This is basically evolutionary biology
[00:07:23] and natural selection but in the machine
[00:07:25] world. Now if its test variation doesn't
[00:07:27] beat the original IQ of the AI file, it
[00:07:29] will revert back to the original file
[00:07:32] and try again. And this is done in
[00:07:34] 5minute loops repeating indefinitely
[00:07:36] until it reaches a certain goal that you
[00:07:38] have or until a human comes and stops
[00:07:40] it. Okay. So what parts of our business
[00:07:42] can we actually apply this auto research
[00:07:44] to to skyrocket past our competitors?
[00:07:47] Well, Eric Sue had a very interesting
[00:07:49] article on Twitter. He says, "Kapathy's
[00:07:52] autonomous AI can make you 701 times
[00:07:55] faster. It's the future of business, not
[00:07:58] coding, but business generally." He
[00:08:00] says, "Most marketing teams will run 30
[00:08:02] experiments a year, but the next
[00:08:04] generation will run 36,500
[00:08:08] experiments per year easily, and they'll
[00:08:10] run the experiments while they sleep
[00:08:12] using the auto research tool." And so
[00:08:14] technically this order research tool
[00:08:16] could be pointed at any part of your
[00:08:19] business. But there are some criteria of
[00:08:21] what it works best for. So there's three
[00:08:24] musthaves and then three nice to haves.
[00:08:26] And if you fit this criteria, you can
[00:08:28] run order research on that part of your
[00:08:30] business. We're going to go through a
[00:08:31] lot of examples together in just a
[00:08:32] second. The must-have rule number one is
[00:08:34] it needs to be scored objectively. So if
[00:08:37] you're like make this page look better,
[00:08:39] there's no objective measure. If you
[00:08:40] said come up with the best video idea,
[00:08:42] there's no objective measure. Come up
[00:08:44] with the funniest joke. How do you
[00:08:45] measure funny? Well, is it the most
[00:08:47] laugh? Now, you're starting to get an
[00:08:48] objective measure, but that would be
[00:08:50] make a joke that gets the most laughs
[00:08:52] and measure the decibel volume. You need
[00:08:53] that objective measure in order for AI
[00:08:55] to score it without a human in the loop.
[00:08:57] So, things like load speed of a website,
[00:08:59] excellent. Number of impressions a piece
[00:09:01] of content gets, excellent.
[00:09:03] Click-through rate on a page, excellent.
[00:09:05] Then, rule number two is you need a fast
[00:09:08] feedback loop. You need the results in
[00:09:10] minutes or maximum hours, not weeks. For
[00:09:14] example, a load speed on a website. Once
[00:09:17] again, you can test that in seconds,
[00:09:18] which means you get more iterations and
[00:09:20] more improvements and it's going to
[00:09:21] actually work for you. Or email opens,
[00:09:23] how many people are opening that email
[00:09:25] that hour, that will pass. However, SEO
[00:09:27] rankings, you make a change to your
[00:09:29] website and be like, "Let's wait to see
[00:09:30] Google reindex this 10 days later." It's
[00:09:33] not going to work for you because
[00:09:34] there's too big of a feedback loop for
[00:09:36] the AI to actually get enough data to
[00:09:38] learn. Or pricing. What if I lower my
[00:09:40] pricing? Is that going to reduce my
[00:09:42] churn in 6 months from now? Really hard
[00:09:44] for an AI to actually have a feedback
[00:09:46] loop and iterate on that. Number three,
[00:09:48] the AI obviously needs access to change
[00:09:51] it. So, if it's a HTML file or an API in
[00:09:53] a software you use, excellent. it's got
[00:09:55] access to the asset that you need.
[00:09:57] However, if it's a video that's been
[00:09:59] already published on YouTube and you're
[00:10:01] like, "Oh, change the intro." You can't
[00:10:02] log into a past YouTube video and change
[00:10:04] the intro because it's already published
[00:10:06] and AI cannot have access to that. So,
[00:10:08] if you tick the box on those three
[00:10:10] things, then you want to have a look at
[00:10:11] the nice to have cuz this will make your
[00:10:13] order research even more powerful. You
[00:10:15] want a high volume of feedback. If you
[00:10:17] have a website and you're getting 50,000
[00:10:19] impressions per day and you're changing
[00:10:20] the ad copy on the website, incredible.
[00:10:22] you're going to get a lot of data, a lot
[00:10:24] more iterations, and therefore a lot
[00:10:25] more improvement in your website
[00:10:27] conversions. If you're only getting 50
[00:10:28] impressions a day, it's going to be
[00:10:30] really tough. You're going to have to
[00:10:31] wait a lot longer to test it. It does
[00:10:33] also need to be cheap to fail. So, if
[00:10:35] you plug an image model, so if you're
[00:10:37] looking to do graphic design and you're
[00:10:38] plugging a image model, say Nano Banana,
[00:10:40] into your AI and you're having it create
[00:10:42] images and then scoring them based on
[00:10:44] whatever rating system, we'll get to
[00:10:46] that in a second, you are using, that's
[00:10:48] great. That's going to be relatively
[00:10:49] cheap for you to generate those images.
[00:10:51] If you are having your AI literally go
[00:10:53] out there and hire graphic designers and
[00:10:54] then wait to see their work, it's going
[00:10:56] to be too expensive. You're going have
[00:10:57] to pay thousands of dollars for these
[00:10:58] graphic designs, not going to work. Your
[00:11:00] iterations need to be fast, they need to
[00:11:02] be cheap, and they need to have a lot of
[00:11:04] volume. Number six, you need consistent
[00:11:07] measuring stick. So, we have a file. The
[00:11:10] scoring system is file that the AI
[00:11:12] cannot touch. It cannot manipulate the
[00:11:14] goals to say, "Oh, yes, we did it. We
[00:11:16] improved it." what your definition of
[00:11:18] better is, which we said at the start,
[00:11:20] must stay the definition the whole time
[00:11:22] and AI cannot manipulate that. But also,
[00:11:25] the scoring mechanism that you put in
[00:11:27] that file must be objective and it must
[00:11:29] be consistent. For example, if you split
[00:11:32] test and email to fresh audiences,
[00:11:35] you're going to have a consistent
[00:11:36] measuring stick. However, if you're
[00:11:38] emailing the same list over and over
[00:11:40] with new different titles, they're going
[00:11:42] to have list fatigue because they've had
[00:11:44] six emails already and therefore the
[00:11:46] seventh they're going to be way less
[00:11:47] likely to open cuz they're not going to
[00:11:48] open seven emails in a row in a period
[00:11:49] of 35 minutes from you. Let's go through
[00:11:51] some examples together of things we can
[00:11:54] point this auto research at. So, coding
[00:11:57] efficiency, this is the obvious one.
[00:11:58] This is the one that Toby Luki and Andre
[00:12:00] Kapathy have also done. How do you make
[00:12:03] your coding, how do you make your
[00:12:04] website faster? The asset to optimize
[00:12:07] would be the source code of the actual
[00:12:09] website and the scoring system would be
[00:12:11] the runtime in milliseconds that it
[00:12:13] takes to load once booted up. Cold email
[00:12:16] outreach. Nick Surv had an excellent
[00:12:18] example of this one where he has a cold
[00:12:20] email outreach company that is using
[00:12:22] auto research to test the titles of the
[00:12:24] emails and the uh body of the emails.
[00:12:26] What's actually in the content? The
[00:12:28] instructions would be get more replies.
[00:12:30] This is what you're telling the auto
[00:12:31] research to do. We need more replies.
[00:12:33] That is the metric that we want to score
[00:12:34] it on. So, a positive reply rate is the
[00:12:36] scoring system. The asset optimize is
[00:12:38] the actual email, the subject, the
[00:12:40] opener, and the call to action in that,
[00:12:41] which it could just be spinning up tests
[00:12:43] and shooting it to 100 people in the
[00:12:45] first email, 100 people in the second
[00:12:47] email cuz these are cold emails. It's
[00:12:48] not to an actual list. Instagram DM
[00:12:50] outreach. Your instructions to your
[00:12:52] order research could be book some more
[00:12:54] calls, stay human, and don't spam. Of
[00:12:56] course, these instruction files, which
[00:12:57] I'll walk you through in just a second,
[00:12:58] how to build them yourself, are going to
[00:13:00] be much longer than this. This is just a
[00:13:02] snippet of an example just so we can
[00:13:03] start to get some ideas on how these
[00:13:05] would work. What to optimize? You'd
[00:13:07] optimize the DM script, what's the
[00:13:08] scoring system, how many replies you
[00:13:10] get, and what the booking rate is per
[00:13:12] template. Website load speed, an easy
[00:13:15] one. Sales page copy, an easy one. Video
[00:13:17] watch time, what videos are holding the
[00:13:19] viewer retention the longest? YouTube
[00:13:21] titles and thumbs. You could plug this
[00:13:23] into your YouTube dashboard and test
[00:13:26] your thumbnails and titles over time, as
[00:13:28] long as they're getting enough data to
[00:13:30] them. What metric would you use? The
[00:13:31] amount of views or the watch through uh
[00:13:33] or the click-through rate is the one
[00:13:34] that I would actually use. Sales
[00:13:36] scripts. Now, this is starting to get to
[00:13:37] the longer feedback loops. And Andre
[00:13:39] Kapathy says you need 5 minute feedback
[00:13:41] loops. But when we're applying this to
[00:13:43] business, we can be more more lenient.
[00:13:44] It's just going to take more time to get
[00:13:45] that feedback loop connected. But you
[00:13:48] could do something like sales scripts
[00:13:49] and have the AI analyze which of these
[00:13:51] scripts are giving the best close rate.
[00:13:53] Sales funnels, app speed, cart
[00:13:56] checkouts, prompt engineering, what
[00:13:57] prompts are giving you the best results?
[00:13:59] your agent intelligence or your agent AI
[00:14:01] effectiveness. And so let's run through
[00:14:03] some of these examples actually in the
[00:14:05] real world together to show you how you
[00:14:06] would do it at home for your business.
[00:14:08] So really important to understand once
[00:14:10] again, we have an instructions file. We
[00:14:12] have an asset to optimize. We have a
[00:14:14] hypothesis that the AI makes and then
[00:14:16] tests scores it to see if the actual
[00:14:19] test out did based on the scoring
[00:14:22] mechanism the original asset to
[00:14:24] optimize. If it does, it keeps it. If it
[00:14:25] doesn't, it throws it away and goes
[00:14:27] again. And it repeats indefinitely
[00:14:29] overnight, which is critical that you
[00:14:31] have that as part of the instructions.
[00:14:32] So that literally works non-stop on your
[00:14:35] behalf. And so I've made you a master
[00:14:37] prompt for it to walk you through
[00:14:39] setting up this exact system. All you
[00:14:40] have to do is copy paste this prompt
[00:14:42] into your Claude code. And he will
[00:14:44] literally set up the three file system
[00:14:45] for you and ask you what asset is it
[00:14:48] that you're optimizing. So when you walk
[00:14:49] through it, he's going to help you get
[00:14:51] all the files, the connections, the APIs
[00:14:52] plugged in so you can start your auto
[00:14:54] research on whatever asset it is you're
[00:14:56] trying to improve. It has pulled
[00:14:58] Kapathi's rules. It has modeled
[00:15:00] Kapathi's GitHub. It is the exact prompt
[00:15:02] that you need to start auto researching
[00:15:04] in your business. So we're going to walk
[00:15:06] through three live examples together.
[00:15:08] Starting with the easiest and the
[00:15:09] fastest iterative loop, making a website
[00:15:12] faster. So this is a local file I have.
[00:15:15] I got Claude called to mock up a
[00:15:16] website, but it's not fully optimized.
[00:15:19] It doesn't load as fast as it possibly
[00:15:21] can. And what a developer would normally
[00:15:22] do or I would normally do as a business
[00:15:24] owner is like, I want my website to be
[00:15:25] quicker. Hm, let me think about how it's
[00:15:27] going to be be quicker or hire a
[00:15:29] developer. And the developer is like, I
[00:15:30] have a hypothesis. What if I change this
[00:15:32] and test AI is handling all the
[00:15:34] hypothesis and all the testing. All we
[00:15:37] have to do is come to our claude code,
[00:15:39] paste in the prompt that I'm giving you
[00:15:41] in this video, and Claude code will
[00:15:43] respond. Hi, I'm now your auto research
[00:15:46] engineer. Here's the deal. In one
[00:15:48] breath, we pick one thing in your
[00:15:49] business and he turns is it good into a
[00:15:51] single honest number and then I sit here
[00:15:53] all night changing it, scoring it,
[00:15:55] keeping what wins and trashing what
[00:15:57] loses. Fantastic. That is auto research.
[00:15:59] So, we want to improve the speed of a
[00:16:02] website. I said Cord says that's a great
[00:16:05] pick and an honest one. Website speed is
[00:16:07] textbook auto research target. It is
[00:16:10] objective measure. It is fast and is
[00:16:12] reachable. It can have the page and HTML
[00:16:14] and the JPEGs all in one place locally,
[00:16:16] which I'll show you in just a second.
[00:16:18] But remember, the fit check is for the
[00:16:21] ideal thing to auto research. We're kind
[00:16:22] of stretching the limits of auto
[00:16:24] research and applying it to business.
[00:16:26] And therefore, you may have a slower
[00:16:28] feedback loop or you might be trying
[00:16:29] something that, you know, even if you do
[00:16:31] have a 2hour feedback loop or a 24-hour
[00:16:34] feedback loop, it might be better than
[00:16:35] you having to go do all the testing
[00:16:37] yourself. So, we're sort of on the
[00:16:39] cutting edge at this part, but at least
[00:16:41] for this example here, it does fit
[00:16:43] Kapathy's criteria of what auto research
[00:16:46] would be good for. So, I linked him to
[00:16:48] the website, which I just showed you,
[00:16:50] and he set off on his way. I let Claude
[00:16:53] pick scoring, which is any scoring. It
[00:16:55] is just the milliseconds, the time that
[00:16:57] it takes to load, and he's not allowed
[00:16:59] to touch that scoring file as we've
[00:17:01] discussed. And basically he analyzed it
[00:17:03] and did round after round after round
[00:17:05] making the website faster and faster.
[00:17:08] Now I also asked him to mock up a report
[00:17:10] to show me exactly how he went which you
[00:17:13] can also ask your claude code to mock
[00:17:14] up. This is a classic claude code
[00:17:16] looking file. But you can see it went
[00:17:18] from 800 milliseconds baseline all the
[00:17:21] way down here to 90.5 milliseconds
[00:17:23] according to claude code. And these are
[00:17:24] the rounds that it actually knocked off
[00:17:26] the milliseconds of uh and exactly what
[00:17:29] it did to knock them out. So now we have
[00:17:31] a pretty incredibly optimized fast
[00:17:34] website. Okay. So the next example is
[00:17:36] cold emails. I saw Nick Serev who does a
[00:17:38] cold email business uh give an example
[00:17:41] of how he was using this. And so
[00:17:43] basically say I have 300,000 emails uh
[00:17:46] that are cold emails that I want to
[00:17:48] reach out to and do cold outreach which
[00:17:50] cold outreach is very different to a
[00:17:51] warm list. You're not going to get your
[00:17:53] 40 50% opens. You're going to get your 1
[00:17:55] to 3% opens. But a lot of people make
[00:17:57] money that way. I do not. But if you are
[00:17:59] in that camp, you can now use auto
[00:18:01] research to improve something like your
[00:18:03] email bodies, your email headlines, or
[00:18:06] just overall your click-through rate,
[00:18:07] your reply rate, or how many people
[00:18:09] actually buying your product. So, I came
[00:18:11] back into a new cla code window pasted
[00:18:13] in our prompt. He says, "Consider me
[00:18:15] your oneperson R&D department."
[00:18:18] Fantastic. He's going to run auto
[00:18:19] research. I sent him back. I want cold
[00:18:22] email subject lines tested or improved,
[00:18:25] should we say. I want you to measure
[00:18:27] 24-hour open rates across your sent
[00:18:29] emails. Cross reference the scoreboard
[00:18:31] or the scorecard of higher open rate.
[00:18:33] So, we're just changing the subject line
[00:18:35] of the email. We're going to send the
[00:18:37] same exact email. And how he's going to
[00:18:39] know what wins and loses is he's going
[00:18:40] to send a bunch of them, a thousand of
[00:18:42] them in this example, and he's going to
[00:18:44] look after 24 hours how many of them got
[00:18:46] opened verse the last headline, and he's
[00:18:48] either going to bin that or he's going
[00:18:49] to replace it and make it the best holy
[00:18:51] grail uh email subject line. Now, if you
[00:18:54] use something like smart lead AI, you
[00:18:56] can plug it into that. You can also use
[00:18:58] auto research for something like
[00:19:00] calling. If you have an auto dialer or
[00:19:02] if you have AI dialing agents, you can
[00:19:04] plug and play new scripts, new openers
[00:19:07] for that. Or if you're doing uh DM
[00:19:09] marketing, you could use something like
[00:19:10] Manyhat to do your auto research. If you
[00:19:12] do want more help integrating AI agents
[00:19:14] or something like auto research into
[00:19:16] your business, come and join our private
[00:19:18] community where you can get all the
[00:19:19] resources and step-by-step help for
[00:19:21] people like me or even our top AI
[00:19:23] researcher who is in the group 12 hours
[00:19:25] a day helping people out. Now, for this
[00:19:27] example, 24 hours is a lot longer period
[00:19:30] of time and we can't actually wait weeks
[00:19:31] to show you this one example. So I asked
[00:19:33] Lord to mock up what it would look like
[00:19:35] if we ran this for weeks where it's
[00:19:37] starting to score and give open strength
[00:19:39] predictors based on what email subject
[00:19:42] lines that is actually sending. And of
[00:19:44] course the only thing missing here is
[00:19:45] the actual how many people of those
[00:19:47] thousand people open that email. Feed it
[00:19:50] back in to make sure that the every
[00:19:51] change is making is actually making the
[00:19:53] email be opened more and more. Okay. The
[00:19:55] last example I once again pasted in the
[00:19:58] prompt and then asked it to improve my
[00:20:00] Facebook ads. Now, this is where things
[00:20:02] get really impressive and really scary.
[00:20:04] This is what Chimath was saying, how if
[00:20:06] you have something that can render
[00:20:07] images, can render video, can render
[00:20:09] really good copy. Go out there, post a
[00:20:13] live Facebook ad, testing that new copy
[00:20:15] or testing that new image, seeing how
[00:20:17] many clicks we got for like $10, for
[00:20:19] example, and then bidding the ones that
[00:20:21] do bad and then testing a new one every
[00:20:23] five or 10 or 20 minutes or even an
[00:20:25] hour. Even if it takes you 2 hours to
[00:20:26] get to spend that $10, it doesn't matter
[00:20:28] cuz you're constantly testing new data
[00:20:30] in the background. And I saw a guy do
[00:20:32] this with his actual Instagram and Tik
[00:20:35] Tok short form content where he had a AI
[00:20:38] rendering the short form videos and then
[00:20:39] an auto research learning how well they
[00:20:41] did, coming back and giving him
[00:20:42] basically machine learning feedback on
[00:20:44] the next one. And he's doing really
[00:20:45] well. We're actually making a video over
[00:20:47] the next couple of weeks on a system
[00:20:49] like this. So make sure you hit that
[00:20:50] subscribe button if you haven't already.
[00:20:52] But for Facebook ads, I said, I want you
[00:20:54] to plug straight into my Facebook ad
[00:20:55] account and make variations of the ads I
[00:20:57] already have. I want you to test them
[00:20:59] with $10 each. The thing I want you to
[00:21:01] measure is the price per click of the
[00:21:03] ad. And so once again, this is going to
[00:21:05] be a longer tail thing to actually show.
[00:21:07] And we're going to be running these
[00:21:08] tests in our premium community if you
[00:21:09] want to see more of the actual results
[00:21:11] side of things, but I will be posting a
[00:21:12] lot more here on YouTube as well. We had
[00:21:14] some mock data. So I gave it my Facebook
[00:21:16] ad data. It started to create variations
[00:21:18] and it has a predicted cost per click
[00:21:21] for each one. It mocked up a directory
[00:21:23] and file structure for me. It's got its
[00:21:26] scoreboard, how it actually judge how
[00:21:27] well things go and then it's got its
[00:21:29] experiment logs where you can see all
[00:21:30] the losing files. And this thing is
[00:21:32] literally going to run while I sleep.
[00:21:34] Let me know in the comments below what
[00:21:35] you're going to be using auto research
[00:21:36] for. Thanks for watching. I'll see you
[00:21:38] in the next video.
