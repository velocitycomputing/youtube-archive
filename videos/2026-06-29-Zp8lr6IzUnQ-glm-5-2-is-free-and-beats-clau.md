---
video_id: Zp8lr6IzUnQ
title: "GLM 5.2 Is Free And Beats Claude On Most Work. So Why Can't Companies Switch?"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=Zp8lr6IzUnQ"
watched_date: 2026-06-29
watched_at: "2026-06-29T12:00:00Z"
watch_count: 1
duration_seconds: 1055
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 15
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 106
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What was discussed:**
GLM 5.2 is a free, open-source model that outperforms Claude on routine, center-of-distribution tasks (brochure sites, standard coding, copywriting, synthesis) and costs 98% less to run, yet companies aren't switching away from expensive frontier models like Claude and GPT-4. The core problem isn't the model itself—it's that switching requires completely rebuilding the "harness" (system prompts, tool calls, memory architecture, prompt optimization) around a new model, and this is prohibitively expensive without specialized AI talent. Frontier model providers like Anthropic counter this switching cost with sticky team-level products: Claude Tag integrates into Slack, automatically capturing your company's context and making the model inseparable from daily workflow. Meanwhile, companies struggle to accurately measure whether their work is center-of-distribution (where GLM 5.2 excels) or edge-case (requiring frontier models), and employee demand for familiar tools adds organizational friction. The real bottleneck is scarce last-mile AI talent—most companies cannot afford the engineers needed to build custom harnesses, creating structural lock-in to expensive providers.

**What's actionable for the user:**
If you work at a company or run an agency: (1) Map your actual task distribution—what percentage of work is routine vs. novel? (2) Ask whether you own your company's context or are renting it back from Anthropic/OpenAI through tools like Claude Tag. (3) If you have the technical capability to refactor systems for GLM 5.2, the ROI math is compelling—potentially 98% cost savings. (4) If you're in consulting, positioning yourself as someone who can refactor AI pipelines to cheaper models is a high-demand, high-margin service in 2026. (5) Don't assume you need frontier models everywhere; most work is center-of-distribution and GLM 5.2 genuinely excels there. Start by identifying which critical tasks actually require edge-case reasoning, then route only those to expensive models.

## Transcript

[00:00:00] I tried GLM 5.2 and it blew my mind. By
[00:00:02] the end of this video, you should know
[00:00:04] where GLM 5.2, an open-source model, can
[00:00:07] be clawed, where it can safely replace
[00:00:09] an expensive model, and where switching
[00:00:11] models is a bit of a trap because you're
[00:00:12] not replacing a model call. You're
[00:00:15] actually replacing a whole work system.
[00:00:16] And that's the thing I want to draw
[00:00:18] through in this video. So, let me start
[00:00:20] at the beginning here. GLM 5.2 did not
[00:00:22] fake impress me. It actually impressed
[00:00:25] me because it's not just cheap, and it's
[00:00:27] very cheap to run on the cloud, it's
[00:00:28] free if you set up your own servers, and
[00:00:30] for a lot of normal work, it's
[00:00:32] incredibly good. It's It's often better
[00:00:35] than Claude. And when I say normal work,
[00:00:37] I mean the fat middle of everyday AI
[00:00:39] tasks, right? So, if you're setting up a
[00:00:41] brochure site for a client, if you have
[00:00:43] a PowerPoint outline, it's a pretty
[00:00:45] standard deck. For a first pass copy,
[00:00:47] routine synthesis, for coding tasks that
[00:00:50] are tackling familiar problem types in
[00:00:53] coding, these are tasks with familiar
[00:00:54] shapes, with lots of examples, with
[00:00:56] outputs that a human can check quickly.
[00:00:59] The nerdier phrase for this is that this
[00:01:01] is the middle of the distribution work
[00:01:03] for AI. In other words, what you are
[00:01:05] getting is what someone has tried with
[00:01:07] models millions of times before, where
[00:01:10] the answer pattern is pretty normal, and
[00:01:12] the output is pretty easy to inspect.
[00:01:14] How many different brochure sites have
[00:01:16] you seen, right? In that world, GLM 5.2
[00:01:19] is incredible. It's fast, it's cheap,
[00:01:21] it's easy, and it's extremely high
[00:01:23] quality. It's higher quality than
[00:01:25] Claude. And a lot of those tasks, I
[00:01:27] don't think it's honest to say it's just
[00:01:29] good enough. I think it's It's more
[00:01:31] accurate to say this is the best model
[00:01:34] in the world at those center of
[00:01:36] distribution kinds of tasks, especially
[00:01:39] ones where front-end taste is important.
[00:01:41] And so, this is not a video about GLM
[00:01:43] 5.2 being bad, even though it's not my
[00:01:46] daily driver, and I'm going to explain
[00:01:48] why. And so, GLM 5.2 is incredible, but
[00:01:51] I'm still not using it every day. And in
[00:01:53] fact, a lot of companies I know are
[00:01:55] really struggling with the idea that
[00:01:57] they want to transition to more of a
[00:02:00] generic router where they can route to
[00:02:02] the cheapest model available, but it's
[00:02:04] not actually easy to do in practice. Why
[00:02:06] is that, right? We're going to talk
[00:02:07] about why that is, talk about where open
[00:02:10] source is going, talk about what the
[00:02:12] shape of work looks like in 2026, and
[00:02:14] we're going to tie it back into GLM 5.2
[00:02:16] and the way we actually need to build to
[00:02:19] take advantage of models like this.
[00:02:21] Because cheap AI, it's not a theory
[00:02:23] anymore. Cheap incredible AI is here. In
[00:02:26] fact, it's going to be here more and
[00:02:28] more and more and more because the US
[00:02:30] government is now slowing down frontier
[00:02:32] model releases. 5.6 is the latest model
[00:02:35] to be affected. It's apparently going to
[00:02:36] be released customer by customer, which
[00:02:38] is code for we don't know when we're
[00:02:40] going to get it. For the first time,
[00:02:41] there is no defined expected cadence for
[00:02:44] future model releases that are frontier,
[00:02:46] even though the labs are still doing a
[00:02:48] phenomenal job training and
[00:02:50] reinforcement learning their models. And
[00:02:52] so we're going to have more and more of
[00:02:53] this open source conversation. And a lot
[00:02:55] of the open source conversation is
[00:02:57] frankly about moving down the cost
[00:03:00] curve, right? Because these frontier
[00:03:01] model costs are expensive. If you're
[00:03:04] running a company, they get really
[00:03:05] expensive. There are stories going
[00:03:07] around where the numbers are absolutely
[00:03:09] eye-popping. Like one engineer spending
[00:03:11] $80,000 in token costs in a week. That's
[00:03:13] a lot. So if you have that kind of
[00:03:15] pricing power, if people are spending
[00:03:17] tens of thousands of dollars a week on
[00:03:19] tokens, there's an a tremendous amount
[00:03:21] of incentive to make these models work.
[00:03:22] So why is it so hard? Why are why are we
[00:03:25] not seeing a tremendous tipping point
[00:03:26] away? Why are we still seeing Anthropic
[00:03:28] growing their revenue like crazy, OpenAI
[00:03:30] growing their revenue like crazy when
[00:03:32] these incredible good models exist?
[00:03:34] Well, there's a number of factors to
[00:03:36] that, and I want to list them for you so
[00:03:37] that you can actually understand the
[00:03:39] perspective. This is based on talking
[00:03:40] with engineers at companies as well as
[00:03:42] with leaders. The first one is the
[00:03:44] ergonomics of work. If you are just
[00:03:47] trying to get something you've heard
[00:03:49] about, seen about, you have a frontier
[00:03:50] model at you have a frontier model at
[00:03:53] home on your phone, you just want access
[00:03:55] to that. There's a lot of employee
[00:03:56] pressure around Claude and around OpenAI
[00:03:59] in a way that there just isn't for open
[00:04:01] source models. So, that's one piece. Uh,
[00:04:03] and it's not small. Like, when people
[00:04:04] are asking for it vocally saying this
[00:04:06] will help my work, overburdened IT
[00:04:08] departments tend to listen to that.
[00:04:09] Number two, it is actually very, very
[00:04:12] difficult to correctly figure out
[00:04:16] whether your task load is center of
[00:04:19] distribution or edge of distribution
[00:04:22] weighted. If it's edge distribution
[00:04:23] weighted, you actually do want the
[00:04:25] frontier models. If it's center of
[00:04:26] distribution, the open source models are
[00:04:28] going to be really, really good because
[00:04:30] they're common patterns. But, people
[00:04:32] don't They're not used to measuring
[00:04:34] their work that way. Individuals aren't,
[00:04:35] teams aren't. if you're a company trying
[00:04:37] to figure out what is your model
[00:04:38] strategy, you kind of got to tackle
[00:04:41] what is your distribution of tasks? And
[00:04:43] almost no one has asked that question
[00:04:45] properly yet. And people are trying to
[00:04:47] figure out how to measure that. The
[00:04:48] folks that have gone the farthest,
[00:04:50] actually, are folks like Flo Crivello,
[00:04:52] who is, uh, leading the Lindy team, and
[00:04:55] who very publicly wrote up his journey
[00:04:57] to a deep seek architecture away from
[00:05:00] Claude. And, you know, he saved a lot,
[00:05:02] etc., etc. But, he was also very honest
[00:05:05] about the fact that the Lindy team had
[00:05:07] to essentially rewrite their harness
[00:05:10] from scratch around deep seek, and they
[00:05:13] could not just take all of their systems
[00:05:15] for working with Claude, all of their
[00:05:17] prompts, all of the way they handle
[00:05:19] memory, all of their tool calls, and
[00:05:20] just automatically lift and shift. It
[00:05:22] doesn't work that way. These models need
[00:05:24] their own harnesses.
[00:05:25] He was incentivized to do that because
[00:05:27] he is literally serving AI as a service,
[00:05:29] and if he can deliver a cheaper and more
[00:05:31] effective service that hits his margin,
[00:05:33] and it's it's tremendously impactful.
[00:05:35] For folks who are using AI internally
[00:05:37] for coding or for back office
[00:05:38] automation, that ROI is not as clear,
[00:05:40] and the incentive to move is not as
[00:05:42] clear, either. And so, what I have seen,
[00:05:44] and I have seen anecdotes from this, not
[00:05:46] just from Flo, but from other folks that
[00:05:48] I know personally. I know entrepreneurs
[00:05:49] who are wrestling with this today. The
[00:05:52] ones who are actually making the jump to
[00:05:54] open source and dealing with the
[00:05:56] different system prob dealing with the
[00:05:57] different tool called dealing with a
[00:05:58] different memory architecture, etc. That
[00:06:00] is tuned around the fact that these are
[00:06:02] center of distribution models. Those
[00:06:04] guys or those gals are focused on ROI
[00:06:09] for a particular AI tool they have in
[00:06:12] market. Just like Lindy, they see value
[00:06:15] back in their pockets when they can cut
[00:06:17] their token costs. And for everyone
[00:06:19] else, because the incentive is not as
[00:06:21] strong, you don't have the same
[00:06:24] commitment to wade through the challenge
[00:06:26] of building a harness. And that is not a
[00:06:28] small thing. And one of the things I
[00:06:30] want you to take away from this video is
[00:06:32] that a model can be an incredible
[00:06:34] [snorts] brain in a jar. And it it just
[00:06:37] isn't useful to you without a harness.
[00:06:39] And so this is why I pay a ton of
[00:06:41] attention to harness innovations. And I
[00:06:43] want to name a couple that are top of
[00:06:45] mind as we look at GLM 5.2 in context.
[00:06:48] First, I notice that GLM 5.2 was
[00:06:51] released with its own Codex clone
[00:06:53] harness. That's one piece that I pay
[00:06:55] attention to. It looks like the open
[00:06:57] source model makers are realizing they
[00:06:59] need to deliver harnesses as well. And
[00:07:00] so I would expect more innovation in
[00:07:02] that direction. I notice that Codex is
[00:07:04] starting to call out publicly that you
[00:07:07] can use Codex the harness without using
[00:07:09] any OpenAI model. That's notable because
[00:07:13] there's a different path to value for
[00:07:15] OpenAI there. Maybe OpenAI's models are
[00:07:17] the default, but if they're calling out
[00:07:19] that they are actually the harness for
[00:07:20] all of work, it gives them a way to be
[00:07:22] stickier long term. Three, the Anthropic
[00:07:25] team is not just sitting there as all of
[00:07:27] these developments happen. They launched
[00:07:28] Claude Tag this week, and Claude Tag is
[00:07:31] an incredibly sticky product. It is a
[00:07:34] team level harness, and team level
[00:07:35] harnesses are where the energy is going
[00:07:37] because so much of the work we've got is
[00:07:39] individually productive work in AI. It's
[00:07:42] not team productive work. And we're
[00:07:44] trying to figure out, how do we align
[00:07:46] our efforts that are individually
[00:07:47] productive into something that is team
[00:07:49] productive? And Claude tag, which is
[00:07:51] just tag Claude, anyone can tag Claude
[00:07:53] and get work done in Slack, is one of
[00:07:56] the first examples of a sticky viral
[00:07:58] consumer team harness. Where like if
[00:08:01] you're an ordinary knowledge worker at a
[00:08:03] particular company, you can envision
[00:08:05] using that as as a team harness. And you
[00:08:07] don't have to know the word team
[00:08:08] harness, it's just going to work. You
[00:08:09] tag Claude and it works. But look at it
[00:08:12] strategically from Anthropic's
[00:08:13] perspective. Now they're not just
[00:08:15] getting the engineers. Now they're
[00:08:16] getting everybody who's a knowledge
[00:08:17] worker in Slack and they're reading all
[00:08:19] of the messy context that lives in Slack
[00:08:23] that no one knows how to codify and that
[00:08:25] is now getting fed into Claude
[00:08:27] automatically and it can be something
[00:08:30] that the Anthropic team learns from
[00:08:31] within privacy policies long term for
[00:08:34] Claude in the context of that company to
[00:08:38] start to own the harness itself in a way
[00:08:44] that no company can get away from. It's
[00:08:45] an incredibly sticky experience because
[00:08:47] you think about it. Let's say you you
[00:08:49] know that GLM 5.2 is a lot cheaper,
[00:08:51] which it is. It's like 98% cheaper or
[00:08:53] something like that. If it's that much
[00:08:55] cheaper than Claude and it's just about
[00:08:57] as good on most tasks, it is rational to
[00:09:00] build a routing system and assign most
[00:09:02] tasks to GLM 5.2. Except that hey, are
[00:09:05] you going to have Claude tag, right? Are
[00:09:07] you going to go to tag in Claude on that
[00:09:08] stuff? Is that convenience going to be
[00:09:09] there? Are are you going to have to
[00:09:12] restart the job of giving this AI
[00:09:14] context from your company because Claude
[00:09:16] magically acquired it in Slack and you
[00:09:18] didn't have to think about it? We have
[00:09:20] taught companies for decades that data
[00:09:23] is alpha. Data is something you have an
[00:09:25] edge with if you're serious. If data is
[00:09:28] alpha, what do we think about giving all
[00:09:32] of that data to a frontier model
[00:09:34] provider as context? Even if they don't
[00:09:37] release it into training data, even if
[00:09:38] they if the privacy policy is really
[00:09:40] good and they're behaving really
[00:09:42] ethically, which I have no reason to
[00:09:43] think they're not, you still are
[00:09:45] effectively renting your own context
[00:09:47] back to yourself because Claude is going
[00:09:50] to be in your slack as a team level
[00:09:51] harness and is going to be incredibly
[00:09:53] close to all the work your team does and
[00:09:55] it's going to be impossible to rip out.
[00:09:57] No matter how cheap the GLM 5.2 class
[00:10:00] models are,
[00:10:01] how can you rip out the model that's
[00:10:02] that close to context? And I think that
[00:10:05] the GLM 5.2 team knows this. That's why
[00:10:07] they released a harness, a Codex-like
[00:10:09] interface with their AI. It's a first
[00:10:12] stab at it. But we got to get much
[00:10:14] farther there in tech, where the
[00:10:16] companies that know they need harnesses
[00:10:19] generally cannot afford to hire the AI
[00:10:22] talent to build those harnesses unless
[00:10:24] they're extraordinary companies because
[00:10:27] that AI talent is so in demand right now
[00:10:30] that it can charge anything it wants and
[00:10:31] it usually goes to one of the
[00:10:33] hyperscalers or another large company.
[00:10:35] And so we're in the dynamic where the
[00:10:36] only companies that can build their own
[00:10:38] last-mile harnesses, their own auto
[00:10:40] routers, are companies that can afford
[00:10:42] that, that can afford the AI talent to
[00:10:44] do that, which is very scarce. And so if
[00:10:46] you actually think through this dynamic
[00:10:48] with GLM 5.2 and how it's possible but
[00:10:50] at the same time we can have an
[00:10:52] incredible open-source model that we're
[00:10:54] excited about and also that Anthropic
[00:10:56] still has pricing power to charge a lot
[00:10:59] for their tokens even though their
[00:11:00] tokens are just marginally better, it's
[00:11:02] actually not a story of intelligence.
[00:11:03] It's a story of the last-mile in AI and
[00:11:06] the fact that the talent to build the
[00:11:09] last-mile in AI is incredibly scarce.
[00:11:12] Which should, honestly, for a lot of you
[00:11:14] watching, be a source for optimism. If
[00:11:17] we have that scarce a talent, where
[00:11:19] people are ending up locked into
[00:11:20] contracts with a frontier model provider
[00:11:23] because they don't know how to build a
[00:11:25] harness for themselves, wow is there a
[00:11:27] lot of opportunity in knowing how to
[00:11:29] build an AI. Like it's an incredible
[00:11:31] opportunity right now. It is not easy to
[00:11:33] do this work. It's not easy to know this
[00:11:36] is how you handle a tool call in GLM 5.2
[00:11:39] and how you should do it differently
[00:11:40] from Claude. So does figuring out how
[00:11:42] memory will work for that system. So
[00:11:44] does figuring out how the system prompt
[00:11:46] needs to change because it's a center of
[00:11:48] distribution model. It's a lot of
[00:11:50] technical work. And if you know how to
[00:11:52] do that work or know how to do parts of
[00:11:54] that work to essentially refactor
[00:11:56] agentic pipelines so they work with an
[00:11:59] open-source model, you are going to be
[00:12:01] incredibly in demand. Especially if you
[00:12:04] compare that with the ability to route
[00:12:06] tasks where you can take a task and
[00:12:08] recognize on the fly that it's a
[00:12:10] frontier model task and it should go to
[00:12:11] a frontier model versus everything else
[00:12:13] going to a cheaper open-source model.
[00:12:15] That is going to be a huge investment
[00:12:17] theme for companies in 2026, 2027 and
[00:12:20] they're going to keep innovating. Claude
[00:12:21] tag is a fantastic example of how of how
[00:12:24] incentives in frontier close-source
[00:12:26] models are giving us incredible
[00:12:29] experiences. If you have pricing power,
[00:12:30] you are heavily incentivized to make
[00:12:33] sure that your experience is as
[00:12:34] convenient and ergonomic as possible.
[00:12:36] And so features like Claude Claude tag
[00:12:38] are going to appear really, really fast,
[00:12:41] really rapidly, really completely from
[00:12:44] teams at Anthropic, also from OpenAI
[00:12:46] because they're incentivized to keep
[00:12:48] those those prices high and to go after
[00:12:51] that business. And with open-source
[00:12:53] models, you don't have the same margin
[00:12:55] to work with, you don't have the same
[00:12:56] cash flow to work with and you don't
[00:12:58] have the same incentive to dig in and
[00:13:00] deploy thousands of forward-deployed
[00:13:01] engineers and really make these
[00:13:03] harnesses sing. And so one of the really
[00:13:06] interesting facts that we come to after
[00:13:08] all of this can simultaneously be an
[00:13:11] incredible model, a model that a lot of
[00:13:13] entrepreneurs switch to when the ROI is
[00:13:15] clear and they're technically savvy
[00:13:16] enough to do it, and also not a model
[00:13:19] that is easy for a given company that
[00:13:22] you turn up in phone book to actually
[00:13:25] use. It any given company is going to
[00:13:28] have to think about how they use GLM 5.2
[00:13:30] to use it usefully, and they're going to
[00:13:32] have to think a lot less to sign up for
[00:13:34] a frontier model contract that's going
[00:13:35] to fit right into their existing
[00:13:37] workflows. That last mile is literally a
[00:13:40] trillion-dollar last mile in AI. And one
[00:13:43] of the biggest open questions right now
[00:13:46] is whether we will scale our talent fast
[00:13:49] enough to enable businesses to tackle
[00:13:52] that problem set without paying so much
[00:13:57] that they can't afford it. I don't know
[00:13:58] what the answer's going to be, but
[00:13:59] that's a question we're going to have an
[00:14:01] answer to. We will all collectively
[00:14:03] answer together in the next 3 to 6
[00:14:07] months. We are going to find out,
[00:14:09] especially as the US government has this
[00:14:11] effective pause in place on frontier
[00:14:13] model releases,
[00:14:14] and the open-source systems are going to
[00:14:16] continue to be available, we're going to
[00:14:17] find out whether companies can adjust to
[00:14:21] the fact that intelligence is 98%
[00:14:23] cheaper and takes a last mile to build.
[00:14:25] Can they actually build that last mile?
[00:14:27] Can they find teams to build that last
[00:14:28] mile? If you are in an agency or in a
[00:14:30] consulting space, this is a golden goose
[00:14:33] moment. Like you have a chance here. You
[00:14:35] can really go to town and basically
[00:14:37] promise to save people a ton of money on
[00:14:40] tokens as part of your ROI proposition,
[00:14:42] as long as you can deliver that refactor
[00:14:44] in a way that maintains quality, which
[00:14:45] is not a trivial task. If it was easy,
[00:14:47] we wouldn't be having this video. So,
[00:14:49] where does this leave us? GLM 5.2 is an
[00:14:53] incredible model. It is important not to
[00:14:56] shame a model or diss a model because
[00:14:58] it's good at center of distribution
[00:14:59] task, because by definition that is most
[00:15:01] of our work. Collectively as a species,
[00:15:04] most of our knowledge work is center of
[00:15:05] distribution, just by definition. And if
[00:15:07] that's the case, a model that's really
[00:15:09] good at that is worth taking really
[00:15:11] seriously. And if we take it seriously,
[00:15:13] that means we have to take the last mile
[00:15:15] seriously. We have to take the idea that
[00:15:16] we need a harness for that last mile
[00:15:18] seriously. And that's a lot of what I
[00:15:20] have been doing in public is starting to
[00:15:22] articulate what it takes to build a
[00:15:25] harness, whether it's open skills or
[00:15:27] open brain or open engine, which I've
[00:15:29] all talked about on this channel. How do
[00:15:32] you start to take these pieces and put
[00:15:33] them together in a way that is agent
[00:15:35] agnostic, that is model agnostic, so you
[00:15:37] can start to install those pieces and
[00:15:39] actually take advantage of all the
[00:15:41] intelligence on tap. Whether it's
[00:15:43] Claude, whether it's it's Codex, whether
[00:15:45] it's Hermes, whether it's whatever
[00:15:47] whatever system you want, whether it's
[00:15:49] your own iPhone 2, you should be able to
[00:15:52] easily build to that last mile. And and
[00:15:56] I know that there's a lot of custom work
[00:15:57] for individual companies, and that's why
[00:15:58] I keep saying this is a time for
[00:16:00] builders. But if we don't start down
[00:16:02] that path, we're essentially going to be
[00:16:03] renting our company brain and company
[00:16:05] context back from the frontier model
[00:16:09] providers.
[00:16:10] And they're going to have it. And
[00:16:11] they're going to be able to use it to
[00:16:13] continue to improve their systems and
[00:16:15] make them more useful, and they'll be
[00:16:16] incredibly convenient, incredibly sticky
[00:16:18] products. And what are we going to do?
[00:16:20] We're going to have to use them. So,
[00:16:21] this is a very pivotal moment for
[00:16:23] corporations. The firm has never faced a
[00:16:26] moment where the firm's brain has been
[00:16:29] on rent. And that is what we're on the
[00:16:30] verge of with tools like Claude Tag,
[00:16:33] which are incredibly useful. I'm not
[00:16:35] saying they're not useful, they're very
[00:16:36] useful. That's exactly the dangerous
[00:16:38] thing. So, I would encourage you
[00:16:40] if you are even if it's a tiny company,
[00:16:43] let's say you're building your own
[00:16:44] agency, you're an individual
[00:16:45] entrepreneur, think seriously, just as
[00:16:48] you would if you're a larger company
[00:16:49] leader, think seriously about whether
[00:16:51] you want to rent that context and
[00:16:53] intelligence or not. Think seriously
[00:16:56] about where you want to go with your
[00:16:57] context long term. Ask yourself, do you
[00:17:01] have an idea of the distribution of your
[00:17:03] tasks? Do you have access to technical
[00:17:05] talent that you can use to build out
[00:17:07] that last mile? What are the task sets
[00:17:10] that you would want to assign that would
[00:17:12] save you a ton in tokens? A lot of
[00:17:14] people don't sit down and get pencil and
[00:17:16] paper and actually ask themselves those
[00:17:17] kinds of questions. And I have a whole
[00:17:19] sort of question set that's in more
[00:17:20] detail that I've been going over with
[00:17:22] leaders. I put that on the Substack. Uh
[00:17:24] but this is a really serious thing. This
[00:17:26] is a moment for open source. GLON 5.2
[00:17:29] opened that door for all of us, and it's
[00:17:31] going to be up to us to see how we take
[00:17:33] advantage of it. Good luck with that.
[00:17:34] Cheers. Bye.
