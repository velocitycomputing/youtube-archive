---
video_id: suY66oTDn0s
title: Claude Fable 5 Bossed 20 Cheap AI Agents. The Whole Site Cost $8.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=suY66oTDn0s"
watched_date: 2026-07-08
watched_at: "2026-07-08T22:23:09Z"
watch_count: 1
duration_seconds: 1157
source: youtube-history-browser
added_date: 
history_label: Today
history_order: 1
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1157
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video demonstrates a multi-agent system where Claude Fable 5 ($50/million tokens) orchestrated four cheaper model families to rebuild an accessible website for a deaf-blind author in 1-2.5 hours for $8 total—versus $85-105 if using Fable 5 alone. The system caught four escalating failures autonomously: hallucinated quotes (fixed by a checking agent comparing verbatim text), accessibility-breaking shortcuts by workers, a CSS dark-mode bug written by Fable itself (caught twice), and an incorrect checker that was overruled when escalated to Fable. The key pattern: staff work like an org chart—expensive models write specs and review, cheap models execute with clear briefs—and every task includes an independent checking agent that validates output without trusting the worker's report.

You can adopt this immediately by defining your success criteria upfront (e.g., "accessibility constitution" with WCAG standards) and testing every build round against it, then routing execution to cheaper models with Fable 5 as judge. The speaker emphasizes this isn't novel research but a simple recipe now available to non-engineers; Elsa, who doesn't use the terminal, validated the final site was superior to six days of single-agent work. If you have ambitious work that feels too big for AI, structure it with multiple agents and checkpoints rather than hoping one frontier model handles everything—you can likely complete it in hours at 1/10th the cost while getting better results.

## Transcript

[00:00:00] The number one thing that people tell me
[00:00:02] about AI agents is that they cannot
[00:00:04] trust them, that they hallucinate. And
[00:00:06] you know what? You're right. They do.
[00:00:08] Yesterday, one of mine hallucinated my
[00:00:11] own wife's words while it was rebuilding
[00:00:14] her website. And here's the thing. I
[00:00:16] didn't have to correct it. I didn't have
[00:00:18] to fix it. I didn't have to lift a
[00:00:20] finger because my multi- aent system
[00:00:24] caught it for free. And it not only
[00:00:26] caught it, it got it fixed. The site
[00:00:28] shipped and it made a better site. That
[00:00:31] multi-agent swarm that I'm going to show
[00:00:32] you made a better site in one hour than
[00:00:35] I was able to make in six days with
[00:00:37] hands-on AI work with Codeex last month.
[00:00:40] So, did the hallucination still happen?
[00:00:43] Yeah. Yeah, it did. Is that increasingly
[00:00:45] not the point? Yeah, it's not the point
[00:00:47] anymore. The larger takeaway for you is
[00:00:50] that running a team of AI agents has not
[00:00:53] only never been easier, it's actually
[00:00:55] become something that any of us can do
[00:00:58] and it's become something that allows us
[00:01:00] to answer one of the hardest and most
[00:01:02] bedeing problems in AI work today. How
[00:01:05] do you get models to do real big work
[00:01:08] without lying and hallucinating along
[00:01:10] the way? So, let's jump into it. How to
[00:01:12] structure your team of agents, which
[00:01:13] model gets which job, and how to think
[00:01:15] about it. how to check everything
[00:01:17] without reading any of the individual
[00:01:19] mistakes, errors, and results of those
[00:01:22] models. And most important, how to
[00:01:24] prompt for work this big. Along the way,
[00:01:26] you're going to watch the system catch
[00:01:28] four distinct failures. Each one is
[00:01:30] actually bigger than the last. I don't
[00:01:32] have to catch any of them. And the last
[00:01:34] one, it's a little bit of a surprise. I
[00:01:36] cannot wait to show you. And I'm going
[00:01:37] to show you at the end also a full guide
[00:01:40] with a one-click setup that gets your
[00:01:41] own agent running in this exact
[00:01:43] orchestration pattern. And that's it's
[00:01:45] not a flex, guys. It's actually a
[00:01:47] recipe. Multi- aent setups are a recipe
[00:01:49] and you can grab that. So, I'll put that
[00:01:52] link in the video and we're going to get
[00:01:54] into it. I'm going to show you the full
[00:01:55] setup and how it works. The website of
[00:01:57] Elsa Hunison. She's a deaf blind author.
[00:01:59] She's a Hugo winner, subject of the PBS
[00:02:01] documentary. And this is going to matter
[00:02:04] later. She has been doing accessibility
[00:02:06] work professionally for over a decade.
[00:02:07] Her new book, Dear Blind Lady, launches
[00:02:09] in October, which means her website is
[00:02:11] not a hobby at this point. It's a
[00:02:12] storefront for launch season. And I'm
[00:02:14] telling you all of this with her
[00:02:15] permission because she's my wife and
[00:02:17] it's her story too. Now a month ago,
[00:02:19] Elsa rebuilt this site herself and you
[00:02:21] can see how it used to look. She used
[00:02:23] codeex 5.5 one agent and she sat with
[00:02:26] it. She steered it and you know to be
[00:02:28] honest that's the state-of-the-art for
[00:02:29] how a lot of capable people use AI
[00:02:31] today. And it took her 6 days to work
[00:02:34] through that. Now 6 days working with an
[00:02:36] AI as a professional who knows what she
[00:02:38] wants and at the end of it also told me
[00:02:40] she still had a fix list. So, it's six
[00:02:42] days working with an AI back and forth
[00:02:44] in the midst of everything else like so
[00:02:46] many of us do and still not quite
[00:02:48] getting what we want. But to be fair,
[00:02:51] the codeex built website shipped. It was
[00:02:53] a ton better than it was before. And she
[00:02:55] was pretty happy with it until I said,
[00:02:56] "Please, can we use this as an
[00:02:58] experiment for my multi- aent system?
[00:03:01] Can I see if I could beat it?" And she
[00:03:03] kindly said, "Yes." Now, as an
[00:03:04] accessibility professional, you might
[00:03:06] think, well, the original website at
[00:03:08] least had perfect accessibility. But
[00:03:11] anyone who is a professional will know
[00:03:13] that they never have time for their own
[00:03:15] stuff. And that was true for this
[00:03:16] website, too. Elsa had a long fixed list
[00:03:18] around accessibility that she just
[00:03:20] hadn't had time to get to for her own
[00:03:22] site. Even though she knows the standard
[00:03:23] cult, she could write the checklist from
[00:03:25] memory, but the hours just weren't
[00:03:27] there. If that sounds familiar to you,
[00:03:29] you're not alone. So yesterday, the team
[00:03:31] of agents that we hired for this, and
[00:03:34] this is the way I think about it now. We
[00:03:35] basically have a team of agents that
[00:03:37] work for us. They took her site from a
[00:03:39] blank repo to production. And the build
[00:03:41] looked like this. We have a boss. We
[00:03:44] have a foreman. That's Claude Fable 5.
[00:03:46] Claude Fable 5 never wrote a single
[00:03:48] page. Instead, the work was staffed by
[00:03:50] four cheaper model families that did all
[00:03:52] the work. They wrote everything. They
[00:03:53] had 34 tasks. Every single one was
[00:03:55] checked not by me, not by Elsa, but by a
[00:03:58] machine. And 12 of those tasks were
[00:04:01] caught and sent back for rework. Now,
[00:04:03] the hallucination I told you about that
[00:04:04] got handled as the first of four big
[00:04:06] mistakes along the way. We're going to
[00:04:08] get to the other three in a minute. And
[00:04:09] what Elsa said when she saw the finished
[00:04:11] site, and I'll and I'll share that with
[00:04:12] you at the end. It made my whole day. It
[00:04:15] was one of the reasons I do what I do.
[00:04:17] So, I'll I'll share that at the end. All
[00:04:18] right. I told you I think of these
[00:04:20] agents as teams that were hiring. And
[00:04:21] so, the first job that I had to do was
[00:04:24] do some hiring for agents. Two of the
[00:04:26] models I wanted for speed had never
[00:04:28] worked in a swarm system that I had put
[00:04:31] together before. So, I had to give them
[00:04:33] an audition, an actual try out task. I
[00:04:35] asked them to write five tagline
[00:04:37] candidates for the book's pre-order
[00:04:38] page. Exactly five, 12 words or fewer in
[00:04:41] the script that automatically rejected
[00:04:43] cheesy words, right? Inspiring stuff
[00:04:45] that Elsa would reject because it just
[00:04:47] didn't match her voice. One model passed
[00:04:49] this entire exercise in just 29 seconds.
[00:04:53] And both models made the team. And by
[00:04:55] the way, the winning line for the
[00:04:56] record, "You didn't know you needed
[00:04:58] this. Pre-order before she changes her
[00:05:00] mind." A little bit snarky. and else it
[00:05:02] is snarky. Now, why am I showing you a
[00:05:04] try out? Because it tells you what this
[00:05:06] system actually is. It's not one genius
[00:05:09] AI doing everything. It's an org chart.
[00:05:12] And the org chart is the first
[00:05:14] structural move that you need to
[00:05:16] understand to replicate this at home.
[00:05:18] Here's the thing about AI models in mid
[00:05:20] 2026. Intelligence comes in price tiers
[00:05:24] now, and the spread is just absolutely
[00:05:26] insane. At the top, you have Claude
[00:05:28] Fable 5. that costs 50 bucks per million
[00:05:30] tokens of output and it's worth it for
[00:05:32] the right work. At the bottom you have
[00:05:34] models like GLM 5.2 that can code all
[00:05:36] day for pennies. So you staff this work
[00:05:39] the way any functional company staffs.
[00:05:41] The expensive mind is taking the boss
[00:05:43] role. It writes the specs. It designs
[00:05:45] the system. It reviews the work. It
[00:05:47] rules on disputes. And it never ever
[00:05:49] codes. The coding work goes to the
[00:05:50] cheapest worker in the stack as long as
[00:05:53] they have clear specs. Now, I want to
[00:05:55] give you a really honest breakdown of
[00:05:57] how much I saved doing that. So, in
[00:05:59] total, this project burned between 11
[00:06:01] and 13 million tokens. If I run those
[00:06:04] same tokens through the Fable model all
[00:06:07] by itself, same job, same afternoon, I
[00:06:10] am estimating between $85 and $105 in
[00:06:14] costs. Now, if I run it through the org
[00:06:16] chart that I just showed you, it's $2.74
[00:06:19] on the meter. It's five to seven bucks
[00:06:22] all in once you factor in the audio,
[00:06:24] which I'll get to in a moment. And I'm
[00:06:26] going to round it up to eight because
[00:06:27] I'd rather round against myself. It's
[00:06:29] the same work. It's a 10 plus multiple
[00:06:32] price gap and nothing got worse. In
[00:06:35] fact, Fable did more judging, not less.
[00:06:37] And once you see that, I certainly read
[00:06:40] every company torches its AI budget
[00:06:42] stories really differently because now I
[00:06:44] have a really simple question. What were
[00:06:46] you doing with your routing? Who was
[00:06:48] doing all the coding for you? Almost
[00:06:50] every horror story has the same answer.
[00:06:52] Somebody had not built a router and was
[00:06:55] allowing engineers to assign the most
[00:06:57] expensive model to do everything. And
[00:06:59] that is not an AI problem. That is an
[00:07:01] org design problem. And you literally
[00:07:04] just watch the fix. But hold on. Cheap
[00:07:06] workers doing the work unsupervised
[00:07:08] ought to worry, right? That's exactly
[00:07:10] what you worry about. Pattern three, and
[00:07:12] I'm going to say it in one sentence.
[00:07:14] Every single task ships with a checking
[00:07:17] agent job that executes the work and
[00:07:20] does not consider the worker agents own
[00:07:23] report at all. So builds might get
[00:07:25] compiled. Uh cited URLs can get
[00:07:28] refetched and rematched. Audio files can
[00:07:30] get reme-measured against the text.
[00:07:32] Accessibility gets tested in a real
[00:07:34] actual browser on light mode or dark
[00:07:36] mode. Every single route you can think
[00:07:38] of. The worker can say done, but the
[00:07:41] checking agent decides whether that's
[00:07:43] true. Now, let me get into that
[00:07:46] hallucination story in a little bit more
[00:07:48] depth here. Now, catch one, the
[00:07:50] hallucination. The capture agent's job
[00:07:53] was very simple. Grab Elsa's words
[00:07:55] verbatim and come back and literally
[00:07:58] give quotes back into the system for
[00:08:00] more tasks down the road. It came back
[00:08:01] with 213 quotes, all of which it said
[00:08:05] were verified. But the checking agent
[00:08:08] didn't believe that. The checking agent
[00:08:09] recompared every quote, character for
[00:08:12] character, curly quotes included,
[00:08:14] against the current live site, and found
[00:08:16] that 13 of them had been stitched
[00:08:18] together or paraphrased by the agent
[00:08:20] that was supposed to just retrieve
[00:08:22] quotes. It was close enough to fool
[00:08:23] anyone skimming, which is what makes it
[00:08:25] very dangerous, right? Elsa's words are
[00:08:27] her product as a writer, and close
[00:08:29] enough is not acceptable. So, the
[00:08:31] failures went back to the worker, and it
[00:08:33] was not told to try again. It was told
[00:08:35] here is precisely what is wrong by the
[00:08:37] checker agent and then attempt two came
[00:08:39] back perfect. Total human involvement
[00:08:41] zero. And that's the loop. You execute,
[00:08:44] you fail specifically, an agent gives
[00:08:47] feedback and you retry until true. And
[00:08:49] if you're thinking, okay, fine. Checks
[00:08:50] can catch sloppy work. Sure, but watch
[00:08:53] what happens as the afternoon build goes
[00:08:56] by. Because because the hallucination
[00:08:58] was the easy case. Catch number two, the
[00:09:00] worker that cheated. Late in the build,
[00:09:02] a worker agent needed to get one of
[00:09:04] Elsa's required passages onto a web page
[00:09:07] to pass its check. So, it hid the text
[00:09:10] inside an invisible paragraph. It's
[00:09:12] invisible to you, but it's not invisible
[00:09:14] to a screen reader where it becomes
[00:09:16] meaningless noise read aloud to a blind
[00:09:18] visitor because it's completely out of
[00:09:20] context. So, think about it this way.
[00:09:22] The AI agent that was a worker chose a
[00:09:24] shortcut that is cosmetically fine
[00:09:26] because you'd never see it with your
[00:09:28] eyes, but it's harmful to precisely the
[00:09:30] people the site is for, blind people.
[00:09:32] And we're not done yet. Another worker
[00:09:34] satisfied a hard layout requirement with
[00:09:37] a literal empty element, and that was
[00:09:39] caught by an accessibility agent check.
[00:09:42] So, look, cheap workers cut corners. We
[00:09:45] price that into the system, and the
[00:09:47] system isn't built on trusting them.
[00:09:49] It's built so that the cut corners don't
[00:09:52] survive these checks. And by the way,
[00:09:54] both of those checks, again, caught by
[00:09:56] agents designed to check the work. This
[00:09:59] one surprised me. Fable 5, the boss, the
[00:10:01] designer of this whole system, the $50
[00:10:04] model, the one that designed this entire
[00:10:06] site itself, it wrote a bug, a CSS bug,
[00:10:10] a dark mode rule that made the pre-order
[00:10:12] button invisible. The single most
[00:10:14] important button on an author's website
[00:10:16] in launch season, gone on the boss's own
[00:10:18] design, and it got caught twice
[00:10:20] independently. Once by the accessibility
[00:10:22] agent checker and once by the boss's own
[00:10:25] review pass. The loop that we are
[00:10:27] building here does not care about the
[00:10:29] org chart. There is no rank in this
[00:10:31] system high enough to avoid
[00:10:33] verification. And that's a really
[00:10:35] important principle of agent design.
[00:10:36] Okay. Catch number four. The one the
[00:10:38] skeptics out there are waiting for.
[00:10:40] Because the sharpest objection to
[00:10:41] everything I've just shared with you is
[00:10:43] who checks the checker agents? And we
[00:10:45] answered that one, too. Now, here's the
[00:10:47] story. A worker agent in the build got
[00:10:49] failed by a checker agent for delivering
[00:10:52] news posts that were too short under a
[00:10:54] length floor that the check enforced.
[00:10:56] Except those posts really are that short
[00:11:00] on Elsa's website. So they're real and
[00:11:03] they're short because they're
[00:11:04] announcements. They don't need to be
[00:11:05] long. The spec itself said that honesty
[00:11:08] beats padding. And so when the worker
[00:11:11] agent escalated the dispute to the boss
[00:11:14] agent, yes, this really happened. Fable
[00:11:17] 5 came back in favor of the worker and
[00:11:20] the checker agent got corrected.
[00:11:22] Failures get investigated in both
[00:11:24] directions. So let's look at the ladder
[00:11:27] that we just climbed together. The
[00:11:29] worker agent gets caught, the cheater
[00:11:31] gets caught, the boss gets caught, and
[00:11:34] the checker agent gets caught. Those are
[00:11:36] four different rungs in the system. And
[00:11:38] in every single case, the answer to who
[00:11:41] watches that turns out to be the system
[00:11:43] does if you design it right. And that
[00:11:46] not any model release that is what has
[00:11:49] changed agents this year. And I want to
[00:11:51] be really clear about something. None of
[00:11:53] this required a lab or a team or custom
[00:11:55] research with Fable 5 doing the
[00:11:57] orchestration. This is just a recipe.
[00:11:59] It's it's written down. I I've linked it
[00:12:01] below. Hallucination isn't solved. It's
[00:12:04] just structurally positioned out of the
[00:12:06] picture because we've designed systems
[00:12:08] that are anti-h hallucination at root.
[00:12:10] Hallucination didn't get solved per se.
[00:12:13] It got handled structurally and you can
[00:12:16] design and run the structure. Which
[00:12:17] brings us to the larger point of this
[00:12:19] entire video because all of this
[00:12:21] machinery was in service of a website
[00:12:23] for a deaf blind author in launch season
[00:12:26] and what it built is the thing that
[00:12:28] surprised me and honestly shocked Elsa.
[00:12:30] So as an example, large print is an
[00:12:32] aesthetic statement. The body font that
[00:12:35] Fable chose is Atkinson hyperled
[00:12:37] legible. It's designed by the Braille
[00:12:38] Institute to be extremely readable. the
[00:12:41] site's signature divider. That was also
[00:12:43] Fable's idea. It's a white cane with a
[00:12:45] red tip. And that brings us to the last
[00:12:47] pattern, the one that so many of us miss
[00:12:49] because it's the answer to how do you
[00:12:51] even prompt it to do something like this
[00:12:53] cool, right? And the answer is you
[00:12:55] don't. Not task by task. Before a single
[00:12:59] page existed, the research phase
[00:13:01] produced a 14-point accessibility
[00:13:03] constitution for this website, a written
[00:13:06] standard, and every build round got
[00:13:08] tested against it in a real browser.
[00:13:10] both themes, light and dark, every route
[00:13:12] you could think of. And that should be
[00:13:14] how you prompt for big work. You name
[00:13:17] what done right means for you one time
[00:13:19] at the top and the system enforces it on
[00:13:22] every single round while you do
[00:13:24] something else. And the prompt that's
[00:13:27] not instructions, it's just a standard
[00:13:29] plus a way to check it. And by the way,
[00:13:31] in this case, the prompt given to Fable
[00:13:35] was a prompt to produce a site. And the
[00:13:39] comment given to Fable was to please
[00:13:42] produce the site in line with
[00:13:43] accessibility since of course that that
[00:13:46] is aligned with what Elsa's mission is.
[00:13:48] And Fable came up with the constitution.
[00:13:50] Fable did the research. Fable organized
[00:13:53] the workers to get all of that done. And
[00:13:54] I was really careful here because I
[00:13:56] didn't want Fable to take away Elsa's
[00:13:59] voice in the rewrite. Elsa's words
[00:14:01] shipped verbatim. There were 171
[00:14:03] protected passages from the original
[00:14:05] site that were all machine checked on
[00:14:07] every build and all Fable did was
[00:14:10] orchestrate writing in character
[00:14:12] connective tissue between those passages
[00:14:15] and then Elsa checked and validated it.
[00:14:17] The persona that mattered the most to me
[00:14:18] and Elsa was Maya, a blind reader on
[00:14:21] voice over with a braille display. She
[00:14:23] asked for things that the original
[00:14:25] design didn't want to give her, right?
[00:14:27] navigable headings, meaningful link
[00:14:29] text, a real image description instead
[00:14:31] of a joke, and she outranked the design.
[00:14:33] All of what she wanted shipped. And
[00:14:36] Fable went so far as to test as Maya to
[00:14:40] make sure that her experience was good
[00:14:42] and went to the trouble of creating a
[00:14:45] spoken voice over of the site that she
[00:14:49] could play to help her understand the
[00:14:51] site, which is something Elsa's always
[00:14:52] dreamed of and never had time to put
[00:14:54] together. Now, Elsa's the real judge
[00:14:56] here, and she looked through the
[00:14:57] finished site, and as someone with
[00:15:00] professional accessibility work under
[00:15:02] her belt, she was shocked because she
[00:15:06] gave this build nothing. There was no
[00:15:07] brief, there was no brand notes. Uh she
[00:15:10] it was it was like a five-word prompt,
[00:15:12] right? And I just ran with it with with
[00:15:14] a team of agents. And it learned to use
[00:15:17] her color palette, it learned her voice,
[00:15:19] it learned her book cover, and it went
[00:15:22] all the way to a W keg 2.2 2A standard,
[00:15:25] which is something that very few
[00:15:27] websites in the world actually beat. And
[00:15:29] so this is something that instead of
[00:15:30] taking 6 days for her with one agent
[00:15:33] last month, took an hour and a half or
[00:15:36] so, maybe 2 and 1/2 hours at 8 bucks.
[00:15:39] And Elsa's assessment is that this site
[00:15:41] is so much better than the last one. So
[00:15:44] it's cheaper, it took less time, it's
[00:15:46] way better. Why aren't we using more
[00:15:48] multi- aent systems? And I think the
[00:15:51] answer is really simple. It's scary.
[00:15:53] It's hard. It feels intimidating to look
[00:15:57] at 20 agents. And that is what I am
[00:16:00] trying to to take away as an objection
[00:16:03] with this video. It is not hard to do
[00:16:05] multi- aent systems, especially not in
[00:16:08] MIT 2026. We have recipes now to do work
[00:16:11] like this that we never had before. And
[00:16:14] the whole reason we do it that way is so
[00:16:17] you can skip the plumbing and start
[00:16:19] working on your first job. And that's
[00:16:21] where I want to leave you. If this is so
[00:16:25] easy that we can all do it, then it's
[00:16:29] just about making sure that we
[00:16:32] understand the kinds of tasks we can ask
[00:16:35] agents to do. And that's actually one of
[00:16:37] Elsa's takeaways. She and I were talking
[00:16:39] after the website and she was telling
[00:16:41] me, "I didn't realize that multi-agent
[00:16:44] systems make such a massive difference
[00:16:48] in the kinds of work you can get done
[00:16:50] and I need to start thinking bigger
[00:16:52] about how much work I give multi- aent
[00:16:54] systems." That's really true. I if you
[00:16:57] are thinking of a piece of work and
[00:16:58] you're like, I don't know if AI can do
[00:17:00] it or if it feels too big. I'm trying to
[00:17:03] put together a tool set here that you
[00:17:05] can use to get that work done. And if
[00:17:08] you don't touch a terminal, this one's
[00:17:10] for you because Elsa doesn't touch a
[00:17:12] terminal either, right? Elsa doesn't
[00:17:14] feel super comfortable running swarms. I
[00:17:17] wanted to take a noncode ccentric task.
[00:17:20] Yes, I know code was used in the
[00:17:21] website, but it's not centered around
[00:17:23] code. It's centered around the value of
[00:17:25] telling Elsa's story on the web. And I
[00:17:27] wanted to make sure that I could show
[00:17:29] that multiple agents help tell that
[00:17:32] story in a way that you just can't get
[00:17:34] to even with a frontier agent doing
[00:17:37] really good work even in a great harness
[00:17:39] like Codeex. This multi- aent pattern is
[00:17:42] very close to hitting mainstream. I'm
[00:17:44] sharing it with you because it's just
[00:17:46] breaking out of engineering circles now
[00:17:48] and I want you to be the first to grab
[00:17:49] it. When it breaks loose, the headlines
[00:17:52] are going to look like, "Hey, AI built
[00:17:54] this website for eight bucks." I don't
[00:17:56] think that's the right headline. I think
[00:17:58] a better headline is that we are now
[00:18:01] able to delegate bigger, more muscular,
[00:18:04] more ambitious tasks to AI and as a
[00:18:08] result, we can get more done. Elsa
[00:18:10] always wanted an accessible website, but
[00:18:12] she was so busy bringing accessibility
[00:18:14] to others, she didn't have time to
[00:18:16] actually sort it out for herself, so the
[00:18:18] agents did. And I think that when you
[00:18:20] think of that kind of work in your
[00:18:22] world, whatever it is for you, it might
[00:18:24] not be accessibility, it might be
[00:18:26] anything else under the sun that you
[00:18:27] think you can tackle with computing with
[00:18:30] agents, this is what you can use to do
[00:18:34] that affordably. And yes, you can use
[00:18:36] the power of Fable to get there without
[00:18:39] the money that Fable would otherwise be
[00:18:41] spending. Who wants to spend a hundred
[00:18:43] bucks when you could be spending eight,
[00:18:45] right? Like you don't want to do that.
[00:18:47] So you might only be one afternoon away
[00:18:50] from that work that you want done. And
[00:18:51] it's not because the models got magical.
[00:18:54] It's because actually orchestrating
[00:18:57] multi- aent systems has gotten simple
[00:18:59] enough that I can talk about this and
[00:19:01] share this and it's really very doable.
[00:19:04] And that's happened like really in the
[00:19:05] last 30 days or so. So have fun. Go jump
[00:19:08] into it and tell me what you build with
[00:19:10] your multi- aent system. I can't wait to
[00:19:12] hear
