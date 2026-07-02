---
video_id: YpufDU9imnU
title: Ornith 35B Benchmarked vs Qwen 35B - 16GB Local LLM setup
channel: "Luke's Dev Lab"
url: "https://www.youtube.com/watch?v=YpufDU9imnU"
watched_date: 2026-07-02
watched_at: "2026-07-02T15:00:07Z"
watch_count: 1
duration_seconds: 1379
source: youtube-history-browser
added_date: 
history_label: Today
history_order: 1
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 138
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Luke tested Ornith 35B against Qwen 3.6 35B on a 16GB VRAM setup using a comprehensive benchmark suite: token generation speed, 256k context memory retention (needle-in-haystack), tool-use reasoning (agency tasks), Python coding challenges (OpenAI human eval), and two complex coding simulations (sand physics and dungeon crawler). Results showed Ornith slightly faster on token generation (~20 tokens/sec prefill, ~10 tokens/sec decode), identical memory performance at full context, nearly tied on agency tasks (Qwen marginally better at tool chaining), Qwen better on OpenAI eval (98% vs 97% pass rate, but Ornith wasted tokens overthinking), Ornith winning on sand physics (one-shot vs requiring fixes), and both struggling equally with dungeon generation. Overall conclusion: Ornith performs "basically as good as Qwen" despite being version 1.

For someone running a local 16GB setup, choose Ornith if you need marginally faster token generation and better physics simulation coding; choose Qwen if you need more efficient token use and better multi-step tool reasoning. Both models struggle with complex algorithms requiring iteration—expect multiple prompts needed for intricate generation tasks. Luke plans to test smaller 9B variants next and will run additional coding challenges to find a clearer performance winner.

## Transcript

[00:00:00] Hey, welcome to Luke's Dev Lab. My
[00:00:02] name's Luke and I'm here to help you cut
[00:00:04] through the hype and find out what AI
[00:00:06] can actually do for you. And in this
[00:00:07] video, we're going to be looking at
[00:00:09] ORNIF and comparing it to Quen. Now,
[00:00:12] this is one I know a lot of you have
[00:00:14] been asking for. Now, by the way, I
[00:00:17] apologize if there is background noise.
[00:00:19] I am on vacation this week and I'm
[00:00:21] recording this from an Airbnb. So,
[00:00:24] apologies for that. So, for those of you
[00:00:27] that are not aware, or is a model from
[00:00:30] Deep Reinforce AI, and this model was
[00:00:34] post-trained on top of Gemma 4 and Quen
[00:00:37] 3.5 and they've got some benchmarks here
[00:00:40] that would suggest it's pretty good. And
[00:00:42] if we go over to the hugging face for
[00:00:44] this specific 35B that we're going to
[00:00:47] look at, they are comparing it to Quen
[00:00:51] 3.635B 635b
[00:00:53] and saying it's better across the board.
[00:00:56] So that's a bold claim I think. So what
[00:00:59] we're going to do, we're going to grab
[00:01:00] this model in 4bit Q4KM and then we're
[00:01:03] going to test it against Quen 3.635B
[00:01:06] from Unsllo GGF so we can run it in
[00:01:08] llama CPP and we're going to go for the
[00:01:11] Q4 KM as well. Now I know these are the
[00:01:15] Unsllo dynamic quants. So there is a
[00:01:17] slight difference here, but I still
[00:01:18] think this is a pretty close apples to
[00:01:20] apples. Still Q4km on both. So let's
[00:01:24] compare them. For our tests, we're going
[00:01:26] to be running our usual test suite when
[00:01:28] we review a model. So we're going to be
[00:01:29] doing performance to see the token
[00:01:32] prefill and token generation. Then we're
[00:01:34] going to be doing memory where we're
[00:01:35] going to fill up the context to its full
[00:01:37] 256k and see how it does finding data
[00:01:40] within that. We're going to do our
[00:01:41] agency, which is our fake company
[00:01:43] sandbox environment where the model will
[00:01:45] have to choose from a selection of tools
[00:01:47] that it can call, including chaining
[00:01:49] tools together. Then we're going to be
[00:01:51] doing our open AAI human eval, which is
[00:01:53] 164 handwritten Python challenges. And
[00:01:56] then we've got our two coding
[00:01:57] challenges, which is our sand physics
[00:01:59] simulator, and our dungeon crawler,
[00:02:01] which simulates random generation as
[00:02:04] well as algorithms for ray casting. And
[00:02:07] in these tests, the models are not
[00:02:08] allowed to reach for frameworks or
[00:02:11] libraries. They must code all the
[00:02:13] algorithms themselves. And then a quick
[00:02:15] look at the system that I'm running this
[00:02:17] on. So this is a separate system that
[00:02:19] I'm running inference on with 16 gigs of
[00:02:22] VRAM. And then I've got 32 gigs of DDR4
[00:02:25] RAM. So nothing too impressive here. As
[00:02:27] I did mention, I'm on vacation this
[00:02:29] week. So I'm actually connecting to this
[00:02:30] box in a different country. So fingers
[00:02:33] crossed all goes well. Okay. So first
[00:02:35] we're going to jump in and look at the
[00:02:37] performance for ONRIF. So you can see on
[00:02:40] the prefill here we're getting just
[00:02:42] under 200. So the prefill is the model
[00:02:46] ingesting tokens such as your prompt.
[00:02:48] And then on the decode which will be the
[00:02:51] output, the tokens per second basically.
[00:02:54] You can see it stays at a steady 43 no
[00:02:57] matter what the length is of the output.
[00:03:00] So let's open up our result for Quen 35B
[00:03:04] and then we'll put this side by side and
[00:03:06] have a look how it compares. So we've
[00:03:09] got ONR ornif now on the left and then
[00:03:11] Quen on the right. So for decode, Quen
[00:03:14] is slightly slower across the board
[00:03:18] there. So we're looking at about 20
[00:03:21] tokens slower on the decode. So again,
[00:03:24] that's the model reading your prompt.
[00:03:28] And then now the output speed. So again,
[00:03:31] we're getting about 10 tokens slower. So
[00:03:35] it looks like Ornith is actually
[00:03:37] slightly faster than Quen. Now I wonder
[00:03:40] if there's a difference in the active
[00:03:42] parameters because from my reading, I
[00:03:44] couldn't actually see anything from
[00:03:46] Ornith mentioning how many active
[00:03:49] parameters there are on this model. I
[00:03:51] assumed it would be active 3B, the same
[00:03:53] as Quen, but maybe not. Maybe it's
[00:03:56] slightly less. So that's the performance
[00:03:58] result. Ornif is slightly faster in my
[00:04:01] testing. So let's move on. So here's the
[00:04:04] results for the memory test. This is our
[00:04:06] needle in the haststack test. So what we
[00:04:08] do is we fill up the context entirely
[00:04:11] for the model. And we're using the full
[00:04:12] 256k.
[00:04:14] And then we put pieces of data at either
[00:04:16] 0, 25, 50, 75, or 100% of the context
[00:04:21] depth. And we ask the model to find the
[00:04:23] data. Obviously the model doesn't know
[00:04:24] where that data is within that context.
[00:04:27] And then we run the test three times
[00:04:28] over for each depth as well just to
[00:04:30] ensure consistency. So ornif has scored
[00:04:34] 93% here and it's done very well. So we
[00:04:37] can see all the way up to 75% depth all
[00:04:41] three runs it's found the data. So
[00:04:44] that's really good. And then only on
[00:04:46] 100% context depth one out of the three
[00:04:49] times it hasn't managed to find that
[00:04:51] piece of data that it's supposed to be
[00:04:52] looking for. So let's see how that
[00:04:54] compares to Quen's result. Okay, so
[00:04:56] Ornif on the left, Quen on the right,
[00:04:58] and it looks like they've done exactly
[00:05:00] the same in terms of the pass rate. So
[00:05:02] let's have a look at the graph. Okay,
[00:05:04] it's exactly the same. So they've both
[00:05:07] managed to pass apart from one run on
[00:05:10] the full depth. So a very good result
[00:05:12] from both. Uh, as you can see, these
[00:05:15] tests took 12 hours to run each. So it
[00:05:18] took me over 24 hours to run these
[00:05:20] tests. So, thumbs up if you appreciate
[00:05:22] that on the video. And that's why it
[00:05:24] took me a little while to get this test
[00:05:25] to you. And uh a lot of you have
[00:05:27] mentioned, yeah, better hardware will
[00:05:29] help. So, I am looking at upgrading my
[00:05:31] hardware for some of these tests. But if
[00:05:33] I do, I will still use my original
[00:05:35] hardware for performance because I feel
[00:05:37] like this setup is more in line with
[00:05:39] what is accessible to a lot of people.
[00:05:41] Anyway, with that said, let's move on.
[00:05:43] So, we're going to move on to our agency
[00:05:45] benchmark now. So, if you're new around
[00:05:47] here, I've got this uh overview which
[00:05:49] you can find linked in the GitHub down
[00:05:51] below. And essentially the agency test
[00:05:53] is we put the model into a fake company
[00:05:56] environment with an array of tools that
[00:05:58] it has access to and we want to give
[00:06:01] problems and tasks to the model and then
[00:06:04] basically hopefully the model can assess
[00:06:06] the tools it has, reason around
[00:06:08] problems, chain tools together to solve
[00:06:10] the task that we're giving it. So again,
[00:06:12] if you want to read this more, find this
[00:06:14] down below. Otherwise, let's jump into
[00:06:16] the result. So, Ornif is scoring 95%
[00:06:19] here and it's passed all but one of the
[00:06:22] scenarios. So, this is a very good
[00:06:24] result here. Now, again, if you're
[00:06:25] familiar with this test, you'll probably
[00:06:27] know the one it hasn't passed. The most
[00:06:29] difficult one is unlucky task number 13.
[00:06:32] So, let's see if it's the one. And it
[00:06:34] is. Yeah. So this is the one where the
[00:06:36] model must chain multiple tools together
[00:06:39] to reach the desired outcome of the
[00:06:41] currency conversion to go from USD to
[00:06:44] Japanese yen. So there's no direct tool
[00:06:46] to go from USD to Japanese yen. But you
[00:06:49] can go through a chain of tools to reach
[00:06:51] this outcome. And the model has not done
[00:06:54] it here. It's uh it's basically answered
[00:06:56] saying the pairs that are available. So
[00:06:59] let's see how this compares to Quen.
[00:07:01] Okay. So we've now got Quen on the right
[00:07:03] side here. And it's looking like the
[00:07:06] same story again from the overview. So
[00:07:09] if we go down to 13 and just confirm.
[00:07:13] Yes, it is 13. So if we put them side by
[00:07:16] side for the outputs, let's see what the
[00:07:18] model's answer is. Okay, so Quen has
[00:07:21] done slightly better here. So Quen has
[00:07:24] found the chain required but it has not
[00:07:27] successfully called the convert currency
[00:07:29] at the end which a lot of models do fall
[00:07:31] over at that very last step. So what
[00:07:33] they do once they have the numbers they
[00:07:35] do the currency conversion sort of in
[00:07:37] their head rather than using the
[00:07:39] internal tool which is specified within
[00:07:41] the company like use this for currency
[00:07:44] conversion. So it's kind of ignored the
[00:07:46] tool that is supposed to be used for
[00:07:48] currency conversion and done it itself.
[00:07:50] So, it's slightly closer basically with
[00:07:53] the result from Quen, but not quite
[00:07:55] there. So, Quen does do slightly better
[00:07:57] on this test, but it's only just a very
[00:08:00] small amount better on this one. A small
[00:08:02] win for Quen. So, next we're going to be
[00:08:05] looking at our OpenAI human eval. So,
[00:08:07] OpenAI human eval
[00:08:11] themselves. And this is essentially 164
[00:08:14] handwritten Python coding challenges
[00:08:16] where the code is actually run in the
[00:08:18] evaluation stage to check for
[00:08:20] correctness as well. So I'll have this
[00:08:22] link down below if you'd like to have a
[00:08:24] read yourself and maybe even run this
[00:08:25] test yourself too. Otherwise, let's jump
[00:08:28] in. So here are the results for ONRIF.
[00:08:31] So okay, so it hasn't answered all the
[00:08:33] questions here. So 45 were unanswered.
[00:08:37] Usually, this means the model has burned
[00:08:39] up all of its budget thinking. Uh, some
[00:08:42] models tend to do this. Some models
[00:08:44] won't though, and they will just answer
[00:08:46] every single question. So, maybe I could
[00:08:49] increase the thinking allowance on this,
[00:08:50] but it's already quite generous. So,
[00:08:52] typically, if the model hasn't answered
[00:08:55] already by now, it's probably just
[00:08:56] thinking too much. But, I'll consider
[00:08:59] upping the budget. But, if we look at
[00:09:00] the results we have here, so of the ones
[00:09:03] it's answered, it's actually got a 97%
[00:09:05] pass rate. So that's very good. But then
[00:09:07] if we score it based on its total
[00:09:10] answers and non-answered, it's scored
[00:09:12] 70%. So it's not too bad. The once it's
[00:09:14] done, it's done well, but it's just
[00:09:16] spent a lot of time thinking. So let's
[00:09:18] see how this compares to Quen. Okay, so
[00:09:20] we've got Quen on the right here. So
[00:09:22] Quen has answered more questions. It's
[00:09:25] only unanswered 29. So there's obviously
[00:09:28] some part of this model that obviously
[00:09:31] likes to think a lot. Now, I noticed
[00:09:32] that Ornith is actually trained on Quen
[00:09:34] and Gemma. And I know Gemma likes to
[00:09:37] think a lot, like more than Quen, I
[00:09:39] would say, from experience. So maybe
[00:09:40] this is the the Gemma part of the
[00:09:42] training in Onif that's causing it to
[00:09:45] answer less. Just a theory. So we've got
[00:09:48] 98% from Quen on the ones it's answered
[00:09:51] and then an 80% overall. So the win
[00:09:54] definitely does go slightly to Quen on
[00:09:57] this one, but again, it's not a huge
[00:09:59] lead. So, not a bad result from either
[00:10:02] model, but it would be nice to see them
[00:10:03] answering more. Okay, so we're going to
[00:10:06] go into our coding challenges now.
[00:10:08] Starting with the sand physics
[00:10:10] simulator. I've got the prompt here.
[00:10:12] Feel free to pause the video if you'd
[00:10:14] like to read it, but you can also find
[00:10:16] this linked down at the GitHub in the
[00:10:17] video description. So, I'm going to copy
[00:10:19] this prompt and I'm going to paste it
[00:10:21] over to ORNIF first. And we are running
[00:10:24] this in Pi as I've been quite enjoying
[00:10:27] this harness lately. So happy to keep
[00:10:30] going with this. So we'll let this run
[00:10:32] and then we'll check back in when
[00:10:34] there's something to see. Okay. So has
[00:10:37] come back with sand physics. It's given
[00:10:40] us a nice summary of what's been done.
[00:10:43] So I'm going to run mpx serve in the
[00:10:47] directory which will serve an html if it
[00:10:49] exists. It does. So let's run it and see
[00:10:52] what we've got. Okay. So it's in / sand,
[00:10:56] right? Let's make that a little bit
[00:10:58] bigger. We go. Visually looks very nice.
[00:11:02] So, let's go with sand. Yep, that's
[00:11:04] working. It's nice and snappy as well in
[00:11:07] terms of performance. I like to see
[00:11:08] that. Water. Let's try a different brush
[00:11:11] size.
[00:11:14] Yep, that's working nicely.
[00:11:17] We also have some different colors going
[00:11:19] on here. Interesting.
[00:11:21] And let's put down some wall tiles. So,
[00:11:27] that's working. We'll do our usual fill
[00:11:30] the
[00:11:32] wall up. See the overflow. Yep, that's
[00:11:35] working.
[00:11:36] And then let's use the acid material
[00:11:39] which had burned through the others.
[00:11:42] And it does.
[00:11:44] Wow. There we go. One shot done from
[00:11:46] Ornith. So a very good start on the
[00:11:49] coding challenges here. So let's move on
[00:11:51] to Quen and see how it compares. Okay,
[00:11:53] so we'll give the exact same prompt over
[00:11:56] towen 3.635b
[00:11:58] A3B and see how it does. Okay, Quen has
[00:12:02] come back and I can say it definitely
[00:12:04] took longer than ORNIF and it even
[00:12:07] reached the context limit and needed to
[00:12:09] compact. So it said 32,000 tokens
[00:12:13] exceeds the available 327,000.
[00:12:16] So I'm assuming I don't know wanted to
[00:12:19] do something that was 32K because our
[00:12:21] total context as you can see here is 64K
[00:12:24] basically. So this would suggest to me
[00:12:27] that it it was at 32 and it was trying
[00:12:29] to do something that needed another 32.
[00:12:31] So I'm not quite sure what went on but
[00:12:34] it definitely took longer. It definitely
[00:12:36] burned a lot more tokens. But let's see
[00:12:38] the result. So as usual we'll run our
[00:12:40] MPX serve in the directory. It's now
[00:12:42] serving the HTML that seemingly does
[00:12:44] exist. So, let's run that. Okay. Yep.
[00:12:48] This is looking decent. Just zoom out.
[00:12:51] Make sure I'm not missing anything. Yep.
[00:12:52] Okay. So, got sand. So, let's place
[00:12:56] that. Yep, that works. So, I can see
[00:12:58] it's added like a texture to the
[00:13:00] background here to the canvas, which is
[00:13:02] quite nice. We'll go for a bigger brush.
[00:13:06] We'll do water.
[00:13:08] Oh, okay. That's a bit of a fail on the
[00:13:12] water physics there. Uh, wool. Okay. I
[00:13:16] was expecting maybe the wool would do
[00:13:18] that, too. So, interestingly, you can
[00:13:20] place the wool through the water, but
[00:13:21] not the sand. I mean, that kind of does
[00:13:23] make sense.
[00:13:24] And then we'll go with the acid.
[00:13:28] Okay. So, yeah, the physics are a bit
[00:13:32] a bit weird here, that's for sure.
[00:13:38] Yeah,
[00:13:39] it looks kind of cool, but and we've got
[00:13:41] an erase, which is kind of nice,
[00:13:44] but um yeah, this is definitely not
[00:13:49] ideal. So, I guess we can give it
[00:13:50] another prompt and see if we can sort
[00:13:52] these problems out. Okay, so Quen has
[00:13:55] come back after a few minutes and
[00:13:57] claimed fixes have been made. So, we'll
[00:13:59] reload this and then we'll try again.
[00:14:01] So, sand was already okay.
[00:14:05] water. That's better. Let's do the
[00:14:07] walls.
[00:14:09] Yep. Cool. Let's fill that up. Yep. Very
[00:14:13] nice. And then if we place the acid.
[00:14:17] Yep. That's working as it should as
[00:14:19] well. And then we can do some erasing
[00:14:21] here too, which is pretty nice. So,
[00:14:24] okay. Wasn't quite a one shot, but it
[00:14:27] did get there. But it definitely got
[00:14:29] there slower and it burnt a lot more
[00:14:31] tokens than Ornif. So, a win from onif I
[00:14:34] would say on this. Okay, so on to the
[00:14:37] next one. Our dungeon crawler where
[00:14:38] we're going to test if the model can do
[00:14:40] algorithms and random generation of the
[00:14:43] dungeon with ray casting. So, we're
[00:14:47] going to copy the prompt. As always, you
[00:14:49] can find it down in the GitHub link
[00:14:50] below. Let's pass that over to Ornif now
[00:14:53] and then we'll check back in when
[00:14:55] there's something to see. Okay, Ornith
[00:14:57] has come back with our dungeon crawler.
[00:15:00] There's a nice summary including the
[00:15:03] algorithm that it chose to use for the
[00:15:06] map generation and the fog of war. So
[00:15:09] let's see if it's done it. So MPX serve
[00:15:12] in the directory and let's have a look.
[00:15:15] Okay, so let's zoom out a bit. Yep.
[00:15:19] Right. So dungeon crawler. So our player
[00:15:23] does not move. The ray casting is just
[00:15:27] one pixel around.
[00:15:29] God mode does work. There's no map. So
[00:15:33] yeah, this is this is okay. I mean, we
[00:15:36] have something, but yeah, a lot of the
[00:15:38] key components are missing. So let's go
[00:15:40] back to with this and get something
[00:15:42] better going. Okay, so has come back
[00:15:46] with fixes that it's done. It's given us
[00:15:49] a nice problem cause and then fix table
[00:15:52] here. So that's nice to see. So I'm just
[00:15:56] going to reload our server and then
[00:15:59] let's see.
[00:16:03] Seems exactly the same. Let me check the
[00:16:05] console. There are no errors in the
[00:16:07] console.
[00:16:09] H.
[00:16:12] Okay, let's go back to ONRIF then.
[00:16:16] Okay, so it looks like we've got a
[00:16:19] working result from Ornif now, but it
[00:16:21] took a lot to get here. So, we're going
[00:16:23] to jump in, refresh, make sure I've got
[00:16:25] the latest. So, as we can see, we can
[00:16:29] move around the dungeon.
[00:16:31] The fog of war is working. The ray
[00:16:34] casting is working. So, it's it's
[00:16:36] working really nice. We've got a really
[00:16:39] nice result here. Now, we can
[00:16:41] regenerate. That works. God mode.
[00:16:45] So everything is working very nice now.
[00:16:49] But it took a lot to get here. Many many
[00:16:53] shots. So the same problem would persist
[00:16:56] where what you saw before where we just
[00:16:58] had a single pixel for the player. We
[00:17:00] couldn't move. There was no ray casting,
[00:17:02] nothing really. I would tell it that the
[00:17:05] problems that were there, I would list
[00:17:06] what needed to be fixed as you can see
[00:17:09] here. And it would come back. Problem
[00:17:11] wouldn't be fixed. Nothing's changed.
[00:17:13] Multiple times I kept telling it and
[00:17:15] multiple times it would come back
[00:17:17] exactly the same. And then eventually
[00:17:19] the model decided, okay, let's start
[00:17:21] outputting some debug into the page. And
[00:17:24] once the model did that, which is what
[00:17:27] you're seeing up here, I was able to
[00:17:29] give that to the model and then it would
[00:17:31] think, it would try and fix it. But even
[00:17:33] then, it took maybe another three
[00:17:35] prompts of keep passing the debug back
[00:17:38] to the model. It kept extending the
[00:17:40] debug. It kept getting longer, but the
[00:17:42] model did recognize what was going wrong
[00:17:45] each time and iterated through. It
[00:17:47] definitely wasn't so easy like the sound
[00:17:49] physics for the model to get here. But,
[00:17:51] you know, the model understood like when
[00:17:53] you're a programmer and you encounter a
[00:17:55] problem, this is exactly what you do.
[00:17:57] You start outputting the logs and what's
[00:18:00] happening so that you can understand
[00:18:01] where the code's failing. So once the
[00:18:03] model started behaving like that and I
[00:18:05] could work with it and give it the debug
[00:18:07] output, we did eventually get to this
[00:18:09] result which you can see is actually
[00:18:11] really nice now. So yeah, a bit of back
[00:18:13] and forth, bit of hard work to get
[00:18:14] there, but the end result is really nice
[00:18:16] now we're there. So let's see how Quen
[00:18:18] does. So we'll give the prompt over to
[00:18:20] Quen and fingers crossed it can get
[00:18:22] there a bit faster. Okay, Quen has come
[00:18:25] back. Took a few minutes. the first
[00:18:28] result after the initial prompt usually
[00:18:30] does take just a few minutes with both
[00:18:31] of these models. So, let's serve
[00:18:34] whatever's in the directory and then see
[00:18:37] what we've got. Okay, so ray casting is
[00:18:41] obviously
[00:18:42] decent. I mean, we don't know how it
[00:18:44] responds with walls because there are no
[00:18:47] walls, but seems like maybe just dungeon
[00:18:52] generation is missing here. So, let's go
[00:18:54] back to Quen. Okay, Quen says there are
[00:18:57] walls in the dungeon now. Just reload.
[00:19:00] Yep, there are indeed walls.
[00:19:03] However, the fog of war is not working.
[00:19:06] And there are undiscoverable places
[00:19:09] here.
[00:19:11] But let's get this fog of war fixed
[00:19:13] next, I think. Okay, so Quen has come
[00:19:16] back and it says the fog of war is
[00:19:17] fixed. So, let's refresh. Make sure
[00:19:19] we've got the latest. And yes, it looks
[00:19:22] like it is working. We have a very
[00:19:25] limited dungeon movement here. So,
[00:19:27] that's not great. It's more like a cave
[00:19:30] system almost. But yeah, it's okay. I
[00:19:34] reckon maybe just like one more prompt
[00:19:35] and you can probably get the sections
[00:19:38] joined up here. So, let's give Quen just
[00:19:40] another prompt and we'll get these areas
[00:19:42] in the dungeon fully discoverable. Okay,
[00:19:45] so Quen has come back and mentioned that
[00:19:49] the rooms should hopefully now be
[00:19:52] connected. So, refresh this and let's
[00:19:54] have a little explore.
[00:19:57] Yep, that's definitely looking better.
[00:19:59] Let's turn on god mode to confirm. Yep.
[00:20:01] Okay, so everything's joined. Everything
[00:20:04] is now reachable. So, yeah, we've made
[00:20:06] it with Quen. So, a few prompts to get
[00:20:09] there. It looks like neither model
[00:20:11] really nailed it on this task. They both
[00:20:14] needed some multiple prompting, a bit of
[00:20:16] back and forth on what was going wrong,
[00:20:18] and they both did struggle a bit with
[00:20:19] this one. So, I don't know, maybe it's a
[00:20:21] tie on this one between the two models,
[00:20:23] but they both got there in the end. So,
[00:20:25] yeah, not too bad. So, that brings us to
[00:20:28] the end of this video on ONRIF with the
[00:20:31] comparison against Quen with the 35B
[00:20:33] variants. So, the conclusion I'm getting
[00:20:35] from this is on the performance, the
[00:20:38] prefill the was about 20 tokens faster
[00:20:42] and then on decode it was about 10
[00:20:44] tokens faster. So, ornif was slightly
[00:20:46] faster in my test than Quen. Then on the
[00:20:49] memory test, they actually performed
[00:20:51] identically and they both performed very
[00:20:53] well at their full 256k context. So
[00:20:56] that's really good to see. Then on the
[00:20:58] agency benchmark, they performed almost
[00:21:01] identically on that as well, but there
[00:21:03] was just a slight edge for Quen on that
[00:21:05] one, but very close. Maybe a different
[00:21:08] seed and the result could have been
[00:21:09] different. Then on the OpenAI human
[00:21:12] eval, the Quen version did do slightly
[00:21:14] better than Ornith. It answered more
[00:21:16] questions. From the questions they
[00:21:18] answered, they both did get a very
[00:21:20] similar pass rate. So maybe if they had
[00:21:22] more thinking budget or they didn't
[00:21:24] overthink, they could be quite in line
[00:21:26] in the score there. So a win to Quen
[00:21:29] simply because it spent less time
[00:21:30] thinking and answered. Then for sand
[00:21:33] Physics, Ornith was the winner on that
[00:21:35] one. It one-shotted it and it got it
[00:21:37] straight away. It was perfect really.
[00:21:39] And then on Quen, it wasn't far behind.
[00:21:42] It just required an extra prompt to get
[00:21:45] there. So not too bad. And then on the
[00:21:48] dungeon crawler, both models did
[00:21:49] struggle with this. So Ornith did take
[00:21:52] more prompting and more work to get to
[00:21:54] the end result. But again, it was quite
[00:21:56] close between them because neither model
[00:21:58] was perfect. So summary really is Ornif
[00:22:01] is basically as good as Quen, I would
[00:22:04] say. And this is their version one as
[00:22:07] well. Just like we saw with North Mini,
[00:22:09] they're on version one. So there is
[00:22:11] definitely hope that can perform better,
[00:22:13] I think. So, what I want to do next is I
[00:22:16] actually want to do some more coding
[00:22:18] challenges between these two models. So,
[00:22:20] I think we're going to do in the next
[00:22:21] video, we're probably going to do these
[00:22:22] two models and we're going to do the
[00:22:24] perhaps the 2D driving game, the fake
[00:22:27] desktop coding challenge, and perhaps
[00:22:29] the agents in a maze as well. So, then
[00:22:32] we can really look into this because
[00:22:34] they're so close at the moment. I want
[00:22:36] to see if there is a clear winner in any
[00:22:38] any aspect. And then perhaps after that,
[00:22:40] I will move on to look at the 9B version
[00:22:42] of this model. and then we can compare
[00:22:44] that to the Quen 9B as well. So, I know
[00:22:46] a lot of you have been asking me to look
[00:22:48] at some smaller models, so it would be
[00:22:49] good to do that, too. So, that concludes
[00:22:51] it for this video. Give the video a like
[00:22:53] if you enjoyed it, and subscribe if you
[00:22:55] want to see more content like this. Bye.
