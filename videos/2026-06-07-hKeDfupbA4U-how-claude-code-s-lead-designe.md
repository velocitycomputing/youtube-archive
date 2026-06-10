---
video_id: hKeDfupbA4U
title: How Claude Code’s lead designer builds with AI
channel: Dive Club 🤿
url: "https://www.youtube.com/watch?v=hKeDfupbA4U"
watched_date: 2026-06-07
watched_at: "2026-06-07T12:00:00Z"
watch_count: 1
duration_seconds: 738
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 75
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 74
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker, Anthropic's lead Claude Code designer, demonstrated practical workflows for using AI to accelerate development on open-source projects like Excalidraw. Key techniques covered include: using git worktrees to run multiple Claude sessions in parallel without conflicts, leveraging a custom `/prototype` skill to generate multiple implementation options before Claude selects the best one, utilizing the Loop feature for iterative refinement until completion, automating code quality checks via custom skills (simplify, code-review), employing Claude in Chrome for frontend verification with screenshots, and building scheduled routines that automatically audit code changes (e.g., flagging frontend work shipped without designer input and creating adversarial design PRs). The speaker emphasized that Claude handles both coding and non-coding tasks—research, PR reviews, merge automation, CSS polish—to maintain crafting quality while freeing engineers for higher-level decisions.

To apply this immediately: set up worktrees when running concurrent Claude sessions, build a `/prototype` skill to generate multiple design options before committing to one, enable auto mode to reduce permission prompts, use Loop for iterative tasks, and delegate non-coding work (research, documentation, code review triage) to Claude. More ambitiously, create scheduled Claude routines to audit your team's work (e.g., checking that design reviews happened before shipping frontend changes) and set up automation to handle PR merging once CI passes. Keep humans in the loop for design decisions and judgment calls about what ships—automation should amplify human judgment, not replace it.

## Transcript

[00:00:00] What I'm actually going to show today is
[00:00:01] what I would consider a pretty practical
[00:00:04] demo of some of the workflows that I
[00:00:06] think will help up level people who are
[00:00:08] using Claude code.
[00:00:11] >> [clears throat]
[00:00:11] >> The way I like to describe it and in
[00:00:13] some of my experience so far in the
[00:00:14] industry,
[00:00:15] we're kind of operating in like these
[00:00:17] really compressed time horizons, but the
[00:00:19] way that we work at Anthropic because we
[00:00:21] just have access and we're playing all
[00:00:22] the time and all day, it feels like
[00:00:24] we're like always looking for the next
[00:00:25] way to work and make ourselves more
[00:00:27] optimal. And so I'm going to show some
[00:00:28] of the things that have become really
[00:00:29] popular internally for how we work and
[00:00:31] hopefully this will all help you up
[00:00:32] level.
[00:00:33] One thing I'll call out is that I am a
[00:00:35] CLI die hard. Like I've designed the
[00:00:37] CLI. Like Claude is in there. I think
[00:00:40] it's just like like I used to design CLI
[00:00:42] products even before AI, so know that
[00:00:44] like this is not how you need to work
[00:00:45] that the desktop app is much more
[00:00:46] accessible and like you can do
[00:00:48] everything that I show today on the
[00:00:50] desktop app as well.
[00:00:51] But um this is going to be on an open
[00:00:53] source repo. Does everyone know what
[00:00:54] Excalidraw is? Does anyone know what it
[00:00:56] is? It's like a
[00:00:58] Yeah.
[00:00:59] Excellent product. Super great that
[00:01:00] they're open source. You can always
[00:01:01] contribute. If you actually want to
[00:01:02] practice, they're really great one cuz
[00:01:04] they have a great backlog of issues and
[00:01:05] a pretty open community. First tip, if
[00:01:07] you don't know it, is that you should
[00:01:08] always be starting your work in a work
[00:01:10] tree. Does everyone do this or does
[00:01:11] anyone know what this is?
[00:01:14] All right. So work trees are pretty
[00:01:16] complicated and generally I don't think
[00:01:18] you need to know what they are, but all
[00:01:19] you need to know is that if you have a
[00:01:21] local source of your repository on your
[00:01:23] computer
[00:01:25] and you want to run multiple Clauds at
[00:01:26] once, you might have run into the issue
[00:01:28] where your Clauds start conflicting with
[00:01:29] each other and you're doing one thing in
[00:01:31] one and another thing in another and
[00:01:32] they're overriding each other and
[00:01:33] they're competing, work trees keep makes
[00:01:35] an isolated copy of your repository so
[00:01:38] that you can do multiple parallel tasks.
[00:01:40] So if you find yourself having multiple
[00:01:42] windows open and doing multiple things
[00:01:43] at once or you see your engineers who
[00:01:45] have four or five Clauds open, know that
[00:01:47] they either have multiple copies of the
[00:01:49] repository on their laptop and they
[00:01:51] might call it like repo one, repo two,
[00:01:53] repo three
[00:01:54] or or using work trees. And I recommend
[00:01:56] work trees cuz it's a little bit easier
[00:01:57] to manage. And to start it up, you just
[00:02:00] do Claude {dash} {dash} worktree. And so
[00:02:02] you can kind of see in the branch
[00:02:04] there, it's in a worktree and it already
[00:02:06] checked out a new branch for me. So, pro
[00:02:08] tip number one, if you're
[00:02:09] multi-Clauding, use worktrees.
[00:02:12] The second pro tip I'll give,
[00:02:14] I know not everyone has access to this,
[00:02:16] depending on your organization, so I
[00:02:17] just say like I am always in Opus 1
[00:02:20] million contexts, just so you don't have
[00:02:22] to think about it. And then I am always
[00:02:24] in fast mode.
[00:02:26] Uh [laughter]
[00:02:28] yeah.
[00:02:30] So, once again, I know it's not
[00:02:32] accessible to everyone.
[00:02:36] And I am going to do this so that we can
[00:02:38] fast forward through the demo a little
[00:02:39] bit cuz I only have 15 minutes, but I do
[00:02:41] think that it does, you know, it does
[00:02:43] make a little bit of a difference. Okay,
[00:02:45] and then I'm a big
[00:02:47] typewriter. Claude is actually really
[00:02:48] good at getting typos if you type them,
[00:02:51] but uh I put this here so that y'all
[00:02:53] could see it.
[00:02:55] This is a prompt that I'm just going to
[00:02:56] get Excalidraw to add a new autocomplete
[00:02:59] feature.
[00:03:00] That's it. No design specs, no just like
[00:03:03] I want to add autocomplete, I want to
[00:03:04] see what it looks like. A few things I'm
[00:03:05] going to call out here that I think are
[00:03:07] important when you're prompting. The
[00:03:09] first is I built myself a slash
[00:03:10] prototype skill.
[00:03:12] I asked Claude to build this, you could
[00:03:13] build it in like 2 seconds. All it does
[00:03:14] is get Claude to generate uh n number of
[00:03:17] options, default to five, of a different
[00:03:20] implementation of a feature, generate an
[00:03:22] HTML file, preview it, and then iterate
[00:03:24] on it a few times and I can enter that n
[00:03:26] and I can enter what the feature is
[00:03:27] going to be. Uh I did not write this. No
[00:03:30] one ever writes their skills by hand
[00:03:31] anymore. If anyone tells you they do,
[00:03:32] they're lying. Everyone just prompts
[00:03:33] them.
[00:03:34] Um and then a few things I will add in
[00:03:37] here is I always ask Claude to pick an
[00:03:40] option for me first. I think it's
[00:03:42] actually fun to see what Claude comes up
[00:03:43] with. So, historically, I used to be
[00:03:45] like, oh, like prototype and then I'll
[00:03:47] choose. Now I'm like, oh, prototype and
[00:03:48] then you should choose what you're going
[00:03:50] to do and then tell me why.
[00:03:52] And then I say another one is like feel
[00:03:55] free to research online. Now, if I were
[00:03:57] doing this in my production code base,
[00:03:58] I'd say like please look at Slack,
[00:04:01] Google Docs, any discussions, and like
[00:04:03] like BigQuery, like look at all these
[00:04:04] sources and figure out which is the best
[00:04:06] one. But given that this is an
[00:04:07] open-source repo, online research is
[00:04:09] fine. And then, you know, implement the
[00:04:11] best option, verify, get the styles to
[00:04:14] match. Um really important one, put up a
[00:04:16] PR with a screenshot. Claude is actually
[00:04:18] really good at this, and I actually
[00:04:20] don't review the outputs anymore of
[00:04:21] Claude in the transcript. I'm typically
[00:04:23] reviewing a PR that Claude put up that
[00:04:24] has a recording of the feature that
[00:04:26] implemented. And then a new feature that
[00:04:28] we released, I think a few months ago,
[00:04:29] is Loop. Does anyone Has anyone used
[00:04:32] this before?
[00:04:34] Loop is pretty much just cycle.
[00:04:36] Keep going. So, loop until you're done
[00:04:39] just means keep going at this until it's
[00:04:41] fully done.
[00:04:42] And so I'll I'll show some more
[00:04:43] applications of Loop in the future, but
[00:04:44] it's like a pretty standard prompt. If
[00:04:46] an engineer asked me to like build
[00:04:47] something, I would this is like Well, to
[00:04:50] be honest, they would probably do this
[00:04:51] on their own without me and then send me
[00:04:52] a five-coded prototype. But if I was
[00:04:55] doing it from the ground up, this is how
[00:04:56] I would do it.
[00:04:58] Oh, the other pro tip that I forgot to
[00:05:00] mention, I'm always and everyone at
[00:05:02] Anthropic is always in auto mode. So,
[00:05:04] auto mode is our
[00:05:06] kind of workaround for lower permission
[00:05:09] modes. We have a classifier that will
[00:05:11] detect whether or not a risky action is
[00:05:12] being taken on your computer. So, you
[00:05:14] don't have to be sitting there being
[00:05:14] like, "Yes, I accept. Yes, yes, yes,
[00:05:16] yes." So, you should be using it in this
[00:05:18] way, and it'll go a lot faster.
[00:05:20] Now, I've done a lot of these demos
[00:05:21] before, and Claude takes a long time to
[00:05:23] work. So, typically, if I were doing
[00:05:25] this, I'd actually spin up a bunch of
[00:05:26] these, but because we're here and I'm
[00:05:28] trying to showcase a workflow tonight,
[00:05:30] I'm actually going to show a few other
[00:05:31] things I do on the side while Claude is
[00:05:33] working.
[00:05:34] But
[00:05:36] um
[00:05:37] I think these are a few tenants that I
[00:05:39] hold true as I'm working today, and
[00:05:41] they're going to kind of inform some of
[00:05:42] the workflows that I'm going to show all
[00:05:44] of you today.
[00:05:45] So, the first is that Claude,
[00:05:47] tragically, and most LLMs are not good
[00:05:50] at design yet. So, what this means is
[00:05:53] that you should still very much be in
[00:05:54] the loop for the craft and the
[00:05:55] decision-making. It doesn't mean this is
[00:05:57] going to be holding true forever, but a
[00:05:58] lot of my workflows revolve around the
[00:06:00] idea that I still need to be the one
[00:06:02] making a decision about what actually
[00:06:03] goes into the product.
[00:06:05] Perfect. So, you can see here, sorry,
[00:06:06] this is going to be a little back and
[00:06:07] forth, that Claude has used my prototype
[00:06:09] skill to list a bunch of different
[00:06:11] options of what tabs to complete could
[00:06:13] look like. And so, it's showing all the
[00:06:15] different ways. I'll typically like
[00:06:17] preview, sometimes I'll play around with
[00:06:18] it.
[00:06:19] Um
[00:06:20] Sometimes Claude asks me for one. Does
[00:06:22] anyone have a preference on one that
[00:06:24] they like?
[00:06:25] >> [snorts]
[00:06:28] >> Two.
[00:06:28] >> All right, I'm going to go two.
[00:06:31] That's it. All right. Um the second is
[00:06:34] that I actually, yes, coding is
[00:06:37] automated, but I hand off so much of my
[00:06:38] work that is not coding to Claude. And
[00:06:40] if you're not doing that, then you're
[00:06:41] actually not using Claude in the most, I
[00:06:43] think, like automated way. You We really
[00:06:45] need to start thinking about more than
[00:06:46] just code when we think about AI
[00:06:47] automation.
[00:06:49] And then the third one, which I don't
[00:06:50] think is controversial for this room,
[00:06:51] but has definitely been one that has
[00:06:53] been an uphill battle a lot of places,
[00:06:54] is just because everyone can ship
[00:06:57] doesn't mean not everything should ship.
[00:07:00] And that's a pretty important
[00:07:01] distinction that we need to start making
[00:07:03] as we're adding more features and as
[00:07:04] everyone has the ability to access code
[00:07:06] and like push to production, we need
[00:07:08] better systems that scale.
[00:07:10] And so, some ways that we're fighting
[00:07:12] this internally today is I actually use
[00:07:15] Claude in the web. Does everyone have
[00:07:17] this internally at their teams or
[00:07:18] companies?
[00:07:20] Uh you might have it with your own
[00:07:21] internal infrastructure, but I have like
[00:07:24] Claude in the cloud or Claude in the web
[00:07:26] is a service that we offer and I use it
[00:07:27] as a way to send like hundreds of tiny
[00:07:30] little polish fixes all the time that I
[00:07:32] find in the app. They're not worth
[00:07:33] spinning up a new session for, they're
[00:07:34] not worth dedicated time. I just have
[00:07:36] all of these going and I would say, uh
[00:07:38] sometimes I get complaints from the
[00:07:39] engineers that there's too many of them.
[00:07:41] So, every now and then I'll ask Claude
[00:07:42] to squash them all into one PR for me.
[00:07:44] And sometimes they just got auto
[00:07:46] approved because they're tiny CSS
[00:07:47] changes and no one really needs to
[00:07:49] review them. So, I would say like this
[00:07:51] is a really great way to maintain
[00:07:52] crafting quality in your products and
[00:07:54] it's something that you can do on the
[00:07:55] side as Claude is working.
[00:07:58] A second one is that almost everyone at
[00:08:00] Anthropic actually always has Claude's
[00:08:02] running and always has Claude's running
[00:08:05] to help merge PRs. So, one thing that I
[00:08:07] never do anymore actually is once an
[00:08:08] idea is done, I'm never actually in CI.
[00:08:10] I'm never reviewing like like until
[00:08:12] merge. I'm never like addressing code
[00:08:13] review comments and stuff like that.
[00:08:15] It's actually all fully automated now.
[00:08:16] And so, there's two tricks that I did to
[00:08:18] do with that. The first is All right,
[00:08:20] perfect. So, now you can see I asked
[00:08:22] Claude to verify.
[00:08:24] So, Claude is opening Chrome right now
[00:08:27] and it's going to test that it's
[00:08:29] working, but I'm just going to We can
[00:08:31] watch it if you want. If you guys have
[00:08:33] the Claude in Chrome, I would highly
[00:08:34] recommend using it cuz if you're doing
[00:08:35] front end changes, it's actually the
[00:08:37] best way to have Claude be able to
[00:08:38] self-verify.
[00:08:40] And you can see the ADHD we all way we
[00:08:42] all work right now where we're like
[00:08:43] doing one thing and then Claude pops in
[00:08:45] and is doing another thing.
[00:08:46] Uh but I'm just going to let that go.
[00:08:48] Uh these are the commands. The first one
[00:08:50] I do actually before when I make big
[00:08:52] code changes is just a really good way
[00:08:54] to
[00:08:55] like do a little bit of a hygiene check.
[00:08:57] Uh simplify and code review are internal
[00:09:00] to our repository, but I guarantee you
[00:09:02] if your engineering team is using AI,
[00:09:04] they have an equivalent of that that
[00:09:06] kind of prunes your code base. So, ask
[00:09:08] your engineering partners like how do
[00:09:09] like what skills do you guys have to
[00:09:11] simplify your PRs and then they'll be
[00:09:12] able to put them up. And then this
[00:09:14] commit push PR is one that runs a bunch
[00:09:16] of checks that we have internally as
[00:09:17] well. So, these are all ones that our
[00:09:18] team has built. Some of them are
[00:09:19] available externally, but I also like
[00:09:21] know that all your engineering teams
[00:09:23] have dev prod teams that have built
[00:09:24] these and you should be using them.
[00:09:26] Uh and then the second one is one that
[00:09:27] almost everyone engineering
[00:09:29] non-engineering has at Anthropic. This
[00:09:30] is built into skill, but I wrote out the
[00:09:31] full command that we used to use, which
[00:09:33] is just to review any open PRs and just
[00:09:36] get them over the finish line. And the
[00:09:39] somewhat annoying thing, but really
[00:09:41] great thing that we have is cuz it's
[00:09:42] connected to Slack, it will DM people if
[00:09:45] they are on your code review as well, or
[00:09:46] it'll DM the stamp channel and ping
[00:09:49] who's on call. So, the full integration
[00:09:51] of your suite is where it's at.
[00:09:55] Uh and then the last one, which I think
[00:09:57] has been the most game-changing for me
[00:09:58] personally as our product suite has
[00:10:01] grown, is actually I have a Claude code
[00:10:04] routine, which is a scheduled task if
[00:10:06] you use uh Claude code work. And what
[00:10:09] this does is it scrapes all of our
[00:10:13] repositories for any front-end changes
[00:10:15] that anyone has implemented.
[00:10:17] It will check if a designer was involved
[00:10:19] in it by going through Slack, Google
[00:10:22] Meet transcripts, like uh Google Docs,
[00:10:24] like any kind of data that it has access
[00:10:26] to. If a designer was not involved in
[00:10:29] it, it will flag that it shipped without
[00:10:31] a designer or not.
[00:10:34] >> [laughter]
[00:10:35] >> If it shipped without a designer,
[00:10:37] it will come up with an adversarial or
[00:10:40] it'll review the design and then it will
[00:10:42] typically come up with an adversarial
[00:10:44] design in a PR already drafted,
[00:10:48] DM it to the engineer who shipped that
[00:10:50] feature,
[00:10:52] and then ask them to work with the
[00:10:53] designer
[00:10:56] on that feature.
[00:10:59] I tested this a few times and I had to
[00:11:00] turn off the DMing cuz Claude was
[00:11:01] actually really bad at design,
[00:11:03] unfortunately. And I We did have to like
[00:11:05] it's And like that goes back to my first
[00:11:07] one, like Claude is not good at design
[00:11:08] yet, but I think this is the level of
[00:11:10] automation that you have to be thinking,
[00:11:11] like not just the first step, but like
[00:11:13] the next step, the next step, the next
[00:11:14] step after that. Like you want to be
[00:11:15] pushing it so far that it's like
[00:11:17] building the actual end product. And I
[00:11:19] think we have a lot of forgiveness right
[00:11:21] now in the industry because we're all
[00:11:22] testing how these workflows work. So, uh
[00:11:25] people were very forgiving when I first
[00:11:26] tried this and it was really bad. And
[00:11:27] now I just consume this myself, but uh
[00:11:30] I'm always ready for when the next
[00:11:31] model's going to come out and this is
[00:11:32] actually going to be ready and available
[00:11:33] because I have it all written up. So,
[00:11:35] when we're testing the next one, I'll
[00:11:36] just throw that up, get it, see if it'll
[00:11:38] work, and it typically gets better.
[00:11:41] Yeah. And so, these are the three tips
[00:11:44] if I could like really impress on you of
[00:11:45] like workflows that we're using that
[00:11:47] have really like just augmented how the
[00:11:49] team works. These are the three things I
[00:11:50] demoed today. And then, if we go back to
[00:11:55] the session, you can see that Claude is
[00:11:57] now
[00:11:59] recording a screenshot from Claude in
[00:12:02] Chrome here. Uh, it does it through a
[00:12:04] series of GIFs. It's going to post it
[00:12:06] up, and then it's going to open the PR.
[00:12:09] Yeah, but that's it for my demo.
[00:12:10] Hopefully, this is helpful, and
[00:12:11] hopefully, this helps you guys all use
[00:12:12] Claude code.
