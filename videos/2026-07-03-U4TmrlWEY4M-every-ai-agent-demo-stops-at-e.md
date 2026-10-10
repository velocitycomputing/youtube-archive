---
video_id: U4TmrlWEY4M
title: Every AI Agent Demo Stops at Email. I Pointed Mine at the Bills That Cost You Money.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=U4TmrlWEY4M"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 944
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 71
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 94
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What was discussed:** Most AI agent demos stop at email and calendar because those are safe starting points, but this misses the real opportunity. The presenter demonstrated a reusable "skeleton" of nine components—ingestion, chunking, normalization, storage, retrieval, citation, export, and gating—that works across low-stakes (email scheduling) and high-stakes (insurance appeals, tax organization) work. The key insight is that agents excel not at taking action (sending, filing, paying) but at transforming messy unstructured documents into clean, normalized, citeable case files that humans can review and act on with confidence. All three example builds used identical underlying structure, creating a "flywheel" where each new application reuses the same primitives, making subsequent builds faster and cheaper.

**What's actionable for you:** Start with a low-stakes agent task like email to learn the pattern without risk, then apply the same skeleton to the messy paperwork folders costing you money or time (insurance denials, tax documents, medical records, education forms). Build systems, not one-offs—invest in normalizing and citing your data, and your agent can handle increasingly complex work with cheaper models. Always gate the final step: the agent organizes, drafts, and cites; *you* review and submit. Identify your own "folder you haven't opened" and point this agent skeleton at it; the bridge from simple scheduling to high-stakes financial or healthcare work is shorter than you think.

## Transcript

[00:00:00] Every AI agent demo that you've seen
[00:00:02] this year starts in the same place,
[00:00:04] email and calendar, or I feel like I've
[00:00:06] seen a ton of them. You draft the
[00:00:08] replies, you schedule the meetings, and
[00:00:10] and I get why, right? So many of us have
[00:00:12] this problem every single day. It's
[00:00:14] where we spend a lot of time, bad and
[00:00:16] Slack, but here's the trap that I see a
[00:00:18] lot of us fall into. We set up the
[00:00:20] agent, it kind of works, and we're kind
[00:00:22] of stuck from there because we don't
[00:00:23] know how to go from that level of work
[00:00:27] where you're just getting some of your
[00:00:28] day-to-day stuff triaged to real work
[00:00:30] like insurance, like like payments, like
[00:00:33] health care that takes a lot of
[00:00:36] delicacy, that takes real trust. So,
[00:00:39] today, we're going to solve that for
[00:00:40] you. I'm going to build one agent
[00:00:42] skeleton live. We're going to learn
[00:00:44] about it on email and calendar, where
[00:00:46] mistakes are cheap. And then I'm going
[00:00:48] to show you how I use the same agent
[00:00:50] machinery to actually build a real
[00:00:54] delicate work, highstakes agent that
[00:00:56] handles insurance and tax stuff. When
[00:00:59] you tackle agent problems, here's the
[00:01:01] frame I want you to use. That tax folder
[00:01:04] you haven't opened, uh maybe the
[00:01:05] insurance denial that you never
[00:01:06] appealed, uh those kinds of problems
[00:01:10] look like different problems to us
[00:01:12] because we organize them by domain,
[00:01:14] health versus taxes. But anytime you're
[00:01:17] dealing with files or paperwork, it's
[00:01:19] not a different problem. From an agent's
[00:01:22] perspective, it's the same thing. It
[00:01:24] requires an understanding of policy. It
[00:01:28] requires an understanding of category.
[00:01:30] It requires an understanding of detail.
[00:01:32] And you don't have good organization to
[00:01:34] get any of that out. In other words,
[00:01:36] it's a messtofile organization problem
[00:01:39] first and then you get structured
[00:01:41] insights out. That is a common pattern
[00:01:43] across a lot of our delicate high trust
[00:01:46] paperwork issues that bedevil our lives
[00:01:49] and cost us time after time. I see the
[00:01:51] same thing when I'm booking medical
[00:01:52] appointments, right? You see the same
[00:01:54] thing with education forms. Anytime that
[00:01:57] you have to take a bunch of stuff and
[00:02:00] turn it into structured context that you
[00:02:02] can use for a delicate operation, it's
[00:02:04] the same fundamental agent principle.
[00:02:06] Now, when we talk about agents, we
[00:02:09] almost always talk about action, right?
[00:02:10] the agent will do something. It will
[00:02:12] send an email or file something. And I
[00:02:15] get it, right? It looks really good, but
[00:02:17] when you're doing high trust work, I
[00:02:20] would encourage you and I would ask you
[00:02:22] to focus on the part that the agent
[00:02:24] actually lifts the weight on. Like I'm
[00:02:26] interested in agents that lift the load
[00:02:28] off. And and to me, an agent that can
[00:02:30] sort through bureaucracy with
[00:02:32] unstructured context with the mess in my
[00:02:35] folder. Uh that's more useful to me than
[00:02:38] an agent that can click a button. I can
[00:02:40] click the button. I need the agent to
[00:02:42] get everything ready so that clicking
[00:02:44] that button is really easy. And so the
[00:02:45] skeleton we're building today does nine
[00:02:47] things. And you're going to see every
[00:02:49] one of them on screen. So I'll just say
[00:02:50] them once. We're building a context
[00:02:52] pack. We're building injust. We're
[00:02:54] building chunking. We're building
[00:02:56] normalizing, storing, retrieving,
[00:02:58] citing, exporting, and gating. And yes,
[00:03:00] agents will help with all of it. That
[00:03:02] last one, the gate, is the rule from the
[00:03:04] top of this video. If the agent can read
[00:03:06] and organize and draft and site, that's
[00:03:08] great. but it's not allowed to submit or
[00:03:10] pay or sign. And I want to be clear,
[00:03:13] this is a job that we're giving the
[00:03:15] agent from the beginning. So, it has
[00:03:17] good guard rails. We're not giving the
[00:03:19] agent ever the option to take an
[00:03:22] unallowed step. And it's up to you as
[00:03:25] the human to keep that guardrail in
[00:03:28] place as you build and to ensure that
[00:03:29] you are actually testing this stuff and
[00:03:32] you are actually validating before you
[00:03:33] submit an insurance claim or a tax claim
[00:03:35] that it's on you as the human to submit
[00:03:38] it. It's not on the agent. So, here's
[00:03:39] how we're going to run this. We're going
[00:03:40] to have three builds all in this video.
[00:03:43] Same fundamental structure. What I'm
[00:03:44] trying to teach you is one structure
[00:03:46] that scales. We're going to start easy.
[00:03:48] We're going to start with your email and
[00:03:49] calendar, which is unstructured mess,
[00:03:50] but very low stakes. Then, I'm going to
[00:03:52] stop and I'm going to show you the
[00:03:54] bridge, the actual move that takes you
[00:03:56] from the calendared email world to the
[00:03:58] more advanced part. And it's something
[00:03:59] everybody skips. And then, we're going
[00:04:01] to get into insurance appeals and then
[00:04:03] taxes as some of our advanced use cases,
[00:04:05] our 2011 use cases, if you will. So,
[00:04:08] let's get started. All right, we're
[00:04:09] going to get into build one. And let's
[00:04:11] be honest, your inbox is probably a
[00:04:13] dumpster fire. Mine certainly was, too.
[00:04:15] And it's not because we're disorganized.
[00:04:17] I'm going to keep saying that. It's
[00:04:18] because email is effort that other
[00:04:20] people give to us. Everything lands
[00:04:22] there, not on our agenda. And it's so
[00:04:25] hard to structure it. Now, let's notice
[00:04:27] something before we start. This is not
[00:04:29] just the training wheels example. Your
[00:04:31] W2 is probably in that inbox somewhere.
[00:04:33] I know mine was. The denial letter from
[00:04:35] an insurance company may have arrived as
[00:04:37] a PDF attachment. You may have notes
[00:04:39] from your doctor leading to secure
[00:04:40] messages. The trusted work we're
[00:04:42] building toward is often email mediated.
[00:04:45] Here's a thread where someone's trying
[00:04:46] to schedule a meeting with me. The agent
[00:04:48] gets a context pack. That's the first
[00:04:50] skeleton idea that I talked about. And a
[00:04:52] context pack just defines what the agent
[00:04:55] is allowed to read. This thread, my
[00:04:57] calendar constraints, the people
[00:04:58] involved. And it has one goal. Prepare a
[00:05:01] reply with a proposed calendar hold.
[00:05:03] Notice the word prepare. Watch what it
[00:05:05] does. It ingests the thread. It pulls
[00:05:08] out the people, the date ranges, the
[00:05:10] time zone mismatch. Dates become dates.
[00:05:13] People become people. That's what
[00:05:14] normalization is called. And I know it
[00:05:16] sounds boring, but this boring stuff is
[00:05:19] what makes the agent do useful high
[00:05:21] trust work. I promise you it's worth it.
[00:05:23] So the agent checks my constraints. It
[00:05:25] drafts the reply and it builds the
[00:05:26] proposed calendar of Now watch this
[00:05:29] because this is the moment the whole
[00:05:30] video turns on. The draft is done and
[00:05:32] the next obvious thing would be to send
[00:05:34] it and and the agent stops and I want it
[00:05:37] to. It leaves the draft. It leaves the
[00:05:38] proposed hold and it leaves a receipt.
[00:05:40] What sources it used? What it changed?
[00:05:42] What still needs my approval? And if
[00:05:44] it's right, I'll just send it. If it's
[00:05:46] wrong, I can fix it. That receipt to me
[00:05:50] is critical. It's the difference between
[00:05:52] AI handled it and I know what happened
[00:05:55] here and I can trust the AI. It is so
[00:05:57] important to build for trust from day
[00:05:59] one. if you ever want your AI to do
[00:06:01] stuff that involves high value delicate
[00:06:04] work where real money is on the line
[00:06:06] where real value is coming back to you
[00:06:09] because like you we all know like if we
[00:06:10] appeal insurance and we win if if if we
[00:06:12] file taxes correctly and we get a refund
[00:06:15] that's real money on the lens thousands
[00:06:16] of dollars potentially if you wanted to
[00:06:18] help with that you got to get this trust
[00:06:20] piece right now let's pause for a second
[00:06:22] because this is a move almost everybody
[00:06:24] misses and it's the reason most people
[00:06:27] never get past that initial email simple
[00:06:30] 101 agent demo. You might think that
[00:06:33] going from a basic agent like an email
[00:06:35] agent to an insurance appeal means
[00:06:37] starting over. A new tool, a new setup,
[00:06:39] a new system that's higher trust. It
[00:06:41] doesn't if you build it right. Look at
[00:06:43] what you already own from build one. You
[00:06:46] own ingestion, turning documents into
[00:06:48] text the agent can use with anchors back
[00:06:50] to the source. You own normalization.
[00:06:52] You own dates becoming dates and people
[00:06:54] becoming people. You own the receipt.
[00:06:56] You own the gate. And those are
[00:06:57] primitives or building blocks. And none
[00:07:00] of them care whether you're in a
[00:07:01] scheduling thread or an insurance denial
[00:07:04] claim. It's the same thing to the agent.
[00:07:06] And that's why I keep calling this a
[00:07:08] flywheel. Every build we do, if we're
[00:07:10] doing it right, adds a skill to our
[00:07:12] shelf. And that makes the next build
[00:07:15] cheaper. So now, let's turn around
[00:07:17] again, and let's tackle a task that
[00:07:19] actually costs you money. First, I'm
[00:07:22] going to tell you what's real and what
[00:07:23] isn't here because I want you to
[00:07:24] actually know and trust this demo. The
[00:07:26] policy documents you're about to see are
[00:07:28] real. Insurers publish their plan
[00:07:30] documents. So, this system is querying
[00:07:31] an actual insurers's actual policy
[00:07:33] language. The patient for privacy is
[00:07:36] synthetic. The denial letter is built
[00:07:38] from the kind of denial letter that
[00:07:39] people post publicly, but every
[00:07:41] identifying detail has been masked. And
[00:07:43] this build works exactly the same on
[00:07:45] your real files and yours stay on your
[00:07:48] machine. Now, some new words to learn
[00:07:50] here in the context pack. We have denial
[00:07:51] letter. We have real policies and claim
[00:07:53] histories and supporting documents. And
[00:07:55] we have a new goal. I don't want a
[00:07:57] vibes-based appeal letter. I want a case
[00:07:59] file that I can inspect. So, this is
[00:08:01] more delicate work already than the
[00:08:03] email. All right, let's get to work. The
[00:08:05] agent starts by chunking. The denial
[00:08:07] letter is not one blob, right? It's got
[00:08:09] a date. It's got a denial reason. It's
[00:08:10] got a claim number, a deadline, and
[00:08:12] somewhere in there, there's a paragraph
[00:08:14] that says, "What evidence would change
[00:08:16] that decision?" And the policy is not
[00:08:18] one blob either. It has sections and
[00:08:19] definitions and exclusions and appeal
[00:08:21] rules. Everything is getting split into
[00:08:23] tagged and addressable pieces by the
[00:08:25] agent. Now we're normalizing. Like
[00:08:28] before, dates are becoming dates.
[00:08:30] Amounts are becoming amounts. And this
[00:08:31] one matters. Missing documents are
[00:08:33] becoming missing documents. That's
[00:08:35] especially important if you have a gap
[00:08:37] in your evidence because it can affect
[00:08:38] what you can act on and you won't get a
[00:08:40] surprise a few days before some kind of
[00:08:42] deadline. All of it is stored locally.
[00:08:45] You have a little database called SQLite
[00:08:47] and you have a folder and you can open
[00:08:48] the sources and the records yourself.
[00:08:50] Nothing leaves your machine. You never
[00:08:52] have to ask the model to remember what
[00:08:53] happened. When an insurer denies you,
[00:08:55] they're required to site the specific
[00:08:57] policy language they're relying on.
[00:08:59] Think about what that means. You're not
[00:09:01] searching for something you can't find.
[00:09:02] You already know the address of the
[00:09:04] thing that's hurting you. So, there's no
[00:09:05] vector database there, only a similarity
[00:09:08] search. The system simply has to
[00:09:10] retrieve by structure the denial reason,
[00:09:13] the exact policy section, the denial
[00:09:15] sites, the deadline, and the document
[00:09:16] checklist. And the first thing that the
[00:09:19] agent is going to do when it does all
[00:09:20] this is a sanity check. Does the section
[00:09:23] they cited actually say what the letter
[00:09:25] implies that it says? Sometimes it
[00:09:27] doesn't. And when it doesn't, that's
[00:09:28] finding number one. Now, look at what
[00:09:30] this produces. There's a timeline with a
[00:09:33] service date and claim date and denial
[00:09:35] date and an appeal deadline. There's
[00:09:36] actually a denial map. There's the exact
[00:09:39] policy language that governs all of
[00:09:41] this. There's an evidence checklist,
[00:09:43] what I have right now, what isn't there
[00:09:44] yet. And yes, there's a draft appeal
[00:09:46] letter, but the letter isn't the main
[00:09:48] thing. The whole evidence packet is what
[00:09:51] really matters here because the citation
[00:09:54] map means you can actually validate that
[00:09:56] what you're arguing is true. So, here's
[00:09:59] the reframe against conventional wisdom.
[00:10:02] The agent is not winning the appeal for
[00:10:05] you. It is turning the pile of
[00:10:07] unstructured information into a case
[00:10:09] file that makes you able to win. you
[00:10:12] were losing or you didn't win because
[00:10:14] you were showing up to a structured
[00:10:16] fight with an unstructured pile. This
[00:10:18] bill doesn't guarantee that you win. It
[00:10:20] just means you stopped showing up with
[00:10:22] bad data. Now, again, watch where the
[00:10:24] agent stops. The agent has drafted the
[00:10:26] appeal, the address, the claim number,
[00:10:28] the deadline, and the viral demo would
[00:10:31] be to say, "Okay, now we're going to
[00:10:32] send it." No, it stops. And I want to be
[00:10:35] very plain about this. You are
[00:10:37] responsible for what you send. I'm not
[00:10:39] advocating anybody fire one of these
[00:10:41] packets at an insurance company unread.
[00:10:44] The citations make your review faster.
[00:10:46] They don't make it optional because if
[00:10:48] an agent sends a bad appeal on its own,
[00:10:50] now you have two problems. The denial
[00:10:52] and the mess the agent made. This is the
[00:10:54] same skeleton as our email build. The
[00:10:57] nouns may have changed, but the
[00:10:59] underlying data, the underlying
[00:11:01] structure of how we solve this problem
[00:11:03] is exactly the same from the agents
[00:11:05] point of view. And that's how we build
[00:11:06] momentum. Okay. Build number three. I'm
[00:11:09] going to show you taxes. Everybody has
[00:11:11] to deal with taxes. And I want you to
[00:11:13] notice how fast this goes now because
[00:11:15] this is the flywheel doing what I
[00:11:17] promised at the top of the video. Again,
[00:11:19] we're going to say synthetic documents
[00:11:20] here. Tax folders are things nobody
[00:11:22] should see on YouTube. Uh, and we're
[00:11:24] going to tackle some new objects, right?
[00:11:26] So, you're going to see W2s and 1099s
[00:11:28] and invoices and receipts and bank
[00:11:30] exports and mileage notes. The works.
[00:11:32] And notice where half of this stuff was
[00:11:34] living. It was living in the inbox. That
[00:11:37] dumpster fire from build one is a source
[00:11:39] now for build three. Our new goal here
[00:11:42] is we're not filing. We are preparing a
[00:11:45] reviewable packet for you or your CPA.
[00:11:47] And if you're paying somebody hundreds
[00:11:49] of dollars or thousands of dollars to
[00:11:51] painfully comb through your pile of tax
[00:11:53] docs, understand what you're paying for.
[00:11:56] You're paying for the combing. This is
[00:11:58] the combing of the docks. It's the same
[00:12:00] skeleton we already built. It goes
[00:12:02] through the same order agent-wise.
[00:12:04] You're just ingesting. You chunk it into
[00:12:06] forms. You have income, expenses,
[00:12:08] unknowns. You normalize into a tax year
[00:12:10] ledger with date and vendor and amount
[00:12:12] and category and source file. And again,
[00:12:14] we have guard rails. The citation guard
[00:12:16] won't let a deduction float through
[00:12:18] without evidence. If the agent says it's
[00:12:20] a business expense, it's going to point
[00:12:22] at the receipt or it's going to flag the
[00:12:24] line instead of pretending it knows. The
[00:12:27] export you get is a packet, not a
[00:12:29] completed 1040 return. You get an income
[00:12:32] summary, an expense ledger, a deduction
[00:12:34] evidence map, and missing docs where you
[00:12:36] have them, plus a list of questions for
[00:12:37] the CPA. And that last one is
[00:12:39] underrated. A good agent doesn't just
[00:12:41] give you answers. A good agent gives you
[00:12:43] better questions to ask an expert. And
[00:12:46] look at that. It doesn't submit. It
[00:12:48] doesn't file. It doesn't email your CPO.
[00:12:50] It preps the folder. It gives you a
[00:12:52] summary. It stops. The whole build took
[00:12:55] a fraction of the setup the insurance
[00:12:58] one did. Why? Nothing in it was new.
[00:13:00] Third turn of the wheel, much easier.
[00:13:02] This is the principle I want you to
[00:13:04] understand. You put the work into
[00:13:06] building this system. Now, you can do
[00:13:09] lots of sensitive stuff relatively
[00:13:11] easily. This is an expandable agent.
[00:13:14] We're into Legos here, people. Okay? So,
[00:13:16] hold these three builds side by side for
[00:13:18] a second. Email, insurance, and taxes.
[00:13:22] Sure, the words changed, the stakes
[00:13:24] changed, but the skeleton of the agent
[00:13:26] didn't. You still had to have a context
[00:13:28] pack and ingest and chunk and normalize
[00:13:31] and store and retrieve and site and
[00:13:33] export and gate. You've now watched me
[00:13:35] run that list three times. That is the
[00:13:38] build. Now, one more thing that all
[00:13:40] three builds share underneath. Clean
[00:13:42] normalized data. That's the secret,
[00:13:45] guys. When dates are dates and every
[00:13:48] claim has an address, you stop needing
[00:13:50] the most expensive model for most of the
[00:13:52] work. I get asked a lot, especially post
[00:13:54] fable, what's the cheapest model? It's
[00:13:56] the open- source model. Listen, this is
[00:13:58] the same play Apple wants to run on your
[00:14:00] phone. Lightweight models can do
[00:14:02] advanced things when the data underneath
[00:14:04] is clean. So, I'm laying the stage for
[00:14:06] you to think about more model choice by
[00:14:09] making sure you take care of the data
[00:14:11] first. Number one, the hard part is not
[00:14:14] the final click. The hard part is
[00:14:16] context. Fix that dirty pile of data
[00:14:18] first. Number two, learn the gate where
[00:14:21] mistakes are cheap. Where does it become
[00:14:24] expensive to do something? Number three,
[00:14:26] understand where humans need to have
[00:14:29] expertise. If it touches money, if it
[00:14:32] touches health, this is something where
[00:14:34] a professional needs to get involved and
[00:14:36] you need to not pretend that AI can just
[00:14:38] do the job. Number four, don't build one
[00:14:41] offs. Please, I'm begging you, build a
[00:14:44] flywheel like I showed you today. Every
[00:14:46] build that I'm showing you makes the
[00:14:47] next one cheaper. And the bridge from
[00:14:50] your 101 agent to your 2011 to your 301
[00:14:53] is shorter than you think. The Substack
[00:14:55] post has both of the runbooks, the
[00:14:57] healthcare appeals build and the tax
[00:14:59] prep organizer, plus the two open skills
[00:15:02] underneath them. It has a guide for
[00:15:03] context engineering, and it has
[00:15:05] runbooks. Now, here's what I'm asking
[00:15:07] you to do. Put in the comments the
[00:15:09] folder you'd point this at next, whether
[00:15:11] it's insurance or taxes or something I
[00:15:13] haven't thought of. Tell me what it is.
[00:15:15] I'll pick a few and we're going to build
[00:15:16] guides around them because this shelf is
[00:15:18] going to grow over time. Next time we're
[00:15:20] going to talk about how to put every
[00:15:22] model in the world at your fingertips,
[00:15:24] including the cheap ones. Because once
[00:15:26] your data is as clean as I've shown you
[00:15:28] in this video, you don't need an
[00:15:30] expensive model for most of this work.
[00:15:32] You just need the same agent skeleton
[00:15:34] and you can apply to different
[00:15:36] paperwork. You can keep that human yes
[00:15:38] or no at the end and you can go for it.
[00:15:41] So, subscribe for more and go open that
[00:15:43] folder and get to
