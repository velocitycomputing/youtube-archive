---
video_id: R2-Y1Hjwx2U
title: Stop Coding. Start Steering. Claude vs Codex
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=R2-Y1Hjwx2U"
watched_date: 2026-06-10
watched_at: "2026-06-10T15:00:12Z"
watch_count: 1
duration_seconds: 973
source: youtube-history-browser
added_date: 
history_label: Today
history_order: 3
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 973
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Claude Code and Codex represent two different philosophies for working with AI agents. Claude Code feels like "steering"—you stay close to the model, have conversations about fuzzy problems, and maintain tight control through plan mode, hooks, and iterative feedback. Codex feels like "dispatching"—you write clear assignments, run tasks in parallel across separate threads, verify results through receipts and proof (diffs, logs, artifacts), and hand off well-defined work. The speaker emphasizes the core difference isn't which model is smarter, but that each interface trains different mental habits: Claude rewards thoughtful iteration when the problem itself is unclear, while Codex rewards delegating clear jobs and inspecting what comes back.

Use Claude when taste, design judgment, architecture decisions, or defining the actual question are the hard parts—bring half-formed problems and workshop them together. Use Codex when you can write the work down as a clear assignment with identifiable sources, files, and success criteria—especially when parallelism matters or you want to turn repeated work into durable workflows. For high-stakes work, use both: let one model plan while another reviews, or have one implement while another inspects against standards. The actionable skill being developed across both is "agent loop management"—knowing when to steer versus delegate, and most critically, being the human who decides what proof counts, what good means, and when the output is actually ready to leave the machine.

## Transcript

[00:00:00] Everyone is asking whether claude code
[00:00:01] or codeex is better. I I literally get
[00:00:03] this question. Nate, you talk about
[00:00:05] codec. Does it mean you don't like
[00:00:06] claude code? Nate, what do you think
[00:00:08] about cla code? Can I do this in claude
[00:00:09] or codeex? Those are the wrong
[00:00:12] questions. The better question is, what
[00:00:13] does each tool make you better at doing
[00:00:15] with agents? Because the skill of 2026
[00:00:18] is agent literacy. And I'm going to give
[00:00:20] you a short hand at the top here. I
[00:00:21] think Claude makes steering agents feel
[00:00:23] very, very natural and codeex makes
[00:00:25] dispatching agents feel very, very
[00:00:27] natural. We're going to get into those
[00:00:28] differences in this video. That
[00:00:30] difference may matter more than which
[00:00:32] model wins a benchmark this month
[00:00:34] because it teaches you a habit. Look,
[00:00:36] this is like the Mac versus Windows
[00:00:38] fight of the agent age. Not because
[00:00:39] Claude is Mac and Codeex is Windows or
[00:00:41] the other way around. That's too cute.
[00:00:43] The point is that interfaces train
[00:00:45] behavior. Mac and Windows did not just
[00:00:48] compete on features. They actually
[00:00:49] taught people what a computer was for,
[00:00:52] where work lived, how files moved, how
[00:00:54] much the machine should hide or show,
[00:00:56] how much control the user ought to have.
[00:00:58] So Claude and Codex are doing that now
[00:01:01] for agents. They are teaching us what an
[00:01:04] agent is for. And that is why this
[00:01:06] matters even if you don't write code.
[00:01:08] The names make this sound like a
[00:01:09] developer fight, right? And a lot of
[00:01:11] developers use these tools. So claude
[00:01:12] code, codecs, work trees, hooks,
[00:01:14] sandboxes, diffs. You hear these words
[00:01:16] and you're like, what are they? And I
[00:01:18] get why people are like, "These tools
[00:01:20] are not for me." But I think that this
[00:01:22] is one of the first AI debates that
[00:01:24] non-technical people should force
[00:01:26] themselves into the room and say, "No,
[00:01:27] we deserve to understand this." Because
[00:01:29] coding agents are where agent habits we
[00:01:32] all will use are showing up first. A
[00:01:35] chatbot answers and an agent takes a
[00:01:37] job. Right? That's the simplest
[00:01:39] distinction. That latter piece, the
[00:01:41] agent taking the job. That's the piece
[00:01:42] we have to get fluent at directing. And
[00:01:45] so you have to be able to say, "Here's a
[00:01:47] folder. Here's a goal. Here's what done
[00:01:49] means to your agent, and here's what
[00:01:50] you're allowed to touch." And the agent
[00:01:52] will then read files and call tools and
[00:01:54] open pages and run commands and edit
[00:01:56] drafts and check what happened and come
[00:01:58] back with something you can check. That
[00:02:01] showed up first in coding because code
[00:02:03] has proof that of what good looks like
[00:02:06] built into it. Does the code run or does
[00:02:08] it not? Most knowledge work was not that
[00:02:11] easy. And so that's why all of these
[00:02:13] tools showed up as coding tools first
[00:02:15] and now knowledge work is coming up
[00:02:16] because these agents are getting better
[00:02:18] and that's why claude versus codeex and
[00:02:21] understanding their different approaches
[00:02:22] to agents matter. Now so the coding
[00:02:25] world is giving us the vocabulary that
[00:02:27] both of these tools run on and I want to
[00:02:29] translate that very very quickly. Once
[00:02:31] you translate terms like this this
[00:02:34] entire tool set becomes way less
[00:02:36] intimidating. These are just the parts
[00:02:38] of a serious assignment, right? You need
[00:02:40] to have context and permissions and
[00:02:42] tools and checkpoints and helpers and
[00:02:44] proof if you're doing real work. Now,
[00:02:46] the Claude versus Codex question gets
[00:02:48] really interesting. Claude code feels
[00:02:50] like a cockpit that you're flying,
[00:02:52] right? In an airplane. You're close to
[00:02:54] the model. You're steering the model.
[00:02:55] You're talking through the work while it
[00:02:57] happens. You can ask it to read the
[00:02:58] codebase or the source folder and tell
[00:03:00] you what is going on. You can ask it to
[00:03:02] interview you before writing the spec.
[00:03:04] You can stop it. You can correct it. You
[00:03:06] can make it rethink the plan. You can
[00:03:08] keep the work really close. And that
[00:03:10] feels like a real advantage when the
[00:03:12] work is fuzzy. You want Claude to be
[00:03:14] close to you, right? This is the
[00:03:15] experience I've had with Claude co-work.
[00:03:17] It's the experience I've had with Claude
[00:03:18] code. Is it subjective? Yes. But a lot
[00:03:21] of folks agree with me. If the hard part
[00:03:23] is taste, if it's ambiguity, if it's
[00:03:25] design judgment where you want to get
[00:03:27] close to the problem and really wrestle
[00:03:28] with it, if it's writing, uh if it's if
[00:03:30] it's architecture or figuring out the
[00:03:32] actual question, Claude is really really
[00:03:35] good at that. the personality matters
[00:03:37] there and that that that can sound
[00:03:39] really soft but it's not. If a tool
[00:03:41] feels patient and it feels thoughtful
[00:03:42] and it feels focused on the right
[00:03:44] solution, you can bring it a halfformed
[00:03:47] version of the problem and you can bring
[00:03:49] it something you can't quite name yet
[00:03:52] and you can figure it out together.
[00:03:54] Sirius Claude code users, serious Claude
[00:03:56] co-work users are not just chatting.
[00:03:58] They use plan mode before edits. They
[00:04:00] keep a claw.markdown file which is
[00:04:02] basically a standing note that says
[00:04:04] here's how the project works. Here are
[00:04:06] the commands, here are the rules. They
[00:04:08] use hooks so that important checks run
[00:04:10] automatically. They use MCP servers to
[00:04:12] connect tools. They split work across
[00:04:14] sessions. A session can write and review
[00:04:16] and investigate and test. That's real
[00:04:18] agent work. The risk is that you're
[00:04:20] assembling a lot of the system yourself.
[00:04:22] You are managing the context window
[00:04:24] more. You are deciding when it makes
[00:04:26] sense to do a planning session. you are
[00:04:28] deciding how to handle hooks when you
[00:04:31] want to put hooks into your system to do
[00:04:33] automated reviews. You're thinking about
[00:04:35] when to invoke workflow mode, which is a
[00:04:38] brand new mode in Claw that lets the
[00:04:39] spin out sub agents. Uh, and so if
[00:04:42] you're very disciplined, that's an
[00:04:44] incredibly powerful tool because you
[00:04:45] have all of these tools lined up in
[00:04:47] front of you and you can use them to get
[00:04:49] close to the work and really drive a
[00:04:52] lengthy work session productively. But
[00:04:55] if you're not careful, the conversation
[00:04:56] can become a bit of a junk drawer. The
[00:04:58] context can fill up, which is a bigger
[00:05:00] risk with Claude right now. Codeex feels
[00:05:03] different. Codeex feels more like an
[00:05:05] operations desk. I can have one thread
[00:05:07] reading a folder, another drafting a
[00:05:09] document, another checking a package,
[00:05:11] another using the browser, another
[00:05:13] turning a repeated process into a skill,
[00:05:15] all at the same time. There's a lot more
[00:05:17] parallel compute with codecs right now
[00:05:19] because the anthropic team is still
[00:05:20] looking for compute, right? The work Q
[00:05:23] is visible with codecs. The job stays
[00:05:25] separated, the outputs are inspectable
[00:05:27] very easily, and that changes what I'm
[00:05:29] willing to hand over. With codeex, I
[00:05:31] still ask for help thinking, but much
[00:05:33] more often, I say, "Go do this piece of
[00:05:35] work. Bring back the results and show me
[00:05:37] the proof you did it." For software,
[00:05:39] that could be a diff or a test output or
[00:05:41] a PR. For knowledge work, the proof
[00:05:43] might be a source list or a rendered
[00:05:45] document or a comparison table, uh, or
[00:05:48] even just a doc that summarizes what
[00:05:50] happened. and then the source docs that
[00:05:52] show that actually that got done and
[00:05:54] that's why codeex feels a lot bigger
[00:05:56] than coding to me. Open AI started codec
[00:05:58] and software because software has very
[00:06:00] clean feedback loops and that's actually
[00:06:01] the same reason anthropic started claude
[00:06:03] code on software but the shape of work
[00:06:05] of course has gotten broader and that's
[00:06:07] why these larger conversations are
[00:06:09] needed because you can use the same
[00:06:11] workflow of assigning a task and setting
[00:06:13] a goal and using tools to do a lot of
[00:06:14] other knowledge work. Now a sandbox just
[00:06:17] means the agent has a contained place to
[00:06:19] work. It can try things without touching
[00:06:21] everything else. Uh, and it can use
[00:06:24] tools. It can use skills. It can work on
[00:06:27] work that's separated out in a work tree
[00:06:30] all without touching the rest of your
[00:06:31] machine. And this has made codeex feel
[00:06:34] really safe to use. Especially now that
[00:06:37] the auto review means that there's a
[00:06:40] separate 5.5 codeex model that checks
[00:06:42] what my execution 5.5 model wants to do
[00:06:46] in codeex and make sure it's aligned
[00:06:48] with my intent before it lets it do
[00:06:50] stuff. And that gives me context to
[00:06:52] sometimes go outside the sandbox with
[00:06:54] codeex. And going outside the sandbox
[00:06:56] means computer use as in letting codeex
[00:07:00] take control of my computer which is
[00:07:01] something that is much more flexible
[00:07:03] with codecs than with claude right now.
[00:07:05] Computer use means that Codex can see
[00:07:06] and click and type on the screen and I
[00:07:08] don't even have to be there, right?
[00:07:09] There are background automations that
[00:07:11] mean Codeex can wake up and run later
[00:07:13] and do work without me having to pay
[00:07:15] attention to it. So, this is not just a
[00:07:17] feature list when you stack all of these
[00:07:19] together. This is a way of making agent
[00:07:22] labor easy to manage. And that's why I'm
[00:07:24] loving codec so much right now. Not
[00:07:26] because Claude is weak. It's actually an
[00:07:28] incredibly strong model. 4.8 is really
[00:07:30] good. Uh Claude is one of the most
[00:07:32] important AI products in the world. than
[00:07:34] claude code has pushed the whole
[00:07:35] category forward and there's a reason so
[00:07:37] many developers use it but my bottleneck
[00:07:39] is often not can I think about the work
[00:07:41] my bottleneck is often moving the work
[00:07:43] across the computer rapidly finding the
[00:07:46] file and reading the transcript and
[00:07:47] using the source and rendering the docx
[00:07:49] and using a site and copying the file to
[00:07:51] the handoff location and verifying it
[00:07:53] exists that's not a code task it's work
[00:07:56] on the computer and codeex has made me
[00:07:59] more willing to hand that work to the
[00:08:01] machine not blindly right I don't trust
[00:08:03] the agent just because it sounds
[00:08:05] confident. I trust the receipts. I I
[00:08:07] make it show me the files. I make it
[00:08:09] show me the logs. And and that's the
[00:08:12] codec advantage. It makes the assignment
[00:08:14] design feel so natural. It makes
[00:08:16] delegation of work to agents feel so
[00:08:19] natural. But Codex has a failure mode
[00:08:21] too. A completed run can make the work
[00:08:24] feel more done than it really is. The
[00:08:26] agent will come back and it will say the
[00:08:28] task is complete. And on the surface, it
[00:08:30] has all the right signals of progress.
[00:08:32] But maybe it followed the instruction
[00:08:34] too pedantically. Maybe it optimized for
[00:08:37] completeness instead of quality. Maybe
[00:08:39] it used the wrong source. Maybe it
[00:08:40] created a pile of work that now takes
[00:08:42] longer to review than it would have
[00:08:43] taken to do the little task myself. So
[00:08:46] codeex is not perfect. And I want to be
[00:08:50] really honest about the differences and
[00:08:52] what makes them feel risky to use
[00:08:54] because they are changing the way you
[00:08:56] think about completeness and quality.
[00:08:58] So, if you're trying to learn failure
[00:08:59] modes, be careful which failure mode
[00:09:02] you're learning depending on which tool
[00:09:03] you use. Claude can seduce you with a
[00:09:06] great conversation and make you feel
[00:09:07] closer to the work than you are. Codeex
[00:09:09] can persuade you that a workflow is
[00:09:11] completed when it's really not. Both
[00:09:14] still require judgment. Both still
[00:09:16] require proof. And so, if you're trying
[00:09:18] to figure out like what to use or when
[00:09:20] to use it, let me give you a practical
[00:09:22] decision rule. Use Claude when the
[00:09:24] problem needs conversation before it can
[00:09:26] become an assignment. Use Claude when
[00:09:28] taste and ambiguity and design judgment
[00:09:31] and writing and architecture uh when the
[00:09:33] shape of the question is the hard part.
[00:09:36] Use codeex when the work can be written
[00:09:38] down and it's a job you can delegate.
[00:09:40] Use codecs when there are sources and
[00:09:41] files and tools and checks and artifacts
[00:09:43] that you can all call in. Use codecs
[00:09:45] when parallelism matters, doing two or
[00:09:47] three things at once. Use codeex when
[00:09:49] you want a repeated task to become a
[00:09:51] durable workflow instead of just one
[00:09:52] helpful exchange. And use both when the
[00:09:56] stakes are high enough, right? Let one
[00:09:57] model plan and the other critique. Let
[00:09:59] one implement and the other review. Let
[00:10:01] one agent produce the artifact and
[00:10:03] another inspect it against the standard.
[00:10:05] And then you decide. And that last part
[00:10:07] that's not just like ceremonial. That's
[00:10:10] the job. You are not disappearing in
[00:10:12] this world. You are the human that moves
[00:10:15] to the part of the work that can't be
[00:10:16] skipped. You're deciding and compiling
[00:10:19] meaning and figuring out what work
[00:10:20] should exist, what good means, what
[00:10:22] risks matter, what proof counts, and
[00:10:24] when the output is ready to leave the
[00:10:25] machine. That is why this is not just
[00:10:28] about software, right? People feel the
[00:10:30] power of these tools, but they also feel
[00:10:32] the stress of working with them.
[00:10:34] Managing agents is legitimately tiring
[00:10:37] in another way. You have to trust work
[00:10:39] you did not personally do without
[00:10:40] becoming careless. You have to stop
[00:10:42] micromanaging every step without
[00:10:44] becoming gullible. You have to let the
[00:10:46] machine run and then be ruthless about
[00:10:48] what came back. That is a new skill
[00:10:50] we're all learning. Learning when to
[00:10:52] steer. We're learning when to dispatch.
[00:10:54] We're learning when to verify. And this
[00:10:56] is the agent literacy I care about. Yes,
[00:10:59] prompting is a part of it, but prompting
[00:11:00] is far too small a word for what we're
[00:11:02] doing here. We're doing agent loop
[00:11:04] management. Now, the skill is writing
[00:11:06] assignments that come back as inspected
[00:11:08] work. And the interface war that we're
[00:11:10] talking about with Claude versus Codeex
[00:11:12] is over which product makes habits that
[00:11:15] feel natural with our workflows. Which
[00:11:17] one makes you ask better questions?
[00:11:19] Which one makes you write cleaner
[00:11:21] assignments? Which one makes permissions
[00:11:23] obvious? Which one makes it natural to
[00:11:24] run more than one agent? Which one makes
[00:11:27] proof hard to forget? These are human
[00:11:29] questions that come up because of the
[00:11:30] agent interface, right? Which one turns
[00:11:32] repeated work into a skill, a hook, an
[00:11:35] automation, a workflow? That's what I am
[00:11:37] watching right now. I don't think the
[00:11:39] honest answer is Claude wins or Codex
[00:11:42] wins. They're pulling the future in
[00:11:44] different directions and I'm keeping an
[00:11:46] eye on both. Claude is very good at
[00:11:48] keeping the agent close while the work
[00:11:50] is still becoming very very clear. Codex
[00:11:53] is really good at making agent work feel
[00:11:55] very assignable and parallel and and
[00:11:57] inspectable. The best users I know are
[00:12:00] using both. And if you're asking which
[00:12:02] one has changed my own work more, I have
[00:12:05] to be honest. It was Claude first and
[00:12:07] now it's Codeex. They both changed the
[00:12:09] way I work a lot and working with both
[00:12:11] has made me better. And right now what's
[00:12:13] special about Codeex is it made me stop
[00:12:16] thinking of AI as a place where I get
[00:12:18] help and start thinking of my computer
[00:12:20] as a place where work can be delegated
[00:12:22] and checked and packaged and continued
[00:12:24] autonomously. And that's the beginning
[00:12:26] of a new kind of computer literacy that
[00:12:29] this is how interface shifts usually
[00:12:31] feel. First they look like a niche
[00:12:33] workflow for power users. It's the
[00:12:34] people using Blackberry back in ' 07
[00:12:36] and08 and then it becomes the default
[00:12:39] way serious work gets done. Now
[00:12:40] everybody's on their phone, right? So
[00:12:42] don't reduce claude versus codeex to a
[00:12:44] coding tool debate or even to a Mac
[00:12:46] versus Windows debate. Watch what each
[00:12:48] tool makes it easier for you to imagine.
[00:12:51] Watch very carefully what each tool
[00:12:53] makes it easier for you to forget. Watch
[00:12:57] the habits it creates in you. The most
[00:12:59] important question is not which agent is
[00:13:01] smarter guys. The most important
[00:13:03] question is what work am I now capable
[00:13:06] of running and what proof would make me
[00:13:09] trust it and which of these tools helps
[00:13:12] me to do that. The thing to remember,
[00:13:14] the thing to keep in mind is that you
[00:13:17] are on the edge of the agent revolution.
[00:13:19] Now we all are. Anyone who says they've
[00:13:21] got it figured out is lying. They're
[00:13:23] lying to you. We are all figuring out
[00:13:26] together how to manage rapidly evolving
[00:13:28] agents. It's a new paradigm for
[00:13:30] computing. And I'm passionate about
[00:13:32] talking about the differences between
[00:13:33] these tools because the differences are
[00:13:37] going to shape the way we imagine with
[00:13:39] agents. It's going to be different if
[00:13:42] you're a Claude user in six months and
[00:13:43] you have mental patterns that are clawed
[00:13:45] patterns versus codecs. Do you know how
[00:13:47] I know that? I know developers who feel
[00:13:50] like they are switching interfaces and
[00:13:52] their brain hurts when they switch from
[00:13:54] one to the other because they have to
[00:13:56] think differently about how agents work.
[00:13:58] The the sandbox example is a good one.
[00:14:00] Codex runs in sandbox. Claw doesn't.
[00:14:02] That's just one example among many. So
[00:14:05] start to think about really
[00:14:06] intentionally what kind of of work feels
[00:14:11] natural to you. In in developer terms,
[00:14:13] we call this developer ergonomics,
[00:14:15] right? Like imagine being comfortable in
[00:14:17] a working space. What helps you to run
[00:14:20] agents that get work done? Is it codecs?
[00:14:24] Is it delegating the work? Is it clawed?
[00:14:26] Is it feeling close to the work and
[00:14:28] digging in and having a conversation?
[00:14:30] And these, by the way, are are
[00:14:32] summaries. If you're relying on this and
[00:14:34] you're like, "Wow, Nate says that Claude
[00:14:36] is this and and I found Claude to be
[00:14:37] that." Well, tell me in the comments,
[00:14:39] right? Like the the point is that we
[00:14:42] want to build up the knowledge together.
[00:14:44] I believe strongly in a cool kid
[00:14:46] philosophy for AI. In other words, you
[00:14:48] should be the one who gets to be the
[00:14:50] cool kid for the day by showing all of
[00:14:52] us the amazing work that you do with AI.
[00:14:55] So, if you have a trick with Claude or a
[00:14:56] trick with Codeex or a different
[00:14:58] approach to ergonomics with these, a
[00:15:00] different approach to feeling
[00:15:01] comfortable using these agents, put it
[00:15:02] in the comments. Let's talk about it.
[00:15:04] Let's learn about it together. I think
[00:15:07] it's really really important that we
[00:15:09] take the time to dig into what makes
[00:15:11] these interfaces distinct because I
[00:15:14] believe strongly that as agents get more
[00:15:16] powerful, they're shaping the way our
[00:15:18] minds work with AI. And we got to be
[00:15:21] intentional about that. We got to pick
[00:15:22] something that feels like it works for
[00:15:24] us and lets us do work that's meaningful
[00:15:26] for us. And that's that's very personal,
[00:15:29] right? It's around aligning the subject
[00:15:30] matter we work with, the outputs we're
[00:15:32] looking for, the quality of the model,
[00:15:34] the quality of the harness or tool like
[00:15:36] Claude or Codeex, and then finally, our
[00:15:38] willingness and ability to work with
[00:15:40] that tool to get the work done and our
[00:15:42] ability to feel comfortable with that.
[00:15:44] My whole goal with Claude versus Codex
[00:15:46] is to give you enough of a taste here
[00:15:49] that you can start to either be curious
[00:15:50] because you've never tried both, or that
[00:15:53] you can start to jump out of your seat
[00:15:54] and say, "Nate, I've got it. Nate,
[00:15:56] you're right. Nate, you're wrong." Well,
[00:15:57] tell me that, right? Tell me in the
[00:15:59] comments. Let's make this a learning
[00:16:00] activity. And then if you want to get
[00:16:01] started, I absolutely have very very
[00:16:04] detailed get started guides for both of
[00:16:06] these today. And of course that deep
[00:16:07] dive on codecs coming Friday. So get
[00:16:10] excited for that and I'll see you in the
[00:16:11] comments. Cheers.
