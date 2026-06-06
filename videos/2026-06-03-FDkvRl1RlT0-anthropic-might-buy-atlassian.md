---
video_id: FDkvRl1RlT0
title: "Anthropic Might Buy Atlassian For $40B. Here's Why It Makes Sense."
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=FDkvRl1RlT0"
watched_date: 2026-06-03
watched_at: "2026-06-03T12:00:00Z"
watch_count: 1
duration_seconds: 1747
source: youtube-history-browser
history_label: Wednesday
history_order: 57
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1747
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video argues that issue trackers like Jira and Linear—originally designed for human coordination—have become critical infrastructure for AI agents. These tools provide exactly what agents need: durable state outside context windows, explicit ownership and permissions, state machines, audit history, and coordination mechanisms. While the human experience of manually grooming tickets is decreasing, the underlying substrate is becoming *more* valuable, not less. This pattern extends beyond issue trackers: CRMs, service desks, ERPs, calendars, and source control systems all function as agent infrastructure because they encode structured work, permissions, and history. Atlassian's Jira and Confluence are particularly strategically positioned since they own the largest installed base of agent-readable work state in the enterprise.

To prepare for agent-driven operations: **Builders** should expose clean data models and verbs through APIs/MCP servers rather than bolting AI chatbots to UIs. **Teams** should recognize that your work-tracking choice (Jira vs. Linear) is now an agent infrastructure decision—clean, structured work data directly enables agent capability. **Leaders** should treat your current operational systems as repricing infrastructure; ensuring ownership is current, status fields are meaningful, and work is consolidated (not spread across Slack threads and spreadsheets) is now AI readiness. Evaluate tools by their structural qualities—records, state machines, explicit ownership, defined verbs, queryable history—not by AI feature checklists.

## Transcript

[00:00:00] This is the story of one of the most
[00:00:01] surprising software categories of 2026.
[00:00:04] And I'm talking about the issue trackers
[00:00:06] that are the substrate for AI agents now
[00:00:09] and were never built to be that. They
[00:00:11] weren't. Sometimes the programs we build
[00:00:13] for ourselves turn out to be
[00:00:15] accidentally useful to agents. I think
[00:00:16] it's one of the most fascinating stories
[00:00:18] of 2026 and they weren't ever designed
[00:00:21] for AI. They still aren't. They became
[00:00:23] useful because they happened to encode
[00:00:25] something that agents desperately need
[00:00:27] like state, like ownership, like
[00:00:29] permissions or history, or even a clean
[00:00:31] idea of what should happen next. Issue
[00:00:33] trackers is my favorite example. It's
[00:00:36] the most boring software in the
[00:00:37] engineering stack. I'm not going to
[00:00:38] pretend to you it's exciting. It's the
[00:00:40] thing people complain about. It's Jira,
[00:00:42] right? It's the thing that feels like
[00:00:44] process overhead, the thing everyone
[00:00:45] wants to make simpler and lighter and
[00:00:47] invisible. And yet, the issue tracker is
[00:00:50] quietly becoming one of the most
[00:00:51] important pieces of agent infrastructure
[00:00:53] out there right now. Because if you want
[00:00:55] agents to do real work, the hard part is
[00:00:57] not just making the model smarter. The
[00:00:59] hard part is giving the agent a place to
[00:01:01] find the work, a place to understand who
[00:01:03] owns the work, to know what state it's
[00:01:05] in, to see what changed, to ask for a
[00:01:07] review, and to hand the result back.
[00:01:08] That's exactly what issue trackers were
[00:01:11] built to do for people. They were built
[00:01:13] for handoffs, for memory, for
[00:01:14] accountability, for dependencies, for
[00:01:16] review. And by accident, those are
[00:01:18] almost exactly the things agents need.
[00:01:20] And that is why one small product story
[00:01:22] from the last month matters a lot more
[00:01:24] than it looks. Linear CEO published a
[00:01:26] letter saying issue tracking is dead.
[00:01:29] And just a little over a month later,
[00:01:31] OpenAI published Symphony, an
[00:01:33] open-source Codex orchestration spec
[00:01:35] whose central idea is to use an issue
[00:01:37] tracker, specifically a Linear board, as
[00:01:39] the control plane for autonomous coding
[00:01:41] agents. That is the entire contradiction
[00:01:44] of this space in 2026. The issue
[00:01:46] tracking experience might be dying, the
[00:01:48] issue tracking substrate is getting
[00:01:51] promoted. The old habit of humans
[00:01:53] manually translating messy reality into
[00:01:55] tickets, that's absolutely under
[00:01:57] pressure. But the underlying structure
[00:01:59] of the issue tracker, the state machine,
[00:02:02] the assignee field, the audit trail, the
[00:02:04] dependency graph, it's all underneath
[00:02:05] that UI, that's becoming more valuable,
[00:02:08] not less. And once you see why issue
[00:02:11] trackers work for agents, you can start
[00:02:13] spotting the same pattern in a lot of
[00:02:14] other places. CRMs, service desks, ERPs,
[00:02:18] calendars, source control, HR systems,
[00:02:20] finance systems, a lot of the programs
[00:02:23] we've already written are more agent
[00:02:25] useful than they look. And so this
[00:02:27] video, yeah, it's about issue trackers,
[00:02:29] but it's also about a much larger
[00:02:30] question. Which boring tools did we
[00:02:33] accidentally build that agents are going
[00:02:35] to need? And I want to walk through four
[00:02:36] pieces of that. First, why agents need
[00:02:38] something that looks suspiciously like
[00:02:40] an issue tracker. Second, why the boring
[00:02:42] infrastructure we built for human
[00:02:43] coordination turns out to fit agent
[00:02:45] coordination almost perfectly. Third,
[00:02:47] why Atlassian, Linear, Salesforce,
[00:02:49] ServiceNow, and a bunch of unsexy
[00:02:51] enterprise tools are suddenly sitting on
[00:02:53] something much more strategic than
[00:02:54] people realized. And fourth, how to tell
[00:02:57] which tools in your company are going to
[00:02:58] become that kind of agent infrastructure
[00:03:00] and which ones are going to get wrapped
[00:03:02] up or replaced. But the short version is
[00:03:04] this, the boring tools are winning in
[00:03:07] 2026. The really interesting question
[00:03:09] now is which boring tools win next and
[00:03:12] why. Let's go back to that Linear letter
[00:03:14] for a minute because the argument that
[00:03:15] Karri made was actually very reasonable.
[00:03:17] So on March 24th, uh Karri, the CEO of
[00:03:19] Linear, published a page called Issue
[00:03:21] Tracking Is Dead. And the basic idea was
[00:03:23] that issue trackers were built for a
[00:03:25] handoff model of software development.
[00:03:26] Uh they were built for a world where the
[00:03:28] product manager scopes the work and
[00:03:29] someone else writes the ticket and
[00:03:31] someone else picks it up later and the
[00:03:32] ticket moves through various statuses
[00:03:34] and people argue about priority and
[00:03:35] acceptance criteria and ownership and
[00:03:37] roadmaps and dependencies, whether
[00:03:39] something is a bug or a feature, and
[00:03:41] very slowly the system that was supposed
[00:03:43] to help the work becomes a big part of
[00:03:45] the work. This gets at what Linear was
[00:03:47] originally designed to solve and it is a
[00:03:49] real problem. And I want to emphasize
[00:03:52] that I have used both Linear and Jira. I
[00:03:54] see why we switched to Linear. Linear is
[00:03:57] fast, it's intuitive. I get why if
[00:03:59] you're using an issue tracker to solve
[00:04:01] this problem, you make the switch. But
[00:04:03] regardless of whether you've used Linear
[00:04:05] personally, you've probably used a
[00:04:06] ticketing system. If you've worked
[00:04:08] inside Jira or any heavily customized
[00:04:11] project management system, you know
[00:04:12] exactly what this feels like. The ticket
[00:04:14] ends up being a translation layer
[00:04:16] between reality and the team. A customer
[00:04:18] has a problem, a designer has an idea to
[00:04:20] solve it, an engineer sees a bug, a
[00:04:22] support person hears the same complaint
[00:04:24] five times. All of that messy context
[00:04:26] has to go somewhere. It gets It gets
[00:04:28] compressed into a record with a title
[00:04:30] and a description and an owner and a
[00:04:31] state and maybe a due date. That
[00:04:33] compression is useful, but it's also
[00:04:35] expensive. And so when Kari Saarinen was
[00:04:38] writing his essay, he pointed out agents
[00:04:40] change this picture. Agents can read
[00:04:42] more of the underlying context. They can
[00:04:44] look at raw customer feedback and
[00:04:46] internal discussion and product
[00:04:47] decisions at code at docs. They don't
[00:04:50] necessarily need a human to do as much
[00:04:52] of that translation step first. And
[00:04:54] Linear's answer is to become less like a
[00:04:56] place where people manually move tickets
[00:04:58] around and more like a shared product
[00:05:00] system where context turns into
[00:05:02] execution. Linear agent skills,
[00:05:04] automations, code intelligence, code
[00:05:06] depths, and eventually a coding agent
[00:05:08] that writes code and fixes bugs with
[00:05:10] native Linear context. That's the part
[00:05:12] where I think he's right. The interface
[00:05:13] is changing. The human ceremony around
[00:05:15] tickets is shrinking. The world where a
[00:05:17] person spends half their week turning
[00:05:19] messy reality into well-behaved tickets,
[00:05:21] that's not our end state anymore. But
[00:05:22] then, OpenAI published Symphony. And
[00:05:25] Symphony makes the opposite point just
[00:05:26] as clearly. Symphony says, "Take a
[00:05:28] project management board like Linear,
[00:05:30] read the tasks, create a dedicated
[00:05:32] workspace for every issue, run the
[00:05:34] agents continuously, and just let humans
[00:05:36] review the results." OpenAI says some
[00:05:38] internal team saw a 500% increase in
[00:05:41] landed pull requests when using this
[00:05:42] model. And the OpenAI spec actually does
[00:05:45] use Linear as the tracker of choice in
[00:05:47] their roll out of Symphony. So, Symphony
[00:05:49] defines polling, per issue workspaces,
[00:05:51] active and terminal states, retries,
[00:05:54] observability, concurrency limits, and
[00:05:55] handoff states, human review is an
[00:05:57] example handoff state. In other words,
[00:05:59] the issue tracker in the Symphony world
[00:06:01] did not die. It got promoted. It stopped
[00:06:04] being the only user interface for human
[00:06:06] coordination and became the data layer
[00:06:08] for agent coordination. And that
[00:06:09] distinction matters. That human
[00:06:10] translation step that Kari was talking
[00:06:13] about killing, that can die. But the
[00:06:15] underlying substrate of why we have
[00:06:18] issue trackers can get stronger at the
[00:06:19] same time. The part humans hated,
[00:06:21] manually grooming tickets and manually
[00:06:23] translating messy reality, can go away.
[00:06:26] Well, the part agents need, which is
[00:06:28] actually tracking stuff over time,
[00:06:30] becomes essential. And once you see
[00:06:31] that, once you see that distinction
[00:06:33] between what humans need and agents
[00:06:35] need, everything starts to look
[00:06:37] different. And once you have the core
[00:06:39] insight that agents need to work against
[00:06:41] a stateful ticketing system, you see the
[00:06:44] whole history of the issue tracking
[00:06:45] category differently. And the reason
[00:06:48] that's the case goes all the way back to
[00:06:49] 1998. Bugzilla was one of the first
[00:06:52] canonical issue trackers. Terry Weissman
[00:06:54] wrote it for Mozilla to replace the
[00:06:55] internal defect tracker that Netscape
[00:06:57] had been using. It was originally
[00:06:58] written in TCL and moved to Pearl with
[00:07:00] MySQL underneath. The first public
[00:07:02] deployment was in April of 1998. The
[00:07:05] important thing about Bugzilla is that
[00:07:06] it was narrow on purpose. The Bugzilla
[00:07:09] team explicitly said they wanted to
[00:07:10] focus on tracking software defects. They
[00:07:12] were not trying to build a general
[00:07:13] project management system or a support
[00:07:15] queue or a universal business process
[00:07:17] engine. They were just trying to solve
[00:07:19] one problem. When a lot of people are
[00:07:20] building software asynchronously, how do
[00:07:23] you make sure the bugs don't just
[00:07:24] disappear into the ether and never get
[00:07:26] worked on? And that narrow problem
[00:07:28] produced a very powerful shape. A bug
[00:07:30] had durable state outside anyone
[00:07:32] person's head. It was not in someone's
[00:07:34] inbox. It was not in a hallway
[00:07:36] conversation. It was a record in a
[00:07:37] database. It had a state machine. It
[00:07:39] could be new, assigned, resolved,
[00:07:42] verified, or closed. And of course,
[00:07:44] there's the infamous won't fix, which
[00:07:46] was one of the most emotionally honest
[00:07:47] software states ever invented. But, the
[00:07:49] system had ownership. The assignee field
[00:07:51] made it clear whose turn it was. It even
[00:07:53] defined verbs we still use today like
[00:07:55] create, comment, assign, resolve,
[00:07:57] reopen, mark duplicate, block another
[00:07:59] bug. It had dependencies. This bug
[00:08:01] blocks this release. This issue depends
[00:08:03] on that issue. It had audit history. Who
[00:08:05] changed what, when, and from what to
[00:08:06] what? None of that was designed for AI.
[00:08:08] There was no AI in the relevant sense.
[00:08:10] This This was just a bunch of humans
[00:08:12] trying to coordinate software work
[00:08:14] across time zones, across teams, across
[00:08:16] release trains, and across memory gaps.
[00:08:18] But, those human constraints turn out to
[00:08:20] be close to agent constraints. Humans
[00:08:22] forget context. Well, agents lose
[00:08:24] context. Humans need handoff. Well,
[00:08:26] agents need handoffs, too. Humans need
[00:08:28] accountability. Turns out, agents need
[00:08:30] observability. Humans need permissions.
[00:08:32] Agents need permissions even more.
[00:08:34] Humans need a shared source of truth.
[00:08:36] When work stretches across days and
[00:08:37] weeks, it turns out agents need that
[00:08:39] because the context window's not a
[00:08:40] source of truth. That is the accident,
[00:08:44] in the sense that we didn't intend it
[00:08:46] that way. Although, I would argue that a
[00:08:47] lot of the way we designed agents is to
[00:08:49] mimic people, so maybe it wasn't as
[00:08:51] accidental as we thought. Regardless of
[00:08:53] whether you think agents were designed
[00:08:55] like us on accident or on purpose, the
[00:08:57] system we built to compensate for human
[00:08:59] weakness does compensate very, very well
[00:09:02] for agent weaknesses, too. And that's
[00:09:04] why the old issue tracker shape just
[00:09:06] keeps surviving. You can see the same
[00:09:08] pattern in the way the category evolved.
[00:09:10] Bugzilla escaped from Mozilla and became
[00:09:12] the default tracker for a generation of
[00:09:13] open source projects. And then Jira
[00:09:15] showed up in 2002 and took the same
[00:09:18] basic model to the enterprise. Jira
[00:09:20] added workflows and custom fields and
[00:09:22] project hierarchy and permissions and
[00:09:23] integrations and enough configurability
[00:09:25] to map almost any company's internal
[00:09:27] process into the tool. That was the
[00:09:29] commercial genius of Jira. It could
[00:09:31] become your company. It is also why
[00:09:33] developers hated it. Every Jira
[00:09:35] deployment became its own local maze.
[00:09:37] The underlying primitives were good, but
[00:09:39] the configuration surface to make it
[00:09:41] sailable was so large that the tool
[00:09:44] could absorb every organizational
[00:09:45] dysfunction around it. Linear came later
[00:09:47] with a different philosophy. Linear did
[00:09:50] not say, "Bring us your org chart and
[00:09:52] every weird approval process and we will
[00:09:53] lovingly recreate it in software."
[00:09:55] Linear said, "This is your problem. Use
[00:09:58] our model, it's a cleaner model." Issues
[00:10:00] live in cycles, cycles connect to
[00:10:01] projects. The UI is fast, the opinion is
[00:10:04] strong, the customization surface is
[00:10:06] much smaller. And that is why Linear
[00:10:08] felt so good compared to Jira. It was
[00:10:09] not that Linear invented a new
[00:10:11] substrate, the basic data model was the
[00:10:13] same: issue, state, assignee, priority,
[00:10:15] dependency, history. Linear's innovation
[00:10:17] was making that model pleasant enough
[00:10:19] that people use it voluntarily and
[00:10:21] consistently. And that's the part that
[00:10:23] counterintuitively matters for agents,
[00:10:25] because you see good UX ends up getting
[00:10:27] more human involvement, which produces
[00:10:29] cleaner data, which is useful to agents.
[00:10:32] When people hate a tool, they work
[00:10:33] around it. They leave fields blank. They
[00:10:35] put important decisions in Slack. They
[00:10:37] use fake statuses. They create tickets
[00:10:39] after the work is done. They use the
[00:10:41] tracker because someone made them, not
[00:10:42] because it reflects reality. When people
[00:10:44] like the tool, more of the real work
[00:10:46] ends up in the tool and in the system,
[00:10:48] and that means the state is cleaner and
[00:10:50] the descriptions are better and the
[00:10:51] ownership is current and the
[00:10:52] dependencies are less made up. The audit
[00:10:54] history happens to be actually useful.
[00:10:56] Linear was a UX win. The UX win became a
[00:10:59] data win because people used good UX,
[00:11:01] and the data win matters much, much more
[00:11:04] once agents arrive. Because an agent
[00:11:05] does not care whether your project
[00:11:07] management tool feels elegant, it cares
[00:11:09] whether the state inside it is reliable
[00:11:12] enough to act on. That's the first big
[00:11:13] lesson. The best agent substrate may not
[00:11:16] be the tool with the most AI features,
[00:11:18] it may be the tool your team has been
[00:11:19] using cleanly for years because they
[00:11:22] love it. And yes, this is a plea for
[00:11:24] good UX. Good human UX in 2026, we still
[00:11:27] need it. Now let's talk about why agents
[00:11:30] want this particular shape of product so
[00:11:32] badly. An agent loop desperately needs a
[00:11:36] durable state. The context window does
[00:11:39] not count. It can be summarized, it can
[00:11:40] drift, it can get truncated, it can get
[00:11:42] reset. If the work spans multiple runs,
[00:11:45] multiple agents, multiple days, the
[00:11:47] state needs to live somewhere outside
[00:11:50] the model. A ticket does that. The agent
[00:11:52] can read the ticket at the beginning of
[00:11:53] a run and write back what happened at
[00:11:55] the end. The next run can pick up the
[00:11:57] work because the state is not trapped
[00:11:59] inside the previous conversation. That
[00:12:01] sounds really boring, but I promise you
[00:12:03] it's not boring. It is one of the
[00:12:04] biggest differences between a demo and a
[00:12:06] working agentic system. The agent also
[00:12:08] needs handoff semantics. Who owns that
[00:12:11] right now? Is the agent supposed to work
[00:12:12] on it? Is it waiting for a human? Is it
[00:12:14] blocked by another task? Is it ready for
[00:12:15] review? Is it done? In a good tracker,
[00:12:18] you don't depend on memory for this, you
[00:12:19] don't depend on vibes. These are fields.
[00:12:22] The assigning answers part of that
[00:12:24] problem, the status answers part of that
[00:12:26] problem, the dependency graph answers
[00:12:28] part of that problem, and the comment
[00:12:30] history answers part of it. Together,
[00:12:31] those fields become something like a
[00:12:33] protocol, and that's what Symphony is
[00:12:35] exploiting. The board is not just a
[00:12:37] visual planning surface. The board is a
[00:12:40] state machine. It's a way for agents to
[00:12:42] track their status over time, and that
[00:12:44] turns out to be critical for agents to
[00:12:46] actually get meaningful work done. An
[00:12:48] agent system also needs a way to
[00:12:50] coordinate many, many workers at once.
[00:12:52] This is where the Cursor long-running
[00:12:53] agents work is useful. Cursor wrote
[00:12:55] about running hundreds of agents on
[00:12:57] large coding projects and discovered
[00:13:00] that naive coordination breaks down very
[00:13:02] quickly when you get serious. So, if you
[00:13:04] have a flat agent system where every
[00:13:06] agent runs to the ball, agents hold
[00:13:08] locks too long, they forget to release
[00:13:09] them, they wait on each other, they
[00:13:10] become risk-averse and pick easy stuff,
[00:13:12] they take small little tasks instead of
[00:13:14] the hard end-to-end work they need to
[00:13:16] do. In other words, flat orgs of agents
[00:13:18] have a coordination problem, and issue
[00:13:20] trackers are coordination tools. They
[00:13:22] already have a unit of work, they
[00:13:23] already have claiming, they already have
[00:13:25] status, they already have blockers, they
[00:13:27] already have priority, they already have
[00:13:29] a way for humans to see what is
[00:13:31] happening without opening 20 terminals.
[00:13:34] So, the agent system does not have to
[00:13:36] invent a coordination layer from
[00:13:38] scratch. It can use the one the company
[00:13:39] already trusts. The next thing agents
[00:13:41] need is auditability. And this is where
[00:13:43] a lot of enterprise AI starts to kind of
[00:13:45] break at the edges. The demo will work,
[00:13:47] the pilot looks very good, I'm sure, and
[00:13:49] then something goes wrong in production
[00:13:50] and nobody can answer really basic
[00:13:52] questions about the defect. What did the
[00:13:54] agent see? What did it decide? What did
[00:13:56] it change? Who approved it? What state
[00:13:57] was the work in before and after? Issue
[00:14:00] trackers have ironically been logging
[00:14:02] this kind of history for decades. They
[00:14:04] did it because humans working
[00:14:05] asynchronously needed replayable history
[00:14:08] across time zones. Now, that same
[00:14:09] history is what makes agent work
[00:14:11] investigatable. Last but not least,
[00:14:14] agents need permissions. The whole
[00:14:16] security story for autonomous agents is
[00:14:18] about scoped access. What can the agent
[00:14:20] read? What can it write? Which systems
[00:14:22] can it touch? Which actions require
[00:14:23] approval? Which actions are blocked
[00:14:25] entirely? Enterprise issue trackers
[00:14:27] already live inside permission models.
[00:14:29] Jira projects have roles. Linear
[00:14:31] workspaces have permissions. Atlassian's
[00:14:33] Rovo MCP server respects the user's
[00:14:35] existing access controls. These systems
[00:14:37] were not built for agents, but they were
[00:14:39] built for controlled work. And that
[00:14:40] gives you a simple rule. The agent
[00:14:42] should not get to do more than the human
[00:14:44] assignee would be able to do. And that
[00:14:46] is a much easier rule to implement when
[00:14:48] the work is already inside a permission
[00:14:50] system with records and owners and
[00:14:52] actions and history. So, when you put
[00:14:54] all of this together, the fit between
[00:14:56] agents and ticketing systems becomes
[00:14:58] very obvious. Agents need durable state,
[00:15:01] they need clear ownership, they need
[00:15:02] legal transitions and bounded
[00:15:03] permissions and audit history. Issue
[00:15:05] trackers already have those things. And
[00:15:08] that is why Symphony looks so obvious
[00:15:11] after you see it. The surprising part is
[00:15:13] not that OpenAI used Linear per se, the
[00:15:15] surprising part is that we ever expected
[00:15:17] the agent layer to replace the work
[00:15:19] tracker instead of running through it.
[00:15:21] This also makes Atlassian look really
[00:15:22] different. For the last decade, a lot of
[00:15:24] people looked at Jira as the old world.
[00:15:26] It was powerful, it was entrenched, it
[00:15:27] was annoying, it was too configurable,
[00:15:29] it was deeply embedded in the enterprise
[00:15:31] process. But if issue trackers are agent
[00:15:33] substrates, then Atlassian owns one of
[00:15:36] the largest installed bases of agent
[00:15:38] readable work state in the world. And
[00:15:40] that changes the frame, doesn't it? In
[00:15:42] May 2025, Atlassian introduced its
[00:15:44] remote MCP server in beta. And the pitch
[00:15:46] was really simple. Let AI tools interact
[00:15:48] with Jira and Confluence data starting
[00:15:50] with Claude as the first official
[00:15:51] partner with Cloudflare infrastructure
[00:15:53] underneath. By February 2026, Atlassian
[00:15:55] said the Robo MCP server was generally
[00:15:57] available, right? It supports a broad
[00:15:59] set of clients. It can search and
[00:16:00] summarize Jira and Confluence and
[00:16:02] Compass. It can create and update issues
[00:16:03] and pages. It uses OAuth. It respects
[00:16:06] existing permissions. It supports admin
[00:16:07] controls and white listing. This is not
[00:16:09] just an integration. This is Atlassian
[00:16:12] making Jira and Confluence agent
[00:16:15] readable and agent writable.
[00:16:16] Mechanically, this is the same pattern
[00:16:18] Symphony assumes with linear. Take the
[00:16:20] system where work already lives, expose
[00:16:23] it through a controlled interface, and
[00:16:25] let agents operate against the work
[00:16:26] graph. This is why the Atlassian and
[00:16:28] Anthropic relationship is super
[00:16:30] interesting. Atlassian launched its
[00:16:32] remote MCP work, and Anthropic was the
[00:16:33] first one they picked, right? And in
[00:16:35] February, Anthropic signed a multi-year
[00:16:37] partnership with Atlassian Williams
[00:16:39] Racing, making Claude the team's
[00:16:40] official thinking partner and
[00:16:42] integrating Claude across Williams
[00:16:44] internal operations. But that F1 deal is
[00:16:46] not the main story here, right?
[00:16:48] Sponsorships are sponsorships. The brand
[00:16:50] alignment is more chilling. You have an
[00:16:51] AI lab that wants to be the enterprise
[00:16:53] agent layer sitting very close to the
[00:16:56] company that owns Jira and Confluence.
[00:16:59] And then you get the rumors. Online
[00:17:00] chatter started circulating that
[00:17:02] Anthropic might buy Atlassian at a
[00:17:04] premium. Treat that as rumor. That's not
[00:17:06] information. There's no formal
[00:17:07] announcement. There's no SEC filing.
[00:17:09] There's no deal. And there's no
[00:17:10] confirmation it will ever happen. But
[00:17:12] the rumor is still interesting for one
[00:17:14] reason. A few years ago, Frontier AI lab
[00:17:17] buys Atlassian would have sounded really
[00:17:18] bizarre. Why would the model company buy
[00:17:20] the issue tracker company? But now the
[00:17:22] logic is obvious enough that people will
[00:17:24] take it seriously even if the specific
[00:17:26] rumor goes nowhere. Because the issue
[00:17:27] tracker is no longer just a ticketing
[00:17:29] product. It is a map of how work happens
[00:17:31] inside the enterprise. It would benefit
[00:17:33] Anthropic to know that stuff. It knows
[00:17:35] the projects, it knows the dependencies,
[00:17:36] it knows the owners, it knows the
[00:17:38] history, it knows the approvals, it
[00:17:39] knows which work matters and which work
[00:17:41] is blocked. That's exactly the kind of
[00:17:43] context agents need. So the real
[00:17:45] headline is not Anthropic might buy
[00:17:47] Atlassian. The real headline is, in the
[00:17:49] agent era, Jira looks like
[00:17:51] infrastructure. And once you see Jira
[00:17:52] that way, a lot of other software starts
[00:17:54] to reprice in your head. And this is the
[00:17:56] part that jumps way beyond software
[00:17:58] engineering and way beyond ticketing
[00:18:00] systems into a larger strategy. Because
[00:18:03] the substrate hypothesis is real. Tools
[00:18:06] that have persistent records, defined
[00:18:08] verbs, ownership, permissions, and audit
[00:18:10] history become agent usable across
[00:18:12] software almost by accident. Tools that
[00:18:14] don't have those properties need a very
[00:18:16] expensive wrapper to be agent usable.
[00:18:18] And the agent layer has to invent
[00:18:20] structure that the underlying product
[00:18:21] never had. So which tools are like issue
[00:18:24] trackers? The first and obvious one is
[00:18:26] the CRM. Salesforce and HubSpot are
[00:18:28] issue trackers for revenue. They have
[00:18:30] accounts and contacts and opportunities
[00:18:32] and owners and stages and next steps and
[00:18:34] history and permissions and
[00:18:35] integrations. Sales teams already live
[00:18:37] inside the state machine there. A deal
[00:18:39] moves from prospecting to qualification
[00:18:41] to proposal to negotiation to closed one
[00:18:43] or closed lost. That is agent substrate.
[00:18:45] The agent can research an account, it
[00:18:47] can draft a follow-up, it can update
[00:18:48] fields, it can flag risk, it can prepare
[00:18:50] the next meeting, it can ask for human
[00:18:52] approval before sending something
[00:18:54] externally. The CRM is already a durable
[00:18:57] state layer. The second obvious category
[00:18:59] is service desk software. Zendesk,
[00:19:01] ServiceNow, Intercom, Jira Service
[00:19:03] Management. These are the issue trackers
[00:19:05] for customer problems. They have tickets
[00:19:07] and assignees and statuses and SLAs and
[00:19:10] escalation paths and macros and customer
[00:19:12] history and audit trails, and
[00:19:13] permissions all built in. If you were
[00:19:15] designing a customer support agent from
[00:19:16] scratch, you would rebuild a bunch of
[00:19:18] that. So, the agent will not replace the
[00:19:20] service desk, it will operate through
[00:19:22] it. The third category is ERP and
[00:19:24] business process systems. SAP, Oracle,
[00:19:27] Workday, NetSuite, these are not fun
[00:19:29] tools. Nobody wakes up excited to spend
[00:19:31] their day in an approval workflow, but
[00:19:33] they have records. They have business
[00:19:34] objects. They have permissions. They
[00:19:36] have approvals. They have audit trails.
[00:19:38] They encode how money and people and
[00:19:40] inventory and procurement and payroll
[00:19:41] and compliance move through the
[00:19:43] business. That is exactly the kind of
[00:19:45] boring structure agents need if they're
[00:19:47] going to do real work. And then you have
[00:19:49] some smaller but still important cases.
[00:19:51] Calendars are issue trackers for time.
[00:19:53] They have events and attendees and
[00:19:55] owners and rooms and availability and
[00:19:57] changes and history. Source control is
[00:19:59] an issue tracker for code change.
[00:20:00] Branches and commits and pull requests
[00:20:02] and reviewers and checks and merge
[00:20:04] status and blame and history.
[00:20:05] Procurement tools, they're issue
[00:20:07] trackers for spend. HR information
[00:20:09] systems are issue trackers for employees
[00:20:11] and roles. Finance systems are issue
[00:20:12] trackers for money movement. The pattern
[00:20:14] repeats. If a system was built to
[00:20:17] coordinate people asynchronously around
[00:20:19] really important work, it probably has
[00:20:21] the bones of an agent substrate. And the
[00:20:23] weaker candidates in this story are just
[00:20:25] as important. Email has a state, it has
[00:20:27] a history, it has permissions, but the
[00:20:29] verbs are really weak, right? Reply,
[00:20:31] forward, archive, label. There's not a
[00:20:33] native way to assign it or resolve it or
[00:20:35] block it or approve it in the general
[00:20:37] email model. That means agents can help
[00:20:39] with email, but email itself is not a
[00:20:41] very clean control plane. It's very It's
[00:20:43] too conversational. Slack and Teams are
[00:20:45] similar. They contain a huge amount of
[00:20:46] context, but the structure is mostly
[00:20:49] transcript structure. A thread is a pile
[00:20:51] of messages, the state of the work is
[00:20:52] often implied rather than encoded.
[00:20:54] Agents will and do read Slack,
[00:20:56] absolutely. They will summarize Slack.
[00:20:58] They are in Slack now. They will extract
[00:21:00] tasks from Slack. And Slack has reaped
[00:21:02] the benefits of being the place where
[00:21:03] humans are because agents end up getting
[00:21:06] built into Slack. But, if Slack is the
[00:21:08] only place your work state lives, the
[00:21:10] agent has to infer too much.
[00:21:12] Documentation tools, they kind of sit in
[00:21:14] the middle in this framework.
[00:21:15] Confluence, Notion, Google Docs, they
[00:21:17] have permissions, they have version
[00:21:19] history, they have comments, sometimes
[00:21:21] they have databases, but ownership is
[00:21:22] often very fuzzy and the verbs are
[00:21:24] usually edit and comment and share.
[00:21:26] That's useful context, but it's weaker
[00:21:28] as a substrate for serious work.
[00:21:30] Spreadsheets are the strangest
[00:21:33] middle-of-the-road case out there. They
[00:21:34] have rows, they have columns, they have
[00:21:36] formulas and structure, but the schema
[00:21:38] is user-defined and often implicit. The
[00:21:40] spreadsheet can be incredibly structured
[00:21:43] if the human designed it well, and also
[00:21:44] can be completely impossible if the
[00:21:46] human designed it like a personal
[00:21:47] scratchpad. So, spreadsheet agents will
[00:21:49] get better, but spreadsheets are not the
[00:21:51] easy case. The agent has to infer the
[00:21:53] user's schema before it can act. All of
[00:21:56] this gives you a very simple diagnostic
[00:21:58] for every tool in your stack. Just ask
[00:22:00] five questions. Does this tool have
[00:22:02] records or does it mostly just have
[00:22:04] content? Does it have a state machine or
[00:22:06] does it just have labels? Is ownership
[00:22:08] an explicit field or is it something
[00:22:10] people infer from conversation? Are the
[00:22:12] verbs structural or are they just
[00:22:14] conversational? I've given you examples
[00:22:16] of both. Is the history queryable or is
[00:22:18] it just visible? Tools that score well
[00:22:20] on these questions become agent
[00:22:23] infrastructure. Tools that score poorly
[00:22:25] become context sources at best, and in
[00:22:27] many cases they become places where
[00:22:29] someone else builds the real substrate
[00:22:31] around them. That's a very different way
[00:22:33] to evaluate software. It means the most
[00:22:35] important question is not does this
[00:22:37] product have an AI chatbot? The better
[00:22:39] question is, can an agent safely
[00:22:41] understand and change the state of work
[00:22:43] inside the product? Those are not the
[00:22:45] same set of questions, are they? It
[00:22:47] means the most important question is not
[00:22:49] does this product have an AI chatbot?
[00:22:51] The most important question is, can an
[00:22:53] agent safely understand and change the
[00:22:55] state of work inside this particular
[00:22:57] product? Totally different question.
[00:22:59] Now, what What you do with all this? For
[00:23:01] builders, I think the implication is
[00:23:03] really straightforward. Your data model
[00:23:05] is a strategic surface now. If you're
[00:23:07] building a product that you want agents
[00:23:08] to use later, don't start by bolting the
[00:23:11] chat into the UI. That's a very 2024
[00:23:13] approach. Start by making the underlying
[00:23:15] state clean. Expose your records, define
[00:23:17] your verbs, make ownership really
[00:23:19] explicit, preserve your history, build
[00:23:21] permissions into the model, make the
[00:23:22] really important actions available
[00:23:24] through a real API or an MCP server. If
[00:23:26] your product is opaque, the agent's
[00:23:28] going to have to scrape the UI or guess
[00:23:30] what the user meant, and that's very
[00:23:31] fragile. If your product exposes really
[00:23:33] clean state and really clean verbs, the
[00:23:36] agent can operate through it. And that's
[00:23:37] the difference between we added AI for
[00:23:40] the board and actually we became part of
[00:23:42] the agent stack and no one's going to
[00:23:44] disrupt us. And that's the difference
[00:23:46] between just we added AI for show and we
[00:23:48] actually became part of the agent stack.
[00:23:50] For teams, the implication is more
[00:23:52] uncomfortable. Your work tracking choice
[00:23:54] is becoming your agent infrastructure
[00:23:56] choice and you have to get used to that.
[00:23:57] The Jira versus Linear decision used to
[00:24:00] feel like a UX and a workflow decision.
[00:24:02] Which tool do the engineers like? Which
[00:24:03] one fits our planning process? Which one
[00:24:05] integrates with GitHub? Which one annoys
[00:24:07] people less? And those questions do
[00:24:09] still matter, but now there's another
[00:24:10] question. Which substrate do you want
[00:24:13] your agents to run on? If your work data
[00:24:15] is clean, your agents get a head start.
[00:24:18] If your work data is spread across Slack
[00:24:20] threads and half-filled tickets and
[00:24:21] mystery spreadsheets and undocumented
[00:24:23] tribal knowledge, agents will struggle
[00:24:25] in exactly the places you want them to
[00:24:27] help. This is one of the hidden costs of
[00:24:30] messy operations. Messy operations used
[00:24:32] to be a human tax. People could
[00:24:34] compensate with meetings and memory and
[00:24:36] relationships and heroics. Agents are
[00:24:39] worse at those things. Agents really
[00:24:41] need the business to be legible. And
[00:24:43] that means the boring part of cleaning
[00:24:44] up your workflows and consolidating
[00:24:46] systems and enforcing fields and keeping
[00:24:48] ownership current and making sure status
[00:24:50] actually means something is not just
[00:24:52] good hygiene, it's AI readiness. For
[00:24:55] leaders, that implication is very
[00:24:56] strategic, right? That boring
[00:24:58] infrastructure your company already runs
[00:24:59] on, that's repricing. The tickets and
[00:25:02] records and workflows and approvals and
[00:25:03] comments and histories and permissions
[00:25:05] and dependency graphs, those are not
[00:25:07] just stuff your team happens to produce.
[00:25:09] They're the map agents are going to use
[00:25:11] to build on your business. That
[00:25:12] definitely favors incumbents, right?
[00:25:14] Folks like Atlassian and Salesforce and
[00:25:16] ServiceNow and Microsoft and Oracle and
[00:25:18] SAP and Workday. These companies own
[00:25:20] systems of record. They may not have the
[00:25:22] flashiest demos. They may not feel like
[00:25:24] the future, but they own that substrate
[00:25:26] agents build on, and the substrate is
[00:25:28] hard to displace. And that's why I'm a
[00:25:29] little bit skeptical of a lot of the
[00:25:31] greenfield agent platform stories. If
[00:25:33] the agent platform does not own the
[00:25:35] records, the permissions, the history,
[00:25:37] the workflows, or the user habits, it
[00:25:39] has to borrow those from somewhere. It
[00:25:42] has to borrow them from incumbent
[00:25:43] systems. It becomes a wrapper. Now,
[00:25:45] wrappers can be valuable. Some wrappers
[00:25:47] become very big companies, but owning
[00:25:48] the substrate is better than being the
[00:25:51] thing that sits on top of someone else's
[00:25:52] substrate. That's the strategic lesson
[00:25:54] from issue trackers. The 30-year
[00:25:56] accumulation of human coordination
[00:25:58] infrastructure is not going to disappear
[00:26:00] just cuz agents arrived. It's going to
[00:26:02] become the surface agents consume. Some
[00:26:04] companies will wrap around it, sure.
[00:26:05] Some companies will choose to expose it.
[00:26:07] Some companies are going to figure out
[00:26:09] how to own and drive against it
[00:26:10] deliberately. You want to know which
[00:26:12] side of that line you're ending up on.
[00:26:14] So, come back to the start of the story.
[00:26:16] Carissa said issue tracking is dead.
[00:26:18] OpenAI published a system that uses the
[00:26:20] issue tracker as the control pane for
[00:26:22] autonomous coding agents. It's not a
[00:26:24] contradiction if you understand the
[00:26:26] substrate story. The old user experience
[00:26:28] is dying. Carissa was right. The ritual
[00:26:30] of humans translating every bit of
[00:26:31] context is going away. That world is
[00:26:33] shrinking. But the substrate underneath
[00:26:36] it isn't dying. The substrate agents
[00:26:38] need to work against is a durable state.
[00:26:40] Uh the substrate needs ownership and
[00:26:42] permissions and a state machine and
[00:26:44] history for the agents to do work. So,
[00:26:46] why throw out the issue tracker that
[00:26:47] we're already putting good data into?
[00:26:49] That's where we're going to develop a
[00:26:52] shared map of work. And agents need that
[00:26:54] map more than humans do. And that is why
[00:26:55] issue trackers have won, and they won in
[00:26:57] the most boring possible way. They
[00:26:58] became too useful to replace. Not
[00:27:00] because everyone loved them, although
[00:27:02] Linear has its fans. Not because they
[00:27:04] were built for AI. They They won because
[00:27:05] they encoded coordination. And it turns
[00:27:08] out that the hard part of coordinating
[00:27:10] humans and the hard part of coordinating
[00:27:12] agents is a lot more overlap than a lot
[00:27:14] of us expected. So, the next time you
[00:27:16] look at a super boring enterprise tool,
[00:27:18] don't ask whether it has an AI assistant
[00:27:20] in the corner. Ask whether it has
[00:27:22] records and states and owners and verbs
[00:27:24] and permissions and history. And ask if
[00:27:27] they're willing to expose that. If it
[00:27:28] does, and if they are, that tool is
[00:27:31] probably more important than it looks.
[00:27:33] And if it doesn't, someone is going to
[00:27:34] build the agent substrate around it. And
[00:27:36] the difference between building on that
[00:27:38] substrate and owning that substrate and
[00:27:40] just kind of pretending it isn't there
[00:27:41] or dumping it out of the side and saying
[00:27:43] we don't need it anymore, that's going
[00:27:44] to matter a lot. Sure, the human
[00:27:46] translation step that Cary wrote about
[00:27:48] is dying. But the need to keep track of
[00:27:51] things over time is a persistent need
[00:27:53] agents have as well. The boring tools
[00:27:56] win. And the job now is figuring out
[00:27:59] which boring tools are next and how do
[00:28:01] we stitch these boring tools together so
[00:28:03] they form a useful agentic substrate for
[00:28:07] our businesses. Because I got to tell
[00:28:08] you, every business has a unique
[00:28:10] patchwork of these agent substrates. And
[00:28:13] a lot of the work of good agentic
[00:28:14] pipelines at the heart of the business
[00:28:16] is mapping your agentic substrate and
[00:28:18] figuring out how do you stitch together
[00:28:20] your ERP and your CRM and how do you
[00:28:22] stitch it with your tickets and how do
[00:28:23] you stitch it with your voice of
[00:28:24] customer? That's where the rubber meets
[00:28:26] the road, and that is why we need to
[00:28:28] take the current data we have in these
[00:28:30] systems seriously. Because you can't do
[00:28:31] real work by just wiping all of that
[00:28:33] away and setting it up clean and new.
[00:28:35] Instead, you need to be in a position
[00:28:37] where you can say, "This is how I audit
[00:28:40] the current system I'm in, and this is
[00:28:42] how I start to plan across the database
[00:28:45] schemas for these different systems of
[00:28:47] record to figure out how I can install
[00:28:50] an agentic pipeline that takes this data
[00:28:52] seriously based on actual live
[00:28:54] connectors. And if you're curious to do
[00:28:55] that more, I put together a complete
[00:28:57] guide for that over on the Substack. And
[00:28:59] if you're like, "Man, boring tools are
[00:29:01] boring." I promise we'll be back to
[00:29:02] covering the exciting hyperscalers soon.
[00:29:04] Subscribe and I'll see you next time.
[00:29:06] Cheers.
