---
video_id: 8gATb_QUcYE
title: "Google's New AI Just Changed AI Business Forever (Gemini 3.5)"
channel: Cyril Imhof
url: "https://www.youtube.com/watch?v=8gATb_QUcYE"
watched_date: 2026-05-29
watched_at: "2026-05-29T12:00:00Z"
watch_count: 1
duration_seconds: 1924
source: youtube-history-browser
history_label: Friday
history_order: 41
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1924
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What Was Discussed:**
The episode covered harness engineering as the foundation for effective AI systems—using an orchestrator agent paired with smaller, cheaper agents for specialized tasks rather than applying expensive frontier models to every problem. Google's Gemini 3.5 Flash was released with performance on par with or exceeding the previous Pro model, but at significantly higher pricing than prior Flash versions, raising questions about the cost trajectory for 3.5 Pro. The hosts discussed how AI businesses have two paths: revenue acceleration (sales, GTM, RFPs) or cost-cutting, with rising API costs making revenue-focused solutions more viable. They highlighted emerging pain points including rising development costs (developers now cost companies their salary plus API fees), the inefficiency of human-to-human artifact handoffs in organizations, and the growing importance of memory infrastructure (Micron hit $1 trillion market cap) as reasoning workloads require high-bandwidth memory.

**What's Actionable for You:**
Build AI products using the orchestrator pattern—reserve expensive models like Opus/GPT-4.5 for the main coordinator and use cheaper, faster open-source models for sub-tasks to control costs. Prioritize building revenue-acceleration tools (enhanced sales processes, outreach automation, RFP assistance) over cost-cutting solutions until AI pricing stabilizes. Wait for Gemini 3.5 Pro's release and pricing before committing to Gemini—Flash pricing may decrease when Pro launches. If building multi-agent systems, use frameworks like Claude's or open-source alternatives like Hermes rather than custom builds. Consider that log compression tools are becoming essential for managing agent debugging costs at scale. Monitor energy and memory infrastructure stocks as sustained tailwinds for data center growth.

## Transcript

[00:00:00] Hello everybody and welcome back to
[00:00:02] episode 52 of This is the year the Swiss
[00:00:04] AI engineering and builder podcast yet
[00:00:07] again with me today. We were both a
[00:00:10] little bit off and out on the weekend
[00:00:12] after our gathering on Friday here in
[00:00:14] Lisbon. Uh but we're back stronger than
[00:00:16] ever with a new episode for you guys in
[00:00:18] the audience. Today we're talking about
[00:00:20] our latest insights into harness
[00:00:22] engineering, the actual building block
[00:00:24] that's really enabling great multi- aent
[00:00:26] and aentic AI systems in production.
[00:00:29] Today we're also talking briefly about
[00:00:31] let's say a bit of a of a pulse feel on
[00:00:34] the AI builder community. Should you be
[00:00:35] building a particular solution that's
[00:00:37] actually accelerating revenue for your
[00:00:39] target ICP or ideal customer profile and
[00:00:42] or then on more on the cost cutting side
[00:00:44] of things which comes with new
[00:00:46] complexities. This will then segue us to
[00:00:48] a pricing discussion very briefly. We're
[00:00:50] also talking about Gemini 3.5 flash, one
[00:00:53] of the most overlooked models probably
[00:00:56] recently. And we finish it off with a
[00:00:58] bit of a victory lap on our end on
[00:01:00] Micron that just hit $1 trillion and we
[00:01:03] called it on this show roughly on the
[00:01:06] fifth episode. Uh that yeah the re the
[00:01:08] age of reasoning is here and that is why
[00:01:11] all these uh memory stocks should be
[00:01:13] flying very much soon. So we are taking
[00:01:15] a bit of a victory lap. But that's
[00:01:16] basically what what is happening.
[00:01:18] anything from the model provider stack
[00:01:21] to the compute stack to the
[00:01:22] infrastructure stack and maybe now also
[00:01:24] the memory stack as we talk today
[00:01:26] because all these reasonings all these
[00:01:28] memory um ideas they need high bandwidth
[00:01:31] memory so that's also a potential kind
[00:01:33] of domain maybe that is super
[00:01:35] interesting there's two companies maybe
[00:01:37] three but two worth mentioning Micron
[00:01:39] and SKH highex from Korea that are in in
[00:01:41] this space feel free to check that out
[00:01:43] carefully as well in case you're
[00:01:44] interested but all this memory memory
[00:01:46] idea is really really needed and the
[00:01:48] data or AI factories as Jensen and one
[00:01:51] call it but welcome back on the show
[00:01:54] happy to have you you are the AI
[00:01:56] engineering wizard last time we talked
[00:01:58] about many things amongst others that
[00:02:00] you're building AI agents of course not
[00:02:03] many that many and every single day but
[00:02:05] one very holistic super smart agent but
[00:02:08] how are you doing you're also back from
[00:02:10] the from the illness journey
[00:02:13] yeah uh but like most things today uh
[00:02:16] nowadays it is very very fast. So got
[00:02:19] very sick, got healthy in a matter of a
[00:02:21] couple days. Never really stopped to
[00:02:23] think if AI could have been of any help.
[00:02:26] I think biomedical is one of those uh
[00:02:29] areas that it's going to be hard for for
[00:02:31] AI to fully replace humans. Um I know in
[00:02:35] research that they're trying to I know
[00:02:37] people are self diagnosing a bunch with
[00:02:38] it. Uh but well when you're desperate
[00:02:42] what you need is like system overthec
[00:02:43] counter medication. Uh I don't think any
[00:02:46] C agent can can truly but truly help
[00:02:48] you.
[00:02:48] >> I mean in my case since I was probably
[00:02:51] having the same I would say fluish stuff
[00:02:54] that you've had. I was kind of trying to
[00:02:56] as usually in these situations when I
[00:02:58] have a bit of time I was trying to
[00:02:59] experiment between Chachi PT and CL the
[00:03:03] way they guide me through this journey
[00:03:04] of like fever and what what have my like
[00:03:07] my symptoms are going to look like and
[00:03:09] all that. And every day, I mean, I'm
[00:03:11] running Whoop um on on my wrist
[00:03:13] essentially, and I will up upload the
[00:03:15] the screenshot of my stats and then I'm
[00:03:17] just basically explaining to both AIS.
[00:03:20] And something I've learned really is I
[00:03:22] think Claude is super like business
[00:03:24] focused. So, every time I was mentioning
[00:03:26] like I'm basically sick is like please
[00:03:28] go back and kind of rest up and then we
[00:03:32] need to get work done because these and
[00:03:33] these and these and these are the
[00:03:34] deadlines that are coming.
[00:03:36] >> Wow. And on on ChachiBT, it's it's like
[00:03:39] fully fully agnostic to anything outside
[00:03:41] of my personal well-being. So I think
[00:03:44] truly if I had to like pick one of the
[00:03:46] two as my companion/verirtual
[00:03:49] doctor, I would certainly choose Chach
[00:03:51] GPT. I've run this experiment now more
[00:03:53] than once and clothed only for work,
[00:03:56] right? So I think even that experience
[00:03:58] made me kind of realize that I think
[00:03:59] ChachiT is truly embedded as like a
[00:04:02] personal coach, psychologist
[00:04:05] agent even as opposed to clo is really
[00:04:07] truly about work. I had to mention clo
[00:04:10] multiple times. Please don't bring up
[00:04:11] these conversations I'm going to have on
[00:04:13] Friday.
[00:04:15] I'm just not I don't want to talk about
[00:04:17] it. Just focus on maybe whatever I
[00:04:19] should be getting in terms of
[00:04:20] overthe-counter medicines. That was a
[00:04:22] truly unique experience once again
[00:04:24] comparing open AI versus enthropics I
[00:04:27] guess harness and maybe let's use that
[00:04:29] segue a bit of a as a first talking
[00:04:31] point. So what what's the update maybe
[00:04:33] on the latest from your perspective
[00:04:35] Shuah on engineering grade harnesses
[00:04:37] maybe just for the audience quickly what
[00:04:39] is a harness if you can redefine it end
[00:04:41] of May 2026 how has it more or less
[00:04:43] evolved and what's the latest and best
[00:04:45] practices from your perspective.
[00:04:48] So around a year ago um we were advising
[00:04:50] people to not build with multi- aent
[00:04:53] systems because we've heard about them
[00:04:56] and there's certain headed use cases but
[00:04:58] they were just complex to build with. So
[00:05:01] if you're building something from
[00:05:02] scratch from the code up like you're
[00:05:04] you're using probably some coding
[00:05:06] framework but if you're actually writing
[00:05:07] the code for the multi- aent system it's
[00:05:10] complicated. You have to handle contexts
[00:05:11] and handoffs and how those things are
[00:05:14] just implemented uh codewise. By now we
[00:05:17] have agents that are ready to deploy
[00:05:19] like cloud but also like open code like
[00:05:21] Hermes uh like the pi coding agent.
[00:05:24] There's a lot of open source projects
[00:05:26] lots of clos source projects and that
[00:05:28] means you can set up agents as simply as
[00:05:31] having a a single file probably even
[00:05:33] like in some guey opening a window
[00:05:36] clicking some buttons and you have an
[00:05:37] agent which means we're going back to
[00:05:39] multi- aents. I think it's a cycle like
[00:05:41] fashion cycles last around seven years
[00:05:43] or decade and AI is even faster so it
[00:05:46] lasts it lasts about a year or less. The
[00:05:49] idea is
[00:05:51] um
[00:05:53] LM's got expensive uh opus is incredibly
[00:05:56] expensive. GP55 is equally uh expensive
[00:05:59] especially if you're using reasoning. If
[00:06:01] you want the best results, you usually
[00:06:02] toggle toggle on reasoning and you set
[00:06:04] up too high or very high. And you see
[00:06:06] the output tokens, half of them, you
[00:06:08] might even think they don't make sense
[00:06:10] or they're not really efficient.
[00:06:11] Sometimes the model just goes off and
[00:06:13] saying, "hm, I should check this, but
[00:06:15] maybe the user doesn't want me to check
[00:06:16] it." And there's like three or four
[00:06:18] sentences of the model deciding whether
[00:06:20] to check it or not. It could have done
[00:06:22] it in two sentences. Just check it, you
[00:06:23] get the response, it just proceed. But
[00:06:27] so LM are expensive and they take a long
[00:06:29] time to run and thus switching this to a
[00:06:32] cheaper model or to a faster model will
[00:06:34] yield you worse results. So you no one's
[00:06:36] wants to to give up like the results
[00:06:37] that they already have performance that
[00:06:39] they already have. So a good balance is
[00:06:42] having one smart agent. Usually they
[00:06:44] call it the orchestrator like the
[00:06:45] supervisor. It's the one you talk to.
[00:06:47] You ask for things. uh and that agent
[00:06:50] usually has three, four, five different
[00:06:53] agents, smaller things, smaller models
[00:06:55] and usually cheaper and faster that they
[00:06:57] can do things for it. For example, you
[00:06:59] have an orchestrator and you say, "Hey,
[00:07:01] I'm looking to buy a car. Uh please
[00:07:03] recommend me stuff." And the
[00:07:04] orchestrator instead of going online and
[00:07:06] spending tokens and time to parse the
[00:07:08] web and looking for recommendations,
[00:07:10] it'll assign like different tasks for
[00:07:13] different agents like a researcher
[00:07:14] agent, a librarian agent, some agent to
[00:07:17] check uh your personal even documents
[00:07:19] and memories whether kind of what kind
[00:07:21] of car you usually like and smaller
[00:07:24] agents that go to the web and find what
[00:07:26] cars exist, what the prices are. So do
[00:07:29] do the comparison. all the agents and
[00:07:31] return to the main agent with the found
[00:07:33] information. So the main agent doesn't
[00:07:35] have to bother to search. It asks for
[00:07:37] the results. It gets the results back
[00:07:39] and then it presents you with the best
[00:07:42] comparison possible. That happens and
[00:07:44] that kind of orchestration can be
[00:07:47] helpful in any case. If you're doing a
[00:07:48] feature or if you're coding, if you're
[00:07:50] doing emails and schedule management uh
[00:07:53] corporate wise, this orchestration is
[00:07:55] probably the best bang for your buck. So
[00:07:58] you spend a bit of money on GPT55 or
[00:08:00] claude because you never get to use it
[00:08:03] as for everything. You'll save a lot of
[00:08:05] tokens and so you can probably use a
[00:08:07] smaller subscription then you can spend
[00:08:09] 5 10 15 bucks on open source models
[00:08:12] which are much much cheaper much much
[00:08:14] faster usually uh and they'll just do
[00:08:16] the heavy work um the that needs to be
[00:08:20] done to do mo most of queries that I've
[00:08:22] come up with. Uh however try different
[00:08:26] things. I was stuck on copilot for
[00:08:29] around a year almost a year and a half
[00:08:31] because it was cheap enough uh and it
[00:08:33] was good enough for me not to bother
[00:08:35] searching for other things. Copilot
[00:08:37] broke that rule by being turning itself
[00:08:40] into incredibly expensive product and so
[00:08:43] that converted me into like okay let's
[00:08:45] try a few different things and there is
[00:08:47] a whole world out there besides clot
[00:08:49] besides JPT of models and software that
[00:08:52] you can install for free try for free
[00:08:54] only pay what you like and only pay if
[00:08:57] you like the results that you're getting
[00:08:58] so try different configurations and even
[00:09:01] when setting up these projects you might
[00:09:03] think it's super complicated and it'll
[00:09:04] take you months to get like fine-tuned
[00:09:07] to your use case. I've seen like entire
[00:09:09] plugins and entire like additions to to
[00:09:12] the software where the install guide has
[00:09:15] a manual section but before that has hey
[00:09:18] just tell your AI this and it's a single
[00:09:21] sentence that you put on your current
[00:09:23] agent and the agent itself will
[00:09:25] configure and install things on the
[00:09:27] environment. So you don't have to if
[00:09:29] you're running open code for example or
[00:09:31] Hermes agent you can just say to the
[00:09:32] Hermes agent hey I want this plug-in
[00:09:35] please configure it and the Hermes agent
[00:09:37] will add its own plug-in to its own
[00:09:39] environment so it's a pretty cool thing
[00:09:41] it's easier than people think so try and
[00:09:44] experiment
[00:09:45] >> give give it a try no thank you for the
[00:09:47] for the update I think it's one of the
[00:09:48] probably fastest evolving fields
[00:09:51] currently in in achanting artificial
[00:09:52] intelligence just to wrap it in maybe my
[00:09:55] own words as as a summary quickly um
[00:09:57] It's essentially what you're wrapping um
[00:10:00] an L an LLM by right. So it's not like
[00:10:02] that you're actually like in the old
[00:10:04] days you're fine-tuning a domain
[00:10:05] specific large language mode. You're
[00:10:07] actually equipping it with some some
[00:10:08] sort of an execution possible layer that
[00:10:11] you can then just run any particular
[00:10:13] task. It's truly the magic that
[00:10:14] currently is is giving initially also
[00:10:17] cloud the capability to run code to then
[00:10:20] generate powerpoints to generate word
[00:10:22] documents to generate excels to
[00:10:24] ultimately execute on tools know when to
[00:10:26] call via MCP and or to do any other
[00:10:29] useful things that you intend to do as
[00:10:31] an agentic AI system. Also one
[00:10:33] particularly key part is logging um that
[00:10:36] you have some sort of of a track what is
[00:10:38] actually going on and including that is
[00:10:40] also debugging. I think what
[00:10:42] particularly caught my eye just this
[00:10:43] week as uh as I was scrolling through
[00:10:46] the latest um startups that were
[00:10:50] accepted into Y Combinator is this
[00:10:51] startup here called Kodak. Ultimately um
[00:10:54] it's it's a solution that is essentially
[00:10:56] compressing system logs for for agents.
[00:10:59] I think that's probably a handy tool if
[00:11:01] you're if you're technical founder and
[00:11:03] or you're a person that's it's heavy on
[00:11:05] on the debugging. um basically your
[00:11:08] agents needs to debug any particular
[00:11:10] outcome. I think that's a handy a handy
[00:11:13] maybe potential solution and or if it's
[00:11:15] not the solution that's fully working
[00:11:16] for you, you can be essentially building
[00:11:18] something on on that line. So once again
[00:11:20] codec I'll put it here on the screen. Um
[00:11:23] ultimately again the goal is always to
[00:11:25] make the the best price for um compute
[00:11:29] outcome um as as possible right as an AI
[00:11:32] builder that's really the bottom line
[00:11:33] you need to optimize if you just give it
[00:11:35] um any particular log you will of course
[00:11:38] burn context and in that sense you'll
[00:11:40] also burn tokens and money as well. So
[00:11:43] that's eating into your mark margins if
[00:11:45] you have a bad setup how you actually
[00:11:48] are working with with uh log files and
[00:11:50] they might actually be becoming truly
[00:11:52] large. So in the example the startup is
[00:11:54] giving is like 20 6.6 million tokens
[00:11:57] which is probably around 1.2 million
[00:11:59] lines of code. Um that's just the raw
[00:12:02] logs right that the agent needs to maybe
[00:12:05] go through skim through to look for what
[00:12:07] is actually working through what they're
[00:12:09] actually calling a compression capsule.
[00:12:10] They're compressing it 8,000 times to
[00:12:13] 3.3k tokens. And that's really the magic
[00:12:16] then for the LLM to then only crawl back
[00:12:18] to the
[00:12:21] complete domain and look for what
[00:12:22] actually is is there to debug
[00:12:24] accordingly. So that's a bit just a
[00:12:26] rundown on maybe harness engineering
[00:12:28] once again the magic that is is actually
[00:12:30] empowering large language models or a
[00:12:32] multitude of them to to do useful things
[00:12:34] and there's still a lot of I would say
[00:12:36] design surface to be solved for for
[00:12:38] example system log compression for AI
[00:12:41] agents very brief um side note before we
[00:12:44] go into maybe some of the latest model
[00:12:46] releases maybe I'll put that on the
[00:12:48] screen here as well there is not only
[00:12:50] this typical way of harness engineering
[00:12:52] there is also maybe a graph-based
[00:12:54] approach
[00:12:55] Once again the paper is called the lo is
[00:12:58] the agent. There is also different types
[00:13:00] and different techniques that is not
[00:13:02] only the typical harness maybe it's it's
[00:13:03] more coming from a graph-based uh
[00:13:06] approach. So there is still a fastly
[00:13:08] evolving field. So if you're interested
[00:13:10] again I will also put the paper into
[00:13:12] description for you to check out without
[00:13:13] going too much uh into detail. So that's
[00:13:16] probably not the approach most of the
[00:13:18] hair builders are actually taking. It's
[00:13:19] more what you mentioned Chu but that's a
[00:13:21] little bit of a I would say a research
[00:13:22] field that is uh evolving ultimately. Um
[00:13:26] if we give a bit of a pulse before we
[00:13:27] talk about Google Gemini 3.5 flash where
[00:13:30] we're standing in terms of AI building.
[00:13:33] I think ultimately we've mentioned that
[00:13:35] multiple times here on the show. You can
[00:13:36] either be building a software that is
[00:13:38] accelerating the revenue of your target
[00:13:41] customer or your enterprise that you're
[00:13:42] selling it to. that's anything um that
[00:13:45] maybe we can quickly brainstorm a few
[00:13:47] use cases for and or you can actually be
[00:13:49] helping them to cut costs and ultimately
[00:13:52] costs are only ultimately cuted when FTE
[00:13:55] or or humans are let go and that's I
[00:13:57] think something that a lot of the
[00:13:58] companies are still trying to experiment
[00:14:00] which of these software are we actually
[00:14:02] buying something we've learned and just
[00:14:04] to holistically bring out the point
[00:14:06] before we go back to you is even if we
[00:14:08] cut cost for human FTEES um the pricing
[00:14:11] is actually increasing and increasing
[00:14:13] inreasing and increasing and increasing
[00:14:15] in terms of AI compute. So ultimately
[00:14:17] the cutting cost case I think as it gets
[00:14:20] a little bit of a damper and the revenue
[00:14:22] accelerating case for AI builders might
[00:14:24] be the more appealing. But what's the
[00:14:26] latest if you had to choose one or the
[00:14:28] two which is an easier cell which is an
[00:14:30] easier build for AI builders. Uh, I
[00:14:32] think you usually have your own pain
[00:14:34] points in your workflow dayto-day. And
[00:14:36] as a builder, as some someone who knows
[00:14:38] how to create these agents, you're going
[00:14:40] to want to uh just erase those pain
[00:14:43] points away. Automate that boring work
[00:14:46] that you want to do. Even the the fun
[00:14:47] work that you don't want to do. If you
[00:14:49] don't want to do it, you can just put an
[00:14:50] agent on top of it. However, it is true
[00:14:53] that usually you just create an agent
[00:14:55] and you'd imagine that work to be done
[00:14:58] automatically almost for free. Like you
[00:15:00] had an initial effort to create the
[00:15:01] agent, but now it's running and it's
[00:15:03] saving you a lot of time, a lot of
[00:15:04] money, a lot of uh just open space on
[00:15:08] your mind to focus on different things.
[00:15:11] It is no longer the case and is longer
[00:15:12] the case especially on a corporate
[00:15:14] level, especially at scale because if
[00:15:16] you're an individual builder, then you
[00:15:19] have your own codec subscription, your
[00:15:21] own class subscription, and you use that
[00:15:23] and you're making sure to pay attention
[00:15:25] to the 5-hour limits, the weekly limits,
[00:15:27] the monthly limits. um to make sure that
[00:15:30] you stay uh on top of those and you you
[00:15:33] don't get cut off mid uh flow at scale.
[00:15:36] This means that developers uh are
[00:15:40] costing the company now almost their
[00:15:43] entire salary in API costs. Sometimes a
[00:15:46] fraction like half the salary is in API
[00:15:48] costs and it became expensive again to
[00:15:51] have developers and became expensive to
[00:15:53] have AI. I think we're coming to like
[00:15:56] one of those kinds of plateaus uh where
[00:15:59] people are saying yes we still going to
[00:16:00] automate things uh and it can be done
[00:16:02] and it shall be done but it has to be
[00:16:05] done in kind of a smarter way that is
[00:16:07] throwing opus or what is the latest
[00:16:09] biggest frontier model at the problem
[00:16:12] because the latest frontier model will
[00:16:13] probably have the intelligence to fix or
[00:16:15] do whatever you want it that is you want
[00:16:17] to automate but it also cost you
[00:16:19] probably as much as you would as you
[00:16:21] having an intern or someone middle level
[00:16:23] doing And those costs seem to be rising.
[00:16:26] And it's not just inference, it's also
[00:16:28] maintaining those projects. There's
[00:16:30] always when you're having a company,
[00:16:33] there's always this different ways of
[00:16:35] you. If you want software, three ways of
[00:16:36] getting it. One is getting a SAS. So you
[00:16:40] choose one that you want to use. You get
[00:16:42] a subscription for it. You make some
[00:16:44] deal and you get that. So it's
[00:16:46] externally provided. The other one is
[00:16:48] you having having it custom ordered. So
[00:16:50] you write some kind of I think they call
[00:16:52] it RFP or some kind of request for that
[00:16:56] software request for a provider and
[00:16:58] different companies will reply to it.
[00:17:00] They'll try to build a software for you.
[00:17:02] Uh and in 6 months to a year you have a
[00:17:04] software you want or you just try to
[00:17:06] build it inhouse. Usually in that order
[00:17:09] it's the cheapest to the most expensive.
[00:17:11] So if it's built already the
[00:17:13] subscription for it or the license for
[00:17:14] it will be the cheapest option and
[00:17:16] building it inhouse is usually the most
[00:17:18] expensive. As a software engineer, I
[00:17:20] always prefer building it in-house
[00:17:22] because I'm the one building it. But I
[00:17:24] realized it is expensive, especially
[00:17:26] because it's not just a single engineer.
[00:17:27] It's a whole engineering team plus some
[00:17:29] project managers and UX developers and
[00:17:31] QA testers and all the management uh
[00:17:35] meetings and board meetings that take to
[00:17:38] decide what the project actually does,
[00:17:39] who's going to pay for it, who's going
[00:17:41] to maintain it. It takes a lot of time
[00:17:43] and effort and at the end money for a
[00:17:46] company to build inhouse. AI made
[00:17:48] building cheaper and I was talking to to
[00:17:51] serial before this episode. It made
[00:17:53] build cheaper for smaller companies and
[00:17:56] for individual people because it means
[00:17:58] one person can build more. But all this
[00:18:00] overhead that corporate has of having
[00:18:02] PMs and QA testers and UX and board
[00:18:05] meetings to decide what the project
[00:18:07] actually does, they're still happening.
[00:18:09] So there that overhead is still is still
[00:18:12] there, still exists, still costing a
[00:18:14] whole lot of money to build that
[00:18:15] software. Uh, and so I think we're come
[00:18:19] coming to kind of a normalization where
[00:18:22] smaller companies can build incredibly
[00:18:24] fast and big corporate companies are
[00:18:27] struggling to actually take advantage of
[00:18:28] this AI. They're paying through the roof
[00:18:30] for API costs, but they're not getting
[00:18:32] the speed or the efficiency that
[00:18:35] startups uh are able to handle. Uh,
[00:18:38] that's why Enthropic is launching a new
[00:18:40] product every two weeks and big
[00:18:41] corporate is doing the same product for
[00:18:43] six months and is still halfway through
[00:18:45] their road map. Yeah, I mean that's my
[00:18:47] experience.
[00:18:47] >> I think it's a definitely a good
[00:18:49] synthesis um that I do have some sort of
[00:18:51] a holistic feedback. But maybe just
[00:18:53] before that if you're building uh a ch
[00:18:55] agents or multi- aent systems for
[00:18:58] revenue acceleration maybe some ideas
[00:19:00] that come to mind is of course anything
[00:19:02] in terms of sales outreach go to market
[00:19:04] engineering GTME that's one of the few
[00:19:07] new roles that I think AI brought into
[00:19:09] place especially with a company called
[00:19:11] Clay that was I I think um kind of
[00:19:13] pioneering this role. It's ultimately
[00:19:15] using a aentic AI augmented signals that
[00:19:18] you know who you actually need to sell
[00:19:20] your software to. Of course, you
[00:19:21] mentioned also um RFPs. You mentioned
[00:19:25] indirectly any upselling activity. So if
[00:19:27] you have agents that are somewhat able
[00:19:29] to help enterprises sell more of what
[00:19:31] they're actually already doing, I think
[00:19:33] that's a unique approach uh especially
[00:19:36] in the time where aentic AI cost or AI
[00:19:39] agent cost is really skyrocketing and
[00:19:41] people do not yet know should we
[00:19:42] actually now implement something that
[00:19:44] saves us money X in May 2026 and then
[00:19:48] ultimately it's maybe X minus 80% in
[00:19:50] December 2026 when the actual true AI
[00:19:53] cost is landing the market. So maybe for
[00:19:55] the time being it might actually be a
[00:19:57] smarter move to focus on systems that
[00:19:59] are first accelerating revenue and or
[00:20:02] helping on revenue capture and then once
[00:20:05] this kind of AI pricing alignment is
[00:20:07] actually being executed maybe focus back
[00:20:09] again on AI to help cut cost. Ultimately
[00:20:14] something I'm con consistently mention
[00:20:16] here on the podcast as well is like
[00:20:18] human work the way it is done and as you
[00:20:20] mentioned now with all the hierarchical
[00:20:22] layers it seems to be anyway completely
[00:20:24] misaligned management in most cases is
[00:20:27] is not work it's truly just humans
[00:20:29] syncing other humans and they do that by
[00:20:32] handoffing work artifacts and pre- AI
[00:20:36] these work artifacts excels powerpoints
[00:20:38] word documents they were handcrafted by
[00:20:40] humans now they're handcrafted by AI I
[00:20:43] most of the time or 75 80% of that 20%
[00:20:47] human fine-tuned but they're still
[00:20:48] handed off to other humans and then
[00:20:50] these new humans in the hierarchical
[00:20:52] order of a firm andor to your external
[00:20:54] provider they're being synced they're
[00:20:56] being received they're being analyzed
[00:20:58] augmented and then hand off to their
[00:21:00] management. And so if you look at this
[00:21:01] from an entire chain end to end let's
[00:21:03] say for example hypothetically a sale of
[00:21:05] a software you as a software dev me as a
[00:21:08] salesperson as just as an example you
[00:21:10] prepare some stuff with me I have to
[00:21:12] augment it with PowerPoint I have to
[00:21:13] send it to my client my client reviews
[00:21:16] it sends it to the procurement
[00:21:17] department send it to the compliance
[00:21:19] team sends it maybe to his team manager
[00:21:21] and or whoever has the line item to
[00:21:23] cross of this contract then some weeks
[00:21:26] go by humans are being synced on the
[00:21:28] right side then it's a sync in the
[00:21:30] middle the humans are being synced on
[00:21:32] the left side because once we actually
[00:21:34] sold the software us as deliveries we
[00:21:36] need to sync internally once again when
[00:21:39] do we deliver how do we staff this what
[00:21:41] are the APIs the interconnects we need
[00:21:43] to build are there some MCPS we have
[00:21:45] more alignments more sync work being
[00:21:48] done and ultimately we're starting the
[00:21:49] wheel again we're confirming to our
[00:21:52] clients they need to receive that I can
[00:21:54] go on and on and on you get the point
[00:21:56] it's just highly ineffective once again
[00:21:58] management is not perk. It's just human
[00:22:01] syncing humans and all these humans in
[00:22:03] this chain in the entire world in 2026
[00:22:06] are essentially handoffing M365
[00:22:09] artifacts and code that probably has to
[00:22:12] be reshaped. This entire value creation
[00:22:14] of the world has to be reshaped with
[00:22:16] eight aantic interfaces, aantic
[00:22:18] checkouts, aantic payments with human in
[00:22:20] the loop as an interface. But just if I
[00:22:23] reason through that, it kind of doesn't
[00:22:24] make sense how we move in the world and
[00:22:27] generate value and all these trillions
[00:22:28] and trillions of dollars of GDP. But
[00:22:30] that's more or less that what happened
[00:22:32] with Google Gemini 3.5 Flash. Where does
[00:22:34] it land before we then wrap the show up
[00:22:37] with Micron a bit of a victory up from
[00:22:40] our end. So a bit of context on Google
[00:22:42] and their lineup of models. They usually
[00:22:44] have a flash model and a pro model. Uh
[00:22:47] that was the case for 2.5, for three,
[00:22:49] for 2.1. And so usually the flash model
[00:22:52] is cheap, it's fast, it does, you know,
[00:22:55] the light work that you need that you
[00:22:57] don't need to think much about it. And
[00:22:59] the Pro model is the one that's the the
[00:23:01] the smarty pants of the two. Uh usually
[00:23:05] takes longer, usually it's more
[00:23:07] expensive, uh and it gets you the best
[00:23:09] results. What we're seeing is Google
[00:23:11] launcher 3.5 flash. The flash model is
[00:23:15] on par or sometimes better than the
[00:23:17] previous pro model. So that's usually a
[00:23:20] very good sign like a green flag that
[00:23:22] models are improving uh quite
[00:23:24] substantially. However, the pricing also
[00:23:26] matches this increase. So the model is
[00:23:29] faster, the model is smarter, but also
[00:23:31] the model is more expensive, which
[00:23:33] raises a couple red flags because if 3.5
[00:23:37] flash is already not expensive
[00:23:39] expensive, but a little bit expensive,
[00:23:41] be a bit pricey, way more than any flash
[00:23:43] model previously was, how expensive is
[00:23:46] 3.5 Pro going to be? And there's two
[00:23:50] possible outcome. There's infinite
[00:23:51] possible outcomes, but there's two the
[00:23:53] most probable outcomes. One is 3.5 Pro
[00:23:57] is just more expensive. It's expensive
[00:23:59] on par with Opus, on par with GPT55,
[00:24:03] even more expensive than those two
[00:24:05] because usually when a Frontier model
[00:24:07] comes out, if it can beat the
[00:24:08] benchmarks, they'll price it
[00:24:10] accordingly. You'll need for for the
[00:24:12] Frontier models for the last year or so,
[00:24:15] it's harder to get a better model for
[00:24:17] cheaper. But there's a better, more
[00:24:19] hopeful version, which is when they'll
[00:24:21] finally launch 3.5 Pro. And they're
[00:24:23] taking a while, and that's fine. I was
[00:24:24] hoping that it would come out on Google
[00:24:26] IO, which was around a week ago. It
[00:24:28] didn't. But when 3.5 Pro comes out, it
[00:24:31] might be the case that 3.5 Pro has
[00:24:34] similar pricing to 3.5 Flash and they'll
[00:24:36] just decrease the pricing for 3.5 Flash.
[00:24:39] So the idea is 7.5 Flash is the most the
[00:24:43] best model available. So also the most
[00:24:45] expensive from Google. And finally, when
[00:24:47] they launch a better one, they'll lower
[00:24:49] the price for Flash for Flash compatible
[00:24:52] pricing. uh which is probably a very
[00:24:55] good thing. Uh people have not been
[00:24:57] using Gemini models in general in
[00:25:00] augentic environments because they're
[00:25:02] harder to work with than most open
[00:25:04] source ones and the the cost to
[00:25:07] intelligence. the ratio isn't that
[00:25:09] appealing compared to let's say OPO or
[00:25:11] GP55 where you get the best possible
[00:25:13] intelligence but also at the premium
[00:25:15] cost or open source models where you get
[00:25:18] really really fast results for
[00:25:21] usually just cents on a dollar compared
[00:25:24] to Frontier models. Uh Gemini is on an
[00:25:27] awkward position there. Let's see how
[00:25:29] 3.5 Pro comes out. uh maybe in be in a
[00:25:31] couple weeks, maybe it will take a few
[00:25:33] months, hopefully not uh to see if the
[00:25:36] pricing changes because if things get
[00:25:39] keep getting more expensive, the AI
[00:25:41] landscape has to be altered and the way
[00:25:44] we build things and what is built will
[00:25:47] have to go to a much more thorough
[00:25:48] process of is this actually going to
[00:25:50] make us money because
[00:25:53] most of them for now are not.
[00:25:55] >> I mean, it's a good I think it's a good
[00:25:56] overview on on this model. I think just
[00:25:58] what mostly surprised me even in again
[00:26:00] May 2026 which is somewhat of an
[00:26:03] advanced stage of new models being
[00:26:05] released and I think we always got the
[00:26:07] groove a bit what is coming that flash
[00:26:09] ranks so high up on the intelligent
[00:26:11] scales. Yes, 4.7 is out for a few weeks
[00:26:14] now but still the flash model being
[00:26:16] quite intelligent versus yes as you
[00:26:18] mentioned the price is still quite
[00:26:20] significant but it is super fast and I
[00:26:22] believe it might be an interesting
[00:26:24] add-on if you have a multi- aent system.
[00:26:26] Once again, we talked about harnesses,
[00:26:27] of course, you could harness also a
[00:26:29] flash model like that with its
[00:26:31] capabilities. And just to wrap up the
[00:26:33] episode, um, just to give a bit of a
[00:26:35] market update. Um, before we do that,
[00:26:38] let me quickly also play the clip where
[00:26:40] we are mentioning Micron. Here it goes.
[00:26:44] A few months ago, we mentioned that
[00:26:48] ultimately Micron might be aside from SK
[00:26:51] Hinx and Sundisk on the verge of an
[00:26:53] explosion. I think the stock price back
[00:26:55] then at least that that's my purchasing
[00:26:57] price was $80 and today it reached 10x
[00:27:00] that ultimately mostly because and once
[00:27:03] again a surprise in the stock market I
[00:27:05] still getting surprised in the AI game
[00:27:07] is because UBS the Swiss bank um my
[00:27:10] house bank ultimately they raised the
[00:27:13] price target of Micron TBD if that's
[00:27:17] even realistic to 1.6K
[00:27:19] which would again be a 100% gain of
[00:27:22] today. Um so Micron reaches one trillion
[00:27:25] market cap. That is a severe increase of
[00:27:28] course in capability in terms of their
[00:27:32] um let's say reasoning um memory
[00:27:35] capability but at the same time it seems
[00:27:36] to be quite high still for the world. It
[00:27:39] jumped significantly today on the stock
[00:27:41] exchange single day I think it's 15 or
[00:27:44] 70% at a time for a stock that has
[00:27:46] already been valued at somewhat like 800
[00:27:49] billion is quite substantial. It just
[00:27:51] underlines again this memory and or ARAS
[00:27:55] is still on. It's probably getting a bit
[00:27:57] on the heated side of things. And one
[00:27:59] stock I'm still desperately waiting to
[00:28:00] pop off of course is Micro and Soft.
[00:28:04] They're doing both.
[00:28:06] And nothing aside from being micro and
[00:28:08] soft in terms of their return, which I
[00:28:11] do believe might have to do something
[00:28:13] with OpenAI's IPO. So once this is also
[00:28:15] maybe fresh out in the water, let's see
[00:28:18] what is happening to Microsoft. But
[00:28:20] that's a bit of of an update from the
[00:28:21] financial corner. A quick victory lap on
[00:28:23] our side. Micron and again the next
[00:28:26] frontier might be space. The next
[00:28:28] frontier might be co-ackaged optics.
[00:28:30] Something we've been mentioning since
[00:28:32] probably November 2025 as well. Anything
[00:28:35] else from your side before we wrap up
[00:28:37] the episode? Yes, you told me I have
[00:28:39] paper hands because I have been selling
[00:28:40] Micron.
[00:28:42] But other than this, any any last
[00:28:45] thoughts? Um around that time that we
[00:28:48] said that Micron was going to explode, I
[00:28:50] also mentioned uh energy providers as
[00:28:54] potential uh good purchases and
[00:28:56] potential investments in general because
[00:28:58] data centers and memory and GPUs all
[00:29:01] require power. I held I think a hopeful
[00:29:05] view that renewables and nuclear and
[00:29:07] like this high techch forms of energy
[00:29:10] was going to be used for data centers
[00:29:12] and I still think they might be in the
[00:29:14] future. However, the landscape is a bit
[00:29:16] different. AI landscape is rush. It's
[00:29:19] rushed from end to end. Everything is to
[00:29:21] be done yesterday. Um, data centers need
[00:29:24] to be done yesterday. Everyone needs
[00:29:25] them right now and they want to build
[00:29:28] them as fast as possible. And so, no one
[00:29:30] wants to pay the high upfront cost that
[00:29:31] is to build a renewables power plant.
[00:29:34] Uh, or they are less motivated to do so
[00:29:37] because they're already spending a whole
[00:29:38] bunch on the GPUs and infrastructure for
[00:29:40] data center itself. What they want is
[00:29:42] power. They don't care much on how that
[00:29:45] power comes from or where that comes
[00:29:46] from or what form does it take. And
[00:29:49] that's why we're seeing data centers
[00:29:50] being built with just gas generators uh
[00:29:53] right next to it because as long as it
[00:29:55] has power, people building data centers
[00:29:57] don't care. The name of the game is
[00:30:00] rush. And so name of the game is not
[00:30:02] let's build the coolest most high-tech
[00:30:05] looking renewable power plants with
[00:30:07] solar panels. Even though they are
[00:30:09] expensive, even they're have a good
[00:30:12] value proposition, but they they are
[00:30:14] expensive upfront. Renewables have all
[00:30:17] their cost mostly up front, while all
[00:30:20] the other funds of energy, coal, gas,
[00:30:22] oil, whatever, you can build a cheaper
[00:30:24] plant and you can pay that cost in the
[00:30:27] actual gas in the actual oil you're
[00:30:28] putting into it. And so it makes for
[00:30:30] better preposition for data centers. Not
[00:30:32] the dreamy outcome that I had a year
[00:30:35] ago. I still hold the belief that we're
[00:30:38] going to build renewables and we are
[00:30:39] building renewables uh worldwide but
[00:30:42] it'll take a while and it'll take a bit
[00:30:45] of effort and energy and a lot of
[00:30:47] political power and political will to to
[00:30:49] make it happen because name of the game
[00:30:52] is creating power as fast as possible
[00:30:53] not the cleanest
[00:30:55] >> but I think even to wrap up the episode
[00:30:57] on on this edge maybe I think it is
[00:30:59] still much faster to set up solar um
[00:31:02] let's say panels as opposed to um
[00:31:05] turbines that you need for gas power
[00:31:06] plants because they're taking years and
[00:31:08] years and years in the making. You also
[00:31:10] need to get all the the paperwork done,
[00:31:12] especially if it's built in the US, let
[00:31:13] alone be in Europe. And again, solar
[00:31:16] panels are still more or less fast to
[00:31:18] buy from from China, then set up quite
[00:31:20] swiftly. That's also maybe potentially
[00:31:22] why Elon Musk is moving to space, but
[00:31:24] TBD TBD on this. So, thank thanks again
[00:31:27] for joining. As always, to the audience,
[00:31:29] we're shooting these episodes. We're
[00:31:31] trying every single week to give an
[00:31:32] update. Um, and next week's episode, we
[00:31:36] are already approaching the mid-50s.
[00:31:38] We're running this show for 52 episodes
[00:31:41] as today, but you can definitely expect
[00:31:42] more from us in terms of AI harnesses,
[00:31:45] agentic AI building, even some business
[00:31:47] insights and financial insights, which
[00:31:49] is a great advantage if you're building
[00:31:51] an AI. You also see what is actually
[00:31:53] happening on the ground, where the
[00:31:54] constraints, and how you can allocate
[00:31:56] even the money you make as an AI builder
[00:31:58] to your stock portfolio. So, that being
[00:32:00] said, thank you SH for joining. See you
[00:32:01] in the next one. Bye-bye. See you next
[00:32:03] one.
