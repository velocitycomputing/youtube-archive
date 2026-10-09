---
record_id: "youtube:eohlvJj8CiY"
video_id: eohlvJj8CiY
title: NEW Gemini 3.7 is FAST
channel: Mehul Mohan
url: "https://www.youtube.com/watch?v=eohlvJj8CiY"
watched_date: 2026-08-13
watched_at: "2026-08-13T12:00:00Z"
watch_count: 1
duration_seconds: 801
source: youtube-history-browser
added_date: 
history_label: Aug 13
history_order: 76
watched_at_precision: date-from-history-label
watched_percent: 73
estimated_watched_seconds: 585
transcript_status: fetched
transcript_content_hash: 10d5dbd1eb6b6312b04f8578c22b6ec8d60942be7b711b52d54ff16e63aa3b0d
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

The video covers Google's release of Gemini 3.7 Flash, which the presenter says is not the smartest model. Frontier models, open-weight models like Kimi and Qwen, and even Meta's Muse Spark all score higher on intelligence. Its selling point is speed: about 340 tokens per second on Artificial Analysis, against roughly 150 for GPT 5.6 and about 52 for Opus 5 Max. That makes it six to seven times faster than Opus. It also has an introductory price at half of Gemini 3.6 Flash's, and 3.6 Flash was released only a couple of weeks earlier. The presenter argues that speed gives you faster feedback loops for coding and a better experience in consumer apps like chatbots and support systems. A 14-second wait would become about 2 seconds. In a live test, a security review of an internal project took 2 minutes 38 seconds for about 90,000 tokens of work, which was slower than he expected because of tool calls. He estimates Opus or Fable would take 10 to 15 minutes on the same job. The video also includes a sponsor segment for TestSprite, an agent that runs end-to-end tests through the web or a CLI. The last part shows DeepSeek's new browser-based harness, which you start with an NPX command. It shows time to first token, tokens per second, cache hit rate, and a "trajectory" view of the full system prompt and AGENTS.md handling. It supports OpenRouter, and Gemini 3.7 Flash ran in it at roughly 203–231 tokens per second.

For your own work, consider Gemini 3.7 Flash for latency-sensitive jobs: customer-facing chat, support bots, and quick iterative coding where you can accept a few follow-up prompts to fix mistakes. Keep a stronger model such as Opus or Fable for hard reasoning tasks. Check the current speed, price and intelligence numbers on Artificial Analysis before committing, and take advantage of the introductory half-price rate while it lasts. Run one of your own tasks on it to measure real speed, and don't rely on a multi-tool code review as the benchmark, since the presenter found that slows it down. If you prefer to see what your agent is doing, try DeepSeek's browser harness with an OpenRouter key. It lets you compare models side by side and watch cache hits and token speed, though the presenter notes the model picker lacks search. TestSprite is free for the first month through the presenter's link. It may be worth trying if you ship AI-written code without end-to-end tests. Treat the sponsor's claims with the usual caution.

## Transcript

[00:00:00] So, Google released a new model today,
[00:00:02] Gemini 3.7 flash, and this is a big
[00:00:05] deal. I'm not saying this is the best
[00:00:07] frontier model out there, and you know,
[00:00:09] it's number one and so on. It is
[00:00:11] definitely not number one if you go by
[00:00:12] benchmarks and even feel.
[00:00:15] But, I'm going to tell you why it is an
[00:00:16] important release and why you should be
[00:00:18] excited about this. But, before we get
[00:00:20] to that, let's actually take a look at
[00:00:22] what this model is and how is this
[00:00:24] improvement over Gemini 3.6 flash, which
[00:00:27] was literally just a couple of weeks
[00:00:30] ago. I can I can actually remember like
[00:00:32] that's happening like last week or last
[00:00:34] to last week when they released 3.6
[00:00:36] flash and a cyber variant of that model.
[00:00:39] And now we have 3.7 flash, which is
[00:00:43] better than Gemini 3.6 flash, but at the
[00:00:46] same time with an introductory price of
[00:00:48] half of the original 3.6 flash cost per
[00:00:51] million tokens. So, it's 50% discounted
[00:00:53] over 3.6 original price as well. And if
[00:00:55] you look at artificial analysis, the
[00:00:57] Gemini 3.7 flash model weirdly stands
[00:01:01] out from all the other models, right?
[00:01:02] It's a 340 tokens per second model, a
[00:01:05] lot faster than what we have seen
[00:01:07] generally, you know, LLMs spitting out.
[00:01:11] Even with GPT 5.6 Luna Max, you can see
[00:01:13] like we are getting north of 150 tokens
[00:01:15] per second. Now, if you look at
[00:01:17] intelligence wise,
[00:01:19] 3.7 flash is not a particularly very
[00:01:23] intelligent model compared to frontier
[00:01:25] models, right? We still have the whole
[00:01:27] GPT 5.6 data and salt class of models
[00:01:30] over here. We have fable, opus, even
[00:01:33] grok, and open weight models like Kimi
[00:01:36] and Quinn in front of this 3.7 flash.
[00:01:40] Even Facebook's Muse spark is
[00:01:43] intelligent compared to 3.7 flash.
[00:01:46] But, don't let it fool you from the fact
[00:01:50] that this is indeed a faster model. And
[00:01:53] that is why, you know, I wanted to
[00:01:56] uh tell you why you should be excited
[00:01:58] about this model. And this is the
[00:02:00] reason. As a programmer, you might be
[00:02:02] habitual to AI being slow, right? It
[00:02:04] taking a lot of time for processing your
[00:02:06] code or, you know, just doing something,
[00:02:08] um, in a loop that you are just giving
[00:02:10] it away for a few hours of time and just
[00:02:12] heading off. But real AI applications
[00:02:15] where consumers are involved, like for
[00:02:17] example, a chatbot or something which is
[00:02:19] a support system, ideally that should be
[00:02:21] very fast, as fast as possible. So, the
[00:02:24] speed is actually a very, very good
[00:02:27] thing about this model, which is almost
[00:02:29] a feature, right? We don't really talk
[00:02:31] about model speed as a feature,
[00:02:34] but I would myself work a lot more with
[00:02:38] AI if models are faster. Because if they
[00:02:40] are faster, you will have faster
[00:02:42] feedback loop. That means you will get
[00:02:43] more stuff done
[00:02:46] every single iteration, every single
[00:02:47] time you're sitting with a model, you
[00:02:49] will get more things done. Now, granted
[00:02:51] that this is like, uh, not as
[00:02:53] intelligent as Opus 5 Max, but if you
[00:02:56] look at Opus 5 Max speed, it's 52 tokens
[00:02:59] per second, right? Roughly. This one
[00:03:01] over here is 340, which is about six to
[00:03:04] seven times faster, right? That means
[00:03:07] what Opus is taking, let's say, six
[00:03:09] hours to do, Gemini 3.7 Flash
[00:03:13] might take 1 hour to complete like the
[00:03:15] baseline work, and let's say you need
[00:03:16] like 30 minutes of more prompting for
[00:03:19] fixing the stuff it got wrong.
[00:03:22] Right? So, you'll still end up with a
[00:03:23] complete work in less than 2 hours. This
[00:03:26] is a direct thing for your own coding,
[00:03:28] your own programming work, but this
[00:03:30] generally applies for consumer apps as
[00:03:32] well, right? Where if somebody is
[00:03:34] waiting for, let's say, 14 seconds in
[00:03:37] order to get a response, at a 7x boost,
[00:03:39] they will just wait 2 seconds. Which
[00:03:41] makes a lot of difference if you talk
[00:03:43] about UX of the application. So, let's
[00:03:45] take Gemini 3.7 Flash for a spin as
[00:03:47] well, just to get a feel of the speed
[00:03:50] over here. I am inside one of my
[00:03:51] internal directory, so I'm just going to
[00:03:53] give it a prompt. Can you go ahead and
[00:03:55] do a quick security review of this
[00:03:56] project? You are also live on YouTube,
[00:03:59] so avoid speaking anything which is
[00:04:02] sensitive data, right? Just don't show
[00:04:04] it on the screen. All right, so I'm just
[00:04:05] going to hit enter and we're going to
[00:04:07] see from this point onwards how fast the
[00:04:09] model is. I'll try to not have guts in
[00:04:12] the video, right? Now, we're going to
[00:04:13] have a lot to discuss about Gemini 3.7
[00:04:15] Flash and Deep Seek's new harness in
[00:04:18] this video. But, before we get into
[00:04:19] that, I want to introduce you to today's
[00:04:21] sponsor, which is Test Sprite. Now, if
[00:04:23] you're using AI to ship code, which I
[00:04:24] know you are, then you should use a
[00:04:27] product like Test Sprite. This is
[00:04:29] because if you are not doing E2E API,
[00:04:31] visual, or regression testing with your
[00:04:33] code bases, you are doing it wrong.
[00:04:35] Think of Test Sprite as an agent which
[00:04:37] helps you build tests, run them, store
[00:04:40] the output, and do everything end-to-end
[00:04:43] testing your application like a real
[00:04:44] user. And you can get started with Test
[00:04:46] Sprite in less than 2 minutes, either on
[00:04:49] web or through CLI as well by giving
[00:04:52] your AI agent like Claude Code, like
[00:04:54] Cursor, or even Gemini access to Test
[00:04:57] Sprite CLI. Let me show you how it
[00:04:59] works. The moment you sign in, you're
[00:05:00] going to see you have the ability to
[00:05:02] create web tests or MCP tests, and both
[00:05:05] of them can also be created from your
[00:05:07] CLI. When you configure your Test Sprite
[00:05:09] CLI and ask your agent to use it, Test
[00:05:12] Sprite is going to go ahead and create
[00:05:14] multiple tests which test your product
[00:05:16] end-to-end by actually browsing it like
[00:05:19] a real user. It will list down the steps
[00:05:21] and it's going to give you an option to
[00:05:22] export these results to GitHub as well.
[00:05:25] The tests which are getting blocked or
[00:05:26] are actually failing can be further
[00:05:29] fixed by Test Sprite itself using your
[00:05:31] own AI harness. Getting started with
[00:05:33] Test Sprite CLI is super simple. All you
[00:05:36] have to do is install the CLI and let
[00:05:38] your AI agent set it up with your
[00:05:40] account. The whole project, everything
[00:05:42] that I've just shown you on the web, can
[00:05:44] be created and managed using your Test
[00:05:47] Sprite CLI by your agent, so you don't
[00:05:49] have to do it. TestRight is used by some
[00:05:51] of the best companies in the world, so
[00:05:53] you are definitely in good company. And
[00:05:55] of course, if you are not testing your
[00:05:57] applications before shipping it to end
[00:05:58] users, you are doing it horribly wrong
[00:06:01] because in today's time when AI is
[00:06:03] shipping so much code, you want to make
[00:06:05] sure that you are shipping code that
[00:06:07] actually works. Getting started with
[00:06:09] TestRight is free of cost, and if you
[00:06:10] use my link in the description, you're
[00:06:12] going to get starter plan completely
[00:06:14] free for the first month. So, once
[00:06:15] again, thanks to TestRight for
[00:06:17] sponsoring this part of the video. Do
[00:06:18] check them out. All the links are in the
[00:06:20] description. And now, back to the video.
[00:06:23] So, let's see. So, this is
[00:06:28] I mean
[00:06:35] Let's wait for the text to start
[00:06:38] streaming because that is
[00:06:40] like a place where we can actually tell
[00:06:41] how fast the model is.
[00:06:56] I mean, I definitely thought that this
[00:06:57] would be faster than what I'm perceiving
[00:07:01] personally, but I mean, obviously, I
[00:07:03] know like, you know, code review is
[00:07:04] generally like an expensive thing to do
[00:07:07] when you have to do a lot of files and
[00:07:09] searches and stuff. But, let's see.
[00:07:22] So, it's already up to 53,000 tokens
[00:07:26] here.
[00:07:28] Um
[00:07:30] Okay, probably code review is not the
[00:07:32] best
[00:07:33] thing to give a model when you want to
[00:07:35] just check the model speed
[00:07:38] because this is definitely slow to work.
[00:07:41] And I'm assuming this is all of this is
[00:07:42] because of
[00:07:43] you know, multiple tool calls and stuff
[00:07:45] that is happening.
[00:07:47] Um
[00:07:50] but yeah, let's see.
[00:08:12] All right. So, now we see that the model
[00:08:14] sort of like streams fast.
[00:08:17] And this took about 2 minutes and 38
[00:08:20] seconds in total to do about 90,000
[00:08:23] tokens worth of work. I'm sure like if
[00:08:26] you give Fable or Opus any of this,
[00:08:29] it'll easily take like 10 to 15 minutes
[00:08:32] without any doubt, right? They generally
[00:08:34] tend to spend a lot more time. I mean, I
[00:08:36] wouldn't be surprised if Opus also
[00:08:38] spends up like sub- some sub-agents or
[00:08:40] something in order to get even better
[00:08:42] clarity. But yeah, the model is
[00:08:44] definitely faster than your typical
[00:08:46] model. On to the next thing. So, now we
[00:08:48] have DeepSeek's official harness
[00:08:50] available as well. For the first time,
[00:08:53] DeepSeek is providing you its own
[00:08:55] harness that you can use instead of just
[00:08:58] using open code or you know, any other
[00:09:00] harness that you're using.
[00:09:02] And surprisingly, this harness is built
[00:09:05] to run inside a web browser. Now, I have
[00:09:08] actually tried it, and it's actually
[00:09:10] fun. It's not bad. Look at this harness
[00:09:13] over here. So, I did sort of try a run
[00:09:15] over here. Again, like a same security
[00:09:17] audit sort of thing. But if you look at
[00:09:19] this harness, this is running inside
[00:09:20] browser. The moment you write that NPX
[00:09:22] command, it'll give you a URL which you
[00:09:24] can start. And if you look at this, this
[00:09:26] sort of looks like ChatGPT-based
[00:09:28] interface.
[00:09:30] I mean, the look and feel is sort of
[00:09:31] like similar to Codex.
[00:09:34] And you know, generally,
[00:09:36] but this is inside a website and you can
[00:09:38] customize a bunch of these things
[00:09:40] including the folder which is mounted on
[00:09:43] your computer inside this, right? So,
[00:09:45] you just select sort of like a folder, a
[00:09:47] workspace folder and you just work into
[00:09:48] that.
[00:09:50] Then you have a model selector over here
[00:09:52] and the effort as well. Now, one thing I
[00:09:54] really, really liked about this harness
[00:09:56] is that it gives you a lot more
[00:09:58] information. Just look at this over
[00:09:59] here. It gave me the time to first
[00:10:02] token. It gave me tokens per second and
[00:10:05] it gave me cache hit as well. It's 0%
[00:10:07] because it's the first message right
[00:10:08] now.
[00:10:09] But if I just write, "How are
[00:10:12] you?" You're going to see that the cache
[00:10:14] hit will start to climb up.
[00:10:16] Right? Because again, like I explained
[00:10:19] you in one of the videos how cache rate
[00:10:21] works. But the other thing which is
[00:10:22] there is this trajectory over here.
[00:10:25] Right? Which is a complete breakdown
[00:10:27] into how the model is working in the
[00:10:29] first place including the system prompt.
[00:10:31] And this is actually pretty cool. It
[00:10:33] automatically included the agents.md
[00:10:36] file inside the system reminder over
[00:10:37] here and the system prompt is this
[00:10:39] exactly.
[00:10:43] Right? It's very, very transparent, very
[00:10:45] easy to understand what the LLM is doing
[00:10:47] in the first place. I really like this
[00:10:50] sort of UI. Now, definitely this is sort
[00:10:53] of something I would say on the advanced
[00:10:55] side of things because your typical
[00:10:57] white coder would not sort of like
[00:10:59] understand this. But I really doubt like
[00:11:01] how many actual true white coders, like
[00:11:04] people who have zero knowledge about
[00:11:06] anything
[00:11:07] are anyway using apps like Codex or
[00:11:10] Cloud Code directly. They might be using
[00:11:12] something like lovable or Replit or
[00:11:15] emergent or, you know, something which
[00:11:16] are basic tools which are running in the
[00:11:18] website.
[00:11:20] But if you're using these offline tools
[00:11:22] and if you want to be in full control of
[00:11:24] what you are doing exactly, I think this
[00:11:26] is a great harness to try. The
[00:11:28] interesting thing here is that you can
[00:11:30] indeed configure multiple models. So, I
[00:11:32] just have Deep Seek right now, but you
[00:11:33] can do all of these models. And I I mean
[00:11:36] like you would basically have open
[00:11:37] router here as well, right? So, you can
[00:11:39] literally run Gemini 3.7 flash, which I
[00:11:43] just showed you inside this harness as
[00:11:44] well. As a matter of fact, let me just
[00:11:46] show you. Let's just also try if that
[00:11:49] works or not. All right, so inside open
[00:11:51] router, we have all these models coming
[00:11:53] in now, and I would really appreciate if
[00:11:55] we can have like a search bar of some
[00:11:56] sorts over here because this is
[00:11:58] definitely a nightmare to
[00:12:00] try like this. So, we have Gemini 3.7
[00:12:06] flash latest. Let's try this. How are
[00:12:09] you?
[00:12:10] And let's just wait for it to reply you
[00:12:12] back. And as you can see on the first
[00:12:14] two messages itself, we are sort of
[00:12:15] hitting like 203 tokens per second.
[00:12:18] Write me a engine X config and explain
[00:12:22] that. Right, so as you can see, this 203
[00:12:25] should now go up because we are now
[00:12:28] giving it a little bit of more writing
[00:12:30] space
[00:12:32] so as to improve its number. So, it has
[00:12:33] gone to 231 now, right? Which is pretty
[00:12:36] interesting. And again, if you go to the
[00:12:38] trajectory, you're going to see the same
[00:12:39] stuff. Other than this, you can sort of
[00:12:41] like define agent presets. You can even
[00:12:43] add multiple plugins.
[00:12:46] And they have a lot of such plugins,
[00:12:48] right? Which you can just add and just
[00:12:49] play around with this. So, I I like this
[00:12:52] harness generally. This could be
[00:12:54] something that I start using eventually.
[00:12:56] I am generally not a huge fan of
[00:12:58] UI-based harnesses. I've told this like
[00:13:01] a lot of times. I prefer CLI-based ones.
[00:13:03] But I mean, this is something which is
[00:13:05] super powerful, I feel.
[00:13:08] And it gives a lot of like
[00:13:09] customizations and stuff out of the box.
[00:13:11] So, definitely worth a try. So, yeah,
[00:13:12] that's pretty much it for this video.
[00:13:14] Hopefully, you liked it. If you did,
[00:13:15] make sure you leave a like and subscribe
[00:13:17] to the channel. I'm going to see you in
[00:13:19] the next video very soon.
