---
video_id: ddFgXoNa9_0
title: How I use Linear to manage my SaaS
channel: Brian Casel
url: "https://www.youtube.com/watch?v=ddFgXoNa9_0"
watched_date: 2026-06-01
watched_at: "2026-06-01T12:00:00Z"
watch_count: 1
duration_seconds: 1592
source: youtube-history-browser
history_label: Jun 1
history_order: 167
watched_at_precision: date-from-history-label
watched_percent: 12
estimated_watched_seconds: 191
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker manages a 4+ year old SaaS product (Clarity Flow) with a small team and replaced GitHub Issues with Linear for superior threaded comments and organization. Linear's workflow uses custom statuses (new → soon → later → shaping → to-do → in progress → in review → reviewed → ready to deploy → deployed) to track work through its lifecycle. Work is organized by projects (Conversations, Forms, Commerce, Appointments) and labels (customer request, bug, research), with large features broken into 10–12 smaller issues. Each issue contains detailed checklists and technical instructions; threaded comments allow the team to collaborate asynchronously with quoted discussions that serve as permanent documentation. Bug reports and feature requests are always linked back to original customer conversations in Help Scout or Clarity Flow itself so the team can follow up later.

To implement this system: set up a Linear workspace with custom issue statuses matching your workflow, create projects for each major feature area in your product, use color-coded labels to highlight customer requests (make them bright so they stand out), and develop a template for new issues that includes a checklist section with subtasks. Train your team to quote and reply in comment threads rather than leaving standalone messages, and make checking the Linear inbox a daily habit—use status colors to prioritize which messages are blockers (in-progress items likely need answers) versus updates (completed items). When you ship a feature that customers requested, go through the linked customer conversations and send each customer a personal message mentioning their feedback led to the feature.

## Transcript

[00:00:00] So, one of my SAS products that I run
[00:00:02] every day has been running for over four
[00:00:05] years, and it has a very active roadmap.
[00:00:08] I have a small team working with me, uh,
[00:00:10] two developers and one, uh, customer
[00:00:12] support person. And, yeah, it's just it
[00:00:14] it's gotten to a really efficient
[00:00:16] workflow where we're managing our
[00:00:18] roadmap, we are building and shipping
[00:00:20] new features, we're fixing bugs, we're
[00:00:22] helping customers, and we manage all of
[00:00:24] that in a tool called Linear. You may
[00:00:27] have heard of it. So, I thought in this
[00:00:28] video I would walk through and show you
[00:00:30] our actual uh linear project management
[00:00:34] setup for my SAS product. We used to use
[00:00:37] GitHub issues and although we still use
[00:00:39] GitHub today, we don't use the issues
[00:00:42] system as our project management tool
[00:00:44] anymore. Now, we're using Linear because
[00:00:47] it has a really strong integration with
[00:00:49] GitHub. But anyway, uh the the product
[00:00:52] that I'm talking about is Clarity Flow.
[00:00:54] that is a SAS product that I started
[00:00:57] back in 2021 and you know it's a good
[00:00:59] little product. It's built into uh you
[00:01:01] know quite a few features as you can see
[00:01:04] uh over the years. So let me kind of
[00:01:06] take you behind the scenes and show you
[00:01:08] what day-to-day life of uh of managing
[00:01:10] this Clarity Flow SAS product looks like
[00:01:14] in linear. All right, so here's a look
[00:01:16] at Linear. I'm going to uh increase the
[00:01:18] screen size so we can dive right into
[00:01:20] it. Here's the general view that I hop
[00:01:22] into on a daily basis. I usually have
[00:01:24] this bookmarked in my browser. And I
[00:01:27] like the cananban layout. Of course, you
[00:01:29] could switch to uh to like a list mode
[00:01:31] as well, but um I really like this
[00:01:33] cananban layout. It's showing me
[00:01:36] basically this is filtered to the active
[00:01:39] issues that are currently happening. I
[00:01:41] usually spend most of my time looking at
[00:01:42] this um yellow section which is in
[00:01:45] progress. These are the issues that my
[00:01:48] developer is currently working on. Um,
[00:01:50] these are issues that my developer has
[00:01:53] finished. These are under what we call
[00:01:55] in review. So, these are finished and
[00:01:58] they're waiting for me to hop in and
[00:02:00] actually review them. In this case, we
[00:02:02] are in the middle of building out a a
[00:02:04] big new feature. Um, so I'm sort of
[00:02:06] waiting for most of the sub features to
[00:02:09] be finished before I go in and review
[00:02:11] everything. Um, I'll get more into that
[00:02:12] workflow in just a minute. Over here on
[00:02:14] to-do is the other area that I focus on
[00:02:16] a lot and these are this is like the
[00:02:20] queue. I really like this concept of
[00:02:23] almost all of my work I think of in
[00:02:26] terms of a queue. What's happening next?
[00:02:29] So whatever is at the top of this queue
[00:02:31] is going to be mostly my developer next
[00:02:33] task. Some of these are um actually
[00:02:35] assigned to me and they've been sitting
[00:02:37] in this queue for a long time because I'
[00:02:39] I've been slow to get to my queue. But I
[00:02:41] can also filter by person. So now I'm
[00:02:44] filtered to just the issues that are
[00:02:46] assigned to Sandia uh my developer. And
[00:02:49] I can see that um her queue is is still
[00:02:51] pretty long. And I'm constantly going in
[00:02:53] here and I'm I'm sort of like
[00:02:55] reshuffling the uh the issues that she's
[00:02:58] going to be working on next. That's in
[00:03:00] the to-do status. Let me step back a
[00:03:04] little bit and um and go into the
[00:03:06] settings to show you how we can manage
[00:03:08] where is it? Settings. Yeah. Yeah. So,
[00:03:10] you can go into your your teams and then
[00:03:13] go into issue statuses and automations.
[00:03:16] And this is where you can manage um all
[00:03:18] of the different issue statuses. So, um
[00:03:22] I I pay a lot of visual attention to
[00:03:24] these icons. So, like the dotted circle
[00:03:27] means that it's sort of in this like
[00:03:30] preQ phase. And I have several statuses
[00:03:34] here. So, like new, soon, later, and
[00:03:37] noted. And then we have sort of like the
[00:03:40] next phase of the life cycle of an issue
[00:03:42] which is like shaping which means that I
[00:03:45] know it's it's soon to be cued for my
[00:03:47] developer to work on but I need to spend
[00:03:50] time in the shaping process um writing
[00:03:52] out the requirements and I'll show you
[00:03:54] that in just a minute. And then we have
[00:03:55] that to-do phase which I just showed
[00:03:57] you. Um that's the long list of of
[00:03:59] that's the actual cue of of what what's
[00:04:02] on deck. Then we get into actually
[00:04:04] working on the issues. So in progress
[00:04:06] that's yellow. So, I'm constantly
[00:04:07] looking for these yellow icons to see
[00:04:09] like, all right, these are the the one,
[00:04:11] two, sometimes three issues that are
[00:04:12] actually in in progress. Then, we get
[00:04:15] into review. So, that means that my
[00:04:17] developers finished and now it's ready
[00:04:18] for me to review. And then we often have
[00:04:21] a lot of issues that I have already
[00:04:23] reviewed um but we haven't actually
[00:04:26] greenlighted them to go into our deploy
[00:04:29] process. So, that I put those into
[00:04:30] reviewed and then we have a lot of
[00:04:32] issues in ready to deploy or actually we
[00:04:34] don't have a lot. We try to have a small
[00:04:36] number of issues to deploy but that
[00:04:38] means that we've done the review we've
[00:04:40] done the internal testing and QA and
[00:04:42] it's all ready and so then um it's in
[00:04:45] the the batch of issues to you know
[00:04:47] merge into our main branch and deploy.
[00:04:50] Then once we have deployed we will uh
[00:04:52] push it into pending and deployed or
[00:04:56] deployed. The difference between these
[00:04:58] two is we have already deployed
[00:04:59] something to the production app, but we
[00:05:02] still need to notify some customers to
[00:05:04] say, "Hey, we've fixed that bug or or
[00:05:07] hey, we need to um send out a a
[00:05:09] newsletter to announce this new
[00:05:10] feature." That means it's pending and
[00:05:12] deployed. Or if it's completely done,
[00:05:14] deployed, already announced, already
[00:05:16] told everyone we need to tell, that's in
[00:05:18] deployed. We don't really use this one
[00:05:19] anymore. Occasionally, we'll have an
[00:05:21] issue that we just cancel it. So, we'll
[00:05:23] put into into canceled. So that's how
[00:05:24] I've like customized all the possible
[00:05:26] statuses that a issue can have and
[00:05:29] that's what defines
[00:05:31] um these columns. If I go back into all
[00:05:35] issues and if I actually like zoom out
[00:05:37] to all issues, this will include
[00:05:39] everything. So you know getting back to
[00:05:42] that um how I've started to organize
[00:05:45] things I I'll talk a little bit more
[00:05:47] about these statuses and how we're using
[00:05:49] projects in linear and how we're using
[00:05:51] labels. So, you know, at a high level
[00:05:54] again, like Clarity Flow is a somewhat
[00:05:56] mature product. We're over four years
[00:05:59] into its existence. So, we're in this
[00:06:02] phase now where we have a lot of past
[00:06:05] features. We have some new features that
[00:06:07] are on the future roadmap, but most of
[00:06:10] our work revolves around managing
[00:06:13] feature requests, bugs, and small new
[00:06:16] enhancements to existing features. And
[00:06:18] so we're constantly receiving um
[00:06:21] customer requests and we label those
[00:06:22] with the label customer request. I made
[00:06:25] it a bright yellow because I try to
[00:06:26] focus my attention on the things that
[00:06:28] customers are asking for. So anytime a
[00:06:30] customer is asking for something, we're
[00:06:32] going to um slap the the customer
[00:06:34] request label on it. And so then a lot
[00:06:36] of my job as the owner and the product
[00:06:39] manager here is to spend a lot of time
[00:06:42] in these columns. Really, no one else on
[00:06:44] the team is is doing this. I'm the one
[00:06:46] who focuses on these columns to try to
[00:06:48] decide, okay, these are the ones that I
[00:06:50] think we should try to get to soon.
[00:06:52] These are the ones that we'll get to a
[00:06:55] little bit later. And these are noted,
[00:06:57] meaning like, all right, I know that
[00:06:58] they exist. We still want to have them
[00:07:00] documented here in linear, but we're
[00:07:02] probably not going to do them anytime
[00:07:04] soon. Or maybe we will, but I haven't
[00:07:06] decided yet to push it into soon or
[00:07:09] later or into shaping. So then we get
[00:07:11] into shaping and that's when I'll I'll
[00:07:13] take an issue from over here and put it
[00:07:16] into into shaping. And as you can see,
[00:07:19] there's not much info in here yet.
[00:07:21] That's why it's in shaping, meaning this
[00:07:24] is an issue that's waiting for me to
[00:07:26] write some some notes about it. I'm
[00:07:28] still actually a little bit unsure about
[00:07:29] this one. Uh but yeah, I haven't uh
[00:07:32] gotten to it yet. Let's see this one.
[00:07:33] Okay, so here's one. It's a customer
[00:07:36] request, and as you can see, several
[00:07:38] customers have requested it. Me and uh
[00:07:40] Cat, our customer support person, have
[00:07:42] gone back and forth and discussed this
[00:07:45] uh quite a bit. These are some of the
[00:07:47] notes that actually Cat wrote. She's our
[00:07:49] customer success person uh and she um
[00:07:52] noted them. And so I'm at some point I'm
[00:07:55] going to come in here and convert these
[00:07:57] notes into hard requirements. I'm going
[00:07:59] to get more into that in just a minute
[00:08:00] to show you what it looks like once I
[00:08:02] get it into the queue for my developer
[00:08:04] to to run with. Um, but that's what's
[00:08:06] happening in shaping. And frankly, a lot
[00:08:09] of these things get kind of stale where
[00:08:11] like I might think something is
[00:08:12] happening soon, but then it'll sit in
[00:08:14] the soon list for for way too long. And
[00:08:17] that's probably the case with most of
[00:08:18] these things. So, you know, I I try to
[00:08:21] come in here every month or two or 3
[00:08:23] months and sort of retriage things. But
[00:08:26] I'll be completely honest, most of that
[00:08:28] kind of falls to the back burner. I'm
[00:08:29] I'm spending most of my time h in the
[00:08:32] to-do um column. Before I get into the
[00:08:35] details on, you know, these like
[00:08:37] detailed notes that go into an actual
[00:08:40] issue, I want to talk more about some of
[00:08:42] the organizational stuff. So, I talked
[00:08:44] about the customer request label. The
[00:08:46] other label that we use quite a bit, of
[00:08:48] course, is the red one that says bug.
[00:08:50] So, if we look at, let's see how many
[00:08:53] bugs were currently. So, here's one. Um,
[00:08:55] this is a bug. We gave it the red bug
[00:08:58] label. So, those are really the two
[00:09:00] labels that we use a lot. either
[00:09:02] customer request or bug. We have
[00:09:05] actually a lot of other labels but that
[00:09:06] we don't use as much. Um sometimes I'll
[00:09:10] use the research label when it's
[00:09:13] sometimes I'll have like an issue that's
[00:09:15] not really a new feature to build. It's
[00:09:17] just a technical research task like give
[00:09:19] this some thought or give this some
[00:09:20] research. I might slap that one on it.
[00:09:22] Um if we're focusing on writing tests,
[00:09:24] maybe I'll I'll put that on there.
[00:09:26] Sometimes it's a super small issue and
[00:09:28] I'll and I'll put the small label on it.
[00:09:30] A lot of these labels are old and not
[00:09:32] used anymore. So just a few weeks ago
[00:09:35] actually or a few couple months ago, we
[00:09:38] started actually making use of linear
[00:09:41] projects feature and that's these down
[00:09:44] here with these like cube icons. In this
[00:09:48] product, in this SAS product, we have
[00:09:50] quite a few major features and those
[00:09:53] features have sub features. So these are
[00:09:55] more like areas of the app, right? So,
[00:09:58] ClarityFlow, it's a it's a platform for
[00:10:00] coaching. So, we have a big
[00:10:01] conversations section. We have a a newer
[00:10:04] uh forms feature. We have Clarity Flow
[00:10:07] Commerce, which is our payments and
[00:10:09] Stripe integration. We have appointments
[00:10:11] booking. So, for each of these big areas
[00:10:14] of the app, we gave it a project. So now
[00:10:17] I so that enables me to filter our
[00:10:20] entire board down to just the sub
[00:10:24] features or bugs or feature requests
[00:10:27] that are related to in this case our
[00:10:29] appointment setting feature. Right? So
[00:10:31] actually right now we're we're currently
[00:10:33] building a new feature that is still
[00:10:36] under the umbrella of the appointments
[00:10:38] feature. So we've already shipped the
[00:10:39] big appointments scheduling feature.
[00:10:42] Next, we're going to be shipping
[00:10:43] recurring appointments. The ability to
[00:10:45] sell and book a recurring appointment
[00:10:48] thing the way that a coach would
[00:10:49] typically sell like coaching engagements
[00:10:51] every week or every month. They can sell
[00:10:54] these recurring um appointments. And
[00:10:56] it's actually a super complex feature to
[00:10:58] build. So, um all of that is happening
[00:11:01] under the appointments project. If I
[00:11:03] want to hop over to the commerce, that's
[00:11:05] another huge feature in our app. It's
[00:11:07] it's a Stripe integration. It's the
[00:11:09] ability to sell and have product pages
[00:11:11] and subscriptions and manage customers,
[00:11:14] manage purchases. So, that's a huge
[00:11:17] project. And as you can see, all of
[00:11:19] these sub features or all these little
[00:11:22] issues are related to our um commerce
[00:11:26] feature. So, we've started doing that
[00:11:27] and I've informed my team that we want
[00:11:30] every single issue, no matter what it
[00:11:32] is, to fall into one of these projects.
[00:11:35] Occasionally we'll use this like
[00:11:37] miscellaneous project for things that
[00:11:39] you know just don't really fit into
[00:11:40] anything or maybe they're just related
[00:11:42] to like our clarity flow checkout
[00:11:44] process itself or something like that.
[00:11:46] But yeah, we're using these these
[00:11:47] projects quite a bit. Okay, now let's
[00:11:49] dig into the issues themselves. I want
[00:11:51] to show you what it looks like uh behind
[00:11:53] the scenes, my interaction with my team
[00:11:55] and and how we how we work together.
[00:11:58] First, let's focus on new features. So,
[00:12:00] as I said, we are currently in the
[00:12:02] process of building a new feature. This
[00:12:04] is our recurring appointments feature.
[00:12:06] So, I'm going to pull open this issue.
[00:12:09] So, this is one piece of this big new
[00:12:12] feature. And I've broken the the big new
[00:12:14] feature into probably like 10 to 12
[00:12:17] different issues. And as you can see, I
[00:12:20] this is already shaped. So, I spent the
[00:12:22] time to write all of these checklists.
[00:12:25] Um, so everything that you see here was
[00:12:27] written by me. Um, I give a quick
[00:12:30] overview and then I have a lot of these
[00:12:32] checklists and subchecklists, lots of
[00:12:35] technical uh, instructions um, giving
[00:12:39] like labels and my developer and I we
[00:12:42] sort of have some like shorthand on on
[00:12:44] how we like to describe different
[00:12:46] interface elements to each other. Um,
[00:12:48] and as you can see these are all checked
[00:12:49] off because this is now in review which
[00:12:52] means uh, Sandy has already finished all
[00:12:54] these items. I really like to use these
[00:12:56] check these checkable things so that I
[00:12:58] can see exactly which items uh she is
[00:13:01] finished. So if I back out and look at
[00:13:03] one of these. Yeah. So this one is in
[00:13:06] progress. And down here here's like the
[00:13:08] checklist for that. You can see only
[00:13:09] some of them are checked and some of
[00:13:11] them are not. That's how I can hop in at
[00:13:13] any point in any day to see what exactly
[00:13:16] is the current progress without needing
[00:13:18] to bug my developer to say, "Hey, where
[00:13:20] are we at on this or that?" You know, um
[00:13:22] I can just see right in the checklist.
[00:13:23] It's very easy. Um, let me get back into
[00:13:26] one of these issues which is now ready
[00:13:30] for review. So that's the top section.
[00:13:32] That's like the description where I put
[00:13:33] the the checklist. If I scroll down,
[00:13:36] this is the comment section. A lot of
[00:13:38] activity happens in our comments
[00:13:39] section. And this is actually one of the
[00:13:42] reasons why I chose to switch over to
[00:13:45] using linear away and moving away from
[00:13:48] using GitHub issues. GitHub did not have
[00:13:51] the ability to have threaded comments.
[00:13:54] So one way we use comments in linear is
[00:13:58] you know we have the single comment and
[00:14:01] then I can reply underneath it. And what
[00:14:03] that allows us to do is when it's
[00:14:06] finished as it is here you know um Sandy
[00:14:08] was clarifying some requirements and
[00:14:11] then I gave her a quick uh answer. She
[00:14:14] thumb she gave me a thumbs up to say
[00:14:16] like got it. Um, and so even though this
[00:14:18] is three weeks ago, what I probably
[00:14:20] should have done is I can resolve this
[00:14:23] and I can hide it away. And I love that
[00:14:25] we can, and I'm actually going to keep
[00:14:27] it open in case she still needs it. But,
[00:14:29] you know, all these individual comment
[00:14:31] threads, we can we can just, you know,
[00:14:33] resolve them and hide them away. Okay.
[00:14:35] So, uh, here's a good example of a piece
[00:14:38] of a feature which we've already
[00:14:40] shipped. This is our tasks feature where
[00:14:43] my developer and I had uh lots of back
[00:14:46] and forth conversation about how this
[00:14:48] feature should work and the underlying
[00:14:51] logic that goes into it. And this is
[00:14:53] where linear comments really um shine.
[00:14:56] As I said, we can expand and collapse
[00:14:58] the comments when we're done looking at
[00:15:00] them. Um but here's a good case where my
[00:15:03] developer sort of raised, let's see, one
[00:15:06] two different issues in one comment. And
[00:15:10] what I'd like to do here is then
[00:15:11] separate these out to separate comments,
[00:15:14] which is exactly what I did here. So she
[00:15:16] raised the issues here. I collapsed it
[00:15:20] and then I started a separate comment
[00:15:22] for each one. So here's, you know, issue
[00:15:25] one and we do a lot of like quoting of
[00:15:26] each other to say this is the thing that
[00:15:28] I'm going to reply to. So she asked this
[00:15:30] question and then I gave this response
[00:15:32] about how we should think about the
[00:15:34] logic around issue one. And then my
[00:15:37] developer always gives me a reaction to
[00:15:39] just confirm to me like yes, got it. I
[00:15:41] don't need a message to say like yes, I
[00:15:43] got it. Because that's going to be like
[00:15:45] another message that goes into my inbox
[00:15:46] which I don't need. But I do want to see
[00:15:48] like saw it, got it on it. Like so we
[00:15:51] use these thumb thumbs up emojis a lot.
[00:15:54] So keeping it separate, keeping one
[00:15:56] issue or one question to one comment
[00:16:00] allows me to give a response. Maybe
[00:16:02] we're going to continue to to to hash
[00:16:04] this one question out, but when it's
[00:16:06] finished, we can resolve that and then
[00:16:09] we can move on to the other issue. So
[00:16:11] again, like this is the se the second
[00:16:13] issue and I started a separate comment
[00:16:15] thread. Here it is. Um there's actually
[00:16:18] a little bit more to it. And and then
[00:16:20] here we we sort of go back and forth. As
[00:16:23] you can see, we are quoting each other
[00:16:25] um quite a bit. You know, this is where
[00:16:27] communic async communication especially
[00:16:29] textbased communication or technical
[00:16:32] discussions, technical product
[00:16:34] discussions, this is how my my developer
[00:16:36] and I collaborate. I actually think that
[00:16:39] this is a better way than going on a
[00:16:42] call and talking it through because then
[00:16:44] a lot of that a lot of that nuance a lot
[00:16:46] of these details get lost or getting
[00:16:47] forgot get forgotten about. Whereas here
[00:16:50] we have it all documented in highly
[00:16:52] technical, highly specific comment
[00:16:55] threads that my developer or I can
[00:16:58] always refer back to. And we are often
[00:17:00] referring back like many weeks, many
[00:17:03] months out into the future. We're we're
[00:17:05] referring back to technical discussions
[00:17:07] that we had months ago. And it's all
[00:17:10] logged here in really easy to find um
[00:17:13] comment threads. again like we're I'm
[00:17:15] giving some some examples for different
[00:17:17] scenarios and and how we should be
[00:17:19] handling each of these scenarios and and
[00:17:21] the logic that that goes into them. Um
[00:17:23] sometimes you know she's referencing a
[00:17:25] block of code or um you know and then
[00:17:28] finally uh we get to okay this is all
[00:17:30] completed and here's the PR. So that's
[00:17:33] what it looks like when we are kind of
[00:17:34] like hashing out a new feature that
[00:17:36] we're actively building. The other thing
[00:17:38] that we do quite a bit is taking in bug
[00:17:42] reports and customer requests. And I
[00:17:44] want to show you what those look like
[00:17:45] cuz they happen they they look a little
[00:17:47] bit different in linear. So let me go
[00:17:50] back into all of our active issues and
[00:17:53] um okay so here is an example of a bug
[00:17:56] that a customer reported. So what
[00:17:58] happened here was the customer
[00:17:59] originally uh reported the the issue.
[00:18:03] Actually they used ClarityFlow to report
[00:18:05] the issue to us. Sometimes they use
[00:18:06] Clarity Flow, sometimes they use Help
[00:18:08] Scout, our our help desk software that
[00:18:10] we use. Um but our support person took
[00:18:13] the customer report and then and then
[00:18:16] she replicated the issue to confirm like
[00:18:18] yes this is a bug she sees it too and
[00:18:21] then uh she wrote up this issue um which
[00:18:25] includes the details about what he was
[00:18:27] trying to do um and she said that she
[00:18:30] tried to figure it out um and she
[00:18:33] included the the customer's video that
[00:18:34] he shared. What we also always always do
[00:18:37] both when it's a bug report and when
[00:18:40] it's a customer request is we add the
[00:18:43] link. You can do uh command K uh link um
[00:18:48] yeah add link and you can just add a
[00:18:50] link to a help desk issue or uh or or
[00:18:54] like a clarity flow link or or you know
[00:18:56] wherever the customer reported it. We
[00:18:59] always do that so that later when we
[00:19:02] come around and fix this issue, we have
[00:19:04] the the quick link that points to that
[00:19:06] person's um message thread where we can
[00:19:09] get back to them and say, "Hey, it's
[00:19:10] fixed." Right? So, um Cat reported this
[00:19:13] issue or Cat filed this issue in linear.
[00:19:16] She actually tagged me. This was 6
[00:19:18] months ago. So, since then, we've
[00:19:19] switched it over so that uh you know,
[00:19:22] Sandy will just, you know, hop in and
[00:19:24] immediately receive it from cat and I
[00:19:26] don't even really need to touch it. Uh
[00:19:28] but Sandy Sandy our developer will go in
[00:19:31] and um identify the issue. Uh she fixed
[00:19:33] it. She made a PR and um and then uh I
[00:19:37] moved it over to ready to deploy and she
[00:19:39] deployed it to production. Um and then
[00:19:41] from here uh cat will take it and go
[00:19:44] back to the customer and say hey your
[00:19:46] your issue has been fixed. So that's
[00:19:48] typically what a bug fix looks like. So
[00:19:51] um here is one of those like big
[00:19:53] features that we received a lot of
[00:19:54] customer requests for. It's it's tasks
[00:19:57] like the ability to assign to-dos to
[00:19:59] clients in your message threads in
[00:20:01] ClarityFlow. Um what we usually do uh
[00:20:04] anytime we have this customer request
[00:20:06] label on it, you can expect that it
[00:20:09] should have at least one link to a
[00:20:11] customer who has requested that feature.
[00:20:14] So these are links that point to like
[00:20:16] help scout conversations. Sometimes
[00:20:18] they're pointing to clarity flow
[00:20:20] conversations. Um, and uh, you know,
[00:20:23] we've probably have had even many more
[00:20:26] requests than this. These were just the
[00:20:27] ones that we happened to remember to to
[00:20:30] link to. Um and when customer when
[00:20:32] feature requests come repeatedly, the
[00:20:35] benefit of organizing all these requests
[00:20:38] using projects and using labels and
[00:20:41] using very uh detailed specific titles
[00:20:44] is that it makes it easy for our support
[00:20:46] person or myself to find the existing
[00:20:49] issue that we have and add that
[00:20:51] customer's uh voice to the list of
[00:20:54] links. The reason why this is really
[00:20:56] helpful is first when it comes time for
[00:20:59] me to go in and shape the feature and
[00:21:01] design it and decide like what
[00:21:03] functionality we're going to have. I
[00:21:05] spend a lot of time going through and
[00:21:06] reading these these uh request help
[00:21:10] threads from customers to really get a
[00:21:12] sense on what exactly they were trying
[00:21:14] to do in terms of like the job to be
[00:21:17] done. And that's what will inform me to
[00:21:20] figure out how we should scope out and
[00:21:21] shape an issue. And then most
[00:21:23] importantly is later when we come back
[00:21:26] and we have finished a feature and you
[00:21:30] can see some of these happen like over
[00:21:31] many months sometimes across years. We
[00:21:34] circle back and we send a personal note
[00:21:36] to each of these customers to say hey
[00:21:38] that feature that you wrote us in and
[00:21:41] and asked for we've shipped it. It's
[00:21:42] live. Check it out. Here you go. We'll
[00:21:45] probably do like a larger announcement
[00:21:46] of every feature as well, but we always
[00:21:48] send a personal message to each
[00:21:50] individual customer who ever asked for a
[00:21:53] feature and we have them all linked up
[00:21:55] here right from from the linear ticket.
[00:21:57] So, um that's really really helpful.
[00:22:00] What else? So, I use the favorites thing
[00:22:02] in the in the left side um to get to a
[00:22:05] lot of the most commonly viewed views.
[00:22:09] So, uh, you know, again, I I basically
[00:22:11] put every project that we have in a
[00:22:14] favorite so that I can easily get to
[00:22:16] that get to that view. And then I also
[00:22:19] put people. So, um, there's myself and
[00:22:22] then Sandy is our like primary developer
[00:22:24] right now. And so, I'm always clicking
[00:22:26] on her name to be able to, um, just
[00:22:29] filter all the issues by to see like
[00:22:32] what is Sandy working on and what's in
[00:22:35] her queue. And of course, I I probably
[00:22:37] should have led with this at the start
[00:22:38] of the video, but the inbox. So, usually
[00:22:41] every morning when I'm coming into
[00:22:43] Linear to check the status, the very
[00:22:45] first place that I'm going to go to is
[00:22:47] this inbox in the top left. One
[00:22:49] complaint that I have about Linear is
[00:22:51] that they don't send regular email
[00:22:54] notifications. Or they they do, but I
[00:22:56] don't like how they do the digest thing
[00:22:58] where they gather multiple issues and
[00:23:01] multiple comments into a single email in
[00:23:04] my regular email inbox. I'm not a fan of
[00:23:06] that. I would much prefer to have
[00:23:09] separate
[00:23:10] individual email messages from any apps
[00:23:14] that send me messages so that I can deal
[00:23:15] with them like regular emails. like one
[00:23:17] message needs one reply and I might I
[00:23:21] might need to reply to that later. So,
[00:23:22] I'm going to leave that one message
[00:23:23] unread. Um whereas other messages I can
[00:23:26] just work through. Linear just does not
[00:23:28] have that individual separate
[00:23:30] notification for each individual
[00:23:32] comment. Yes, it leads to lots more
[00:23:35] emails, but I can I can then process
[00:23:37] those emails one by one. So, that's
[00:23:40] unfortunate, but the good thing is that
[00:23:42] Linear itself has a really good inbox of
[00:23:44] its own. So, I've actually stopped using
[00:23:47] Linear's email notifications and instead
[00:23:49] I just have a daily habit of every
[00:23:51] single morning I'm coming into Linear
[00:23:53] and the first place I go is the inbox. I
[00:23:55] can see how many new messages. I usually
[00:23:57] leave it in this mode where I'm not
[00:24:00] showing my red messages, but I can
[00:24:02] toggle that on if I need to get into
[00:24:06] older stuff, but mostly I'm just looking
[00:24:07] at the new stuff. I like how they can
[00:24:09] show me that this isn't even a message.
[00:24:11] This is just a thumbs up. So that that's
[00:24:14] something that like I know that Sandy
[00:24:16] didn't actually send me a new comment
[00:24:18] that I need to read. All I need to do is
[00:24:20] like click it. I can see that she's
[00:24:21] thumbmed up it and that's all I need to
[00:24:23] do. Done. I also like how in this view
[00:24:26] the inbox will show me the current
[00:24:28] status. It'll show me the status of the
[00:24:31] issue that the comment is on. So I can
[00:24:34] see that these are all yellow, which
[00:24:35] means these are all comments on issues
[00:24:38] that are currently in progress. And that
[00:24:40] tells me that these are probably
[00:24:42] questions that are blockers. What most
[00:24:45] likely happened here, and I haven't even
[00:24:46] read this one yet, is she ran into a
[00:24:49] blocker or she ran into a question. This
[00:24:51] is still in progress. So, I need to read
[00:24:54] it and give her an answer so that she
[00:24:56] can move forward. And if I go into my
[00:24:57] red messages, you can see a lot of these
[00:24:59] are green like like this one, I could I
[00:25:02] could see, you know, she finished this
[00:25:04] uh this part of the feature where she
[00:25:06] completed the task. Um, so her comment
[00:25:08] to me was just to tell me that she
[00:25:10] completed it and she recorded a video to
[00:25:12] show me uh the the the task which is
[00:25:15] very helpful. But I can see here that
[00:25:17] the status of that comment or the status
[00:25:21] of the issue where that comment is it's
[00:25:22] green which means like it's not as
[00:25:24] urgent in my mind uh because that's just
[00:25:28] a message to tell me that it's complete.
[00:25:30] Whereas these are messages on in
[00:25:31] progress things which are probably
[00:25:33] blockers. So, I'm going to prioritize
[00:25:34] that and get right back to my developer
[00:25:36] as quickly as I can so that we can move
[00:25:38] forward and ship faster. Um, so that's
[00:25:40] how I manage the inbox and uh yeah,
[00:25:43] overall that's as much as I could show
[00:25:45] you on how we use Linear to manage my
[00:25:48] SAS application. Now, the other app that
[00:25:51] I'm using every single day is Cursor.
[00:25:54] That is the tool that I use for all of
[00:25:57] my coding and using AI to uh to make
[00:26:00] code changes in my projects. So I'm
[00:26:02] constantly bouncing back between linear
[00:26:05] and cursor. Linear is where we manage
[00:26:07] our uh code related projects between me
[00:26:11] and my small team. And cursor is where I
[00:26:13] spend my time coding and building
[00:26:15] products. And so if you want to see an
[00:26:17] inside look into how I'm using cursor
[00:26:20] every day and how I'm using AI to help
[00:26:22] me uh you know ship my products faster,
[00:26:26] check out my other video that I just did
[00:26:28] on how I'm using cursor to build
[00:26:30] products. I'll see you there.
