---
video_id: PhJnZnQuuT0
title: Same 128GB but cheaper
channel: Alex Ziskind
url: "https://www.youtube.com/watch?v=PhJnZnQuuT0"
watched_date: 2026-05-21
watched_at: "2026-05-21T12:00:00Z"
watch_count: 1
duration_seconds: 1030
source: youtube-history-browser
history_label: Thursday
history_order: 108
watched_at_precision: date-from-history-label
watched_percent: 53
estimated_watched_seconds: 546
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video compares three machines with similar memory bandwidth: the Nvidia Jetson Thor (128GB RAM, $1000+ cheaper), the DJX Spark (128GB RAM, highest performance), and the Apple M4 Pro Mac Mini (64GB RAM). Testing with LLMs like Mistral 3 and Llama 3.3 70B revealed distinct performance profiles: the Mac Mini maxed out its memory on large models; the Thor showed variable GPU usage patterns with moderate power consumption (~90W under load); and the Spark delivered the fastest prompt processing speeds (2x-3x faster than Thor on certain models) but consumed significantly more power (~140-150W). The key finding is that performance depends heavily on model architecture—sparse models (mixture of experts) like GPT OSS 12B showed larger gaps between Thor and Spark, while dense models showed narrower differences.

For practical decision-making: choose the Thor if you need deterministic latency for robotics/automotive with cost constraints and can accept moderate speed for dense model inference; choose the Spark if you're serving multiple users or need consistent burst performance and can absorb the 2-3x power cost; avoid the Mac Mini for production if you need to run models larger than 40GB. Test your specific workload before committing, as model type dramatically affects which hardware wins—the Thor's cheaper option only makes sense if your use case aligns with its deterministic-latency design rather than multi-user throughput.

## Transcript

[00:00:00] The Jetson Thor is Nvidia's new
[00:00:02] developer kit, and the DJX Spark is for
[00:00:06] everybody, but what's not often talked
[00:00:08] about is the Thor has 128 gigs of RAM,
[00:00:10] just like the Spark. That's a lot of
[00:00:12] RAM, and it's more than $1,000 cheaper
[00:00:15] than the Spark. So, why don't we just
[00:00:17] buy the Thor instead of the Spark? Well,
[00:00:19] you could. I'm going to run some tests
[00:00:21] right now to see what it's capable of
[00:00:22] and talk about a couple of differences
[00:00:24] between those two machines and also
[00:00:26] Apple Silicon. The reason I picked these
[00:00:28] three is because the M4 Pro, the Thor
[00:00:31] platform, and the Spark all have 273 GB
[00:00:35] per second memory bandwidth. And I
[00:00:37] mentioned before many times that memory
[00:00:39] bandwidth is really important for
[00:00:40] machine learning, but that doesn't tell
[00:00:42] the whole story. By the way, Nvidia sent
[00:00:44] me this Thor to do some testing. And
[00:00:46] they're also giving away the Jetson Orin
[00:00:49] Nano Super signed by Jensen One. Rules
[00:00:53] for the raffle are in the description.
[00:00:54] The other two machines I bought. So
[00:00:56] these days I'm always flipping between
[00:00:57] models. GPD for research, cloud for
[00:01:00] coding, nanobanana for image generation,
[00:01:02] VO cling, and runway for video, six
[00:01:04] tabs, six bills, and counting. Enter
[00:01:07] chat LLM teams. One dashboard houses
[00:01:10] every top LLM and route pickics to write
[00:01:13] one. GPT Mini for ultra fast answers,
[00:01:15] Claude Sonnet for coding, Gemini Pro for
[00:01:18] massive context. They recently added
[00:01:20] Gemini 3 and GPT 5.1 the moment they
[00:01:22] dropped. Create professional
[00:01:24] presentations with graphs, charts, and
[00:01:26] deep research detailed content. Need
[00:01:28] human sounding copy? Humanize rewrites
[00:01:30] text to defeat AI detectors. Need
[00:01:32] visuals? Pick frontier or open-source
[00:01:35] models. Nano banana, midjourney, flux
[00:01:37] for images, magnific upscaling, plus VO,
[00:01:40] WAN, and Sora for video, all builtin.
[00:01:43] You also get Abaca's AI deep agent to
[00:01:45] pretty much do anything. Build full
[00:01:47] stack apps, websites, reports with just
[00:01:49] text prompts and deploy them on the
[00:01:51] spot. They have Abacus AI Desktop, which
[00:01:53] is the brand new coding editor and
[00:01:55] assistant that lets you vibe code and
[00:01:57] build productionready apps. And the
[00:01:59] kicker, it's just $10 a month, less than
[00:02:02] one premium model. Head over to
[00:02:03] chatlm.abacus.ai
[00:02:05] or click the link below to level up with
[00:02:07] Chat LLM teams. When it comes to these
[00:02:10] kinds of machines, an important thing to
[00:02:12] consider is the amount of power they
[00:02:14] use. Here I just have the terminal open.
[00:02:16] Envy Top running in the Thor and Spark
[00:02:18] and activity monitor running on the Mac.
[00:02:20] And here is the power usage. Mac Mini M4
[00:02:23] Pro is using about 8 watts. The Thor is
[00:02:26] using about 31 watts and the Spark is
[00:02:28] using about 44 watts. That's just to
[00:02:30] kick things off. I'm going to run a
[00:02:31] couple LM here and then do some
[00:02:33] benchmarking so you get an idea of how
[00:02:34] these perform. There's a brand new model
[00:02:36] called Minist. Haven't tested that on
[00:02:38] the channel before. So, let's start with
[00:02:40] that one. And I'm using Olama, which is
[00:02:42] a really dead simple way to get started.
[00:02:44] I've created tutorials on the channel
[00:02:46] before on how to start with that and how
[00:02:47] to set it up. There's really not much to
[00:02:49] it. Palama Run Ministral 3 and I'm going
[00:02:53] to give it the verbose flag. Now,
[00:02:54] different models behave very
[00:02:56] differently. That's why we have to test
[00:02:59] as many models as possible. I wish there
[00:03:01] was a way to keep track of all the
[00:03:02] different models, all the different
[00:03:04] versions of them on all the different
[00:03:05] hardware that I'm testing, but it's kind
[00:03:08] of hard to do that. I'm working on
[00:03:09] something. Design a scalable web
[00:03:11] application architecture for an
[00:03:12] e-commerce platform and so on and so on.
[00:03:14] This is one of my medium prompts. It's
[00:03:16] uh it gives a really nice long output.
[00:03:19] really detailed architecture. I have
[00:03:21] different length prompts that I use.
[00:03:23] They're all in my GitHub. I'll link to
[00:03:24] it down below. All right, let's go. And
[00:03:26] there it goes.
[00:03:29] That is really interesting that the Mac
[00:03:32] and the Spark are printing out pretty
[00:03:33] much the same exact result. They're a
[00:03:36] little bit different. Now, this is going
[00:03:38] to be a very, very long result. So,
[00:03:40] while it's happening, take a look at
[00:03:42] what's going on with uh the Spark here.
[00:03:44] There is the GPU usage. We're going at
[00:03:46] about 95% usage. And over here on the
[00:03:49] Thor about 94 to 96% usage as well. But
[00:03:53] the characteristic of the of the line is
[00:03:57] very different on these two. The Spark
[00:03:59] is very even. So it's constantly using
[00:04:01] 95% of that GPU. But the Thor is
[00:04:05] bouncing around a little bit, which
[00:04:07] tells me that just based on the graph, I
[00:04:09] don't know what's going on on the inside
[00:04:10] there, but it's telling me that things
[00:04:12] are loading and unloading, loading and
[00:04:14] unloading um at a rapid pace. So, it may
[00:04:17] not be as efficient as the Spark, for
[00:04:20] example, at this particular task, but
[00:04:22] we'll see what happens when the result
[00:04:23] comes. Oh, Spark is done and so is the
[00:04:25] Mac Mini. You can see that usage is
[00:04:28] pretty even there as well. I didn't
[00:04:29] expect it to finish so soon because I
[00:04:32] wanted to get the power usage, but I'll
[00:04:34] get that in a moment. Here are first
[00:04:36] results. 39 tokens per second for the
[00:04:39] generation. This is token generation.
[00:04:41] We'll get to prompt processing in a bit
[00:04:43] and prefill. We have 30.82 82 tokens per
[00:04:46] second on the Thor and 34.97
[00:04:50] tokens per second on the Spark. So,
[00:04:53] they're all kind of close to each other.
[00:04:55] Uh, well, I guess the Mac Mini won this
[00:04:58] round and the Thor lost this round with
[00:05:00] the Spark coming in right in the middle
[00:05:02] there. But the token generation speed is
[00:05:03] not the only story here. Look at the
[00:05:05] prompt eval rate. That's the prompt
[00:05:08] processing. This is the part of the
[00:05:09] process that's not related to memory
[00:05:11] bandwidth. This is pure computation. And
[00:05:14] in pure computation, the Mac Mini loses
[00:05:17] 353 tokens per second here. The Thor has
[00:05:20] 1,036 tokens per second here. Three
[00:05:23] times faster. And the Spark 2,46
[00:05:27] tokens per second. So we have very
[00:05:29] different characteristics on all three
[00:05:31] of these machines. But the two Nvidia
[00:05:32] machines both have the latest Blackwell
[00:05:35] chips, which is where that prefill gets
[00:05:37] processed. So we have the latest Tensor
[00:05:39] cores in there and the latest CUDA
[00:05:41] cores. By the way, the Thor has 25% more
[00:05:44] than the previous generation, which was
[00:05:45] the AGX Orin, but the Spark definitely
[00:05:48] beats it out, at least in the prompt
[00:05:51] prefill stage in the calculation,
[00:05:52] because it has a lot more tensor cores
[00:05:55] and CUDA cores. But that's not the only
[00:05:57] difference. All three of these are
[00:05:59] ARMbased systems, but just because these
[00:06:01] two are Blackwell system doesn't mean
[00:06:03] that they have the same exact chip. The
[00:06:05] Thor has a 4 nanometer process and
[00:06:07] that's the CPU part of the chip. Whereas
[00:06:10] the Spark has a three nanometer process
[00:06:12] chip for the CPU and that's going to
[00:06:14] directly affect that CPU toGPU
[00:06:16] communication. So the Spark may be more
[00:06:18] capable of feeding the GPU part, the
[00:06:21] Blackwell part than the Thor. But the
[00:06:23] Thor is not exactly designed for that
[00:06:27] particular scenario as we'll see in a
[00:06:28] bit. Now this model is a brand new model
[00:06:31] and this is a mixture of experts model.
[00:06:33] So it's not using all of its parameters
[00:06:36] that are available at the same time.
[00:06:38] It's only using a subset of the
[00:06:40] parameters. It's called a sparse model.
[00:06:42] If there's a dense model, it has very
[00:06:44] different characteristics. First, let's
[00:06:46] run this again because I want to take a
[00:06:48] look at how much power is being used
[00:06:50] while all three of these are working. So
[00:06:52] there they are. The GPU is plugging
[00:06:55] away, doing its thing on all three of
[00:06:57] these. Let's take a look at what's
[00:06:58] happening with the power. So, we're
[00:07:00] about 70 watts on the Mac Mini. We're
[00:07:03] about 90 watts here. Almost 90 watts on
[00:07:05] the Thor. And we're at 141 watts on the
[00:07:10] Spark, which is quite a bit higher.
[00:07:12] Almost two times higher power usage on
[00:07:14] the Spark. And that's all being used by
[00:07:16] that compute, that really powerful fast
[00:07:18] compute that's on there with more cores.
[00:07:20] Mech Mini is done. We got 38.95 tokens
[00:07:23] per second there. 32.92 tokens on the
[00:07:27] Spark. just a tiny bit slower, but the
[00:07:29] prompt eval rate went up here to 2,817
[00:07:34] tokens per second, which is ridiculous.
[00:07:36] And we got 28 tokens per second on the
[00:07:39] Thor. A little bit slower again, but the
[00:07:42] prompt eval rate 1,090. So, really good
[00:07:45] there. Let's take a look at a dense
[00:07:47] model, which means it's going to be
[00:07:49] using all the parameters. So, this is
[00:07:51] going to be quite a bit slower, but
[00:07:52] dense models are really good for
[00:07:54] clustering, and I'm going to go into
[00:07:55] more of that in later videos. For
[00:07:58] example, with Sparks over here and Apple
[00:08:01] silicon machines. Stay tuned for that.
[00:08:03] I'm going to run Llama 3.3 70 billion
[00:08:05] parameter model, which is a really
[00:08:08] chunky model. It's over 40 GB on disk,
[00:08:11] which means it's going to require all
[00:08:14] that memory and then some if you want to
[00:08:16] include some context. So, this little
[00:08:18] Mac Mini is almost all but filled up
[00:08:21] with its 64 GB of memory there. These
[00:08:24] machines have plenty more to go with 128
[00:08:27] each. All right, here we go. Same
[00:08:28] prompt. And we got a bigger model now.
[00:08:30] Boom. Boom. Boom.
[00:08:33] Look how much slower this thing is.
[00:08:36] 70 billion parameters. It's a lot of
[00:08:38] parameters. I mean, you got to give it
[00:08:41] to these little guys. They're they're
[00:08:42] small. Look how small they are. It's a
[00:08:44] 70 billion parameter model. Think about
[00:08:46] that. This is going to take a while. All
[00:08:47] right, let's take a look at what's
[00:08:48] happening here. Um, we've got the GPU
[00:08:51] usage is pretty steady on the Spark,
[00:08:53] 96%. We got a similar kind of thing
[00:08:56] going on the Thor where the GPU usage is
[00:08:58] going up and down by a little bit,
[00:09:00] jumping up and down there. And the Mac
[00:09:02] Mini has pretty steady GPU usage, but
[00:09:05] interestingly, it's higher than it was
[00:09:07] when we were doing the Minist 3 model,
[00:09:10] just by a little bit. So, it's using
[00:09:11] more of the GPU. Memory used on the Mac
[00:09:13] Mini, 56.87 87 GB out of the 64, but the
[00:09:17] memory pressure is nice and clean there.
[00:09:20] No orange or red, so we're good. Power
[00:09:22] usage is a bit different here. We got
[00:09:24] more power usage on the Mac Mini, almost
[00:09:27] 80. We got more usage on the Thor,
[00:09:29] almost 100 there, and about the same or
[00:09:32] just a tiny bit more on the Spark with
[00:09:35] 153 watts. Watts is the unit we're
[00:09:39] talking about here, folks. I know
[00:09:41] somebody was going to leave that
[00:09:42] comment. 53. What? What?
[00:09:46] [Laughter]
[00:09:48] Oh, I'm hearing some sounds.
[00:09:51] Who is it? Who is it?
[00:09:54] The Mag Mini. Can we hear that?
[00:10:00] It's kind of hard to tell in the video,
[00:10:02] but trust me, that's what's happening
[00:10:04] here. The Spark is an extremely quiet
[00:10:06] machine. Is that good or bad? I don't
[00:10:09] know. There's other manufacturers like
[00:10:11] the Dell GB10. That one has a little bit
[00:10:14] more cooling going on. I have a couple
[00:10:16] of those that I'm going to be testing
[00:10:18] soon, so stay tuned. But yeah, I never
[00:10:20] heard the Mac Mini make that that much
[00:10:23] squealing before. It's not squealing,
[00:10:24] it's it's more like a blowing sound. I
[00:10:27] gotta say Llama 3.370B
[00:10:31] was a good model, but it's getting a
[00:10:33] little bit long in the tooth. Uh,
[00:10:35] compared to some of the more some of the
[00:10:37] smaller models even that are more
[00:10:39] modern. Look at this. This is supposed
[00:10:41] to be an architecture prompt. I wanted
[00:10:43] architecture, but it's giving me code.
[00:10:47] Not exactly what I wanted. These two are
[00:10:49] actually giving me architecture. There
[00:10:50] is a little bit of code and pseudo code,
[00:10:52] but this one gave me straight up code.
[00:10:54] It doesn't even know like what
[00:10:56] technology I want to use. Okay, we've
[00:10:58] got 5.43
[00:11:00] tokens per second here on the Mac Mini.
[00:11:02] Oh, interesting. 4.61 tokens per second
[00:11:07] on the Thor and 4.46 tokens per second
[00:11:10] on the Spark. A little bit of a
[00:11:12] diminishing returns there on the Spark,
[00:11:15] even though the prompt eval rate still
[00:11:18] was amazing on the Spark. More than two
[00:11:20] times faster, almost three times faster
[00:11:22] than anything else. So 283 tokens per
[00:11:24] second on prompt eval which is basically
[00:11:27] prefill. That's the first stage before
[00:11:29] we do the decode stage and that's the
[00:11:32] token generation. If I didn't mention
[00:11:34] that earlier my apologies got prefilled.
[00:11:36] That's the prompt evaluation and that
[00:11:38] could include the whole context. So if
[00:11:40] you are having a chat session for
[00:11:42] example with one of these things it's
[00:11:44] going to include your entire chat
[00:11:45] session. Send that in process it
[00:11:48] everything including the system prompt
[00:11:50] too. So, you want that to be fast
[00:11:51] because sometimes the conversations can
[00:11:53] get pretty long. So, good on you,
[00:11:55] Sparky. Uh, we got Thor with 103 tokens
[00:11:59] per second. Not too bad. Pretty terrible
[00:12:01] with the Mac Mini. 34 tokens per second.
[00:12:05] But the M5 generation,
[00:12:08] hold on to your pants. We'll be taking a
[00:12:10] look at that shortly as well. The prompt
[00:12:12] processing on that has improved quite a
[00:12:14] bit. So, 4.46 tokens per second for the
[00:12:17] Spark. Let's verify these numbers from a
[00:12:20] different perspective. We're going to
[00:12:21] use a tool called Llama Bench, which
[00:12:24] comes with Llama CPP, and I got the
[00:12:26] exact same model that I'm going to be
[00:12:27] running, but this is the GGUF version.
[00:12:30] And this gives us both the prefill and
[00:12:32] the token generation. By the way, I
[00:12:34] compiled these on the machines. For the
[00:12:36] two Nvidia machines, I used CUDA
[00:12:37] compilation. That's why it's detecting
[00:12:39] the CUDA devices for here, device zero,
[00:12:42] Nvidia Thor, and here we got device 0,
[00:12:44] Nvidia GB10. And GB10 is basically the
[00:12:46] platform for Spark, for the Dell, for
[00:12:48] the ASUS machines. And since the creator
[00:12:50] of Llama CPP actually uses a Mac, you
[00:12:53] just run the basic build on the Mac and
[00:12:55] it automatically compiles for it. Now,
[00:12:57] take a look at this. On the Mac, Llama
[00:12:59] Bench is actually utilizing more GPU
[00:13:02] than when we were running Olama just by
[00:13:04] a tiny bit. You can kind of visually see
[00:13:06] it. I don't have any concrete numbers
[00:13:07] here, but maybe we'll see some when we
[00:13:09] actually see the final results here.
[00:13:11] Olama might have just a tiny bit of
[00:13:13] overhead with whatever else is running
[00:13:15] the services that it's running. And
[00:13:18] whoa, look at this. So on the Spark, we
[00:13:21] got a flat line just like we did before.
[00:13:23] But here on the Thor, look at that up
[00:13:25] and down. It's basically shutting down,
[00:13:27] going to zero on the GPU usage, and
[00:13:29] going back up to 98%. So more GPU usage,
[00:13:33] but also less. It's really doing that up
[00:13:36] and down quite a bit. That was for
[00:13:38] prefill. That was when we were
[00:13:40] processing. Now for token generation,
[00:13:42] it's actually flat. Really interesting
[00:13:45] results here for that same exact model.
[00:13:48] The llama 3.370 billion parameter Q4KM
[00:13:51] by the way is the quantization. Same one
[00:13:53] I used with O Lama. And Q4 just means
[00:13:56] it's quantized down from the original,
[00:13:58] which was probably BF16 if I'm not
[00:14:01] mistaken, but you'll probably correct me
[00:14:02] in the comments. Uh down to uh int four.
[00:14:07] So, integer 4, which means it's four
[00:14:09] times smaller, requiring less memory to
[00:14:12] run. Still, 42 GB is a pretty
[00:14:14] significant chunk, which means you won't
[00:14:15] be able to run it on uh even like a 5090
[00:14:18] with just 32 gigs of VRAM. Okay, the
[00:14:21] Spark gave us a result that's pretty
[00:14:23] much the same as what Olama gave us.
[00:14:25] 4.56 tokens per second for TG128. TG128
[00:14:30] just means token generation. Then we got
[00:14:32] about 283 tokens per second for PP512
[00:14:37] which is prompt processing or prefill on
[00:14:39] the Thor. It's not done yet. So wait for
[00:14:41] that one. On the Mac Mini, 42 which is
[00:14:45] higher for prompt processing 512 and
[00:14:48] 5.48
[00:14:50] for token generation. Thor has slightly
[00:14:53] higher PP 512 prompt processing 130
[00:14:56] tokens per second and TG128 token
[00:15:00] generation at 4.4. So about the same
[00:15:02] there, but the Mac Mini is faster at
[00:15:04] token generation in this case. This is a
[00:15:06] dense model. Let's take a look at a
[00:15:08] sparse model that's pretty popular. GPT
[00:15:10] OSS 20B. Let's just do 12B because why
[00:15:13] not? It's a mixture of experts model. So
[00:15:16] it should be much faster than Llama 70B.
[00:15:19] But I am a little bit worried about the
[00:15:21] amount of memory that's available on the
[00:15:23] Mac Mini because this is a pretty big
[00:15:25] model. So let's see. Oh, failed to load
[00:15:27] the model on the Mac Mini. Oh, that's
[00:15:30] too bad. You can see where having 128
[00:15:32] gigs of memory is a big plus here. The
[00:15:36] two Nvidia boxes have that and they're
[00:15:39] still running it. And here a pretty big
[00:15:40] difference between the Thor and the
[00:15:41] Spark is finally revealed. In this
[00:15:43] particular architecture for this
[00:15:45] particular model, we have more than two
[00:15:47] times faster speed for prompt processing
[00:15:50] on the Spark than the Thor and almost
[00:15:53] two times faster token generation speed
[00:15:55] as well. So the Thor 37.17
[00:15:58] for token generation, 464 for prompt
[00:16:01] processing, while the Spark has 52.77
[00:16:04] token generation, 977 for PROM
[00:16:07] processing. Pretty big difference there.
[00:16:09] As you can see, the type of model and
[00:16:10] the architecture of the model that
[00:16:11] you're running matters a lot. But let's
[00:16:13] say you're running a dense model and you
[00:16:16] want to save some money. The Thor is not
[00:16:18] a bad option. 128 gigs. But generally,
[00:16:21] the Thor is meant for applications like
[00:16:24] automotive, robotics. It's supposed to
[00:16:26] have deterministic latency, which means
[00:16:29] it doesn't vary its performance as
[00:16:30] widely as Spark does. I didn't test the
[00:16:33] variability between different things. I
[00:16:35] just showed you examples, but
[00:16:37] theoretically, that's what it's supposed
[00:16:38] to be good at. So, safety first, power
[00:16:40] conservative. We saw that it uses a lot
[00:16:42] less power than the Spark and the Spark
[00:16:44] would be better for bursty kind of
[00:16:46] applications and serving multiple users.
[00:16:49] Now, we took a look at Llama CPP. On the
[00:16:52] CUDA platform, you have VLM, which is
[00:16:54] really good at serving multiple users at
[00:16:57] the same time and doing concurrent
[00:16:59] tasks. I haven't showed you it in this
[00:17:00] case, but I did make a video about that.
[00:17:03] You can watch that right over here.
[00:17:04] Thanks for watching and I'll see you in
[00:17:05] the next one.
