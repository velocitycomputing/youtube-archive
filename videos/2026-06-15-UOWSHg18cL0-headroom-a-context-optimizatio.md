---
video_id: UOWSHg18cL0
title: "Headroom: A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc."
channel: The Linux Foundation
url: "https://www.youtube.com/watch?v=UOWSHg18cL0"
watched_date: 2026-06-15
watched_at: "2026-06-15T12:00:00Z"
watch_count: 1
duration_seconds: 2471
source: youtube-history-browser
added_date: 
history_label: Monday
history_order: 65
watched_at_precision: date-from-history-label
watched_percent: 40
estimated_watched_seconds: 988
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Headroom is a local context optimization layer that compresses data sent to LLMs by removing "noise" while preserving meaning. Built by Tejas Chopra at Netflix, it addresses the problem that 80-90% of data in LLM context windows is wasteful—whether from log files, database queries, code, or web pages. The tool uses specialized compressors (JSON, code AST, text-based) routed by content type, combined with reversible compression that lets LLMs retrieve original data if needed via tool calls. It optimizes for provider-specific quirks like Claude's 5-minute prefix caching window, and has saved users 200 billion tokens ($700k value) with typical 20-30% savings. The project has grown to 1,900+ GitHub stars and 30+ contributors in four months.

To use Headroom, install it locally (`pip install headroom`) and wrap your LLM calls—either as a proxy (`headroom wrap claude`), integrated into LangChain/Agno pipelines, or via MCP server. It works for coding agents, voice agents, document analysis, and video processing with no data leaving your laptop and opt-in telemetry only tracking token counts. If you use Claude Code at work behind corporate proxies, Headroom is integrating with LiteLLM. The project is open-source on GitHub where you can test it, contribute, or submit pull requests to extend it for your specific use case or domain.

## Transcript

[00:00:00] Hi everyone.
[00:00:01] Thank you so much for
[00:00:03] coming over and listening to my topic
[00:00:06] today. I'm Tejas. I am going to present
[00:00:10] an open source project that I personally
[00:00:11] worked on. It's called Headroom. And
[00:00:15] it's my first time in Minneapolis. So I
[00:00:18] would like to take this opportunity to
[00:00:19] thank the Linux Foundation for inviting
[00:00:22] me here
[00:00:24] as well as all of you who have traveled
[00:00:25] from different parts of the world. It's
[00:00:28] great to see the power of open source.
[00:00:31] It's great to see that even if even when
[00:00:33] we are seeing AI churn and produce code
[00:00:37] at each breath we still value the
[00:00:40] foundations and the ethos of open
[00:00:42] source. So thank you for that. With that
[00:00:45] in mind, I'll get started.
[00:00:47] So Headroom is this project that started
[00:00:50] around 4 months ago. And the idea was
[00:00:53] very simple. I use a lot of cloud code
[00:00:56] and there's no shame in admitting that.
[00:00:59] I use a lot of it. I ran out of tokens
[00:01:03] every day.
[00:01:04] I used to pull my hair that when will
[00:01:06] the clock reset and can I now start
[00:01:09] using more tokens?
[00:01:10] That is where I decided, you know what?
[00:01:12] I have no idea where the tokens are
[00:01:14] going. So let me try to cut open and see
[00:01:18] where tokens are being spent. And can I
[00:01:21] give myself some extra Headroom when it
[00:01:24] comes to tokens? So that was where the
[00:01:26] project started. Um
[00:01:29] Who am I? I'm Tejas. In California, I go
[00:01:33] by Tejas. And I work at Netflix as a
[00:01:37] senior engineer. My day job is building
[00:01:41] the data storage that makes
[00:01:43] recommendations possible. So when you
[00:01:45] click on Netflix, when you like
[00:01:47] something, when you don't like
[00:01:48] something, when you watch something,
[00:01:50] when you skip something, I capture all
[00:01:52] of that data. I store it in a way that
[00:01:54] makes it easy for recommendation models
[00:01:57] to recommend you the latest movies or
[00:01:59] shows based on that.
[00:02:00] But that's my day job.
[00:02:02] Headroom is what I do after I do
[00:02:04] everything at Netflix. And um Headroom
[00:02:07] essentially started off with just me uh
[00:02:11] trying to solve my own problem for cloud
[00:02:13] code.
[00:02:14] And as you can imagine, Python gets most
[00:02:16] of the work done when you're working for
[00:02:18] yourself. So um I started uh Headroom
[00:02:21] with Python
[00:02:22] uh for just cloud code. But it found
[00:02:25] some resonance with the community and
[00:02:28] people started extending it left, right,
[00:02:30] and center.
[00:02:31] And I was very excited. I was like,
[00:02:32] "Yay! It's It has open cloud
[00:02:34] integration. It has
[00:02:35] uh you know, Codex integration."
[00:02:37] And then I realized they make it so hard
[00:02:40] for you to integrate with different
[00:02:42] providers. So Headroom has now
[00:02:45] grown from just its Python base to now
[00:02:48] trying to implement a Rust
[00:02:49] implementation.
[00:02:51] In the In just 4 months since it has
[00:02:53] been open source, we are at 1,900 GitHub
[00:02:55] stars. Thanks to the community. We have
[00:02:57] 30-plus contributors from across the
[00:02:59] world. Um and my background being in
[00:03:01] data infrastructure and storage helped
[00:03:04] me uh build some of the core pieces of
[00:03:06] Headroom that I'll try to cover in this
[00:03:07] session.
[00:03:10] Let's first talk about the problem that
[00:03:12] exists everywhere nowadays. Uh just with
[00:03:15] a show of hands, how many of you use
[00:03:17] cloud code?
[00:03:20] How many of you use Codex?
[00:03:22] The same bunch, I guess, like me. How
[00:03:24] many of you use anything that's out
[00:03:26] there that can save you tokens?
[00:03:28] All right then. So uh great. Thank you.
[00:03:32] So the token um when I started looking
[00:03:34] at you know, where my money is being
[00:03:36] spent, um I realized that um
[00:03:39] in my [clears throat] cloud code
[00:03:40] sessions, like in one of the sessions I
[00:03:42] was asking, you know, my CPU usage uh
[00:03:45] went high in one particular session and
[00:03:48] that crashed my laptop. So can you find
[00:03:51] from the logs, you know, where that
[00:03:53] happened? And I realized that there was
[00:03:55] a tool called made to read the log
[00:03:57] files. The entire log file was pulled
[00:04:00] into the context window.
[00:04:02] That is wasteful. Because 90% of it is
[00:04:05] waste and garbage that I don't care
[00:04:07] about.
[00:04:08] And then I realized, you know, if it is
[00:04:10] happening with one log file, this can
[00:04:12] extend to other pieces. Let's say a
[00:04:15] database. You're making a call to a
[00:04:17] database to get some information. The
[00:04:20] structure of the data that is returned
[00:04:21] is JSON. And let's say you get multiple
[00:04:24] entries.
[00:04:25] 80% of them are waste. You just care
[00:04:27] about the 20% that really answer the
[00:04:30] user's query.
[00:04:32] Most of the literature on token
[00:04:34] compression has been focused on user
[00:04:37] prompt compression. So, if I use very
[00:04:40] flowery language, it'll try to condense
[00:04:43] my prompt into something that's
[00:04:45] semantically similar. And it calls it
[00:04:47] token compression. But I realized that
[00:04:49] 90% of my coding workflow involves
[00:04:52] anything but the user prompt. There are
[00:04:54] local reads that are happening to code
[00:04:56] files. There are external tool calls.
[00:04:59] There are
[00:05:00] like web pages that are being read.
[00:05:02] There are archive papers that are being
[00:05:03] read. And I realized that one size fits
[00:05:06] all will not work here. So, that is
[00:05:08] where I started digging into where
[00:05:10] tokens are being spent. And as you can
[00:05:11] see here,
[00:05:13] uh most of the agent's token budget is
[00:05:16] really noise.
[00:05:20] And um I looked around. I looked at, you
[00:05:22] know, what have other people done to
[00:05:24] solve this problem? Some of you may be
[00:05:25] familiar with some of these tools, but
[00:05:27] if not, these are great tools to get to
[00:05:29] know.
[00:05:30] The first one is these providers, like
[00:05:33] OpenAI and Claude, provide you prefix
[00:05:36] caching and compaction. In simple words,
[00:05:39] when you run out of enough of your
[00:05:41] context window, they will summarize or
[00:05:44] they will compact.
[00:05:45] It is extremely lossy in
[00:05:48] As you can imagine, um um and the other
[00:05:50] thing is they have restricted the entire
[00:05:53] knowledge that you've captured in your
[00:05:55] context window to a flat wall of text.
[00:05:59] Because when you compact something,
[00:06:01] you're just representing it in a
[00:06:02] markdown file. That's a lot of
[00:06:04] information loss, if you think about it.
[00:06:07] And that's what providers natively
[00:06:09] provide. The other thing is
[00:06:11] uh how many of you are familiar with KV
[00:06:13] cache?
[00:06:15] Okay, a lot of you. But, um
[00:06:18] when you whenever you talk to Claude or
[00:06:22] you use a coding agent, you think that
[00:06:24] you're saying something, it's responding
[00:06:26] with something. You're saying something
[00:06:27] else, it's responding with something
[00:06:28] else. It's actually not you saying a new
[00:06:30] sentence. It's everything that you've
[00:06:32] said till now and it has responded till
[00:06:34] now, all going again in the call.
[00:06:37] So, it's a contiguous appended array of
[00:06:41] all your historical messages that goes
[00:06:43] again to the LLM.
[00:06:46] And now you can think about it, every
[00:06:47] time you just say a hi after everything
[00:06:49] you've said till now, it's everything
[00:06:51] that you've said till now plus that hi
[00:06:53] that goes to an LLM.
[00:06:55] As you can imagine, 99% of it is things
[00:06:57] that you've already sent. So, what the
[00:06:59] providers do is they have this concept
[00:07:01] of prefix caching.
[00:07:03] They say that if you've sent us all of
[00:07:05] this data before and you're sending it
[00:07:08] again to us, we will charge you just 10%
[00:07:11] of the cost.
[00:07:13] And we'll cache that information. But,
[00:07:15] even if you change a little bit within
[00:07:17] that entire window,
[00:07:20] it is not a hit. It's not a cache hit.
[00:07:22] So, we will penalize you for the entire
[00:07:24] window. So, these are nuances that every
[00:07:27] provider sort of hides in their
[00:07:29] documentation, um and that's what they
[00:07:31] expose for you to take benefit of.
[00:07:34] There are other projects like RTK. Has
[00:07:36] anybody used RTK?
[00:07:38] Oh, nice.
[00:07:39] Uh RTK is uh a token killer in some
[00:07:42] ways. In simple words, let's say you're
[00:07:45] using cloud code and you say, "You know
[00:07:47] what? My GitHub PR failed. Can you go
[00:07:50] investigate what's the failure and fix
[00:07:51] it?"
[00:07:52] It will issue a lot of GitHub CLIs.
[00:07:55] Now, the CLIs that it issues by default
[00:07:58] are not really compressed outputs. So,
[00:08:02] many of the CLIs have {dash} {dash}
[00:08:04] compress as an option, which compresses
[00:08:07] what you see on your screen and it's not
[00:08:09] verbose.
[00:08:10] So, RTK is this smart tool that looks at
[00:08:12] all the different CLIs that your cloud
[00:08:15] code or codex can call and tries to
[00:08:17] compress them at at the point at which
[00:08:19] you're making the call. Lean CTX is lean
[00:08:22] context. It's another variant of it. And
[00:08:24] then there are some commercial companies
[00:08:26] like compressor and token company.
[00:08:28] These are Y Combinator funded companies
[00:08:30] and what they expose is an API in the
[00:08:32] cloud. You call compress, you give it a
[00:08:35] payload, and it gives you a compressed
[00:08:37] output back.
[00:08:39] Because all of these providers have
[00:08:40] different nuances of the hardness, it is
[00:08:44] impossible to integrate these into your
[00:08:46] daily workflows. So, that is where
[00:08:48] headroom was uh started, where I wanted
[00:08:52] the same experience as all these
[00:08:54] combined
[00:08:55] with the idea that it should work on
[00:08:58] your laptop as a proxy.
[00:09:00] Very simple pip install, it should just
[00:09:02] work out of the box. Um and that is how
[00:09:05] it differentiates.
[00:09:06] And the other aspect of it, which I'll
[00:09:08] get into later, is it is reversible
[00:09:10] compression.
[00:09:11] Um now, how can compression be
[00:09:13] reversible?
[00:09:14] Uh you may ask. And it's it's a very uh
[00:09:17] it's it's sort of a marketing term here
[00:09:19] because uh it's really the fact that you
[00:09:22] compress something, but you inject
[00:09:24] information to the LLM saying that if
[00:09:26] you need more, here is a tool call you
[00:09:28] can do.
[00:09:29] So, if the LLM wants to get the original
[00:09:31] context back because you compressed too
[00:09:33] aggressively, it can can make a tool
[00:09:35] call and fetch that.
[00:09:37] That is how it is reversible.
[00:09:40] Um
[00:09:41] So, in essence, it's a local compression
[00:09:44] layer between the agent and the model,
[00:09:48] and it shrinks everything in between.
[00:09:50] Whether it's your tool calls, whether
[00:09:52] it's your uh file reads, uh whether it's
[00:09:56] it's some glob or grep data, whether
[00:09:58] depending on the type of tool call or
[00:10:00] also. Uh it has six compressors that
[00:10:03] we'll try to get to for deploy modes,
[00:10:05] and no data leaves your box. So, it runs
[00:10:07] on your laptop.
[00:10:13] So, here is at a very high level. Sorry
[00:10:14] for the size of the text here.
[00:10:17] Uh a lot of this information is already
[00:10:19] present in um in the GitHub repo. Um and
[00:10:23] also, just a caveat, these slides were
[00:10:25] made using Claude AI {slash} design. So,
[00:10:28] if you've not tried it, it's a fantastic
[00:10:30] tool. Put your GitHub repo there and say
[00:10:32] I need I need slides to be made.
[00:10:34] Maybe you can put headroom in front of
[00:10:35] it and it'll save some tokens. Uh
[00:10:38] but uh it has three stages here. Uh and
[00:10:42] the stages are
[00:10:44] I I'll explain I'll try to explain it in
[00:10:45] simple words. The first is cache
[00:10:47] aligner.
[00:10:48] What does that mean?
[00:10:49] L- Just like I explained, if you have
[00:10:51] everything packed and cached, your
[00:10:54] provider will only charge you 10%.
[00:10:57] But if you change even a single thing in
[00:11:00] that previous huge array,
[00:11:03] then you get a cache miss.
[00:11:05] Now, what could be things that you
[00:11:06] change?
[00:11:07] If your system prompt, which you
[00:11:10] probably don't have control over,
[00:11:11] contains a date field or contains some
[00:11:14] UUID that changes per session,
[00:11:17] you've effectively you're effectively
[00:11:19] getting a cache miss every single time.
[00:11:22] That will blow up your costs. So, what
[00:11:24] cache aligner does is it looks at your
[00:11:26] system prompt, your tools, and it tries
[00:11:29] to extract fields that are dynamic in
[00:11:32] nature,
[00:11:33] take it out from there and put it
[00:11:34] towards the end. So that you still get
[00:11:36] cash hit for a majority part of your
[00:11:39] session.
[00:11:40] The second one is content router.
[00:11:42] So once you've done all of that, you
[00:11:44] have a you have payload that you want to
[00:11:46] send to the LLM.
[00:11:48] If you try to apply the same logic of
[00:11:50] compression, it doesn't work. I tried
[00:11:53] that. That was the simplest model I
[00:11:54] built. It just did not work. I realized
[00:11:56] that you need different types of
[00:11:58] compressors per type of data.
[00:12:00] A lot of coding agents look at files
[00:12:03] that are already code. So code has this
[00:12:05] natural structure of uh and you can use
[00:12:08] AST parsing for code. So we use
[00:12:11] AST-based compressors for coding uh for
[00:12:13] code files. And we use JSON compressors
[00:12:17] for JSON data. We use a DOM compressor
[00:12:20] for all the DOMs and other things that
[00:12:22] you get from web pages.
[00:12:24] Similarly, you can extend and build many
[00:12:26] more compressors here.
[00:12:27] Um I'll I'll try to go over some of them
[00:12:30] in the next few slides. But once you're
[00:12:32] done with these compressors, you then
[00:12:35] try to fit them together in the context.
[00:12:37] This is where knowledge of different
[00:12:39] hardnesses comes into play. For example,
[00:12:43] in Claude, uh
[00:12:44] and I'll give you this example because I
[00:12:45] got burnt by that.
[00:12:47] Uh
[00:12:48] how many of you know prefix cash
[00:12:50] settings in Claude?
[00:12:52] Perfect. Nobody knows it. Awesome. So by
[00:12:56] default, Claude has a prefix cash
[00:12:58] setting of 5 minutes. What does that
[00:13:01] mean? It means that while you're
[00:13:02] interacting with your session, and if
[00:13:04] you're within 5-minute boundary of
[00:13:06] continuous interaction, it'll give you
[00:13:08] the nice sweet deal of 10% of the
[00:13:10] pricing. But as soon as you switch over
[00:13:13] to the 6th minute,
[00:13:14] it'll charge you for the entire huge
[00:13:18] array of tokens.
[00:13:19] What's interesting is that this 5-minute
[00:13:21] is also not in your control technically.
[00:13:24] Because if Claude decides that it has to
[00:13:26] fork off a sub-agent to perform your
[00:13:28] task.
[00:13:29] The sub-agent has its own prefix cache.
[00:13:32] So, by the time the sub-agent comes
[00:13:34] back, you've already exhausted your 5
[00:13:36] minutes. Uh and this is a neat trick
[00:13:38] that I've personally experienced they
[00:13:40] play quite a lot where they'll even for
[00:13:42] a simple thing they'll just create a
[00:13:43] sub-agent, try to make it more than 5
[00:13:46] minutes so that I I pay a lot.
[00:13:48] There's another setting that they
[00:13:49] expose, but it's hidden in their
[00:13:51] documentation.
[00:13:52] It is a 1-hour TTL.
[00:13:54] Not a 5-minute TTL.
[00:13:56] But the catch is you pay two times the
[00:13:59] cost of for your rights
[00:14:02] to get 90% savings for your reads.
[00:14:05] So, for every user
[00:14:08] depending on your coding style,
[00:14:10] depending on how often do you come back
[00:14:13] and resume a session, or how interactive
[00:14:15] your sessions are, one choice may be
[00:14:17] better than the other choice. Uh in
[00:14:20] Headroom,
[00:14:21] we're trying to expose that uh I have a
[00:14:23] PR that I have to push now, but it'll
[00:14:25] look at your historical sessions,
[00:14:28] and it'll automatically set that
[00:14:30] environment variable for you so that
[00:14:33] your token savings are more.
[00:14:36] And this was just the nuance of Claude.
[00:14:38] Codex exposes extremely different APIs
[00:14:42] and ways to do this.
[00:14:45] And then you have Gemini,
[00:14:46] which is still trying to figure out
[00:14:49] according to me what it wants to do
[00:14:51] because it's extremely confusing to get
[00:14:53] it to work with all these settings. Um
[00:14:56] Open code allows you to work with
[00:14:58] external models, but some of them do not
[00:15:01] uh you know, play well with some of
[00:15:03] these settings.
[00:15:04] So, we are trying in Headroom to get
[00:15:06] Open code to work properly so that it
[00:15:09] can work uh you know, for multiple
[00:15:11] users.
[00:15:12] Another nuance is
[00:15:14] uh I don't know if you know, but Claude
[00:15:16] has subscription model and API model.
[00:15:19] So, if you subscribe to a $200 plan, you
[00:15:22] can use it for Claude code
[00:15:25] until some point and then you fall back
[00:15:27] to APIs if you want to use it.
[00:15:29] But they go through different paths. So,
[00:15:31] it's
[00:15:33] the short of it is it's extremely
[00:15:34] complex to get it working for all
[00:15:36] combinations that these providers
[00:15:37] expose.
[00:15:39] And finally, we have the CCR. CCR is
[00:15:42] this technique called
[00:15:44] compress cache and retrieve.
[00:15:47] It's the reversibility where if you are
[00:15:49] giving a JSON payload to Claude,
[00:15:52] you will compress it and squash it and
[00:15:55] put a marker there saying that if the
[00:15:57] LLM wants to uncompress it or open this,
[00:16:00] it should make a tool call.
[00:16:01] This way we get compression as well as
[00:16:03] reversibility and CCR is that local
[00:16:05] storage that stores that reversible
[00:16:09] original context so that the LLM can get
[00:16:11] and retrieve that.
[00:16:15] Um
[00:16:16] and there are four ways in which you can
[00:16:18] integrate it.
[00:16:20] If you want to use it in your LangChain,
[00:16:22] Agno, and other pipelines, you can just
[00:16:23] call a compress command with messages.
[00:16:26] The simplest thing that people try to do
[00:16:28] is Headroom wrap Claude or Headroom wrap
[00:16:31] Codex.
[00:16:32] This will work. It'll start up the proxy
[00:16:34] on your local machine and it'll route
[00:16:36] all the calls through it. It also has an
[00:16:38] MCP server that allows it to retrieve
[00:16:41] these tools.
[00:16:44] So, let's try to go under the hood a
[00:16:45] bit. Uh
[00:16:47] there are 11 hooks and in short,
[00:16:51] whenever you're talking to Claude or
[00:16:53] OpenAI, whether you're using coding
[00:16:55] agents or not, there are different hooks
[00:16:57] that are exposed by them. These hooks
[00:16:59] are good interception points if you want
[00:17:01] to build a harness. These hooks tell you
[00:17:04] what to call before the session starts,
[00:17:07] what to call before a tool call or after
[00:17:08] a tool call, and Headroom tries to
[00:17:10] integrate intelligently with all these
[00:17:12] hooks.
[00:17:13] So, it's it's an overview of the hooks.
[00:17:16] Um
[00:17:17] But based on different types of
[00:17:19] compressors, um it will actually show
[00:17:22] you different uh crushers or compressors
[00:17:24] that we use.
[00:17:25] Uh so for JSON, we use smart crusher
[00:17:27] that gives us 83 to 95% savings uh in
[00:17:30] the best case. For source code, we use
[00:17:32] the code compressor and so on and so
[00:17:34] forth. The last part is interesting,
[00:17:37] which is what if I have nothing of all
[00:17:39] these? What do I do? Does it go
[00:17:41] uncompressed? Um Initially, when I
[00:17:43] started Headroom, I used LLM Lingua. How
[00:17:46] many of you are familiar with LLM
[00:17:47] Lingua?
[00:17:48] Okay. So LLM Lingua is an open-source
[00:17:51] project by Microsoft that is only used
[00:17:54] for text compression.
[00:17:55] Um
[00:17:56] It did not give me great performance, so
[00:17:58] I created my own called compress model.
[00:18:01] Uh it's an open-source model. And in
[00:18:03] very simple terms, what it does is it
[00:18:06] looks at your payload and decides,
[00:18:08] should I keep a token or should I remove
[00:18:10] a token? That's it. It's not fancy. It's
[00:18:13] not a summarizer. It's an encoder-only
[00:18:15] model, so it is not generating text.
[00:18:17] It's just uh weighing the different
[00:18:19] tokens and deciding if the presence of a
[00:18:22] token or an absence of a token impacts
[00:18:24] the output or not. And it it gives us
[00:18:26] compression for text.
[00:18:29] Uh
[00:18:30] and this one is the smart crusher
[00:18:32] algorithm.
[00:18:33] Uh this one is a very basic one that
[00:18:35] we've kept in open source, um but it has
[00:18:37] evolved over time. Uh in simple words,
[00:18:40] we look at your JSON payload, we look at
[00:18:42] the user's prompt, we decide which are
[00:18:44] the fields that the user cares about or
[00:18:46] the response cares about, which are the
[00:18:48] outliers,
[00:18:50] what is the standard mean and standard
[00:18:51] deviation across all the different
[00:18:53] fields in the JSON, and we then squash
[00:18:56] the unimportant ones.
[00:18:58] Um It will try to also um
[00:19:01] based on your compression, let's say you
[00:19:05] compressed it too much, and the next
[00:19:07] time the LLM had to fall back and
[00:19:10] retrieve the original or uncompress it.
[00:19:12] We have a learning mechanism that will
[00:19:15] detect that and the next time it will
[00:19:17] compress less. So that you you're
[00:19:19] intelligently learning how much to
[00:19:21] compress the data.
[00:19:24] The code compressor is a simple one. You
[00:19:26] have a lot of code in your files
[00:19:29] uh and a lot of it could be stripped
[00:19:31] away. Uh so generally, if you have an
[00:19:35] LSP, uh it's your code will not be read
[00:19:38] directly. Uh so cursor, for example,
[00:19:41] will not do a grep over your code if you
[00:19:43] try to ask it a question. But Claude
[00:19:45] will. Um and
[00:19:48] what this does is it uses the structured
[00:19:51] um
[00:19:52] nature of code to compress it
[00:19:53] intelligently. There is support for
[00:19:55] different languages um at the bottom.
[00:19:59] And the next one is compress base. Uh so
[00:20:03] like I said, this is an encoder-only
[00:20:05] model. That means it only looks at text
[00:20:07] and it tries to give them a weight on
[00:20:10] every token in the text. Um and we've
[00:20:13] trained it on agentic traces. LLM
[00:20:16] Lingua, the original model the by that
[00:20:19] Microsoft had, was trained on meeting
[00:20:21] summaries.
[00:20:22] But meeting summaries are not a good
[00:20:24] representative of what I do with my
[00:20:25] coding uh agents. So I uh trained it on
[00:20:28] coding agents' data. It's not the best
[00:20:31] model, to be very honest, but that's
[00:20:32] where the opportunity lies to make it
[00:20:34] even better. Um it's open source at the
[00:20:36] moment and we are trying to go for a
[00:20:39] version two
[00:20:40] where we can try to learn more about
[00:20:42] different coding agents and make it
[00:20:44] better.
[00:20:48] So this is uh cache aligner, which I
[00:20:49] kind of briefly explained, but the idea
[00:20:51] was that if you have uh
[00:20:55] like
[00:20:56] if your message in your agents
[00:20:59] uh has date or other dynamic fields, it
[00:21:02] it is almost always a prefix cache miss.
[00:21:05] So you pay a lot of money. And we try to
[00:21:07] move it towards the end.
[00:21:09] Um and this shows the different
[00:21:10] discounts that different providers
[00:21:11] provide uh have. So, Anthropic, if you
[00:21:15] uh specify cash {underscore} control
[00:21:17] tags, which we take care of
[00:21:18] automatically in Headroom, it gives you
[00:21:20] a 90% discount. OpenAI
[00:21:23] doesn't expose any such tag, but it
[00:21:25] gives you a 50% discount. Uh and Google
[00:21:28] uh has cached content which almost
[00:21:31] doesn't work well, but it gives you a
[00:21:33] 75% discount if it works well.
[00:21:37] And uh the next one is um
[00:21:42] So, we actually um this this shows that
[00:21:45] we can retrieve the data from the uh CCR
[00:21:48] system. Um it
[00:21:51] CCR works not just for JSON data. I
[00:21:54] explained it using JSON, but even if you
[00:21:55] use compressed base or code AST or any
[00:21:58] other compressor, CCR allows you to
[00:22:00] fetch it.
[00:22:01] Now, if you think about it, it works on
[00:22:03] your laptop, but it is only it's
[00:22:05] ephemeral, too. We cannot keep having
[00:22:08] the original context stay forever in in
[00:22:10] CCR. So, CCR is backed by a local Redis
[00:22:14] uh and SQLite, and it has a 5-minute
[00:22:16] TTL. So, if you're looking for data that
[00:22:18] is older than 5 minutes, we'll have to
[00:22:20] configure the TTL separately. But it
[00:22:22] comes at the cost of storage.
[00:22:26] So, let me go to a demo.
[00:22:32] Is it starting?
[00:22:34] Yeah, okay.
[00:22:38] If it works. Okay. So, you will not
[00:22:41] probably be able to see, but there's
[00:22:42] Headroom wrapped Claude at the bottom.
[00:22:44] It starts Claude here. Um and I just put
[00:22:47] it put a basic question, you know, um
[00:22:50] how does it work and can you find data?
[00:22:53] You will notice Claude is doing its
[00:22:55] stuff in parallel, but very quickly
[00:22:57] you'll notice that this is working on
[00:22:58] your local machine. Um
[00:23:01] and this is the cost savings and token
[00:23:03] savings you will see. So, you have to go
[00:23:04] to localhost 8787, which is the port.
[00:23:07] You will notice the savings. Uh, you
[00:23:09] will notice the cache prefix hits.
[00:23:12] Um, and this is the same demo that is on
[00:23:14] on the GitHub uh website as well, so you
[00:23:16] can check it out there, too. But, uh
[00:23:18] I have typically uh seen our users save
[00:23:22] 20 to 30% uh it is a function of the
[00:23:25] tool calls that they do.
[00:23:26] Uh, the other thing is we have reached
[00:23:29] 200 billion tokens saved. To put that
[00:23:32] into perspective, that is $700,000
[00:23:36] of money saved for our users. And we
[00:23:40] have telemetry that is opt-in,
[00:23:42] which means 200 billion is the minimum
[00:23:45] that people are willing to share with
[00:23:46] us. There are many people that don't
[00:23:48] want the telemetry to go away, and the
[00:23:49] telemetry is nothing but tokens saved.
[00:23:51] We don't look at any uh data, but uh
[00:23:55] that tells you uh that different
[00:23:57] providers are charging that much money
[00:24:00] for bloat.
[00:24:03] Uh, there's another demo I have,
[00:24:05] uh which is around memory. So, we have a
[00:24:08] mode called memory, and you'll notice
[00:24:10] that there are three tabs here. The
[00:24:11] first two have memory, but the last one
[00:24:13] doesn't. So, if I just say, "You know
[00:24:15] what? I want to remember that I like
[00:24:16] dark mode in one tab," which has memory.
[00:24:19] Uh,
[00:24:20] the other one you can ask, "What do I
[00:24:21] prefer?" and it'll say, "You know what?
[00:24:23] You like dark mode." But, the third one
[00:24:25] is the basic one, which does not
[00:24:27] remember anything. So, uh
[00:24:31] this when I when I built this demo, this
[00:24:33] was an older demo.
[00:24:35] Claude did not have memory.md. Claude
[00:24:37] has since included memory.md, but
[00:24:39] there's a lot of value in this because
[00:24:41] today when you work across agents, you
[00:24:43] know, there are companies that say that
[00:24:45] they uh will, you know, you have a
[00:24:48] cloud-based knowledge graph, where you
[00:24:51] can save information from your Claude
[00:24:53] session, and use it in your Codex
[00:24:55] session.
[00:24:56] This is a very basic one. It uses SQLite
[00:24:59] on your laptop. It stores a simple graph
[00:25:02] of your memory from one coding session,
[00:25:05] let's say cloud code. And then when you
[00:25:07] open up codex, it actually um you know
[00:25:09] bridges between the SQLite database and
[00:25:12] the agent MD or memory MD file. So it
[00:25:14] syncs them and your new agent can also
[00:25:18] use the same memory.
[00:25:19] If you can extend this forward, let's
[00:25:22] say you want to build it as a managed
[00:25:24] offering, you can use learnings from one
[00:25:28] person's agents and pass that memory to
[00:25:31] another person as well.
[00:25:36] So these are some of the numbers that we
[00:25:38] were able to get from our community. Um
[00:25:40] they tried different agentic workloads,
[00:25:43] not just coding agents. So these are
[00:25:45] across agents. Like I have another demo
[00:25:47] which shows you the power of headroom
[00:25:50] even without coding agents. But you'll
[00:25:52] notice that uh different types of
[00:25:55] headroom is great when you have a lot of
[00:25:57] data to process, but you need a very
[00:25:58] small piece of it. And um it's not great
[00:26:01] when everything is important.
[00:26:04] Um all of this will only work if it's
[00:26:07] accurate. If it's not accurate, there's
[00:26:09] no point uh of compressing anything. So
[00:26:11] we tried to uh benchmark it across
[00:26:14] different accuracy frameworks. This is
[00:26:15] still ongoing. The evals are still
[00:26:17] ongoing and there's a great opportunity
[00:26:19] for folks that are interested to
[00:26:21] contribute to it as well, where um we
[00:26:23] tried to measure it versus the baseline.
[00:26:25] And the hope was because we have
[00:26:27] reversibility,
[00:26:28] we should be the same.
[00:26:30] The other interesting part is when you
[00:26:31] compress tokens, you're not saving
[00:26:33] money. You're actually saving latency.
[00:26:35] And you're actually uh saving accuracy.
[00:26:38] Uh one of our users is using headroom in
[00:26:40] their voice uh agent. Their whole idea
[00:26:43] is um let's say I'm using a voice agent
[00:26:45] and I say, "Can you do deep research for
[00:26:48] this product from my competitor?"
[00:26:51] The voice agent calls an LLM because you
[00:26:53] have a text uh you have a
[00:26:55] speech-to-text, text-to-LLM, the LLM
[00:26:58] spits an output, and that output is then
[00:27:00] converted to speech. So, in that middle
[00:27:02] phase, where you're sending data to an
[00:27:04] LLM which has to make tool calls, that's
[00:27:06] where they put headroom, and their whole
[00:27:08] value proposition was latency.
[00:27:11] Because if you use a voice agent today,
[00:27:13] generally, the latency is 300
[00:27:15] milliseconds. Human perceptible latency
[00:27:18] is 200 milliseconds, which means when
[00:27:21] someone is responding within 200
[00:27:22] milliseconds, we feel like it's a human
[00:27:24] that's talking to us. So, their entire
[00:27:26] game is to get that latency down, and
[00:27:28] that's where headroom is helping. And
[00:27:30] when you think about accuracy, as
[00:27:32] context windows grow, I mean, we have
[00:27:35] all seen that the accuracy drops
[00:27:36] significantly. So, by compressing tokens
[00:27:39] and being intelligent about what we put
[00:27:41] into the context window, accuracy is
[00:27:42] also benefited.
[00:27:45] Um so, where is this going? You know, we
[00:27:47] have built something very basic. Uh
[00:27:50] works for coding agents, but like I
[00:27:52] said, we have a compressor that's
[00:27:54] trained on some agentic workloads. We
[00:27:57] are now working to see how we can have
[00:27:59] compressors per domain.
[00:28:01] So, you can look at financial data. It
[00:28:03] has very different characteristics of
[00:28:05] compression. You cannot just remove
[00:28:07] numbers from there or clauses. But,
[00:28:10] medical data is again separate from
[00:28:11] that. Uh the other one is, like I said,
[00:28:14] voice agents are using it.
[00:28:16] Another use case is image and video. One
[00:28:21] of our users goes to factories, they
[00:28:23] wear glasses, and they record what
[00:28:25] someone is doing to different machines.
[00:28:28] And that entire video that is recorded
[00:28:30] is sent to Claude.
[00:28:32] Per video, it charges $3 to upload it.
[00:28:36] And the output of Claude is a set set of
[00:28:38] instructions on how to operate the
[00:28:40] machine.
[00:28:41] They're using headroom,
[00:28:43] an image variant of headroom, which
[00:28:45] chops the image or chops the video into
[00:28:48] pieces and then uses headroom to
[00:28:49] compress tokens and the cost is down to
[00:28:52] $0.2 per upload. Uh, the last part is
[00:28:55] interesting which is um,
[00:28:57] provenance for every token.
[00:28:59] Provenance is this attribute that you
[00:29:03] can
[00:29:04] confirm and say what has gone into a
[00:29:07] context window and from where did you
[00:29:08] get that information? So, because
[00:29:11] headroom is sitting in the middle
[00:29:13] between LLMs and agents, we can actually
[00:29:16] track source of data and that metadata.
[00:29:19] And this cannot live in a foundation
[00:29:21] model because they don't care where your
[00:29:22] data is coming from and you could use
[00:29:24] three different model providers. Even if
[00:29:26] you pass them metadata, you are left to
[00:29:28] the mercy of the provider to keep it
[00:29:30] around. So, companies want to keep this
[00:29:33] metadata
[00:29:34] uh, and this memory in-house. That's
[00:29:37] where we're trying to see how headroom
[00:29:39] um, will work and that new project we
[00:29:42] will open source very soon. It's called
[00:29:43] headlight. Uh, and it'll try to uh,
[00:29:47] it'll try to focus on context provenance
[00:29:49] with a very simple idea that most of the
[00:29:52] observability today, open telemetry,
[00:29:55] open LLM-etry, I am never able to
[00:29:57] pronounce that. Uh,
[00:29:58] is built for humans to consume.
[00:30:01] If you uh, like most of the dashboards
[00:30:03] are for us to consume.
[00:30:05] But a year out from now, agents will
[00:30:07] consume telemetry data.
[00:30:09] So, the telemetry output should be token
[00:30:12] efficient for agents to use. That is the
[00:30:15] genesis of headlight and we are using it
[00:30:17] to track uh, every token that goes into
[00:30:19] headroom.
[00:30:21] And this is the last demo that I have.
[00:30:23] It shows how headroom helps beyond just
[00:30:26] coding agents. Here we are trying to use
[00:30:28] document compression. So, it's a
[00:30:29] financial document, a 10K document, 190
[00:30:32] pages and you will notice that we have
[00:30:35] 34% reduction in tokens
[00:30:38] uh, and we try to measure the accuracy
[00:30:41] asking it a very weird question and it
[00:30:43] still answered it properly. So, it works
[00:30:46] across different types of agents.
[00:30:49] Uh
[00:30:50] instead of you typing the GitHub repo,
[00:30:52] you can please scan this code uh and try
[00:30:55] it,
[00:30:56] break it, send PRs, fix PRs. Thank you
[00:31:00] so much.
[00:31:01] >> [applause]
[00:31:06] >> And we have exactly 10 minutes for
[00:31:08] questions and answers.
[00:31:10] Perfect. It was a concurrent one. Both
[00:31:13] of you did it at the same time.
[00:31:15] I'll go with him first.
[00:31:18] How does
[00:31:20] your token cooperation layer
[00:31:22] distinguish between
[00:31:25] compressible content and
[00:31:27] non-compressible content organization
[00:31:30] metadata
[00:31:31] such as robust access control claims,
[00:31:34] denial rules, and delegated identity
[00:31:37] context?
[00:31:38] Great question. I'll repeat the
[00:31:39] question. How does uh Headroom uh
[00:31:42] differentiate between compressible
[00:31:44] content and non-compressible content? Uh
[00:31:47] like for example, some authorization
[00:31:50] data, some PII, PHI maybe, as well as
[00:31:53] some identifiers. So, Headroom by
[00:31:56] default, uh at least we have a PR out
[00:31:59] that tries to remove PII, PHI, and
[00:32:02] identity data before we try to compress
[00:32:05] anything. So, we do not try to touch it.
[00:32:07] We do not try to compress it.
[00:32:09] Um and we our compress base model is
[00:32:12] trained to not compress those fields.
[00:32:15] So, whenever we see a UUID um and other
[00:32:18] things or like a link, we try to not
[00:32:21] compress it at all. Um the other thing
[00:32:23] is, let's say that we do compress
[00:32:25] something like that. We have
[00:32:26] reversibility to help us because
[00:32:29] uh the MCP like the LLM will make an MCP
[00:32:32] call to retrieve whatever we've
[00:32:34] compressed and we keep that around. So,
[00:32:36] that way we protect ourselves against
[00:32:38] compressing any such identity
[00:32:40] information.
[00:32:41] Thank you. Yes. Um we use Claude Code at
[00:32:44] my work. Will we get in trouble if we
[00:32:46] use
[00:32:48] Uh great question. So, the question is
[00:32:51] if Claude Code is used
[00:32:52] at work,
[00:32:54] will you get into trouble if you use
[00:32:55] Headroom?
[00:32:56] So, a lot of people at work do not
[00:32:59] directly talk to Claude. They have a
[00:33:01] proxy that sits in the middle. It could
[00:33:02] be a light LLM proxy or it could be some
[00:33:04] better
[00:33:05] uh proxy. So, the challenge is how do
[00:33:07] you integrate Headroom with that?
[00:33:09] Because you don't want a proxy and a
[00:33:11] proxy and then, you know, a call to
[00:33:13] Claude. So, we are working to see how we
[00:33:15] can integrate well with light LLM. In
[00:33:17] terms of just the privacy and the
[00:33:19] security, because we do not capture any
[00:33:21] data, it lives on your laptop. We do not
[00:33:25] like there's no data that is shared.
[00:33:27] The even the opt-in telemetry for us is
[00:33:30] the number of tokens that we've saved
[00:33:32] you. That's it. Like we look at we try
[00:33:34] to look at what compressors are used,
[00:33:37] but we do not capture that. We give you
[00:33:39] the ability to run stats and your
[00:33:41] dashboard that shows you, you know, you
[00:33:44] used the code compressor more than the
[00:33:46] JSON compressor,
[00:33:47] all of those statistics. And the reason
[00:33:49] we do that is so that if you find a bug,
[00:33:51] you can tell us and share us share with
[00:33:53] us what you ran into so that it helps us
[00:33:56] debug. But in terms of like Netflix has
[00:33:59] many teams that are using Headroom
[00:34:01] today. So, there is no data leakage of
[00:34:04] any sort.
[00:34:06] Thank you.
[00:34:07] Yes. How does the LLM know when it needs
[00:34:10] to compress something because it doesn't
[00:34:11] have understanding of if it was missing
[00:34:14] anything? Yes, great question. The
[00:34:16] question is how does the LLM know when
[00:34:18] it needs to compress or decompress
[00:34:20] something because it doesn't have any
[00:34:22] understanding of the data.
[00:34:24] And the answer is that's the um
[00:34:27] the way MCP interestingly works is when
[00:34:30] you declare a tool,
[00:34:32] you actually give an explanation of call
[00:34:34] this tool
[00:34:35] whenever blah blah blah blah blah. So,
[00:34:37] when we have headroom retrieve as the
[00:34:40] MCP tool that we register, we say that
[00:34:43] if you're not able to find information
[00:34:45] or if something is compressed out from
[00:34:48] this payload,
[00:34:50] call this MCP tool.
[00:34:52] And in the in the squashed data
[00:34:55] compressed data that we provide to the
[00:34:56] LLM, we also embed an ID with which they
[00:35:00] have to call. So, the LLM is intelligent
[00:35:02] enough that when it comes across
[00:35:03] something like this, it actually makes
[00:35:05] the tool call. And the LLM
[00:35:08] does that and it also bumps up the some
[00:35:11] stats that we have to show us that it
[00:35:13] actually did this retrieve call and that
[00:35:15] we use to compress less next time. We
[00:35:18] tried this with
[00:35:20] GPT-4 Mini or 4 O Mini, which is very
[00:35:23] small, very old model, and it still
[00:35:26] worked pretty well trying to call that
[00:35:28] retrieve tool call with the ID. So,
[00:35:31] that is like a very uh
[00:35:33] that I mean, everything around headroom
[00:35:36] is based on that little thing. Will the
[00:35:38] LLM be smart enough to call that? Um in
[00:35:41] practical usage, we've seen that 99% of
[00:35:43] the times the LLM doesn't call
[00:35:46] because it doesn't need it. It finds its
[00:35:48] answers other way
[00:35:49] on other places. So, hopefully that
[00:35:52] answers your question.
[00:35:53] Any other question?
[00:35:55] Yes. Yeah, my question is
[00:35:58] if you're running multiple models on
[00:36:00] your own device
[00:36:02] and you use something like headroom to
[00:36:04] do compression,
[00:36:05] does that also
[00:36:08] help with like lowering the electricity
[00:36:11] cost in running
[00:36:13] Yeah. a local device?
[00:36:14] Yeah. I'll repeat the question. If you
[00:36:16] have local models and if you're using
[00:36:18] headroom with that, does that help
[00:36:20] energy or electricity costs? And the
[00:36:23] answer is yes, because if you are um
[00:36:26] compressing tokens, you're using less of
[00:36:28] the context window, Uh uh and energy
[00:36:31] cost is uh like it scales with the
[00:36:33] context window usage. Um and also um
[00:36:36] because it's doing local tool calls,
[00:36:38] it's avoiding some tool calls,
[00:36:40] um there is a lot of uh energy savings.
[00:36:42] We don't have statistics on that because
[00:36:44] a lot of our users are people that are
[00:36:46] really burnt by token costs more than
[00:36:48] anything else, and these are Claude Code
[00:36:51] and Codex users and Gemini users.
[00:36:54] I think there was a hand there. Yes. I
[00:36:56] think yours was before that.
[00:37:00] Yes. Uh the question is how do we
[00:37:01] measure accuracy?
[00:37:03] Um
[00:37:04] we've seen that um
[00:37:06] first of all, it's anecdotal.
[00:37:08] Most mostly it's anecdotal uh that you
[00:37:10] know, yeah, it seemed to have done its
[00:37:12] job. Now, how do you know whether it it
[00:37:14] went around in circles to come to an
[00:37:16] answer or did it get it in the first
[00:37:18] shot? For that, there are accuracy
[00:37:20] benchmarks, which is what we tried to
[00:37:22] cover that show us that for um different
[00:37:25] types of coding tasks, uh these
[00:37:27] benchmarks with and without Headroom
[00:37:29] show the same numbers. So, that tells us
[00:37:31] that it did not go around in circles, it
[00:37:33] did not waste time trying to understand
[00:37:35] what tokens are where and which tools to
[00:37:37] call because these benchmark numbers
[00:37:39] also cover how quickly can you converge
[00:37:41] to a goal.
[00:37:42] So, that gives us good signals on
[00:37:44] accuracy. But, eval is a very big field
[00:37:47] and the success of Headroom rests on us
[00:37:50] being able to get that right. So, we are
[00:37:52] a lot of our PRs and issues are around
[00:37:54] how can we make evals better.
[00:37:57] And there's a question there as well.
[00:37:59] Yes. Um so, you mentioned you have like
[00:38:01] several teams at Netflix using this, but
[00:38:04] it's a local first tool, right? And I'm
[00:38:07] wondering how
[00:38:08] um
[00:38:10] like if we're thinking about providing a
[00:38:12] platform to like enable like
[00:38:15] providing agentic workflows to
[00:38:17] developers across organizations, uh
[00:38:20] what kind of changes you would need to
[00:38:22] make to Headroom to provide this as like
[00:38:25] a multi-user, more generally scaled
[00:38:28] Yeah.
[00:38:29] Yeah, the question is Headroom today
[00:38:31] works on a laptop for a user. What does
[00:38:34] it take to scale it to an organization
[00:38:36] and what pieces would change? So, we
[00:38:38] built Headroom as an interface
[00:38:40] implementation mechanism where you can
[00:38:42] plug in different pieces.
[00:38:44] And the things that would change are,
[00:38:46] you know, our memory or our CCR is local
[00:38:48] only. Those things will change because
[00:38:51] they will then sit, let's say if you're
[00:38:53] running on AWS, you will have RDS or
[00:38:56] something that backs them. We've tried
[00:38:58] to use components that are easily
[00:39:00] interchangeable across different cloud
[00:39:01] providers so that you can all you have
[00:39:04] to do is just plug in these different
[00:39:05] providers. The other thing is that
[00:39:08] our learnings and observability today,
[00:39:10] we use open telemetry
[00:39:12] to spit out observability data that we
[00:39:15] don't collect, but you know, an
[00:39:16] organization may want to route it to
[00:39:17] their open telemetry collector,
[00:39:20] Prometheus, LangFuse, LangSmith, all
[00:39:22] these other systems. That's again a
[00:39:24] plugin that's available. So, it in
[00:39:26] principle should be
[00:39:29] like it should be easy to get these
[00:39:31] different pieces slotted in.
[00:39:33] Some of our community members have are
[00:39:34] also working on PII, PHI removal from
[00:39:38] prompts and from tools. So, those become
[00:39:40] again plugins that you can use Nightfall
[00:39:42] AI or Google's DLP providers to remove
[00:39:46] some of these PII information.
[00:39:49] I be I will be able to take one more
[00:39:51] question, so
[00:39:53] uh
[00:39:55] I can meet you after the call. I'll go
[00:39:56] with the lady.
[00:39:58] How are you thinking about addressing
[00:40:00] drift? I mean, I'm assuming that when
[00:40:02] you
[00:40:03] check for accuracy now, that's a
[00:40:05] relatively developed process, etc. But
[00:40:07] obviously the models are always coming
[00:40:09] up with new versions and so will you be
[00:40:11] doing that periodically over time and
[00:40:13] how does that adjust your so
[00:40:15] Yes, Uh the question is how do we uh
[00:40:17] tackle drift? Uh if we uh you know
[00:40:20] evaluate today uh
[00:40:23] do we have a way to measure these
[00:40:25] evaluations? Uh so, we have a weekly job
[00:40:28] that does this today, and that protects
[00:40:31] us against unintended drifts. But, the
[00:40:34] goal is that every uh check-in that we
[00:40:37] do, we want to be able able to evaluate
[00:40:40] uh drift with the base model versus our
[00:40:42] own uh original accuracy measurements.
[00:40:45] Um it's just that uh it's expensive to
[00:40:48] run it every single check-in. So, we try
[00:40:50] to run it at every major version bump or
[00:40:53] minor version bump that we have. Um
[00:40:56] but that is something that we still need
[00:40:58] to think about.
[00:40:59] You know, uh I'll be honest. We don't
[00:41:01] have a good story there.
[00:41:03] Uh so, would help if you know folks can
[00:41:04] bring in their opinions and thoughts
[00:41:06] there.
[00:41:07] But, thank you so much for joining me
[00:41:08] today. I really appreciate your time
[00:41:10] here.
