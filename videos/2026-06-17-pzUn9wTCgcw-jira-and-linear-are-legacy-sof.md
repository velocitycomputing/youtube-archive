---
video_id: pzUn9wTCgcw
title: Jira and Linear are legacy software
channel: Theo - t3․gg
url: "https://www.youtube.com/watch?v=pzUn9wTCgcw"
watched_date: 2026-06-17
watched_at: "2026-06-17T12:00:00Z"
watch_count: 1
duration_seconds: 1416
source: youtube-history-browser
added_date: 
history_label: Jun 17
history_order: 129
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1416
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Issue tracking systems like Jira and Linear were built around handoff-based development workflows where PMs scope work and engineers execute it later, requiring extensive overhead and process to manage. Linear solved this by removing complexity and prioritizing engineer experience, but with AI agents now handling procedural work at scale, the entire model is becoming obsolete. Linear's enterprise workspaces show 75% agent adoption and a 5x growth in agent-authored work over three months; the company is repositioning from "issue tracking" to "context into execution" with new tools like Linear Agent, Skills, and Automations. The speaker argues that traditional role specialization (PM, engineer, designer, QA) only made sense when humans could each fill one role, but with AI now capable of handling all specialties, we should abandon the historical way we structure and plan work—shifting instead to "code as planning" (building quick prototypes to understand scope rather than writing extensive specs upfront).

To apply this immediately: stop writing detailed specs before building. Instead, create a rough prototype in a few days to discover what's actually needed and identify architecture shortcomings, then write a much simpler, informed plan based on what you learned, and build the final version. Delegate repetitive procedural work (stand-ups, release notes, monitoring tasks) to automations—non-technical roles especially benefit since they haven't conditioned themselves to ignore automation opportunities like developers have. Most critically, re-examine whether your team's role silos (separate product and engineering orgs, distinct design teams) still make sense if AI can competently fill multiple roles; flatten divisions where possible and move from "handoff" workflows to "context + agent execution" models rather than continuing to reinvent human-based processes for machine actors.

## Transcript

[00:00:00] If you're anything like me, you probably
[00:00:01] hate issue trackers, which is why it's
[00:00:03] so exciting to see them die. That said,
[00:00:05] I'm a little scared of what's next. I
[00:00:07] need to address something really quick
[00:00:08] though. You might have thought the
[00:00:09] thumbnail was clickbait. I know I use
[00:00:11] fake tweets sometimes to get your guys
[00:00:12] attention. This time it wasn't. Even
[00:00:15] Linear is saying that issue tracking is
[00:00:17] dead. Kind of crazy that they are trying
[00:00:19] to kill the industry category that they
[00:00:21] have been leading for a while, but I'm
[00:00:22] actually really excited about the
[00:00:24] direction that they're going in. They
[00:00:26] just posted an article all about this
[00:00:28] and I couldn't agree more. It seems like
[00:00:29] the future of development is not a pile
[00:00:32] of issues on Jira and Linear that you
[00:00:34] slowly go through as a team, and instead
[00:00:36] it's going to look and feel a lot
[00:00:39] different. It's really hard to say what
[00:00:40] the future's going to look like, but I'm
[00:00:41] excited to explore what Linear is
[00:00:43] working on. But there is something I
[00:00:44] know is useful right now. Today's
[00:00:46] sponsor. Two years ago I had a
[00:00:47] conversation that has stuck with me
[00:00:49] since. It was a conversation with
[00:00:50] Guillermo, the CEO of Vercel. We were
[00:00:52] talking about things that we did right
[00:00:53] and wrong with our businesses. And the
[00:00:55] thing that he said that shocked me is
[00:00:57] that he deeply regrets rolling his own
[00:00:59] off at Vercel. That might sound insane
[00:01:01] with a company the size of Vercel. Like,
[00:01:02] obviously you should be rolling your own
[00:01:04] everything. It's your platform, right?
[00:01:06] Well, it turns out there's a lot of
[00:01:07] problems when you own your off layer,
[00:01:09] and they're not things like setting up
[00:01:11] Google to sign in correctly as annoying
[00:01:12] as that is. Problems go deeper. What
[00:01:14] happens when real companies want to
[00:01:16] onboard onto your product and they don't
[00:01:18] have the weird niche expectations their
[00:01:20] IT team expects to make it so their
[00:01:22] business employees can sign into your
[00:01:23] service using their existing
[00:01:25] authentication. Spoiler, I'm not the
[00:01:27] only one Guillermo's had this
[00:01:28] conversation with. And as he says here,
[00:01:30] "I think we could have done even more
[00:01:32] business if we had partnered with WorkOS
[00:01:33] earlier. It's been incredibly well
[00:01:35] received." I'm sure you've guessed by
[00:01:37] now, but today's sponsor is WorkOS, the
[00:01:38] off platform used by OpenAI and
[00:01:40] Anthropic, Vercel, T3 Chat, and many,
[00:01:43] many more. WorkOS has found an
[00:01:44] incredible balance of developer
[00:01:46] experience and enterprise readiness,
[00:01:48] where they have everything you need to
[00:01:49] onboard these real companies. Never
[00:01:51] having to think about identity provision
[00:01:53] again is a gift from the heavens, and I
[00:01:55] am so thankful for WorkOS making it so
[00:01:57] that I never have to configure ADP again
[00:01:59] for the rest of my life. If that's all
[00:02:01] they offered it would be worth it, but
[00:02:02] there's so much more to the platform.
[00:02:04] AuthKit makes it really easy to set up
[00:02:05] the buttons and panels that you need for
[00:02:07] your users. MCP Auth means you can
[00:02:09] finally add authorization to your MCP
[00:02:11] servers. Directory sync makes it trivial
[00:02:13] for companies to keep things in sync
[00:02:14] between their dashboards and your
[00:02:16] product. Vault's one of the best ways to
[00:02:18] store user-specific encrypted values,
[00:02:20] things like API keys that they might be
[00:02:22] using in your service. And there's so
[00:02:24] much more to explore. Your next fear
[00:02:26] going to be the price cuz there's no way
[00:02:27] it can be that good for cheap, right?
[00:02:29] Well, you have nothing to worry about
[00:02:30] cuz the first million users are free.
[00:02:33] Get yourself enterprise ready at
[00:02:34] soidiv.link/workos.
[00:02:36] I'm very excited to read into what
[00:02:38] Linear is cooking here. You know they're
[00:02:39] cooking something different cuz this is
[00:02:40] the only not dark mode page I've ever
[00:02:42] seen Linear ship. They actually took the
[00:02:44] time to make it so when you read this
[00:02:46] particular page, it is light mode and
[00:02:48] they flipped the logo and everything in
[00:02:49] the top nav. They also did the usual
[00:02:51] Linear thing of trying way too hard in
[00:02:53] design for something that doesn't matter
[00:02:54] that much with the logo. You can move
[00:02:55] your cursor through like a fluid and
[00:02:57] click to pulse it. It's cool. It's very
[00:03:00] uh Linear of them. Anyways, issue
[00:03:02] tracking is dead. It was built for a
[00:03:04] handoff model of software development. A
[00:03:07] PM would scope the work, engineers would
[00:03:08] pick it up later, and the system was
[00:03:10] filled with prioritization, negotiation,
[00:03:13] and workflows to bridge the gap. That
[00:03:14] ceremony came from real constraints.
[00:03:17] Engineering time was scarce. Teams
[00:03:19] needed a way to route work carefully
[00:03:20] across roles and functions. Absolutely
[00:03:23] agree. This is my whole life when I was
[00:03:24] an engineer back at Twitch. It was the
[00:03:26] chaos of breaking up large piles of work
[00:03:29] into small tickets, throwing those into
[00:03:30] a queue, and then going through them,
[00:03:32] assigning them to people, and trying to
[00:03:34] guesstimate when all of the work
[00:03:35] necessary would be done to ship the
[00:03:37] thing they all lean into. But over time,
[00:03:39] complexity started to look like
[00:03:40] sophistication. The more process a
[00:03:42] system could absorb, the more advanced
[00:03:44] it seemed. Overhead kept growing and the
[00:03:46] process became work itself. Yep, my Jira
[00:03:49] dashboard back at Twitch would take over
[00:03:51] 2 minutes to load. Technically saying
[00:03:54] that is against the terms of service for
[00:03:56] Jira, but thankfully I have been out of
[00:03:58] Twitch for over 5 years now, so I can
[00:03:59] say whatever the [ __ ] I want. Yeah, Jira
[00:04:02] ran like [ __ ] garbage, and that was
[00:04:05] because we had filled it with so much
[00:04:07] complex [ __ ] across the absurd
[00:04:09] number of tickets in different fields
[00:04:11] and data links across things at Twitch.
[00:04:14] And that's just what happens. When you
[00:04:15] have a system like this, every single
[00:04:17] feature is going to be used and abused
[00:04:20] until it breaks at the seams. People are
[00:04:22] confused about why I can't talk about
[00:04:25] Jira's performance. They did a terms of
[00:04:26] service update back in the day when I
[00:04:28] was at Twitch that explicitly banned
[00:04:32] talking about the performance
[00:04:33] characteristics of Jira and sharing
[00:04:35] benchmarks for its performance when I
[00:04:37] was at Twitch. But now it's been long
[00:04:39] enough that I will tell you guys Jira
[00:04:41] performs like [ __ ] garbage at real
[00:04:42] companies. Also, yes, I do have Jira as
[00:04:45] a banned term on my switch streams
[00:04:47] because I thought it was funny to do. I
[00:04:48] might need to go remove that if one of
[00:04:50] the moderators can go figure out how to
[00:04:51] do that, please do. At least for now.
[00:04:53] Yeah, Jira, the correct spelling with
[00:04:55] the star. We need to not say the J-word
[00:04:57] if we can avoid it. Back to the article.
[00:04:59] Linear's always been built on the
[00:05:00] opposite belief, the opposite of the
[00:05:02] system continuing to grow and get more
[00:05:03] complex. The best systems should remove
[00:05:05] overhead so the teams can focus on
[00:05:07] building. That's absolutely how Linear
[00:05:09] felt. It felt like they were trying to
[00:05:10] remove as much weight as possible. So
[00:05:12] getting in, looking at the issues,
[00:05:14] filtering through things, and getting
[00:05:15] the data you need to go back to work was
[00:05:17] as easy as possible. And that's why so
[00:05:19] many engineers preferred Linear. It was
[00:05:20] kind of a bet on engineers being the
[00:05:22] ones who made important decisions at
[00:05:24] companies because Jira was the thing
[00:05:26] that product managers picked because
[00:05:27] that's who it was marketed to, to be
[00:05:28] clear. And Linear wanted something the
[00:05:30] engineers liked because they hated using
[00:05:32] Jira at the companies they were at. So
[00:05:34] they made Linear to make something nice
[00:05:36] and simple and elegant for enges, and it
[00:05:38] more than succeeded and is now doing
[00:05:39] quite well. I would bet they have a
[00:05:40] similar number of users and a
[00:05:42] significantly higher number of startups
[00:05:43] than a Jira ever has or will. But now
[00:05:46] we're in the AI era and things are
[00:05:48] changing fast. Again, their goal is to
[00:05:50] remove overhead and according to them,
[00:05:51] agents push the removal of that overhead
[00:05:53] even further. They can make software dev
[00:05:54] a lot simpler. Planning, implementation,
[00:05:56] and code review begin to compress as
[00:05:59] agents absorb more of the procedural
[00:06:01] work. You'll get to spend more time on
[00:06:02] intent, judgment, and taste, and less
[00:06:04] time managing the mechanics of the
[00:06:06] process. This one's particularly
[00:06:08] interesting to me because I actually
[00:06:10] kind of worked the same way when I was
[00:06:12] at Twitch. It was so common to have
[00:06:14] tickets that just didn't correctly
[00:06:16] estimate how hard things were and missed
[00:06:18] a bunch of subtasks that were important.
[00:06:20] And to be frank, I never read a spec
[00:06:23] that was written before the product was
[00:06:25] made that even came close to describing
[00:06:27] what the product actually would be, how
[00:06:28] it should be implemented, and how long
[00:06:30] it would take. It was almost always
[00:06:31] entirely inaccurate. So, what I did
[00:06:34] instead is I would go build a small
[00:06:36] version of what we were aiming for in 1
[00:06:38] to 3 days just to force out whatever
[00:06:40] could let us test the UX. And through
[00:06:42] that process, I'd be able to identify
[00:06:44] any tech shortcomings we have to touch
[00:06:46] out of a very clear service area of
[00:06:48] things we have to know about and be
[00:06:50] involved in order to make this work. Out
[00:06:52] of a demoable, usable version of the
[00:06:54] product that we could use for testing
[00:06:55] both internally and in front of users
[00:06:57] when we brought users into the office.
[00:06:58] And through that, we were able to
[00:06:59] collect a ton of information in order to
[00:07:02] make sure that we steered the product
[00:07:04] and its design in the right direction.
[00:07:06] The result of this is that we could
[00:07:07] write way better specs because we
[00:07:08] actually had a rough idea of what the
[00:07:10] product would look like and how it would
[00:07:12] work. The more surprising part for me,
[00:07:14] though, was how often we would just ship
[00:07:16] that quickly built version. And to be
[00:07:18] very clear, the point of this process
[00:07:19] wasn't to get the feature out faster. It
[00:07:21] was to develop a working prototype of it
[00:07:24] to know what was required to do it and
[00:07:26] to make a better spec and most
[00:07:27] importantly, have a version that people
[00:07:29] could start testing to make sure this is
[00:07:30] even worth doing. And I would say about
[00:07:32] half the time we ended up slightly
[00:07:33] polishing that first pass and just
[00:07:35] shipping it because we had no reason to
[00:07:37] go much further with it. The amount of
[00:07:39] times I had a a that should have been a
[00:07:40] huge 20-page spec that we spent weeks
[00:07:44] writing and debating that just took me a
[00:07:46] few days and we ended up shipping as is
[00:07:48] is hilarious. To be frank, this hurt my
[00:07:50] career growth to an extent because we
[00:07:52] didn't have all these fancy documents we
[00:07:53] could point out during my promotion
[00:07:55] process that was built all around that
[00:07:56] [ __ ] But it did make me pretty well
[00:07:58] regarded internally and this is still
[00:08:00] referred to as the Theo method or the
[00:08:02] Theo prototype at Twitch to this day.
[00:08:04] Depending on the team, of course, but a
[00:08:06] lot of teams still do things this way. I
[00:08:07] know I fully overhauled a handful of
[00:08:09] teams process around product design by
[00:08:11] just refusing to write a boring useless
[00:08:13] spec. There's nothing I hate more than
[00:08:15] useless [ __ ] being done by engineers
[00:08:18] that doesn't even make them feel good.
[00:08:20] Engineers love useless [ __ ] as long
[00:08:21] as it's inside of their terminal. They
[00:08:23] hate it when it's inside of Google Docs.
[00:08:24] So trying to get them away from those
[00:08:26] things and instead back into their
[00:08:28] editor was always beneficial. And it
[00:08:30] turns out a lot of people agree, they
[00:08:31] just weren't good enough devs to agree.
[00:08:33] Okay, I shouldn't say good cuz this is a
[00:08:34] different skill. There's a lot of very
[00:08:36] talented devs that don't build very
[00:08:37] fast. There's a lot of average devs that
[00:08:39] happen to build really fast. That's how
[00:08:40] I would have described myself when I was
[00:08:42] at Twitch. I was a okay to decent dev,
[00:08:45] but I was really good at trimming the
[00:08:46] fat, identifying where in the system we
[00:08:48] can insert the thing to make it way
[00:08:50] easier to build, and then building the
[00:08:52] thing. That was one of the things that
[00:08:53] made me unique. But it's also a
[00:08:54] capability that almost all engineers now
[00:08:56] have because of agents. Benefits and
[00:08:58] negatives. That said, I think that way
[00:09:00] of building is so much better. Make a
[00:09:02] first version of the thing, then make
[00:09:04] the spec, then build it correctly,
[00:09:06] rather than write a spec assuming you
[00:09:08] know how it will work, and build it
[00:09:10] wrong because you were incorrect with
[00:09:11] the spec, and then keep [ __ ] throwing
[00:09:13] band-aids on it until it kind of works,
[00:09:14] and then you ship a broken thing. Hate
[00:09:16] that strategy. The first version of
[00:09:18] software will always be less than ideal.
[00:09:20] Do it first to figure it out, throw it
[00:09:22] away, and then make a good version
[00:09:23] after. Now that is much more viable. And
[00:09:25] it's nice to see Linear realizing the
[00:09:27] same thing, too. I almost feel as though
[00:09:29] these types of issues tracking systems
[00:09:31] discourage that type of exploration
[00:09:33] building because it's so valuable.
[00:09:35] According to Linear, the shift with
[00:09:38] agents is already underway. Coding
[00:09:39] agents are installed in more than 75% of
[00:09:42] Linear's enterprise workspaces. Not just
[00:09:45] side projects, not just people playing
[00:09:46] around with it. The enterprise deals
[00:09:48] they have with big businesses using
[00:09:49] them. 75%
[00:09:51] or more are already using agents as
[00:09:54] integrations in Linear. I bet you the
[00:09:55] other 25% are largely copy-pasting the
[00:09:58] issues into their agent of choice to get
[00:10:00] the code built. In the last 3 months,
[00:10:02] the volume of work completed by agents
[00:10:04] grew 5x. Do you understand how crazy
[00:10:08] that is in particular? That's the Opus
[00:10:10] 4.5 effect when people woke up to how
[00:10:12] powerful these models could be and the
[00:10:14] level of work they could get done. And
[00:10:16] obviously now with Codex, we can go even
[00:10:18] further. They also noted that agents
[00:10:20] authored nearly 25% of new issues, which
[00:10:22] is very interesting to me. I still
[00:10:24] haven't gotten into the letting AI make
[00:10:26] the issues side of things. I let them
[00:10:28] close them, but I don't let them open
[00:10:29] them yet. Maybe I need to get over that.
[00:10:30] In this new world, the next system is
[00:10:32] not designed around hand-offs. It's
[00:10:34] designed around context and agents.
[00:10:36] Agents aren't mind readers. They become
[00:10:38] useful through context. Customer
[00:10:39] feedback, internal ideas, strategic
[00:10:41] direction, decisions, and code all need
[00:10:44] to be captured in a system that humans
[00:10:46] and agents can work from together. Very
[00:10:49] interesting. That system should
[00:10:50] understand intent, route work to the
[00:10:52] right actor, escalate when needed, and
[00:10:54] keep execution moving. It should help
[00:10:56] teams move work forward, not trap them
[00:10:59] inside the process. The number of people
[00:11:01] I know whose jobs are effectively just
[00:11:03] using Linear or Jira is heartbreaking.
[00:11:06] Like those apps are good. Okay, one of
[00:11:08] those apps is good, but none of those
[00:11:10] apps are good enough to spend your day
[00:11:12] in them. As somebody who spends their
[00:11:13] day in email lately, I I empathize. And
[00:11:16] this is apparently what Linear plans to
[00:11:17] become. Linear is the shared product
[00:11:19] system that turns context into
[00:11:21] execution. That's a really cringe
[00:11:22] one-liner. I don't like that. I hope
[00:11:24] they rethink that. It holds feedback,
[00:11:26] intent, decisions, plans, and code,
[00:11:28] shapes that context into work, and helps
[00:11:30] humans and agents carry it all the way
[00:11:32] to production. So, you have customer
[00:11:34] requests, bug reports, and feedback.
[00:11:35] Those become the context with the plans,
[00:11:37] discussions, specs, all the above. That
[00:11:39] becomes rules that are used to actually
[00:11:41] command the agents within the context,
[00:11:43] like automation skills and permissions.
[00:11:44] That is handed to the agents, and the
[00:11:45] output is the product. Notice that there
[00:11:47] are no issues here. Notice that there is
[00:11:50] no sprint planning here. This is
[00:11:52] incentive, context, rules, developer,
[00:11:55] effectively. In order to get there, they
[00:11:57] just launched a bunch of new things.
[00:11:58] They have a linear agent that you can
[00:12:00] use to actually do a lot of the work
[00:12:03] against your context. They have a new
[00:12:04] skills product, which lets you codify
[00:12:06] things that are being done over and
[00:12:08] over. And then automations, which will
[00:12:10] allow you to automatically trigger
[00:12:12] things remotely. I'm assuming. Yeah,
[00:12:14] triage will trigger agent workflows the
[00:12:15] moment an issue enters the system. Every
[00:12:17] new issue adds context to your
[00:12:18] workspace, and Linear can now
[00:12:20] intelligently refine, synthesize, or
[00:12:21] take action on the context the moment it
[00:12:23] arrives. Cool. I think automations are
[00:12:25] more and more going to become like the
[00:12:27] next new thing. Do I not even have the
[00:12:28] Codex app installed on this computer? I
[00:12:30] don't. I just formatted this, and I've
[00:12:32] been using a a better app recently,
[00:12:33] believe it or not. Uh certain T3 code. I
[00:12:37] want to show a feature in here. Back in
[00:12:39] this lackluster, laggy app that broke my
[00:12:41] brain because of how cool it is to build
[00:12:43] this way, but just doesn't handle the
[00:12:45] scale that we build at, sadly. So, it
[00:12:46] does have some really cool things in it.
[00:12:48] I think the skills browser and creator
[00:12:50] thing is relatively cool. I've been able
[00:12:52] to make some useful things in this. It's
[00:12:54] not my favorite thing, but it's decent.
[00:12:56] I don't think the official OpenAI docs
[00:12:58] skill should be included by default.
[00:13:00] That's cringe. Happy I went to this
[00:13:02] page. I had a bunch of useless skills
[00:13:03] that were on by default. That is fixed
[00:13:05] now, though. But that's not the time I'm
[00:13:06] here for. I'm here for automations. I
[00:13:08] will be honest, I overlooked automations
[00:13:11] when I started using the Codex app, and
[00:13:13] I've noticed that most devs have as
[00:13:15] well. For whatever reason, devs just
[00:13:17] aren't as into this side of things. And
[00:13:20] I kind of get why. A lot of the examples
[00:13:22] are just not very good for developers.
[00:13:24] Like, what dev wants to summarize
[00:13:27] yesterday's get activity for a stand up?
[00:13:29] They don't, I promise you. What dev
[00:13:31] wants to synthesize this week's PRs,
[00:13:33] rollouts, and incidents and reviews into
[00:13:35] a weekly update? The kind that's not
[00:13:37] very good at coding and is on a quick
[00:13:38] path to become a PM or a designer of
[00:13:40] some form. And then release prep. Draft
[00:13:43] weekly release notes for merged PRs.
[00:13:45] Before tagging, verify change logs,
[00:13:47] migrations, feature flags, and tests.
[00:13:49] Let's say I want to set up one of these.
[00:13:51] I click it. I can set a schedule, so I
[00:13:53] can choose when I want it to fire. If I
[00:13:55] want it to fire daily at 9:00 a.m., I
[00:13:57] can choose what project it fires in. It
[00:13:58] will spin up a work tree and then go do
[00:14:00] the thing. You can even choose which
[00:14:01] model and reasoning levels with this
[00:14:03] really weird pinned thing there. God, I
[00:14:05] hate this UI. Whatever, you get the
[00:14:07] idea. This is a concept that I
[00:14:09] personally didn't think was the coolest
[00:14:12] thing ever. It wasn't a big, oh yeah,
[00:14:14] this is great. Something I learned
[00:14:16] recently is that there's an increasing
[00:14:18] number of non-devs using the Codex app
[00:14:21] lately. A lot of them are doing it
[00:14:23] because they have things on their
[00:14:24] computer that they wanted to be able to
[00:14:26] do, but even more using it from what
[00:14:28] I've seen because they love automations.
[00:14:31] I know a comms person at a startup
[00:14:32] that's using an automation to go check a
[00:14:35] bunch of different websites and news
[00:14:36] sources for mentions of their company in
[00:14:39] order to then bring it into Slack. So,
[00:14:41] the automation will fire, go find all of
[00:14:44] this info, and then DM her on Slack the
[00:14:46] results. And this person's never been a
[00:14:48] dev before. They had friends at the
[00:14:49] company using Codex app. They thought it
[00:14:51] was cool to check out, and they just
[00:14:52] fell in love with automations. They have
[00:14:54] like 30 plus of them now doing all sorts
[00:14:55] of [ __ ] To normies, this is the first
[00:14:58] time they could automate part of their
[00:15:00] life or work. And I don't think most
[00:15:03] developers think this way because to an
[00:15:05] extent, we already learned how to
[00:15:06] automate things. That's why we're
[00:15:08] developers. But, we know work it is to
[00:15:11] automate things, so we often don't
[00:15:12] bother because writing the code to
[00:15:15] automate something like grabbing all of
[00:15:17] the commits that you did in the last
[00:15:18] week and dumping that as in some
[00:15:20] information to you on Slack or whatever.
[00:15:22] That's code all of us can write. We're
[00:15:23] all devs. Almost every single person
[00:15:25] watching this is good enough at writing
[00:15:26] code to do something like that. But,
[00:15:28] it's also a lot of work to do it. So,
[00:15:30] we've kind of trained our brains to
[00:15:31] ignore the urge to automate things that
[00:15:33] aren't super useful. People who have
[00:15:35] never had this experience before are all
[00:15:37] of a sudden able, and now that it's
[00:15:39] easier, they're doing it even more. I
[00:15:41] know way more people doing automations
[00:15:43] outside of the dev world than inside of
[00:15:44] it. And if I'm being frank, and this is
[00:15:46] not meant to be an insult, this is an
[00:15:47] observation, the devs I find who are
[00:15:49] using automations a lot, who are using
[00:15:51] open claw a lot, and using those types
[00:15:53] of things, tend to be the less good devs
[00:15:55] that I've worked with. No offense to
[00:15:57] these two particular people, but two of
[00:15:58] the actual worst devs I've ever seen in
[00:16:00] my life are open claw gods. One of them
[00:16:03] built their own equivalent of open claw
[00:16:05] before it came out, and it barely
[00:16:07] worked, and it resulted in her spam
[00:16:08] texting me dozens of times a day as she
[00:16:10] was trying to make it function at all.
[00:16:11] It's kind of weird. Them liking
[00:16:13] automations doesn't make them bad, but
[00:16:15] it almost seems like we as devs have
[00:16:17] wired our brain against this type of
[00:16:19] thing. And people who are less wired
[00:16:20] into the dev world are more wired in a
[00:16:23] way where they're willing to do this
[00:16:24] type of thing. So, while the linear
[00:16:25] automations that they're describing here
[00:16:27] might seem not that cool to us as devs,
[00:16:30] I know to me it's like my instinct is,
[00:16:31] "Oh, whatever. What is it actually going
[00:16:34] to add?" I promise you the PMs, the
[00:16:37] leads, the people who don't code are
[00:16:39] going to love this, and they're going to
[00:16:40] massage it into something useful almost
[00:16:43] certainly. I will say the end here is
[00:16:45] kind of cringe. These updates build on
[00:16:47] our early work in triage intelligence,
[00:16:49] deep integrations with cloud coding
[00:16:51] agents, and other AI tools. By grounding
[00:16:53] agents in the full context of your
[00:16:55] product and code base, we're collapsing
[00:16:57] the distance between an idea and its
[00:16:58] implementation. Issue tracking was built
[00:17:00] for hand-offs. Linear turns context into
[00:17:03] execution. So, here's my hot take. I
[00:17:05] personally not found much value in
[00:17:07] things like G stack. If you're not
[00:17:08] familiar, I might do a whole video on it
[00:17:10] in the near future. The point of G stack
[00:17:12] is it gives you a bunch of skills that
[00:17:15] are effectively different characters
[00:17:17] that are being played by the models to
[00:17:20] do specific types of things. Gary built
[00:17:23] these specialists. The CEO founder, the
[00:17:26] eng manager, the senior designer, the
[00:17:27] design partner. It should be clear,
[00:17:29] these aren't like code or anything
[00:17:30] complex. These are just markdown. These
[00:17:32] are just text files that describe how
[00:17:34] the model should behave in these times
[00:17:36] and in these particular requests. For
[00:17:39] what it is worth, I think this is
[00:17:40] [snorts] cringe as [ __ ] There are some
[00:17:42] fun ideas in here like {slash} codex,
[00:17:44] which cuz this is built for Claude code.
[00:17:46] This will call the codex CLI from Claude
[00:17:48] code to review the changes and give a
[00:17:51] second pass saying, "Yeah, I'm codex. I
[00:17:53] think that's good or bad." Chat's
[00:17:54] already figured it out. So, this is how
[00:17:56] devs role play. Yeah. My hottest take is
[00:17:59] that the way we have broken up work
[00:18:01] historically only made sense because
[00:18:04] developers and other fields that we
[00:18:06] interfaced with were different enough
[00:18:08] and hard enough to find and level up in
[00:18:10] that we needed to have these roles so
[00:18:12] that we could get the work done and meet
[00:18:15] the quality bars that we needed to. But,
[00:18:16] let's be real here. If the model is
[00:18:18] smart enough to be the CEO, to be the
[00:18:20] eng manager, to be the designer, to be
[00:18:21] the design partner, to be the staff
[00:18:23] engineer, to be the debugger, to be a
[00:18:24] designer who also knows how to code, to
[00:18:26] be the QA lead and reporter. If the
[00:18:28] model is smart enough to be all of these
[00:18:29] things, why are we still defining these
[00:18:32] things? Why do we need to have a thing
[00:18:35] for this anymore? My hot take is that
[00:18:38] the way we have broken up all these
[00:18:40] pieces made sense when humans did it and
[00:18:43] a given human could only do one of these
[00:18:45] things. Now that AI is smart enough to
[00:18:46] do most of these things, the way we
[00:18:49] break up the work no longer makes sense.
[00:18:51] And I see this all over the place. One
[00:18:53] of the place I see it the most is
[00:18:55] multi-step planning processes. There's
[00:18:57] no reason for planning to take hours.
[00:19:00] There's no reason for planning to fill
[00:19:02] your entire context. There's no reason
[00:19:04] that planning should have lots of
[00:19:05] different sub plans and steps and
[00:19:07] process and specs and all of that
[00:19:09] [ __ ] Models are for the most part
[00:19:11] good enough. So, instead of spending all
[00:19:13] of this time after you take in the
[00:19:15] request, bug report, or whatever, to
[00:19:17] build all of these additional pieces in
[00:19:20] for context, like the specs, technical
[00:19:22] design, the plans, the decisions, the
[00:19:24] summaries, and all that [ __ ] just for
[00:19:25] the model to go do the build, why not
[00:19:27] have it start with a build but accessing
[00:19:29] all of these things as tools? What if
[00:19:31] the model could do a first pass, use
[00:19:34] these things, figure out what doesn't
[00:19:35] doesn't work, and then have the first
[00:19:37] pass be the plan, so to speak? Not that
[00:19:39] the code is going to be used directly,
[00:19:41] but the process of it building and
[00:19:43] touching all of those things is enough
[00:19:45] for you to realize, oh, I guess that's
[00:19:47] how this works. I guess that's where the
[00:19:48] flaws are. And then from there, make a
[00:19:50] much simpler plan that actually touches
[00:19:53] the things you need, and then go build
[00:19:54] it again. We've went through this loop
[00:19:55] already with MCP, funny enough, where we
[00:19:57] thought this new standard was going to
[00:19:58] be the best way for models to access
[00:20:00] data and do things, and then it sucked.
[00:20:02] So, we ended up moving it back to code,
[00:20:04] because it models are really good at
[00:20:06] writing code. And once the models could
[00:20:07] use code to use MCP, all of a sudden it
[00:20:10] got way, way better and way more
[00:20:12] performant and reliable. I think we're
[00:20:13] going to go through the same thing here.
[00:20:15] We're in a weird spot now, where we're
[00:20:16] going to reinvent everything based on
[00:20:19] how it always worked, even though it
[00:20:20] doesn't [ __ ] matter. And what we're
[00:20:22] going to end up back at is code as
[00:20:24] planning. We're going to reinvent plans
[00:20:27] a million [ __ ] times over the next
[00:20:28] year, and then we're going to just go
[00:20:30] back to code. I like what Naman had to
[00:20:32] say here. This is the functional versus
[00:20:34] product divisions at companies. I
[00:20:36] absolutely agree there. Here's a fun
[00:20:38] fact I learned recently. Did you know
[00:20:39] that GitHub has a separate product and
[00:20:41] engineering org? Did you know that they
[00:20:43] share zero leadership? That product and
[00:20:45] eng, the people who actually build the
[00:20:47] product, cannot interact with each
[00:20:49] other? Cuz I didn't know that until
[00:20:50] recently, and it explained a lot of why
[00:20:52] GitHub is a [ __ ] disaster. I don't
[00:20:54] see how GitHub can ever get better if
[00:20:55] the product people don't code and the
[00:20:57] devs don't make product decisions. Kind
[00:20:59] of makes sense that GitHub is an
[00:21:00] absolute [ __ ] [ __ ] show. And if we
[00:21:02] keep pretending that way of building
[00:21:04] makes sense, we're going to keep
[00:21:05] reinventing shitty processes that only
[00:21:07] worked for humans. There is a way I
[00:21:09] could be wrong here though, and I don't
[00:21:10] know cuz I haven't done enough of this
[00:21:12] like code as planned type thing because
[00:21:14] I'm too busy to do either coding as a
[00:21:15] plan or coding in general. I have way
[00:21:17] too much [ __ ] [ __ ] going on. I do
[00:21:18] plan to do this, pun intended, but there
[00:21:21] is a potential failure case in the way
[00:21:22] I'm thinking of this that I am imagining
[00:21:24] now, which is that the reason agents can
[00:21:26] work better this way is because they're
[00:21:27] trained on data from humans and there's
[00:21:29] enough data of humans working this way
[00:21:31] that eventually the AI can do it too.
[00:21:33] Perhaps. And it might be better for the
[00:21:34] AI to behave like a human than for it to
[00:21:36] behave like an AI because the AI is
[00:21:38] trained on humans in the first place.
[00:21:39] Yeah. I don't think that will be the
[00:21:41] case though. I still pretty firmly
[00:21:42] believe that the best plan is a
[00:21:44] prototype and if you still need a plan
[00:21:45] after that, you'll be able to write a
[00:21:47] much more informed one after you make a
[00:21:49] first trial version of the thing. So
[00:21:51] instead of all of this nonsense, I would
[00:21:53] take the handful of useful pieces of
[00:21:55] context here, throw those into a tool
[00:21:57] call of some form, and then tell the
[00:21:59] model, "I want to build a scrappy
[00:22:00] prototype of this feature that was
[00:22:03] described in whatever request bug
[00:22:05] reporter feedback was provided. Help me
[00:22:07] identify the scope of this and then
[00:22:09] build this first version so that we can
[00:22:11] understand what foot guns and other
[00:22:12] shortcomings might exist in the code
[00:22:14] base as we implement this." You get this
[00:22:15] early version, you get a bunch of the
[00:22:17] things that were hard about it, and then
[00:22:18] you can go build the right one. I think
[00:22:20] that's probably going to be a better
[00:22:21] bet. I could be wrong, but having built
[00:22:23] with a lot of this [ __ ] myself, that has
[00:22:24] been generally the direction that has
[00:22:26] worked for me. Hell, I've been building
[00:22:28] this way since before AI. I cannot tell
[00:22:30] you how many times I filed a shitty PR
[00:22:32] to one of our repos just to showcase the
[00:22:34] UX or DX that I had in mind and then
[00:22:37] poor Julius had to go make it into
[00:22:38] actual production ready code. As Flambo
[00:22:40] said in shot, "Love this. Build it three
[00:22:42] times and throw away the first two."
[00:22:43] Yeah. This didn't make sense when code
[00:22:45] was expensive, but now code is cheap as
[00:22:47] [ __ ] Build the code. Stop inventing all
[00:22:49] this [ __ ] So in some senses, Linear
[00:22:51] is far ahead of the curve here. In
[00:22:53] others, I think they're still thinking a
[00:22:54] little too much about how teams were
[00:22:57] split up historically and not enough
[00:22:59] about how that's going to change. And
[00:23:00] I've also never been so confident that
[00:23:01] Jira is [ __ ] cuz you know they aren't
[00:23:03] thinking about any of this. They are
[00:23:05] thinking so little about this that they
[00:23:07] bought one of my least favorite
[00:23:08] companies, the browser company, which is
[00:23:10] a very good fit if you know anything
[00:23:11] about how Jira and Atlassian work as
[00:23:13] well as how much the browser company
[00:23:15] doesn't work.
[00:23:17] Think I've said all I have to here. As
[00:23:18] you can tell, I have a lot of feelings
[00:23:20] and hopefully this will be useful to you
[00:23:22] guys. I know a lot of you work at real
[00:23:23] companies where you're using things like
[00:23:24] issue trackers and I would love to hear
[00:23:26] from y'all. What are you guys doing now
[00:23:27] and how is it changed with AI? Are you
[00:23:29] using AI with your issues? What does
[00:23:31] that look like? I'm actually really
[00:23:32] curious and want to hear more. Let me
[00:23:33] know and until next time,
[00:23:35] peace nerds.
