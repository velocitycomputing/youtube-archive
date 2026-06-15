---
video_id: jQ2ft0RKhsY
title: How to Get Started with OpenHands (CLI, Cloud & SDK Explained)
channel: OpenHands
url: "https://www.youtube.com/watch?v=jQ2ft0RKhsY"
watched_date: 2026-06-13
watched_at: "2026-06-13T12:00:00Z"
watch_count: 1
duration_seconds: 1429
source: youtube-history-browser
added_date: 
history_label: Saturday
history_order: 24
watched_at_precision: date-from-history-label
watched_percent: 39
estimated_watched_seconds: 557
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

OpenHands is an AI agent platform that automates coding tasks—running commands, editing files, and completing projects—available in three form factors: CLI (fastest for local use), Cloud GUI (for scaling and team collaboration with integrations like GitHub, Slack, and Jira), and SDK (for building advanced systems and scheduling automation). Agents execute in isolated sandboxes, the platform is model-agnostic (supporting Claude, Gemini, and others), and can be self-hosted or deployed to the cloud.

To get started: use the CLI for the fastest setup, try OpenHands free in their Slack community (no account setup needed initially), or sign up at openhands.dev to access free miniax model credits in the cloud GUI. For teams, join the free 30-day guided pilot program at openhands.dev/contact with dedicated engineering support and biweekly check-ins. Bring your own LLM API key (OpenAI, Anthropic, etc.) if preferred, and use the open-source SDK to build custom workflows or connect custom MCPs for integrations like HubSpot or Salesforce.

## Transcript

[00:00:00] I want to welcome everyone for joining
[00:00:02] today's webinar. Today's webinar is all
[00:00:04] about getting started with Open Hands.
[00:00:07] I'm Jamie. I lead developer relations at
[00:00:09] Open Hands and I'm really excited to
[00:00:12] introduce our presenter today, my
[00:00:15] colleague Owen, who will take it away.
[00:00:18] >> Hey everyone, I'm Owen. I work with
[00:00:20] Jamie and uh the go to market team here
[00:00:23] at OpenHands. Um, in light of the Aremis
[00:00:28] 2 mission happening over the last
[00:00:29] several days, this webinar will have a
[00:00:33] bit of a space theme. So, for all you
[00:00:35] space enthusiasts, get your astronaut uh
[00:00:38] helmet on and let's go for a tour of
[00:00:41] Open Hands. Um, again, this is a quick
[00:00:44] walkthrough of Open Hands. The idea is
[00:00:46] to keep this really simple. Open Hands
[00:00:49] um lets AI agents do work for you. Not
[00:00:52] just answer questions, but run commands,
[00:00:55] edit code, complete tasks. Um and today
[00:00:58] I'll show you how to think about it. If
[00:01:00] you already have used open hands
[00:01:03] extensively, this might be some repeat
[00:01:05] information for you. Today's goal is
[00:01:07] really to lower the barrier of entry of
[00:01:10] getting started with open hands. We
[00:01:12] won't go every over every detail, just
[00:01:14] sort of the mental model. Hopefully by
[00:01:17] the end of this presentation you should
[00:01:19] know how to start with open hands, which
[00:01:21] mode to use and how to scale your use
[00:01:24] for your particular use case.
[00:01:28] Um let's see. Awesome. Yeah. So our
[00:01:32] mission briefing um so to say is this
[00:01:37] one. Before you start open hands, you
[00:01:39] kind of want to know why there are so
[00:01:40] many ways to use it and what those
[00:01:42] different ways are. Um our mission is to
[00:01:45] make coding agents accessible for the
[00:01:47] entire coding community. So we know that
[00:01:49] engineers out there have many different
[00:01:51] setups um from hosting locally to
[00:01:55] preferring CLI setups or preferring guey
[00:01:57] setups. Um so the main things to know
[00:01:59] with open hands are that there's two
[00:02:02] main uh optional optionality layers. One
[00:02:05] is where it runs and then two is how you
[00:02:08] use it. So when it comes to where open
[00:02:12] hands runs, uh the main options are a
[00:02:15] local setup, a cloud setup, or some sort
[00:02:17] of self-hosted enterprise or onrem or
[00:02:21] virtual private cloud setup. When it
[00:02:24] comes to the form factors or how you
[00:02:26] interact with open hands, we have a CLI,
[00:02:29] we have a guey, and we have an SDK. So,
[00:02:33] if you're looking to get started with
[00:02:34] Open Hands, you really want to think
[00:02:37] what mission you're going on and which
[00:02:40] setup, whether where you want to run it
[00:02:42] and what form factor you want to use
[00:02:44] make the most sense for your mission.
[00:02:47] I'll go over the three main form
[00:02:49] factors.
[00:02:50] So, this is a kind of overview of our
[00:02:54] CLI. You can see a picture here of what
[00:02:56] it looks like when you get started.
[00:02:59] Think of the CLI as the fastest way to
[00:03:02] use OpenHands. You type commands, it
[00:03:05] runs tasks, it edits files directly on
[00:03:07] your machine. This is the single fastest
[00:03:11] way to get started with OpenHands. Um,
[00:03:13] and the install docs are really uh
[00:03:15] they're on our website. Very easy to get
[00:03:17] started. Uh, you could try it out fixing
[00:03:20] bugs uh with files that are on your
[00:03:22] computer. You can uh add features,
[00:03:25] improve tests and um something to know
[00:03:28] about open hands is that we are model
[00:03:30] agnostic. So you can bring your own LLM
[00:03:32] uh whether that's cla gemini or some
[00:03:35] other uh LLM. So if you're thinking
[00:03:39] about I just want to get started with
[00:03:40] open hands as fast as possible, take a
[00:03:42] look at our install docs and opt for the
[00:03:45] CLI.
[00:03:48] Now we also have a cloud uh version.
[00:03:51] This is a screenshot here of what our
[00:03:53] cloud version looks like. This is where
[00:03:55] you want to go if you want to start
[00:03:57] scaling things. Um, instead of working
[00:04:00] locally, you want to run agents in the
[00:04:02] background. This is good for debugging
[00:04:05] logs, resolving merge conflicts. Um, it
[00:04:08] connects to tools you use like GitHubs,
[00:04:12] GitLab, Slack or Jira. Some folks are
[00:04:15] connecting it to Data Dog and you can
[00:04:17] start to scale to more agents. This is
[00:04:21] if you want more capability and don't
[00:04:24] care as much about speed, you want some
[00:04:27] more leverage, start considering the uh
[00:04:29] cloud option. And this is also an option
[00:04:32] if you are looking to work with team
[00:04:36] members. Uh we do have an organizations
[00:04:39] function coming for our cloud in the
[00:04:41] pipeline. Um we do have a private beta
[00:04:44] for that. So, if you're looking to use
[00:04:46] Open Hands with your team, uh, please
[00:04:49] drop a comment in the chat or reach out.
[00:04:51] We're happy to get you access to that
[00:04:54] beta. We'd love feedback on that.
[00:04:58] If you are looking to do the most with
[00:05:01] open hands and scale, uh, and you're
[00:05:03] looking to do robust projects, uh, I
[00:05:05] would recommend the SDK for this is for
[00:05:08] building systems. I see we have a
[00:05:10] question in the chat there. Just want to
[00:05:12] make sure.
[00:05:15] Okay. Yeah, Jamie, you're just
[00:05:16] commenting. Awesome. Um,
[00:05:19] yeah. So, if you're looking to do more
[00:05:21] robust projects, I would really
[00:05:23] recommend the SDK. This is for building
[00:05:26] systems. This is not just for running
[00:05:29] one task, uh, but automating things at a
[00:05:32] very high level. Um, you can automate
[00:05:34] security fixes, dependency updates,
[00:05:37] large migrations, and you can customize
[00:05:40] tools. This is kind of where if you're
[00:05:42] looking to run agents overnight on
[00:05:44] overnight tasks or scheduled tasks, um
[00:05:47] this is where open hands really becomes
[00:05:49] programmable. Not just something that
[00:05:51] you use but something you build with. So
[00:05:53] this is for our most advanced users
[00:05:59] there. This is something to keep in mind
[00:06:01] too um for the enterprise deployment of
[00:06:05] a open hands. If you're looking for a
[00:06:08] specific um hosting situation, we have
[00:06:12] options for that as well. So definitely
[00:06:14] reach out. Um it's important to know
[00:06:17] that uh Open Hands is uh ephemerrable
[00:06:20] and isolated ephemeral and isolated
[00:06:22] sandboxes. So uh agents execute in their
[00:06:25] own isolated uh containers. There's not
[00:06:28] a lot of risk of crosscontamination and
[00:06:30] we're happy to answer questions uh if
[00:06:32] those are concerns.
[00:06:36] A few important things to know when
[00:06:38] you're get getting started. U first of
[00:06:40] all, everything can connect to the cloud
[00:06:42] whether you're using the CLI, the SDK,
[00:06:46] um all of it. Second, um you can run a
[00:06:49] lot of agents, not just one. Um third, I
[00:06:51] kind of mentioned this already, you can
[00:06:53] bring your own model, so you're not
[00:06:54] locked into one model provider. Uh and
[00:06:58] then finally you can trigger events
[00:07:00] through pipeline through you can trigger
[00:07:02] agents through events or pipelines. So
[00:07:05] really think about open hands as a
[00:07:07] system not just a uh single tool. U
[00:07:11] common integrations that are useful to
[00:07:13] know about are obviously code providers
[00:07:15] gitlab github u jura and slack and data
[00:07:19] dog are the most common other in
[00:07:21] integrations.
[00:07:25] So, you're probably thinking, uh, which
[00:07:29] mode wins? Which which is best for my
[00:07:31] mission? And it really depends on what
[00:07:33] you're trying to do. If you're doing
[00:07:36] solo coding, I really recommend trying
[00:07:38] our CL CLI. Like I said, that's the
[00:07:40] easiest uh place to start. There's also
[00:07:43] the guey. If you're looking for team
[00:07:45] collaboration, go for the open hands
[00:07:47] cloud. Um, and then if you're looking
[00:07:49] for the uh to push the boundaries of the
[00:07:53] mission, if you if you will. um try
[00:07:55] using the SDK um or reach out about
[00:07:58] enterprise setups.
[00:08:04] So one of the most common questions I
[00:08:06] get is is open hand safe to run? Will
[00:08:09] this be approved by my organization? Um
[00:08:12] by default things run in sandboxes. So
[00:08:15] they are isolated. Uh nevertheless you
[00:08:17] know still start with a test repo. don't
[00:08:21] uh you know operate with the uh minimum
[00:08:24] information needed u but it is safe to
[00:08:26] explore and and we're open source so uh
[00:08:29] when you're ready you know start small
[00:08:31] and then expand later and we're happy to
[00:08:34] uh work with teams on any security
[00:08:36] concerns uh if you want to test open
[00:08:38] hands in your environment
[00:08:42] so I want to go over a small demo of
[00:08:46] open hands
[00:08:48] okay awesome everyone yes So, this is uh
[00:08:51] one of our most exciting features. Uh we
[00:08:53] get a lot of wows on this. Um if you go
[00:08:57] and you're welcome to try this out on
[00:08:58] your own. You can go to our community
[00:09:01] Slack channel if you're not a part of
[00:09:02] that. Happy to drop the link uh down
[00:09:05] below. Um but you can just try this out
[00:09:08] by going at openhands.
[00:09:12] Um, please create an issue to
[00:09:18] translate
[00:09:20] this
[00:09:22] repo to let's say Portuguese.
[00:09:31] And then uh, you can't see this, but I'm
[00:09:33] selecting which repo I want to use here.
[00:09:39] And just give it a second here.
[00:09:54] So you can see that open hands is
[00:09:56] replying and we can uh track the
[00:09:59] progress here. We can open up our
[00:10:02] conversation
[00:10:04] and we can watch what open hands is
[00:10:07] doing here.
[00:10:20] out of curiosity. Do we have to track
[00:10:23] the conversation or can we just let it
[00:10:26] go?
[00:10:26] >> We can let it go. Uh we do not have to
[00:10:29] track track the conversation. Uh we can
[00:10:32] close this and then our issue will
[00:10:35] appear on the repo. Uh these were
[00:10:39] Yeah, you can see uh these were opened
[00:10:43] and then we can even
[00:10:46] add open hands here.
[00:10:51] Fix this issue.
[00:11:01] And we can see that open hands is on it
[00:11:03] uh with an emoji of eyes. It sees what's
[00:11:06] going on. and uh can start working on
[00:11:09] this. So if you want to get started u
[00:11:11] feel free to try this out in our
[00:11:13] community Slack. It's really fun just to
[00:11:16] see how powerful Open Hands is
[00:11:19] and pass it over to Cliff to talk about
[00:11:21] our Q2 uh pilot program.
[00:11:25] >> Yeah, thanks Owen. Um so we are uh
[00:11:29] running a uh free pilot program for u
[00:11:33] any party or community members that are
[00:11:36] interested in kind of taking open hands
[00:11:39] for a full spin. It is a 30-day um
[00:11:43] guided pilot and you're going to get
[00:11:45] access to our engineering resources to
[00:11:47] help you properly set up open hands. And
[00:11:50] this is uh really good uh if you have a
[00:11:53] team of users um from your company or
[00:11:56] from your uh you know institution.
[00:12:00] uh you know when you have a mixed bag of
[00:12:03] use cases that you think the cloud
[00:12:05] agents can be a good fit for um you know
[00:12:08] you can sign up to join the program
[00:12:12] where we can help you set it up open
[00:12:15] hands environment so the team can
[00:12:17] collaborate and really uh experiment the
[00:12:21] enterprise version of open hands uh
[00:12:23] again there's no cost and you will get
[00:12:26] dedicated uh slack support slack channel
[00:12:28] for report and uh we will meet with you
[00:12:32] on a bi-weekly
[00:12:34] uh meetings to ensure that the 30 days
[00:12:38] is productive and at the end hopefully
[00:12:41] you'll uh reach a a conclusion about the
[00:12:45] value of open hands. So yeah um the way
[00:12:48] to uh get into the program is uh you can
[00:12:52] contact us using the link below the
[00:12:54] openhands.dev/cont dev/c contact and
[00:12:57] just submit your request and then we'll
[00:13:00] follow up with uh schedule a meeting to
[00:13:02] to understand your uh specific use case
[00:13:06] and scenario. Thank you.
[00:13:10] >> Awesome. Thanks, Cliff. And uh with
[00:13:13] that, we'd like to turn it over to the
[00:13:14] audience for any questions and we're
[00:13:17] happy to answer questions with Open
[00:13:19] Hands Mission Control.
[00:13:21] Yeah, as we wait for the audience to
[00:13:25] drop questions in the chat or in the Q&A
[00:13:28] section, I did have a question about you
[00:13:31] said we could join the Slack and go
[00:13:33] ahead and get started using Open Hands
[00:13:35] in the Slackbot chatter channel and I
[00:13:38] just wanted to understand do I need to
[00:13:40] have my open hands account set up
[00:13:43] already?
[00:13:47] Yes, you do need to have your openhands
[00:13:49] account set up. Um, it is uh very easy
[00:13:53] if you have a GitHub or GitLab account
[00:13:56] to um start. So, if you go to
[00:13:58] openhands.dev
[00:13:59] uh and just click try uh you'll be
[00:14:02] prompted and it's very easy.
[00:14:05] >> Cool. And then can I get started for
[00:14:08] free? Like what are the costs associated
[00:14:10] if I sign up?
[00:14:12] >> Yeah, absolutely. Uh we're currently
[00:14:14] offering minax uh usage for free. Um if
[00:14:18] for some reason you uh want to try
[00:14:20] something out and uh need help getting
[00:14:23] more tokens into your account, feel free
[00:14:25] to reach out. We're happy to uh help you
[00:14:27] and make sure that you have the
[00:14:28] resources to fully test Open Hands.
[00:14:32] >> Does it cost anything to bring my own
[00:14:34] API key if I have like Open AI or
[00:14:37] Anthropic?
[00:14:39] >> Nope.
[00:14:42] Very cool. Um, I don't think I see any
[00:14:46] questions. I'll go ahead and just pause
[00:14:48] there just to see if anything trickles
[00:14:50] in.
[00:14:55] Okay. Uh, I I have a couple questions um
[00:14:59] for people who watch the recording later
[00:15:01] and may be thinking these as well. Um,
[00:15:05] what's your favorite way to use open
[00:15:07] hands?
[00:15:10] Um, it looks like uh Robert asked if
[00:15:13] there's a free trial. Yeah, Open Hands
[00:15:15] is free to start. Um, so yeah, there's a
[00:15:18] it's a free to start for the
[00:15:20] individuals. If you're looking for some
[00:15:23] kind of uh enterprise solution, then
[00:15:25] feel free to reach out and we have that
[00:15:27] pilot program. My favorite way to use
[00:15:29] Open Hands uh is I I love that Slack
[00:15:32] integration. Um, and then
[00:15:36] you know I I do I do like the CLI.
[00:15:38] Sometimes I find myself uh using the
[00:15:41] guey more. Um, but uh because it's
[00:15:45] easier to uh kind of see the motions it
[00:15:48] goes through. Um, but yeah, just try it
[00:15:51] out. Try it on a real project and see
[00:15:54] which form factor you like.
[00:15:56] >> Very cool. I went ahead and dropped the
[00:15:59] docs for the Slack integration in case
[00:16:01] anyone is interested in implementing
[00:16:03] that in their own server. Um, like Owen
[00:16:06] said, it's the easiest way is to not set
[00:16:09] it up and use it in OpenHand Slack just
[00:16:11] to like try it out. But if you want to
[00:16:12] set it up, the docs are right there. And
[00:16:14] then also, I just wanted to follow up
[00:16:16] with Robert's question about the free
[00:16:18] trial. Um so when you sign up to open
[00:16:20] hands you will automatically have free
[00:16:24] access to the miniax model and you can
[00:16:26] use that in the cloud. Um and so that
[00:16:30] means you can use it in the browserbased
[00:16:32] guey. If you are bringing your own key
[00:16:36] whether you are in the guey in the
[00:16:38] browser or local guey or local CLI
[00:16:42] you'll be able to use open hands in any
[00:16:45] shape that you want. Um, so yeah,
[00:16:49] there's not a ton of C. It's you you can
[00:16:53] make it free. You can make it free to
[00:16:54] use OpenHands. It just really depends
[00:16:57] what model you want. In the end, if you
[00:17:00] don't use the Miniax, which we provide
[00:17:02] for free, the cost associated would be
[00:17:05] with the LLM you're choosing.
[00:17:12] Cool.
[00:17:15] If we don't have any more questions,
[00:17:17] I'll pause for another 30 seconds or so.
[00:17:20] Then I think oh we have a question from
[00:17:23] Sadesh about for open-source version. Do
[00:17:27] I get the app integrations by default?
[00:17:30] One of the use cases that I want to use
[00:17:32] open hands is to connect to multiple CRM
[00:17:35] like HubSpot and Salesforce. So how can
[00:17:39] I do that?
[00:17:41] I think I will take that an uh question
[00:17:44] if that's okay Owen. So the open-source
[00:17:47] version is any way that you can use open
[00:17:52] hands not in an enterprise setting. So
[00:17:55] we do have an enterprise license that is
[00:17:58] specific to people who are self-hosting
[00:18:00] on prem
[00:18:02] etc etc. This doesn't sound like your
[00:18:04] use case so I'm going to leave that be.
[00:18:06] Um, so basically all the other ways are
[00:18:08] open- source. In terms of app
[00:18:11] integrations, we have we have skills
[00:18:15] very much like
[00:18:19] cloud code. And so I'm just getting the
[00:18:23] documentation for you and dropping it in
[00:18:25] the chat.
[00:18:28] The way basically you can use the skill
[00:18:31] to interact with whatever you need to.
[00:18:33] Um, it really depends
[00:18:37] about how that app would need
[00:18:40] interaction. And what I mean by that is
[00:18:43] if the app already has an MCP server,
[00:18:47] then you can set up that MP MCP server
[00:18:49] with open hands and not have to worry
[00:18:52] about skills. If the there is no MCP
[00:18:56] server and you have an API key then you
[00:19:00] can set up a skill to use that API key.
[00:19:05] Now the skills that we have are in this
[00:19:09] extension and I believe once it gets
[00:19:11] updated it populates into open hands so
[00:19:14] that you can select it. You can create
[00:19:17] your own skills. Uh we definitely
[00:19:19] encourage people if you have a skill
[00:19:21] that's working for you, please make a PR
[00:19:24] to our openhandextensions
[00:19:27] and we would be happy to merge that and
[00:19:29] have that be available for the
[00:19:30] community. But off the top of my head, I
[00:19:35] assume HubSpot and Salesforce likely
[00:19:37] have an MCP. So probably what I would
[00:19:41] suggest to get started with that is you
[00:19:44] can use the CLI and you can get those
[00:19:46] MCPs set up. It really depends if it
[00:19:48] uses OOTH or not. If it uses OOTH to
[00:19:52] authenticate the MCP, then cloud is
[00:19:55] probably not the best option because I
[00:19:58] believe this is something that we plan
[00:19:59] to have but we don't have today, which
[00:20:01] is OOTH support. The CLI and the local
[00:20:04] guey, you can use that OOTH support to
[00:20:06] authorize that MCP.
[00:20:08] If you don't want to use MCP, like I
[00:20:10] said, APIs, just get that API key and
[00:20:13] you can add it as a secret and then you
[00:20:15] can develop a skill to use that or you
[00:20:19] can just say, "Hey, Open Hands, access
[00:20:23] my HubSpot, look up the APIs that you
[00:20:26] need to." And then once you figure out
[00:20:28] that workflow, you can have Open Hands
[00:20:31] create that skill for you. You don't
[00:20:32] have to create that skill by hand. And I
[00:20:36] think for the most part that answers the
[00:20:38] question.
[00:20:51] >> Thanks for the question. Great question
[00:20:53] there.
[00:20:55] >> Just waiting in case there's any other
[00:20:57] questions.
[00:21:01] Okay. So if you think of a question
[00:21:06] later,
[00:21:07] please join our Slack. That is our
[00:21:10] contact. Um please join our Slack and
[00:21:14] ask in the question section.
[00:21:17] Cliff, Owen, and myself are all there to
[00:21:20] help you be successful with open hands.
[00:21:23] Um so yeah, please join the Slack. If
[00:21:25] you have any questions about the pilot
[00:21:27] program that Cliff talked about, please
[00:21:31] contact using the um slashcont.
[00:21:35] >> Yeah, Robert, I see that Robert, you had
[00:21:37] a um you posted a a comment in the chat
[00:21:41] box and if you're interested in free
[00:21:43] trial, uh just complete the contact form
[00:21:47] and uh one of us will follow up with you
[00:21:49] and and to share more information about
[00:21:51] that.
[00:21:54] And then can I attach uh Sadesh just had
[00:21:57] another question. Can I attach my custom
[00:21:59] MCPS?
[00:22:00] You can connect your custom MCPS.
[00:22:05] It just depends how your MCP would need
[00:22:10] to be connected and I can pull in our
[00:22:14] docs. There'll be more information. It
[00:22:16] really just depends if you're
[00:22:20] going to be using the MCP locally. Is
[00:22:23] the MCP hosted locally? is it hosted
[00:22:24] somewhere else, etc. Um, that's the
[00:22:29] doc that came up and then if you scroll
[00:22:31] to the bottom of that doc, it can talk
[00:22:33] about like the CLI versus SDK, etc. So,
[00:22:36] that should
[00:22:38] have you be good to go. But join the
[00:22:40] Slack in case you run into anything and
[00:22:42] we can answer those questions as they
[00:22:44] come in.
[00:22:45] >> Yeah. And the other thing I want to call
[00:22:47] out is um for a lot of these advanced
[00:22:50] use cases um definitely check out our
[00:22:53] SDK which is also open source. Uh for
[00:22:57] advanced engineers uh you're going to
[00:23:00] find the SDK provides a lot more
[00:23:02] flexibility to be able to build these
[00:23:04] custom uh coding workflows. uh there
[00:23:07] will be a lot more control that will
[00:23:09] allow you to uh you know manage the
[00:23:13] agent behavior uh which is u you know
[00:23:17] most of our community members and
[00:23:19] advanced users find it super helpful. I
[00:23:22] just wanted to call that out as well.
[00:23:26] >> Thank you Cliff. You can even use our
[00:23:28] SDK to create essentially your own open
[00:23:31] claw as well. uh we have people on the
[00:23:34] team who have created like workspaces
[00:23:37] using the SDK for their specific stack
[00:23:41] and workflow. Um so yeah, for the power
[00:23:43] users, 100% agree with Cliff. Check out
[00:23:46] the SDK and I dropped the docs down
[00:23:48] there.
