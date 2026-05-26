---
video_id: iUSdS-6uwr4
title: RTX 5090, Mac Studio, or DGX Spark? I tried all three.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=iUSdS-6uwr4"
watched_date: 2026-05-18
watched_at: "2026-05-18T12:00:00Z"
watch_count: 1
duration_seconds: 1955
source: youtube-history-browser
history_label: May 18
history_order: 162
watched_at_precision: date-from-history-label
watched_percent: 34
estimated_watched_seconds: 665
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

# Summary

The video argues that AI agents are making personal computing relevant again because they need access to your local files, tools, and workflows. Rather than a "cloud bad, local good" stance, the speaker emphasizes that as AI becomes more integrated into personal work, you should intentionally decide which tasks to own locally versus rent from cloud providers. The core insight is that much valuable AI work isn't about frontier model capabilities—it's about context-heavy tasks like searching your notes, reviewing your code, summarizing your meetings, and managing your documents. The video breaks down the complete local AI stack: hardware (Mac unified memory vs. Nvidia CUDA vs. DGX Spark), runtime (Ollama, LM Studio, vLLM), a portfolio of models for different jobs rather than one "best" model, memory systems you control (Obsidian, Postgres, or Open Brain), and interfaces that integrate into your existing tools (editors, terminals, note apps).

For immediate action: Start by identifying your actual workflows—if you write, research, handle sensitive documents, and want privacy, begin with a Mac mini M4 Pro (64GB) or Mac Studio (128GB), then layer in Ollama for the runtime, a small set of models (fast local model, stronger generalist, coding model, embeddings), local Whisper for transcription, and either Obsidian or SQLite for searchable memory. If you need maximum privacy/compliance, invest in a Mac Studio or DGX Spark with Postgres for memory and MCP servers for tool access with audit logging. The key principle: buy hardware for the work you actually do daily, not for benchmarks; build your stack incrementally; and own the runtime layer while renting cloud models only for genuinely frontier tasks.

## Transcript

[00:00:00] The strangest thing about AI right now
[00:00:01] is that it's making the computer on your
[00:00:03] desk important again. For the last 15
[00:00:06] years, the story of personal computing
[00:00:08] was basically the story of the computer
[00:00:09] disappearing. Your files moved into
[00:00:11] someone else's cloud, your apps became
[00:00:13] browser tabs, your storage became a sink
[00:00:15] of some sort, your OS became a launcher
[00:00:18] for other people's infrastructure. And
[00:00:20] for a lot of software, that seemed fine.
[00:00:22] It was convenient. It was maybe the
[00:00:24] right trade at the time. But agents are
[00:00:26] changing the direction of travel for
[00:00:28] compute because a useful agent doesn't
[00:00:30] just answer a question. It wants to
[00:00:32] touch the work. It wants to read the
[00:00:33] file and inspect the folder and run the
[00:00:35] test and edit the spreadsheet and search
[00:00:37] your notes and open the browser and
[00:00:39] remember the decision you made and try
[00:00:40] again when the first attempt fails. So,
[00:00:42] the more useful the agent becomes, the
[00:00:44] more it starts reaching back toward the
[00:00:46] oldest primitives of computing, files
[00:00:48] and processes and permissions and memory
[00:00:51] and local state and execution. That's
[00:00:53] why the personal AI computer matters.
[00:00:56] Now, a quick caveat up front because I
[00:00:57] talk a lot about frontier models on this
[00:00:59] channel and I'm going to keep doing
[00:01:01] that. The best cloud models are
[00:01:02] incredibly useful and one of the most
[00:01:04] important trends is that they're moving
[00:01:06] closer to our personal computers, not
[00:01:07] farther away. So, Codex, Cloud Code, and
[00:01:10] the whole class of coding agents matter
[00:01:12] precisely because a cloud model can now
[00:01:14] interact with your repo, your terminal,
[00:01:16] your files, and your tools on the
[00:01:18] machine right in front of you. So, the
[00:01:19] argument here is not cloud is bad, local
[00:01:22] is good. The argument is that as AI
[00:01:24] reaches deeper into the personal
[00:01:25] computer, the ownership question for you
[00:01:28] gets sharper. If models are going to
[00:01:29] touch your files and remember your work
[00:01:31] and call your tools and sit inside your
[00:01:33] workflows, there is still room, maybe
[00:01:35] more room for a stack that is all yours.
[00:01:37] And that stack matters because some of
[00:01:39] the most valuable AI work is not the
[00:01:41] most difficult work in the abstract.
[00:01:44] It's not the work that takes a cloud
[00:01:45] model at the very edge of the frontier.
[00:01:48] It's the work that is closest to your
[00:01:49] own context, your notes, your meetings,
[00:01:52] your drafts, your unfinished projects,
[00:01:53] your weird folder system. And the
[00:01:55] question for you becomes which parts of
[00:01:58] that should you keep renting and which
[00:02:01] parts should you own, and how do you
[00:02:03] start to intentionally think about that
[00:02:05] as models keep getting better and that
[00:02:08] workflow divide starts to change?
[00:02:10] Because even a few months ago,
[00:02:12] open-source models could not do a lot of
[00:02:16] what I just described at all. And now,
[00:02:18] they still aren't as good as the
[00:02:19] closed-source frontier models and you
[00:02:21] still can't give them as much messy work
[00:02:23] as say ChatGPT 5.5 by any stretch, but
[00:02:26] they're getting a lot better and it's
[00:02:27] worth thinking about at least for some
[00:02:29] of your workflows, especially if you
[00:02:31] value privacy or have highly
[00:02:33] confidential information on your
[00:02:34] computer. So, by the end of this video,
[00:02:36] I want you to have a mental model for
[00:02:37] the whole personal AI stack, not just
[00:02:40] which GPU should I buy, not just which
[00:02:42] model is best this week, but the actual
[00:02:44] stack, the machine, the runtime, the
[00:02:46] models, the memory, the apps, and the
[00:02:48] workflows that make local AI worth
[00:02:50] owning in the first place. Because the
[00:02:52] biggest mistake you can make is buying a
[00:02:54] really fancy computer whose only job is
[00:02:56] to run benchmark prompts or to do your
[00:02:58] emails, which is what so many people do
[00:03:00] with their Mac minis and open claw. The
[00:03:02] best version of a personal computer is a
[00:03:04] lot more compelling than that. It's
[00:03:07] building a durable place where AI can
[00:03:09] attach to the rest of your computing
[00:03:10] life and you still have privacy. There's
[00:03:12] a historical echo here that I think is
[00:03:14] easy to miss. Before the personal
[00:03:16] computer, the dominant model was
[00:03:18] actually time-sharing. You rented
[00:03:19] compute on someone else's mainframe. You
[00:03:22] waited in queues, you worked inside
[00:03:24] rules set by an operator you would never
[00:03:26] meet. The first personal computers did
[00:03:28] not beat that mainframe on raw power.
[00:03:31] They won because they collapsed the
[00:03:33] distance between the person and the
[00:03:34] machine. AI is creating a similar
[00:03:37] opening. Frontier models are still
[00:03:38] better at the hardest tasks and they're
[00:03:40] going to stay better for a while, but
[00:03:42] most personal work is not a moonshot
[00:03:44] benchmark. Most personal work is messy
[00:03:47] and it's repeated. It's not too huge.
[00:03:49] It's private and it's context-heavy.
[00:03:51] It's like, what did we decide here in
[00:03:53] the meeting? Please find this draft.
[00:03:56] Look in this repo and explain why the
[00:03:57] test is failing or can you make a
[00:04:00] follow-up memo or help me do a
[00:04:02] journaling program? All of that work
[00:04:04] benefits from the model being in your
[00:04:06] files, your tools, your memory, and the
[00:04:08] places where you're already doing
[00:04:10] personal computing. When all of that
[00:04:11] gets separated out into the cloud, it
[00:04:13] gets harder for the AI to touch all of
[00:04:15] the files and folders you want that you
[00:04:17] need taken care of on a single computing
[00:04:21] space. And frankly, that's why a lot of
[00:04:24] enterprise workflows involve a lot of
[00:04:26] harnesses that tie a cloud model into a
[00:04:30] local memory file system attached to
[00:04:32] Azure or attached to AWS. They're
[00:04:34] essentially doing the grown-up
[00:04:36] enterprise version of exactly what I'm
[00:04:38] describing here for a company. It's the
[00:04:40] same principles. You want to get the
[00:04:42] model close to the work it needs to do.
[00:04:44] And if you want to go local, the open
[00:04:46] weight ecosystem is moving fast enough
[00:04:48] now that this is no longer a theoretical
[00:04:50] conversation. Meta's practical open
[00:04:52] weight line is no longer just about the
[00:04:54] old Llama 3 story. Llama 4 Scout and
[00:04:56] Llama 4 Maverick have moved that Llama
[00:04:59] lineage into mixture of experts models
[00:05:01] where the important question is no
[00:05:02] longer how big is the model, but how
[00:05:04] much of the model fires for each token.
[00:05:06] Open AI has GPT-OSS-20B
[00:05:09] and GPT-OSS-120B,
[00:05:11] which are open weight reasoning models
[00:05:13] under Apache 2.0. They're not ChatGPT.
[00:05:16] They're not models you call through the
[00:05:17] normal OpenAI API. They're weights you
[00:05:20] run on infrastructure you control. Qwen
[00:05:22] has become one of the most important
[00:05:23] local model families for agents, for
[00:05:25] coding, for multilingual work, and for
[00:05:27] tool use. Google's Gemma 4 pushed
[00:05:29] serious capability down into smaller
[00:05:31] local models under a more permissive
[00:05:33] license. It's designed for open claw.
[00:05:35] Mistral's newer open models fill in both
[00:05:37] large frontier cell deployments and
[00:05:39] efficient local ones. Now, in April 24,
[00:05:41] DeepSeek previewed V4 with Pro and Flash
[00:05:44] variants, which is a good reminder that
[00:05:45] any model list you make today, it starts
[00:05:47] aging right away, right? That's the
[00:05:49] point. The model list is not the durable
[00:05:51] thing. The durable thing is the stack.
[00:05:53] If you build this right, you're not
[00:05:54] buying a single model appliance, you're
[00:05:56] building a local substrate that you can
[00:05:58] evolve over time. New models can drop
[00:06:01] in. New runtimes can replace old ones.
[00:06:03] New memory stores can be added. New
[00:06:04] agents can call the same tools. New
[00:06:06] interfaces can show up without taking
[00:06:08] your knowledge base with them. The
[00:06:09] personal AI computer should not be a
[00:06:11] sealed box that does just one trick. It
[00:06:13] should be a place where the rest of AI
[00:06:15] can connect to the rest of computing.
[00:06:17] So, start with the least glamorous part,
[00:06:19] the hardware. This is where people get
[00:06:20] trapped because they want one universal
[00:06:22] answer. Mac or Nvidia, the CUDA tower or
[00:06:25] the DGX Spark, buy now or wait. There
[00:06:27] isn't only one answer because local AI
[00:06:29] is constrained by memory capacity,
[00:06:31] bandwidth, accelerator support, software
[00:06:34] maturity, cooling, power, noise, and
[00:06:36] that annoying one, what you do every
[00:06:37] day. So, the better question is not what
[00:06:39] is the best AI computer, period. The
[00:06:41] better question is what local workload
[00:06:43] are you trying to own? If you're
[00:06:44] learning the stack, if you're running
[00:06:46] private document search and doing local
[00:06:48] writing and local coding assistance and
[00:06:49] maybe transcribing audio, the boring
[00:06:51] answer is that a recent Mac with enough
[00:06:53] unified memory is enough. A Mac mini
[00:06:55] with M4 Pro and 64 gigs is a great entry
[00:06:58] point. A Mac Studio becomes interesting
[00:07:00] when you want 128 gigs or 256 or even
[00:07:03] more, 512 gigs of unified memory. The
[00:07:06] Mac advantage is not raw tensor
[00:07:08] throughput here. The advantage is
[00:07:10] unified memory and low noise and power
[00:07:12] efficiency and the fact that the machine
[00:07:13] feels like a computer instead of a
[00:07:15] project. Now, this is the CUDA path. An
[00:07:17] RTX 5090 gives you 32 gigs of GDDR7, say
[00:07:21] that five times fast, and excellent
[00:07:23] throughput. Two of them gives you 64
[00:07:25] gigs across cards, but that's not one
[00:07:28] clean 64 gig pool of memory, right? The
[00:07:30] payoff is speed and ecosystem support.
[00:07:32] And so, you're dealing with a cost of
[00:07:34] drivers, of heat, of power, sharding
[00:07:36] maybe, maintenance. So, you have to
[00:07:38] think that through, right? And then
[00:07:40] there's the Nvidia DGX Spark, which is
[00:07:41] the appliance version of the Nvidia
[00:07:43] path. You get a Grace Blackwell chip on
[00:07:45] the desk, you get 128 gigs of coherent
[00:07:48] unified memory, you get Nvidia's
[00:07:50] software stack and a product story
[00:07:51] around local inference and fine-tuning
[00:07:53] instead of just a parts list. That
[00:07:55] doesn't mean it beats every custom rig.
[00:07:57] It means it packages the Nvidia stack in
[00:07:59] a way that may be worth paying for if
[00:08:01] you want a CUDA-native local AI without
[00:08:03] building the tower yourself. AMD's Strix
[00:08:05] Halo systems are kind of the value
[00:08:07] wildcard here, right? The hardware story
[00:08:09] is attractive, the software story is
[00:08:10] still less mature than CUDA and less
[00:08:13] frictionless than Apple silicon. Which
[00:08:15] brings us back to the real buying rule.
[00:08:17] Don't buy for the biggest model you read
[00:08:19] about. Buy the thing you're going to run
[00:08:20] daily. If the work is private writing or
[00:08:23] notes or documents or meetings, you want
[00:08:25] to buy memory and simplicity. If the
[00:08:26] work is coding agents and throughput,
[00:08:28] buy CUDA and just accept the
[00:08:30] maintenance. If the work is long context
[00:08:32] personal memory, buy storage, buy
[00:08:34] unified memory, buy a real database,
[00:08:36] right? If you're just experimenting,
[00:08:38] start with what you own. The box needs a
[00:08:40] job before it arrives, so do that work.
[00:08:43] Once the machine exists, the next
[00:08:45] question is whether the software makes
[00:08:47] it feel like a tool or just a tax on
[00:08:49] your time. And this is where runtime
[00:08:51] really matters, the software that loads
[00:08:53] the weights, that serves the inference,
[00:08:54] that handles quantization, that exposes
[00:08:56] APIs, that manages batching, and that
[00:08:58] decides whether your expensive hardware
[00:09:00] is actually being used well. Most people
[00:09:03] underestimate this layer because it
[00:09:04] isn't as exciting as the model name. But
[00:09:06] runtime is the difference between local
[00:09:08] AI feeling like a normal part of your
[00:09:10] computer and local AI feeling like a
[00:09:12] weekend that you just have never had a
[00:09:14] chance to recover from. The foundation
[00:09:16] underneath a lot of this is a tool
[00:09:18] called llama.cpp. Even if you never call
[00:09:20] it directly, you benefit from it all the
[00:09:22] time if you run your own stack. It
[00:09:24] helped make GGUF, the common local model
[00:09:27] format. It runs across your CPU, across
[00:09:30] Apple Metal, across CUDA, across Vulkan,
[00:09:32] and more. And for most people, the
[00:09:34] runtime on top of that should still be
[00:09:35] Ollama. It's not always the fastest or
[00:09:37] the most configurable, but it gives you
[00:09:39] a clean command-line interface, a local
[00:09:41] server, a simple model registry, and an
[00:09:43] OpenAI-compatible surface that other
[00:09:45] tools can talk to. That makes local
[00:09:47] inference feel normal, especially if
[00:09:49] you're used to cloud models. And just a
[00:09:51] quick note on all of the technical terms
[00:09:53] I'm using, I know that I'm using a bunch
[00:09:55] of very specific terms in this video,
[00:09:58] don't be scared by them. If you want to
[00:10:00] build your own local stack, you really
[00:10:02] can start with a Mac Mini, and I'm going
[00:10:04] to give you a complete teardown across
[00:10:06] multiple degrees of complexity at the
[00:10:08] end of this video to help you understand
[00:10:11] which approach you want to take
[00:10:12] depending on the workloads you're going
[00:10:13] after. So, don't let the technical
[00:10:15] terminology scare you. And in fact, you
[00:10:17] can load the transcript from this video
[00:10:19] into your AI of choice and have it
[00:10:22] explained to you what each of the
[00:10:24] technical terms I'm mentioning mean. So,
[00:10:26] let's keep moving. If you want to go
[00:10:27] with a more sophisticated runtime, LM
[00:10:29] Studio is a polished workbench for
[00:10:31] testing models and quantization. If you
[00:10:33] want to go with something Apple native,
[00:10:35] MLX matters on Apple silicon because
[00:10:37] it's a more native performance path. And
[00:10:39] if you're serving real workloads on
[00:10:40] Nvidia hardware, vLLM is where the
[00:10:43] conversation starts to really up-level,
[00:10:45] right? It handles batching, OpenAI
[00:10:47] compatible serving, and enough
[00:10:48] throughput for a team or an internal
[00:10:50] product. Beyond that, you can tackle SG
[00:10:52] Lang or TensorRT-LLM or an even Nvidia
[00:10:55] and NeMo. Those are all for serious
[00:10:56] deployment tiers. That's where you get
[00:10:57] into latency, structured generation,
[00:10:59] agents, and serving economics that
[00:11:01] enable you to justify the complexity of
[00:11:04] your build because of how much you're
[00:11:06] getting done. But, the practical default
[00:11:07] is simple. Ollama for daily use, LM
[00:11:10] Studio for evaluation, maybe MLX if
[00:11:13] you're tackling the Mac side of things,
[00:11:15] vLLM when serving becomes
[00:11:16] infrastructure, and that deeper Nvidia
[00:11:19] stack when you've committed to CUDA.
[00:11:20] Notice what happened here. We haven't
[00:11:22] picked the model yet. That's
[00:11:23] intentional. If the runtime layer is
[00:11:25] healthy, models become very swappable.
[00:11:28] If the runtime layer is brittle, every
[00:11:30] new model becomes a migration effort.
[00:11:32] It's a lot of pain. Now, the model layer
[00:11:35] is where the yelling in the discourse
[00:11:37] gets loudest and also where it ages out
[00:11:38] the fastest. So, I would not build a
[00:11:41] personal AI computer around a single
[00:11:43] model name. I would build around model
[00:11:46] classes for particular workloads. So,
[00:11:48] for example, you probably want a fast
[00:11:50] local model for cheap calls, a stronger
[00:11:52] local generalist model, a coding model
[00:11:55] if that's what you're into, an embedding
[00:11:56] model for memory, a speech model, maybe
[00:11:58] a vision model, and of course, a
[00:12:00] frontier cloud fallback for the work
[00:12:02] that still deserves it if that's what
[00:12:03] you're willing to do. So, the personal
[00:12:05] AI computer that I'm describing here is
[00:12:07] not necessarily anti-cloud, it's just
[00:12:10] anti-dependence.
[00:12:11] You don't want to be dependent on the
[00:12:12] cloud models. And for general work, the
[00:12:14] local landscape now has real choices.
[00:12:17] Llama 4, Scout, and Maverick are
[00:12:19] important because they show where the
[00:12:20] open ecosystem is headed. They have
[00:12:22] mixture of experts models. It's a
[00:12:24] multimodal approach, longer context,
[00:12:26] more deployment nuance there. GPT-OSS
[00:12:29] matters because OpenAI put permissively
[00:12:31] licensed reasoning models out into the
[00:12:33] self-hosted world. Qwen matters because
[00:12:35] it's become a default family for lots of
[00:12:37] agents, for coding, for multilingual
[00:12:39] work, and for tool use. Gemma matters
[00:12:41] because Google is pushing very capable
[00:12:43] local models down to smaller sizes
[00:12:45] designed specifically for open claw type
[00:12:47] applications. Mistral matters because it
[00:12:49] keeps offering serious open weight
[00:12:51] alternatives with a strong enterprise
[00:12:53] and deployment story. But, the most
[00:12:54] important takeaway here is this. There
[00:12:56] is no one right model that wins at all
[00:12:59] the use cases. Part of what you're doing
[00:13:01] when you set up a strong personal
[00:13:03] computer for AI is you're asking
[00:13:05] yourself, "What is the mixture of models
[00:13:07] I need?" And that's what I'm looking to
[00:13:08] give you is the sense of choices and the
[00:13:10] rationale you'd use to make those
[00:13:12] choices. For example, for coding, you
[00:13:14] don't want one model doing everything.
[00:13:16] You want a small autocomplete model, a
[00:13:18] repo-aware editor model, and a deeper
[00:13:21] reasoning model for architectural
[00:13:22] changes, for debugging, for migrations.
[00:13:25] If you're doing docs, you probably want
[00:13:27] to think about an embedding model and
[00:13:28] how you handle embeddings so that you
[00:13:30] can retrieve semantic memory correctly.
[00:13:34] Qwen embedding models are good here.
[00:13:35] There's other options that as well.
[00:13:37] Whatever fits your stack. Embeddings are
[00:13:39] very cheap to run. They're easy to
[00:13:40] cache, and they're central to privacy if
[00:13:42] you value a private set of core
[00:13:45] documents that don't go to the cloud.
[00:13:47] You know, if your documents end up
[00:13:49] leaving your machine just to become
[00:13:50] vectors, you've missed one of the
[00:13:52] easiest wins in local AI. If we're
[00:13:54] talking about speech, Whisper is still a
[00:13:56] reference point. Local transcription is
[00:13:58] fast and private, and if you own the
[00:13:59] hardware, it's very economical. For
[00:14:01] vision, local models are finally good
[00:14:03] enough for document screenshots, for
[00:14:05] chart extraction, not for all visual
[00:14:07] reasoning, but for a lot of personal
[00:14:09] media search and work, and that belongs
[00:14:11] in your stack now. Ultimately, your
[00:14:12] model portfolio should feel less like
[00:14:14] picking your favorite chatbot and a lot
[00:14:17] more like building a tool cabinet. A
[00:14:18] small model for fast loops, bigger
[00:14:20] models for hard local work, a
[00:14:22] specialized models like I've been
[00:14:23] describing for various aspects of code
[00:14:26] editing, code production, media, and
[00:14:28] then a cloud model for the frontier
[00:14:29] cases. The principle should be you own
[00:14:32] the runtime, and you only rent the cloud
[00:14:34] model in exceptional cases. Now, if
[00:14:36] you're wondering, "Do I have to do all
[00:14:38] of this? This feels like a lot of work.
[00:14:40] Nate, can I just use a cloud model?" The
[00:14:42] answer is absolutely you can. And for
[00:14:44] many people, that's going to be the
[00:14:46] answer. But, I know a lot of folks in my
[00:14:47] audience who value the privacy that
[00:14:50] comes with their own local stack, and I
[00:14:51] want you to have the tools to be able to
[00:14:54] build that stack in a way that aligns
[00:14:56] with your workflows because a lot of the
[00:14:58] videos that I see are really useful for
[00:15:01] building your own personal computer, but
[00:15:02] they're not useful for helping you
[00:15:04] decide what stack you should be on,
[00:15:06] which is arguably the more important
[00:15:08] thing to do. Figure out the workflows
[00:15:09] you need to go after, and then build the
[00:15:12] stack that fits. And that's really my
[00:15:13] focus here, and I'm giving you
[00:15:14] essentially lots of choices that you can
[00:15:16] dig into. And if you want a full punch
[00:15:18] list, yes, it's absolutely going to be
[00:15:20] on the Substack. Getting back to our
[00:15:21] stack, the layer that actually turns
[00:15:23] this from a toy into infrastructure is
[00:15:25] memory. And that's the part that I think
[00:15:27] people tend to underbuild. The model is
[00:15:29] stateless, but your life isn't
[00:15:31] stateless. Your life remember You you
[00:15:32] remember things. You go through your
[00:15:34] life with durable memory. Every useful
[00:15:36] personal AI system also needs durable
[00:15:38] memory outside the model. It needs notes
[00:15:39] and documents and transcripts and email
[00:15:41] and tasks and calendar events and code
[00:15:43] decisions and research and preferences
[00:15:45] and a sense of long-running project
[00:15:47] state. And so, your most important
[00:15:48] architectural decision is that this
[00:15:50] memory should belong to you, not the
[00:15:52] model provider. And that's why I built
[00:15:54] Open Brain. Open Brain is an
[00:15:56] open-source, GitHub available memory
[00:15:59] system that allows you to build a
[00:16:01] SQL-driven database approach to memory
[00:16:04] with an easy MCP server attached, but
[00:16:06] that also recently we've added an
[00:16:08] embedding management system for. So, you
[00:16:11] can do almost an Andrej Karpathy-like
[00:16:13] hybrid memory system where you have the
[00:16:15] Karpathy approach to memory involving
[00:16:17] lots of different interlinked and
[00:16:19] interweaved embeddings that help you
[00:16:21] make sense of multiple documents at
[00:16:22] once, and also a SQL approach that lets
[00:16:25] you store and categorize facts in a neat
[00:16:28] way. And so, that's something to think
[00:16:29] about. You obviously don't need to use
[00:16:30] Open Brain to solve for this, but I
[00:16:32] built it because I think that memory is
[00:16:34] very high leverage, and it's important
[00:16:35] to manage your own memory in the age of
[00:16:37] AI so you're not beholden to a
[00:16:39] particular cloud provider. After all, in
[00:16:41] the cloud-first model, the AI service
[00:16:43] really wants to own your memory, and you
[00:16:45] visit your memory. Whereas in the
[00:16:46] personal compute model that I'm
[00:16:48] describing here, you own the memory, and
[00:16:50] the models come to you if you choose to
[00:16:52] rent them. And that inversion is the
[00:16:53] heart of the whole thing. The source
[00:16:55] material for your life, your memory,
[00:16:57] should live somewhere durable. If you
[00:16:58] don't want to go with Open Brain, you
[00:17:00] know what? You can go with Obsidian.
[00:17:01] It's a It's a default if you have a lot
[00:17:03] of docs. It won't work as well for lots
[00:17:05] of quantitative storage and facts. But,
[00:17:07] if most of your work is in docs, it will
[00:17:09] store it in markdown in folders you can
[00:17:11] control, and you can absolutely use
[00:17:13] Obsidian. I know a lot of people who do.
[00:17:14] Plain markdown plus Git is like the
[00:17:16] boring immortal version. For structured
[00:17:18] work, you might go with Postgres, which
[00:17:20] might be better than your notes. That's
[00:17:21] why I built Open Brain that way. But,
[00:17:23] the key property for memory overall is
[00:17:24] very simple. Your knowledge keeps
[00:17:26] existing even if the AI app disappears.
[00:17:29] Then, you need retrieval. For many
[00:17:30] serious systems, Postgres with pgvector
[00:17:33] is the grown-up default because it lets
[00:17:34] you keep relational data and metadata
[00:17:36] and permissions and vector search all in
[00:17:38] one place. SQLite with SQLite vec is the
[00:17:41] lightweight personal version. It's just
[00:17:43] a single file. It's easy to back up.
[00:17:44] It's easy to understand. Now, the part
[00:17:46] almost everybody gets wrong is on the
[00:17:48] pipeline side. Good retrieval is not
[00:17:50] throw every document into chunks and
[00:17:53] hope. By the way, if you're wondering,
[00:17:54] "Wow, this sounds complicated," Open
[00:17:56] Brain does take care of a lot of the
[00:17:57] chunking strategy, a lot of the
[00:17:59] retrieval strategy, a lot of the input
[00:18:01] and classification strategy for you. And
[00:18:03] so, that's an option for you if you if
[00:18:05] you'd like it. But, the point here is
[00:18:06] that different kinds of data need
[00:18:08] different memory handling, and you have
[00:18:10] to think about that in advance. Like,
[00:18:11] PDFs need different handling than
[00:18:13] markdown. Meeting transcripts need
[00:18:15] speakers. They need timestamps. Code
[00:18:17] needs symbol-aware indexing. Notes need
[00:18:19] links preserved. You need to know what
[00:18:20] changed, what was indexed, and what
[00:18:22] should be regenerated when a better
[00:18:24] embedding model comes along, which is
[00:18:25] why it's so important to have your raw
[00:18:27] data and your embeddings in your
[00:18:28] database separately. Because then you
[00:18:30] can always rebuild it if something goes
[00:18:32] wrong. Most of the time when something
[00:18:33] goes wrong with a memory system, it's
[00:18:35] not the model itself, it's the pipeline
[00:18:38] that's the issue. And you have to think
[00:18:39] about how the pipeline affected your
[00:18:41] chunking strategy, for example, or how
[00:18:43] it affected your ability to handle
[00:18:45] retrieval, etc. And then there's the
[00:18:47] access there where MCP becomes
[00:18:48] interesting. Open Brain has MCP. An MCP
[00:18:51] server in front of your database can let
[00:18:52] Claude or ChatGPT or any custom tool you
[00:18:54] want query that memory. That is the
[00:18:57] right direction. But, don't assume just
[00:18:59] because you have an MCP in front of
[00:19:01] something, you can treat it like magic.
[00:19:02] MCP servers are just executable tool
[00:19:04] surfaces. They still need permissions
[00:19:06] and logging and secrets management and
[00:19:08] and boundaries to work well. Your
[00:19:10] personal AI computer should not just be
[00:19:12] a pile of local tools that any model can
[00:19:14] call for anything. It should be an own
[00:19:16] system that you set up intentionally.
[00:19:18] That's the difference between useful
[00:19:20] local intelligence and just giving the
[00:19:21] model the keys to the vehicle and hoping
[00:19:23] it all goes well. The next failure mode
[00:19:25] is interface. A great runtime with no
[00:19:27] comfortable surface is just a setup that
[00:19:29] you're going to stop using after a week
[00:19:31] cuz you're not in it. And that's why
[00:19:32] local AI can't just live in the
[00:19:34] terminal. The model has to live where
[00:19:36] your work lives. You can use something
[00:19:38] like Open Web UI for chat. Anything LLM
[00:19:41] is worth considering when you really,
[00:19:42] really want to focus on retrieval
[00:19:44] heavily. LM Studio is good for direct
[00:19:46] model work. You just want to pick the
[00:19:49] tools for the interface that feel like
[00:19:51] they align with your current workflow.
[00:19:53] That's the principle. For for editors,
[00:19:55] continue is one of the obvious bridges
[00:19:56] because it can point at OpenAI
[00:19:58] compatible endpoints. Aider remains very
[00:20:00] good for terminal-based code editing,
[00:20:02] and there's a whole class of coding
[00:20:03] agents that are converging on a very
[00:20:05] similar pattern that you'll want to work
[00:20:06] with, right? Model plus tools plus repo
[00:20:09] plus context in a in a planning loop.
[00:20:10] And that's really how it works, whether
[00:20:12] you're using a cloud model or a local
[00:20:14] model, if you're into coding. Now, for
[00:20:15] launchers and command surfaces, the
[00:20:17] things that get the models going, the
[00:20:19] boring tools matter more than you might
[00:20:20] think. Stuff like Raycast and Alfred and
[00:20:23] shortcuts and shell commands, small menu
[00:20:25] bar apps, an LLM command line interface.
[00:20:28] A personal AI computer basically
[00:20:29] shouldn't require you to open a chatbot
[00:20:31] just to talk to the LLM. You should be
[00:20:33] able to call it from your editor, from
[00:20:34] your notes, from your browser, from your
[00:20:36] finder. You get it, right? Anywhere
[00:20:38] you're in the computer, you should just
[00:20:39] be able to speak or to type, and you
[00:20:41] should be able to get the LLM. Voice is
[00:20:42] underrated here because hosted voice
[00:20:44] assistants trained everyone to expect
[00:20:47] disappointment over the last few years.
[00:20:48] But, local voice can be different now.
[00:20:50] Whisper handles transcription, a local
[00:20:52] or hybrid model handles intent and clean
[00:20:54] up and summarization and routing. And
[00:20:55] the interface principle then is not just
[00:20:57] install a bunch of AI apps, it's just
[00:20:59] speak what you're looking for, and it
[00:21:01] sticks what you're asking into a single
[00:21:03] stack underneath. The principle is many
[00:21:05] surfaces, one stack underneath. So, your
[00:21:08] editor, your note app, your browser,
[00:21:09] your launcher, your terminal, and your
[00:21:11] voice recorder, they those don't have
[00:21:13] separate memory layers, right? They
[00:21:14] should call into the same local runtime
[00:21:17] in the same memory layer, and they'll
[00:21:19] actually work well. This is the part
[00:21:21] that a lot of products aren't going to
[00:21:22] give you because their business model
[00:21:23] depends on owning the memory underneath
[00:21:25] the input channel. And so, you
[00:21:27] accumulate that memory inside a
[00:21:29] particular cloud model for meeting
[00:21:31] transcripts, right? And then you can't
[00:21:32] get it out again. The last layer that
[00:21:34] you should think about is where you want
[00:21:37] to put your workflows. And this is where
[00:21:39] you stop asking, "Can I run the model
[00:21:41] locally?" and you start asking, "What is
[00:21:44] the workflow I now control beyond the
[00:21:46] model itself?" If you're thinking about
[00:21:48] managing workflows, personal RAG or a
[00:21:51] personal memory system like I described
[00:21:52] earlier with Open Brain, that is still a
[00:21:54] clean first win. You can index your
[00:21:56] notes and your drafts and your PDFs, you
[00:21:58] can create a database. The value there
[00:22:00] is not generic search, it's that you
[00:22:02] actually develop a long-term
[00:22:04] institutional memory of your work over
[00:22:06] time. A frontier model might have read
[00:22:08] the public internet. It's not read the
[00:22:10] past few years of your meeting notes,
[00:22:11] and it shouldn't need to. Private coding
[00:22:13] is another obvious loop, right? A local
[00:22:15] coding assistant with repo access can do
[00:22:17] a lot more than auto complete these
[00:22:19] days, right? do refactoring, it can do
[00:22:21] test generation, it can do drafting. It
[00:22:23] may not be up to what frontier models
[00:22:24] can do on the code side, but it can do a
[00:22:26] lot. And you can keep frontier models
[00:22:28] for the hardest tasks. Again, I keep
[00:22:30] emphasizing this is not about a hard
[00:22:31] rule, it's just about choosing where you
[00:22:33] want to fight your battles. And local
[00:22:34] models now are good enough for a lot of
[00:22:36] the agentic loop to work by default on
[00:22:38] many of the simpler software problems
[00:22:40] out there. Meeting capture is another
[00:22:42] one. You have local Whisper plus a local
[00:22:44] summarizer, it means you can record and
[00:22:46] transcribe and summarize and extract
[00:22:48] decisions and create tasks and store
[00:22:50] that result in your memory layer. No
[00:22:51] audio ever leaves the machine, no per
[00:22:53] hour transcription bill. You can run
[00:22:55] that on every call for a year, and
[00:22:57] you're going to start to see things over
[00:22:58] time, right? Your decisions become
[00:23:00] searchable, your commitment that you
[00:23:01] make becomes something you can retrieve
[00:23:03] and look at, your recurring
[00:23:04] conversations become part of effectively
[00:23:06] a private institutional memory that you
[00:23:08] own. Long-running agents also start to
[00:23:10] make more economic sense when inference
[00:23:12] is local because cloud APIs they they're
[00:23:14] expensive, right? You might
[00:23:15] psychologically not want to run as many
[00:23:18] tokens because you don't want to pay for
[00:23:19] it. But, if you're just limited by the
[00:23:21] cost of electricity, you're going to be
[00:23:22] more inclined to set up really
[00:23:24] long-running agentic loops, which is
[00:23:25] exactly what we see with the open claw
[00:23:27] phenomenon where people set up local
[00:23:29] computers and they just have their
[00:23:30] agents always on. Research and synthesis
[00:23:32] are probably going to stay at least
[00:23:34] partially hybrid for a long time because
[00:23:36] local models can retrieve and organize
[00:23:38] and summarize and prep context, but
[00:23:40] frontier models are needed for hard
[00:23:41] synthesis type problem types, hard
[00:23:43] research in the same way that they're
[00:23:45] needed for very difficult coding
[00:23:47] problems. So, at this point, I think the
[00:23:49] buying decision becomes a lot clearer if
[00:23:51] you're going back to the stack you need.
[00:23:53] Imagine three people. One is a
[00:23:55] local-first knowledge worker. They
[00:23:56] write, they research, they code a little
[00:23:58] bit, they handle sensitive documents,
[00:24:00] and and maybe you want private AI
[00:24:01] without turning the home office into a
[00:24:03] complicated server room. That person
[00:24:05] should probably start with a Mac mini M4
[00:24:07] Pro with 64 gigs or maybe a Mac Studio
[00:24:10] M4 Max with 128 gigs if the budget
[00:24:12] allows. They'll use Ollama, LM Studio,
[00:24:14] maybe MLX, probably local embeddings or
[00:24:17] local memory system of some sort,
[00:24:19] Whisper, Open Web UI, Continue, and a
[00:24:21] very simple retrieval stack that maybe
[00:24:23] has an SQLite and Obsidian mixed in or
[00:24:25] something that has the markdown and
[00:24:26] something that has the database on the
[00:24:28] Open Brain side. It's not too
[00:24:29] complicated. I know that sounds like a
[00:24:31] lot of names, but you really can load
[00:24:33] this into an LLM, and it will literally
[00:24:35] give you a punch list of what you need
[00:24:37] to get it in what order you need to set
[00:24:38] it up. And I have a whole write-up on
[00:24:40] Substack, too. And that person can still
[00:24:41] keep one frontier subscription or API
[00:24:43] account for the hard work. And it gives
[00:24:45] you a sane default if that's you, right?
[00:24:47] You get privacy, you get speed, you get
[00:24:49] ownership, you get enough capability for
[00:24:51] daily use without pretending the cloud
[00:24:52] is irrelevant. Another person, you maybe
[00:24:54] you're a all local maximalist, right?
[00:24:56] You're not hearing this desire for
[00:24:58] cloud, you're like, "No, no, no, I've
[00:24:59] got to have privacy." So, you want
[00:25:00] privacy, you want compliance, you want
[00:25:02] sovereignty, you want to run your core
[00:25:04] work without a dependency. At that
[00:25:05] point, you're looking at a high memory
[00:25:07] Mac Studio or a DGX Spark or a similar
[00:25:09] serious workstation. You have to have
[00:25:11] something that gives you full control,
[00:25:13] right? You might even look at a mini
[00:25:14] Nvidia stack. The memory layer would be
[00:25:16] something like Postgres with PG Vector.
[00:25:18] Tools would probably sit behind MCP with
[00:25:20] permissions and audit logs. And I've got
[00:25:22] to be honest, this is not the cheapest
[00:25:24] build, right? But, it's the cleanest
[00:25:25] expression of the local thesis, right?
[00:25:27] Local modes, local memory, local tools,
[00:25:29] local workflows. And then, you can just
[00:25:31] go to town, right? Last but not least,
[00:25:33] there's the local-first builder. A
[00:25:35] developer or a small team building
[00:25:37] software, running agents, testing
[00:25:39] products, or just trying to reduce cloud
[00:25:41] inference spend. That person probably
[00:25:43] cares more about CUDA throughput, about
[00:25:45] serving, about evals, and about
[00:25:46] repeatability. So, they might get dual
[00:25:48] RTX 5090s, workstation GPUs, DGX Spark,
[00:25:51] or maybe a mixed local-cloud GPU setup.
[00:25:54] The LLM for serving, Ollama for
[00:25:56] prototyping, TensorRT LLM or NeMo when
[00:25:58] deployment efficiency matters. The
[00:26:00] principles are simple here. Local models
[00:26:02] absorb development, they take care of
[00:26:04] private data, they provide opportunity
[00:26:06] to handle batch jobs and high volume
[00:26:07] inner loops, and those economics start
[00:26:09] to add up because you're handling it
[00:26:11] locally. Local inference does not have
[00:26:12] to replace every single hosted call to
[00:26:14] add value. It only needs to absorb
[00:26:16] enough of the repetitive, private, high
[00:26:18] volume work that you feel like you get
[00:26:20] your money's back on that purchase. And
[00:26:21] that's the key distinction. Ultimately,
[00:26:23] the personal AI computer is not a purity
[00:26:25] test, it's just a routing system. Some
[00:26:27] work stays local because it's private
[00:26:29] and it's cheap and it's repetitive or
[00:26:31] context-heavy. Some work is going to go
[00:26:32] to the cloud because it's rare and it's
[00:26:34] hard and it's high value or maybe it
[00:26:36] needs the frontier. The power comes from
[00:26:38] you deciding instead of just defaulting
[00:26:39] to what the cloud providers want. The
[00:26:41] long-term reason to build this stack is
[00:26:43] not cost savings, although the cost
[00:26:45] savings can be real. The deeper reason
[00:26:47] is compounding your knowledge over time,
[00:26:49] and that's why I talked about memory so
[00:26:50] much. Every project, note, meeting,
[00:26:53] decision, correction, preference, and
[00:26:54] workflow can become part of a memory
[00:26:56] system you own. Over time, the personal
[00:26:58] AI computer becomes less like a chatbot
[00:27:00] and more like an operating layer over
[00:27:02] your work. The model might change out
[00:27:03] every few months, the memory can get
[00:27:05] better every year, and that's why
[00:27:06] extensibility matters a lot, but
[00:27:08] fundamentally, the source data that
[00:27:10] you're storing on this system, the
[00:27:12] markdown notes, the PDFs, the
[00:27:13] transcript, the code repositories, the
[00:27:15] media files, they stay, they're a source
[00:27:17] of truth, and you can just continue to
[00:27:19] expand and improve your data set that
[00:27:21] you build off of that over time, whether
[00:27:22] you're building with embeddings or
[00:27:24] whether you're building a SQL database.
[00:27:25] However you decide to solve that
[00:27:27] problem, and I've got other videos on
[00:27:29] that, you can absolutely
[00:27:31] build a memory system that evolves over
[00:27:34] time and that gets better over time,
[00:27:36] that preserves your institutional
[00:27:38] memory, that preserves the workflows
[00:27:40] that you have. And the mission is simple
[00:27:42] here, right? Your goal would if you care
[00:27:44] about this is to not let a proprietary
[00:27:47] AI app capture you and become the only
[00:27:49] place your knowledge exists. I talk a
[00:27:51] lot about the idea that there are
[00:27:52] multiple good models out there. Well, we
[00:27:54] need an underlying compute layer that
[00:27:56] enables us to take advantage of that.
[00:27:58] So, build open interfaces, right? OpenAI
[00:28:00] compatible local endpoints let many apps
[00:28:02] talk to your models, you're not locked
[00:28:04] into local only, you can talk to cloud
[00:28:06] if you want. Model context protocol lets
[00:28:08] multiple clients talk to your tools and
[00:28:10] your memory. Postgres or SQLite keep
[00:28:12] retrieval from becoming trapped inside
[00:28:14] one product, it's a lot of the basis for
[00:28:15] Open Brain. Plain files and Git keep the
[00:28:17] whole thing very inspectable. Treat your
[00:28:19] tools as you use them on this system
[00:28:21] like permissions instead of just
[00:28:23] conveniences. That's a that's an
[00:28:24] important principle as you're thinking
[00:28:25] about the design. The more useful an
[00:28:27] agent becomes, the more you have to
[00:28:30] think about this because agents with
[00:28:31] access to shell permissions, access to
[00:28:34] payments, agents with access to serious
[00:28:36] parts of your computing stack are agents
[00:28:38] that need serious permissions to operate
[00:28:40] responsibly. So, you need to think ahead
[00:28:43] and ask yourself, "If I'm operating
[00:28:45] multiple agents on this machine, what is
[00:28:47] a responsible access pattern here?" A
[00:28:48] writing agent does not need shell
[00:28:50] access. A coding agent doesn't need my
[00:28:52] bank statements. A meeting summarizer
[00:28:54] doesn't need permission to delete files.
[00:28:56] Think about how you control the attack
[00:28:59] surface of your agents if you're going
[00:29:01] to do this, right? Otherwise, you'll
[00:29:02] have extensibility without boundaries,
[00:29:04] and you'll just be in trouble. You want
[00:29:06] to be in a position where you are
[00:29:07] managing the scope your agents have so
[00:29:10] that they are not irresponsibly
[00:29:12] permitted to do anything on the machine.
[00:29:14] Now, I've been emphasizing memory as the
[00:29:16] heart of this system, to give you a few
[00:29:17] tips there. Memory needs to be
[00:29:19] cumulative, but also auditable. The
[00:29:21] system should be able to learn from your
[00:29:22] work, and you should also be able to
[00:29:24] inspect what it stored, delete what's
[00:29:26] wrong, trace where a fact came from, and
[00:29:28] rebuild indexes when better embeddings
[00:29:30] arrive. Assume in general that you're
[00:29:32] going to persist a hybrid experience
[00:29:33] where you call the cloud and call these
[00:29:35] larger models sometimes. They'll
[00:29:36] continue to get better. In most cases,
[00:29:38] you're going to want that unless you are
[00:29:40] a very hardcore local compute-only
[00:29:42] person, in which case I've got a stack
[00:29:44] for you, and I I talked about it. But,
[00:29:46] for most of us, the point of a personal
[00:29:47] AI computer is not to reject every cloud
[00:29:50] model forever. The point is actually to
[00:29:52] positively own the substrate that cloud
[00:29:54] models or any other model can plug into
[00:29:56] it well. Cuz a frontier model can still
[00:29:58] be called for rare and hard and
[00:29:59] high-value work whenever you want. But
[00:30:01] this kind of setup allows cloud AI to be
[00:30:03] a visitor to the system, not dominant
[00:30:06] across the system as a whole. And by the
[00:30:07] way, if you're like, "No, no, no, I just
[00:30:09] want to use cloud models, Nate." That's
[00:30:10] fantastic. I talk about cloud models all
[00:30:12] the time. There's lots of future videos
[00:30:15] and past videos that are all about
[00:30:17] setting up cloud models and cloud agents
[00:30:19] on your system. And I'll keep making
[00:30:20] those cuz so many people need that
[00:30:22] fluency as well. Now, once you have your
[00:30:23] personal stack, the rest of the
[00:30:25] computing world starts to look a little
[00:30:26] different. You're through the mirror.
[00:30:28] You ask yourself, "Why does this app
[00:30:29] need to upload my draft to its server?
[00:30:31] Why does this agent want a token for my
[00:30:33] entire account? Why does this assistant
[00:30:35] lose its memory the moment I close the
[00:30:37] tab? Or why am I paying per interaction
[00:30:39] for a model that can handle this routine
[00:30:41] job on the box already sitting on my
[00:30:43] desk?" And those questions, they tend to
[00:30:46] only be visible once you actually go
[00:30:48] through that looking glass, you build a
[00:30:49] personal stack, and you have an
[00:30:51] alternative. That's what makes the
[00:30:52] questions that I described just now feel
[00:30:54] tangible and real. And this is where I
[00:30:56] think people get the local AI argument a
[00:30:58] little bit wrong. I hear a lot about
[00:31:00] beating the cloud. It's not about
[00:31:01] beating the cloud. The cloud frontier is
[00:31:03] going to keep mattering. It may matter
[00:31:05] more, not less, as the hardest models
[00:31:06] become more expensive to train and
[00:31:08] serve. But that actually strengthens the
[00:31:09] case for owning the rest of the stack.
[00:31:11] It lets you use the frontier model as
[00:31:13] the specialist. You don't make it your
[00:31:15] memory, your file system, your workflow
[00:31:17] engine, your operating layer. You hire
[00:31:18] it for the job it's best at, and you
[00:31:20] stop renting it the rest of your life.
[00:31:22] Your personal AI computer is then not
[00:31:24] really a nostalgia play. It's not a
[00:31:26] hobbyist retreat from the internet. It's
[00:31:27] a bet that intelligence becomes more
[00:31:29] useful when it's closer to work, when
[00:31:31] it's closer to the files, closer to the
[00:31:33] tools, closer to your memory, closer to
[00:31:35] the person, you, that's asking it to
[00:31:37] act. The machine on your desk has a job
[00:31:41] to do. That's the whole point of this
[00:31:42] video. It doesn't have to be the
[00:31:44] smartest computer in the world. It can
[00:31:45] just be your computer. It can just be
[00:31:48] your AI. And that's why I made this
[00:31:50] video. I want you to feel empowered to
[00:31:52] make an intelligent choice and say,
[00:31:54] "Actually, I do want that world of the
[00:31:56] prosumer. I do want an all-local world.
[00:31:58] I want a local-first developer model and
[00:32:00] developer machine stack." If that's you,
[00:32:02] you can head on over to the Substack.
[00:32:03] I've got a full punch list and build
[00:32:05] recommendations. I've also got a nice
[00:32:07] reminder and guide to Open Brains so you
[00:32:10] can dig into the memory side because
[00:32:11] there are lots of people that are just
[00:32:12] using Open Brain for the memory piece,
[00:32:14] and they're not going after the full
[00:32:15] hardware stack, and that's another way
[00:32:17] to put your toes in the water on owning
[00:32:18] part of your compute stack. Whatever
[00:32:20] your choice is, I just want you to feel
[00:32:22] comfortable and feel like you own your
[00:32:23] destiny, and like the AI agents and the
[00:32:26] LLMs out there that are cloud-provided
[00:32:27] don't get to run the long-term
[00:32:30] parameters of intelligence in your life.
[00:32:32] It's up to you, and it should be up to
[00:32:33] you.
[00:32:34] I'll see you next time.
