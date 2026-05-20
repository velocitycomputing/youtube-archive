---
video_id: LIkYVsxMpS8
title: When to Automate, Build, Buy, Hire, or Wait on AI
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=LIkYVsxMpS8"
watched_date: 2026-05-17
watched_at: "2026-05-17T12:00:00Z"
watch_count: 1
duration_seconds: 1666
source: youtube-history-browser
history_label: Sunday
history_order: 62
watched_at_precision: date-from-history-label
watched_percent: 13
estimated_watched_seconds: 217
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker argues that 40% of AI projects fail because organizations focus on vendors and models without first understanding their actual workflows. Rather than one AI problem per department, there are typically multiple distinct workflows requiring different investments—for example, an accounts receivable team needs separate solutions for collections prioritization, invoice matching, dispute resolution, and reporting. To evaluate workflows, assess how often they repeat, the cost of mistakes, required judgment, company specificity, and market solution maturity. He presents five investment levers (Automate, Build, Buy, Hire, Wait) and a decision matrix: common, well-served workflows warrant buying; company-specific workflows warrant building; immature categories warrant prototyping or waiting. Core principle: "Do not automate what you cannot describe."

Map and describe your high-priority workflows in concrete terms—inputs, outputs, standards, exceptions, ownership—before any technology decision. Apply the decision matrix: buy off-the-shelf for common work, build for company-specific work using purchased primitives, wait for immature categories. For hiring, identify the specific capability missing in six months for a particular workflow, rather than hunting for an impossible "AI unicorn." Stack your investments by leverage—prioritize workflows delivering disproportionate business impact and organizational learning first, defer lower-priority ones. Automate only routine, clearly-defined processes, and frame AI as enabling people to do higher-impact work, not replacing them.

## Transcript

[00:00:00] The Cretaceous extinction is coming,
[00:00:02] right? Gartner has a line that says more
[00:00:04] than 40% of Agentic AI projects will get
[00:00:07] killed by the end of 2027. Uh why? I
[00:00:10] mean, it's pretty predictable if you're
[00:00:11] in the space, right? Cost, unclear
[00:00:13] business value, inadequate risk
[00:00:14] controls. I have seen all of these
[00:00:15] firsthand. They do happen. So, if you're
[00:00:18] reading the headline and you're
[00:00:19] thinking, well, the issue is agentic
[00:00:21] tech. No, it that's not why these issues
[00:00:24] are coming up. We find over and over
[00:00:26] again success stories where we see
[00:00:28] excellent productive agentic workflows.
[00:00:30] That's why so much money is flowing into
[00:00:32] this space. This video is about how to
[00:00:36] think about your investment logic in
[00:00:40] your AI projects so that you adequately
[00:00:44] invest in the parts of the project that
[00:00:47] truly drive value versus investing in
[00:00:50] levers that are likely to make you
[00:00:52] disappointed and you end up on that 40%
[00:00:55] Gartner list. Look, I had a finance
[00:00:57] leader tell me last month that her CFO
[00:01:00] wanted to do AI in orders to cash and
[00:01:04] three vendors had quoted her three
[00:01:06] different shapes of solution. None of
[00:01:08] them had described the actual work that
[00:01:12] she was doing. And I got to tell you,
[00:01:14] every conversation in this space feels
[00:01:16] like that where like the people inside
[00:01:18] the business are saying this is what we
[00:01:20] need. They don't fully understand what
[00:01:22] that looks like from a workflow
[00:01:23] perspective. And there's about 10
[00:01:25] million vendors knocking down the door
[00:01:27] saying, "Here, we'll sell it to you.
[00:01:29] This is what you need. I promise you,
[00:01:30] this is what you need. You don't
[00:01:31] understand AI, but this is what you
[00:01:32] need." We need to take a minute. We need
[00:01:35] to shut the proverbial door to all the
[00:01:37] vendors for just a second and have a
[00:01:38] conversation inside the house about
[00:01:41] where we invest, why we invest, and what
[00:01:44] is likely to yield success from an
[00:01:46] agentic workflow perspective. And that
[00:01:48] is what this video is about. So here's
[00:01:50] the first thing that I see going wrong
[00:01:53] in the conversations I've had a peak in
[00:01:54] and conversations execs have shared with
[00:01:56] me privately etc. First and foremost AI
[00:02:00] investment is not an AI question. It is
[00:02:03] actually a question about the shape of
[00:02:05] our work. The model question is
[00:02:07] downstream of that. The vendor question
[00:02:09] is downstream of that. The dashboard or
[00:02:11] whatever you want to build and show is
[00:02:12] downstream of that. What sits at the
[00:02:15] root of the whole conversation is how
[00:02:16] the work itself is shaped and
[00:02:18] accomplishes value. But it's really hard
[00:02:20] to talk about that. We don't have a good
[00:02:23] vocabulary for it. And I find in
[00:02:25] practice most teams skip that step,
[00:02:27] especially if their vendors encourage
[00:02:29] them to do that, which so many do. Let
[00:02:32] me give you an example here. An accounts
[00:02:34] receivable team does not have one
[00:02:37] singular AI problem in the space. They
[00:02:40] have, you know, half a dozen, maybe
[00:02:42] eight. They have to tackle collections
[00:02:44] prioritization. They have to tackle
[00:02:45] invoice matching, customer followup,
[00:02:48] exception handling, cash application,
[00:02:50] dispute resolution, reporting, and
[00:02:52] escalation. Those are all very different
[00:02:54] shapes of work. They route to very
[00:02:56] different investments. Like you might
[00:02:58] buy some, you might build some, etc. If
[00:03:01] you pile all of them into a single RFP,
[00:03:04] which I see happening a lot, you're
[00:03:06] going to get a mediocre tool that does
[00:03:08] maybe one of them well and isn't
[00:03:10] adequately covering what you really need
[00:03:12] and maybe covers a bunch of other stuff
[00:03:13] in another department. It's just not
[00:03:15] going to be a great fit. What if we look
[00:03:17] at product? It's a similar situation,
[00:03:19] right? User research synthesis is in one
[00:03:22] shape of work. Spec drafting is in
[00:03:24] another shape of work. Backlog grooming
[00:03:26] and design review and experiment
[00:03:28] analysis and roadmap judgment and launch
[00:03:30] coordination and customer escalation are
[00:03:32] all different shapes of work. Maybe some
[00:03:34] of them are builds, maybe some of them
[00:03:35] are buys. The unit of decision for AI is
[00:03:38] not your department head. It's not a
[00:03:41] particular role. It is that work that I
[00:03:43] am naming. Now, quick definition before
[00:03:46] I go further. When I say workflow, I
[00:03:48] don't mean a prompt. I mean the entire
[00:03:51] operating loop. what information comes
[00:03:53] in, what the system is allowed to do,
[00:03:56] and what good output looks like, who's
[00:03:59] checking what, what gets escalated, who
[00:04:01] owns and is accountable for what the
[00:04:03] result is. The AI model is a tiny tiny
[00:04:06] part of that loop. It does make the
[00:04:07] whole thing go. It's like the brains of
[00:04:09] the business. I get it, right? It's a
[00:04:10] big deal to have an AI model in a loop.
[00:04:12] That's why we're having this
[00:04:14] conversation, but it's not the only
[00:04:15] thing. And if you want to understand how
[00:04:18] to invest correctly, you have to think
[00:04:20] less in terms of model and more in terms
[00:04:22] of the workflow because the workflow is
[00:04:25] what you are actually investing in.
[00:04:27] That's what gives you leverage if you do
[00:04:28] it better. Once you get to that level,
[00:04:30] the question becomes much easier to
[00:04:32] follow. Every workflow can be evaluated.
[00:04:34] There are handful of obvious inputs. How
[00:04:36] often a workflow repeats? How costly a
[00:04:38] mistake is in that workflow? How much
[00:04:40] judgment does that workflow need? How
[00:04:42] specific to you is that workflow? Does
[00:04:44] the market have a solution here? Is the
[00:04:46] next model release going to eat this
[00:04:48] workflow? Uh where does the workflow
[00:04:50] output go? So I want you to think about
[00:04:53] your workflows. Think about your high
[00:04:54] priority workflows in that sort of
[00:04:57] deeply inshed detailed understanding.
[00:05:02] And I want you to then walk into your
[00:05:04] investment decision from there. Then you
[00:05:06] walk into well do I build? Do I buy? Do
[00:05:10] I wait? Do I kill the workflow? do I
[00:05:13] hire for it? You really only have five
[00:05:15] options or five levers when it comes to
[00:05:17] your workflows. You can either automate
[00:05:19] it away. Uh you can also call that
[00:05:21] eating or deleting the workflow. It's
[00:05:22] similar. You can build that workflow in
[00:05:25] detail with AI and it's a complicated
[00:05:27] workflow and it's not fully automated,
[00:05:28] but there's big AI components. Uh you
[00:05:31] can just buy a solution off the shelf
[00:05:32] and take care of it. Uh you can hire and
[00:05:34] those smart people are supposed to help
[00:05:36] you make the right calls or you can just
[00:05:38] do nothing and wait. And by the way,
[00:05:40] often times the solution is a mixture of
[00:05:43] those. So you have to think about moving
[00:05:44] more levers at once. Like I've seen
[00:05:45] cases where someone wants to build, but
[00:05:47] they need to hire to build first. For
[00:05:48] example, of those levers, the easiest
[00:05:51] call is to automate. If you're going
[00:05:52] through your workflow priorities,
[00:05:54] automation is the one that most teams
[00:05:56] understand. Automation, deleting, eating
[00:05:58] the workflow. It's the right call when
[00:06:00] the work repeats often, follows a clear
[00:06:02] pattern, has recognizable exceptions
[00:06:05] that you can define, and you can check
[00:06:07] if it's good really cheaply. So IBM ask
[00:06:09] HR is a great example there. Another one
[00:06:11] if you're thinking well that's build
[00:06:13] Nate you're doing multiple levers. Yeah
[00:06:14] we're doing multiple levers. Another one
[00:06:16] is uh a buy lever plus an automate lever
[00:06:19] and that might be Finn. So Finn is an
[00:06:21] agent from intercom and is really tasked
[00:06:24] with sort of tackling repeatable
[00:06:26] customer support case volume. Now there
[00:06:29] are folks that build that. Finn is a
[00:06:30] case where you can buy that but it's a
[00:06:32] similar idea. But whatever it is, you
[00:06:35] cannot be religious about automating.
[00:06:38] You need to be focused on where the
[00:06:40] value is in the system and where AI can
[00:06:43] handle it versus where a human can
[00:06:45] handle it better, whether you're dealing
[00:06:46] with internal or external audiences. So
[00:06:49] regardless, automation makes sense where
[00:06:52] routine cases dominate and exceptions
[00:06:54] are easy to understand. Don't automate
[00:06:57] when the exception is where most of the
[00:07:00] value is. And by the way, I think this
[00:07:02] is where a lot of bad enterprise AI
[00:07:05] demos start to fall down. The vendor
[00:07:07] shows you the routine case in the deck
[00:07:10] and the buyer signs the contract because
[00:07:12] the routine case is impressive, but the
[00:07:15] buyer never realizes that their
[00:07:17] production traffic is a lot of
[00:07:19] exceptions and the executive team is
[00:07:21] staring at an accuracy number that's
[00:07:23] very low wondering why they were lied
[00:07:24] to. Well, nobody was lied to. The buyer
[00:07:26] just bought the wrong thing, which
[00:07:28] happens a lot right now, which is why
[00:07:29] I'm making this video. If you want to
[00:07:31] dig into what is a full scoring
[00:07:33] template, how do you understand how to
[00:07:36] have a good conversation around whether
[00:07:38] to buy, whether to invest in building,
[00:07:41] whether to hire, how do you balance all
[00:07:43] of that for particular applications. I
[00:07:45] have a very detailed rubric that I put
[00:07:47] together on the Substack for that. Uh
[00:07:49] but for now, I want to focus on these
[00:07:51] big levers in this video so you
[00:07:53] understand how to start to pull them. So
[00:07:54] automation, I think, is the easiest one.
[00:07:56] The next category is one that a lot of
[00:07:57] executives get excited about and they
[00:07:59] don't really know how to allocate money
[00:08:01] efficiently here. So I'm talking about
[00:08:03] building here. I'm talking about the
[00:08:04] idea that the worksheet that you select
[00:08:07] is not suited to purchasing because it's
[00:08:10] unique because it's something that has a
[00:08:11] lot of edge cases. It has a lot of
[00:08:13] exceptions. It's something where you
[00:08:15] have company specific context that
[00:08:17] matters. Your data, your standards, your
[00:08:19] approval gates, your risk thresholds,
[00:08:20] whatever it is. Uh it's your team's way
[00:08:22] of doing the job. It's the secret sauce.
[00:08:25] uh and obviously you are ready at that
[00:08:28] point if you're building to invest right
[00:08:30] this is not a chatbox solution we're
[00:08:32] talking about having uh the right
[00:08:34] repeatable agentic loop where you may
[00:08:37] have skills involved you may have
[00:08:38] connectors like MCP you may have plugins
[00:08:40] you may have data calls you may have sub
[00:08:43] agents uh you may have even vendors with
[00:08:46] tools that you call inside this remember
[00:08:48] how I said you'd have multiple levers
[00:08:50] well you might buy a lever that is a
[00:08:52] tiny part of that loop in that workflow
[00:08:54] and then you build most of it. So the
[00:08:57] hard part here is making sure that you
[00:09:01] understand what is the data that you
[00:09:04] need to put into this workflow. What
[00:09:07] does good look like for this workflow?
[00:09:10] And how do you know that the output at
[00:09:14] the end of that workflow is going to be
[00:09:17] up to snuff, going to be great, going to
[00:09:19] be fantastic if you try to build it.
[00:09:23] Because right now, presumably, if you
[00:09:24] were in business, the humans can already
[00:09:26] do it pretty good. If it was easy to
[00:09:29] automate and delete, you would have
[00:09:30] automated and deleted it. There is
[00:09:32] something complicated enough here that
[00:09:34] you need agents and data and tools and
[00:09:36] connectors to do all of that. And I'm
[00:09:39] asking you, and this does not get asked
[00:09:40] enough, do you have bounds around that
[00:09:42] task? Do you understand the edges of
[00:09:44] that workflow? Do you understand all the
[00:09:45] bits that go into it? I named a bunch of
[00:09:47] them. And do you know what good looks
[00:09:50] like at the end? Because your team is
[00:09:52] going to come back to you and they are
[00:09:54] going to be incented, incentivized to
[00:09:56] tell you, "Yep, this is good. Yep, we
[00:09:59] built the AI thing. The AI thing the
[00:10:01] executive wanted. We did it for you.
[00:10:02] It's amazing." Okay. Do you know if it's
[00:10:06] good or not? Can you be the honest
[00:10:09] third-party eyes that say, "You know
[00:10:11] what? This actually works." Or, "You
[00:10:14] know what? This is terrible. It's
[00:10:16] unacceptable. Go back and build it
[00:10:18] again." or I gave you the wrong mission
[00:10:20] and you couldn't build it. You need to
[00:10:21] have people. I'm going to hire people.
[00:10:23] Whatever it is, that level of clarity
[00:10:27] around value is missing from most of the
[00:10:31] build conversations that I get told
[00:10:33] about that I've sometimes been in the
[00:10:34] room for. And even though we've had this
[00:10:38] massive gain in a Gentic pipeline value,
[00:10:41] Agentic Pipeline skill, Aentic pipeline
[00:10:43] impact in the last four or five months,
[00:10:46] this conversation keeps repeating. the
[00:10:48] people in the room buying have not
[00:10:49] upleveled their conversation in response
[00:10:52] to what we can actually do and they
[00:10:54] aren't realizing how important it is
[00:10:56] that they the executive understand what
[00:10:58] good looks like if they're going to be
[00:11:00] suggesting building so often it's like
[00:11:02] you go build it uh we can't afford to
[00:11:04] buy it and we can't afford to hire
[00:11:05] people so you go build it and it better
[00:11:06] be good and they can't tell you what
[00:11:08] good looks like that that is not a
[00:11:10] solution that is not a solution so
[00:11:12] that's the build level now we come to
[00:11:14] buy right it's often build versus buy so
[00:11:16] I thought putting them next to each
[00:11:17] other made sense. Buy is really a
[00:11:21] question of whether you have the
[00:11:24] capability to take the thing you're
[00:11:27] purchasing and apply it to your workflow
[00:11:29] in a way that gives you value back right
[00:11:31] away. And that's a lot more complicated
[00:11:34] when you're talking about workflows than
[00:11:36] when you're talking about traditional
[00:11:37] software. You need to understand what is
[00:11:40] the underlying substrate that your
[00:11:42] purchase solution will sit on. Is it a
[00:11:44] data substrate? like what is it where is
[00:11:46] it going to sit in your system and then
[00:11:48] how do you know that your dev team is
[00:11:50] going to be able to integrate it well
[00:11:51] and actually get you value and that's
[00:11:53] always been a very high level question
[00:11:54] in software but because software
[00:11:56] traditionally has been so bounded it's
[00:11:58] been a really clean box you can at least
[00:12:00] have that conversation clean with
[00:12:01] workflows if you're buying a solution
[00:12:03] that is effectively a part of the
[00:12:04] workflow it's going to be more
[00:12:06] complicated and that's why when I talk
[00:12:08] about buying I often will separate it
[00:12:10] out and I will say you want to either be
[00:12:12] buying primitives like basic compon
[00:12:14] components or services that you can
[00:12:16] stack into a lot of Agentic workflows
[00:12:18] that you build and those are fairly easy
[00:12:20] because then if your dev team likes them
[00:12:21] they'll use them a lot. Um I think
[00:12:23] Stripe has put a lot of Agentic
[00:12:24] primitives out there right now uh that
[00:12:27] are actually very easy to get started
[00:12:28] with. You're not making a big purchase
[00:12:30] decision. You're just starting to play
[00:12:31] with them and build with them and your
[00:12:32] dev team can put solutions together. uh
[00:12:34] and that's great or you want to be in a
[00:12:37] position where the primitives are
[00:12:40] something that allow you to build
[00:12:43] directly in your system. And so there's
[00:12:45] some tools out there where you're
[00:12:47] starting to have like uh tools that help
[00:12:50] your AI that you build communicate with
[00:12:53] other AIs in your system. So that's sort
[00:12:55] of a a notebook tool or a context tool
[00:12:58] that's focused around tickets. There's
[00:13:00] different kinds of solutions there.
[00:13:01] Those are things that you can imagine
[00:13:03] reapplying because they're basically
[00:13:04] about how does the AI agent communicate
[00:13:06] context to other agents in your system.
[00:13:08] You may buy that one piece. It may
[00:13:09] integrate with your particular tools and
[00:13:11] you may build around it. And then
[00:13:13] there's the folks who kind of like
[00:13:14] Harvey for example for legal. They sell
[00:13:16] the whole thing. It's a whole agentic
[00:13:18] pipeline effectively under the surface
[00:13:20] and you have to decide if that works
[00:13:21] with your workflow as a legal firm or a
[00:13:23] legal department. And so when I when I
[00:13:25] look at all that the the hardest to most
[00:13:27] complicated one is sort of the Harvey
[00:13:28] case. How do you decide that buying
[00:13:32] Harvey makes sense? And I think the
[00:13:35] heart of that question is if you were to
[00:13:39] look at the work that you're doing
[00:13:40] today, is it kind of Harvey shaped or
[00:13:43] not? Do you know their product well
[00:13:45] enough to answer that question? If
[00:13:46] they're selling you a workflow, in this
[00:13:48] case, I don't care that it's legal.
[00:13:49] Harvey is just an example. If you're
[00:13:51] buying a vendor's workflow solution, do
[00:13:53] you know that solution well enough to be
[00:13:55] confident that there's like an 80 90%
[00:13:57] overlap with the shape of their work and
[00:13:59] how they envision the workflow and
[00:14:01] yours? Because if there's not, you're
[00:14:03] going to do a lot more work than you
[00:14:05] think adjusting it. And it's more
[00:14:06] complicated than in the age of AI than
[00:14:08] it was in the age of deterministic
[00:14:10] software. Now, hiring. I'll be honest
[00:14:12] with you. A lot of companies right now
[00:14:14] are trying to find the impossible hire,
[00:14:16] the purple unicorn, the domain expert
[00:14:18] who's an AI builder, who's a systems
[00:14:19] architect with executive experience and
[00:14:21] a change leader. Sometimes that person
[00:14:24] exists. More often than not, the market
[00:14:27] is going to clear out a lot of AI talent
[00:14:30] from under you while you figure out what
[00:14:32] you actually want. And so I think the
[00:14:34] better question if you're looking for AI
[00:14:36] talent to hire is to ask yourself what
[00:14:39] kind of human capability the workflows
[00:14:41] that you're putting together actually
[00:14:43] need in 6 months or a year and then hire
[00:14:46] for that missing piece that you don't
[00:14:48] have on your existing team. Maybe it's
[00:14:50] domain trust, maybe it's workflow
[00:14:51] engineering, maybe it's evaluation
[00:14:53] design, maybe it's executive ownership.
[00:14:55] I don't know what it is, but that is a
[00:14:57] much more sustainable way to hire than
[00:15:01] to just say we need the perfect AI
[00:15:02] unicorn. And I think that this is
[00:15:04] something that's a good sort of reminder
[00:15:06] for all of us because I get that we have
[00:15:09] talent issues with AI. People are coming
[00:15:11] to me saying, can you help me find
[00:15:12] talent? And the answer is I know lots of
[00:15:15] folks. I'm looking for lots of folks. I
[00:15:17] bring folks together where it makes
[00:15:18] sense. But ultimately, you need to be in
[00:15:21] a place where you understand your work
[00:15:24] well enough and how you're investing in
[00:15:26] your team long term well enough and how
[00:15:28] your team's gaps align to the workflows
[00:15:30] you're building to be able to make a
[00:15:32] coherent job description that is for a
[00:15:34] specific person, not a purple unicorn,
[00:15:37] and who you can hire for in that market
[00:15:39] and really assess. One of the things
[00:15:41] that makes hiring really hard right now
[00:15:42] is that people are trying to sift
[00:15:44] through all the noise from the AI
[00:15:45] generated resumes and maybe AI deep
[00:15:47] fakes on video and all of the fluff
[00:15:50] around hiring and the complexity of the
[00:15:52] market. Really a broken hiring market
[00:15:54] right now. And at the same time, they
[00:15:57] have never had less clarity on what they
[00:16:00] want to hire for. And so they're trying
[00:16:02] to sort of wade through the fog of their
[00:16:04] own job description and also wade
[00:16:06] through the fog of the market. And it's
[00:16:08] just a disaster. like they they it takes
[00:16:10] months to clear roles. It's frustrating
[00:16:12] for candidates. It's frustrating for
[00:16:14] companies. It doesn't make sense. Hire
[00:16:16] more specifically. And again, the
[00:16:18] workflow is the key. The workflow helps
[00:16:20] you unlock that hiring definition and
[00:16:22] what what hire gaps you really have
[00:16:24] versus what your team can grow into. And
[00:16:27] you really should be at a point where
[00:16:28] you can say, if my team or someone on my
[00:16:30] team can level up in six months to get
[00:16:32] to this particular talent set I need for
[00:16:34] where I want to go with my workflows,
[00:16:36] keep them inside the house. Train them
[00:16:39] up. Level them up. Do not hire for that
[00:16:42] because it's just it's so painful to
[00:16:43] hire right now. And I know that there
[00:16:45] will be people who are listening to this
[00:16:46] video who are like, I you know, it's me.
[00:16:48] I'm raising my hands. I I'm here and I
[00:16:49] look, I get it. But on the hiring side
[00:16:52] of the table, it looks like 10,000
[00:16:54] people saying, I'm here. It's me. and
[00:16:56] raising their hands and how do you know
[00:16:57] which is which and so we've talked about
[00:17:00] that uh I've talked about talent board
[00:17:02] which is a community that we're standing
[00:17:03] up along with uh Substack to help folks
[00:17:06] to connect over hiring roles and over uh
[00:17:09] proving that they have AI talent. It's
[00:17:11] early days but I'm excited for that. And
[00:17:14] ultimately where we want to go here is
[00:17:16] we want to be in a position where we
[00:17:18] start to clear the fog out of the
[00:17:20] market. And if something like talent
[00:17:23] board or another tool helps you to
[00:17:25] understand who actually has AI skills
[00:17:28] versus who says they do and then if you
[00:17:30] take this video seriously and you start
[00:17:32] to actually define your role as a hiring
[00:17:34] manager and you start to understand how
[00:17:36] your role aligns with workflows, I think
[00:17:39] you'll be in much better shape to go
[00:17:41] wherever you go with your hiring
[00:17:42] journey. and actually get clear answers
[00:17:44] on the AI talent and actually pick up AI
[00:17:46] talent before the market clears it out
[00:17:47] from under your feet. And that's really
[00:17:48] my goal, right? If you're going to
[00:17:50] choose to hire, hire clearly and hire
[00:17:52] quickly. And that takes a lot of work on
[00:17:55] your part up front to define against the
[00:17:57] workflow you're looking to get to. Okay?
[00:17:59] Waiting is the last motion. And it's the
[00:18:01] most counterintuitive when the world is
[00:18:03] shouting at you to do AI. I am not
[00:18:05] saying, by the way, that you should not
[00:18:07] be leaning into AI transformation. That
[00:18:09] is not what this is about. I am saying
[00:18:12] you should be deliberate about where you
[00:18:15] apply AI for leverage in your business
[00:18:17] first. Let's say your whole business
[00:18:19] probably needs AI transformation which
[00:18:20] is a fair basic assumption for most
[00:18:22] businesses. Think about where you get
[00:18:25] the most leverage from going first. And
[00:18:27] when you have things that are
[00:18:29] workflowshaped that are lower on the
[00:18:31] priority list, think about waiting.
[00:18:34] Maybe it doesn't make sense to start
[00:18:36] there. You have limited resources for
[00:18:38] change management in your firm by
[00:18:40] definition. Apply those resources where
[00:18:43] you get the most bang for the buck.
[00:18:46] Apply them where you get the most
[00:18:47] leverage from transforming the workflow,
[00:18:49] the most leverage on your people, from
[00:18:51] learning how to work in an AI native
[00:18:53] way. And then you can spread out from
[00:18:56] there to drive the change. And so I'm
[00:18:58] not saying wait forever. I'm not even
[00:19:00] saying wait for a year. I'm saying stack
[00:19:02] your investments and make sure that the
[00:19:05] right ones are up top and deliver
[00:19:07] disproportionate leverage. Right? I'm
[00:19:09] not c because there's a lot of people
[00:19:11] who will tell you well if you're waiting
[00:19:14] you're too late etc. Look in the larger
[00:19:17] sense if you are saying I don't want to
[00:19:19] do AI I would fully agree you are too
[00:19:21] late it is a problem you got to get on
[00:19:23] board with that as a company as an
[00:19:24] individual fully agree but within that
[00:19:27] and this is true for individuals as much
[00:19:29] as firms you have to understand where
[00:19:32] you want to prioritize that time and
[00:19:33] there will be some things that you don't
[00:19:35] want to prioritize because it's just too
[00:19:37] too much work to change right like I'll
[00:19:39] give you an example if you're trying to
[00:19:41] rewrite your analytic system you may not
[00:19:44] want to prioritize ize changing the SQL
[00:19:46] query polls too fast because SQL just
[00:19:49] works for you and you can get
[00:19:50] deterministic polls and data and is just
[00:19:52] not broken and so it's not the first
[00:19:53] thing you're going to fix and you're
[00:19:54] going to focus on natural language
[00:19:56] descriptions of the analytics and
[00:19:58] storytelling and things that you can
[00:19:59] only do with AI that give you a lot more
[00:20:01] upstream leverage and that's a very
[00:20:02] small example but it illustrates what I
[00:20:04] mean when I talk about waiting and why
[00:20:05] why waiting makes sense in certain
[00:20:07] cases. Now there is one principle that I
[00:20:09] have been dancing around in this whole
[00:20:11] video that I want to say very very
[00:20:13] plainly. If you remember nothing else
[00:20:15] from this video, remember this. Do not
[00:20:19] automate what you cannot describe.
[00:20:23] And this is a line that should sit in
[00:20:25] every single AI investment review. If
[00:20:27] you cannot describe the work you're
[00:20:29] doing in really plain English, well,
[00:20:31] what's your inputs? What's your outputs?
[00:20:32] What are the standards here? What are
[00:20:34] the exceptions? Who owns it? It's going
[00:20:36] to be really, really hard to make good
[00:20:38] investment decisions. And a lot of AI
[00:20:40] projects right now fail before that
[00:20:43] conversation ever comes to a conclusion
[00:20:45] because the team that wants to propose
[00:20:47] the AI thing doesn't have clean, clear
[00:20:51] words like I just described to talk
[00:20:53] about what they mean. They're hiding 20
[00:20:56] workflows inside the same broad ass to
[00:20:58] the vendor. They are talking about broad
[00:21:00] outputs that could mean six different
[00:21:02] things and everyone inside the room is
[00:21:04] reading that differently. they're
[00:21:06] putting broad words in the job
[00:21:07] description that they're hiring for and
[00:21:09] everyone's talking about that
[00:21:10] differently and interviewing for it
[00:21:12] differently. Be specific so that you can
[00:21:16] get impact for your AI investment.
[00:21:18] Please, please, please. Now, if you want
[00:21:20] to dive into the operational layer, what
[00:21:23] actually makes agent work in practice
[00:21:27] useful and high yield for the firm, I
[00:21:29] have a whole deep dive on that in the
[00:21:30] substack today. I think it goes with the
[00:21:32] whole conversation here. I didn't have
[00:21:34] time for it in this video, but it's it's
[00:21:36] a good reminder that you need to be
[00:21:39] thinking about agent capabilities and
[00:21:40] agent workflows end to end as a leader
[00:21:45] if you're going to make a build by
[00:21:47] higher weight decision. And so I wanted
[00:21:49] to dive deep on that. All right, before
[00:21:51] we go further, let's look very
[00:21:53] classically at an investment matrix
[00:21:55] because I love these, right? Like this
[00:21:57] is I've seen these in so many board
[00:21:58] decks. We're going to look at investment
[00:21:59] matrix and and how you think about
[00:22:01] decisioning. So let's do that here. So
[00:22:03] what you have is two axes. First an axis
[00:22:06] about how specific this work is to your
[00:22:08] company. Is it super specific or is it
[00:22:10] pretty pretty general and everyone in
[00:22:12] the space does it? Uh an example of that
[00:22:14] would be everybody does customer service
[00:22:17] in telecom. Like that's not a specific
[00:22:19] thing, right? That's not special. Uh but
[00:22:22] on the other hand, if you have very very
[00:22:24] specific plan switching incentives that
[00:22:26] are driven by a long-term marketing
[00:22:28] motion and nobody else has those, well
[00:22:30] that might be specific. The second axis
[00:22:32] is vertical and it is how mature the
[00:22:34] market solution is for your vertical on
[00:22:37] AI and that obviously changes by
[00:22:39] industry a lot. So very very high level
[00:22:42] right that the these always have four
[00:22:44] boxes and I want you to get get the
[00:22:46] takeaway here. If the work is common,
[00:22:48] general, right, and the market is
[00:22:49] mature, it's an obvious buy, right? Uh
[00:22:52] you can think of this outside AI as like
[00:22:54] workday for commodity HR and payroll,
[00:22:56] right? Uh you can say you're buying
[00:22:58] stripe for payment primitives, right? Uh
[00:23:00] you can say you're buying any standard
[00:23:02] help desk solution for standard help
[00:23:03] desk needs. It makes sense the work is
[00:23:05] common. Now, if the work is common and
[00:23:07] the market is not mature, you want to
[00:23:09] prototype narrowly or you want to wait.
[00:23:12] The category is still defining itself.
[00:23:14] You don't want a five-year contract for
[00:23:16] a tool category that will look different
[00:23:17] in 12 months. And if you want to invest
[00:23:21] here, you want to be prototyping and
[00:23:22] building because you have a chance to
[00:23:24] win the category. So, this sort of
[00:23:25] depends on your vision for the company
[00:23:26] where you want to go here. Now, if the
[00:23:28] work is companyspecific
[00:23:30] and the market has some useful
[00:23:32] primitives, buy the primitives, buy the
[00:23:35] building blocks, buy the tools you can
[00:23:37] call, but you own and set up the
[00:23:39] workflow that everything runs on, where
[00:23:41] the value lives. This is where most
[00:23:43] ambitious teams ought to be living right
[00:23:44] now. You want to buy the connectors, you
[00:23:46] want to buy the model, you want to buy
[00:23:47] the orchestration, and you want to own
[00:23:49] the standard. Uh now, some people of
[00:23:51] course are standing up their own open
[00:23:52] weights models. That's another way to do
[00:23:54] it. But regardless, uh you build it and
[00:23:57] you just bring in the building blocks as
[00:23:58] you need it. Now, there's a bit of a
[00:24:00] blurry line here, but if the work is
[00:24:02] company specific and the market is very
[00:24:04] thin or immature, you want to definitely
[00:24:08] be building because there's value there.
[00:24:10] Um, and you want to make sure that
[00:24:12] you're building in a way that enables
[00:24:14] you to own that category. That's a very
[00:24:16] easy call. If you're wondering, hiring
[00:24:19] cuts across this grid, you need to
[00:24:21] define your workflows to get the hiring
[00:24:22] right. And by the way, pro tip, if the
[00:24:25] work you're trying to define is
[00:24:27] something that nobody is able to define,
[00:24:29] well, if it requires trust, if you need
[00:24:31] to frame it up, if someone needs to
[00:24:33] define the standard and what goods looks
[00:24:34] like, and you're like, "Oh gosh, Nate, I
[00:24:36] don't have that." that's a clue that you
[00:24:38] should be hiring. Your next investment
[00:24:40] is probably a person. Um, and you need
[00:24:43] to think about what person that is and
[00:24:45] how you can define their role in such a
[00:24:47] way that they're set up to enable that
[00:24:50] larger workflow decision to be helpful,
[00:24:53] correct, and long-term impactful for the
[00:24:56] business. And if you're wondering, does
[00:24:58] this mean the executive role is
[00:25:00] changing? Absolutely. We're talking
[00:25:02] about a change in how we allocate
[00:25:04] capital and a need to understand agent
[00:25:06] workflows in more detail to do that.
[00:25:07] Well, the job is not to become the
[00:25:10] person who personally evaluates every
[00:25:11] single tool. I'm not advocating that.
[00:25:13] The job is to understand enough about
[00:25:15] the workflow you're investing in to make
[00:25:18] really good capital allocation
[00:25:20] decisions, which is what we're doing,
[00:25:22] right? Uh if you're hiring, if you're
[00:25:23] building, if you're buying, if you're
[00:25:25] waiting, those are all capital
[00:25:26] allocation decisions. And you have to
[00:25:29] define what are the outcomes that
[00:25:31] matter, what are the problem frames that
[00:25:33] matter, what are the workflows that you
[00:25:35] should prioritize,
[00:25:36] where do you want to allocate talent in
[00:25:39] that mix, and then how do you set up
[00:25:41] your teams to be successful as you think
[00:25:44] about these larger workflows that you
[00:25:45] want to unlock for AI and you want to
[00:25:47] prioritize for AI. And so what I'm
[00:25:49] advocating is essentially instead of
[00:25:51] looking at AI as a sort of a singular
[00:25:53] blob that you want to have a
[00:25:54] conversation about where your CEO says,
[00:25:56] "Let's do an AI strategy." No, don't do
[00:25:58] that. Instead, look at the workflows and
[00:26:01] make good investment decisions once you
[00:26:04] understand those workflows. One last
[00:26:06] thing before we close. There is a very
[00:26:09] cheap version of this conversation I
[00:26:11] hear a lot that tends to turn the debate
[00:26:13] into AI versus people. I don't think
[00:26:16] that is a serious version. It's not a
[00:26:18] helpful version in most cases. The
[00:26:20] serious version of this conversation
[00:26:22] asks where people should be maximizing
[00:26:23] their time, where should they should be
[00:26:25] upleveling, where there are talent gaps
[00:26:26] you can hire for, and where we have
[00:26:29] cases where people need to transform
[00:26:31] their allocation within a job family
[00:26:33] because certain bundles of tasks are
[00:26:36] getting picked up in automation. That is
[00:26:38] a much more serious conversation. It's
[00:26:39] one that is productive. It's one that's
[00:26:41] useful. It's not one I hear nearly as
[00:26:44] much as the drama-filled version, which
[00:26:46] is AI versus humans. It's not it's not
[00:26:48] useful. Ultimately the human work that
[00:26:50] remains in this version as we look at
[00:26:52] these workflows is getting more
[00:26:53] impactful and more leveraged because we
[00:26:55] are putting AI and powerful agentic
[00:26:58] systems at the heart of the business and
[00:27:00] we need to get that right and that is
[00:27:02] that is a people problem. And so this is
[00:27:04] not AI replacing workers. This is
[00:27:07] figuring out how to make investment
[00:27:10] decisions that unlock disproportionate
[00:27:12] value that get you out of that Gartner
[00:27:14] 40% figure and get you into a place
[00:27:17] where you're getting real value back on
[00:27:20] that agentic investment. And and it
[00:27:22] starts and ends with the workflow. If if
[00:27:23] I if you take nothing else away from
[00:27:25] this, understand your workflows, be able
[00:27:28] to talk about them specifically, and
[00:27:30] have discrete investment conversations
[00:27:33] about those particular workflows that
[00:27:35] matter most to your business. And that's
[00:27:37] going to set you up for success in a way
[00:27:39] that most conversations that start with
[00:27:41] we need an AI strategy will not. Best of
[00:27:44] luck and I'll see you next
