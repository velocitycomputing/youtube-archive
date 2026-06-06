---
video_id: Rt3MsyMRXcI
title: "Only Builders and Sellers Will Matter in AI | EP 586 | May 27 | Daily AI News from GAI Insights"
channel: "GAI Insights: Daily AI News & Learning Lab"
url: "https://www.youtube.com/watch?v=Rt3MsyMRXcI"
watched_date: 2026-05-30
watched_at: "2026-05-30T12:00:00Z"
watch_count: 1
duration_seconds: 1890
source: youtube-history-browser
history_label: May 30
history_order: 132
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 189
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode reviewed six AI developments across management, developer tools, automation, and data infrastructure. Key discussion points included: (1) managers becoming bottlenecks as AI increases worker productivity—the constraint has shifted from work generation to validation and review processes; (2) Grock Build, XAI's terminal-based coding agent tool, competing with Claude Code and Cursor; (3) Microsoft's WebRite, which creates minimal web interfaces for faster agent task completion instead of navigating full browsers; (4) Google Cloud's Glance, a pipeline converting long videos into social media clips using speech-to-text and Gemini analysis; (5) an open models commentary piece rated as low-impact; and (6) Dun & Bradstreet's complete rebuild of their 642-million-business database to be AI-agent readable, adding semantic graphs, resolution engines, and MCP tools rather than just human-analyst-optimized interfaces.

Actionable takeaways: your organization urgently needs new management processes to handle AI-generated output—establish validation workflows before bottlenecks paralyze teams. Evaluate multiple coding agents (Grock, Claude Code, Cursor) to find the best fit for your stack and cost model. Implement web automation tools like WebRite for deterministic business process efficiency. If you produce video content, adopt AI video-clipping workflows for social distribution. Most critically: audit your organization's data infrastructure and begin rebuilding legacy databases to be AI-agent compatible—make your data "robot readable" with semantic graphs, entity resolution, and API-first design, as Dun & Bradstreet demonstrated.

## Transcript

[00:00:06] [music]
[00:00:09] Good morning, good evening everyone.
[00:00:11] This is Ludika Pikina with GI Insights.
[00:00:14] Welcome to Daily AI news where we rate
[00:00:18] everyday AI developments essential,
[00:00:21] important or optional. The articles that
[00:00:25] we are going to review today are at
[00:00:27] jiinsights.com/articles.
[00:00:31] Please follow along and let us know what
[00:00:33] you think about these developments and
[00:00:35] whether you agree or disagree with our
[00:00:38] ratings. Today I have Adam who is back,
[00:00:42] Adam Raaport. Um, welcome back Adam John
[00:00:47] Ankage and a wonderful guest Chris
[00:00:50] Brookke who um who who has wonderful
[00:00:55] great insights and when he joins us
[00:00:58] periodically. Welcome Chris.
[00:01:01] >> Good to be here. Good to be here.
[00:01:03] >> Great. All right, let's start with the
[00:01:04] first article anash.
[00:01:07] >> Thanks Luda. So the first one that we
[00:01:09] have for today comes from Harvard
[00:01:10] Business Review and it is titled
[00:01:13] Managers Are Struggling to Keep Up with
[00:01:15] the AI productivity boom.
[00:01:18] >> Yes, an interesting um article. John,
[00:01:22] what do you think about this one? Yeah,
[00:01:25] I read what it is about.
[00:01:26] >> Yeah, I read this thing as essential and
[00:01:28] the reason is that they do a great job
[00:01:31] of showing that the real critical issue
[00:01:36] in AI from management standpoint is a
[00:01:39] change in management process in
[00:01:40] particular a change in timing and we
[00:01:43] hear this again and again that uh people
[00:01:45] are getting more work done but the work
[00:01:48] process can't productively use that. So
[00:01:51] for a specific example, lots of work is
[00:01:54] coming through on something like when
[00:01:57] you look at uh software coding for
[00:01:59] example, the bottleneck has gone from
[00:02:02] specification to validation and Karpathy
[00:02:06] u said something very interesting is he
[00:02:08] said you know uh traditional software
[00:02:12] can do things that can be specified. He
[00:02:15] said the big difference in AI is that
[00:02:18] you can do anything that can be
[00:02:20] validated. And I think that's a proper
[00:02:23] the more I think about it the more that
[00:02:25] that's a really brilliant statement
[00:02:27] because that's true both in
[00:02:29] organizational process which this
[00:02:31] article points out somebody's done the
[00:02:33] work is it AI slop is it validated and
[00:02:35] so forth. So the new choke point comes
[00:02:37] to the validation point in whatever your
[00:02:39] cognitive capacity is in your
[00:02:41] organization.
[00:02:43] And that's also true for
[00:02:46] uh software and agents that have
[00:02:48] reinforcement learning because when you
[00:02:50] think about reinforcement learning
[00:02:52] that's a process of validation between
[00:02:54] an objective function and the results
[00:02:57] from the model and so um I think that
[00:03:01] the insight of karpathy that we're
[00:03:03] moving to the world of automating those
[00:03:05] things which can be validated and then
[00:03:07] rethinking what organizational processes
[00:03:10] need to be in the context of that I is I
[00:03:13] think job one for organizations that
[00:03:17] have gone if you take our rise model
[00:03:19] organizations that have gone through
[00:03:20] research and education islands of
[00:03:21] innovation validation is a critical part
[00:03:24] of scaling so um I give it essential
[00:03:29] >> okay essential from John um article
[00:03:32] specifically points out that the
[00:03:34] managers are really overwhelmed and
[00:03:36] can't process the stuff that uh AI
[00:03:39] generates from their from their uh
[00:03:42] direct reports. Can
[00:03:44] >> I just interrupt one one thing there?
[00:03:46] They can't they can't they're
[00:03:48] overwhelmed in the existing management
[00:03:50] process.
[00:03:51] >> Correct.
[00:03:52] >> If you go back to the industrial
[00:03:53] revolution,
[00:03:54] uh you know, executives at the railroads
[00:03:57] were overwhelmed by the amount of
[00:03:58] information they were getting until they
[00:03:59] created modern accounting.
[00:04:01] >> Right. So it it it it is a it's becoming
[00:04:04] a bottleneck because the process hasn't
[00:04:06] changed. So the underlying uh there's
[00:04:09] more more stuff created by employees
[00:04:12] using AI. They surface it back and then
[00:04:15] managers cannot process it uh in the old
[00:04:18] process. Um Adam, what did you think?
[00:04:22] >> Yeah. Um I was I was important on this
[00:04:24] one. I I think uh it was good to name
[00:04:27] this bottleneck, right, that basically
[00:04:29] the manager has review. I'm sure a lot
[00:04:31] of managers who read this will recognize
[00:04:33] that that's what's happening to them. uh
[00:04:35] many of them might already be aware of
[00:04:37] it. So that in itself I'm not sure was
[00:04:40] such a big realization here that they
[00:04:42] are that bottleneck. I'm sure they're
[00:04:43] experiencing it. Um I felt like it it
[00:04:45] didn't give enough practical advice
[00:04:47] other than to get out of the way. I feel
[00:04:49] John's point is essential. Uh and the
[00:04:51] point he makes definitely transcends the
[00:04:53] scope of this article. Uh so I was
[00:04:55] important. I think it's worth naming and
[00:04:57] raising the discussion, but I didn't
[00:04:59] find it an essential read.
[00:05:01] >> Okay. Uh Chris, what were your thoughts?
[00:05:05] So, I'm with Adam being important, but I
[00:05:08] think John's insight was definitely
[00:05:10] essential. I think when you give
[00:05:12] employees the ability to do 40 hours of
[00:05:15] work in one day or 500 hours of work in
[00:05:18] one day for certain um tasks, when you
[00:05:22] extrapolate that to a manager that has
[00:05:25] 30 reports or 15 reports, that manager
[00:05:28] is now inundated with employees that are
[00:05:31] hyperproductive. And there's no um
[00:05:34] solution offered right now on how that
[00:05:38] manager without an AI themsel to vet and
[00:05:41] manage this inbound productivity to get
[00:05:45] out of this bottleneck that they've now
[00:05:47] become. So I I think it's essentially uh
[00:05:51] it's an essential problem that companies
[00:05:53] are going to absolutely bottleneck and
[00:05:55] hit. But I think this just an important
[00:05:57] article. They didn't really give us the
[00:05:58] solutions.
[00:06:00] >> Yeah. uh and the solutions are are yet
[00:06:02] forming I think but this is just a good
[00:06:05] identifier well well stated well
[00:06:08] described as a as a here's a problem
[00:06:11] look at it right what did you think an
[00:06:15] >> u I was important on this one duda I
[00:06:17] agree with what uh John is saying but I
[00:06:19] also agree with Chris that there is no
[00:06:21] solution here and we need those
[00:06:23] solutions immediately to sort of solve
[00:06:26] this problem so that's very important
[00:06:29] Okay, I was actually with John.
[00:06:33] [laughter and gasps] So, but it is two
[00:06:35] of us John on three. So, um I don't
[00:06:41] know. But I I my feeling is yes it
[00:06:44] didn't talk about solutions but the
[00:06:46] solutions I think are not generic
[00:06:50] necessarily other than change the
[00:06:52] process figure out how are you going to
[00:06:55] uh do it better but um but just but just
[00:06:58] voicing the problem is actually
[00:07:01] critically important. So we're going
[00:07:03] essential on this one. All right let's
[00:07:05] proceed.
[00:07:08] >> Okay moving on to the next one. This one
[00:07:10] comes from XAI and they are introducing
[00:07:13] Grock build.
[00:07:15] >> Chris, tell us all about it and what do
[00:07:17] you think?
[00:07:19] >> All right, so this is
[00:07:22] Grock um X SpaceX Elon Musk's version of
[00:07:28] the Claude Code CLI terminal computer.
[00:07:34] You see this with Codeex, you see this
[00:07:36] with Claude, you see this with Manis,
[00:07:38] you see this in the sort of open claw
[00:07:40] movement. Um, Grock now has their entry
[00:07:43] point where you can install this on the
[00:07:45] terminal and utilize it to code um to
[00:07:51] build to spawn agents. Um, it's in beta.
[00:07:55] They know they're going to have some
[00:07:56] issues. Um it's interesting to see that
[00:08:00] they've launched this solution with all
[00:08:02] of their compute going to anthropic and
[00:08:07] um so that that's that's a deeper um
[00:08:10] interesting parallel that's going on.
[00:08:12] But I'm sure that what this provides to
[00:08:15] most coders is another solution to add
[00:08:18] to their coding stack. Um it's
[00:08:22] essentially $30 a month for the base
[00:08:26] model. That'll get you um a certain
[00:08:28] amount of usage. And then their super
[00:08:30] Grock is $300 a month. Um which is $100
[00:08:34] more than Claude's $200 a month model,
[00:08:37] but Claude gets into overages where
[00:08:39] maybe Grock may give you more usage. So
[00:08:42] um with that, this is for the developer
[00:08:44] side that's not afraid of terminal. And
[00:08:47] um I would say it's
[00:08:50] um it's essential for uh the frontier
[00:08:54] models that Grock is there, but um for
[00:08:57] the business leader, this is just an
[00:08:58] important um development.
[00:09:01] >> Okay. Um Adam, what did you think?
[00:09:06] >> Yeah, I I was optional. I I I think I
[00:09:09] could support important. Um I don't
[00:09:10] think I think people still underestimate
[00:09:12] Grock and what XAI is doing in the
[00:09:14] space. Um the the a key here is
[00:09:16] definitely they're challenging on
[00:09:18] pricing against against the other
[00:09:19] leaders. Um probably on speed as well,
[00:09:22] but most of the capabilities are are
[00:09:24] pretty much catch-ups. Um so I don't
[00:09:27] think if someone were using codeex or
[00:09:28] cursor, they would be switching this
[00:09:30] week. It also is gated to a degree uh in
[00:09:32] terms of the subscription models and the
[00:09:34] pricing. Um but Chris, just to the one
[00:09:37] thing there, you were talking about
[00:09:38] Enthropic using uh XAI's infrastructure
[00:09:41] for the training and so how did they
[00:09:43] bring this out? But what I what I found
[00:09:45] in that is that cursor actually you
[00:09:47] recently used um their training
[00:09:49] inference and they actually got a whole
[00:09:51] bunch of training data from cursor as
[00:09:54] part of that deal. Uh so it's really
[00:09:56] interesting to see like what will they
[00:09:57] get from anthropic uh in trade when they
[00:10:00] when they you know get possibly help
[00:10:02] them with their data. So uh they're in a
[00:10:04] really interesting position in terms of
[00:10:05] actually helping some of the other
[00:10:07] state-of-the-art models get their models
[00:10:08] built now. Um definitely something to
[00:10:10] keep an eye on. I thought this news
[00:10:11] itself was a bit of a catch-up uh for
[00:10:14] the developer, but I could support
[00:10:15] important.
[00:10:17] >> Okay. Yeah, it's another it's a product
[00:10:19] announcement. No data is there of how
[00:10:22] good it is and how versatile it is. So,
[00:10:26] it's uh it's really a product
[00:10:27] announcement in preview to to boot.
[00:10:30] Okay. Uh Ankash, where were you?
[00:10:33] >> Uh this is optional for an AI leader.
[00:10:35] Luda, I don't think any AI leader would
[00:10:37] take the risk of using uh Xi's models or
[00:10:41] uh even their build uh right now for uh
[00:10:44] their organization related uh
[00:10:47] development activities. So optional.
[00:10:49] >> Okay. Uh and John, you have the final
[00:10:51] word here.
[00:10:53] >> Yeah, I had it as essential. Um the um
[00:10:56] first of all, I I'm not confident in
[00:10:58] what you just said um an a lot of
[00:11:01] business leaders aren't using Barack one
[00:11:02] way or another. uh they don't have as
[00:11:04] much market share but I think um
[00:11:08] uh you know I think that they are a
[00:11:10] contender at least for some some
[00:11:12] functions and certainly small business
[00:11:14] and so forth. I think that the second
[00:11:16] thing is I and and tell me if I'm wrong
[00:11:18] here because you know Adam you and Chris
[00:11:20] you know obviously are more technical
[00:11:22] but I thought that this notion of
[00:11:24] launching multiple agents off one agent
[00:11:27] uh was a step forward compared to other
[00:11:30] uh software development environments.
[00:11:32] Um,
[00:11:32] >> not really.
[00:11:33] >> Um, a lot of them will spit up sub
[00:11:35] agents and and even agent swarms now.
[00:11:38] >> Okay. Well, then I that downgraded to
[00:11:41] important. That's interesting because
[00:11:42] the model said it was distinct
[00:11:44] in terms of their implementation.
[00:11:46] >> They may give you more capability to run
[00:11:48] more agents without maxing out your
[00:11:51] token limit. Um, is probably
[00:11:54] >> what what the big deal there is. and
[00:11:56] Grock can and um Open AAI can do a
[00:11:59] little bit more multimodal like visual
[00:12:01] audio than what Claude can. So there's
[00:12:03] probably some things Grock can lead on
[00:12:06] voice intelligence they're they do very
[00:12:08] very well at. So I I think they're going
[00:12:10] to have some wins for sure. It's just
[00:12:13] their pricing model and really what what
[00:12:15] the problem is is now that you have all
[00:12:16] of these coding agents that you wouldn't
[00:12:18] mind using all of them at once, you need
[00:12:20] another solution. There's there's a
[00:12:22] couple floating out there now that are
[00:12:24] helping you manage all of your coding
[00:12:26] agents that have multiple coding agents
[00:12:28] spawning. So, as the operator, it it's
[00:12:31] starting to um be a really interesting
[00:12:34] ecosystem of managing all of these
[00:12:36] frontier model coders and allowing them
[00:12:39] to look at the same project is is a
[00:12:42] phenomenal capability. So, then you get
[00:12:44] the intelligence across all three um
[00:12:46] which is super um it's a super
[00:12:49] capability. It's like a superpower. Um,
[00:12:51] that's probably what the skills are.
[00:12:53] >> Yeah, but they're not really yet
[00:12:54] focusing on it. So guys, I'm going to go
[00:12:57] optional because it's a product
[00:12:58] announcement, no data. It's a preview.
[00:13:01] It's an entrance and catchup uh from um
[00:13:05] from XAI, but it's really from Grock,
[00:13:08] but it's not telling us much. So, let's
[00:13:12] just reserve our judgment. Optional, it
[00:13:14] is. Let's proceed.
[00:13:17] >> Okay, moving on to the next one.
[00:13:20] Uh this one comes from Microsoft and
[00:13:22] this is about webbrite. A terminal is
[00:13:25] all you need for web variant.
[00:13:28] >> Yes, Adam, please tell us all about it.
[00:13:31] >> Yeah, so uh webbrite terminal is all you
[00:13:33] need. I I thought this was optional.
[00:13:35] It's it's research. It's certainly
[00:13:36] interesting. I'm just not sure. Uh we
[00:13:39] we'll probably have to wait and see how
[00:13:40] it plays out. So, it's a really cool
[00:13:42] concept and that's that rather than
[00:13:44] using the traditional model of a of a
[00:13:46] browser or even an agent browser where
[00:13:48] you go through and navigate the existing
[00:13:50] website, it actually just stands up the
[00:13:52] web parts that it needs to get a job
[00:13:54] done. And there's some demos on there
[00:13:56] where you can watch it fast forward
[00:13:57] through. Um but like for example a task
[00:14:00] of finding specific flights from one
[00:14:01] place to another without this sort of
[00:14:04] approach it took 15 minutes and it was
[00:14:06] six minutes by just creating a specific
[00:14:08] part that used the Google flight skill
[00:14:11] that was already curated for
[00:14:13] specifically the search they were
[00:14:14] looking for. So it's a neat idea. Um it
[00:14:17] feels a bit like too much like research
[00:14:19] still uh to have any direct immediate
[00:14:21] relevance though.
[00:14:23] >> [clears throat]
[00:14:24] >> Uh what did you think Ankash?
[00:14:28] >> I was leaning toward important on this
[00:14:29] one. Luda Adam uh correct me if I'm
[00:14:32] wrong here. I thought this is more of a
[00:14:35] play on the playright uh web automation
[00:14:38] approach that is already there right u
[00:14:40] so I was just using it yesterday to
[00:14:42] create a code which goes to our AI
[00:14:45] factory and then fetches the articles
[00:14:49] that it has uh extracted for me or uh
[00:14:51] identified for me. Right. Uh so this
[00:14:54] takes that further. Right. This uh can
[00:14:58] do that for me and then we can create a
[00:15:00] skill out of it which can be then
[00:15:02] replicated across various things and can
[00:15:05] be done in multiple ways. And I don't
[00:15:07] think it's just research right now Adam
[00:15:09] it's not uh tested uh broadly but they
[00:15:13] are already offering it out that you can
[00:15:15] just use it test it out and do all of
[00:15:18] these things. And I think it's important
[00:15:21] because you see a lot of computer use
[00:15:24] agents or browser agents as well, right?
[00:15:26] So they try to do some of the things
[00:15:30] non-deterministically
[00:15:31] which can be done deterministically
[00:15:33] through these small uh code snippets
[00:15:36] that we can write through web or
[00:15:38] playright right and that's where it
[00:15:40] becomes interesting that okay you can do
[00:15:42] something deterministically which a
[00:15:45] claude or a charge will first take a lot
[00:15:48] of time to do that and will not do it
[00:15:50] 100% of the time right so that's why I
[00:15:53] was thinking that this might be
[00:15:55] important I'm I'm totally convinced on I
[00:15:58] think
[00:16:00] >> I'm actually essential about it and I
[00:16:02] think we have some deep um deep thinkers
[00:16:06] here. Um um Ashish is saying that this
[00:16:10] can change the game for Cal um for for
[00:16:13] poor agents and uh Deepak is saying that
[00:16:17] they the Microsoft is very quietly um
[00:16:22] hitting the state-of-the-art in um web
[00:16:25] agents and that is is this is the
[00:16:28] capability that essentially allows web
[00:16:31] agents to be um manageable
[00:16:35] uh reroutable
[00:16:37] reworked controlled uh with the memory
[00:16:40] with um so it's way higher level than
[00:16:45] what currently anthropic and open AI
[00:16:47] offer with their terminal uh type of
[00:16:50] things. So this is a next level next
[00:16:54] level of intelligence uh here. What did
[00:16:57] you think uh Chris?
[00:17:00] >> I would rate it as important as a user
[00:17:04] if you're going into this stack. Um, you
[00:17:06] can live in terminal now. If your skills
[00:17:08] were okay in terminal before AI and the
[00:17:12] last 90 days have been so
[00:17:13] transformational in the world of coding,
[00:17:15] you can live in terminal and be super
[00:17:17] productive. Things you always wanted to
[00:17:19] do but couldn't, you can now. So, so
[00:17:22] this is a great conduit to allow you to
[00:17:24] manage your infrastructure and frontier
[00:17:28] models and uh manage probably token
[00:17:30] consumption. So um maybe some indexing
[00:17:33] of your code base so Cloud Code works it
[00:17:36] uh a little bit more effectively and you
[00:17:38] don't hit your usage limit. So so I
[00:17:40] think there's going to be a big uptick
[00:17:41] for users of this platform. I haven't
[00:17:43] used specifically this tool but um I I
[00:17:46] think anything that it would enable your
[00:17:47] terminal management and skill level to
[00:17:50] um uplevel your your skills would be a
[00:17:53] win. So I'll go with important on this
[00:17:55] um for any of the users that are in the
[00:17:57] tech space.
[00:17:58] >> Okay. Um so Ashish is really bullish.
[00:18:01] So, he's saying he will um buy it today
[00:18:04] and it's essential for for him. John,
[00:18:07] what were your thoughts?
[00:18:10] >> Yeah, I originally had this is optional,
[00:18:12] but uh you know, given the conversation
[00:18:14] about being able to do everything from
[00:18:15] the terminal and especially the thing
[00:18:17] you said, Chris, about a way to monitor
[00:18:20] uh token use, which I think is going to
[00:18:22] be a huge issue, continue to be a huge
[00:18:24] issue. Um I'm I'm good for important.
[00:18:27] >> All right, go important. important it is
[00:18:29] but I I think this is the next level of
[00:18:33] um capability that uh Microsoft quietly
[00:18:35] put together. All right. Um let's go
[00:18:38] next one and we'll have to accelerate.
[00:18:42] >> Okay. Moving on to the next one. This
[00:18:43] one is a case study from Google Cloud
[00:18:45] and it is titled how Glance turns hours
[00:18:48] of video into mobile ready clips with
[00:18:51] AI.
[00:18:52] >> Yes, could you please tell us more about
[00:18:54] this one?
[00:18:57] Luda. So this is a very interesting case
[00:18:59] study where Glass uh is taking uh large
[00:19:02] videos. So 30 minutes, 40 minutes, 1
[00:19:05] hour videos and it is using a whole
[00:19:08] pipeline of geni and non-jennai tools to
[00:19:12] convert them to small clips. I think uh
[00:19:15] Luda this can be very useful for our
[00:19:17] sort of video editor who is on the call
[00:19:20] right now. They should use this
[00:19:22] definitely. Uh but yeah so uh what they
[00:19:25] are doing is they're using a speechto
[00:19:28] text model first to convert uh the video
[00:19:31] into a transcript and then they are
[00:19:33] using Gemini to go through that
[00:19:35] transcript identify uh the part of the
[00:19:38] transcript that can go viral and then
[00:19:41] they are using some of the deterministic
[00:19:43] tools to cut the video from that part
[00:19:46] identify if a person is speaking if a
[00:19:49] single person is speaking or multiple
[00:19:50] people are speaking and then go about
[00:19:53] cutting the video bases all that
[00:19:55] information. So I think this is a
[00:19:57] workflow which every organization needs.
[00:20:01] Uh so that's why I was sort of essential
[00:20:03] on this one
[00:20:04] >> and there's a free layer that is quite
[00:20:06] powerful I take it. Okay. Um but so
[00:20:10] anash you are important on this one.
[00:20:11] Optional
[00:20:12] >> essential. Essential
[00:20:14] >> essential. All right. Uh Chris,
[00:20:19] >> I felt this was a really cool feature ad
[00:20:22] of I I've used platforms like Opus Clip
[00:20:25] and others that are able to like uh clip
[00:20:27] the viral moments and help for social
[00:20:29] media. So there there's a lot of players
[00:20:31] in the space. This is Google's um
[00:20:33] product for that. It's really cool.
[00:20:35] That's for sure. If you're trying to um
[00:20:38] if you do a podcast for your business
[00:20:39] and you want the best three minute clips
[00:20:42] sliced up so you can share them on
[00:20:43] social media and Instagram like these
[00:20:45] are awesome solutions for that and if
[00:20:48] Google's building it in it's another um
[00:20:50] reason to go into their ecosystem.
[00:20:52] >> So you're thinking
[00:20:54] >> important
[00:20:55] >> important um John
[00:21:01] >> I'm on the fence between important and
[00:21:02] essential. I think the ability to grab
[00:21:04] this stuff and put it vertically is
[00:21:05] critical for consumption for all the
[00:21:07] reasons I mentioned.
[00:21:08] >> Okay. Uh Adam,
[00:21:12] >> yeah, I think Chris is right though. It
[00:21:13] is a fairly crowded space and if if
[00:21:15] people are already on to this, it's it's
[00:21:18] probably the latest greatest version. Um
[00:21:20] they do a good job. I would keep it
[00:21:22] important because as a case study, they
[00:21:24] do a good job of actually laying out the
[00:21:26] architecture and what they've done. But
[00:21:28] at the end of the day, it's it's uh it's
[00:21:30] just a fairly complex pipeline. It's a
[00:21:33] nice example of a combination of
[00:21:34] probabilistic and deterministic uh
[00:21:37] components coming together to get a
[00:21:38] really best-in-class solution. Uh but I
[00:21:40] I don't think it's essential.
[00:21:42] >> Okay, important. It is. Let's proceed.
[00:21:46] >> Okay, moving on to the next one. This
[00:21:48] one comes from Nathan Lambert of
[00:21:50] Interconnect AI and he's proposing some
[00:21:53] ideas for what comes next in May 2026
[00:21:56] and beyond.
[00:21:58] >> Yeah. Um interesting observations,
[00:22:02] several of them on the open uh model
[00:22:05] frontier. What did you think about this
[00:22:07] Chris? So reading it, I would say that
[00:22:11] um it covers some ground on um open
[00:22:15] models as like Quinn and some of these
[00:22:17] other open- source systems haven't quite
[00:22:19] had their um boost like the Frontier
[00:22:23] models. Um he sort of rags a little bit
[00:22:26] on Gemini not really having a complete
[00:22:28] product compared to Claude. I don't
[00:22:30] necessarily agree um with some of his
[00:22:33] setup. The one interesting thing he does
[00:22:35] bring up in this is Mythos. mythos um
[00:22:37] concept is that um I I I don't know if
[00:22:40] it's well defined in this article, but
[00:22:42] um the idea that Claude has developed a
[00:22:44] system that is able to find zero day
[00:22:46] vulnerabilities at scale and there's
[00:22:48] lots of vulnerabilities that their AI
[00:22:50] can now find. Um the truth of the matter
[00:22:53] is bad actors are using AI before mythos
[00:22:57] to find ways to fish um to attack to to
[00:23:02] uh take command and control of systems.
[00:23:05] So I I think this is a weak article that
[00:23:07] um sort of highlighted [snorts] some
[00:23:09] things we're already seeing that's um
[00:23:11] sort of common knowledge. Um so with
[00:23:13] that I would say it's um optional for
[00:23:16] the business owner.
[00:23:17] >> Okay. Optional from Chris. What did you
[00:23:20] think Adam?
[00:23:21] >> Yeah I I agree. My my commentary I said
[00:23:24] it was a good aggregation of updates uh
[00:23:26] but it didn't really provide much
[00:23:28] direction or guidance. Yeah.
[00:23:30] >> So fell a little flat for me.
[00:23:32] >> Okay. Um
[00:23:35] John, we're going optional.
[00:23:38] Yeah, an okay with that.
[00:23:41] >> Yes, Luda.
[00:23:42] >> Okay, optional it is. Let's proceed to
[00:23:45] the last one.
[00:23:47] >> Okay, the last one comes from Venturebe
[00:23:49] and it talks about DNB's database of 642
[00:23:53] million businesses that it was built for
[00:23:55] humans, not AI agents. So, how they
[00:23:58] rebuilt it for AI agents. Yeah, it's um
[00:24:02] it's impressive. The volume is
[00:24:04] impressive. So, Adam, tell us tell us
[00:24:06] about it.
[00:24:07] >> So, um yeah, I would say I'm at least
[00:24:10] important on this. I I don't think I've
[00:24:11] even fully thought through the
[00:24:14] significance of this in terms of a um I
[00:24:16] guess a signal in market, right? But so
[00:24:18] done in Brad Street or they call them
[00:24:20] DNB. Um that's they've had over 180
[00:24:23] years of building this comprehensive
[00:24:25] commercial database. Uh they have this
[00:24:27] thing commercial graph. It has 642
[00:24:30] million businesses as well as the
[00:24:32] relationships, the corporate
[00:24:33] hierarchies, risk profiles, just
[00:24:35] tremendous amounts of information, but
[00:24:37] it was built for human credit analysts.
[00:24:40] Uh, and they were finding that the the
[00:24:42] agent system were actually having
[00:24:44] problems with the system as it existed.
[00:24:45] And they actually completely rebuilt it.
[00:24:48] Uh, which was a massive overhaul. I
[00:24:50] mean, talking about 642 million
[00:24:51] businesses and all that information
[00:24:53] about them. But what you have now is
[00:24:55] this resolution engine. And so the
[00:24:58] agents don't just get a match on a name
[00:25:00] when someone's looking for information.
[00:25:02] They actually verify an entity. And
[00:25:04] that's really what having these
[00:25:05] probabilistic systems built into this
[00:25:08] now is really offering them, which is
[00:25:09] incredibly powerful. So they had to do a
[00:25:11] completely new schema, a data fabric
[00:25:14] layer. Um, they now have tools that are
[00:25:16] served through MCP. They have skills
[00:25:18] built into it. Um, you know, it's it's
[00:25:20] just a complete modern rewrite. And you
[00:25:24] think about a Bloomberg or a Lexus Nexus
[00:25:26] or so many of these other things, we
[00:25:28] should uh either anticipate that these
[00:25:30] are going to be coming or start to be
[00:25:32] expecting it of them and demanding it uh
[00:25:35] so that they can modernize their own
[00:25:36] systems and for a lot of organizations
[00:25:39] maybe start asking yourself if there's
[00:25:40] anything uh of your own in terms of data
[00:25:43] that that you need to be applying this
[00:25:45] to. So at least important for me.
[00:25:48] >> Okay. Um what did you think Chris?
[00:25:52] I would go with Essential on this one.
[00:25:53] Um it's a great case study and it's a
[00:25:56] company that um we've interacted with if
[00:25:59] you run business whether you really know
[00:26:02] it how easy the transaction is. I I use
[00:26:04] them if you're going to be an app
[00:26:06] developer to make sure that you're um
[00:26:08] able to get your Apple developer
[00:26:10] accounts in the past or if you're
[00:26:11] working with SBA before they change
[00:26:13] their sort of naming for um being
[00:26:15] government contracting they they use
[00:26:17] DNB. So it has a wealth of data. it's
[00:26:20] it's probably going to change the way a
[00:26:22] lot of companies operate by using this
[00:26:24] as an MCP uh for tracking vendors and
[00:26:27] management and things. So, um I would
[00:26:29] say it's essential and it's a an amazing
[00:26:32] um large use case of uh a traditional
[00:26:36] data set that existed before AI with now
[00:26:38] the full AI treatment.
[00:26:41] >> That's interesting. Okay. Um essential
[00:26:44] from Chris. What do you think, John?
[00:26:46] >> Yeah, I had I was on the fence between
[00:26:48] important and essential. like support
[00:26:49] essential um for all the reasons he said
[00:26:52] like this whole issue of making things
[00:26:54] robot readable not just human readable
[00:26:56] is central here's a great example of it
[00:26:58] uh another fun fact you know that
[00:27:00] William McKinley um Grover Cleveland uh
[00:27:04] Abraham Lincoln all work for Dunham and
[00:27:06] Brad Street isn't that funny
[00:27:09] >> uh what I also liked is they don't they
[00:27:12] don't present an architecture but they
[00:27:14] talk through it so they built the
[00:27:17] database layer they they built the uh
[00:27:19] semantic graph on top of it. They built
[00:27:22] the identic harness essentially on top
[00:27:24] of that and um and and and and then they
[00:27:28] give four um thoughts right of what they
[00:27:33] experience doing this. And even though
[00:27:36] those are like we talk about data
[00:27:39] foundations
[00:27:40] um come before agent infrastructure but
[00:27:43] this is the fact that they had such a
[00:27:46] scale right and needed to rethink it and
[00:27:49] think about how they put together this
[00:27:52] uh data layer so that it is easily
[00:27:54] accessible and the like. So the four um
[00:27:59] practices that they highlight are also
[00:28:01] pretty important. Um, Ankash, where were
[00:28:04] you?
[00:28:06] >> Uh, essential Luda.
[00:28:08] >> All right. All right. Let's put it as I
[00:28:11] asked everybody, right? Yes. Um, great.
[00:28:14] So, let's put it as essential. And, um,
[00:28:18] that is the last one. Any announcements,
[00:28:21] Chris, what's happening on your on in
[00:28:24] your life over there?
[00:28:25] >> Well, uh, building a lot of AI agents.
[00:28:28] Uh the interesting thing that I started
[00:28:30] working on this week was I I let my
[00:28:33] agents uh system read an encyclical uh
[00:28:36] that just got released on AI agents and
[00:28:39] it was really interesting. It started
[00:28:41] talking about the language of war and a
[00:28:44] lot of this AI agent system that I was
[00:28:47] building um some of it builds itself or
[00:28:50] names itself and there was a lot of
[00:28:51] grammar in some of my build that this
[00:28:54] encyclical uh advised me against. Do you
[00:28:57] need a war room or should that be named
[00:28:59] something else when you're managing your
[00:29:01] your agents? So ju just some really
[00:29:03] interesting things also um about
[00:29:07] deference is in the encyclical and my AI
[00:29:10] didn't really defer sometimes. Sometimes
[00:29:12] it tried to solve and solve and solve
[00:29:14] when sometimes it could just wait or be
[00:29:16] silent and there there's probably some
[00:29:18] importance there. So really interesting.
[00:29:20] we're in a world of coding and there's
[00:29:22] so many other institutional players that
[00:29:25] have been around for centuries um that
[00:29:28] are going to start stepping in and
[00:29:29] giving direction. So um this AI
[00:29:31] responsibility I think is going to start
[00:29:33] really becoming part of our um our
[00:29:36] builds and our sort of constitution like
[00:29:38] how are these AI agents built? So, um
[00:29:41] it's it's really a unique time I think
[00:29:43] in humanity um that we're building
[00:29:45] something with so much power and um what
[00:29:49] does it mean, you know? So, that that's
[00:29:51] what I'm working on this week.
[00:29:53] >> Great. Thank you, Chris. Uh John, uh
[00:29:56] announcement of the learning lab.
[00:29:57] >> Yeah, we have a Alden Rosario um is
[00:30:01] going to give a learning lab on June
[00:30:03] 1st, Monday night, 700 pm to 8:00 p.m.
[00:30:06] Eastern. We're going to talk about um
[00:30:09] basically how he's building what I think
[00:30:11] of as a cognitively capable
[00:30:12] organization, right? He's building a new
[00:30:14] age organization. It's a combination of
[00:30:16] people and machines. He's going to tell
[00:30:18] us what he does and how he does it.
[00:30:20] >> Yeah. And and a reminder that if you're
[00:30:22] in Boston, there are 600 events spread
[00:30:25] over a couple of days. Uh today is the
[00:30:28] second day. Um Women Applying AI is
[00:30:31] running an event at six o'clock uh with
[00:30:33] authors and robot dog. So come over,
[00:30:36] check us out. And I want to end with
[00:30:40] Deepak's quote. The future isn't
[00:30:42] building smarter agents. It's rebuilding
[00:30:45] everything agents plug into. That's an
[00:30:48] interesting
[00:30:48] >> well said. Yeah.
[00:30:49] >> Observation. Well said, Debug. Put it as
[00:30:52] a quote on your LinkedIn or something.
[00:30:54] All right. Um,
[00:30:57] thank you. Thank you all very much. And
[00:30:59] as a um today we had one two essentials
[00:31:04] um two importance and two optionals. A
[00:31:06] very balanced day. Thank you everyone
[00:31:09] for listening. Thank you Chris for
[00:31:11] joining. Thank you Adam for joining.
[00:31:13] We'll see you more of you in the coming
[00:31:15] days and we'll see you tomorrow.
[00:31:22] [music]
