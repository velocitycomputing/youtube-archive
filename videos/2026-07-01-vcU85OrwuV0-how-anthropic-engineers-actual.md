---
video_id: vcU85OrwuV0
title: How Anthropic Engineers Actually Prompt Fable 5
channel: "Nate Herk | AI Automation"
url: "https://www.youtube.com/watch?v=vcU85OrwuV0"
watched_date: 2026-07-01
watched_at: "2026-07-01T12:00:00Z"
watch_count: 1
duration_seconds: 644
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 8
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 644
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Fable 5 is Anthropic's newest flagship model, positioned as significantly more capable than Opus 4.8 but at higher cost ($10/$50 per million tokens). The video outlines six core prompting techniques: provide context explaining *why* you're asking for something rather than just the task; use negative prompting to explicitly state what the model should *not* do; tell it to act once it has enough information instead of over-planning; require verification by asking it to prove claims with evidence; avoid requesting reasoning explanations (which can trigger silent handoffs to Opus 4.8 due to safety guardrails); and keep instructions short and clear rather than verbose. The promotional pricing period ends July 7 and requires usage credits after exhausting 50% of weekly limits.

To use Fable 5 effectively, apply these in practice: structure prompts with context first ("I'm building X, here's who it's for, they need Y—with that context, can you...") rather than bare requests; add guardrails like "don't add features, don't over-explain, don't make assumptions without asking"; build verification into your workflow by requiring the model to show evidence before declaring work done; avoid asking it to explain its own reasoning; match effort levels to task complexity (high as default, x-high for hardest work, low/medium for routine); and use Fable 5 selectively for only 5–15% of your work, falling back to cheaper models for simpler tasks.

## Transcript

[00:00:00] So, we've all waited long enough. Fable
[00:00:01] 5 is finally coming back to us, and it's
[00:00:03] an incredible model. It's the strongest
[00:00:05] one that I've ever used, hands down.
[00:00:07] I've built things like my second brain,
[00:00:08] my AI operating system. So, obviously,
[00:00:10] I've been playing around with this model
[00:00:11] a ton, and I've been trying to figure
[00:00:12] out the best way to use it so that you
[00:00:14] can actually use it efficiently and
[00:00:15] you're not paying for tokens for no
[00:00:17] reason. I've looked at what people have
[00:00:18] said on X. I've listened to Enthropic
[00:00:19] Engineers, and also, I've read through
[00:00:21] this entire documentation right here on
[00:00:23] the best practices for prompting Claude
[00:00:25] Fable 5. So today what I did is I
[00:00:27] distilled all of this into the six most
[00:00:30] simple and effective things that you
[00:00:31] should be doing right now when you are
[00:00:32] prompting Claude Fable 5 to get the most
[00:00:34] out of it. But it's certainly not a
[00:00:35] cheap model. It costs double opus at $10
[00:00:38] per million input tokens and $50 per
[00:00:40] million output tokens. And the other
[00:00:42] thing is it won't always be on your
[00:00:45] Claude plan. And they're calling this a
[00:00:46] promotional period and you can only use
[00:00:48] up to 50% of your weekly limits with
[00:00:50] Cloud Fable 5 at no extra cost. But then
[00:00:53] after that, you would have to switch to
[00:00:54] usage credits. Unfortunately, the
[00:00:56] promotional period ends July 7th. So, we
[00:00:59] only have like 6 days and part of that
[00:01:01] is Fourth of July weekend. Come on.
[00:01:02] Anyways, it will pretty much work
[00:01:03] anywhere though. Cloud desktop app, VS
[00:01:06] Code, include code, you know, wherever
[00:01:07] you want to use it. You can see right
[00:01:08] here, I just got this message that
[00:01:09] Claude Fable 5 is back. And if I go to
[00:01:12] /model, we can see that we do have
[00:01:14] access to Fable. Once again, thank you
[00:01:17] so much. I'm glad that you're back. And
[00:01:19] because this certainly isn't cheap and I
[00:01:21] want to be able to test it a ton for you
[00:01:22] guys, then I hope you'll forgive me for
[00:01:24] pausing for a quick message from today's
[00:01:26] sponsor. Real quick guys, a message from
[00:01:27] the sponsor of today's video, Hyper
[00:01:29] Agent. Hyper Agent has helped me fix a
[00:01:31] major problem that AI has. It's a yes
[00:01:33] man. Ask it about your idea and it tells
[00:01:35] you you're a genius. So on Hyper Agent,
[00:01:37] built by the Air Table team, I built a
[00:01:39] council of agents, a handful of
[00:01:41] different AI agents, each with its own
[00:01:43] persona, each running on its own cloud
[00:01:45] machine with a real browser and tools to
[00:01:47] go do actual research. So, I can just
[00:01:49] simply drop an idea in Slack and they
[00:01:51] will tear into it. One of them will play
[00:01:53] the skeptical investor. One will dig up
[00:01:54] what competitors are already doing. One
[00:01:56] will stress test the numbers. They'll
[00:01:58] all go pull real data and come back to
[00:02:00] me with actual brutally honest feedback.
[00:02:02] Not something like, "Looks great, Nate."
[00:02:04] It'll tell me where stuff is weak and
[00:02:06] why and how to fix it. So, by the time
[00:02:08] they're done, I've got a sharp idea and
[00:02:09] the receipts to back it. And that's the
[00:02:11] part I love because it's not just one
[00:02:13] chatbot nodding along, but it's a team
[00:02:15] that disagrees with me on purpose. And I
[00:02:17] built the whole thing myself. in just an
[00:02:19] afternoon. So, if you want to build your
[00:02:20] own council, links in the description
[00:02:22] with free credits. So, go get roasted.
[00:02:24] Let's get back to the video. So, the
[00:02:25] first thing to understand about Cloud
[00:02:26] Fable 5 is that it is obviously built a
[00:02:28] little bit different than Opus and, you
[00:02:30] know, GPT. So, there's different things
[00:02:32] that it does really good. It follows
[00:02:34] short, clear direction better than older
[00:02:36] models do because it's just better at
[00:02:38] reasoning. And if you spent some time
[00:02:39] playing with it, it just feels like when
[00:02:41] you ask it to do something, it just
[00:02:43] feels like it knows what you're talking
[00:02:45] about and understands it a little bit
[00:02:46] better. Okay, so here are these six
[00:02:48] habits, six things to do. I've tagged
[00:02:50] each of these if they are sort of like
[00:02:52] any model or fable specific. So this
[00:02:54] first one is any model to give it the
[00:02:56] why. Give it the context behind why
[00:02:58] you're doing something. Enthropic says
[00:03:00] that Fable does better when it
[00:03:01] understands your intent. So the context
[00:03:03] lets it connect your task to the right
[00:03:05] information instead of guessing what you
[00:03:07] meant. So instead of saying something
[00:03:08] like, "Write me an email to a client
[00:03:10] about the delay." Say, "I'm working on
[00:03:12] this bigger task and here's who it's
[00:03:13] for. what they need is blah blah blah
[00:03:16] and with that in mind, can you help me
[00:03:18] write an email to this client about the
[00:03:20] delay? And if you have your second brain
[00:03:21] and your whole AIOS set up in the right
[00:03:23] way, that will also prompt it to look
[00:03:25] through specific context files to make
[00:03:27] sure that it has the right information
[00:03:28] that it needs to make all of these
[00:03:30] emails or whatever you're doing feel
[00:03:32] more specific. The next thing, which
[00:03:33] I've also found in general works better
[00:03:35] for all AI models, is to specifically
[00:03:37] negative prompt, specifically tell it
[00:03:39] what not to do. Think about it like
[00:03:41] this. AI is trained on a ton of data.
[00:03:44] So, it literally at its core is trying
[00:03:46] to predict the next word that makes the
[00:03:48] most sense. And sometimes it will try to
[00:03:49] get creative and it will try to do
[00:03:51] things that you didn't ask for. And
[00:03:53] sometimes that's good, but a lot of
[00:03:54] times it's not. So, explain what not to
[00:03:56] do. If you look through this page
[00:03:58] prompting Claude Fable 5, when you start
[00:04:00] to go through here, you will see that
[00:04:01] they do that right here. When you have
[00:04:03] information to act on, act. Do not do
[00:04:06] this. If you are weighing a choice, give
[00:04:07] a recommendation, but do not do this.
[00:04:10] Here's another example. Don't add
[00:04:11] features. Don't do this. Don't do this.
[00:04:13] Don't do this. Don't do this. Do the
[00:04:15] simplest thing that works well. The way
[00:04:17] I like to think about that is if you
[00:04:18] were explaining a task to an intern, you
[00:04:20] would tell them specific things to not
[00:04:22] do because they don't understand the
[00:04:23] process yet. They're trying to learn it.
[00:04:24] So instead of saying something like,
[00:04:25] "Take a look at this problem and handle
[00:04:27] it." You might say, "When I'm describing
[00:04:29] a problem or asking a question, the
[00:04:30] deliverable is your assessment. Report
[00:04:32] what you find and stop. Don't fix, send,
[00:04:35] edit, or delete anything until I say
[00:04:36] go." I feel like the models have
[00:04:38] actually evolved a little bit because I
[00:04:39] used to find that negative prompting
[00:04:41] didn't work as well then just being very
[00:04:43] specific about what I wanted it to do.
[00:04:45] But lately, the more I've been negative
[00:04:47] prompting, the more I found that it
[00:04:48] tends to work pretty well. So, if you
[00:04:50] guys want to access this full guide
[00:04:51] where you can see this full writeup, you
[00:04:53] can do so by joining my free school
[00:04:54] community. The link for that will be
[00:04:55] down in the description. All you have to
[00:04:56] do is go in here, go to the classroom,
[00:04:58] and click on all YouTube resources, and
[00:04:59] you'll find everything in there. Okay,
[00:05:01] the next one also works for any model.
[00:05:03] This is to let it act once it has
[00:05:05] enough. So stop it overplanning. I
[00:05:07] actually don't even very often use plan
[00:05:10] mode inside of cloud code anymore. I
[00:05:11] know that's something that I used to say
[00:05:12] always start in plan mode, but I don't
[00:05:14] do that anymore. I basically have my own
[00:05:16] plan mode that I have it go through
[00:05:18] until it's ready to act. So instead of
[00:05:20] saying research everything and make a
[00:05:21] full plan before you do anything, you
[00:05:23] can say more stuff like when you have
[00:05:25] enough information to act then act. If
[00:05:27] you guys remember that is basically the
[00:05:29] example that we read right here, which
[00:05:30] is the first thing that Claude Fable 5
[00:05:32] doc says because individual requests on
[00:05:35] hard tasks can run for many minutes at
[00:05:37] higher effort settings, especially when
[00:05:39] the task requires gathering context,
[00:05:41] building, self-verifying, essentially
[00:05:42] just building a plan. And another big
[00:05:44] piece of this here is thinking about the
[00:05:46] different effort levels. You know, you
[00:05:48] can do low, medium, high, extra high.
[00:05:50] You've got all these different effort
[00:05:51] levels and you want to make sure that
[00:05:53] you're matching the effort levels to the
[00:05:54] correct task. They recommend to use high
[00:05:56] as the default for most tasks, use X
[00:05:58] high for the most capability sensitive
[00:06:00] workloads, and medium or low for routine
[00:06:03] work. And it's quite interesting because
[00:06:04] if you look at Fable 5 versus Opus 4.8
[00:06:07] with different reasoning levels as well
[00:06:09] as the cost, you can see that they get
[00:06:11] into this area where they're similar,
[00:06:13] but Fable 5 on low, even though it's
[00:06:16] similar to Opus 4.8 on X high and max,
[00:06:18] is cheaper. So really starting to
[00:06:20] experiment with different effort levels
[00:06:22] and feeling when you need to use certain
[00:06:24] ones is going to be a very important
[00:06:26] skill along with understanding what
[00:06:29] tasks to use, what model for in general.
[00:06:31] Because if you're using Fable 5 for
[00:06:32] everything, that is almost 100%
[00:06:34] overkill, especially when you're getting
[00:06:35] into the usage credit territory with
[00:06:36] Fable 5, you really don't need it for
[00:06:39] that many things. You probably more
[00:06:40] realistically only need to reach for
[00:06:42] Fable like 5 to 15% of the time. Number
[00:06:45] four, which I think is probably the most
[00:06:46] important one, is to make it prove it.
[00:06:48] And this is for any model. Like I said
[00:06:50] once again, sometimes models will tell
[00:06:52] you that they're done, but they're not.
[00:06:53] Or maybe they are done, but they haven't
[00:06:55] verified things. The whole point is if
[00:06:57] you were to give work to a human and
[00:06:59] they come back with, you know,
[00:07:00] something, some output, you would have
[00:07:02] to review that yourself. You want to get
[00:07:04] it to the point where you trust this
[00:07:06] person or this model so much because
[00:07:07] you've baked in these verification loops
[00:07:09] that when it hands you something, you
[00:07:11] probably still should check it, but you
[00:07:12] don't feel like you have to as much
[00:07:14] because you know that it already has
[00:07:15] checked its own work 2, three, four,
[00:07:17] maybe even five times and it's tested
[00:07:19] and fully verified that everything's
[00:07:21] working the way that it should be. So
[00:07:22] instead of just asking, is this done and
[00:07:24] is it working? You could say before you
[00:07:25] tell me something is done, point to the
[00:07:27] result that proves it. Only report work
[00:07:29] you can show evidence for. If something
[00:07:30] isn't verified, say so plainly instead
[00:07:33] of guessing. And this is something that
[00:07:34] would be really good to work into all
[00:07:35] your skills, all of your agents, all of
[00:07:38] your, you know, claim MD files rather
[00:07:40] than always just throwing this at the
[00:07:41] end of every prompt. Okay, number five.
[00:07:43] And this one is more fable specific,
[00:07:45] which is stop asking it to show its
[00:07:47] reasoning on Fable 5. A standing explain
[00:07:50] your reasoning line, especially in the
[00:07:51] system prompt, can trigger a refusal and
[00:07:53] it can hand your task to Opus 4.8. Now,
[00:07:56] if you guys didn't know, and I'll cover
[00:07:57] this a little bit more at the end of
[00:07:58] this video, but because Fable 5 has
[00:08:01] concerns of, you know, jailbreaking, and
[00:08:03] it's already a lesser model of Mythos 5,
[00:08:06] we have to be careful about making sure
[00:08:07] that we don't trigger Opus because
[00:08:09] basically there's a bunch of safety
[00:08:11] guardrails into Fable that will route it
[00:08:13] to a less capable model like Opus if it
[00:08:15] thinks that the intent of your request
[00:08:17] might be malicious or anything like
[00:08:19] that. So, for some reason, if you are
[00:08:21] trying to get Fable to show its
[00:08:22] reasoning, it might revert you down to
[00:08:24] Opus 4.8. So that's why we put this one
[00:08:27] in here that is a fablesp specific
[00:08:28] prompting rule. And then number six is
[00:08:30] to say less not more which kind of
[00:08:33] sounds a little bit counterintuitive
[00:08:34] because typically we've thought the more
[00:08:36] context that you give these models the
[00:08:38] better. But because Fable is so
[00:08:40] intelligent now and especially if you
[00:08:41] have it wrapped up in a good environment
[00:08:43] with you know context and tools and
[00:08:45] skills and everything like that a short
[00:08:47] instruction can now steer just as well
[00:08:49] as spelling out most of the rules by
[00:08:51] name. And this is not a contradiction
[00:08:52] with tip one. adding the why, if you
[00:08:54] remember back here, give it the why,
[00:08:56] give it the context. Still doesn't mean
[00:08:57] to bloat everything out. So instead of
[00:08:59] saying like, hey, rule one is be
[00:09:00] concise, rule two is do this, rule three
[00:09:02] is do this, just say more something like
[00:09:04] lead with the outcome. Keep it simple
[00:09:06] and pause only when the work truly needs
[00:09:08] me. And that's how you can start to wrap
[00:09:09] all of these other tricks into your
[00:09:12] system files, your memory files, your
[00:09:14] cloudmomd files, and your skills and all
[00:09:16] of your prompts moving forward so that
[00:09:18] you can make sure you're getting the
[00:09:19] most out of this incredible model, Cloud
[00:09:21] Fable 5. So, I wanted to wrap up here
[00:09:23] with what I talked about very briefly,
[00:09:24] which is what happens when Fable hands
[00:09:26] off to Opus 4.8 or whatever model in the
[00:09:29] future it ends up handing off to. If
[00:09:31] this is still the case, Fable will run a
[00:09:33] quick safety check before it goes ahead
[00:09:35] and answers your request. If it realizes
[00:09:37] that it might be within a certain
[00:09:39] bucket, then it will push that to Opus
[00:09:41] 4.8. If it looks like anything that has
[00:09:43] to do with hacking or dangerous biology
[00:09:45] or asking the model to reveal its own
[00:09:47] private reasoning, then it might shoot
[00:09:49] that off. And when that happens, it
[00:09:52] won't show you. It will silently route
[00:09:54] to Opus. If you are building on the API,
[00:09:56] it will send back a response that shows
[00:09:57] you that was Opus, but otherwise, you
[00:09:59] may not notice it. Luckily, when you do
[00:10:01] it, it should be routing to Opus 4.8, so
[00:10:04] you're not paying as much as Fable.
[00:10:06] Otherwise, that would be pretty bad. And
[00:10:07] so, just be aware of that. You can avoid
[00:10:09] it by obviously doing something like
[00:10:10] this that I mentioned, but also, you
[00:10:13] know, not asking it to help you do
[00:10:15] things that are clearly malicious or
[00:10:17] suspicious. So, please feel free to go
[00:10:20] ahead and go to this documentation and
[00:10:21] read through it. It has a lot of golden
[00:10:23] nuggets. But that's going to do it for
[00:10:24] this one. So, hopefully you guys enjoyed
[00:10:25] or you learned something new. If you're
[00:10:27] interested in learning more about those
[00:10:28] agent loops kind of verification that I
[00:10:30] was talking about earlier, then
[00:10:31] definitely check out this video right
[00:10:32] here. I pretty much explain it. I give
[00:10:34] it some examples and I think that doing
[00:10:36] this technique with Fable 5 will be
[00:10:38] super awesome. So, hopefully I'll see
[00:10:40] you guys over there. Otherwise, thanks
[00:10:41] for making it to the end of the video
[00:10:42] and thanks everyone.
