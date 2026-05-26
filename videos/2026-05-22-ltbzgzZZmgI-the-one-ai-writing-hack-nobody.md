---
video_id: ltbzgzZZmgI
title: The One AI Writing Hack Nobody Talks About.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=ltbzgzZZmgI"
watched_date: 2026-05-22
watched_at: "2026-05-22T12:00:00Z"
watch_count: 1
duration_seconds: 1310
source: youtube-history-browser
history_label: Friday
history_order: 59
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 131
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What Was Discussed:**
The video examines why AI hallucinations happen not because of bad prompts, but because of poor organizational workflows. Using Sullivan and Cromwell's legal filing disaster (fabricated citations in court documents) as a case study, the speaker argues that modern agents like Claude 4.7 Opus and OpenAI 5.5 can now solve this by working directly with file systems. The key insight is that the first prompt should never be "write the deliverable"—instead, it should be "organize my messy source materials into a structured data room." This involves creating three critical artifacts: a source inventory table (documenting every file's path, date, authority level, and current status), a conflict log (surfacing disagreements between sources), and a missing context list (identifying information gaps). Only after the agent has organized and inventoried your materials should you ask it to draft the final work.

**What's Actionable:**
Create a local folder structure or "data room" for your next serious project and ask the agent to: find all relevant materials (files, transcripts, notes, emails, spreadsheets), build a source inventory table showing which files are authoritative vs. outdated, flag conflicts and contradictions between sources, and list what information is missing. Once the agent hands you these organized artifacts, review them for accuracy, then use a simple final prompt like "Draft the memo using the inventory as reference, treat the current operating plan as authoritative for numbers, and flag unsupported claims." This workflow eliminates the conditions that breed hallucinations—a clean data environment where the agent operates transparently, you see its reasoning through artifacts, and gaps stay visible instead of getting filled with invented information.

## Transcript

[00:00:00] A few weeks ago, Sullivan and Cromwell,
[00:00:02] one of the most prestigious law firms on
[00:00:04] the planet, had to write an apology
[00:00:06] letter about AI to a federal bankruptcy
[00:00:08] judge. Their emergency motion in a
[00:00:10] chapter 15 case had been filed with
[00:00:12] dozens of fabricated or misqued
[00:00:14] citations. AI hallucinations. The other
[00:00:16] side's lawyers caught them. Sullivan and
[00:00:18] Cromwell's own review did not. The
[00:00:21] partner who signed the apology letter is
[00:00:23] the co-head of the firm's restructuring
[00:00:25] practice. This is the failure mode I
[00:00:27] want you to think about with me for the
[00:00:29] next few minutes. I'm not talking about
[00:00:31] 2024 hallucinations where a solo
[00:00:33] practitioner uses chat GPT and tries to
[00:00:36] tell it not to hallucinate. I'm talking
[00:00:38] about organizational and structural
[00:00:41] hallucinations at the top of aic
[00:00:43] workflows. In this case, the motion
[00:00:45] looked legitimate. The structure of the
[00:00:47] motion was correct. The citations were
[00:00:49] professionally formatted. Dozens of them
[00:00:51] were pointing at the wrong things and
[00:00:53] nobody on the team caught it before the
[00:00:55] filing. The model is not the problem
[00:00:57] here. The working environment around the
[00:00:59] model is the problem and it's the source
[00:01:01] for most of our 2026 hallucinations. I
[00:01:04] know what some of you are thinking,
[00:01:06] Nate, the answer is a better prompt. We
[00:01:08] talked about this. Just tell the model
[00:01:09] not to hallucinate. And by the way, the
[00:01:11] Mark Andrees screenshot has been all
[00:01:13] over the timeline for a few days now. It
[00:01:16] doesn't work. You cannot tell a language
[00:01:19] model not to hallucinate any more than
[00:01:22] you can tell autocomplete not to
[00:01:23] autocomplete. There is no separate truth
[00:01:26] check pass inside the model that the
[00:01:29] instruction can hook into and have some
[00:01:31] purchase and meaning. Sullivan and
[00:01:33] Cromwell had access to the best AI
[00:01:35] tooling that money can buy. The wrong
[00:01:37] detail still made it into court. The fix
[00:01:40] is not a sharper prompt. It just isn't.
[00:01:43] In the last month with 4.7 Opus and 5.5
[00:01:47] from OpenAI, agents have picked up a
[00:01:49] capability that changes the way we think
[00:01:51] about this. And I don't think law firms
[00:01:53] or most other people have realized it
[00:01:54] yet. There is a fix. It is not a prompt
[00:01:57] fix. And that's what I want to talk
[00:01:59] about today. So what is it about 4.7 and
[00:02:02] 5.5 that's special? They do longunning
[00:02:05] agentic tasks, as I've said a lot, but
[00:02:07] they do it on your file system. And
[00:02:10] that's such an unsexy thing to talk
[00:02:12] about. Oh, files. That's all the way
[00:02:14] back to 1982, right? Like that's a long
[00:02:16] time ago we handled files. Longer ago
[00:02:18] than that. Why do we care about files
[00:02:20] now? Why do we care that agents that are
[00:02:22] long running are now very good at taking
[00:02:24] and manipulating files? And how does all
[00:02:26] of that connect to the hallucination
[00:02:28] story? I will tell you these new agents
[00:02:31] do not just read what you paste. They
[00:02:33] can walk a folder tree. They can open
[00:02:35] files. They can compare dates across
[00:02:37] documents. They can inspect metadata.
[00:02:39] The workflow around hallucinations has
[00:02:42] flipped, but most people haven't caught
[00:02:45] that yet because the first useful prompt
[00:02:47] in a serious project is now like it's
[00:02:50] not write the document, right? It's much
[00:02:52] more boring than that. It is build me
[00:02:54] the folder in the file room. Build me
[00:02:56] the room to do the work in. And I want
[00:02:59] to talk to you about three key takeaways
[00:03:02] in this video. And if you follow them,
[00:03:04] you are not going to end up in the same
[00:03:06] hallucination place because you will
[00:03:08] have set up a process that is
[00:03:10] structurally antagonistic to
[00:03:12] hallucinations. I'm not saying they
[00:03:14] never happen. I am saying that you are
[00:03:16] building a structure that makes them
[00:03:18] much less likely to occur at scale and
[00:03:21] it keeps you and the work you do much
[00:03:24] more accurate and much less likely to
[00:03:26] lead to the kind of corporate liability
[00:03:28] that this prestigious law firm generated
[00:03:31] for itself because it did not think
[00:03:33] through its agentic pipeline correctly.
[00:03:35] It all comes back to file. So here we
[00:03:37] go. Three things. One, why your first AI
[00:03:41] prompt is never do the thing. And I
[00:03:43] talked about that just above. We're
[00:03:44] going to get into why that is. Two, what
[00:03:46] to ask the agent for when you want to go
[00:03:49] deeper and how you do that
[00:03:50] intelligently. And three, why this
[00:03:53] approach actually works with 5.5 in
[00:03:56] particular. 5.5 is really good at this
[00:03:57] and also with 4.7 as well. Look, the
[00:04:00] thing that sold me on this workflow was
[00:04:02] a real moment that I had multiple real
[00:04:05] moments over the last couple of weeks
[00:04:06] with codeex. I have been in situations
[00:04:10] where the AI agent has now been able to
[00:04:13] do incredibly powerful simultaneous
[00:04:17] drafting of up to eight different
[00:04:19] documents. I haven't gone past eight
[00:04:21] yet. I think I could. And the only way I
[00:04:24] could get eight documents drafting at
[00:04:26] once in codeex is because I prepared the
[00:04:29] data room first and I knew my outputs
[00:04:32] and I could then execute really cleanly
[00:04:35] and consistently. And it saved me so
[00:04:37] much time. It was an incredible speed
[00:04:40] up. It felt like the hair was blowing
[00:04:42] back on my face and I was living in the
[00:04:43] future. And I think that that's one of
[00:04:45] the things that we need to pay attention
[00:04:47] to is that we get these aha moments when
[00:04:50] we think about the boring primitives
[00:04:52] when we think about the files. And
[00:04:53] that's why we're going to talk about
[00:04:54] look because of chat GPT. Back in 2022,
[00:04:57] most people think the AI workflow starts
[00:04:59] with doing a job. Does the model write
[00:05:02] for me? Does the model code for me? Does
[00:05:03] the model make the Excel file? that's
[00:05:05] where the value is, right? It starts
[00:05:07] when the agent walks in and does
[00:05:10] something. But I don't think that's
[00:05:11] true. I think a serious project almost
[00:05:14] never has its source material organized.
[00:05:16] And we have had to be the human
[00:05:18] organizers for most of the prompting era
[00:05:21] in the last couple of years. We've had
[00:05:22] to find the strategy docs and the
[00:05:24] meeting transcripts and the spreadsheets
[00:05:25] and the half-finish notes and the
[00:05:26] follow-up emails and the old deck and
[00:05:28] the PDF you forgot about and the Slack
[00:05:30] thread where the actual decision was
[00:05:31] made. Can you tell I've actually had to
[00:05:33] do this? Some of it is current. Some of
[00:05:34] it is stale. Some of it contradicts
[00:05:36] itself. A few files may be helpful.
[00:05:38] You're not sure which one is the source
[00:05:39] of truth. You're often wrong. When you
[00:05:41] ask an AI to write from that general
[00:05:44] mess, you're asking it to do two jobs at
[00:05:46] once. Job one, figure out what this is.
[00:05:49] And job two, produce this beautiful
[00:05:51] artifact for me. That is a recipe for a
[00:05:53] really mediocre result. And it's one of
[00:05:55] the situations in which it's likely that
[00:05:58] you will have a hallucination problem in
[00:06:01] the way that this law firm did. The
[00:06:03] model didn't have a clean working
[00:06:05] environment. So, the dirt got into the
[00:06:07] dock. It didn't know which sources
[00:06:09] mattered. It didn't know what was stale.
[00:06:11] It didn't know what was missing. It
[00:06:12] didn't know which file was
[00:06:13] authoritative. You cannot patch that
[00:06:16] with a better opening sentence. And you
[00:06:18] really can't patch it by reading the doc
[00:06:20] and hand editing anymore because we're
[00:06:21] working at a different kind of scale.
[00:06:23] You have to patch it and prevent it from
[00:06:25] the beginning by cleaning up your data
[00:06:27] room first. So your first instruction
[00:06:29] should not be do the thing like write
[00:06:31] the memo, make the Excel etc. Instead,
[00:06:34] your first instruction needs to be find
[00:06:36] the relevant materials on the internet
[00:06:40] on my local computer in my files in the
[00:06:42] tools that I have connected to you. And
[00:06:44] by the way, Claude and Codeex both have
[00:06:46] a ton of connectors now. And so you can
[00:06:48] actually tell them to look in their
[00:06:49] connectors and they will. And so the
[00:06:50] first instruction is find the relevant
[00:06:52] materials, preserve the originals, build
[00:06:54] me a data inventory, put it in a folder,
[00:06:57] tell me which files seem authoritative,
[00:06:59] which are duplicates, which are old,
[00:07:00] which are missing. Summarize every
[00:07:02] source before you synthesize anything.
[00:07:04] And do not write the deliverable yet.
[00:07:06] We're just learning. That is so
[00:07:08] powerful. And it's possible because
[00:07:11] these tools can do complex longunning
[00:07:13] file manipulation tasks successfully and
[00:07:16] with very high accuracy. So let's use
[00:07:18] them to do that. Let me give the
[00:07:20] workflow a name so we can talk about it
[00:07:22] very very clearly. I'm calling it a
[00:07:25] project room or a data room. A project
[00:07:27] room is a bounded workspace for one
[00:07:29] serious job. It's a project, a
[00:07:31] deliverable, a source set. Now, this is
[00:07:34] much smaller than a whole second brain.
[00:07:36] It's much more specific than a knowledge
[00:07:38] management system. It is a workspace set
[00:07:40] up so an agent can do useful work inside
[00:07:42] it. And in most cases, it is a local
[00:07:44] workspace. This is different than a lot
[00:07:48] of the published cloud solutions that
[00:07:50] claude and chatgpt and codeex have had
[00:07:53] where they say here start up a project
[00:07:54] and sort of a shared context window that
[00:07:57] people can all chat into and all work
[00:07:59] with. I have found those have been much
[00:08:01] less useful than the flexibility of a
[00:08:04] local file system. And there is a whole
[00:08:06] 2026 conversation to be had around the
[00:08:08] idea that we are going back to files and
[00:08:10] going back to simple primitives. And
[00:08:12] those tend to work really really well
[00:08:14] because LLMs are being taught to use
[00:08:17] computers at their most primitive and
[00:08:19] root level in order to successfully do
[00:08:21] anything on computers. And when we go
[00:08:23] back to files, we are going back to what
[00:08:25] they know really, really well. Why not,
[00:08:27] right? Why not lean into it? So, let me
[00:08:28] give you an example. For a consulting
[00:08:30] project, this could look like client
[00:08:32] decks, interview transcripts, data
[00:08:34] exports, prior proposals, meeting notes.
[00:08:36] For a house purchase, it's inspection
[00:08:38] reports, disclosures, contractor
[00:08:40] estimates, mortgage documents, email
[00:08:42] threads. For a Substack, article you're
[00:08:43] writing, it could be uh sources you're
[00:08:45] researching, transcripts, draft notes,
[00:08:48] screenshots, prior related posts. For a
[00:08:50] board doc, it's a financial model, an
[00:08:52] operating plan, an old board deck, the
[00:08:53] current KPI exports, and the notes from
[00:08:55] the last three review meetings. The
[00:08:57] point here is that you don't have to
[00:08:59] build a perfect archive to gain a
[00:09:01] tremendous amount of advantage in the
[00:09:03] task you're setting the model. The point
[00:09:05] is just to give the agent a usable work
[00:09:07] surface, just enough room for it to
[00:09:09] operate. Where you build your room, of
[00:09:12] course, will depend on your preference
[00:09:14] on your source set. Look, you can do
[00:09:16] this in cloud projects. It's solid when
[00:09:18] you need a bounded workspace with
[00:09:19] uploaded docs. Chat GPT projects handle
[00:09:22] smaller sort sets and spreadsheets.
[00:09:24] Cursor or clawed code is the right tool
[00:09:26] in the room. Includes a code or folder
[00:09:27] tree. Codeex works for that too.
[00:09:30] Notebook LM works when it's very sort of
[00:09:32] research heavy and sourcebounded. And
[00:09:34] like I said, my personal preference,
[00:09:36] just go to local files, have it create a
[00:09:39] folder, and you can stick literally
[00:09:40] anything in there. And that's what I
[00:09:42] love about it because there's no like
[00:09:43] file type limitations that you get with
[00:09:45] some of the tools I mentioned. If it's a
[00:09:47] file, it goes in there. And if Codex can
[00:09:49] read it or Claude can read it, you're in
[00:09:50] good shape. So, if you want to dive
[00:09:52] deeper on different options to organize
[00:09:54] your files from the all those different
[00:09:57] tools and how you want to think about
[00:09:58] making that choice, I put that on
[00:10:00] Substack. You can dig into strategies
[00:10:01] for local file organization because
[00:10:03] imagine doing 20 projects. You're going
[00:10:05] to need to have some thinking around
[00:10:06] that. Uh you're going to want to dig
[00:10:08] into strategies if you want to use other
[00:10:09] tools too like uh projects on claude or
[00:10:12] on notebook LM looking at the sort of
[00:10:14] the folder structure, how you think
[00:10:15] about project breakdown. I've got all of
[00:10:17] that in detail there. We're going to
[00:10:19] stick in this video with how we think
[00:10:21] about this as an archetype, how we think
[00:10:23] about this as a larger pattern that
[00:10:25] works across many tools. So let's keep
[00:10:27] moving. So, you have your folder. You
[00:10:30] have stuff in it. The most important
[00:10:32] artifact in this whole folder I haven't
[00:10:35] talked about yet. It's a table. It's
[00:10:37] just a table. Hear me out. It's called
[00:10:38] the source inventory. And once the room
[00:10:40] exists, it's the first thing you ask the
[00:10:43] agent to produce. For every file in the
[00:10:45] room, the agent records the path, the
[00:10:48] type, the date, the apparent authority,
[00:10:50] whether the file is current or
[00:10:51] superseded, what claims it supports,
[00:10:54] what its limitations are, and how it
[00:10:55] should be used in the final work. Yeah,
[00:10:57] that does sound boring. It's also the
[00:10:59] artifact that determines whether
[00:11:00] everything downstream is any good. And
[00:11:02] by the way, it's an artifact that makes
[00:11:04] it really, really helpful when another
[00:11:06] LLM checks your current LLM's work. It
[00:11:09] makes it easy to pass. The inventory
[00:11:11] tells you what the agent thinks the
[00:11:12] project consists of, which is critical,
[00:11:14] and that gives you a chance to correct
[00:11:16] the working set of docs and and current
[00:11:18] set of data before the final draft is
[00:11:21] going to like inherit a bunch of
[00:11:23] mistakes and lead to hallucinations,
[00:11:25] frankly. And so yes, I do recommend
[00:11:27] checking what is in your inventory and
[00:11:30] making sure you're aligned with it and
[00:11:31] nothing is missing. And when in doubt,
[00:11:32] just say, "Hey, you know, codeex, I
[00:11:35] think this transcript may not be in
[00:11:36] here. Can you check and if need be,
[00:11:37] create a file for it?" And we'll do
[00:11:39] that. And the beautiful thing is these
[00:11:40] agents are strong enough to sort this
[00:11:42] out. Right? They can tell that an
[00:11:44] approved deck represents the story even
[00:11:46] when the underlying data lives
[00:11:47] elsewhere. That the old PDF might be
[00:11:49] useful background but not a source for
[00:11:51] current claims. and the the agents
[00:11:53] really can sort that out at the at the
[00:11:55] opus 4.7 at the Chad GPT 5.5 level and
[00:11:58] and the inventory artifact that you you
[00:12:01] create that table I'm talking about what
[00:12:03] you're really doing is you're making the
[00:12:06] agents judgment visible and legible so
[00:12:08] you can see it really really clearly
[00:12:11] because if you review the inventory and
[00:12:12] you can't tell why one file outranks
[00:12:14] another you can just like focus on
[00:12:16] getting the inventory right focus on
[00:12:18] making sure all the data is there before
[00:12:19] you have to go farther it's a really
[00:12:21] clean gate Now, I have been testing
[00:12:23] different knowledge systems for AI and
[00:12:26] the the organization framework that I
[00:12:28] landed on for large projects is
[00:12:30] something I'm writing up in a lot of
[00:12:31] detail on Substack. So, if you're
[00:12:33] serious about AI work, if you're trying
[00:12:34] to figure out how you organize these
[00:12:36] files at a 10, 20, 30 project scale so
[00:12:39] you're clean and you understand what
[00:12:41] you're working with, that's what you
[00:12:42] want to get to. Like, I have it all
[00:12:43] written up over there. Let's get into a
[00:12:46] couple of more artifacts to illustrate
[00:12:47] the principles because remember that's
[00:12:49] what we're doing. So, we talked about
[00:12:50] the table. Let's talk about two more
[00:12:52] artifacts. The first is the conflict
[00:12:54] log. When the agent reads a serious
[00:12:57] source set, it will find disagreements.
[00:12:59] The old PDF says one thing, the current
[00:13:00] plan says another. The transcript uses a
[00:13:02] different name for a person who's a key
[00:13:04] stakeholder versus a doc. The
[00:13:06] spreadsheet has a number with no visible
[00:13:08] assumptions behind it. Two documents
[00:13:09] that look adjacent are actually three
[00:13:11] months apart. A weak workflow lets the
[00:13:14] agent synthesize and smooth those
[00:13:16] conflicts over. The output will read
[00:13:18] confidently, but you don't know what you
[00:13:19] can trust. you get into the same
[00:13:21] hallucination problem that the law firm
[00:13:23] did at the beginning of this video. A
[00:13:25] strong workflow surfaces that
[00:13:27] disagreement without necessarily
[00:13:29] resolving it or at least without
[00:13:30] resolving it, without you being able to
[00:13:32] tell. The conflict log allows your agent
[00:13:35] to surface conflicts that I've just
[00:13:37] described and recommended responses and
[00:13:40] allows you to have opinions and edit,
[00:13:42] adjust, tell the agent it's wrong, etc.
[00:13:45] before you get into building the doc.
[00:13:48] The second artifact I want to talk about
[00:13:50] on top of the conflict log is the
[00:13:51] missing context list. One of the best
[00:13:54] signs that an agent is helping properly
[00:13:56] is that it tells you what it doesn't
[00:13:58] have to do the job well. The missing
[00:14:00] decision, the number with no source, the
[00:14:02] current version of a file that that's
[00:14:03] nowhere to be found. The completely
[00:14:06] absent data file that is referred to in
[00:14:09] only one document. All that matters
[00:14:11] because the missing material is often
[00:14:13] more important than the material you
[00:14:15] have. Your file can say as discussed and
[00:14:18] the actual discussion can be somewhere
[00:14:20] else. The deck can include a chart in
[00:14:21] the data source ends up being way far
[00:14:24] away and maybe not in your data room at
[00:14:25] all. Ask for the final memo or the final
[00:14:29] output or whatever you're writing too
[00:14:30] quickly and all of those gaps become
[00:14:32] effectively hallucination traps. The
[00:14:34] model invents its way around them to get
[00:14:36] your job done and the pros looks fine
[00:14:38] and you may ship something with a very
[00:14:40] soft spot underneath and someone will
[00:14:42] find it. So ask for the missing context
[00:14:44] list first and those gaps become
[00:14:46] transparent and legible and you can
[00:14:48] review them. You can see them. You can
[00:14:50] decide whether they matter, whether you
[00:14:51] can find the source, whether you have to
[00:14:53] phrase the claim more carefully. So the
[00:14:56] full sevenfolder structure that I use
[00:14:58] inside projects, every folder name, the
[00:15:00] purposes, and all of that, I link that
[00:15:01] in the substack. It's all laid out. You
[00:15:03] can see it really cleanly there. Uh
[00:15:05] we're going to go on from here to talk
[00:15:07] about duplicates. And and I want to be
[00:15:10] really honest about this because a lot
[00:15:12] of people miss this. People think
[00:15:14] duplicate detection in files is
[00:15:16] housekeeping. But in AI work, duplicates
[00:15:19] can be a reasoning problem. If the agent
[00:15:21] sees three versions of a plan and
[00:15:23] doesn't know which one is current, it
[00:15:25] might blend them. The same transcript
[00:15:27] exported twice can get overweighted in
[00:15:29] the synthesis if you're not careful. An
[00:15:31] old deck and a new deck with similar
[00:15:32] titles can become a source for wrong
[00:15:34] claims. a revised budget sitting next to
[00:15:36] an earlier copy. It produces averaged
[00:15:38] assumptions, right? You do not want your
[00:15:40] agent deleting duplicates, but you do
[00:15:43] want it to produce a duplicates report
[00:15:46] and probably a separate folder with
[00:15:48] suspected duplicates and hand that back
[00:15:50] to you. Let the agent find the mess. Let
[00:15:52] the agent name the duplicates, name the
[00:15:54] likely duplicates, name the level of
[00:15:56] confidence, name the version families.
[00:15:58] Do not let it silently resolve the mess,
[00:16:01] especially when you care about the work.
[00:16:03] the agent finds you decide that is a
[00:16:06] really healthy way to have good clean
[00:16:09] agentic pipeline work for very
[00:16:11] complicated highv value critical
[00:16:13] knowledge work. So why does all of this
[00:16:14] matter? One more thing before I get to
[00:16:17] like how we write the prompt to get
[00:16:19] actually going into stuff. There's a
[00:16:21] reason this matters now. The agents have
[00:16:24] just gotten so much better at the
[00:16:26] details of the file manipulation I'm
[00:16:28] talking about. They really do walk
[00:16:30] folder trees cleanly. They open files
[00:16:32] well. They inspect metadata. They're
[00:16:34] good at actually doing the nitty-gritty
[00:16:37] work of file comparison at high fidelity
[00:16:40] across hundreds of documents for a long
[00:16:42] period of time. And so file organization
[00:16:45] used to be something we had to do to
[00:16:47] housekeep for ourselves. Increasingly, I
[00:16:50] think of it as a canvas that we have to
[00:16:53] work with the agent to create so that
[00:16:55] the final work reflects the underlying
[00:16:58] data. In that sense, the data underneath
[00:17:00] is the substrate for the canvas. It's
[00:17:01] that white gesso that's on the surface
[00:17:03] of the canvas and then you paint across
[00:17:05] it the work you want to create with your
[00:17:06] agent. But if you don't get the canvas
[00:17:09] right, you're never going to get the
[00:17:11] final work to look right. And that's
[00:17:13] what we're doing with a data room.
[00:17:14] You're framing the work. Literally,
[00:17:16] you're framing the work. And because we
[00:17:17] are now doing harder work because the
[00:17:19] agents are more capable, our traditional
[00:17:22] ways of compensating don't work. You
[00:17:24] used to be able to compensate for a
[00:17:25] messy folder with a sharp prompt. It's
[00:17:27] too big now. You can't now. The mess is
[00:17:30] becoming structural and entangled and
[00:17:32] it's becoming something that you can't
[00:17:33] clean up with a single prompt. The mess
[00:17:36] is sitting inside the agent's context
[00:17:38] window and it's something that the agent
[00:17:40] will disentangle in the best way it
[00:17:42] knows how. And the risk is actually
[00:17:44] higher because the agent will find you
[00:17:46] know no matter what come hell or high
[00:17:48] water and a way to disentangle it
[00:17:50] because that's its job and it's trained
[00:17:52] to go after that task aggressively. You
[00:17:54] may just not have ever seen that way of
[00:17:56] disentangling it. you may not be
[00:17:57] aligned. And that's exactly where you
[00:17:59] get the kinds of hallucinations that we
[00:18:02] saw in the law firm at the top of this
[00:18:03] video. That's that's the structural
[00:18:06] reason those sorts of things start to
[00:18:08] surface in final materials. Now, the
[00:18:10] good news is we're finally at the prompt
[00:18:12] part. I know you guys are waiting for
[00:18:13] it. Once the room is in shape, once you
[00:18:16] have inventory, conflict log, missing
[00:18:18] context list, duplicates report, the
[00:18:20] writing prompt actually gets really
[00:18:22] short. It's not long and the output gets
[00:18:24] much better. Before the room, the prompt
[00:18:27] was like, "Write me a strategy memo.
[00:18:29] Here are a bunch of files." And then if
[00:18:30] you're doing prompt engineering, it's a
[00:18:32] very detailed like, "Here's what I want
[00:18:33] you to write." After the room, after you
[00:18:35] have your data together, the prompt is
[00:18:38] very simple. Use the reviewed source
[00:18:40] inventory in the project room in the
[00:18:41] working brief. Treat the current
[00:18:43] operating plan as authoritative for
[00:18:45] numbers, the transcript as source
[00:18:47] material for decision context, and the
[00:18:48] older deck as background only. Draft the
[00:18:50] memo, site claims, flag anything not
[00:18:52] supported. The key here is that all I'm
[00:18:55] doing in that prompt is I am saying this
[00:18:59] is what matters to me. This is what I
[00:19:01] care about from a conflict perspective.
[00:19:04] This is what I think the authoritative
[00:19:06] true line is for this piece of work that
[00:19:08] we're working on together. And then you
[00:19:11] go do the rest. And this makes the AI's
[00:19:14] work inspectable. It's not that I'm
[00:19:16] saying if you do this the AI's work will
[00:19:17] be perfect. But it is the difference
[00:19:19] between using AI as a colleague and
[00:19:22] using AI as a gopher. And we are really
[00:19:26] underusing these agents if we treat them
[00:19:28] like gophers and say just go deal with
[00:19:29] stuff and we don't give them any any
[00:19:32] ability to think about their structure
[00:19:34] and their context with us. They are more
[00:19:36] senior than that. Now our AI agents
[00:19:38] deserve to be able to shape their
[00:19:40] context windows and their data rooms
[00:19:42] together with us if we want to get the
[00:19:44] most out of them. and they are capable
[00:19:46] of doing so. Now, a word on calibration
[00:19:48] before I close. I am talking
[00:19:50] specifically about agents for serious
[00:19:53] knowledge work. Right? If you are
[00:19:55] working with codecs for a 30, 40, 50
[00:19:57] hour, two-hour run, this makes sense. It
[00:20:00] makes sense for coding. It makes sense
[00:20:02] for heavy knowledge work like I've been
[00:20:03] discussing with projects and reports. Do
[00:20:06] not run this workflow on every casual
[00:20:08] interaction with AI. It's way overkill.
[00:20:10] Also obviously I am not talking about
[00:20:12] using this approach to produce agentic
[00:20:15] pipelines that take care of back office
[00:20:17] operations. You still need a data
[00:20:19] strategy. You need to think about how
[00:20:20] you input data. That's important and I
[00:20:22] cover it in other videos, but it's not
[00:20:24] this problem. And yes, I have more
[00:20:26] prompts on the Substack. I know that not
[00:20:28] everyone has the exact prompt situation
[00:20:30] that I gave you. If you want more sample
[00:20:32] prompts that kind of cover a wider
[00:20:34] variety of use cases for this kind of
[00:20:35] knowledge work, it's on the Substack.
[00:20:37] you can grab them and apply it to your
[00:20:39] messiest folder this week. It'll help.
[00:20:40] So, in closing, here's the mental model
[00:20:43] shift that I want you to walk away with.
[00:20:45] I'm really passionate about this. I
[00:20:47] think this is one of the most slept on
[00:20:48] implications of AI in the last 40 days
[00:20:50] and and we're not talking about it
[00:20:52] enough because it's files and it's
[00:20:53] boring. The old AI question was whether
[00:20:55] the model could do the thing, right?
[00:20:56] Could it write the memo? Could it make
[00:20:58] the spreadsheet? Could it write the
[00:20:59] code? Those questions still matter.
[00:21:01] They're just not the most powerful
[00:21:03] questions anymore because the models
[00:21:05] have gotten so good. The new question is
[00:21:06] whether the agent can help prepare the
[00:21:08] conditions under which good work
[00:21:10] happens. Can it shape the canvas? Can it
[00:21:12] find the right sources? Can it tell
[00:21:14] which ones are current? Can it identify
[00:21:16] what's missing before it invents around
[00:21:18] the missing thing? That's where agents
[00:21:20] start to feel really useful as
[00:21:22] colleagues for real work. Because an
[00:21:23] agent can walk into a messy room, it can
[00:21:25] turn on the lights. It can label what's
[00:21:27] in all of the folders. And it can get
[00:21:29] the entire desk area organized for
[00:21:31] serious work. That is an AI worth using.
[00:21:35] Please use your AI that way. And I'm
[00:21:37] talking specifically about Chad GPT 5.5
[00:21:41] and Opus 4.7. I would not do this with
[00:21:43] earlier models. I hope this has been
[00:21:45] helpful. There will be more practical
[00:21:46] tips coming on this channel shortly, so
[00:21:48] subscribe for more. Cheers.
