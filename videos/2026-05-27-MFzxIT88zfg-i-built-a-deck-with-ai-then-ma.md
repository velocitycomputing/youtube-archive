---
video_id: MFzxIT88zfg
title: I Built a Deck With AI, Then Made a Second AI Attack It.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=MFzxIT88zfg"
watched_date: 2026-05-27
watched_at: "2026-05-27T12:00:00Z"
watch_count: 1
duration_seconds: 1169
source: youtube-history-browser
history_label: Yesterday
history_order: 14
watched_at_precision: date-from-history-label
watched_percent: 19
estimated_watched_seconds: 222
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker explains how to reliably create Excel and PowerPoint files with AI by implementing a four-stage workflow rather than jumping straight from messy sources to finished documents. The core problem: AI-generated office files often look polished but contain undetectable errors like incorrect formulas, blended data sources, or unsupported claims. The solution involves preparation (creating a source inventory and conflict log), structure (generating a file specification with narrative spine and tab architecture before any slides or formulas), creation (building the artifact constrained by the spec), and verification (using a "hostile reviewer" prompt to systematically identify claims without sources, unexplained numbers, inconsistent formulas, and unsupported assumptions). The speaker uses CodeX to build files and Claude Opus 4.7 to review them in iterative loops, treating knowledge work like code that must pass inspection before release.

To implement this, start your next project by writing a narrative spine in plain English before opening any AI tool, then drop source materials into the system and request a source inventory with dates, owners, and status tags. Generate a storyboard with claims and evidence citations before adding visual design. Before sharing any file, run the hostile reviewer prompt: "Read this as a skeptical reviewer who suspects every claim and number. For each slide/sheet, identify claims without source attribution, numbers without data sources, charts with untraceable data, inconsistent formulas, and assumptions presented as facts. Enumerate issues—don't fix them." Use this feedback to create an edit loop, repeating verification until high-risk claims (financial calculations, regulatory language, claims reaching leadership) are defensible. This shifts your time investment from polish to accuracy, reducing downstream trust failures.

## Transcript

[00:00:00] So, finally, this is the Excel
[00:00:02] spreadsheet conversation. Finally, we
[00:00:04] get to talk about what all of these
[00:00:06] agents have made a difference for when
[00:00:08] it comes to work and office files
[00:00:10] because everything still lives in Word.
[00:00:12] It lives in Excel. It lives in
[00:00:13] PowerPoint. And when I did all of my
[00:00:16] prompting guides and everything like
[00:00:17] that last year, they were hugely popular
[00:00:19] around Excel and PowerPoint. You can
[00:00:21] still find them. They're still useful
[00:00:22] for building individual assets, but we
[00:00:25] have moved past individual asset
[00:00:27] territory with what models can do now.
[00:00:30] It just isn't the same thing. I I'm not
[00:00:32] kidding you. I can now draft eight
[00:00:34] simultaneous documents at once. I don't
[00:00:36] think that's the ceiling. That's just
[00:00:37] what I happened to do this week. And I
[00:00:39] did it by focusing on the structure of
[00:00:42] the data around the document so that
[00:00:44] what I got was high high quality and
[00:00:46] very powerful. You want to think beyond
[00:00:48] that. You want to think in terms of how
[00:00:50] you build an entire infrastructure
[00:00:53] around agents that drives successful
[00:00:56] artifact creation, whether that's Excel
[00:00:58] or PowerPoint or something else. And
[00:01:00] that mindset parallels a lot of what
[00:01:03] we're seeing in the rest of the
[00:01:06] workforce as we wrestle with what it
[00:01:08] means to have agents in production in
[00:01:10] 2026. Because the real, you know,
[00:01:13] n-dimensional move, the big brain move
[00:01:15] right now is not to think of it as I
[00:01:17] bolt this onto my workflow, but to think
[00:01:19] of it as agents are at the heart of the
[00:01:22] new workflow. I therefore need to torque
[00:01:24] myself around, change my process, adjust
[00:01:26] everything inside so that agents are
[00:01:28] centralized and agents are first. And so
[00:01:29] a lot of what I'm going to talk about is
[00:01:31] essentially how you rebuild an office
[00:01:34] document workflow agentically. And
[00:01:36] that's the theme. That's what makes this
[00:01:37] really exciting because if you do that,
[00:01:39] that's when you get to these massive
[00:01:41] increases because if you think about it,
[00:01:43] eight documents, 10 documents, whatever
[00:01:44] it is, you're talking about an order of
[00:01:45] magnitude increase in productivity on
[00:01:48] just knowledge work. That's huge. And I
[00:01:50] don't see that happening. In fact, I
[00:01:52] know that's not happening because I have
[00:01:53] talked to folks at Hyperscalers about
[00:01:55] what I'm doing and they're like, "Oh,
[00:01:56] wow. That's actually really cool. We
[00:01:57] didn't know that these models could do
[00:01:59] that." Well, they can. And we're going
[00:02:01] to show you how. Claude can build Excel
[00:02:03] and PowerPoint files. Chat GPT analyzes
[00:02:06] any spreadsheet you drop into it. So
[00:02:07] does Codeex. Microsoft Copilot for
[00:02:09] Office hit general availability in
[00:02:11] April. Everybody watching this video has
[00:02:13] access to AI that can build a PowerPoint
[00:02:16] deck in minutes. What you don't have is
[00:02:19] a way to know that the deck is correct,
[00:02:21] accurate, and complete. A and I know
[00:02:23] this because I've lived it. Last
[00:02:25] quarter, I opened an Excel file that
[00:02:26] looked like a financial model.
[00:02:28] Assumption inputs at the top, revenue
[00:02:29] projections, valuation outputs rolling
[00:02:31] up very cleanly. There was a written
[00:02:33] guide attached saying the model had been
[00:02:35] validated. And then I opened the revenue
[00:02:37] growth row and the formula was incorrect
[00:02:39] and it was copied across every future
[00:02:41] year from the same two cells year after
[00:02:43] year. Excel didn't tell me that. There
[00:02:45] was no ref error. The valuation output
[00:02:47] still looked good, but it was a
[00:02:49] financial model in a costume. It wasn't
[00:02:52] the real thing. The the layout was
[00:02:54] right. The labels were right. The cells
[00:02:55] were incorrect. And that's obviously the
[00:02:57] only thing that matters. And the same
[00:02:59] thing is happening in a lot of docs that
[00:03:01] I see time after time in real production
[00:03:05] environments. And in this video, I want
[00:03:08] to fix that for you. I want to get into
[00:03:10] how we build workflows for agents with
[00:03:12] agents at the center that help us to
[00:03:15] build these heavy knowledge work
[00:03:17] documents in ways that ensure
[00:03:18] reliability and accuracy. The key fix is
[00:03:21] a mental shift. A prompt asks for an
[00:03:24] output. A workflow defines the stages
[00:03:26] the output has to pass through before it
[00:03:28] can be trusted. And you need to be in a
[00:03:30] workflow world, not a prompt world. So
[00:03:32] for Office files, that workflow has four
[00:03:35] stages. And we're going to go through
[00:03:37] all four. One, you have to prepare your
[00:03:39] sources. You do not ask for the deck or
[00:03:42] the spreadsheet. You ask for an
[00:03:43] inventory of what the model has to work
[00:03:46] with, and you make sure that it's
[00:03:47] organized. Two, structure. Before any
[00:03:51] slide or formula gets created, AI needs
[00:03:53] to produce a file specification. For a
[00:03:56] deck, that's a narrative spine and a
[00:03:58] slide list with claim headlines. For a
[00:04:00] workbook, it should have a tab
[00:04:02] architecture and a calculation flow. You
[00:04:04] want to go from producing that spec to
[00:04:06] then building the artifact. Right now,
[00:04:08] you build the artifact constrained by
[00:04:10] the source packet of information,
[00:04:12] constrained by the spec that you've
[00:04:14] built. You're not freestyling from
[00:04:16] whatever the model thinks the answer
[00:04:18] should be. And then four, verification.
[00:04:21] The file isn't done when it opens. It's
[00:04:24] done when it has survived a reviewer
[00:04:26] that looks at it really aggressively. I
[00:04:28] use another model for this. I actually
[00:04:29] use codeex to build office artifacts and
[00:04:32] then I use claude opus 4.7 to review
[00:04:35] them aggressively and generate edit
[00:04:36] loops. And it's like my own Ralph loop,
[00:04:38] right? Where like it finishes and opus
[00:04:40] looks at it and says, "Oh, you're not
[00:04:41] finished. Here's your edit loop to make
[00:04:43] it better." And I just keep running that
[00:04:45] until I get a very high quality set of
[00:04:47] docs. And I can run it at scale if my
[00:04:50] document source repositories are clear.
[00:04:52] I I'm increasingly thinking of knowledge
[00:04:54] work as if it was code. So the
[00:04:56] capability to generate these files is
[00:04:58] absolutely everywhere and it's far
[00:05:00] outpacing our ability to scale quality
[00:05:02] unless we have these kinds of systems
[00:05:04] like I'm talking about. I wrote about
[00:05:05] the upstream piece of this on Substack
[00:05:07] earlier this month about how to organize
[00:05:09] your sources before you ever ask AI to
[00:05:11] write anything. It's critical for this
[00:05:12] kind of work to actually scale and call
[00:05:14] that the before, right? This video is
[00:05:17] the after, how you build with it. Uh, so
[00:05:19] that link to the previous Substack is in
[00:05:21] the description. If you're interested,
[00:05:22] feel free to dive in. I think it's a
[00:05:24] nice pair with this video. Let's get
[00:05:26] back to it. The failures I worry about
[00:05:28] aren't dramatic. They're ordinary enough
[00:05:30] to survive a quick review. Right? A
[00:05:32] board deck pulled from a folder
[00:05:34] containing a Q3 actuals export and a Q4
[00:05:36] plan file. The slide headline says,
[00:05:38] "Revenue is ahead of plan." and the
[00:05:41] chart looks really clean and then you
[00:05:43] look at the underlying numbers and
[00:05:45] they're blending actuals and plan data
[00:05:47] because nobody labeled the difference
[00:05:49] and that error travels every time the
[00:05:51] deck gets shared. It traveled out of the
[00:05:52] spreadsheet or wherever it came from
[00:05:54] originally and it's a problem. So you
[00:05:56] are now in a world where you can have a
[00:05:58] great PowerPoint with sharp headlines
[00:06:00] and executive language but there's no
[00:06:02] way to show that it has a foundation. It
[00:06:05] may look finished but it has no
[00:06:07] foundation. And I want to talk to you
[00:06:09] about how you build documents reliably
[00:06:12] in a pipeline that are wellounded
[00:06:13] because that's how you actually start to
[00:06:15] build momentum with this knowledge work.
[00:06:17] Otherwise, all of this AI tooling
[00:06:19] becomes a massive trust breaker. And I
[00:06:22] want to be clear, I'm not cherrypicking
[00:06:23] edge cases here. Models are
[00:06:25] goaloriented. If you tell them to build
[00:06:27] something on a bad foundation, they'll
[00:06:30] try to do it. And that's the normal
[00:06:32] result of asking AI to jump straight
[00:06:34] from messy sources to a finished file.
[00:06:36] the model is optimizing for the artifact
[00:06:39] you asked for. And if you ask for a deck
[00:06:41] and don't give it choices, it'll try to
[00:06:42] make a deck. Same thing with a
[00:06:44] spreadsheet. Unless you explicitly
[00:06:46] define the evidence structure, the tool
[00:06:48] treats source discipline as optional.
[00:06:50] And that's backwards. Source discipline
[00:06:52] is a big part of the work. And I want to
[00:06:54] call out this is not because the models
[00:06:57] are getting worse. In fact, the models
[00:06:59] have had a lot of work put into them to
[00:07:01] care about sources. And if you give them
[00:07:03] the chance to, they will. Part of why we
[00:07:06] have to have this conversation now is
[00:07:08] that the models are trained to check
[00:07:10] claims and look at sources. And if you
[00:07:11] don't take the same care as the models
[00:07:13] do, the models will try to take that
[00:07:15] care, try to look at sources. And that
[00:07:18] very goalorientedness to build
[00:07:21] completely will betray you because you
[00:07:24] have no clean sources for it to rely on.
[00:07:26] It will just have to work its way
[00:07:27] through and guess, but it's been trained
[00:07:29] to try and find it. So, it will try and
[00:07:31] do that and it will guess and then
[00:07:33] you'll be in trouble. And so we have to
[00:07:35] be aware of where the hyperscalers are
[00:07:38] taking the models. And the hyperscalers
[00:07:40] are basically saying models need to do
[00:07:42] better work by checking sources. They're
[00:07:43] right, but we have to do the work of
[00:07:45] making sure the sources and the workflow
[00:07:47] pipelines are there so the models can
[00:07:49] build these office documents
[00:07:50] appropriately. And that's what serious
[00:07:52] knowledge work looks like in 2026. The
[00:07:54] goal is to make every important claim
[00:07:57] and calculation something that can be
[00:07:59] checked and that invites that scrutiny.
[00:08:01] And so you have two stages here, right?
[00:08:03] You have source prep. That's stage one.
[00:08:06] Before you ask AI for the deck or the
[00:08:08] workbook, you need to ask AI to look at
[00:08:10] what it can see. What's in the folder?
[00:08:12] Find out what your work packet has. Does
[00:08:14] does everything in the work packet have
[00:08:16] an owner and a date and a file type? And
[00:08:19] can you create an index of evidence that
[00:08:21] has all of that? Does it have a status?
[00:08:23] Has the AI said if it's current data or
[00:08:25] superseded? If it's an estimate, if it's
[00:08:27] a transcript, if it's raw data, have you
[00:08:30] removed sensitive material that would
[00:08:31] need to be removed before any public-f
[00:08:33] facing artifact gets generated? That
[00:08:35] does happen, too. Uh, have you checked
[00:08:37] your facts and your estimates based on
[00:08:39] research on the net? This one move
[00:08:42] changes the process. A messy folder can
[00:08:44] become a controlled work packet. The AI
[00:08:46] can't blend a transcript and a deck and
[00:08:48] a spreadsheet and a half-remembered
[00:08:49] assumption into a confident answer if
[00:08:51] you've organized everything and if
[00:08:53] there's an index of what's in there.
[00:08:55] Stage two is structure. Before any file
[00:08:57] gets created, you need to produce a file
[00:09:00] specification. At least if you're doing
[00:09:02] serious work. I'm not saying every
[00:09:03] single time you have a conversation with
[00:09:04] Jet GPT. Don't don't misunderstand me.
[00:09:06] I'm saying when you're doing serious
[00:09:07] knowledge work that has implications. So
[00:09:09] for PowerPoint, that's the narrative in
[00:09:11] English in a way that you understand.
[00:09:13] And do insist on plain English. One of
[00:09:15] the issues with the current models is
[00:09:16] they like cute language. They like
[00:09:18] shortorthhand. Insist on plain English.
[00:09:20] Who is the audience? What decision do
[00:09:21] they need to make? What do they need to
[00:09:23] believe before they can make that
[00:09:24] decision? And then look at the list of
[00:09:27] slides. What are the claims? What are
[00:09:29] the supporting source IDs? Where are
[00:09:30] charts needed? What are the assumptions?
[00:09:32] What are the open questions? And for
[00:09:34] Excel, you need to look at your tab
[00:09:35] architecture. Where does raw data live
[00:09:37] in the tab? Where do the assumptions
[00:09:38] live? Where are calculations performed?
[00:09:41] Where are checks recorded? Where does
[00:09:42] the user see the summary and how is it
[00:09:44] driven? So the file spec is like a
[00:09:46] blueprint for a serious doc. If the
[00:09:48] blueprint doesn't explain where the
[00:09:51] truth lives, the finished file won't do
[00:09:53] that either. So, if you're wondering how
[00:09:55] to get started, there is a full source
[00:09:56] packet template on the Substack,
[00:09:59] including an ID schema, a status
[00:10:00] taxonomy, a conflict log format. If you
[00:10:03] want to copy it for your team for the
[00:10:04] next big project you do, I've linked it
[00:10:07] in the description. Let's move on here,
[00:10:09] though. I want to talk about file
[00:10:10] creation. This is the part we all want,
[00:10:12] right? How can we create this stuff? So
[00:10:15] only now does AI actually build the
[00:10:17] artifact. After you prep for PowerPoint,
[00:10:20] I would do it in two passes. First pass
[00:10:22] is the storyboard. You want slide titles
[00:10:24] and claims and evidence and notes. Don't
[00:10:27] design render yet. No charts laid out,
[00:10:29] just the argument and the evidence
[00:10:31] trail. Second pass, render the deck.
[00:10:34] This split keeps visual polish from
[00:10:36] hiding a weak argument. And you catch
[00:10:38] unsupported claims before they become
[00:10:40] beautiful and difficult to edit. Right
[00:10:42] now I am doing all of the argumentation
[00:10:45] in codec and I'm moving to claude opus
[00:10:47] 4.7 for the render of the deck because
[00:10:49] that front-end polish is just beautiful
[00:10:51] and claude for Excel do it in three
[00:10:53] layers. Layer one load the raw data
[00:10:56] exactly. Layer two build the assumptions
[00:10:58] in the calculation logic and layer three
[00:11:01] produce the output views. A workbook
[00:11:03] should be able to answer a very simple
[00:11:05] question. If I change an assumption,
[00:11:07] does the relevant output change for the
[00:11:09] right reason? And that question matters
[00:11:11] a lot more than whether the workbook
[00:11:12] itself looks good. A spreadsheet that
[00:11:14] cannot recalculate isn't a model. A
[00:11:17] model whose formulas can't be inspected
[00:11:19] isn't ready for decisioning. Right now,
[00:11:21] what I am doing is I am using codeex to
[00:11:24] build Excel models and then I am having
[00:11:27] Claude take a pass at making them pretty
[00:11:29] afterward. But I find that codeex is
[00:11:31] really really good at completeness in
[00:11:33] Excel files and that's really important
[00:11:35] when you're trying to build serious
[00:11:36] models. One more piece I want to call
[00:11:38] out here. You need to understand your
[00:11:40] task risk gradient. Where is AI highest
[00:11:43] risk or lowest risk? AI is lowest risk
[00:11:45] for formatting, layout exploration,
[00:11:47] chart drafts, summary wording and
[00:11:49] consistency checks. It's medium risk for
[00:11:51] source attribution and data extraction.
[00:11:54] And it's highest risk for numerical
[00:11:56] synthesis, for financial calculations,
[00:11:58] for any kind of regulatory language or
[00:12:00] compliance language, and for claims that
[00:12:02] will travel up to senior leadership for
[00:12:04] a decision. Make sure you check those.
[00:12:07] So yes, let the model help her
[00:12:09] everywhere. No matter what the task risk
[00:12:10] gradient is, it's faster with the model.
[00:12:12] Now, don't give every task the same
[00:12:14] review burden depending on the risk. If
[00:12:16] you want to understand how to dig into
[00:12:18] that further, there's more on that in
[00:12:19] the substack. I broke down the full file
[00:12:21] specification format. There's a
[00:12:23] PowerPoint narrative spine template.
[00:12:25] There's an Excel tab architecture.
[00:12:27] There's assumption log fields. And there
[00:12:29] are sort of checks, tab, smoke alarms
[00:12:31] you can set in Excel that I put
[00:12:32] together. So, if you want the full
[00:12:34] version both for PowerPoint and Excel,
[00:12:36] the link is in the description. We're
[00:12:38] going to move on though to one of the
[00:12:39] things I think is most important, and
[00:12:41] that's verification with a hostile
[00:12:43] reviewer prompt. So verification asks
[00:12:46] whether the artifact can be trusted.
[00:12:48] Sources, dates, formulas, assumptions,
[00:12:50] charts, and unsupported claims. Every
[00:12:53] one of these gets inspected. It's a
[00:12:54] different job from proofreading, and
[00:12:56] most teams tend to skip it because the
[00:12:58] file can look done much sooner than it's
[00:13:00] actually done. The useful pattern is to
[00:13:03] make the model itself act as a hostile
[00:13:05] reviewer. You you can use the same
[00:13:08] model. I use different models for this.
[00:13:09] I like to play them off against each
[00:13:11] other. So, I use Opus 4.7 to review what
[00:13:14] 5.5 does. I think that's super fun. Uh,
[00:13:16] and I'm going to give you the prompt
[00:13:18] right here. So, you know, pay attention.
[00:13:19] So, the prompt is this. Read this Decker
[00:13:22] workbook as a skeptical reviewer who
[00:13:24] suspects every claim and every number.
[00:13:26] For each slider sheet, identify claims
[00:13:29] without source attribution, numbers
[00:13:31] without a data source, charts whose
[00:13:33] underlying data isn't traceable,
[00:13:35] formulas inconsistent across parallel
[00:13:38] rows or columns, and assumptions
[00:13:40] presented as facts. Produce a written
[00:13:42] list of every issue found. Don't fix
[00:13:44] anything, just enumerate. That last
[00:13:47] instruction, don't fix, just enumerate,
[00:13:49] is what makes it work. The model is just
[00:13:51] trying to find the problems. It's not
[00:13:52] trying to solve them. different task,
[00:13:54] different output, different value. A
[00:13:56] model can catch a lot of its own
[00:13:58] mistakes when you flip the task from
[00:14:00] generation to enumeration. And the human
[00:14:02] gate can stay on the consequential
[00:14:04] claims, the numbers that travel, the
[00:14:06] calls that are going to become an
[00:14:07] important decision. And and one of the
[00:14:09] things I want to call out here is my
[00:14:10] personal workflow is very much a Ralph
[00:14:13] loop for this. I will take a doc that is
[00:14:16] created by codeex and I will give it to
[00:14:19] opus 4.7 and I will ask opus 4.7 to do
[00:14:22] that hostile review and generate an
[00:14:23] extremely detailed edit list. I will
[00:14:26] pipe that back to codeex and I will ask
[00:14:28] codeex to fix everything in there with a
[00:14:31] new version in the same folder. Then I
[00:14:34] will go back to the same thread in open
[00:14:36] 4.7 and say check the work. Did they do
[00:14:38] the job? And then I will do it again and
[00:14:40] I will do it again. And toward the end,
[00:14:42] I will actually introduce a language
[00:14:44] check. Opus is actually very very good
[00:14:46] at checking for LLM isms like you're
[00:14:49] absolutely right in the doc, right?
[00:14:51] Something like that. And you can get it
[00:14:53] into plain English that actually works
[00:14:55] better for humans to read if you
[00:14:56] introduce that polish step later. And
[00:14:58] the overall goal is that you have an
[00:15:00] autonomous loop between codeex and opus
[00:15:03] that gets you to Alevel work without
[00:15:06] having to invest a ton of time along the
[00:15:09] way so that your time is best focused on
[00:15:11] reading A-level material and saying,
[00:15:13] "Okay, this is where I agree. This is
[00:15:15] where I disagree. This is where I would
[00:15:17] edit. Here's some final polish." And
[00:15:19] that's what it looks like to do heavy
[00:15:21] knowledge work in 2026. If we step back,
[00:15:24] AI has made it much easier to create
[00:15:26] Office files, right? And that matters a
[00:15:28] lot. PowerPoint and Excel are still
[00:15:30] where an enormous amount of business
[00:15:31] judgment becomes visible inside
[00:15:33] companies. And traditionally, they have
[00:15:34] taken real hours out of everyone's week
[00:15:38] in millions and millions of cases. If AI
[00:15:40] helps people build those artifacts
[00:15:42] faster, the productivity upside is real.
[00:15:45] It's measured in weeks a year for all of
[00:15:47] us. The upgrade is that you can now
[00:15:49] build a repeatable production system
[00:15:51] around the file. Source prep and
[00:15:53] structure and constrained creation and
[00:15:55] verification. The file is just an output
[00:15:58] of that knowledge works system. It's not
[00:16:00] the whole thing. Drag in the sources,
[00:16:02] ask for a deck, hope the output is
[00:16:04] right, that's the version of the
[00:16:05] workflow that loses you a meeting.
[00:16:07] Instead, if you prepare your sources and
[00:16:09] define your structure and create the
[00:16:11] file carefully and verify it, you're
[00:16:12] going to be trusted more and more. So,
[00:16:15] the next deck you build with AI should
[00:16:16] not start with a deck. It should start
[00:16:18] with the moves that I described. Right?
[00:16:20] Write out a narrative spine before you
[00:16:22] open the AI tool. Drop in your source
[00:16:24] materials and ask for a source
[00:16:26] inventory. Ask for a conflict log before
[00:16:28] you try and make any slides. Generate
[00:16:30] the storyboard with claims and notes
[00:16:32] before any visual rendering. And then
[00:16:34] run a hostile reviewer prompt before you
[00:16:37] decide to share it out. The model can
[00:16:39] help everywhere, but you have to keep
[00:16:41] owning the truth. This is the your
[00:16:43] polish stopped meaning trust. The
[00:16:45] companies that build a truth layer
[00:16:46] around their AI office files are going
[00:16:48] to ship a lot faster and be wrong much
[00:16:51] less. The ones that don't are going to
[00:16:53] put out a really nice looking deck next
[00:16:55] quarter with a number that nobody can
[00:16:57] defend. And by the way, if you think
[00:16:58] that's not true, I want you to remember
[00:17:00] that the team at OpenAI did that with a
[00:17:04] chart that chat GPT presumably helped
[00:17:07] make in the chat GPT5 launch. And the
[00:17:11] chart was famously wrong and everyone
[00:17:12] had a good chuckle and that happens to
[00:17:15] the best of us. We can do better than
[00:17:17] that. I want to answer one question to
[00:17:20] close us off and I think I I I think a
[00:17:22] number of you will ask this and it's
[00:17:24] simple. Nate, why is it this hard? I
[00:17:28] have to build this entire effectively
[00:17:29] knowledge work harness on my own. Why do
[00:17:32] I have to do that? Why hasn't someone
[00:17:34] made this for me so it's easier and it's
[00:17:36] just push a button simple? I have a
[00:17:38] really clear answer for you. Knowledge
[00:17:40] work is profoundly contingent on domain
[00:17:44] knowledge. That's why it's knowledge
[00:17:45] work. If you are going to do knowledge
[00:17:48] work that is specific and memorable and
[00:17:51] useful and deep, you have to be deep
[00:17:54] enough in theformational
[00:17:56] context that you can custom assemble the
[00:17:59] pieces of information you need to make a
[00:18:02] useful artifact. It's not something you
[00:18:05] can generically turn into a workflow.
[00:18:08] It's not that simple. It's not like you
[00:18:10] can assume there are five slots for
[00:18:11] evidence for a PowerPoint deck and good
[00:18:13] luck if you have more than five. No one
[00:18:15] who does serious knowledge work thinks
[00:18:16] like that. And so I think part of the
[00:18:19] reason we have to build our own, it's
[00:18:21] sort of like Luke Skywalker making his
[00:18:23] own lightsaber. You have to understand
[00:18:25] how the system works to become a master
[00:18:27] at that system. And I am sure that there
[00:18:30] are startups out there that are working
[00:18:32] on making parts of this simpler, parts
[00:18:35] of gathering the information simpler,
[00:18:37] parts of communicating that review step
[00:18:40] simpler, parts of checking the work and
[00:18:42] checking sort of the calculations on
[00:18:44] Excel simpler. All of those pieces are
[00:18:47] problems that we can get better at
[00:18:49] solving. But I don't want to lose sight
[00:18:51] of the fact that good deep knowledge
[00:18:53] work is tremendously detailed. reality
[00:18:56] has a surprising amount of detail. Good
[00:18:58] deep knowledge work is extremely
[00:19:00] detailed and it's difficult to
[00:19:02] generalize an abstraction like an
[00:19:04] abstracted knowledge work harness over
[00:19:06] that level of detail. So that's the
[00:19:07] honest answer for you. That's why we
[00:19:10] can't just get a push button answer from
[00:19:12] Microsoft that makes Excel superpowered
[00:19:14] for this. There you go. I if wishes were
[00:19:17] fishes, right? I wish it was that way.
[00:19:18] But instead, we get to work at this. And
[00:19:21] by the way, for everyone saying we'll
[00:19:22] lose our brains when we use AI, this is
[00:19:24] a great example of why you got to keep
[00:19:25] your brain turned on when you use AI.
