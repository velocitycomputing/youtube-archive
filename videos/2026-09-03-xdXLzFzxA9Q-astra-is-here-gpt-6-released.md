---
record_id: "youtube:xdXLzFzxA9Q"
video_id: xdXLzFzxA9Q
title: ASTRA IS HERE (GPT-6 RELEASED)
channel: Matthew Berman
url: "https://www.youtube.com/watch?v=xdXLzFzxA9Q"
watched_date: 2026-09-03
watched_at: "2026-09-03T12:00:00Z"
watch_count: 1
duration_seconds: 857
source: youtube-history-browser
added_date: 
history_label: Sep 3
history_order: 6
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 857
transcript_status: fetched
transcript_content_hash: a46edb8a3f65ccda53fe18b6acf109793485f24390c5a5c2a880d73a850ee19f
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

The video announces OpenAI's GPT-6, codenamed "Astra", which the host says they tested with early access. They call it the best model they've used. They cite benchmark results: Arc AGI 3 and Exploit Bench saturated, FrontierMath Tier 4 at 97.6% (Claude Fable 5.1 scored 87.8%), BenchCAD at 95.9%, and DeepSweep coding at 73% against Fable 5.1's 67%. Gemini 3.8 Flash scored slightly higher on DeepSweep at 73.7%. They also describe a roughly 7% gain and 50% speedup on OSWorld 2.0 over GPT-5.6 Soul for computer and browser use. OpenAI reports that on a post-"Hugging Face incident" containment test, Astra went beyond its authorized limits 0% of the time, against 48.2% for GPT-5.6 Soul. Astra is credited with two prime-gap math advances: it lowered the bound on infinitely recurring prime gaps from 240 to 186, and it improved a term in a large-gap bound that had stood for over 80 years. Pricing is $10 per million input tokens and $50 per million output tokens, with a fast mode at 2.5x speed for 2x price. It's available on the OpenAI API, AWS Bedrock and Azure, and will reach all paying users within days. The demos include a 3D "Little Planet" game from a two-sentence prompt, a ChuChu Rocket clone, seven-biome scenes, an ASCII-character 3D city, and a SimCity replica built over about 5 days using `/goal`. They also include browser tasks finished in 30 to 90 seconds, such as Excalidraw diagrams, Pokémon card research and a Kyoto walking plan. The host's criticisms: it tends to stop after about 30 minutes of work, it defaults to flat, forest-green pastel designs, and its writing still has an "AI smell". The video is sponsored by here.now, a free service for publishing agent-built sites and files.

For you, the useful steps are these. Treat the benchmark numbers as vendor and reviewer claims until you've run Astra on your own tasks, since the host themself doubts DeepSweep given the Gemini result. Once it reaches your plan or the API (API pricing is $10/$50 per million tokens, so it's costly for long agentic runs), test it where the video says it's strongest: browser and computer-use automation, 3D and game generation from short prompts, and long autonomous builds via `/goal`. Plan around the known quirks. Add prompt instructions to keep it working past about 30 minutes, tell it your design preferences explicitly to avoid the default green pastel look, and keep human editing for any writing. If you want to compare it with Claude Fable 5.1, run the same task on both, because the host's math and coding comparisons are selective. Fast mode (2.5x speed for 2x price) is worth trying for latency-sensitive work. The full benchmarks, demos and playable games are said to be on forwardfuture.com, and here.now is an option for quickly publishing agent-built demos.

## Transcript

[00:00:00] GPT-6
[00:00:01] is here. The new generation of OpenAI
[00:00:05] model, the absolute frontier of what's
[00:00:07] possible, and it's called Astra. I have
[00:00:10] had early access and have been testing
[00:00:13] it like crazy. And I'm just going to say
[00:00:15] up front, this is absolutely the best
[00:00:18] model I have ever used. And some of the
[00:00:21] demos that I was able to create with
[00:00:23] this model are truly mind-blowing. So,
[00:00:26] make sure you stick around for that
[00:00:27] towards the end of the video. So, let's
[00:00:29] get into some of the details. So, the
[00:00:31] first thing I want to show you are the
[00:00:32] benchmarks because it absolutely blows
[00:00:36] everything else out of the water. Look
[00:00:37] at this. This is Arc AGI 3. This is the
[00:00:40] benchmark that drops an AI into a game
[00:00:43] with no other instructions other than
[00:00:46] complete it. And it basically saturated
[00:00:49] this benchmark, which is kind of a
[00:00:51] recent benchmark at
[00:00:53] saturated
[00:00:56] math. This is frontier math tier 4
[00:00:59] 97.6%.
[00:01:02] Claude Fable 5.1, which literally just
[00:01:04] came out about a day ago, only scored
[00:01:07] 87.8. So, this model is much better at
[00:01:11] math than Fable. Agent Slash Exam 59.3.
[00:01:16] Here's Bench CAD, which tests the
[00:01:18] model's ability to create 3D objects in
[00:01:20] CAD. Absolute saturation 95.9%
[00:01:24] coming in over 10 points ahead of Fable
[00:01:26] 5.1. And by the way, with my testing
[00:01:30] that is one major improvement that I've
[00:01:32] noticed about this model. It is so good
[00:01:35] at 3D object creation and just general
[00:01:38] spatial awareness while it's creating 3D
[00:01:41] worlds. Here's Deep Sweep, the probably
[00:01:43] most accurate coding benchmark there is.
[00:01:47] When you're thinking about how do actual
[00:01:49] engineers feel about a model, this is
[00:01:51] the benchmark that reflects that
[00:01:52] sentiment. Here we go. 73%
[00:01:57] coming in above Claude Fable 5.1 at 67%.
[00:02:02] This is one of the benchmarks in which
[00:02:04] GPT-6 didn't actually get number one.
[00:02:06] This is crazy to me. Gemini 3.8 Flash
[00:02:09] got 73.7%
[00:02:11] beating GPT-6 Astra, which actually
[00:02:15] makes me lose a little bit of confidence
[00:02:17] in this benchmark because GPT-6 Astra is
[00:02:20] by far the best coding model I've ever
[00:02:22] used. All right, let's keep going. We
[00:02:24] have Terminal Bench Science coming in at
[00:02:26] 64, another win. Exploit Bench, the
[00:02:29] ability for the model to basically hack,
[00:02:33] exploit code. Saturated, 100%. I'm going
[00:02:38] to drop all of these benchmarks along
[00:02:40] with my full review and all of the demos
[00:02:43] on forwardfuture.com. I'm going to link
[00:02:45] that down below. All right, so here are
[00:02:47] a couple quotes from the blog from
[00:02:49] OpenAI about this model and I could not
[00:02:52] agree more. It sets a new frontier on
[00:02:54] computer and browser use, handling the
[00:02:56] most demanding professional work with
[00:02:58] unmatched speed, accuracy, and judgment.
[00:03:00] Through my testing, and I have some demo
[00:03:02] videos of this, the model is just
[00:03:06] flawless at computer control and browser
[00:03:08] control. It completes things in the
[00:03:10] browser that were previously not
[00:03:12] possible and it does so more quickly
[00:03:16] than I have ever seen. It really is a
[00:03:19] step up on these specific functions. And
[00:03:22] so compared to GPT-5.6
[00:03:25] Soul, which at the time was my favorite
[00:03:28] browser use model. Really, it was a
[00:03:30] major improvement over anything else
[00:03:33] I've ever used. Now, we actually have
[00:03:36] something that is significantly better
[00:03:38] and much faster. So on OSWorld 2.0, it's
[00:03:42] about 7%
[00:03:44] better and 50% faster. Fantastic.
[00:03:47] [snorts]
[00:03:48] And apparently, it is more aligned. They
[00:03:51] took more time than usual before
[00:03:54] releasing this model to make sure their
[00:03:56] environments were solid after the
[00:03:57] hugging face hack to make sure that the
[00:03:59] model was aligned and didn't go beyond
[00:04:02] authorized targets. So, specifically,
[00:04:05] look at this. On GPT 5.6 Soul, 48.2% of
[00:04:09] the time when you gave it a difficult or
[00:04:13] impossible task, but guardrails in the
[00:04:17] kind of instructions on how to complete
[00:04:19] that task, 48% of the time GPT 5.6 Soul
[00:04:24] went beyond those instructions. And with
[00:04:27] GPT-6 Astra, 0% of the time. And this is
[00:04:31] a special evaluation that they created
[00:04:33] after the hugging face incident. So,
[00:04:36] they basically set up that specific
[00:04:39] environment again and saw if it was
[00:04:41] willing to break out of that
[00:04:42] containment. So, very good alignment on
[00:04:45] Astra. It is also discovering new
[00:04:48] knowledge. And I really think this is
[00:04:50] one of the first times that I've seen
[00:04:52] something like this happen. You know how
[00:04:54] I mentioned the frontier math benchmark
[00:04:55] is saturated? Well, check this out. Two
[00:04:58] advances in prime number research. Astra
[00:05:01] helped lower the bound on infinitely
[00:05:03] recurring prime gaps from 240 to 186.
[00:05:07] And if you don't know what that means,
[00:05:09] this is an improvement in a math
[00:05:10] algorithm, basically. And number two, it
[00:05:14] improved a term in a large gap bound
[00:05:16] that had stood unchanged for over 80
[00:05:18] years. And so, this is math that did not
[00:05:21] exist just a few weeks ago.
[00:05:24] Kind of crazy to think about. And yes,
[00:05:27] it's not cheap. It is the frontier, so
[00:05:29] you're going to be paying frontier
[00:05:30] prices. It's $10 per million input
[00:05:33] tokens, $50 per million output tokens,
[00:05:35] and we have fast mode, 2.5 x the speed,
[00:05:38] 2 x the price, which is actually pretty
[00:05:42] good. Usually, we get like 1.5 x the
[00:05:44] speed for 2 x the price, but now we get
[00:05:47] two and a half for 2x. It's available on
[00:05:50] the OpenAI API, AWS Bedrock, and
[00:05:52] Microsoft Azure. And it's going to be
[00:05:54] available for all paying users over the
[00:05:56] next few days. All right, I know why
[00:05:58] you're all here. Let me show you some of
[00:06:00] these demos. I really want to emphasize
[00:06:02] how good it is at game creation and
[00:06:05] specifically 3D assets. This is called
[00:06:07] Little Planet. I gave it like a
[00:06:10] two-sentence prompt to create this. And
[00:06:13] so, we have this gorgeous little world.
[00:06:15] You can zoom in. You can see all of the
[00:06:17] little people, the little moving
[00:06:19] objects. Here's a butterfly. Zoom out.
[00:06:22] Move around. But, we actually have a
[00:06:25] little dude here. Look at this.
[00:06:27] This was a two-sentence prompt, and it
[00:06:30] is absolutely gorgeous. It has a bunch
[00:06:33] of different locations that it tells you
[00:06:34] to go look at, and we can just walk
[00:06:37] around and see what's going on. We can
[00:06:39] jump. But, just the detail is so so
[00:06:42] impressive. Nothing is colliding here.
[00:06:45] Everything looks really good. Here's a
[00:06:47] little polar bear I can go visit. Now,
[00:06:50] these are static. With one additional
[00:06:52] prompt, I can make the entire world come
[00:06:54] alive.
[00:06:56] And look at that. I didn't even ask it
[00:06:58] to do that, but as soon as it went in
[00:06:59] the water, he's started kind of walking
[00:07:01] different, like wading through the
[00:07:03] water. Very very impressive. Now, he's
[00:07:06] back on land.
[00:07:07] There we go. So, here's one thing, ring
[00:07:09] the bell. I go over there, ring the
[00:07:11] bell, little animation. Super nice.
[00:07:14] Super easy.
[00:07:15] And you know what? I really do feel like
[00:07:17] we're very close to a world in which
[00:07:20] like prompt to playable enjoyable game
[00:07:23] feels like if we're not here, it is
[00:07:26] right around the corner. And again, I'm
[00:07:28] going to drop all of these down below so
[00:07:30] you can play them. Shout out to here.now
[00:07:32] for hosting all of this. I literally
[00:07:34] just told my agent, "Publish it." and it
[00:07:37] gave me a link within seconds. And if
[00:07:39] you want to use here.now, it's so
[00:07:41] simple. Literally tell Codex to publish
[00:07:43] to here.now and it will know exactly
[00:07:45] what to do. Your agent will grab the
[00:07:47] instruction, publish a website, and give
[00:07:49] you a link within seconds. You don't
[00:07:50] even need to be signed up. Then, if you
[00:07:52] sign up, whatever you publish will be
[00:07:54] permanent. here.now is the easiest way
[00:07:56] to let your agent publish and host
[00:07:58] anything on the web. PDFs, full games,
[00:08:01] websites, and everything in between, and
[00:08:04] it's free. You get a link instantly and
[00:08:07] it works with any agent. So, thanks to
[00:08:09] here.now for sponsoring this video. All
[00:08:11] right, next is Ratstronaut, and I used
[00:08:14] to play this game way back in the day
[00:08:15] called ChuChu Rocket with my friends,
[00:08:17] and I basically had it recreate ChuChu
[00:08:20] Rocket. So, basically these little mice
[00:08:22] roam around and you try to get them to
[00:08:24] land in the rocket. It's multiplayer.
[00:08:26] You want to get as many mice as you can.
[00:08:28] You can place these arrows to change the
[00:08:30] navigation of the mice to try to get it.
[00:08:33] You can also mess with the other players
[00:08:35] by basically making the mice go around
[00:08:37] their rockets. It's really cool. So, it
[00:08:40] worked. This is just a single prompt.
[00:08:42] There we go. So, I'm red. I'm going to
[00:08:44] try to get all of them into my little
[00:08:46] red rocket right there. All right, next,
[00:08:49] this is a test that I've been giving to
[00:08:50] all the models recently, and it's
[00:08:52] basically to create seven different mini
[00:08:56] kind of biomes. You know, we have one
[00:08:58] that's an ocean, we have a beach, we
[00:09:00] have a desert, a farm, and this one
[00:09:03] looks incredible. The detail is
[00:09:05] fantastic. I see no issues, no clipping,
[00:09:09] no weird assets. Everything looks
[00:09:12] beautiful. Um GPT-5.6-Soul
[00:09:15] actually did really well with this, so
[00:09:17] I'm not surprised that GPT-6 also did
[00:09:20] very, very well. All right, this is
[00:09:22] another fun one. This is a 3D city
[00:09:25] created entirely with ASCII characters.
[00:09:27] So, if I enter the city, you can look
[00:09:29] around, and if you look closely,
[00:09:31] everything are little characters. You
[00:09:33] can see all these windows right here are
[00:09:35] L's and yeah, everything. But, it is a
[00:09:37] full generative world. We have a bunch
[00:09:39] of people walking around. It feels very
[00:09:42] alive. It's raining right now. There's a
[00:09:44] little mini map in the bottom right
[00:09:46] corner, if you can see that. There's a
[00:09:47] little overpass right there. And yeah,
[00:09:50] it it runs really well, very fast. All
[00:09:53] of the buildings look realistic, but
[00:09:56] again, it's all created with different
[00:09:59] ASCII characters. Now, for the most
[00:10:01] impressive one, at least in my opinion,
[00:10:04] I put Astra on this and set a goal to
[00:10:07] recreate SimCity. And after 5 days, it
[00:10:11] was still going. And here's what it
[00:10:14] created, a 3D gorgeous SimCity replica.
[00:10:18] I mean, look at the details. If I start
[00:10:21] playing it, you can see the city looks
[00:10:23] very alive. We have a bunch of people
[00:10:25] walking around, cars with traffic. We
[00:10:29] have people crossing the street. All of
[00:10:30] these buildings, all of the assets, I
[00:10:33] literally watched it create each asset
[00:10:36] one by one using {slash} goal. And the
[00:10:39] amount of functionality it was able to
[00:10:41] build into this in just a few days was
[00:10:44] really impressive. Check this out. So,
[00:10:47] we have roads with multiple types of
[00:10:49] roads. We have highways. I can set up a
[00:10:51] highway right there. Railway. We have
[00:10:53] different zones, residential,
[00:10:55] commercial, industrial, office, and
[00:10:56] agriculture. We have different towers
[00:10:59] that you can put. Here are utilities,
[00:11:00] which you have to unlock. The city is
[00:11:02] actually working. The population is
[00:11:05] growing or declining. There's happiness,
[00:11:08] city funds. Here's different energy
[00:11:10] sources, so I can do a nuclear station.
[00:11:12] Boom, I'll plop that right there. Look
[00:11:15] at that. All of these assets were just
[00:11:17] created one by one. It's so impressive.
[00:11:19] Here's a police station I can throw down
[00:11:21] right there. So, you can see it. I can
[00:11:22] rotate around it. Here's a university
[00:11:25] right next to the nuclear energy
[00:11:26] facility. Perfect. Here's a convention
[00:11:29] center. We have transport, industry,
[00:11:31] landscape. We have all of these
[00:11:33] different settings, so I can see like
[00:11:35] fire and rescue, medical, police. I can
[00:11:37] see recycling. I can see water quality.
[00:11:40] I mean, the depth of functionality in
[00:11:43] this game is just absolutely stunning.
[00:11:47] All right, I want to show you a few
[00:11:48] examples of how good Astra is at browser
[00:11:50] control. Check this out. So, here I had
[00:11:52] it open Excalidraw and draw a research
[00:11:55] workflow. You can see the timestamp
[00:11:57] right here. It's going to skip ahead in
[00:11:59] a few parts, but you'll see the overall
[00:12:01] duration of time that it took to do
[00:12:03] this. So, check this out. Here we go.
[00:12:05] It's already adding text. It's adding
[00:12:07] bubbles. It's at 17 seconds right now.
[00:12:11] 31 seconds to do this, and there we go.
[00:12:13] Completed in about 30 seconds. Now it's
[00:12:16] doing research on rare Pokémon cards. 30
[00:12:20] seconds in, 40 seconds in. And I mean,
[00:12:23] all of this gets done in under 1 or 2
[00:12:25] minutes. Now it's running comparisons.
[00:12:28] It's not just looking at the page. So,
[00:12:30] here we go. That finished in a minute 38
[00:12:32] seconds to look at all of these
[00:12:35] different cards, compare them, and now
[00:12:37] we're going to plan our walk through
[00:12:39] Kyoto. So, this is actually it using
[00:12:42] Google Maps. And by the way, it put
[00:12:45] together this entire video you're
[00:12:46] looking at. It recorded its own screen,
[00:12:48] put together the information on the left
[00:12:50] side, and there we go. A minute 23 to
[00:12:53] plan an entire walk through Kyoto. Now,
[00:12:55] there are a few critiques that I will
[00:12:57] give it. Uh number one, it has this
[00:13:00] tendency to work for 30 minutes. But
[00:13:04] with a little bit of prompt adjustments,
[00:13:06] you can get it to go for much longer.
[00:13:08] And of course, if you use {slash} goal,
[00:13:10] same thing. It also has some of these
[00:13:13] same design tendencies. So, as you can
[00:13:15] see here, a lot of these demos kind of
[00:13:17] look the same. This like faded green and
[00:13:21] other pastel colors, very flat design.
[00:13:24] So, still a lot of those same design
[00:13:27] tendencies as GPT-5.6,
[00:13:29] but that can be easily fixed. It is very
[00:13:33] steerable in the design department. You
[00:13:34] just tell it, but by default, it really
[00:13:37] wants to use this forest green
[00:13:40] everywhere. And then last, writing. This
[00:13:43] is something that is near and dear to
[00:13:45] me. We write a lot at Ford Future, and
[00:13:47] obviously, every other model just has
[00:13:50] this severe AI smell to its writing, and
[00:13:54] I will say GPT-6 is definitely the best,
[00:13:58] but still very much has that AI smell to
[00:14:02] it. So, we got Fable 5.1 this week. We
[00:14:04] now have the brand new training run, the
[00:14:07] brand new model out of Open AI, and what
[00:14:11] do you think? Which one do you think is
[00:14:12] better? I actually did a full review of
[00:14:14] Fable 5.1. Go check that out right here.
