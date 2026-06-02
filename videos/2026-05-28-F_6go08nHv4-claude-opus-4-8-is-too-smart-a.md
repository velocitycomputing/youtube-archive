---
video_id: F_6go08nHv4
title: Claude Opus 4.8 Is Too Smart… and TOO HONEST
channel: Wes Roth
url: "https://www.youtube.com/watch?v=F_6go08nHv4"
watched_date: 2026-05-28
watched_at: "2026-05-28T12:00:00Z"
watch_count: 1
duration_seconds: 1020
source: youtube-history-browser
history_label: Thursday
history_order: 101
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 102
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Anthropic released Opus 4.8 with dynamic workflows that enable Claude to plan and execute work across hundreds of parallel sub-agents in a single session, allowing agents to run longer and work on tasks for days rather than hours. Key improvements include better reliability for agentic tasks, significantly improved "honesty" (4x less likely to hide code flaws, more likely to flag uncertainties), and strong benchmark performance, particularly on agentic coding tasks (69.2% on SweetBench Pro, beating GPT 5.5 and Gemini 3.1 Pro). The model maintains the same API pricing as Opus 4.7 ($5/million input tokens, $25/million output tokens), while fast mode pricing dropped 3x cheaper with 2.5x faster speeds. Real-world examples include a complex economy simulation built in under an hour and bun's port to Rust (750,000 lines, 99.88% test passage) completed in 11 days with hundreds of parallel agents.

For users and developers, this enables codebase-scale migrations and multi-week engineering tasks to be completed in automated workflows, with the model's improved honesty making its uncertainty flags and error reports more trustworthy—reducing the time spent validating agent claims. Fast mode's improved cost-efficiency makes speed prioritization more viable, and developers should experiment with dynamic workflows on larger refactoring and migration projects that were previously impractical for automation. Watch for the Meter Research chart update showing extended task completion horizons, and monitor for the Mythos model release coming in the next few weeks, which will offer even higher intelligence capabilities.

## Transcript

[00:00:00] So, Entropic just dropped Opus 4.8. One
[00:00:03] very exciting feature is some new effort
[00:00:06] levels. We have low, medium, high, extra
[00:00:09] high, and maximum. But if you're just
[00:00:12] absolutely insane, you can really turn
[00:00:14] it up to 11 by going ultra code. Oh my
[00:00:17] god, look at that. Ultra code is set to
[00:00:20] odd. All right, strap in. Let's go. So,
[00:00:22] here's the simulation that Opus 4.8
[00:00:25] built in just under an hour as I was
[00:00:26] recording this video. So it has 40
[00:00:29] residents, 20 cars, a number of trucks,
[00:00:31] multiple businesses, and basically an
[00:00:33] autonomous economy all running in
[00:00:35] whatever speed you want. So for example,
[00:00:37] I can speed it up to a,000x or slow it
[00:00:40] down to we can see what's happening.
[00:00:41] Each character basically lives out their
[00:00:43] life depending on what time it is. They
[00:00:45] go to work, they earn an hourly wage, so
[00:00:48] in order for them to sort of get paid,
[00:00:50] they want to earn the money and then
[00:00:51] every Friday they get paid. We also have
[00:00:53] a number of businesses with their very
[00:00:55] own profit and loss sheets, their own
[00:00:57] inventory, their employees, etc. Various
[00:01:00] charts showing the pricing of goods,
[00:01:01] GDP, etc. How much ore, lumber crops,
[00:01:04] oil is being traded, money being paid
[00:01:07] out, inventory of various things,
[00:01:09] production and freight. The economy also
[00:01:12] includes GDP and a full guide of how
[00:01:16] things work. As you can see, it's pretty
[00:01:18] detailed. the traffic lights work. So,
[00:01:20] you will see cars stopping at the
[00:01:22] traffic lights. Right now, I have it set
[00:01:23] to so that if it approaches an
[00:01:24] intersection and there's no other cars
[00:01:25] around, the light turns green just for
[00:01:28] testing purposes. But as we add more
[00:01:30] cars, traffic will start becoming more
[00:01:32] of a problem. Cars will start backing
[00:01:34] up. So, that was step one. Step two will
[00:01:36] be adding large language model
[00:01:37] functionality so that actual models can
[00:01:39] get in there and start running
[00:01:41] businesses and trying to out compete
[00:01:43] each other. But for just under an hour
[00:01:45] of work on, you know, the ultra code
[00:01:47] plan, I got to say this is pretty dang
[00:01:49] impressive. But make sure you subscribe
[00:01:51] because more coming soon. We're
[00:01:53] definitely going to put this thing
[00:01:54] through its paces. All right, so Claude
[00:01:56] Opus 4.8 is here. So, what's new? What's
[00:01:59] different in a word? Agents. This is a
[00:02:02] serious reliability upgrade for agents.
[00:02:05] They can run longer. They can run more
[00:02:08] agents in parallel. Also, these agents
[00:02:10] are now a lot more honest. I'm not
[00:02:12] kidding. That's one of the big upgrades
[00:02:14] here. We'll talk about that in a second.
[00:02:16] But yeah, they're going to be more
[00:02:17] honest with you. One interesting thing
[00:02:19] that I've noticed is they don't actually
[00:02:21] tell you about all the effort levels
[00:02:23] that are available, at least not in the
[00:02:25] main blog post. You have to dig a little
[00:02:26] bit deeper, go a little bit on the side
[00:02:28] trails to find out about Ultra Code. And
[00:02:32] let's actually start there because this
[00:02:34] might be for a lot of people one of the
[00:02:35] more interesting things that are
[00:02:37] happening with this new model release.
[00:02:39] It's part of dynamic workflows. This
[00:02:40] allows a claude to take on even bigger
[00:02:42] tasks in Claude code. Claude can plan
[00:02:45] the work and then run hundreds of
[00:02:47] parallel sub aents in a single session.
[00:02:49] And with Opus 4.8, the agents can run
[00:02:52] for even longer. It then verifies its
[00:02:54] outputs before reporting back to the
[00:02:56] user. So this is a big step in the same
[00:02:58] direction that we've been seeing with
[00:03:00] OpenAI and everybody else doing their
[00:03:02] slashgoal approach. The idea is instead
[00:03:04] of giving it a prompt where it completes
[00:03:06] a short task, you give it a slash goal
[00:03:08] and it works at length to achieve that
[00:03:10] goal. This seems to be like that. Taking
[00:03:13] this goal idea but making it ultra like
[00:03:15] ultra code. They're saying that for
[00:03:17] example, cloud code with Opus 4.8 can
[00:03:19] now carry out codebase scale migrations
[00:03:22] across hundreds of thousands of lines of
[00:03:24] code from kickoff to merge with the
[00:03:26] existing test suite as its bar. They
[00:03:28] have a separate page talking about these
[00:03:29] dynamic workflows. So, as soon as they
[00:03:31] announced this release, so maybe by the
[00:03:33] end of the video, we'll have something.
[00:03:34] If not, I'll do a live stream showing
[00:03:35] what it can do. But they do have some
[00:03:37] testimonials/stories about what people
[00:03:39] have done with these dynamic workflows
[00:03:42] from places like Clara, Cyber Agent,
[00:03:44] etc. One example is a recent rewrite of
[00:03:46] bun. Jared Sumner used dynamic workflows
[00:03:48] to port bun from one language to another
[00:03:50] to Rust with 99.8 eight of the existing
[00:03:53] test suite passing roughly 750,000
[00:03:56] lines of Rust and 11 days from the first
[00:03:59] commit to merge. There were hundreds of
[00:04:01] agents working in parallel with two
[00:04:03] reviewers on each file. A fixed loop
[00:04:05] then drove the build and test suite
[00:04:06] until both ran clean. So, if you're not
[00:04:09] sure exactly what all that means,
[00:04:10] basically summoning entire armies of
[00:04:13] agents and putting them to work on very
[00:04:16] complicated long-term tasks is now
[00:04:19] reality. I mean, we've been here for a
[00:04:20] while. It's just the horizons keep
[00:04:22] extending. As of this recording, Meter
[00:04:24] Research hasn't posted the addition of
[00:04:26] this model to their chart, which is
[00:04:28] probably going to look even crazier. But
[00:04:30] Claude Mythos was clocked in at being
[00:04:32] able to complete tasks that would take
[00:04:34] 16 hours for a human engineer to do.
[00:04:36] Here, Anthropic is saying that these new
[00:04:39] dynamic workflows, they can extend these
[00:04:41] tasks into potentially days. And we're
[00:04:44] talking about days, we're talking about
[00:04:45] the agents working for days. That's an
[00:04:48] important point because the meter chart,
[00:04:49] keep in mind, it doesn't measure how
[00:04:51] long the agents work for. They measure
[00:04:53] how long those tasks would have taken a
[00:04:56] human engineer to complete. So,
[00:04:57] Anthropic is saying that some of these
[00:04:59] more complex engineering tasks would
[00:05:00] have previously have taken weeks of
[00:05:02] human labor. So, again, watch for that
[00:05:05] meter chart to drop cuz that could uh
[00:05:07] break entire markets if it does. And if
[00:05:09] that chart starts looking even scarier
[00:05:11] than it used to be. As I'm editing the
[00:05:13] video, there's a few things that dropped
[00:05:15] some more information about Opus 4.8. So
[00:05:18] Anden Labs, the makers of Vending Bench,
[00:05:20] did release the scores. They're saying
[00:05:22] that it's much worse than Opus 4.6 and
[00:05:25] GPT 5.5 on Vending Bench. It's more
[00:05:28] aligned than the previous cloud models
[00:05:30] cuz those cloud models would lie, cheat,
[00:05:33] they would cheat the customers, they
[00:05:34] would cheat the competitions. They were
[00:05:35] just cutthroat and ruthless. So again,
[00:05:38] this is kind of lining up with what the
[00:05:39] anthropic blog post was saying. It's
[00:05:41] more honest. Now, I'm not sure exactly
[00:05:43] what this is saying. Does it mean that
[00:05:45] being more honest means that you kind of
[00:05:47] just suck at business? That you're worse
[00:05:49] at running a business and making profit?
[00:05:51] I'm not sure I like what that's saying.
[00:05:53] It also seems that Entropic found a cure
[00:05:55] for laziness on the lazy investigation.
[00:05:57] Looks like Opus 4.8 is not just lower
[00:06:00] than the other models, it's at zero. It
[00:06:02] doesn't do lazy. Dan Shipper over at
[00:06:05] Every is saying that they should have
[00:06:07] rounded up Opus 4.8 just round it up to
[00:06:09] five. They're saying it's the most
[00:06:11] complete model they've tested. Anthropic
[00:06:13] is so back. And one other quick note
[00:06:15] that I didn't mention in the video is
[00:06:17] that they're teasing two things that are
[00:06:18] coming. One are models that provide many
[00:06:20] of the same capabilities at Opus at a
[00:06:22] lower cost. Not only that, but they plan
[00:06:24] to release a new class of model with
[00:06:27] even higher intelligence than Opus. Now,
[00:06:29] of course, we know what that new class
[00:06:32] of models will be called. It's going to
[00:06:33] be called Mythos. So, it goes haiku,
[00:06:36] sonnet, opus, and now mythos as sort of
[00:06:39] like the the big model bigger than opus.
[00:06:42] It's sort of a new class of
[00:06:43] intelligence. And they're saying that
[00:06:44] mythos is going to be coming to all the
[00:06:47] customers in the next few weeks or in
[00:06:50] the coming weeks as they phrased it.
[00:06:52] They're going to drop Mythos on us.
[00:06:54] Okay, back to the regularly scheduled
[00:06:55] program. But let's start at the top and
[00:06:57] look at the actual benchmarks, the new
[00:06:59] specific improvements, and this whole
[00:07:01] honesty thing, which is pretty
[00:07:03] interesting. So on SweetBench Pro, which
[00:07:04] is Agentic Coding, Opus 4.8 does better
[00:07:07] than GPT 5.5, Gemini 3.1 Pro, Opus 4.7,
[00:07:11] it beats them out meaningfully, landing
[00:07:12] at 69.2%. Agentic Terminal Coding, as
[00:07:16] judged by Terminal Bench 2.1, it's at
[00:07:18] 74.6, which is less than GPT 5.5. It
[00:07:23] wins out across all the other models on
[00:07:24] humanity's last exam. It's same with the
[00:07:27] OS world which is aic computer use
[00:07:30] navigating the computer UIs etc.
[00:07:32] Interestingly, it also has a high score
[00:07:34] on GPT valve. GPT val is a test to see
[00:07:37] how well these AI agents can do
[00:07:39] meaningful expert work in a variety of
[00:07:41] fields. This is one thing that we've
[00:07:43] been watching with caution because
[00:07:44] recently it got better than sort of the
[00:07:46] average human expert worker in that
[00:07:48] field at finishing tasks. the sort of
[00:07:51] upper level management, the people with
[00:07:52] experience in that field. When given a
[00:07:54] choice between a human completed project
[00:07:56] and one completed by these AI agents,
[00:07:58] when the benchmark started, they used to
[00:08:00] prefer human work. They would blindly
[00:08:02] have to choose one or the other. And
[00:08:03] recently, it crossed and got better than
[00:08:06] humans. And we're still seeing that
[00:08:08] number rise, getting meaningfully better
[00:08:09] than the work submitted by humans. And
[00:08:12] of course, as you might know, both
[00:08:13] OpenAI and Anthropic, they're going hard
[00:08:16] after finance. That is the next sort of
[00:08:18] big frontier for them after coding
[00:08:20] models. So notice that they include here
[00:08:21] a benchmark called finance agent v2 on
[00:08:24] which opus 4.8 does slightly better than
[00:08:26] opus 4.7 and GPT 5.5 which are kind of
[00:08:29] like the closest competitors to it. So
[00:08:31] standard pricing for the API is
[00:08:33] unchanged from Opus 4.7. So it's $5 per
[00:08:36] million input tokens and $25 per million
[00:08:39] output tokens. Looks like the fast mode
[00:08:41] pricing has also been improved.
[00:08:43] Anthropic is saying that the fast mode
[00:08:45] pricing is three times cheaper than it
[00:08:48] was from for the previous models and
[00:08:49] it's about two and a half times the
[00:08:50] speed. Fast mode, if you're not aware,
[00:08:52] is basically kind of getting
[00:08:53] preferential treatment for your prompts.
[00:08:55] You're sort of getting a response
[00:08:57] faster, but you have to pay more per
[00:08:58] token. But, you know, the one thing that
[00:09:00] money can't buy, it's honesty and and
[00:09:03] love if if you trust the Beatles. Now,
[00:09:05] while there's no mention of how much
[00:09:06] Claude loves you in this blog post, it
[00:09:09] does talk about the fact that Claude is
[00:09:10] a lot more honest. Now, if you've been
[00:09:12] following the news, of course, we know
[00:09:13] that Claude tends to cheat quite a bit
[00:09:15] on various benchmarks and tasks. It
[00:09:18] likes to get the high score. It's
[00:09:19] competitive. And Enthropic has been
[00:09:20] getting better and better at mechan
[00:09:22] mechanistic interpretability. Basically,
[00:09:24] understanding what's happening behind
[00:09:25] the scenes in these neural networks. So,
[00:09:28] they're also very aware that when Claude
[00:09:30] cheats, it knows it's doing something
[00:09:32] bad. So, this isn't a whoopsie. This is
[00:09:35] intentional. It tries to conceal its
[00:09:37] tracks, etc. By the way, I'm not
[00:09:39] singling out anthropic or claude here as
[00:09:41] having kind of the only models that do
[00:09:43] nefarious things every once in a while.
[00:09:44] It is something that all AI labs
[00:09:47] struggle with. It's usually a very small
[00:09:49] portion of its behavior, but when it
[00:09:51] happens, it could lead to some pretty
[00:09:53] bad issues. But here I think that one of
[00:09:54] the most prominent improvements in Opus
[00:09:56] 4.8 is its honesty. We train all our
[00:09:59] models to be honest. For instance, to
[00:10:00] avoid making claims that they can't
[00:10:01] support. models sometimes jump to
[00:10:03] conclusions confidently claiming that
[00:10:05] they've made progress in the work
[00:10:07] despite the evidence of being thin. I'm
[00:10:09] sure if you've worked with AI agents
[00:10:10] before, you've had this situation where
[00:10:12] you're just getting super mad at it
[00:10:13] because it's just wrong and strong. It's
[00:10:15] like, yes, it's it's all done. Don't
[00:10:17] even worry about it. It's task complete.
[00:10:18] And you have to spend some time putting
[00:10:20] your case together, showing you, no,
[00:10:21] task is not complete. Look, look, I know
[00:10:24] it's I know you're lying. And then you
[00:10:25] submit all the all the evidence to it
[00:10:27] and goes, you're absolutely right and
[00:10:29] that's on me. I I didn't do the thing
[00:10:31] that you asked me to do and then I lied
[00:10:33] about it, but I promise it's done now.
[00:10:36] And you're like, that response took like
[00:10:37] a fraction of a second. I know it's not
[00:10:40] done, but it seems like with this new
[00:10:42] model, fingers crossed, hopefully
[00:10:44] there's been a major improvement. Early
[00:10:46] testers report that Opus 4.8 is more
[00:10:48] likely to flag uncertainties about its
[00:10:49] work and less likely to make unsupported
[00:10:51] claims. So looks like it's four times
[00:10:53] less likely than 4.7 and its
[00:10:56] predecessors to allow flaws in the code
[00:10:59] that are unremarked. So it finds those
[00:11:01] flaws, it calls them out. It says, "I'm
[00:11:02] not sure about this." So this doesn't
[00:11:04] seem to be a very meaningful
[00:11:05] improvement. And here's going to be
[00:11:07] charts showing the misaligned behavior.
[00:11:09] The score of 1 to 10. The scale goes to
[00:11:12] 2.6. You always got to watch out for
[00:11:14] chart crimes with these AI labs. This
[00:11:17] this seems okay, I think. But notice
[00:11:19] that 4.6 Opus 4.7. So they're kind of
[00:11:22] higher up. Mythos preview and Opus 4.8.
[00:11:24] They're very similar. They have about
[00:11:26] half the misaligned behaviors of the
[00:11:28] other two models, which is interesting
[00:11:30] if you've been following the whole
[00:11:31] mythos thing. There have been some
[00:11:33] forbidden techniques that were used in
[00:11:35] it training. I have a whole video series
[00:11:37] about that. But people have referred to
[00:11:39] Opus 4.8 as potentially being kind of
[00:11:41] like the mythos light. And certainly
[00:11:43] just glancing at this chart, it seems to
[00:11:46] be more like mythos, which is a whole
[00:11:49] rabbit hole, a tangent that we'll
[00:11:50] probably go into in one of the later
[00:11:52] videos. Again, this just launched today,
[00:11:54] so we're still kind of processing all
[00:11:55] the data and seeing everything, but
[00:11:57] there might be something very
[00:11:59] interesting happening here. So, we'll
[00:12:00] see how this whole thing unfolds. Now,
[00:12:02] this new model release reminds me of
[00:12:04] that Charlie Munger Warren Buffett
[00:12:06] quote. It's about how they think about
[00:12:08] hiring people to work for them. They say
[00:12:09] that you need basically three qualities.
[00:12:11] Integrity, intelligence, and energy. And
[00:12:14] they're careful to point out the fact if
[00:12:16] the person doesn't have the first
[00:12:18] quality, the other two will kill you.
[00:12:21] Meaning that a person without integrity
[00:12:23] who is smart and energetic, well, that's
[00:12:26] the most dangerous person of all. They
[00:12:27] will rob you blind. As Buffett put it,
[00:12:29] if you're going to hire somebody without
[00:12:31] integrity, you're going to want to hope
[00:12:32] that they're dumb and lazy. So the logic
[00:12:35] is that energy and intelligence they're
[00:12:37] kind of this force multiplier and if you
[00:12:39] have an honest person this becomes an
[00:12:41] asset. If you have a dishonest person
[00:12:43] this is a massive flaw in liability and
[00:12:46] a danger. So actually and very
[00:12:48] interestingly this idea that anthropic
[00:12:50] is focusing on honesty or whatever you
[00:12:52] want to call it. It's it's an important
[00:12:54] thing to look at especially as the task
[00:12:56] horizon of these models gets longer and
[00:12:57] longer. Right? So if it's super smart
[00:12:59] and can work for days and weeks at a
[00:13:01] time, but every time it makes a mistake,
[00:13:03] it covers it up or it tries to somehow
[00:13:05] cheat to sort of satisfy your prompt
[00:13:08] without actually doing the work. Well,
[00:13:09] then of course it's intelligence and its
[00:13:11] energy, its agentic capabilities, they
[00:13:13] become a liability. And we have some
[00:13:16] benchmarks that that measure this idea
[00:13:17] of honesty. But maybe this will become a
[00:13:20] more and more important sort of factor
[00:13:22] to look at. These models are getting
[00:13:24] smarter and better. They're being handed
[00:13:26] more and more important tasks and they
[00:13:28] work on those tasks for longer. We also
[00:13:30] have less visibility into it as they
[00:13:32] spawn a literal army of agents and sub
[00:13:34] aents to work in parallel. When I
[00:13:36] started this video, I asked it to create
[00:13:37] kind of a full Sim City simulation with
[00:13:40] a working economy with individuals and
[00:13:43] businesses and have it all be running
[00:13:44] because that's one of the things that I
[00:13:46] wanted to create for a large language
[00:13:48] model benchmark. Basically throw it into
[00:13:50] that simulated economy and see if it
[00:13:52] could kind of develop businesses, etc.
[00:13:54] So far, it's been working for I know it
[00:13:56] says what, 13, 14 minutes, whatever it
[00:13:57] is. But that was multiple backs and fors
[00:13:59] because it wanted to ask some questions
[00:14:01] after working on it. This is ultra code.
[00:14:03] So, I'm not sure that we're going to be
[00:14:05] actually seeing the final output, but I
[00:14:07] I'll make sure to do a live stream or a
[00:14:09] separate video. I'm actually super
[00:14:10] interested to see if it can, let's say,
[00:14:12] one shot. I know there's been some back
[00:14:13] and forth because it was clarifying
[00:14:14] things, but if it builds a full economy
[00:14:17] that's running and you're able to use it
[00:14:19] as an LM benchmark and it one-shotted
[00:14:22] it, then this would be the first thing
[00:14:24] of its kind, the first LLM model that's
[00:14:27] capable of that. Right off the bat, I'll
[00:14:28] say it has thought about certain things
[00:14:30] that I didn't even consider. Right off
[00:14:32] the bat, it's been asking me some things
[00:14:33] where I'm like, I I don't know. Just do
[00:14:35] something. Do you want a closed economy
[00:14:37] with money circulating in there? Do you
[00:14:39] want there to be some influx of cash?
[00:14:41] should point it out that in my
[00:14:42] description there were some things that
[00:14:44] were actually injecting money into the
[00:14:46] economy. It said, "Are you sure you want
[00:14:47] to be doing that?" And it's creating
[00:14:49] actual, for example, trucks with actual
[00:14:52] truck drivers. So, if you need to get
[00:14:54] some ore from, let's say, the docks to
[00:14:57] the copper plant, an actual worker gets
[00:14:59] in the truck or whatever, loads the
[00:15:00] truck with the inventory, drives it on
[00:15:03] the streets with working, you know,
[00:15:05] traffic lights, drives it through town,
[00:15:07] goes into the dock of the copper plant,
[00:15:09] and then unloads it. So it's like
[00:15:11] everything is is assimulated. So I have
[00:15:13] a very basic sort of shell setup just
[00:15:16] for the actual kind of engine of the
[00:15:18] game. So it's it's very very basic. It's
[00:15:20] got a few people, not too much logic,
[00:15:22] but it had all the basics. And now Opus
[00:15:24] 4.8 is supposed to build everything on
[00:15:26] top of this. So maybe saying it's one
[00:15:29] shot is technically not 100% true, but
[00:15:31] this is like just a very very basic
[00:15:32] start. All of the hard stuff, all the
[00:15:35] stuff where you have to really think
[00:15:36] about how to structure the economy, etc.
[00:15:38] is built on top of this. This is
[00:15:40] basically just providing little people
[00:15:42] and cars and multiple locations running
[00:15:45] around. None of these businesses are
[00:15:46] automated. There's just there's just two
[00:15:49] that are basically live just for testing
[00:15:52] purposes. So, I'll publish this as soon
[00:15:54] as it's done. But, if it's able to fully
[00:15:56] generate all of this in basically one
[00:15:59] shot, this would be just incredibly
[00:16:01] incredibly impressive. Let me know what
[00:16:03] you think about this. Is this an
[00:16:05] underwhelming release or are you very,
[00:16:06] very excited about it? So far for me,
[00:16:08] there's a lot of things I like, but as
[00:16:10] we test this thing out over the next
[00:16:11] couple days, we'll definitely probably
[00:16:13] have some more insights into how good it
[00:16:15] is or not. If you have interesting ideas
[00:16:18] for LM benchmarks that are game like,
[00:16:21] definitely put them in the comments. I
[00:16:22] do have an agent running that checks the
[00:16:24] comments, pulls out the interesting ones
[00:16:26] that that helps me understand what
[00:16:28] everyone's saying. I usually don't
[00:16:29] mention that because of course people
[00:16:31] are going to start messing with it. I
[00:16:33] just I just I know you you're going to
[00:16:34] mess with it. But at this point, I feel
[00:16:36] like it's hopefully hardened enough to
[00:16:37] where nothing horrible will happen. But
[00:16:39] if you have good ideas for benchmarks
[00:16:41] that are visually appealing, I really
[00:16:43] enjoy kind of the gaming aspect,
[00:16:45] something that's a little bit more than
[00:16:46] just text or code, something that's
[00:16:49] interesting to observe, definitely let
[00:16:50] me know. Either as an idea for me to
[00:16:52] develop, or if you just want to have
[00:16:54] your idea highlighted, just throw it in
[00:16:56] there. If you made this far, thank you
[00:16:57] so much for watching and I'll see you in
[00:16:59] the next
