---
video_id: 2OD14-0cot4
title: GLM 5.2 in Claude Code is Blowing My Mind
channel: "Nate Herk | AI Automation"
url: "https://www.youtube.com/watch?v=2OD14-0cot4"
watched_date: 2026-06-18
watched_at: "2026-06-18T12:00:00Z"
watch_count: 1
duration_seconds: 943
source: youtube-history-browser
added_date: 
history_label: Jun 18
history_order: 139
watched_at_precision: date-from-history-label
watched_percent: 23
estimated_watched_seconds: 217
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The creator tested GLM 5.2, an open-source 753B-parameter model available through Z.AI, and found it delivers comparable quality to Opus 4.8 while costing ~5x less. GLM 5.2 excelled at design tasks, creative HTML generation, and multi-agent research workflows—completing a complex research report with 5 different personas and verification passes, and creating website designs in under 4 minutes versus Opus's 15 minutes. On benchmark evaluations, GLM 5.2 beats Opus 4.7 and Sonnet 3.7 in many categories, though Opus remains superior for heavy reasoning tasks. The key insight: most knowledge work (80%+) doesn't require Opus's power—matching the right model to task type is a critical emerging skill.

To get started, sign up at Z.AI and grab an API key from their console, then add three environment variables to your `settings.local.json` in Claude Code: set `ANTHROPIC_BASE_URL` to Z.AI's endpoint, `ANTHROPIC_API_KEY` to your Z.AI key, and change default model names to `glm-5.2`. Z.AI offers plans ranging $16–$144/month or pay-per-token pricing ($1.40 input, $4.40 output). You can maintain per-project configurations by creating separate directories with different `settings.local.json` files, allowing you to use GLM 5.2 for design/research and Opus for reasoning-heavy decisions. Consider pairing a Z.AI subscription ($64/month) with a Claude plan ($100/month) and switch between them based on task requirements.

## Transcript

[00:00:00] So, I've been playing around with GLM
[00:00:01] 5.2 inside of Cloud Code all day, and
[00:00:04] it's incredible. It feels faster. It's
[00:00:06] significantly cheaper, and it just fits
[00:00:07] right into the Cloud Code harness pretty
[00:00:09] well. It's been doing so well, in fact,
[00:00:10] that it edited this entire intro that
[00:00:12] you're watching right now from raw video
[00:00:14] all the way to what you're watching. So,
[00:00:16] in today's video, I'm going to show you
[00:00:17] just how quick and easy you can get set
[00:00:19] up with GLM 5.2 in Cloud Code. So, let's
[00:00:21] not waste any time and just get straight
[00:00:22] into the video. So, obviously that intro
[00:00:24] wasn't perfect, but that was literally
[00:00:25] one prompt. It was one/goal right here.
[00:00:27] It took a little over an hour, an hour
[00:00:29] and 15 minutes for, you know, a 23
[00:00:31] second video. So, that did take a little
[00:00:32] bit long, but this was the session that
[00:00:34] we did it in. It was GLM 5.2 1 million
[00:00:37] context. As you can see right here, it
[00:00:39] used about 357,000 tokens. But, as I've
[00:00:41] been playing around with it more and
[00:00:42] more, there are some tasks where it
[00:00:44] finishes way faster than Opus. And then
[00:00:46] there are some like this one where Opus
[00:00:48] would have done this much quicker. So,
[00:00:49] I'm going to show you guys exactly how
[00:00:50] to get set up. But before that, let me
[00:00:51] just show you a few of the things that
[00:00:52] I've played around with and what GLM has
[00:00:55] been able to do. So, it's actually like
[00:00:57] really solid at design. I want you guys
[00:00:59] to look right here and see which one of
[00:01:01] these do you think was designed by GLM
[00:01:04] 5.2 and which one was designed by Opus.
[00:01:06] So, as we sort of scroll down here, you
[00:01:08] can see that we have, you know, similar
[00:01:10] style branding and it's obviously the
[00:01:11] same company, but we have elements on
[00:01:14] both that are very similar. We have all
[00:01:16] of these things come up dynamically as
[00:01:18] well on either side. And there's even a
[00:01:20] CTA at the bottom. I think the dead
[00:01:22] giveaway here is this right side was
[00:01:24] opus because it has these weird Fs that
[00:01:25] it loves to do. It loves that font. But
[00:01:27] either way, these are both very solid
[00:01:29] for a oneshot prompt. Especially when
[00:01:31] you consider the fact that you are
[00:01:33] getting this output for like five times
[00:01:35] cheaper. So these are the actual
[00:01:36] terminal sessions where we did those
[00:01:38] website designs. On the left side with
[00:01:40] GLM, we got this done in 3 minutes and
[00:01:42] 59 seconds. On the right side with Opus,
[00:01:43] we got this done in 14 minutes and 59
[00:01:45] seconds. And not only did the lefth hand
[00:01:48] side GLM use less tokens, but its cost
[00:01:51] per token is also five times cheaperish.
[00:01:53] So in this case, it was quicker and it
[00:01:55] was much cheaper and it was a relatively
[00:01:56] similar result. I also shot off this
[00:01:58] prompt on each side where I gave them a
[00:01:59] homework assignment. You can see right
[00:02:01] here we've got GLM and then right here
[00:02:02] we've got Opus 4.8. I had Codeex create
[00:02:04] the homework assignment just so there
[00:02:06] was no like crosscontamination or
[00:02:08] anything like that. And then when they
[00:02:09] finished, I had Codeex judge both
[00:02:11] results and tell us what it thought.
[00:02:13] Now, in this case, it said that agent 2,
[00:02:15] which was opus, was better because it
[00:02:17] handled one subtle edge case that agent
[00:02:18] one missed, which were duplicate records
[00:02:20] with values like true versus one or one
[00:02:22] versus 1.0. So, the short version is
[00:02:24] that agent 1, GLM 5.2 was good, but
[00:02:27] agent 2 here was more precise. And
[00:02:29] generally, the way that I feel about
[00:02:30] this so far is that GLM 5.2 is really
[00:02:33] solid and it's pretty quick for most
[00:02:35] tasks that don't require heavy
[00:02:36] reasoning. Obviously, at the end of the
[00:02:38] day, Opus 4.8 is a better model. It's a
[00:02:39] closed source model. But realistically
[00:02:42] ask yourself how often do you actually
[00:02:44] need the power of Opus? Probably only
[00:02:46] maybe 10 to 20% if that of the tasks
[00:02:49] that you do all day. You could probably
[00:02:50] handle 80% or more of your knowledge
[00:02:52] work with something like GLM 5.2 or
[00:02:54] something more like sonnet 3.7. So
[00:02:56] that's really going to be a key skill as
[00:02:58] we move into the future of AI is
[00:03:00] understanding which models to use per
[00:03:02] task. But here's an example where you
[00:03:04] can see Opus took about 5 minutes and
[00:03:05] GLM 5.2 took about 24 minutes. And this
[00:03:08] was me on a $60 a month plan for um Z.AI
[00:03:13] for GLM 5.2. And I've played around with
[00:03:16] this for this was about four or five
[00:03:18] hours straight of just literally
[00:03:20] hammering it. Five different sessions
[00:03:21] open, testing GLM 5.2. And my 5-hour
[00:03:24] quota is a little bit over halfway used.
[00:03:26] And my weekly quota is about 10% used.
[00:03:28] I'll talk about the billing and how to
[00:03:29] get set up in just a sec. Let me show
[00:03:30] you guys what else I did with it. So I
[00:03:32] did a few more/goal prompts. And I hate
[00:03:34] when the terminal does this, but this
[00:03:35] first one that I did was I did /goal and
[00:03:37] I literally said like, "Hey, get
[00:03:39] creative. Show me how good your design
[00:03:40] skills are and just build me whatever
[00:03:42] you want. Just make me an HTML
[00:03:44] document." And then this is what it gave
[00:03:46] me. It gave me the anatomy of attention.
[00:03:48] You can see we've got like some stars
[00:03:49] moving around in the background. This
[00:03:50] obviously looks a little bit vibe coded
[00:03:52] up here, but not too bad. And as we sort
[00:03:53] of scroll down, we can see a language
[00:03:55] model has no grammar book and no
[00:03:57] dictionary. And then on this thing, the
[00:03:59] animal didn't cross the street because
[00:04:00] it was too tired. This is kind of like
[00:04:02] an interactive element here. We see the
[00:04:04] query word and then we see where it
[00:04:05] points. So tired was pointing to it. It
[00:04:09] was pointing to the animal. Cross was
[00:04:10] pointing to the street. So kind of
[00:04:13] interesting. First the sentence is
[00:04:14] broken. Every token gets a place in
[00:04:16] space. So we've got a little bit of like
[00:04:17] a relationship graph here. We've got
[00:04:19] some charts down here and some different
[00:04:21] elements. So anyways, this is what GLM
[00:04:23] came up with when I said, "Hey, just be
[00:04:24] creative and just give me whatever you
[00:04:26] want. Show me whatever interests you, I
[00:04:29] And then I did the exact same prompt
[00:04:30] into Opus to see what kind of
[00:04:32] differences we would get. And Opus came
[00:04:33] up with the life of a Death Star. Here
[00:04:35] once again, you can see that classic F
[00:04:37] that Opus loves to do. But anyways, this
[00:04:40] one is more of like a timeline where we
[00:04:42] go through the actual kind of like life
[00:04:43] cycle of a Death Star. And we can see
[00:04:46] this one is also pretty good as well.
[00:04:48] But once again, pay attention to the
[00:04:49] fact that from a design perspective with
[00:04:52] one shot, is Opus that much better? Is
[00:04:55] Opus five times better? Because you're
[00:04:56] paying five times more. However, with
[00:04:58] this one, the goal took about 35
[00:05:00] minutes, and for Opus, this goal only
[00:05:01] took about 11. So, it's really a hit or
[00:05:03] miss as far as when is GLM 5.2 actually
[00:05:06] faster. Typically, the more reasoning,
[00:05:08] the slower it's going to be. And so,
[00:05:09] just remember, cloud code is a harness.
[00:05:11] It's a harness for AI models, and
[00:05:12] typically cloud models are going to use
[00:05:14] the harness the best. But, GLM 5.2 does
[00:05:17] pretty decent. It's able to use the SLG
[00:05:18] goal. It's able to read my cloudmd. It's
[00:05:20] able to use my skills. Right here I said
[00:05:22] /goal I need you to use the storm
[00:05:24] research skill which I'll have a video
[00:05:25] coming out about that very soon to
[00:05:27] research open source AI models versus
[00:05:29] closed source and the end deliverable is
[00:05:31] an HTML report. So it goes through it
[00:05:33] does a bunch of sub aents all the sub
[00:05:35] aents were using GLM 5.2 as well and it
[00:05:37] had a bunch of different personas. This
[00:05:39] took about 27 minutes and I got this
[00:05:41] report back. This was our storm research
[00:05:43] and you see it says V2. That just means
[00:05:45] that it had one pass and then it has
[00:05:46] another set of agents come and read that
[00:05:49] and then it makes some changes. So
[00:05:51] anyways, this is the HTML report that we
[00:05:53] got. I'm not going to read every single
[00:05:54] word of this, but it is very thorough.
[00:05:56] It's very solid. It looks decent. You
[00:05:58] can see we had five different lenses
[00:06:00] going through this, which you'll
[00:06:01] probably see a little bit sprinkled
[00:06:02] throughout. We have a 60-second summary.
[00:06:04] We have five key findings. This one was
[00:06:06] supported by the academic and the
[00:06:08] skeptic. This one was supported by the
[00:06:10] practitioner, economist, and the
[00:06:12] academic. And it was challenged by the
[00:06:13] skeptic and the historian. So basically
[00:06:15] we're just leveraging like you know a
[00:06:17] mixture of experts here or a mixture of
[00:06:19] different you know styles of agents to
[00:06:22] help us do the research and help us
[00:06:23] debate over how this thing is actually
[00:06:26] constructed. We have the hidden
[00:06:27] connection. We have the assumption that
[00:06:29] the briefing rests on what to actually
[00:06:31] do different. So if you guys want to
[00:06:33] pause this and actually read through it.
[00:06:34] It has some really good information in
[00:06:35] here. But anyways this is what it came
[00:06:37] up with. This made me start to wonder
[00:06:39] like okay where would I actually use GLM
[00:06:41] 5.2 over something like Opus 4.8 because
[00:06:43] I do think that after I did a ton of
[00:06:45] knowledge work with this today and
[00:06:46] testing, it's pretty solid. And so I
[00:06:48] think for something like this, I would
[00:06:49] 100% be comfortable with GLM 5.2 doing
[00:06:52] this because I felt comfortable with the
[00:06:54] way that I orchestrated that storm
[00:06:56] skill. Bunch of different agents, bunch
[00:06:57] of different verification checks. And
[00:06:59] that is way more important ultimately
[00:07:01] than the model, than the underlying
[00:07:02] model. It's all about the way that you
[00:07:04] prompt them, the way that you use them,
[00:07:05] the way that you have your skills and
[00:07:06] your harness and your context layer. So
[00:07:08] I would trust GLM 5.2 here big time to
[00:07:10] do me a bunch of research. And by
[00:07:12] research, I mean like gathering a bunch
[00:07:14] of opinions and gathering data and
[00:07:16] pulling in sources. But I probably would
[00:07:18] want Opus to actually help me think
[00:07:20] through based on all this data what
[00:07:22] really matters and how do I apply it to
[00:07:24] my life. That's where I'd probably lean
[00:07:26] on a heavier reasoning model, a stronger
[00:07:28] model like Opus. So I feel like everyone
[00:07:29] needs to be thinking about that kind of
[00:07:31] stuff. It's not binary. It's where in
[00:07:33] each process, what steps should I use
[00:07:35] what model for? Anyways, why am I
[00:07:36] talking about GLM 5.2? Because it is an
[00:07:39] open- source model, right? So like
[00:07:41] chatbt or claude but those are those are
[00:07:42] closed source models meaning you rent it
[00:07:45] you pay directly to the provider in
[00:07:47] order to access it. Now yes you guys saw
[00:07:49] earlier I am paying a subscription to
[00:07:51] access GLM 5.2 and that is just because
[00:07:54] it is so massive. It is a massive model
[00:07:56] 753 billion parameters which is very big
[00:07:59] which means that I couldn't actually run
[00:08:00] that on my machine. Yes it is open
[00:08:02] source. Yes you could run it locally but
[00:08:04] you would need the hardware you would
[00:08:06] need the infrastructure to support that.
[00:08:07] Most of us don't have that just lying
[00:08:09] around. So what we can do is we can rent
[00:08:10] it online. So kind of very similar the
[00:08:12] way that you pay Anthropic for Claude,
[00:08:14] but it's so much cheaper than Claude. So
[00:08:16] everyone is freaking out because it's
[00:08:18] basically yours. You're able to download
[00:08:19] it or get it for much cheaper. It's very
[00:08:21] smart. I'll show you guys some
[00:08:22] benchmarks in a sec. And it is very
[00:08:24] cheap. If you did a heavy day of coding,
[00:08:26] it'd be about five times cheaper than
[00:08:27] Opus 4.8 for the same job. You can see
[00:08:29] here, here is the input and output
[00:08:31] tokens. Opus 4.8 is $5 on the input, $25
[00:08:34] on the output, whereas GM 5.2 is $1.40
[00:08:37] 40 cents on the input and $4.40 on the
[00:08:40] output. So this is where I got the
[00:08:41] numbers where I said it's about five
[00:08:42] times cheaper. So if you go to something
[00:08:44] like Olama, which is somewhere where you
[00:08:45] can actually download and pull in local
[00:08:47] models, you can see here that we have GM
[00:08:49] 5.2. It's got the 1 million context
[00:08:51] window and the size is 756 billion
[00:08:54] parameters in this case. Now they don't
[00:08:55] actually let you pull this in. They let
[00:08:57] you run it from their cloud, which is
[00:08:58] nice because it is such a big model. But
[00:09:00] take a look at some of these benchmarks
[00:09:02] compared to Cloud Opus 4.8 8 and GBD 5.5
[00:09:06] which are like the two best models right
[00:09:07] now. Look where GLM 5.2 is stacking up.
[00:09:11] It is really comparable to all of these
[00:09:14] other top tier close source models which
[00:09:16] is why obviously a lot of people are
[00:09:17] freaking out about it right now and
[00:09:18] looking at it. Think about the fact that
[00:09:19] Fable got pulled away from us, right?
[00:09:21] That just tells you that we are renting
[00:09:23] something that could be taken away from
[00:09:25] us for, you know, out of nowhere. And
[00:09:27] what I'm worried about is Enthropic and
[00:09:29] Openi aren't profitable companies right
[00:09:31] now. We're paying $200 a month for a
[00:09:33] clawed max plan, but we're getting like
[00:09:35] $8,000 worth of inference out of that if
[00:09:37] we actually utilize it all the way. So,
[00:09:39] they are not profitable. So, what
[00:09:40] happens when we finally maybe we get
[00:09:42] Fable back, they're obviously not
[00:09:44] profitable on that either. So, what they
[00:09:45] might do is bring it back and say, "Hey,
[00:09:46] but you can't use this in your
[00:09:47] subscription. You can only use this via
[00:09:49] API billing." That's more expensive than
[00:09:51] Opus. So, if you can start to understand
[00:09:53] these open source models and you can
[00:09:54] start to deploy them locally for
[00:09:55] basically like completely free, then it
[00:09:57] is really going to help you stay ahead
[00:09:59] of the game here. Take a look at this
[00:10:01] bench, Frontier S. SWE. It performed
[00:10:03] better than GPT 5.5 in this benchmark,
[00:10:06] which is just absolutely crazy. If you
[00:10:08] guys liked Opus 4.7, which a lot of you
[00:10:10] guys did, some of you guys didn't. GLM
[00:10:11] 5.2 was beating that model in a lot of
[00:10:13] these evaluations. And it beats the most
[00:10:15] recent Sonnet model in a ton of these
[00:10:17] evaluations as well. So, just think
[00:10:18] about it like that. Think about truly
[00:10:20] how decent this model really is. Here's
[00:10:21] some more benchmarks. Aenta coding. I'm
[00:10:23] not going to go through all these
[00:10:24] because I, you know, we all know that
[00:10:26] you should always take these with a
[00:10:27] grain of salt. It's more about the feel
[00:10:28] and how you actually use them, but they
[00:10:30] are interesting to look at every once in
[00:10:32] a while. So, anyways, let's talk about
[00:10:33] how you get set up. What you do is
[00:10:35] you're going to go to z.ai and you might
[00:10:37] pull into something that looks like
[00:10:38] this. You can go ahead and chat. You can
[00:10:40] make landing pages right here. You can
[00:10:41] do 3D modeling. You can build your own
[00:10:43] mini game. And it's really good at this
[00:10:45] stuff. It's really impressive on the
[00:10:46] front-end design stuff. So, come in
[00:10:48] here, play around with it if you want to
[00:10:49] just test it out and see how it feels.
[00:10:51] But then if you want to plug it into
[00:10:52] Cloud Code or Open Code or Hermes Agent
[00:10:54] or wherever you want to plug it in,
[00:10:56] you're going to click on this button up
[00:10:57] in the top right and that's going to
[00:10:58] take you to the actual API console. And
[00:11:00] so you've got the option to just pay per
[00:11:02] token which obviously is not too
[00:11:04] expensive. If you come here and I go to
[00:11:05] my billing and I go to the model
[00:11:06] pricing, you can see on the input it's
[00:11:08] $1.4 and on the output it is where'd it
[00:11:11] go? $4.4. But you could also just get a
[00:11:14] plan. So you could go on 16 bucks a
[00:11:16] month, 64 bucks a month or 144 bucks a
[00:11:18] month. And if you go yearly, you can
[00:11:19] save even more money. Obviously, they're
[00:11:21] not a sponsor. I'm not working with
[00:11:22] them, but you can also get on a plan.
[00:11:24] So, maybe you can be on a Claude plan
[00:11:26] for maybe 100 bucks a month, and then
[00:11:27] you can be on a Z plan for 64 bucks a
[00:11:30] month. And then just switch between
[00:11:32] them. Whenever you need a certain type
[00:11:33] of task, then you can bounce back and
[00:11:35] forth. And that way, you're getting way
[00:11:36] more out of your subscriptions. Once you
[00:11:38] get a plan, what you would do is you
[00:11:40] would go to API key and you would go
[00:11:41] ahead and grab one. So, you would add an
[00:11:43] API key here. And then you're going to
[00:11:45] be able to start just using that inside
[00:11:47] of Cloud Code. and then you'll be able
[00:11:48] to watch your usage limit here. Now, the
[00:11:50] five- hour quota and the weekly quota
[00:11:51] work very similar to claude code
[00:11:53] subscription. They also have peak hours
[00:11:55] where it consumes, you know, a higher
[00:11:57] multiple of your quota. And then what's
[00:11:59] interesting is they have like web search
[00:12:00] quota as well. So, if you were doing a
[00:12:03] lot of web searching, um it will eat
[00:12:04] this up, but you could obviously connect
[00:12:05] it to maybe like perplexity or a
[00:12:07] different API to do more web searching.
[00:12:08] So, it's not a huge deal, but I did
[00:12:10] think that that was kind of interesting.
[00:12:11] So anyways, all you're going to do is
[00:12:13] you are just going to edit your config
[00:12:15] file within cloud code, which sounds a
[00:12:17] little bit scary or technical, but it's
[00:12:18] really not. Let me just pull up my cloud
[00:12:20] real quick and show you what that looks
[00:12:22] like. So inside of yourcloud, you should
[00:12:24] have a settings.local.json.
[00:12:26] And this is where you can play with your
[00:12:27] permissions and your MCP servers and all
[00:12:29] that kind of stuff. And you can also set
[00:12:30] environment variables. So if you guys
[00:12:32] have activated agent teams, this might
[00:12:34] live here like mine or it might live
[00:12:36] globally. Wherever it lives, that's an
[00:12:37] environment variable. And all you need
[00:12:38] to do is you need to come in here and
[00:12:40] you need to set these. So what I'm going
[00:12:42] to do is I'm going to have this exact
[00:12:44] thing, paste it in the description of
[00:12:46] this video. So all you have to do is
[00:12:47] copy this, put it into your environment
[00:12:49] variables. You can also say, hey, cloud
[00:12:50] code, put this into my
[00:12:51] settings.local.json, and then all you
[00:12:53] have to do is switch out your own API
[00:12:55] key. So this is where you will put your
[00:12:58] Z API key that you just got in here when
[00:13:00] you go to API keys, and you added one
[00:13:02] right there. Because what you're doing
[00:13:04] here is you can see we have enthropic
[00:13:06] base URL and we are routing that to Z's
[00:13:09] API rather than to an anthropic API. So
[00:13:11] we're just switching out the engine of
[00:13:12] the car. If the harness is the car and
[00:13:14] the engine's AI model, we're just
[00:13:16] switching out the engine. And you can
[00:13:18] see right here I have left the enthropic
[00:13:20] API key blank. We put this in as the
[00:13:22] enthropic o token and that is my Z API
[00:13:25] key. And then we changed all of these
[00:13:26] default models to GLM 5.2. And then when
[00:13:29] you open up your new claude, if I go in
[00:13:31] here, claude, we open that up and what
[00:13:33] do we see right here? We see GLM 5.2
[00:13:36] with 1 million context API usage
[00:13:39] billing. And so that is just like on a
[00:13:40] per project setting. So if I come into
[00:13:44] this other one and I show you guys like
[00:13:46] you know on this lefth hand side we have
[00:13:48] GLM. On this right hand side we have um
[00:13:51] opus. The way I did that is I just have
[00:13:52] these in two different directories. And
[00:13:54] this is a very ugly view. I'm sorry
[00:13:55] about that. But what I did is in here I
[00:13:58] have two folders. I have GLM and I have
[00:14:00] opus. So in the GLM folder, my
[00:14:02] settings.local.json
[00:14:04] shows this stuff, right? And then in my
[00:14:06] opus folder, I don't even have a
[00:14:08] settings.local.json. And that's how I'm
[00:14:10] able to open up claude in this
[00:14:12] directory. And we just have the regular
[00:14:15] Claude. And this looks absolutely awful.
[00:14:16] So let me just show you. There we go.
[00:14:18] Because we are not in a directory that
[00:14:20] has a settings.local.json JSON with this
[00:14:22] routing. It just pulls up automatically
[00:14:24] with Opus on my Cloud Max plan. So
[00:14:26] that's how you can sort of, you know,
[00:14:28] tweak which projects are using which AI
[00:14:30] model. And also, if you guys were
[00:14:31] wondering, this entire slide deck, of
[00:14:34] course, was built by GLM 5.2. It's funny
[00:14:37] cuz it keeps referring to me as Herk,
[00:14:39] and I think by this it just means Herk
[00:14:41] 2, like my project called Herk 2. But
[00:14:43] this was made by GLM 5.2. And you'll
[00:14:45] notice it looks like a lot of my other
[00:14:46] slide decks because it used my skill for
[00:14:48] that. Anyways, I know this one was a
[00:14:50] quick one, but I wanted to make it quick
[00:14:51] and show you guys how to get set up so
[00:14:52] you can play with it. I am planning on
[00:14:53] bringing you guys a ton more content on
[00:14:56] local models and maybe even some other
[00:14:58] stuff like open code because you don't
[00:15:00] always want to be locked into maybe
[00:15:01] cloud code's hardest. So, please let me
[00:15:03] know in the comments what you want to
[00:15:04] see around open-source AI because trust
[00:15:07] me, I can definitely see a future where
[00:15:09] every company is just running their own
[00:15:11] local models. And I think Enthropic is
[00:15:12] starting to realize that too. OpenAI is
[00:15:14] starting to realize that too. That's why
[00:15:15] they're investing into other things like
[00:15:18] services and other ways that they can
[00:15:20] integrate into companies like their
[00:15:22] forward deployed engineers because they
[00:15:24] know that the model might not be the
[00:15:26] moat at the end of the day. Right now
[00:15:27] there's a huge gap, but we see this gap
[00:15:30] closing super quickly and it's really
[00:15:31] fun to watch in real time. So, let's
[00:15:33] start playing around more with open
[00:15:34] source models. If you guys enjoyed the
[00:15:36] video or you learned something new,
[00:15:36] please give a like. Helps me out a ton.
[00:15:38] And as always, I appreciate you guys
[00:15:39] making it to the end of the video and
[00:15:40] I'll see you all in the next one. Thanks
[00:15:42] everyone.
