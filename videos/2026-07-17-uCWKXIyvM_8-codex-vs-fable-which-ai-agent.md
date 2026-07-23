---
video_id: uCWKXIyvM_8
title: "Codex vs Fable: Which AI Agent Picked the Better Problem?"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=uCWKXIyvM_8"
watched_date: 2026-07-17
watched_at: "2026-07-17T12:00:00Z"
watch_count: 1
duration_seconds: 728
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 63
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 728
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video compared Codex and Fable as autonomous problem-solvers by asking each to audit the creator's Slack and files, identify a pain point, and propose an automation. Codex picked a practical but narrow problem: streamlining the research-to-scripting handoff to save time on story selection. Fable picked a more strategic problem: building a pre-pipeline tool to refine and rank story ideas before committing to them. While Codex delivered reliably in one error-free run, Fable demonstrated superior problem recognition—identifying the real leverage point despite being difficult to work with (multiple permission dialogs). The takeaway: Codex gravitates toward bounded, solvable problems even with unlimited tokens, while Fable thinks more strategically about business impact.

The creator released a reusable skill that automates this discovery process for users: point it at your files and Slack (with safeguards you define), and it audits your actual behavior patterns to recommend automation solutions tailored to your specific pain points. The skill works with both Fable and Codex; users can run both concurrently to compare perspectives, then use cheaper Codex to implement the better-defined problem. The actionable move: stop trying to guess what you need to automate—ask an AI agent to find it for you by analyzing your existing workflow, then build the tool.

## Transcript

[00:00:00] I cannot wait to give you this video,
[00:00:01] because this is the Fable versus Codex
[00:00:05] 5.6 knockdown, drop-out fight video I've
[00:00:08] been waiting to do. So, what did I do? I
[00:00:11] asked it to automate something that I
[00:00:14] did not tell it to do. In other words,
[00:00:16] part of the challenge in 2026 is to ask
[00:00:19] your AI to pick the problem. You don't
[00:00:23] just ask it to pick the prompt. You
[00:00:24] don't just ask it to pick the tool. You
[00:00:26] ask it to pick the problem. And so, what
[00:00:28] I did is I said, "Codex, Fable,
[00:00:31] freehand. You can look at all of my
[00:00:34] local files. You can look at all of my
[00:00:35] Slacks. Anything you want to look at
[00:00:38] that describes my business process. And
[00:00:41] when you do that, you are obligated to
[00:00:44] come back to me with a problem
[00:00:46] definition.
[00:00:47] And you're obligated to come back to me
[00:00:49] with a solution and automation. And then
[00:00:51] when I was working on this, and I did
[00:00:52] this sort of knockout, and I'm going to
[00:00:54] give you the results. I'm going to give
[00:00:55] you the results. When I did this, I
[00:00:58] realized
[00:00:59] that I could turn this into a reusable
[00:01:02] skill. And so, that's what I'm putting
[00:01:04] together for you today. You're going to
[00:01:05] see it today. It's It's a lot of fun to
[00:01:07] make. It's a lot of fun to use. Because
[00:01:09] what I find is most of us have a
[00:01:12] different verbal understanding of the
[00:01:15] problems in our business than our
[00:01:17] behavior shows. Especially if you have a
[00:01:19] team that you work with. Whether you're
[00:01:21] a leader or an individual contributor,
[00:01:23] you may not realize all of the mess that
[00:01:26] goes on around you. This is your biggest
[00:01:28] pain point. And you know what's
[00:01:29] fascinating? Codex and Fable picked
[00:01:32] different pain points. So, sit back.
[00:01:34] We're going to go through the full Codex
[00:01:37] versus Fable results. We're going to dig
[00:01:40] into why they made the choices they did.
[00:01:42] And we're going to talk about the skill
[00:01:44] that I'm releasing that helps you get
[00:01:47] your automations done, whether in Fable
[00:01:49] or in Codex. Both will work. And I'll
[00:01:51] explain why and how. And I'll So, So,
[00:01:53] basic All right. Let's jump into Codex
[00:01:56] first. Pros first for Codex. I love the
[00:01:59] Codex harness. I've said it before, but
[00:02:01] this gives me a chance to explain why.
[00:02:03] When I give Codex a job and I give Codex
[00:02:06] Ultra a job, it just goes and does it.
[00:02:09] Now, Codex Ultra is a special setting
[00:02:11] you have to go and fish out of the
[00:02:12] interface. If you look, you have to go
[00:02:15] and manually select it and it warns you
[00:02:16] it's going to burn a lot of tokens. One
[00:02:18] of the interesting things about Chat GPT
[00:02:20] work and Codex is that together they've
[00:02:22] been gaining about a million users a day
[00:02:25] in just the last week. That's a huge
[00:02:27] scale up. And they are now between Chat
[00:02:30] GPT work and Codex, more people are
[00:02:33] using that product set than are using
[00:02:35] Claude code. And so it's been gaining a
[00:02:37] tremendous amount of popularity and I
[00:02:39] can see why. I can give Codex a
[00:02:42] challenge like this. Basically, I told
[00:02:45] it, one, you have to go and discover
[00:02:50] my Slack, all of the places I work. Two,
[00:02:54] you have to go and do that
[00:02:57] and write an automation script
[00:03:00] afterward. And three, you have to tell
[00:03:03] the story of why this happened and why
[00:03:04] you picked what you chose. So there's
[00:03:06] multiple tasks here and I didn't give it
[00:03:08] a problem. It had to pick the problem.
[00:03:10] Now, Fable was a complete hassle to work
[00:03:12] with. I just got to be honest, right?
[00:03:13] This is This is what you come to this
[00:03:14] channel for. I'm not going to pull my
[00:03:15] punches. Fable was a complete hassle to
[00:03:18] work with. Multiple permission
[00:03:20] dialogues, but I waited through that. I
[00:03:22] really wanted to see what Fable would
[00:03:24] come up with. And Fable in the end, once
[00:03:27] it ground through the problem, came up
[00:03:29] with a much, much better problem.
[00:03:33] It found a much more interesting problem
[00:03:35] because what what Fable realized
[00:03:37] strategically, and this is where like
[00:03:39] there's that big model smell. I don't
[00:03:40] know how else to put it. Fable had the
[00:03:42] strategic sense to realize that one of
[00:03:45] the hardest jobs in the storytelling
[00:03:48] business is finding the right story to
[00:03:51] tell. Finding the thing that matters to
[00:03:53] talk about in a world of infinite AI
[00:03:56] stories. And I get asked this all the
[00:03:57] time, "Nate, how do you pick your
[00:03:58] stuff?" And to be honest with you, it's
[00:04:01] a lot of pain, and it's a lot of sweat
[00:04:03] and blood and tears and thinking about
[00:04:05] what you guys want to hear and what
[00:04:07] makes sense and asking you guys in some
[00:04:08] cases, and I just kind of got to go with
[00:04:10] my instinct. It's it's been very much
[00:04:13] instinctive.
[00:04:15] And Fable jumped into that and said, "I
[00:04:17] bet I can build something that helps
[00:04:20] with pre-pipelining." Basically, helping
[00:04:23] you to refine ideas so that they are
[00:04:25] easier to choose. Wow, there's leverage
[00:04:29] in that idea. That idea is not a dry
[00:04:33] handoff concept. That idea has legs to
[00:04:36] it. And unfortunately, and this is where
[00:04:38] the twist comes, it came back with a
[00:04:40] much, much too narrow definition of the
[00:04:43] problem. Because you see, Codex audited
[00:04:45] my media slack and the way I tell
[00:04:46] stories and how I make these stories
[00:04:49] come alive for folks. And it came up
[00:04:51] with the most boring possible
[00:04:53] interpretation of the problem. Now, it
[00:04:54] may be real, and it may be a real
[00:04:56] problem, but it's a typically
[00:04:58] Codex-flavored definition of the
[00:05:00] problem. And this is my con with Codex,
[00:05:02] and that shows in the kinds of problems
[00:05:05] it picks when it has an open-ended
[00:05:08] problem space to work in. It can pick
[00:05:10] any problem, right? Like I was like,
[00:05:12] "Any size, you have a completely free
[00:05:14] hand, you can go after it."
[00:05:16] And
[00:05:17] what it chose to pick was, "Hey, can we
[00:05:20] make the handoff package better so that
[00:05:22] Nate can get into scripting faster?" So,
[00:05:24] all of the research can be done and Nate
[00:05:26] can figure out what the story is that he
[00:05:28] wants to tell. But,
[00:05:30] it's not the most painful problem right
[00:05:32] now.
[00:05:33] It's not the most challenging problem in
[00:05:35] the business right now. It is a problem
[00:05:37] that Codex found that was voiced, that
[00:05:41] Codex could wrap its arms around.
[00:05:44] And that is a tremendous clue if you're
[00:05:47] a Codex user. That is something you can
[00:05:49] take to the bank. Because when you give
[00:05:52] Codex
[00:05:53] a free rein,
[00:05:55] and you say, "Go and pick any problem
[00:05:56] you want." Codex is going to keep itself
[00:05:59] bounded. Even in ultra mode, when it has
[00:06:02] a tremendous number of tokens to burn,
[00:06:04] and I have been burning multiple
[00:06:05] billions of tokens a day with Codex, it
[00:06:08] still picks bounded problems. Now, it
[00:06:10] gets it done. It got all the way done.
[00:06:12] It was finished. It was one run, zero
[00:06:15] issues. But that's not enough. I need a
[00:06:18] better problem nose. But that being
[00:06:20] said,
[00:06:21] Fable is an amazing, amazing strategic
[00:06:24] thinker. It did a great job at
[00:06:26] understanding the intent behind the
[00:06:29] prompt, and discovering a problem that
[00:06:32] was worth going after. And I love that
[00:06:34] about it. And I'm excited because
[00:06:37] you know, Codex's tool that it built is
[00:06:39] fine. I will probably use it.
[00:06:42] Fable's tool is now essential. I've got
[00:06:45] to have that tool. I can't not have that
[00:06:47] tool. And that is the bar that I want to
[00:06:49] set. I'm not interested in AI agents
[00:06:52] that build tools that are okay, it's
[00:06:55] fine. Because too many of us got open
[00:06:58] claw, and then we didn't do anything
[00:07:00] with it. And that's the reason why I'm
[00:07:03] making this video. This video is for
[00:07:06] people who don't realize that the open
[00:07:10] claw problem, the what do I do with my
[00:07:12] open claw problem, is solvable by AI.
[00:07:16] You don't have to know what you need to
[00:07:17] do to get value out of your agents. You
[00:07:20] can just tell the agent, "Look at my
[00:07:23] behavior, pick an automation
[00:07:25] opportunity, and let's go." And that
[00:07:27] brings me to the build. So, I realized,
[00:07:30] as I went through this process, yeah,
[00:07:32] sure, this is fine for me. But for you
[00:07:35] guys, you deserve to have an automation
[00:07:38] solution that's kind of like a magic
[00:07:41] easy button. And it turns out that what
[00:07:44] you need to get that done is a skill
[00:07:48] that puts safeguards in place that lets
[00:07:49] you put walls in. I had a personal slack
[00:07:52] I didn't want my AIs to touch, so I put
[00:07:53] a wall in there. Said you can't touch
[00:07:55] that in the course of this research that
[00:07:58] allows it to expand its understanding of
[00:08:00] the problem. That allows it to dig in to
[00:08:04] the first, second, third level of
[00:08:05] causation, understand the leverage in
[00:08:07] the problem space, pick strategically,
[00:08:11] and then after it root causes what's
[00:08:13] really going on in your business or your
[00:08:15] project or your personal life, come back
[00:08:18] with an automation recommendation, which
[00:08:20] is very 2025. And then what's 2026? Come
[00:08:24] back with a tool that it built to fix
[00:08:27] that for you. And I've included, because
[00:08:30] I learned this through this process with
[00:08:32] Codex, I've included a special section
[00:08:35] in this script reminding the AI not to
[00:08:38] think small, and reminding it that when
[00:08:40] thinks big, it needs to build
[00:08:43] completely. And so if it's going to
[00:08:44] build something that's a solution for
[00:08:46] you, it needs to build it all the way
[00:08:48] through and think about security. It
[00:08:50] needs to think about how you
[00:08:52] authenticate if that's what needs to
[00:08:54] happen. It needs to think about how you
[00:08:57] get business value out of this. Now, I
[00:09:01] don't know what you're going to build
[00:09:02] with this. That's the magic. The whole
[00:09:04] point of this is that because AI is
[00:09:07] non-deterministic,
[00:09:09] I can launch effectively an automagic
[00:09:12] skill that audits your unique
[00:09:15] fingerprint. I never see it. The data
[00:09:17] never comes to me, right? It's all in
[00:09:19] your AI instance.
[00:09:21] And it will build for you based on the
[00:09:23] skill an automation solution that's
[00:09:25] neatly tuned to the most pressing
[00:09:27] problems in your business, your personal
[00:09:29] life, your side project, whatever you
[00:09:31] have that comes to mind. And you can
[00:09:33] point it, right? When you write the
[00:09:34] prompt to to with this, you can say,
[00:09:36] "This is focused on this side project."
[00:09:38] Or "This is focused on this business
[00:09:39] area that I'm working on." Or "This is
[00:09:40] my personal life and this is what I care
[00:09:42] about." And so, I call it an auto magic
[00:09:45] button for automation. But, because it
[00:09:47] got into the problem space, because I
[00:09:49] saw what it was wrestling with, and
[00:09:51] because I saw what Fable was working on,
[00:09:54] I now have the option to run hard and
[00:09:57] get a full solution to my pre-pipeline
[00:09:59] concept, which Fable came up with, out
[00:10:02] of Codex, which is cheaper. In other
[00:10:04] words, if you run this simultaneously
[00:10:07] across Fable and Codex, you're going to
[00:10:10] get different responses, different
[00:10:12] thinking, a diversity of perspective,
[00:10:14] and you're going to be able to come back
[00:10:16] and say, "This is the winner, and this
[00:10:18] is how I want to implement it." And yes,
[00:10:20] Ringer will help you implement it well,
[00:10:22] because Ringer's a lot cheaper to run
[00:10:24] than just going with Fable, for example.
[00:10:26] It was so much fun to run. I'm not going
[00:10:28] to lie. One of the things that I want
[00:10:29] people to realize with AI is that it is
[00:10:32] fun to do this stuff. It is fun. It is
[00:10:35] fun to realize I don't have to carry the
[00:10:37] load anymore of figuring out where all
[00:10:40] the problems are. I can ask AI to help.
[00:10:42] And I can disagree, and I can agree, and
[00:10:44] I can align, and I can shape a
[00:10:46] perspective, and then I can build a
[00:10:48] tool, and that can all happen in a
[00:10:51] single prompt. A single prompt that just
[00:10:54] says, "Here, use this skill and go after
[00:10:56] this." And that's what I'm releasing.
[00:10:57] I'm releasing it as a skill because
[00:10:59] skills are so easy to sort of trade and
[00:11:01] interchange and understand and learn
[00:11:02] from and evolve over time. And I just
[00:11:06] want it to be something that you can use
[00:11:08] as a framework to quickly evolve. And
[00:11:10] so, that's what I'm doing. I'm excited
[00:11:12] to have it out there. Please, please,
[00:11:14] please, if this inspired you, tell me
[00:11:16] what you're automating. Tell me what you
[00:11:18] told your Codex to go and get. Tell me
[00:11:20] what you told your Claude to go and get.
[00:11:21] If you split tested them, which one did
[00:11:24] you prefer? Because I got to be honest,
[00:11:26] when I baked all of it out all the way
[00:11:27] through, I am divided. I loved Fable's
[00:11:32] strategic perspective. I loved it so
[00:11:35] much and I think that if, you know, gun
[00:11:37] to my head, I had to pick, I would pick
[00:11:39] Fable because that strategic perspective
[00:11:41] gives me leverage that I can work
[00:11:43] through with Codex, that I can work
[00:11:44] through with Ringer, etc.
[00:11:47] But, the Codex harness is just so nice
[00:11:49] that as an everyday driver, I'm burning
[00:11:51] way more tokens there because it's fast,
[00:11:54] it's dependable, it doesn't give me
[00:11:55] those annoying pop-ups, and for most
[00:11:58] work, if it's not problem recognition, I
[00:11:59] can just go after it. What do you think?
[00:12:01] Tell me in the comments. Cheers.
