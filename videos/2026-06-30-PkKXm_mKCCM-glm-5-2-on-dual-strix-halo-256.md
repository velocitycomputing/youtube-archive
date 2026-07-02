---
video_id: PkKXm_mKCCM
title: "GLM 5.2 on Dual Strix Halo (256GB): Worth it?"
channel: Donato Capitella
url: "https://www.youtube.com/watch?v=PkKXm_mKCCM"
watched_date: 2026-06-30
watched_at: "2026-06-30T12:00:00Z"
watch_count: 1
duration_seconds: 1108
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 26
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 111
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video evaluates whether GLM 5.2, a 744-billion-parameter open-weight model comparable to GPT-4.5, can run efficiently on dual Strix Halo devices (256GB total RAM). GLM 5.2 requires the IQ2M quantization (239GB VRAM, using mixed bit-widths rather than pure 2-bit) and delivers ~67 tokens/second prompt processing initially, degrading to 32 tokens/second at 32K context—roughly 3x slower than DeepSeek V4 Flash. On a coding benchmark (SWE-bench verified), both models achieved nearly identical quality (~44/45 tasks), but GLM 5.2 took twice as long (~42 minutes vs. 21 minutes per task).

For users with dual 128GB devices: **Don't use GLM 5.2**—DeepSeek V4 Flash (Q4 quantization) or MiniMax M2.7 are significantly faster for similar or better results. If you insist on trying GLM 5.2, download the IQ2M quantization and use the distributed llama script from llama.cpp toolbox (configure SSH between nodes, enable KV cache quantization Q8+, set reasoning effort to "high"). Expect ~7 tokens/second generation in practice and multi-minute latencies per query. Only pursue this if a specific task provably requires GLM 5.2's capabilities over DeepSeek.

## Transcript

[00:00:00] This video is going to be a little bit
[00:00:02] different from my usual videos in that I
[00:00:05] have been traveling quite a lot for
[00:00:07] work, meaning I haven't had time to
[00:00:10] properly script it. Neither would I have
[00:00:12] time for a lot of editing. So, I've got
[00:00:15] some notes just to make sure that I
[00:00:17] don't ramble too much. Of course, the
[00:00:20] video is on GLM 5.2. This is according
[00:00:24] to benchmarks the best or one of the
[00:00:27] best openw weight models available to
[00:00:30] us. People compare it to GPT 5.5 and to
[00:00:35] Oppus and indeed this is an extremely
[00:00:38] capable model. But the question I want
[00:00:41] to ask is can we run this model on local
[00:00:45] hardware? What does it take to run this
[00:00:47] model? what kind of quantizations we can
[00:00:50] run and does it make sense for us to run
[00:00:53] that model. Now when I say for us I mean
[00:00:56] for people that have one or two of these
[00:01:00] 128 GB strict sale devices or similar
[00:01:05] for example you might have the the GX
[00:01:07] Spark you might have some of the Mac
[00:01:09] Studios with 128 or 2556
[00:01:14] gigabytes of memory. So the question is
[00:01:18] can we run a decent quantization of this
[00:01:21] model? What kind of performance do we
[00:01:23] get compared to some other very good
[00:01:26] models such as DeepS V4 Flash that we
[00:01:29] saw in the previous video? Actually go
[00:01:31] and check that video out because I'm
[00:01:33] going to try to compare the two models.
[00:01:36] If you just take a look at the numbers,
[00:01:39] DeepSk V4, which I've got here, well,
[00:01:44] the Flash model has 284 billion
[00:01:48] parameters and 13 of those are active.
[00:01:52] So, this is a model that you can run on
[00:01:55] Streo. We saw you can run this Q2
[00:01:59] quantization on one single streak solo
[00:02:03] device and actually the performance was
[00:02:05] quite good. Let me pull up the
[00:02:09] performance benchmark for that.
[00:02:12] You will see that the smaller version
[00:02:15] this model runs on a single device and
[00:02:18] PROM processing starts actually quite
[00:02:21] high over 200 prom uh tokens per second
[00:02:25] and then it goes down as the context
[00:02:28] increases of course but you are still
[00:02:30] talking about
[00:02:32] 140 tokens per second as you reach a
[00:02:35] context of 64k. So this on a single
[00:02:38] strict solo device is really useful and
[00:02:41] if you have two of them you can run this
[00:02:44] Q4 quantization
[00:02:46] distributed across the two and you can
[00:02:48] see that prompt processing is about 40
[00:02:51] sorry 60 tokens per second so not
[00:02:54] fantastic but still useful and it
[00:02:58] doesn't go down as the context grows and
[00:03:01] as you can see here prompt processing
[00:03:04] with these smaller models is starts
[00:03:06] starts with 16 tokens per second and
[00:03:09] then it goes down to around 12 tokens
[00:03:12] per second. As we saw this is slow but
[00:03:15] fairly usable and even the distributed
[00:03:17] model uh is around 13 to how much have
[00:03:23] we got here? Probably 12 tokens per
[00:03:26] second. So we saw this works. The
[00:03:29] question is can you run GLM 5.2 to on
[00:03:34] one or two strict solo devices. Well,
[00:03:38] the model is fairly big. It is much
[00:03:42] bigger than deepseeek before flash. 744
[00:03:47] billion parameters of which 40 active.
[00:03:52] Now, 13 billion active parameters versus
[00:03:56] 40 billion active parameters. This is
[00:03:59] going to make a difference. And
[00:04:01] obviously even the sheer number of
[00:04:04] parameters means for example that you
[00:04:06] are not going to find any quantization
[00:04:10] that can actually run on a single 128
[00:04:14] GBTE device that there is nothing
[00:04:16] meaningful you can do there. So
[00:04:18] immediately you need two of these
[00:04:22] devices. And if you look at the
[00:04:25] unslaught dynamic quants, they do
[00:04:28] recommend their IQ2M
[00:04:32] quant which takes 239
[00:04:35] GBTE of VRAM. So it will run on a Mac
[00:04:39] studio or in our case on a device like
[00:04:43] two two strict cell boxes with 128 GB of
[00:04:47] VRAM and this is the quant they
[00:04:49] recommend because it is the kind of
[00:04:53] smallest quant that still makes sense to
[00:04:55] run but make no mistake
[00:04:58] this IQ2
[00:05:01] is not the same two bit quantization
[00:05:05] that is using for deepseek v4 flash. A
[00:05:10] lot of the weights in this quantization
[00:05:13] are actually in 8 bits. For example, the
[00:05:16] attention projections the experts some
[00:05:19] weights are even in 16 bits. And so you
[00:05:24] can see that this model uh maintains
[00:05:29] much better accuracy even at these uh Q2
[00:05:33] quantization than for example the
[00:05:36] dynamic quant by slot. So again the
[00:05:40] question and the benchmarks I'm going to
[00:05:42] be showing you will be comparing the
[00:05:44] performance you can get uh on these. So
[00:05:48] here we can see the benchmarks and it is
[00:05:53] still going. I was hoping it would be
[00:05:55] finished by the time I started recording
[00:05:58] the video. Alas, this is really slow.
[00:06:01] This is slower as expected than uh
[00:06:05] Deepseek V4 flash. It starts with 67
[00:06:09] tokens per second as the context is
[00:06:11] quite small. But as you the context
[00:06:14] keeps growing as you can see here at 32K
[00:06:17] we have 32 tokens per second of prefill
[00:06:21] or prompt processing. This is really
[00:06:24] slow and I don't know what number I'm
[00:06:28] going to have when the 60 4K context
[00:06:32] comes back. Actually, I am probably
[00:06:34] going to have to stop this so I can show
[00:06:38] you a few a few more things and maybe in
[00:06:41] the comments in the next few days
[00:06:43] overnight I will rerun this benchmark
[00:06:46] and give you all the data.
[00:06:58] So this is the performance of the model
[00:07:01] in terms of token generation and pro
[00:07:04] processing. But what about the actual
[00:07:06] quality of the output? I mean does it
[00:07:09] make sense for example to run GLM 5.2
[00:07:13] overnight on some tasks versus deepseek
[00:07:16] before flash. So for that I am running
[00:07:20] the uh sw bench verified mini. As you
[00:07:24] remember, if you saw the other video, I
[00:07:26] ran it on DeepSync V4 Flush. Uh, and
[00:07:31] that got 90% on these 45 tasks and GLM
[00:07:37] 5.2 actually got one task less. I mean,
[00:07:40] there is a little bit of variability. I
[00:07:42] think the performance is pretty similar
[00:07:45] on this particular coding benchmark. And
[00:07:47] again, keep in mind all the caveats on
[00:07:50] coding benchmarks. And I think this SWE
[00:07:53] verified benchmark is clearly quite
[00:07:57] saturated by both models. So if you
[00:08:00] really wanted to compare them in terms
[00:08:03] of quality of output, you would need to
[00:08:06] have a different benchmark. But I cannot
[00:08:09] tell you how long it took to run this
[00:08:14] benchmark. And at least with the llama
[00:08:16] CPP engine, what I found is that I left
[00:08:19] it overnight and it was crashing,
[00:08:22] running out of memory. I don't think
[00:08:24] Llama CPP on the RPC server, the
[00:08:28] distributed inference has good memory
[00:08:30] handling or as good memory handling as
[00:08:33] the DS4 engine here. So keep that in
[00:08:36] mind. And obviously the speed, the
[00:08:39] average duration to complete a task with
[00:08:41] Deepseek Flash was 21 minutes for the
[00:08:44] same quality of output. Essentially for
[00:08:46] completing the same task, the average
[00:08:49] time was twice as much for GLM 5.2. So
[00:08:55] again, it's quite difficult for at least
[00:08:58] this benchmark to justify that anybody
[00:09:02] tries to use GLM 5.2 to if you have two
[00:09:06] strict cell devices I think today or two
[00:09:09] devices with 128 GB of RAM I think today
[00:09:13] DeepSync V4 flash in Q4 quantization is
[00:09:17] one of the best options uh that you can
[00:09:21] run or alternatively if you want
[00:09:23] something else you can do the M the
[00:09:27] Miniax M2.7
[00:09:29] there is a quantization uh that's very
[00:09:32] good that runs really well on on streak
[00:09:34] sale. Maybe I'm going to talk about it
[00:09:37] uh later, but it was provided by uh some
[00:09:40] of the uh followers of the channel. So
[00:09:43] that's the verdict.
[00:09:47] So that's the verdict. Is so
[00:09:52] so to wrap this up, is GLM 5.2 worth it
[00:09:56] if you have two strict cell devices?
[00:09:59] Probably not. you are much much better
[00:10:02] off running DeepSync V4 flash or
[00:10:06] alternatively I think MiniMax M27 in
[00:10:10] this quantization here and it is in the
[00:10:14] VLM toolbox I think it just runs way
[00:10:19] better than GLM 5.2 but again it's on
[00:10:23] this benchmark there are definitely
[00:10:25] other tasks where I think GLM 5.2 2 will
[00:10:28] outperform uh DeepSc V4, but it is not
[00:10:32] clear whether this two bit quantization
[00:10:35] will be able to outperform DeepSc V4.
[00:10:39] Maybe in the comments below. Send me
[00:10:42] some tasks that you want me to try out
[00:10:44] and I'm going to try those for you and
[00:10:46] we can see how long it takes and whether
[00:10:48] it's able to complete them. Now, let's
[00:10:51] see how to run this model on two strict
[00:10:53] SO devices. I make it really simple. If
[00:10:56] you go on strict sero toolboxes, you can
[00:11:00] take my llama CPP toolbox and if you
[00:11:05] pull the repository down, I have a
[00:11:07] script which you can use called
[00:11:10] distributed llama and this allows you to
[00:11:13] very simply bring up a model using llama
[00:11:16] CPP RPC infrastructure. So what you are
[00:11:20] going to need to do first of course on
[00:11:22] your head node you are going to need to
[00:11:25] download the correct two bit
[00:11:27] quantization which is this one over here
[00:11:30] UDI IQ2M
[00:11:33] 239
[00:11:35] GB. It's going to take a while obviously
[00:11:37] I've already downloaded it. Once you've
[00:11:40] got that you have your repository here
[00:11:43] and you can go in the scripts folder and
[00:11:46] run uh run distributed llama. Now you
[00:11:49] need to point it to the folder where you
[00:11:52] have your GGUF files. In this case, I've
[00:11:54] already pointed it to that. You need to
[00:11:56] choose one of the toolboxes and that
[00:11:58] toolbox needs to be available on the
[00:12:02] remote machine as well, of course. And
[00:12:04] then you need to configure your remote
[00:12:07] server. In my case, you can see
[00:12:11] I have my remote server on 192.168100.1
[00:12:17] and that's obviously got SSH
[00:12:20] open and this box can SSH into that
[00:12:23] host. This is how this script
[00:12:24] orchestrates everything. So once that's
[00:12:28] configured uh you need to choose Lama
[00:12:31] server unless you want to benchmark here
[00:12:33] benchmark things as I was doing. So,
[00:12:36] Llama server, you select a context size.
[00:12:39] Uh, you can go up to 124,000.
[00:12:43] Uh, but you will find that llama CPP can
[00:12:47] get quite unstable. And what I recommend
[00:12:50] doing if you need a large context is to
[00:12:53] enable uh KV cache quantization.
[00:12:57] Probably at least Q8, which preserves
[00:13:00] essentially the quality. That's what I
[00:13:03] recommend. But if you need more space,
[00:13:05] obviously you can be uh you can be quite
[00:13:07] aggressive. Again, it probably doesn't
[00:13:10] make sense to try and run this without
[00:13:12] quantization. And then in my extra
[00:13:15] arguments here, you want to add
[00:13:18] reasoning effort high. So I think GLM
[00:13:21] has got different reasoning efforts. And
[00:13:23] you don't want to set this to max. It's
[00:13:26] really going to take way too long to
[00:13:29] produce answers. It's already quite slow
[00:13:32] as it is. But essentially once you
[00:13:34] configure this you can run the
[00:13:37] distributed server. You can see that it
[00:13:39] connects to the other host and starts
[00:13:42] the llama CPP server which then listens
[00:13:45] on port 50 uh 52 and so it connects to
[00:13:51] that. And now as you can see llama CPP
[00:13:55] comes up and it's going to take a while
[00:13:57] to load this because it's going to need
[00:13:59] to synchronize the weights with the
[00:14:01] other node. And I can actually show you
[00:14:03] here that the RPC server is already
[00:14:06] running. The memory has already been
[00:14:09] allocated. So right now it's
[00:14:11] synchronizing the weights. So again when
[00:14:13] this is done, we're going to have this
[00:14:15] up and running. So this is now up and
[00:14:18] running on port 8080. So we can go here
[00:14:21] on local host. You can see the model
[00:14:23] here. Hey, write a hip kernel to
[00:14:28] multiply to matrices, which as you know
[00:14:31] is my default prompt. And now you can
[00:14:35] see how responsive this is.
[00:14:46] Interestingly, it decided not to think
[00:14:49] at all. So it is just going with the
[00:14:53] answer but you can see seven tokens per
[00:14:56] second. So this is really really slow
[00:15:00] but it does work to an extent and you
[00:15:03] can see on the two servers the GPU being
[00:15:08] utilized and we already know that llama
[00:15:11] CBP RPC is not the most efficient. It
[00:15:14] does allow distributed inference but it
[00:15:16] uses pipeline parallelism. So you're not
[00:15:19] really fully utilizing the uh GPUs at
[00:15:23] this point. But again, it does work. And
[00:15:26] if you're so inclined, you can of course
[00:15:28] use it with any coding agent harness.
[00:15:32] For example, here I am in Visual Studio
[00:15:34] Code and I've got the uh PI agent. This
[00:15:38] is a project I've got and I can go in
[00:15:41] and ask it what is this project about?
[00:15:46] And I asked this question because it
[00:15:49] takes tool calling and also prompt
[00:15:52] processing. And you will see uh that
[00:15:55] this is not going to be fast. Especially
[00:15:58] if you look at the DeepSec V4 video, it
[00:16:00] was able to answer this question quite
[00:16:03] quickly. In this particular case, if we
[00:16:06] go on the servers, you can see that
[00:16:09] they're working. They're taking their
[00:16:11] time. Uh, but
[00:16:14] it's not going to Oh, well, it's coming
[00:16:16] back. At least it's done a little bit of
[00:16:18] thinking. Now, it's looked at the
[00:16:22] contents of this folder. It's reading
[00:16:24] different files. But again, every time
[00:16:27] it needs to read a file,
[00:16:30] it's going to take a considerable amount
[00:16:34] of time because of how slow prompt
[00:16:36] processing is with this model. But
[00:16:39] anyway, it does kind of work. And
[00:16:43] obviously, we know that the quality of
[00:16:44] the output encoding is good. So, if
[00:16:47] you're patient, uh maybe this is going
[00:16:50] to be uh good enough for you. If you
[00:16:52] have a very complex task that a smaller
[00:16:55] model like maybe quen uh 35 billion
[00:16:58] parameters if that's your go-to model
[00:17:00] obviously much faster maybe that model
[00:17:03] is not able to do something and you can
[00:17:05] just swap the model and have this work
[00:17:09] on your code. So that is an option. It
[00:17:12] does work.
[00:17:15] So we can see after a few minutes that
[00:17:18] it is actually giving us the answer. It
[00:17:20] is better than what I expected actually
[00:17:22] in terms of speed and you can see that
[00:17:24] it understood this is a deep research
[00:17:28] agent. It understood the entire
[00:17:30] structure and architecture of the
[00:17:33] project the organization of the code
[00:17:36] base and the key files and all of the
[00:17:40] notable features. So it's it's a good
[00:17:43] answer and it would be as I said before
[00:17:47] usable just fairly slow.
[00:17:50] That's all the time I have for this
[00:17:52] video. I need to go and pack my luggage
[00:17:55] as I am leaving tomorrow again for
[00:17:57] another conference. But let me know in
[00:18:00] the comments if you want to see some
[00:18:02] other things related to this model. And
[00:18:04] even as I'm traveling, I can usually SSH
[00:18:06] into my server and run a couple of
[00:18:09] things. I know there is obviously a lot
[00:18:11] of interest for GLM 5.2. I got it up and
[00:18:15] running. Let's see if there is some
[00:18:19] tasks that we find as a community where
[00:18:21] GLM 5.2 actually makes sense.
