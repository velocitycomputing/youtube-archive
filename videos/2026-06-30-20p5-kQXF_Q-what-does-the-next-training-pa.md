---
video_id: 20p5-kQXF_Q
title: What does the next training paradigm look like?
channel: Dwarkesh Patel
url: "https://www.youtube.com/watch?v=20p5-kQXF_Q"
watched_date: 2026-06-30
watched_at: "2026-06-30T12:00:00Z"
watch_count: 1
duration_seconds: 1193
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 20
watched_at_precision: date-from-history-label
watched_percent: 13
estimated_watched_seconds: 155
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video discusses the dominant research bet that scaling RL training across millions of verifiable tasks in diverse environments will achieve AGI, while highlighting a critical limitation: domains requiring real-world interaction (business-building, politics, legal cases) can't be trained via traditional RL because they lack replayable, deterministic environments—explaining why computer use has progressed slower than math or coding. To bridge this gap, two emerging approaches are being researched: on-policy self-distillation (OPSD), which distills what a deployed model learns during a single session back into its base weights by training it to match the behaviors of a contextually-enriched teacher model; and "dreaming," where AI constructs internal simulations to practice skills repeatedly without real-world constraints, similar to how AlphaZero played millions of simulated games internally.

The actionable takeaway is that AI capability improvements will shift from pre-deployment training to post-deployment continual learning by 2027-2028. Instead of waiting for new model releases, deployed AI systems will work alongside you for extended periods (full weeks in context), then distill learned knowledge into their base weights, allowing them to develop skills beyond their original training distribution. This means: expect your AI tools to improve through actual use and each interaction; AI will handle increasingly ambiguous, real-world tasks rather than just repeating training behaviors; and improvements will compound across all users as models learn from collective deployment experience. The technical bottleneck is now architectural innovation and loss functions for safe continual learning, not raw compute scaling.

## Transcript

[00:00:00] So here's a big research bet that all the labs are making.
[00:00:02] They think that if we train AIs to accomplish millions of verifiable
[00:00:06] tasks across thousands of diverse RL environments, then we will have
[00:00:11] basically built AGI, because this kind of training will have created a kind of
[00:00:16] problem-solving agent: the kind of thing that can make progress on open-ended
[00:00:20] tasks for weeks on end in the face of errors and mistakes and ambiguity.
[00:00:25] And the people who are optimistic about this vision will say that all
[00:00:27] these things we talk about as the fundamental deficits in the current
[00:00:31] training paradigm — for example, the data inefficiency of these models,
[00:00:35] or the fact that they lack continual learning — can just be steamrolled if we
[00:00:39] scale training more, in the same way that all the fundamental research problems
[00:00:43] in natural language processing collapsed when we threw enough compute into LLMs.
[00:00:48] So in the previous essay, I talked about how these models are one
[00:00:52] one-millionth as sample-efficient as humans, and the people who are in favor
[00:00:56] of the current training paradigm will say, "Look, that might be true, but
[00:00:59] this is only true during training."
[00:01:01] Training is this one-time cost that is amortized across billions of
[00:01:05] sessions that a model will experience.
[00:01:08] What really matters is how smart and general and sample-efficient
[00:01:11] the model is during a session, and this has clearly been improving as
[00:01:15] we've been doing more RL training.
[00:01:17] AI agents are able to solve more and more ambitious problems over
[00:01:20] longer and longer time spans.
[00:01:21] Anybody who has used these models for coding knows that.
[00:01:24] Similarly, people would say, look, continual learning — this capability
[00:01:27] I keep harping about, where the model's weights get updated based on
[00:01:31] what it's learning from deployment — may simply not be necessary.
[00:01:35] Because if in-context learning gets so good across longer and longer
[00:01:40] time horizons, then you don't need to distill everything the model is learning
[00:01:44] on the job back into the weights.
[00:01:46] People often say that their employees are not net productive
[00:01:49] until six months or more on the job.
[00:01:52] So clearly, online learning is necessary for competence.
[00:01:56] But what if you could just fit those six months into the context window?
[00:01:58] There have been tons of architectural innovations that dramatically increase
[00:02:01] the amount of information, or the amount of context, that a transformer can store.
[00:02:06] And why not think that, with a couple more years of progress,
[00:02:08] we might have what feels like infinitely large context windows?
[00:02:12] Okay, so before we discuss this research bet a bit further, I want to step
[00:02:15] back and ask a completely tangential question, which I find actually
[00:02:19] very interesting and confusing about the nature of current AI progress.
[00:02:24] Why has progress on computer use been so much slower than other domains?
[00:02:30] Computer use is so clearly verifiable.
[00:02:34] You could ask a question like: did the desired Etsy item I ordered get delivered?
[00:02:38] Is the venue for an event I'm trying to organize booked?
[00:02:41] Have my taxes been submitted?
[00:02:43] So isn't it weird that computer use has been making so much slower
[00:02:46] progress than coding and math and these other verifiable domains?
[00:02:49] I'm sure there are many reasons for this, and one of them, of course,
[00:02:52] is the fact that the models are exposed to far less high-quality
[00:02:56] multimodal data during pretraining.
[00:02:59] But one reason that I think is actually quite underrated by people, and which I
[00:03:03] think reveals the canyon walls against which this river of AI progress will
[00:03:07] only slowly chip away, is that it is not enough for a domain to be verifiable.
[00:03:12] It also has to be very grindable, in the sense that you have to be able
[00:03:16] to run lots of parallel rollouts against a deterministic and replayable
[00:03:20] simulator, and you have to run those rollouts from the same starting point.
[00:03:24] If you're trying to make a model better at coding, you can define some
[00:03:27] container that has a software repo with some missing feature that you
[00:03:30] have tasked the AIs with creating.
[00:03:32] And then you have a thousand parallel agents go at the problem, each of which
[00:03:36] has an identical copy of the container.
[00:03:38] But this doesn't work with computer use, at least not trivially.
[00:03:41] You can't just have a thousand agents go try the same checkout flow
[00:03:43] on Amazon to get better at using websites, because Andy Jassy will
[00:03:48] find your bots and shut your ass down.
[00:03:51] You can solve this by making clones of Slack and Gmail and all the other
[00:03:54] common applications and websites.
[00:03:56] But at least currently, this is a very labor-intensive and unscalable
[00:03:59] way to build environments.
[00:04:01] Of course, once AIs get good enough at coding themselves to build these
[00:04:04] clones with extremely high fidelity, then I'm sure computer use will make
[00:04:08] quicker progress than it is right now.
[00:04:10] And you're also killing two birds with one stone with this kind of procedure,
[00:04:13] because getting AIs to rebuild whole applications from scratch is also
[00:04:18] a great RL objective for coding.
[00:04:20] So while computer use itself may soon be solved, its current lethargy
[00:04:23] is telling us the following: that unless you can build a very replayable
[00:04:27] training target for a domain, the models will struggle to make much progress.
[00:04:32] And the reason this is true, of course, is that the models are incredibly
[00:04:35] sample-inefficient during training.
[00:04:37] This is the point I was making in my last video essay.
[00:04:39] So for computer use, we might be able to make up for the sample-efficiency
[00:04:42] deficit by building these farmable deterministic simulators.
[00:04:46] But for so many other different kinds of skills that we need AIs
[00:04:49] to have, we simply can't do this.
[00:04:52] How do we train an AI to get really good at building a business from scratch?
[00:04:55] How about winning court cases, or having a profitable day of trading in the markets,
[00:04:59] or helping a candidate win an election?
[00:05:02] The rollout here requires interacting with the real world, and you can't
[00:05:05] recreate it from just within a datacenter.
[00:05:08] The outer-loop verification here may take months or even years of
[00:05:12] real-world actions to elicit, and you can't re-observe it by perturbing the
[00:05:16] model's actions slightly in thousands of parallel rollouts to isolate exactly
[00:05:22] what the model did that actually worked.
[00:05:24] Now, dealing with such reset-free, non-stationary environments
[00:05:27] is a known open problem in RL.
[00:05:29] I'm not pointing out anything new.
[00:05:31] But I really do want to emphasize that because of the idiosyncratic
[00:05:33] and sparse nature of data in most domains in the world, you need sample
[00:05:38] efficiency in order to get proficient.
[00:05:41] If AIs are to develop all the skills that humans have, and even skills
[00:05:45] that humans don't have, then they need to be able to learn from information
[00:05:49] revealed in unstructured, unverifiable, and ambiguous ways from scarce
[00:05:54] amounts of real-world interaction.
[00:05:56] Because in many domains, the relevant training information simply
[00:06:00] doesn't exist in any other way.
[00:06:02] What is the RL environment to make an AI that is as good at politics as
[00:06:05] Lyndon Johnson, or as good at building a space-launch business as Elon Musk?
[00:06:10] The labs are betting that RLVR will generalize.
[00:06:12] That is, that if you train on enough containerized, reproducible
[00:06:15] environments, you will develop a very general agent that can make and
[00:06:19] execute plans and learn rapidly from new information, and even pick up new
[00:06:24] skills, all within a single session.
[00:06:27] If you drop this endlessly RLVR'd AI into Texas politics in 1948, it
[00:06:32] could give you better advice than LBJ about winning the Senate seat.
[00:06:35] And if you gave it a hundred million dollars in 2002 and let it cook,
[00:06:38] it would build SpaceX for you.
[00:06:39] Now, whether RLVR can generalize this well is an empirical question.
[00:06:43] If the labs went from spending billions of dollars on RL environments to a trillion
[00:06:48] dollars, would you get the kind of thing that is a fully human-like general
[00:06:52] intelligence within the context window?
[00:06:54] Dario gave a telling quote during our podcast together, which I think
[00:06:57] hints that RLVR generalization is not infinitely strong.
[00:07:02] When he was explaining why model performance tends to degrade at long
[00:07:05] context, he said: "There's two things.
[00:07:07] There's the context length you train at, and there's a context
[00:07:09] length that you serve at.
[00:07:11] If you train at a small context length and then try to serve at a long context
[00:07:15] length, maybe you get these degradations."
[00:07:17] Now, maybe I'm reading too much into this, but it seems like he's
[00:07:19] saying that short-horizon RL training doesn't necessarily generalize
[00:07:23] to long-horizon RL performance.
[00:07:25] And if you can't generalize from short horizon to long horizon, then how are
[00:07:29] agents supposed to generalize from getting trained at a bunch of white-collar tasks
[00:07:33] to, say, having the ability to be dropped in the real world and build a business
[00:07:38] from scratch as well as Sam Walton?
[00:07:40] And even if, after enough in-context experience, the AIs could become
[00:07:42] like Henry Ford or Albert Einstein, all that would be ephemeral and
[00:07:46] wasted if you couldn't get those learnings back into the weights.
[00:07:50] Around 30 to 50 percent of a lab's compute goes to inference, and that compute is
[00:07:54] currently not playing any productive role in helping improve the model.
[00:07:58] This seems like a huge waste.
[00:08:00] And it's even worse than it sounds, because it is only in deployment
[00:08:03] that the most valuable bits of information which your model could
[00:08:06] learn from are actually revealed.
[00:08:08] What's actually happening in the organizations where I'm being used?
[00:08:11] What are they using me for?
[00:08:13] And what kinds of mistakes do I tend to make in the real world?
[00:08:16] We've got some genius grad student who's never been allowed to take a real
[00:08:19] internship, and we keep giving it more and more classroom case studies in the
[00:08:22] form of RL training on environments.
[00:08:25] It's so bizarre that we have AIs that are broadly deployed through the
[00:08:29] economy already, and are participating in so many different kinds of tasks,
[00:08:33] and are privy to so much domain- and organization-specific tacit knowledge,
[00:08:39] and they're not able to make use of it.
[00:08:41] But this kind of continual learning requires going back to the weights.
[00:08:45] AIs can't just keep building up a bigger and bigger KV cache as they
[00:08:48] learn from more and more users.
[00:08:50] That's just not scalable, and that's also not how humans do it.
[00:08:53] There's no clean separation in our brain between parameters and activations,
[00:08:56] and it's not like some part of your skull keeps expanding as you learn
[00:09:01] more things throughout your lifetime.
[00:09:03] When we learn stuff, there's clearly some kind of compression, and this
[00:09:07] aids our generalization and grokking.
[00:09:09] There are, in fact, some humans who have this autistic-savant-type ability
[00:09:13] to recall random tables of numbers or nonsense syllables years later
[00:09:19] — basically the kind of fidelity of information that models have in context.
[00:09:23] And such sheer volume cripples these humans' ability to understand
[00:09:27] abstractions and metaphors.
[00:09:29] Human continual learning is less about having all your observations at the tip
[00:09:32] of your tongue and more about chiseling the right intuitions and big-picture
[00:09:36] knowledge back into the weights.
[00:09:38] But the moment you move into the weights, you have to give up on
[00:09:41] in-context learning's sample efficiency.
[00:09:43] Because gradient updates are super sample-inefficient, all of the
[00:09:46] successfully shipped online-learning models have had to learn the exact
[00:09:50] same thing across millions of users.
[00:09:52] For example, the Cursor Tab model online-learns by predicting the
[00:09:57] same exact objective for over 400 million requests a day.
[00:10:00] The objective here is which edits actually got accepted by the user.
[00:10:04] At least so far, we haven't seen models online-learn different kinds of things for
[00:10:09] different users, because while a single session may generate more than enough
[00:10:13] data for a human to learn from, it's not enough to train a more capable AI.
[00:10:18] Current online learning can work for a very limited number of use cases.
[00:10:22] But the whole point of continual learning is that the world is very
[00:10:26] complicated, and each job and company and problem is different, and you need
[00:10:31] your intelligence to be able to learn the specific information related to a
[00:10:36] particular deployment, which simply can't be stuffed into some shared training run.
[00:10:41] These are all the things we're talking about when we talk about on-the-job
[00:10:43] learning: things like how everything in your organization works and fits
[00:10:47] together, how to cooperate with all the infrastructure and the other people
[00:10:50] around you to make progress on some larger project, what the common failure modes
[00:10:55] are, and many other things like this.
[00:10:58] As the podcast has grown, I've had to deal with more and more operational overhead.
[00:11:02] Take paying bills.
[00:11:03] In the past, contractors would just email me their invoices.
[00:11:06] Every few weeks, I'd dig through my inbox, create a folder with all the
[00:11:09] bills, and manually pay each one.
[00:11:11] At this point, though, I just give everybody an email address
[00:11:14] that goes straight to Mercury, which is my banking platform.
[00:11:17] Whenever anybody sends an invoice to that address, Mercury automatically
[00:11:20] downloads it, scans it, and extracts all the relevant information — things
[00:11:24] like the contractor name, address, payment amount, invoice number,
[00:11:27] and due date — and then uses all of this to create a draft payment.
[00:11:30] Mercury then stores a list of these drafts for me to review.
[00:11:33] I just go through the list and double-check that
[00:11:35] they've been built correctly.
[00:11:36] I don't have to track anything or enter any information myself.
[00:11:39] Mercury does all the fundamental things for your business extremely well,
[00:11:43] and it puts them all in one place.
[00:11:44] If you want to learn more, go to mercury.com.
[00:11:48] Mercury is a fintech company, not an FDIC-insured bank.
[00:11:52] Banking services provided through Choice Financial Group
[00:11:54] and Column N.A., Members FDIC.
[00:11:57] In this way, sample efficiency and continual learning are actually
[00:12:01] deeply connected problems.
[00:12:02] Relatively little data is available to the model on the job.
[00:12:07] Now, to learn from this data requires sample efficiency, and models can do that
[00:12:11] in context, but using the fast weights that are built on the fly by attention,
[00:12:16] which allow for this sample efficiency, scales very poorly in terms of memory.
[00:12:20] So we need architectural innovations that allow for some kind of
[00:12:23] intermediate representation.
[00:12:25] I talked before about how we already have many different working ideas
[00:12:28] for this kind of thing, from sparse attention to KV cache compaction.
[00:12:32] And every week, somebody releases a new paper suggesting some kind of
[00:12:35] other architectural optimization.
[00:12:37] It doesn't seem to me that architecture is fundamentally what
[00:12:40] is bottlenecking continual learning.
[00:12:42] So perhaps the bottleneck is the loss function.
[00:12:44] How do we update the weights, AKA how do we improve the model itself,
[00:12:49] based on information that was learned from one particular session?
[00:12:53] Even here, naively, it seems like there are many ideas that ought to work.
[00:12:56] A lot of people are talking about this technique called on-policy
[00:12:59] self-distillation recently.
[00:13:01] If you want to learn more about it, I recorded a little impromptu
[00:13:03] blackboard lecture on my iPhone with Sasha Rush a couple weeks ago, and
[00:13:08] it's in the link in the description.
[00:13:09] But to summarize the explanation, the idea is that we encourage the base model
[00:13:14] to make the same predictions when trying to solve some real-world problem as the
[00:13:18] model with all the context accumulated after a long session would have made.
[00:13:22] The whole point of this procedure is to distill what the model learned in a
[00:13:26] session back into the weights themselves.
[00:13:29] This is better than RLVR for two reasons.
[00:13:31] One, OPSD doesn't require us to have some outer-loop verifiable reward.
[00:13:36] We just need a model that can learn the right things within the context window.
[00:13:40] And as long as we have that, we can train the base model to match our veteran
[00:13:44] teacher model, which has built up all this experience during the session.
[00:13:48] And two, OPSD provides a much denser supervision signal than naive RL.
[00:13:54] Instead of projecting a single reward through the whole
[00:13:56] trajectory, you can train on the per-token probability discrepancy
[00:14:00] between the teacher and student.
[00:14:02] For continual learning, OPSD is also superior to supervised fine-tuning.
[00:14:06] The most naive version of SFT for this application that you can
[00:14:09] imagine is just to train the base model to predict all the tokens that
[00:14:12] are observed during the session.
[00:14:14] But this makes no sense if you think about it as a learning target.
[00:14:16] The way you get better at your job is not by recalling the transcript
[00:14:19] of every single thing that happened every day with perfect fidelity.
[00:14:23] Rather, it's by consolidating the handful of insights and pieces of
[00:14:26] knowledge that are actually relevant to you getting better at your job.
[00:14:30] RL training doesn't suffer from this failure mode.
[00:14:32] RL is great at concentrating the update to only what is relevant
[00:14:36] to getting the outcome right.
[00:14:38] That's why
[00:14:41] the updates from RL are incredibly sparse.
[00:14:43] And this is a very important property for continual learning, because as
[00:14:46] you're learning on the job, you don't want to overwrite and forget all the
[00:14:49] other things that the base model knows.
[00:14:51] I wrote a post a few months earlier arguing that RL learns
[00:14:55] much less information per sample than supervised learning.
[00:14:58] But this may be a good thing rather than a bad thing.
[00:15:00] You only change the model as much as is absolutely necessary to
[00:15:04] achieve the outcome, and no more.
[00:15:07] OPSD preserves this property of RL, where instead of slingshotting towards
[00:15:11] the teacher distribution as supervised learning would have you do, you only
[00:15:15] extract the knowledge that is necessary to achieve the same results as the
[00:15:19] teacher on actual real-world tasks.
[00:15:22] OPSD is one way to attack the sample-efficiency problem.
[00:15:26] You take this scarce real-world experience, and you squeeze all the
[00:15:29] signal into a tiny, well-targeted update.
[00:15:31] But there's also another much more speculative idea.
[00:15:34] Let's call it dreaming.
[00:15:36] If the AI can build a good simulation of reality against which to rehearse
[00:15:40] new skills, or try alternative strategies and reinforce what actually
[00:15:44] works, then AIs could experience orders of magnitude more simulated
[00:15:48] samples in the same wall-clock time.
[00:15:51] Let's go back into history a bit.
[00:15:53] A couple years after DeepMind released AlphaZero, a group of researchers
[00:15:56] trained a model called EfficientZero, and the whole point of this model
[00:15:59] is to be very efficient with data.
[00:16:01] So if this model and a human both got two hours to play against a simulator
[00:16:06] of an Atari game that they hadn't seen before, this model would actually
[00:16:10] probably beat the novice human.
[00:16:11] Does this mean that the model was more sample-efficient than the humans?
[00:16:14] Well, that was the goal of the training, but it depends on how
[00:16:17] you measure sample efficiency.
[00:16:19] Because for each step in the real game, EfficientZero is playing dozens
[00:16:23] of simulated games in its head.
[00:16:25] In a similar way, future LLMs might be able to consume far less
[00:16:29] real-world data while practicing endlessly against environments
[00:16:32] that they build for themselves.
[00:16:34] The big difference, of course, is that it will be much harder to build
[00:16:37] a simulation of the whole world than it is to emulate the game of Go.
[00:16:41] That's why I said this is a much more speculative idea.
[00:16:44] If it works, it would become a fourth axis of scaling alongside pretraining,
[00:16:48] RL, and inference-time compute.
[00:16:50] You could call it test-time training or dreaming.
[00:16:53] The model spends compute writing up RL environments and then training
[00:16:56] against them, and it's rehearsing all the skills that will actually be used
[00:17:00] in production for a specific user.
[00:17:03] So instead of hitting /compact in Codex or Cursor or Claude, which kindles a small
[00:17:09] amount of compute to write up a summary, and which gives you the simulacrum of
[00:17:13] continual learning, you hit /dream.
[00:17:14] And this incinerates huge amounts of compute to build and train against a
[00:17:20] video-game version of what the model is witnessing in the real world.
[00:17:24] So what might continual learning look like by 2027 or 2028?
[00:17:26] And how do we get there?
[00:17:29] Here's one scenario.
[00:17:30] All of this RLVR training is producing an agent that can get its bearings when
[00:17:34] it's thrown at an unfamiliar problem, and it can try different strategies, and
[00:17:38] it can iterate when it hits a roadblock.
[00:17:40] This is the crucial thing that RLVR has given you: an AI that
[00:17:44] is at least competent enough to start getting some real-world
[00:17:47] experience, if it could learn from it.
[00:17:50] And once you have that, you send it out into the world to do real
[00:17:53] work, even on projects that are off the training distribution.
[00:17:56] Now let's say at this point, the effective context lengths have expanded
[00:17:59] such that AIs can jam and co-work with you for a full week of wall-clock time.
[00:18:06] At the end of a week, you give it a thumbs up or a thumbs
[00:18:08] down, you give it a work review.
[00:18:10] And if you give it a thumbs up, the base model distills everything that
[00:18:13] the AI learned during the session, and it may use OPSD, it may use dreaming,
[00:18:17] it may use some other technique that we aren't even aware of, or it'll use
[00:18:21] a combination of all of the above.
[00:18:23] And AI can get better at domains that are adjacent to what it was explicitly
[00:18:28] trained for beforehand with RLVR.
[00:18:32] And in the next round it gets better at the thing adjacent to what it
[00:18:35] was previously online learned.
[00:18:37] In this way, the gamut of AI skills and knowledge and capabilities can
[00:18:41] expand far beyond the verifiable domains that the model was originally
[00:18:46] trained against before it was deployed.
[00:18:48] Just as pretraining created a base intelligence that was smart enough to
[00:18:52] become a competent agent with enough RLVR on top, so RLVR has created an agent
[00:18:58] that is competent enough to actually be broadly deployed in the world, and
[00:19:02] from this broad deployment to learn on the job once the training recipe for
[00:19:06] continual learning actually arrives.
[00:19:08] By this point, the main way that AIs get better is not from the
[00:19:12] training they have received before they are released to the public.
[00:19:14] Rather, it's from all this experience that they'll be accumulating from being broadly
[00:19:18] deployed in the economy and engaging in so many different kinds of tasks.
[00:19:22] Every time that you interact with an AI, it'll be smarter, not only because
[00:19:26] it's been learning from your previous sessions, but also because it's been
[00:19:28] learning from all its interactions with all the other users in the world.
[00:19:33] And that's very scary and exciting and different from the
[00:19:36] way that AI improves right now.
[00:19:38] This was a narration of a blog post that I also released on
[00:19:42] my website at dwarkesh.com.
[00:19:44] Go there if you want to read all the footnotes, or if you want to
[00:19:47] sign up so you can find out when I release the next blog post.
[00:19:50] Otherwise, I'll see you on the next episode.
