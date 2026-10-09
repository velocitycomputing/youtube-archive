---
record_id: "youtube:VmT7SU81tuM"
video_id: VmT7SU81tuM
title: GLM 5.3 Flash Is HERE – Is THIS Better Than the FULL GLM 5.3?
channel: Bijan Bowen
url: "https://www.youtube.com/watch?v=VmT7SU81tuM"
watched_date: 2026-08-28
watched_at: "2026-08-28T12:00:00Z"
watch_count: 1
duration_seconds: 2215
source: youtube-history-browser
added_date: 
history_label: Aug 28
history_order: 51
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 222
transcript_status: fetched
transcript_content_hash: 08612ad4b7420e45bd8fe6ce7cfa69bda1ca39e3c9a9ab16505be882f5d0989c
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video covers the release of GLM 5.3 Flash, revealed to be the stealth "ox alpha" model that ran free on OpenRouter for about a week. It is an open-weights, 320B-parameter mixture-of-experts model with 18B active parameters, and the creator says it is close to Claude Opus 4.8. It has a hybrid attention design for cheaper long context and uses MHC, which DeepSeek proposed in December 2025. After the promotional 50% discount ends, pricing is about $0.15 per million input tokens and $0.50 per million output tokens, which is cheaper than DeepSeek V4 Flash Vision. The creator notes that the free period was served entirely on domestic Chinese AI chips. They then ran it in Z Code (Z.ai's coding app) against the same tests they gave DeepSeek V4 Flash. The Mac OS 9 browser OS took 1h07m and came out solid, with working sound, a wallpaper lab and a "Chronos Snap" session-restore feature, but its GTA clone was nearly unplayable. The mid-80s 3D wrestling game took 1h25m and was decent but hard to play, which the creator thinks beats the full GLM 5.3's attempt. The C++ Terrain 2 (Deformers) recreation took 53 minutes and worked well, with checkpoints, a minimap, water slowdown and multiple cameras. The C++ NYC skateboard game took 2h17m and was weak, with z-fighting and rendering problems. For the Google Coral USB accelerator task, the model trained a 41k-parameter CNN by behavioral cloning to drive a motorcycle game. The Coral itself didn't work, and INT8 quantization wrecked the steering (accuracy fell from 74% to 47%), but the best float model still cut collisions sharply versus random input (0.48 hits/km). The Blender-plus-Godot "Street Yeet" game, built in about 52 minutes, was the standout, with 17 generated models, combos, and a working city. The creator's overall verdict is that it is strong for a Flash model but probably slightly behind DeepSeek on the browser OS test. The transcript was truncated, so the ending isn't covered.

For you, the practical points are these. The weights are on Hugging Face now, so you can try it locally if you have the hardware. Expect heavy memory needs for a 320B model, so wait for community quants such as Unsloth's. At about $0.15 in and $0.50 out per million tokens, it is a cheap option for agentic coding if you're comparing it with DeepSeek V4 Flash or the full GLM 5.3. Treat the speed with caution: the long agentic tasks took 1 to 2+ hours despite the "Flash" name. Its strengths are long, multi-step builds that include assets, such as Blender-to-Godot pipelines and C++ game recreations from a reference image. It is weaker on tight real-time game feel (controls, collision, rendering polish). If you use the GLM coding plan, expect uneven reliability, since the creator reports it as hit-or-miss and the free stealth period had errors under load. If you test it yourself, reuse the creator's prompts (browser OS from a reference screenshot, C++ recreation from a web search, tiny-NN game agent) and compare the results against your current model. For edge-AI work, keep in mind that tiny steering-type nets can break under INT8 quantization, so check accuracy after quantizing before you deploy.

## Transcript

[00:00:00] Let's see how ye eatable this city is.
[00:00:02] Yep. Oh, look at it's spraying water.
[00:00:04] Good, good attention to detail. GLM 5.3
[00:00:08] Flash has been released and revealed to
[00:00:10] be the mysterious ox alpha model that
[00:00:12] was on Open Router for free for the past
[00:00:14] week or so. This is something that I
[00:00:16] think got one of the largest amounts of
[00:00:18] interest for a stealth model that I've
[00:00:20] seen before. And now that we see that it
[00:00:22] is existing in the world, it's open
[00:00:24] weights, it's not super large, and it is
[00:00:26] pretty darn cheap, I think the
[00:00:28] excitement was warranted. So before we
[00:00:29] get into it, do feel free to subscribe
[00:00:31] so we can hit the 75K figure and then
[00:00:33] onwards to the 100K plaque. In
[00:00:35] additionally to that, let's take a look
[00:00:37] at some of the interesting things about
[00:00:38] this model and then we'll jump into some
[00:00:40] fun testing which is going to be
[00:00:42] slightly different from some of our
[00:00:43] normal tests. I don't want there to be a
[00:00:45] lot of fatigue and like the same exact
[00:00:47] test. So GLM 5.3 flash is a 320 billion
[00:00:51] parameter mixture of experts model with
[00:00:53] 18 billion active. And they mention here
[00:00:55] that it is basically within striking
[00:00:57] distance of Claude Opus 4.8 which is
[00:00:59] still a very highly regarded model as it
[00:01:02] seems Opus 5 has a lot of love it or
[00:01:05] hate it experience from the community.
[00:01:07] So, additionally to this and something
[00:01:09] that I think is worthy of specific
[00:01:11] mention is the fact that throughout this
[00:01:13] free period on open router when it was
[00:01:15] stealth, the amount of free tokens that
[00:01:18] folks had allocated, whether it be open
[00:01:20] code saying that I think they could
[00:01:22] handle 100 trillion tokens per day and
[00:01:24] then essentially it was like almost
[00:01:26] unlimited. This was served entirely on
[00:01:29] domestic Chinese AI chips. And I think
[00:01:31] that is something to really kind of
[00:01:33] mention because currently Nvidia is like
[00:01:36] the de facto provider for a lot of AI
[00:01:39] inference. This is basically saying and
[00:01:41] showcasing, hey, we just had this model
[00:01:43] that was incredibly incredibly popular
[00:01:45] and it was all served on our own
[00:01:47] domestic chips, our own serving stack,
[00:01:49] and something that is definitely a
[00:01:50] consideration when I don't know, just
[00:01:54] it's interesting to see the evolution of
[00:01:57] other ways of doing things that are born
[00:02:00] out of competition. And it's definitely
[00:02:03] worthy of specifically mentioning that.
[00:02:05] And I would imagine almost more
[00:02:06] importantly than this model is the
[00:02:08] validation of that domestic serving
[00:02:11] right there. So just something I wanted
[00:02:12] to specifically take note of a couple of
[00:02:15] things in terms of like tech specs of
[00:02:16] this model. They mentioned that it has
[00:02:18] several architectural improvements. One
[00:02:21] of them being a hybrid architecture
[00:02:22] combining different types of attention.
[00:02:24] So essentially it can serve long context
[00:02:27] for cheaper but also maintain quality in
[00:02:29] longer generations. Something else is
[00:02:31] they have adopted MHC which is something
[00:02:33] that was proposed by DeepSeek in
[00:02:36] December of 2025 just in a way to as it
[00:02:40] says improve scaling efficiency. There
[00:02:42] is a technical paper for that that you
[00:02:43] can find online if you just search MHC
[00:02:46] DeepS. It should pop up pretty high in
[00:02:48] these search results. Now in terms of
[00:02:50] cost this model is incredibly cheap. Now
[00:02:52] we can see here on Open Router it is
[00:02:54] currently listed at 50% off. So let's
[00:02:56] assume that promotion has ended. That
[00:02:58] would essentially make this 15 cents per
[00:03:00] million in and 50 cents per million out.
[00:03:03] If this is truly competitive with
[00:03:05] something like Deep Seek Flash Vision
[00:03:07] Experimental, this is quite a bit
[00:03:09] cheaper than that model. So, it's
[00:03:10] interesting to see competition in that
[00:03:12] size range as well. Additionally to
[00:03:14] that, we have some benchmark information
[00:03:16] right here. But being that this was
[00:03:17] stealth as ox alpha, we are somewhat
[00:03:19] familiar with at least some of its
[00:03:21] capabilities, scoring pretty decently on
[00:03:23] deep s. When I started filming this,
[00:03:25] this was not currently available on
[00:03:27] hugging face. If you clicked the link,
[00:03:29] it was just 404ing. That has actually
[00:03:31] changed. So, if we click that right
[00:03:32] here, this model is truly open weights
[00:03:34] right now. I don't specifically know how
[00:03:37] much system memory you're going to need
[00:03:39] to run this. I don't believe we have any
[00:03:41] specific like VRAM figure and they'll
[00:03:43] inevitably have some like unsloth
[00:03:45] dynamic one-bit quant that will probably
[00:03:47] allow this to run on something that is
[00:03:50] not outrageous in the scheme of like a
[00:03:52] local AI system. So, for how we're going
[00:03:54] to be testing this today, I do have like
[00:03:56] the mid tier of the GLM coding plan.
[00:03:58] It's been hit or miss over the course of
[00:04:00] the few months I've had it. Sometimes it
[00:04:02] works great. Sometimes the models can be
[00:04:04] a bit frustrating. And that is something
[00:04:05] also folks were noticing. When this was
[00:04:08] free as ox alpha, it would sometimes
[00:04:10] stop or hit errors. I wouldn't
[00:04:12] necessarily judge this based off of that
[00:04:15] performance being that that thing was
[00:04:16] getting hammered pretty darn hard. We
[00:04:18] can see even in some of the graphs here
[00:04:20] in terms of how much use it had over the
[00:04:22] week that it was free on open router.
[00:04:24] But I currently am just going to be
[00:04:26] testing this and for the duration of the
[00:04:28] video using Zcode which is their native
[00:04:30] coding application. It is very very
[00:04:32] similar to codeex which I do like as I
[00:04:34] like codecs and this works very nicely
[00:04:36] on Ubuntu. I also want to mention that
[00:04:39] all cache for any previous runs using
[00:04:41] ZAI models or really anything has been
[00:04:44] removed. So there will be no
[00:04:45] contamination from previous model
[00:04:47] results. And because this model is
[00:04:49] something that's going to be pretty
[00:04:50] heavily compared to the Deepseek Flash
[00:04:52] Light Vision Experimental, I am going to
[00:04:55] give this the browser OS test that we
[00:04:57] gave to that model as well where it's
[00:04:59] the traditional one. However, included
[00:05:01] is this reference photo and it is told
[00:05:03] that we would like a pixel perfect
[00:05:04] replication of this as a browser OS and
[00:05:07] then including the GTA clone and things
[00:05:09] like this. This is of course a Mac OS 9
[00:05:12] screenshot. All right. So, after an hour
[00:05:13] and 7 minutes, which okay, it was on
[00:05:16] Mac's thinking, but not necessarily
[00:05:18] flash speed, it has completed the
[00:05:20] browser OS. Let's take a look at it. I
[00:05:22] have not seen this yet. So, here's our
[00:05:23] Mac OS 9 inspired browser OS. Okay,
[00:05:27] interesting. Good. Something I wanted to
[00:05:29] know is for the procedural wallpaper
[00:05:31] movement, would it still try to mirror
[00:05:32] what was shown in the image as like a
[00:05:34] reference? And it does. Okay, I will say
[00:05:38] the menu bars here are pretty good. The
[00:05:40] apple that was also shown in the image
[00:05:42] is perhaps a bit mangled, but we have
[00:05:45] chronos snap, which is going to be the
[00:05:47] special feature. Something I noticed
[00:05:49] about this specific test is that it's
[00:05:52] got a lot of like visual
[00:05:54] stuff. Okay, the hover effects here are
[00:05:57] more or less correct. These are black
[00:05:59] and that is kind of how it would look if
[00:06:00] actually using this Mac OS system. We
[00:06:03] have a bit of about Mac OS 9.
[00:06:06] Me close that. And I'm also going to
[00:06:08] turn the sound on as there is a speaker
[00:06:09] icon here. So there must be sound
[00:06:12] effects when we're actually clicking on
[00:06:13] things. We have a terminal or a text app
[00:06:17] editor. There are little button presses.
[00:06:20] Oh, okay. You have to press it twice.
[00:06:22] That works. But it's got cute little
[00:06:23] like beeps, I guess could be said now.
[00:06:26] Okay. It did actually make all of these
[00:06:28] selectable folders, but most of them, if
[00:06:31] not all, are probably just going to be
[00:06:32] empty. That was something I wanted to
[00:06:34] see as well because it just shows like
[00:06:36] attention to detail and whether or not
[00:06:37] it actually makes these more
[00:06:39] interactive. Permanently delete the
[00:06:41] items in the trash and it had a sound
[00:06:43] effect. That's good. We do have the
[00:06:45] correct time in our local in the top
[00:06:46] right. And I would imagine my home will
[00:06:49] probably have our applications in it.
[00:06:50] All right. Now is where the fun starts.
[00:06:53] I guess we'll just look through them one
[00:06:54] by one. This mail client does look very
[00:06:57] very period correct and I like seeing
[00:06:58] that. John Apples Seed. Okay. wallpaper
[00:07:02] lab department and like meta references
[00:07:04] to this rogue city.gov. It has a
[00:07:07] reference here to the GTA game. I have
[00:07:09] no idea what vehicle you're talking
[00:07:11] about. This is actually kind of clever.
[00:07:13] Dear citizen, we keep getting reports
[00:07:14] about a light blue compact doing donuts
[00:07:16] on Avenue approximately 900 mph in
[00:07:19] reverse.
[00:07:20] Drive friendly. And then we have a
[00:07:22] response to that that it's included as
[00:07:23] well. I have no idea what vehicle car
[00:07:25] was stolen anyway. Technically the
[00:07:27] city's fault for leaving keys in it.
[00:07:29] regards a concerned citizen. Clever. I
[00:07:31] like seeing a lot of these models like
[00:07:33] to put little like bits of creative
[00:07:35] writing in the email results. I believe
[00:07:37] we looked at my pad, which was the
[00:07:40] writing app. And with that, let's take a
[00:07:42] look at our GTA clone.
[00:07:44] Nice. Oh, all right. Particle effects.
[00:07:50] It's
[00:07:54] inverted a bit.
[00:07:57] This is it's troubled, but it's
[00:08:02] the movement here is is not right.
[00:08:06] It's it's difficult to move around. Is
[00:08:08] that a vehicle? I think it's like a
[00:08:10] statue or a fountain, but you never
[00:08:12] know. Okay, I don't see any vehicles,
[00:08:14] unfortunately. All
[00:08:15] right, let's see if we can. [laughter]
[00:08:18] Okay, at least there's some interest.
[00:08:25] Okay,
[00:08:29] it's
[00:08:34] it could benefit from some improvement,
[00:08:35] but it spent 67 minutes on this. So, and
[00:08:38] it was looking at these and just doing
[00:08:40] some Oh, okay. That's wonderful. That's
[00:08:42] great. fly again. This is actually uh
[00:08:47] impossible to play. All right. Again, I
[00:08:50] think both of the games have perhaps
[00:08:51] some of the same issues. Now, this is
[00:08:53] actually kind of cool. This wallpaper
[00:08:55] lab speed, we have hue. It doesn't
[00:08:58] actually reflect here, but it does show
[00:09:00] on the preview that that's either there
[00:09:01] or not. So, that's cool. We have some
[00:09:03] other options here as well. Sunset
[00:09:05] Ridge,
[00:09:08] Vapor Grid,
[00:09:11] Deep Space.
[00:09:16] Good. And the movement does work. That
[00:09:17] one's actually pretty nice. Terminal
[00:09:19] Rain. Oh, a bit chaotic.
[00:09:24] Cool. And the color change does actually
[00:09:25] work. The hue tint to it. Nice. So, the
[00:09:29] final thing here, I believe, is the
[00:09:30] chronos snap. I do like how it properly
[00:09:34] kept the style of like OS9 Windows more
[00:09:37] or less. Press this or use take snapshot
[00:09:41] now. Windows may be snapshotted mid
[00:09:43] task. Games are stored closed. Okay,
[00:09:46] cool. We have a snapshot. So, let's
[00:09:48] close these all except this. We'll do
[00:09:50] restore last session. Rewind.
[00:09:56] Oh,
[00:09:57] I thought it would have opened the Is
[00:09:59] there a right click? No, there isn't.
[00:10:01] That's more forgivable in this.
[00:10:03] Secrets.txt.
[00:10:04] Type rose bud anywhere on the desktop.
[00:10:11] There's no sled loaded yet. Okay. It
[00:10:13] made a Citizen Cane reference. I don't
[00:10:15] know why. It mentioned something about
[00:10:17] the GTA game when I typed Rose Bud. The
[00:10:19] models seem to like to be a little more
[00:10:21] clever when given this specific prompt.
[00:10:24] Interesting. All right, let's try one
[00:10:25] more time.
[00:10:27] Rose Bud
[00:10:30] open Rogue City. I did. All right. Well,
[00:10:32] this was interesting. Not bad at all. I
[00:10:35] think the Deepseek result may have beat
[00:10:37] this out, but it's definitely up for
[00:10:39] debate. So, next up, we're going to be
[00:10:41] doing something that was not able to be
[00:10:43] done when testing Ox Alpha. This is the
[00:10:45] wrestling game, the mid80s 3D wrestling
[00:10:48] game. The prompt is right here. It's
[00:10:50] basically just give us a cool fun 3D
[00:10:52] wrestling game that is styled like it
[00:10:53] was in the mid80s. I was unfortunately
[00:10:56] not able to get a conclusion for the
[00:10:58] results for this when using this as ox
[00:11:00] alpha. So I'm very eager to see what it
[00:11:02] would have done here. Again, these are
[00:11:04] some results where we have direct
[00:11:05] comparisons to the Deepseek V4 Flash
[00:11:08] Vision model and its results which did
[00:11:10] perform very well across these tests.
[00:11:11] All right, so it is the next day and the
[00:11:13] reason for delaying this video a bit is
[00:11:16] because I know folks sometimes get a
[00:11:17] little fatigued with doing the same
[00:11:19] exact tests each time. So I did end up
[00:11:21] running a few more that are a bit more
[00:11:23] complex. But with that, we did leave off
[00:11:25] in the wrestling game. We do see a bit
[00:11:27] of a spoiler for it right here. However,
[00:11:28] I have not seen any of this result
[00:11:30] except for this spoiler. And this result
[00:11:32] took an hour and 25 minutes just for
[00:11:34] some reference as to how long this took.
[00:11:36] Okay, we do have sound. So, I will turn
[00:11:38] the speaker up, but it should be playing
[00:11:41] already. So, it's possible I have to
[00:11:43] click into it to enable sound.
[00:11:51] Are there two instances of this playing?
[00:11:53] No. Okay. So, the music is just really
[00:11:55] odd with that. Uh maybe we'll Oh, okay.
[00:12:01] Okay. We have Rex Tracker, El Tormenta,
[00:12:04] Iron Ivan, or Rockin Randy Riot.
[00:12:09] It's interesting. Different models have
[00:12:11] like very similar choices for which
[00:12:13] wrestlers they choose. Okay.
[00:12:18] [laughter]
[00:12:19] Okay. Okay. It's doing like an
[00:12:21] introduction.
[00:12:23] Let's get it on. Okay, maybe an
[00:12:24] interesting thing.
[00:12:28] Look at the ropes in the ring now. Okay.
[00:12:35] This game is difficult to play. Mash
[00:12:36] space to kick out.
[00:12:44] Okay, let's let me try this again.
[00:12:55] Liberty Slam. All right. Still, this is
[00:12:58] pretty good for a flash model. I believe
[00:13:01] this is a better result than the full-on
[00:13:04] GLM53 produced, which is interesting.
[00:13:11] These games are still not super
[00:13:13] playable.
[00:13:15] Oh no.
[00:13:17] All
[00:13:21] right, someone's picked up a chair.
[00:13:29] And unfortunately, it's still they're
[00:13:31] sinking under the ring, which happened
[00:13:33] as well with the Quen Next model. All
[00:13:36] right, I think I've seen enough of this,
[00:13:38] but I'll say this is actually pretty
[00:13:39] well done, especially considering that
[00:13:41] this is a Flash variant. So, our next
[00:13:43] test is a C++ one. However, it's not
[00:13:46] something we've ever done before. And
[00:13:47] I've started it out just by asking, "Can
[00:13:49] you search the web?" The model said yes.
[00:13:51] And I said, "I want you to find an early
[00:13:53] game demo called Terrup 2. I would like
[00:13:56] you to use the reference photos as well
[00:13:58] as the concept and create a game just
[00:13:59] like it using C++ with no RALI." It did
[00:14:03] find the correct information about this
[00:14:05] game, also known as deformers from 1996,
[00:14:08] is a Hungarian Freeware MS DOS off-road
[00:14:11] driving demo written in x86 assembly
[00:14:13] rendering to VGA. It features a software
[00:14:16] rendered texture height map terrain,
[00:14:18] buggies and bronos, spring mass physics
[00:14:20] where cars visibly crumble in crashes,
[00:14:22] hence deformers, multiple surface types
[00:14:24] affecting handling, free roaming, etc.
[00:14:27] We do have a reference photo of that
[00:14:28] game. So this is a reference photo of
[00:14:30] the actual game that I've told it I
[00:14:32] would like a replication of, not what it
[00:14:34] made itself. So we can see for 1996,
[00:14:37] this was pretty impressive, especially
[00:14:38] given like the soft body physics that it
[00:14:40] included. So it culminated in building a
[00:14:43] 2700 line C++ script, a replication of
[00:14:46] this, which I do believe it has called
[00:14:48] retro race. Good. A playable recreation
[00:14:50] of Terab 2 in 53 and 1/2 minutes. So
[00:14:53] let's take a peek at this. All right, we
[00:14:55] do have sound.
[00:14:59] I'd say this is actually not bad. Okay,
[00:15:03] good. That's something we want to make
[00:15:04] sure and test is is there the element of
[00:15:07] like emulated suspension in this? Now,
[00:15:10] this is not as close to the vehicle
[00:15:12] models at least. But look at this.
[00:15:14] There's actually some gameplay logic
[00:15:16] where we do need to get to these
[00:15:17] checkpoints. And when we go through
[00:15:19] them, it does actually give us like
[00:15:21] checkpoint too. And we have a mini map.
[00:15:24] I'll say this did a faithful job of
[00:15:26] getting the overall vibe and feel of
[00:15:28] this result, even if it's not directly
[00:15:31] the same in terms [music] of aesthetics.
[00:15:32] I think the Source one had some cooler
[00:15:34] looking car models, but we do have what
[00:15:37] else? So, we should also have some
[00:15:40] different Oh, so here's the Bronco.
[00:15:43] Okay, so I did just mess up by
[00:15:45] unfortunately resetting our progress,
[00:15:47] but yeah. So,
[00:15:49] air. What happens if we go in the water?
[00:15:52] And the original said the terrain
[00:15:54] affects like the speed and things. So
[00:15:56] good. That's exactly what we wanted to
[00:15:58] see. So going in the water kind of
[00:15:59] stalls our progress. And look at the way
[00:16:01] it's drawn it. This is actually kind of
[00:16:02] I'm impressed with this especially
[00:16:04] because we gave it a pretty static
[00:16:06] example of what we wanted it to
[00:16:08] replicate for us. Says F9 for a
[00:16:10] different camera. Oh, look at that.
[00:16:13] Okay. So the So the arrow keys
[00:16:18] and WD controls these. So, I'm
[00:16:21] controlling both right now, but using
[00:16:23] separate keys. The blue car is WD. The
[00:16:26] buggy is red. I mean, the buggy's
[00:16:29] arrows.
[00:16:32] Still, this was actually I would say
[00:16:34] this is pretty well done. If we go back,
[00:16:37] we have some other things. P is for
[00:16:39] pause. F10 is a map toggle. Okay, so
[00:16:42] that just hides or shows the mini map.
[00:16:44] There's another one that I can't quite
[00:16:46] make out right here. F1 or F5. Let's try
[00:16:49] F1. And then F5 is just so these are
[00:16:51] different camera views. Overall, I'm
[00:16:54] actually I'm satisfied with this and it
[00:16:57] did a nice job on the mini map as well.
[00:16:59] So, backed by popular demand because
[00:17:01] some folks had mentioned missing this in
[00:17:02] our Quen result is the C++
[00:17:05] self-contained skateboard game. This is
[00:17:07] the one where the map needs to be an
[00:17:08] early 2000's New York City block. We can
[00:17:11] see this was a longer generation working
[00:17:12] for 2 hours and 17 minutes. It's given
[00:17:15] us just what's in the game. And the
[00:17:16] culmination of this was about 2400
[00:17:18] lines. Oh, no. It's saying 4,000 lines,
[00:17:21] single file C++, not using Ray as well.
[00:17:24] I'm pretty sure that is included. Yes.
[00:17:26] So, let's take a peek at what this made.
[00:17:27] And I'm expecting something pretty
[00:17:29] decent. So, here's the New York City
[00:17:31] skate map. Okay.
[00:17:34] It's
[00:17:36] troubled. It's got some
[00:17:41] troubled issues. I'll say the NPCs there
[00:17:45] walking are not too bad. Let's see if
[00:17:46] any of the tricks work. Okay, they do.
[00:17:48] And the board does move independently of
[00:17:50] the player, which is nice to [laughter]
[00:17:52] which is nice to see. Now, something I'm
[00:17:54] going to notice here is that it's not
[00:17:56] really clearcut that we can move back
[00:17:58] and forth. It does have a mini map,
[00:17:59] which is interesting as well. It seems
[00:18:01] like the textures that are applied to
[00:18:03] this taxi are either Z fighting and
[00:18:05] there's like actually I think there's a
[00:18:06] bunch of car models stacked and spawned
[00:18:08] in right there. So, that is some issue.
[00:18:10] And then we can see the rendering is
[00:18:11] just not all there. Sometimes we can see
[00:18:13] further down the block. I think this is
[00:18:15] a result that could be made competent,
[00:18:18] but I'm not as impressed with this as I
[00:18:21] had hoped to be to be totally honest
[00:18:22] with you. I do believe now because we
[00:18:25] didn't do this specific test with the
[00:18:27] Quenext model, I can't say definitively,
[00:18:29] but based off of the C++ result that
[00:18:31] model had made, I would assess that
[00:18:33] would probably have outperformed this on
[00:18:35] this specific task. So make of that what
[00:18:37] you will and it's
[00:18:41] somewhat that's just like not right. But
[00:18:44] other than that it's okay. Now this next
[00:18:47] test was intended to be something that
[00:18:49] is pretty darn difficult and it's going
[00:18:50] to take a little bit of prior knowledge
[00:18:53] just to get what exactly was supposed to
[00:18:55] happen here. So initially I had wanted
[00:18:57] this to take this board right here which
[00:18:59] is a Ragsta Pi 3W. It's like a Raspberry
[00:19:03] Pi clone and it has some decent
[00:19:05] performance and I wanted it to optimize
[00:19:07] an AI model on this without web
[00:19:10] searching to see how much it could speed
[00:19:11] it up and just optimize this in running
[00:19:13] an AI model. I couldn't get this board
[00:19:15] working and believe me I tried. Fable
[00:19:17] also was having trouble with it. So I
[00:19:19] canned that idea and instead I grabbed
[00:19:21] this which is a USB Google Coral AI
[00:19:24] accelerator. I do believe this is a few
[00:19:26] years old at this point. However, the
[00:19:28] task for this model was to using this AI
[00:19:31] accelerator and when given a simple
[00:19:34] motorcycle driving game that I had Fable
[00:19:36] make to train a tiny little neural net
[00:19:39] to be able to drive the motorcycle
[00:19:41] through traffic without crashing. Now,
[00:19:43] this is something that truthfully does
[00:19:44] not require an external little USB AI
[00:19:47] accelerator like this. It's more than
[00:19:49] small enough to run on this laptop,
[00:19:51] which is even too much power for a tiny
[00:19:53] little thing like this. However, the
[00:19:55] reason for adding the coral was just to
[00:19:57] kind of implement a more difficult and
[00:19:59] constrained way of getting this done.
[00:20:01] Now, unfortunately, we see that the
[00:20:03] coral itself apparently was not working
[00:20:05] for some reason. I have not really tried
[00:20:07] that device on this computer before, so
[00:20:09] I can't definitively confirm or deny
[00:20:11] that there's some hangup that either
[00:20:13] this flash model missed itself or
[00:20:15] whether or not the Coral was just
[00:20:16] problematic. However, it did actually
[00:20:19] figure out a way to look at the game,
[00:20:21] watch it run, cycle through, and then
[00:20:22] autonomously play it, take frames,
[00:20:25] create this little tiny neural net model
[00:20:27] to actually know when to move side to
[00:20:30] side so the motorcycle does not collide
[00:20:32] with cars. Now, the culmination of this
[00:20:34] right here is something this run.sh
[00:20:36] where it will actually open the game and
[00:20:38] using this tiny little model that it
[00:20:40] trained, it will autonomously drive the
[00:20:42] motorcycle around and try not to crash.
[00:20:44] So, first off, let's just take a look at
[00:20:46] the actual source of the game that this
[00:20:48] is going to be trained on to play. Now,
[00:20:50] this was not made by the Flash model.
[00:20:52] This was made by Fable. So, essentially,
[00:20:55] it's supposed to have trained a model
[00:20:57] just so this motorcycle can drive around
[00:20:59] here and weave through traffic without
[00:21:01] crashing. We can see this result by
[00:21:02] itself is pretty darn impressive. But
[00:21:04] again, this was the job of Fable that
[00:21:06] created this and not GLM Flash.
[00:21:08] Although, that model in our OX alpha
[00:21:09] stealth testing did actually make a
[00:21:11] pretty competent motorcycle game. So the
[00:21:13] whole point is to be able to drive like
[00:21:14] this autonomously without that
[00:21:16] happening. So with that, let's close
[00:21:18] this now and then go into the specific
[00:21:20] directory for this. And it said that to
[00:21:22] see it drive, we are just going to type.
[00:21:25] So I'm doing nothing right here. And
[00:21:27] we're going to actually see that this is
[00:21:28] a tiny little trained model that this
[00:21:30] has created that is actually controlling
[00:21:32] the movements of this motorcycle
[00:21:34] designed to avoid obstacles. And the
[00:21:38] model did this entirely by itself. I
[00:21:39] gave it the script and a prompt that
[00:21:41] we'll take a look at more in depth once
[00:21:43] we have a better like understanding of
[00:21:45] this. So, okay, like a car just swerved
[00:21:48] in front of us and that became an issue.
[00:21:50] And again, this is like a tiny little
[00:21:53] like I wouldn't expect super performance
[00:21:55] from this, but the fact is it's
[00:21:57] something really different that the
[00:21:58] model had to show some capability in a
[00:22:00] few different areas. See, so now it's
[00:22:02] like trying to at least respond to the
[00:22:04] fact that it sees a car in traffic in
[00:22:06] front of us and then try not to hit it,
[00:22:08] which it did seem to fail at doing. And
[00:22:10] now we're having a bit of issues here.
[00:22:12] Although I suppose that would be like a
[00:22:14] [laughter] it's like a hack to make sure
[00:22:15] that it doesn't collide with anything
[00:22:17] because it's kind of just now riding the
[00:22:20] center line where there would be no
[00:22:22] vehicles. So I think a good way to go
[00:22:23] about this is basically reading this
[00:22:25] plain English version of what exactly
[00:22:27] this agent did. So, because this game is
[00:22:29] an infinite runner and it never actually
[00:22:31] ends, the agent invented its own
[00:22:33] scorecard first. Four fixed random seeds
[00:22:36] and 45 seconds of sim time each
[00:22:38] measuring how many collisions per
[00:22:40] kilometer, the average speed, and then
[00:22:42] the lane fraction. So, how often the
[00:22:44] bike was actually in bounds of a lane
[00:22:46] and not just on the shoulder as we did
[00:22:48] see it riding in one of the examples.
[00:22:50] Additionally to that, it made the game
[00:22:52] deterministic just by having seated
[00:22:54] random numbers and timed key presses to
[00:22:56] rendered frames. So the same policy on
[00:22:59] the same seed replays almost exactly.
[00:23:01] That's what let it compare models fairly
[00:23:03] instead of against noise. Then we have
[00:23:05] the reference models. So random keys as
[00:23:07] we saw right here had a higher value for
[00:23:09] how many times you crash into a car per
[00:23:11] kilometer. And then we have our inlane
[00:23:13] percentages and the average speed at
[00:23:15] which these runs occurred. Just holding
[00:23:17] W had higher hits, but we did have a
[00:23:20] higher average speed. and we stayed in
[00:23:22] the lane more often because when you
[00:23:24] spawn in and just hold W, you're likely
[00:23:26] going to be in a lane anyway and not off
[00:23:28] to the side. The scripted expert was the
[00:23:30] one that could basically just read the
[00:23:31] car positions from the actual game. So
[00:23:33] naturally, it had no issues at all and
[00:23:35] it was essentially a perfect run. And
[00:23:37] then the best neural net that this
[00:23:39] produced had a hits per kilometer value
[00:23:41] of 0.48, an average speed of 150, and
[00:23:45] then 63% in lane. So this value, the
[00:23:48] average speed was good. the average hits
[00:23:50] had gone down significantly over just
[00:23:52] random which is essentially what we
[00:23:54] wanted to see in this creating a little
[00:23:55] model to make this better. We have our
[00:23:58] randomized baseline here
[00:23:59] non-scientifically and it definitely
[00:24:01] outperformed that by a large margin
[00:24:03] although the percentage that it stayed
[00:24:05] in lane was not necessarily the best.
[00:24:07] Now in terms of how it trained the
[00:24:09] network we have this right here
[00:24:10] behavioral cloning. So it would drive
[00:24:11] with the expert, record around 12,000
[00:24:14] pairs of 160x40 pixel grayscale
[00:24:16] screenshots, which keys the expert
[00:24:18] pressed and then train a 41k parameter
[00:24:21] CNN to copy that. All nine models are
[00:24:23] variations of that one idea. Training
[00:24:25] data is the 170 megabytes in data. Then
[00:24:28] we have nine different versions of
[00:24:29] models and these are actually visible in
[00:24:31] the folder right here. So if we go into
[00:24:32] models right here, we have all of these
[00:24:34] specific ones. And if we go in some of
[00:24:36] these, we actually see like these are
[00:24:37] specific things you may be familiar with
[00:24:39] if you've played with tiny little models
[00:24:41] like this on edge devices or something
[00:24:43] of the sort. So, it's really kind of
[00:24:45] interesting how it went about doing all
[00:24:46] of this. And it did also, as part of the
[00:24:48] prompt, it was told to essentially give
[00:24:50] us then a self-contained HTML file with
[00:24:53] a report of these like pieces of
[00:24:55] information. Okay, cool. It stylized
[00:24:57] this in the same way as the game. So,
[00:24:59] this is kind of what we were just
[00:25:01] looking at right there where we were
[00:25:02] reading through in plain English. We
[00:25:03] have our architecture. We have the loop
[00:25:05] budget and these are just giving us more
[00:25:07] bits of information. Things like how
[00:25:09] much lag is there between like pressing
[00:25:11] the key and then like making an effect.
[00:25:14] It has to measure that as well,
[00:25:15] especially if it was going to use the
[00:25:17] coral which would introduce some level
[00:25:19] of latency being that it would be
[00:25:21] processed on this and then have to
[00:25:23] traverse through USB to then make a key
[00:25:25] press and things of that sort. Now,
[00:25:27] additionally, something to talk about is
[00:25:28] we do have mentions of quantization kind
[00:25:31] of making things become problematic. So
[00:25:33] let's take a look at what exactly
[00:25:34] happened with that right here. So we can
[00:25:36] see here's what the model did. Standard
[00:25:37] post-training quantization take the
[00:25:39] train float model feed it 800 real
[00:25:41] frames so the converter can learn the
[00:25:43] range of every activation and convert
[00:25:45] everything to 8bit integers which would
[00:25:47] be required for the Google coral. It
[00:25:49] then compiled that and the coral
[00:25:51] compiler mapped all 14 operations to the
[00:25:53] TPU which is the tensor processing unit
[00:25:56] inside this little coral with no CPU
[00:25:58] fallback. So the deployment side was
[00:26:00] right and that's cool to see. So, here's
[00:26:02] what broke. And essentially, throttle
[00:26:03] and braking survived. But it's actually
[00:26:05] kind of interesting to see what
[00:26:06] happened. Steering collapsed from 74 to
[00:26:09] 47% with three steering choices. That's
[00:26:12] barely better than guessing. On the
[00:26:14] road, that shows up as the INT8 bike
[00:26:16] swerving onto the shoulder and staying
[00:26:17] there at 184 km. The better collision
[00:26:20] number is fake because, as we saw when
[00:26:22] we first ran this, riding on the
[00:26:24] shoulder is like an infinite cheat for
[00:26:26] this. So, in some ways, it's actually
[00:26:28] kind of interesting, but there are no
[00:26:30] cars on the shoulder. or the agent said
[00:26:31] so explicitly. Here's steering like why
[00:26:34] did steering die? Essentially TLDDR is
[00:26:37] mentioned right here. The difference
[00:26:38] between hold and nudge left is a few
[00:26:40] pixels of lane marker position in a
[00:26:42] 160x40 pixel image. Brake and throttle
[00:26:45] or coarse decisions. Is there a big dark
[00:26:47] blob ahead or no? An 8bit precision is
[00:26:49] plenty for that. Steering relies on
[00:26:51] small activation differences that 8bit
[00:26:54] rounding flattens. That's the typical
[00:26:56] pattern for tiny nets on tiny inputs.
[00:26:58] There's no capacity to spare. So every
[00:27:00] bit of precision was doing work. So
[00:27:02] basically there wasn't enough fine grain
[00:27:03] detail that was preserved to determine
[00:27:06] the proper like left right steering I
[00:27:09] guess could be said and then we have a
[00:27:11] bit of information here on how it tried
[00:27:12] to fix it and then a summary just of
[00:27:14] like what exactly went wrong. So it's
[00:27:17] very interesting to see this stuff and I
[00:27:18] know this is again a little outside the
[00:27:20] scope but there's a whole bunch of like
[00:27:22] cool information and experiments that
[00:27:24] can be done with things like these tiny
[00:27:26] little models on relatively cheap
[00:27:28] devices like this. definitely provide a
[00:27:30] fantastic learning opportunity for like
[00:27:32] some of the lower level concepts of
[00:27:34] things like in these gigantic AI models
[00:27:36] that we use all the time. So, it's
[00:27:38] pretty cool to see. And again, this did
[00:27:40] a pretty strong job, I would say, for a
[00:27:42] flash model in something that's not
[00:27:44] like, oh, I'm going to go on GitHub and
[00:27:46] figure out how to map a little neural
[00:27:48] net to play this motorcycle game. So, it
[00:27:51] went about approaching this even from
[00:27:52] the ground up just doing this. And I
[00:27:54] find this is pretty darn cool and
[00:27:56] perhaps something we'll keep in the
[00:27:57] repertoire of more difficult tests. So
[00:28:00] we also did the Street Yeet game.
[00:28:02] However, this had to make the assets for
[00:28:03] this from within Blender and then build
[00:28:05] the game itself in GDAU. We can see it
[00:28:07] took around 52 minutes which really is
[00:28:09] not bad. 51 minutes I should round down
[00:28:12] 17 different models. The Yeet, we have
[00:28:14] the Punch Windup and Strike Sound and
[00:28:16] then City of Life. This is not the one
[00:28:18] that has the cinematic cutscene in the
[00:28:20] beginning of it. And I have not at all
[00:28:21] seen this, so I'm pretty darn exciting.
[00:28:24] Excited. Open the folder and press F5 or
[00:28:26] run out. SH. So, here is our street eat
[00:28:29] game. Okay, we have music. We've got
[00:28:32] pedestrians. Oh, the arms seem like
[00:28:34] they're somewhat detached. All right,
[00:28:36] let's just
[00:28:39] There's a police vehicle. Hey, it made
[00:28:41] these models as well and did not do a
[00:28:43] bad job. There are mesh colliders.
[00:28:45] [laughter]
[00:28:46] That's good. I like this. It's pretty
[00:28:48] like pretty good actually.
[00:28:54] Can we eat this fire hydrant? Which I do
[00:28:56] have to say that's a pretty good model
[00:28:58] of a fire hydrant. Let's see how ye
[00:28:59] eatable this city is. Yep. Oh, look at
[00:29:02] it's spraying water. Good. Good
[00:29:04] attention to detail. All right. Sorry. I
[00:29:06] just got like excited.
[00:29:09] Look at this city. Like how much there's
[00:29:11] drawn in the distance there. Oh.
[00:29:15] [laughter]
[00:29:16] All right. We got to find some people.
[00:29:19] All right. Yeah, there's like a green
[00:29:21] annory space as I call them. No, I'm
[00:29:23] kidding. [laughter]
[00:29:26] This This is a very very very good
[00:29:28] result. I am quite quite pleased with
[00:29:30] what I'm seeing right here. Gone.
[00:29:33] [laughter]
[00:29:33] And then
[00:29:35] they do run away from us. Insane ye.
[00:29:40] Oh, we're getting combos, too.
[00:29:43] Can we double ye? Oh, yeah, we can.
[00:29:45] That's messed up.
[00:29:48] Oh, that bar that was there is like a
[00:29:50] combo timer. So, if we don't have
[00:29:52] another yeet by the time that color runs
[00:29:54] out there in that bar, then it like the
[00:29:57] combo ends. This is like,
[00:30:00] if I were to make a complaint, okay,
[00:30:03] it'd be cool if the cars were moving and
[00:30:05] not static, but like honestly, it's not
[00:30:08] really a big deal. It placed them nicely
[00:30:10] as if they would have been moving.
[00:30:13] There's good feel to these. Like the
[00:30:15] mass of these cars just Oh, a double
[00:30:18] whoosh. All right, one more.
[00:30:25] Quick, quick. Oh, our combo ran out.
[00:30:35] Can we eat the street light? A
[00:30:41] All right. If anyone's interested in
[00:30:43] this, you'll be able to find it on Steam
[00:30:44] for $1.99. No, I'm kidding. I don't I
[00:30:47] don't actually I don't do that and tell
[00:30:50] people that I've done it.
[00:30:53] That was awesome. That was very very
[00:30:55] well done. It was just like it was
[00:30:57] competent, I could say. So, overall,
[00:31:00] that is going to conclude our first look
[00:31:02] and test of the newly releasleased GLM53
[00:31:05] flash model. Now, for this test, I have
[00:31:07] been using it through the mid tier of
[00:31:09] the Zcode subscription. And from our
[00:31:11] usage right here, we can see that
[00:31:13] overall every single test we ran today
[00:31:15] culminated in 23% of our weekly usage
[00:31:18] limit getting used up. So, we have 77%
[00:31:21] of the weekly usage limit. I think it's
[00:31:23] subjective to judge whether that's good
[00:31:25] or bad, but I can say in specific the
[00:31:27] test where it had to train the model for
[00:31:29] the Google Coral, that took I believe
[00:31:31] over four hours that it was working for.
[00:31:33] So, it did do a bit of work. Now, I
[00:31:36] think we should just do like a brief
[00:31:37] results overview as at least with this
[00:31:39] browser OS. I kind of haven't seen this
[00:31:42] since yesterday. Oh, it's already open
[00:31:43] here. Good. I think because the Quen
[00:31:45] Next model also was given basically the
[00:31:47] identical test, it's harder to judge
[00:31:49] this one. The Quen model basically did a
[00:31:52] pixel perfect replication of this. This
[00:31:54] didn't, however, this had some better
[00:31:55] elements such as the GTA game being
[00:31:57] better, and it was still overall a very
[00:31:59] well done result, especially the way the
[00:32:01] hover effects look here and just some of
[00:32:03] the other things like including all of
[00:32:05] these photos and a nice replication, but
[00:32:07] with movement of the background scene in
[00:32:10] that. Next up, we had our Super Slam 86
[00:32:13] wrestling game. Now, this is one that we
[00:32:15] can't compare to the Quen Next result
[00:32:17] because this just used 3JS for it
[00:32:19] instead of using GDAU and Blender.
[00:32:21] Though, I have to say I almost think
[00:32:23] that this is a better result than what
[00:32:26] the full-size GLM 5.3 did. Oh, look at
[00:32:29] that. Like, don't quote me on this 100%,
[00:32:31] but this is actually quite impressive.
[00:32:33] I've only run this test a few times in
[00:32:35] the history of the tests we've done on
[00:32:37] this channel, but I'll say this is quite
[00:32:39] well done. It's clean. It's got some
[00:32:41] nice bounce effects to the actual ring.
[00:32:43] There's some good effects and movements
[00:32:45] and the tricks and everything like that.
[00:32:47] It's nicely done. The scenery is good.
[00:32:49] the environment fits and it's
[00:32:53] it's a well done result. Iron curtain
[00:32:56] trouble.
[00:32:57] See, like that's pretty good. So, I was
[00:33:00] impressed with this. Then we had our C++
[00:33:02] game where it needed to create a replica
[00:33:04] of the game that is shown right here in
[00:33:06] this reference photo. Okay, not that
[00:33:09] one. In this reference photo right here.
[00:33:11] So, I think it did a pretty nice job of
[00:33:13] this. One thing I'd say where I knock it
[00:33:15] is it didn't really properly recreate
[00:33:16] these vehicles in the same style. These
[00:33:19] vehicle models are better than what we
[00:33:20] received from our GLM model. This second
[00:33:23] reference photo is of the game that
[00:33:25] spawned from this one called insane but
[00:33:27] with a one in the title. So, one insane.
[00:33:29] And we can probably ignore that. It had
[00:33:31] some nice elements to it here though.
[00:33:33] The mini map was well done and the way
[00:33:35] that the terrain actually affected the
[00:33:37] vehicle model. So, when we went into the
[00:33:38] water, it bogged down. There's some
[00:33:40] bounce to the suspension and some of
[00:33:42] that soft body physics style. But the
[00:33:44] really cool thing was the split screen
[00:33:45] that it implemented here. So, we can
[00:33:47] drive both of these vehicles from either
[00:33:49] WD for the bottom one or the up, down,
[00:33:52] left, right arrow keys for the top one.
[00:33:54] And this was a pretty nice bit to
[00:33:56] include. Both of them do have mini maps
[00:33:58] and things like this. I like that it did
[00:34:00] this and it just gives us a pretty cool
[00:34:01] visual if nothing more. It did
[00:34:03] definitely keep the style of this game
[00:34:05] similar to the reference and there's not
[00:34:07] a bunch of information out there for
[00:34:09] that reference. So, it was pretty darn
[00:34:10] cool to see what it did. Then, we had
[00:34:12] our skate game. Now, unfortunately, this
[00:34:15] just was not it. The bail effect is one
[00:34:18] kind of disturbing, but two also kind of
[00:34:20] funny. And there are elements here that
[00:34:22] look decent, like the pedestrian, some
[00:34:24] angle of the tree, the street light. It
[00:34:26] has a pretty darn populated mini map
[00:34:28] here as well. But unfortunately, there's
[00:34:30] just a lot of visual artifacting and
[00:34:32] glitching. And this is something that I
[00:34:36] think the I will say comparatively to
[00:34:38] its larger sibling of the full-size
[00:34:41] GLM53, I think this model is actually
[00:34:43] pretty darn good. And that can be judged
[00:34:45] based off this result in specific, this
[00:34:47] is not as good as the big sibling of
[00:34:50] this model. However, considering this is
[00:34:52] much smaller, it's still fairly decent,
[00:34:54] I would say. Then we had our Google
[00:34:56] Coral model and we kind of spent a bit
[00:34:58] of time going over how exactly it did
[00:35:00] this. So I won't say too much more about
[00:35:02] it, but I think it's pretty interesting
[00:35:04] to see how this model performed. When
[00:35:06] given a task that didn't really have
[00:35:07] concrete steps to achieve the goal, it
[00:35:09] was basically just like here's a game.
[00:35:11] Train a tiny little neural network that
[00:35:13] will actually play the game without the
[00:35:14] motorcycle crashing into cars. Like good
[00:35:17] luck, go ahead. And it did a good enough
[00:35:18] job. We actually saw some improvement in
[00:35:20] the models and we saw the way that it
[00:35:22] went about training them. Unfortunately,
[00:35:24] it didn't successfully get it deployed
[00:35:26] to the coral TPU over USB. However, we
[00:35:28] saw in our overview that the actual
[00:35:30] model was mapping to the tensor chip in
[00:35:32] this. So, it did do some level of
[00:35:35] competence in terms of getting this all
[00:35:36] done. And it gave us a really nice
[00:35:38] overall report of what it did here as
[00:35:40] well. And this worked for over 4 hours
[00:35:42] in doing this task. A bit over 4 hours,
[00:35:44] I believe. So, a longer drawn out task
[00:35:47] that was definitely more technically
[00:35:48] challenging. Then finally, we had our
[00:35:50] Street Eat game where it did use GDAU
[00:35:52] and Blender for the assets and for the
[00:35:54] game. This was exceptionally well done.
[00:35:57] The music fit this well. The aesthetics
[00:36:00] are nice looking. Just the overall
[00:36:02] gameplay here. You can get a vibe for
[00:36:03] it. The feel of the vehicles when you
[00:36:05] actually hit them, they feel good. It's
[00:36:07] like they have the correct amount of
[00:36:08] mass that you would expect they would in
[00:36:10] this game. And this one overall, this
[00:36:12] was exceptionally well done. I have not
[00:36:14] really done this test very often in
[00:36:15] which they must use GDO and Blender for
[00:36:17] this game, but I think as we do this
[00:36:20] specific test more and more, we'll see
[00:36:21] this definitely holds its own over time
[00:36:24] as we see other bigger models perform
[00:36:26] this as well. So,
[00:36:29] that is pro I'm like not even going to
[00:36:31] be able to post this video. I'm going to
[00:36:32] be stuck here playing this game. Oh, W.
[00:36:35] That is probably going to conclude our
[00:36:37] first look and test of GLM 5.3 Flash,
[00:36:40] which was also known in stealth as ox
[00:36:42] alpha. So, overall, [snorts] if you have
[00:36:45] any questions, please feel free to leave
[00:36:47] them in the comments. And thanks for
[00:36:49] watching. One more yeet. [laughter]
[00:36:53] Yeah, this is this is quite well
