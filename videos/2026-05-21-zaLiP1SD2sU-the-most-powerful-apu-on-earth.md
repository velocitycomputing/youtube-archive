---
video_id: zaLiP1SD2sU
title: The Most Powerful APU on Earth
channel: Alex Ziskind
url: "https://www.youtube.com/watch?v=zaLiP1SD2sU"
watched_date: 2026-05-21
watched_at: "2026-05-21T12:00:00Z"
watch_count: 1
duration_seconds: 818
source: youtube-history-browser
history_label: Thursday
history_order: 71
watched_at_precision: date-from-history-label
watched_percent: 66
estimated_watched_seconds: 540
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video reviews the Beelink GTR 9, a compact desktop PC housing the Ryzen AI Max Plus 395—the most powerful x86 APU available—with 128GB shared memory priced under $2,000. The reviewer benchmarks its AI performance against competitors like the Mac Studio M3 Ultra, Framework Desktop, and GMK Tech Evo X2, testing various LLMs (Qwen 3, GPT models) in different quantizations. Key findings: Beelink GTR 9 achieves the fastest token-per-second rates (e.g., 72 tokens/sec on medium prompts with INT8 quantization), Linux (Fedora 42) outperforms Windows by 5-10%, allocating 96GB VRAM vs. 64GB to the GPU significantly improves performance, but the machine runs noticeably louder than competitors and has firmware stability quirks.

**Actionable takeaway:** If you need a cost-effective local AI inference machine for running LLMs and image generation, the Beelink GTR 9 offers the fastest performance per dollar compared to alternatives. Set GPU allocation to 96GB in BIOS, plan to use Linux for better throughput, and expect firmware updates soon—but be prepared for higher noise levels and plan to install it away from your workspace.

## Transcript

[00:00:00] What's this?
[00:00:02] Ooh.
[00:00:05] Nice. Wait a minute.
[00:00:08] What?
[00:00:11] What is this?
[00:00:13] It's an impostor. This is the Beelink
[00:00:16] GTR 9. And as you can see, it's very
[00:00:20] similar to another piece of gear that's
[00:00:23] quite familiar to us, the Mac Studio.
[00:00:25] Yeah, on the outside it might look the
[00:00:28] same, but on the inside it's very
[00:00:29] different. See, the Beelink GTR 9 has
[00:00:32] the most powerful x86 APU chip
[00:00:36] on the planet right now. That'll be the
[00:00:38] Ryzen AI Max Plus 395, the same one
[00:00:42] we've seen in the GMK Tech Evo X2
[00:00:44] earlier that I covered. And also the
[00:00:46] same one that we've seen in the
[00:00:47] Framework Desktop. Yeah, this is the
[00:00:50] desktop, but it's the version that's you
[00:00:52] can build yourself. There's a bunch of
[00:00:54] other OEMs that have that chip inside.
[00:00:56] It's a very powerful chip, but they're
[00:00:59] not all equal. Well, let's face it, this
[00:01:02] little mini PC is pretty good. Look at
[00:01:04] the IO on it. Compared to the Mac
[00:01:06] Studio, we've got two 10 gig NICs. We've
[00:01:09] got the same Mickey Mouse power supply,
[00:01:11] internal power supply, which means no
[00:01:13] brick. I love that. It also has USB-A,
[00:01:17] two of those, and HDMI. But this one has
[00:01:21] connector, which the Mac Studio does
[00:01:23] not. On the front, we have an SD card
[00:01:25] reader and a power button with a
[00:01:27] fingerprint reader. However, the Mac
[00:01:29] Studio, this one is the M3 Ultra, it
[00:01:31] does have four Thunderbolt 5 ports,
[00:01:36] which this one does not. And that's a
[00:01:38] big, big miss. But it does have that 360
[00:01:41] microphone array, which is pretty cool.
[00:01:43] So, it's an interesting machine, and I
[00:01:44] think most people are going to be
[00:01:46] interested in this machine for its AI
[00:01:48] capabilities. Specifically, because it
[00:01:50] has 128 gigs of memory that's shared
[00:01:53] with the CPU and a GPU for under $2,000.
[00:01:57] Yeah, that's still pretty expensive, but
[00:02:00] 128 GB, considering we have 128 GB
[00:02:04] machines for $4,000, like this DGX
[00:02:08] Spark, and we have this very
[00:02:10] heavy Mac Studio, which I happened to
[00:02:12] get from the recertified store, is that
[00:02:15] what they call it? Whatever they call
[00:02:16] it, for over $3,000.
[00:02:19] And this is the cheapest one, okay? So,
[00:02:20] price-wise, the Beelink is actually
[00:02:24] pretty good deal. But that's not where
[00:02:25] the story is. I think most people are
[00:02:27] going to be getting this because they
[00:02:28] want to be able to run local AI, local
[00:02:31] LLMs, image processing, image
[00:02:33] generation, things like that. So, aside
[00:02:35] from all the externals and all the
[00:02:36] capabilities, I'm going to focus only on
[00:02:39] that in this review. And if you're
[00:02:41] curious about this machine in general or
[00:02:43] how it compares with the other ones, let
[00:02:45] me know in the comments down below, and
[00:02:46] maybe I'll do more videos on this one.
[00:02:48] This hotel just told me, "Just use the
[00:02:49] Wi-Fi, no login needed." Open network,
[00:02:52] lots of laptops, no thanks. So, I flip
[00:02:54] on Surfshark before I type a single
[00:02:56] command. One click and my git pushes,
[00:02:58] container pulls, and package installs go
[00:03:00] through an AES-256 encrypted tunnel.
[00:03:03] CleanWeb swats the junk, ads, trackers,
[00:03:06] the usual suspects. Meanwhile, Surfshark
[00:03:08] keeps no logs, independently audited,
[00:03:10] and the servers are RAM-only, which
[00:03:12] means reboots wipes them clean. The best
[00:03:15] perk? Unlimited devices. This MacBook,
[00:03:17] my phone, and any of my other devices
[00:03:19] are all covered under one plan. SSHing
[00:03:22] to the lab feels a lot less sketchy on
[00:03:24] public Wi-Fi now. Head to
[00:03:25] surfshark.com/alexiskin,
[00:03:27] you'll get four extra months free and a
[00:03:30] 30-day money-back guarantee. Link down
[00:03:32] below. Protect your traffic and keep
[00:03:34] building. Now, back to the video. Mac
[00:03:36] Studio up on top, Beelink GTR 9 at the
[00:03:39] bottom. I got LM Studio running on both,
[00:03:41] and we've got the same prompt: design a
[00:03:43] scalable web application architecture
[00:03:45] for an e-commerce platform. It's a
[00:03:47] medium-size architecture prompt that I
[00:03:49] have out of my collection of prompts.
[00:03:51] We'll get into more prompts in a bit.
[00:03:52] Let's start it off nice and easy. Qwen 3
[00:03:55] 4B. Now, Mac Studio is running the MLX
[00:03:58] version because that's what's optimized
[00:04:00] for running on Apple Silicon, so why
[00:04:02] not? Let's run the most optimized thing.
[00:04:04] Load model on both, and boom. Let's go.
[00:04:08] I think these are both acceptable
[00:04:10] results as far as speed goes, but I
[00:04:13] think it's pretty obvious that Mac
[00:04:15] Studio is way, way faster. And that Mac
[00:04:17] Studio is the M3 Ultra with 96 gigs of
[00:04:20] RAM. It's the lowest variant. They go up
[00:04:22] to 512 GB. We got 144 tokens per second
[00:04:26] on that. That's crazy. I'm going to stop
[00:04:29] this one because it just keeps going. 52
[00:04:32] tokens per second here. So,
[00:04:34] I'd say quite a bit of a difference
[00:04:36] there. Okay, okay, Alex, you're not
[00:04:38] being fair. You're comparing Apple
[00:04:39] Silicon's best chip right now to AMD's
[00:04:43] best mobile chip. But I wanted to use
[00:04:45] you know where we are right now as far
[00:04:48] as what's available right now for these
[00:04:50] form factor machines, small form factor.
[00:04:53] Yes, Apple Silicon machine is much more
[00:04:55] expensive than this one. But how does
[00:04:56] this AMD chip stack up against the other
[00:05:00] AMD options that are out there, which
[00:05:02] are substantially cheaper than Mac
[00:05:03] Studios? And for those of you that are
[00:05:05] curious about this, I am running Vulcan
[00:05:08] Llama.cpp, and on AMD you basically have
[00:05:12] three options. You can run CPU, which is
[00:05:14] going to be really slow. You don't want
[00:05:16] to do that. If it runs on a CPU, it's
[00:05:18] not using the GPU power to run in
[00:05:21] parallel. That's an oversimplification,
[00:05:22] but for this video, it'll do. We also
[00:05:25] have ROCm, which is AMD's API to be able
[00:05:27] to run LLMs and image generation models
[00:05:30] on AMD hardware. And we also have
[00:05:32] Vulcan, which is kind of a third-party
[00:05:34] API, but it runs across multiple
[00:05:36] platforms, and it happens to be one of
[00:05:40] the best ones right now. That's what I
[00:05:42] ran it on right now. If I run this on
[00:05:44] ROCm, well, let's just take a look. So,
[00:05:46] I got 52.8 tokens per second using
[00:05:49] Vulcan, and if I do the exact same
[00:05:52] prompt using ROCm, let's see what we
[00:05:54] get. This is the latest LM Studio as of
[00:05:56] right now, using the latest ROCm
[00:05:59] libraries and latest Vulcan libraries.
[00:06:01] We get 60 tokens per second. So, a
[00:06:04] little bit better. I'm actually
[00:06:05] surprised here because ROCm didn't do so
[00:06:07] well when it comes to larger models. So,
[00:06:09] this is a very small 4 billion parameter
[00:06:12] model, but I did test this on a few of
[00:06:15] these larger models. And to save you
[00:06:17] some time, I actually did my automation
[00:06:20] script against a bunch of different
[00:06:21] machines, including this one and
[00:06:23] including the M3 Ultra. So, let's take a
[00:06:26] look at that. All right, here we go.
[00:06:27] Now, in case you're not familiar with
[00:06:28] the way the AI 395 Plus Max Plus Ryzen
[00:06:32] 7840HS machine runs,
[00:06:34] you can basically choose how much is
[00:06:37] allocated to the GPU from the BIOS
[00:06:40] setting. You can set it to auto, which
[00:06:42] on some machines you can do, but on
[00:06:44] other machines you can't. On this
[00:06:46] machine, you cannot. You can either
[00:06:47] choose 64 or 96. So, here are both
[00:06:51] options, and look at the difference
[00:06:53] here. 96 gives us, that's the blue one,
[00:06:57] by the way,
[00:06:58] gives us a lot more performance than 64.
[00:07:02] For example, that medium architecture
[00:07:04] prompt that I just ran, 72 tokens per
[00:07:06] second for Qwen 3 Coder 30B, and on the
[00:07:11] 64 GB setting, we got 67 tokens per
[00:07:15] second. So, quite a bit less, with a bit
[00:07:16] more variance, too, between the runs. By
[00:07:18] the way, the script that I wrote runs
[00:07:20] multiple times and then takes the
[00:07:21] average and then has a standard
[00:07:23] deviation that shows up like this little
[00:07:25] bar right here. The extra-long
[00:07:27] programming prompt, which is about
[00:07:29] 30,000 tokens for a prompt. Yeah, it's
[00:07:33] big. We still have 22 tokens per second
[00:07:35] for the 96 GB setting, and we have 13.9
[00:07:39] tokens per second for the 64 GB setting.
[00:07:41] A big difference. You know what else
[00:07:43] makes a big difference? Right now, I'm
[00:07:45] on Linux here. I'm on Fedora 42, but I
[00:07:48] also ran these on Windows. And wouldn't
[00:07:51] you know, something you might already
[00:07:53] kind of suspect. Yeah, it's faster on
[00:07:56] Fedora 42 than on Windows. So, the red
[00:07:58] one here is Fedora 42. We got for that
[00:08:01] medium architecture prompt, 70 tokens
[00:08:03] per second, and 65.9
[00:08:06] tokens per second for the same exact
[00:08:08] model, for the same exact prompt on
[00:08:10] Windows. And you can pretty much see
[00:08:12] that all throughout. By the way, these
[00:08:13] are available on my GitHub, at least the
[00:08:15] data. You still have to run the script
[00:08:17] to generate the charts. Now, as far as
[00:08:20] the machine goes, the machine came with
[00:08:21] Windows 11 pre-installed and runs
[00:08:23] beautifully. Well, it's everything's
[00:08:26] fine with it. Although, I did find a
[00:08:27] couple of blog posts saying that the
[00:08:29] NICs needed to be upgraded, [music]
[00:08:32] firmware issues. You can always upgrade
[00:08:34] that. I'm talking about hardware only
[00:08:36] here and the chip. All those other
[00:08:38] firmware and software issues can be
[00:08:40] mitigated. But I'd say, if you're going
[00:08:41] to be releasing a product, you probably
[00:08:44] want to check that first. Make sure you
[00:08:46] do a lot of testing. I think they were
[00:08:49] in a rush to get this out. And yeah,
[00:08:50] they were probably one of the last
[00:08:52] companies to get a machine out, but they
[00:08:54] did, and it's out, and now they just
[00:08:57] need to update some of the firmware. I'd
[00:08:58] say the Windows implementation runs
[00:09:01] really well. However, the Fedora
[00:09:03] implementation
[00:09:05] had some quirks. My mouse would die once
[00:09:07] in a while, I had to reboot. The screen
[00:09:09] would freeze once in a while, I had to
[00:09:11] reboot. I'm sure that's all going to be
[00:09:13] taken care of, but I thought I would
[00:09:14] mention it. Now,
[00:09:16] this is the interesting part. How does
[00:09:19] this compare with the other machines
[00:09:22] that have the exact same chip? I'm going
[00:09:24] to start off with a negative, okay?
[00:09:26] Forgive me. And yes, I went into the
[00:09:28] BIOS, I set it to performance mode, best
[00:09:30] performance, as I did on all the other
[00:09:32] machines. But this one is consistently
[00:09:35] the loudest machine in the room. And if
[00:09:38] you're sitting right next to it, you're
[00:09:39] going to hear it. However, that is not
[00:09:41] without its benefits, because it's also
[00:09:43] the fastest. Let me show you. So, here's
[00:09:45] Qwen 3 Coder 30 billion again, 64 GB
[00:09:48] allocated for the GPU, which means the
[00:09:50] other 64 are allocated for the system
[00:09:53] memory. Here's the 96 GB allocation,
[00:09:56] does a little bit better. And let's take
[00:09:57] a look at the Framework Desktop, which I
[00:10:01] really like. It works amazingly well.
[00:10:03] Everything just works. It's almost a
[00:10:05] silent machine. I really liked it. I did
[00:10:08] a whole review on it. You can check it
[00:10:10] out. I'll link to it down below.
[00:10:11] However, if we take a look at the tokens
[00:10:14] per second, if we only take a look at
[00:10:16] that, then this machine blows it out of
[00:10:19] the water. Here's a 64 gigabyte GPU
[00:10:21] allocation for the Framework Desktop in
[00:10:23] orange. You can see that the Beelink one
[00:10:26] is way faster. And here's the 96
[00:10:28] gigabyte allocation. It's a little bit
[00:10:30] faster than orange, but still the
[00:10:32] Beelink machine destroys it, especially
[00:10:35] over here. Medium architecture prompt.
[00:10:37] Again, the Beelink GTR 9, this machine
[00:10:39] right here, 72 tokens per second for
[00:10:42] this model. Framework Desktop, 51 tokens
[00:10:44] per second. I mean, those are both good
[00:10:46] numbers, but still you can see it's
[00:10:48] pretty consistent that the Beelink
[00:10:50] machine beats the Framework machine.
[00:10:51] Except the really long prompts. Over
[00:10:56] there, the Framework machine actually
[00:10:57] does really well. Let's take a look at
[00:10:59] the INT8 quantization. The other one was
[00:11:01] INT4 quantization. So, here we're doing
[00:11:03] pretty well, too. Medium architecture,
[00:11:05] we've got 48 tokens per second at 64
[00:11:09] gigabyte allocation. Framework Desktop
[00:11:11] still does a little bit worse, 37.7
[00:11:14] tokens per second. The GMK Tech Evo X2,
[00:11:17] which does a little bit better than
[00:11:19] Framework one, quite a bit better in
[00:11:20] some of these cases, but still 46 tokens
[00:11:23] per second for medium architecture,
[00:11:25] which is a bit lower than the Beelink
[00:11:27] Desktop. And that one was the fastest
[00:11:29] until now. Now, the M3 Ultra. Let's take
[00:11:31] a look at that one. Boom.
[00:11:33] >> [laughter]
[00:11:35] >> Yeah, you can see that that just uh
[00:11:37] different different scale here. Working
[00:11:39] with a different level. Medium
[00:11:40] architecture for that particular prompt
[00:11:42] is 72 tokens per second in INT8
[00:11:45] quantization. Now, a couple of other
[00:11:47] interesting points I want to point out
[00:11:49] here about this machine. GPT-OSS 20
[00:11:52] billion. It's a model that's pretty
[00:11:54] popular. It's by Open AI. It ran it
[00:11:56] under Vulcan, but it would not work
[00:11:59] under ROCm. And it's only on this
[00:12:01] machine that it wouldn't do it. It ran
[00:12:03] it fine on the Framework Desktop. It ran
[00:12:06] it fine on the GMK Desktop. Wouldn't
[00:12:08] work here. Here's a chart in case you're
[00:12:10] interested. GPT-OSS 20B, this is under
[00:12:13] Vulcan and it does quite well. Except
[00:12:16] the really long prompts where it just
[00:12:18] says, "Nah,
[00:12:20] I don't think I'm going to do that one."
[00:12:21] The extra long repo prompt. Actually,
[00:12:23] now that I look at it,
[00:12:26] it does do pretty well across most of
[00:12:27] these medium-sized prompts. So,
[00:12:30] not bad. Just ROCm for some reason would
[00:12:33] not work very well. Now, I know that
[00:12:35] ROCm works on this chip and it works
[00:12:37] quite well. In fact, you can check
[00:12:39] Donato Capitella's channel. He's got
[00:12:41] I'll link to it down below. He's got a
[00:12:43] couple of videos. He's built a few
[00:12:44] different toolboxes to be able to
[00:12:46] containerize these different APIs and
[00:12:48] run them and run benchmarks on them and
[00:12:50] they work very well. I've already shown
[00:12:51] this on my Framework video. You can
[00:12:53] check that out. But for a lot more
[00:12:54] details, see his channel. So, overall,
[00:12:56] this machine does pretty well. There are
[00:12:59] some quirks, but I think that's just
[00:13:00] BIOS version and firmware and software
[00:13:02] related, which will probably be ironed
[00:13:05] out uh
[00:13:06] month two, I don't know, but they'll be
[00:13:09] ironed out. I think that they tuned this
[00:13:10] machine
[00:13:11] pretty high. That's why it performs so
[00:13:14] well, but also you get a lot of noise
[00:13:16] level, so keep that in mind. Overall,
[00:13:19] nice-looking machine, I would say,
[00:13:21] wouldn't you? All right, let me know
[00:13:23] what you think about this machine,
[00:13:24] whether you'd pick it up or not. And
[00:13:26] also check out that Framework Desktop
[00:13:28] video right over here. Thanks for
[00:13:30] watching and I'll see you next time.
[00:13:35] >> [music]
[00:13:36] >> Yo.
