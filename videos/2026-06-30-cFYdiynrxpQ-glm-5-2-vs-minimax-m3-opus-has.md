---
video_id: cFYdiynrxpQ
title: "GLM-5.2 vs MiniMax-M3: Opus Has REAL COMPETITION (Model Stacking)"
channel: IndyDevDan
url: "https://www.youtube.com/watch?v=cFYdiynrxpQ"
watched_date: 2026-06-30
watched_at: "2026-06-30T12:00:00Z"
watch_count: 1
duration_seconds: 1579
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 24
watched_at_precision: date-from-history-label
watched_percent: 75
estimated_watched_seconds: 1184
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

GLM-5.2 and MiniMax-M3 are now legitimate competitors to Opus, with GLM-5.2 delivering near-Opus performance at one-fifth the cost and MiniMax-M3 offering further 5x cost reductions at the price of ~5-10% performance loss. The speaker presented these models using a three-tier framework (state-of-the-art, workhorse, lightweight) and a trade-off triangle showing that models can excel in only two of three dimensions: performance, speed, and cost. While GLM-5.2 is surprisingly fast, most of its tokens go to reasoning rather than response generation, making practical response times comparable to alternatives. Running these models locally remains impractical until mid-2027, requiring $2-100k in hardware investment.

For engineering agents, use the highest-capability model affordable; for product agents, route to the cheapest model that clears the quality bar for your users. Build a model stack with multiple providers rather than depending on a single vendor—don't wait for local deployment, rent GPU by the hour or use serverless APIs from multiple hosted providers. Use specialized prompts and context engineering to unlock workhorse model performance, allowing you to confidently downgrade from GLM-5.2 to MiniMax-M3 without sacrificing results.

## Transcript

[00:00:00] Engineers, it's official. Opus has real
[00:00:04] competition. GLM 5.2 is the leading open
[00:00:08] weights model, and right behind it is
[00:00:10] another really fantastic model, Minimax
[00:00:13] M3. Normally, I ignore the open weight
[00:00:16] models. In the past, they haven't been
[00:00:17] good. They haven't been competitive.
[00:00:18] That is no longer the case. It is now
[00:00:21] official. Opus has real competition. It
[00:00:24] has competition on multiple dimensions.
[00:00:26] Of course, as soon as Fable is launched,
[00:00:28] that competition is going to disappear,
[00:00:30] but there are other important key pieces
[00:00:32] of information I want to share with you
[00:00:33] here that can help your agentic
[00:00:35] engineering. So, let's frame our focus
[00:00:37] here on GLM 5.2 versus Minimax M3,
[00:00:41] because this is going to reveal four big
[00:00:44] ideas and 10 insights. Here they are. If
[00:00:47] these ideas interest you, stick around.
[00:00:48] Let's jump right into the conversation.
[00:00:51] The headline is simple. Opus has
[00:00:53] competition, but it goes deeper than
[00:00:54] that. As you know, the industry is
[00:00:56] undergoing a massive shift right now,
[00:00:58] and one of the big things I'm worried
[00:01:00] about, one of the big things many
[00:01:01] engineers are concerned about right now,
[00:01:03] is can an AI lab, the government, or
[00:01:05] anyone kill your agents at any point in
[00:01:07] time? We're thinking about resiliency.
[00:01:09] We're thinking about control and true
[00:01:11] ownership over our AI. And this is where
[00:01:13] open weight models really stand out.
[00:01:16] There are many providers for GLM 5.2,
[00:01:18] for Minimax M3, and we're going to
[00:01:20] discuss when and how can we really own a
[00:01:23] powerful model like GLM 5.2 that is near
[00:01:27] the front tier. This is not a
[00:01:28] benchmarking video. I want to give you
[00:01:29] the insights. I want to give you the oil
[00:01:31] of all the benchmarks out there, of all
[00:01:33] the information up there, so you can
[00:01:35] really understand the open weight
[00:01:37] landscape in a very efficient
[00:01:39] engineering first way. So, this is not
[00:01:41] about live coding. This is about
[00:01:42] engineering. This is about building out
[00:01:43] your engineering agents and your product
[00:01:46] agents. And then, at the end, I'm going
[00:01:47] to share my model stack. So, I'm going
[00:01:49] to share how I'm organizing all of these
[00:01:52] models on three tiers, [music] three
[00:01:54] categories, which we'll break down right
[00:01:56] now, State-of-the-art workhorse and
[00:01:58] lightweight models. So, of course, we're
[00:02:00] going to have the cracked Fable in
[00:02:01] there. You already know where that's
[00:02:02] going, but let's refocus on GLM 5.2
[00:02:06] versus [music] Minimax M3.
[00:02:12] What I like to do with all of my models
[00:02:14] is I place them on one of three tiers.
[00:02:18] We have the state-of-the-art tier, we
[00:02:19] have the workhorse tier, and we have the
[00:02:21] lightweight tier. This is a quick mental
[00:02:23] model for understanding where the
[00:02:26] language models capability sit. We're
[00:02:27] going to use Opus as our max control
[00:02:30] group. GLM 5.2 and Minimax are going to
[00:02:32] be the experimental groups we're going
[00:02:34] to be focusing all of our attention on.
[00:02:36] And then we're going to also have a min
[00:02:37] control model. Comparing a model in
[00:02:39] isolation is useless. So, what I like to
[00:02:41] do is I like to set up a
[00:02:43] state-of-the-art
[00:02:45] comparison. So, as you can imagine, Opus
[00:02:47] 4.8, this is the ceiling. This is the
[00:02:49] very top of the capability of models.
[00:02:51] There are others in this category, but
[00:02:53] just for this experiment, just to
[00:02:54] compare GLM 5.2 and Minimax M3, we're
[00:02:57] going to have a single front tier model.
[00:02:59] And we're also going to compare it
[00:02:59] against Quinn 3.6. So, this is running
[00:03:03] right on your local hardware. This is a
[00:03:04] lightweight model that you can own right
[00:03:07] now. So, when we have a max control
[00:03:08] model and a minimum control model, this
[00:03:10] gives us a clear framing to inspect and
[00:03:13] understand GLM 5.2 and Minimax at a
[00:03:16] deeper level. GLM 5.2 is going in the A
[00:03:18] tier and Minimax M3 is going in the B
[00:03:21] tier on raw performance. This is a
[00:03:23] performance benchmark, by the way, just
[00:03:24] to make that super, super clear. This is
[00:03:26] how I like to organize my models. I
[00:03:28] think about tiers of models, three
[00:03:30] tiers, and a single stack. So, it's not
[00:03:32] about picking one model, it's about
[00:03:34] having multiple options for your
[00:03:36] engineering agents and your product
[00:03:38] agents. So, here's the headline. I'm
[00:03:40] just going to give it all away right
[00:03:41] now. GLM 5.2 is the better model, but
[00:03:44] Minimax M3 is the better deal. So, the
[00:03:46] only real question that should be
[00:03:48] guiding your decision on which model to
[00:03:50] be using here, again for engineering
[00:03:52] agents and product agents is this. Do
[00:03:54] you need maximum capability or can you
[00:03:56] optimize for price? And that basically
[00:03:58] will flip your tier list. Opus goes
[00:04:00] right to the bottom, GLM goes right to
[00:04:02] the B tier, Minimax goes into A tier,
[00:04:04] and Quinn, of course, jumps into S tier.
[00:04:07] You can run this, air quotes, for free
[00:04:09] on your local hardware. And with a cloud
[00:04:11] provider, Quinn becomes a lot more
[00:04:13] powerful and fast while paying a very
[00:04:16] minimal price. So, that's the headline.
[00:04:17] GLM wins on performance, Minimax wins on
[00:04:20] price. And this is where things get
[00:04:22] pretty interesting. So, if we look at
[00:04:23] the raw stats of this, this is what
[00:04:25] really matters here. It's performance,
[00:04:26] speed, and cost. So, it's very clear
[00:04:29] Opus is in a decent lead above these
[00:04:32] open-weight models. A lot of
[00:04:33] hype-centered content creators and
[00:04:35] creators on X, they're going to tell you
[00:04:36] that GLM is a replacement for Opus 4.8.
[00:04:39] And as you likely know, that is not
[00:04:40] true. They are competitive. They're
[00:04:42] competitive in two dimensions,
[00:04:44] performance and cost, but they are not
[00:04:46] going to beat Opus. Let me just de-hype
[00:04:47] that. GLM cannot replace Opus. Let's be
[00:04:50] super clear about that. But both GLM 5.2
[00:04:52] and Minimax have some pretty great
[00:04:54] things to offer, great speed, and of
[00:04:56] course, great price. Now, this is where
[00:04:58] things really break down and where the
[00:05:00] numbers don't look so good for Opus.
[00:05:07] Starting with tokens per second, as you
[00:05:08] can guess, these lightweight sub-100
[00:05:10] billion parameter models, they're very,
[00:05:12] very fast and they're nowhere near as
[00:05:14] fast as they can be when we start adding
[00:05:16] things like speculative decoding,
[00:05:18] multi-token prediction. There are many
[00:05:20] ways to speed these models up even
[00:05:22] further. If you're on a Mac device, MLX
[00:05:24] is going to be a great first place to
[00:05:26] go. GLM's surprisingly fast, but the
[00:05:28] catch with this model is that GLM 5.2
[00:05:31] thinks a lot. Many, many, many of its
[00:05:33] tokens are just reasoning. And this
[00:05:35] shows up directly in the benchmarks. So,
[00:05:38] on artificial analysis, if we scroll
[00:05:39] down to output tokens here, GLM 5.2, if
[00:05:42] we look at the total output tokens per
[00:05:44] task, pretty much all the tokens were
[00:05:46] spent reasoning. And it's even more than
[00:05:48] Opus in max mode. It's much more than
[00:05:50] Minimax M3. So, very interesting here
[00:05:52] that a model can be quite fast, but if
[00:05:54] that speed is put toward thinking, it
[00:05:57] doesn't really, really matter. Because
[00:05:59] what we're looking for is response time.
[00:06:02] It's that total wall time that matters
[00:06:04] when we're thinking about getting
[00:06:05] results, when we're thinking about
[00:06:06] calling tools, and when we're thinking
[00:06:07] about the experiences that users will
[00:06:10] have when they're using your product
[00:06:12] agent. Okay, so inside one speed, all
[00:06:14] these models are viable. All these
[00:06:15] models are usable. This isn't really the
[00:06:17] differentiation point of these models.
[00:06:24] So, insight number two is the raw
[00:06:26] comparison. So, what is the
[00:06:28] differentiation? It is, of course,
[00:06:29] performance against price. So, this is
[00:06:31] what really matters in the, you know,
[00:06:33] the decision tree is quite simple. You
[00:06:34] should pick GLM 5.2 when capability is
[00:06:37] the most important thing at a lower
[00:06:39] price than Opus. And then you're going
[00:06:40] to want to pick Minimax when cost and
[00:06:42] volume are the constraints. And, of
[00:06:44] course, when Minimax can do the job. And
[00:06:47] this is like always the decision tree
[00:06:48] here. If the model can't do the job, it
[00:06:50] doesn't matter the price, it doesn't
[00:06:51] matter the speed, you can't use it. And
[00:06:53] that's the interesting part about GLM
[00:06:55] 5.2 is that we're getting into the space
[00:06:57] where GLM 5.2 is performing on par and
[00:07:00] slightly under a lot of the tasks Opus
[00:07:03] 4.8 is executing on. But when it comes
[00:07:05] to GLM 5.2 versus Minimax, this is the
[00:07:07] big takeaway. Use GLM if you need
[00:07:09] performance, use Minimax, though, if it
[00:07:12] can do the job. This is where we get to
[00:07:14] the cost curve. Because things get
[00:07:16] really, really interesting when you just
[00:07:17] look at the cost curve. The number here
[00:07:19] is that every time you drop a tier of
[00:07:21] capability, and the tier capability is
[00:07:23] becoming smaller and smaller every
[00:07:25] single month. But every time you drop a
[00:07:26] tier capability, you basically drop your
[00:07:28] price 5x. And it's the same from GLM to
[00:07:31] Minimax, and it's the same from Minimax
[00:07:33] down to Qwen 3.6. Although at this
[00:07:36] level, you lose too much capability. The
[00:07:38] Qwen models, although very powerful,
[00:07:40] although on device, although private,
[00:07:42] which are all important things we're
[00:07:43] paying close attention to, the
[00:07:44] intelligence must be at a certain level.
[00:07:47] I got to say though, you know, the more
[00:07:48] I experiment with Qwen 3.6 35 billion
[00:07:51] reactive, the more I like it.
[00:07:53] >> [laughter]
[00:07:54] >> And the more excited I am for the next
[00:07:56] Qwen local model release. The cost curve
[00:07:59] looks terrible. Like it's a cliff. It's
[00:08:01] a 5x cliff. And again, you just drop
[00:08:04] down one tier. And with each tier
[00:08:06] capability, you're not losing that much.
[00:08:09] Okay, so that's insight number three.
[00:08:10] The cost curve looks really, really
[00:08:12] rough for Opus. Opus 4.8 doesn't have
[00:08:14] much longer on the market before open
[00:08:16] weights models catch up pretty
[00:08:17] indefinitely.
[00:08:23] With that being said, insight four is us
[00:08:26] being really balanced here. Engineering
[00:08:27] is all about trade-offs. We'll talk
[00:08:28] about that more in a moment. The
[00:08:29] workhorse models called tools like Opus,
[00:08:31] but they don't ship like Opus. You can
[00:08:33] look across every single benchmark in
[00:08:35] this benchmark here on artificial
[00:08:37] analysis. I've dialed into these four
[00:08:39] models to simplify the comparison. But
[00:08:41] if we just search GLM 5.2 max, across
[00:08:43] the board this model will always lose to
[00:08:45] Opus. And sometimes very dramatically.
[00:08:48] And you can see here, every once in a
[00:08:50] while it's losing to Minimax as well.
[00:08:52] But the thing to pay attention to here
[00:08:53] isn't just all the benchmarks that GLM
[00:08:56] 5.2, it's the emergent behavior that
[00:08:59] emerges as you go up on these benchmark
[00:09:02] scores. Like all of these benchmarks are
[00:09:03] proxies for some capability. Terminal
[00:09:06] bench, super popular one, agenda coding
[00:09:08] and terminal use. This is just one proxy
[00:09:10] for agenda coding. The benchmarks do a
[00:09:13] decent job alone. When you really put
[00:09:14] together the index, it means a lot more.
[00:09:17] And so when you just look at the raw
[00:09:18] numbers here on how much better this
[00:09:21] five points looks like a small amount,
[00:09:23] it's not. It's a massive amount. The
[00:09:24] five points of difference on the index
[00:09:26] means a lot. Just because you can call
[00:09:28] tool doesn't mean you're a great model.
[00:09:30] And things really start to fall off for
[00:09:32] long horizon tasks. Whatever Anthropic
[00:09:35] is doing to train their Claude series
[00:09:37] models, specifically Opus and Fable.
[00:09:39] This is a huge point of differentiation.
[00:09:41] Workhorse models called tools like Opus,
[00:09:43] but they don't ship like Opus. The
[00:09:45] results are not the same. So, there's
[00:09:47] still a gap. Let's be super honest about
[00:09:48] that. GLM is not a replacement for Opus
[00:09:51] 4.8. It's a decent competitor.
[00:09:58] I always think about this trade-off
[00:10:00] triangle. As I'm working through
[00:10:02] benchmarks, as I'm creating my own
[00:10:03] custom benchmarks, and as I'm building
[00:10:05] engineering agents and product agents,
[00:10:07] I'm always comparing these models with
[00:10:09] this framework. And this is how I like
[00:10:10] to visualize this. There are three axes.
[00:10:12] You have performance, you have speed,
[00:10:14] and you have cost. And in reality, you
[00:10:16] get to pick two, never all three. Very
[00:10:19] clearly, Opus gives you performance.
[00:10:20] Minimax is going to give you cost and
[00:10:23] performance, more on the cost side.
[00:10:25] Quinn, of course, this is all speed and
[00:10:27] cost, probably more on the cost side.
[00:10:29] And then, GLM is going to give you the
[00:10:31] speed and performance. And honestly,
[00:10:32] this one's pretty good on cost, as well.
[00:10:34] GLM's probably going to be that closest
[00:10:36] one that does all three for you. Every
[00:10:38] single model has a trade-off. And if
[00:10:40] we're going to be objective, if we're
[00:10:41] going to do actual engineering and not
[00:10:43] vibing, we need to be honest about where
[00:10:45] all these models are. I use this
[00:10:47] trade-off triangle all the time to help
[00:10:49] me place these models. I use this and
[00:10:51] the tier list. Engineering is all about
[00:10:53] trade-offs. Language models and agents
[00:10:54] are no different. Every model can be
[00:10:56] placed on this chart. We can probably
[00:10:58] push GLM's performance up a little bit
[00:11:00] more here, as well as Minimax. But this
[00:11:02] is really what it's about. Understanding
[00:11:04] your model and then creating a model
[00:11:06] stack, which we'll talk about more
[00:11:08] later. I keep saying engineering agents
[00:11:09] and product agents. Let me just clarify
[00:11:11] this. Engineering agents are the first
[00:11:13] version of agents. Thanks to Claude
[00:11:15] Code, thanks to the first Claude series
[00:11:17] models, agents for engineers have been
[00:11:19] unlocked. But this is just a fraction,
[00:11:22] literally less than 1% of all the agents
[00:11:25] that will be created in the future. What
[00:11:26] are the other agents? It's product
[00:11:28] agents. Here, I'm just grouping every
[00:11:30] other domain under product agents. And
[00:11:32] these are the agents you'll deploy into
[00:11:34] your products. This is where tokenomics
[00:11:36] really matters and where you have to
[00:11:38] arbitrage your tokens because that's the
[00:11:40] business. For engineering, we can be a
[00:11:42] little bit more loose and dynamic with
[00:11:44] our token spend because of course we're
[00:11:46] still in the experimentation phase, but
[00:11:48] it's also harder to measure the ROI
[00:11:51] right now out of engineering agents. All
[00:11:53] that being said, it's still important to
[00:11:55] know how and when to use the right
[00:11:57] language model for your agents. The
[00:11:59] simple guideline is if you can afford
[00:12:01] the best compute, use it because you'll
[00:12:03] be getting the best results. At the same
[00:12:04] time, as these models catch up, as we
[00:12:07] discussed in our Fable band video, just
[00:12:09] like Opus can do a lot of what Fable can
[00:12:11] do, we're getting to that point where
[00:12:12] some of these open weight models can do
[00:12:14] 80, 90% of what Opus can do. And I'm
[00:12:17] specifically looking at GLM 5.2. If
[00:12:19] you've been using this model, you
[00:12:20] understand that it is getting close. It
[00:12:23] is competitive with Opus 4.8 at a fifth
[00:12:26] of the price. It's becoming harder and
[00:12:27] harder to ignore that. So, again, just
[00:12:29] thinking about that three-tier
[00:12:30] framework, right? We have
[00:12:32] state-of-the-art for our hardest work,
[00:12:33] and then we have daily drivers and
[00:12:35] high-volume agents. These are your
[00:12:37] workhorse agents that can do a lot of
[00:12:39] work, not at the best performance, but
[00:12:41] it's going to be a lot cheaper, and by a
[00:12:42] lot, we're talking 5x cheaper, and then
[00:12:44] 20x cheaper if you drop down to the
[00:12:46] Minimax tier level. And then of course,
[00:12:48] we have what we're all looking for,
[00:12:49] local private models. This is coming. We
[00:12:52] need more time. As mentioned, we're
[00:12:53] going to talk about some of the hardware
[00:12:55] requirements needed to ship and really
[00:12:57] use a GLM level model on local hardware
[00:13:00] in just a moment here. So, this is how I
[00:13:02] think about engineering agents.
[00:13:03] Basically, if you can, spend all the
[00:13:05] compute. If you can't, delegate to
[00:13:07] smaller, cheaper models. And I think
[00:13:09] it's important to understand the local
[00:13:11] model capabilities of models like Qwen
[00:13:12] 3.6, Gemma 4, so you really know what is
[00:13:15] possible on device right now. I'm going
[00:13:18] to be creating a lot more content around
[00:13:20] these local models because they're
[00:13:22] catching up and there are a lot of use
[00:13:24] cases that they can cover now while
[00:13:26] being local and private. So, make sure
[00:13:28] you like, make sure you subscribe, all
[00:13:29] that good stuff. Let's keep rolling.
[00:13:35] Product agents is a bit different
[00:13:37] because tokens matter. The tokenomics
[00:13:39] matters. Routing to the cheapest model
[00:13:41] that clears the bar, that satisfies your
[00:13:43] users is what makes or breaks your
[00:13:45] business when we're talking about your
[00:13:46] product agents. So, for example, with
[00:13:48] our two models we're looking at right
[00:13:50] here, GLM versus Minimax, when you have
[00:13:52] users at scale and we're talking tens of
[00:13:54] thousands, hundreds of thousands of
[00:13:55] users, you have to think about the
[00:13:57] tokenomics. You cannot just throw Opus
[00:13:59] at it. It's not scalable. As you can
[00:14:01] very easily imagine, at the same time,
[00:14:03] something like Qwen 1.5 6 super low
[00:14:05] performance, all that to say very, very
[00:14:07] simple task. And I'm not talking about
[00:14:08] role-playing, I'm not talking about
[00:14:10] these stupid really low-level entry use
[00:14:12] cases for these models. I'm talking
[00:14:14] about like real work, right? We're
[00:14:15] talking about accounting, we're talking
[00:14:16] about finance, we're talking about
[00:14:17] healthcare, we're talking about
[00:14:18] biomedicine, we're talking about getting
[00:14:20] value out of these models at consumer
[00:14:22] level scale. These models make
[00:14:24] businesses run now. GLM 5.2, Minimax M3.
[00:14:27] If you study these models, if you
[00:14:28] understand the tokenomics, if you
[00:14:30] understand the performance, you know,
[00:14:31] GLM is your performance per action and
[00:14:33] then Minimax M3 is going to be your cost
[00:14:35] per action winner here. This matters a
[00:14:37] lot for your product agents and I'm
[00:14:40] building out products right now that I'm
[00:14:41] consciously making this decision on. Do
[00:14:43] I need performance here? Do I need cost
[00:14:45] here? When I benchmark both these, what
[00:14:47] does the result look like? When can I
[00:14:49] use Minimax? When should I use GLM 5.2?
[00:14:57] Another important insight I want to
[00:14:58] share with you, three of the four of
[00:15:00] these models can't be switched off.
[00:15:01] We're all up to date on what's going on
[00:15:03] with Fable, the government, Anthropic.
[00:15:05] Insert any AI lab substitutability isn't
[00:15:08] a footnote, it's the whole strategy in
[00:15:09] 2026 and beyond. If you're going to
[00:15:11] scale your engineering agents and your
[00:15:13] product agents into production, we can't
[00:15:16] have models that can just switch off at
[00:15:18] any second. Now, of course, there's a
[00:15:20] lot of fear around this. The economics
[00:15:22] around shutting down an AI model is so
[00:15:25] bad for Anthropic, for OpenAI, for
[00:15:27] Gemini, that they would never allow it
[00:15:29] to happen for too long. But, um things
[00:15:31] that can happen do happen.
[00:15:33] Right? As we saw with the Fable model.
[00:15:35] And it's not like mythos class of the
[00:15:36] models are going to stop. It's being
[00:15:38] said that Anthropic has finished
[00:15:40] training the model after Fable. So, it's
[00:15:42] not like the model progression stops.
[00:15:44] But, the key here is we're not in
[00:15:45] control of this. This is a closed source
[00:15:47] model. Fable was the last straw. We
[00:15:49] cannot fully depend on the most
[00:15:50] important technology to be available to
[00:15:52] us. We must make sure it's available to
[00:15:55] us. And so, these open models are going
[00:15:56] to be really, really important for that.
[00:15:58] Right now, only lightweight models are
[00:16:01] available to really own end-to-end. I
[00:16:03] definitely recommend, if you don't, grab
[00:16:05] whatever chips, any device you can, so
[00:16:07] that you can get your hands on these
[00:16:09] sub-50 billion parameter models with the
[00:16:11] mixture of experts on it, so that you
[00:16:13] can really have local AI, no matter
[00:16:15] what. But, what's coming next, and what
[00:16:17] I think a lot of us are really excited
[00:16:18] for, is when we can run GLM 5.2 and
[00:16:21] MinimaX M3 on some local hardware, on
[00:16:24] our home lab. Now, this is possible now.
[00:16:27] Some prosumers, some engineers, you
[00:16:29] know, spending tens of thousands of
[00:16:30] dollars can do this now. So, let's
[00:16:32] analyze like what does it really take to
[00:16:34] own GLM 5.2, a powerful workhorse model.
[00:16:42] GLM is available right now. You and I
[00:16:44] can own this, but it's just not all too
[00:16:46] realistic yet when you look at the
[00:16:48] actual cost breakdown. So, an M5 Max
[00:16:51] MacBook Pro device like mine, I cannot
[00:16:53] run this. Okay, so I'm out of the
[00:16:54] running already. I need custom hardware,
[00:16:57] custom chips, Nvidia hardware to be able
[00:16:59] to run this thing. At about a budget of
[00:17:01] 2 to 4,000, you could probably get a
[00:17:04] serious 1 2-bit quant of GLM 5.2 running
[00:17:08] on your budget home lab at a very slow 6
[00:17:10] to 11 tokens per second. To me, this is
[00:17:12] unrunnable. So, this is not worth it at
[00:17:14] all. Now, at the next tier up, things
[00:17:16] become a bit more viable, but it's going
[00:17:18] to cost you. This is usable, 10 to third
[00:17:20] tokens, but you're going to need
[00:17:21] something like Mac Studio M3 Ultras or
[00:17:23] DGX Sparks stacked up. Bandwidth is
[00:17:25] going to be the constraint here. Again,
[00:17:27] this is viable. This is something you
[00:17:29] can do right now. It's getting harder
[00:17:30] and harder to find access to RAM and
[00:17:33] it's becoming more and more expensive,
[00:17:34] but this is available. Now, where this
[00:17:37] really becomes viable is if you're
[00:17:39] willing to drop, you know, 50 to 90k,
[00:17:41] really 50 to 100,000 dollars on, you
[00:17:43] know, something like six RTX Pro Black
[00:17:46] Wells. That's going to give you a 500 GB
[00:17:47] of RAM. Then you'll be able to run the
[00:17:49] like 4-bit quant GLM 5.2. As you can
[00:17:52] see, very, very expensive. I have a
[00:17:54] rough timeline here. This is just my
[00:17:56] rough estimate. I'm looking for that
[00:17:58] mid-2027
[00:18:00] time period to really get a GLM class
[00:18:03] model running locally on my hardware, on
[00:18:05] some box. I'm really hoping for that
[00:18:07] next gen M5 Ultra from Apple, but if
[00:18:10] they don't put it out, I'll build it
[00:18:11] myself with some Nvidia and AMD
[00:18:14] hardware. Whatever I have to do to get
[00:18:15] that, it's now a priority for me to make
[00:18:18] sure I de-leverage off of closed-source
[00:18:20] AI models. As we kind of move toward
[00:18:22] that place, you know, not all of us are
[00:18:24] going to drop tens of thousands of
[00:18:25] dollars on compute when we can take this
[00:18:27] compute and throw it against an API. So,
[00:18:29] you know, I just want to list out the
[00:18:30] options for you. This is how I'm
[00:18:31] thinking about this right now. There's
[00:18:32] kind of four options, right? You can set
[00:18:34] up a home lab. You can rent GPU by the
[00:18:36] hour. So, if you're running a business
[00:18:38] at scale, this is an option. Someone
[00:18:40] else can host the open weights. There
[00:18:42] are tons of providers. I think this is
[00:18:44] going to be the current action for most
[00:18:46] of us because we can always have one of
[00:18:48] 20 providers up and running for us. Very
[00:18:51] likely you'll only need two or three,
[00:18:52] but you for sure want to de-leverage off
[00:18:54] of a single provider for the model
[00:18:56] that's running your business.
[00:18:57] Specifically talking about product
[00:18:59] agents here, but also engineering agents
[00:19:00] as well. And then there's of course just
[00:19:02] paying per second, scale to zero, best
[00:19:04] for burst to uses. But this sits very
[00:19:06] closely to hosted open weight APIs. So,
[00:19:09] these are kind of the options that I'm
[00:19:10] looking at. I'm really, really looking
[00:19:12] forward to getting the home lab, but
[00:19:13] it's not all too realistic. And it's
[00:19:15] going to be a lot simpler, especially if
[00:19:16] you're running a business, to rent GPU
[00:19:18] by the hour or to do what we're all
[00:19:19] doing right now, which is just to hit
[00:19:21] serverless. So, the story for owning
[00:19:23] your own GLM 5.2 is basically you have
[00:19:26] to wait a year. Right now, we're stuck
[00:19:27] using cloud providers. But that's okay,
[00:19:29] because we have more cloud providers
[00:19:31] than ever. GLM is hosted on some 10, 20
[00:19:33] different providers. I'm really, really
[00:19:35] looking forward to this. There is a
[00:19:37] nightmare scenario here where GPU and
[00:19:39] and RAM prices continue to just go up
[00:19:41] throughout 2027. This is a real
[00:19:43] possibility, which will then push out
[00:19:45] this timeline even further for owning
[00:19:47] these workhorse models locally on your
[00:19:50] device. So, I think Minimax is smaller,
[00:19:52] right? Minimax is 400 billion parameters
[00:19:55] and runs 23. So, Minimax is a lot closer
[00:19:58] to being run on some local hardware. If
[00:20:00] you really want that Opus level
[00:20:01] performance, we're going to have to wait
[00:20:02] a bit longer. But this is just something
[00:20:04] to keep your eyes on.
[00:20:09] Don't pick a model, pick a model stack.
[00:20:11] So, this is one of the, you know, big
[00:20:12] ideas that I've been talking about on
[00:20:14] the channel more and more and more. You
[00:20:15] don't want to be dependent on one model.
[00:20:17] You don't want to be dependent on one
[00:20:18] model provider. Everything going on with
[00:20:19] Anthropic, with Fable, with the
[00:20:21] government is kind of showing us that
[00:20:23] right now. It's time to pick a model
[00:20:25] stack. Let's elevate ourselves. Let's
[00:20:27] de-leverage. Let's become more resilient
[00:20:29] as agentic engineers. We need model
[00:20:31] stacks. So, these are all the models I'm
[00:20:33] actively using, researching,
[00:20:35] experimenting, and using in both
[00:20:36] engineering and product agents right
[00:20:39] now. I wanted to kind of share my tier
[00:20:40] list with you to kind of give you an
[00:20:41] idea of where these models belong in
[00:20:44] each category. Let's start with the top
[00:20:45] and the bottom. So, Fable 5 is S+ tier.
[00:20:47] No other model is going to be an S+
[00:20:49] tier. This is the best of the best. As
[00:20:51] soon as this comes back online, I have
[00:20:52] several gnarly experiments that I want
[00:20:54] to run, and I'll be doing heavy, heavy
[00:20:55] multi-agent orchestration. Check out the
[00:20:57] previous couple videos where we talked
[00:20:58] about this model in detail. So, that's
[00:21:00] our very state-of-the-art. And then at
[00:21:02] the bottom, we have our Gemma, and we
[00:21:04] have the Quint 3.6 35 billion parameter
[00:21:07] model. So, I'm actively using these,
[00:21:08] testing, building on these. These are
[00:21:10] the lightweight models. At the
[00:21:12] lightweight level, you own this fully.
[00:21:14] That's one of the properties of
[00:21:15] lightweight, it can run on your device.
[00:21:16] So, we're talking sub 100 billion
[00:21:18] parameter model. Then we have our
[00:21:19] workhorses. So, these are the models
[00:21:21] that could run up to 90% of what you're
[00:21:23] probably using state-of-the-art for.
[00:21:25] These models are the GLM 5.2 and the
[00:21:28] Minimax M3. And the only difference here
[00:21:30] really between the A and B tier is a
[00:21:33] performance hit of maybe 5 to 10 points
[00:21:36] on artificial analysis. GLM 5.2 down to
[00:21:39] Minimax, it's going to be like 5-6
[00:21:40] points in that 40 to 50 range. And
[00:21:43] that's going to be pretty consistent
[00:21:44] across every single benchmark. You're
[00:21:46] going to see a 5 to 10% drop in
[00:21:48] performance by dropping down the A tier
[00:21:51] to the B tier, but you're still going to
[00:21:52] have a great workhorse. And with great
[00:21:54] prompt, context, and harness
[00:21:56] engineering, you can easily make a B
[00:21:58] tier an A tier. But, you know, by
[00:22:00] default, out the box, your B tier is
[00:22:02] going to be a little more optimized for
[00:22:03] price, while your A tier is going to be
[00:22:04] more optimized for performance. I'm just
[00:22:06] going to go ahead and place the rest of
[00:22:07] these, right? These are all the models
[00:22:08] I'm using right now in my model stacks.
[00:22:11] Opus, obviously S tier. GPT 5.5 coming
[00:22:13] right before it. We have a ton of
[00:22:16] workhorse models here. So, Gemini Flash
[00:22:18] coming in here. We have Gemini 3.1 Pro.
[00:22:21] I'm going to throw that behind GLM 5.2.
[00:22:24] We of course have our Deep Seek Pro. And
[00:22:26] then we have Deep Seek Flash. That's
[00:22:27] going to be your B tier model. Uh Kimika
[00:22:29] 2.6, that's going to be a B tier. And
[00:22:31] then Quinmax, this is also going to be
[00:22:33] an A tier model. This is my model stack.
[00:22:35] And the whole idea here is you want to
[00:22:37] think about your models in tiers, in a
[00:22:40] stack. You want to have your
[00:22:41] state-of-the-art for your hardest work,
[00:22:42] for your engineering work. You want to
[00:22:44] have your workhorses that you put in
[00:22:45] your products. And then you have your
[00:22:46] lightweight that you can run locally and
[00:22:48] use for private personal things. And
[00:22:50] eventually, the idea is that all these
[00:22:52] models over time will move down the
[00:22:54] stack while new ones come in to the
[00:22:56] state-of-the-art and in to the S tier.
[00:22:58] And this gives you and I more and more
[00:22:59] control, but we have to choose the right
[00:23:02] model for the job trading off
[00:23:04] performance, speed, and cost when it
[00:23:06] matters the most. And a great side
[00:23:08] effect of this is that you deleverage
[00:23:10] off of the closed sourced models that at
[00:23:13] any point in time can just rug pull or
[00:23:15] be rug pulled as we saw with the Fable
[00:23:17] model. We have a ton of open weights
[00:23:19] options now. I think GLM is actually
[00:23:21] outperforming 3.5 Flash. We can go ahead
[00:23:23] and look at that. Exactly, yeah, it is.
[00:23:25] So, it's just a point above Gemini 3.5
[00:23:28] Flash, which is pretty insane. Minimax
[00:23:30] and GLM, two really, really great
[00:23:32] models. It's a simple question of
[00:23:34] performance versus cost. It's incredible
[00:23:36] to see an open weights model this high
[00:23:39] up in the benchmarks. I don't think an
[00:23:40] open weights model has ever hit this
[00:23:42] high. This is a top five model, which is
[00:23:44] a, you know, pretty insane thing to say.
[00:23:46] If you're looking at pure intelligence,
[00:23:47] GLM 5.2 is top five. And also, pretty
[00:23:50] insane, Minimax M3 is also top five,
[00:23:53] although it's on the edge here. There
[00:23:55] are other models that can do what
[00:23:56] Minimax can do. For instance, DeepSeek
[00:23:58] V4 Pro is a great example. As mentioned,
[00:24:00] GLM 5.2 is also very fast, but most of
[00:24:03] those tokens are going to be reasoning
[00:24:05] tokens. So, it's not going to really
[00:24:06] feel fast unless you're staring at the
[00:24:08] thinking trace. And as a side effect of
[00:24:11] that, the GLM 5.2 price is actually
[00:24:13] going to be a little higher than you
[00:24:14] want it to be. Although, it's going to
[00:24:15] be a decent amount cheaper than your top
[00:24:19] end models, of course, like the GPTs and
[00:24:21] the Fable fives. I'm personally a really
[00:24:24] huge fan of Minimax 3. I've been
[00:24:26] enjoying using this model and really
[00:24:28] dialing in the system prompt of agents
[00:24:30] running this model so that it runs in
[00:24:32] exact straight lines at really, really,
[00:24:35] really cheap prices. This is a
[00:24:36] capability that I think is super
[00:24:38] underrated right now. If you really
[00:24:40] specialize your model, uh if you build
[00:24:42] agent experts as we talk about and
[00:24:44] discuss in Agent Horizon, your model can
[00:24:47] really, really bump up in capability,
[00:24:49] but that's if you're being specific and
[00:24:51] if you know the exact repeat task that
[00:24:53] you want your Minimax, your Flashes, and
[00:24:55] your Kimmys to execute. And really all
[00:24:58] of your workhorse models. If you can
[00:24:59] really guide and steer your workhorse
[00:25:01] models, you can drop down your price
[00:25:03] even further. That's where great agentic
[00:25:06] engineering comes into play. So, this is
[00:25:08] my model stack. This is how I'm thinking
[00:25:09] about great open weight models like GLM
[00:25:12] 5.2 and Minimax M3. If you got value out
[00:25:15] of this video, if the model stack
[00:25:17] framing helps you engineer, drop a like,
[00:25:20] subscribe, join the journey. We're on a
[00:25:21] mission to build software that works
[00:25:24] while we sleep. Comment down below. Let
[00:25:25] me know what your model stack is if you
[00:25:27] have one. And if you don't, comment down
[00:25:29] below and let me know what you think
[00:25:31] your model stack is going to be.
[00:25:32] Building your model stack is going to be
[00:25:34] more important every single day as we
[00:25:36] use these powerful fable mythos class
[00:25:38] level models to orchestrate other work
[00:25:40] and as we build out individual agents
[00:25:43] running inside of products for our
[00:25:45] users. We're in the age of agents. So,
[00:25:48] knowing the best tools, models,
[00:25:50] contexts, and prompts to equip your
[00:25:52] agents with is the name of the game. And
[00:25:55] when you have optionality and resiliency
[00:25:57] built into your model stack, when one of
[00:25:59] these models go down, you will be the
[00:26:01] engineer unaffected continuing to win,
[00:26:04] continuing to ship as everyone moves
[00:26:06] more and more into the vibes of all
[00:26:08] these models. Let's stay focused on
[00:26:10] great engineering patterns and
[00:26:11] principles. You know where to find me
[00:26:13] every single Monday. Stay focused and
[00:26:16] keep building.
