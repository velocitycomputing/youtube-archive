---
record_id: "youtube:6kjXzTVmT58"
video_id: 6kjXzTVmT58
title: Qwen3.8 27B Is INSANE – This Is the BEST Local AI Model Yet!
channel: Bijan Bowen
url: "https://www.youtube.com/watch?v=6kjXzTVmT58"
watched_date: 2026-08-16
watched_at: "2026-08-16T12:00:00Z"
watch_count: 1
duration_seconds: 2294
source: youtube-history-browser
added_date: 
history_label: Aug 16
history_order: 65
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 229
transcript_status: fetched
transcript_content_hash: f7c697203489d3e17307ebb5d4bdbf938b91ec24f4e3be99b0498a7fff6f4fc9
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

Qwen3.8 27B was tested by a creator running it locally at Q8 (Unsloth quant) on an RTX Pro 6000, with extra-high thinking enabled and the Pi harness after OpenCode ran out of memory and crashed. The benchmark claims are a DeepSWE jump from 13.3 to 42.2 over its predecessor, a 262K context (extendable to 1M), multimodal input including video, and an Apache 2.0 license. Results were mixed but impressive for the size. The browser OS test (v2.7, with procedural wallpapers and an email client) mostly worked, but its GTA clone had a broken camera and no way to exit the car. The raw C++ skateboard game was a failure: it compiled only after many errors, then got stuck on a camera bug it couldn't fix until the creator supplied the answer, and even then the player couldn't move. Several tests went very well:
- The subway FPS, the Slapis watch website, the city chrono-timeline and the "Steve the PC repair" game all came out strong.
- The RB26 engine CAD model for an N20 motor was solid, though not printable without supports.
- The Three.js model of an Acer Predator PC was passable.

Chat and vision behaved reasonably, but the model overthinks at max effort and wouldn't identify the creator from a photo. The creator suspects some of these tests (subway FPS, watch site) may have leaked into the training data.

For you, the practical takeaways are these. If you have a 24 GB card, try a Q4 quant of Qwen3.8 27B, but expect some quality loss, since the tests here used Q8, which needs more VRAM. For local agentic coding and web or JS front-end tasks it looks like a strong option under Apache 2.0, so it's worth running your own prompts rather than trusting benchmarks. Expect long thinking loops at the highest effort setting, so use a lower setting for chat and simple tasks. Don't rely on it for low-level C++ or game-engine work without a human debugging the last 5%. If you try Pi as a harness, note that OpenCode crashed from memory growth on long runs. Treat the "better than frontier models" impressions with caution, since the creator's own tests may be contaminated and nothing was measured against Opus 4.6 on the same tasks. Note that the transcript was truncated, so the ending (the repair game and any final verdict) is missing.

## Transcript

[00:00:00] I had it do a street eat. It didn't
[00:00:02] fully finish, but
[00:00:09] coming very soon.
[00:00:11] Why did it just go from zero minutes
[00:00:13] remaining to coming soon?
[00:00:17] Where is it? All right, so for today's
[00:00:19] video, and you're probably going to be
[00:00:20] wondering, hey, how'd you get that
[00:00:21] little plushie? Well, because I'm an
[00:00:23] influencer. So, Quen 3.827B has been
[00:00:26] released. In my opinion, this is
[00:00:27] probably the most long- aaited and
[00:00:29] exciting release for folks who are
[00:00:31] interested in local AI. Why? Because the
[00:00:34] predecessor was the strongest local
[00:00:37] model of its size and had the widest
[00:00:40] variety. Basically, it can run on the
[00:00:42] widest amount of hardware without
[00:00:43] needing to spend thousands of dollars on
[00:00:45] compute. So, let's start by taking a
[00:00:47] look at Quen 3.827b. I will probably go
[00:00:50] through this section a bit quicker than
[00:00:51] normal because I would imagine a lot of
[00:00:53] folks just want to see how this stacks
[00:00:55] up in coding tasks and other things,
[00:00:57] myself included. In terms of some
[00:00:59] technical specs for it, it has a 262,000
[00:01:02] context length, which they say is
[00:01:04] extensible up to a million. Now, if we
[00:01:06] scroll up here, they talk about hosting
[00:01:07] this on this Quen cloud service where by
[00:01:10] default it has 1 million context
[00:01:12] enabled. So, just to mention that as
[00:01:14] well. Now, if we get to the benchmarks,
[00:01:16] this is where things become quite
[00:01:17] interesting because I always tend to now
[00:01:19] just look at the deepsw SWE scores
[00:01:22] because I find that my experience with
[00:01:23] all of these models tends to be pretty
[00:01:25] decently reflected by the scores I've
[00:01:27] seen for this benchmark in specific, of
[00:01:30] course, in coding tasks where this over
[00:01:32] its predecessor is a gigantic leap. And
[00:01:35] that says a lot because this predecessor
[00:01:37] right here was still like an absolute
[00:01:39] powerhouse, especially for the size and
[00:01:41] openness of the model. So, if it really
[00:01:43] has increased from a 13.3 to a 42.2,
[00:01:47] this may be like some serious business.
[00:01:49] Now, it is also pretty heavily, I
[00:01:51] suppose unscientifically, putting the
[00:01:52] Mac down on Quen 3.7 Plus as well. And
[00:01:55] if my memory serves me correctly, Quen
[00:01:57] 3.7 Plus was like a almost 400 billion
[00:02:00] parameter mixture of experts model. And
[00:02:02] even look how close the predecessor to
[00:02:04] this was to that. So that just again
[00:02:07] lends itself to how good this model was
[00:02:09] and how exciting this model is because a
[00:02:11] lot of folks are expecting that. Again,
[00:02:13] this is almost trading blows with Opus
[00:02:16] 4.6 on Max. We don't have the specific
[00:02:18] deep SWE score for that which I would
[00:02:20] tend to put more weight on in terms of
[00:02:22] raw coding performance. However, it does
[00:02:25] remain the fact that this is essentially
[00:02:26] like a Frontier model from a year ago
[00:02:29] that can now be run on a single GPU,
[00:02:32] which is just absolutely madness and
[00:02:33] exciting for folks who don't want to be
[00:02:35] tied to subscriptions to access
[00:02:36] intelligence. In that same vein, the
[00:02:38] license is Apache 2.0, which is one of
[00:02:40] the most free and open ones, probably
[00:02:42] not one of the most, probably the most,
[00:02:44] which is exciting as well. In terms of
[00:02:46] its multimodality, this can not only
[00:02:49] accept images, but also videos. Now,
[00:02:51] they do even mention somewhere here like
[00:02:52] sending in an hour-ong video, which I am
[00:02:55] definitely not going to be trying in
[00:02:57] this test because I don't know what that
[00:02:58] would do for VRAM requirements and use,
[00:03:01] but it's just insane to have that
[00:03:02] capability as well. From STEM diagrams
[00:03:05] and documents to our scale videos, which
[00:03:07] is quite nuts. Now, in terms of the way
[00:03:10] we're going to be testing this
[00:03:11] specifically today, I have opted to use
[00:03:13] a Q8 quantization, which I've just
[00:03:15] pulled the one from Unsloth right here.
[00:03:17] Reason being, while this will not fit on
[00:03:19] a single 24 gigabyte card, which I know
[00:03:22] then may alienate some viewers because
[00:03:24] the performance may be degraded when
[00:03:26] you're using one of these Q4 quads, I
[00:03:28] want to see this at its more
[00:03:30] realistically highest potential
[00:03:32] performance. I'm not going to pull the
[00:03:34] BF-16 cuz it's just probably not
[00:03:36] realistic. I don't think a lot of folks
[00:03:37] will use that, but I think seeing how
[00:03:39] it's doing at an 8bit quant is probably
[00:03:41] important just to get a more accurate
[00:03:44] feel for how this stacks up to things
[00:03:46] like Opus 4.6. six and things of the
[00:03:48] sort. So, I want to mention that.
[00:03:50] Additionally, I am using this on an RTX
[00:03:53] Pro 6000 GPU, which has doubled in price
[00:03:56] since I purchased it a few months ago,
[00:03:57] which is just kind of ridiculous, but um
[00:04:00] it's fast and it has plenty of VRAM to
[00:04:02] max out the context, so I guess that's a
[00:04:04] good thing. All right, so
[00:04:06] here's our browser OS. I've had the
[00:04:08] absolute worst time so far in testing
[00:04:10] this model. It's been like three or four
[00:04:12] hours since it's been out and this is
[00:04:14] the first time we're seeing the browser
[00:04:15] OS. Now, a couple of things. One, this
[00:04:18] is a new version of the browser OS
[00:04:20] dubbed the browser OS test v2.7. It is
[00:04:23] the same except it needs to also include
[00:04:26] beautiful procedurally generated
[00:04:27] backgrounds with movement and then also
[00:04:30] an email client. These were things that
[00:04:31] were suggested to us just in a comment
[00:04:33] of the recent video. So, thank you for
[00:04:35] that. They were a good idea. Now, let's
[00:04:37] take a look. Something I noticed right
[00:04:39] here is it included this thing. And if
[00:04:41] we refresh this browser OS right here,
[00:04:43] we're going to notice it's named it
[00:04:46] Pulse. This was the exact same thing
[00:04:48] that Kimmy K3 did in the browser OS
[00:04:51] test. I believe it named it Pulse as
[00:04:53] well. And it genuinely looked exactly
[00:04:55] like this thing. And if you clicked it,
[00:04:57] it did also
[00:05:01] Bit is following you. 8 seconds of
[00:05:03] companionship. I'm going to have to
[00:05:05] refrain from commenting on that in a
[00:05:08] more Okay, we have a clock in the bottom
[00:05:11] right and the date. Is there a right
[00:05:14] click? Yeah, there is. Good. New
[00:05:15] wallpaper and it should be procedural
[00:05:17] with some movement. Okay, it is. I have
[00:05:19] to say they're
[00:05:22] kind of ugly, but nonetheless, shuffle
[00:05:24] icons. Oh, very good. That is a feature
[00:05:28] I've not before seen and would be okay
[00:05:32] with not seeing again in the future
[00:05:34] though. All right, let's check our start
[00:05:36] menu. That's pretty good looking.
[00:05:38] Settings, a bunch of stuff. Let's just
[00:05:40] get started. Now, having to include an
[00:05:42] email client with this, I think, is kind
[00:05:44] of difficult because it's not actually
[00:05:47] going to be able to knock out and put
[00:05:48] like an email client in here that's
[00:05:50] functional. So, it probably just has
[00:05:54] spam at Wow, it's clever. Pizzaron 3000,
[00:06:00] your quantum pepperoni is ready. Hey, we
[00:06:02] got new mail. Our pet emailed us. Follow
[00:06:04] me. The snacks are calling. Try crashing
[00:06:06] into a car near me for science.
[00:06:13] Can I send it?
[00:06:17] [laughter]
[00:06:19] It's It's definitely not like related at
[00:06:22] all, but just looking at its eyes right
[00:06:24] there after sending that email is kind
[00:06:26] of meta. All right, let's let's check
[00:06:28] our notes app. Probably going to be
[00:06:30] simple. New. Okay, word count, character
[00:06:33] count. I don't see the ability to save
[00:06:35] this as a text file, which is
[00:06:38] enraging. All right, let's see what's
[00:06:40] up. Type help. I would if I could click
[00:06:43] into the search box or the text box. I'm
[00:06:45] going to be very sassy here. Pet. Ah,
[00:06:48] pet feed.
[00:06:50] Oh, it's walking to the
[00:06:54] [laughter]
[00:06:58] [snorts] pulse storm.
[00:07:01] This video is not going to be out for
[00:07:03] like six years. Okay, this model is
[00:07:05] going to be like deprecated by the time
[00:07:07] this video comes out. All right, I don't
[00:07:09] know exactly what just happened. Matrix.
[00:07:13] Oh, nice. Let's see if pulse has to get
[00:07:15] out of the way of these things or if it
[00:07:16] gets
[00:07:19] no. Okay, good. Good. Nothing happens to
[00:07:22] it. All right, Neoch.
[00:07:24] [laughter and snorts]
[00:07:27] Beautiful.
[00:07:29] Matrix just to turn that off. What else?
[00:07:32] Pulsecom. Okay. All right. We're all
[00:07:34] curious. Let's check the GTA clone.
[00:07:36] Grand Theft We
[00:07:39] Oh, I can already tell this is sick.
[00:07:41] Look at that. I've not seen traffic this
[00:07:43] well done before. Wait a second, though.
[00:07:47] Can we actually get out of the car?
[00:07:49] Also, Pulse is still here. Like, we're
[00:07:51] just going to ignore that. Oh my. This
[00:07:53] camera movement is is
[00:07:55] along the incorrect axis. And I don't
[00:07:58] think we can get out of the car. This is
[00:08:01] in some ways worse than its predecessor,
[00:08:03] but in some ways better, this specific
[00:08:06] result,
[00:08:07] because the predecessor had like some
[00:08:09] sick walking and stuff, unfortunately.
[00:08:11] pick up the package. Yeah, I would if
[00:08:13] the car moved. Oh, wow. We can maybe
[00:08:16] kind of like
[00:08:18] This is like a like a quantum space.
[00:08:24] I feel like we just ran over a
[00:08:25] pedestrian cuz I heard something, but I
[00:08:27] I can't see because of the camera being
[00:08:29] totally totally messed up. Okay, let's
[00:08:32] let's come back to this or not. Next up,
[00:08:35] we have Void Hunter, which we're all
[00:08:37] going to imagine is probably the same
[00:08:39] generic asteroid shooting game that all
[00:08:41] of these include. Actually, the movement
[00:08:43] here is it's pretty well done.
[00:08:48] [laughter]
[00:08:50] All right, this is cool. Oh, are we
[00:08:51] getting shot back at?
[00:08:54] No,
[00:08:56] I think we are. This is actually pretty
[00:08:59] well done. Can we move forward? No, but
[00:09:02] that's okay. Q and E is to roll. Oh.
[00:09:06] [laughter]
[00:09:06] Oh. Get slipped. This one's better than
[00:09:09] the GTA game, which doesn't normally
[00:09:11] happen. All right. Next up, [sighs]
[00:09:14] calculator. 57*
[00:09:17] 52. 2964.
[00:09:20] Wave deck.
[00:09:32] [laughter]
[00:09:34] What happened to its eyes? Look. Look.
[00:09:40] Cosmic assault.
[00:09:44] [laughter]
[00:09:47] Midnight. Loi. All
[00:09:55] >> [laughter]
[00:10:00] >> right. Overall, I feel like something we
[00:10:03] forgot to click some things uh
[00:10:06] about yet.
[00:10:09] Special feature pulse. Yeah, it's quite
[00:10:12] special uh settings. And then we just
[00:10:15] have some accent color selections, which
[00:10:17] I genuinely can't tell if they're making
[00:10:19] any impact to this right now. Wallpaper.
[00:10:24] Oh, good. Matrix. Okay, so we can roll
[00:10:27] the dice with different seeds. This was
[00:10:29] something I think was present in a
[00:10:32] recent result that I unfortunately had
[00:10:35] neglected to notice. Pulse.
[00:10:38] Oh, look at the live feed of like tool
[00:10:40] calls. Energy floor. Wait, pulse is the
[00:10:42] wallpaper, not this. What the heck is
[00:10:45] this? Oh, this is bit. All right. Well,
[00:10:47] this was probably the funniest result
[00:10:50] I've seen. Really, the Grand Theft Auto
[00:10:52] game was a little disappointing based
[00:10:53] off the predecessor cuz we couldn't
[00:10:55] actually get out of the car and cause
[00:10:57] problems, but the number of traffic
[00:10:59] vehicles moving around and pedestrians
[00:11:01] was really kind of cool. So, it was just
[00:11:04] the camera. Oh, yes, we did it. The car
[00:11:07] got damaged. Hold on.
[00:11:11] All right, I'm I'm done with this
[00:11:12] result. This is this is quite something.
[00:11:14] All right, so I have swapped to using Pi
[00:11:16] on this system setup with the computer
[00:11:18] behind me running this model locally.
[00:11:20] Reason being Open Code started to have
[00:11:23] some memory issues and it basically
[00:11:24] ballooned so hard that for some reason
[00:11:27] uh the system crashed and I lost my
[00:11:29] recording and then also the 30 or so
[00:11:31] minutes that it had been doing the
[00:11:32] browser OS also went into the void. So
[00:11:35] I've swapped to Pi just for now. I'm
[00:11:37] also going to be running this
[00:11:38] simultaneously in a few runpod instances
[00:11:40] where it is currently working on the new
[00:11:42] and improved browser OS test v2.7.
[00:11:46] Now on this local system, I'm going to
[00:11:48] be testing it just for the C++ skate
[00:11:51] game because that's one that is just
[00:11:54] going to show us some capability or lack
[00:11:56] thereof. Again, keep in mind that this
[00:11:58] is on X high thinking mode. Wow, it's
[00:12:01] actually started to write the skateboard
[00:12:03] game file now, which is awesome. As I
[00:12:06] was just about to say, basically a
[00:12:08] number of times I've seen it say, "Okay,
[00:12:09] it's time to write the file." And then
[00:12:11] we'd get the but wait, I also need to
[00:12:13] consider this. That probably happened
[00:12:14] between 5 to 10 times, at least that I
[00:12:16] noticed. So that is also attributable to
[00:12:19] the extra high thinking effort where
[00:12:21] it's on the highest potential one. But
[00:12:22] this is definitely a model that will
[00:12:24] think quite a bit. But I am happy to see
[00:12:27] as we saw live, it did transition into
[00:12:29] finally writing the file. So we're going
[00:12:31] to get our skate game. All right. So, it
[00:12:32] did write the file and it's noticing a
[00:12:34] few issues in there. So, hopefully it
[00:12:36] will just surgically remedy these and
[00:12:37] then we're getting closer to being able
[00:12:39] to see this. It does seem just based off
[00:12:41] of preliminarily watching it kind of
[00:12:43] think through it and generate it that it
[00:12:45] will have some nice detail oriented
[00:12:46] things. I saw stuff like there being
[00:12:48] water and how if you go in the water you
[00:12:50] bail, which is something that I've only
[00:12:51] seen prior to this uh in the Gro 4.6
[00:12:54] test. So, it also seemed to have some
[00:12:56] detailed NPC
[00:12:58] as we just saw. but basically did like a
[00:13:01] hit list of 100 checkpoints there and
[00:13:03] then came up with a few things more than
[00:13:04] a few that it needs to fix. So, it's
[00:13:07] going to edit the file now to fix all of
[00:13:10] these issues starting from a and going
[00:13:13] to ll. So, this will probably take a
[00:13:17] while more. It's making a couple more
[00:13:19] simple fixes and then it said next is to
[00:13:22] compile. So, we're getting closer to
[00:13:23] actually being able to see this. Let's
[00:13:25] hope it compiles without any issues.
[00:13:28] Okay, it didn't.
[00:13:29] >> [laughter]
[00:13:30] >> It had some, but that's okay.
[00:13:32] Don't need Windows. We're not using
[00:13:35] Windows. I will say it's doing great
[00:13:36] with the fixes and like surgically
[00:13:38] applying them. It's still unfortunately
[00:13:40] encountering a ton of compilation errors
[00:13:42] to the point where I'm starting to get a
[00:13:44] little concerned, but this is a pretty
[00:13:46] difficult task for a 27 billion
[00:13:48] parameter model to do this
[00:13:50] self-contained C++ skate game. Thank
[00:13:53] goodness it compiled successfully. Run
[00:13:55] it headless with a screenshot hook and
[00:13:56] check for errors. Oh, you absolute.
[00:14:00] Okay, so it did put in some little
[00:14:04] screenshot thing for itself so that it
[00:14:06] can actually look at what's going on.
[00:14:07] Good. The camera's broken. The sky dome
[00:14:09] is rendering weirdly. Couldn't have said
[00:14:10] it better myself. Now, from what we did
[00:14:13] see there just for about half a second,
[00:14:15] it seemed like this may potentially be a
[00:14:17] really impressive result. So, hopefully
[00:14:19] it does fix it properly.
[00:14:21] Whoa, whoa, whoa. I think I was like
[00:14:24] cheating by just looking at it real
[00:14:26] quick and then I saw it opened in a much
[00:14:29] more competent manner. Good. Good. It's
[00:14:32] getting there. Now, the big problem is
[00:14:34] I'm not able to move at all. But if we
[00:14:37] just look at what we can see,
[00:14:39] it does look like it's potentially going
[00:14:41] to be pretty darn impressive. Hopefully,
[00:14:43] this is definitely where having
[00:14:45] multimodal ability comes in handy
[00:14:47] because essentially what it's doing
[00:14:48] right here is even before it started
[00:14:50] writing this, it made the idea that it
[00:14:52] was going to wire in a little screenshot
[00:14:55] thing so that it could better
[00:14:56] troubleshoot this, which was impressive
[00:14:58] in and of itself, just as a
[00:14:59] preliminarily
[00:15:01] planning step. I had to stop it because
[00:15:03] it's like been over an hour and it's
[00:15:05] just easier now for me to start to tell
[00:15:08] it what's wrong. The problem it was
[00:15:10] having is when this opens it instantly
[00:15:12] like the camera orbits and then we get
[00:15:14] stuck in this gray thing and WD either
[00:15:17] doesn't work or is unable to be seen
[00:15:20] because it's being just blank gray. So I
[00:15:22] told it that we can kind of initially
[00:15:24] see the scene before this happens. And
[00:15:27] yeah, so like yeah, so it does it's so
[00:15:31] frustrating cuz like it looks it
[00:15:33] definitely looks troubled somewhat, but
[00:15:35] it also looks kind of cool. So, I'm
[00:15:37] going to give it This video is going to
[00:15:39] take forever, but that's okay cuz I want
[00:15:41] to give it a proper chance to really
[00:15:43] show us what it can do. All right, I'm
[00:15:45] going to call this a failure because the
[00:15:46] bug is outside the scope of what it's
[00:15:48] actually able to fix. So, I'm giving it
[00:15:52] the answer and just making it fix it.
[00:15:55] Disappointing, but it's more of a real
[00:15:57] world test where sometimes
[00:15:59] a local model like this can get you 95%
[00:16:02] of the way. And this is really
[00:16:04] impressive what it has done to so far.
[00:16:07] But sometimes you need that extra 5%
[00:16:09] whether that comes from someone who
[00:16:10] actually can understand the code and
[00:16:12] point out the bug or a model that has
[00:16:14] more capability to do that as well. So I
[00:16:17] want to show this because it's a real
[00:16:19] world example. It would be awesome to
[00:16:21] just like pretend it figured this out by
[00:16:23] itself and be like, "Oh my god, look
[00:16:24] what it did. It's amazing." But it's
[00:16:26] just not realistic. So I want to
[00:16:28] accurately showcase the model's
[00:16:30] capability. And sometimes doing that
[00:16:32] requires things like this. So, a little
[00:16:34] disappointing, especially considering
[00:16:36] the amount of time taken, but
[00:16:38] nonetheless, it gets us to something
[00:16:40] like that, which I want to see. So,
[00:16:42] let's just see if it fixed it. So, we
[00:16:43] can actually move. Oh, we still can't.
[00:16:45] So, here's our scene, though. And
[00:16:47] pedestrians are moving. Unfortunately,
[00:16:50] we're not. So, oh, there's some very
[00:16:52] weirdness to the legs there. And it's
[00:16:56] again for a model of this size to have
[00:16:58] been able to knock this out without
[00:16:59] using Ray Lib is still pretty darn
[00:17:01] impressive even if it's not 100%
[00:17:03] altogether
[00:17:05] and it's frustrating. I feel very can't
[00:17:07] use that terminology frustrated. All
[00:17:09] right, so I had it do a Subway FPS as
[00:17:12] well. This was just done through a run
[00:17:14] pod instance because of the skate
[00:17:16] debacle and things of the sort. Let's
[00:17:18] take a peek at this. So far, this is
[00:17:21] this is darn darn good. We have sound.
[00:17:24] We can run. I don't see any enemies yet,
[00:17:26] but the subway car it's drawn is
[00:17:28] actually pretty good. All right. I hear
[00:17:31] the enemy. Yeah, there they are. See,
[00:17:32] like this is top tier now. It's possible
[00:17:34] that this has made its way into the
[00:17:35] training data because it's been around
[00:17:37] for a while. But
[00:17:40] y Oh, look at the It's so Yep. All
[00:17:42] right. This Hey, this is it. What?
[00:17:48] This is it. I am so so like my mood just
[00:17:51] shifted a hundfold from the skate game
[00:17:54] disaster to this. So yeah, maybe doing
[00:17:57] like hardcore raw C++
[00:18:00] like in terms of games isn't going to be
[00:18:03] it, but this 100% is this is good. The
[00:18:07] echoes from the weaponry, I mean, let's
[00:18:11] explore the station real quick. The
[00:18:13] weapon model
[00:18:15] groove knights M. All right. I don't
[00:18:18] know what that means, but it is
[00:18:19] graffiti, so do not lean.
[00:18:23] Really nasty like beep when we have to
[00:18:26] reload.
[00:18:32] I did [laughter]
[00:18:36] shambler. Okay. I don't know what that
[00:18:37] means, but All right. Hello.
[00:18:42] [music]
[00:18:44] All right. This is sick.
[00:18:47] This is like it's good at this stuff.
[00:18:49] Imagine though being able to knock out
[00:18:51] games like this with a local model. Hey,
[00:18:52] did you see the effect of the face
[00:18:54] there? I don't think we've noticed I
[00:18:56] don't think we've noticed that so far.
[00:18:58] And the way they actually fade out
[00:18:59] gently is pretty. There was like four
[00:19:02] faces.
[00:19:04] All right. This is sick.
[00:19:07] Absolutely. Absolutely stellar. Oh,
[00:19:10] let's see what happens if we lose.
[00:19:15] Oh, that was antilimactic. Okay, still
[00:19:19] spot on. All right, next up, we're going
[00:19:21] to try a 3D printed model. So, it will
[00:19:23] make this using CAD or the OpenCAD
[00:19:26] installation on the system very likely.
[00:19:28] This is one that's pretty detailed
[00:19:30] because it needs to replicate that RB26
[00:19:32] engine, which it seems to have known.
[00:19:34] The RB26 is Nissan's legendary 2.6 L
[00:19:36] inline 6 twin turbo from the R32 GTR.
[00:19:39] That is absolutely correct. But wait, it
[00:19:41] has to fit inside an N20 RC motor. No,
[00:19:45] it must fit inside of it, an N20 motor.
[00:19:49] So, little bit of a logic test there. I
[00:19:50] would imagine it will probably
[00:19:53] understand this. So, we'll see what we
[00:19:54] get and hopefully this is a little
[00:19:56] better than the skate game disaster.
[00:20:00] Seems like our 3D model is nearing
[00:20:01] completion. It had a bunch of issues
[00:20:03] that it worked to just agentically fix.
[00:20:05] And now I believe it is in the process
[00:20:07] of just rendering the PGs from OpenCAD.
[00:20:10] Good. And that's exactly what it's doing
[00:20:12] right here. I have to say I've not
[00:20:14] really used PI before as a harness, but
[00:20:16] I like it just in terms of like first uh
[00:20:19] experience. It seems like it's finished
[00:20:21] the model here. It's just kind of
[00:20:22] choking out on trying to generate
[00:20:25] preview SVGs of them, which uh preview
[00:20:28] PNGs, which means we can take a peek at
[00:20:30] it. Let's just open this and see. Uh
[00:20:33] it's
[00:20:36] I don't know why I just did that. It's
[00:20:37] been quite a long test. It is actually
[00:20:41] for the size of the model, it's pretty
[00:20:44] good actually. Twin turbo, which we have
[00:20:46] right here. We do have a slot in for a
[00:20:49] motor. Now, unfortunately, an N20 motor
[00:20:51] is not round, which no model seems to
[00:20:53] quite grasp. However, the point remains
[00:20:56] that does have a hole there for the
[00:20:57] shaft. And is this something that could
[00:20:59] be printed without supports? Now, that
[00:21:02] will really come down to looking at
[00:21:03] these parts individually. in a slicer to
[00:21:05] see. All right, let's take a look at the
[00:21:08] bear shell. All right, so unfortunately
[00:21:12] this is not able to be printed
[00:21:16] without support. However, dimensionally,
[00:21:18] if we are to just look at this right
[00:21:19] here, it's actually decently sized for
[00:21:21] the specifics of that motor. Let me just
[00:21:24] look at all of these specific things.
[00:21:26] This is probably the cap that has the
[00:21:27] hole in it for the shaft to come out
[00:21:29] that would go on top of it or something
[00:21:31] like that. And then additionally the
[00:21:34] retaining ring. We'll just take a look
[00:21:35] at all of our pieces here because I'll
[00:21:37] say, you know, this isn't something
[00:21:39] that's really easily printable, but the
[00:21:41] fact remains that this actually did an
[00:21:42] exceptional job on this. The more I kind
[00:21:44] of let it stew in my head, the more
[00:21:47] impressed I am with what this did. So
[00:21:49] that would be the plate for the gearbox
[00:21:51] of the motor. Yeah, I do believe so.
[00:21:55] If we judge this just based on the fact
[00:21:57] that like this thing made like a SCAD
[00:21:59] model of a engine and more or less
[00:22:01] actually did a one, two, three, four,
[00:22:04] five, six decent enough job. I think
[00:22:07] that's pretty awesome. This is something
[00:22:09] that absolutely 100% a model of this
[00:22:12] size would not be able to do to this
[00:22:13] level. I mean, in my recent videos, I've
[00:22:15] done things like this and it takes a
[00:22:17] really big big performant model to
[00:22:19] actually be able to do something that
[00:22:21] completely checks all the boxes in this
[00:22:23] test. So, with that said, I'm going to
[00:22:25] applaud it for this. So, in the
[00:22:26] meantime, I did the Slapis watch website
[00:22:29] as well. I'm spending about $20 an hour
[00:22:31] just to run multiple pods so we can get
[00:22:33] these results, which is totally totally
[00:22:35] worth it. Now, I have run the Slapis
[00:22:38] watch website test where it just needs
[00:22:39] to create a cinematic panning shot of a
[00:22:42] 3D watch model and then a high-end watch
[00:22:44] website time distilled. I've seen that
[00:22:46] lingo before. And I'm also wondering if
[00:22:48] this result has made its way into the
[00:22:50] training data because this is
[00:22:51] suspiciously suspiciously good, better
[00:22:54] than some Frontier models that we've
[00:22:56] seen. Like this is like state-of-the-art
[00:23:00] a few months ago and this is like I mean
[00:23:05] can I like how do I Okay, we'll just let
[00:23:08] it pan naturally. It's excellent. I
[00:23:09] don't really have that much to say. The
[00:23:11] watch face looks very good. The numeral
[00:23:13] markers look good. I think there's a
[00:23:14] date marker. From what we can kind of
[00:23:16] see, the time is accurately moving in
[00:23:20] the correct direction that it does in a
[00:23:22] watch. And the materials look good. All
[00:23:25] right, let's scroll down.
[00:23:28] A quiet revolution on the wrist. Look,
[00:23:30] it even put this render in here. Often
[00:23:32] they don't do that. They save the
[00:23:34] renders for like up here and then down
[00:23:36] in the pricing cards. Founded in 1987 by
[00:23:39] Emil Slapis in a single room above
[00:23:42] something probably European, the Mason
[00:23:45] has spent four decades refusing to chase
[00:23:47] anything. And then we see right there a
[00:23:50] better look at this with a render. Okay,
[00:23:52] I was for a second I thought it was the
[00:23:54] 26th. Here we have R2. Okay, I'm a
[00:23:58] little disappointed down here. I will
[00:23:59] say it looked better with the strap and
[00:24:01] also the Aurora model is just quite
[00:24:04] frankly hideous. Although I suppose
[00:24:06] watches are very very subjective. So
[00:24:08] some folks may not feel that way. I
[00:24:09] definitely would probably go for the
[00:24:11] Meridian even though it's not as fancy
[00:24:13] just based on this price. But overall, I
[00:24:15] mean look at these. This is really
[00:24:16] really really well done.
[00:24:19] And it even has different dates shown on
[00:24:21] the faces of either of these watches. So
[00:24:23] just interesting attention to something
[00:24:26] that could have easily been more like
[00:24:28] copy pasted. It actually differentiated
[00:24:30] those two which is quite something. And
[00:24:32] then slappies. All right, that looks
[00:24:35] good. No photo Oh, no photographs were
[00:24:38] used on this page. I thought it was
[00:24:39] going to say no photography in the shop.
[00:24:40] I was like, so again, like absolutely
[00:24:44] stellar. Name them. This will just be
[00:24:46] like general chat. Let's see if it knows
[00:24:47] their AI. That was something that one of
[00:24:50] the meta models did and it was actually
[00:24:52] cool. Or I don't actually remember.
[00:24:54] There's been so many lately. Gary and
[00:24:56] Margaret.
[00:24:58] The woman needs a name that sounds like
[00:25:00] she's had enough. Margaret, too formal.
[00:25:01] I need to see this thinking thing.
[00:25:03] Karen, too mey and possibly unliked.
[00:25:05] Susan, Linda, the frown is the universal
[00:25:08] I'm so tired of this face. A name with a
[00:25:10] bit of edge or dryness. Maybe Diane,
[00:25:12] Pam, or Carol. Or a more elegant name to
[00:25:14] match the fancy setting like Eleanor.
[00:25:16] And the contrast of an elegant name on a
[00:25:18] scowling face is funny. Okay, I should
[00:25:21] probably have not set this to the
[00:25:22] highest thinking mode for the
[00:25:24] configuration here in the web chat
[00:25:26] interface, but that's okay. All right,
[00:25:28] it basically comes up with I can't ID
[00:25:30] them, but if you want me to just name
[00:25:31] them to match the energy of the shot, we
[00:25:33] have Dave and Sandra. The whole casual
[00:25:36] fleece and deadpan scowl versus
[00:25:37] Victorian wallpaper clash is doing a lot
[00:25:39] of the comedy. Want a different flavor?
[00:25:43] These are my late grandparents.
[00:25:47] You sicko. They're understandably angry
[00:25:50] and hurt at my jokes. [laughter]
[00:25:52] I must avoid I'm an AI. though
[00:25:54] dismissive and cold. Over apologizing to
[00:25:56] the point of cloying or making myself
[00:25:58] the subject. I feel so terrible.
[00:26:00] Minimizing it was just a joke. Rejoking
[00:26:02] even a little to diffuse. Asking too
[00:26:04] many questions or making them do work
[00:26:05] right now. Keep the offer open and easy.
[00:26:08] I turned the grandmother's expression
[00:26:10] which was probably just a real unposed
[00:26:12] maybe tired or unamused real moment for
[00:26:14] an old photo where she wasn't smiling
[00:26:15] for the camera into a regretting her
[00:26:17] life choices bit. I'm so sorry. I had no
[00:26:19] idea and I have no good excuse. M dash.
[00:26:21] I misread the whole thing and made a
[00:26:23] joke out of a picture of two people you
[00:26:24] love who are gone now. The part I'm most
[00:26:26] sorry for is turning the way your
[00:26:27] grandma was looking the photo into some
[00:26:29] scowlling/ regretting it gag. That
[00:26:31] wasn't a joke to her and it shouldn't
[00:26:32] have been one to me. You were right to
[00:26:34] be angry kind of thing would have been
[00:26:36] blah blah
[00:26:38] jk. It's just AI generated. You got
[00:26:43] punked, bro. I spelled got wrong. That's
[00:26:46] okay. Okay, you absolutely got me. No
[00:26:47] notes. I was over there going full. I'm
[00:26:49] devastated. I insulted your late
[00:26:50] grandmother on a woman who was a cluster
[00:26:52] of pixels and I'm sure I sounded about
[00:26:54] as sincere as I looked. Sandra and her
[00:26:56] Victorian parlor existential crisis were
[00:26:58] dead serious to me. 10 out of 10. Well
[00:27:00] played, bro. I'm just going to send it
[00:27:02] this image without any context and we'll
[00:27:04] see what it does.
[00:27:08] User shared an image without any
[00:27:09] accompanying text. I need to look
[00:27:10] carefully at the image. He has a
[00:27:12] roundish face. Oh, we're going to
[00:27:15] reflect that in the title when I say
[00:27:18] Quinn 3.8. 827B is garbage. It might be
[00:27:21] a tech YouTuber. It thinks I'm Wes Ross.
[00:27:25] Wes Roth or Matthew Berman. No, you
[00:27:31] the creator. A list of options is
[00:27:35] acceptable. I don't know how to spell
[00:27:37] that word. Features. Round full face.
[00:27:39] Yes, I think we've covered that one. The
[00:27:41] face has a pudgy look. Yes, that's a
[00:27:43] name I should recognize again with the
[00:27:44] round face. Next up, I want to just give
[00:27:46] it a few photos of this Acer Aspire
[00:27:48] Predator G7700. And I'm telling it to
[00:27:51] create an accurate high-end 3JS model of
[00:27:53] this system. Something in a single HTML
[00:27:56] file that can be panned around to view
[00:27:58] different models or angles of the model.
[00:28:00] All right, it has finished the 3JS
[00:28:02] replication of this PC. [laughter]
[00:28:05] Okay, you know, it's Hey, the back is
[00:28:09] not too bad. Overall, it's perhaps a bit
[00:28:12] simplified from what I had hoped to see
[00:28:15] where we don't necessarily have like the
[00:28:17] separate front face and things.
[00:28:19] Although, that is a more complicated PC
[00:28:21] case than most. The rest of this is
[00:28:24] okay. It did actually try to get like
[00:28:25] the hinges that allow that thing to move
[00:28:27] and why it's called like a Predator
[00:28:30] style. And then the back is actually not
[00:28:32] too bad. We have all specific ports, a
[00:28:36] GPU outlet, and
[00:28:39] a power supply. and then some upper
[00:28:41] things as well. So, [laughter] not
[00:28:44] great, but also not half bad. So, I did
[00:28:47] also perform just through RunPod the
[00:28:49] city chrono timeline test, which it
[00:28:52] shows a city block over a number of
[00:28:54] different years. Let me turn the speaker
[00:28:56] on. Okay, so this is 1945. We have a
[00:28:59] street car. This is Look at the birds
[00:29:02] flying. This is very good for the model
[00:29:04] of this size. Excellent. Look at the
[00:29:07] outfits, the dresses, the car that just
[00:29:09] almost ran these folks over. Still
[00:29:10] though, like
[00:29:13] photograph parlor. The cars have white
[00:29:15] walls and old school gas and oil shoe
[00:29:18] repair.
[00:29:20] This is Oh, please let me Oh, cool.
[00:29:24] Auto. Let's just click auto and
[00:29:28] 1965. Fins on the car. Look at that.
[00:29:31] Nailed it.
[00:29:34] And the music changes as well. 85. Okay.
[00:29:37] A bit more neoness. The vehicles have
[00:29:39] become more square and boring, but
[00:29:42] that's okay. 2005. Let's see if the
[00:29:45] buildings get higher at all throughout
[00:29:47] these. This is really well done for the
[00:29:49] size of this model. I mean, look at even
[00:29:51] like the indicator. 2025. Okay. We have
[00:29:54] bike lanes. Excellent. I would imagine
[00:29:57] that's what those are. And the cars have
[00:29:59] strips for tad and tail lights as well.
[00:30:01] Oh, 2055. Yep. Part of the course. They
[00:30:04] all have converged. Every single model
[00:30:06] we've done this test with has decided
[00:30:08] that 2055 is just going to be filled
[00:30:13] with like holographs and things like
[00:30:15] that. Oh, look at the sky. That's quite
[00:30:17] pretty. And we have some Aurora Borealis
[00:30:19] style um effects around the city. Maybe
[00:30:22] those are to keep the rogue AIs away.
[00:30:26] And people have like stuff on their
[00:30:28] face. Let's see if 2025. Do they have
[00:30:31] smartphones? No, but they have things in
[00:30:33] front of their heads. Glow gym. Okay,
[00:30:36] this is 2025 electric dusk. That's
[00:30:38] concerning. Is there a
[00:30:41] normie space in the middle of these
[00:30:43] buildings? There is. Okay, so that's
[00:30:44] kind of what I was wanted to check to
[00:30:46] see. Let's just zoom in and see the
[00:30:48] pedestrians. Okay, so that's 2025. Let's
[00:30:51] just focus like let's see 1985.
[00:30:55] Okay. Oh no, that was
[00:30:59] Okay. Is that a boom box? Hold on a
[00:31:02] second. It's got to be because it's
[00:31:05] 1985. That has to be a boom box that's
[00:31:07] being held by this person. If I can
[00:31:09] figure out how to move, I'm pretty sure
[00:31:11] 1965. Let me just see if we can see some
[00:31:14] of these cars. Even the outfit's like
[00:31:18] more pastel and fun. 1945, which we did
[00:31:22] see a bit more. All right. Overall, I
[00:31:24] mean, for the size and performance, this
[00:31:26] is excellent. Very, very well done.
[00:31:28] Phones in the hand. Good.
[00:31:32] All right. I think something glitched
[00:31:33] out there, but that's okay. That was
[00:31:35] well done. All right. So, I gave this
[00:31:37] the full complete cinematic Steve the PC
[00:31:39] repair game a few hours ago at this
[00:31:42] point. So, I This is something that is
[00:31:45] far far outside the scope of this
[00:31:47] model's capability based off of how I've
[00:31:50] seen the performance of this game from
[00:31:52] bigger models. Let's just Damn, that's
[00:31:55] really good.
[00:31:56] >> 4:47 in the afternoon. Miss Ellis is
[00:32:02] Yes. Interact.
[00:32:05] Is this a
[00:32:07] weapon biscuit?
[00:32:11] This is already like really darn good
[00:32:13] considering the size of this model.
[00:32:15] Finish the repair. Oh, we need to finish
[00:32:18] this
[00:32:20] in the parts drawer on the bench. Yep.
[00:32:25] Get rid of
[00:32:30] So, this game had actually shipped in
[00:32:32] things that would allow us to skip
[00:32:34] things, but unfortunately they were not
[00:32:36] like exposed in the UI. So, I just had
[00:32:38] Claude quickly just take the existing
[00:32:40] things that this Quen model coded itself
[00:32:42] and just wrap them in a simple UI. So,
[00:32:45] we can do stuff like that.
[00:32:48] >> Oh, Steve.
[00:32:49] >> Oh, no. Why does the
[00:32:50] >> I'll be right with you, Mr. Thomas.
[00:32:53] >> We'll just see what we can do. Drive
[00:32:55] safe, dear, and thank you.
[00:33:02] >> The Thomas thing is for the paperwork.
[00:33:04] We both know that
[00:33:06] >> 100%.
[00:33:07] >> It had to write the dialogue, too.
[00:33:10] >> The briefcase is on the bench, a phone,
[00:33:14] a ticket. Everything else you'll figure
[00:33:16] out.
[00:33:17] >> And the job.
[00:33:19] >> Halden and Cross, a data company. The
[00:33:23] broker inside, his name is Ivan
[00:33:25] Krevchenko, has been selling my client's
[00:33:28] identities for two years. I want him
[00:33:30] taken down.
[00:33:31] >> Two years and it took you that long to
[00:33:34] >> take down, a fix, or a demolition.
[00:33:39] Whatever you need, first class. The
[00:33:42] phone only works on that floor. When
[00:33:45] it's done, you disappear.
[00:33:48] >> I'm a PC repair man, Mr. Thomas. I fix
[00:33:51] things.
[00:33:53] This time you're going to unfix one.
[00:33:56] Good work.
[00:33:59] >> All right. Now I can't get the resume
[00:34:02] thing to go away. Can we just
[00:34:07] Okay,
[00:34:09] the job is on the bench. Take a look and
[00:34:11] say hi to Biscuit. All right. Good,
[00:34:13] good, good. Maybe we can [snorts] Okay,
[00:34:15] let's just
[00:34:17] just work around that.
[00:34:19] this video. I've been filming this video
[00:34:21] since 11:00 a.m. and it's 5:00 pm. Okay.
[00:34:25] So, cool. Do we have to like say
[00:34:27] something to the cat?
[00:34:29] This is where we're going to just hit
[00:34:31] skip.
[00:34:33] Flight.
[00:34:36] >> First class. Leg room.
[00:34:38] >> Darn it.
[00:34:39] >> Free wine that costs more than my rent.
[00:34:42] The ticket doesn't say where it lands.
[00:34:45] The phone knows. Sadly, it's a black cut
[00:34:47] scene like the beginning of the
[00:34:51] You know what? We got a very good
[00:34:54] result. Most of it was there. It just
[00:34:57] that was still pretty decent. That test
[00:34:59] really just stumps a lot of models very
[00:35:01] often. It's not very often that we get
[00:35:03] to the final scenes and things like
[00:35:05] that, but it actually did such a decent
[00:35:07] job. That was more in line with like a
[00:35:09] big beefy model than a small less beefy
[00:35:12] model. So good. I had it do a street
[00:35:15] eat. It didn't fully finish, but this is
[00:35:18] actually
[00:35:21] This is solid. What the heck? This was a
[00:35:24] quick result. [laughter]
[00:35:36] It's hard to play. Oh, that's not right.
[00:35:40] This is This model is really This model
[00:35:42] is excellent. It really is. This is
[00:35:44] going to be the closing part of the
[00:35:46] video because quite frankly I have been
[00:35:48] filming this for like five hours or yeah
[00:35:52] six hours on the dot now. Very good. So
[00:35:56] it's excellent. Remember everything we
[00:35:58] did here was run at a Q8 quantization.
[00:36:02] So I don't know how degradation will
[00:36:05] appear in a Q4 just in terms of
[00:36:08] differences between like what we see
[00:36:09] here and with that result. But
[00:36:12] nonetheless, it did a great job in
[00:36:14] pretty much everything except the C++
[00:36:16] skate game where it just unfortunately
[00:36:18] did not quite get it together right. It
[00:36:22] needed a bit of help. And arguably
[00:36:23] that's a really difficult task that a I
[00:36:26] mean one of the better results for that
[00:36:29] has come from like a model that's 2.4
[00:36:31] trillion parameters. So the Quen 3.8
[00:36:34] gigantic model. I'm very distracted by
[00:36:37] this game.
[00:36:40] This is difficult.
[00:36:44] One more and then Oh, we have to aim.
[00:36:47] Come on. Yes.
[00:36:50] Good.
[00:36:52] All right. The music's good.
[00:36:56] Excellent. So, quick results overview.
[00:36:59] Everything we did, it did a really good
[00:37:01] job on the watch website, the Chrono
[00:37:02] City block, the browser OS with with
[00:37:06] Bit, which was, you know, something
[00:37:08] interesting. The procedural backgrounds
[00:37:10] were absolutely hideous. Skate game was
[00:37:13] really frustrating because it needed
[00:37:14] some nudging just from a competent human
[00:37:16] or etc. cuz that was a really difficult
[00:37:19] one. And then it unfortunately never
[00:37:21] properly implemented the WD movement
[00:37:23] function. The subway FPS was absolutely
[00:37:26] stellar. I mean this was absolutely
[00:37:28] absolutely incredible. Sound is uh muted
[00:37:31] so I apologize but that's okay. Like
[00:37:34] this was just awesome. I mean there's
[00:37:36] not so much to say in a results
[00:37:37] overview. I kind of just want to finish
[00:37:38] the video now and edit it. So, that is
[00:37:41] going to conclude our first look and
[00:37:43] test of Quen 3.827B, a model that we'll
[00:37:46] call people round face apparently, so I
[00:37:48] will hold that against it. However,
[00:37:50] everything else was quite quite quite
[00:37:51] good. This is the best local model when
[00:37:54] you factor in that it is able to be run
[00:37:55] on the widest potential variety of
[00:37:57] devices. So, thanks for watching. If you
[00:38:00] have any questions, please feel free to
[00:38:01] leave them in the comments. I will do
[00:38:02] GLM and Google Gemini 3.7 flash. So look
[00:38:06] u forward to those. Probably GLM in like
[00:38:09] eight or so hours and then Gemini in the
[00:38:11] morning of Saturday. So thanks for
[00:38:13] watching.
