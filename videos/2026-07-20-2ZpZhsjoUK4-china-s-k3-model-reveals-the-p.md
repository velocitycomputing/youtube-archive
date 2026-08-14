---
video_id: 2ZpZhsjoUK4
title: "China's K3 Model Reveals the Problem With Open Weights"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=2ZpZhsjoUK4"
watched_date: 2026-07-20
watched_at: "2026-07-20T12:00:00Z"
watch_count: 1
duration_seconds: 1126
source: youtube-history-browser
added_date: 
history_label: Jul 20
history_order: 163
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1126
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Moonshot's K3 model (releasing July 27) delivers near-frontier coding performance but shatters the myth that open-source models are cheap or efficient to run. K3 requires 64 accelerator cores for proper performance and costs ~$15 per million output tokens via API—frontier pricing. More critically, K3 uses significantly more tokens than Claude or OpenAI models to reach answers, revealing that Chinese model makers are actually less efficient at inference than commonly believed. The speaker argues closed-source labs (OpenAI, Anthropic) maintain a sustained 6-7 month technical lead; as open-source models scale toward frontier capabilities, serving costs increase rather than decrease—there is no free lunch. K3 also marks the inflection point where open-source models become credible cyber threats, signaling governments will likely restrict distribution within months.

Plan immediately for a diversified AI strategy: audit your software and systems using the strongest available model (Claude Fable) for vulnerabilities before threat actors exploit open-source models. Harden identity security with layered defenses—varied passwords, 2FA via authenticator app (not SMS), and a secret family phrase to detect AI-generated voice clones impersonating relatives (critical as wire fraud accelerates). Maintain redundant access: run local open-source via LM Studio, maintain subscriptions to multiple cloud providers, and avoid dependency on any single model or company. Spend time brainstorming novel use cases with others who understand advanced models—competitive advantage lies in creative questions you haven't asked, not predetermined workflows. Consider K3 specifically for code analysis, reverse-engineering, and fine-tuning where Claude and OpenAI explicitly refuse.

## Transcript

[00:00:00] Open source changed again. So Kimmy K3
[00:00:03] is a brand new model from Moonshot and
[00:00:07] they released a brand new open-source
[00:00:09] openweights model. Now I say open
[00:00:10] weights, it's actually coming like July
[00:00:12] 27. They're going to release the open
[00:00:13] weights. The reason you should care is
[00:00:16] that this changes the dynamic of
[00:00:19] opensource. So open- source like what I
[00:00:21] have traditionally heard what a lot of
[00:00:23] people hear and think about open source
[00:00:24] is one hey it's cheap to run and two hey
[00:00:28] it's really efficient to run and sure
[00:00:30] there are a ton of models that fit that
[00:00:33] rubric but today I'm going to talk to
[00:00:36] you about how Kimmy K3 breaks that
[00:00:40] assumption in some really important ways
[00:00:43] and why we should pay attention because
[00:00:44] it tells us about where the race is
[00:00:46] going and it tells us about where we
[00:00:48] should be putting our personal compute
[00:00:50] dollars. So, let's pay attention and dig
[00:00:53] in. All right, so first Kim K3 is a big
[00:00:56] model. They say at top performance, you
[00:00:59] need 64 accelerator cores to run this
[00:01:02] model. I'm going to give you a hint. You
[00:01:04] don't have 64 accelerator cores at home.
[00:01:06] I like 1% of you do. A tenth of 1% of
[00:01:09] you do. Almost nobody has that at home.
[00:01:11] That is a corporate installation kind of
[00:01:14] footprint. It is a big model. It is a
[00:01:17] heavy model. Now the good news is you
[00:01:19] get performance for that and so if you
[00:01:22] do run it you get near frontier not
[00:01:25] really Fable 5 but close to Fable 5
[00:01:27] coding performance. It falls off in some
[00:01:29] of the other areas. It doesn't have
[00:01:31] safeguards effectively like it has a
[00:01:33] few. It has the usual ones that Chinese
[00:01:35] models have. If you're trying to
[00:01:36] fine-tune a model, Fable won't let you.
[00:01:38] In fact, Fable will be very upset at you
[00:01:41] for that. It is guardrail not to do that
[00:01:43] because that is part of how Enthropic is
[00:01:45] trying to protect their proprietary
[00:01:46] information. On the other hand, Kimmy K3
[00:01:48] will be happy to help you fine-tune a
[00:01:50] model. And so there are some legitimate
[00:01:52] use cases that closed source models have
[00:01:55] kind of locked off that Kimmy opens up.
[00:01:58] And so even if it is not quite at what
[00:02:00] is out there right now in the public
[00:02:02] market, if it's like a shade or two
[00:02:04] below the frontier that's publicly
[00:02:06] available, you still get some nice
[00:02:08] capabilities you can't get any other
[00:02:10] way. And so I think that there are going
[00:02:12] to be a bunch of use cases for Kimmy K3
[00:02:15] that are going to pop out of the
[00:02:17] woodwork, but efficiency and using it
[00:02:21] because it's cheap isn't one of them.
[00:02:23] Now, part of why is because you have to
[00:02:26] spend a lot in compute to run that
[00:02:29] thing. But also part of why is because
[00:02:32] if you don't and you use the cloud
[00:02:34] model, Kimy's pricing is kind of
[00:02:38] expensive in two different dimensions.
[00:02:40] Stick with me. First, Kimmy is pricing
[00:02:43] in multiple dollars per million tokens,
[00:02:46] which if you're used to Chinese models,
[00:02:48] is already expensive. It's already up
[00:02:50] into the frontier pricing tiers right
[00:02:52] now. It's not as bad as Fable's not 50
[00:02:54] bucks, but it's getting up there. I
[00:02:55] think it's it's 15 bucks uh per million
[00:02:57] output tokens. So, Kim is not cheap. But
[00:02:59] Kim is also not cheap because it uses
[00:03:03] more tokens to get to the answer. And so
[00:03:06] part of how you save money with a model
[00:03:08] is you have the model use less tokens to
[00:03:10] get to the answer. And Kimmy K3 for a
[00:03:14] given answer that it gets to uses a lot
[00:03:17] more tokens than OpenAI's models do that
[00:03:20] like that 5.6 or 5.5 does or Fable 5
[00:03:24] does. Right? These models that are on
[00:03:26] the frontier, they may be expensive, but
[00:03:27] they're very token efficient. Relatively
[00:03:30] speaking, Kimmy K3 is not as efficient.
[00:03:32] Now, here is where we start to get into
[00:03:35] the implications, and I want you to
[00:03:37] stick with me here. If we have the old
[00:03:41] deepseek narrative on Wall Street, it
[00:03:43] turns out that inference is kind of a
[00:03:45] subset of the distilling and the back
[00:03:47] propagation that they have to do to get
[00:03:50] the model trained up in the first place
[00:03:52] from a seed, right? From a a a
[00:03:55] topography, a set of parameters that
[00:03:57] they're able to distill down from an
[00:03:59] existing Frontier model. And if you have
[00:04:00] to do back propagation across that part
[00:04:02] of that process requires inference. And
[00:04:05] so if you think they're efficient at
[00:04:07] that, they should be efficient at
[00:04:09] serving the model. And so the fact that
[00:04:11] they're not suggests that some of the
[00:04:15] narrative that we have been given around
[00:04:18] how Chinese model makers are incredibly
[00:04:20] efficient may not be as true as we
[00:04:22] think. I'm not saying that there's not
[00:04:23] like great innovation going on. Don't
[00:04:25] get me wrong, there's a lot of cool
[00:04:27] innovation going on here. It is
[00:04:28] incorrect to say it's just distilled.
[00:04:30] That is absolutely not true. There's a
[00:04:32] lot of good stuff. But it doesn't mean
[00:04:35] that it's just a story of efficiency.
[00:04:38] And I hear so often, well, Chinese
[00:04:40] modelmakers are incredibly efficient. I
[00:04:42] would actually say the evidence we have
[00:04:45] suggests that open AI is incredibly
[00:04:47] efficient at serving models and that
[00:04:50] anthropic is becoming fairly efficient
[00:04:52] at serving models and that Chinese model
[00:04:54] makers are behind on serving models
[00:04:57] efficiently which suggests that net net
[00:04:59] from a knowledge perspective the major
[00:05:02] labs remain ahead the closed source labs
[00:05:04] anthropic and open AAI and I will go
[00:05:07] further and I will say we often mistake
[00:05:11] comparing comparing the existing
[00:05:13] frontier model in the marketplace with
[00:05:16] the existing internal model benchmark in
[00:05:19] the lab. The true frontier in American
[00:05:22] labs is what is not released. It is what
[00:05:25] is in the lab. Fable is is has been out
[00:05:28] inside the lab for at least that long
[00:05:30] and we're just getting it now. And so
[00:05:31] when you think about the narrative that
[00:05:33] Chinese models are catching up, you have
[00:05:35] got to start benchmarking correctly.
[00:05:37] They are still about six or seven months
[00:05:40] behind just like they were a year ago.
[00:05:42] And I see a narrative where it's like,
[00:05:44] wow, they're almost close to Fable.
[00:05:46] They're almost close to, you know, 5.6.
[00:05:48] They'll pass them by the end of the
[00:05:50] year. I've seen that take. That's just
[00:05:52] incorrect. The model makers are well
[00:05:54] past that now. It'll be another four,
[00:05:57] five, 6 months before we see what
[00:05:58] they've got internally. They will do
[00:06:00] even more safety testing because it's a
[00:06:02] risk now, but they're not catching up.
[00:06:05] And there's no sign that they're
[00:06:07] imminently catching up. The closed
[00:06:09] source models in anthropic and open AI
[00:06:12] have a tremendous lead and they're not
[00:06:15] letting up right now. Now, we can talk
[00:06:17] about what that means and we will, but
[00:06:20] one of the things that I want to push
[00:06:21] back on is the narrative that we have
[00:06:24] efficient, open-source models that are
[00:06:26] cheap and easy to run that are at the
[00:06:28] frontier or catching up. That none of
[00:06:30] those things are completely true
[00:06:32] anymore. And in fact, and this is one of
[00:06:34] the larger implications I want you to
[00:06:36] take away, as we push models forward
[00:06:38] toward the frontier with larger and
[00:06:42] larger and larger Chinese models, we are
[00:06:45] going to get to a point where we have
[00:06:46] more and more expensive models to serve
[00:06:48] because you have to scale them up to get
[00:06:51] them to the frontier, right? You cannot
[00:06:53] just sit there and say, "We will
[00:06:55] magically make them small and small and
[00:06:57] small and they will somehow match
[00:06:58] frontier performance." There is no free
[00:07:00] lunch here. you're going to have to
[00:07:02] start to scale them up. And when you
[00:07:03] start to scale up the models, it gets
[00:07:04] harder and more expensive to serve. It's
[00:07:07] less efficient to serve. You have to get
[00:07:08] more compute to serve. Which means that
[00:07:12] we are going to have to face the reality
[00:07:14] that open-source models are not closed
[00:07:17] source, that they come with real costs
[00:07:20] to serve, whether you're paying that in
[00:07:22] computer chips or you're paying that
[00:07:23] directly to the provider, and that
[00:07:26] they're not going to be as good as
[00:07:28] closed source for the foreseeable
[00:07:29] future. None of which should imply that
[00:07:33] we shouldn't use them. Open source is a
[00:07:35] valuable tool in the arsenal. I did a
[00:07:37] video on open source just on Sunday and
[00:07:40] why it's important to have that in your
[00:07:41] toolkit. I think it's fantastic. I think
[00:07:44] you have a wide range of open source
[00:07:45] models now and I love that. They've
[00:07:47] never been easier to work with. But we
[00:07:51] should not mistake that availability for
[00:07:54] the performance level that we get at the
[00:07:56] frontier. And so I come back again when
[00:07:59] I look at the future of computing. I
[00:08:00] want to draw a few core lessons out for
[00:08:02] us at the end just like I said I would.
[00:08:05] Lesson number one, what your approach is
[00:08:09] to AI safety for yourself, your family,
[00:08:13] and if you have a company, your company.
[00:08:15] And the reason I say that is because
[00:08:18] with this model Kimmy K3 that dropped,
[00:08:22] we have now crossed the frontier into
[00:08:25] open-source models being cyber threats
[00:08:28] and we're just going up from here. You
[00:08:31] need to think about the reality that
[00:08:33] these open- source models, just like I
[00:08:35] said, I said a couple months ago this
[00:08:37] would happen. We are coming into a world
[00:08:40] in the second half of 2026 where these
[00:08:42] open- source models are going to be
[00:08:43] everywhere on the internet. They are
[00:08:45] going to be cyber threats and they will
[00:08:47] be used as cyber weapons by bad actors.
[00:08:51] And so you need to be asking yourself,
[00:08:52] what do you need to secure your family?
[00:08:54] What do you need to do to secure your
[00:08:55] company? And I'm going to give you some
[00:08:57] specific tips based on best practices.
[00:09:00] You also need to take the time to do a
[00:09:01] full audit cuz I don't know your full
[00:09:03] system. So one, get a hold of the
[00:09:06] strongest model you can. Fable's a good
[00:09:07] example while we have it. Make sure you
[00:09:10] use it to audit any software you have
[00:09:13] and look at it from an adversarial
[00:09:15] posture. Is it safe to use? Are there
[00:09:18] leaks that you don't intend? Is there
[00:09:21] malicious code somewhere? Is there not
[00:09:23] even malicious code? Is there code that
[00:09:25] is just buggy and leaking something out
[00:09:27] that shouldn't be? Is it accessible from
[00:09:30] an adversarial perspective? How do you
[00:09:33] set up your software so you have a more
[00:09:35] secure posture given the best model you
[00:09:37] can get a hold of? Now, how do you think
[00:09:39] about multiple layers of defense when it
[00:09:41] comes to your cyber identity for your
[00:09:44] family as well as for any software
[00:09:47] assets that you have? And so in
[00:09:48] software, we talk about the idea that
[00:09:50] you have multiple layers of defense from
[00:09:51] social engineering, from software
[00:09:53] attacks, etc. And so that a software
[00:09:56] attacker, a hacker cannot get in through
[00:09:59] just one ring of defense and get the
[00:10:01] whole thing. They have to like go
[00:10:02] through multiple layers of defense. You
[00:10:03] can catch them along the way. With our
[00:10:05] identities, it's similar. You want to be
[00:10:07] in a position where you can protect your
[00:10:09] identity through obviously the old stuff
[00:10:11] like varied passwords, uh, two-factor
[00:10:13] authentication. You want to be able to
[00:10:15] wherever you can move from just a
[00:10:18] textbased authenticator to a more secure
[00:10:21] like fingerprint-based or maybe a uh
[00:10:24] USB-based authenticator where you have
[00:10:26] that key and wherever you can you want
[00:10:28] to move from just a password to 2FA not
[00:10:30] just 2FA with a text but like 2FA with
[00:10:32] an authenticator app something like that
[00:10:34] where you actually have multiple secure
[00:10:37] ways to verify your identity for digital
[00:10:40] access. You also want to make sure that
[00:10:42] you are looking at how identity works in
[00:10:45] the digital age with AI. So you should
[00:10:47] have a password with your family,
[00:10:49] something that you would never normally
[00:10:51] use in conversation that the whole
[00:10:53] family knows that if you use that word,
[00:10:56] it's really you. But if someone clones
[00:10:59] your voice, if someone clones your
[00:11:01] likeness and they call that that digital
[00:11:03] persona is not going to know that secret
[00:11:05] word or that secret phrase, and they're
[00:11:07] not going to be able to guess. And that
[00:11:08] way your family will know if there's
[00:11:10] some sort of digital demand for ransom,
[00:11:12] it's not really you. It's it's some
[00:11:14] people who are hacking them and they
[00:11:16] will be able to avoid wiring a bunch of
[00:11:19] money and losing money. And this is
[00:11:20] personal to me, by the way. Uh my
[00:11:22] grandfather lost a lot of money to wire
[00:11:24] fraud. Uh we never got it back. Um and
[00:11:26] they took advantage of him. He had
[00:11:28] dementia and it was terrible. So it's it
[00:11:31] it is a real thing. It happened in the
[00:11:33] past before AI. It will happen more now.
[00:11:36] It will happen especially as we have
[00:11:38] these capable models that make it easier
[00:11:40] and easier and easier to simulate speech
[00:11:43] to simulate uh likeness to simulate
[00:11:45] sophisticated hacking programs. In this
[00:11:47] case, Kim K3 is very much on the hacking
[00:11:50] program side. There are other models
[00:11:51] that have come out recently on the voice
[00:11:53] side on the video side that are also if
[00:11:55] you assemble them a scary combination.
[00:11:57] So, make sure that you protect yourself.
[00:12:00] That's lesson number one. Lesson number
[00:12:02] two, and there are three of these.
[00:12:04] Lesson number two, make sure that you
[00:12:08] recognize that we are moving into the
[00:12:12] age when your imagination and ability to
[00:12:15] pose the right question is what is going
[00:12:18] to matter. And I'm thinking about that
[00:12:19] more and more, not just with Kimmy K3,
[00:12:21] but with Fable coming out now with 5.66
[00:12:24] is on the horizon. Opus 5 is about to
[00:12:26] come out. In that world, you are going
[00:12:29] to be tested for your ability to ask
[00:12:32] questions. You can't just sit there and
[00:12:34] say, "I already have a job for AI. This
[00:12:36] is the job for AI, and I'm going to give
[00:12:38] it." I talked to someone recently who
[00:12:40] was really honest with me. He said, "I'm
[00:12:42] just not giving Fable something
[00:12:45] interesting to do." And I said, "Well,
[00:12:46] let's just kick it around. Let's talk."
[00:12:47] And as we talked, as we brainstormed, he
[00:12:50] came up with like three great use cases
[00:12:52] that only Fable could do. But he needed
[00:12:55] to brainstorm with someone who knew
[00:12:57] Fable to kind of kick that around and
[00:13:00] get that sense of what that model could
[00:13:02] do. so he could figure out where the
[00:13:04] value was. We need more of that. Now, my
[00:13:07] Substack community has that and that's
[00:13:09] great, but wherever you're getting it,
[00:13:11] it doesn't have to be with me, you got
[00:13:13] to find people who can help you grab
[00:13:16] onto that imagination and start to ask
[00:13:19] bigger questions because otherwise
[00:13:22] you're not going to be finding new and
[00:13:24] creative ways to use AI and that is
[00:13:27] going to be where the alpha is. The
[00:13:29] alpha is not going to be in the
[00:13:31] predetermined stuff that everybody else
[00:13:33] already also knows. It is going to be in
[00:13:36] your imagination married to AI driving
[00:13:38] toward human connection and building
[00:13:40] experiences that are incredible. And
[00:13:42] that requires yes touching grass which
[00:13:44] is great but also making sure that you
[00:13:47] have the imagination to ask really
[00:13:48] interesting questions of AI because that
[00:13:50] is where you get the most creative and
[00:13:52] powerful responses from very very strong
[00:13:55] models whether they're open source like
[00:13:56] Kimmy K3 or whether it is fable or
[00:13:59] whether it is 5.6 or whatever future
[00:14:00] model we have in a month. The models
[00:14:02] have hit another inflection point.
[00:14:03] That's where we are going. Lesson number
[00:14:06] three, we need to plan for an increased
[00:14:08] risk that governments are going to get
[00:14:11] more and more involved in hampering the
[00:14:13] distribution of models over the next 6
[00:14:16] months. As I've been saying all the way
[00:14:18] through, models are getting more
[00:14:20] capable. Kimmy K3 says that moment comes
[00:14:23] to open source just as much as to close
[00:14:25] source, which is exactly what we should
[00:14:27] expect. If that is the case and we keep
[00:14:30] seeing scaling and we get to an open-
[00:14:31] source model that is fable level truly
[00:14:34] and then maybe one that is mythos level
[00:14:36] by Christmas time, we should expect
[00:14:39] governments to start to pay attention
[00:14:41] and restrict. And I don't just mean the
[00:14:43] American government. There there are
[00:14:45] some rumors coming out of China that the
[00:14:48] Chinese government is thinking about
[00:14:49] restricting certain tiers of open-source
[00:14:53] models and not letting them out into the
[00:14:55] world in the same way they are right
[00:14:56] now. We don't know where that's going to
[00:14:58] end up, but net net looking at increased
[00:15:03] government involvement in model makers
[00:15:06] would lead us to suppose that we are
[00:15:08] going to have to plan for a multimodel
[00:15:11] diverse future if we want to have
[00:15:15] artificial intelligence around. And
[00:15:17] that's the good news for Kimmy K3,
[00:15:19] right? Because Kimmy K3 is another model
[00:15:22] in our arsenal. We can figure out how to
[00:15:23] serve it. Yes, they're going to drop
[00:15:25] those weights on the 27th and we can
[00:15:27] grab them and they we can have other
[00:15:28] models, right? It's not just Kim K3. We
[00:15:30] can have a bunch of models locally. We
[00:15:31] can have a model garden if you will. Uh
[00:15:34] and we can also have access to cloud
[00:15:35] models, etc. The point is we are going
[00:15:39] to be in a world increasingly where all
[00:15:41] of computing is trending toward being
[00:15:44] tokenized and therefore in order to
[00:15:48] compete we need to not be vulnerable to
[00:15:50] any given disruption, right? Whether
[00:15:52] that's an anthropic issue or maybe an
[00:15:54] open AAI issue or maybe there's some
[00:15:56] Chinese model issue, we don't want to be
[00:15:58] disrupted anywhere. We want the ability
[00:16:01] to tokenize regardless. And that is a
[00:16:04] theme that is really really big right
[00:16:07] now as we look at what happened with
[00:16:09] Fable and Mythos and juxtapose that with
[00:16:12] the availability of Kimmy K3 and just
[00:16:15] flatline project that out to the end of
[00:16:16] the year. If you look at the
[00:16:17] capabilities, you look at how worried
[00:16:19] governments are now, they're not going
[00:16:20] to get less worried and we should expect
[00:16:23] more surprising policy and we should
[00:16:26] plan for that. And I think that that
[00:16:28] goes for individuals as much as for
[00:16:31] companies. Yes, companies need to plan
[00:16:32] for it, but individuals, if you want to
[00:16:34] make sure that you have the ability to
[00:16:36] get the intelligence you want to get
[00:16:38] stuff done, you got to plan for that,
[00:16:40] too. Maybe that means LM Studio like I
[00:16:42] talked about on Sunday. Maybe it means
[00:16:45] making sure you have multiple
[00:16:46] subscriptions to different cloud
[00:16:48] providers. You will have to decide what
[00:16:50] your risk tolerance is. But you should
[00:16:53] assume you need at least one model and
[00:16:55] at least one backup model and make sure
[00:16:58] that you are comfortable with the risk
[00:17:01] profile that those models represent. So
[00:17:05] wrapping all of this up, where does this
[00:17:06] leave us with Kimmy K3? Kimmy K3 is an
[00:17:10] inflection point in the opensource race.
[00:17:15] It is by far the best model that we have
[00:17:17] seen come out. It reminds us that even
[00:17:19] if open-source models are trailing
[00:17:22] Frontier models by about the same
[00:17:24] margin, they are also ipso facto still
[00:17:28] scaling at about the same speed. They
[00:17:30] are getting incredibly good. And so
[00:17:32] Kimmy K3 is not even about whether it's
[00:17:35] behind. It's about the fact that it's an
[00:17:36] incredible coding model that's being
[00:17:38] released and that you can use to drive a
[00:17:41] tremendous amount of value. So, if you
[00:17:43] haven't used it, go give it a try. I've
[00:17:46] been playing with it. It is like many
[00:17:48] open- source models, a little bit
[00:17:50] narrower in terms of what it can do, but
[00:17:53] the coding in particular, its ability to
[00:17:56] code is very, very strong. Tell me if
[00:17:58] you're using it. Tell me how you're
[00:18:00] comparing it to Fable, how you're
[00:18:01] comparing it to OpenAIS 5.6. I'd love to
[00:18:04] see specific examples of stuff you've
[00:18:06] built back and forth in the comments so
[00:18:07] we can kind of dig into it. There are
[00:18:09] places, as I called out, where it is
[00:18:12] going to be stronger. If you want to
[00:18:14] straight up dig into a particular piece
[00:18:17] of software and rip it and copy it and
[00:18:19] just make a clone, you will often run
[00:18:22] into, oh, I don't do that from Fable or
[00:18:24] even maybe from OpenAI. You will not run
[00:18:26] into that issue from Kimmy. And that is
[00:18:28] going to be a specific application that
[00:18:30] is going to be very very popular with
[00:18:32] people who are trying to replace SAS
[00:18:34] solutions and do so affordably. And so I
[00:18:37] can see some of these dots connecting.
[00:18:39] I'd be curious what you're building. Let
[00:18:41] me know in the comments. I'll see you
[00:18:43] next time. Cheers.
