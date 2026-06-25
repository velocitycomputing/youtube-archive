---
video_id: BOXK2XFLA-E
title: "Don't build more AI agents until you watch this"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=BOXK2XFLA-E"
watched_date: 2026-06-18
watched_at: "2026-06-18T12:00:00Z"
watch_count: 1
duration_seconds: 1105
source: youtube-history-browser
added_date: 
history_label: Jun 18
history_order: 106
watched_at_precision: date-from-history-label
watched_percent: 21
estimated_watched_seconds: 232
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Vercel improved its sales agent by removing 80% of its tools, not adding more—the opposite of conventional agent-building wisdom. The speaker explains that agents improve through maintenance, not accumulation. Four key principles: (1) Models improve constantly, so harnesses that worked yesterday break when models get better; (2) Agents inherit stale data from surrounding systems—outdated wikis, changed processes, wrong dashboards—and act on it without realizing it's wrong; (3) Leading AI companies (Anthropic, OpenAI) win by continuously maintaining and evolving the "harness" (workbench) around agents rather than just shipping capability; (4) Agents are like sailboats requiring constant maintenance, not apps you launch and forget. The real maintenance problem is pruning, not building.

To maintain your agent, define your harness explicitly—the folders it reads, sources it trusts, what it can touch, what approval is needed, and what proof it must provide. Then actively maintain it by checking: Are your sources current? Are permissions still appropriate for the improved model? Is the agent's job still clear or has it drifted? Does it cite actual sources or just claim things? Does it actually save work after human review, or create new work? Delete tools and capabilities that no longer serve the job as models improve. Treat maintenance as an ongoing deletion question, not just addition.

## Transcript

[00:00:00] Vercel made its agent better by deleting
[00:00:03] 80% of its tools. You heard that right.
[00:00:05] And that sentence can sound wrong if
[00:00:07] you've been following a lot of the hype
[00:00:09] around new tools and new skills for
[00:00:10] agents. So, I want to set the record
[00:00:12] straight. The usual story we hear is
[00:00:14] that agents get better as you give them
[00:00:16] more stuff, right? More context, more
[00:00:19] memory, more tools, more integrations,
[00:00:21] more access, more autonomy. Let the
[00:00:23] agent touch the CRM, let it use Slack,
[00:00:25] let it browse the web, let it update the
[00:00:27] record. Vercel's example is a really
[00:00:30] healthy counterexample in that process.
[00:00:33] And no, it's not just about context
[00:00:35] window, which is the usual reason people
[00:00:36] dump out tools. Messages came in. Some
[00:00:38] were real leads, some were spam, some
[00:00:40] were support questions dressed up as
[00:00:42] sales questions, some came from little
[00:00:44] companies, some came from accounts that
[00:00:46] might matter to Vercel, some deserved a
[00:00:48] really quick reply, and some needed
[00:00:50] research, and some needed routing. It's
[00:00:51] the usual messy inbox. So, Vercel
[00:00:54] studied one of its best reps. They
[00:00:56] watched the workflow closely enough to
[00:00:58] turn pieces of it into an agent. I love
[00:01:00] that part. You have to study what people
[00:01:02] are already doing. What did the rep
[00:01:03] ignore? What did they answer? What made
[00:01:05] a lead real? What research happened
[00:01:07] before the reply? When was a message
[00:01:09] actually a support issue? Where did the
[00:01:11] human still need to make a judgment
[00:01:12] call? Then, they built the agent around
[00:01:14] the actual observed workflow, not the
[00:01:16] paper workflow. Again, love that. The
[00:01:19] agent filtered inbound messages, it
[00:01:21] qualified leads, it researched
[00:01:22] companies, it drafted responses, it
[00:01:24] routed support questions away from
[00:01:26] sales. A human still reviewed the work
[00:01:28] because the goal was not to let a bot
[00:01:30] roam around the company, right? The goal
[00:01:31] was to take a repeatable workflow from a
[00:01:33] strong employee and make that repeatable
[00:01:35] bit run fast. And that's already a great
[00:01:37] story. But, the more important lesson is
[00:01:39] what happened after the agent existed.
[00:01:43] The agent did not get better when the
[00:01:45] team kept piling on tools. It got better
[00:01:48] when they took away tools. And this is
[00:01:51] something that I think that a lot of
[00:01:53] folks who are excited about agents need
[00:01:55] to sit with more. And this goes for
[00:01:57] skills, too. If you've got a pile of
[00:01:58] skills in your codex or Claude, pay
[00:02:00] attention. Because most of us are
[00:02:02] building agents the opposite way in
[00:02:04] practice. We're so enthused about
[00:02:06] building, right? We start with one task
[00:02:07] and add a tool and add another tool and
[00:02:09] add a memory file and add a slack
[00:02:10] integration, add a browser, and add a
[00:02:11] CRM action, add another exception. And
[00:02:14] after a while, the agent will look super
[00:02:16] powerful and muscled up, but it's going
[00:02:18] to become harder to trust. The beginner
[00:02:20] instinct is to add. The maintenance
[00:02:22] instinct is to ask what should be
[00:02:25] removed. That is the real agent story of
[00:02:27] 2026. Not can you build an agent? Look,
[00:02:30] I've got a video on that. There's dozens
[00:02:32] of videos out there on that. Of course,
[00:02:34] you can build an agent. The harder
[00:02:35] question is whether you can keep the
[00:02:37] setup around the agent healthy as the
[00:02:39] work changes and the model evolves.
[00:02:41] People call that setup a harness. If
[00:02:43] that word feels super technical, you can
[00:02:45] call it a workbench. It's kind of the
[00:02:46] same thing. The agent is the worker, the
[00:02:48] harness is the workbench. It's what the
[00:02:50] agent reads, it's what it remembers,
[00:02:52] it's what tools it can touch, it's what
[00:02:54] it's allowed to change, it's what proof
[00:02:56] it has to bring back, it's what stops it
[00:02:58] when the work gets risky. For Salesforce
[00:03:00] agent, had a workbench or harness. It
[00:03:02] had a documented workflow from a top
[00:03:04] performer. It had tools, it had
[00:03:05] handoffs, it had human review, it had
[00:03:07] feedback, and then the team learned that
[00:03:10] part of maintaining that workbench or
[00:03:12] harness is pruning. And that is a much
[00:03:14] more important lesson than AI replaced
[00:03:17] the sales process, which is what all the
[00:03:18] headlines were about. The real lesson is
[00:03:20] that useful agents desperately need good
[00:03:24] maintenance. And I think there are four
[00:03:25] first principles here that I want to lay
[00:03:27] out that are going to be durable for
[00:03:28] 2026. The first is that agents
[00:03:31] themselves are moving. The model
[00:03:33] underneath the agent is not stable. It's
[00:03:36] getting better, it's getting better at
[00:03:38] tool use, it's better at reasoning
[00:03:39] across steps, it's better at
[00:03:41] understanding messy instructions, it's
[00:03:42] better at reading files, it's better at
[00:03:44] remembering what matters, it's better at
[00:03:46] moving through work without needing
[00:03:47] every step spelled out. So, agents get
[00:03:50] better, and that sounds purely good. And
[00:03:52] mostly it is, but it also means
[00:03:54] yesterday's harness can become very
[00:03:56] wrong very quickly at the price of an
[00:03:58] update. A tool that helped a weaker
[00:04:00] model can confuse a stronger one. A A
[00:04:03] rule that protected you from an
[00:04:04] unreliable model's mistakes can trap a
[00:04:08] better model. A workflow that forced
[00:04:10] structure around a clumsy agent can
[00:04:12] become a drag when the model can handle
[00:04:14] a lot more of the work itself. These are
[00:04:16] all real examples. We are used to
[00:04:18] software breaking when it gets worse.
[00:04:20] That's our mental model.
[00:04:22] Agents can also break when the model
[00:04:25] gets better and that is a different and
[00:04:27] new thing. It's a strange new
[00:04:29] maintenance problem. Imagine the first
[00:04:31] version of an agent is not very
[00:04:33] reliable. It overreaches. It invents
[00:04:35] patterns. It treats one example like a
[00:04:37] trend. So you build a really careful
[00:04:39] harness around it. You give it strict
[00:04:40] tools and narrow the prompt and say only
[00:04:42] use these sources. Don't infer. Don't
[00:04:44] create records. Don't recommend a next
[00:04:46] step. Just summarize what you see. And
[00:04:48] that may be exactly right for that
[00:04:49] model.
[00:04:51] the model improves. Again, real examples
[00:04:53] here. Now it can compare sources better.
[00:04:56] It can understand the workflow better.
[00:04:57] It can tell the difference between a
[00:04:59] weak signal and a real pattern. It can
[00:05:00] draft a useful next step. I am
[00:05:02] describing November to March of this
[00:05:04] past 6 or 8 months. But your harness
[00:05:07] still treats it like the old model. So
[00:05:09] the agent is underused or the opposite
[00:05:11] happens, right? The old model was clumsy
[00:05:13] so you give it broad access because you
[00:05:15] knew a human would catch everything.
[00:05:17] Then the model gets better. Now it can
[00:05:19] take 20 plausible actions in a few
[00:05:21] minutes. Now they look real. They look
[00:05:22] organized. They create work that a human
[00:05:24] has to unwind. So the model improved,
[00:05:27] the harness did not and that is a
[00:05:30] massive driver of agent breakage in
[00:05:32] 2026. Normal systems drift. Prompts
[00:05:35] drift. Wiki's get stale. Dashboards
[00:05:37] break. Automations keep running long
[00:05:39] after the process changes. SOPs describe
[00:05:41] how the company worked months ago. Slack
[00:05:43] channels become junk drawers. Templates
[00:05:45] survive long after the reason for the
[00:05:47] template disappeared. None of that
[00:05:48] started with AI, right? Every company
[00:05:50] already has this problem. The product
[00:05:52] wiki, it's a little or a lot wrong. The
[00:05:54] CRM field means something slightly
[00:05:56] different than it used to. The
[00:05:57] dashboard, it still says activation, but
[00:06:00] the team changed what activation means.
[00:06:02] The support tags have evolved. The road
[00:06:04] map moved, the owner changed, the
[00:06:05] process changed, the docs didn't. With
[00:06:07] normal software, this is vaguely
[00:06:08] annoying and you sometimes get messages
[00:06:10] saying, "Please update your wiki." With
[00:06:12] agents, it's very dangerous because
[00:06:14] agents don't sit. They produce work.
[00:06:16] They're proactive. That's their job.
[00:06:18] They summarize, they recommend, they
[00:06:19] draft, they route, they update, and
[00:06:21] sometimes, of course, they act. That's
[00:06:23] the value. So, a stale wiki that is
[00:06:26] annoying to you is incredibly dangerous
[00:06:30] to an agent because it doesn't know that
[00:06:32] and it just keeps on working. And this
[00:06:35] is the second principle I want to
[00:06:36] communicate. Agents inherit all of the
[00:06:39] crud of the systems around them. If your
[00:06:41] wiki is stale, your agent reads and
[00:06:44] ingests stale truth. If your process
[00:06:47] changed, your agent will follow old
[00:06:49] process unless you update your docs. If
[00:06:52] your prompt is written for last
[00:06:53] quarter's company and model, that agent
[00:06:55] may keep serving last quarter's company
[00:06:57] and not realize everything's changed.
[00:07:00] If your dashboard definition is
[00:07:01] incorrect now, the agent will make the
[00:07:03] wrong number feel very convincing. This
[00:07:06] is not a model failure in the simple
[00:07:08] sense, right? The agent did its job.
[00:07:10] It's the old maintenance problem with a
[00:07:12] machine that now can produce work from
[00:07:15] that mess that is sometimes very
[00:07:16] convincing. And this is why Stewart
[00:07:18] Brand's Maintenance of Everything, I
[00:07:21] think it's the right frame for agents.
[00:07:23] Brand is writing about sailboats and
[00:07:24] vehicles and weapons and manuals and
[00:07:27] corrosion and the work that keeps
[00:07:28] important systems alive after the launch
[00:07:31] moment is over. Agents are a lot less
[00:07:33] like apps and more like sailboats. I
[00:07:34] love this book. This is like one of my
[00:07:36] favorite books of the year. You don't
[00:07:38] just launch agents and walk away. The
[00:07:40] weather changes, the lines loosen, salt
[00:07:42] gets into everything, and yes, this is
[00:07:44] all from that book. The same setup that
[00:07:46] worked yesterday can be wrong tomorrow.
[00:07:48] A sailboat is not maintained because it
[00:07:51] was badly designed, it is maintained
[00:07:53] because it lives in motion. Agents live
[00:07:56] in motion, too.
[00:07:57] The model changes inside them. The world
[00:08:00] changes around them. In that sense, they
[00:08:03] are much more like traditional vehicle
[00:08:05] maintenance than anything else we've
[00:08:06] seen in software in a long time. The
[00:08:08] harness has to keep up with the model
[00:08:11] changes and the world changes.
[00:08:14] And so few of us really have a good
[00:08:16] system for that. Now, the third
[00:08:17] principle I want to call out is that the
[00:08:19] biggest AI companies already know this.
[00:08:22] A lot of the implicit bet from the
[00:08:23] frontier labs and platform companies is
[00:08:26] not just that their models will get
[00:08:27] better. It is that they can use those
[00:08:29] better models to ship and evolve the
[00:08:31] harness faster. And I think that's one
[00:08:33] reason why it's really important to talk
[00:08:35] about Codex in the strategic context of
[00:08:38] OpenAI's long-term strategy. And I think
[00:08:40] that's one reason Codex matters so much.
[00:08:42] Codex is strong not just because the
[00:08:45] model is strong. Codex is strong because
[00:08:48] OpenAI keeps maintaining the harness
[00:08:50] around the model so it feels intuitive
[00:08:53] and native as the model and the world
[00:08:55] evolve around it. It has become closer
[00:08:57] to an operating surface for work as it's
[00:08:59] evolved. So, it has a terminal and a
[00:09:01] desktop app and an IDE and a browser and
[00:09:04] computer use and files and plugins and
[00:09:06] memory and automations and approvals and
[00:09:08] sandboxing and network controls and
[00:09:10] keychain storage and manage configs and
[00:09:12] logs.
[00:09:13] This is way beyond a chat box with a
[00:09:15] smarter brain. It's a very carefully
[00:09:17] maintained workbench around machine
[00:09:20] work. And the Claude code team is doing
[00:09:22] the same thing, right? They're investing
[00:09:24] heavily in their harness. I'm really
[00:09:26] excited to do the Claude code is as
[00:09:28] amazing as Codex review, guys. So,
[00:09:30] please give me something that cool. And
[00:09:33] to go back to the workbench analogy,
[00:09:34] every tool in that workbench is
[00:09:36] carefully chosen with Codex, right? The
[00:09:38] terminal matters because real work lives
[00:09:40] in commands and repos and files and
[00:09:42] tests and local tools. This was Clyde
[00:09:44] Code's original insight, by the way. The
[00:09:46] browser matters because real work
[00:09:48] happens on interfaces that humans see.
[00:09:51] And both Anthropic and OpenAI are
[00:09:53] building that way. Computer use matters
[00:09:55] because not every tool has a clean API.
[00:09:57] Plugins matter because work lives in a
[00:10:00] bunch of other systems: GitHub, Google
[00:10:02] Drive, Jira, Slack, etc. Memory matters
[00:10:05] because preferences and corrections
[00:10:07] should not have to be rebuilt every day,
[00:10:09] right? Approvals and sandboxing matter
[00:10:12] because a capable agent still needs
[00:10:13] boundaries. Logs matter because when an
[00:10:15] agent does something weird, someone
[00:10:17] needs to know what happened. This whole
[00:10:18] surface together is the harness. It's an
[00:10:21] art to build a good harness. And there
[00:10:23] are really two teams in the world
[00:10:25] building good harnesses: the Anthropic
[00:10:26] team and the OpenAI team right now. And
[00:10:28] this is where the hyperscaler and
[00:10:30] frontier platform bet gets super
[00:10:31] interesting. If the model can help you
[00:10:33] ship the harness and test the harness
[00:10:35] and refactor the harness and observe the
[00:10:37] harness and train the harness, then
[00:10:39] capability gain is going to start to
[00:10:40] compound real fast. Because better
[00:10:42] agents can help build more effective
[00:10:44] harnesses, better harnesses can make the
[00:10:46] agents more useful, and then better
[00:10:48] agents can help rebuild that harness
[00:10:50] once more. That is why the Vercel story
[00:10:52] is not just a quirky sales automation
[00:10:55] story. It's a pattern we all need to
[00:10:56] learn from. The companies that win are
[00:10:58] not the ones that build the perfect
[00:11:00] wrapper once. They're the ones that keep
[00:11:03] rebuilding the wrapper as the model and
[00:11:05] the work change. They rebuild that
[00:11:06] workshop. They rebuild that harness. And
[00:11:08] this is why the direction of Codex over
[00:11:11] time feels really significant to me. If
[00:11:13] Codex keeps getting more capable, and
[00:11:14] that's an if,
[00:11:16] and the Codex harness keeps getting
[00:11:18] closer to the operating system of work,
[00:11:19] another if, then OpenAI is not only
[00:11:22] selling intelligence, they are selling
[00:11:24] the environment in which intelligence
[00:11:26] becomes useful. And that's the same bet
[00:11:27] Anthropic is making with Clyde Code and
[00:11:29] Clyde Co-work. The harness evolves, the
[00:11:31] model evolves, the harness lets the
[00:11:33] model touch more real work over time.
[00:11:36] More real work creates more pressure to
[00:11:38] improve the harness, and that loop is
[00:11:40] ignited like a flywheel. And that loop
[00:11:42] matters, and it raises the bar for all
[00:11:44] of the rest of us. Because if you're
[00:11:46] building your own agent setup, you are
[00:11:48] now not just choosing a model, you're
[00:11:50] choosing how much harness maintenance
[00:11:53] you are choosing to own versus how much
[00:11:55] harness maintenance you're outsourcing.
[00:11:57] A light custom harness might be a clean
[00:11:59] set of instructions and memory and
[00:12:01] source folders and repeatable methods
[00:12:03] around Codex or Quad. That can be
[00:12:05] enough.
[00:12:06] Here are the sources. Here's the job.
[00:12:08] Here's what you can't touch. Here's the
[00:12:09] proof I need. Here's when a human
[00:12:12] decides. A deeper custom harness is a
[00:12:15] very different thing. Because now you
[00:12:17] have a data feed, a review screen,
[00:12:19] permission levels, logs, model choice,
[00:12:21] escalation paths, approval rules, and a
[00:12:24] plan for what happens when the model
[00:12:25] changes. And that can be very worth it
[00:12:27] to invest in, but now you're not just
[00:12:30] building an agent. You are investing in
[00:12:33] the long-term maintenance of an agent
[00:12:36] and harness system. You are taking
[00:12:38] responsibility for evolving the system
[00:12:41] around the agent over time. And the more
[00:12:43] custom the harness, the more you own the
[00:12:46] upkeep. And this is not abstract for me.
[00:12:49] So now I'm thinking about my delegation
[00:12:50] model differently, and part of it is
[00:12:52] just the ordinary mess of work, right?
[00:12:53] Folders move, drafts change, source
[00:12:55] packets get updated, memory gets stale,
[00:12:57] and the way I want the agent to use
[00:12:58] local context changes as the agent gets
[00:13:01] better. So the thing I maintain is a lot
[00:13:03] more than a prompt. It's It's the whole
[00:13:05] way the agent meets my files.
[00:13:07] Where should it look first? Which
[00:13:08] folders are a source of truth? What
[00:13:09] should it ignore? What should it ask
[00:13:11] about before touching? What should it
[00:13:12] remember? What should it forget? When it
[00:13:14] searches memory,
[00:13:16] is that right? When does it actually go
[00:13:18] read the file? That is a harness
[00:13:20] question for me. And that's a tiny
[00:13:22] personal harness question, right? I'm
[00:13:23] not even talking about team harnesses
[00:13:25] here. And it has changed because the
[00:13:27] agents have changed, because the models
[00:13:29] have updated. And
[00:13:31] this brings me
[00:13:32] to the fourth principle, and it's the
[00:13:34] one that I think matters the most. You
[00:13:36] need to ask, I think all of us need to
[00:13:38] ask, what is my harness? What is my
[00:13:41] workshop? Not in a sort of technical way
[00:13:44] that makes it feel scary, but in a very
[00:13:46] practical way. If you use chat GPT or
[00:13:49] Claude or or CodeX or any other agentic
[00:13:51] tool, your harness is the setup that
[00:13:53] makes that model useful for your real
[00:13:55] work. Maybe it's project folders, maybe
[00:13:57] it's your memory, your prompts, your
[00:13:58] source docs, your approval habits, your
[00:14:01] browser access, your file rules, your
[00:14:03] tools, your verification loop, your way
[00:14:06] of asking for proof, your habit of
[00:14:08] making the agent read the actual source
[00:14:11] instead of guessing from context. If
[00:14:13] you're a product leader, your harness
[00:14:14] might be the sources your agent reads
[00:14:16] before planning, right? If you're in
[00:14:17] sales, your harness might be the CRM
[00:14:19] fields or the call notes or the routing
[00:14:21] rules and and the human approval steps.
[00:14:23] Maybe you're in support, right? Your
[00:14:24] harness might be the policy store and
[00:14:27] escalation paths and refund rules. If
[00:14:29] you're a writer, your harness might be
[00:14:31] your drafts and your transcripts and
[00:14:33] your voice notes and your editorial
[00:14:34] rules and your archive and the
[00:14:36] instruction that the agent has to show
[00:14:38] where an idea came from.
[00:14:40] If you're an engineer, of course, your
[00:14:41] harness would be a repo, test, terminal,
[00:14:43] permissions, work trees, logs, review
[00:14:45] rules. That in many ways is the most
[00:14:47] mature example of a harness we have
[00:14:49] today. But that's the real question for
[00:14:51] all of us, whether we're engineers or
[00:14:52] not. What is your harness? What are you
[00:14:54] doing to ship it? What are you doing to
[00:14:56] rebuild it? Do you know when to rebuild
[00:14:58] it? Do you know how to rebuild it? What
[00:15:00] are you doing to evolve it as the models
[00:15:03] improve? The more useful question is
[00:15:07] can I maintain this sailboat over a
[00:15:09] voyage? What harness does this agent
[00:15:12] need? Those are the same question. And
[00:15:13] then the really mature question is
[00:15:16] what part of this harness will I need to
[00:15:18] delete later? And and Brand gets into
[00:15:20] this, he talks about simplicity as a key
[00:15:22] to maintenance, and I love that. This is
[00:15:23] the Vercel lesson. The agent got better
[00:15:26] when the workbench got cleaned up. And
[00:15:28] once you start to realize that your your
[00:15:31] maintenance question is not just a
[00:15:34] modification question, but potentially a
[00:15:37] deletion question, the whole agent
[00:15:39] conversation becomes a lot more complex.
[00:15:41] You stop treating the harness as a
[00:15:43] one-time wrapper, you treat it as a
[00:15:45] living system where you do have to add
[00:15:46] sometimes, and you do have to take away.
[00:15:49] You have to think about the system's
[00:15:50] health overall. So, for any serious
[00:15:52] agent, I would check these five things.
[00:15:54] First, what's it eating, right? What's
[00:15:56] it reading? Are the sources current? Did
[00:15:58] the workflow move? Did a new source
[00:15:59] become important? Did an old source
[00:16:01] become misleading?
[00:16:02] Second, I would test its reach. What can
[00:16:05] it touch? Can it only read? Can it
[00:16:07] draft? Can it create tickets? Can it
[00:16:08] post in Slack? Can it update records?
[00:16:10] Can it spend money? Can it publish? A
[00:16:12] permission that was harmless for a
[00:16:14] weaker model may be too broad for a
[00:16:15] strong one. A restriction that made
[00:16:17] sense for an unreliable model may hold
[00:16:19] back a better one. Third, I would check
[00:16:21] its job. Is this still a summary agent?
[00:16:24] Is that useful? Is it becoming a
[00:16:25] planning agent because agents are
[00:16:27] getting better and it can be? Is it
[00:16:28] supposed to find themes? Is it supposed
[00:16:31] to recommend tradeoffs? Is it supposed
[00:16:33] to route work? Do not let the job change
[00:16:36] silently. Change the job on purpose if
[00:16:39] you're going to do it at all. Fourth,
[00:16:41] check the proof. The agent shouldn't
[00:16:44] just say, "Customers are frustrated with
[00:16:46] onboarding." It needs to link to the
[00:16:48] tickets. It should link to sales notes.
[00:16:50] It should quote customer language and
[00:16:52] have a source.
[00:16:54] And it should say which sources it
[00:16:55] checked and where, and which ones it
[00:16:57] could not access. So, the proof is not
[00:17:00] just the agent saying it. The proof is
[00:17:02] an a linkable trail a human can inspect.
[00:17:05] Fifth and last, check the agent's value.
[00:17:09] I don't think this gets done enough.
[00:17:10] It's like asking if the sailboat got
[00:17:12] there, right? Does anyone read the
[00:17:13] output? Does it change the work? Does it
[00:17:15] save time after review? Does it create
[00:17:17] another pile of work? Is it duplicating
[00:17:19] a report? Has the model improved enough
[00:17:21] that the agent ought to be rebuilt? Has
[00:17:23] the business changed enough that the
[00:17:24] agent should be retired? That can
[00:17:26] happen. Agents, unlike almost anything
[00:17:28] else, break in two directions. They
[00:17:31] break because the world around them
[00:17:33] drifts, and they break because the model
[00:17:35] inside them improves. And maintenance is
[00:17:38] the work of keeping the harness fit
[00:17:40] between those two moving things. That
[00:17:42] delicate art, that sailing art, is the
[00:17:45] future of agents. It's not just more
[00:17:46] capability, it's better maintained
[00:17:48] capability. The work changes around the
[00:17:50] agent, the model changes inside it. And
[00:17:52] if you ignore either of those, the agent
[00:17:54] does not have to fail very loudly to
[00:17:57] become quite dangerous. All the agent
[00:17:59] has to do is to keep working, and it
[00:18:01] will start to haunt your business. And
[00:18:03] before I forget, yes, I'm going to say
[00:18:04] it again, read the Maintenance of
[00:18:06] Everything. If I could recommend one
[00:18:08] book on agents that isn't about AI, I
[00:18:10] would recommend this one. It's a
[00:18:12] phenomenal book. It's out of Stripe
[00:18:13] Press. I love what Stripe Press is
[00:18:15] doing. Thank you, guys. It's by Stewart
[00:18:17] Brand. Go get it and read it. It will
[00:18:19] teach you a lot about how to think about
[00:18:21] the maintenance of technical systems.
[00:18:23] Have fun. I'll see you next time.
