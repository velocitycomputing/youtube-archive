---
video_id: zP6TnEiueEc
title: Google Spent a Year Stitching MCP, A2A, AG-UI Together. I/O Today.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=zP6TnEiueEc"
watched_date: 2026-05-19
watched_at: "2026-05-19T12:00:00Z"
watch_count: 1
duration_seconds: 1242
source: youtube-history-browser
history_label: Tuesday
history_order: 100
watched_at_precision: date-from-history-label
watched_percent: 30
estimated_watched_seconds: 373
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Google presented six agent protocols launched over the past year—MCP, A2A, AGUI, A2UI, AP2, and X42—that address core questions about agent capabilities: What tools can agents access? Which other agents can they coordinate with? How do humans maintain control? Three protocols form the emerging standard stack: MCP is a tool integration layer that standardizes how agents discover and invoke external systems (GitHub, Slack, databases, etc.), though it requires careful security design to prevent tool poisoning attacks. A2A enables agent-to-agent delegation across product boundaries through standardized "agent cards," adding flexibility but also latency and failure points. AGUI provides the human control layer for long-running agents, enabling observation, approval of sensitive steps, and course correction—addressing the reality that traditional chat interfaces are inadequate for non-deterministic agent workflows. The other three protocols (A2UI for structured UI rendering, AP2 and X42 for payments) remain more specialized and contested, though payment protocols in particular are proliferating as a valuable space.

To build agent products effectively, map your specific workflow against these six questions: Does the agent need tool access (MCP)? Must it coordinate with other agents (A2A)? Where does the user need approval or steering (AGUI)? Does it render dynamic UI (A2UI)? Does it need to authorize transactions (AP2) or autonomously pay for resources (X42)? Recognize that protocols are customer experience choices, not just technical ones—understand how each protocol's assumptions about authorization duration, payment methods, or geographic preferences affect your customers. Audit your current team's focus: most overemphasize model selection while underspecifying the operating surface (which tools agents can see, approval flows, interaction models). The real work in 2026 is stitching these substrates together in ways that create compelling customer experiences.

## Transcript

[00:00:00] Google IO opens today, May 19th. There
[00:00:02] will be a ton of agent demos. I can
[00:00:04] guarantee you that I will get into
[00:00:06] coverage for Google at another time. The
[00:00:08] more interesting story is what is
[00:00:10] happening underneath Google IO,
[00:00:12] including in many of the protocols
[00:00:14] Google is putting out there to drive the
[00:00:16] Agentic Revolution. I want to talk today
[00:00:18] about six agent protocols that have
[00:00:21] launched in the last year and how they
[00:00:23] underly agentic systems. Why do we do
[00:00:26] that? Because it turns out that the
[00:00:27] substrates for agents actually shape the
[00:00:30] customer experience. What are those six?
[00:00:32] MCP, A2A, AGUI, A2UI, AP2, and X42. It's
[00:00:38] not Star Wars robots. It's actually real
[00:00:40] protocols. And if you're building an AI
[00:00:42] agent product right now, that list is
[00:00:45] really hard to wrestle with and
[00:00:46] understand. It feels like a standard
[00:00:48] scrum. New acronyms are popping up all
[00:00:50] the time. There's new diagrams. There's
[00:00:52] new claims that some missing piece of
[00:00:54] the agent stack has been solved with a
[00:00:56] new protocol. Here is my read. Three of
[00:00:59] the six that I just named are becoming
[00:01:01] the actual agent stack. The other three
[00:01:04] are very much in contested layers that
[00:01:07] we need to be honest are still under
[00:01:09] debate. So, we're going to talk about
[00:01:10] all six today and we're going to talk
[00:01:12] about the three that are part of the
[00:01:13] core standard stack first. But before we
[00:01:16] get into which three are the standard, I
[00:01:19] want to lay out the overall landscape
[00:01:21] for agentic protocols. What are the
[00:01:22] questions that we're trying to answer
[00:01:24] with agentic protocols? I want to
[00:01:25] suggest three for you. Number one, what
[00:01:28] can the agent use? Number two, who else
[00:01:31] can the agent work with? And number
[00:01:32] three, how does the human stay in
[00:01:35] control while the agent is working? Keep
[00:01:37] those three in mind because they shape
[00:01:38] the customer experiences that we're
[00:01:40] trying to drive at the end of the day,
[00:01:41] whether we're building for internal or
[00:01:43] external customers. And they also help
[00:01:46] us to understand what really matters
[00:01:47] when there's a bunch of standards out
[00:01:49] there. Now, three of those six protocols
[00:01:51] directly map onto those three questions.
[00:01:54] MCP, that's a tool and data layer. It's
[00:01:56] the protocol an agent uses to discover
[00:01:59] and invoke the systems where your work
[00:02:00] lives. ADA, that's an agent coordination
[00:02:04] layer. It's the protocol one agent uses
[00:02:06] to discover and delegate to another
[00:02:08] agent across product or company
[00:02:09] boundaries. AGUI is a human interaction
[00:02:12] layer. It's a protocol that lets a
[00:02:14] longunning back-end agent share state
[00:02:16] and events and approvals and
[00:02:18] interruptions with a userfacing app. The
[00:02:21] other three protocols, A2UI, AP2X42,
[00:02:25] they all sit in a different spot in the
[00:02:27] stack. A2 UI is about how agents render
[00:02:29] structured interfaces. AP2 is about
[00:02:32] authorizing agent-led purchases. X42 is
[00:02:35] about machine to-achine payment at the
[00:02:37] HTTP layer on the web. All are really
[00:02:40] important and all are still contested or
[00:02:44] very domain specific. I break down all
[00:02:46] six protocols layer by layer on the
[00:02:48] Substack with source links, name partner
[00:02:50] list. If you want the full version, you
[00:02:52] know where to get it. We're going to
[00:02:53] move on in this video to MCP, perhaps
[00:02:56] the most popular and most well-known
[00:02:58] protocol stack in AI. MCP won share
[00:03:02] first because it solves the most
[00:03:04] immediate pain in agentic building. An
[00:03:07] agent sits in a chat box and has no
[00:03:09] access to tools and cannot do work.
[00:03:11] Right? It can only advise. It can
[00:03:13] summarize. It can draft. It's a 2024
[00:03:15] world. The work itself lives somewhere
[00:03:17] else. It lives in GitHub. It lives in
[00:03:19] Slack. It lives in Drive and Postgress
[00:03:21] and Stripe and Linear and Salesforce in
[00:03:23] some internal API in a calendar. Before
[00:03:26] MCP, every integration with all of the
[00:03:29] tools I just named looked like custom
[00:03:31] glue to your chatbot, right? You had to
[00:03:33] have tool definitions and authentication
[00:03:35] patterns and parameter schemas and error
[00:03:37] handling all written from scratch every
[00:03:39] time. The beauty and power of MCP is
[00:03:42] that it standardizes all of that. A
[00:03:44] server exposes tools and resources. An
[00:03:46] agent host connects to it. The model
[00:03:48] receives a usable description of what
[00:03:50] can be done. New capabilities composed
[00:03:53] without every single agent platform
[00:03:54] rebuilding every connector. Cloud
[00:03:56] Desktop supports local MCP servers and
[00:03:58] so do most of the other agent tools out
[00:04:00] there including Codeex. Uh Google has
[00:04:02] support for it. There are more than
[00:04:04] 14,000 MCP servers now. And it's
[00:04:06] tempting to treat MCP as if it makes
[00:04:08] tools safe just because it's a standard
[00:04:10] across the internet. It doesn't. Tool
[00:04:13] access enables arbitrary code execution
[00:04:15] and arbitrary data access. And that's
[00:04:18] good because MCP is designed to allow
[00:04:20] agents to use tools in arbitrary ways to
[00:04:23] get task done. That's the reason it was
[00:04:24] created. But that also means that MCP
[00:04:28] was created for a high trust
[00:04:30] environment. And we now have to think
[00:04:32] about how we configure security and
[00:04:35] security stances around a tool using
[00:04:39] agent experience. MCP was not designed
[00:04:41] for that at root. And so there are other
[00:04:44] challenges that we have to solve if we
[00:04:47] are trying to build secure agents. You
[00:04:49] know, Invariant Labs has already
[00:04:50] published research on what they call
[00:04:52] tool poisoning attacks, which are
[00:04:54] malicious instructions that can hide
[00:04:56] inside tool descriptions that can be
[00:04:58] exposed via MCP. And those malicious
[00:05:01] instructions can influence an agent
[00:05:03] through the very metadata that's
[00:05:05] supposed to make the tool discoverable.
[00:05:07] So tool access is not a feature toggle
[00:05:10] even though it's treated that way in a
[00:05:12] lot of user interfaces. Now it is a
[00:05:14] security boundary that you're crossing.
[00:05:16] If your team is shipping MCP servers,
[00:05:18] you still need scopes and approval flows
[00:05:21] and audit trails and a real answer to
[00:05:23] which tools the agent can see in which
[00:05:25] context. MCP does get the agent close to
[00:05:28] the work. It does not decide whether the
[00:05:31] agent should do the work. And if you're
[00:05:33] interested in digging into the security
[00:05:35] side of things, the Substack piece goes
[00:05:37] deep on the Invariant Labs tool
[00:05:39] poisoning research, what that means for
[00:05:41] how we design our scopes, how we design
[00:05:43] our approvals. If your team's already
[00:05:45] running MCP servers, you definitely need
[00:05:47] to dig into that topic. You need to
[00:05:49] understand what you're exposing. For
[00:05:50] now, we're going to move to A to A and
[00:05:52] the delegation layer. So MCP gets agents
[00:05:55] reach, right? The second problem arrives
[00:05:58] the moment the agent actually starts
[00:06:00] working. So the agent can't know
[00:06:02] everything. It can't own every
[00:06:03] capability. A procurement agent will
[00:06:06] need a supplier agent. A travel agent
[00:06:08] needs a hotel agent. A finance agent may
[00:06:10] need a tax agent. Uh a software agent
[00:06:12] may need a security reviewer. In fact, I
[00:06:14] know it does. Work is distributed across
[00:06:18] owners and permissions and domains and
[00:06:19] expertise. No one agent does it all. So
[00:06:22] A to A turns that distribution into
[00:06:24] something that agents can reason about.
[00:06:26] And the important primitive in that
[00:06:28] stack is the agent card. A remote agent
[00:06:30] publishes a card that describes what it
[00:06:32] is, what it does, which skills it
[00:06:34] exposes, where it can be reached, and
[00:06:36] how another agent ought to interact with
[00:06:37] it. The agent card is the first version
[00:06:40] of an operating contract. It has real
[00:06:42] terms and real interfaces and real
[00:06:44] responsibility. Google launched ADA with
[00:06:46] a bunch of partners, right, with
[00:06:47] Atlassian and Box and Coher and MongoDB
[00:06:50] and PayPal and Workday. more than 50.
[00:06:52] The list matters because A toa A only
[00:06:55] works if agents really can cross product
[00:06:58] and company boundaries. So you want a
[00:07:00] world where you have discoverable
[00:07:02] delegation for agents, not just a bunch
[00:07:04] of swarms that look good on paper. But
[00:07:07] there's a cost here. Coordination isn't
[00:07:09] free. A toa adds another surface where
[00:07:11] you can have latency and failure and
[00:07:13] permissions and observability issues. If
[00:07:15] an agent asks another agent to do work,
[00:07:17] it certainly makes the agents workflow
[00:07:19] more flexible, but it also makes it less
[00:07:22] predictable. So A to A isn't the right
[00:07:24] answer for every product. A single
[00:07:26] product with a small set of tools may
[00:07:27] not need agent coordination at all. The
[00:07:30] right question to ask is whether this
[00:07:32] workflow requires delegated expertise or
[00:07:34] authority outside the primary agent. If
[00:07:37] the answer is yes, you need to think
[00:07:39] about what that looks like ahead of
[00:07:41] time. Decide what your agent can say
[00:07:43] about itself. decide what it can accept,
[00:07:45] decide what it can't share, decide what
[00:07:47] requires human approval, decide how a
[00:07:50] downstream result gets validated. The
[00:07:52] agent card is Google's attempt to make
[00:07:54] part of that process standard, but it's
[00:07:57] still missing a control layer, and
[00:07:59] that's where we get to AGUI. Now, I know
[00:08:02] it's easy to underestimate AGUI because
[00:08:04] most people who hear about it think it
[00:08:06] is about driving the user interface. I
[00:08:09] don't think that's the best reading. I
[00:08:11] think a better reading is that AGUI
[00:08:13] helps us to ensure trust in agentic
[00:08:15] workflows. An agent that's longunning,
[00:08:17] that's non-deterministic, and that's
[00:08:19] capable of touching external systems
[00:08:21] needs a lot more than a final answer for
[00:08:23] a human to see. Humans need to be able
[00:08:25] to observe that agent as it works,
[00:08:27] approve sensitive steps, correct course,
[00:08:30] inspect state, understand why the agent
[00:08:32] is waiting. And traditional web apps are
[00:08:34] just built for call and response. They
[00:08:36] don't really handle the streaming work
[00:08:38] that agents do. They don't handle the
[00:08:40] fact that agents may discover new
[00:08:42] information mid task. The chatbot
[00:08:45] experience is not enough for that and
[00:08:48] neither are most traditional apps. So
[00:08:50] AGUI is the open candidate for the human
[00:08:53] control layer. The docs talk about what
[00:08:55] agent apps actually need, right?
[00:08:57] Streaming, shared state, front-end tool
[00:08:59] calls, backend tool rendering, custom
[00:09:01] events, steering, sub aent composition.
[00:09:03] This is the layer many teams will ignore
[00:09:06] until their agents start doing real work
[00:09:08] and generating real bucks. So they'll
[00:09:09] wire a model to tools. They'll wire up a
[00:09:11] nice chat component. And then they'll
[00:09:12] discover what their agent is really
[00:09:14] doing. And then they'll say, "Oh no, we
[00:09:15] need approval buttons. Oh no, we need
[00:09:17] logs. We need a progress spinner." None
[00:09:19] of those things by themselves are fixes
[00:09:22] for the root issue, which is about
[00:09:23] finding the right control points,
[00:09:25] understanding what the agent is trying
[00:09:27] to do, understanding what it's waiting
[00:09:29] for, and then figuring out where the
[00:09:31] user needs to approve or deny or edit or
[00:09:33] cancel. So, AGUI
[00:09:36] belongs with MCP and ADA in the core
[00:09:38] stack even if the specific protocol is
[00:09:40] earlier in the adoption curve. AGUI
[00:09:43] itself may win that race, maybe a close
[00:09:46] cousin does. But the point is that an
[00:09:48] agent that can't show its work becomes
[00:09:50] supervision debt for humans. And this is
[00:09:53] a way to address that and actually at
[00:09:55] root think about the control problem for
[00:09:57] agents and build systems that allow
[00:09:59] humans to interact at the right moments
[00:10:01] with running agent workflows. Now, if
[00:10:03] AGUI is new for you, if you want to dive
[00:10:05] deeper, the Substack piece gets into all
[00:10:08] the elements in the ecosystem. It talks
[00:10:10] about AGUI with Langraph and Crew AI and
[00:10:12] Amazon Bedrock Agent Core and Pidantic
[00:10:15] AI and Mastra and Copilot Kit. If you're
[00:10:17] picking a framework, that's where you
[00:10:18] want to dive in and look. Now, we need
[00:10:21] to get to the other three protocols, the
[00:10:22] one that I said weren't part of the core
[00:10:24] stack, because we need to understand
[00:10:26] why. Because they won't tell you they're
[00:10:27] not part of the core stack. Every
[00:10:29] protocol thinks it's a standard. Why are
[00:10:30] these not standards? And what does that
[00:10:32] tell us about the state of the agent
[00:10:34] race? So the other three are A2 UI, AP2,
[00:10:37] and X42.
[00:10:39] A2UI is Google's project for agent
[00:10:42] generated interfaces. Instead of sending
[00:10:44] arbitrary HTML or JavaScript from a
[00:10:46] remote agent, which is frankly a
[00:10:48] security disaster waiting to happen,
[00:10:50] A2UI sends a structured declarative UI
[00:10:53] representation. The client renders using
[00:10:56] trusted components. The agent asks for
[00:10:59] components from an approved catalog. It
[00:11:01] cannot execute arbitrary interface code
[00:11:03] and that is absolutely the right
[00:11:05] direction to be running in. But it's
[00:11:06] much narrower from a solution space than
[00:11:09] the human control problem that AGUI is
[00:11:12] solving. A2 UI is just one piece of the
[00:11:15] overall rendering question and it
[00:11:17] doesn't try and establish a whole user
[00:11:20] control layer like AGUI. And so that's
[00:11:23] why I see A2 UI as being useful and
[00:11:25] helpful for driving some kinds of
[00:11:27] generated experiences, but maybe not as
[00:11:31] focused on the substrate that many many
[00:11:33] agents will need to drive successful
[00:11:36] workflows in the new Agentic economy.
[00:11:38] AP2 meanwhile is Google's Agentic
[00:11:40] payments protocol. 60 plus collaborators
[00:11:43] jumped onto this. You might think that
[00:11:44] makes it a standard, but not in
[00:11:46] payments. Uh the collaborators include
[00:11:47] Auden and American Express and Coinbase
[00:11:50] and Mastercard and PayPal and Salesforce
[00:11:52] and Union Pay and World Pay. That the
[00:11:54] key mechanic here is what's called the
[00:11:56] mandate, a cryptographically signed
[00:11:59] proof of what the user authorized. AP2
[00:12:02] is trying to answer the most difficult
[00:12:04] question in Agentic Commerce. How does
[00:12:06] the ecosystem know the agent was
[00:12:08] authorized to buy? Meanwhile, X42 is
[00:12:12] Coinbase's HTTP native payment protocol.
[00:12:14] Cloudflare's adopted it. The use case is
[00:12:16] very much agent-gagent payment for
[00:12:18] resources. An agent buys an API call or
[00:12:20] a data source or a document or a
[00:12:22] benchmark run and it doesn't have to set
[00:12:24] up an account or negotiate a
[00:12:26] subscription. So AP2 and X42 are very
[00:12:28] much adjacent, but they're not the same
[00:12:30] thing. AP2 is about commercial trust and
[00:12:32] user authorization, and X42 is about how
[00:12:35] do you settle payments for resources for
[00:12:37] agents. And this this is not the end of
[00:12:39] the story. The protocol pile gets really
[00:12:41] big with payments because payments are a
[00:12:43] very valuable space to be in. If you're
[00:12:45] interested in diving deeper, I did an
[00:12:46] entire video recently on Stripe and its
[00:12:49] role in the payment space. That is
[00:12:51] definitely a video you want to check out
[00:12:52] if you're looking at payments and agent
[00:12:54] protocols. They've done a phenomenal job
[00:12:57] understanding that you are driving human
[00:13:00] trust in Aentic Commerce. And that is
[00:13:02] why their suggested experience of just
[00:13:05] sending an agent to a link to get an
[00:13:07] authorization token feels so smooth. So
[00:13:10] the protocols are going to keep piling
[00:13:11] up in the payment space even beyond
[00:13:13] Stripe. You have uh Mastercard with
[00:13:15] Aentic tokens. Visa with intelligent
[00:13:17] commerce. American Express has an Aentic
[00:13:19] commerce experiences developer kit.
[00:13:22] PayPal is supporting AP2 but is also
[00:13:24] building its own commerce layer. The
[00:13:26] payment space is so valuable, everyone
[00:13:28] wants to jump in. And if you're a
[00:13:30] builder right now, I would encourage you
[00:13:32] to think in the customer obsessed way
[00:13:35] that you see from recent Stripe launches
[00:13:38] because what you want to do is think
[00:13:40] about for my customers who have to trust
[00:13:43] agents. How do I ensure that the payment
[00:13:46] space is something that they feel they
[00:13:49] can participate in, authorize an agent
[00:13:51] to transact in, and feel good that their
[00:13:53] wallet is secure, the payment is
[00:13:55] authorized, the payment will be
[00:13:56] completed, and their order will be done
[00:13:58] as they expected. And so, don't look at
[00:14:01] payment protocols in particular as just
[00:14:03] a technical choice. They're very much a
[00:14:05] customer experience choice. Okay,
[00:14:08] stepping back here. How do you think
[00:14:10] about how substrates shape the customer
[00:14:13] experience? And how do you think about
[00:14:15] wrestling with them and getting into
[00:14:16] that problem space? If you've been
[00:14:18] assigned to ship an AI strategy or make
[00:14:20] an AI agent or complete a workflow with
[00:14:23] AI agents first and foremost, I've
[00:14:25] talked about this before. Get into the
[00:14:27] specifics, understand what you're really
[00:14:28] doing. Are you tackling support triage
[00:14:30] or procurement or sales territory
[00:14:32] analysis? Are you doing customer renewal
[00:14:35] prep? uh what what are you actually
[00:14:37] doing right understand that and then
[00:14:40] start to ask how does the substrate we
[00:14:43] are talking about shape the agentic
[00:14:46] experience for the customer right the
[00:14:48] MCP layer is absolutely going to be part
[00:14:50] of the conversation in most cases
[00:14:52] because you're going to want to have the
[00:14:54] option to bring that agent close to the
[00:14:55] work the ATA layer is narrower but can
[00:14:59] be very important if you're trying to
[00:15:01] understand how agents need to reason
[00:15:04] across other agent workflows. The AGUI
[00:15:07] layer is where you want to think about
[00:15:10] the ability to handle humanapproved
[00:15:14] longunning agent workflows. So for
[00:15:15] example, where the CSM might see a
[00:15:18] packet being assembled for the customer
[00:15:20] and might need to approve whether
[00:15:21] billing context should be included on
[00:15:23] the fly. Now, something like A2 UI might
[00:15:26] matter if the agent renders a particular
[00:15:29] usage chart or particular contract chart
[00:15:31] that helps someone understand what the
[00:15:34] agent is producing and you want some
[00:15:36] control and some guarantee that those
[00:15:38] components are real. And in this world,
[00:15:41] you need to be going through and asking
[00:15:43] yourself how your specific workflows map
[00:15:48] to the specific nuances of those
[00:15:51] protocols. And I'll give you an example
[00:15:52] from payments. So payments are
[00:15:55] complicated because payments are unique
[00:15:57] in different geographies. And one of the
[00:15:59] things that's really interesting about
[00:16:00] the payments experience with agents is
[00:16:02] that you have to blend in multiple
[00:16:05] competing protocols with multiple
[00:16:07] competing geographies as far as where
[00:16:09] customers are comfortable transacting,
[00:16:11] what payments methods they have, how
[00:16:13] they feel about using agents and compute
[00:16:15] when they're doing payments, etc. So
[00:16:17] there's a whole gnarly customer
[00:16:18] experience. There's a bunch of competing
[00:16:20] substrates. And if you want to put
[00:16:22] together an experience that is
[00:16:23] compelling, it is up to you to
[00:16:25] understand that a given payments
[00:16:28] experience may be biased toward the
[00:16:31] United States, toward US payment
[00:16:32] methods, given payments experience may
[00:16:34] be biased towards an assumption that
[00:16:38] humans will not make microp payments.
[00:16:40] And I I think that one of the things
[00:16:42] that I want to encourage you to do is to
[00:16:44] look at the things that may seem boring
[00:16:46] about these protocols. things like how
[00:16:48] fees are handled, things like how
[00:16:50] returns are handled, things like how
[00:16:52] delivery is handled, things like how uh
[00:16:54] authorization is handled and how long
[00:16:56] authorization runs for. And recognize
[00:17:00] that those have real customer
[00:17:01] implications. If your customer is not
[00:17:04] comfortable reauthorizing and you have a
[00:17:06] short-term token that you're driving for
[00:17:09] payment authorization and and your
[00:17:10] customer just wants it done and doesn't
[00:17:13] want to reauthorize every 30 minutes,
[00:17:15] you're going to have a very frustrated
[00:17:17] customer on your hands and that may be
[00:17:19] built into the protocol as a friendly
[00:17:21] default because it assumes a different
[00:17:23] customer. So, so protocols can be
[00:17:24] opinionated and that's okay, but you
[00:17:27] have to think about what that means for
[00:17:29] you. And I prepared six questions to
[00:17:32] help you start to dig into that. Number
[00:17:34] one, what tools and data does the agent
[00:17:37] need? Does the agent need to get into
[00:17:39] the MCP layer? Find out, right? Number
[00:17:41] two, what other agent surfaces or
[00:17:43] specialists does it need to call? Right?
[00:17:45] That's the A to A layer. Three, where
[00:17:47] does the user need to approve or edit or
[00:17:50] interrupt or steer the work? That's the
[00:17:51] AGUI layer, the control layer. Does the
[00:17:54] workflow need structured UI beyond text?
[00:17:56] That would be number four. A2 UI would
[00:17:58] help there. Number five, does the agent
[00:18:01] need to spend money? Does the agent need
[00:18:03] to authorize a transaction? Maybe that's
[00:18:04] an AP2 use case. Number six, does the
[00:18:07] agent need to autonomously pay for a
[00:18:09] resource programmatically?
[00:18:11] Maybe that's X42. Maybe it's something
[00:18:13] else. In general, most teams are
[00:18:15] overfocused on model selection, and
[00:18:17] they're very underspecified on the
[00:18:19] operating surface around the model. They
[00:18:21] know which LLM they want. They don't
[00:18:23] know which tools the agent can or should
[00:18:25] see. They may have a prototype that can
[00:18:27] call APIs, but they don't have an
[00:18:29] interaction model for user approval.
[00:18:31] They can imagine multiple agents
[00:18:33] coordinating, but they don't have any
[00:18:34] way to enforce or validate that. The
[00:18:37] actual work lives in those kinds of
[00:18:39] questions. So, I know we began this
[00:18:41] video talking about Google IO. There's
[00:18:43] going to be a lot of Agentic demos. I
[00:18:45] want you to watch at Google IO for one
[00:18:47] thing. Does Google make the agent stack
[00:18:50] feel like a single operating model? Does
[00:18:52] Gemini Enterprise stitch ADA agents and
[00:18:55] MCP tools and A2 UI interfaces and AP2
[00:18:58] payments into something a builder can
[00:19:00] chip against? Or does IO give us a new
[00:19:03] set of standards, another another two or
[00:19:05] three standards to add to the pile?
[00:19:07] Because this is a year where the agent
[00:19:09] stack needs to stop being a list of
[00:19:11] acronyms and needs to start being really
[00:19:13] really buildable. And the companies that
[00:19:16] figure out how to build against the
[00:19:18] protocol stack in ways that shape
[00:19:20] customer experiences, they're they're
[00:19:22] going to be the ones that win, right?
[00:19:24] And we're going to look back in six
[00:19:25] months and realize that because agent
[00:19:28] workflows for developers unlocked in the
[00:19:31] first half of 2026, this was a golden
[00:19:33] time for building what really mattered.
[00:19:36] Now, if you want to dive into those six
[00:19:38] questions and how you understand how to
[00:19:40] think about agentic workflows with an
[00:19:42] eye on the customer and an eye on how
[00:19:44] these protocol substrates drive the
[00:19:47] customer experience in detail. I get
[00:19:49] into all that on the substack, right?
[00:19:50] We'll talk about Salesforce and
[00:19:52] Snowflake and Drive and Slack all how
[00:19:55] they operate at the MCP layer. We'll
[00:19:57] talk about billing and legal agents at
[00:19:59] the ADA layer. There's a dive on CSM
[00:20:01] facing approval services at the AGUI
[00:20:04] layer and how you think about that. So,
[00:20:05] if you want to get a quick start on
[00:20:07] copying some of those pieces for your
[00:20:08] team, you can grab that link. It's
[00:20:10] great. I hope that this dive into the
[00:20:13] substrate of agents has been helpful. It
[00:20:15] may not feel sexy to talk about why
[00:20:18] agent substrates drive customer
[00:20:20] experiences, but it's profoundly
[00:20:22] impactful and it's something I don't see
[00:20:24] coming up enough in conversations with
[00:20:26] build teams as they think about their
[00:20:28] agent workflow. So, I thought it was
[00:20:29] important to lay it out, lay out the
[00:20:31] standards really clearly and help you
[00:20:33] understand how to think about these
[00:20:35] standards and of course the next one
[00:20:38] that's going to come along next week.
[00:20:39] I'll see you on the next one. Cheers.
