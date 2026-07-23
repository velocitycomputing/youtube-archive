---
video_id: WAFUMBLOjHo
title: SEE CMUX SOLVE Multi-Agent Orchestration (Claude Code and Pi Agent)
channel: IndyDevDan
url: "https://www.youtube.com/watch?v=WAFUMBLOjHo"
watched_date: 2026-07-06
watched_at: "2026-07-06T12:00:00Z"
watch_count: 1
duration_seconds: 1829
source: youtube-history-browser
added_date: 
history_label: Monday
history_order: 35
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1829
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The presenter demonstrates CMUX, a terminal multiplexer designed for multi-agent orchestration on Mac, to solve three critical problems: lack of programmatic agent access (keeping humans as bottlenecks), inability to monitor agent behavior for improvement, and slow manual bootstrapping of agent teams. CMUX provides hierarchical visibility through workspaces, windows, panes, and tabs, enabling agents to operate terminals programmatically via send/read/close-surface APIs. The core philosophy is "agentic engineering"—agents must be fully visible and controllable to improve performance—versus "vibe coding," where engineers spin up agents and ignore their behavior. Demonstrated patterns include running multiple coding agents (Claude Code, Pi Agent, Codeex, GLM) in parallel for security audits, racing competing agents to solve production bugs faster, and a three-tier hierarchy (orchestrator → team leads → worker agents) for structured collaboration.

Practically, adopt CMUX if you're on Mac and running 5+ concurrent agents; otherwise use T-Mux (Linux/Windows). Key actionable: build a `justfile` with quick-launch commands (e.g., `just fast cc SSC`) to instantly spin up pre-configured team structures instead of booting agents manually each time. The non-negotiable rule is programmatic access—without it, ignore the tool. Implement visibility practices: color-code workspaces by team, use live banners/tabs for status, enable orchestrator notification events to signal completion, and maintain the habit of jumping into individual agent windows to understand failures and successes so you can reinforce winning patterns in future prompts.

## Transcript

[00:00:00] As engineers, there's just one idea you
[00:00:03] and I need to win in the age of agents.
[00:00:07] Scale your compute to scale your impact.
[00:00:10] The goal is clear, but the path is less
[00:00:12] clear. The big open question the best
[00:00:15] engineers are asking is how exactly
[00:00:18] should you orchestrate your agents for
[00:00:20] maximum impact? And there's no shortage
[00:00:23] of options. Boris and Peter are saying
[00:00:26] loop engineering is the future and
[00:00:28] prompt engineering is already dead. I
[00:00:30] completely disagree with this. There's
[00:00:31] the Ralph style to-do list to keep your
[00:00:34] agents focus on a massive list of work.
[00:00:37] Fable is going to love Ralph. Then
[00:00:39] there's classical sub aent delegation
[00:00:41] and many many more patterns. I've been
[00:00:44] engineering for over 15 years and
[00:00:46] building with agents since it was first
[00:00:48] possible. And we have to call out the
[00:00:50] fact that these AI labs have massive
[00:00:53] incentives to keep you and I spending
[00:00:56] tokens, token maxing, when the truth is
[00:00:58] there's a dozen different agentic
[00:01:00] patterns you can use to ship with
[00:01:02] agents. One of my favorite patterns is
[00:01:05] three tier agent orchestration.
[00:01:08] Orchestrators prompt the leads. Leads
[00:01:10] prompt the specialized agent experts.
[00:01:13] But every multi- aent approach has
[00:01:16] similar problems. The big three being
[00:01:19] how do you start, interact, and improve
[00:01:22] your growing fleet of agents. If you're
[00:01:24] vibe coding or token maxing, this
[00:01:26] doesn't matter at all. You can spin up
[00:01:28] 20 agents in a loop and look the other
[00:01:30] way. On this channel, we don't vibe
[00:01:32] code. We agentic engineer because an
[00:01:34] agent you can't monitor is an agent you
[00:01:37] can't improve. I have three multi- aent
[00:01:41] orchestration problems I'm going to
[00:01:43] solve and I'm looking at CMUX as a
[00:01:45] potential solution to this problem. As
[00:01:48] we work through the feature set of CMUX,
[00:01:50] I want to share with you how I'm
[00:01:52] continuing to learn new tools and
[00:01:54] technology with agents. If these ideas
[00:01:57] interest you, smash the like button,
[00:01:59] lock in, and let's improve our agent
[00:02:02] orchestration.
[00:02:08] Whenever I sit down to learn a new tool
[00:02:10] or technology, I have a state-of-the-art
[00:02:13] agent build out a comprehensive HTML
[00:02:16] file that I can use to visually
[00:02:19] understand, study, and master new tools.
[00:02:22] So, that's how we're going to learn CMOX
[00:02:24] right now. Let's start with the problem.
[00:02:27] What problems are we going to solve? I
[00:02:29] don't start with tools. Problems come
[00:02:31] first, tools come second. I know I'm
[00:02:33] late to the Semox game, but I don't
[00:02:35] really care outside of experimentation.
[00:02:37] If I don't need a tool, I don't pick it
[00:02:39] up until I have a problem. First, I have
[00:02:41] three problems surrounding multi-agent
[00:02:43] orchestration that you likely have, too.
[00:02:46] Let's see if can solve three popular
[00:02:49] multi- aent orchestration problems. So,
[00:02:51] first off, no programmatic access to
[00:02:53] your agents. This is a massive problem
[00:02:55] because it means you're the bottleneck
[00:02:57] and it keeps you in the loop all the
[00:03:00] time, meaning your agents can never move
[00:03:02] at the agentic speed. The big question
[00:03:04] is, can Semuk solve this? The answer is
[00:03:07] of course yes. The core value
[00:03:09] proposition of tools like CMUX and the
[00:03:11] triedand-true T-M is this exactly. They
[00:03:14] give you agentic access to every single
[00:03:17] terminal. An agent you can't see is an
[00:03:19] agent you can't improve. This is going
[00:03:21] to be increasingly controversial. A lot
[00:03:23] of engineers are turning off their
[00:03:24] brain. They're not studying what their
[00:03:26] agents are doing. They're spinning up
[00:03:27] fleets and they're ignoring the journey,
[00:03:29] all the mistakes, all the successes, all
[00:03:32] the things that they would want to
[00:03:33] emphasize, reproduce, and cut out of
[00:03:35] their workflow is completely ignored.
[00:03:37] This is one of the key differences
[00:03:39] between vibe coding and agentic
[00:03:41] engineering. An agent you can't see is
[00:03:44] an agent you can't improve. I need to be
[00:03:46] able to see everyone of my agents. Okay?
[00:03:49] It doesn't matter if it's cloud code,
[00:03:51] pi, open code, codeex. I need to be able
[00:03:53] to see it, monitor it and understand
[00:03:54] when things are going right so I can
[00:03:56] re-emphasize that behavior in the agent
[00:03:58] via the core 4 or I need to know when
[00:04:00] things are going wrong so I can present
[00:04:02] negative rewards. Okay, so can Semox
[00:04:04] solve that problem for us? Yes, it can.
[00:04:07] We have per workspace color roll icons,
[00:04:10] identity, we have tabs, we have banners.
[00:04:12] We have everything we need to quickly
[00:04:14] jump into an agent and see it. Quick
[00:04:16] teaser here. I have semox ready to go
[00:04:19] and you can see here we have a great
[00:04:21] breakdown the kind of fundamental pieces
[00:04:23] of a tool where we can quickly see
[00:04:25] observe and therefore improve everything
[00:04:28] right we have a cloud code agent we have
[00:04:29] a codeex agent we have two pi agents
[00:04:31] running the minimax m3 and the jm 5.2
[00:04:33] too. We'll get back to this in a second.
[00:04:35] Let's fully understand every single
[00:04:37] problem. And this is a big one. It's
[00:04:38] increasingly becoming a problem as I
[00:04:40] deploy more and more agents and set up
[00:04:42] new teams to do specific sets of work
[00:04:44] extraordinarily well. If you're building
[00:04:46] custom agents, you're running into this
[00:04:48] problem, too. If you're deploying 5, 10,
[00:04:50] 20 plus agents, you have also seen this
[00:04:52] problem. Booting an agent team by hand
[00:04:54] kills the agentic speed. It just takes
[00:04:57] too much time. So, can T-book solve
[00:04:58] this? Of course, yes, it can. and it has
[00:05:00] reusable session files. But more
[00:05:02] importantly, this tool has agentic
[00:05:05] access. If a tool has agentic access,
[00:05:08] that means you can move at the agentic
[00:05:10] speed and solve problems in natural
[00:05:12] language with well- constructed prompts.
[00:05:15] Okay, so these are the problems we're
[00:05:16] going to solve. CMOX has solutions to
[00:05:19] all of them. I think the question is, do
[00:05:21] you have to use CMX or is something like
[00:05:23] T-Max going to get you all the way there
[00:05:26] as well? So, let's dial back into CMOX
[00:05:28] and understand what this tool can do and
[00:05:29] see if it can help us solve these three
[00:05:31] key problems. Agentic access, monitor to
[00:05:34] improve, and quick agentic launch for
[00:05:36] your thousandth agent run. Not your
[00:05:39] first, not your 10th, not your hundth.
[00:05:44] So, what is our agent teaching us about
[00:05:46] CMX? Let's understand the mental model
[00:05:49] that really builds the foundation of
[00:05:51] understanding CMOX and other terminal
[00:05:53] multiplexes as well. You have the window
[00:05:54] which is going to be this entire window
[00:05:56] here with control shift N. We can boot
[00:05:58] up a brand new window. And then we have
[00:06:00] our workspace. Workspaces, you know, we
[00:06:02] can boot up with command N. And this is
[00:06:04] going to give us a new workspace to set
[00:06:06] up teams of agents to set up groups of
[00:06:08] terminals to do whatever you need to do.
[00:06:10] Then we have PES. The pane is going to
[00:06:12] be the actual window. We have a pane
[00:06:14] here. We have a pane here. We have one
[00:06:16] here, here, and here. It's important to
[00:06:18] mention if we do commandt, this opens a
[00:06:21] new surface inside of this existing
[00:06:24] pane. So we have individual windows. You
[00:06:27] can separate and group your agent teams,
[00:06:29] your terminals, you can have production,
[00:06:31] you can have staging, you can have dev,
[00:06:33] we can have workspaces. So for me, I'm
[00:06:35] going to put my agent teams on the
[00:06:37] workspace level. And then inside of the
[00:06:39] workspace, you have your individual
[00:06:41] panes. So we have a pane here in my
[00:06:43] multi- aent orchestration workflow. I'm
[00:06:44] going to put my lead here. And then the
[00:06:46] workers go over on the right. So I can
[00:06:48] look at the level that I need to to get
[00:06:50] the job done while not losing the depth
[00:06:53] of visibility into the low-level worker
[00:06:56] agents. This is super key, right?
[00:06:58] Prompting in a black box in sub agents
[00:07:00] is a great place to start. Terrible
[00:07:02] place to finish, right? We can do a lot
[00:07:03] better than that with the right agentic
[00:07:06] tools. That's why we're trying to see if
[00:07:08] we can really improve our multi- aent
[00:07:10] orchestration abilities. Okay, so that's
[00:07:12] the mental model of cmox. And so how do
[00:07:14] we control it?
[00:07:19] Uh it's pretty simple. Thanks to the
[00:07:20] programmatic access, we do four things.
[00:07:23] We can send information like send key.
[00:07:25] We can then read the screen after the
[00:07:27] action has been completed. And then we
[00:07:28] can open and close surfaces and the loop
[00:07:31] repeats. Okay, so this is how you
[00:07:33] control it. We're going to walk through
[00:07:34] concrete examples of how you can use
[00:07:36] semucks in just a moment here, but
[00:07:37] here's an example of the API, right?
[00:07:39] Send, read, close surface. You specify
[00:07:42] the surface and the exact text you want
[00:07:45] to send in. Another powerful part about
[00:07:46] CMX, we can build an orchestration agent
[00:07:49] around pushing and pulling specific
[00:07:52] events from the CMX life cycle and
[00:07:55] therefore our agents life cycle. Okay,
[00:07:57] so there's a lot of customizability
[00:07:58] here. When I sit down to learn a tool, I
[00:08:00] use agents the entire time. Learning is
[00:08:03] the killer use case for agents. Coding
[00:08:05] comes next. in these HTML rich guides. I
[00:08:08] want an incremental tier-based
[00:08:11] explanation of how I can best use these
[00:08:12] tools to solve my specific use case. And
[00:08:15] that's exactly what my agent has done
[00:08:16] here. A lot of really smart engineers
[00:08:18] are turning their brains off. I want to
[00:08:20] push back against that. We want to rise
[00:08:22] with the ceiling of agentic engineering,
[00:08:24] not the floor of vibe coding. Okay. So,
[00:08:27] um let's run this, right? Let's
[00:08:28] understand CMOX at a deeper level. You
[00:08:30] see here, this tool can get very, very
[00:08:31] complex. It can help you orchestrate and
[00:08:33] do a lot of work. They even have like a
[00:08:35] mobile app here. You can access
[00:08:36] browsers. There's a lot of cool stuff
[00:08:38] you can do with this tool. We're not
[00:08:39] going to cover all that. We're going to
[00:08:40] focus on the problems we need to have
[00:08:41] solved. Whenever I'm learning a new
[00:08:43] tool, I like to start super simple,
[00:08:45] understand the foundations of the tool,
[00:08:48] and then move to more and more complex
[00:08:50] scenarios. All right, so let's go ahead
[00:08:52] and start from scratch here. I'm going
[00:08:53] to open up a terminal, boot up a cloud
[00:08:54] code opus window here. If you're working
[00:08:57] in the future, you have access to Fable.
[00:08:58] I am jealous of you right now. Can't
[00:09:00] wait for that model to be turned back
[00:09:01] online. Although, it looks like there's
[00:09:03] going to be massive delays with getting
[00:09:04] that back online. So I have a semox
[00:09:05] skill that was built that just makes the
[00:09:07] agent aware of the tool. Open a
[00:09:08] workspace in a fresh temp directory.
[00:09:10] Create 63A files lsla read the output
[00:09:14] back and then continue from there. All
[00:09:15] right. So we're just having our
[00:09:17] orchestrator agent operate on cmox
[00:09:20] windows. So let's see how this looks and
[00:09:21] I'll hold them both open here at the
[00:09:23] same time. So you can see here our
[00:09:25] existing agent team window is open. My
[00:09:27] agent is operating this window. Okay. So
[00:09:30] we have a new workspace here. Inside the
[00:09:32] window, we have a pane with a single
[00:09:34] tab. You can see there's that ls. You
[00:09:36] know, I'm not typing anything here. This
[00:09:37] my agent operating a workspace to be
[00:09:40] clear. This is bigger than a terminal.
[00:09:41] It's done. Right? So, we had an ls all
[00:09:44] these mock files it created. Right? If
[00:09:46] we close this, do ls ourselves, we can
[00:09:47] see them exactly. The great part about
[00:09:49] tools like cmox and t-mox is that you
[00:09:51] can jump in whenever you need to. Right?
[00:09:53] The agent stopping black boxes when you
[00:09:55] can actually touch and jump in to the
[00:09:58] terminal window. Aentic access here is
[00:10:00] super super important. very simple,
[00:10:01] great place to start when you're
[00:10:02] learning a new tool. Just show a basic
[00:10:04] use case of the app. So, let's split
[00:10:06] into a grid. I want to see a grid here.
[00:10:07] So, I'm going to close our throwaway 60
[00:10:10] and we'll work our way up to, you know,
[00:10:12] a full multi- aent orchestration example
[00:10:14] here. We're just setting the groundwork.
[00:10:15] Always start with the fundamentals.
[00:10:22] So, this is going to open a 2x two grid
[00:10:24] in a new workspace.
[00:10:27] There we go. And in each workspace, it's
[00:10:30] going to run specific commands. On the
[00:10:31] right here, it's just an empty terminal.
[00:10:33] Here we have the date being updated per
[00:10:35] second. And then we have a tick in the
[00:10:37] bottom left. And then in the top left,
[00:10:39] we have h top running. Each one of these
[00:10:41] clearly documented in the workspace
[00:10:43] name. You can see how this can be very
[00:10:45] very powerful for agents. Right? So, not
[00:10:47] only is this tool helping us move at the
[00:10:49] agentic speed, it's giving us access to
[00:10:52] quick start commands to run repeat
[00:10:54] workflows. All right? So, boot up your
[00:10:56] front end, boot up your back end, boot
[00:10:57] up all your services, boot up your
[00:10:58] database. Let's keep pushing to see how
[00:11:00] this tool is differentiated from a tool
[00:11:02] like T-Mox because T-Mox is the OG of
[00:11:05] this. Let's go and tidy up. Let's have
[00:11:06] our agent clean everything up. Take the
[00:11:08] dash workspace, rename it, flash it, and
[00:11:11] then start closing it. Okay, so this is
[00:11:13] where we start pushing into the value
[00:11:15] prop of CMX. It can control the PES and
[00:11:17] the windows in a very, very precise way.
[00:11:19] There's the flash. It updated the name
[00:11:21] to retired. So we have live updates
[00:11:23] happening at any point in time that we
[00:11:26] can agentically program. We can prompt
[00:11:28] engineer into the system to really
[00:11:30] control the experience of agentic
[00:11:32] engineering. And that's really where
[00:11:34] this all goes, right? The ultimate user
[00:11:37] interface for agentic engineering, the
[00:11:39] DX for agentic engineering, it is not
[00:11:42] set in stone yet. As much as everyone's
[00:11:44] talking about loop engineering and
[00:11:45] building these new DXs, there are no
[00:11:47] winners yet. Okay? only experimenters,
[00:11:49] only researchers, only those pushing
[00:11:52] what they can do with agents. So, keep
[00:11:54] looking for the optimal developer
[00:11:57] experience for your work, for your
[00:11:59] agent, so on and so forth. Right? And
[00:12:00] that's what we're doing here. We're just
[00:12:02] understanding the state space of the
[00:12:04] available agentic tools. Okay? And as
[00:12:07] you'll notice here, building blocks,
[00:12:09] extensibility, adaptability,
[00:12:11] pluggability is a key part of great
[00:12:15] agentic technology, right? which is why
[00:12:17] I'm drawn to CMOX in the first place.
[00:12:19] Great. Agentic access renamed Flash.
[00:12:21] Close the whole workspace. Great, you
[00:12:22] get the picture. Let's get more complex
[00:12:24] here. Let's boot up Cloud Code and the
[00:12:25] PI coding agent side by side. We're
[00:12:27] going to do this in a brand new
[00:12:28] workspace. That's the mode I like to
[00:12:30] work in here with CMU. So far, I'm
[00:12:32] getting into this nice pattern of
[00:12:33] creating new workspaces, not Windows.
[00:12:35] Two columns here side by side. And one
[00:12:37] is PI and one is Claude. And so, another
[00:12:40] great piece about this, you can
[00:12:41] orchestrate any agent coding tool you
[00:12:43] want to. If you're a cloud code guy,
[00:12:45] scale up your cloud codes. If you're a
[00:12:46] Codeex fan, scale those up. If you're an
[00:12:48] open code scrub, go for that. Just
[00:12:50] kidding. Just kidding. If you're a PI
[00:12:52] coding agent, elite agentic engineer
[00:12:55] plugging and playing with your own
[00:12:56] custom agent harnesses, then you'll go
[00:12:58] for that, right? Opus 4.8, one of the
[00:13:00] best orchestrator models in the game
[00:13:02] until Fable supersedes it. You can see
[00:13:04] here we are orchestrating multiple
[00:13:06] coding agents with the orchestrator
[00:13:08] agent. Okay, very, very powerful stuff.
[00:13:10] I'm using IPI for my PI coding agent.
[00:13:12] This is my customized PI coding agent
[00:13:15] with several different extensions built
[00:13:16] into it. This a specialized developer
[00:13:19] experience as an agent harness. So we've
[00:13:20] just asked a simple question here about
[00:13:22] processes versus threads and they both
[00:13:25] answered, right? So nothing special
[00:13:26] there, but the value proposition is
[00:13:29] obvious. You can boot up agents and you
[00:13:31] can prompt agents using cmox and we can
[00:13:33] continue to scale this. Okay, so let's
[00:13:35] do exactly that. Let's start
[00:13:37] orchestrating fleets of agents. Okay, so
[00:13:40] let's do a 2x2 fleet. And a really
[00:13:41] important piece here that you'll also
[00:13:43] notice is that these agents have
[00:13:44] completed. They then send a notification
[00:13:48] to this top window. Okay? So, say you're
[00:13:50] working over here getting things done on
[00:13:52] another branch of work, another set of
[00:13:54] work. CMU is going to notify you when
[00:13:57] this set of agents or single agent if
[00:13:59] you want to do one workspace per agent.
[00:14:01] It'll let you know when that work is
[00:14:03] done. Okay. But here we go. We have a
[00:14:04] new fleet. This is our security fleet.
[00:14:06] Send up four coding agents. Cloud Code,
[00:14:08] Codeex, Pi with Minamax and GLM. Create
[00:14:11] a fleet. List the top three security
[00:14:13] vulnerabilities you can find in this
[00:14:15] repository. So this is a simple mock
[00:14:17] repository. This is a waste for these
[00:14:18] agents. Not really going to do anything.
[00:14:20] But you can see here this is a simple
[00:14:22] important idea of literally scaling your
[00:14:24] computer to scale your impact. Say you
[00:14:26] were looking for security
[00:14:27] vulnerabilities in your codebase. You
[00:14:29] can spin up one agent and have sub
[00:14:30] agents under it run. Or you could set up
[00:14:32] different agentic coding tools with
[00:14:34] their own unique advantages running
[00:14:36] different agents to run the exact same
[00:14:39] validation pattern, the exact same
[00:14:41] security checks across your codebase.
[00:14:44] Okay, this is the simplest clearest
[00:14:46] example of scaling your compute to scale
[00:14:48] your impact. The big difference here
[00:14:50] with a tool like CMX or T-Mox is that
[00:14:52] this is fully visible. Okay, so we have
[00:14:56] Minamax M3 giving a shot at this GLM 5.2
[00:14:59] and of course the state-of-the-art
[00:15:00] models GPT 5.5 and Opus 4.8. They're all
[00:15:04] applying their opinions, their
[00:15:06] perspective, their expertise, their
[00:15:08] specific model advantage against this
[00:15:10] problem of checking for security
[00:15:12] vulnerabilities, a big topic right now
[00:15:14] in the age of agents. One of the key
[00:15:16] pieces of this is now inside of our
[00:15:19] orchestrator because remember the way
[00:15:20] I'm looking at this tool is any point to
[00:15:23] be able to use my orchestrator to drive
[00:15:25] results in any one of my windows, any
[00:15:28] one of my workspaces and then the
[00:15:30] individual panes, but also have the
[00:15:32] ability to go into any individual agents
[00:15:35] and really just prompt out and dial into
[00:15:38] any details we need to on an agent
[00:15:40] level. Okay, so this is important. We
[00:15:42] want to be able to jump into the process
[00:15:44] at any point, understand what every
[00:15:45] agent is doing, who's got the advantage,
[00:15:47] who's running patterns we want to
[00:15:49] replicate, and who's doing stupid
[00:15:51] we don't want to do again. Okay? And
[00:15:53] that's on a agent coding tool level, all
[00:15:56] the way down to, of course, the model
[00:15:58] level. And then further on down, right?
[00:16:00] Context, model, prompt, tool, system
[00:16:02] prompt, context. So great, these are all
[00:16:04] done. And the orchestrator is reading it
[00:16:06] back out. This is now in idle mode
[00:16:09] because the orchestrator has read the
[00:16:11] response. It's read the surface, right?
[00:16:13] It knows that things are done. This is
[00:16:15] where we start getting out of what T-Max
[00:16:17] can do, right? We're working on multiple
[00:16:19] problems. We're scaling our computer
[00:16:21] scale impact and we can see everything
[00:16:23] and we can understand everything. Okay,
[00:16:26] fantastic. So, we are doing multi- aent
[00:16:28] delegation, but of course, one of the
[00:16:30] key things here is any agent can prompt
[00:16:32] any other agent. So, I'll just try to do
[00:16:34] something random here. Inside of this
[00:16:36] cloud code worker, I'll type cmox to
[00:16:38] activate the skill. Ping your other
[00:16:39] fleet co-workers. So very powerful stuff
[00:16:42] here. It's going to read the screen of
[00:16:43] each surface. I've been seeing really
[00:16:44] really great success with this three
[00:16:46] tier architecture with my agents, right?
[00:16:48] You have a top level orchestrator. You
[00:16:50] then have team leads and then the leads
[00:16:52] have workers that actually do the work.
[00:16:54] Okay, so we're replicating traditional
[00:16:56] hierarchy structures without the true
[00:16:59] cons and true problems with hierarchies,
[00:17:01] right? This is not a top- down
[00:17:02] structure. Any agent can prompt any
[00:17:04] agent. You can see that here thanks to
[00:17:06] this skill here. We're going to do a
[00:17:08] nice simple prompt coming into every
[00:17:10] single agent from inside CMX, right? So,
[00:17:13] our agents can prompt our agents. This
[00:17:15] is a flat hierarchy even though there is
[00:17:17] one orchard is at the top. And so, I
[00:17:19] like to put my team lead on the left as
[00:17:20] you'll see in a moment, but we can just
[00:17:21] drag and drop this down here or we'll
[00:17:23] move it over here. And this very quickly
[00:17:25] kind of shows you the organizational
[00:17:27] structure that you can build. Lead here,
[00:17:29] workers here. And you can build any
[00:17:31] structure you want. The point is is that
[00:17:32] the communication channel is flat. All
[00:17:34] right. So, fantastic. What else can we
[00:17:36] do with this tool? Let's scale into
[00:17:38] workspaces. Let's really push what we
[00:17:40] can do with this. So, I'm going to copy
[00:17:41] this larger prompt here. Going to have
[00:17:42] my agent do this here. We're going to
[00:17:44] showcase like the importance of
[00:17:45] organization inside the workspace. You
[00:17:48] can see here we're starting to already
[00:17:49] have a lot more organization than normal
[00:17:51] if we were just in a single terminal or
[00:17:52] if we were using a single terminal with
[00:17:53] tabs. We're getting notification events
[00:17:55] which are pretty pluggable. You can do a
[00:17:58] lot more with them than we are. You can
[00:17:59] see here, imagine you're booting up
[00:18:01] multiple teams to solve multiple
[00:18:03] problems. We have gamma, beta, alpha. We
[00:18:05] can jump into these and we can see our
[00:18:06] let me pull up the orchestrator so we
[00:18:08] can see what's going on here. Our
[00:18:09] orchestrator getting work done booting
[00:18:11] up sets of agents programmatically.
[00:18:13] Let's close our security fleet here.
[00:18:15] Okay, so we have gamma, we have beta,
[00:18:17] and we have alpha booted up. Okay, so
[00:18:20] you know, imagine any multi- aent
[00:18:22] orchestration set of teams you want.
[00:18:25] That's a key value proposition here. You
[00:18:26] have multi- aent coordination at a
[00:18:28] massive scale, right? Just an absolutely
[00:18:30] massive scale and you're in control and
[00:18:32] you have visibility into it. Okay, super
[00:18:35] super important. If you hold command,
[00:18:36] you can see all the hot keys for each
[00:18:37] workspace. This is clearly the unit that
[00:18:40] CMX sees as the most important to be
[00:18:42] navigating. It's at that workspace
[00:18:44] level. But of course, we can quickly
[00:18:45] move through all of our surfaces as
[00:18:48] well, right? So again, just expressing
[00:18:50] the idea here. You can scale agents
[00:18:51] across multiple workspaces as well.
[00:18:59] So let's look at the scenario where you
[00:19:01] need to fix a bug right away. Say
[00:19:03] production's going down. Your customers
[00:19:05] and your users are completely blocked.
[00:19:07] So you're losing money by the second.
[00:19:10] Okay. So I'm going to hit new here just
[00:19:11] to reboot everything and then paste this
[00:19:13] in here. There's a longer prompt, but
[00:19:15] we're going to have agents race toward a
[00:19:17] solution. Okay. So I'm going to close
[00:19:18] all these windows here. Say there's a
[00:19:19] production issue and you need to resolve
[00:19:22] it yesterday. This is going to be a
[00:19:23] differentiating agentic engineering
[00:19:26] pattern that you can use. It's super
[00:19:27] simple. Throw more compute at the
[00:19:29] problem. Have your agents race toward a
[00:19:31] solution. We're going to do a needle in
[00:19:32] a haystack search. In reality, this will
[00:19:34] be a hot fix. You'll need to deploy, but
[00:19:37] you can just throw a bunch of agents at
[00:19:38] a problem at the same time in parallel.
[00:19:41] You want the first available answers so
[00:19:42] you can deploy the fix back into
[00:19:44] production. Okay. So, in this scenario,
[00:19:46] we're going to boot up an eight agent
[00:19:47] race to just race toward a solution. So,
[00:19:50] there we go. All the windows popping
[00:19:52] open here. And we're going to deploy a
[00:19:54] variety of compute to get the job done.
[00:19:56] This is needle in a hay stack. Capture
[00:19:58] the flag. first agent to the goalpost
[00:20:00] wins type of task. Okay. And multi- aent
[00:20:03] orchestration lets you do this really
[00:20:05] really well. Every context model prompt,
[00:20:07] every agent coding tool is going to have
[00:20:09] their unique advantages, strengths and
[00:20:11] weaknesses. And so when you need to
[00:20:13] deploy something quickly, when you have
[00:20:14] a hot fix you need to deploy, throwing
[00:20:16] different types of intelligence at the
[00:20:19] problem is going to get you the better
[00:20:21] result pretty much every single time if
[00:20:23] you're willing to of course pay for the
[00:20:25] compute. And so you can imagine, you
[00:20:27] know, you have your red team agent race
[00:20:29] here and then you might have another set
[00:20:31] of agents in a, you know, your
[00:20:33] infrastructure agents or your deploy
[00:20:35] agents here. And then you might have
[00:20:37] your review set of agents here to at
[00:20:39] scale quickly review the issue so that
[00:20:42] you can then hand it off to your infra
[00:20:44] team of agents, right? Your deploy
[00:20:46] agents. And now we have a bunch of
[00:20:48] compute thrown at the problem. We've got
[00:20:50] Opus, we've got Sonnet. And another
[00:20:52] advantage here, you can see a couple of
[00:20:53] my PI agents didn't even fire. It looks
[00:20:55] like an environment variable setup
[00:20:56] problem. That's fine. My local agent, my
[00:20:59] local Quinn is working. All the codecs
[00:21:01] and all the Sonnet models quickly found
[00:21:03] the solution. That's done. And now this
[00:21:05] issue can be reported. And now we're
[00:21:07] waiting for that notification event for
[00:21:10] my orchestrator and needs input. There
[00:21:12] we go. Okay, so it finally triggered
[00:21:13] there. And now our orchestrator should
[00:21:15] pick this up. Let's go and see if it
[00:21:17] does pick it up cuz all the agents are
[00:21:19] complete. Maybe this is a good time for
[00:21:21] us to transition a little bit and talk
[00:21:22] about the pros and cons of this tool,
[00:21:24] right? And maybe my agents just don't
[00:21:26] don't understand the tool properly.
[00:21:27] That's fine. It could be a mistake on my
[00:21:29] part. When you're using tools like this,
[00:21:30] these new tools, tools that are just
[00:21:32] kind of appearing overnight, and I know
[00:21:34] CMX deserves more credit than that. This
[00:21:36] is a solid tool that's been around for a
[00:21:37] while. There's a whole wave of agentic
[00:21:39] tools coming. And you're always going to
[00:21:41] want to compare that against tried and
[00:21:43] true technology. So, when I sit down to
[00:21:44] solve problems and learn with agents,
[00:21:47] I'm always comparing against what else
[00:21:49] exists. For a lot of the capability
[00:21:51] we've looked at here, T-Max can do the
[00:21:53] job. The thing is that it's not going to
[00:21:54] be as customizable and aesthetic, and
[00:21:58] the developer experience, I think, with
[00:21:59] T-Max is a little harder to get right.
[00:22:02] That's what CMOX does really, really
[00:22:04] well. It's made for the modern era of
[00:22:07] building with agents programmatically on
[00:22:09] Mac devices. Okay, so yeah, probably
[00:22:12] should have mentioned that earlier. If
[00:22:13] you're on Linux, Windows, WSL, you know,
[00:22:15] you're going to need to use a tool like
[00:22:16] T-Mox. This is Mac only. The big problem
[00:22:19] with this is just maturity, right? These
[00:22:21] brand new tools have issues and it could
[00:22:23] be me. But you can see here, you know,
[00:22:25] in our red team response here, our
[00:22:27] orchestrator has done nothing. Check and
[00:22:29] understand why you stalled there, right?
[00:22:31] Because really we wanted to ping on the
[00:22:34] first completion of our tool, right? Our
[00:22:36] first completion of any window. Okay, so
[00:22:39] foreground 10 minute. Okay, very weird.
[00:22:40] So we did get a notification event. uh
[00:22:42] it just seems like our agent didn't
[00:22:44] register it. This is one of the things I
[00:22:46] need to spend more time on to make sure
[00:22:47] I'm getting right and it's just one of
[00:22:49] the things that you'll have to
[00:22:50] understand when you're building and
[00:22:52] teaching your agents how to use the
[00:22:53] tool. Something can be improved there,
[00:22:54] but the high level is still there. There
[00:22:56] are notification events you can plug
[00:22:58] your agents into to wait for responses
[00:23:00] from your agents.
[00:23:06] We're going to stand up eight agents
[00:23:08] across four workspaces, two agents in
[00:23:10] each. Give them each a two column
[00:23:11] layout. The left is the agent and the
[00:23:13] right is going to be a browser. Now,
[00:23:15] this direction is fine. CMX is, you
[00:23:17] know, trying to grow as a product, so it
[00:23:19] has inapp browsers. That's really cool.
[00:23:21] The real killer feature here is
[00:23:23] programmability. This is the most
[00:23:25] important thing. It's nice that it's
[00:23:26] lightweight. Of course, open source is
[00:23:28] super important, but customizability is
[00:23:30] what comes next. And there's a whole
[00:23:32] slew of customization you can build out
[00:23:35] into your CMX application that we're
[00:23:38] going to gloss over because these are
[00:23:40] extra features. You can change the theme
[00:23:42] and feel. You can add custom action
[00:23:44] buttons. That's all well and good. The
[00:23:46] most important thing here by far is a
[00:23:49] gentic access, right? This is a huge
[00:23:51] theme. This is one of the key pillars of
[00:23:54] agentic engineering, right? is making
[00:23:56] sure that you have a gentic access to
[00:23:59] every tool to every service to every
[00:24:00] product that you want to interact with
[00:24:02] at the speed of agents not the speed of
[00:24:04] humans. I think we can just say that
[00:24:06] right in the digital world eventually
[00:24:08] the physical world too we move very
[00:24:11] slowly now and there are advantages to
[00:24:13] moving slowly coding is not our domain
[00:24:15] anymore that is the domain of agents
[00:24:18] okay but orchestrating intelligence is
[00:24:20] our domain this is one of the five
[00:24:21] pillars of agentic engineering we've
[00:24:23] covered this in a previous video I'll
[00:24:24] link that below if you're interested
[00:24:27] here's the kind of high level of the
[00:24:28] five pillars I'm really really focusing
[00:24:30] on right now over 2026 and aentic access
[00:24:33] is number five Even your agents should
[00:24:36] have agentic access, right? You want
[00:24:38] that meta level of control. And this is
[00:24:40] all to raise the ceiling of your agentic
[00:24:43] engineering, not the floor of vibe
[00:24:45] coding. When these mythos class models
[00:24:47] come out, a lot of engineers are just
[00:24:48] going to sit. They're going to get lazy.
[00:24:50] They're going to stop thinking and just
[00:24:51] hand the wheel to the agent. On this
[00:24:53] channel, we're not going to be doing
[00:24:54] that. If you agree with that ideology,
[00:24:57] like, follow, subscribe, all that good
[00:24:58] stuff. The kind of oneliner is if a tool
[00:25:01] does not have programmatic access, I
[00:25:03] just completely ignore it. Now I don't
[00:25:04] give it another second of my time. Okay.
[00:25:07] Agentic access gives you the agentic
[00:25:10] speed. Let's see where our team is. FS
[00:25:12] delta gamma beta alpha team. Imagine
[00:25:14] these are you know the names of features
[00:25:16] the names of bug fixes the names of
[00:25:19] things you are actually building
[00:25:20] against. We have a nice browser on the
[00:25:22] side. And we have a two agent team per
[00:25:24] workspace to work on that browser. Okay.
[00:25:27] So you get the idea here, right? We have
[00:25:28] a little custom theming here to help us
[00:25:31] get back in the loop when we need to be
[00:25:33] in the loop to orchestrate our agents.
[00:25:35] So again, you know, having visual
[00:25:37] identifiers improves your developer
[00:25:38] experience, lets you focus on what
[00:25:40] matters the most and then you can just
[00:25:42] move on. The biggest risk with CMX is
[00:25:45] that this is a new relatively fastmoving
[00:25:47] tool. I'm going to be using both of
[00:25:49] these tools side by side, not so much
[00:25:51] using warp anymore, but CMX and T-Mox
[00:25:54] I'm going to be spending some time on.
[00:25:55] And that leads us to the kind of final
[00:25:57] problem. I need to be able to quickly
[00:25:59] launch agents for the thousandth time.
[00:26:01] So, let me show you really concretely
[00:26:02] how I'm using a tool like this. So,
[00:26:08] I have a just file inside of my code
[00:26:11] bases and this lets me give a really
[00:26:13] quick onetap command to boot up new
[00:26:15] agent teams. Okay, so I'll just type
[00:26:17] jfast cc. If I hit enter here, I need to
[00:26:20] pass in a feature. So, what's the focus
[00:26:23] of this agent team? Okay, so I'll type
[00:26:25] fast CC and then we'll call this SSC.
[00:26:28] Let's assume we're adding server sent
[00:26:30] events into our web server. Okay, so
[00:26:32] we'll hit enter there and this is going
[00:26:33] to pretty much instantly boot up an
[00:26:36] agent team and this is a unique agent
[00:26:39] team in the multi- aent orchestration
[00:26:40] pattern that I like. This is three tier
[00:26:43] multi- aent orchestration and it looks
[00:26:44] like this. The orchestrator here, team
[00:26:46] leads here. Every one of these is a team
[00:26:48] lead in my workspace. And so this
[00:26:51] specifically is the team lead. Right now
[00:26:52] I'm using a GLM 5.2 two and then every
[00:26:54] team lead gets access to worker agents.
[00:26:57] Okay, so here's my plan agent, here's my
[00:27:00] theoretical build agent, here's the
[00:27:01] build front end, and here's the testing
[00:27:04] agent. Might seem complex to add one
[00:27:06] additional level of agent, but it helps
[00:27:08] a lot. And I've needed a tool like CMX.
[00:27:11] T-Max wasn't cutting it for the right
[00:27:13] organizational structure. And so I'm
[00:27:15] picking up a tool like CMUX to kind of
[00:27:17] help me solve this multi- aent
[00:27:18] orchestration problem. these sets of
[00:27:21] problems. It's starting agents. It's
[00:27:23] monitoring agents so you can improve
[00:27:24] them. And then it's being able to scale
[00:27:26] your orchestration to whatever level you
[00:27:29] need to. And so, as mentioned, this is
[00:27:31] not top-down agent communication, right?
[00:27:33] Any agent can prompt any agent. I also
[00:27:35] have my specialized comsnet PI agent
[00:27:38] coding extension, but CMOX lets me push
[00:27:40] outside of the extension and have any
[00:27:42] agent decoding tool talk to any agent
[00:27:45] decoding tool. Thanks to the semox
[00:27:47] skill, birectional flat agent
[00:27:49] communication is super important while
[00:27:50] maintaining an orchestrator, a lead, and
[00:27:54] then a worker level setup. And I'll link
[00:27:56] the video where we go into multi-tiered
[00:27:59] agent orchestration. This isn't for
[00:28:01] everyone. A lot of engineers are going
[00:28:02] to look at this and say, "Why do I need
[00:28:04] this? It's slop. This isn't useful."
[00:28:06] That's fine. It just means it's not for
[00:28:07] you. Okay? As I mentioned in the
[00:28:08] beginning, there's many ways to do this.
[00:28:10] You can use the Ralph to-do list. You
[00:28:12] can use the new loop engineering
[00:28:14] patterns. And you can just use classic
[00:28:16] cloud code subbasation delegation that's
[00:28:18] fine right they have the slashworkspaces
[00:28:20] they have slashloop they have slashgoal
[00:28:22] right use whatever works for you my goal
[00:28:24] here is just to show you the optionality
[00:28:26] of what's available to you and to
[00:28:28] reemphasize a gentic access and full
[00:28:32] control over the primitives of agentic
[00:28:34] engineering right context model prompt
[00:28:36] tool once you have an agent up and
[00:28:38] running you can scale it right now I
[00:28:40] have a team here that has let's say
[00:28:42] these are each 1 million contacts each
[00:28:45] specialized, that gives me 5 million
[00:28:47] tokens of context to work with, quite
[00:28:49] literally, right? That's not an
[00:28:50] exaggeration. When you put together your
[00:28:52] agents in a way where they can all
[00:28:53] communicate, you're getting a bigger
[00:28:55] team of intelligence to work on your
[00:28:57] behalf. Okay, so um you know, what's the
[00:29:00] verdict? I like CMX. I'm going to be
[00:29:02] using this tool. It stands up to T-Mox
[00:29:04] pretty well. I'm going to be keeping my
[00:29:05] eye on any glitches or bugs with this
[00:29:08] tool, but so far, I'm a big fan. It's
[00:29:11] the scriptable service API, the agentic
[00:29:13] access that really matters with this
[00:29:15] tool. There are a bunch of other
[00:29:16] features here I didn't mention. I'm sure
[00:29:18] some CMOX hardcore users are going to be
[00:29:21] flaming me for this being so relatively
[00:29:23] simple. But the key here is it's
[00:29:25] programmable, right? That's the most
[00:29:27] important thing by far. Aentic access is
[00:29:29] a requirement for agentic engineering.
[00:29:33] And this is going to compound. Every
[00:29:35] single thing you set up here from this
[00:29:37] five item list is going to give you a
[00:29:39] compounding advantage for agentic
[00:29:41] engineering. Once again, we want to be
[00:29:43] moving up with the ceiling of agentic
[00:29:46] engineering, not the floor of vibe
[00:29:47] coding. All these ideas are big ideas we
[00:29:51] talk about and really break down in
[00:29:52] tactical agentic coding. I'll leave a
[00:29:54] link in the description for that if
[00:29:56] you're interested in paying a little bit
[00:29:58] to get a massive advantage. If you're
[00:30:00] not though, that's totally fine. I'm
[00:30:01] going leave my entire guide code base
[00:30:03] here to really break down Semox
[00:30:05] capabilities. If you made it to the end
[00:30:06] and you want to see more agentic
[00:30:08] engineering content like this, drop a
[00:30:09] like, share the video with a friend,
[00:30:11] with a co-orker, and then comment down
[00:30:12] below. How are you thinking about multi-
[00:30:15] aent orchestration? Do you have any
[00:30:16] unique experiments or tools you're
[00:30:18] running to better scale your computer to
[00:30:20] scale your impact? You know where to
[00:30:22] find me every single Monday. Stay
[00:30:24] focused and keep building.
