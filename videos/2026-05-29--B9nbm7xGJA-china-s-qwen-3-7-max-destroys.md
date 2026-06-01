---
video_id: -B9nbm7xGJA
title: China’s Qwen 3.7 Max DESTROYS Claude?
channel: "AI News Today | Julian Goldie Podcast"
url: "https://www.youtube.com/watch?v=-B9nbm7xGJA"
watched_date: 2026-05-29
watched_at: "2026-05-29T12:00:00Z"
watch_count: 1
duration_seconds: 911
source: youtube-history-browser
history_label: Friday
history_order: 59
watched_at_precision: date-from-history-label
watched_percent: 48
estimated_watched_seconds: 437
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Alibaba released Qwen 3.7 Max, a frontier-level AI model that scores within 0.7 points of Claude Opus 4.7 on the Artificial Intelligence Index while costing half the price ($2.50 per million input tokens versus $5, and $7.50 per million output tokens versus $25). The model beats Claude Opus 4.6 on multiple benchmarks including Terminal Bench 2.0, SWE Bench Pro, and GPQA Diamond, and is already available on Alibaba Cloud Model Studio, OpenRouter, and Together AI with compatibility for multiple agent frameworks including Hermes Agent and Claude Code. However, two significant caveats exist: the model outputs roughly 4x more tokens than competitors on the same tasks, potentially eroding cost savings in practice, and it has a 48% refusal rate on factual questions (down from 67% attempt rate on the previous model), achieving its low 22.9% hallucination rate by declining to answer questions it's uncertain about. Alibaba demonstrated a vendor-claimed 35-hour autonomous task where the model optimized a custom AI kernel 10x better than the original, though this hasn't been independently verified.

To evaluate Qwen 3.7 Max for your business, test it on your actual workflows (lead generation, content creation, research, coding) and measure both output quality and real token costs rather than relying on headline pricing. If you're already running Hermes Agent or OpenAI's frameworks, plug Qwen 3.7 Max in as a drop-in model replacement and monitor token verbosity in your specific use cases. Avoid switching if you're using Claude Opus 4.7 successfully, but seriously evaluate Qwen 3.7 Max if you're running AI agents at scale where cost compounds daily. For teams not yet using AI agents, now is an optimal time to start since frontier-level intelligence is becoming affordable; focus first on the business problem you want automated, then choose your model afterward.

## Transcript

[00:00:00] Alibaba's Qwen 3.7 Max just ran for 35
[00:00:05] hours straight. Not just that, but it's
[00:00:07] also destroying Claude in many
[00:00:09] benchmarks. This is China's most popular
[00:00:13] model right now across the world in
[00:00:15] terms of being an intelligent tool, and
[00:00:17] this was running for 35 hours straight
[00:00:20] with no human, no breaks, 1,158 tool
[00:00:24] calls, and at the end of it, it had an
[00:00:27] optimized complex AI kernel
[00:00:30] to run 10 times faster than the
[00:00:31] original. This is not a marketing slide.
[00:00:33] That is the demo they showed at the
[00:00:36] Alibaba Cloud Summit in Hangzhou on May
[00:00:39] the 20th, 2026, and it should have way
[00:00:42] more people talking about it because
[00:00:44] here's what actually happened. Alibaba
[00:00:46] just released a frontier-level AI model,
[00:00:50] Qwen 3.7 Max, that scores within 0.7
[00:00:53] points of Claude Opus 4.7 on the
[00:00:56] Artificial Intelligence Index, the most
[00:00:58] credible independent AI benchmark out
[00:01:01] there right now, and it costs half the
[00:01:02] price. Not just that, but it's actually
[00:01:04] beating many of the benchmarks for
[00:01:07] Claude Opus 4.6 as well. So, if you've
[00:01:09] been spending money on Claude Opus 4.7
[00:01:11] or GPT-4 for your business, you need to
[00:01:14] know about this because the AI landscape
[00:01:16] in 2026 is not just Anthropic and OpenAI
[00:01:19] anymore. China just showed up at the
[00:01:21] frontier. So, let me talk you through
[00:01:23] exactly what this model is, what it can
[00:01:24] do, where it beats the competition, and
[00:01:26] crucially where it doesn't because there
[00:01:28] are real caveats to this, of course, as
[00:01:30] well. And I'd rather you know them up
[00:01:32] front than find out the halfway. So,
[00:01:34] Qwen 3.7 Max, what is it? It's Alibaba's
[00:01:37] new flagship AI model, and this is a big
[00:01:40] shift for Alibaba because they've always
[00:01:42] been known for releasing open-source
[00:01:44] models, models anyone can download and
[00:01:46] run themselves. Qwen 3.5, 3.6, all of
[00:01:48] those were open and free to use. 3.7 Max
[00:01:51] is not that. This is their first serious
[00:01:53] closed proprietary flagship. They're
[00:01:56] going to have to enterprise money now.
[00:01:57] They want to compete with Anthropic and
[00:01:59] OpenAI for real business customers. And
[00:02:01] that's a major strategic move. The model
[00:02:03] dropped on May the 19th, 2026, quietly,
[00:02:06] one day before the big public
[00:02:08] announcement at the Cloud Summit. It's
[00:02:10] already live on Alibaba Cloud Model
[00:02:12] Studio, OpenRouter, Together AI, and a
[00:02:14] platform called Qubit AI. You can use it
[00:02:16] right now, pretty much everywhere. And
[00:02:17] here's where it gets interesting. For
[00:02:19] anyone running AI agents, Qwen 3.7 Max
[00:02:22] works across multiple agent frameworks.
[00:02:24] So, it supports Google Cloud, it
[00:02:25] supports Hermes Agent, the self-evolving
[00:02:28] open-source agent from Nous Research. It
[00:02:30] supports Claude Code. It can even
[00:02:32] support Qwen's own Qwen Code framework.
[00:02:34] The API is compatible with both the
[00:02:36] OpenAI spec and the Anthropic spec. So,
[00:02:40] if you're already running Open Cloud or
[00:02:41] Hermes in your business, you can drop
[00:02:43] Qwen 3.7 Max in as your underlying model
[00:02:46] without rebuilding anything from
[00:02:48] scratch, which is actually massive
[00:02:49] because it means you don't have to
[00:02:50] choose between the best agent framework
[00:02:53] and the cheapest frontier model. You can
[00:02:54] actually just have both. Now, let's talk
[00:02:56] benchmarks because the numbers here are
[00:02:57] genuinely surprising, too. On Terminal
[00:02:59] Bench 2.0, one of the hardest agentic
[00:03:02] coding tasks out there, Qwen 3.7 Max
[00:03:04] scores 69.7. That beats DeepSea 34 Pro
[00:03:07] at 67.9. And it beats Claude 2.16 at
[00:03:10] 66.7. And it beats Claude Opus 4.6 Max
[00:03:14] at 65.4. On SWE Bench Pro, which tests
[00:03:17] the model's ability to fix real software
[00:03:19] bugs, Qwen 3.7 Max scores 60.6. Claude
[00:03:22] Opus 4.6 Max scores 57.3.
[00:03:25] DeepSea 34 Pro scores 59. And on MC
[00:03:28] Atlas, which tests how well a model
[00:03:30] coordinates with other tools and agents,
[00:03:33] Qwen 3.7 Max scores 76.4. Claude Opus
[00:03:37] 4.6 Max scores 75.8. On GPQA Diamond,
[00:03:41] one of the hardest reasoning tests
[00:03:42] available, hard PhD-level science
[00:03:44] questions, Qwen 3.7 Max scores 92.4.
[00:03:47] Claude Opus scores 91.3. So, across
[00:03:50] almost every benchmark that matters for
[00:03:52] running AI agents in your business, Qwen
[00:03:54] 3.7 Max is at or above what Anthropic's
[00:03:59] best publicly available model can do.
[00:04:02] And the overall artificial analysis
[00:04:03] intelligence index puts it at 56.6
[00:04:06] compared to Claude Opus 4.7 and 57.3.
[00:04:09] 0.7 point difference at the frontier
[00:04:11] level. Now, here's a price comparison.
[00:04:13] This where you need to pay attention.
[00:04:14] So, Claude Opus 4.7 $5 per million input
[00:04:18] tokens. $25 per million output tokens.
[00:04:21] Chinchilla 5.5, $5 per million input
[00:04:23] tokens, $30 per million output tokens.
[00:04:26] Qwen 3.7 Max, 2.5 per million input
[00:04:30] tokens and 7.5 per million output
[00:04:32] tokens, right? It's half the input price
[00:04:34] of Opus and a quarter of the output
[00:04:36] price. So, if you're running heavy AI
[00:04:38] workflows, agents in research, writing,
[00:04:40] analysis, lead generation, the cost
[00:04:42] difference over a month of usage is real
[00:04:44] money. But, I have to be honest with you
[00:04:45] here because there's a catch on the cost
[00:04:47] side that most people aren't talking
[00:04:49] about. Qwen 3.7 Max is the boss. So,
[00:04:52] during public and independent benchmark
[00:04:54] testing, it generated 97 million output
[00:04:57] tokens. The median for other models in
[00:04:59] the same test was around 24 million. So,
[00:05:01] it's outputting about four times more
[00:05:03] words for the same tasks. At $7.5 per
[00:05:06] million output tokens, those extra words
[00:05:09] add up. A task that would cost you $180
[00:05:13] with an average model could cost closer
[00:05:15] to $727
[00:05:17] with 3.7 Max depending on what it's
[00:05:20] doing. So, don't just look at the rate
[00:05:22] card, run your actual task for it and
[00:05:24] measure. The savings are real, but
[00:05:26] they're not as dramatic as headline
[00:05:27] numbers suggest for every use case.
[00:05:29] There's also a hallucination story here
[00:05:31] that deserves a closer look. So, Qwen
[00:05:33] 3.7 Max has a hallucination rate of
[00:05:35] 22.9% on the AA Omniscience test. That's
[00:05:39] the lowest of any frontier model in its
[00:05:41] comparison group. That sounds
[00:05:43] incredible, right? Here's a full
[00:05:44] picture. The model achieves that low
[00:05:46] hallucination rate partly by refusing to
[00:05:48] answer things it's not actually sure
[00:05:50] about. So, it's attempt rate, how often
[00:05:52] it actually tries to answer a question,
[00:05:54] dropped from 67% on the previous model
[00:05:57] to 48% on Qwen 3.7 Max. So, it's
[00:06:00] basically saying, "I don't know." more
[00:06:02] than half the time rather than risking
[00:06:04] it wrong. For certain tasks, that's
[00:06:06] probably what you want, right? But if
[00:06:08] you're using it for coding, for
[00:06:09] analysis, for building workflows, a
[00:06:10] model that says, "I'm not sure." instead
[00:06:12] of making something up is a good thing.
[00:06:14] But if you're building a customer-facing
[00:06:16] chatbot that needs to answer lots of
[00:06:17] questions with high confidence, the 48%
[00:06:20] attempt rate is a real problem. It will
[00:06:22] leave too many questions unanswered. So,
[00:06:24] you really want to know your use case
[00:06:26] before you even switch. And speaking of
[00:06:27] use cases, let me tell you about that
[00:06:29] 35-hour
[00:06:31] demo in more detail because this is
[00:06:33] genuinely the most ambitious
[00:06:35] single-agent demonstration any major AI
[00:06:38] lab has published in 2026. So, Alibaba
[00:06:41] gave Qwen 3.7 Max a task: Optimize a
[00:06:44] specific AI computation kernel, a piece
[00:06:47] of software that handles how AI models
[00:06:49] process memory for Alibaba's own custom
[00:06:51] chip, the GenWoo
[00:06:54] M890. This chip has never appeared in
[00:06:57] any AI training data. The model had
[00:06:59] never seen it before. No documentation,
[00:07:02] no example code, just a task description
[00:07:04] and an evaluation script. Over 35 hours,
[00:07:07] the model made 32 separate attempts at
[00:07:10] optimizing the kernel. It called tools
[00:07:13] 1,158 times, diagnosed its own failures,
[00:07:16] rewrote its approach multiple times, and
[00:07:18] kept improving even after a 30 hours,
[00:07:21] well past the point where most models
[00:07:23] would stop making progress. The final
[00:07:25] result, it was 10 times faster than the
[00:07:27] original code. So, by comparison, GLM
[00:07:29] 5.1 hit 7.3 times on the same task, Deep
[00:07:33] Seek V4 Pro hit 3.3 times, and Qwen 3.7
[00:07:36] Max more than doubled the second best
[00:07:38] result. Now, for transparency, this is
[00:07:40] the vendor-stated. So, Alibaba ran the
[00:07:43] demo, independent researchers had not
[00:07:45] reproduced it as of May 25th, 2026. So,
[00:07:48] treat it as a very promising signal, not
[00:07:51] confirmed fact. But, even if the
[00:07:53] real-world number is half of that, it's
[00:07:55] still an extraordinary result. And the
[00:07:57] bigger point is what it shows about
[00:08:00] where AI agents are heading, right? A
[00:08:01] year ago, the idea of an AI agent
[00:08:04] running for 35 hours and completing a
[00:08:06] complex engineering task better than any
[00:08:08] human team would have kind of felt like
[00:08:11] science fiction. In May 2026, Alibaba
[00:08:13] just did it on their own hardware using
[00:08:15] their own model with no human in the
[00:08:16] loop. That's the direction everything's
[00:08:18] headed. Now, let me talk about Hermes
[00:08:20] agent here as well, because if you're
[00:08:21] watching this channel, there's a good
[00:08:22] chance you've already heard me talk
[00:08:24] about Hermes agent, the self-evolving
[00:08:26] agent from Mistral Research. It builds
[00:08:27] skills from experience, runs
[00:08:28] persistently, has a built-in feedback
[00:08:30] loop. Right, Qwen 3.7 Max is now listed
[00:08:32] as comparable model for Hermes, which
[00:08:34] means you can use Hermes self-evolving
[00:08:36] agent framework with Alibaba's Frontier
[00:08:38] model powering it underneath. Hermes
[00:08:40] handles the memory, the skill building,
[00:08:41] the persistence. Qwen 3.6, sorry, 3.7
[00:08:44] Max handles the reasoning, the coding,
[00:08:46] the analysis. Now, that combination
[00:08:48] works pretty well. I've tested it out
[00:08:49] myself, works really well. And since
[00:08:51] Qwen 3.7 Max has strong MCP coordination
[00:08:55] skills, remember 76.4
[00:08:58] on MCP Atlas, it should handle
[00:09:01] multi-tool orchestration well. Now, if
[00:09:03] you're already inside the Upwork bot,
[00:09:05] you already have access to our agent OS,
[00:09:07] the system where you can plug in all
[00:09:08] your AI agents, including your open core
[00:09:10] setup, your Hermes agent, and your
[00:09:12] Claude code workflows into one unified
[00:09:14] operating system for your business.
[00:09:16] We've already been testing it with Qwen
[00:09:18] 3.7 Max integrations inside the agent
[00:09:21] operating system. And members inside
[00:09:23] have been asking about this. So, if you
[00:09:24] want live walk-throughs, a 30-day
[00:09:27] roadmap for plugging Qwen 3.7 Max into
[00:09:30] your agent stack, and step-by-step
[00:09:32] tutorials on setting this up inside
[00:09:34] agent OS with coaching calls where you
[00:09:36] can ask questions live about your
[00:09:38] about your specific setup. Link in the
[00:09:40] comments description or go to the
[00:09:41] airpodform.com. Now, let me address
[00:09:43] something I hear a lot, which is like,
[00:09:45] "Julian, don't need another model.
[00:09:47] Already use Claude. Why should I even
[00:09:49] care about this?" Here's the honest
[00:09:50] answer. You probably don't need to
[00:09:51] switch everything over today. Claude
[00:09:53] Opus 4.7 is still slightly ahead on the
[00:09:56] overall intelligence index. If you have
[00:09:57] workflows that are working well, don't
[00:09:59] break them for the sake of it, right?
[00:10:01] But, here's what you should be thinking
[00:10:02] about. As AI agents become more central
[00:10:04] to how your business runs, lead
[00:10:05] generation, content creation, research,
[00:10:07] customer follow-up, proposal writing,
[00:10:09] the cost of running these agents at
[00:10:11] scale becomes a real business expense,
[00:10:14] right? $2.5
[00:10:15] versus $5 per million input tokens
[00:10:17] sounds small, but if you're running
[00:10:19] agents all day, every day, that
[00:10:21] difference compounds fast. And bear in
[00:10:22] mind, like, we're only using AI agents
[00:10:24] more and more, right? We're not using
[00:10:25] them less anymore. So, the businesses
[00:10:27] that figure out how to run
[00:10:28] frontier-level intelligence at
[00:10:30] mid-market prices are going to have a
[00:10:31] real cost advantage over the ones paying
[00:10:34] premium prices for marginally better
[00:10:36] performance. Qwen 3.7 Max is the first
[00:10:38] time a Chinese model has genuinely
[00:10:41] closed the gap enough to make that
[00:10:43] conversation worth having. And this
[00:10:45] isn't a one-off, right? The Artificial
[00:10:46] Intelligence Index shows Alibaba at
[00:10:49] 56.6, Opus 4.7 at 57.3. Only 0.7 points,
[00:10:53] right? Six months ago, that gap was much
[00:10:55] larger. The trajectory is here, right?
[00:10:57] And it's clear, which is Alibaba is
[00:10:59] catching up. There's also a broader
[00:11:01] thing worth saying as well. We're in
[00:11:02] 2026. The idea that the AI race is just
[00:11:06] between Anthropic, OpenAI, and Google
[00:11:08] was always going to have a shelf life.
[00:11:10] Chinese AI labs have been building hard,
[00:11:13] right? The Alibaba Cloud Summit framing
[00:11:15] was, "We're building China's AI
[00:11:17] factory." It's not marketing, right?
[00:11:19] It's a full stack strategy. Their own
[00:11:21] frontier model, their own custom chip,
[00:11:24] their own agent frameworks, their own
[00:11:26] deployment infrastructure. This is a
[00:11:27] complete ecosystem play, not just a
[00:11:30] model release. And if you're building
[00:11:31] your business on AI right now, you need
[00:11:33] to understand that the models you're
[00:11:34] using 6 months from now might look very
[00:11:37] different from the ones you're actually
[00:11:38] using today. So, what should you
[00:11:40] actually do with all of this? If you're
[00:11:42] running Open Q you can configure 3.7 Max
[00:11:45] as you want to through Alibaba Cloud
[00:11:46] Model Studio or Open Retail. Test on
[00:11:48] your actual tasks, content creation,
[00:11:50] research, lead generation, and compare
[00:11:52] the output quality and cost against what
[00:11:54] you're currently running. If you're
[00:11:56] running Hermes Agent, Qwen 3.7 Max is
[00:11:59] already listed as a compatible model.
[00:12:01] Plug it in and run your standard Hermes
[00:12:03] workflows through it. Pay attention to
[00:12:05] the verbosity. Hermes workflows with a
[00:12:07] lot of back and forth may generate more
[00:12:09] tokens than expected. And if you're not
[00:12:11] running any AI agents yet, this is a
[00:12:14] great moment to start. The cost of
[00:12:16] Frontier AI level is dropping. The tools
[00:12:19] for running agents, Open Q, Hermes Agent
[00:12:21] OS, are getting more capable and models
[00:12:23] like Qwen 3.7 Max are making it more
[00:12:25] affordable to run serious AI workflows
[00:12:28] without enterprise-level budgets. The
[00:12:30] businesses that win over the next 2
[00:12:31] years are the ones building AI workflows
[00:12:33] now while most of their competitors are
[00:12:35] still doing things manually, which
[00:12:37] brings me to the biggest limited belief
[00:12:38] I see holding people back right now. All
[00:12:40] right, a lot of people think AI's too
[00:12:41] complicated for you to get set up. And
[00:12:44] I'm not going to lie, right? 6 months
[00:12:45] ago getting AI agents running your
[00:12:47] business took real technical effort. In
[00:12:49] 2026 with tools like Open Q's dashboard,
[00:12:51] Hermes built-in tools, and the Agent OS
[00:12:53] inside the AI Profit Bottom, the setup
[00:12:55] has never been simpler, right? You don't
[00:12:57] need to touch a line of code. You need
[00:12:59] to understand what tasks you want
[00:13:00] automated and follow a step-by-step
[00:13:02] process for it. Some people as well will
[00:13:03] say, "Well, I don't know which model to
[00:13:05] use." That's actually the wrong question
[00:13:06] to start with. Start with the problem
[00:13:08] you're trying to solve. If it's
[00:13:09] generating leads, there's a workflow for
[00:13:10] that. If it's writing content, there's a
[00:13:12] workflow for that, right? The model
[00:13:13] choice comes after the workflow design,
[00:13:15] not before. And this is exactly the kind
[00:13:18] of decision we walk through on the
[00:13:19] weekly coaching calls inside the AI
[00:13:21] Profit Bottom. Other people say, "Well,
[00:13:22] I'll wait until the technology is more
[00:13:24] stable." Here's the thing, the
[00:13:25] technology is not going to stop
[00:13:27] changing. Quen 3.7 Max just dropped and
[00:13:29] it's already competitive with Claude
[00:13:30] Opus 4.7. In 3 months, there will be
[00:13:33] something new. In 6 months, something
[00:13:35] else after that, right? The people
[00:13:36] waiting for stability are the people who
[00:13:39] will still be waiting in 2027 while
[00:13:41] their competitors have had 12 months of
[00:13:44] AI automation experience under their
[00:13:45] belt, right? The time to learn is now
[00:13:47] while the tools are still accessible and
[00:13:49] the competition hasn't caught up yet.
[00:13:51] And if you want to stay ahead of all
[00:13:52] this, not just today, but as the models
[00:13:54] keep improving, come join us inside the
[00:13:56] AI Profit Boardroom. We've built the
[00:13:57] Agent Operating System
[00:13:59] where you can plug in Quen 3.7 Max, Open
[00:14:02] Claude, Hermes, Claude Code, all your
[00:14:04] tools into one unified system for your
[00:14:07] business. We've got tutorials going up
[00:14:09] showing exactly how to configure Quen
[00:14:11] 3.7 Max in your agent stack, how to use
[00:14:14] it for lead generation and content
[00:14:16] workflows, and coaching calls where
[00:14:17] 3,200 business owners are already
[00:14:19] automating with these tools and can tell
[00:14:21] you exactly what's working right now.
[00:14:22] Plus, a 30-day roadmap specifically
[00:14:24] designed to get your first AI agent
[00:14:26] workflows live generating results. Link
[00:14:28] in the comments and description or just
[00:14:29] go to the AI Profit Boardroom.com. The
[00:14:31] short version of Quen 3.7 Max is this:
[00:14:33] it's a Chinese frontier level
[00:14:35] intelligence, half the price of Claude
[00:14:36] Opus 4.7, works with Open Claude and
[00:14:38] Hermes out of the box, built to run long
[00:14:40] horizon tasks automatically and
[00:14:42] autonomously. The caveat is for both, so
[00:14:45] measure your actual cost, has a high
[00:14:47] abstention rate on factual questions, so
[00:14:49] test it on your specific use case, and
[00:14:51] the 35-hour autonomous demo is vendor
[00:14:54] stated, not independently verified,
[00:14:57] right? But the direction is clear.
[00:14:58] Chinese AI, sorry, China's AI is the
[00:15:02] frontier now. The price war is real and
[00:15:04] the businesses that figure out how to
[00:15:06] use these tools are going to have a
[00:15:07] serious advantage over the ones that
[00:15:08] don't. Thanks for watching. I'll see you
[00:15:10] in the next one. Cheers. Bye-bye.
