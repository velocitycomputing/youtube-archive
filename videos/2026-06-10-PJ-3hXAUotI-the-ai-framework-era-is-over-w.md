---
video_id: PJ-3hXAUotI
title: "The AI Framework Era Is Over: Why Context Is the Moat | Jerry Liu"
channel: The Chain of Thought Podcast
url: "https://www.youtube.com/watch?v=PJ-3hXAUotI"
watched_date: 2026-06-10
watched_at: "2026-06-10T12:00:00Z"
watch_count: 1
duration_seconds: 3161
source: youtube-history-browser
added_date: 
history_label: Wednesday
history_order: 58
watched_at_precision: date-from-history-label
watched_percent: 37
estimated_watched_seconds: 1170
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Jerry Liu, CEO of LlamaIndex, argues that the AI framework era has ended because models and agent loops have become sophisticated enough to absorb the scaffolding layer that early RAG applications required. As frontier models (Claude, GPT, Gemini) have improved, they've converged on coding as the primary abstraction for automation and are becoming increasingly capable at reasoning and planning independently. The real differentiation is no longer in framework abstractions but in context quality—the accuracy and accessibility of data, documents, tools, and systems of record that agents can access. The conversation explores how context is becoming the durable moat: structured data from databases, unstructured documents from PDFs and files, APIs from systems of record, web context, and metadata annotations all feed agents the information they need to solve problems at scale.

For organizations building with AI agents today: prioritize extracting and organizing your document context with high accuracy rather than building custom frameworks—frontier models typically achieve only ~80% accuracy on complex documents, which is insufficient for regulated industries, so specialized tools become necessary. Instead of overengineering custom stacks, provide agents with well-structured context and MCPs (tools/APIs), or wait 6 months for general agent harnesses to improve. If you're operating in document-heavy verticals (legal, financial services, insurance, manufacturing, healthcare), focus infrastructure investment on high-accuracy document parsing and metadata extraction since agents will soon be your primary consumers of this context, not humans.

## Transcript

[00:00:00] Think about like any task that like you
[00:00:02] might have difficulty like solving now
[00:00:04] in a generalized fashion. Basically,
[00:00:06] instead of like overengineering your
[00:00:07] stack, if you just like wait 6 months
[00:00:09] with a more general agent harness, like
[00:00:11] it'll probably get better and be able to
[00:00:12] solve the task.
[00:00:18] Is the AI framework era over? Let's talk
[00:00:21] about it. Welcome back to Chain of
[00:00:23] Thought, everyone. I am your host,
[00:00:24] Connor Bronden. My guest today has
[00:00:27] argued publicly earlier this year that
[00:00:30] the AI framework era is over, that the
[00:00:32] scaffolding layer that he actually
[00:00:34] helped build is collapsing into the
[00:00:36] model itself, and that context quality
[00:00:39] is the durable moat once agent loops get
[00:00:42] good enough. In fact, he runs the
[00:00:44] company that's betting on that thesis.
[00:00:46] I'm delighted to have Jerry Lou on the
[00:00:48] show today. Jerry is co-founder and CEO
[00:00:50] of Llama Index. He built one of the most
[00:00:53] installed pieces of AI plumbing of the
[00:00:55] last three years, the indexing and
[00:00:57] retrieval layer a generation of rag apps
[00:00:59] were stitched together with and then
[00:01:01] took Llama index into a new era by
[00:01:03] pivoting the company into managed
[00:01:05] document infrastructure with Llama Cloud
[00:01:07] and Llama Parse. He's made a really
[00:01:10] quite aggressive bet that the framework
[00:01:12] layer he helped popularize is the wrong
[00:01:14] place to play long term. You've probably
[00:01:16] seen him at a conference giving a
[00:01:18] fantastic talk. You've likely seen him
[00:01:21] on Twitterx.
[00:01:22] Jerry, great to have you on Chain of
[00:01:24] Thought. Welcome. And where are you
[00:01:26] joining us from?
[00:01:26] >> Yeah, thanks for having me, Connor. I'm
[00:01:28] joining from, you know, beautiful San
[00:01:30] Francisco.
[00:01:31] >> It is always a pleasure to see you when
[00:01:33] I'm in the Bayer area, and I feel like I
[00:01:35] often just run into you at a conference,
[00:01:37] too. You are so busy these days with the
[00:01:39] success of Llama Index. And one of the
[00:01:42] ways that you have made the company so
[00:01:44] successful is with this aggressive bet
[00:01:47] that what you built originally is no
[00:01:50] longer the approach. The AI framework
[00:01:51] era is over as you put it. What
[00:01:53] specifically died and what survives?
[00:01:56] >> Yeah. So maybe there's probably a little
[00:01:57] bit of nuances to that that statement
[00:01:59] too and I can kind of help clarify it to
[00:02:01] the audience. Um but just to kind of
[00:02:03] trace through an evolution of the
[00:02:05] company, you know, we started off as uh
[00:02:07] kind of a core set of abstractions in
[00:02:09] open source land to help like developers
[00:02:11] back in 2023 build these initial
[00:02:14] applications uh over large language
[00:02:16] models. And at the time, you know, none
[00:02:19] of the patterns were fully formed yet.
[00:02:20] You know, people didn't really quite
[00:02:22] know what agents were and people were
[00:02:24] just starting to get the hang of this
[00:02:26] idea of retrieval augmented generation
[00:02:28] or rag or feeding your private context
[00:02:30] into a model. And so I think basically
[00:02:32] when there's a a space where things are
[00:02:35] still being figured out um and then you
[00:02:37] know there's kind of a lot of
[00:02:38] flexibility in the end application and
[00:02:41] that's where there's kind of value in a
[00:02:44] framework layer because the framework
[00:02:45] provides you know the core abstractions
[00:02:47] to make it easier to build certain
[00:02:49] things. And if you think about like life
[00:02:50] or just like software in general it's
[00:02:52] basically just a series of like
[00:02:53] abstractions layered on top of each
[00:02:54] other. And so we were kind of just the
[00:02:56] open- source abstractions at the base
[00:02:58] layer around the LLM that made it easier
[00:03:00] to both connector data, use different
[00:03:03] types of LLMs and then also experiment
[00:03:05] with different techniques like um you
[00:03:07] know retrieval um being able to do some
[00:03:10] sort of like query rewriting and then
[00:03:12] eventually some sort of a tech reasoning
[00:03:14] harness so you can plug in like tool
[00:03:15] calls and and that type of stuff. Um and
[00:03:18] so I think basically um the reality is
[00:03:21] over the past three years um this space
[00:03:23] has obviously evolved quite a bit. The
[00:03:25] models themselves have gotten
[00:03:26] exponentially better. But what that also
[00:03:28] meant is you know the kind of harnesses
[00:03:30] and the agentic applications themselves
[00:03:33] um have also gotten a lot better and the
[00:03:35] core architecture and patterns around
[00:03:38] certain types of agents have solidified.
[00:03:40] And so it's not like, you know,
[00:03:41] frameworks in in the abstract sense are
[00:03:44] kind of like no longer relevant like
[00:03:46] universally. You know, obviously there's
[00:03:47] still web frameworks. Um there's still a
[00:03:49] bunch of like frameworks in general that
[00:03:51] even like today like agents want to be
[00:03:53] able to use like certain types of
[00:03:55] abstractions on top of others so they
[00:03:56] don't have to like rewrite everything
[00:03:58] from scratch. Um but the reality is like
[00:04:00] a lot of the old patterns of just like
[00:04:02] you know really trying to figure out the
[00:04:05] different internals and mechanics of an
[00:04:06] agent um are less relevant today because
[00:04:09] a lot of those have uh solidified into
[00:04:11] these like general agent harnesses. If
[00:04:13] you look at cloud code, open qua you
[00:04:16] know manis um kind of any sort of like
[00:04:18] deep research agent out there they all
[00:04:21] kind of start following uh general
[00:04:23] patterns where you start having
[00:04:25] abstractions appear at a higher level
[00:04:27] than at the code layer. So whereas at
[00:04:29] the code layer, you know, you might need
[00:04:31] to import like Python classes that wrap
[00:04:33] like different LLA providers, um at a
[00:04:36] higher level now it becomes how do you
[00:04:37] define like a natural language set of
[00:04:39] skills, um an MCP tool, um how do you
[00:04:42] like program this like engine that's
[00:04:44] already running and so there certainly
[00:04:46] is room for like a set of abstractions
[00:04:48] at this layer too. Um and you know there
[00:04:51] are plenty of companies kind of building
[00:04:52] stuff in this space whether it's like
[00:04:54] open code or kind of like you know these
[00:04:55] protocols um being able to help support
[00:04:58] this like new age of agent programming.
[00:05:00] It I think for us personally as a
[00:05:02] company um we did start off at the
[00:05:04] framework layer but fundamentally I
[00:05:06] think our mission was always connecting
[00:05:08] data without webs. And so I think
[00:05:10] throughout the years you know we could
[00:05:12] have operated I guess continued to
[00:05:13] operate at a framework layer as it um
[00:05:16] went up in abstraction but I think for
[00:05:18] us we decided to really identify and
[00:05:21] kind of solve an opportunity where we
[00:05:23] realized you know even as the AI agents
[00:05:26] were getting better um the context layer
[00:05:28] itself was not solved. um you know a lot
[00:05:31] of folks were uploading like
[00:05:32] unstructured document-based data into
[00:05:34] these systems and a lot of that data was
[00:05:37] just like not represented the right way
[00:05:39] and a lot of the legacy kind of OCR
[00:05:41] technology themselves um you know was
[00:05:43] not actually doing a good job at reading
[00:05:46] information out of these pages. And so
[00:05:48] we kind of basically narrowed our focus
[00:05:50] as a framework um to kind of becoming
[00:05:53] core infrastructure um to help provide
[00:05:56] you know highquality context to these
[00:05:58] evolving AI agents which is yeah a
[00:06:00] little bit different than being at the
[00:06:01] framework layer but we do think um
[00:06:04] especially in our position right now is
[00:06:06] something that um you know should be
[00:06:08] durable even as these agents improve.
[00:06:10] Now of course there's still plenty of
[00:06:11] space for like other types of companies
[00:06:13] around the stack. you know, a lot of
[00:06:15] folks are kind of building various types
[00:06:16] of context um that plug in through like
[00:06:19] MCP or skills uh systems of record.
[00:06:22] That's still a thing. Um and you know,
[00:06:24] as I mentioned, they're still kind of
[00:06:25] like higher level abstractions and
[00:06:26] frameworks. Um it's just like those are
[00:06:29] uh kind of a little bit different than
[00:06:30] what we started with. Yeah, I love this
[00:06:32] idea of context quality as a moat
[00:06:35] because increasingly it has become like
[00:06:39] a a watch word for folks this last
[00:06:41] really like six six months in particular
[00:06:43] I feel like where the the push to have
[00:06:47] great context has just exploded as
[00:06:50] coding agents have gotten better and
[00:06:52] better. Um data has become you know
[00:06:54] we've known it's been differentiated for
[00:06:56] a long time but it is just becoming so
[00:06:58] clear that to get the most out of you
[00:07:01] know the next frontier model being able
[00:07:03] to fuel it you need to have great
[00:07:05] documents great data for it and I look
[00:07:10] at the way we are approaching enterprise
[00:07:12] AI today and how much data is still
[00:07:16] locked away in silos and both from a
[00:07:19] tribal knowledge perspective but very
[00:07:21] much so from document perspective and it
[00:07:24] seems incredibly clear that this pivot
[00:07:28] or focusing as you put it has a ton of
[00:07:31] value for enterprises in particular as
[00:07:34] they say okay how can I get all of the
[00:07:36] massive corpus of documents and data
[00:07:38] that we've established over the you know
[00:07:40] maybe decades that we've been in
[00:07:42] existence into extremely useful
[00:07:46] highquality content that can be fed to
[00:07:50] our LMS of choice whether that's you
[00:07:52] know an open model or whether that's you
[00:07:54] know a frontier closed model. So I would
[00:07:58] wonder from your perspective have you
[00:08:00] seen a behavior change that either drove
[00:08:05] your decision to make this pivot for law
[00:08:08] index or is now driving this kind of
[00:08:10] next phase of the company?
[00:08:12] >> Yeah, it's it's a good question. I think
[00:08:14] the context uh need has kind of always
[00:08:17] been present even since when we started
[00:08:19] the framework. Um, part of the reason
[00:08:21] the framework itself got popular is
[00:08:23] because, you know, literally, um, you
[00:08:25] know, you had all these large language
[00:08:26] models. They had a 4,000 token context
[00:08:28] window. I think the first thing a lot of
[00:08:31] Bill was trying to do was, you know, how
[00:08:32] do I just get this to understand my
[00:08:34] company knowledge base? And obviously
[00:08:35] the company knowledge base was not going
[00:08:36] to fit within the 4,000 uh context
[00:08:39] window. Um, whether it was your notion
[00:08:41] database, you know, your kind of uh set
[00:08:43] of juror tickets, um, you know, your
[00:08:45] Salesforce, that type of stuff, like it
[00:08:47] just wasn't going to fit. And so how do
[00:08:48] you figure out patterns to kind of
[00:08:50] inject LMS with the right set of
[00:08:51] information at any given time which you
[00:08:54] know gave rise to this uh these
[00:08:56] techniques of rag in 2023. Um and so I
[00:08:59] think even from from that point onwards
[00:09:01] there's some almost like by definition
[00:09:04] need to kind of provide context um to an
[00:09:07] LLM at the time in order to make it
[00:09:09] actually do stuff. Um and I think as the
[00:09:11] AI space has evolved like the LLM part
[00:09:13] evolved into some like general agentic
[00:09:15] harness. you know there's claude co-work
[00:09:17] quad code openclaw um manis like some
[00:09:20] some of these like general agents uh
[00:09:22] implementations that you can basically
[00:09:24] use from a third party provider um and
[00:09:26] then you know uh there's all the things
[00:09:29] you can plug into the agent harness so
[00:09:31] MCP tools skills um the actual task that
[00:09:34] you want to define um by definition this
[00:09:37] is almost like the this is the context
[00:09:39] layer right and the frontier labs are
[00:09:41] building these incredible generalized
[00:09:43] reasoning capabilities um that uh need
[00:09:46] access to like external services, tools
[00:09:49] and context to actually do things. And
[00:09:51] so when I think of the context layer,
[00:09:53] it's literally anything surrounding the
[00:09:54] model like the set of services that has
[00:09:56] access to in order to do things. And
[00:09:58] this extends this could be anything like
[00:10:01] it could be an existing piece of
[00:10:03] software that the agent is able to use
[00:10:06] like if it has MCB connectors to
[00:10:08] Confluence or Salesforce, you know,
[00:10:10] those are providers of context. Um
[00:10:12] that's why I think people think this
[00:10:13] idea of a system of record is still
[00:10:15] going to be around because um agents um
[00:10:18] need a way to actually store act and
[00:10:20] operate on data. Um and then you know
[00:10:23] there's like web context being able to
[00:10:25] actually crawl the internet and being
[00:10:27] able to efficiently search for things um
[00:10:29] so that the agent has access like live
[00:10:31] information. There's structured data,
[00:10:33] you know, stuff locked up within SQL
[00:10:35] databases. Um, and then and for us it's
[00:10:37] it's like document context, like stuff
[00:10:39] that's locked up within, you know, these
[00:10:41] unstructured document containers within
[00:10:43] your file system in the form of like
[00:10:45] PDFs or PowerPoints that need advanced
[00:10:47] technology like new age OCR to actually
[00:10:49] read information off the page. Um, and
[00:10:52] so I think uh for any builder or
[00:10:54] basically any software company today,
[00:10:56] one of the boats is actually just being
[00:10:57] a a provider of like tools and context
[00:11:00] um to the AI agent. Or maybe to put it
[00:11:03] another way, I think a lot of software
[00:11:04] companies are trying to figure out how
[00:11:06] to make their software and services more
[00:11:08] agent native and also based on
[00:11:10] consumption. Um, and so, you know,
[00:11:11] instead humans using uh your SASful or
[00:11:15] humans, you know, reading your documents
[00:11:17] um or humans doing, you know, uh
[00:11:19] searches in Google, you now have agents
[00:11:21] actually going in and, you know, calling
[00:11:23] a ton of MCP tools and writing scripts
[00:11:25] and doing these calls. And um a lot of
[00:11:28] the world is basically redesigning these
[00:11:30] patterns to make it suitable so that
[00:11:32] agents can like launch massive volumes
[00:11:34] of queries through any piece of software
[00:11:36] to both like get information and also do
[00:11:39] things. Um and so I think that's uh kind
[00:11:41] of how it's evolved over the years. But
[00:11:43] even from the beginning like almost like
[00:11:45] again by definition like you need like
[00:11:48] kind of this idea of specifying some
[00:11:50] sort of task plus like additional data
[00:11:52] for um AI to do things. Um and I think
[00:11:56] the like functionality of that has only
[00:11:59] expanded over the years as AI agents
[00:12:01] have gotten more advanced.
[00:12:02] >> Yeah. The fact that even Mercury for
[00:12:05] banking has a CLI now I think really
[00:12:07] says a lot
[00:12:09] >> about what we're trying to provide.
[00:12:12] >> We've not to say that developer
[00:12:14] experience has gone away but agent
[00:12:15] experience is as important if not I
[00:12:18] would argue much more important
[00:12:19] especially not just now but in the
[00:12:21] months ahead. We need to be providing
[00:12:24] all this information to agents to make
[00:12:25] them special. And part of this is
[00:12:27] because, you know, native function
[00:12:29] calling has gotten so good. Construction
[00:12:31] following has gotten much better. Agent
[00:12:33] loops are at least good enough. And the
[00:12:36] models are just so much smarter than
[00:12:37] they were 2 years ago. I think you used
[00:12:38] to be able to see this major gulf
[00:12:41] between certain frontier models. Um, and
[00:12:45] particularly since, you know, Deepseek
[00:12:47] really shawned the onto the scene. But I
[00:12:50] would look at Kimmy and others where
[00:12:52] open models are are not far behind. And
[00:12:55] now I should caveat I haven't gotten
[00:12:56] access to mythos yet. So maybe there is
[00:12:59] this massive leap coming that I'm not
[00:13:01] seeing. Uh but right now it feels like a
[00:13:04] lot of the differentiation that you're
[00:13:05] seeing between companies is how
[00:13:07] effectively are they able to give an LLM
[00:13:10] data and context and tools um and
[00:13:13] provide it the right governance to just
[00:13:16] go and run essentially.
[00:13:18] >> Yeah. Yeah. Exactly. I think basically
[00:13:20] all the generalized frontier labs are
[00:13:22] converging on kind of similar ideas um
[00:13:24] with like some slight implementation
[00:13:26] differences and the ideas you know
[00:13:28] they're all kind of settling on this
[00:13:30] idea of uh coding as the first layer of
[00:13:32] abstraction that um you know that uh
[00:13:35] they're just going to get really good at
[00:13:37] helping to automate and in the process
[00:13:39] because coding is basically a proxy for
[00:13:40] computer use then you know you can kind
[00:13:43] of use some of the techniques and
[00:13:44] capabilities there and use that to
[00:13:46] basically automate any type of knowledge
[00:13:48] work not just software engineering. Um
[00:13:50] that is why Clyde uh interfaces today
[00:13:53] are so popular because they're basically
[00:13:54] tuned for these like coding agents are
[00:13:56] really good at writing bash and writing
[00:13:58] code um and actually just enabling them
[00:14:01] to do that to basically operate an
[00:14:02] interface. Um so I think the um frontier
[00:14:06] models honestly are probably all going
[00:14:08] to start like they're all going after
[00:14:10] kind of like the same type of things. um
[00:14:12] you know maybe one day it's like uh Opus
[00:14:14] is better at like financial knowledge
[00:14:16] work, maybe GPD 5.5 is like a little bit
[00:14:18] better at certain types of coding.
[00:14:20] They're all kind of going after it. Um
[00:14:21] and I think open weight models are
[00:14:23] catching up. I mean I think it's kind of
[00:14:24] impressive to see kind of the uh
[00:14:26] diversity of like parameter sizes are
[00:14:28] basically almost like simulating what
[00:14:30] you know opus uh like four was you know
[00:14:33] like a few months ago or half half um
[00:14:35] half a year ago um with like a smaller
[00:14:37] parameter size model. Um so the advance
[00:14:39] advancements are great. I think for
[00:14:40] everybody else in the space it just
[00:14:42] means um think about like any task that
[00:14:44] like you might have difficulty like
[00:14:47] solving now um in a generalized fashion.
[00:14:50] Um and like basically instead of like
[00:14:52] overengineering your stack if you just
[00:14:53] like wait six months um with a more
[00:14:56] general agent harness like it'll
[00:14:57] probably get better and be able to solve
[00:14:58] the task assuming you actually just like
[00:15:00] specified the parameters and the task
[00:15:01] right. Yeah, I totally agree and I think
[00:15:03] your point about Frontier Labs in
[00:15:06] particular solidifying around coding as
[00:15:09] this first abstraction layer is so apt.
[00:15:11] A, it's just a great way to communicate
[00:15:13] with computers which enables so much
[00:15:15] particularly as we it becomes so much
[00:15:17] cheaper to automate and we now can do
[00:15:20] differentiated automations, not just
[00:15:22] linear ones. But I I would look back to
[00:15:25] a conversation I had with the poolside
[00:15:27] co-founders on the podcast of God, a
[00:15:29] little over a year ago now, something
[00:15:30] like that, where they talked about this
[00:15:32] idea of coding is the way to AGI. And
[00:15:36] you know, that's a it's a bit of a hype
[00:15:38] phrase, but I think we're really seeing
[00:15:39] that come to fruition where it's like,
[00:15:41] oh yeah, everything is converging around
[00:15:42] being excellent at coding and then being
[00:15:46] able to automate tasks because of that.
[00:15:49] Uh, and we're just seeing that push
[00:15:50] forward. Yeah, I think I think it's
[00:15:52] definitely a proxy. Um I think it's
[00:15:54] because the way your computer is
[00:15:56] designed is that you know if you um uh
[00:15:58] like code and program around it. It
[00:16:00] basically gets you to most of the way of
[00:16:02] what you want. Um anyways, because
[00:16:04] there's like the command line, you can
[00:16:05] like write scripts, you can execute
[00:16:06] tasks, like every uh service has like an
[00:16:09] API that you can just call. Um and you
[00:16:11] know like with coding you can get a lot
[00:16:13] of the way there. I think yeah the next
[00:16:14] part is probably just like vision
[00:16:15] capabilities. Um, I think with advanced
[00:16:17] vision capabilities, you can start
[00:16:19] looking at things that, you know, not
[00:16:20] just at the code or like text level, but
[00:16:23] um, you know, actually be able to take
[00:16:24] like an entire computer screen and just
[00:16:26] like operate it at a visual level so you
[00:16:28] can know what to click and, you know,
[00:16:29] um, know what you're looking at, zoom in
[00:16:31] on certain things. Um, I think that's
[00:16:33] probably the next step that every
[00:16:34] Frontier Lab is is going for is just
[00:16:36] like combining uh coding, which is an
[00:16:38] efficient way of like, you know, writing
[00:16:40] automation and operating over interfaces
[00:16:42] with just like vision. Um, and even like
[00:16:44] operating over video streams, um, so it
[00:16:47] can just like more intelligently take
[00:16:48] actions.
[00:16:49] >> Yeah, it's interesting to see this all
[00:16:50] converging as well with robotics and the
[00:16:52] approaches there of okay, how can we now
[00:16:55] get these to take more intelligent
[00:16:57] actions in the real world? Uh it's going
[00:17:00] to be fascinating to see how this all
[00:17:01] develops the next few months. But in
[00:17:04] particular, as you mentioned, the way to
[00:17:07] make this effective, whether that's
[00:17:10] trying to have a million door dashers
[00:17:12] wear a camera so that your robots can
[00:17:14] get better at delivering food, whether
[00:17:16] that's getting as much excellent code or
[00:17:20] bad code that I wrote back in the day
[00:17:22] into your model for training so that you
[00:17:24] can be great at coding, or whether it's
[00:17:26] trying to get your particular business
[00:17:28] to uh or your particular set of agents
[00:17:31] to understand your business through the
[00:17:32] document. context and other context uh
[00:17:35] that you've established over the years.
[00:17:36] It all comes back to, you know, training
[00:17:39] data and context. And I I think this is
[00:17:42] a bit of a simplification, but I would
[00:17:44] argue that, you know, we can kind of
[00:17:46] look at context just like a crucial type
[00:17:47] of data. And it's almost silly for us
[00:17:49] sometimes to not conflate the two terms.
[00:17:52] Like obviously there are reasons not to,
[00:17:54] but like anytime you say data, you could
[00:17:56] also think of data as just like context
[00:17:57] for a model in in the right situation.
[00:18:00] And you've made this bet that context
[00:18:03] quality is what's going to compound over
[00:18:04] the next couple years.
[00:18:06] Can you talk to me about why you're so
[00:18:09] convinced this is going to be durable
[00:18:10] instead of just another, you know,
[00:18:12] commoditized step?
[00:18:13] >> Yeah, for sure. Well, you know, I can
[00:18:15] talk a little bit about um maybe like
[00:18:17] documents in particular, but the, you
[00:18:19] know, start with the overall space. Um I
[00:18:20] think in general you know if you think
[00:18:22] about the context layer I think as I
[00:18:23] mentioned um the overall like um uh
[00:18:27] agent harness is kind of a blank slate
[00:18:28] like this the frontier labs will give
[00:18:30] you you know you have access to cloud
[00:18:31] co-work um you have access like cloud
[00:18:33] code um like there's no kind of um
[00:18:37] starting thing um like you basically
[00:18:39] have to put in the instructions to
[00:18:41] actually get it to do things um and I
[00:18:43] think like once you start like operating
[00:18:45] with that kind of mindset then you know
[00:18:48] there's certain types of tasks where you
[00:18:49] have to give it a lot of instructions by
[00:18:51] definition for it to actually do things
[00:18:53] well because not only is it spec like
[00:18:55] can you specify that task in like a
[00:18:56] single sentence of natural language you
[00:18:59] now have to give it a lot of context
[00:19:00] like for instance if I'm trying to um
[00:19:02] you know like prepare for a customer
[00:19:04] call um that's upcoming on my calendar
[00:19:06] um it's not like I can just say I need
[00:19:08] you to prepare for my customer call I
[00:19:10] need to actually feed it the you know
[00:19:12] previous five to 10 transcripts on the
[00:19:14] customer um actually look into kind of
[00:19:16] the email threads of what the recent
[00:19:18] conversation history has And so there
[00:19:20] are just like tasks that by definition
[00:19:22] need like lookup of kind of external
[00:19:24] sources of data and um you know you kind
[00:19:28] of need ways of actually providing that
[00:19:30] data for uh the task to kind of be more
[00:19:33] well specified so you can actually solve
[00:19:35] it. Um, and I think the way I think
[00:19:37] about vertical AI, which we're not
[00:19:39] doing, but you know, a lot of these
[00:19:40] vertical AI companies, um, is basically
[00:19:43] packaging context in a way that's like a
[00:19:45] little bit easier, um, to kind of, uh,
[00:19:48] solve certain tasks instead of relying
[00:19:50] on users to do it themselves. You know,
[00:19:51] I think Claude Cobberg is such a blank
[00:19:53] slate and I'm pretty sure if you
[00:19:54] equipped it with the right like tools
[00:19:56] and MCPS and skills. Um, you could
[00:19:58] basically use it to do anything um that
[00:20:01] like is possible within the current like
[00:20:03] you know um uh realm of possibility of
[00:20:06] like AI agents. Um but it's just certain
[00:20:08] things will require you to put in like
[00:20:10] you know a lot of work like you would
[00:20:12] need to write and really tune like some
[00:20:15] giant skills file plus like MCP tools uh
[00:20:17] for it to solve like some sort of
[00:20:19] knowledge task. Um and you know the
[00:20:21] reality is most people either don't have
[00:20:23] time um or they don't know how to um or
[00:20:26] some combination of both and um
[00:20:28] especially if you look at all these like
[00:20:30] AI solutions in certain verticals like
[00:20:32] whether it's financial research or kind
[00:20:34] of healthcare I mean who knows like you
[00:20:35] know anthropics kind of building some of
[00:20:36] these tools too but basically you know
[00:20:38] like by providing a tailored interface
[00:20:40] to solve a task it just makes it way
[00:20:42] easier to kind of actually do the thing
[00:20:45] with AI versus like relying on you
[00:20:48] actually having to program this like
[00:20:49] blank slate to actually do everything.
[00:20:52] Um, and I think that's kind of where the
[00:20:53] value of a lot of like vertical AI
[00:20:55] provides. Um, is I almost think of
[00:20:57] vertical AI as a form of like context uh
[00:20:59] to help like solve uh more domain
[00:21:01] specific tasks. Um, now kind of going
[00:21:04] into a little bit what we do because
[00:21:05] context itself I think is like super
[00:21:07] general. Um, it's just like literally
[00:21:09] any set of like uh inputs you provide to
[00:21:11] the model including both like inputs
[00:21:12] plus like task plus uh you know uh
[00:21:15] external data. We're specifically
[00:21:17] interested in like document context and
[00:21:20] turning a PDF into markdown or some um
[00:21:24] extracted form of information that's
[00:21:25] like easy and accurate um for the agents
[00:21:28] to understand. Um I think the way that
[00:21:31] we get compared is against both um kind
[00:21:33] of legacy OCR tools. Um there's like 25
[00:21:36] plus years of uh document OCR tools that
[00:21:39] their entire job was to convert PDFs to
[00:21:41] like markdown uh or some sort of text.
[00:21:43] Um, and the other alternative is you um,
[00:21:47] uh, feed an image of like the screenshot
[00:21:50] directly into the frontier model. Um,
[00:21:52] and then basically just use the frontier
[00:21:54] model um, as an OCR tool. So I think
[00:21:56] like that's kind of um, uh, like that
[00:22:00] that's kind of the basis of comparison
[00:22:01] here. And I think for us um we kind of
[00:22:04] see a lot of opportunity in building
[00:22:07] something that's just like extremely
[00:22:09] high accuracy um at low cost if we just
[00:22:12] like focus on both like very fine-tuned
[00:22:15] models plus like agentic harness
[00:22:17] techniques um only on document
[00:22:19] understanding. Um I think the reality
[00:22:21] with all the frontier models um all the
[00:22:24] frontier models are getting better at
[00:22:26] like general visual understanding. You
[00:22:27] look at Gemini, Opus, um, GPT, every new
[00:22:30] release, they're starting to climb the
[00:22:32] benchmarks on like general visual
[00:22:33] understanding, but they're also just
[00:22:35] tuned for coding, reasoning, and a lot
[00:22:38] of other tasks. And um, especially if
[00:22:41] you're trying to like unlock context for
[00:22:43] just like parse a million PDFs, you
[00:22:45] really need something that's both
[00:22:46] extremely high accuracy, but also really
[00:22:49] cheap. Um, and I think the way the
[00:22:51] Frontier models are tuned, they're just
[00:22:52] not incentivized to actually do that
[00:22:54] because they're tuned for like high
[00:22:55] intelligence tasks. Um and so what we
[00:22:58] basically want to provide is um or the
[00:23:01] opportunity that we see is providing
[00:23:03] just really deep tech to both like parse
[00:23:05] and extract documents with extremely
[00:23:08] extremely high accuracy, low cost plus
[00:23:11] like being able to provide uh relevant
[00:23:13] metadata annotations and tags on these
[00:23:16] documents that then provide like these
[00:23:18] AI agents access to almost like auto
[00:23:21] trails back to the source document. If
[00:23:23] you can trace back to the exact like
[00:23:25] words and draw a box around the words
[00:23:27] that like a legal contract came from
[00:23:29] when an AI agent generates a response,
[00:23:31] that's a very powerful tool in kind of a
[00:23:33] lot of uh uh vertical AI stacks. Um
[00:23:36] whether it's like a big company, small
[00:23:38] company. Um and so we kind of think of
[00:23:41] ourselves as building like just a
[00:23:43] general toolkit plus all the surrounding
[00:23:45] metadata that's also really high
[00:23:47] accuracy uh for AI agents to access like
[00:23:49] any pool of documents. And um for us
[00:23:52] like hopefully it should be uh enough of
[00:23:55] a moat that um is differentiated from
[00:23:57] like users trying to do it with Frontier
[00:23:58] models themselves.
[00:23:59] >> Are you seeing particular verticals
[00:24:02] adopt your stack you know more
[00:24:05] aggressively?
[00:24:06] >> Yeah for sure. You know I think for us
[00:24:08] um the typical verticals that we go
[00:24:10] after uh reflect industries that have a
[00:24:13] lot of their context locked up in
[00:24:14] documents. Um and I totally acknowledge
[00:24:16] like there are a lot of companies that
[00:24:18] honestly like they don't have a lot of
[00:24:20] documents. Um if your entire you know um
[00:24:23] uh like stack is basically dependent on
[00:24:25] like code for instance like we we don't
[00:24:27] typically index like code bases that's
[00:24:29] typically the uh domain of like coding
[00:24:31] agents um but within legal within
[00:24:33] financial services within insurance um
[00:24:36] within manufacturing healthcare um
[00:24:39] education government um and then
[00:24:41] basically the tech versions of all these
[00:24:43] um there are a lot of use cases where uh
[00:24:46] they're just like either humans um or
[00:24:48] just a lot of like inherent knowledge
[00:24:50] bases um that contain you know like
[00:24:52] millions if not more of like just
[00:24:55] unstructured document based data. Um,
[00:24:57] and this is kind of like the uh the
[00:25:00] basis that of a lot of projects that if
[00:25:02] you go into these companies, um, they're
[00:25:04] really trying to automate a lot of
[00:25:06] workflows that typically humans used to
[00:25:07] do and using kind of AI to actually
[00:25:10] understand all the information within
[00:25:11] these docs, extract out the right
[00:25:13] information and also take actions.
[00:25:14] >> And I imagine accuracy becomes a major
[00:25:17] differentiator especially as you're
[00:25:19] working with regulated industries that
[00:25:21] are touching customer funds.
[00:25:23] >> Yeah, that's actually uh super
[00:25:25] important. Um, and the reason why I
[00:25:27] think it's also hard to just like DIY
[00:25:29] your own and stack with a Frontier
[00:25:30] model, I think what um, if you look at
[00:25:32] Opus 4.7, GPU 5.5, um, you know, they're
[00:25:36] they're like not bad at understanding
[00:25:39] like medium complexity documents. Um,
[00:25:41] but it it kind of gives a deception of
[00:25:43] like it'll get you 80% accuracy over
[00:25:45] your document corpus. Well, there'll be
[00:25:47] like 20% of documents that um uh just
[00:25:51] like it'll hallucinate some number um or
[00:25:54] uh you know it'll just like represent a
[00:25:55] table wrong. Um the issue in a lot of
[00:25:58] these use cases is that basically makes
[00:26:00] it below the accuracy bar for like what
[00:26:03] you can actually operate with because
[00:26:04] with 20% hallucination rate that means
[00:26:07] if you actually you know try to extract
[00:26:09] out information or answer questions over
[00:26:11] that data the downstream AI agent
[00:26:13] workflow is going to be disrupted. um
[00:26:15] and kind of any sort of like straight
[00:26:17] through automation with agents. Um it it
[00:26:19] makes it a little harder to trust uh
[00:26:21] given the kind of gap in accuracy. And
[00:26:23] so a lot of these require like really
[00:26:25] high accuracy, but you know 95% plus um
[00:26:28] especially in kind of more sensitive use
[00:26:30] cases with human in the loop review on
[00:26:32] some of the um extracted data.
[00:26:35] >> So are you seeing a tension between
[00:26:37] agentic pipelines where the model
[00:26:39] decides what to extract and then
[00:26:40] deterministic pipelines that have more
[00:26:42] onability? How is that functioning with
[00:26:44] these regulated enterprises?
[00:26:46] >> Yeah, I think um maybe just to reframe
[00:26:49] the question a little bit um I think the
[00:26:52] um there's kind of two use cases for um
[00:26:55] using AI to uh automatically extract
[00:26:58] information from documents which is
[00:27:00] basically what we do as a company. Um
[00:27:02] and so um I know our kind of mission or
[00:27:04] tagline was you know you can kind of um
[00:27:07] use our stuff to unlock context from
[00:27:09] documents and feed it to AI agents. One
[00:27:12] practical instantiation of that is you
[00:27:14] have a bunch of data um that's in the
[00:27:16] form of documents maybe in your box,
[00:27:18] Dropbox, Microsoft, SharePoint. You want
[00:27:20] to create a knowledge base from those
[00:27:21] documents and so um you know and put it
[00:27:24] into a vector database. That basically
[00:27:26] means that you use our capabilities to
[00:27:28] uh kind of do that first pass OCR um on
[00:27:32] top of the documents, convert it into
[00:27:33] markdown and then downstream operations
[00:27:36] become like chunking and batting putting
[00:27:38] into some storage system so you can
[00:27:39] actually search over it. So I think um
[00:27:41] that's kind of like one of the use cases
[00:27:43] where you're uh structuring context in a
[00:27:46] way such that you can use it for any
[00:27:47] downstream agent um whether that agent
[00:27:50] is like simple um you know kind of like
[00:27:52] a a low sophistication agent uh or
[00:27:55] something that's like super advanced
[00:27:56] like cloud code um and I think uh that's
[00:27:59] a very common use case basically any
[00:28:01] enterprise wants to create some agent
[00:28:03] ready knowledge base that can you know
[00:28:05] give some u uh agent like the ability to
[00:28:08] do things now the the Second use case um
[00:28:12] is kind of related but a little bit
[00:28:14] different in that there's a lot of these
[00:28:16] like human workflows that have existed
[00:28:18] already prior to to AI agents where uh
[00:28:22] humans are basically just like reviewing
[00:28:24] massive piles of paperwork and then
[00:28:26] doing like manual data entry into
[00:28:28] systems whether it's like you know
[00:28:30] onboarding um claims invoices uh and you
[00:28:34] know like KYC that type of stuff um
[00:28:36] there's a lot of like existing software
[00:28:38] where it's really just the helper
[00:28:40] interface for humans to upload a bunch
[00:28:42] of documents, help like automatically
[00:28:44] flag some some values and then enable
[00:28:46] them to like more easily do data entry
[00:28:48] and correct like wrong values. And I
[00:28:50] think the advantage of a lot of this
[00:28:52] technology, especially with what we have
[00:28:54] in comparison to legacy OCR tools, is it
[00:28:57] just like massively increases the
[00:28:59] potential to actually automate the
[00:29:01] extraction of all these documents with
[00:29:03] really high accuracy. Um, it's a little
[00:29:05] bit less that story of like I'm going
[00:29:07] to, you know, structure all these
[00:29:08] documents into a knowledge base and give
[00:29:10] it to an AI agent. It is a little bit
[00:29:12] more deterministic too because there's
[00:29:14] usually like business rules and flags
[00:29:16] you want to apply and then systems you
[00:29:17] wanted to route to, but it's still like
[00:29:19] a super important use case cuz like a
[00:29:22] lot of these companies just like have a
[00:29:24] lot of folks just like kind of doing
[00:29:26] this task um that's like relatively
[00:29:29] repetitive. Um, and I think if like they
[00:29:32] use slightly better technology to
[00:29:35] actually understand these documents and
[00:29:36] translate it into a digitalized
[00:29:38] representation, um, you both be like
[00:29:40] saving a lot of money and be able to
[00:29:41] process a lot more volume. Um, that's
[00:29:43] actually pretty common in a lot of these
[00:29:45] industries too. Um, and that's where
[00:29:46] we're seeing some, you know, some kind
[00:29:48] of usage as well. It's interesting
[00:29:50] because it seems like from what you're
[00:29:54] saying if coding agents are basically
[00:29:58] the abstraction layer that models are
[00:30:00] centralizing around and you are enabling
[00:30:04] this other primitive of of the file
[00:30:06] system uh to be unlocked.
[00:30:09] Is this telling us about what the future
[00:30:12] or I guess what does this tell you about
[00:30:14] the future of how agents are going to
[00:30:16] evolve based off of this like clear
[00:30:19] abstraction layer and you know crucial
[00:30:21] primitive.
[00:30:22] >> Uh so I'm not actually convinced the
[00:30:24] file system plus coding agents is going
[00:30:26] to be like the feature so to speak like
[00:30:28] you know a year from now, a year and a
[00:30:30] half, two years from now. Honestly, I
[00:30:31] have no idea. Um so I think I'm I'm
[00:30:33] going to leave that to kind of uh
[00:30:35] whoever wants to like drop a prediction.
[00:30:37] Um, I do think that's kind of the
[00:30:38] current state-of-the-art. Um, because,
[00:30:40] uh, like coding agents are proxy for
[00:30:42] computer use. Um, and vision
[00:30:44] capabilities aren't quite there to help
[00:30:46] like, you know, these agents massively
[00:30:48] stream like real-time video yet. And so
[00:30:50] this is the one of the closer
[00:30:51] representations towards just being able
[00:30:53] to automate a bunch of stuff um on your
[00:30:55] computer. um you know you combine that
[00:30:57] with now this abstraction of uh the file
[00:31:00] system is like CLI ready um and it's
[00:31:02] ready for coding agents to use and these
[00:31:04] agent harnesses are also very good at
[00:31:06] kind of using file systems to help like
[00:31:09] navigate existing documents um you know
[00:31:12] uh like retrieve the right context and
[00:31:14] then like you know take actions over
[00:31:16] them and so I think it's a very powerful
[00:31:18] abstraction right now that actually
[00:31:20] solves like a good chunk of knowledge
[00:31:22] work um and I think where we come in is
[00:31:24] you know again like we we basically
[00:31:26] would be one of the kind of core modules
[00:31:28] if there are like document um um
[00:31:31] document based like types of data um to
[00:31:33] help like unlock contexts from those
[00:31:35] containers um into the file system going
[00:31:37] into the future though like honestly I
[00:31:38] have no idea like I I think um the thing
[00:31:41] is the there's probably going to be some
[00:31:43] new abstraction that's not like just
[00:31:44] coding um like all the vision stuff that
[00:31:46] I mentioned there's probably going to be
[00:31:48] something there that allows them to more
[00:31:50] generally see the screen and do actions
[00:31:52] there might be new types of operating
[00:31:53] systems that actually make it a little
[00:31:55] bit friendlier for agents to like do
[00:31:56] things on top of. Um and then yeah like
[00:32:00] I but but I think for for me like you
[00:32:02] know I reason from first principles like
[00:32:03] even if the um harnesses like like the
[00:32:06] or or even like the kind of core
[00:32:08] primitives change like going from um
[00:32:11] file systems CLY and like coding to
[00:32:14] something a little bit more like vision
[00:32:15] based. Uh this concept of like context I
[00:32:18] think still still matters quite a bit.
[00:32:19] And I think for us like you know I I
[00:32:21] feel reasonably confident in our
[00:32:22] position um of being like a durable
[00:32:24] layer even as these like agent patterns
[00:32:26] evolve.
[00:32:27] >> Yeah. I was wondering about this when
[00:32:29] you brought up the idea of oh the reason
[00:32:31] why we're converging on code today is
[00:32:34] because that's the easiest way to just
[00:32:36] communicate with computers essentially.
[00:32:39] >> And I was kind of going like okay well
[00:32:41] we're already seeing changes in our
[00:32:43] hardware layer. You know it's not just
[00:32:45] GPUs and CPUs anymore. you know, we've
[00:32:48] got TPUs, we've got XPUs, we're we're
[00:32:50] expanding. Are are we going to see a
[00:32:53] total rethinking of like what a computer
[00:32:56] is? I mean, we've already seen people
[00:32:59] talking about it. There's this whole
[00:33:00] idea of Neurolink, etc. Everyone's
[00:33:02] trying things with vision. Uh I I I
[00:33:05] don't know, but it seems like we are at
[00:33:07] the onset of a new hardware wave too,
[00:33:12] though it may take a little longer, that
[00:33:14] is going to match agents, maybe more
[00:33:16] specifically. Yeah, it's possible. Um I
[00:33:18] think there might be a new hardware wave
[00:33:20] and you would know more than I do on
[00:33:21] this. Um in terms of just like kind of
[00:33:22] the underlying um infra and hardware
[00:33:25] that powers some of these evolving
[00:33:26] models, especially as some of the
[00:33:28] architectures like evolve and change and
[00:33:29] that type of stuff. I'm not actually
[00:33:31] sure that there will be like an entirely
[00:33:33] new software layer though um for for AI
[00:33:35] because uh the way it works right now
[00:33:37] with AI is like um and part of the
[00:33:39] reason it's so powerful is instead of
[00:33:41] trying to like reinvent every part of
[00:33:42] the software stack um they just uh the
[00:33:44] Frontier Labs has just made it really
[00:33:45] easy to operate on top of existing tools
[00:33:48] everyone's already using. Um so you know
[00:33:50] they're they're taggraphy not
[00:33:51] reinventing like Windows or Mac or
[00:33:53] Photoshop or just like or even a lot of
[00:33:55] these like SAS tools. um the idea of
[00:33:57] MCP, the idea of like skills, um the
[00:34:00] idea of like, you know, actually just
[00:34:02] being able to write code but import like
[00:34:04] Python libraries is operating on top of
[00:34:07] existing abstractions that have already
[00:34:08] existed. And so I do think it's more
[00:34:10] likely that they're going to try to
[00:34:11] build something that you know runs on
[00:34:13] Mac or Windows um uh even in a
[00:34:15] generalized computer use way versus like
[00:34:17] um you know and then like later on there
[00:34:19] might be a new agent native operating
[00:34:21] system and I'm sure like Microsoft or
[00:34:23] something will come out with that um if
[00:34:24] they if they haven't already tried but
[00:34:26] like basically like I think it's um the
[00:34:29] overall AI trend is to adapt with
[00:34:30] existing tools um and kind of go from
[00:34:32] there. Yeah, this brings to mind the
[00:34:36] framing of kind of this whole episode,
[00:34:38] which is, hey, Llama Mandex went from an
[00:34:41] open source framework to this big pivot.
[00:34:43] Um, how did you do it successfully?
[00:34:46] Because I think there are a lot of folks
[00:34:48] listening or, you know, reading Twitter
[00:34:49] who are going, uh, I'm a little worried
[00:34:52] my startup's going to get killed by
[00:34:53] cloud code. Uh, I'm a little worried
[00:34:55] that a Frontier Lab is going to demolish
[00:34:58] whatever I'm doing because they simply
[00:35:00] start to do it better. they are able to
[00:35:03] automate it away.
[00:35:05] How have you made law index so durable?
[00:35:07] >> It's a good question. I mean, I wouldn't
[00:35:08] say we're in the clear yet. I'm going to
[00:35:09] be totally honest. I mean, we're not
[00:35:11] like um again, we're not Microsoft. Um
[00:35:13] and I do think like at this stage,
[00:35:15] literally anything could happen. Like,
[00:35:16] you know, you look at companies are even
[00:35:18] much more scale than we are. And I'm
[00:35:19] pretty sure they're also having uh
[00:35:21] constant like existential crises every
[00:35:23] time there's kind of some some like new
[00:35:25] model release coming out. I do think
[00:35:27] that what we have done has put us in a
[00:35:29] bit more of a durable position um
[00:35:31] compared to what we were like three
[00:35:33] years ago. Um and I think um to be
[00:35:35] honest it's not like um you know for any
[00:35:38] uh potential founders like it's it's not
[00:35:40] like an easy process. Um you like are
[00:35:42] fundamentally kind of thinking about how
[00:35:44] to disrupt um your own product your own
[00:35:47] product strategy um and then also kind
[00:35:49] of uh maybe almost like move the
[00:35:51] audience of who you're serving. Um, and
[00:35:53] there's going to be a core group that
[00:35:54] remains um to kind of like some other
[00:35:56] group that uh maybe is like a little bit
[00:35:59] more adjacent to what you were
[00:36:01] originally uh serving. And so I think
[00:36:03] just like all these questions um you
[00:36:05] know it's it's not an easy task. Um but
[00:36:07] I do think you know one thing that's
[00:36:09] interesting is you listen to all these
[00:36:10] podcasts of folks um with companies that
[00:36:13] are like much bigger than where we are
[00:36:15] today and they're all kind of like
[00:36:18] wondering the same things. Like I think
[00:36:19] even these like very seasoned business
[00:36:21] leaders at public SAS companies are
[00:36:22] trying to figure out how to disrupt
[00:36:24] their business or figure out how to like
[00:36:25] completely reinvent their product. And
[00:36:27] so I guess the only thing I'll say is
[00:36:29] you know you're not the only one and
[00:36:31] pretty much like companies that are a
[00:36:32] thousand times bigger than you are also
[00:36:34] trying to do the same thing. Um and
[00:36:35] that's harder than you trying to do it
[00:36:37] yourself. Um and so I think that's
[00:36:39] that's one of the things I'll say. Um in
[00:36:42] general I I think uh especially in this
[00:36:44] like AI landscape, everybody has to kind
[00:36:46] of be extremely on their toes and just
[00:36:48] be willing to kind of like reinvent um
[00:36:50] like their ICP. Um and and I know that
[00:36:53] has some potential issues for kind of
[00:36:55] like uh continuity. Um but you know at
[00:36:58] the same time if you are able to do it
[00:37:00] um and even for like some period of time
[00:37:02] it helps you establish your foothold and
[00:37:04] uh just be able to like serve some like
[00:37:07] emerging need in the AI market. And the
[00:37:09] benefit is because like everybody's so
[00:37:11] interested in AI once something does
[00:37:13] land um it typically grows pretty
[00:37:14] quickly. How did you have to alter your
[00:37:18] own I guess internal company strategy
[00:37:21] when as you made this pivot like did you
[00:37:23] have to change your hiring processes or
[00:37:25] have you changed it in other ways due to
[00:37:27] what's going on? Oh yeah. I mean um I
[00:37:30] mean I think uh I mean this entire
[00:37:32] journey and you know luckily I think we
[00:37:34] hired uh kind of like some some core
[00:37:36] folks that you know are are like uh
[00:37:39] really invested and just like this this
[00:37:41] overall northstar that we had actually I
[00:37:43] don't think has changed too much. Um
[00:37:45] even if the product surface and you know
[00:37:46] the ICP itself has changed the north
[00:37:48] star was always like figuring out how to
[00:37:50] get data into LMS. I mean I think that
[00:37:52] basically was how the company started.
[00:37:53] Um and to some extent that's pretty much
[00:37:55] like still what we are doing trying to
[00:37:57] figure out how to get data into Labs
[00:37:59] just maybe operating at like a little
[00:38:00] bit different of a layer. Um I think
[00:38:03] people understood that mission and I
[00:38:05] think part of the goal was to understand
[00:38:07] like okay what are the best tools
[00:38:09] actually serve that mission. I think in
[00:38:11] the beginning it was a framework um
[00:38:12] because people just didn't really have
[00:38:14] anything really settled down. So the
[00:38:16] best way to build those tools was
[00:38:17] something that just made it easier for
[00:38:18] folks to uh build like various types of
[00:38:21] apps and connect their data in various
[00:38:22] ways. I think as those patterns emerged,
[00:38:24] it became clear one of the value that
[00:38:27] you could uh or the valuable pieces you
[00:38:29] could provide is basically just like
[00:38:31] providing really deep tech around a
[00:38:33] certain piece of context. Um because the
[00:38:35] abstractions were solidifying um but the
[00:38:38] need for like high quality production
[00:38:39] context uh was still evolving. Um just
[00:38:42] communicating that to the team um and
[00:38:44] just accept that there's going to be
[00:38:46] friction and then yes like hiring will
[00:38:48] obviously change depending on what you
[00:38:49] actually build. you know, we need like
[00:38:51] kind of core applied AI researchers. Um,
[00:38:53] if you're interested, let me know. Um,
[00:38:55] to actually kind of work on the frontier
[00:38:56] of document understanding um,
[00:38:58] capabilities and actually, you know,
[00:39:00] like do like deep tech like ML, not just
[00:39:03] AI engineering, like actual ML, right?
[00:39:05] Like, you know, model tuning, training,
[00:39:06] that type of stuff. Um, and so, you
[00:39:09] know, I think when you're a startup, you
[00:39:10] just have to adapt.
[00:39:11] >> Jerry, now is when I have to ask you to
[00:39:13] drop your email or best way for folks to
[00:39:15] get in touch if they are listening and
[00:39:17] they're they do want to apply, where
[00:39:18] should they go? Yeah, for sure. Um,
[00:39:20] there's uh llamaindex.aicareers
[00:39:24] um if you're interested. Um, you know,
[00:39:25] we're looking for a variety of roles I
[00:39:27] think at the time of whenever this comes
[00:39:29] out. Um, I'm sure the roles may have
[00:39:30] changed too because, you know, there's
[00:39:31] always kind of expanded needs across
[00:39:32] like go to market and also edge. Um, I
[00:39:35] think the um other piece is, you know,
[00:39:37] we're pretty active on socials. So,
[00:39:38] we're pretty active on LinkedIn. You can
[00:39:39] follow us on Wama Index um and also on
[00:39:42] Twitter. Um, you know, and and um I I
[00:39:45] have a Twitter account, too.
[00:39:46] >> Uh, some folks may have seen you on
[00:39:47] Twitter. That that is for sure. Uh
[00:39:49] Jerry's fairly popular there to say the
[00:39:51] least and I will co-sign here and say I
[00:39:55] know a lot of incredible folks at
[00:39:56] Landex. So seems like it's a cool place
[00:39:58] to work though I haven't actually done
[00:40:00] it myself. Uh so definitely check that
[00:40:02] out if there are any roles that are of
[00:40:03] interest to you. I want to bring it back
[00:40:06] to something you said before we derailed
[00:40:08] on hiring a little more. And it's really
[00:40:11] poignant, but also uh I'm finding it
[00:40:13] mildly concerning as I think more about
[00:40:15] it, which is this idea of, you know, the
[00:40:17] whole job of llama index is getting data
[00:40:19] into LMS. Uh and it's making me think
[00:40:22] about what a high percentage of my own
[00:40:25] job today is just that problem. Um, so I
[00:40:31] guess really it just brings to mind this
[00:40:32] point that you made earlier of like look
[00:40:34] this we may not be durable forever but
[00:40:38] what we're doing today is really
[00:40:39] valuable because uh I mean so much of
[00:40:42] the value creation happening at
[00:40:44] companies around the world today is that
[00:40:46] exact problem of how do we effectively
[00:40:48] get data into LMS? How do we make sure
[00:40:50] it's accurate? How do we just enable
[00:40:53] these models to help us run faster? If
[00:40:55] we all think that velocity and
[00:40:56] throughput is rapidly increasing through
[00:41:00] LLMs that we need to do the same to keep
[00:41:01] up, whether it's in our own jobs or for
[00:41:03] our companies, I mean that's a very
[00:41:05] valuable place to be.
[00:41:07] >> Yeah. Yeah, for sure. I mean, I think um
[00:41:09] you know, there's this existential
[00:41:11] question of just like how much are we
[00:41:13] just an outland in general. Um but yes
[00:41:15] like also I think as um I I do think as
[00:41:18] humans um we basically are kind of
[00:41:20] responsible for at least like defining
[00:41:23] the task uh specifications um and
[00:41:25] understanding it's like similar to
[00:41:27] eventually like how you would
[00:41:28] communicate to another human from a
[00:41:30] junior to eventually a senior employee
[00:41:32] um at their function and be able to give
[00:41:34] them enough like context to get on board
[00:41:36] and get started. And that includes like
[00:41:38] all the data that might be present that
[00:41:40] you don't explicitly communicate but
[00:41:42] that they have to go and research
[00:41:43] themselves. Um, and so they would go in,
[00:41:45] look at your, uh, internal company
[00:41:47] knowledge base, um, look at your
[00:41:48] transcripts, look at your calendar,
[00:41:49] email, um, and be able to synthesize
[00:41:51] stuff. And that's basically what's
[00:41:53] happening with LMS today. You give like
[00:41:54] a task specification. They look at your
[00:41:56] context. Um, they go do things. And this
[00:41:58] only gets better as the models get
[00:41:59] better. We've talked a lot about context
[00:42:02] today. But I'm curious to get your take
[00:42:04] on agent memory, which is something that
[00:42:06] folks are starting to increasingly talk
[00:42:08] about. We had a great episode with
[00:42:09] Richmond on it that I totally recommend
[00:42:12] folks check out. What's your take on
[00:42:14] this and how memory and context should
[00:42:16] be interacting?
[00:42:17] >> Yeah, I think memory is basically just a
[00:42:19] form of I guess like persistent context.
[00:42:22] Um I kind of think of it as like um yeah
[00:42:25] kind of I I I'm still kind of forming my
[00:42:27] opinions about this. Um I think there's
[00:42:29] different types of memory. I mean on one
[00:42:31] hand there's just like um this idea of a
[00:42:33] system of record like entries that you
[00:42:35] update in a database um just because you
[00:42:37] need like a table of things to store
[00:42:39] things. I mean, just think about if you
[00:42:41] make a new entry in a CRM or you you
[00:42:43] make a new entry in notion, right? That
[00:42:45] is a form of memory because you're
[00:42:47] updating your context um within some
[00:42:49] system of record and then with the
[00:42:51] ability to store and retrieve from it.
[00:42:53] And I think there's a lot of um uh ideas
[00:42:57] around like how agents update their
[00:42:59] state that basically revolve around
[00:43:00] that. It could be updating like an
[00:43:02] actual database, updating a SAS tool.
[00:43:04] And with you know Karpathy's tweet it
[00:43:06] was around like being able to build and
[00:43:08] update like your own internal wiki uh
[00:43:10] which is basically a system of record on
[00:43:11] your file system. I mean I think that's
[00:43:13] kind of like um just a general
[00:43:15] applicable practice that literally
[00:43:16] anyone using a coding agent can do
[00:43:18] today. You know you kind of build some
[00:43:20] internal knowledge base of just like a
[00:43:21] set of files um that you can lock up
[00:43:23] later. Um, oftentimes I find especially
[00:43:26] for uh non-titable people or people that
[00:43:29] are a little bit you know too lazy to to
[00:43:31] code um like these days sometimes um you
[00:43:34] know like the simpler the abstraction
[00:43:36] the better and so this concept just like
[00:43:37] having memory just be a pool of files
[00:43:39] under file system is kind of like nice
[00:43:41] to think about because it's pretty easy
[00:43:42] to to represent and store. Um I think
[00:43:45] there are certainly more complicated
[00:43:47] forms of memory. Um there's ways of like
[00:43:50] being able to actually synthesize like
[00:43:51] some sort of like graph from your memory
[00:43:53] or something form like entity
[00:43:55] relationships. Um you know be able to
[00:43:57] synthesize summaries. Um I personally
[00:44:00] have not spent a ton of time like
[00:44:01] building those systems. Um I'm sure
[00:44:02] there are folks that have a lot more
[00:44:04] experience there. And I do think you
[00:44:06] know maybe uh for some of these frontier
[00:44:08] labs when they bake in memory as one of
[00:44:09] the features you do a lot of research to
[00:44:11] kind of understand some of the more
[00:44:13] advanced primitives that actually enable
[00:44:15] users to store various forms of state so
[00:44:17] that you know they don't have to retype
[00:44:19] like various types of context for the
[00:44:20] next task. Um, but I think for for like
[00:44:23] general users, what I'm interested in uh
[00:44:25] a lot of times is just like these dead
[00:44:27] simple abstractions um that like
[00:44:30] literally anyone can just like take
[00:44:31] today um and can still be uh like people
[00:44:35] can still use that as uh an initial
[00:44:37] instantiation of memory um for basically
[00:44:40] any task that they do.
[00:44:41] >> Yeah, I had a conversation I mean
[00:44:43] recorded this morning actually with
[00:44:45] Tyler Aikido who's the CTO of Red Panda
[00:44:48] and I think it'll come out the week
[00:44:50] before this episode. So if it if it
[00:44:51] didn't, I apologize to everyone who's
[00:44:52] watching this and doesn't have that
[00:44:54] right context. But uh he talked about a
[00:44:58] paper that they're working on where
[00:45:00] they're working with a psychologist to
[00:45:02] basically identify trends in agents and
[00:45:05] think through like what are we missing
[00:45:07] as far as how agents think and operate
[00:45:10] in the world. And one of the things that
[00:45:12] came up for us and we talked briefly
[00:45:14] about was this idea of almost like
[00:45:16] cultural memory, the training memory
[00:45:18] that we're starting to see emerge across
[00:45:20] different frontier model families. Uh
[00:45:23] and I think the example that is obvious
[00:45:25] to folks who who are maybe too much on
[00:45:27] Twitter like myself is OpenAI really
[00:45:29] loves goblins evidently like okay GPT
[00:45:32] like sure. Or you can look at like some
[00:45:34] of the the ticks that Claude has picked
[00:45:36] up along the way and how it is kind of
[00:45:39] seen by many as treating things a little
[00:45:41] differently than the OpenAI family of
[00:45:44] models. And I think we're starting to
[00:45:46] see this kind of emerging almost like
[00:45:48] model lineage. You know, you brought
[00:45:50] that up earlier this conversation, this
[00:45:51] idea of look, the models are converging
[00:45:53] on what they can do, but there's this
[00:45:54] like different flavors almost of of
[00:45:56] what's happening there. And I'm curious
[00:45:59] if you have a perspective around,
[00:46:02] you know, what do you think is driving
[00:46:04] this? Is it related to essentially the
[00:46:06] the training data and context are being
[00:46:08] provided? Is it more about the alignment
[00:46:12] approach that the model teams are
[00:46:14] taking? Um do you expect to see this
[00:46:17] kind of almost like differentiated
[00:46:21] diverging cultures occur? Like what do
[00:46:22] you expect to happen on the model front?
[00:46:25] >> I think it's a fascinating topic. Um, I
[00:46:27] will say I um I probably don't have that
[00:46:30] much experience to actually speak to it.
[00:46:31] So I mostly speak to it as like a
[00:46:33] observer. Um, when I think about memory
[00:46:35] like especially because we're kind of
[00:46:36] like the builders on top of these
[00:46:38] models, it's typically the stuff that
[00:46:39] like is individual user based uh to help
[00:46:41] like store state to help like solve your
[00:46:43] task and less like the general memory. I
[00:46:45] think a lot of the pre-trained memory is
[00:46:47] is super interesting though because
[00:46:48] obviously there's like uh personality
[00:46:50] differences between 5.5 and like opus
[00:46:52] and obviously they all have like these
[00:46:54] different texts. they write a little bit
[00:46:55] differently. I think um that's actually
[00:46:57] been one of my top complaints is a lot
[00:46:59] of these models uh at least in my
[00:47:00] opinion um my humble opinion are
[00:47:02] absolutely trash at writing um according
[00:47:05] to how I want them to actually write. Um
[00:47:07] and it might be a skill issue on my end.
[00:47:09] Um but basically like I think the um the
[00:47:14] uh like ability to actually um have both
[00:47:18] like this personality characteristics
[00:47:19] which actually does flow into your
[00:47:21] writing too. Um, I think a lot of it's a
[00:47:23] result of post training. And you know,
[00:47:24] it's kind of interesting. There's all
[00:47:25] these RL environments um that are being
[00:47:27] sold to all these frontier labs these
[00:47:29] days. I almost wonder if it's just like
[00:47:31] you do some data distribution of like uh
[00:47:33] all the different environments and sims
[00:47:35] that like every Frontier Lab is running
[00:47:37] and then you kind of correlate that to
[00:47:38] the personality type of like what it
[00:47:40] actually ends on. Um, I would be super
[00:47:42] curious. I just don't have access to any
[00:47:43] of this data so I can't actually speak
[00:47:45] to it intelligently.
[00:47:46] >> If someone wants to send Jerry and I
[00:47:48] that data that would be fascinating. I
[00:47:49] think we would love to check that out.
[00:47:51] Yeah, like you know let's say this was
[00:47:52] like 50% tuned on like you know
[00:47:54] financial knowledge work whereas this
[00:47:56] other frontier model is like 30% tuned
[00:47:57] but like 20% more tuned on like you know
[00:48:00] patients or or doctor like you know
[00:48:02] doctors talking. Yeah, I think it'd be
[00:48:04] super interesting.
[00:48:05] >> That makes a lot of sense to me. I
[00:48:07] interesting. Yeah, I um I will bring up
[00:48:09] on the writing skills front briefly too
[00:48:11] as we're wrapping up here. uh highly
[00:48:13] recommend. What I've found successful is
[00:48:16] basically taking three classes of skills
[00:48:19] to help LLM's write on my behalf. One
[00:48:22] being like writing voice context. So
[00:48:24] building out like a context document of
[00:48:26] how I like to write and like building a
[00:48:29] skill on top of that and then having
[00:48:30] have a bunch of examples I can reference
[00:48:31] particularly for like different types of
[00:48:32] writing. Two, I built a skill that I
[00:48:35] open sourced called uh avoid AI writing.
[00:48:38] Um it's done pretty well. model's got
[00:48:39] like a I don't know 1400 stars or
[00:48:41] something on it now. But basically it
[00:48:42] says okay here are all the ticks we see
[00:48:44] for models. Please just get rid of that.
[00:48:46] Like like think think about rhythm
[00:48:48] differently. Do these things. Um you
[00:48:49] might find that useful. And then the
[00:48:51] third one I have is I have like an
[00:48:52] editor on top of that where I have like
[00:48:54] a second pass editor. It's like okay
[00:48:56] like I wrote this in your voice then I
[00:48:58] went through it with the the clean AI
[00:49:00] writing skill and said okay like let's
[00:49:02] get all rid of all the m dashes. Let's
[00:49:03] cut down on these like repetitive steps.
[00:49:06] Uh because models while decent writers
[00:49:08] in some cases will often like they'll
[00:49:10] repeat themselves on like oh I I'm this
[00:49:13] thing works I'm just going to use it 15
[00:49:14] times in this essay and it's like good
[00:49:16] lord and then like have that second pass
[00:49:18] editor to help it out.
[00:49:19] >> Yeah it's funny you know I think I tried
[00:49:21] to create like my own writing skill. I
[00:49:23] think it roughly captures uh some of the
[00:49:25] stuff that you're talking about just
[00:49:26] maybe with a little bit less
[00:49:27] sophistication. Um and it's interesting
[00:49:29] you know we're trying to hack our way
[00:49:30] around these models like not being great
[00:49:32] writers themselves. I wonder if it will
[00:49:34] get postering to be better. Yeah, I
[00:49:36] think I I think it will, but the problem
[00:49:38] I see is that everyone I mean we're
[00:49:41] seeing conversions in how people write
[00:49:43] in some areas, but I feel like anyone
[00:49:45] who really cares about writing the craft
[00:49:46] of it wants to have a bit of a
[00:49:47] differentiated voice too. So I I I do
[00:49:50] think it's crucial to have your own form
[00:49:52] of post- training through context and
[00:49:54] how you provision the model and struct
[00:49:55] it as well.
[00:49:57] >> For sure. Yeah, totally agree. Uh well,
[00:49:59] thank you for following me on this this
[00:50:00] brief uh distraction around uh writing
[00:50:04] with AI because I think it's a
[00:50:04] fascinating topic, but I'll I'll
[00:50:06] probably talk about more on this podcast
[00:50:07] at some point. Maybe I'll write an essay
[00:50:09] on it. Uh but Jerry, it's been fantastic
[00:50:11] catching up with you. I appreciate you
[00:50:13] taking the time to come on the show and
[00:50:14] super excited to get this out. Do you
[00:50:16] have any closing thoughts you want to
[00:50:17] share with the audience?
[00:50:19] >> Yeah, no, thanks so much for h having me
[00:50:20] on on the podcast. Um, it was great to
[00:50:22] talk about kind of like the general, you
[00:50:24] know, macro evolutions of like AI itself
[00:50:26] and just like the concept of the context
[00:50:28] layer. Um, I will say, you know, I think
[00:50:30] I'm I'm not like um an expert to like
[00:50:33] 100% accurate at like predicting u
[00:50:35] what's going to happen in like the next
[00:50:36] year or two. Um, but I I do think from
[00:50:38] like first principles uh this idea of
[00:50:41] like I think AI is something that uh is
[00:50:44] going to like fundamentally change and
[00:50:46] get better. So it's helpful to think
[00:50:48] about like exponentials um in that sense
[00:50:50] >> but it's also helpful to think about
[00:50:52] like what typically uh you know stays
[00:50:54] constant like what what are just like by
[00:50:56] definition things you need uh to enable
[00:50:58] the AI even as it gets exponentially
[00:51:01] better. That's basically a thought
[00:51:02] exercise that we did where we thought
[00:51:04] about like the context layer in general.
[00:51:06] Um and for us it meant like narrowing a
[00:51:08] little bit down to kind of like focusing
[00:51:09] on document based data. Um, I think for
[00:51:12] like a lot of builders in like verticals
[00:51:14] or kind of like other uh uh industries,
[00:51:17] it's just like helpful to think about,
[00:51:18] you know, what are things that these
[00:51:20] labs um are likely going to pursue. Um,
[00:51:23] and then, you know, what are things
[00:51:24] that, you know, they're probably not
[00:51:26] just not going to have time for or can't
[00:51:28] u because of like the interface and
[00:51:29] those are areas that you could kind of
[00:51:31] go in and dig into. And so mine, my
[00:51:33] thoughts are just one perspective. Um,
[00:51:35] there's plenty of successful AI
[00:51:37] companies out there. Um, and so, you
[00:51:39] know, I I hope at least some of this was
[00:51:40] like interesting.
[00:51:41] >> I will definitely say it was interesting
[00:51:43] from my end. So, I hope our listeners
[00:51:44] loved it as well. And I know they can
[00:51:46] find a lot more information from Jerry
[00:51:48] and Llamaex atlindex.ai,
[00:51:51] at Jerry's Twitter account, on LinkedIn,
[00:51:53] anywhere else, Jerry, they should go
[00:51:54] check out besides that career page you
[00:51:56] mentioned earlier, which definitely they
[00:51:58] should.
[00:51:58] >> Yeah. No, for sure. I mean, I think if
[00:51:59] you're um if you're generally interested
[00:52:01] um if you do have a lot of docs, you
[00:52:03] know, and and you want to talk about
[00:52:04] this, we do have a self-s serve product
[00:52:06] called model parse. Um, and then you
[00:52:07] know, we also have like a contact form
[00:52:09] on the site. Um, but in general, if you
[00:52:11] also have some of these use cases,
[00:52:12] you're welcome to DM me on Twitter.
[00:52:14] >> Amazing. Jerry, thank you so much for
[00:52:15] coming on the show. It's been great
[00:52:16] catching up with you. I'm going to have
[00:52:18] to try to write an essay for our
[00:52:20] Substack at newsletter. Font.show based
[00:52:23] off of this discussion about writing and
[00:52:25] some of the great insights you provided.
[00:52:26] Uh, so super excited to get that out and
[00:52:28] um, thanks so much for coming on.
[00:52:30] >> Yeah, thanks so much for having me.
