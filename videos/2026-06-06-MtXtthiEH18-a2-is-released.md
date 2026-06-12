---
video_id: MtXtthiEH18
title: A2 is released
channel: Neural Amp Modeler
url: "https://www.youtube.com/watch?v=MtXtthiEH18"
watched_date: 2026-06-06
watched_at: "2026-06-06T12:00:00Z"
watch_count: 1
duration_seconds: 1559
source: youtube-history-browser
added_date: 
history_label: Saturday
history_order: 113
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 156
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Steve Atkinson released A2, Neural Amp Modeler's new neural network architecture for modeling guitar and bass amps, which delivers higher accuracy with lower CPU usage while remaining "slimmable"—trainable once but deployable at different complexity levels. The architecture was developed with input from companies building products with NAM and optimized through collaboration with Tone 3000. Performance testing demonstrated dramatic improvements: A2 Light ran 200 instances on an M1 MacBook compared to 144 instances for A1 Nano, while A2 Full achieved 64 instances versus 46 for A1 Standard. A2's quality was validated through a large-scale MUSHRA listening test with over 1,000 participants and 100,000+ labels, showing A2 Full ranked highest among all tested methods, with particularly strong consistency and performance on full rig models.

Musicians can immediately download the new Gateway plugin (now notarized on macOS) from the website and train A2 models using the updated recipes in the GUI trainer, Google Colab, or Tone 3000's service. If you use NAM on existing hardware or plugins running A1, you'll need to wait for product updates to run A2, but all current A1-compatible devices will be able to run A2 once updated—A1 Standard products can upgrade to A2 Full, and A1 Nano users get A2 Light. The entire listening test dataset and analysis code are publicly available for independent review, and the project remains fully open source.

## Transcript

[00:00:03] [music]
[00:00:15] [music]
[00:00:25] [music]
[00:00:33] [music]
[00:00:37] [music]
[00:00:45] [music]
[00:00:53] [music]
[00:01:04] >> Hi, I'm Steve Atkinson and I'm the
[00:01:06] creator and maintainer of Neural Amp
[00:01:08] Modeler. Today I'm releasing A2,
[00:01:11] NAM's new standard neural network
[00:01:13] architecture for modeling guitar and
[00:01:15] bass amps. Compared with its
[00:01:17] predecessor, which I'm now referring to
[00:01:19] as A1, A2 delivers higher accuracy with
[00:01:23] lower CPU usage, while also being
[00:01:25] slimmable, a single model that can trade
[00:01:28] off between the two. In this video,
[00:01:29] we're going to explore all of that.
[00:01:31] Before we do that, I want to thank the
[00:01:32] folks at Tone 3000 who sponsored A2's
[00:01:36] open-source development and collaborated
[00:01:38] closely with me on this work. It's a
[00:01:40] privilege to be able to work on
[00:01:42] technology that can be shared freely
[00:01:43] with the world. I'm deeply thankful for
[00:01:45] everything that's been built with NAM
[00:01:48] and I'm very excited for what you'll
[00:01:49] make with A2. Speaking of that, one more
[00:01:51] thing that's really important about A2
[00:01:53] is how it's been informed by the needs
[00:01:55] of companies who want to build with NAM.
[00:01:58] A lot of people got in touch when I
[00:01:59] asked, and I'm really excited about what
[00:02:02] came out of it. Okay, there's a lot to
[00:02:03] talk about. Let's get into it. First
[00:02:05] off, A2 is open source. The Python
[00:02:07] training code, the C++ code to run the
[00:02:10] models in real time, and the plugin that
[00:02:12] demonstrates how to use that real time
[00:02:14] code. As always, if you're looking to
[00:02:16] build with NAM, I hope you'll find these
[00:02:18] useful. If you're a musician and you've
[00:02:20] gotten NAM by downloading the pre-built
[00:02:23] plugin installer from the website,
[00:02:25] you'll notice that I've changed its
[00:02:26] name. Here's the thing, that plugin
[00:02:29] isn't NAM.
[00:02:31] There are lots of plugins and products
[00:02:33] that support NAM, and that's a good
[00:02:35] thing. Imagine if there was only one
[00:02:36] place to get an IR loader from. By being
[00:02:39] open, NAM has a unique opportunity to be
[00:02:42] a resource not just for myself, but for
[00:02:44] anyone who wants to build something
[00:02:45] cool. So, the plugin that you can now
[00:02:47] get pre-built from the website is going
[00:02:50] to be called Gateway. My hope is that if
[00:02:52] you find it useful, you'll keep going
[00:02:54] and explore what others have made.
[00:02:56] Please support companies that are
[00:02:57] building with NAM. If you support them,
[00:02:59] then they work with me, and I get to
[00:03:01] keep on doing this. So, Gateway is a
[00:03:03] fork of the open source plugin, and
[00:03:05] there are two main differences. First,
[00:03:08] the Apple install is notarized. I know
[00:03:10] that starting with macOS Sequoia got
[00:03:12] really hard to install a non-notarized
[00:03:15] app on your Mac. Gateway is notarized,
[00:03:17] so this will be really easy now. I'm
[00:03:20] looking into doing a similar thing for
[00:03:22] the Windows build as well. Second, I've
[00:03:23] added a screen with a link if you'd like
[00:03:26] to donate and support my work directly.
[00:03:29] For years, people have been asking me if
[00:03:31] they could support NAM. The best thing
[00:03:32] you can do still is to go and support
[00:03:35] the companies who are building with the
[00:03:37] open source software. However, if you're
[00:03:39] finding my plugin helpful and you want
[00:03:40] to say thanks, then there's a link that
[00:03:42] you can follow. Also, if you don't want
[00:03:44] to see it again, you can check a box and
[00:03:46] that's it. Thanks again to everyone
[00:03:48] who's supported NAM by checking it out,
[00:03:50] making music with NAM, and helping
[00:03:51] others get into it. It's an honor to
[00:03:54] maintain this project for you and I'm
[00:03:56] thankful for the opportunity to do it.
[00:03:58] By the way, subscribe to the channel to
[00:04:00] stay in the loop when I make new videos
[00:04:02] about NAMM. Okay, on A2.
[00:04:04] >> [music]
[00:04:07] >> The main motivation for A2 was to make
[00:04:10] NAMM's default architecture more
[00:04:12] accessible. CPU usage is key to that, so
[00:04:15] that's where I want to start. One of the
[00:04:17] first steps of the A2 project was to
[00:04:19] reach out to companies who want to build
[00:04:21] with NAMM and to understand what would
[00:04:23] make it work for them. Folks ran a
[00:04:25] series of tests with a bunch of
[00:04:27] different architectures for us to get
[00:04:29] some understanding of the rough lay of
[00:04:30] the land. We also asked them what
[00:04:32] numbers we'd need to hit for NAMM to be
[00:04:34] able to fit on their products. This way,
[00:04:36] we could be sure that everyone was happy
[00:04:37] with the results. In short, we did it. I
[00:04:40] don't recall any cases where we heard
[00:04:43] that A2 wouldn't work with someone's
[00:04:45] needs, so I'm really excited with what
[00:04:48] this is going to unlock. Now, getting
[00:04:50] the CPU usage right is partially finding
[00:04:54] out a good neural network architecture,
[00:04:55] but it's also optimizing the C++ code
[00:04:58] that runs it. CPU optimization takes a
[00:05:00] lot of work and it's not easy to take
[00:05:03] neural network code and adapt it to run
[00:05:05] on the small embedded chips that you
[00:05:08] find in your favorite guitar pedals.
[00:05:10] This is where João at Tone 3000 stepped
[00:05:12] up in a big way and made some fantastic
[00:05:15] improvements to Neural Amp Modeler Core,
[00:05:18] the real-time DSP library for running
[00:05:21] NAMM. Not only did João optimize A2, but
[00:05:24] even old A1 models are going to run
[00:05:27] quite a bit faster on the new versions
[00:05:29] of the core library. So, even if you
[00:05:31] want to keep on using your favorite A1s,
[00:05:33] getting the latest version will give you
[00:05:35] back some CPU. And who doesn't like
[00:05:38] that? Now, I wanted to do something a
[00:05:39] little goofy to show this off. I'm going
[00:05:41] to open Reaper, put an instance of
[00:05:43] Gateway on a track, and load up a NAMM.
[00:05:45] Then I'm going to copy that track and
[00:05:47] see how many we can do before my
[00:05:49] computer starts choking. Let's do it.
[00:05:51] Okay, I'm here with Reaper and I've got
[00:05:54] an instance of Gateway open
[00:05:58] uh
[00:05:59] with a full rig A1 standard model loaded
[00:06:03] up. Everything else is turned off in the
[00:06:05] plug-in. It's just this one track, this
[00:06:07] one instance of the plug-in running NAM.
[00:06:10] I've got a Focusrite Scarlett 2i2
[00:06:15] connected via USB-C.
[00:06:17] We're running at a sample rate of 48K
[00:06:20] and a uh
[00:06:22] buffer size of 128 samples. This is a
[00:06:26] MacBook Pro late 2020's
[00:06:29] M1 uh chip inside it. I'm going to start
[00:06:33] copying this track and see how many we
[00:06:35] can get before the
[00:06:38] uh playback starts uh skipping.
[00:06:44] 46.
[00:06:46] >> [music]
[00:06:51] [music]
[00:07:00] [music]
[00:07:07] [music]
[00:07:13] >> It's hanging in there. All right, we'll
[00:07:15] call that 46 instances of A1 standard.
[00:07:19] Let's go over to A1 Nano.
[00:07:26] Okay, here we are with 100 instances of
[00:07:30] A1 Nano and we are doing okay.
[00:07:33] >> [music]
[00:07:36] >> Here's 144.
[00:07:44] >> [music]
[00:07:52] [music]
[00:07:58] [music]
[00:08:02] [music]
[00:08:07] >> I think we'll call that at 144 for A1
[00:08:10] Nano.
[00:08:12] Okay, now we're over on A2 and we're
[00:08:15] going to start with the full-size model
[00:08:17] and we'll see how many of these we can
[00:08:19] run.
[00:08:20] This is a little bit of a different
[00:08:21] sounding model since I didn't think far
[00:08:24] enough ahead to make an A1 model of the
[00:08:27] A2 that I was making. So,
[00:08:30] slightly different tone, but we're here
[00:08:32] starting at 50 instances of A2 full and
[00:08:35] seems fine so far.
[00:08:42] >> [music]
[00:08:45] >> Okay, so I bumped it up to this is 64
[00:08:49] instances and it seems to be running
[00:08:51] okay.
[00:08:53] >> [music]
[00:08:58] >> Cool. We'll put that down as 64 for A2
[00:09:01] full. Now it's time for the fun one.
[00:09:04] We're going to go to A2 light and I'm
[00:09:08] going to put a ton of them in here.
[00:09:12] Just to get started, we're going to get
[00:09:14] back up to 100 instances.
[00:09:18] >> [music]
[00:09:25] [music]
[00:09:29] [music]
[00:09:34] [music]
[00:09:37] >> 200 even.
[00:09:42] >> [music]
[00:09:48] >> All right, enough of that. Uh, 200 A2
[00:09:50] lights on this laptop. I'm pretty happy
[00:09:53] with that.
[00:09:56] >> [music]
[00:10:06] >> All right. Slimmable models. This might
[00:10:08] be a new word, but I guarantee you're
[00:10:10] going to get the idea. Think about
[00:10:12] impulse responses. The longer the IR,
[00:10:15] the more you can do with it. When you're
[00:10:17] modeling a cab, a longer IR lets you
[00:10:20] capture details like the decay of the
[00:10:22] room. However, if you've got a product
[00:10:24] that can't play a longer IR, it can
[00:10:27] always truncate that IR to a shorter
[00:10:29] length when you load it on. It's not the
[00:10:31] same, but imagine if you had to go back
[00:10:34] and remake the IR. That's how things
[00:10:36] have been in neural amp modeling,
[00:10:39] lowercase n. You can't just truncate a
[00:10:41] normal neural network like you can an
[00:10:44] IR. Slimmable models are different. You
[00:10:46] train once, and you can use that one
[00:10:49] model in a variety of ways. I published
[00:10:51] a paper last year showing one way to do
[00:10:53] this, and I was really excited for it as
[00:10:56] a way for NAM to maintain its high
[00:10:58] standards for accuracy, while also
[00:11:01] making the same models more accessible
[00:11:04] in compute constrained products. The
[00:11:06] paper showed that it was possible, but
[00:11:08] the approach that I demonstrated there
[00:11:10] wasn't enough for A2. Here's the
[00:11:12] problem. The more ways you want to make
[00:11:14] it possible to slim the model, the
[00:11:17] harder it is for that one model to do
[00:11:19] everything that you're trying to make it
[00:11:21] do. Fortunately, first,
[00:11:23] we know from experience with A1 that
[00:11:26] most people overwhelmingly use either
[00:11:28] standard or nano models. And second, we
[00:11:32] found out that we didn't even need more
[00:11:35] than two options to make the industry
[00:11:37] happy. So, while the paper was showing
[00:11:40] models that you could slim seven
[00:11:42] different ways, that was overkill for
[00:11:44] what we actually needed to do. I
[00:11:46] developed a new way to train slimmable
[00:11:48] NAMs that I'm calling packed training
[00:11:50] that works better when you don't need
[00:11:52] too many different sizes. And so, we're
[00:11:54] going to be calling those two sizes full
[00:11:57] and light.
[00:11:59] >> [music]
[00:12:02] >> Finally, let's talk about accuracy. A
[00:12:04] null test is
[00:12:08] You thought I was going to do a null
[00:12:10] test.
[00:12:11] Nope, we did something better. The
[00:12:12] scientific community generally regards
[00:12:15] subjective listening tests as the gold
[00:12:17] standard for modeling like this.
[00:12:20] And that makes sense. If the numbers
[00:12:22] don't agree with your ears, then the
[00:12:24] numbers are wrong. The point of this is
[00:12:27] to sound good to people. For A2, we
[00:12:30] listened a lot. We tried thousands,
[00:12:34] maybe tens of thousands of different
[00:12:36] models and there are over 40 different
[00:12:40] A2 candidates that were so good that we
[00:12:42] sat down, plugged in our guitars, and we
[00:12:44] tried them out by hand. They even have
[00:12:46] code names. When we were feeling
[00:12:47] confident that we had our favorite model
[00:12:50] picked out, we started to develop a
[00:12:51] MUSHRA test. MUSHRA stands for multiple
[00:12:55] stimuli with hidden reference and
[00:12:57] anchor. Basically, you listen to a
[00:12:59] reference and then some anonymized
[00:13:02] samples and rate each one on how closely
[00:13:05] it matches that reference. One of those
[00:13:07] samples is just a copy of the original
[00:13:10] recording. That's the hidden reference.
[00:13:12] And for one of the other ones, we took
[00:13:14] the original recording and degraded it
[00:13:17] with a low-pass filter. That's the
[00:13:18] hidden anchor. Now, a lot of people said
[00:13:21] after they took the tests that there was
[00:13:23] always one really bad one. Hopefully,
[00:13:26] that was the anchor. The reason why it's
[00:13:28] in there is to keep things in context.
[00:13:31] Folks, the tech for data-driven modeling
[00:13:34] of guitar amps is really, really good.
[00:13:37] Sometimes, we can get into the weeds and
[00:13:39] really obsess over the details, and we
[00:13:42] did that for A2, for sure. But, by
[00:13:44] keeping with an established standard for
[00:13:47] the anchor, we're hoping that we can
[00:13:48] connect better with the greater
[00:13:50] scientific literature. Not only are we
[00:13:52] open-sourcing A2, but we're looking to
[00:13:54] put everything here through peer review
[00:13:56] and publish it as a scientific resource,
[00:13:58] as well. But, anyways, to finish out the
[00:14:00] details of the test, we recorded tones
[00:14:03] from almost 40 different amps, pedals,
[00:14:06] and full rigs for guitar and bass. We
[00:14:08] tried to span a wide variety of tones,
[00:14:11] and we often opted to make them a bit
[00:14:14] more extreme than what I might
[00:14:15] personally pick, so that we could learn
[00:14:18] as much as possible about the modeling.
[00:14:21] There are a couple of different passages
[00:14:23] that you heard for each signal chain.
[00:14:25] So, in total, this test has all of those
[00:14:27] tones with all of those passages through
[00:14:30] all of those different models. It's a
[00:14:31] ton to get through, so we randomly
[00:14:34] assigned different tones to different
[00:14:36] people. If you were talking with other
[00:14:37] people about this test on the internet,
[00:14:40] then you should know that you probably
[00:14:42] weren't listening to the same things.
[00:14:44] Depending upon which tone you're
[00:14:45] listening to, there are either eight or
[00:14:48] nine different models. The reference,
[00:14:51] the anchor, A1 standard, A1 nano, A2
[00:14:55] full,
[00:14:56] A2 lights, and
[00:14:59] Tone X's AI machine modeling V2,
[00:15:03] Neural DSP's Neural Capture V2, and
[00:15:06] sometimes the Line 6 Helix Stadium's
[00:15:09] proxy. The anonymized responses to the
[00:15:12] listening test from everyone who
[00:15:14] responded are free to download. Please
[00:15:16] feel free to have a look, analyze it,
[00:15:18] and share what you find. We'll be doing
[00:15:20] a more in-depth analysis, but for now
[00:15:22] here are a few high-level takeaways.
[00:15:25] First, we received over 100,000
[00:15:29] labels from 1,000 different
[00:15:31] participants. Thank you for everyone who
[00:15:34] chose to take some time and participate
[00:15:36] in this test. To my knowledge, this is
[00:15:38] the largest scale experiment that
[00:15:40] there's ever been done to evaluate
[00:15:42] guitar and amp modeling methods. The
[00:15:44] internet is full of anecdotes and
[00:15:46] examples, this versus that, etc. I've
[00:15:49] made some myself. It can be hard to
[00:15:51] understand how to put all of this
[00:15:53] together, especially when some anecdotes
[00:15:55] conflict. It can be even harder when
[00:15:58] everything you see and hear is
[00:15:59] algorithmically curated for you on
[00:16:01] social media. So, in that context, I
[00:16:04] think that these data are really
[00:16:06] valuable and I'm really proud that I'm
[00:16:08] able to share this as a resource with
[00:16:10] you. Again, a huge thank you to everyone
[00:16:12] who participated. Second, we found that
[00:16:16] there were a lot of bad data. A standard
[00:16:19] method from the literature is to remove
[00:16:21] participants who rate the reference too
[00:16:24] poorly or rate the anchor too highly.
[00:16:28] Applying those quality checks does
[00:16:30] remove a lot of the data from the
[00:16:32] analysis. After removing that data,
[00:16:34] we're still left with over 20,000 labels
[00:16:37] and we're going to use those for the
[00:16:38] rest of this analysis. So, after that,
[00:16:40] we began by looking at aggregate
[00:16:43] outcomes associated with each of the
[00:16:45] models. So, I'm going to show a plot of
[00:16:47] that. When you look at the data all
[00:16:49] together, what you're going to notice is
[00:16:51] that there is a lot of overlap. That
[00:16:53] makes sense. These ratings are going to
[00:16:55] be affected by not just the modeling,
[00:16:58] but on the tone that's being modeled,
[00:17:00] the passage that was played in the
[00:17:02] example, the rater, their listening
[00:17:05] setup, whether it was the start of the
[00:17:08] day or the end of the day, and so on.
[00:17:10] Another thing that you'll see is a lot
[00:17:13] of approaches did really well really
[00:17:16] often. Again,
[00:17:17] we're really good at this. Now, here's
[00:17:19] what my analysis found. Aggregating all
[00:17:22] the ratings for each method across all
[00:17:24] of the tones, passages, and
[00:17:25] participants,
[00:17:27] the median score was highest for the
[00:17:29] reference, followed by A2 Full, A1
[00:17:32] Standard, A2 Light, Neural Capture V2,
[00:17:37] ToneX V2, Proxy, A1 Nano, and then the
[00:17:41] Anchor. The same rank order goes for the
[00:17:43] mean as well as the upper and lower
[00:17:46] quartiles, with one exception, which was
[00:17:48] that the upper quartile for A1 Nano is
[00:17:51] just barely above Proxy. In order to
[00:17:53] take a little bit of a closer look,
[00:17:55] >> Hi, it's Future Steve with that closer
[00:17:57] look. So, I had started to do this, but
[00:18:00] I really wanted to make sure that I felt
[00:18:03] like I was done with all of the analysis
[00:18:06] code, and that I knew exactly what I was
[00:18:08] going to share before I talked about it.
[00:18:10] So,
[00:18:11] that pushed back this part of the video.
[00:18:13] So, here we are.
[00:18:15] Before I get into this, it's important
[00:18:17] to point out that taking a closer look
[00:18:19] can be kind of hazardous. There's
[00:18:22] countless ways that you can visualize
[00:18:24] and draw conclusions from data, and this
[00:18:26] is where cherry-picking lives. I haven't
[00:18:29] seen anything that I'd call
[00:18:31] systematically interesting or
[00:18:34] surprising.
[00:18:35] Sure, there are some exceptions to the
[00:18:37] overall trends, but that happens.
[00:18:40] Again, all of the data are available for
[00:18:43] you to look through.
[00:18:45] I need to time box this video, so here
[00:18:47] are just a few quick things. First, I
[00:18:50] just want to page through a few quick
[00:18:52] box and whisker plots for some specific
[00:18:54] models.
[00:18:56] Here's BA1, a very clean bass amp.
[00:18:59] Personally, I thought that all of the
[00:19:01] different models did really well on this
[00:19:03] one, and you can see that the ratings
[00:19:05] are squashed against the perfect score
[00:19:07] 100.
[00:19:09] Here's PB7,
[00:19:11] an absolutely gnarly bass tone that
[00:19:14] really took no prisoners.
[00:19:16] On this one, you can see that it was a
[00:19:18] decent challenge for most of the
[00:19:20] modeling methods. You'll also see some
[00:19:23] rank ordering changes.
[00:19:25] That happens sometimes, although the
[00:19:27] overall trend usually bears out more or
[00:19:30] less the same way it seems. Here's FRG6,
[00:19:34] a full rig metal tone with some SM57s
[00:19:37] that had quite the 57 peak going on.
[00:19:41] This one really punished A1. You can see
[00:19:45] that Nano is the odd one out on this
[00:19:48] one. One thing I'm really proud of with
[00:19:49] A2 is how good the full rig models are.
[00:19:53] I've personally stayed more with amp
[00:19:55] only models in the past, but I've got to
[00:19:57] say I've been using a lot more full rigs
[00:19:59] just set and forget with A2.
[00:20:02] And it feels really good to trust the
[00:20:04] method more. I don't really want to pick
[00:20:06] on non-NAM stuff too much, but there are
[00:20:09] a few cases where we got some pretty
[00:20:12] brutal failures with the other methods.
[00:20:15] One thing I'm really proud of with A2 is
[00:20:18] its consistency. A1 standard was really
[00:20:21] consistent as well, but Nano wasn't
[00:20:23] nearly as much.
[00:20:25] Uh see FRG6 earlier. There were with
[00:20:28] some of the other A2 candidates, just a
[00:20:31] few cases here and there where we heard
[00:20:33] something that we weren't really happy
[00:20:35] with.
[00:20:36] And a huge part of our thinking as we
[00:20:38] deliberated the final options was that
[00:20:41] if we heard those even once in a while
[00:20:44] to the ones where we're listening out
[00:20:46] with just 40 models,
[00:20:48] then imagine what might happen at the
[00:20:49] scale of hundreds of thousands of models
[00:20:52] that Tone 3000 operates at.
[00:20:55] I can say hand on heart that we were
[00:20:57] thrilled with how this final
[00:21:00] architecture that we picked for A2
[00:21:02] operates.
[00:21:03] And seeing it do so well in the
[00:21:05] listening test is really validating for
[00:21:08] that. But what about the null tests I
[00:21:10] can hear some folks saying. I was
[00:21:13] sincerely surprised how well sample-wise
[00:21:15] error correlated really well with the
[00:21:18] listening test results.
[00:21:20] That said, there were some A2 candidates
[00:21:23] that had exciting ESRs, but when we
[00:21:26] pulled up those models and played
[00:21:28] through them and listened to them, there
[00:21:30] were sometimes things that we could pick
[00:21:31] out that we really didn't like.
[00:21:34] So, it is true that ESR doesn't always
[00:21:37] tell the whole story all of the time,
[00:21:40] but it did predict pretty well how the
[00:21:43] listening test results came back after
[00:21:45] we'd picked A2. Last anecdote that I
[00:21:48] want to share was my first time taking
[00:21:50] this listening test myself. I have gone
[00:21:52] through all 40 of the models, all of the
[00:21:56] figures, all of the different models for
[00:21:59] each one of these several times. The
[00:22:01] first time that I did it, I had already
[00:22:04] heard back from some of my
[00:22:05] collaborators, some very exciting
[00:22:08] results when they'd taken the test
[00:22:10] themselves.
[00:22:12] But I was really nervous to find out
[00:22:15] whether or not my results would come
[00:22:16] back the same. Turns out, my results
[00:22:19] perfectly matched the overall trend. I
[00:22:21] want to point this out because it's kind
[00:22:24] of cool to see a result come out in the
[00:22:26] analysis that seems to be surprisingly
[00:22:28] robust.
[00:22:30] So again, I'm interested and I'm not
[00:22:33] going to lie, a little bit nervous
[00:22:36] to see what you find if you decide to
[00:22:38] have a look at this data.
[00:22:41] But it's definitely helped me sleep at
[00:22:42] night that I've done this analysis a
[00:22:44] number of ways and I haven't really
[00:22:46] found any surprises yet. But anyways,
[00:22:48] we'll keep digging at the data as we get
[00:22:50] our results all written down, but I'm
[00:22:52] also interested what others will find.
[00:22:54] If you want to have a look for yourself
[00:22:56] and get started with the code that I
[00:22:58] wrote to analyze it, the links are
[00:22:59] below. And one more thing on this one, a
[00:23:01] huge thanks to Woody at Tone 3000 for
[00:23:05] building the Mushra web app. This is the
[00:23:07] nicest looking, nicest working Mushra
[00:23:10] test I've ever taken. Tone 3000 have
[00:23:13] graciously decided to open source their
[00:23:17] Mushra code as well. So hopefully folks
[00:23:20] find that helpful who want to carry out
[00:23:23] similar projects.
[00:23:26] >> [music]
[00:23:27] >> Now for the conclusions. In short, we
[00:23:29] did it.
[00:23:30] A2 is finished. It's lighter, better,
[00:23:33] slimmable, and open sourced. With this
[00:23:36] release, the default recipes for
[00:23:38] training in the open source GUI trainer,
[00:23:41] the online trainer in Google Colab, and
[00:23:44] Tone 3000's training service
[00:23:46] have all been updated to the A2 recipe.
[00:23:49] While the open source code remains
[00:23:51] backward compatible with A1 models, and
[00:23:55] Gateway will continue to have full
[00:23:57] support for all open source NAM
[00:23:59] architectures,
[00:24:00] old NAM playing plugins and the firmware
[00:24:03] on existing hardware products will not
[00:24:06] be forward compatible with A2. They'll
[00:24:09] need an update. However, we were careful
[00:24:11] that every product that is out there
[00:24:13] that currently runs A1 will be able to
[00:24:15] run A2 as well. Products that run A1
[00:24:18] standard will be able to fill that space
[00:24:20] with A2 full.
[00:24:22] And places where you maybe saw A1 nano
[00:24:25] or other small custom architectures will
[00:24:28] have space for A2 light. We've been in
[00:24:30] touch with folks as A2's been in
[00:24:31] development to make sure that they have
[00:24:33] what they need to upgrade their
[00:24:34] products. But that's it. Please check
[00:24:36] out A2. Go train a model, try playing
[00:24:39] through it, and please enjoy. Again,
[00:24:41] it's my pleasure to get to work on NAM
[00:24:43] and to share it with you. And a very
[00:24:46] special thanks to my collaborators at
[00:24:49] Tone 3000 for all of their support. This
[00:24:52] couldn't have happened without them. And
[00:24:54] thanks to you for watching. I'll see you
[00:24:56] in the next one.
[00:25:01] >> [music]
[00:25:10] [music]
[00:25:15] [music]
[00:25:32] [music]
[00:25:39] [music]
[00:25:47] [music]
