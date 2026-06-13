---
video_id: v6MWNrVbM4E
title: "Full Episode: The AI Industrial Revolution"
channel: Naval and Nivi
url: "https://www.youtube.com/watch?v=v6MWNrVbM4E"
watched_date: 2026-06-08
watched_at: "2026-06-08T12:00:00Z"
watch_count: 1
duration_seconds: 4202
source: youtube-history-browser
added_date: 
history_label: Monday
history_order: 79
watched_at_precision: date-from-history-label
watched_percent: 52
estimated_watched_seconds: 2185
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode features Naval and three frontier founders—Gumo (Vercel), Blake (Boom Supersonic), and Max (Science)—discussing how AI is reshaping engineering work. The core insight is that software engineers are no longer measured by output (lines of code, tokens) but by their ability to build "factories" that generate multiplicative leverage. AI models like Claude and ChatGPT amplify existing skill—expert developers see 100-1000x gains, while juniors get smaller returns—making the quality of feedback and judgment the critical differentiator. As AI handles routine tasks, junior engineers are effectively promoted to senior roles; architectural decisions, taste, and system understanding now matter far more than writing code by hand. The discussion reveals that pure software is losing its moat; instead, value concentrates in infrastructure building blocks for agents and in hardware companies that integrate AI-driven software workflows into manufacturing (replacing broken Excel-based engineering).

**Actionable takeaway:** Stop optimizing for token costs or perfect prompts—waste tokens to save your time, since AI is cheaper than humans anyway. Focus on developing judgment about system architecture, APIs, and trade-offs rather than syntax; direct AI models with clear constraints (e.g., "use Postgres, not ClickHouse") and expect repeated feedback cycles to refine output. For hardware/manufacturing teams, invest heavily in software infrastructure and frameworks that automate engineering workflows; this is where leverage concentulates. Use the smartest available models for coding tasks, not the cheapest, since intelligence compounds with your decisions. Delegate routine/junior work to AI agents so your team can focus on architectural and strategic choices where human judgment creates moat.

## Transcript

[00:00:00] Welcome. You're listening to the Naval
[00:00:02] podcast, your authoritative source for
[00:00:04] new knowledge. We're trying something
[00:00:06] new today. Uh I have three frontier
[00:00:09] founders with us. Three good-looking
[00:00:11] guys actually, and a fourth good-looking
[00:00:13] guy, Naval. And let me just introduce
[00:00:15] everybody. Gumo the G Roush. Um he's
[00:00:19] building Versel into an AI cloud for the
[00:00:22] world of agents and whatever comes after
[00:00:24] that.
[00:00:25] >> Good to be here. Blake Shawl, he's
[00:00:27] building supersonic aircraft in his own
[00:00:29] factory and jet engines as well. Blake's
[00:00:32] company, Boom Supersonic. And then Max
[00:00:35] Hodak from science. He's building a
[00:00:37] biohybrid brain interface that grows
[00:00:39] living neurons on silicon to restore
[00:00:43] sensory functions like sight, but then
[00:00:45] eventually to explore new parts of the
[00:00:47] brain and new senses. All three of these
[00:00:50] guys are not composing their products
[00:00:52] with off-the-shelf parts. They're
[00:00:54] building their own factories and you
[00:00:56] know we don't care as much about what
[00:00:57] they're building exactly as we do about
[00:01:00] what they're learning about how they're
[00:01:02] building. What's the new knowledge
[00:01:03] they're generating? What's their alpha?
[00:01:06] What principles are they discovering
[00:01:08] that other founders can learn from? What
[00:01:10] are they trying to figure out right now?
[00:01:12] And also what are the cutting edge or
[00:01:14] crazy ideas that they haven't even
[00:01:16] talked about yet and they're still
[00:01:17] forming in their brains. Naval, do you
[00:01:20] have any reactions to any of that before
[00:01:21] I jump into Gummo? Yeah, let's just have
[00:01:24] fun.
[00:01:25] >> Yeah, you guys should just jump in.
[00:01:27] >> Yeah. So, I can't remember my exact
[00:01:29] quote, by the way, but I've been really
[00:01:31] pilled uh with this idea of software
[00:01:34] factories and the job of the engineer
[00:01:37] being something that you just show up to
[00:01:39] work. You used to used to ship the
[00:01:42] output directly and everything inside
[00:01:44] the company was, you know, how good is
[00:01:46] person A at shipping output B. And now
[00:01:49] what's happening is the way that I'm
[00:01:50] judging you as an engineer is like are
[00:01:52] you producing the factory that would
[00:01:54] produce multiplicative outputs B through
[00:01:57] Z, right? Um and that's a that's a
[00:02:00] pretty significant change because
[00:02:01] basically like we used to believe and it
[00:02:03] should be somewhat controversial that
[00:02:04] there's 10x engineers like now clearly
[00:02:07] there's 100x or a thousandx engineers
[00:02:10] and the world hasn't fully adjusted to
[00:02:11] this. I used to get flamed on Twitter
[00:02:13] for saying they're 10x engineers that it
[00:02:15] flies in the face of so much like
[00:02:17] equality philosophy that everyone's
[00:02:19] equal. But the reality is when you're
[00:02:21] operating in idea domains, when you're
[00:02:22] operating intellectual domains and
[00:02:24] virtual digital domains, it's not even
[00:02:25] 10x, it's 100x or thousandx and it
[00:02:27] always has been. Satoshi Notch, you
[00:02:30] know, the guy who invented JavaScript,
[00:02:32] the Brendan I of the world, uh John
[00:02:34] Carmarmac, I mean these are thousandx
[00:02:36] programmers. Not to even mention if you
[00:02:38] choose the right thing to work on versus
[00:02:39] the wrong thing to work on, that's an
[00:02:41] infinity difference and it could just be
[00:02:43] not nemer, just one who had a better
[00:02:45] judgment on what to work on in the first
[00:02:47] place. And now obviously it's less
[00:02:49] controversial because of uh AI leverage.
[00:02:52] What's controversial is that the token
[00:02:54] leaderboards, right? Like people are
[00:02:56] still getting a little confused because
[00:02:57] now they think, well, I have a bunch of
[00:02:59] 100x engineers. Look at all these tokens
[00:03:01] that I'm paying for. I'm curious if you
[00:03:04] guys have seen the same like how do you
[00:03:06] measure ROI?
[00:03:07] >> It's like the old measuring lines of
[00:03:09] code, you know, token consumption with
[00:03:11] lines of code feel like similarly not
[00:03:14] direct paradigms.
[00:03:15] >> I mean, my observation has been that
[00:03:17] claude or cha GPT um or GPT is about is
[00:03:21] basically as good as you are in a
[00:03:23] domain. And so, uh if you're if you're a
[00:03:27] really capable developer, then these
[00:03:28] things are really powerful. And if
[00:03:29] you're a junior developer, then you'll
[00:03:31] kind of find it to be like more of a
[00:03:32] junior developer. Like on the one hand,
[00:03:34] these models are incredibly capable. On
[00:03:35] the other hand, the feedback that you
[00:03:37] give them sporadically seems to be
[00:03:39] incredibly important. And these little
[00:03:41] updates seem to totally determine the
[00:03:43] types of uh performance you get out of
[00:03:45] them.
[00:03:45] >> There's a new kind of support that I
[00:03:47] give which is you come to me and like
[00:03:49] you didn't get good output out of the
[00:03:51] model and I tell you what to prompt the
[00:03:54] model with. So like the idea of like the
[00:03:56] quality of the reprompting which I think
[00:03:58] you're alluding to is is extremely
[00:03:59] important.
[00:04:00] >> But I mean and to be clear I think that
[00:04:01] this will become less important over
[00:04:02] time like as the models get much much
[00:04:04] smarter then you'll be able to put in
[00:04:06] less and get more out. Um but at least
[00:04:08] at this stage it really seems to kind of
[00:04:10] reflect back the judgment that the user
[00:04:13] brings in. In my experience,
[00:04:14] >> I've kind of resisted learning all the
[00:04:17] ticks and tricks and tips like, you
[00:04:19] know, there was a, oh, use Ralph Wigum,
[00:04:22] use Open Claw, use Hermes, use this
[00:04:24] prompt engine, use this scaffolding,
[00:04:26] plug in this piece, you know, uh, always
[00:04:29] use plan mode. I just ignored all of
[00:04:30] that. I just assumed the model's just
[00:04:32] going to get better faster than I would
[00:04:33] figure out how to use it. It would
[00:04:34] figure out how to use me faster than I
[00:04:36] would figure out how to use it. And so
[00:04:38] I've just been completely hamfisted with
[00:04:40] them and I get frustrated at them and
[00:04:42] just sort of I I found myself typing
[00:04:44] less and less information and doing less
[00:04:46] and less work as time goes on with the
[00:04:48] models because I just assume I can brute
[00:04:50] force my way through it and I'll throw
[00:04:52] Codex Claw and Gemini at the same
[00:04:54] problem over and over and just waste
[00:04:56] tokens to save time. And I think no
[00:04:58] matter how expensive these models might
[00:05:00] seem, they're still way cheaper than a
[00:05:01] human. So I would say just waste tokens,
[00:05:04] save time. Don't look at the tokens
[00:05:06] either as inputs or outputs. Just look
[00:05:08] at your time and look at the final
[00:05:10] output. And even if they're writing
[00:05:12] lowquality code, which I know in many
[00:05:14] cases they are, it's not necessarily
[00:05:15] production quality or scalable code.
[00:05:17] When the time comes and I want to ship
[00:05:19] it to production, I'll just throw more
[00:05:20] tokens at it. I'll say, "Okay, now go
[00:05:22] through look at it, rewrite it, and
[00:05:23] they're just going to get better every
[00:05:25] generation." Uh, so yeah, I don't I
[00:05:27] don't see where this necessarily stops.
[00:05:29] As long as we have verifiable domains
[00:05:31] and solve problems, they're going to
[00:05:33] resolve those problems. That's in the
[00:05:34] unsolved problems domain where maybe
[00:05:36] you're terren tower you're at the
[00:05:38] cutting edge of creativity that you need
[00:05:40] to be you know working very
[00:05:42] collaboratively and carefully and
[00:05:43] closely with the model but I'm not in
[00:05:45] that I'm not at that level in software
[00:05:47] engineering and gear but you're probably
[00:05:48] the most extreme software engineer in
[00:05:49] the team right like out of this set
[00:05:51] you're probably the one who most
[00:05:53] hardcore came up from a software
[00:05:55] background like how are you finding
[00:05:57] these models at the edge of their
[00:05:58] capability? Well, there's one thing
[00:06:01] that's happened recently that uh what
[00:06:04] you're saying resonates strongly with,
[00:06:06] which is it used to be that you would
[00:06:09] give a prompt to the model and it kind
[00:06:12] of does it like classic like next token
[00:06:14] prediction thing and it like runs away
[00:06:16] with your idea. And models now have been
[00:06:19] doing this like intuitive planning mode
[00:06:21] without to your point not even having to
[00:06:23] plan where it comes back to you and says
[00:06:25] look what you're asking me for there's
[00:06:28] these three routes we can take. there's
[00:06:30] this set of tradeoffs that we're going
[00:06:31] to go down. That's a moment where like
[00:06:33] you know people do the whole thing on X
[00:06:35] like oh now we have a PhD level engineer
[00:06:37] model like that's very clear that the
[00:06:40] models at some point graduated. They
[00:06:41] used to be junior engineers now they're
[00:06:43] principal engineers because they come
[00:06:45] back to you with a set of tradeoffs and
[00:06:48] obviously sometimes they [ __ ] which
[00:06:49] is hilarious. It tells you this one is
[00:06:52] going to take three weeks and this many
[00:06:55] interest it make really bad predictions
[00:06:56] but clearly it's now this like I respect
[00:07:00] the models a lot more as a as a peer
[00:07:02] like that I'm going back and forth
[00:07:04] intellectually with but there there are
[00:07:06] a lot of gaps still so like if you're
[00:07:08] really really proficient engineer or
[00:07:11] architect you I think you're still
[00:07:13] extracting more juice so the question
[00:07:16] sort of that Max was positing of like if
[00:07:18] you're junior do you get junior back.
[00:07:21] Well, clearly not because a junior gets
[00:07:23] more advanced knowledge in code that
[00:07:25] they would have never been able to write
[00:07:27] by themselves, but doesn't an
[00:07:29] experienced architect get 10x whereas a
[00:07:31] junior engineer gets 2x. That's what I'm
[00:07:34] kind of trying to figure out still.
[00:07:35] >> Yeah. Yeah. But I mean, I think there's
[00:07:36] there's architectural decisions. So,
[00:07:38] when you think about the development,
[00:07:39] I'm seeing this now with some of our the
[00:07:40] junior software engineers on the team of
[00:07:41] like what is the next step in their
[00:07:43] career progression. It's going from like
[00:07:45] writing implementation for a feature to
[00:07:47] picking technologies like choosing
[00:07:49] between Postgress versus some other
[00:07:51] database or picking between ZMQ versus
[00:07:54] some other message Q or like some other
[00:07:56] queuing system and those I mean the
[00:07:58] models can suggest them but that's the
[00:08:00] thing where you'll see it and you'll be
[00:08:01] like no no I want to use this other
[00:08:02] thing. That's the type of little
[00:08:03] feedback that I'm saying really matters
[00:08:05] in the types of output that you seem to
[00:08:06] get at this point.
[00:08:07] >> Taste taste and judgment right? Taste
[00:08:09] and judgment. That said you can ask them
[00:08:11] which one should I use and why and they
[00:08:13] know everything. they'll give you really
[00:08:14] good trade-offs. That's the change I was
[00:08:16] saying has happened recently where you
[00:08:18] would say hey go and um put this super
[00:08:21] high cardality telemetry data into
[00:08:23] Postgress and it's like no bro like we
[00:08:25] don't put that kind of data into
[00:08:26] Postgress like you should consider click
[00:08:28] house or Athena or whatever like that's
[00:08:31] happened to me a lot which is really
[00:08:33] impressive um but I the thing I'm still
[00:08:36] like kind of struggling with is clearly
[00:08:40] the human is still completing the model
[00:08:43] like at one point is it the other way
[00:08:45] about like the the human is the one sort
[00:08:48] of getting the instructions back on like
[00:08:50] go get me this API key because it's
[00:08:52] something that only you can do uh or get
[00:08:55] me this amount of capital for my next
[00:08:57] set of investments that I need to make.
[00:09:00] Uh you just watch like that clearly
[00:09:02] we're still not there yet. That's a
[00:09:03] temporary aberration. Pretty soon every
[00:09:05] good SAS company or hosting provider
[00:09:08] will have a CLI and API interface that
[00:09:11] the models can meet directly. they don't
[00:09:13] even necessarily need an API like as
[00:09:14] long as it's like textbased Unix based
[00:09:17] the agent can hack its own API
[00:09:20] >> and then the money part you insert
[00:09:21] crypto tokens you know put in bitcoin
[00:09:23] put in whatever and the model goes and
[00:09:25] just pays for whatever it needs and I
[00:09:26] think like
[00:09:27] >> you know there people working on this
[00:09:29] >> but the thing I am now thinking through
[00:09:32] is is pure software dead like is pure
[00:09:35] software engineering like an obsolete
[00:09:37] thing it's like saying speaking English
[00:09:39] right the models now speak English we
[00:09:41] had to learn code to communicate with
[00:09:43] the models. Now the models speak English
[00:09:45] and they speak fuzzy sloppy English like
[00:09:48] a human and they understand things. So
[00:09:50] where's the moat like for a founder?
[00:09:52] Hardware it's a boon you know like now
[00:09:55] if you had to build hardware it was hard
[00:09:56] to build a software company alongside
[00:09:58] like Patrick Cullison says software is
[00:09:59] art and it's hard to hire artists. So
[00:10:01] now as a hardware founder great you can
[00:10:03] have really good software develop fairly
[00:10:05] quickly. Um, if you're creating models,
[00:10:08] maybe that's the new software
[00:10:09] engineering, training models and
[00:10:11] tweaking models and post- trainining and
[00:10:12] fine-tuning models. But classic software
[00:10:15] engineering is that dead is pure
[00:10:17] software investable is pure software
[00:10:19] something organize a company, a team
[00:10:21] around and try to get some leverage. Did
[00:10:23] you guys see the uh there was an article
[00:10:26] an X by Mitchell Hashimoto called the
[00:10:29] block economy or the building block
[00:10:31] economy something like that like his
[00:10:33] argument is that the most useful thing
[00:10:35] for agents to have now is really
[00:10:37] powerful reusable building blocks
[00:10:39] because to Max's example you wouldn't
[00:10:41] expect your clanker to reinvent a Q
[00:10:44] infrastructure system every time he
[00:10:46] needs to send an email it needs to bring
[00:10:49] in the right building block that's right
[00:10:52] size for the task that you're asking for
[00:10:54] and say, "Well, okay, for this one, it's
[00:10:55] B MQ." I challenge the notion that I
[00:10:58] would want the agent to reinvent the
[00:11:01] entire universe from first principles in
[00:11:03] a way that's incompatible with the rest
[00:11:04] of society and civilization. Like it's
[00:11:06] almost like reinventing highways, laws,
[00:11:08] policies, etc. just for you. Even if
[00:11:11] there's a potential for extra
[00:11:13] optimization, extra juice that you can
[00:11:15] get out of it, there's a still a um sort
[00:11:19] of like cooperation at large scale value
[00:11:21] of saying we're both depending on
[00:11:23] Postgress 13.2 and so that's still
[00:11:26] really really really valuable. I would
[00:11:27] say like the category of infrastructure
[00:11:30] software and building blocks that these
[00:11:32] agents are going to use obviously embias
[00:11:34] is this what we're building seems
[00:11:35] extremely valuable and I don't see the
[00:11:37] agent anytime soon and by the way you
[00:11:40] could even another metaphor I've been
[00:11:41] using is like agent's already been
[00:11:43] created that the models can reuse is
[00:11:44] like a token cache because you you don't
[00:11:46] want to churn through a trillion tokens
[00:11:49] to reproduce what's already existing. Uh
[00:11:51] and so there's always starting points
[00:11:53] that the model can fork off from, but
[00:11:55] it's going to change things quite
[00:11:56] profoundly.
[00:11:57] >> So these are like libraries and
[00:11:58] dependencies, but for models.
[00:12:00] >> Yes. For agents specifically.
[00:12:03] >> To Naval's question though, I mean I
[00:12:06] learned a program when I was really
[00:12:07] little. And I like that was the thing
[00:12:09] that through all of like being a
[00:12:11] teenager and in my 20s like I get like
[00:12:13] sucked into it and just like code for
[00:12:15] like 20 hours and it was super fun and I
[00:12:17] knew all this stuff about programming
[00:12:18] languages. I haven't written a single
[00:12:20] line of code in quite a while now. And I
[00:12:23] mean, partly that's because my job is
[00:12:24] different, but also since December, I've
[00:12:26] built a huge amount of software that I
[00:12:27] now use every day. There's all these
[00:12:29] projects that I've kind of fantasized
[00:12:31] about for years that now I'm like using
[00:12:33] um that I've actually built and I didn't
[00:12:34] write any of that. And I just can't
[00:12:36] imagine going back to like actually
[00:12:38] writing code by hand anytime. Like I
[00:12:40] mean, I'm unlikely to do that anyway,
[00:12:41] but just like in general, I see that I
[00:12:43] have a hard time seeing that as part of
[00:12:44] the future.
[00:12:46] >> Yeah. There's something really cool is
[00:12:48] that you understand how the pieces click
[00:12:50] together. Like I feel like anyone that
[00:12:52] understands what an API is and how data
[00:12:55] flows, inputs and outputs, performance
[00:12:59] because you kind of you have to orient
[00:13:01] the model around like this is a certain
[00:13:02] level of expectation that I have out of
[00:13:04] this operation like that's that's always
[00:13:07] been infinitely more useful than um than
[00:13:10] writing code. Like I feel like a really
[00:13:12] good
[00:13:14] a proficient engineering leader has been
[00:13:16] quote unquote like vibe coding through
[00:13:19] people on Slack or one-on- ones because
[00:13:21] you're transmitting your will, your
[00:13:23] intent, your experience and you're
[00:13:25] letting others run with it. Uh it's just
[00:13:27] that now we do the same but with agents.
[00:13:30] Uh and so I think that's why you've been
[00:13:32] successful with it. But I don't know
[00:13:33] that everyone sees the same level of
[00:13:35] success. I
[00:13:36] >> mean I went from not having written code
[00:13:38] in 20 years to I'm coding all the time
[00:13:40] now. but through agents and I'm building
[00:13:42] tons of software and it turns out that
[00:13:44] just understanding the basic principles
[00:13:46] of software engineering and algorithms
[00:13:48] actually gets you a long ways because
[00:13:49] the reason I stopped coding was because
[00:13:51] I didn't have time to figure out the
[00:13:53] latest language latest architecture
[00:13:55] infrastructure pieces to plug into and I
[00:13:57] know Verscell makes it a lot easier but
[00:13:59] even then just getting started was a
[00:14:00] bare like just plugging pieces together
[00:14:02] assembling infrastructure was just so
[00:14:04] annoying. The thing that really changed
[00:14:07] is I mean it used to be that you could
[00:14:09] build a lot like you like there's a lot
[00:14:10] that was straightforward but then you
[00:14:12] would hit some random thing and then you
[00:14:14] could spend
[00:14:15] >> kind of some indefinite period of time
[00:14:17] debugging some narrow thing and now with
[00:14:20] the agents what happens is you just
[00:14:21] don't get stuck anymore which is pretty
[00:14:23] amazing
[00:14:23] >> or they get stuck
[00:14:24] >> it's removed well no I mean like
[00:14:25] relatively quickly they can find like
[00:14:27] the right way to do things and it used
[00:14:29] to be that like I remember when their
[00:14:30] friends learned a program be like nope
[00:14:32] it's just like intrinsically frustrating
[00:14:33] like if like that's part of the feel
[00:14:35] that's how you learn and that just isn't
[00:14:37] true anymore.
[00:14:39] >> Blake, how are you applying all the
[00:14:40] stuff at uh Boom Supersonic?
[00:14:43] >> Yeah. What I found is it completely
[00:14:45] changes the role of software and
[00:14:47] hardware developers. The thing that we
[00:14:49] did from day one was uh try to take a
[00:14:53] lot of traditional engineering workflows
[00:14:55] and I mean hardware engineering
[00:14:56] workflows and turn them into software.
[00:14:58] And so if you haven't been around
[00:15:00] hardware engineering, let me see if I
[00:15:01] can make this more clear. there uh
[00:15:03] there's a lot of engineering hardware
[00:15:05] engineering that happens in Excel
[00:15:06] spreadsheets on engineers laptops in a
[00:15:09] silo and it's very complex uh
[00:15:13] spreadsheets sometimes like VBScript
[00:15:16] code and all of this is actually
[00:15:18] software but it's it's treated as if
[00:15:20] it's not software there's no there's no
[00:15:22] source control there's no automated
[00:15:24] testing if you want to hand something
[00:15:26] off from like an aerodynamicist to a
[00:15:28] structures engineer that's done manually
[00:15:30] with like a spreadsheet over email like
[00:15:32] it's the 1990s. It's terrible. And so we
[00:15:35] we started building these kind of like
[00:15:37] software frameworks that can automate
[00:15:39] and make repeatable hardware engineering
[00:15:41] flows. The idea we could reduce the cost
[00:15:42] of iteration. Um but it was it was
[00:15:45] slowgoing because we could never get
[00:15:46] enough we could never like afford enough
[00:15:48] software engineers. And what we've
[00:15:50] gotten into is this uh mind-blowingly
[00:15:53] different model where the software
[00:15:55] engineers actually create the
[00:15:57] architectures because they understand
[00:15:59] systems, they understand algorithms,
[00:16:01] they they understand, you know, division
[00:16:03] of concerns. Uh and then the hardware
[00:16:05] engineers can vibe code their pieces
[00:16:08] because what they know about hardware
[00:16:09] engineering and the result is just like
[00:16:12] mindblowingly different productivity for
[00:16:14] small teams. like give an example like
[00:16:16] like if you're designing a turbine blade
[00:16:18] like classically so a turbine blade
[00:16:21] starts like uh cold but when it runs
[00:16:24] it's hot so it gets bigger and so you
[00:16:26] have to design both the aerodynamics and
[00:16:28] the structural design of the thing to
[00:16:30] work on it cold shape and this hot shape
[00:16:32] and so you have to convert between cold
[00:16:34] and hot and you convert between
[00:16:35] structures and aerodynamics and this
[00:16:37] takes like one engineer one day for one
[00:16:40] blade for one piece of the analysis and
[00:16:43] there are like a thousand blades in a
[00:16:44] jet
[00:16:45] and and so you can't do much and we
[00:16:48] literally now with a combination of
[00:16:50] software and hardware people created the
[00:16:51] solution you can change blade geometry
[00:16:53] you can see in real time the structures
[00:16:55] and aerodynamics results and so it
[00:16:58] allows two engineers to design an entire
[00:17:00] jet engine which is just wildly
[00:17:02] different. One of the things you
[00:17:04] mentioned is that you have software
[00:17:05] engineers creating the tools and
[00:17:07] architectures for the rest of the
[00:17:09] engineers. That to me is the biggest u
[00:17:12] the cataclysm of enterprise software is
[00:17:14] that there's no like startup that builds
[00:17:17] hardware collaboration tools that can
[00:17:19] sell you anything anymore because in
[00:17:21] internally you're just coding the right
[00:17:23] things that you need at any given time.
[00:17:25] Even spreadsheets are kind of cooked,
[00:17:27] right? Because the reason spreadsheets
[00:17:28] were successful is that no one could
[00:17:30] build custom software. So the thing that
[00:17:32] approximates custom software the most is
[00:17:34] a spreadsheet with a bunch of EV script
[00:17:36] functions. I personally have moved
[00:17:38] almost entirely from uh Excel to Python
[00:17:42] models where I can actually like get
[00:17:44] like believable simulations of things.
[00:17:47] >> Yeah. I mean the thing that that AI
[00:17:49] hasn't come to yet that I think it it
[00:17:51] will within the next year like probably
[00:17:52] within 26 that will be very very
[00:17:54] exciting is right now it can generate
[00:17:55] software but soon it'll be it will
[00:17:57] generate step files and PCB layouts. And
[00:18:00] when it comes for mechanical and
[00:18:01] electrical engineering, that will be a
[00:18:04] whole other thing that we haven't seen
[00:18:06] yet. That'll be very, very cool.
[00:18:07] >> Yeah. On the hardware side, I think it's
[00:18:10] really a boon for like all these little
[00:18:11] gadget companies and part companies that
[00:18:14] write really bad software because they
[00:18:16] can't make great software and now
[00:18:17] they're going to be able to make good
[00:18:19] enough software or it may not even
[00:18:21] software that is a human front end. It
[00:18:22] might just be completely agentic for an
[00:18:24] agent to access and you just talk to it
[00:18:26] through voice and control hardware. And
[00:18:28] I this is why one of the reasons why I
[00:18:31] think for example China is big into
[00:18:33] open- source models right they're
[00:18:36] basically going all in on it because
[00:18:37] they have hardware superiority they have
[00:18:39] these very complex supply chains and
[00:18:41] component chains and they're basically
[00:18:42] saying hey if I can just generate
[00:18:45] software on demand then I don't have
[00:18:47] this disadvantage anymore against
[00:18:48] Silicon Valley. So that's not the only
[00:18:50] reason why they're doing open source. I
[00:18:51] think they're also behind. They're
[00:18:53] distilling models. They're catching, you
[00:18:55] know, they're collaborating on
[00:18:56] resources. But I think the Chinese
[00:18:58] government has a history of funding
[00:19:00] efforts that then sort of help their
[00:19:02] entire ecosystem along, especially in
[00:19:04] network effect businesses.
[00:19:05] >> And so I think they want to like uh pull
[00:19:07] all their resources, catch up on AI, and
[00:19:10] use it to give their hardware stuff an
[00:19:12] advantage. And ironically, they're doing
[00:19:13] all the open source stuff because Open
[00:19:15] AI is not open. You know, Gro publishes
[00:19:17] models, but I think they're a model or
[00:19:19] two behind. Uh, Google has some local
[00:19:21] models, but nothing really that
[00:19:22] competitive. Anthropic, to my knowledge,
[00:19:24] I don't even know of any open source
[00:19:26] models from them. So, all the open
[00:19:28] source heft is coming from China. It
[00:19:30] helps all our hardware founders, but it
[00:19:32] helps their hardware founders and
[00:19:33] factories and so on that much more. But
[00:19:36] all all the crappy little software that
[00:19:39] goes with all the little random
[00:19:40] knickknacks and thingamajigs that you
[00:19:43] buy off of Amazon for to tinker with a
[00:19:45] lazy Saturday afternoon, that software
[00:19:47] is getting a lot better very quickly. I
[00:19:49] think everyone's had the wakeup call
[00:19:51] that without great frontier coding
[00:19:54] models, you don't have self-improvement.
[00:19:56] And so imagine China as a whole not
[00:19:59] having the ability to produce frontier
[00:20:02] everything, right? It's not just
[00:20:04] producing software is in any piece of
[00:20:06] this hardware pipeline like Blake was
[00:20:09] saying like you need to generate
[00:20:10] software. If you fall behind on your
[00:20:12] ability to generate software, you fall
[00:20:13] behind on the ability to generate
[00:20:15] everything. One thing I'm curious about
[00:20:16] from you guys is like cuz everyone loves
[00:20:18] to talk about Chinese models like do you
[00:20:21] use Chinese models? Do you know anybody
[00:20:22] that uses Chinese models? This is an
[00:20:24] argument I had yesterday actually which
[00:20:26] is uh one person at the table dinner was
[00:20:29] claiming that uh you know you'll just
[00:20:32] use deepseek for 97% of things because
[00:20:34] it's so cheap and if you need more
[00:20:36] intelligence you'll just run it over and
[00:20:37] over again the same problem and you'll
[00:20:39] only use the open AI anthropic etc
[00:20:41] models for the most advanced tasks and I
[00:20:44] was kind of like I don't know I think
[00:20:45] intelligence is an unalloed good you
[00:20:47] always want more intelligence and when
[00:20:49] these models make a mistake you don't
[00:20:50] know it
[00:20:51] >> and it's always cheaper than a real
[00:20:53] person and real time. So, you'll just
[00:20:55] use the most intelligent model
[00:20:56] available, which isn't great news
[00:20:58] necessarily because it means that, you
[00:21:00] know, you're going to end up creating a
[00:21:02] monopoly or igopoly kind of situation in
[00:21:04] AI. But, uh, I always want the most
[00:21:07] intelligent programmer. I always want
[00:21:09] the most correct answer. I always want
[00:21:10] the best judgment. And given the amount
[00:21:12] of leverage that I'm going to pour into
[00:21:13] it through capital and code and people
[00:21:16] and, you know, marketing, I want to make
[00:21:18] the right decision every time. And often
[00:21:20] when between two models, let's say like
[00:21:22] I have one model that I know is a little
[00:21:24] smarter than the next one and they both
[00:21:26] give me answers. Often I actually don't
[00:21:27] know which is the correct answer, right?
[00:21:29] So if I know one model's a little
[00:21:30] smarter, I'm going to go with that
[00:21:32] answer and eventually I'm going to stop
[00:21:33] asking the model that I think is less
[00:21:34] intelligent. But I don't know, have you
[00:21:36] guys found a use for the these, you
[00:21:38] know, so-called less intelligent models?
[00:21:40] We see uses so that so we have the AI
[00:21:42] gateways uh data that basically like
[00:21:45] every application agent, etc. goes
[00:21:48] through. And so there's definitely usage
[00:21:49] of open models, but the top is like
[00:21:52] heavily dominated by the frontier
[00:21:54] intelligence. And there's a subcategory
[00:21:57] or there's like a caveat to that, which
[00:21:58] is that frontier intelligence at
[00:22:01] reasonable cost and performance like
[00:22:03] slaps at scale. So like people don't get
[00:22:06] really excited about Gemini, but they
[00:22:08] put out these models that are like super
[00:22:09] smart at the right performance cost
[00:22:13] combination and for a lot of tasks other
[00:22:17] than co coding actually interestingly
[00:22:18] enough. Uh they're the best models.
[00:22:20] They're like the best like industrial
[00:22:22] production models. Uh you can throw them
[00:22:24] at like support tasks or browser
[00:22:27] automation. Like I would always put a
[00:22:28] Gemini model there. Uh and I would look
[00:22:30] to Chinese models for those kinds of
[00:22:32] things. But anytime I'm working to push
[00:22:34] the frontier, you need the best possible
[00:22:37] coding model. And that's basically now
[00:22:39] like two or three models and uh and the
[00:22:42] Chinese are not certainly not in it.
[00:22:44] >> Hey Max, you're pushing pretty hard into
[00:22:46] vertical integration and extreme
[00:22:48] urgency. Do you want to talk about that?
[00:22:50] >> Yeah, I mean for many things we
[00:22:53] um you can't buy it so you got to make
[00:22:56] it somehow. Our preference would always
[00:22:57] be to buy something um like if there's a
[00:22:59] vendor that offers a service at a great
[00:23:01] price like for example like PCBs like we
[00:23:03] don't make PCBs like those are they're
[00:23:04] basically free you can buy them in
[00:23:05] unlimited quantity from Asia but the the
[00:23:08] closer that our products get to being
[00:23:10] like a single block of coalently bonded
[00:23:11] matter the better they'll be lower power
[00:23:14] smaller higher performance last longer
[00:23:16] and um there's just like there like the
[00:23:20] components aren't available and in order
[00:23:22] to do that type of integration be able
[00:23:24] to actually innovate beyond things just
[00:23:26] piecing together things that you can buy
[00:23:27] off the shelf which really is is very
[00:23:29] very limiting. I guess you have to like
[00:23:30] learn it to do it yourself and that
[00:23:32] shows up as vertical integration. So we
[00:23:34] own a captive MEMS foundry on the east
[00:23:36] coast which we bought because there was
[00:23:38] really no other way to do the type of
[00:23:39] packaging and assembly stuff that we
[00:23:40] wanted to do and I think that all of
[00:23:43] this is going to be affected heavily by
[00:23:44] AI over the next few years. It's not
[00:23:46] quite there yet. In fact, ironically,
[00:23:48] one of the biggest impacts that we've
[00:23:49] seen of AI inside the companies in
[00:23:51] regulatory interactions because if we
[00:23:53] can do things like generate
[00:23:55] documentation or if we can ask like we
[00:23:57] want to change, we want to evolve this
[00:23:58] product like there's thousands of ISO
[00:24:00] standards that might apply which ones do
[00:24:02] we have to comply with and like trace
[00:24:03] this through. This used to be like
[00:24:04] you're like you're following a whole
[00:24:07] regulatory quality team for several
[00:24:08] months as they trace this and now the AI
[00:24:10] just kind of knows. Um, but when I think
[00:24:13] about stuff like the the surgical
[00:24:16] program or the MEMS fab, I think
[00:24:20] ultimately the software still needs
[00:24:21] hands. Like it's going to be smarter
[00:24:23] than us, but if it can't make things,
[00:24:25] then like those are real real
[00:24:27] boundaries. And so we've instrumented
[00:24:29] our foundry as well as many other parts
[00:24:31] of the company in in ways where um as
[00:24:33] these models get better uh that should
[00:24:36] show up pretty immediately in in things
[00:24:38] like the the cell engineering that we're
[00:24:40] doing and the material science that
[00:24:41] we're that we're developing.
[00:24:42] >> It sort of makes me realize that like
[00:24:44] it's been a while since I've generated a
[00:24:46] basic legal document using a lawyer,
[00:24:49] right? I stopped asking lawyers for NDAs
[00:24:52] and you know agreement for this and sign
[00:24:54] that and research this and like all the
[00:24:56] basic legal tasks are gone too because
[00:24:59] you know there's the old joke that law
[00:25:01] is like spaghetti code you know they
[00:25:02] have this very complicated code that
[00:25:04] they try to put in English and it
[00:25:06] contradicts this code over here and has
[00:25:08] to fit into that code over here and
[00:25:09] there no real APIs for it. Um but for
[00:25:12] just like junior engineers and junior
[00:25:14] engineering I should say junior
[00:25:15] engineers basically got a promotion to
[00:25:16] senior engineers and junior engineering
[00:25:18] got taken over by agents and so the same
[00:25:21] way I think in a way the downside is you
[00:25:23] can look at law and say you know
[00:25:25] parallegals just got fired or you could
[00:25:27] say parallegals just got promoted to
[00:25:29] senior lawyers and now they can spend
[00:25:31] their time thinking about the law. It's
[00:25:32] actually kind of interesting to think
[00:25:33] about the parallels of how software
[00:25:35] engineering is evolving with lawyers
[00:25:38] because lawyers, you never know what
[00:25:40] they put into these documents exactly.
[00:25:43] You just trust them. Like, hey lawyer,
[00:25:45] can you look at this document? Can you
[00:25:46] tell me if it's legit? Can you do red
[00:25:48] lines? Whatever. Like, at the end of the
[00:25:50] day, you're what you're valuing in the
[00:25:52] relationship with a lawyer is that is
[00:25:54] that they're a trusted authority. They
[00:25:57] went to law school and they're putting
[00:25:58] their reputation on the line. Cool.
[00:26:01] >> I think there's a parallel par parallel
[00:26:02] with like the biggest problem in
[00:26:04] software engineering today is these
[00:26:05] mountains of slob that end up as a PR
[00:26:09] and then people are say like there's all
[00:26:10] these memes on Twitter like way back in
[00:26:12] the day we used to read every line of
[00:26:14] code of a PR. Well, in my world
[00:26:17] infrastructure I want engineers to be
[00:26:19] able to say I understand doesn't
[00:26:21] necessarily mean that you've read every
[00:26:24] line of the of the PR. You need to be
[00:26:26] able to say I am signing off on
[00:26:28] understanding the consequences of this
[00:26:30] PR or I wrote the test harness
[00:26:34] the simulations the proofs the type
[00:26:36] checkers etc to be able to say even
[00:26:39] without reading this I have confidence I
[00:26:41] can sign off on it's going to be safe in
[00:26:43] production and so it's it's kind of
[00:26:45] interesting because there's a world in
[00:26:47] which we embrace that everything is
[00:26:49] going to be spaghetti code and that we
[00:26:51] don't fully understand it but we write
[00:26:53] the basically evaluator that give us
[00:26:56] confidence and then we rely on like
[00:26:58] people uh like the infrastructure
[00:27:00] production engineers to say okay I'm
[00:27:03] fine uh sending this into prod you know
[00:27:06] at the end of the day like someone is
[00:27:07] going to get paged if your systems go
[00:27:10] down and I think another thing that
[00:27:12] people are underestimating is that
[00:27:13] creating software is really easy 0ero to
[00:27:15] one but think about a thousand days from
[00:27:18] now what does what does your software
[00:27:21] look like is it secure is it tested is
[00:27:23] it production grade uh is it performant
[00:27:27] and are you still motivated to invest
[00:27:30] all of those tokens in maintaining it in
[00:27:32] prod
[00:27:33] >> I mean humans are becoming verifiers
[00:27:34] right and and that's kind of how we
[00:27:36] train these models with good
[00:27:37] verification data and now we need human
[00:27:39] verifiers so yeah I think a lot of the a
[00:27:41] lot of the old function of people
[00:27:43] lawyers engineers operations people move
[00:27:46] to verifying the stack and saying yeah
[00:27:48] this is roughly correct and I I'll
[00:27:50] roughly stand behind it and I'll support
[00:27:52] you if it goes wrong
[00:27:53] >> one of the things we see related to the
[00:27:55] regulatory is it massively reduces
[00:27:58] change aversion and improves iteration.
[00:28:01] So to give you an example like let's
[00:28:02] let's say you're going to go certify an
[00:28:03] airplane. One of the zillions of things
[00:28:06] you have to do is prove that it could
[00:28:08] withstand a lightning strike and the the
[00:28:11] regulatory documentation for the test
[00:28:13] plan for such a thing stretches on for
[00:28:16] say 200 pages. And what you would
[00:28:18] classically do is hire a, let's be
[00:28:20] honest, not super bright engineer who's
[00:28:22] willing to be there monkey at keyboard
[00:28:24] writing 200 pages of regulatory
[00:28:26] compliance documentation. And it takes a
[00:28:29] couple months. And and by the way, if
[00:28:30] you change the airplane now, you want to
[00:28:33] cry because there's another like two
[00:28:34] months of rework of this like wrote kind
[00:28:37] of regulatory compliance documentation.
[00:28:39] And what we found is you we can build a
[00:28:42] rag that will enable us to basically
[00:28:44] prompt our way through all of that work
[00:28:46] you know in let's call it minutes. The
[00:28:49] first order effect is oh you save a lot
[00:28:51] of time. The the the second order effect
[00:28:53] is if you change the specification of
[00:28:55] the airplane uh it now takes you know uh
[00:28:58] minutes not months. So you can actually
[00:29:01] be willing to change. And the third
[00:29:02] order effect is you can now you know
[00:29:05] basically get rid of the not very great
[00:29:06] engineers and have a small number of
[00:29:08] really creative ones. They can iterate
[00:29:10] rapidly because the cost of change goes
[00:29:12] down and in a certain sense like the
[00:29:14] entire regulatory burden which really
[00:29:16] hurts the ability to iterate drops away.
[00:29:18] I think that this is a really undersold
[00:29:19] story in AI right now. I think the
[00:29:21] consensus in Silicon Valley is that like
[00:29:23] regulation sucks like any like we want
[00:29:25] to go faster, we want to rec realize
[00:29:26] this amazing future. We want abundance.
[00:29:28] We want just like prosperity and stuff
[00:29:30] that slows down that future is just kind
[00:29:33] of to be avoided. And certainly I think
[00:29:36] we've overregulated. We've made it
[00:29:37] impossible to build stuff. It's just
[00:29:38] like it's totally crazy what goes into
[00:29:40] getting building any type of thing in a
[00:29:42] lot of places either physical or
[00:29:44] otherwise. But you know like a lot of
[00:29:46] the regulations themselves are not the
[00:29:48] problem. Like if you've actually read a
[00:29:49] lot of these things like like having non
[00:29:51] smog choked cities is great. Being able
[00:29:53] to swim in like many rivers is great.
[00:29:55] Like having like a lot of these things
[00:29:56] were progress. The problem is that it is
[00:29:58] really difficult for humans to deal with
[00:30:01] understanding and complying with this
[00:30:02] and that every time you have to exchange
[00:30:03] a letter with the government, you wait
[00:30:05] months. And if you could take a lot of
[00:30:08] the things that we've learned and kind
[00:30:09] of make them like totally frictionless,
[00:30:12] that would actually pretty cool. And I
[00:30:13] think that um that I think is an under
[00:30:16] an underold story in in AI right now.
[00:30:19] >> Yeah. until the regulators start spewing
[00:30:20] tokens back at us and then you start
[00:30:22] getting huge amounts of documents from
[00:30:24] the regulators that you have to comply
[00:30:25] and it's agent on agent wars. But
[00:30:28] >> but that's basically what we have now.
[00:30:30] >> Yeah. But but there is a fair fight.
[00:30:32] Yeah.
[00:30:33] >> I'd argue that's an improvement from
[00:30:34] where we are now. Like one of the
[00:30:36] terrible things right now is if you
[00:30:38] build anything physical, you have to get
[00:30:39] a building permit. It's like you're
[00:30:40] guilty until proven innocent. And the
[00:30:42] worst thing I' that we've run into is
[00:30:44] the fire department because they have
[00:30:46] like the moral impremature of, you know,
[00:30:48] people pulling people out of burning
[00:30:50] buildings. And yet what they actually do
[00:30:52] is just like screw with your design for
[00:30:54] buildings for months. And I, you know,
[00:30:56] if we could replace the fire marshall
[00:30:58] with with an agent that would critique
[00:31:00] your your building plan quickly,
[00:31:03] >> um, even even if it's feedback was
[00:31:06] overdone, it would be massively better
[00:31:08] than the delays that exist today. When
[00:31:10] Max was talking about this potentially
[00:31:13] being a good thing to have all this
[00:31:14] regulation, my my head went to the
[00:31:17] things that make agents successful is uh
[00:31:20] humans or other agents setting up the
[00:31:21] right testing guard rails. Uh a lot of
[00:31:25] people are really excited about SLGOLO.
[00:31:27] I don't know if you guys have played
[00:31:28] with that or like Ralph loops where you
[00:31:30] tell the model go do this and this is
[00:31:32] your exit criteria. Well, I'm telling
[00:31:34] Blake go make us all supersonic. your
[00:31:36] exit criteria is that you've complied
[00:31:38] with all of these regulations. So
[00:31:40] there's totally a world in where we say
[00:31:41] like the regulations are great. They're
[00:31:42] like our testing, our test suite. As
[00:31:45] long as this p passing these tests for
[00:31:49] one that's not incurring contradictions
[00:31:51] and the regulations are actually
[00:31:53] reasonable, etc. Like they're actually
[00:31:55] an awesome guard rail to have.
[00:31:58] Otherwise, we would be shipping slop
[00:31:59] directly into into the air.
[00:32:01] >> Yeah. But this is going to turn into a
[00:32:02] red queen race, right? They're going to
[00:32:04] have agents. We're going to have agents.
[00:32:05] I think we might have better agents,
[00:32:07] which is good, as opposed to have to do
[00:32:09] human versus human, but if anything,
[00:32:11] their cycle time, their response time
[00:32:12] may get lower. Like the app store is
[00:32:14] drowning in spam. I'm sure the patent
[00:32:16] office right now is drowning in spam.
[00:32:18] And so these agencies, they're going to
[00:32:20] be slow adopters of AI. They're going to
[00:32:23] get DDoSed, right, by clever
[00:32:25] entrepreneurs just overloading them with
[00:32:27] documents. It's possible that the
[00:32:29] approval time for this stuff might
[00:32:30] extend out as this suddenly get flooded.
[00:32:32] It creates the opportunity to um I think
[00:32:35] really shift the model, the regulatory
[00:32:37] model. Imagine if we drove around a city
[00:32:41] the way we build things today. Before
[00:32:42] you could go anywhere, you'd have to
[00:32:44] write a plan up, ship it to some
[00:32:46] regulator, you know, and your plan would
[00:32:48] have to specify we're going to take such
[00:32:49] and such a route and we're going to
[00:32:50] drive this speed limit. We're going to
[00:32:51] use our blinker and we're going to stop
[00:32:52] at every stop sign and we're never going
[00:32:54] to run a red light, blah blah blah blah
[00:32:55] blah. And then 3 months later, you get
[00:32:57] back critique. It's like, well, we think
[00:32:58] you should like drive on this other
[00:32:59] street. And eventually you get approval.
[00:33:01] didn't go drive somewhere. It's insane.
[00:33:03] You can never go anywhere. And yet that
[00:33:05] is absolutely the way we build physical
[00:33:07] infrastructure in this country. It's
[00:33:09] guilty until proven innocent. And and
[00:33:11] what we should actually do is make more
[00:33:14] of these things enforcementbased
[00:33:16] rather than preapproval based.
[00:33:18] >> I mean, I don't know. I mean, I I don't
[00:33:20] want to be under too much. Like, if I
[00:33:21] ship a medical device to a lot of
[00:33:23] people, there needs to be it's like
[00:33:25] there's unknowns there. It's like we
[00:33:26] were responsible. We did clinical
[00:33:28] trials. We reported all the data, but
[00:33:31] Max, this is this is why there's so
[00:33:32] little innovation in medical right now
[00:33:34] because the FDA approval process is a
[00:33:36] nightmare. Uh, in fact, the two biggest
[00:33:38] advancements in tech in Silicon Valley
[00:33:41] in the last decade, AI and before that,
[00:33:43] crypto, they're both in the math domain
[00:33:45] because it's the last unregulated
[00:33:46] domain. And when they started regulating
[00:33:48] frontier models and started regulating
[00:33:49] GPUs, that stops as well. You know,
[00:33:52] Peter Teal laments about how there's no
[00:33:54] innovation in the physical domain.
[00:33:55] what's been held back by just the huge
[00:33:57] regulatory barriers and you can always
[00:33:58] find a scare version like you vaccine or
[00:34:01] medical like famous ones, right? But the
[00:34:03] regulations spread everywhere. The
[00:34:05] tentacles are everywhere and there's all
[00:34:07] these different contradictory regulatory
[00:34:08] bodies. You saw how uh was it SpaceX,
[00:34:11] they got sued first for for not having
[00:34:14] enough I forget what it was migrants or
[00:34:15] refugees or whatever, but they're not
[00:34:18] allowed to hire them by government
[00:34:19] regulation on the other side because
[00:34:21] they're not citizens. This is not like
[00:34:23] logical code that has to compile in one
[00:34:25] place. These are madeup random
[00:34:26] regulations all over the place. You
[00:34:28] might comply with one state, you violate
[00:34:30] another state, you violate federal over
[00:34:31] here, you annoy this guy over here, that
[00:34:33] guy chooses to prosecute one out of 50
[00:34:35] people who are his friend. It's it's
[00:34:37] very arbitrary. It's very capricious.
[00:34:39] >> And and moreover, like the idea that
[00:34:41] this makes like things safer, I think
[00:34:43] it's just a complete mythology. Like
[00:34:45] just watch, you know, watch watch Boeing
[00:34:46] as an example. They certified the 737
[00:34:48] Max, which had a single sensor that had
[00:34:52] complete authority over the nose up,
[00:34:54] nose down attitude of that airplane. No
[00:34:56] intern is dumb enough to think that's a
[00:34:59] good idea. And yet, it got all the way
[00:35:01] through the certification system. This
[00:35:02] stuff doesn't actually make us safer. It
[00:35:05] just makes us slower. Well, I mean,
[00:35:06] there's definitely dysfunction here. I
[00:35:08] mean, I think that some of this makes us
[00:35:10] safer in the sense that the NRC makes us
[00:35:12] safer, which is that their job was to
[00:35:13] make sure that nuclear energy was safe.
[00:35:15] They did this by permitting zero plants
[00:35:17] until I think like a year ago since the
[00:35:19] 70s. It will be perfectly safe if we
[00:35:21] never build any of it. And I want to be
[00:35:23] really clear that I'm on the side of
[00:35:24] deregulation in on a lot of this. I
[00:35:26] agree with Blake that a lot of this can
[00:35:28] be done a lot more efficiently. But I
[00:35:30] also think it's a little too dismissive
[00:35:31] just to say it's like oh this is like
[00:35:32] the FDA or like even it's it's in the
[00:35:34] reg it's in the agencies in general. And
[00:35:36] the problem is deeper to the degree that
[00:35:39] when the if the FDA approves 10 really
[00:35:42] important drugs, they don't get any
[00:35:44] credit for that. One patient dies and
[00:35:46] they get hauled before Congress and
[00:35:47] yelled at. And so they have very
[00:35:48] negatively biased incentives here. And I
[00:35:51] I think the reality is is that this is
[00:35:53] reflective of the beliefs of the
[00:35:54] American people. There's this trade-off
[00:35:56] here between the perception of risk
[00:35:58] taken in human subjects research and the
[00:36:00] rate at which we get new medicines. And
[00:36:02] it is absolutely true that if we move
[00:36:03] faster on this, we would learn. It's
[00:36:06] totally asymmetric and I think you're
[00:36:08] totally right, Max. If you approve a bad
[00:36:10] thing, your career is over. If you block
[00:36:12] a good thing, nobody notices, right? So,
[00:36:14] it so it creates this asymmetric
[00:36:16] slowdown. And I think this is um I think
[00:36:18] that is the most important problem to
[00:36:20] solve in the regulatory state.
[00:36:21] >> But but this is a very deep problem
[00:36:22] because it is this is where the voters
[00:36:25] are like and we we go and poll some of
[00:36:27] the stuff that we're working on in the
[00:36:28] future to understand kind of like where
[00:36:29] where the American people are on it. And
[00:36:32] if you push too hard on this, like there
[00:36:34] are there are all kinds of ways you
[00:36:35] could work around it. You go to prosper.
[00:36:37] There's all kinds of ways to try to go
[00:36:39] faster. But if you're seen as being a
[00:36:40] bad actor, then you're rejected from the
[00:36:43] society that we live in. That is the
[00:36:45] thing that you need an answer for, which
[00:36:46] is deeper than just saying like, "Oh,
[00:36:48] well, we need regulatory reform."
[00:36:49] >> You you have a deep point there, Max,
[00:36:51] which is uh it's the voters, right?
[00:36:53] Yeah.
[00:36:54] >> This where the citizens are. Like we
[00:36:55] like to blame politicians. You'll see an
[00:36:57] X all the time, right? When people are
[00:36:58] like, "Oh, this politician, that
[00:36:59] politician, you a politician." like
[00:37:00] they're elected, they're voted, majority
[00:37:02] vote, right? This is where the people
[00:37:04] literally are. That's the package.
[00:37:06] That's the bundle they've chosen. And
[00:37:07] you may not like this constantiation,
[00:37:09] but if you were to remove this one,
[00:37:10] something very similar would take its
[00:37:12] place because the voters would just vote
[00:37:13] them right back in. And I think
[00:37:15] culturally it's very hard for most
[00:37:17] people to understand what we lost, what
[00:37:20] we missed, right? So for example, like
[00:37:21] France, you know, there's a French
[00:37:23] entrepreneur on X lamenting that 57% of
[00:37:25] GDP gets sucked up by the government and
[00:37:27] so you can't create companies. But to
[00:37:29] the average French citizen, that's not
[00:37:31] visible. They don't notice what they're
[00:37:32] missing. They just know they're slightly
[00:37:33] poorer than the US. The economist just
[00:37:36] did a little piece on economist is
[00:37:38] finally coming back around to being
[00:37:39] capitalists after 30 years. And they
[00:37:41] just did a little piece on how the US is
[00:37:43] outstripping everybody and growing
[00:37:44] faster and getting bigger. But then they
[00:37:46] immediately turn around and say, well,
[00:37:47] it's because of the oceans, because of
[00:37:49] natural resources, everything but
[00:37:50] capitalism, right? They don't want to
[00:37:52] say the dirty sea word. uh because you
[00:37:54] know for some reason all of these all of
[00:37:56] these uh magazines became Marxist at
[00:37:59] some point um but they can't they can't
[00:38:02] envision or imagine what could have been
[00:38:04] if we had just been a little more lazare
[00:38:06] a little more open
[00:38:08] >> so I would love to see a true experiment
[00:38:10] among the 50 states you know different
[00:38:12] regulations different tax structures not
[00:38:14] because right now the federal tax
[00:38:15] structure and federal regulations
[00:38:17] dominate everything but imagine you know
[00:38:19] you could go to some small state if you
[00:38:21] had cancer and you could try every drug
[00:38:23] that everyone was cooking up in caviat
[00:38:25] mtor and you got to do your research and
[00:38:27] blah blah blah but this is known as the
[00:38:28] experimental zone um same way for drones
[00:38:31] same way for well aircraft is a little
[00:38:32] harder because you got to cross a lot of
[00:38:35] areas but
[00:38:35] >> do you think there's something magical
[00:38:36] in there the notion of like innovation
[00:38:38] zones because we have we have a huge
[00:38:39] like nimi problem right uh but if you if
[00:38:42] you create like you know opt-in yimi
[00:38:45] zones they create some experimentation
[00:38:47] framework and by definition it happens
[00:38:49] where people are consenting and you can
[00:38:51] try different rules or no rules or
[00:38:53] different ways of enforcing or you know
[00:38:55] innocent until proven guilty and then
[00:38:57] see what actually happens and what are
[00:38:58] the innovation consequences and what are
[00:39:00] the safety consequences and then then
[00:39:01] the successes can spread but I mean to
[00:39:03] Naval's to Naval's point an innovation
[00:39:06] zone would not solve the problem in drug
[00:39:07] discovery um there so there was the
[00:39:10] right to try act passed a little while
[00:39:11] ago we've had this pathway called single
[00:39:14] patient IND for a lot longer than that
[00:39:16] um the FDA like if if your doctor calls
[00:39:18] the FDA and says hey I want to give this
[00:39:19] my patient an approved drug they give
[00:39:22] over 99% of those over like they approve
[00:39:24] over 99% of those. They can even grant
[00:39:26] them over the phone. Um the problem is
[00:39:28] that in order to dose a patient, you
[00:39:30] still need clinical grade drug and the
[00:39:32] only entity with that is typically the
[00:39:34] IP owner who's in the middle of running
[00:39:35] a clinical trial. Like they're investing
[00:39:37] hundreds of millions of dollars into
[00:39:38] like making this thing. And the problem
[00:39:40] is that the FDA, they'll draw an adverse
[00:39:42] inference if something bad happens to
[00:39:44] your patient who's probably really sick
[00:39:46] to begin with. And that's going to be
[00:39:48] seen as a property of the drug which is
[00:39:49] global, not related to your innovation
[00:39:52] zone. And so there's kind of two
[00:39:54] problems. One is you need to get the IP
[00:39:56] owner to give you some of your drug
[00:39:58] which they're not going to do. And then
[00:39:59] you need to prevent the global regulator
[00:40:02] from casting doubt on what might happen
[00:40:04] with their clinical trial if they give
[00:40:05] you some.
[00:40:06] >> How would you address I mean I don't
[00:40:07] know your field. How would you address
[00:40:08] that in medicine?
[00:40:10] >> Oh well I mean that in particular I mean
[00:40:12] this is just like a very inside
[00:40:13] baseball. I think the FDA has to be
[00:40:14] prohibited from drawing adverse
[00:40:15] inferences across different users of a
[00:40:17] capsit, for example. There's these like
[00:40:20] a bunch of specific ways that you could
[00:40:21] really accelerate innovation with a
[00:40:24] relatively light regulatory touch by
[00:40:25] just um preventing this this kind of
[00:40:29] paranoia from driving our decisions.
[00:40:31] >> Is there anything better than the FDA
[00:40:33] out there? Like what are we benchmarking
[00:40:35] these regulators against or is it not an
[00:40:38] interesting question because we don't
[00:40:39] have everyone follows the FDA.
[00:40:40] >> So I'll give two two expansions to that.
[00:40:42] The first is um Europe which is not
[00:40:45] really better than the FDA but they have
[00:40:47] a different system in that they've got
[00:40:48] these these notified bodies which are
[00:40:49] basically private businesses that are
[00:40:50] blessed by their host governments to
[00:40:52] certify things whether this is trains or
[00:40:55] planes or medical devices and the
[00:40:57] notified body system uh creates slightly
[00:41:00] better incentives at the review layer
[00:41:01] because they can hire people they can
[00:41:03] grow there's competition among the
[00:41:04] notified bodies they themselves have to
[00:41:06] be compliant with the conditions placed
[00:41:08] by their host governments for
[00:41:09] certification but it means that they can
[00:41:11] there can be many thousands more
[00:41:12] reviewers than you might have in the US.
[00:41:14] The second thing I'll say is there
[00:41:16] actually is one approved getting paid
[00:41:20] implantable BCI today which is in China
[00:41:24] and the CFDA is thinking for itself. And
[00:41:27] they really do have a system that I
[00:41:29] think is going to give us a run for our
[00:41:30] money if we're not if we're not careful.
[00:41:32] And they they they handle it very
[00:41:34] differently.
[00:41:35] >> How do they handle it?
[00:41:36] >> I mean the costs to bring a drug to
[00:41:38] market or a device to market are just
[00:41:40] much lower. I mean you can try things in
[00:41:42] humans and you can try things on market
[00:41:44] like the so the problem the one of the
[00:41:46] things that I've spent a lot of time
[00:41:47] recently thinking about is like 20 years
[00:41:50] ago we were buying far fewer laptops and
[00:41:52] phones each one was much more expensive
[00:41:54] now there's they're cheaper there's far
[00:41:57] more of them we buy more of them the
[00:41:58] total spending has gone up this is great
[00:42:00] stock prices of things like Qualcomm and
[00:42:01] Samsung and Apple are way up everybody's
[00:42:03] happy they're using kind of the excess
[00:42:05] wealth generated by the phones and
[00:42:07] laptops to buy the phones and laptops um
[00:42:09] this doesn't happen in healthcare. In
[00:42:11] healthcare, because you've got this
[00:42:13] reimbursement mechanism in the way where
[00:42:14] there's this kind of enterprise sale
[00:42:16] happening, the bucket of money that we
[00:42:18] use to buy healthcare is basically
[00:42:20] fixed. It is not increasing as there is
[00:42:22] more stuff that is producing better
[00:42:23] healthcare outcomes like we see in
[00:42:25] technological growth industries. And so
[00:42:27] this means that the rate of spending on
[00:42:29] healthcare grows at roughly the rate of
[00:42:31] of growth of tax receipts. And so if
[00:42:33] let's say that like AI is booming and
[00:42:36] there's major advances that are
[00:42:37] happening and two years from now we're
[00:42:38] spending 10 times as much on AI as we
[00:42:40] are now, this could be great, but if in
[00:42:42] two years we're spending 10 times as
[00:42:43] much on healthcare, this would be a
[00:42:44] catastrophe. And this is fundamentally
[00:42:47] at odds with being a technological
[00:42:48] growth industry. And so as time goes on
[00:42:50] and there's more things to spend money
[00:42:52] on that extend and improve quality of
[00:42:53] life for patients, like we can restore
[00:42:55] vision to people go blind in their 80s.
[00:42:57] We might be able to extend life in like
[00:42:59] far past where it's been before. we can
[00:43:02] restore capability to patients that are
[00:43:03] older and in worse condition, but like
[00:43:06] how do you pay for that? There's kind of
[00:43:08] this like omni problem in healthare
[00:43:10] which is all really related the same
[00:43:12] problem which is just too expensive to
[00:43:13] bring these things to market and that's
[00:43:15] what China is getting at. The way out of
[00:43:17] this is not singlepayer or some revision
[00:43:20] to health to health insurance. It's to
[00:43:22] bring down the costs so that someone can
[00:43:24] buy this with a credit card finance
[00:43:25] maybe like a car worst case. And to do
[00:43:28] that, we have to make it cheaper to
[00:43:30] bring these things to market. And
[00:43:31] China's doing that. That that will allow
[00:43:33] them to sell these things for $10,000 on
[00:43:35] $100,000. There's no private market in
[00:43:37] healthcare. And because there's no
[00:43:39] private market, what was the analogy
[00:43:40] people make sometimes? Like imagine
[00:43:42] instead of going to restaurants and
[00:43:44] paying, you would basically go to all
[00:43:46] the restaurants and then at the end of
[00:43:48] the month, you would send all the
[00:43:50] receipts and all the bills to your
[00:43:51] insurer to the government and they would
[00:43:53] reimburse you. Well, there'd be a line
[00:43:54] outside every good restaurant. Every bad
[00:43:57] restaurant, you know, would be
[00:43:58] available. Um, the weights would be
[00:44:00] terrible. The product wouldn't improve.
[00:44:02] You're basically running a small
[00:44:03] communist society inside a larger
[00:44:05] capitalist society. And that's what
[00:44:06] we're doing in healthcare.
[00:44:07] >> It's also what we're doing on roads,
[00:44:09] which is why we have traffic. Like, it's
[00:44:11] the exact same situation on roads. It's
[00:44:13] why there's, you know, there's no
[00:44:14] variable pricing for getting on the
[00:44:16] highway. It's why it's always clogged.
[00:44:17] >> If you want to step on the third rail of
[00:44:19] healthcare for for a moment, think about
[00:44:20] this healthcare plan. Tell me what's
[00:44:22] wrong with it. Right? Imagine that the
[00:44:25] first 20% of your uh annual income was
[00:44:30] your healthcare deductible. Doesn't
[00:44:32] matter like if if you're broke and
[00:44:33] homeless, it's zero. If you're rich, you
[00:44:35] know, it's millions of dollars. Uh but
[00:44:37] whatever your annual income is, the
[00:44:38] first 20% is your healthcare deductible.
[00:44:41] And then the rest is paid by the
[00:44:42] government, the insurance system up to
[00:44:44] the usual caps that they have today. You
[00:44:46] would create a private market pretty
[00:44:49] quickly. And so like in dental and
[00:44:51] plastic surgery and sort of a lot of
[00:44:53] optional medical procedures, you would
[00:44:55] actually get a competitive situation.
[00:44:56] You get improvement. Like if you look at
[00:44:58] optometry, you know, with LASIC, you
[00:45:00] look at dental with like veneers and uh
[00:45:02] braces and all that stuff and kind of
[00:45:04] all the dental surgery stuff that they
[00:45:05] do. Or if you look at plastic surgery,
[00:45:07] like those fields do seem to be
[00:45:09] advancing because they're private
[00:45:10] payers. They have people who are, you
[00:45:12] know, voting with their money. So we
[00:45:14] need to do some equivalent of that in
[00:45:16] the normal healthare system. But people
[00:45:17] lose their minds. They don't want to
[00:45:19] think one step ahead. They're like, "No,
[00:45:20] no, no. Well, what about the broke
[00:45:21] person?" Well, the broke person has no
[00:45:23] income. So, they're like, "Well, 20% is
[00:45:25] too much for some people." Okay, you can
[00:45:26] put some deductible in there. But
[00:45:28] generally, if you don't have some
[00:45:30] private market where people are paying a
[00:45:32] lot of the times for what are medical
[00:45:34] procedures, you're just not going to get
[00:45:36] this feedback loop that you're talking
[00:45:37] about. You're not going to get this
[00:45:38] ability to spend more money into the
[00:45:40] system. Right now, like very wealthy
[00:45:41] people can't spend voluntarily into the
[00:45:43] system, but the prices aren't anywhere.
[00:45:45] The rate cards aren't anywhere. the
[00:45:47] system's not designed for it. It's like
[00:45:49] if you go shopping for medical care and
[00:45:51] you want to pay out of your pocket,
[00:45:53] sometimes they'll quote you a price
[00:45:54] that's 10x what they charge the
[00:45:56] insurance company.
[00:45:57] >> Have you heard Sid's story from GitLab?
[00:46:00] Do you know Sid?
[00:46:02] >> So, he was uh I mean
[00:46:04] >> had a massively successful IPO then was
[00:46:06] diagnosed with a rare cancer and has
[00:46:10] achieved has lived way past the
[00:46:11] prognosis, has really taken it into his
[00:46:13] own hands. I think he went from kind of
[00:46:15] he did frontline chemo and then there
[00:46:17] was one alternative that was available.
[00:46:19] He exhausted it and the doctors were
[00:46:21] like, "We've got nothing for you." Since
[00:46:23] I think like six or seven companies have
[00:46:25] come out of it, there's now 20 or 30
[00:46:27] drugs in his escalation ladder. He's
[00:46:29] still alive. Um years later,
[00:46:31] >> he's doing great. I saw him the other
[00:46:33] day and he he basically created his own
[00:46:35] like personalized medicines and uh
[00:46:38] treatment plan.
[00:46:39] >> Yeah, there's there's a handful of these
[00:46:40] anecdotes that I've heard now. I it is
[00:46:43] really clear to me that at the high end
[00:46:45] if you just kind of have like you're not
[00:46:47] dealing with insurance you have the
[00:46:49] resources you're like I want the full
[00:46:50] toolbox of modern science
[00:46:53] outcomes are possible that that like
[00:46:56] your normal like if you go and ask your
[00:46:57] doctor like oh what will happen if I do
[00:46:58] this they will just start shouting and
[00:47:00] throwing things but it is clear that
[00:47:02] that much that like that crazy things
[00:47:04] are possible at the high end and I think
[00:47:05] that this type of like end of one
[00:47:07] medicine is actually going to end up
[00:47:08] being a really rich source of research
[00:47:10] for understanding how to build more
[00:47:11] translatable things.
[00:47:12] >> It requires a ton of agency from the
[00:47:15] patient in a moment where they're at
[00:47:18] their weakest, which is pretty uh
[00:47:20] ironic. My friend passed away from
[00:47:22] cancer and like last thing he wanted to
[00:47:24] do was research n equals one medicine uh
[00:47:28] because he was just, you know, like like
[00:47:30] dying by the week. But this is where AI
[00:47:33] should really shine and come up with the
[00:47:35] right solutions and democratization of
[00:47:37] like what can you actually do when you
[00:47:39] find yourself in that situation. It's
[00:47:40] kind of crazy how few people get access
[00:47:42] to this just from a knowledge
[00:47:45] perspective, not just monetarily
[00:47:47] speaking.
[00:47:49] >> How much autonomous software do you guys
[00:47:51] have in your organizations that's
[00:47:53] running on its own or near autonomous
[00:47:55] and improving on its own? For us it's
[00:47:57] the a lot of the infrastructure is
[00:47:59] already autonomous because we have uh we
[00:48:01] have this capability uh that fires off
[00:48:04] uh upon finding anomalies which I
[00:48:07] recommend everyone creates a version of
[00:48:08] this or Verscell offers a version of
[00:48:10] this but upon anything happening that's
[00:48:14] anomalous today the mo most engineering
[00:48:16] organizations are responding to this by
[00:48:19] setting up alarms or uh like monitoring
[00:48:22] thresholds by hand which is pretty
[00:48:24] insane but that's actually how the
[00:48:26] entire industry works you say if my
[00:48:28] error rate increases by this amount uh
[00:48:30] at this API endpoint do this so we've
[00:48:33] actually uh automated a lot of the S sur
[00:48:36] job uh site reliability engineering so
[00:48:39] anything uh uh any metric that uh slows
[00:48:44] down speeds up uh throughput changes
[00:48:47] whatever fires off an anomaly alert an
[00:48:50] agent investigates that an agent can
[00:48:53] decide to create an incident if the
[00:48:56] incident is filed, people get looped in
[00:48:58] and the agent begins the process of
[00:49:01] remediation. We're doing everything
[00:49:03] except for like the actual like giving
[00:49:05] the tools for the agent to like you know
[00:49:07] change prod but we're basically like
[00:49:10] serving solutions on a silver platter to
[00:49:13] engineers and then the other thing
[00:49:14] that's working really well for us is
[00:49:16] just autonomous optimization processes
[00:49:19] um and autonomous security research. So
[00:49:21] the other we open source this tool
[00:49:23] called deepseac it's [ __ ] incredible.
[00:49:25] was like mythos, but you get it today.
[00:49:28] Uh we run it against our entire monor
[00:49:30] repo using 10,000 concurrent agents in
[00:49:32] the cloud and it found basically several
[00:49:35] quarters worth of security research uh
[00:49:37] progress was made in um basically a
[00:49:40] couple days and $14,000 worth of tokens.
[00:49:43] So I'm talking about like months worth
[00:49:45] of red teaming, security research,
[00:49:48] entire teams of people. Uh and so we're
[00:49:51] basically now running like this periodic
[00:49:53] because the the other problem with AI is
[00:49:54] that cyber security is becoming a
[00:49:56] nightmare. Um there's way too many
[00:49:59] vulnerabilities, way too much work to
[00:50:00] do. There's too powerful adversaries. So
[00:50:03] you have to like basically be investing
[00:50:05] very proactively. We're running a lot of
[00:50:07] autonomous security research. Um so S
[00:50:11] sur and then optimization work are very
[00:50:15] obvious. Uh you've probably seen on
[00:50:16] Twitter there's people translating code
[00:50:18] bases from language A to language B.
[00:50:20] Like a lot of the work that if you if
[00:50:22] you already put in the work to get a
[00:50:24] working program optimizing it or
[00:50:26] rewriting it in a native programming
[00:50:28] language or things like that is now
[00:50:29] becoming quite um quite doable uh with
[00:50:32] with Frontier models.
[00:50:33] >> I mean just for my own vibe coded app I
[00:50:36] built a uh bug reporting queue for my
[00:50:38] test flight users and they can report
[00:50:40] bugs from inside the app. It uploads the
[00:50:42] logs in a screenshot. And of course,
[00:50:44] they use for feature requests, too. So
[00:50:46] then I just have a simple Damon go
[00:50:47] through, compile all the bug reports. It
[00:50:50] actually proactively analyzes and fixes
[00:50:52] them in the background. And then it
[00:50:53] ships me a test flight version to try
[00:50:55] out before I ship it to the testers. And
[00:50:57] then for feature requests, I just have
[00:50:59] it right now compile them, but I could
[00:51:01] see an app in the future could literally
[00:51:03] be built by the users. Now, I'm not
[00:51:05] saying that's a good idea. It might be a
[00:51:07] mess, but at least it can take the bug
[00:51:10] reports and stuff.
[00:51:10] >> We should ship that, by the way, just to
[00:51:12] see what happens to the social
[00:51:13] experiment.
[00:51:14] >> Yeah. Yeah. The social experiment,
[00:51:15] right? You you end up with like that
[00:51:16] Homer Simpson car where it's got an
[00:51:18] umbrella and like a flashlight, you
[00:51:19] know, a clown horn and so on where it's
[00:51:22] got every feature. But definitely for
[00:51:23] bug fixing, you could do that. We did in
[00:51:25] a way a version of that experiment where
[00:51:27] uh I stopped all project work across the
[00:51:29] entire company for a week and said
[00:51:31] everybody from the receptionist to the
[00:51:34] engineers uh build whatever you think is
[00:51:37] the most important thing to build. Uh
[00:51:39] the only requirements you have to use AI
[00:51:41] and you have to demo it for the whole
[00:51:42] company when you're done. I expected we
[00:51:45] would get a large number of silly
[00:51:46] projects and a small number of needle
[00:51:48] movers. And what we got was a large
[00:51:50] number of needle movers and a very small
[00:51:52] number of silly projects. And wow. Yes.
[00:51:54] >> Yeah,
[00:51:55] >> that's a great experiment.
[00:51:56] >> Yeah, two or three are like trajectory
[00:51:58] changing like they would absolutely
[00:51:59] change the direction of the company. But
[00:52:00] the what this surprised me the most was
[00:52:02] literally the receptionist like the
[00:52:04] shipping and receiving associate whose
[00:52:06] job it was to like take packages off a
[00:52:08] truck and like email people when their
[00:52:11] like stuff came into inventory uh build
[00:52:14] an automation for that and uh and that
[00:52:18] that we're actually using. The
[00:52:19] conclusion I kind of is like, wow, like
[00:52:21] everybody has some idea of what could
[00:52:24] exist that would make the world better,
[00:52:26] but that many times their first order
[00:52:27] ideas are stupid and they don't have the
[00:52:30] they don't have the ability to project
[00:52:31] that out and kind of see that it's
[00:52:32] stupid. But if they have the ability to
[00:52:34] go from idea to an actual thing, if it's
[00:52:36] not working, they can react. They can
[00:52:38] iterate. And if you give them a week, by
[00:52:40] the time they're at the end of the week,
[00:52:41] they've actually built something that
[00:52:42] makes sense.
[00:52:42] >> But imagine if all work was like that.
[00:52:44] like how can you set up a workforce that
[00:52:47] does not do the work directly? All they
[00:52:51] do is train the agent that does the work
[00:52:54] for them. And we've done this as well
[00:52:56] like you have to remind folks and you
[00:52:58] have to like create hackathons and hey
[00:53:01] let's build agents. Uh and obviously
[00:53:03] there's a lot of people there's a
[00:53:04] culture change happening like there are
[00:53:06] a lot of people that are just coming in
[00:53:07] who intuitively know their job is to not
[00:53:10] work on the thing is to actually train
[00:53:11] the agent that works on the thing. But
[00:53:13] I'm curious about like, you know, what
[00:53:14] what does the autonomous company of the
[00:53:17] future look like?
[00:53:18] >> It could get a lot crazier. Maybe you
[00:53:19] just turn on all cameras and the agents
[00:53:21] just watching everything that's
[00:53:22] happening. It see the shipping and
[00:53:24] receiving thing is very inefficient and
[00:53:26] it creates the app presents the app.
[00:53:28] >> Did you see that? Zach installed this
[00:53:30] thing into everyone's machines. He's
[00:53:31] thinking about it. It's like we saw this
[00:53:33] too like we're we're um we're we're
[00:53:35] likely going to ship a feature into AI
[00:53:37] gateway that allows people to opt in
[00:53:40] into preserving inputs and outputs and
[00:53:42] then you can say for all of my inputs
[00:53:44] and all my outputs can you extract the
[00:53:46] skills of the things that I like learn
[00:53:49] from my work and then dump it as skills
[00:53:53] uh so that I can even download them for
[00:53:54] myself. But you could imagine people in
[00:53:56] in companies wanting to to share and and
[00:53:59] pull this together. It's funny because
[00:54:01] for me that's so unimaginable for my own
[00:54:03] work because my own work is not
[00:54:04] repetitive. I look for things to
[00:54:06] automate. There's almost nothing left
[00:54:08] for me to automate for my own work. And
[00:54:09] I and I hope that's where kind of
[00:54:11] everybody ends up, right? You just work
[00:54:13] in your maximum zone of creativity and
[00:54:14] interest at all times. And like if there
[00:54:17] is anything left to automate, you should
[00:54:18] automate it. Get it out of your life.
[00:54:20] It'll free you up to be creative and
[00:54:21] that's where you generate all the value.
[00:54:23] But I think that's very hard to see in
[00:54:25] the job career mindset because you hire
[00:54:27] people to do the same thing over and
[00:54:28] over and that's going away and that's
[00:54:30] really scary because people like, well,
[00:54:31] what am I going to do? Well, you're
[00:54:33] going to do creative things. You're
[00:54:34] going to come up with new things and you
[00:54:35] don't have to come up with a new thing
[00:54:36] every day. That's impossible, right? But
[00:54:38] you're going to come up with a new thing
[00:54:40] once in a while that will then create
[00:54:42] something else, some point of leverage
[00:54:44] for you. But it it is it is a scary time
[00:54:46] for people for sure. If you've been
[00:54:47] doing the same thing over and over for
[00:54:49] 10 years and now all of a sudden it's
[00:54:50] like, well, now you're going to train an
[00:54:51] agent and automate it away, that's
[00:54:53] scary.
[00:54:54] >> I think historically it was the returns
[00:54:56] were like 70% intelligence, 30% agency
[00:55:00] and now it's going to be 70% agency, 30%
[00:55:03] intelligence and that will that will
[00:55:06] shift further as the models get better
[00:55:07] and better.
[00:55:08] >> I'm actually not sure about that, Max.
[00:55:09] I'll take the counterpoint on that. I
[00:55:11] think it's 99% intelligence and 1%
[00:55:13] agency because then the agents will
[00:55:15] exercise the agency,
[00:55:17] >> right? You will literally be like, "Hey
[00:55:18] agent, I'm making smart decisions and
[00:55:20] thinking big thoughts. Just go implement
[00:55:22] stuff." In fact, sometimes I want to
[00:55:24] build features on apps uh that I'm
[00:55:26] flowing out of vibe coding. I'll ask the
[00:55:28] agent, "What features should I build
[00:55:30] next?" You know, go look at the logs, go
[00:55:31] look at the users, what should I do?
[00:55:33] >> To be clear, I'm talking about the
[00:55:35] returns to humans. um the the humans
[00:55:37] that will be best fit for the future
[00:55:39] will be the ones that are more agentic
[00:55:40] which is to say like the ones that can
[00:55:41] come in and just have the thought of
[00:55:42] like I'm going to open cloud and be like
[00:55:44] what should I build versus watch YouTube
[00:55:46] and here's a fun experiment I'll bet you
[00:55:48] we all know a lot of people now who are
[00:55:50] coding who weren't coding before
[00:55:51] including many cases ourselves right so
[00:55:53] the number the percentage of coders in
[00:55:55] the ecosystem has probably gone up by
[00:55:57] might be 10x right yeah it might
[00:56:00] literally be 10 times as many people are
[00:56:01] coding now than we're coding a year ago
[00:56:03] >> it's wild our signup numbers
[00:56:06] are through the roof and there's this
[00:56:08] new class of people who are not
[00:56:10] engineers.
[00:56:12] They just use the infrastructure. But I
[00:56:14] think it might be like podcasters and
[00:56:16] YouTubers and like people posting on X.
[00:56:18] The majority of people are still not
[00:56:20] creating code. Like I go to people and
[00:56:22] I'm like, "Oh man, vibe coding is so
[00:56:24] much fun. It's more fun than like I I
[00:56:25] had a little gaming group that I used to
[00:56:27] play video games and FPS's to blow off
[00:56:29] steam." I completely stopped playing.
[00:56:31] All that time went into vibe coding
[00:56:32] instead. It's more entertaining. you get
[00:56:34] something real out of it and but the
[00:56:36] feedback loop is just as tight or even
[00:56:37] better. And I went to my other friends
[00:56:39] and I was like, "Hey, you should be vibe
[00:56:41] coding instead." And they just gave me
[00:56:43] this blank look and I'm like, "No, no,
[00:56:44] you don't understand. Building things is
[00:56:46] so much easier." But I think to them it
[00:56:49] was always like some blackbox process in
[00:56:52] the background. They never understood
[00:56:54] it. They assume maybe you were just
[00:56:55] talking to computer all along. So they
[00:56:57] don't see what's changed. They don't
[00:56:58] realize it's a lot easier. to them just
[00:57:00] that starting to Max's point the
[00:57:02] starting is so impossible to imagine and
[00:57:04] hard they don't do it. So we might have
[00:57:06] taken you know 0.01%
[00:57:09] of the population writing code to maybe
[00:57:11] now it's 1% call it a 100x increase but
[00:57:14] 99% still never going to write code. So
[00:57:17] we are in this weird space.
[00:57:19] >> It's crazy. It's like it's a video game
[00:57:21] and it's a great video game but real
[00:57:23] stuff comes out.
[00:57:25] >> Yeah. My fiance was up all night last
[00:57:27] night because she couldn't go to sleep
[00:57:29] because she was hacking on something and
[00:57:30] of course she wasn't writing any of the
[00:57:31] code. But it's just like it's addictive
[00:57:32] in a way that programming hasn't been
[00:57:34] for me for like over a decade. It's
[00:57:36] amazing because it's like a lottery for
[00:57:37] people. I think the normies normies have
[00:57:40] gotten a little more into the vibe
[00:57:41] coding but through uh models that are
[00:57:43] more media models, video models for
[00:57:45] example, right? More people probably
[00:57:47] fooled around making videos and images
[00:57:49] than they did writing code and apps. The
[00:57:51] problem is like I don't video has its
[00:57:54] own issues, right? Maybe someday we like
[00:57:56] make me a great movie about X and I'll
[00:57:58] just spit out a good documentary, but
[00:58:00] right now they don't have the taste or
[00:58:01] the judgment. This is a bet that I have
[00:58:03] with uh Andre Carpathy was like what's
[00:58:05] the year that you'll be able to just
[00:58:06] dump in a book and get a movie out? I
[00:58:08] think closer although I think he has
[00:58:10] come down substantially in timeline
[00:58:11] since we made this bet a few years ago.
[00:58:13] By 2030 we're going to have like dozens
[00:58:16] of Lord of the Rings. Like there's going
[00:58:18] to be some fan who's like he did it
[00:58:20] wrong. I'm going to make my own take. Um
[00:58:22] like the famous stories or like the one
[00:58:24] of my other benchmarks for progress in
[00:58:26] AI is I'm a huge fan of of a series
[00:58:28] called The Expanse. Um there's a series
[00:58:30] there's a TV series and there's there's
[00:58:31] nine books and they've made the first
[00:58:33] six books but they haven't made the last
[00:58:34] three books and there's meaningful
[00:58:35] divergences and I just I haven't gotten
[00:58:37] in I haven't read the books. Like I'm
[00:58:39] looking forward to I can dump in the
[00:58:41] last three books conditioned on the TV
[00:58:43] series and be like generate the last
[00:58:45] three seasons.
[00:58:47] >> This is coming.
[00:58:48] >> That's a great feature. Yeah. But that's
[00:58:50] in a way it's easy because there's
[00:58:52] already all this reference material.
[00:58:54] When you said get me the next Lord of
[00:58:56] the Rings, I was really excited because
[00:58:57] we haven't really had a breakthrough in
[00:59:00] imagination.
[00:59:01] >> Oh, we're going to see that
[00:59:02] >> in culture the likes of Harry Potter and
[00:59:04] Lord of the Rings. I I'm really excited
[00:59:05] about that
[00:59:06] >> and that will be the I agree that that
[00:59:07] will be the more exciting one.
[00:59:09] >> What can humans uniquely do? This gets
[00:59:11] back this gets to the core issue. What
[00:59:13] are humans going to be able to uniquely
[00:59:14] do, right? And I think Max, you're an
[00:59:16] AGI maximalist. So for you it's nothing.
[00:59:19] Agents will do everything.
[00:59:20] >> I'm not like antihuman, but I just like
[00:59:22] I think it's going to be we will have to
[00:59:24] find like if your identity is how smart
[00:59:26] and creative you are, you're going to
[00:59:27] have a bad time.
[00:59:28] >> Yeah. I I guess I'm still on the other
[00:59:30] side of that. I think that creativity is
[00:59:33] still the thing in the environment that
[00:59:35] surprises you. You step out of the
[00:59:36] system and do something that wasn't even
[00:59:38] imaginable within the system. It's
[00:59:40] outside of the training data. It's out
[00:59:41] of the out of the distribution of data
[00:59:43] that was fed into the system. And I
[00:59:44] think there'll always be room for that.
[00:59:45] Have you noticed that every cla website
[00:59:47] looks the same? And and people like
[00:59:50] basically like dial in what a cla
[00:59:52] website looks like once you get enough
[00:59:54] generations out of the model. Like
[00:59:56] there's a look it's this serif font.
[00:59:59] It's brown and cream and they use
[01:00:02] monospace fonts with a certain amount of
[01:00:04] spacing. Like after a while you get this
[01:00:07] this distribution that you say well this
[01:00:10] this is not creative. This is slop that
[01:00:13] came out of claude. It's not going to be
[01:00:15] human versus computer. It's going to be
[01:00:17] human with computer versus just
[01:00:19] computer.
[01:00:20] >> Just computer will eventually happen,
[01:00:22] but we're pretty far away.
[01:00:23] >> But the computer is going to be able to
[01:00:25] produce these crazy super stimuluses
[01:00:27] that like it's going to be it's going to
[01:00:29] make the entertainment. And I mean, we
[01:00:32] kind of see a weak form of this in in
[01:00:33] Tik Tok. Um, and so when you think about
[01:00:37] the going like my my personal definition
[01:00:40] of art is meaningful out of distribution
[01:00:43] behavior. And so this is something that
[01:00:45] kind of is surprising in some way. Feels
[01:00:47] like you're kind of moving in the
[01:00:48] Z-axis. Like you're surprised that the
[01:00:50] thing was realized,
[01:00:51] >> but meaningful. Yeah.
[01:00:52] >> Meaningful means that like it it somehow
[01:00:54] to me means that it somehow changes your
[01:00:56] like future trajectory through the
[01:00:57] universe. Like your life is somehow
[01:00:58] different for having thought about it
[01:01:00] and and reflected on it. Well, my
[01:01:02] definition of art is completely
[01:01:03] different and leads to a completely
[01:01:04] different outcome. Sorry to interrupt.
[01:01:06] >> No, it's interesting how just by your
[01:01:08] definition, you get to a different
[01:01:09] premise. That's the extrapolation of the
[01:01:11] axiom.
[01:01:12] >> Yeah. I mean, one of the things I like
[01:01:13] about my definition is that it's so
[01:01:14] broad. Like, there can be like military
[01:01:16] maneuvers that you can be like, that was
[01:01:17] art.
[01:01:18] >> And I think we're going to see this all
[01:01:19] the time. We're going to see move 37s
[01:01:21] all over the place. Although, I'm
[01:01:22] curious what your definition of art is.
[01:01:24] >> I mean, I have multiple definitions, but
[01:01:26] so it's not like a concrete I haven't
[01:01:27] packaged into one thing. But I do think
[01:01:29] of art as something where you convey
[01:01:31] emotion. You convey something you felt
[01:01:33] to another person. And so you create
[01:01:36] some object or something or that that
[01:01:39] creates that that takes an emotion that
[01:01:41] you felt inside. And so to me, a
[01:01:43] computer almost by definition is
[01:01:45] incapable of doing it. The exact same
[01:01:47] piece of art uh without intent behind it
[01:01:51] is sort of meaningless. Now you can also
[01:01:53] argue nature is art like beauty in
[01:01:55] nature like you see a sunset, right? Not
[01:01:57] let's say human. So that one I would
[01:01:58] call it's pure intelligence working
[01:02:00] without motive. There's beauty for
[01:02:03] example in a sunset because there's an
[01:02:04] intelligence there. There's a complex
[01:02:06] system at work there and your brain
[01:02:08] recognize it and there's no motive
[01:02:10] there. So no ego gets involved. But art
[01:02:12] in kind of the more human sense I think
[01:02:14] of as someone felt something and they
[01:02:16] wanted you to feel that thing or they
[01:02:18] wanted to feel that thing again or they
[01:02:20] wanted to capture the feeling they had
[01:02:21] with that thing and so they created the
[01:02:23] thing. Attribution to who created it is
[01:02:26] going to be really important. So like
[01:02:27] for example a beautiful photo, right? If
[01:02:29] a person takes the photo versus AI
[01:02:32] generates the exact same photo down to
[01:02:35] the last pixel, the person taking the
[01:02:37] photo will have more meaning for me.
[01:02:39] >> I just invested in a startup that does
[01:02:41] verifiability with hardware at the
[01:02:42] station that someone some human actually
[01:02:44] took a photo which is going to have a
[01:02:46] lot of really cool use cases.
[01:02:48] >> It will we will be drowned in slop. No
[01:02:50] question.
[01:02:50] >> Do you remember the control net stuff
[01:02:51] from like a year or two ago? There was
[01:02:53] like there's one particular scene of
[01:02:55] like it was like a medieval village. It
[01:02:57] had like a swirl in it. Do you remember?
[01:03:00] >> Yeah.
[01:03:00] >> That was AI generated and that was the
[01:03:02] one of the first times I looked at this
[01:03:04] and
[01:03:05] >> thought it was really cool. Like whether
[01:03:06] you want to call it R.
[01:03:07] >> But that one doesn't that one break your
[01:03:09] your premise because some human came up
[01:03:12] with the the training and the prompt to
[01:03:15] arrive to that really cool riddle. By
[01:03:17] the way, it's totally possible that an
[01:03:19] AI can also do that in the future. But I
[01:03:22] give whoever came up with that idea of
[01:03:25] the optic optical illusion control net,
[01:03:28] I give them more credit than the
[01:03:29] >> I think the bar is going to be raised
[01:03:31] massively. Like it's going to take more
[01:03:32] and more to surprise you. It's going to
[01:03:34] have to be more and more impressive.
[01:03:35] Like Studio that's already happened.
[01:03:37] >> Yeah. Like like OpenAI destroyed Studio
[01:03:39] Ghibli for everybody. Nobody wants to
[01:03:41] see that Studio Ghibli work ever again,
[01:03:43] right? It's been done. And so
[01:03:45] >> Oh, that one also has I have a counter
[01:03:47] point to that one. Like have you watched
[01:03:48] real Studio Giblly? It actually looks so
[01:03:50] much [ __ ] better than the soft that
[01:03:52] open put out. Like watch it again now.
[01:03:55] It's impressive.
[01:03:55] >> Yeah. At the point where you've seen
[01:03:56] tons of Studio Ghibli things everywhere
[01:03:58] all over the internet. It is now in
[01:04:00] distribution. It's no longer surprising.
[01:04:01] The art value has been around.
[01:04:02] >> That's right. That's right. No, your
[01:04:04] surprise definition still works. I just
[01:04:05] think that that humans are the ones who
[01:04:08] can generate surprise completely out of
[01:04:10] the data distribution. And I think they
[01:04:11] can do it with intent and I do think
[01:04:13] intent matters for meaning. So to your
[01:04:15] meaning point, right, you said meaning
[01:04:17] and surprise, right? Right. And I guess
[01:04:19] what I would say is that humans can
[01:04:21] steal the ones generate surprise out of
[01:04:22] the system. For example, let's say you
[01:04:24] took an AI and you trained it to be
[01:04:27] perfect at mathematics, right? The
[01:04:28] perfect mathematics AI and it's within
[01:04:30] the formal system of mathematics. And
[01:04:32] then Kurt Goodle comes along and he has
[01:04:34] something completely outside of the
[01:04:35] system, right? Girdle's in completeness
[01:04:37] theorem. It was completely stepped out
[01:04:38] of the system and used uh attributes of
[01:04:41] physics to basically break the system.
[01:04:43] So that kind of thing I don't think an
[01:04:45] AI could get to. So there's always room
[01:04:46] for creativity outside. surprise and
[01:04:49] then the meaning comes from the fact
[01:04:50] that a human was involved that they did
[01:04:52] it for a purpose and they conveyed
[01:04:53] something. So maybe I can interpret your
[01:04:56] definition my way, but we'll see how it
[01:04:57] plays out. I'm a little more optimistic
[01:04:59] about humans.
[01:05:00] >> So if you train an AI model, it's
[01:05:02] trained on some data distribution. It's
[01:05:04] trained on some tokens. It then learns
[01:05:06] some some distribution of language and
[01:05:08] the structure within that. Um, is it
[01:05:10] possible for an LLM or transformer to
[01:05:13] kind of go out of distribution, have
[01:05:14] like a new idea that was not present in
[01:05:17] the training set somehow? Well, the
[01:05:19] training sets are so large that it is
[01:05:21] hard to imagine ideas that are not
[01:05:23] within the training sets somewhere. But,
[01:05:25] uh, if they exist, they probably lie in
[01:05:27] the natural domain in physics and
[01:05:28] interaction and feeling and emotions and
[01:05:31] evolution in things that the it's not
[01:05:33] subject to. So, I do think that there's
[01:05:35] still things outside of language, but
[01:05:36] language does encapsulate a lot.
[01:05:38] Language is a great compressor and we've
[01:05:39] got a lot of it.
[01:05:40] >> But I mean you can get to these other
[01:05:41] things through selfplay that
[01:05:44] >> selfplay and sensors like cameras are
[01:05:46] sensors like our eyes are sensors.
[01:05:48] >> Yeah. I mean I think the question is how
[01:05:49] do you what how do you go out of
[01:05:50] distribution without randomness? So in
[01:05:52] the case of like RL you can get
[01:05:54] randomness like you can sample an action
[01:05:56] from a distribution of an action space
[01:05:59] and you can get randomness that can take
[01:06:01] you down these walks into new territory.
[01:06:03] But I think the the real to kind of turn
[01:06:04] this around is like can humans go out of
[01:06:06] distribution? Where does any new idea
[01:06:08] come from? Are we also dependent on
[01:06:11] randomness to get us into these new
[01:06:13] territories?
[01:06:13] >> We're not dependent on pure randomness
[01:06:15] like like natural selection works
[01:06:16] through pure randomness, right? Where
[01:06:18] you just mutate a gene and then see what
[01:06:20] happens. But with humans, we seem to
[01:06:22] have this ability to cut through
[01:06:24] infinite space and get, you know, just
[01:06:26] eliminate huge swats. And so our
[01:06:28] creativity makes sense within the larger
[01:06:31] scheme of things. That seems to be one
[01:06:32] of our unique capabilities. And um maybe
[01:06:35] AI is starting to do at the edges as
[01:06:36] we're seeing with solving some of these
[01:06:38] math problems. But even math is a very
[01:06:39] bounded domain, but it's a big one. I'm
[01:06:41] not I'm not saying it'll never get
[01:06:43] there. I don't have that confidence. But
[01:06:44] I think at least at the moment, I would
[01:06:46] say that uh truly stepping outside
[01:06:48] surprising people, that's still a domain
[01:06:50] of humans. And I think humans plus AI is
[01:06:53] where it's all moving to. Like human
[01:06:55] without AI, forget it. Pure AI, I don't
[01:06:57] think is there yet. But I think human
[01:06:59] plus AI, we're in that era. How long we
[01:07:01] stay there, I'm betting is longer than
[01:07:03] people think. I think humans will have
[01:07:04] an enormous amount of value. Um, in
[01:07:06] fact, more value. All of us, everyone
[01:07:09] here, our productivity has gone through
[01:07:10] the roof. And basic economics normally
[01:07:13] says that when someone's productivity is
[01:07:14] higher, they're wealthier. They're
[01:07:16] better off. You actually hire more of
[01:07:17] them, not less of them. Maybe some of
[01:07:19] you are not hiring junior people
[01:07:21] anymore, although I don't know if that's
[01:07:23] necessarily true. I don't think of it as
[01:07:24] junior versus senior. If someone is
[01:07:26] really good with AI and they're really
[01:07:27] smart and creative, I want to hire them
[01:07:29] more than ever because the leverage I'm
[01:07:31] going to get out of them is incredible.
[01:07:32] >> That's a new requirement. And we're
[01:07:33] hiring juniors and super seniors as long
[01:07:35] as they're really good with agents and
[01:07:38] really good with AI and and quick to
[01:07:40] adapt.
[01:07:40] >> And a lot of them don't need to be hired
[01:07:42] anymore. They can create their own
[01:07:43] thing.
[01:07:44] >> My my hypothesis is we end up with a
[01:07:45] larger number of smaller teams. Like the
[01:07:48] number of people required to accomplish
[01:07:49] the given task drops by a lot. And you
[01:07:52] know people who only see first order of
[01:07:53] facts say oh my gosh all the jobs are
[01:07:55] disappear because I can do I can do a
[01:07:56] jet engine with two people. I don't need
[01:07:58] a thousand you know 998 jobs are gone.
[01:08:00] But what it actually means is you can
[01:08:01] create a lot of different chat engines.
[01:08:03] >> I think that's exactly right.
[01:08:04] >> I think there will be goes back to
[01:08:06] Naval's point. I I think the thing
[01:08:08] that's uniquely human is the creativity
[01:08:11] and what's been missing for you know a
[01:08:13] lot of people can be creative but they
[01:08:14] don't know how to turn their vision into
[01:08:17] a real thing that's changing. So I think
[01:08:19] we're have an explosion of an of
[01:08:21] entrepreneurship explosion of founders
[01:08:23] and a very large number of very small
[01:08:25] teams because you don't need many people
[01:08:27] to accomplish something.
[01:08:29] >> Yeah. I think like look AI provided uh
[01:08:32] base level intelligence and uh domain
[01:08:34] knowledge uh and cut through all the
[01:08:36] jargon and then now agents actually
[01:08:39] provide a lot of agency. So the main
[01:08:41] things left are creativity, taste, and
[01:08:43] yes, you need enough agency to get
[01:08:45] started, agency to stick with it, but
[01:08:47] you don't necessarily need the agency to
[01:08:49] like spend 20 years learning one thing
[01:08:51] before you can dive into it, make a
[01:08:52] contribution. And so that barrier going
[01:08:54] down, generalists are having a field
[01:08:56] day. And at the end of the day, we're
[01:08:58] all generalists. All of us like to think
[01:08:59] about everything. We don't like to be
[01:09:01] just trapped in one thing. Like Max is
[01:09:03] here talking about consciousness and the
[01:09:05] FDA and brain science and creativity.
[01:09:07] Like all of us are trying to think about
[01:09:09] everything all the time. And so, uh,
[01:09:11] people in Twitter who are always fond of
[01:09:13] saying like experts, credentials,
[01:09:15] sources, right? Those are the guys
[01:09:16] getting hurt because the expertise
[01:09:18] doesn't matter. You spent 5 years, 10
[01:09:20] years getting a PhD in XYZ,
[01:09:23] you know, hopefully develop your
[01:09:25] creativity and your instincts and your
[01:09:26] taste and your judgment because if all
[01:09:28] it did was help you memorize a whole
[01:09:29] bunch of things and jargon and, you
[01:09:31] know, learn some scaffolding stuff,
[01:09:32] well, AI will cut right through that.
[01:09:34] It's like a, you know, calculator times
[01:09:36] a billion or, you know, bicycle for the
[01:09:38] mind but accelerated. So I I think it's
[01:09:41] about people with AI versus people
[01:09:43] without AI. And so the single best thing
[01:09:45] you can be doing right now for yourself
[01:09:47] is just getting really good with these
[01:09:48] tools, getting comfortable with them and
[01:09:50] always knowing the edges of the
[01:09:51] boundaries of what they're capable and
[01:09:52] what they're not capable of. And that is
[01:09:54] a moving target.
