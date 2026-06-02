---
video_id: KWsuo5mHx1E
title: Every AI Builder Will Regret Ignoring This
channel: Build In Public
url: "https://www.youtube.com/watch?v=KWsuo5mHx1E"
watched_date: 2026-05-30
watched_at: "2026-05-30T12:00:00Z"
watch_count: 1
duration_seconds: 1054
source: youtube-history-browser
history_label: Saturday
history_order: 56
watched_at_precision: date-from-history-label
watched_percent: 24
estimated_watched_seconds: 253
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Anthropic's acquisition of Stainless—a company that auto-generates SDKs, CLIs, and MCP (Model Context Protocol) servers from API specifications—signals a fundamental shift in AI competition from model intelligence to agent infrastructure. Stainless has powered every official Anthropic SDK since inception, and hundreds of companies depend on it for SDK and tool generation. The core insight Anthropic emphasizes: agents are only as capable as the systems they can reach, not the raw intelligence of the model. By acquiring Stainless and tightening control over how Claude connects to external systems, Anthropic is betting that the AI agent race will be won by whoever controls the most seamless bridge between agents and real business tools—databases, CRMs, payment processors, calendars, and repositories. This represents the transition from competing on benchmarks to competing on distribution and tool access.

Builders should immediately start thinking of APIs as agent services, not just developer tools, with clean documentation, stable authentication, and MCP server support. Learn how MCP works and design your products so agents can safely read what they need, write only what's permitted, request approval for risky actions, and leave audit trails. The money isn't in generic AI or prompts—it's in automating specific, repetitive business workflows like invoice reconciliation, listing creation, or lead follow-ups. Pick one boring business process that touches multiple tools, map its APIs, build a minimal agent to automate it with supervision and proper permissions, and sell that workflow. The winners will be builders who master safe, reliable integrations between agents and real business systems, not those chasing model benchmarks.

## Transcript

[00:00:00] So, Anthropic just bought the plumbing
[00:00:03] that makes AI agents useful. And in this
[00:00:06] video, I'm going to break down exactly
[00:00:08] what stainless is and what it means for
[00:00:11] builders and AI agents going forward.
[00:00:13] So, this is the plumbing, the
[00:00:15] infrastructure, the architecture that
[00:00:17] makes AI agents go. And I think this is
[00:00:20] one of those stories that looks really
[00:00:22] boring for a few seconds and then you
[00:00:24] realize it explains where this whole AI
[00:00:27] agent race is going and ending up. So in
[00:00:30] this video I'm going to be talking about
[00:00:32] what Anthropic did and how they acquired
[00:00:35] Stainless and why SDKs and MCP servers
[00:00:38] matter way more than people think and
[00:00:40] what builders should do with this
[00:00:42] information. So, the official Anthropic
[00:00:45] announcement from May 18th, just last
[00:00:48] week, and Anthropic says it's acquiring
[00:00:50] Stainless. It's basically a company that
[00:00:53] generates SDKs, CLIs, and MCP servers
[00:00:56] from API specs. Anthropic says Stainless
[00:01:00] has, you know, powered every official
[00:01:02] Anthropic SDK since the earliest days of
[00:01:05] the Anthropic API. And I'm talking every
[00:01:09] single anthropic SDK. You know, it says
[00:01:12] here, the frontier of AI is shifting
[00:01:14] from models that answer to agents that
[00:01:16] act. And agents are only as capable as
[00:01:20] the systems they can reach. So last
[00:01:23] week, they acquired Stainless. It was
[00:01:25] founded in 2022, and Stainless has
[00:01:28] literally powered the generation of
[00:01:30] every single official anthropic SDK
[00:01:32] since the early days, which is pretty
[00:01:34] impressive. So we're talking TypeScript,
[00:01:36] Python, Go, Java, more languages. the
[00:01:39] libraries developers import when they
[00:01:41] want to connect their apps to Claude and
[00:01:44] command line tools. That's pretty
[00:01:46] simple, right? The connectors and the
[00:01:48] stuff that actually turns an API from a
[00:01:50] web page into something a real builder
[00:01:53] can actually use inside of a product. I
[00:01:55] love that. And the part that most people
[00:01:58] are going to miss, but pay attention
[00:01:59] here, is anthropic did not say agents
[00:02:02] are only as smart as the model. They
[00:02:04] said agents are only as capable as the
[00:02:07] systems they can reach. So, you need to
[00:02:09] check that out. I have the source link
[00:02:10] down below. Just overview it. There's a
[00:02:13] huge shift going on because for the last
[00:02:15] year, most people have basically been
[00:02:18] arguing about model benchmarks. I mean,
[00:02:20] benchmarks are great, but have you ever
[00:02:22] seen a benchmark of a new LLM come out?
[00:02:24] You go and download the LLM or you
[00:02:26] import it into your IDE and then it just
[00:02:28] sucks. It sucks at code review. It sucks
[00:02:30] at refactoring your codebase. It sucks
[00:02:32] at tool calling. and you're like, "This
[00:02:34] scored a 97 on Sweetbench. What is going
[00:02:37] on?" That's why benchmarks are amazing
[00:02:40] until you actually use it. We need
[00:02:42] realworld production use for these
[00:02:44] models. And everyone's been arguing
[00:02:46] about benchmarks. They get the clicks.
[00:02:47] But that's not the real point here for
[00:02:49] builders. It's always been Claude versus
[00:02:51] GPT or Codeex versus Cloud Code. And
[00:02:54] lately, it's been Hermes versus
[00:02:55] OpenClaw. It's like, who cares? People
[00:02:57] have even been saying local models are
[00:02:59] taking over. It really doesn't matter.
[00:03:01] It depends on what you're building,
[00:03:03] right? And yes, the model matters here,
[00:03:05] but just not as much as it people think,
[00:03:08] right? If an agent cannot reach your
[00:03:11] calendar or your database or your CRM or
[00:03:14] your payment processor, more
[00:03:16] importantly, your repo, you know, it is
[00:03:18] still basically just a smart intern
[00:03:20] trapped in a glass box. And that's why
[00:03:22] stainless acquisition matters here.
[00:03:24] Anthropic says stainless turns an API
[00:03:27] spec into SDKs across all languages,
[00:03:30] TypeScript, Python, Go, Java, and more.
[00:03:33] And it also says hundreds of companies
[00:03:36] rely on Stainless to SDKs, CLIs, and MCP
[00:03:40] servers. So that means Stainless is not
[00:03:42] just developer convenience. It's
[00:03:44] distribution for builders and its
[00:03:46] adoption. It is the bridge between a
[00:03:48] company saying we have an API and a
[00:03:51] builder actually shipping something with
[00:03:53] an API. So Antropic owns that bridge now
[00:03:56] and TechCrunch reported a sharper
[00:03:58] version of the story. So basically
[00:03:59] TechCrunch came out and said stainless
[00:04:01] was used by OpenAI, Google, Cloudflare
[00:04:04] and then Anthropic told TechCrunch it
[00:04:07] will wind down all hosted stainless
[00:04:09] products including the SDK generator. So
[00:04:12] this is not just about Anthropic buying
[00:04:14] a helpful internal tool. This is
[00:04:16] Anthropic pulling agent infrastructure
[00:04:18] closer within Claude. And that's why I
[00:04:20] wanted to talk about this story because
[00:04:21] it's relevant to us builders. And if
[00:04:24] you're building with AI agents, you
[00:04:25] really need to pay attention to this
[00:04:26] because the next wave is not the one
[00:04:29] chatbot. It's agents that can actually
[00:04:32] safely run real systems. So Enthropic
[00:04:35] also said it created MCP to make agent
[00:04:38] connectivity more possible. So MCP
[00:04:40] basically stands for model context
[00:04:42] protocol. It is the open protocol for
[00:04:45] anthropic and they've been using it to
[00:04:47] push agents so they can connect tools
[00:04:49] and data sources in a cleaner way.
[00:04:51] That's the real play and a model by
[00:04:53] itself. This is just a brain and MCP is
[00:04:56] kind of like the hands. It's the way it
[00:04:58] works with these tools and skills. SDKs
[00:05:01] give builders an easy way to put those
[00:05:04] hands into real apps. I hope this is
[00:05:06] making sense. CLIs, command line
[00:05:09] interfaces, let operators use those
[00:05:11] hands from a terminal. I know it's a lot
[00:05:14] of jargon, but these are really
[00:05:15] important concepts you need to
[00:05:16] understand if you want to build with AI.
[00:05:19] And if you combine all those together,
[00:05:21] oh my, you get a beautiful piece of the
[00:05:24] puzzle coming together. You get agents
[00:05:27] that do not just chat with you, but they
[00:05:30] actually work and do work autonomously
[00:05:32] for for you agentically, right? and they
[00:05:35] can read records and they can like
[00:05:37] create tickets and update documentation.
[00:05:40] They can call APIs, they move data, they
[00:05:42] can run repeatable workflows and that is
[00:05:44] what people are actually paying for and
[00:05:46] businesses, not just another rapper.
[00:05:48] We're past that point and not just
[00:05:50] another pretty chat UI chatbot. We're
[00:05:53] over that. We want actual work getting
[00:05:55] done reliably. And here's the builder
[00:05:57] angle here. If you're building with AI,
[00:05:59] which I'm sure you are, so if you're
[00:06:01] building with AI or you're building an
[00:06:03] AI tool right now, your moat is probably
[00:06:06] not going to be your prompt. And I know
[00:06:07] people don't want to hear that. I don't
[00:06:09] want to hear that. But prompts are
[00:06:10] getting copied instantly. Very easy to
[00:06:13] go into Cloud Code or Google AI Studio
[00:06:16] or Chad GBT and come up with a really
[00:06:18] good-look prompt. Even workflows are
[00:06:20] getting copied right now and UI patterns
[00:06:22] are getting copied. I mean, every
[00:06:24] vibecoded website looks the same. It's
[00:06:25] annoying. Even model access is getting
[00:06:28] more equal because everybody is routing
[00:06:31] through their same few frontier
[00:06:32] providers. The part that gets harder to
[00:06:35] copy is the integration layer, the exact
[00:06:37] way your agent connects to messy
[00:06:39] business systems, the exact permissions
[00:06:42] model, the exact approval flow and the
[00:06:45] exact logging. So that's why I wanted to
[00:06:47] talk about this. This is a really
[00:06:48] important back-end infrastructure on
[00:06:50] what Anthropic is doing and that is
[00:06:53] where the money is going, right?
[00:06:54] Anthropic is building and buying
[00:06:57] stainless and that's a huge signal here.
[00:07:00] They are not just trying to make cloud
[00:07:02] code smarter or the whole cloud
[00:07:03] ecosystem smarter. They are trying to
[00:07:05] make cloud easier to attach to basically
[00:07:07] the rest of the software world. So if
[00:07:09] you read this line in particular from
[00:07:12] anthropic again they say in this article
[00:07:15] here published on the 18th that agents
[00:07:17] are only as useful as what they can
[00:07:20] connect to. And I 100% believe that that
[00:07:24] should be written above every AI builder
[00:07:26] desk right now. Get it tattooed on your
[00:07:28] forehead. I don't care. This is
[00:07:29] important because most people are still
[00:07:31] building like the model is the product.
[00:07:34] The model is not the product. The
[00:07:35] finished job, the workflow, the agentic
[00:07:38] workflow, the cron job that comes on
[00:07:41] every day on a repeatable task. That is
[00:07:43] the finished product. That's what people
[00:07:44] are buying. If your agent helps a
[00:07:46] reseller list 200 items faster, that is
[00:07:49] the product. I built Easy Flip. It is a
[00:07:52] pro app that I built last year in cloud
[00:07:54] code has generated over $6,000 in
[00:07:56] revenue and I was just solving a small
[00:07:58] problem. How can I help people list
[00:08:00] items on eBay faster with the help of
[00:08:02] AI? That's the product. For another
[00:08:04] example, another app that I made for AI
[00:08:07] agents is a real estate AI photo editor.
[00:08:09] So, if your agent that we've created
[00:08:11] helps real estate agents edit photos and
[00:08:14] publish listings to the MLS faster,
[00:08:16] that's the product. So, if your agent
[00:08:18] helps a small business owner answer
[00:08:21] leads or send follow-ups or update the
[00:08:23] CRM or it can book calls, that's another
[00:08:26] product. The model is just the engine.
[00:08:29] The workflow is the car and the
[00:08:30] integration layer is the road. No road,
[00:08:33] no trip. That's sad. But what should
[00:08:35] builders actually do with this
[00:08:36] information? I mean, come on. I've been
[00:08:38] blabbing everywhere. What should you
[00:08:39] actually do about this? I think the
[00:08:41] first thing you need to do is stop
[00:08:43] thinking of APIs as developer docs only.
[00:08:46] Your API is now an agent service. If an
[00:08:49] human developer can use your API, an
[00:08:52] agent should be able to use it, too. If
[00:08:54] you're building a product and you don't
[00:08:56] give API access, what are you doing?
[00:08:58] Build your product for agents, not for
[00:09:01] humans. That's the next revolution here.
[00:09:03] And that means having clean
[00:09:04] documentation and stable examples,
[00:09:06] simple authentication, and good error
[00:09:08] messages. You need predictable objects,
[00:09:12] small scope permissions, and source for
[00:09:15] the MCP and SDK. And if you're building
[00:09:17] a SAS right now, you need to start
[00:09:19] asking one question to yourself. What
[00:09:21] would it take for an AI agent to use my
[00:09:24] product without human babysitting? H not
[00:09:28] recklessly either, and not with full
[00:09:30] account access, but just safely. I mean,
[00:09:32] Stripe just did that earlier this year.
[00:09:34] I mean, it was like a month ago where
[00:09:35] they actually made money for AI agents,
[00:09:37] right? And that's going to be huge. So
[00:09:39] I'm asking, can your agent read what it
[00:09:41] needs to read? Can it write only what is
[00:09:44] allowed to write? Can it ask for
[00:09:46] approval before anything risky? And can
[00:09:48] it leave an audit trail? Can it recover
[00:09:50] something if it fails? That is where the
[00:09:52] agent economy essentially is and where
[00:09:54] it's going right now. The second thing
[00:09:55] you need to ask yourself is you need to
[00:09:57] learn how MCP works like right now. Not
[00:10:00] because MCP is magic, and it's not, but
[00:10:03] because it is becoming one of the most
[00:10:04] default ways people think about tool
[00:10:06] access for agents. Enthropic says it
[00:10:09] created MCP to make the agent
[00:10:11] connectivity possible. And the stainless
[00:10:13] acquisition is directly tied to SDKs and
[00:10:17] MCP server tooling. So, if you're inside
[00:10:20] the community right now, inside of our
[00:10:22] shipping school community, this is the
[00:10:24] kind of thing I wouldn't ignore. You do
[00:10:26] not need to become some protocol expert.
[00:10:28] But you should understand the basics
[00:10:30] like what is a tool, what is a resource,
[00:10:33] and what does the server expose? And
[00:10:35] what should never be exposed? Those are
[00:10:37] the things you need to know. Like how do
[00:10:40] approvals work? And how do you keep
[00:10:41] secrets out of model contexts? I mean,
[00:10:43] that's exactly why we've kind of redid
[00:10:45] the entire shipping school community is
[00:10:48] we have this course outline being built.
[00:10:51] It's a 24-week sprint of answering all
[00:10:54] those questions. What is an API? What is
[00:10:56] an AI agent? How does machine learning
[00:10:57] work? How does AI inference work? What
[00:10:59] is machine learning? How do AI agents
[00:11:02] communicate with each other? What is
[00:11:03] MCP? What is authentication? We go over
[00:11:05] what is superbase, what is neon, what is
[00:11:08] PostgreSQL, what is vector embeddings,
[00:11:10] all of the technical details to help you
[00:11:12] become the builder you need to be in the
[00:11:14] AI era. I'll put the link to the
[00:11:16] community down below. These are going to
[00:11:18] be courses that are released four times
[00:11:20] a week. And you're seeing the syllabus
[00:11:22] right before your eyes. is a 24-week
[00:11:24] sprint of every single thing you need to
[00:11:27] know about AI to hit the ground running
[00:11:29] to build with AI agents. I really think
[00:11:33] once AI agents can connect to
[00:11:35] everything, the winners are going to be
[00:11:38] the people who know how to connect to
[00:11:40] other tools safely. That is it. I
[00:11:43] believe the third thing we really need
[00:11:44] to be thinking about is if you have a
[00:11:46] boring business, good. That means no one
[00:11:49] else is going to do it and you're going
[00:11:50] to have less competition. I know that
[00:11:52] sounds weird, but stick with me. Boring
[00:11:54] businesses are full of weird workflows.
[00:11:56] Things like invoices. God, I'm already
[00:11:58] bored. Listings, customer messages,
[00:12:00] quote requests, scheduling, inventory,
[00:12:03] even follow-ups is pretty boring. But
[00:12:04] every one of those has tools, APIs,
[00:12:07] spreadsheets, portals, and old processes
[00:12:09] around it that you could build a
[00:12:10] business on. That is agent fuel. The big
[00:12:13] companies are fighting over that
[00:12:14] infrastructure, but the small builders
[00:12:16] can win by turning that infrastructure
[00:12:18] into specific workflows. Not general AI,
[00:12:21] but specific outcomes. An agent that
[00:12:24] reconciles contractor invoices. That is
[00:12:26] huge money. An agent that turns product
[00:12:28] photos into marketplace listings. Money.
[00:12:31] An agent that watches failed builds and
[00:12:34] opens a fixed PR. Oh, you're swimming.
[00:12:36] An agent that checks lead emails or
[00:12:39] drafts a reply or updates a pipeline.
[00:12:42] That's the game we're playing here. And
[00:12:43] if product and if your product basically
[00:12:45] has already an API, you need to make it
[00:12:48] agent readable. And if your product
[00:12:49] doesn't have an API, I need to know why.
[00:12:52] Like come on. Because we are moving into
[00:12:55] a world where the buyer might be a
[00:12:57] human, but the daily user is probably
[00:13:00] going to be an AI agent. This isn't hype
[00:13:02] anymore. This is actually happening.
[00:13:04] That is what these acquisitions are
[00:13:06] pointing at. Anthropic says hundreds of
[00:13:08] companies rely on stainless for SDKs,
[00:13:11] CLIs, and MCP servers. I mean, I have
[00:13:13] the source down below. Read it.
[00:13:14] TechCrunch says the acquisition takes a
[00:13:17] key infrastructure supplier out of the
[00:13:19] hands of Anthropic competitors and says
[00:13:21] Anthropic will wind down hosted
[00:13:23] stainless products. Put those together
[00:13:25] and Anthropic wants tighter control over
[00:13:27] how cloud connects to the world. That
[00:13:29] does not mean that every builder should
[00:13:31] panic, but it does mean we should be
[00:13:33] honest about the direction on where this
[00:13:34] is going. AI companies are not just
[00:13:37] competing on chat anymore. They're
[00:13:39] competing on distribution. They are
[00:13:41] competing on developer experience and
[00:13:43] they're competing on tool access.
[00:13:44] Essentially, they're competing on who
[00:13:46] becomes the default way agents touch
[00:13:48] software. And that is why OpenClaw
[00:13:50] matters here too. I know I need to put
[00:13:52] this in here somewhere. OpenClaw is not
[00:13:55] just another chatbot. The OpenClaw
[00:13:57] readme describes it as a personal AI
[00:13:59] assistant. You run your own devices with
[00:14:02] channels like Telegram, Slack, and
[00:14:03] Discord. And that means open claw is
[00:14:06] already built around the idea that AI
[00:14:08] agents live where the work happens like
[00:14:10] messages and calls and files and tools
[00:14:12] and skills and cron jobs. That's what
[00:14:14] makes it so appealing. Getting it up and
[00:14:16] running is another thing. So the lesson
[00:14:18] from anthropic and the stainless
[00:14:20] acquisition is not that everyone should
[00:14:22] only use cloud. It's the lesson is that
[00:14:24] agent builders need to own their own
[00:14:26] workflow layer. So if you're using
[00:14:28] openclaw, Hermes codeex, cloud code or
[00:14:30] whatever, I don't care. Just start
[00:14:31] thinking less like a prompt engineer and
[00:14:33] more like an operator. Like what systems
[00:14:36] does my AI agent need to work and what
[00:14:38] permissions does it need? What should it
[00:14:40] never touch? What does it need to ask
[00:14:42] approval for? And what does it leave
[00:14:44] proof like an audit trail? And where
[00:14:46] does it fail safely? So you know that it
[00:14:49] fails. That is the difference between a
[00:14:51] demo and an actual business. And that is
[00:14:53] why I keep saying that money is not in
[00:14:55] generic AI. The money is in the workflow
[00:14:57] automation and the money is in the
[00:14:59] boring integrations. Basically, the
[00:15:01] money is in taking a painful job that
[00:15:03] happens every day and running it with
[00:15:05] supervision. Anthropic buying stainless
[00:15:07] is a loud signal that the big labs know
[00:15:10] this, too. And they know the next battle
[00:15:12] is not just bigger context windows or
[00:15:14] better benchmark screenshots, even
[00:15:16] though those get all the clicks. Like, I
[00:15:18] mean, look on Twitter, it's like every
[00:15:20] time a benchmark released, it's like
[00:15:21] 150,000 uh views and 3,000 likes and the
[00:15:26] LLM sucks. Can't even tool call
[00:15:28] properly. What's going on? The money is
[00:15:29] in the connection. It's in the action.
[00:15:31] It's in the reliability. It is in agents
[00:15:34] reaching the tools where the real work
[00:15:35] lives. So, if you're a builder, here is
[00:15:38] the move. You need to pick a business
[00:15:40] workflow and map every tool it touches.
[00:15:42] Find the API docs. Find the MCP server
[00:15:45] if one exists. If one does not exist,
[00:15:48] build it. Then, building the smallest
[00:15:50] agent that can compete and complete one
[00:15:53] real job with an approval and logs,
[00:15:56] that's money. Just have it do one job. a
[00:15:59] job someone would pay to stop doing
[00:16:01] manually. That's money. That is how you
[00:16:03] turn this news into actually something
[00:16:05] useful. Focus on one thing that's
[00:16:06] simple. Automate it. Maybe it's
[00:16:08] something that's already in your
[00:16:08] business that you hate doing. Build it
[00:16:11] for yourself and then sell it. Those are
[00:16:13] the road signs. And I can't drive the
[00:16:15] car for you. I can't build for you. You
[00:16:17] have the tools. You need to actually
[00:16:18] take action. Start messy. Start before
[00:16:20] you're ready. Even if you don't know how
[00:16:22] to use these tools, how do you think I
[00:16:23] learned how to use them? By just
[00:16:25] building and breaking things. So that's
[00:16:27] the road sign and it's very clear the AI
[00:16:29] agent race is moving from intelligence
[00:16:31] to access and the best agent is not just
[00:16:34] the one that thinks the best. It's the
[00:16:36] one that can safely reach the right tool
[00:16:38] at the right time with the right
[00:16:40] permission and finish the actual job. If
[00:16:42] you want help building these actual
[00:16:44] workflows, like I said, I showed the
[00:16:46] syllabus earlier, join us in inside the
[00:16:48] shipping community, shipping school
[00:16:50] community. We have over 150 members and
[00:16:53] like I said, four live calls a week and
[00:16:55] we are building up the course library.
[00:16:57] So you can go back if you can't make
[00:16:58] those calls, you can know what an MCP
[00:17:01] is, how an API works, what is AI, you
[00:17:04] can even learn how to learn learn how to
[00:17:06] install local LLMs. If you are a local
[00:17:09] LLM enthusiast and you have the hardware
[00:17:11] to run it, we teach technical deep dives
[00:17:14] as well. So like we're not just sitting
[00:17:16] around debating all day. We're actually
[00:17:18] learning and building things and we're
[00:17:19] here to help you build them. So, we're
[00:17:21] building agents, we're building
[00:17:22] automations, tools, real stuff that real
[00:17:24] businesses actually need. I'll put the
[00:17:26] link down below. You need to check it
[00:17:28] out. And if you haven't subscribed to
[00:17:29] the video or the channel already, what
[00:17:31] are you waiting for? We'll see you in
[00:17:32] the next one. Have a blessed day.
