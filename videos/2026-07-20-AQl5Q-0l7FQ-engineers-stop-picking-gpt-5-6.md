---
video_id: AQl5Q-0l7FQ
title: Engineers... STOP Picking GPT-5.6 Sol OR Claude Fable 5… FUSE THEM
channel: IndyDevDan
url: "https://www.youtube.com/watch?v=AQl5Q-0l7FQ"
watched_date: 2026-07-20
watched_at: "2026-07-20T12:00:00Z"
watch_count: 1
duration_seconds: 1582
source: youtube-history-browser
added_date: 
history_label: Jul 20
history_order: 149
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 158
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video argues against choosing a single AI model (GPT-5.6 Soul or Claude Fable 5) and instead advocates for "model fusion"—running multiple state-of-the-art models in parallel as coordinated agent teams. The creator demonstrates three commands: /opinion (get independent perspectives from multiple models), /fusion (combine results to identify consensus and divergence), and /auto-validate (have one model write validation gates before another builds the solution). Real examples include comparing scikit-learn algorithms across two models and solving SQLite bulk inserts, where the fused approach identified a 1000x speedup strategy by combining insights from both Claude Fable 5 and GPT-5.6 Soul that neither model alone proposed.

To apply this immediately: stop relying on single AI tools or model providers. For your next complex engineering task, query two or three state-of-the-art models in parallel to gather competing approaches, then explicitly fuse their outputs to extract the strongest ideas from each. Build validation logic before building solutions (have one model write the test/gate, then another implement it). Most critically, customize your agent harness and system prompts for your specific problems—generic out-of-box tools constrain what you believe is possible, while specialized harnesses unlock 10-100x better results by orchestrating agents as tight teams rather than lone actors.

## Transcript

[00:00:00] The AI industry wants one big winner.
[00:00:03] GPT 5.6 Soul or Claude Fable 5. I'm not
[00:00:07] picking one. Picking is the mistake. The
[00:00:09] winning mindset in the age of AI is and
[00:00:12] not or. Combine compute. Don't select
[00:00:15] compute. Don't get me wrong, I maintain
[00:00:17] a model stack to track the best models.
[00:00:20] But when it comes to pushing the
[00:00:21] frontier and getting real engineering
[00:00:23] work done, you want teams of agents
[00:00:25] working for you, not an unchecked lone
[00:00:28] wolf. There's a simple yet powerful
[00:00:30] pattern for this [music] that's existed
[00:00:31] for years. Yesterday it was called
[00:00:33] architect editor, prompt chaining, then
[00:00:36] agent chaining. Today Devon open router
[00:00:39] and [music] others call it model fusion.
[00:00:41] Tomorrow, no matter what it's called
[00:00:43] after you watch this video, it'll
[00:00:44] [music] be another tool in your agentic
[00:00:46] engineering toolbox. I've been running
[00:00:48] this pattern for years across hundreds
[00:00:50] and thousands of agents. You probably
[00:00:51] have too without naming it. If you use
[00:00:53] Model [music] Fusion properly, you're
[00:00:55] combining the intelligence and the
[00:00:57] context windows of your models. [music]
[00:00:59] So, how do we tap into Model Fusion for
[00:01:02] our agentic engineering work? Once
[00:01:04] again, we don't vibe code. Instead, we
[00:01:06] harness engineer with the PI coding
[00:01:08] agent to build a powerful fusion [music]
[00:01:11] harness.
[00:01:17] There are three commands we'll use to
[00:01:19] orchestrate our tight coordinated two
[00:01:21] agent team. Opinion to get multiple
[00:01:24] perspectives from our agents. Fusion to
[00:01:26] combine and consolidate the best results
[00:01:29] of our agents and auto validate to use
[00:01:31] intelligent on the-fly validation to
[00:01:34] improve on the second constraint of
[00:01:36] agentic engineering review. We're going
[00:01:38] to start with a couple of powerful
[00:01:40] workhorse models cloud sonic 5, GPT 5.6
[00:01:42] 6 Terra and then we'll move up to the
[00:01:44] state-ofthe-art models. Let's start
[00:01:46] simple and move to the most valuable/
[00:01:53] opinion lists the top three scikitlearn
[00:01:56] models, use cases, pros and cons. So
[00:01:58] when we fire this off, you're going to
[00:02:00] see exactly what you would expect from a
[00:02:02] fusion harness. We have two agents
[00:02:04] working for us in parallel. This is two
[00:02:06] unique perspectives that we wouldn't get
[00:02:08] out of the box with any other agentic
[00:02:10] coding tool. So if we scroll up here,
[00:02:11] you can see exactly what happened. And
[00:02:13] in fact, this tool is already giving us
[00:02:16] insight into how these models perform
[00:02:18] side by side. Terra blew through this
[00:02:20] problem in just 4.5 seconds. 9K tokens
[00:02:23] in, 300 out, 3 cents. Cloudset 5 took
[00:02:26] double the time. 4K more tokens in, 4K
[00:02:28] more tokens out, and it costs about a
[00:02:30] cent more. We're nitpicking this small
[00:02:33] prompt, but the key is that you can see
[00:02:34] your agents side by side. Relativity is
[00:02:37] the best benchmark. You can see we have
[00:02:39] a nice breakdown here of the top
[00:02:41] scikitlearn models. Random forest should
[00:02:44] be the top answer and then they both
[00:02:46] list a couple other ones. So let's go
[00:02:48] ahead and combine the results into one.
[00:02:55] One agent response is fine. Two agent
[00:02:57] responses is good. Combining the
[00:03:00] perspectives of two models is even
[00:03:01] better. Let's do that now with /fusion
[00:03:04] as table.md in your current working
[00:03:07] directory. So once again, we're going to
[00:03:08] use two models to do this work. They're
[00:03:11] both going to execute on this, write
[00:03:13] their table so that we have a concrete
[00:03:15] result. But then something different
[00:03:17] happens here. After the models do their
[00:03:18] work, a new fusion agent using the same
[00:03:21] model as our architect is going to pick
[00:03:23] up this work and combine the responses.
[00:03:26] So this is the fusion prompt applied
[00:03:28] directly to agents in a dedicated agent
[00:03:31] harness. Now we get to see where the
[00:03:33] models agreed, what's the consensus,
[00:03:35] what's the divergence and what was
[00:03:37] discarded. This information is ultra
[00:03:40] ultra valuable. Okay. So let's just
[00:03:41] understand the results. What are the
[00:03:42] best scikitlearn models according to
[00:03:44] sonnet 5 and gpt 5.6 terra both agents
[00:03:48] completely agreed here. This is great
[00:03:49] random forest grade in boost logistic
[00:03:51] regression. And you can see their
[00:03:53] explanation of why. As engineers when
[00:03:55] you're making decisions you want to
[00:03:56] understand when to use technology and
[00:03:58] you want to understand the pros and the
[00:04:00] cons. Engineering is all about
[00:04:02] trade-offs. Agents don't change that. At
[00:04:04] the end of the day, you have to collapse
[00:04:05] your work into a decision. And if you
[00:04:07] want to make the best decisions, you
[00:04:09] want the best compute available, giving
[00:04:11] you their perspective, giving you their
[00:04:12] input, giving you raw informations you
[00:04:14] can use to build valuable software. You
[00:04:17] can see we have a consensus. They both
[00:04:18] all agreed on all these. We had a small
[00:04:20] divergence. Both answers were
[00:04:22] complimentary, not contradictory. So,
[00:04:24] this is good. Our fusion model kept both
[00:04:26] and there was nothing discarded. You can
[00:04:28] imagine how powerful this can be when
[00:04:30] you're making game time critical
[00:04:32] strategic decisions for your engineering
[00:04:33] work, but also for your business. Once
[00:04:35] again, we're scaling our compute to
[00:04:37] scale our impact. Now, let's use the
[00:04:38] most powerful custom slash command we've
[00:04:40] [music] built into our fusion
[00:04:42] harness/auto
[00:04:47] validate. implement an MVP of these
[00:04:50] models with the smallest possible data
[00:04:53] set to showcase their respective pros,
[00:04:55] cons, and pros, consy, same dur. So,
[00:04:59] super simple example we're working
[00:05:00] through here just to showcase the power
[00:05:03] of this fusion harness. What's happening
[00:05:05] here? This is a unique agentic workflow
[00:05:07] and it's built into the fabric of the
[00:05:09] agent harness. When I type /a
[00:05:10] valvalidate, a workflow inside the
[00:05:12] harness kicks off that does this. You
[00:05:14] can see here the builder is just
[00:05:16] waiting. GBT 5.6 6 Terra is doing
[00:05:18] nothing. What is it waiting for? It's
[00:05:20] waiting for the validator to create a
[00:05:22] validation gate. Cloud Sonnet 5 is
[00:05:24] building out a validation gate right now
[00:05:26] that proves that the work is done. With
[00:05:29] this fusion harness with powerful
[00:05:31] workhorse and especially
[00:05:32] state-of-the-art models, we can do
[00:05:34] something really incredible. Any prompt
[00:05:35] we write can have a validation flow
[00:05:38] written before the work is even started.
[00:05:40] The validator is done now. It's written
[00:05:42] a raw validation script that proves that
[00:05:45] the work is done. It also has fail
[00:05:47] commands to give feedback to our
[00:05:49] builder. Our builder has very very
[00:05:50] quickly built this out and really
[00:05:52] impressed with the speed of the GPT 5.6
[00:05:54] Terra and Luna models. Now what's going
[00:05:56] to happen is really really cool. So the
[00:05:57] validator immediately executed the
[00:05:59] validation script. And you can see there
[00:06:01] was no file created at all. And so the
[00:06:03] validation failed, right? It was just
[00:06:04] running this as its initial check. But
[00:06:06] now this validation script is going to
[00:06:08] run against the work from the builder.
[00:06:11] So check this out. See if we got any
[00:06:12] fails here. Pass pass. All passes, no
[00:06:16] fails. Big shout out to 5.6 Terror.
[00:06:18] Really powerful workhorse model. Kind of
[00:06:20] sitting right next to Cloud Signet 5. I
[00:06:22] think it's actually outperforming it by
[00:06:24] a bit, especially when you take into
[00:06:26] account the speed in which it gets work
[00:06:28] done and the concision in which it does
[00:06:30] it. This is all good. We can scroll back
[00:06:31] up to the validation script that Sonnet
[00:06:33] 5 put out for us. Like look at all the
[00:06:35] validations. Every one of these fail
[00:06:36] statements is feedback for our builder
[00:06:39] agent if something goes wrong. So you
[00:06:40] can see it's running reg x. It's making
[00:06:42] sure that these models exist, right?
[00:06:44] Random force, gradient boost, logistical
[00:06:46] regression. It's making sure that
[00:06:47] everything is expected so that the
[00:06:49] script actually works. And you know,
[00:06:51] yes, these models can do more. They can
[00:06:54] validate their own work. And you see
[00:06:55] this when you run some of these
[00:06:56] state-of-the-art models. They
[00:06:57] automatically validate their work. They
[00:06:59] run scripts, they compile, they run
[00:07:01] llinters, they run tests, so on and so
[00:07:02] forth. This is no different. We're just
[00:07:04] putting the validation before the
[00:07:06] execution. We're saying how can we know
[00:07:08] for a fact this piece of code this unit
[00:07:11] of work is done and we build that as a
[00:07:13] script before anything runs. So this is
[00:07:15] us fighting against the second
[00:07:17] constraint of agentic coding. There's
[00:07:19] two constraints of agentic engineering.
[00:07:21] There's planning and reviewing the
[00:07:22] fusion harness with /autov valalidate
[00:07:24] lets us push past the current review
[00:07:26] constraint. Last week we broke down loop
[00:07:28] engineering and we focused on much more
[00:07:30] valuable concepts software developer
[00:07:32] life cycle ADWs and software factories.
[00:07:35] If you haven't checked that video out,
[00:07:36] definitely do that after you finish
[00:07:37] watching this one. That one went viral
[00:07:39] for a good reason. What we're doing here
[00:07:41] with the fusion harness is we're
[00:07:43] building on a single agent node. So the
[00:07:46] entire harness would be a single agent
[00:07:49] step. Literally once again scaling our
[00:07:51] compute to scale their impact. Instead
[00:07:53] of an individual agent running, we have
[00:07:54] a tight team of agents validating their
[00:07:57] work with each other, creating
[00:07:58] validation scripts before anything runs.
[00:08:00] As you can imagine, if this fails, the
[00:08:02] validator is going to loop back into the
[00:08:04] builder and say, "Hey, you messed this
[00:08:05] up. Correct it." We're adding agents
[00:08:07] into individual agent nodes to make up
[00:08:09] three value creators in the age of
[00:08:12] agents. It's engineers, its agents, and
[00:08:14] it's raw code. Again, check out last
[00:08:16] week's video to really understand the
[00:08:18] shift away from loop engineering because
[00:08:20] loop engineering is not encompassing
[00:08:21] enough. It's a terrible rebrand of the
[00:08:23] software developer life cycle. I hope
[00:08:26] you can see why owning your agent
[00:08:28] harness is so important. Let me just
[00:08:30] like say this very loudly and clearly
[00:08:32] again. Your tools directly limit what
[00:08:34] you believe is possible. When you use
[00:08:36] tools like the PI coding agent that are
[00:08:38] customizable and extensible by design,
[00:08:41] these mental false limits just fall away
[00:08:44] very quickly. You're not waiting for
[00:08:45] someone to deliver an update on some
[00:08:47] feature that's blocking you. Hint hint,
[00:08:49] cloud code, codeex, open code, so on and
[00:08:51] so forth. I mean this all the way down
[00:08:53] to like the fabric of the py coding
[00:08:55] agent. It's meant to be customized. This
[00:08:58] is the true value proposition of the PI
[00:09:00] coding agent and software that adapts to
[00:09:02] your will. There's a big ongoing debate,
[00:09:04] ongoing concern that we're all prompting
[00:09:07] all of our language models, all of our
[00:09:09] agents and we're giving away our
[00:09:11] company's data to these big AI labs,
[00:09:13] anthropic, open AI, Gemini, so on and so
[00:09:16] forth. This discussion of sovereign AI
[00:09:18] is going to become more and more
[00:09:19] important. We need to own our AI. We
[00:09:20] need to have local compute where we can
[00:09:22] run our language models knowing that our
[00:09:24] traces are ours. The most valuable piece
[00:09:27] of our work, the intelligence we're
[00:09:29] deploying, all the work we're putting
[00:09:30] into embedding our IP into agents is
[00:09:34] getting gobbled up by these AI labs. You
[00:09:36] know, make sure you like and subscribe
[00:09:37] cuz next week I'm going to address the
[00:09:39] question head on. Is anthropic and open
[00:09:41] AI stealing our data while we pay for
[00:09:44] it. That's an aside, a really important
[00:09:46] aside that I've been thinking about more
[00:09:47] and more and I want you to be very, very
[00:09:49] aware of as you and I engineer in the
[00:09:51] age of agents. Owning your agent harness
[00:09:53] is ultra important. Now that you
[00:09:55] understand this, now we're going to
[00:09:56] really scale this to the max. Okay, so
[00:09:58] let's throw a a harder, more realistic
[00:10:00] problem [music] at our fusion harness.
[00:10:07] Okay, so we're going to reset and now
[00:10:08] we're going to run FHS fusion harness
[00:10:11] state-of-the-art models. So let's
[00:10:13] imagine a concrete problem. I have an
[00:10:15] SQLite database inside of one of my
[00:10:17] users devices among thousands of users.
[00:10:20] SQLite is fantastic. There are over a
[00:10:23] trillion SQLite databases around the
[00:10:25] world. Knowing when to use SQLite versus
[00:10:27] Postgress versus some NoSQL solution can
[00:10:30] save you loads and loads of trouble. I
[00:10:32] need to insert over a million rows into
[00:10:34] an SQLite database across all my users.
[00:10:37] Am I going to sit down and just prompt
[00:10:39] this solution into a single agent?
[00:10:40] Insert all 1 million rows into this user
[00:10:43] into that user. Sure, we could. In this
[00:10:45] scenario, we absolutely could. But I'm
[00:10:46] thinking ahead. I know I'm going to have
[00:10:48] to solve this problem again and again
[00:10:49] and again for my business. And I don't
[00:10:51] want a one-off vibecoded solution. I
[00:10:53] want to solve every scenario in a fast
[00:10:56] memory efficient way. So what we're
[00:10:58] going to do here is use the fusion
[00:10:59] harness to solve this problem. I want
[00:11:01] the best state-of-the-art models near
[00:11:03] their maximum capability. We're using X
[00:11:05] high here on Clawed Fable 5 and X high
[00:11:08] on GPT 5.6 Soul. Okay. So we have an
[00:11:10] architect and a builder. And I want to
[00:11:12] know what is the best way to insert a
[00:11:15] million rows in a fast memory efficient
[00:11:17] way. So, of course, same flow / opinion.
[00:11:20] We'll paste in this prompt and fire it.
[00:11:22] Feel free to pause to read the exact
[00:11:24] prompt. We're just going to fire this
[00:11:25] off. And now we have two
[00:11:27] state-of-the-art models thinking through
[00:11:29] this problem. I want the opinions of the
[00:11:31] best compute available. As you can see
[00:11:33] here, I am paying for this directly
[00:11:35] through the PI coding agent. Both her
[00:11:37] agents are going to run here and put
[00:11:39] together a comprehensive answer for us.
[00:11:41] This is a slash opinion from two of the
[00:11:43] best models in the world right now. By
[00:11:45] the time you're watching this, you might
[00:11:46] have the new Gemini model. I actually
[00:11:47] don't think that model is going to be
[00:11:49] able to compete with Soul or Fable 5.
[00:11:51] We'll see in the stats. We'll see in the
[00:11:52] benchmarks. Regardless, it's going to be
[00:11:53] more compute available to you and I to
[00:11:55] build with and to combine our compute
[00:11:58] against. We don't need single individual
[00:12:00] winners. As you can see with the way
[00:12:02] things are really working out in the AI
[00:12:04] industry, there going to be many models.
[00:12:06] There going to be many players. And
[00:12:07] picking one is a mistake. Picking one
[00:12:09] model, picking one model provider,
[00:12:11] picking one agentic coding tool is a
[00:12:13] mistake. Here's a crazy stat. I'm
[00:12:14] building a new Asian harness nearly
[00:12:17] every single day. The Fusion harness is
[00:12:19] just one in a long line of custom agent
[00:12:21] harnesses I built out to solve specific
[00:12:24] problems to outperform any other out-
[00:12:26] of-the-box agent coding tool. Something
[00:12:28] to really think about if you're doing
[00:12:29] real production work when you're
[00:12:31] thinking about putting together your AI
[00:12:32] developer workflows that contain
[00:12:34] engineers code plus agents and your
[00:12:36] individual agent nodes. You can put any
[00:12:39] agent harness you need to or want to to
[00:12:41] get extraordinary results. Cloud Fable 5
[00:12:44] done. Took about 90 seconds. Soul
[00:12:46] continuing to work. It looks like it's
[00:12:47] actually running some tests. It's
[00:12:49] actually kind of answering this question
[00:12:51] for us [laughter] before we even get to
[00:12:54] it. Fusion, of course, as you know, is
[00:12:55] coming next. A good workflow I like to
[00:12:57] use with the Fusion harness is, as
[00:12:59] you've seen, ask for an opinion, fuse
[00:13:01] the results of both opinion, and then
[00:13:02] you run the auto validate kind of build
[00:13:05] against it. Again, last week's video was
[00:13:06] so important for many reasons, but as
[00:13:08] you can see here, we're building out
[00:13:10] micro software developer life cycles,
[00:13:12] micro SDLC's. We're doing that inside of
[00:13:15] this harness. You can think of / opinion
[00:13:17] as like scout. You can think of /fusion
[00:13:19] as our unofficial planning step. And
[00:13:21] then, of course, autov validate is a
[00:13:22] twoin one. We're testing and we're
[00:13:24] building. Really curious to see how
[00:13:26] valuable its answer is in comparison to
[00:13:29] Fable. You can see it's already used 3x
[00:13:30] the tokens to generate this result. It's
[00:13:33] thinking a lot. We are in X high mode,
[00:13:35] so it's to be expected. But regardless,
[00:13:37] we're going to get the value of both
[00:13:39] models. There are engineers using fusion
[00:13:41] harnesses like this, using multiple
[00:13:43] models, getting multiple perspectives,
[00:13:44] and they're making better decisions. Let
[00:13:46] me be super clear about that. Engineers
[00:13:48] that can scale their compute to scale
[00:13:50] their impact in a functional, useful
[00:13:52] way, are making better decisions. This
[00:13:54] ties really closely into the CEO agent
[00:13:58] harness we built on the channel a couple
[00:13:59] months back. Again, a custom agent
[00:14:01] harness. We're customizing our
[00:14:03] experience to get specialized results.
[00:14:05] What is alpha? What is asymmetry? It's
[00:14:07] specialization. It's doing what others
[00:14:10] aren't yet. And so there we go. We
[00:14:11] finally got that response. We got some
[00:14:13] really, really insane speed ups from
[00:14:15] both model. Fable got its top speed up
[00:14:17] at uh 300x, but check this out. GPT 5.6
[00:14:21] Soul found a 250 to 10,000X and another
[00:14:25] 400 to 2KX. Let's see if these models
[00:14:28] are bullshitting or if there's some true
[00:14:30] validity to what they're saying. These
[00:14:31] models are just thinking. They're
[00:14:33] reporting back in their own separate
[00:14:34] thought chains. Let's fuse the compute.
[00:14:36] Let's combine the context windows. Let's
[00:14:38] combine the intelligence. Okay, so
[00:14:39] fusion. And I'm going to paste this in
[00:14:41] here. This is going to be a longer one,
[00:14:43] but the idea here is that I'm having the
[00:14:45] models design one benchmark script that
[00:14:47] settles the bulk insert question for
[00:14:49] good, right? On two axes, speed and RAM.
[00:14:52] I'm kind of defining some parameters for
[00:14:54] them. This is an Astral UV single file
[00:14:56] script. Standard library only 1 million
[00:14:58] rows, identical schema generation, blah
[00:15:00] blah blah blah blah, right? Measure peak
[00:15:01] RAM. You get the idea. Pause the video
[00:15:03] here if you want to know the exact
[00:15:04] details. But here we go. They're off to
[00:15:06] the races. State-of-the-art models, the
[00:15:08] best compute money can get you, the best
[00:15:09] decision-making money can get you, the
[00:15:11] best engineering money can get you,
[00:15:13] minus actual engineers. Okay, [laughter]
[00:15:16] that still holds true. But I will say as
[00:15:18] a fact, the best engineers are using
[00:15:20] these models together. The best
[00:15:22] engineers are now like symbiotes with
[00:15:25] these state-of-the-art models. They
[00:15:26] don't make a decision without building,
[00:15:28] testing, validating, ideulating,
[00:15:30] planning with state-of-the-art models.
[00:15:32] One of the highest leverage areas for
[00:15:35] engineers now for agentic engineers is
[00:15:37] decisionmaking and it's planning. And
[00:15:40] guess what these models are great at?
[00:15:42] Uh, increasingly so. Even if they don't
[00:15:44] give you the right answer, they give you
[00:15:45] a very concrete answer you can use to
[00:15:48] increase your impact, to make better
[00:15:49] decisions, to build better software, to
[00:15:51] build better solutions for your users,
[00:15:53] for your business, for your customers.
[00:15:55] And so, they're off to it. This is going
[00:15:56] to chew up lots of thinking tokens. You
[00:15:58] can see here Fable is a lot more
[00:15:59] decisive with its building, with it
[00:16:01] planning. Soul taking its sweet time in
[00:16:03] X high mode. You can see the context
[00:16:05] window differences. You can see the cost
[00:16:07] differences. Fable already what is this
[00:16:09] 10 times more expensive than soul but
[00:16:11] also table 5 is already done here with
[00:16:13] its outputs. We're going to see what our
[00:16:14] builder puts together here. So very very
[00:16:16] simple idea taken to a reasonable level.
[00:16:18] Scale your computer to scale your
[00:16:20] impact. Great. I've said it a million
[00:16:21] times how you can use multiple models at
[00:16:24] the same time to solve problems. Great.
[00:16:25] You know this. You already know about
[00:16:27] delegation. You already know about
[00:16:28] spinning up multiple terminal windows.
[00:16:30] Everyone's using git work trees
[00:16:32] different coding agents. Blah blah blah.
[00:16:33] Cmox herder t-mucks. Like that's all
[00:16:36] great. What we really want to do here is
[00:16:37] combine the intelligence to make the
[00:16:39] best possible engineering decisions.
[00:16:42] This is where we deviate. This is where
[00:16:43] we push a little further than your
[00:16:45] classic sub aent delegation. Right?
[00:16:46] We're not handing off a task. We have
[00:16:48] two agents, really tight-knit team
[00:16:50] working together. We want their
[00:16:51] opinions. We want to fuse their results
[00:16:53] and then we can run auto validate loops
[00:16:56] that generate verification and building
[00:16:59] at the same time. And as these models
[00:17:01] continue to progress and as your harness
[00:17:03] engineering, your prompt engineering,
[00:17:04] your contact engineering continue to
[00:17:06] progress, all of this comes together to
[00:17:07] create some insane engineering results.
[00:17:10] And this is once again, I just want to
[00:17:11] mention this. This is just one node in
[00:17:14] your ADWs in your AI developer
[00:17:16] workflows. Bloom engineering is the
[00:17:18] wrong interpretation. It's the wrong
[00:17:19] mental model for understanding what you
[00:17:22] should be focused on right now. It's AI
[00:17:23] developer workflows. It's your software
[00:17:25] factory. Again, check out last week's
[00:17:27] video. I'm starting to get the feeling
[00:17:28] here that uh soul is going to create an
[00:17:31] insane result here. Hopefully, it's
[00:17:33] thinking is actually generating value.
[00:17:34] Some of these models just chew up
[00:17:36] thinking tokens and generate the same or
[00:17:39] worse outputs because they're
[00:17:40] overthinking it just like you or I might
[00:17:42] overthink something, you know, analysis
[00:17:44] paralysis. But here we go. SQL bulk
[00:17:46] benchmark builder OpenAI GPT 5.6. Here
[00:17:49] we go. It's running it. Uh this is going
[00:17:50] to be awesome. Using a lot of compute
[00:17:52] here to get this result. This is why a
[00:17:54] lot of the benchmarks, a lot of the
[00:17:56] results still say Fable is in the lead.
[00:17:58] The work it does, it just needs fewer
[00:18:01] tokens to ship. The simple way to put
[00:18:03] it, it's just smarter. Like a great
[00:18:04] principal engineer, they know when they
[00:18:06] don't have to do work. Knowing when not
[00:18:08] to work is just as important, maybe even
[00:18:10] more important, than knowing when to
[00:18:12] work. It's like when a senior engineer
[00:18:14] learns that deleting code is often
[00:18:16] better than adding code or modifying
[00:18:17] code. Anyways, skip ahead a little bit
[00:18:19] for you so I don't waste your time.
[00:18:20] There we go. GBD 5.6 took Soul wrapping
[00:18:22] up its response here after 8 minutes. So
[00:18:25] we have the total run for both of our
[00:18:27] agents. You can see here Soul was
[00:18:28] actually twice as expensive as Fable,
[00:18:30] but now Fable in fusion mode is going to
[00:18:33] combine the results. Our architect is
[00:18:35] going to look at both results and put
[00:18:36] them together. So it sees both source
[00:18:38] scripts. It's going to pull them
[00:18:40] together and it's going to fuse the
[00:18:42] result. So you can see there's the
[00:18:43] response from our agents. Looks like we
[00:18:45] have max tune gen with an insane 560x
[00:18:48] speed up for inserting rows over native
[00:18:51] SQL light autocommits. This is the real
[00:18:53] power of the fusion harness. It's really
[00:18:55] in this/ command. Opinion matters. Autov
[00:18:58] validate is a very very powerful pattern
[00:19:00] I highly recommend you check out for
[00:19:01] solving problems when you want to do
[00:19:03] less reviewing and when you trust your
[00:19:04] agents, right? Specifically when you
[00:19:06] have agents that understand your system,
[00:19:08] when you've created a specialized agent,
[00:19:10] a custom agent that understands your
[00:19:11] system better than others. One of the
[00:19:13] key leverage points there is, of course,
[00:19:14] the system prompt. You have to overwrite
[00:19:16] the system prompt to really guide your
[00:19:18] agent to powerful results. But even with
[00:19:20] the defaults, you can get really
[00:19:21] powerful results out of having a
[00:19:22] state-of-the-art model auto validate
[00:19:25] another state-of-the-art model. These
[00:19:26] capabilities will continue to increase.
[00:19:28] I know it sounds a little wacky. You
[00:19:30] know, some engineers rightfully so keep
[00:19:32] pointing to the error rates when you
[00:19:33] keep stacking up these agents. I think
[00:19:35] that's fine. that that is only the case
[00:19:37] when you haven't templated your
[00:19:38] engineering into your system and when
[00:19:40] you're not really putting in the effort
[00:19:41] to create great prompt context and
[00:19:44] harness engineering into your system.
[00:19:46] These out of the box agents are
[00:19:47] fallible. It is your actual work, your
[00:19:50] agent engineering in all these domains,
[00:19:52] right? All these subdomains, prompt,
[00:19:54] context, harness engineering that really
[00:19:56] make up the true value. You can see here
[00:19:58] the fusion agent is combining these
[00:20:01] results and it's going to use the best
[00:20:02] of both worlds. Two state-of-the-art
[00:20:04] models beats one. Two state-of-the-art
[00:20:06] models where you fuse the best of both
[00:20:08] worlds beats two. An auto validation
[00:20:11] loop using both agents with all their
[00:20:13] context. One to build the validation,
[00:20:14] the other to actually build the work.
[00:20:16] They iterate on each other beats just a
[00:20:18] build test workflow. Once again, scaling
[00:20:20] compute to scale your impact. And I
[00:20:21] really want to hit on this key theme.
[00:20:23] Your agent harness is the body that
[00:20:25] transforms compute into intelligence
[00:20:28] that works for you. So, whoever owns
[00:20:30] your agent harness owns your results.
[00:20:32] And this is why, you know, week after
[00:20:33] week I keep talking about the PI agent
[00:20:35] harness. I don't care if you use a PI
[00:20:37] agent harness. Build your own PI agent
[00:20:38] harness. Build a tool that does the same
[00:20:40] thing. Doesn't matter. The key is like
[00:20:41] you want to unblock yourself from being
[00:20:43] stuck on codecs, cloud code, open code.
[00:20:45] It is the customizability and extensible
[00:20:47] design of something like the pi coding
[00:20:49] agent that truly differentiates it and
[00:20:52] truly differentiates your results. The
[00:20:54] workflows that we've looked through here
[00:20:56] are just a few, right? There are many
[00:20:58] other patterns you can build into your
[00:21:00] fusion harness. Couple ideas just to
[00:21:02] throw at you. Debate. You can build a
[00:21:03] slash debate. Pass in a number. Pass in
[00:21:05] a prompt. Pass in a total debate rounds.
[00:21:08] So n 10 times, five times, three times.
[00:21:10] Have your agents debate an idea or a
[00:21:12] concept or an architecture. You can do
[00:21:13] like / parallel. And this should just
[00:21:16] execute both of your agents at the same
[00:21:18] time versus opinion. They're just
[00:21:20] responding. Opinion doesn't have right
[00:21:21] or edit tools. There's something like uh
[00:21:23] you know a coordinate. You give your
[00:21:25] agents a task. They talk back and forth
[00:21:26] about the solution and then they
[00:21:28] actually build it. So this is all in the
[00:21:29] realm of harness engineering and in that
[00:21:32] there's prompt engineering, there's
[00:21:33] context engineering. All of it fits
[00:21:34] under the subdomain of agentic
[00:21:36] engineering, right? Building valuable
[00:21:38] software with agents, with code, and
[00:21:40] with engineers as the three units of
[00:21:42] value creation. Our agent finish here.
[00:21:44] Let's see what the fuse result looks
[00:21:46] like. What's the best strategy? So the
[00:21:48] speed winner setbased CTE. This is a
[00:21:50] combination of builder and architect
[00:21:53] solution to get an a,000x speed up. Love
[00:21:56] that. Here is our memory winner wallt
[00:21:58] tuned generation. Not going to go into
[00:22:00] too much of the details here. If you're
[00:22:01] a database nerd, uh you'll be able to
[00:22:03] look at these results. I'll make sure to
[00:22:04] save this in this codebase so you can
[00:22:06] take a look at these. But the consensus
[00:22:08] divergence, both the models
[00:22:09] independently chose subprocess per
[00:22:11] strategy isolations, one deterministic
[00:22:13] data set, a bunch of stuff. So they
[00:22:15] matched up here. They diverged here.
[00:22:17] This is really interesting. The builder
[00:22:18] solution GBD 5.6 soul was simpler and
[00:22:21] faster, but the three column schema was
[00:22:23] simpler from the architect. single run
[00:22:25] order over median of two shuffled
[00:22:28] simpler that was from the architect.
[00:22:29] Okay, so there's just a bunch of stuff
[00:22:31] here where uh one idea was pulled from
[00:22:33] the architect, one idea was pulled from
[00:22:35] the builder, one idea was pulled from
[00:22:36] the architect, they both got the same
[00:22:37] idea, so on and so forth. These
[00:22:39] divergences is what makes value. It's
[00:22:41] not the fact that you have 10 John's
[00:22:43] working on your team. It's the fact that
[00:22:45] you have a John, a Sally, Tim, you know,
[00:22:47] insert the analogy I'm trying to make,
[00:22:48] right? It's the range of perspectives
[00:22:51] and the range of ideas on your team of
[00:22:53] engineers on your team of agents that
[00:22:55] gives you the real value proposition.
[00:22:56] Okay. So this is why I say don't choose
[00:22:58] compute combine compute thinking ands
[00:23:01] not ors. And so you know the last prompt
[00:23:03] here is the of course autov validate. It
[00:23:05] looks like our agents kind of already
[00:23:07] did run this to like really build this
[00:23:08] out. I'll kick this off. This runs the
[00:23:10] exact same workflow. You know our
[00:23:12] validator agent is going to read the
[00:23:13] work. It's going to create a
[00:23:15] comprehensive gate file that our builder
[00:23:18] must run when it finishes. Again, this
[00:23:20] is built into the fabric of the fusion
[00:23:22] harness. Because we own the Asian
[00:23:23] harness, we can make it so that the
[00:23:24] builder cannot edit the gate file. And
[00:23:26] then if something goes wrong, it'll loop
[00:23:28] and our agents will coordinate together.
[00:23:30] This is a team. This is not subent
[00:23:32] delegation. We have agents working
[00:23:33] together to deliver you better results.
[00:23:36] So, I'm going to leave this PI coding
[00:23:38] agent fusion harness linked in the
[00:23:40] description if you're interested in how
[00:23:41] to combine models to outperform either.
[00:23:44] Just like agents plus code beats agents
[00:23:46] alone and agents plus code beats code
[00:23:49] alone, multiple agents that fuse their
[00:23:51] intelligence beats the agents
[00:23:53] standalone. The industry is coming
[00:23:55] around to this idea once again. We're
[00:23:57] renaming it. I don't care about the
[00:23:58] name. I don't care who's writing a blog
[00:24:00] post about it. I want you to have these
[00:24:01] ideas so that you can scale your
[00:24:03] compute, to scale your impact, so that
[00:24:04] you can win in the age of agents. This
[00:24:07] is another multi-agent orchestration
[00:24:08] pattern and it's another node inside of
[00:24:11] your ADWs or AI developer workflows. For
[00:24:14] those that watched last week's video
[00:24:15] that went pretty viral for a deep tech
[00:24:17] channel like this, we dismantleed loop
[00:24:19] engineering and discussed what we should
[00:24:20] really be focusing our agentic
[00:24:22] engineering on. And the key topics there
[00:24:24] is the software developer life cycle,
[00:24:26] ADWs, and software factories. Check out
[00:24:30] that video if you haven't because the
[00:24:31] fusion harness fits perfectly inside of
[00:24:34] a single agent node and it's all making
[00:24:36] up what's possible. It's one piece of
[00:24:38] the puzzle of the frontier of Agentic.
[00:24:41] I'm going to keep pushing this harness
[00:24:42] forward as I have several of my other
[00:24:44] custom agent harnesses because the value
[00:24:46] proposition is there. We've talked about
[00:24:47] the verifier agent harness. We've talked
[00:24:49] about the CEO agent harness, multi-team
[00:24:51] agent harnesses. The frontier is right
[00:24:54] in front of us and we're just getting
[00:24:55] started. Next week I'm going to dive
[00:24:57] into a very very important spicy topic
[00:24:59] is really critical for you and I as
[00:25:01] engineers building companies building
[00:25:03] software building IP that we want to
[00:25:05] defend. We're going to ask and answer
[00:25:07] the question as long as nothing else you
[00:25:08] know more important comes up. This
[00:25:10] landscape is so crazy. I want to dial
[00:25:11] into this question is anthropic and open
[00:25:14] AI stealing our data while we pay for
[00:25:17] it. Stealing our IP, our valuable
[00:25:19] prompts, our valuable business
[00:25:21] workflows, are they stealing it while we
[00:25:23] pay them for it? Of course, this leads
[00:25:24] directly into the conversation about
[00:25:26] Chinese models, about US openweight
[00:25:28] models, so on and so forth. That's the
[00:25:30] topic for next week. If you made it this
[00:25:31] far into the video, huge thanks to you.
[00:25:33] Make sure you like, make sure you
[00:25:34] subscribe, all that good stuff. Make
[00:25:35] sure you comment, let the algorithm know
[00:25:37] you're interested in true agentic
[00:25:39] engineering on this channel. We don't
[00:25:41] just clickbait the news. We think, plan,
[00:25:43] and build to progress our engineering in
[00:25:45] the age of agents. Our Fable 5 validator
[00:25:48] just finished this [music] nice massive
[00:25:50] validation script so that once it runs,
[00:25:52] we know for a fact the code is going to
[00:25:55] work. There is the initial pass fail
[00:25:57] [music] and now our builder is getting
[00:25:59] to work actually creating the script.
[00:26:01] I'm not going to hold you here for this.
[00:26:02] I'll make sure to add the result into
[00:26:04] the codebase. Again, link in the
[00:26:05] description for you. We have a lot of
[00:26:07] really important concepts to discuss on
[00:26:09] the channel coming up. So, be sure to
[00:26:10] like, subscribe, comment, all that good
[00:26:12] stuff so the algorithm doesn't miss you.
[00:26:14] You know where to find me every single
[00:26:16] Monday. Stay focused and keep building.
