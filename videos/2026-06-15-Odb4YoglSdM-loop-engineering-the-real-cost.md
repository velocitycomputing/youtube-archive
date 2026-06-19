---
video_id: Odb4YoglSdM
title: Loop Engineering & the Real Cost of Agentic AI
channel: "The Engineering Wisdom | Rakia Ben Sassi"
url: "https://www.youtube.com/watch?v=Odb4YoglSdM"
watched_date: 2026-06-15
watched_at: "2026-06-15T12:00:00Z"
watch_count: 1
duration_seconds: 3603
source: youtube-history-browser
added_date: 
history_label: Monday
history_order: 62
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 360
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What Was Discussed:**
The video covers loop engineering—automating AI agent workflows to invert the manual prompting paradigm. The speaker outlined five essential building blocks (automation, work trees, skills, MCP plugins, sub-agents) plus a critical sixth block (persistent memory/state file) that prevents agent amnesia and allows loops to compound rather than restart. Using GitHub's production auto-triage loop as a concrete example, the talk detailed how they achieved 62% token savings through three optimization techniques: removing unnecessary tool schemas from prompts (MCP pruning), prefetching deterministic data before the agent runs, and right-sizing models (Haiku for classification at 3× lower cost, Opus for complex reasoning, Sonnet for batch overnight work). The economics revealed that 85% of session costs come from input tokens (reading files and context), not output generation, making context reduction the primary cost lever. The speaker warned that loops amplify existing patterns—both good practices in clean code and bad practices in legacy systems—and emphasized that infrastructure quality, test coverage, and guardrails must precede scaling token spending.

**What's Actionable:**
Stop manually prompting and design autonomous loops with persistent state files that learn across runs. Immediately audit your AI workflows: implement prompt caching (50× cheaper for repeated context), use the batch API for overnight work (50% discount), and assign Haiku for classification, Opus for architecture decisions, and Sonnet for batch tasks rather than defaulting to Opus everywhere. Prefetch deterministic data (file contents, specs) as markdown before agents run—don't make agents call tools for static information. Only automate repetitive, deterministic work; keep humans in the loop for incident triage and interactive decisions where new information arrives. Before implementing loops on legacy codebases, first improve code quality and documentation, since AI amplifies existing patterns. Track cost per commit rather than total spend, and measure your current baseline before adopting the "$1,000 tokens per engineer per day" target from stronger companies—scale only if your infrastructure, testing, and guardrails can handle high-velocity automated output.

## Transcript

[00:00:00] Today's issue or topic that we will
[00:00:02] tackle is loop engineering hype versus
[00:00:06] reality and the real cost of agentic AI.
[00:00:10] Two things happened recently, actually.
[00:00:14] First, I made the YouTube video warning
[00:00:16] engineers about dark code the crisis
[00:00:20] that AI is generating because AI is
[00:00:23] actually generating more code than any
[00:00:26] human can actually understand. I walked
[00:00:28] through Dan Shepilo's five levels of AI
[00:00:31] coding skills from level zero where you
[00:00:34] write everything by hand up to level
[00:00:38] five which is also known by the dark
[00:00:42] factory.
[00:00:43] And in the dark factory
[00:00:46] it the software builds itself and the
[00:00:48] humans are neither needed nor welcome it
[00:00:52] in writing and reviewing the code.
[00:00:55] And the second thing was an article
[00:00:58] published by Adnan Ousmani. Let me just
[00:01:01] share it on my screen. It's this one.
[00:01:08] And
[00:01:09] in this article Adnan Ousmani explained
[00:01:13] how to build the thing that I was
[00:01:15] warning about
[00:01:17] by using loop engineering.
[00:01:20] But I'm glad that he was also skeptical
[00:01:23] about this paradigm and uh
[00:01:26] clarified what risks are related to it
[00:01:29] and
[00:01:30] uh some scenarios where it might not be
[00:01:34] the best fit and what basics and
[00:01:36] requirements it needs.
[00:01:39] So, naturally I made this deck, the
[00:01:42] slides that I have created for today's
[00:01:44] session. And this section actually
[00:01:47] connects two dots. I will connect Dan
[00:01:50] Shepilo's concept. Dan Shepilo told us
[00:01:54] where we are going in the AI landscape
[00:01:58] and Ali Ousmane told us how to get
[00:02:01] there. And my job today is to tell you
[00:02:04] what it actually costs you and what
[00:02:06] requirements and maybe issues you need
[00:02:09] to be aware of. I will show you also
[00:02:12] what it looks like in production and
[00:02:14] critically what it quietly breaks that
[00:02:17] your metrics will not catch.
[00:02:20] So, let's get into it. Here is a quick
[00:02:23] road map. Five ideas and first uh first
[00:02:27] one is the paradigm shift. It shows us
[00:02:30] why manually prompting is already the
[00:02:33] old way.
[00:02:34] Or at least according to some
[00:02:36] people perspectives.
[00:02:38] And second, the architecture.
[00:02:41] The five building blocks and the sixth
[00:02:43] one that most or almost everyone
[00:02:47] forgets. And the forgetting is
[00:02:49] expensive.
[00:02:50] And the third idea is uh real-world
[00:02:53] example. And this is my favorite part in
[00:02:57] this deck.
[00:02:59] A loop GitHub runs in production right
[00:03:02] now and I will show it step-by-step with
[00:03:05] the token saving they published
[00:03:08] after their optimization.
[00:03:11] And the fourth
[00:03:12] part
[00:03:13] is the costs.
[00:03:16] There are three scenarios from baseline
[00:03:18] to to their factory with actual math.
[00:03:22] And the fifth is the three yet that
[00:03:25] velocity metrics will not surface for
[00:03:28] you. So, here is the uncomfortable
[00:03:30] truth. When you are manually prompting
[00:03:33] any AI coding assistant,
[00:03:35] you made yourself the bottleneck.
[00:03:38] Your throughput is capped by your
[00:03:41] attention
[00:03:42] and how many agents you can run in
[00:03:44] parallel
[00:03:45] in your different terminals.
[00:03:48] And the
[00:03:49] the loop engineering is here to invert
[00:03:53] this concept. So, the concept of loop
[00:03:55] engineering
[00:03:57] is it invites you to stop being the
[00:04:00] person who drives the agent and start
[00:04:03] being the person who designs the system
[00:04:05] that drives the agent.
[00:04:08] So, the throughput
[00:04:10] difference is not two times, and it's
[00:04:12] not even 10 times. It's the difference
[00:04:15] between your working hours and your
[00:04:17] working hours multiplied by however
[00:04:22] parallel loops are running while you
[00:04:24] sleep.
[00:04:26] Both Chenny, the
[00:04:29] head of Claude at Anthropic, actually
[00:04:32] said it, and Peter Steinberger, the
[00:04:35] author of Open Claude, amplified it.
[00:04:38] You should not be prompting agent
[00:04:40] anymore. You should be designing loops
[00:04:43] that prompt agent.
[00:04:46] I want to hear from you which side of
[00:04:49] this diagram
[00:04:51] the left or the right are you on right
[00:04:54] now. Be honest in the comments. There is
[00:04:56] generally no wrong answer. I will
[00:04:58] explain why later. We have
[00:05:02] a quiz
[00:05:03] to
[00:05:05] maybe trigger your curiosity.
[00:05:08] So, this quiz says, "Your loop generates
[00:05:11] code,
[00:05:13] then you review it in the same Claude
[00:05:15] session. What is actually happening?"
[00:05:19] Option A, confirmation bias at machine
[00:05:22] speed.
[00:05:23] Option B, best practice.
[00:05:26] It's best practice what is described
[00:05:28] here.
[00:05:29] It's one session, one bill.
[00:05:31] Or option C, fine. It all tests if it's
[00:05:36] fine if all tests pass,
[00:05:38] and the code speaks for itself.
[00:05:41] Or option D, industry standard
[00:05:44] AI review pattern. So, think about it uh
[00:05:48] for 40 or 60 seconds. Okay, the correct
[00:05:54] answer is actually A.
[00:05:56] This is There is actually confirmation
[00:05:59] bias at machine speed
[00:06:01] because the same session that wrote the
[00:06:04] code already has a position.
[00:06:08] When you ask it to review the code, it
[00:06:09] will really your code or Gemini or
[00:06:12] whatever tool you are using, it will
[00:06:14] rationalize
[00:06:15] and
[00:06:16] this is not actually an honest review.
[00:06:19] A fresh sub-agent with zero context or
[00:06:23] agent with zero context at how the code
[00:06:25] was produced is more honest reviewer in
[00:06:29] this case. And this is structural It's
[00:06:32] structural, not optional, and a very
[00:06:35] important building block
[00:06:38] for your AI leverage system.
[00:06:41] The second quiz says, "You build a loop.
[00:06:45] Which combination makes it compound over
[00:06:48] time instead of restarting from scratch
[00:06:52] every single single run?"
[00:06:55] Option A, autonomous work trees and
[00:06:58] sub-agent. You will leverage those three
[00:07:01] concepts. All five blocks. Each option
[00:07:05] B.
[00:07:06] The sixth is optional.
[00:07:09] I will explain what are the five blocks
[00:07:11] and the sixth
[00:07:12] block that many miss or skip later. And
[00:07:18] option C,
[00:07:19] you will leverage skills plus MCP
[00:07:22] plugins plus sub-agents.
[00:07:25] And all five
[00:07:27] Option D actually says all five blocks
[00:07:31] plus you need to leverage persistent
[00:07:34] memory.
[00:07:35] Think about it for a few seconds before
[00:07:37] revealing the correct answer.
[00:07:39] So, time's up. The correct answer is
[00:07:42] actually
[00:07:44] the last one, option D.
[00:07:46] The five blocks gives you a loop.
[00:07:49] But without persistent memory, your loop
[00:07:53] will have an amnesia. It might
[00:07:55] rediscover yesterday works on every run.
[00:07:58] Every single stage tracking is
[00:08:01] non-negotiable. So, those are the five
[00:08:03] components or building blocks that I
[00:08:06] have mentioned plus one that many miss.
[00:08:08] So, they are
[00:08:10] the
[00:08:11] automations, work trees. By work trees,
[00:08:13] I mean Git work trees. You need to
[00:08:15] leverage them whenever you have multiple
[00:08:17] agents and you need also to leverage
[00:08:20] auto start using
[00:08:22] um agentic loops or loop engineering.
[00:08:26] You need also skills. You need MCP
[00:08:29] plugins and you need sub agents. So,
[00:08:32] think of this five block as an organ or
[00:08:36] the organs of a living system. If you
[00:08:38] leverage all the five plus the state
[00:08:41] file, you will have a loop or a
[00:08:43] well-designed loop.
[00:08:46] And the difference between leveraging
[00:08:48] the
[00:08:48] the sixth block
[00:08:51] and not leveraging it is actually
[00:08:54] matters a lot. The one that I keep
[00:08:56] coming back to is sub agents. This one
[00:09:00] actually, when a model writes code and
[00:09:03] then reviews its own code in the same
[00:09:06] context window, it already has a
[00:09:09] position. It will be biased. It will
[00:09:12] rationalize and it will not review. So,
[00:09:15] you need a separate agent or sub agent
[00:09:18] with zero knowledge
[00:09:20] of how the code was produced.
[00:09:23] And this is not a nice-to-have. It's
[00:09:24] actually a structural safety
[00:09:26] requirement.
[00:09:28] And
[00:09:29] in addition to that, you need persistent
[00:09:33] memory. Because without persistent
[00:09:35] memory, which is the sixth block,
[00:09:38] agent have amnesia. Every run starts
[00:09:41] with the fresh context.
[00:09:44] And without state file,
[00:09:47] your expensive loop rediscovers a stale
[00:09:50] work or yesterday works and tries to do
[00:09:53] it again.
[00:09:54] And this is not optimized. It's not
[00:09:57] actually what you want. This is not
[00:10:00] compounding.
[00:10:01] This is spinning.
[00:10:03] So, the state file is what makes the
[00:10:05] loop get smarter over time rather than
[00:10:08] just louder. And those are the tools
[00:10:11] that makes it here. You might be asking
[00:10:14] how can I uh
[00:10:15] create a loop or what do I need in order
[00:10:18] to create a loop?
[00:10:21] Here we have
[00:10:23] uh Claude code actions.
[00:10:26] It's actually uh
[00:10:29] is the actual GitHub action.
[00:10:31] GitHub used uh the auto triage example,
[00:10:36] the one with uh 62% token
[00:10:40] saving across 109 production runs.
[00:10:44] You can fork what the GitHub has
[00:10:47] published.
[00:10:49] And maybe you can try uh to start using
[00:10:52] it.
[00:10:53] Uh then we have uh GitHub MCP server.
[00:10:58] It's GitHub's own official MCP server.
[00:11:01] It
[00:11:03] uh has OAuth authentication, no API key
[00:11:06] to manage, covers issues, pull requests,
[00:11:10] code search, and actions.
[00:11:13] Then we have Agent X keys.
[00:11:16] It's actually uh the open standard. That
[00:11:19] means
[00:11:20] a skill you write to Claude for Claude
[00:11:24] code also works in Cursor, in Gemini
[00:11:27] CLI, in GitHub Copilot, and in other
[00:11:30] platforms.
[00:11:32] You can write the skill once and run it
[00:11:35] everywhere.
[00:11:37] Then we have Pulse MCP.
[00:11:40] You can check it. You can check maybe
[00:11:42] their website.
[00:11:44] pulsemcp.com
[00:11:46] or pulsemcp.com/server.
[00:11:49] It's actually the place to go when you
[00:11:52] ask things like, "Is there an MCP server
[00:11:55] for X?"
[00:11:56] They already have over 18,000 servers.
[00:12:05] Okay.
[00:12:11] And
[00:12:12] here we have the concrete on this slide.
[00:12:15] We have a concrete verifiable
[00:12:19] still today button.
[00:12:22] GitHub, the platform that hosts hundreds
[00:12:25] of millions of repository, runs this
[00:12:28] loop on their own repository. Not in a
[00:12:31] demo environment and not in a blog post
[00:12:34] thought experiment. It's in production.
[00:12:38] So, let's look at the six steps they
[00:12:40] have used.
[00:12:42] They have first the trigger.
[00:12:47] The trigger is GitHub action.
[00:12:50] Then they have the context
[00:12:53] gather
[00:12:55] is two file reads.
[00:12:57] They have the classification
[00:13:01] is
[00:13:02] one LLM call.
[00:13:05] Then the label and comments and comment
[00:13:08] are two write operations.
[00:13:11] Then we have the state update.
[00:13:15] It's log entry.
[00:13:17] So, that is
[00:13:19] the entire loop of the entire loop. And
[00:13:21] the second version of this or second
[00:13:25] side of this of uh
[00:13:27] this loop story is that they have
[00:13:29] achieved
[00:13:31] 62% more token
[00:13:34] efficiency than without the optimization
[00:13:39] that they have done across 109
[00:13:43] production runs.
[00:13:48] Um
[00:13:51] So, the three optimizations in this
[00:13:53] slide
[00:13:54] are not actually GitHub-specific.
[00:13:57] They apply to every loop you will ever
[00:13:59] build.
[00:14:00] And they might feel obvious,
[00:14:03] but cost you thousands or at least
[00:14:06] hundreds of dollars before you figure it
[00:14:09] out the first time.
[00:14:12] So, first we have the MCP tool pruning.
[00:14:18] Your agent does not need 40 or
[00:14:22] or 100 tools. It probably needs just
[00:14:26] three tools.
[00:14:28] So, every tool schema sitting in your in
[00:14:30] the system prompt is tokens you are
[00:14:34] paying for and on
[00:14:36] every single API call, whether the agent
[00:14:39] uses the tool or not,
[00:14:42] it will cost you money.
[00:14:45] What GitHub did, they had 40 tools and
[00:14:48] they removed 38 tools.
[00:14:53] And that alone saved them eight to 12%
[00:14:57] on input tokens per run.
[00:15:00] And the audit So, you need to audit
[00:15:03] your tool list today,
[00:15:05] not eventually.
[00:15:07] Second, we have prefetch.
[00:15:10] So, if you know what data you need
[00:15:13] before the loop starts,
[00:15:16] fetch it before the loop starts. Give
[00:15:18] the agent the file. Do not make it call
[00:15:21] a tool for deterministic data.
[00:15:25] Or you can
[00:15:27] for example add to your prompt
[00:15:29] explicitly
[00:15:31] uh
[00:15:32] don't call any tool.
[00:15:35] This would be an instruction an
[00:15:36] instruction that you can add to your
[00:15:38] prompt to optimize
[00:15:42] how many tokens it will be consumed and
[00:15:44] how
[00:15:45] much money it will
[00:15:47] cost you running that loop of that one.
[00:15:50] So tool calls inside the reasoning loop
[00:15:53] are expensive and file reads are not.
[00:15:57] Um
[00:15:59] There is also one tip about
[00:16:03] even when you provide your tool some
[00:16:06] files or data
[00:16:07] to
[00:16:09] uh to
[00:16:09] to
[00:16:11] read or
[00:16:13] it needs to consider in the context
[00:16:16] if you need for example to copy-paste
[00:16:19] text or you wanted to
[00:16:22] to read the text, this will be you can
[00:16:25] put it in an MD file. This will cost you
[00:16:28] much less token than do than taking a
[00:16:32] screenshot and providing it to Claude or
[00:16:35] Gemini or whatever because the
[00:16:37] screenshot is image and the image
[00:16:41] in order to pass the image and extract
[00:16:43] the data from it, it will cost much more
[00:16:46] token and much more data. The same also
[00:16:48] applies for the PDF documents.
[00:16:51] If you have
[00:16:53] a text
[00:16:54] you like for example some specification
[00:16:57] or requirement of your
[00:17:00] the features of product if you deliver
[00:17:04] it to your AI as MD file, this will cost
[00:17:09] much less money than delivering it as a
[00:17:13] PDF file because PDF has header, has
[00:17:15] footer, has a lot of formatting and
[00:17:18] parsing all those datas
[00:17:21] will cost more tokens and more money.
[00:17:24] That was uh
[00:17:26] the second part, prefetch data.
[00:17:29] And the third part is model tearing.
[00:17:32] What do we mean by model tearing?
[00:17:35] Using Opus
[00:17:37] for issue classification is like using a
[00:17:40] Formula 1
[00:17:42] car to get grocery.
[00:17:44] You can actually use Haiku. Haiku
[00:17:47] handles
[00:17:48] handles classification at much less cost
[00:17:50] with no measurable quality loss
[00:17:54] for that task.
[00:17:55] GitHub proved this concept
[00:17:58] across 109 runs as I have mentioned it.
[00:18:02] So, the right
[00:18:04] right-size the model
[00:18:06] and implement these three things and you
[00:18:09] will spend less than half
[00:18:13] what you would otherwise.
[00:18:15] That is GitHub's data, not mine. So,
[00:18:18] this is the example that Adi Osmany uses
[00:18:21] to make loop engineering concrete
[00:18:24] and I find it genuinely elegant. It's a
[00:18:27] pattern that you can implement. Let's
[00:18:29] break it down. At 6:00 a.m., you can put
[00:18:33] actually an automation runs on your
[00:18:35] repository.
[00:18:36] It's not waiting for you to wake up. It
[00:18:39] will scroll through Slack. It will
[00:18:41] decide what to work on.
[00:18:44] And while you are
[00:18:46] sleeping,
[00:18:48] this might be the second part.
[00:18:51] Uh this loop
[00:18:53] will read all of yesterday continuous
[00:18:56] integration failure,
[00:18:58] all the open issues, all the recent
[00:19:01] commits,
[00:19:02] and it will
[00:19:04] uh write it.
[00:19:06] It will write also a prioritized list of
[00:19:08] things worth fixing. This is the triage,
[00:19:12] the priorities, and for each item the
[00:19:15] system of your agenda groups can open an
[00:19:19] isolated work tree for each item they
[00:19:21] find. The work tree is just actually
[00:19:23] directory on its own branch and it will
[00:19:29] delegate to the after agent to write the
[00:19:31] fix for that issue.
[00:19:34] Then a separate reviewer agent with zero
[00:19:38] context of how the fix was produced will
[00:19:41] check that fix against your test and
[00:19:45] standards and your documented
[00:19:47] institutional knowledge and so on.
[00:19:49] And if it passes
[00:19:51] a PR will be open but
[00:19:54] if it will not pass the standards and
[00:19:58] the tests it goes to a triage inbox
[00:20:02] with a real human judgment item. Not a
[00:20:06] false alarm. After this you can leverage
[00:20:08] the human
[00:20:09] judgment. This is actually the details
[00:20:12] where most people gloss over. State file
[00:20:15] records what run because the tomorrow's
[00:20:20] loop should discover actually today's
[00:20:22] work not yesterday's work.
[00:20:25] It will be aware about what was already
[00:20:28] implemented and fixed
[00:20:30] thanks to the state file.
[00:20:33] So the tomorrow's loop will continue
[00:20:35] from where
[00:20:36] today stopped.
[00:20:38] And this is what it makes it complete.
[00:20:41] Boris Cherny from
[00:20:43] Claude and Anthropic said it best, "My
[00:20:46] job is to write loops."
[00:20:49] That is the job description of a senior
[00:20:51] engineer in 2026.
[00:20:54] So next we have a quiz. Alert files. You
[00:20:59] open Claude code to triage.
[00:21:02] Teammate says
[00:21:04] "Automate the whole investigation with a
[00:21:06] loop. Do you
[00:21:09] What is your answer? So, do will you
[00:21:12] open uh
[00:21:13] a loop
[00:21:15] for the investigation, the incident
[00:21:18] investigation and troubleshooting and
[00:21:19] fix?
[00:21:21] Option A, yes, loops always beat my
[00:21:25] manual investigation.
[00:21:27] Option B, no, triage is interactive and
[00:21:31] event-driven.
[00:21:33] Or yes, use loop profiling every 30
[00:21:37] seconds.
[00:21:38] Or option D,
[00:21:40] only if the same incident happened
[00:21:43] before.
[00:21:45] So, let's take few seconds to think
[00:21:48] about it.
[00:21:50] The correct answer is actually B. So,
[00:21:53] incident triage is actually interactive
[00:21:56] and event-driven, not repeating.
[00:21:59] It's a human-driven, real-time, and the
[00:22:02] fresh
[00:22:04] uh human inter-
[00:22:05] beats stale automated context. The loop
[00:22:09] handles the prepared work only, like for
[00:22:12] example, uh log polling, commit
[00:22:15] correlation, or state file, and the
[00:22:18] human confirms or rejects hypothesis.
[00:22:23] So, slash loop is useful for one
[00:22:26] subtask, like for example, watch pods
[00:22:29] every 2 minutes,
[00:22:31] and
[00:22:32] um alert me when all of the two pods,
[00:22:36] all of the two Kubernetes uh pods are
[00:22:39] running, and uh
[00:22:41] the deployment is completed. So, this is
[00:22:44] a tight condition and a clear exit.
[00:22:48] Um
[00:22:51] Let's say that you the uh
[00:22:54] you received the notification about the
[00:22:56] incident,
[00:22:58] and then there was a discussion about it
[00:23:00] in your
[00:23:02] um
[00:23:02] in Slack, for example, or whatever other
[00:23:05] system you use
[00:23:06] for the communication.
[00:23:08] You started the investigation and after
[00:23:10] a few minutes
[00:23:13] uh you got new insights and the new
[00:23:15] message
[00:23:17] uh from how
[00:23:19] about the incident, like for example,
[00:23:23] an an uh
[00:23:25] a cron job auditor
[00:23:27] deleted
[00:23:30] that task. That's why it disappeared or
[00:23:34] uh the new info might be about
[00:23:37] which tenant
[00:23:39] was
[00:23:41] was
[00:23:42] impacted by this incident or on which
[00:23:46] browser, on which operating system, on
[00:23:49] which device, and so on. And those
[00:23:51] insights will help you to
[00:23:54] to investigate in more detail and get
[00:23:58] more accurate data about the reason
[00:24:02] uh about the reason for the incident and
[00:24:04] how to fix it.
[00:24:06] So, and this
[00:24:07] without with a loop
[00:24:10] if you are using a loop, the loop might
[00:24:12] take this stale data, this initial data,
[00:24:14] and try to troubleshoot and determine
[00:24:16] the fix and the root cause based on it.
[00:24:19] But it will omit it might omit the new
[00:24:21] data that you have received through new
[00:24:24] Slack messages or whatever. Okay, that's
[00:24:28] why
[00:24:29] you need to know when not to use a loop.
[00:24:32] An incident triage session with live
[00:24:34] Slack updates might be the wrong place
[00:24:38] for a fully automated loop. The value of
[00:24:41] a human interrupt sending a fresh update
[00:24:45] like five times is
[00:24:47] the that it broke the agent out of
[00:24:52] a potentially stale narrative before it
[00:24:55] hardened it into a wrong hypothesis.
[00:24:59] So, loop engineering does not mean
[00:25:02] removing the human from everything or
[00:25:05] from the loop. It means removing the
[00:25:08] human
[00:25:09] from the parts that are repetitive,
[00:25:12] deterministic, and slow.
[00:25:15] And context gathering is that part, but
[00:25:19] the judgment is not.
[00:25:22] So, the slash loop polling pattern, like
[00:25:25] schedule wake up every 2 minutes, is
[00:25:28] generally useful for the code watch
[00:25:32] or
[00:25:34] Kubernetes log logs watch subtask
[00:25:38] because it's a tight condition with a
[00:25:40] clear exit. There is also another case,
[00:25:44] actually, that I see it as
[00:25:47] a misfit, not the best case,
[00:25:50] to use loops. Let's say you are working
[00:25:53] on implementing new features on a legacy
[00:25:56] system and someone else is working on
[00:25:58] implementing features
[00:26:00] on a green field project.
[00:26:03] And the third one is working also on
[00:26:05] implementing features
[00:26:07] on an existing project, but it
[00:26:10] it really has high quality
[00:26:14] of
[00:26:15] implemented code, clean code. It's very
[00:26:18] well designed, very well architectured,
[00:26:21] and so on. Test coverage is optimized
[00:26:24] and so on. And regression test and so
[00:26:26] on.
[00:26:28] So, the
[00:26:29] the people who can leverage and uh
[00:26:33] are more
[00:26:35] have better chance to use loop
[00:26:37] engineering
[00:26:39] and uh get a better result from it
[00:26:43] are the one who is using on a green
[00:26:45] field project and the one who is using
[00:26:48] on a clean code project. But the one who
[00:26:51] is use he who is working on a legacy
[00:26:53] project with uh maybe chaotic code,
[00:26:58] uh spaghetti code,
[00:27:01] low quality,
[00:27:03] maybe
[00:27:04] um
[00:27:05] a lot of the logic in that project is
[00:27:08] actually in the code base in the
[00:27:10] different if else switch and so on
[00:27:13] branches, but it's not documented. The
[00:27:16] documentation might be not covering
[00:27:19] everything or might be not up to date
[00:27:21] and state.
[00:27:23] If you use Loop Engineering in this
[00:27:25] legacy project with all of its problems,
[00:27:29] it might get worse. Why? Because AI is
[00:27:32] an amplifier.
[00:27:33] Amplifier. It's not
[00:27:36] It So, it will amplify. If you have
[00:27:39] clean code, it will read your patterns
[00:27:41] in your project and create more code
[00:27:44] with those patterns.
[00:27:48] And it will also do the same for the
[00:27:50] spaghetti legacy project. It will read
[00:27:52] the chaotic project, the spaghetti code,
[00:27:55] and it will generate
[00:27:57] try it will try to follow the same
[00:27:59] patterns existing there.
[00:28:02] It will not fix it. So, AI is an
[00:28:04] amplifier,
[00:28:05] not a fixer. It will amplify good
[00:28:08] practices
[00:28:10] and also amplify bad practices in your
[00:28:12] project. So, before deciding whether to
[00:28:15] use Loop Engineering or not, you need to
[00:28:18] consider those basics and
[00:28:21] those requirements.
[00:28:24] So, this is in this slide uh
[00:28:28] This slide shows us the optimization
[00:28:30] that many has completely uh or are
[00:28:33] completely missing.
[00:28:36] We have here
[00:28:38] prompt caching.
[00:28:41] And without prompt caching, you are
[00:28:45] almost certainly paying three to five
[00:28:47] times more than you need.
[00:28:53] In a 50 run a turn session, it depends
[00:28:56] on
[00:28:58] how much do you stay in the same
[00:29:00] session? Some people stay in the same
[00:29:02] session with Claude or with Gemini for
[00:29:04] days. Let's say in a 50 turn session, 50
[00:29:09] interruptions in that same session with
[00:29:12] million token, with million input token,
[00:29:15] without caching,
[00:29:17] without using prompt caching, you pay
[00:29:20] for all 1 million at full price.
[00:29:25] That is the difference
[00:29:27] between $3
[00:29:29] and $0.30 per million token on the
[00:29:33] cached portion.
[00:29:34] So, for loops specifically
[00:29:37] your
[00:29:38] your skills
[00:29:40] five, the skills that you have
[00:29:43] on your system or on your project, your
[00:29:45] Claude skills and Gemini skills and your
[00:29:48] Claude MD, Gemini MD are also read on
[00:29:52] every iteration.
[00:29:54] That is exactly the stable repeated
[00:29:57] context caching
[00:29:59] was designed for. So, you need also to
[00:30:02] consider caching your skills and Claude
[00:30:04] MDs and the other files that contains
[00:30:07] instructions
[00:30:08] that will be read by default by your AI
[00:30:11] agent.
[00:30:13] >> [clears throat]
[00:30:15] >> Okay, now we have another quiz.
[00:30:25] So, the quiz says in a 50
[00:30:28] turn agent coding session
[00:30:32] what percentage of total cost comes from
[00:30:35] input tokens?
[00:30:40] Option A,
[00:30:41] 50% input
[00:30:44] and 50% output,
[00:30:47] so it balances out.
[00:30:50] Option B,
[00:30:51] 50% input
[00:30:54] and 70% output, the AI generates a lot.
[00:30:58] Or 60% input and 40% output,
[00:31:02] it's roughly two to one
[00:31:05] ratio ratio.
[00:31:07] And the last option, option D, says that
[00:31:11] 85%
[00:31:14] uh
[00:31:14] is input
[00:31:16] and 15% is output, so the input
[00:31:20] dominates.
[00:31:21] Let's
[00:31:22] uh think about it for a few seconds
[00:31:25] before revealing the right
[00:31:27] option.
[00:31:29] All right, so the right [clears throat]
[00:31:31] uh answer is actually option D.
[00:31:35] 85% of cost
[00:31:38] is input.
[00:31:39] The loop reads files.
[00:31:42] This is input, generates edit. This is
[00:31:45] output.
[00:31:47] It runs bash.
[00:31:50] Rereads modified files. This is input
[00:31:53] again.
[00:31:54] It verifies what is implemented and what
[00:31:57] context exists and so on and what
[00:31:59] instructions. This is input again.
[00:32:02] So the ratio is 25 to one.
[00:32:07] We have 25 to one input to output
[00:32:10] ratios.
[00:32:12] Means every cost optimization
[00:32:15] must start by reducing what feeds the
[00:32:19] context, not compression the output.
[00:32:29] So, and everyone has this question,
[00:32:32] where exactly do the tokens
[00:32:35] go?
[00:32:36] The answer is most interesting than most
[00:32:38] people expect. Actually, 85% of your
[00:32:42] session cost is input tokens.
[00:32:45] As I have said or mentioned it, it's not
[00:32:48] input.
[00:32:51] You
[00:32:52] It's not output, it's input. Your agent
[00:32:55] is not primarily a text generator,
[00:32:58] it's a text reader.
[00:33:01] Unlike what you might be expecting.
[00:33:04] Every tool call,
[00:33:06] uh result, every file read, every bash
[00:33:09] command output, every error message,
[00:33:13] all of that flows back to
[00:33:17] your AI agent or to Claude or to Gemini
[00:33:21] or GitHub Copilot or whatever or Codex
[00:33:25] as input. And
[00:33:27] in 50-turn session, the context window
[00:33:31] keeps accumulating. That's why using
[00:33:34] {slash} command in Claude, for example,
[00:33:36] is a good practice.
[00:33:38] The more turns you have in your session,
[00:33:41] the more each turn will cost.
[00:33:44] It's non-linearly
[00:33:47] a curve or chart. This is why GitHub
[00:33:51] prefetch insight
[00:33:53] in the shared
[00:33:57] uh in the insights they shared publicly
[00:34:00] is so valuable. If your loop is burning
[00:34:02] tokens to read data that is completely
[00:34:05] deterministic, data like data you should
[00:34:08] have fetched in a shell script before
[00:34:11] the agent even started,
[00:34:13] you are paying LLM in this case,
[00:34:16] you are paying LLM input prices for a
[00:34:20] file open call.
[00:34:22] That is an expensive file open call.
[00:34:25] And the number I want you to take from
[00:34:27] this slide is the 25-to-1
[00:34:30] input-to-output
[00:34:33] ratio.
[00:34:34] So, your cost optimization strategy need
[00:34:37] to start from that ratio.
[00:34:40] If input is cost driver,
[00:34:42] reduce what fits the context.
[00:34:45] Use, for example, .md files instead of
[00:34:48] PDFs. Use .md files
[00:34:52] that contains text instead instead of an
[00:34:56] image that contains just the text. Copy
[00:34:58] the text in an MD file and give it as
[00:35:01] input. The image will take
[00:35:04] and requires more tokens in order to be
[00:35:07] uh
[00:35:08] parsed and the data and to extract the
[00:35:11] data from it.
[00:35:12] So,
[00:35:14] uh it is actually that simple
[00:35:17] and that non-obvious.
[00:35:21] Okay.
[00:35:23] Next quiz.
[00:35:26] You loop. This is your loop.
[00:35:29] First, you have uh classify GitHub issue
[00:35:34] into seven labels.
[00:35:35] Second, fix complex
[00:35:38] architecture uh
[00:35:40] fix complex actual regression.
[00:35:43] And third,
[00:35:45] run overnight continuous integration
[00:35:47] triage.
[00:35:49] And the question is the question is
[00:35:53] what's the best model assignment for
[00:35:55] this loop?
[00:35:57] First option, Opus.
[00:36:00] Opus Opus. So, for the three tasks, you
[00:36:03] will assign Claude Opus
[00:36:06] because
[00:36:07] uh it's consistency over cost.
[00:36:11] Option B, you will
[00:36:13] uh assign Haiku, then Opus, then Sonnet
[00:36:18] for the batch API overnight.
[00:36:21] Or you will assign Sonnet, then Sonnet,
[00:36:25] then Sonnet for all the tasks
[00:36:27] because it's good enough as model for
[00:36:29] those tasks or you will assign Sonnet
[00:36:33] then Opus then Haiku.
[00:36:36] for the batch API overnight. Let's think
[00:36:38] about it for a few seconds before
[00:36:41] revealing the correct answer.
[00:36:44] So,
[00:36:45] the correct answer
[00:36:47] is actually option B.
[00:36:50] It's recommended to use Haiku for
[00:36:52] classification.
[00:36:54] GitHub verified this.
[00:36:56] Verified actually 109 runs, no
[00:36:59] measurable quality loss. It's three
[00:37:02] times cheaper than Sonnet.
[00:37:04] Then you can use Opus for hard
[00:37:07] architecture reasoning.
[00:37:10] It's frontier capability where it
[00:37:12] matters.
[00:37:14] And then you can use Sonnet plus batch
[00:37:18] API overnight.
[00:37:20] This is a right here.
[00:37:22] 50% off for async work.
[00:37:25] The option D
[00:37:27] puts actually Haiku for on architecture
[00:37:32] and that is the critical error.
[00:37:35] Because for architecture you need
[00:37:37] a more powerful
[00:37:39] um
[00:37:41] better model.
[00:37:43] Okay.
[00:37:45] >> [clears throat]
[00:37:46] >> So, the full pricing picture and the
[00:37:49] three levels that actually move the
[00:37:51] numbers.
[00:37:53] The table here matters less than the
[00:37:56] three levels
[00:37:57] on the right.
[00:38:00] And let me be direct about this. Many
[00:38:03] people are leaving 60 to 70% of their AI
[00:38:06] budget on the table because they are not
[00:38:09] using these three mechanisms. Prompt
[00:38:12] caching, batch API, and model selection.
[00:38:16] So, level one
[00:38:18] prompt caching.
[00:38:20] Your system prompt, your skills files,
[00:38:23] your project conventions.
[00:38:28] All those you can you can
[00:38:31] cache them.
[00:38:33] You Glue reads this on every single run.
[00:38:37] And that repeated context can be cached.
[00:38:40] Cache reads
[00:38:42] cost 10 cent per million tokens instead
[00:38:45] of $3.
[00:38:48] That is
[00:38:49] a 50 time actually uh reduction on your
[00:38:53] most repeated cost. And most teams are
[00:38:56] not using it.
[00:38:58] Level two,
[00:38:59] the [clears throat] batch API.
[00:39:01] If you Glue
[00:39:03] runs overnight continuous integration
[00:39:05] triage, it does not need a real-time
[00:39:09] response.
[00:39:12] So, batch it.
[00:39:14] It would be half price.
[00:39:16] It's same model, same quality.
[00:39:20] And you wait a few minutes instead of
[00:39:23] seconds. That seems like an obvious
[00:39:25] trade, and yet the batch API is a
[00:39:28] generally under utilized.
[00:39:32] And the level three, it's the model
[00:39:34] selection.
[00:39:36] Many people default to Opus for
[00:39:38] everything or almost for everything
[00:39:41] because it feels premium.
[00:39:44] Using Opus for issue classifications is
[00:39:47] actually not premium. It's wasteful.
[00:39:50] Haiku can handle classification at three
[00:39:53] times lower cost with no measurable
[00:39:56] quality loss. And GitHub proved this.
[00:40:00] So, use the right model
[00:40:02] to the right or for the right task.
[00:40:09] The next quiz says, so this is a
[00:40:12] scenario actually. Let's say you're
[00:40:15] CFO
[00:40:16] read strong DM
[00:40:19] $1,000
[00:40:22] day per engineer benchmark. This is
[00:40:25] actually a real story, the story about
[00:40:27] StrongDM.
[00:40:29] They use the metric
[00:40:32] uh, spending $1,000
[00:40:35] token per engineer per day
[00:40:39] as a metric to measure their
[00:40:40] productivity and their AI leverage.
[00:40:44] So, a CFO
[00:40:46] So, how
[00:40:47] uh, read the blog post from StrongDM
[00:40:50] how they recommend this
[00:40:52] minimum $1,000 tokens per day per
[00:40:56] engineer.
[00:40:57] And they want to know
[00:41:00] should we be spending that at our
[00:41:03] company?
[00:41:04] What is the most accurate answer? Should
[00:41:07] you follow the StrongDM example or not?
[00:41:11] Option A, yes,
[00:41:14] because if not, we fall we fall behind
[00:41:18] every competitor.
[00:41:20] Option B, no,
[00:41:23] because token spent never predict
[00:41:26] output.
[00:41:28] Or option C,
[00:41:30] we need to measure spent first, then set
[00:41:35] the targets.
[00:41:36] Or not yet, only rational with full DTU
[00:41:42] and full infrastructure. Let's think
[00:41:44] about it for a few seconds before
[00:41:46] revealing the correct answer. So, the
[00:41:49] the token is also a tackle
[00:41:52] or it's also about token maxing, if you
[00:41:54] have already heard about this concept.
[00:41:57] But token maxing might be also
[00:41:59] misleading, cuz people might be trying
[00:42:02] to maximize their token
[00:42:05] consumption by
[00:42:08] leveraging bad practices, like for
[00:42:10] example,
[00:42:11] not
[00:42:13] caching the prompts or by using a lot of
[00:42:16] MCP servers, by using a lot of skills, a
[00:42:20] lot of cloud plugins, and so on. This
[00:42:22] will increase your
[00:42:25] how much token you consume per day and
[00:42:28] per
[00:42:29] month, but it doesn't mean that you have
[00:42:33] produced better value.
[00:42:36] Okay.
[00:42:37] And
[00:42:38] um
[00:42:39] the correct answer to this quiz is
[00:42:42] actually the last option.
[00:42:45] Not yet, only rationalized rationalized
[00:42:49] first. So, the math is honest.
[00:42:52] If you
[00:42:54] let's say you have um
[00:42:57] 250,000
[00:43:00] a dollar
[00:43:01] per year in tokens
[00:43:04] to double a five
[00:43:06] hundred dollar
[00:43:09] uh
[00:43:10] thousand engineer,
[00:43:12] it is rational validation infrastructure
[00:43:16] because StrongDM are actually using the
[00:43:18] dark factory. And
[00:43:20] um with their agenda groups, naturally
[00:43:23] their token consumption is increased.
[00:43:26] But, if you don't have
[00:43:28] uh
[00:43:29] the right infrastructure, the right
[00:43:32] guardrails, the right or enough test
[00:43:34] coverage, enough not only unit test, not
[00:43:37] only uh
[00:43:39] um
[00:43:41] very simple test, you need also
[00:43:42] behavioral test. Would the system behave
[00:43:45] correctly? Um
[00:43:48] what will happen if
[00:43:50] Okay, this feature is working, but what
[00:43:52] will happen under load? Will it still uh
[00:43:55] work? Or
[00:43:57] what will happen in a race condition?
[00:43:59] What will happen if some system we are
[00:44:03] integrated with are down, and so on.
[00:44:05] Those are kind of uh behavioral
[00:44:07] uh
[00:44:08] uh scenarios of our system. And strong
[00:44:11] DM are using
[00:44:14] uh one of the guardrails, they are using
[00:44:16] digital twin universe, which are
[00:44:18] behavioral clones of Jira, of Okta, of
[00:44:21] Slack, and they have thousands of tests
[00:44:25] per hours
[00:44:26] that are running per hour. And without
[00:44:28] that,
[00:44:29] the high token spent will be equal to
[00:44:33] high velocity
[00:44:35] that is with unvalidated output.
[00:44:38] So, if you would like to follow
[00:44:41] uh strong DM example, you should not
[00:44:43] just take the thousand
[00:44:46] uh
[00:44:47] dollar token per day per engineer side
[00:44:51] of the story. You need to know what is
[00:44:53] the other part of the story, what are
[00:44:55] the other basic daily requirements, the
[00:44:58] guardrails that they are they are using,
[00:45:01] and so on.
[00:45:02] And
[00:45:03] uh for this wish,
[00:45:06] the option C is actually the failure
[00:45:09] mode.
[00:45:10] So, measure spend first, then set
[00:45:13] targets. This is actually the failure
[00:45:15] mode. Or in your case, you might need uh
[00:45:18] or in your team, if you are
[00:45:20] uh a tech leader or a tech manager or
[00:45:23] team manager, you need to track
[00:45:25] you might need to track cost per commit
[00:45:28] and dollar instead. So, next,
[00:45:32] we have here some metrics. If you are
[00:45:34] actually an engineering leader trying to
[00:45:36] build a budget right now,
[00:45:38] here is the math that you might need to
[00:45:41] do.
[00:45:42] So, here we have three scenarios.
[00:45:44] In the first scenario, scenario A,
[00:45:48] it is where most team are today.
[00:45:51] So, you might they might have cloud
[00:45:54] good, one session per engineer per day.
[00:45:58] It's a standard usage of few session.
[00:46:01] It's roughly
[00:46:03] to $60 per engineer per day depending on
[00:46:07] model and session length.
[00:46:09] For 50 engineer,
[00:46:11] it's 3,000
[00:46:13] to 6,000
[00:46:15] budget per month. This is
[00:46:18] where we have enabled AI tool
[00:46:21] uh baseline.
[00:46:23] There is nothing wrong about it.
[00:46:26] Just do not call it loop engineering
[00:46:30] because it's not.
[00:46:32] Then we have
[00:46:33] uh scenario B.
[00:46:35] It is where you want to go
[00:46:37] or many want to go.
[00:46:39] So, in this scenario,
[00:46:42] you might we might have five sessions
[00:46:44] per day
[00:46:45] and overnight the triage loops
[00:46:48] and prompt caching doing its job.
[00:46:52] And the raw number is
[00:46:55] 12
[00:46:56] uh sorry, $18 per engineer per day.
[00:47:00] But with 60 to 70% cash,
[00:47:04] uh
[00:47:06] we will hit the rate on repeated context
[00:47:08] and the cost will drop
[00:47:11] to uh $10
[00:47:13] or
[00:47:15] uh $11. So, for 50 engineers,
[00:47:18] $10,000
[00:47:20] to $18,000
[00:47:22] a month will be would be our budget.
[00:47:26] This is where compound leverage starts.
[00:47:30] For option C,
[00:47:33] this is the dark factory
[00:47:36] and also the strong DM
[00:47:39] use case or case study. If we are strong
[00:47:43] DM, then we have
[00:47:45] $1,000
[00:47:46] token per day per engineer
[00:47:49] as target or minimum uh
[00:47:52] uh spending.
[00:47:54] And for 50 engineers, this would be a
[00:47:57] million dollar per month.
[00:48:00] So, now here is the context nobody's
[00:48:05] puts on the headline.
[00:48:07] Strong DM actual engineering team
[00:48:10] is actually three people.
[00:48:13] They have digital twin universe. They
[00:48:16] clone their entire production
[00:48:18] environment for testing.
[00:48:20] And without that infrastructure,
[00:48:23] scenario C, which is the dark factory,
[00:48:26] it won't work correctly. It is It would
[00:48:29] be
[00:48:30] It won't be a dark factory. It would be
[00:48:32] an expensive hallucination at scale. So,
[00:48:34] my recommendation is budget for scenario
[00:48:36] B.
[00:48:38] But it depends on your case. So, this
[00:48:40] This might be a recommendation that
[00:48:42] might work for some people or some teams
[00:48:45] and won't work for others. So, budget
[00:48:47] you can you might want to budget for
[00:48:49] scenario B.
[00:48:51] Invest the first 90 days in dashing,
[00:48:56] model selection,
[00:48:57] and the state file.
[00:48:59] Then let the loop compound. Okay.
[00:49:03] So, the quiz says
[00:49:06] your velocity is increased by 40%.
[00:49:10] The Dora
[00:49:12] This is what the Dora metrics and the
[00:49:14] Dora metrics are green.
[00:49:17] The test coverage is unchanged,
[00:49:20] but the senior engineer on your team
[00:49:23] says, "I think we have a problem, but I
[00:49:26] can't prove it."
[00:49:27] What is it? What's the problem?
[00:49:30] Option A,
[00:49:32] token
[00:49:33] overspend. We have a token overspend.
[00:49:37] And loops are too expensive.
[00:49:41] Or the problem is cognitive surrender.
[00:49:45] Team stopped reasoning.
[00:49:47] Or
[00:49:49] there is a comprehension debt.
[00:49:52] Code
[00:49:53] the there is code that nobody
[00:49:55] understands
[00:49:56] or there is a verification debt.
[00:50:01] The pull requests are shipped
[00:50:04] but unreviewed.
[00:50:07] Let's think about it for a few seconds
[00:50:09] before revealing the correct answer.
[00:50:11] So, here despite the 40% increase in the
[00:50:15] velocity and the test coverage that are
[00:50:19] unchanged and so on and
[00:50:22] the good side of the story, the problem
[00:50:24] is comprehension debt. It is also uh
[00:50:27] visible to velocity and to the coverage.
[00:50:32] Anthropomorphic study
[00:50:33] uh
[00:50:35] which covered
[00:50:37] 52 engineers
[00:50:40] I assisted developers. They scored 17%
[00:50:45] lower on comprehension
[00:50:47] while output metrics looked fine.
[00:50:51] And the biggest drops over
[00:50:54] the comprehension debt will be bigger
[00:50:58] on debugging skills. The metric lies to
[00:51:01] everyone in this case.
[00:51:03] So,
[00:51:04] the costs that are invisible
[00:51:07] the loop velocity creates three
[00:51:09] compounding debts
[00:51:11] and all are invisible to current
[00:51:14] metrics.
[00:51:16] You get the bill. The velocity gains
[00:51:19] are visible.
[00:51:21] You ship maybe 10 more
[00:51:24] Jira tickets per sprint or 20 more Jira
[00:51:28] tickets per sprint.
[00:51:29] Your team is creating much more pull
[00:51:32] request or merge request per days and so
[00:51:34] on and is implementing much more
[00:51:37] features. So, this is what I we mean by
[00:51:40] the the velocity gains are visible, but
[00:51:44] what the metrics
[00:51:46] lies about are these three depths which
[00:51:49] are invisible. They compound quietly and
[00:51:53] they surface as an incident.
[00:51:56] So, first we have the comprehension
[00:51:57] depth.
[00:51:59] And Google a run a study on 52 of their
[00:52:03] own engineers. They are people who are
[00:52:06] using
[00:52:08] AI tools professionally, not casually.
[00:52:11] The AI assisted group scored 17%
[00:52:15] lower on comprehension assessment
[00:52:18] than those writing code manually.
[00:52:21] Not lower output.
[00:52:24] So, they
[00:52:25] had lower understanding and the biggest
[00:52:28] gap was in debugging.
[00:52:30] Which is the exact skill
[00:52:33] you must need at 2:00 a.m. when
[00:52:36] something breaks in production. So, the
[00:52:38] velocity went up, but the
[00:52:41] the understanding
[00:52:42] went down. The metric lied to everyone.
[00:52:46] The second depth is the verification
[00:52:49] depth. So,
[00:52:51] what keeps me actually up at night is
[00:52:54] not the code that fails test,
[00:52:56] but it is the code that passes every
[00:52:59] test, ships cleanly, and then does
[00:53:02] something unexpected 3 weeks later that
[00:53:05] nobody can explain because nobody
[00:53:08] actually read it.
[00:53:10] You are no longer in the business of
[00:53:13] securing software that the success in
[00:53:16] this case. You are securing software
[00:53:19] that acts. And that is
[00:53:21] a much
[00:53:23] a materially different threat surface.
[00:53:26] Then, the third
[00:53:29] depth is cognitive surrender. So, let me
[00:53:33] explain what I mean by that.
[00:53:35] So, it might be the most dangerous
[00:53:37] long-term risk.
[00:53:40] Academic research at the published HCI
[00:53:44] literature and found the measurable
[00:53:47] shift away from papers defending human
[00:53:50] judgment in AI systems.
[00:53:53] Down 19% in over in 1 year.
[00:53:57] A junior
[00:53:59] and the junior engineers are being
[00:54:02] bypassed by senior engineers who just
[00:54:05] use AI instead. Which means we are quite
[00:54:10] literally compressing the training path
[00:54:13] on the next generation of people who
[00:54:15] need to be senior in 3 years.
[00:54:18] So, build the loop
[00:54:20] but be deliberate about what you keep.
[00:54:23] Okay, we have covered five verified
[00:54:25] practices for teams building production
[00:54:28] loops.
[00:54:29] Five things in order.
[00:54:32] If this session gives you nothing else,
[00:54:35] implement this before you build your
[00:54:38] next loop.
[00:54:39] Cost optimization comes first.
[00:54:43] Not because money is the goal, but
[00:54:46] because loops are expensive.
[00:54:50] Uh get skilled by finance because they
[00:54:53] have time to compound.
[00:54:56] I have seen this happen actually.
[00:54:58] The loop is working. It is
[00:55:01] producing value and someone sees the
[00:55:04] bills and turns it off.
[00:55:07] Get cost structure right
[00:55:09] early.
[00:55:11] Use sub agent verification.
[00:55:14] It's last on the list
[00:55:17] here
[00:55:18] um
[00:55:20] because it feels like the most optional.
[00:55:23] It is the most essential.
[00:55:25] And
[00:55:27] any AI that reviews its own code
[00:55:32] is not reviewing it. You need to
[00:55:34] remember this. It's just confirming what
[00:55:36] it has implemented or generated.
[00:55:40] In the same context window with the same
[00:55:42] priors,
[00:55:43] it already has a position and a bias,
[00:55:47] but a fresh agent with zero context is
[00:55:50] the only honest reviewer.
[00:55:53] Actually, not 100% honest reviewer, but
[00:55:56] it's much better
[00:55:58] uh
[00:55:59] reviewer or more honest reviewer
[00:56:02] that is not nice to have having a
[00:56:05] different
[00:56:06] reviewer that is different from
[00:56:09] the code implementer
[00:56:10] or the or the code developer AI agent.
[00:56:14] This is a structural requirement for
[00:56:16] code quality at speed.
[00:56:19] If I had a pick to pick one metric from
[00:56:22] this slide to implement from day one,
[00:56:26] it would be it might be actually the
[00:56:28] cost per commit.
[00:56:31] Not the most impactful long term, but
[00:56:35] the best leading indicator.
[00:56:37] So, when that number climbs without
[00:56:40] corresponding complexity increases, your
[00:56:43] loop has drifted
[00:56:46] from signal to noise. That is your your
[00:56:49] fire alarm. And here is the most
[00:56:51] counterintuitive thing
[00:56:53] in this entire deck and I want to make
[00:56:56] sure
[00:56:58] it lands before we close. So, the
[00:57:00] engineer the engineers who are
[00:57:04] furthest ahead with agentic AI are not
[00:57:07] the ones who are delegated the most.
[00:57:11] They are the ones with the strongest
[00:57:13] existing engineering practices.
[00:57:17] They have clean code base. The AI
[00:57:19] replicates good patterns.
[00:57:22] Comprehensive tests. The loop has
[00:57:24] meaningful signals.
[00:57:26] Documented architecture.
[00:57:29] The context window is not full of
[00:57:32] ambiguity and guesswork. Yeah, I want to
[00:57:35] fix your technical debt, it will just
[00:57:38] accelerate so here is the generally good
[00:57:41] news and I mean
[00:57:43] this without irony.
[00:57:46] If your team already
[00:57:48] cares about code quality testing and
[00:57:50] documentation, the things we have always
[00:57:53] known matter
[00:57:55] and always found reason to skip.
[00:57:58] You are better positioned for a gigantic
[00:58:01] shift than teams that move and clean up
[00:58:05] later.
[00:58:07] For once in software engineering, doing
[00:58:10] it right earlier
[00:58:12] pays off immediately.
[00:58:14] AI is an amplifier. Make sure what it
[00:58:17] amplifies is worth amplifying. The loop
[00:58:20] changes the work, it does not delete you
[00:58:23] from it. That's it for today.
[00:58:26] You might need to stop prompting in some
[00:58:28] scenarios, but not in other scenarios
[00:58:31] like
[00:58:32] incident triage with
[00:58:35] uh
[00:58:36] a refreshed or open context.
[00:58:40] You can start design loops.
[00:58:42] GitHub showed us what production looks
[00:58:45] like for loop engineering and maybe dark
[00:58:48] factory. They use trigger gather
[00:58:51] classifier or classify label and logs. I
[00:58:55] also shared with you three optimization
[00:58:57] that actually compound.
[00:58:59] Like prune your tools,
[00:59:03] pre-fetch deterministic data,
[00:59:06] and right-size the model to the task
[00:59:09] that you have.
[00:59:11] This practice
[00:59:12] with this practice actually GitHub saved
[00:59:16] 62% token save
[00:59:19] tokens
[00:59:20] across 109 production runs.
[00:59:23] And when it comes to monitoring and
[00:59:25] observability, measure what matters.
[00:59:27] Don't just measure how many uh uh
[00:59:30] Jira tickets, PRs, lines of codes are
[00:59:34] generated in comparison to maybe before
[00:59:39] before
[00:59:40] leveraging AI, but also measure the
[00:59:43] comprehension depth, understanding
[00:59:45] depth,
[00:59:47] and so on.
[00:59:48] If this was useful,
[00:59:50] share it with one engineer or a friend
[00:59:52] who still just prompting and is curious
[00:59:56] about loop engineering.
[00:59:58] See you in the comments and in the next
[01:00:00] video.
[01:00:02] Take care.
