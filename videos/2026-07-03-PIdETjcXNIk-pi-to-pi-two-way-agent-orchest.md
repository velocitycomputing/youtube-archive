---
video_id: PIdETjcXNIk
title: "Pi to Pi: Two-Way Agent Orchestration with the Pi Coding Agent"
channel: IndyDevDan
url: "https://www.youtube.com/watch?v=PIdETjcXNIk"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 2092
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 66
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 209
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video demonstrates "Pi to Pi" bidirectional agent-to-agent communication using the Pi Coding Agent, where multiple AI agents (like GPT-5.5 and Claude Opus 4.7) operate as equals rather than in hierarchical orchestrator-worker relationships. Dan shows a production example where a production agent running on a Mac mini and a developer agent on an M5 MacBook Pro collaborate to reproduce a production bug while automatically redacting PII—illustrating how peer-to-peer communication enables secure cross-device workflows. The underlying philosophy mirrors flat organizational hierarchies: flat information structures let the best ideas win because communication happens at every level, not through top-down chains. Technically, the system uses four simple tools: list agents, send prompts, and block/non-blocking await responses; specialized, focused agents outperform monolithic ones because narrower context windows reduce error rates, and pairing different models (trained on different RL loops) creates emergent capabilities neither alone possesses.

For your use, implement peer-to-peer agent communication when you need agents to solve coordinated problems—especially multi-device scenarios requiring security isolation (PII redaction, production access control). The pattern works for tool/service evaluation: have specialized agents research and compare features (like the E2B vs. exe.dev sandbox tools) and validate each other's claims, reducing your manual research. Build agents with tight, focused context windows on single problems; add a validator agent on top to double-check outputs. The code is available in the Pi versus Cloud Code codebase with both single-device and network implementations—adapt and tailor them for your use case rather than treating the code as finished.

## Transcript

[00:00:00] What's up engineers? Indie Dev Dan here.
[00:00:02] I have a simple question for you. What's
[00:00:04] better than one GPT 5.5 Pi coding agent?
[00:00:09] You guessed it, two GPT 5.5 Pi coding
[00:00:13] agents. Let's push it further. What's
[00:00:15] better than two isolated side-by-side
[00:00:17] GPT 5.5 agents? Sure, you could add
[00:00:20] another agent. Sure, you could change
[00:00:22] the model, but we can do much better
[00:00:24] than this. What about two GPT 5.5 agents
[00:00:28] that actually work together?
[00:00:31] What about three agents that work
[00:00:33] together with unique models? What about
[00:00:36] four models? So, here we have four Pi
[00:00:39] coding agents and none of them is the
[00:00:41] orchestrator. Instead, they're equals.
[00:00:44] They're co-workers pinging every agent.
[00:00:47] In this video, we'll understand what
[00:00:50] type of agentic engineering we can
[00:00:52] achieve if we gave our agents a true
[00:00:55] two-way communication channel. By the
[00:00:58] end of this video, you'll have a simple
[00:01:00] yet powerful way to coordinate your
[00:01:03] multi-agent systems. This gives us a
[00:01:05] powerful flat agent hierarchy where the
[00:01:09] best information wins, where the best
[00:01:11] ideas win, and where your agents can
[00:01:13] truly coordinate together to outperform
[00:01:16] each other alone. Let's talk about
[00:01:18] Pi-to-Pi two-way agent communication.
[00:01:27] So, let's go ahead and reset here. Let's
[00:01:29] de-hype this a little bit. Let's close
[00:01:31] our agents. As you can see, one by one
[00:01:33] as we close them, they leave the chat
[00:01:35] room. They leave the communication pool.
[00:01:38] We've got a production database on my
[00:01:40] Mac mini. And this production database
[00:01:42] has an issue. Some ProTier users are
[00:01:44] getting locked out of pro features. So,
[00:01:47] in order to fix this issue, I need to
[00:01:48] reproduce it on my local developer
[00:01:50] environment. This is a common
[00:01:52] engineering workflow. You don't fix
[00:01:54] things in production, and fix things on
[00:01:55] your developer environment, and then you
[00:01:57] deploy through staging, and then
[00:01:59] eventually it hits production. The trick
[00:02:01] here is there is sensitive information
[00:02:03] on my Mac mini production environment
[00:02:06] here, and I can't leak any PII while I'm
[00:02:10] fixing this issue. We're not live coding
[00:02:11] here, we're doing real engineering work
[00:02:13] in production systems. Our pie-to-pie
[00:02:16] agent-to-agent communication system is
[00:02:18] perfect for this. So, I'll boot up two
[00:02:20] agents here, one on my Mac mini, the
[00:02:22] production server, and one on my M5
[00:02:24] MacBook Pro, my dev machine. We'll do J
[00:02:26] coms two, and we'll give this a name.
[00:02:28] This is going to be production. J coms
[00:02:30] one, name dev. We'll run some basic
[00:02:32] pings to make sure both agents are up
[00:02:34] and online. And then we're going to
[00:02:35] paste in a production prompt here. This
[00:02:38] is a prod gatekeeper agent. It has a
[00:02:40] production database it's working with
[00:02:42] that's been seeded. We're not going to
[00:02:43] recreate it or anything. And you have a
[00:02:46] team name. And then key piece here, we
[00:02:48] have PII inside of this production code
[00:02:51] base that we're not going to break. This
[00:02:52] is personal identifiable information.
[00:02:56] So, our production agent understands the
[00:02:57] system, it understands what's available,
[00:02:59] and it knows that it's not going to
[00:03:01] expose any information to any other
[00:03:04] agent on the network, okay? And now our
[00:03:07] developer agent is going to get to work.
[00:03:08] We need to reproduce this issue locally.
[00:03:11] Here's our developer prompt. The key
[00:03:12] here is this. Bring the affected slice
[00:03:15] from production over with PII stripped
[00:03:17] into your local dev DB so an engineer
[00:03:20] can reproduce the issue locally. First,
[00:03:22] in order to reproduce a production
[00:03:24] database issue, you need the production
[00:03:26] data. Here's where the magic happens.
[00:03:28] Our agent sees the peer on the network,
[00:03:31] right? It knows that it has connection
[00:03:32] to a prod agent, and now it's going to
[00:03:34] start working through things. So, it's
[00:03:36] going to send a message, it's going to
[00:03:37] send a prompt, and it's going to get
[00:03:38] returned an ID, a message ID. Our agent
[00:03:41] can now await this message, and our
[00:03:43] production agent, as you can see here,
[00:03:46] is getting to work on the production
[00:03:48] side. But it's getting to work with all
[00:03:50] redactions applied, right? It's not
[00:03:52] going to expose any personal
[00:03:54] identifiable information. Our agent is
[00:03:56] going to work back and forth here, not
[00:03:58] as individual agents, not as a sub
[00:04:01] agent, not as workers, right? They're
[00:04:03] going to work together as a team. It's a
[00:04:06] simple, beautiful pattern, and it really
[00:04:08] reflects how great work is done. And so,
[00:04:11] our agent is learning about the local
[00:04:13] DB. It's making sure that it's clean,
[00:04:15] and it's starting to sync things while
[00:04:17] keeping everything PII safe, right? So,
[00:04:20] this is yet another place where if you
[00:04:22] engineer things properly, if you prompt
[00:04:25] things properly, you can do
[00:04:26] extraordinary things in your agentic
[00:04:29] systems. There are endless use cases for
[00:04:32] agents that actually communicate and
[00:04:34] work together. You can see there we got
[00:04:35] another message back, and this process
[00:04:38] is going to continue. So, we're going to
[00:04:40] let our agents cook here. I want to take
[00:04:42] the time to like highlight why
[00:04:44] agent-to-agent communication is so
[00:04:45] important, and highlight, of course,
[00:04:47] once again, why the Pi Coding Agent is
[00:04:49] really the only way that you get this
[00:04:51] level of control out of your agents
[00:04:53] here.
[00:04:59] I think the most important thing to
[00:05:00] start with here is understanding the
[00:05:02] current problem, right? Agents can't
[00:05:04] talk to each other. We know that there
[00:05:06] is sub agent delegation and sub agent
[00:05:09] prompting, right? And this is a great
[00:05:10] pattern. It's a great start. Like if you
[00:05:12] agree with this statement, we are just
[00:05:14] scratching the surface of what the true
[00:05:17] developer experience looks like for
[00:05:19] agentic engineering, right? We don't
[00:05:22] really even know what that form factor
[00:05:23] is. I think very clearly in terminal
[00:05:27] agents
[00:05:29] the center point, but everything around
[00:05:31] that from the agent harness to how we
[00:05:33] manage contexts, models, agent scale,
[00:05:35] tools, this is all a work in progress.
[00:05:38] So, if we're not exploring the state
[00:05:39] space of what's possible with our agent
[00:05:41] communication and other agentic
[00:05:44] workflows and patterns, uh we're going
[00:05:46] to be stuck in the normal distribution,
[00:05:48] the very beginning of what's possible.
[00:05:50] So, sub agents, very important, very
[00:05:52] cool, but this is just the beginning,
[00:05:53] right? When you push further, you can
[00:05:55] find a message queue, and this is what
[00:05:57] the Cloud Code agent teams uses. So, you
[00:05:59] have one agent that kind of sets up all
[00:06:01] the message queue, and then it serves as
[00:06:03] a message broker between agents. Another
[00:06:05] great powerful pattern. You then have
[00:06:07] things like agent chains, where you have
[00:06:08] a deterministic set up workflow that
[00:06:11] have individual nodes of agents. When
[00:06:13] you combine this with code, you get
[00:06:14] powerful AI developer workflows or
[00:06:17] blueprints or representations of agents
[00:06:20] plus code. This is a very, very powerful
[00:06:22] framework, because it adds determinism
[00:06:25] into the process, right? At any one of
[00:06:26] these steps, you can insert code, and
[00:06:28] it'll enhance what your agents can do.
[00:06:30] So, very powerful stuff here, right?
[00:06:31] But, um there's a problem with this. As
[00:06:33] you can see, in every one of these
[00:06:34] workflows, it is traveling information
[00:06:37] in basically one direction, and it's
[00:06:39] always a top-down way. Even if the
[00:06:41] information comes back, it's a one-way
[00:06:43] stream, right? It's never bidirectional.
[00:06:45] So, what's the solution?
[00:06:47] It's quite simple. Let your agents talk
[00:06:50] to each other, right? Prompt response,
[00:06:52] and then prompt response, okay?
[00:06:55] Peer-to-peer, not
[00:06:57] orchestrator-to-worker,
[00:06:59] changes things. Here, agents are equals.
[00:07:02] They're not parent and child, and this
[00:07:04] unlocks, of course, bidirectional flows
[00:07:06] of information, okay? Just two agents
[00:07:08] communicating to each other. As you can
[00:07:10] see here, our agents are still working
[00:07:12] together to figure out these issues, to
[00:07:14] really work through how to perfectly
[00:07:16] reproduce the production slice. But, you
[00:07:19] can push this across devices and across
[00:07:22] multiple agents, right? And this looks
[00:07:23] like exactly what you'd imagine, right?
[00:07:25] Now, we have three agents in the
[00:07:27] network. You might have a researcher,
[00:07:28] coder, planner. These can be anything
[00:07:30] under the sun. In our case, we have a
[00:07:33] prod agent, and we have a developer
[00:07:35] agent talking to each other across the
[00:07:38] network, okay? But, you can just keep
[00:07:39] scaling this up, right? And at some
[00:07:41] point, it's going to be uh harmful,
[00:07:44] right? Like there is a limit to how
[00:07:45] useful this is. Um I'm not just trying
[00:07:47] to sell you the upside here. There's
[00:07:49] downsides to every approach. Great
[00:07:50] engineering is all about managing
[00:07:52] tradeoffs. At some level, you're not
[00:07:54] going to want to use this pattern
[00:07:55] anymore. And at some level, adding
[00:07:57] agents doesn't help anything. But, there
[00:08:00] is certainly a useful level to this
[00:08:02] where you want to have bidirectional
[00:08:04] agent-to-agent communication, where it's
[00:08:06] very, very useful to have every agent
[00:08:08] have access to every other agent, okay?
[00:08:11] And so, why is this useful, right? Let's
[00:08:13] let's really hit on this. Like I think
[00:08:15] at the core of this, it comes down to
[00:08:18] information hierarchies. If you have a
[00:08:20] traditional software engineering job,
[00:08:21] you work at a company that has a
[00:08:23] hierarchy, right? For one reason or
[00:08:25] another, there is someone at the top,
[00:08:27] okay? And information usually travels
[00:08:29] downstream, commands travel downstream,
[00:08:31] objectives travel downstream, and then
[00:08:34] it hits the person, usually the
[00:08:36] engineers, who are actually building the
[00:08:37] thing, right? And oftentimes, the best
[00:08:40] information, the best decisions, the
[00:08:42] best awareness about the system is all
[00:08:44] the way down here, right? It's on the
[00:08:46] worker level, right? It's It's you and
[00:08:48] I, the engineers with their boots on the
[00:08:49] ground every single day, putting in the
[00:08:51] work to understand the system,
[00:08:52] understand the objectives, and then
[00:08:53] actually building it, right? The best
[00:08:55] information is often times down here.
[00:08:58] When you have these hierarchical
[00:08:59] information systems, and I'm speaking in
[00:09:02] a generic way, it doesn't just need to
[00:09:03] be about the job. It doesn't just need
[00:09:05] to be in a career setting. But, just
[00:09:07] information structures like this, often
[00:09:09] times the best ideas are down here. They
[00:09:11] get stuck down here because they don't
[00:09:12] have the right title, they don't have
[00:09:14] the right authority, they don't have the
[00:09:16] right say, right? And you've, you know,
[00:09:18] you've probably heard this, right? But,
[00:09:19] the best companies, the best structures
[00:09:21] are flat, where there's communication
[00:09:24] happening on every single level, where
[00:09:26] everyone can just talk to the other to
[00:09:28] get the job done, right? Nvidia is
[00:09:30] really famous for this, very flat
[00:09:31] reporting structures. Of course, Jensen
[00:09:33] at the top, commanding that insane
[00:09:36] company. But, then he has uh very few
[00:09:38] direct reports, and then it spans from
[00:09:40] there, right? But, startups are famous
[00:09:41] for this, right? You have very, very
[00:09:43] flat structures. All the best
[00:09:45] information systems are flat. Why is
[00:09:48] that? It's because you get valuable
[00:09:50] information wins always over titles and
[00:09:53] politics, okay? Ideas die in
[00:09:55] hierarchies. So, that's why this is so
[00:09:58] important. And And, you know, maybe you
[00:10:00] think I'm anthropomorphizing this too
[00:10:01] much. Maybe you think I am trying to
[00:10:03] apply something where it doesn't belong.
[00:10:05] I completely disagree. I think when you
[00:10:07] really boil things down, everything is a
[00:10:08] system. And a key part about every
[00:10:11] system is that there is flows of
[00:10:14] information inside of systems, and how
[00:10:16] things flow, how the structures, the
[00:10:19] nodes, and the actors in the system
[00:10:21] communicate information matters, right?
[00:10:23] This matters because oftentimes the best
[00:10:26] ideas are down here. They're at the
[00:10:28] bottom level. And so, this means that as
[00:10:30] much as you can, you want to have flat
[00:10:32] hierarchy structures, okay? But, on a
[00:10:34] functional level, we can see that this
[00:10:36] is uh useful for other reasons as well.
[00:10:39] We have cross-device agent-to-agent
[00:10:41] communication, right? We have a
[00:10:42] production service. Say this is in the
[00:10:45] EU,
[00:10:46] right? Where everything has to be
[00:10:47] redacted, everything has to be perfect,
[00:10:50] and nothing can escape the device. But,
[00:10:51] you still need to fix things, right? We
[00:10:53] still need to do real engineering work.
[00:10:55] So, this is a great system. We have
[00:10:56] redacted information properly,
[00:10:58] transferred it to our developer machine.
[00:11:00] And as you can see here, the repro is
[00:11:02] ready, the bug has been imported, okay?
[00:11:04] PII is clean, okay? So, legitimate
[00:11:07] engineering work happening here.
[00:11:09] Obviously, this is not a real production
[00:11:11] server. I'm using this as an example.
[00:11:13] And now I can go ahead, debug, look at
[00:11:15] my code, look at this slice of the
[00:11:18] production database that has been
[00:11:19] reproduced from production. And now I
[00:11:21] can actually resolve the bug. And our
[00:11:23] agents are really great at communicating
[00:11:25] information like this. And that's
[00:11:26] exactly what they've done, okay? So, we
[00:11:27] have very simple two-way bidirectional
[00:11:31] agent-to-agent communication. If I
[00:11:32] needed to, I could come in here and
[00:11:35] validate that everything looks good on
[00:11:36] the production agent side, right? Do one
[00:11:39] final check with the dev agent PRI safe.
[00:11:43] The issue has been repro'd. We can talk
[00:11:45] to any side that we need to, and they
[00:11:48] can then communicate together to get the
[00:11:50] job done. So, I hope you can see the
[00:11:51] value proposition of this. I hope you
[00:11:52] can see why agent-to-agent communication
[00:11:54] is useful, even if you don't think that
[00:11:55] the flat information hierarchies are
[00:11:57] more performant for making sure that the
[00:11:59] best ideas are the ones that always win.
[00:12:02] This is great because now we have simple
[00:12:04] multi-agent communication on different
[00:12:06] devices, okay? And whenever we need to,
[00:12:08] you know, let me just be clear about
[00:12:09] this. Whenever we need to, I can add an
[00:12:11] agent to the pool. So, if I type J
[00:12:12] Comms, let's use four, I think that's
[00:12:15] the GLM agent. You can see GLM added
[00:12:17] here, and now it is part of the pool,
[00:12:19] right? So, fantastic. How else can we
[00:12:21] use this? Agent-to-agent communication,
[00:12:23] it seems very powerful. We're not just
[00:12:24] delegating work, which is in its own
[00:12:26] right a very powerful communication
[00:12:28] pattern, right? This isn't a
[00:12:29] replacement. This is another option for
[00:12:31] your agentic engineering. We can solve
[00:12:33] other problems with it, right? Let let
[00:12:35] let's walk through another example.
[00:12:41] So, let's fire up a E2B agent. And in
[00:12:45] fact, let's open up a new project here,
[00:12:47] sandbox. Same deal, J Comms 2, and name
[00:12:51] EXC dev agent project sandbox. So, we're
[00:12:55] just getting our agents off this
[00:12:57] network. This is a different pool to
[00:12:59] communicate in, right? So, we still
[00:13:00] still have our previous set there. And
[00:13:01] you can actually see that this work here
[00:13:03] was done. PII is safe. All the findings
[00:13:06] are there. So, we verified by having our
[00:13:08] production agent prompt our developer
[00:13:10] agent. Fantastic. There we got the pass.
[00:13:11] Everything looks great. Both context
[00:13:13] windows are sharp and focused. There's
[00:13:15] no spillover between issues. This system
[00:13:18] has completed successfully. So, I've
[00:13:20] been using the E2B agent sandbox tool
[00:13:23] for quite some time now. It's been a
[00:13:24] great tool. It's also expensive, and it
[00:13:26] has some downsides like there's a limit
[00:13:28] to the total duration that you can have
[00:13:30] your agents up in a sandbox. You have to
[00:13:32] pause them to manage that. So, I've been
[00:13:34] looking at exe.dev as a new agent
[00:13:37] sandbox tool to replace or use
[00:13:40] additionally right next to e2b. And so,
[00:13:43] this is another agent sandbox tool. It's
[00:13:44] got a couple of different benefits. I'll
[00:13:46] link both of these in the description
[00:13:48] for you. But, the idea here is I already
[00:13:50] have my e2b agent in this sandbox skill,
[00:13:53] right? So, I have agent sandboxes and
[00:13:54] this is my e2b skill where I can just
[00:13:56] quickly spin up an agent sandbox that my
[00:13:59] agent can fully own and operate on my
[00:14:01] behalf. We've talked about agent
[00:14:02] sandboxes on the channel in the past.
[00:14:04] I'll link those in the description for
[00:14:05] you as well. But, what I want to do here
[00:14:07] is spin up a brand new skill for exe.dev
[00:14:11] that mirrors and matches and has feature
[00:14:14] parity to my e2b agent skill. And
[00:14:16] anything that doesn't match, I want to
[00:14:18] know about it, right? I want to
[00:14:20] understand the feature differences, but
[00:14:22] I want my agent to fail forward. the
[00:14:24] skill to be built so that I can
[00:14:26] prototype and experiment with it right
[00:14:27] away, okay? So, I don't just want a
[00:14:29] simple research comparison. I want a new
[00:14:31] skill I can use that has feature parity
[00:14:34] with my existing skill. That's exactly
[00:14:35] what I'm going to prompt here. In my e2b
[00:14:37] agent, I'm going to fire this off.
[00:14:38] You're the e2b agent. Your teammate is
[00:14:41] exe.dev. They'll be building this skill
[00:14:44] against exe.dev's persistent VM
[00:14:47] platform. Your job is to answer their
[00:14:48] questions, okay? So, we have a teammate
[00:14:51] set up specifically to understand this
[00:14:53] feature set. It's putting up a sandbox.
[00:14:55] It's reminding itself of all the
[00:14:56] features. And when this completes, I'm
[00:14:58] going to kick off the exe.dev agent to
[00:15:01] communicate, work with, and sync up a
[00:15:04] brand new skill. You know, a lot of the
[00:15:06] agent-to-agent communication and
[00:15:07] multi-agent orchestration comes down to
[00:15:09] expanding your context window in a
[00:15:11] useful way such that your agents can
[00:15:14] specialize what they're focused on,
[00:15:16] okay? A lot of engineers do think that
[00:15:18] you just throw everything in one agent,
[00:15:19] wait for for models to get better, wait
[00:15:21] for that 5 million contacts window, and
[00:15:23] then all your problems will be solved. I
[00:15:25] don't agree with this approach at all. I
[00:15:27] think you should lean on the models, you
[00:15:29] should expect them to get better, you
[00:15:30] should plan for that in your products
[00:15:32] and services, but at the same time you
[00:15:33] should be learning how to focus your
[00:15:35] agents on one problem so that the chance
[00:15:38] that they cause an issue, so that the
[00:15:39] chance something goes wrong drops down
[00:15:42] to near zero. And how can you do that?
[00:15:44] You can do that by having focused
[00:15:46] context windows, okay? And by
[00:15:48] effectively specializing your agent to
[00:15:50] focus on one problem and one problem
[00:15:53] only. Spinning up and comparing two
[00:15:55] different tools with likely very similar
[00:15:57] APIs is going to get the context window
[00:15:59] pretty big. You can see here this agent
[00:16:01] is loading, refreshing itself on all of
[00:16:04] the E2B agent skill functionality,
[00:16:06] right? You can see sandbox remove,
[00:16:08] download dir, so on and so forth. We're
[00:16:10] almost at 10% context already. That's
[00:16:11] 100k tokens, okay? If you're using
[00:16:14] agents on a daily basis, you understand
[00:16:16] this fact, right? A focused agent is a
[00:16:18] performant agent. you add to that
[00:16:20] context window, the higher the chance
[00:16:23] something goes wrong is. Specifically,
[00:16:25] when you start muddying unrelated
[00:16:27] context together, okay? This is the art
[00:16:30] of context engineering. It's not just
[00:16:32] getting all the right things, it's
[00:16:33] getting just the right things. This
[00:16:36] agent's booting up, it should be
[00:16:37] complete pretty soon here, and then we
[00:16:39] can prompt our exe.dev to create this
[00:16:42] new skill so that we can boot up brand
[00:16:45] new sandboxes for exe.dev, and we can
[00:16:48] really see what this is all about.
[00:16:50] Moving forward, it's not just about
[00:16:51] these two sandbox tools, right? It's
[00:16:52] about every sandbox tool moving forward
[00:16:55] and our ability to deploy agents to
[00:16:57] understand the tools, to understand the
[00:16:59] technology, and then deploy them into
[00:17:01] valuable use cases on our behalf. So, we
[00:17:04] can use this system over and over and
[00:17:05] over, we can compare the features
[00:17:07] between every specialized agent. I hope
[00:17:09] you get the point, right? If this is all
[00:17:11] making sense, you know, make sure you
[00:17:12] drop a like. This is like really our
[00:17:13] bread and butter on the channel. We're
[00:17:15] scaling our compute to scale our impact.
[00:17:18] It's all about scaling up what our
[00:17:20] agents can do and focusing our agents to
[00:17:22] solve real business problems on our
[00:17:24] behalf via agentic engineering, not vibe
[00:17:27] coding. We're not shooting prompts and
[00:17:29] not looking. We know what our agents are
[00:17:31] doing, okay? And this just stacks up on
[00:17:34] previous videos we've had on the channel
[00:17:36] where we're making our agents secure.
[00:17:38] We're not letting them crush production
[00:17:40] assets when they should not be able to.
[00:17:42] We're adding security to our bash tool
[00:17:44] when they need it. Just like in last
[00:17:47] week's video, we're preventing
[00:17:48] catastrophic commands from running. And
[00:17:50] then, you know, we're letting our agents
[00:17:52] rip on all the tools, all the skills,
[00:17:54] all the commands that we actually want
[00:17:56] our agents to execute, right? As you can
[00:17:58] see here, a lot of that sandbox tool
[00:18:00] running, our agent is understanding what
[00:18:02] it can do here. And soon it's going to
[00:18:03] write this uh presentation file for us.
[00:18:06] And this is one of the great things and
[00:18:07] one of the annoying things about GPT
[00:18:09] 5.5. This model really chews up tokens
[00:18:12] and it just goes and goes and goes to
[00:18:13] really get you the most comprehensive
[00:18:16] result possible. Whereas, I found that
[00:18:18] Opus 4.7 will do that as well, but it
[00:18:20] also will really just focus on the goal,
[00:18:23] right? I think Opus is more
[00:18:25] goal-oriented and really focuses on
[00:18:27] accomplishing the goal. If you prompt it
[00:18:29] wide enough to capture more of that
[00:18:31] state, more of that scope, it'll
[00:18:32] certainly capture that as well, okay?
[00:18:34] But here we go. We're getting that
[00:18:35] inventory file that really compresses
[00:18:37] all the observations. Now, we should be
[00:18:39] able to kick off our exe.dev agent
[00:18:41] pretty soon here. There we go. Nice
[00:18:43] write-up. Look at that detailed write-up
[00:18:45] of all the features, inputs, and
[00:18:47] outputs, the commands, E2B quirks,
[00:18:49] right? This is great. And this was part
[00:18:50] of the prompt, right? We wanted at the
[00:18:52] end a feature inventory. And this is
[00:18:54] going to allow our exe.dev agent to
[00:18:57] really map everything out one-to-one.
[00:18:59] And again, like focus context is so
[00:19:01] important here, right? In tactically
[00:19:03] agentic coding, it's so important. This
[00:19:05] is an entire tactic. We talk about this
[00:19:06] for an entire lesson. A focused agent is
[00:19:09] a performant agent. We have 20% context
[00:19:12] of the 1 million context window GPT 5.5
[00:19:15] focus on just understanding this tool
[00:19:17] and understanding this skill and this
[00:19:19] whole sandbox system. Okay, so there you
[00:19:22] go. Validating its work, making sure
[00:19:23] that that file exists and now we're
[00:19:25] going to boot up our exe.dev agent.
[00:19:27] There we go, perfect. So, it's all
[00:19:29] primed, it's all good to go. Now we're
[00:19:30] going to fire off this prompt inside of
[00:19:32] our exe.dev agent. I actually haven't
[00:19:34] run this before so I'm really curious to
[00:19:36] see how how this executes and how well
[00:19:38] this mirrors. So, you're the exe.dev
[00:19:40] agent. There is no agent sandbox exe.dev
[00:19:42] skill yet. Your job is to build one.
[00:19:44] Okay, so there's the purpose and then
[00:19:46] your reference target is this existing
[00:19:48] skill here which your teammate
[00:19:50] understands is already standing by to
[00:19:52] answer questions about. You're the
[00:19:53] driver of this collaboration. E2B will
[00:19:55] not initiate, you reach out. So, I'm
[00:19:57] setting this up so that in this specific
[00:19:58] scenario, I want my exe.dev agent to be
[00:20:01] the one driving this. I'm giving it a
[00:20:02] couple skills, fire crawl, meta skill to
[00:20:04] really build on this and then we have
[00:20:06] our clear deliverable. So, I want that
[00:20:09] new skill, right? And I'm making it
[00:20:10] super clear here, a new working skill
[00:20:12] that mirrors the {slash} agent sandbox
[00:20:14] is against exe.dev primitives and I also
[00:20:17] want a feature parity document just like
[00:20:20] the E2B agent has as well for us, okay?
[00:20:22] And so, it's starting to get to work
[00:20:23] here. Grabbing all the docs, it's going
[00:20:25] to start building this skill and this is
[00:20:26] the Opus 4.7 running in the Pi agent
[00:20:28] harness. This is going to be some pretty
[00:20:30] fantastic results as this gets to work
[00:20:32] here. So, right now it's gobbling up all
[00:20:34] the documentation, starting to stack up
[00:20:36] that proper context and at some point
[00:20:38] here it's going to begin again, it's
[00:20:40] communicating with our exe.dev agent
[00:20:43] here. So, there it is, we have live
[00:20:44] access confirmed, SSH exe.dev. It's now
[00:20:48] checking out all my VMs, no current VMs
[00:20:50] set up yet but my agent is going to go
[00:20:52] through this process, figure everything
[00:20:54] out and it has all the documentation and
[00:20:56] it has the feature parity it's trying to
[00:20:58] get equal to, okay? So, this is a really
[00:21:00] great way to in general, you know, it
[00:21:02] doesn't really matter what agent agent
[00:21:03] communication system you're using, this
[00:21:05] is a great way to mirror systems
[00:21:07] together, right? In the age of agents,
[00:21:09] we're going to have a hundred different
[00:21:10] services available to us for agent
[00:21:12] sandboxing and frankly, you know, for
[00:21:14] agent harnessing, cloud databases,
[00:21:16] Turso, things like Neon DB, and a lot of
[00:21:18] them are going to be swappable, right?
[00:21:20] Composable. And so, this is a great
[00:21:22] pattern. Once you have one skill against
[00:21:24] one specific service, you can quickly
[00:21:26] create a feature parity document and
[00:21:28] then build directly against another
[00:21:30] service. Asian agent communication is a
[00:21:32] great way to do that because you get
[00:21:33] that focused agent context window and
[00:21:35] then your agent can just quickly
[00:21:37] communicate when they need to. But let's
[00:21:38] go ahead and dig a little bit deeper
[00:21:40] into this system, right? Like how does
[00:21:41] this system really work? There's four
[00:21:42] tools here. There's basically no magic.
[00:21:44] It's really simple.
[00:21:50] You list all the agents on the network,
[00:21:53] send command, or you send the prompt,
[00:21:55] and then optionally, you can await a
[00:21:58] response, right? Sometimes you send off
[00:22:00] a Slack message and you're just sending
[00:22:02] useful information to someone or a
[00:22:03] confirmation or something, and that's
[00:22:05] it. But if you need to, you can await
[00:22:07] the response. You can check in on the
[00:22:09] message. You can do a block wait or you
[00:22:11] can do a non-blocking poll. I have two
[00:22:13] versions of this. It's going to be
[00:22:14] available to you. You can see our agents
[00:22:16] are starting to chat together here. I'll
[00:22:18] have two versions of this available to
[00:22:19] you. Both are going to be available in
[00:22:21] the Pi versus Cloud Code code base.
[00:22:25] This is a code base that has been live
[00:22:27] for quite some time and it's where I
[00:22:29] posted and shared a lot of extensions
[00:22:32] from simple to complex cross multiple
[00:22:34] different agent harness use cases for
[00:22:36] the Pi agent harness, all right? And so,
[00:22:39] the whole idea here is just to hedge
[00:22:40] against Cloud Code, the agentic coding
[00:22:43] market leader, and get control of the
[00:22:45] agent harness. This code base builds on
[00:22:47] that very idea and I'm going to add
[00:22:49] these two extensions for you into this
[00:22:52] code base. And so, you know, what are
[00:22:53] these two extensions? We can just go
[00:22:54] ahead and crack these open here. Coms
[00:22:56] version, so this is the non-network
[00:22:58] version. This operates on a single
[00:23:00] device. But then we have a coms net
[00:23:01] where we basically boot up a simple
[00:23:04] simple simple lightweight bun server
[00:23:06] here that accepts requests over the
[00:23:09] network. And you can imagine we have a
[00:23:10] simple set that let the agent connect,
[00:23:13] get messages, list agents, process
[00:23:16] events, so on and so forth here, right?
[00:23:17] This is a very simple implementation.
[00:23:19] Secure it, make it more legitimate for
[00:23:21] your specific use case. Every piece of
[00:23:23] code you see now, I really think it's
[00:23:25] really about read and adapt, right?
[00:23:27] Through your agents add it and have them
[00:23:29] transform it for your specific use case.
[00:23:31] And always understand the code. 25% here
[00:23:34] on our E2B agent. See, it just responded
[00:23:37] directly here. Kind of looks good.
[00:23:39] Browser. Okay, SBX tool. Nice. So, it
[00:23:42] looks like exi.dev agent was asking
[00:23:44] about the browser tool. All three
[00:23:46] questions cleanly answered. Quick recap.
[00:23:49] Templates versus images. Okay, so
[00:23:51] confirm partial support. Let's see.
[00:23:53] Captured artifacts, arbitrary container
[00:23:56] images. Okay. Browser, two primary
[00:23:58] files, zero E2B import fix, drop in
[00:24:01] portability. Great. Snapshot, no E2B
[00:24:03] equivalent. CP is unique to exi.dev.
[00:24:07] Okay. So, there we go. Here he's writing
[00:24:09] that feature parity doc. This is looking
[00:24:11] great. Yeah, nice. Looks like we had a
[00:24:12] couple chats here to showcase
[00:24:15] everything. Sent this to E2B. Why now?
[00:24:17] The parity has their claims is to flag
[00:24:20] as many E2B claims that's wrong before I
[00:24:21] bake them into the new skill. Very cool.
[00:24:23] Okay. Very nice. So, our agents here are
[00:24:25] doing the work that I would do myself,
[00:24:28] which is validate the claims, right?
[00:24:31] This is something we talked about in the
[00:24:32] verifier agent video we did a couple
[00:24:33] weeks ago where you have an agent
[00:24:35] basically double-checking all the claims
[00:24:38] and all the statements that the primary
[00:24:40] agent is making to make sure that
[00:24:42] they're right. This is a really powerful
[00:24:43] pattern. I like to run my Pi agents, my
[00:24:45] primary Pi agent with a validator on top
[00:24:48] of it, which basically, you know,
[00:24:49] increases the tokens used, but in
[00:24:51] exchange it saves me time because the
[00:24:53] validator is validating everything my
[00:24:55] agent just said, right? It makes sure
[00:24:57] that everything it said is actually
[00:24:59] true. And then it also makes sure that
[00:25:00] the work it said it did is exactly what
[00:25:02] was done. I'll link that in the
[00:25:03] description as well. There we go.
[00:25:05] There's a nice write back to our
[00:25:07] eexi.dev agent. It's like it's asking
[00:25:09] for a recursive flag there, too. Wow, so
[00:25:12] much detail here. Like in the side here,
[00:25:14] this is a great way to just watch these
[00:25:15] models work together, right? GPT-5.5,
[00:25:18] Claude 4.7, gave them a decent size
[00:25:20] prompt, maybe 80 lines each, and a
[00:25:23] skill, and now they're just like hashing
[00:25:25] it out, recreating this new skill. And
[00:25:28] this is again just one of millions and
[00:25:30] millions of different ways to coordinate
[00:25:33] agents to work toward a goal, to work
[00:25:36] toward something, right? So, okay, so we
[00:25:37] got 10 corrections from that exchange,
[00:25:39] right? This is a valuable exchange of
[00:25:41] information. 10 corrections. There's a
[00:25:43] couple comments in my videos recently,
[00:25:44] especially when I talk about multi-agent
[00:25:46] orchestration, some engineers, probably
[00:25:48] a decent amount of vibe coders as well,
[00:25:49] asking, "Why can't you just do all this
[00:25:51] in one agent?" You certainly can. You
[00:25:54] certainly can. But you have to remember
[00:25:56] that couple things. There is a limit to
[00:25:57] the context window. The more problems,
[00:25:59] the more different problems, APIs,
[00:26:02] systems you put into that context
[00:26:03] window, your error rate will go up.
[00:26:05] Okay, this is just a fact. If you don't
[00:26:07] believe that, you don't understand that,
[00:26:08] do more research on the context window,
[00:26:10] okay? And then second, with every unique
[00:26:13] model that you add to your system,
[00:26:15] right? I'm running Claude right next to
[00:26:17] GPT-5.5. These models are trained in a
[00:26:19] completely different way. They have
[00:26:20] different RL loops running on top of
[00:26:22] them. Putting these agents together
[00:26:24] creates something greater. It creates a
[00:26:26] system that outperforms either of them
[00:26:29] alone. Just like code plus agent beats
[00:26:31] either alone, unique agent one plus
[00:26:33] unique agent two communicating beats
[00:26:35] either alone, right? And and that's like
[00:26:39] really the gift and really the value
[00:26:40] proposition of multi-agent
[00:26:42] orchestration. It's not just the 10
[00:26:44] parallel agents you boot up to like
[00:26:46] write all those files or generate all
[00:26:48] those images at the same time. It's
[00:26:50] doing serious engineering work where
[00:26:51] your agents are checking in on each
[00:26:53] other, double checking the work,
[00:26:54] coordinating on a solution, so on and so
[00:26:56] forth, okay? So, that's the idea. And
[00:26:58] so, we got one more message coming back
[00:26:59] here. Hopefully, this wraps it up. And
[00:27:01] yeah, look at this like Opus is just
[00:27:03] being really, really great here with the
[00:27:05] verification. So, please reread the doc
[00:27:07] and either send review complete or flag
[00:27:10] remaining issues. All right, so this is
[00:27:11] just like, you know, it's teamwork,
[00:27:14] right? This is teamwork, okay? Sign off
[00:27:16] one non-blocking knit, okay? And then
[00:27:19] after this, we can proceed with uh
[00:27:21] scaffolding. So, there we go. So, yeah,
[00:27:23] it's loading that meta skill. This is my
[00:27:25] skill that helps me create skills. I'm
[00:27:27] going to let this cook. Comment down
[00:27:28] below if you're interested in my agent
[00:27:31] sandbox skills, the E2B skill, or this
[00:27:33] new exa.dev skill, and I'll add it to
[00:27:35] this codebase. But, that's the idea,
[00:27:38] right? It's it's it's simple, yet it's
[00:27:40] very, very important, okay? Now, you
[00:27:42] know, quickly just talking about pros
[00:27:44] and cons of this system. Every system
[00:27:46] has pros and cons. If you don't address
[00:27:48] them, you'll be exposed to them.
[00:27:55] What are the pros here? It's just an
[00:27:57] agent, right? I just can at any time now
[00:27:59] boot up two agents, three agents, five
[00:28:02] agents on my device, my Mac mini, my M4,
[00:28:05] right? My cloud VMs, all my services,
[00:28:07] all my servers. I can just boot up an
[00:28:09] agent now with the extension, have them
[00:28:11] connect, have them talk to each other.
[00:28:13] It's just an agent. It's that simple. As
[00:28:15] you say, it's just an agent and
[00:28:17] extension. It's permanent, okay? There's
[00:28:19] no you know, no subagent delegation, no
[00:28:22] spin-up or spin-down, no resume. Claude
[00:28:25] has this resume flag where you can
[00:28:27] reboot the agent. These are just agents
[00:28:29] in the terminal. That's it, right? Uh
[00:28:30] customizable, right? End-to-end.
[00:28:32] Obviously, this is like a key value prop
[00:28:34] of why I keep talking about the Python
[00:28:36] coding agent and why I keep bringing it
[00:28:38] up. The the state space of agentic
[00:28:40] engineering is unknown. You know, the
[00:28:42] way I see this is only uh 1% of it has
[00:28:45] been discovered and understood and
[00:28:47] deployed into production, right? I
[00:28:49] talking like really, really low numbers
[00:28:50] here. Customization and extensibility is
[00:28:52] core to the future of agentic engineers.
[00:28:56] And so, this tool becomes more and more
[00:28:58] important to me every single day. The
[00:28:59] tool you use limits what you believe is
[00:29:01] possible. And with the pie agent
[00:29:03] harness, I see no limits. You know, all
[00:29:07] the limitations of of how things work,
[00:29:10] they're just falling away. I don't see
[00:29:12] the same workflows. I don't see the same
[00:29:14] implementations anymore. And I think if
[00:29:16] you're stuck using one agentic coding
[00:29:17] tool, especially one that tells you how
[00:29:19] to do everything, hint hint Claude code,
[00:29:21] hint hint Codex, hint hint, you know,
[00:29:22] Gemini C alive if anyone's using that,
[00:29:24] open code, like whatever it is, right?
[00:29:26] You are not getting, you know, you're
[00:29:27] not pushing into that 99% the rest of
[00:29:30] the value that we can unlock with
[00:29:32] agents, with the right agentic
[00:29:34] technology, okay? So, um that's a big
[00:29:36] one, obviously, right? Uh bidirectional
[00:29:38] comms are flat. No hierarchy, right? No
[00:29:41] information loss. No one agent to rule
[00:29:45] them all, which is a con in another way,
[00:29:48] right? We've talked about the one agent
[00:29:49] to rule them all, the orchestrator.
[00:29:51] Let's be super clear about this. This is
[00:29:52] the orchestrator. Um
[00:29:54] and this is like the current wave of
[00:29:56] multi-agent orchestration. This is super
[00:29:57] powerful. It's a great pattern. I'm
[00:29:59] going to continue to use it, but um
[00:30:01] bidirectional is great cuz it's flat,
[00:30:03] it's two-way, no information gets lost,
[00:30:05] right? Um another great part about this
[00:30:07] is that uh this is a primitive over
[00:30:09] composition approach, right? Once again,
[00:30:11] this kind of ties back into that first
[00:30:12] idea. This is just an agent. It's just a
[00:30:15] pie coding agent, right? Or just
[00:30:17] simplify it, right? Let's not hyper
[00:30:19] fixate on pie, right? This is just an
[00:30:21] agent. I just open up an agent, and then
[00:30:22] I can compose as many agents as I want
[00:30:25] to, okay? So, once again, we're
[00:30:26] engineering. Composition is an
[00:30:28] engineering pattern. We're creating
[00:30:29] slices of things we can combine to make
[00:30:32] something bigger, right? Primitives into
[00:30:34] compositions. But you want the primitive
[00:30:35] first so that you can compose it. That's
[00:30:38] enough glaze. Uh let's go to cons. Uh
[00:30:40] you have to build this yourself or get
[00:30:42] it from any dev Dan for free. Link in
[00:30:45] the description.
[00:30:47] But, you know, you know what I mean,
[00:30:48] right? You have to build this, you have
[00:30:49] to vet this, you have to control the way
[00:30:51] your agents communicate. You need to
[00:30:52] prompt engineer everything, contact
[00:30:54] engineer thing everything, and you need
[00:30:55] to deal with the the cases, right? The
[00:30:57] edge cases is where really where great
[00:31:00] agentic engineering patterns are made,
[00:31:02] and great products in general, right?
[00:31:03] Another con here, loops are possible if
[00:31:06] prompts are sloppy, right? So, you can
[00:31:08] you can really generate some bad loops
[00:31:10] that that are going to really chew up
[00:31:11] your token usage if your prompts are
[00:31:13] sloppy, right? You need an end state,
[00:31:14] right? Let's see if our agents have hit
[00:31:16] their end state yet. Okay, great. So,
[00:31:17] yeah, so we are approaching the end
[00:31:19] state, right? My agent is making
[00:31:21] progress. It is creating this agent
[00:31:23] sandbox EXE dev skill. Okay, so that's
[00:31:25] great. So, this prompt obviously was not
[00:31:27] sloppy. I don't write very a ton of
[00:31:29] sloppy prompts anymore, but this is a
[00:31:31] risk of this strategy, right? And then
[00:31:32] there's just like general costs, right?
[00:31:34] Cost scales linearly with agent count
[00:31:37] plus communication bounce. And so, there
[00:31:40] a bunch of laws around the perfect
[00:31:42] number of actors to have in a team,
[00:31:44] right? Inside of your communication
[00:31:45] channel. That's kind of what this, you
[00:31:46] know, showcases, right? There's some
[00:31:48] magical number, Dunbar's number, or
[00:31:50] something. I wouldn't worry about that
[00:31:51] too much. I would just worry about like,
[00:31:53] what's useful? How can I deploy
[00:31:54] bidirectional agents, bidirectional
[00:31:56] peer-to-peer agents that it's actually
[00:31:58] useful across devices, or on the same
[00:32:01] device, right? The key here is
[00:32:02] peer-to-peer. And just make it as useful
[00:32:04] as possible. If you find that three
[00:32:05] agents, 10 agents, whatever is too much,
[00:32:07] then just trim them. So, it's not a huge
[00:32:09] con, but it's important to uh take into
[00:32:11] account, right? And I think the last con
[00:32:13] is, be careful not to just fall back
[00:32:16] into the orchestration pattern. Unless
[00:32:18] you need it, right? If you need
[00:32:19] orchestration pattern, just build that.
[00:32:20] This is kind of nice though still cuz
[00:32:22] you can compose peer-to-peer agent
[00:32:24] communication back into a orchestration
[00:32:27] pattern where you have more of a
[00:32:28] top-down format where one agent's
[00:32:30] leading the rest. That's fine, too,
[00:32:32] right? As I mentioned, you know, we're
[00:32:34] exploring the state space of what's
[00:32:35] possible. This is equally as valuable,
[00:32:37] but peer-to-peer's advantage is that it
[00:32:40] is flat and there's no hierarchy, right?
[00:32:43] That's the advantage, right? Your agents
[00:32:44] are working together. It's not a
[00:32:46] delegation stream. So, these are some of
[00:32:48] the pros and the cons of this system. I
[00:32:49] think it's important to address the
[00:32:50] upside and the downside, right? Again,
[00:32:52] if you're doing engineering, you need to
[00:32:53] address both of them. So, this is yet
[00:32:54] another multi-agent orchestration system
[00:32:57] that you can use to push what you can do
[00:32:59] with your agents in the age of agents,
[00:33:01] right? And the goal is the same. We're
[00:33:02] not really changing We're not doing
[00:33:04] anything new here on the channel. What
[00:33:06] we are doing week after week is we're
[00:33:07] increasing trust and scale of our
[00:33:10] agentic systems. All right? You can see
[00:33:12] this final reviews coming in. This is
[00:33:14] coordinated agents working together,
[00:33:16] double-checking their work. And you can
[00:33:17] see here our tokens are starting to
[00:33:19] stack up. We have 2 million available,
[00:33:22] but it's split in half. One is focused
[00:33:24] on exe.dev, one is focused on e2b, but
[00:33:27] our agents are still coordinating on the
[00:33:29] same information. We're making sure that
[00:33:31] we're hitting feature parity. We're
[00:33:32] making sure that everything looks good.
[00:33:33] Of course, I'm going to run more tests
[00:33:35] on this and make sure that this looks
[00:33:36] good, but I can almost guarantee you
[00:33:37] this is going to work out of the box
[00:33:39] because I had two agents two
[00:33:40] state-of-the-art agents working together
[00:33:42] to get this shipped out. Enabling
[00:33:44] specialized agents that chat together on
[00:33:46] device and across devices is a unique
[00:33:48] advantage you can add to your agentic
[00:33:51] systems, specifically to your agent
[00:33:53] harness. This pattern and patterns like
[00:33:55] this more and more of these patterns are
[00:33:56] going to emerge. They're impossible if
[00:33:59] you're using, you know, the
[00:34:00] out-of-the-box agents from Anthropic,
[00:34:03] from OpenAI, from Google. It's
[00:34:04] impossible when you're renting your
[00:34:06] agent harness, okay? To be clear, I
[00:34:08] still use Claude Code all the time. It's
[00:34:10] a great tool. I'm going to continue to
[00:34:11] use it, but more and more I'm reaching
[00:34:13] for the Pi agent harness to build the
[00:34:14] exact experience and products that I'm
[00:34:17] looking for, right? And this pattern
[00:34:19] adds to that bag of tricks that you and
[00:34:21] I can now deploy in our agent harness if
[00:34:24] you own your agent harness. I'm going to
[00:34:26] be adding these two extensions to the Pi
[00:34:28] versus Claude Code codebase here
[00:34:30] available to you, link in the
[00:34:32] description. I'm really excited for some
[00:34:34] of the big ideas I have to share with
[00:34:35] you here on the channel coming up. I'm
[00:34:37] waiting for that next Gemini model
[00:34:39] launch to really showcase one of these
[00:34:40] next-gen patterns. So, make sure you
[00:34:42] like, make sure you subscribe, join the
[00:34:43] journey so you don't miss that. You know
[00:34:45] where to find me every single Monday.
[00:34:47] Stay focused and keep building.
