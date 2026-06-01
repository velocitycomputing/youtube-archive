---
video_id: z3pbrFKVyQE
title: The Infrastructure Nightmare Nobody Is Talking About
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=z3pbrFKVyQE"
watched_date: 2026-05-25
watched_at: "2026-05-25T12:00:00Z"
watch_count: 1
duration_seconds: 2796
source: youtube-history-browser
history_label: May 25
history_order: 143
watched_at_precision: date-from-history-label
watched_percent: 23
estimated_watched_seconds: 643
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

# Summary: The Infrastructure Nightmare Nobody Is Talking About

**What was discussed:**
Emma, who leads OpenAI's data platform infrastructure engineering, explained how AI agents and autonomous coding tools (like Codex) are accelerating software development at dramatically uneven rates. While app teams can now rapidly generate features with minimal risk, infrastructure and platform teams face a critical problem: they must maintain near-perfect reliability because failures cascade across thousands of dependent systems. This creates a dangerous disparity—app teams can "vibe code" with agent assistance, but platform teams still need extensive guardrails, manual code review, and operational safeguards. OpenAI is addressing this by building autonomous code review systems with specialized knowledge bases, multi-agent architectures where separate agents review generated code, and operational automation to catch broken workloads before they impact production. The core challenge is that infrastructure teams require access to dozens of interconnected systems (logging, monitoring, Kubernetes, quota managers) simultaneously to understand and fix problems safely, making autonomous operations far more complex than app-level development.

**What's actionable for the user:**
If you work on a platform or infrastructure team, recognize that agent acceleration will outpace your ability to safely deploy changes—this requires deliberate investment in automated code review harnesses and operational safeguards before your organization faces production incidents. Build communication patterns between human teams and agents (like specialized Slack bots and code review agents) rather than hoping humans will review agent-generated code. Plan for autonomous operations by setting up isolated testing environments first, then gradually expand agent authority as trust increases. Finally, flag to leadership if your organization shows a power-law divide between fast-moving app teams and slower platform teams—this imbalance is unsustainable and requires platform investment to match the new AI-driven scaling laws at every layer.

## Transcript

[00:00:00] I would love to hear from you like you
[00:00:02] know tell me about Emma. Tell me about
[00:00:03] how you're here at OpenAI, what you're
[00:00:05] doing etc.
[00:00:05] >> So my name is Emma. I joined OpenAI back
[00:00:07] in 2023 to lead um the data platform
[00:00:10] infrastructure engineering group here.
[00:00:12] >> Um so what we do is anything that
[00:00:15] involves data systems, the guts and
[00:00:18] bowels of creating any product or any
[00:00:20] research system or etc. There's a lot of
[00:00:22] data systems that underly it. So my
[00:00:25] group actually take cares of all of
[00:00:27] that. So whether it's big data so if you
[00:00:29] want to do analytics you want to crunch
[00:00:30] some data um or if it's like streaming
[00:00:34] like you know streaming processing or
[00:00:36] like event buses or if it's ML infra
[00:00:38] like you want to do some ranking
[00:00:40] algorithm etc like feature stores um or
[00:00:43] if it's and then we get to even like
[00:00:45] higher level abstractions which builds
[00:00:46] on top of this which is like piping data
[00:00:48] from one system to another making sure
[00:00:50] that's done securely in a scalable way
[00:00:53] um as well as something unique to open
[00:00:54] eye which is like preparing training
[00:00:56] data um and eval data and making sure
[00:00:59] the systems can sustain kind of that
[00:01:00] kind of load. So that's all on data
[00:01:02] platform. Um so we're we're very low
[00:01:04] level as a team like product team sits
[00:01:07] on top of us, research team sits on top
[00:01:08] of us, we really serve every team in the
[00:01:10] company. Um whether it's like go to
[00:01:13] market, you know, trying to sell
[00:01:15] customers, understanding what customers
[00:01:16] are doing or finance trying to close the
[00:01:18] books or like doing M&A deals to
[00:01:20] understand what's going on. um or even
[00:01:22] HR um you know but also like you know
[00:01:26] for the business itself right building
[00:01:27] the product like personalization is a
[00:01:29] feature that is very much reliant on
[00:01:32] data to crunch the um the information
[00:01:34] used for memory um really every product
[00:01:37] touches us in some way whether you're
[00:01:39] logging into OpenAI or API um or
[00:01:41] integrity it's all plugging into data
[00:01:44] systems underneath
[00:01:46] >> so I I I guess maybe the first question
[00:01:49] I would have is How has that world, how
[00:01:52] has your job, how has the team's role
[00:01:55] shifted maybe in the last year, maybe in
[00:01:57] the last six months, last three months,
[00:01:59] things keep moving really quickly. And
[00:02:00] I'm curious how you feel like things
[00:02:02] have evolved for you and the team
[00:02:04] >> just as you see the models get better
[00:02:07] and sort of how that's impacted the data
[00:02:09] layer.
[00:02:09] >> It's all very new for us too. I would
[00:02:11] say a year ago it wasn't that different
[00:02:13] from you know artisal software
[00:02:16] engineering of the of the Y. Um but
[00:02:18] really in the last six months or so
[00:02:20] things really started accelerating. I
[00:02:21] think Codeex got a lot better. Um the
[00:02:23] models are also like getting much better
[00:02:26] m like very very fast. Um so we're
[00:02:29] seeing like really rapid changes in the
[00:02:31] last six months and I don't think this
[00:02:32] is the end of it. It's it's very much
[00:02:34] the beginning and I think we're going to
[00:02:35] see even bigger changes coming up very
[00:02:37] soon um that I don't know if anybody has
[00:02:39] a clear idea what's going to look like
[00:02:41] in six months. Um but in terms of on the
[00:02:44] platform teams like ours um we we we
[00:02:48] kind of see what's happening in terms of
[00:02:49] accelerating our own work which is the
[00:02:51] exciting part. We're also seeing how how
[00:02:54] much it's accelerating everybody else
[00:02:55] around us which
[00:02:57] >> um if if like different parts of the
[00:03:01] organism are growing at different rates
[00:03:03] then you can imagine that there may be
[00:03:05] like actual problems that are caused by
[00:03:07] um using a lot of agents and autonomous
[00:03:09] like coding tools.
[00:03:11] So
[00:03:12] >> yeah, that makes a ton of sense.
[00:03:15] >> Yeah, I I can dig into this as well. Um
[00:03:18] but uh in terms of just on the on the
[00:03:21] data infrastructure front in terms of
[00:03:23] how we're accelerating things um we're
[00:03:26] using codecs as well as like agentic
[00:03:28] tooling for things that are just like uh
[00:03:31] we didn't really imagine that we can use
[00:03:33] like agents therapy for for example our
[00:03:35] release process. Um so but okay so I'll
[00:03:38] back up a little bit. So we have a lot
[00:03:40] of um uh basically proprietary uh oss
[00:03:43] software that we use and we basically
[00:03:45] patch those um like underlying software
[00:03:48] uh pieces up um every so often and then
[00:03:50] we release that and then we use that in
[00:03:52] our systems right so we have our own
[00:03:54] release process for these underlying
[00:03:55] components um and it's a very manual
[00:03:58] process to test validate um make sure
[00:04:01] like run all the like you know cases
[00:04:03] through and then to promote it to like
[00:04:06] the next stage let's say from staging to
[00:04:08] um canaries and then from canaries to
[00:04:10] like prod right and then we have a lot
[00:04:12] of different packages like this you know
[00:04:14] dozens so every time we need to do a
[00:04:16] release process it's very manual people
[00:04:18] have to like watch the jobs like it's
[00:04:20] couple hours sometimes days and then you
[00:04:22] have to remember to like check all the
[00:04:23] results and promote it so now that's all
[00:04:25] controlled by the agent the release
[00:04:26] process is the agent itself it does
[00:04:28] everything um that I mentioned
[00:04:30] autonomously it will ping you know us in
[00:04:33] Slack to let us know what the status of
[00:04:34] things are if something is is broken it
[00:04:37] will also like try to do its own triage
[00:04:38] and give suggestions on what's going on.
[00:04:41] So, we're completely hands-off. That's
[00:04:43] like hours of time that people are
[00:04:44] spending like every day. Um, and it's
[00:04:47] done a fantastic job, probably better
[00:04:48] than humans can. Uh, so that's one area.
[00:04:52] Another area is like, um, we've been
[00:04:54] using a lot more um, we've been just
[00:04:56] capturing like the the knowledge, the
[00:04:58] specialized knowledge that we have as
[00:04:59] infra teams into more skills um, and
[00:05:03] more kind of like capture in the agent
[00:05:05] itself. Um so that users can take
[00:05:07] advantage of that, right? So um so
[00:05:11] before there's just like we need to
[00:05:12] build a lot of guard rails to like oh
[00:05:14] you you know user can do this wrong and
[00:05:16] then it'll end up being like a really
[00:05:18] long running job it'll break. But now we
[00:05:19] can encode that in skills. So then when
[00:05:21] users are using that it actually is like
[00:05:23] extremely smart about what to do and how
[00:05:25] to um debug. A recent um kind of example
[00:05:29] is
[00:05:30] um we launched a skill for users to help
[00:05:33] export data for training purposes.
[00:05:35] >> So that used to be a very manual
[00:05:37] process. It's going to take hours.
[00:05:38] There's a lot of sharp edges in terms of
[00:05:40] what could go wrong. And um with the new
[00:05:44] kind of like codeex assisted like um you
[00:05:47] know skills kind of way of doing things
[00:05:49] uh the user launched this job and then
[00:05:51] just went to sleep and then the agent
[00:05:54] was running in the background. it
[00:05:55] actually found some issues. It got
[00:05:57] blocked. Um, and then normally if you
[00:05:59] know if a person's blocked, you have to
[00:06:00] ping us and find out what's going on.
[00:06:02] The agent was actually able to go into
[00:06:05] the internal systems itself because it's
[00:06:08] all one big codebase and figure out what
[00:06:10] might be wrong there. So, it went into
[00:06:11] like four or five different internal
[00:06:12] systems and check the code there and be
[00:06:14] like, hey, why is this why is this
[00:06:15] breaking in this way? Um, and then it
[00:06:18] also pinged us in our support channel,
[00:06:19] but this was midnight, so we didn't see
[00:06:20] it. Um, and then and then it went and
[00:06:23] actually like three layers deep, it
[00:06:25] found like this tiny bug that existed
[00:06:27] three layers deep, it went and somehow
[00:06:30] patched it and fixed it. Um, and
[00:06:33] basically worked around it in a way that
[00:06:35] the job could continue. So by the time a
[00:06:37] user woke up in the morning, it was
[00:06:38] completely done.
[00:06:40] >> Like no conversations needed to be had.
[00:06:42] Um, so that's kind of where we're at
[00:06:44] right now. Um, I can give you more
[00:06:46] examples on how we're using like kind of
[00:06:47] agents, but there's like more kind of I
[00:06:49] think more like kind of vanilla cases
[00:06:51] like I think everybody's using it this
[00:06:52] way in that we have some like um kind of
[00:06:56] uh data tooling um that we launch for
[00:06:59] all users. So kind of think about um
[00:07:02] autonomous dashboarding, autonomous
[00:07:03] notebooking, you know, uh and in order
[00:07:06] to make that really good um we take a
[00:07:09] lot of user feedback and they will just
[00:07:10] like put in Slack is like I want this
[00:07:12] feature, I want this feature. So we
[00:07:14] basically have the agent drive this. We
[00:07:15] have Codex go pick things up um and
[00:07:19] really try to do it on its own. And we
[00:07:21] have created tooling so that Codex can
[00:07:22] plug into like the full cycle like it
[00:07:25] can it can it supports browser use for
[00:07:27] example, right? It can load the whole
[00:07:28] DOM. It can figure out like it can do
[00:07:30] the clicks and figure out what's going
[00:07:32] on and it can validate its own behavior
[00:07:34] and its own um uh kind of like fixes and
[00:07:37] so it can do the full loop. So
[00:07:39] essentially uh for many tickets not all
[00:07:41] I would say it's not like quite
[00:07:43] completely there yet for many tickets it
[00:07:45] takes like a user like a comment and
[00:07:47] some description and then codeex will
[00:07:49] just execute on full stack full loop and
[00:07:51] then it'll come back with a PR with all
[00:07:54] the the proof of how it fix it with a
[00:07:55] video and everything.
[00:07:56] >> Wow.
[00:07:57] >> Um and then yeah so it's it's really
[00:07:59] accelerated a lot of parts of
[00:08:01] engineering for us. Um, and then I'll
[00:08:04] talk about the other piece that I
[00:08:05] mentioned earlier, which is like, okay,
[00:08:06] what if the acceleration is uneven? And
[00:08:09] I I think I'm seeing this a little bit
[00:08:11] right now. I think it'll even out longer
[00:08:14] term, but right now, this is what we're
[00:08:15] seeing is that if you are on a team
[00:08:18] where um the surface area or um
[00:08:24] like basically the spread of um the
[00:08:26] damage if something breaks is like a
[00:08:28] little bit more limited. Let's say you
[00:08:30] have a like you're you're still building
[00:08:31] like um like a project that um hasn't
[00:08:34] been launched in production yet. You're
[00:08:35] iterating on it or it's like um you know
[00:08:37] only launched alpha customers. You're
[00:08:39] iterating around very very fast. So if
[00:08:40] you think about like a lot of these kind
[00:08:42] of teams, they can go very very fast.
[00:08:44] They can vibe code completely, right?
[00:08:46] Like codecs can just like turn out like
[00:08:48] features by features. But if you're on a
[00:08:50] very like like a like a like um like a
[00:08:53] root level team um like an
[00:08:54] infrastructure team where if I change
[00:08:56] one thing it will like basically affect
[00:08:57] like thousands of different teams um
[00:09:01] it's harder to go uh just complete by
[00:09:03] coding. We still have to have a lot of
[00:09:04] guardrails in place. we still have to do
[00:09:06] a lot of manual checking to make sure
[00:09:07] that like it doesn't you know affect
[00:09:09] things um in a way that will like you
[00:09:12] know harm a lot of users and um uh and
[00:09:16] so so like I don't think the model is
[00:09:19] like quite I think it's going to get
[00:09:20] there but it's not quite there yet in
[00:09:22] terms of creating like a 100% oneshot it
[00:09:25] like perfect code so we have to iterate
[00:09:27] on it a lot more so you can imagine is
[00:09:29] like a lot of users who are sitting on
[00:09:30] top of our platform are vibe coding like
[00:09:33] all these new applications and things um
[00:09:36] and then they land on our platform which
[00:09:38] we're in charge of running, right? If
[00:09:39] you imagine like a Spark job or like a
[00:09:42] Flink workload um
[00:09:44] >> if they break often times we we we will
[00:09:47] check with the user and the user
[00:09:48] probably like has less of a clue of
[00:09:50] what's going on because it's codeex
[00:09:51] generated. We've had instances in the
[00:09:52] past where like users are like I don't
[00:09:54] even know what Flink is. I don't really
[00:09:55] know how how to use it. Um but you know
[00:09:59] but it's it was working I thought you
[00:10:01] know so I can't really help you. you
[00:10:03] guys should figure out like what's
[00:10:04] broken and fix it. So there's almost
[00:10:06] like a transfer of responsibility and
[00:10:09] load onto a lot of these platform teams
[00:10:11] who are running the code. There's more
[00:10:12] code, right? There's a lot more code is
[00:10:14] being created really fast and the teams
[00:10:16] are responsible for ultimately running
[00:10:18] it successfully and making sure that
[00:10:19] it's not breaking. Um they're inheriting
[00:10:22] a lot of the the burden. So so what are
[00:10:24] we doing for that? So um at open we're
[00:10:27] also thinking about how you know we
[00:10:29] don't have a good term for it. So, so
[00:10:31] you know, sorry for I'm using my own
[00:10:32] terminology, but it's like almost like a
[00:10:34] defense in-depth kind of um kind of
[00:10:37] strategy where it's like, okay, on the
[00:10:39] code review side, um this is kind of the
[00:10:42] interface that we have right now. We
[00:10:44] will evolve from here, but how do we
[00:10:46] make autonomous agentic code reviews
[00:10:48] happen for each team? So, it captures
[00:10:51] our specialized knowledge to make sure
[00:10:52] bad things don't happen.
[00:10:54] >> Right now, we still have to spend a lot
[00:10:55] of manual effort looking at code and
[00:10:57] inspecting it. Yes, we're using codec to
[00:10:58] inspect it, but it's in order for things
[00:11:01] to to really be tied down, we we really
[00:11:03] still need to do that. How do we encode
[00:11:05] all of that knowledge and knowhow and
[00:11:07] all of our runbooks and all the past
[00:11:09] incidents and all of that and have this
[00:11:11] agent kind of do that work for us? Um, I
[00:11:14] think some people, again, it's an
[00:11:15] unsolved problem. These are all unsolved
[00:11:17] problems. Some people are like, okay,
[00:11:18] why can't we encode that in like agent
[00:11:20] MD files and like the the the agent
[00:11:22] that's writing the code itself, right?
[00:11:24] Why doesn't it just know to do the right
[00:11:26] thing? Um it's it's an open question but
[00:11:29] in my perspective I do think the
[00:11:31] incentives will always be somewhat
[00:11:32] misaligned. That's why we have you know
[00:11:34] people who write code and people who
[00:11:35] review code and they're separate people.
[00:11:37] You know I I think it'll be it'll be
[00:11:39] hard for the model to like juggle those
[00:11:40] two things uh consistently. I think
[00:11:42] there should be a multi- aent
[00:11:43] architecture for for this kind of thing.
[00:11:45] Um and where a separate agent will will
[00:11:48] look at the code and review the code and
[00:11:50] um kind of like you know it's kind of
[00:11:52] like a code owners like plus+ situation
[00:11:54] where it's like if this code touches
[00:11:56] like different teams then the different
[00:11:57] teams different agents will come in and
[00:11:59] review the code and make sure that it's
[00:12:01] like you know tiptop according to that
[00:12:03] team's like specifications. Um but then
[00:12:06] also every other layer on the infra
[00:12:08] operations layer as well. How can we
[00:12:10] make that autonomous right? If we if we
[00:12:12] find like a bad workload, how can we
[00:12:14] sequester that a lot faster in an
[00:12:16] autonomous way where it doesn't have to
[00:12:17] like page us? Um we've also see
[00:12:20] incidents where like a user again um you
[00:12:22] know would can can by code something
[00:12:24] that um they really didn't intend to.
[00:12:26] they like flip um feature flag from like
[00:12:29] uh you know like uh that that they
[00:12:31] didn't mean to turn on and it just took
[00:12:33] took the entire cafa cluster down you
[00:12:35] know those kinds of things like how can
[00:12:36] we build systems that can very quickly
[00:12:39] capture these kinds of erroneous usages
[00:12:42] and and and do something about it
[00:12:44] because I don't think the world is force
[00:12:46] users to write manual code or like
[00:12:49] review their code completely manually
[00:12:51] understand every single thing I don't
[00:12:52] think that's where we're going we're
[00:12:53] going to like full autonomous mode where
[00:12:54] it's like code produced producers and
[00:12:56] code reviewers and code deployers and
[00:12:58] code um and also like just people
[00:13:00] running the systems. It's all
[00:13:01] autonomous. It's all agents um every
[00:13:04] layer. How do we get there um safely?
[00:13:07] And so I think the models are getting
[00:13:09] really good. So I think we'll get there
[00:13:10] pretty fast. So it's a very exciting
[00:13:12] world we're we're in right now. Um yeah,
[00:13:14] I'll stop there.
[00:13:16] >> No, there's there's a lot to dig into
[00:13:18] there. Um I could pick at probably any
[00:13:20] number of half a dozen threads. One of
[00:13:22] the ones that I think popped out for me
[00:13:24] is you talk a lot about sort of framing
[00:13:28] your world in terms of the kinds of
[00:13:30] autonomous problems that are solvable at
[00:13:33] the platform team layer versus the kinds
[00:13:36] of autonomous problems that you know
[00:13:37] teams that sit on top app teams might
[00:13:39] might engage with. And maybe we can dig
[00:13:42] into that a little bit because I think
[00:13:43] that you have a really great point that
[00:13:44] I've seen chatting with other companies
[00:13:47] as well where they feel like there's
[00:13:48] this huge separation and difference
[00:13:51] between what the front-end app teams can
[00:13:53] go after with perhaps less less need to
[00:13:57] be completely correct on code versus
[00:13:59] where platform teams have to be near
[00:14:01] 100% correct and need to insist on
[00:14:04] holding that standard even as they're
[00:14:05] supposed to speed up. And so maybe if
[00:14:08] you can dig into a little bit more like
[00:14:10] what are what are the pieces of this
[00:14:12] where you feel like we have a handle as
[00:14:14] a platform team on where autonomous
[00:14:16] agents are at now uh and then maybe we
[00:14:18] have line of sight to some problems that
[00:14:20] we think are linearly solvable uh for
[00:14:22] platform teams and then from there maybe
[00:14:25] we can blue sky a little bit and and I
[00:14:26] can hear a little bit about how you're
[00:14:27] thinking about sort of the longer run
[00:14:29] and I and by the way I fully realize
[00:14:31] agents are going so fast the longer run
[00:14:33] is probably like six months or something
[00:14:34] like this is the world we live in but I'
[00:14:36] I'd love to hear your perspective.
[00:14:39] >> Yeah, I mean it's a really tough
[00:14:41] question because it's so open-ended
[00:14:43] right now and nobody knows exactly what
[00:14:45] to do. Um I can tell you what our
[00:14:48] thoughts are. Um and uh all of these
[00:14:51] things are are more conjectures right
[00:14:52] now than things are like um you know
[00:14:55] close to completion. Um, but I I really
[00:14:58] do think we need a better at least, you
[00:15:01] know, as as one of the first things that
[00:15:03] we should do is um a a better like code
[00:15:07] review harness almost where it can also
[00:15:09] plug into different tool calls and also
[00:15:13] um plug into different knowledge bases
[00:15:15] so that it can perform autonomously what
[00:15:18] a human right now needs to do.
[00:15:20] uh we we have like a a code review bot
[00:15:23] but it's not um kind of specialized and
[00:15:27] I think it needs to be specialized
[00:15:28] because you know there's just so much
[00:15:30] vast human knowledge that goes into a
[00:15:32] code review that's not captured by like
[00:15:34] a generic agent that just has access to
[00:15:36] like monor repo um or even like the
[00:15:38] tools uh yeah so I think iterating on
[00:15:42] kind of a framework for that will be
[00:15:43] really important and that's something
[00:15:45] we're looking into as well um but I
[00:15:50] Uh yeah the like to to your question is
[00:15:54] like what is the difference in this
[00:15:55] world between like you know these teams
[00:15:57] are like you know maybe building
[00:15:58] frontends and you know apps that are
[00:16:00] running on platforms and the platforms
[00:16:02] itself. Uh
[00:16:05] yeah I I think until we solve this
[00:16:07] problem the disparity will get very
[00:16:08] great. That's the thing with AI is it's
[00:16:11] very much power law dynamics and we're
[00:16:13] seeing this you know in the industry as
[00:16:14] well like people who are accelerating
[00:16:16] with HI AI can go much much faster than
[00:16:19] um teams without and so even within
[00:16:22] companies that dynamic needs to be
[00:16:24] noticed and dealt with or else it gets
[00:16:26] um it can really harm a company's like
[00:16:29] you know uh ability to like you know uh
[00:16:32] just run its business. Um,
[00:16:35] so I guess I'm sorry like I don't have
[00:16:37] like really great answers to be like,
[00:16:39] "Oh, this is what we should do to like
[00:16:40] solve it." Um, but I do think it's
[00:16:43] something that we should pay attention
[00:16:44] to um, and invest in. So on on our end,
[00:16:47] we're investing in these harnesses.
[00:16:49] We're investing in like autonomous like
[00:16:50] operations underneath. But I think there
[00:16:53] may be even more of a fundamental shift
[00:16:55] in how things get operated. I can
[00:16:57] imagine because of power dynamics um
[00:17:01] that like a lot of like um uh
[00:17:05] like you know higher layers you know
[00:17:08] higher layer abstractions teams on top
[00:17:10] will just be like um extremely agentic
[00:17:14] whereas the the platform layers um
[00:17:17] increasingly need to like uh like
[00:17:20] support more and more load and therefore
[00:17:22] it needs to like temporarily grow as
[00:17:25] well in order to build a systems to
[00:17:27] catch up and once it catches up then we
[00:17:29] can grow like together. Um but right now
[00:17:32] it's almost the scaling laws of the
[00:17:34] upper layers are like AI scaling laws
[00:17:36] and the lower layers are human scaling
[00:17:38] laws and that's not sustainable. So how
[00:17:40] do we get the lower layers to be into in
[00:17:42] get into the AI scaling laws as well? We
[00:17:44] need to build those platforms and I
[00:17:46] think we I think we're super focused on
[00:17:48] like code creation and feature creation
[00:17:51] and not about operations and running
[00:17:53] right now. And I think that's the next
[00:17:55] le lever that we need to pull and I
[00:17:57] think we're we're working on that right
[00:17:58] now. So hopefully in another three
[00:17:59] months we'll have a better answer for
[00:18:00] you.
[00:18:02] >> No. Well, I mean we can always come back
[00:18:03] and we we can chat some more. Um you
[00:18:06] know, another thread maybe that I'd pull
[00:18:07] at uh you mentioned sort of the whole
[00:18:10] concept of someone sort of typing in
[00:18:12] Slack something they'd like to see and
[00:18:13] the agent picking it up and running with
[00:18:14] it. It got me thinking a little bit
[00:18:17] about different pathways that uh agents
[00:18:21] unlock for communication between teams
[00:18:24] and orgs.
[00:18:25] >> Uh so like if we're talking about
[00:18:26] communicating between teams and orgs,
[00:18:28] I'm thinking yes, Slack is one where the
[00:18:30] agents and the humans are together. But
[00:18:31] if you think a little bit more
[00:18:32] creatively, arguably like distributing a
[00:18:35] plug-in for codeex would also be a form
[00:18:37] of communication. And you talked about
[00:18:38] that as well. You're trying to give app
[00:18:40] teams essentially your brain, your
[00:18:43] ability to understand how their proposed
[00:18:46] data pull is actually going to work with
[00:18:48] your platform and review that code
[00:18:50] before they decide to set it up and
[00:18:52] stand it up on their own. Do it. It's
[00:18:55] sort of playing with that abstraction a
[00:18:56] little bit. We can be very creative
[00:18:57] about how how far we want to take that
[00:18:59] thread. How have you seen um agent
[00:19:03] communication patterns shifting how
[00:19:06] teams work across that platform app team
[00:19:08] boundary?
[00:19:13] >> Yeah, this is a very good question as
[00:19:14] well. There's so many layers to all of
[00:19:17] these. Um I'll talk about like maybe the
[00:19:18] surface layer which is like people are
[00:19:20] increasingly using agents to like
[00:19:22] communicate with others like via Slack.
[00:19:24] There's a lot of generated messages at
[00:19:26] this point, right? um they they look
[00:19:28] like they come from humans, but if you
[00:19:29] read it, it's very obviously agent
[00:19:30] generated. They tend to be very verbose.
[00:19:33] Um so so for folks reading it, it it
[00:19:35] takes a long time and sometimes it's a
[00:19:37] little bit even harder to like get to
[00:19:39] the point where it's like, you know,
[00:19:40] it's too diplomatic or too wrapped up.
[00:19:43] Um
[00:19:44] and then so what people are doing is
[00:19:46] they're digesting this with their codecs
[00:19:48] as well. So it's like codeex, right? And
[00:19:50] then codeex redistill it back to human
[00:19:52] language for me. What is the point here?
[00:19:54] Um, we're seeing a little bit of that
[00:19:56] and I think that's actually like not a
[00:19:58] bad thing. Um,
[00:20:00] >> uh, you know,
[00:20:02] every time we chat with Codex, every
[00:20:04] time you give Codex anything, it it it,
[00:20:06] you know, like it it basically builds a
[00:20:07] hive brain even even even better. So
[00:20:09] like the fact that we're mediating
[00:20:11] through CEX is not a it's not a bad
[00:20:12] thing. It'll it'll help us in the future
[00:20:14] as it accumulates more of this
[00:20:15] knowledge. Um, but you can imagine as a
[00:20:18] human in the middle, you know, it
[00:20:20] sometimes is jarring to see Slack become
[00:20:22] like a little bit like, you know, filled
[00:20:24] with like agent communication. Um, so I
[00:20:28] think there's there's a little bit of
[00:20:29] like, you know, sense of like, oh,
[00:20:30] things are really changing, but also
[00:20:32] like excitement that, you know, we can
[00:20:34] do this.
[00:20:36] Um, another layer is, uh, you know, like
[00:20:40] increasingly as we kind of launch more
[00:20:43] kind of capabilities, um, as a platform
[00:20:45] team or as any team like surfacing with
[00:20:48] users, uh, we're we're trying to get to
[00:20:51] a point where our agents are good enough
[00:20:53] that it can handle a lot of the user
[00:20:55] communications, right? So, we actually
[00:20:56] launched this um this kind of support
[00:20:59] Slack support bot. uh the initial
[00:21:02] iterations were not that good but now
[00:21:04] the models have gone very very good and
[00:21:06] we can leverage codeex um the support is
[00:21:09] actually getting a lot better so um it's
[00:21:11] actually able to answer a lot of really
[00:21:13] great like hard questions very
[00:21:15] intelligently um and previously you know
[00:21:19] what I mentioned before is kind of like
[00:21:20] what users feel as well previously when
[00:21:22] users see an automated response they
[00:21:24] instinctively it's like I don't even
[00:21:25] want to read this it's super long you
[00:21:27] know like I just want a human to answer
[00:21:28] my question but because of quality
[00:21:30] answers have gone so much better. Um,
[00:21:33] and because it has tool use and all of
[00:21:35] this as well, it's not just like
[00:21:36] searching through like a dead Slack
[00:21:38] corpus. Um, we see that interaction
[00:21:40] pattern changing as well. It's like
[00:21:42] people are more open-minded about like,
[00:21:43] oh, this is a generated Slack response.
[00:21:46] It but it could be very helpful. So, I
[00:21:48] see people reading it a little bit more.
[00:21:49] So, it's shifting the other direction as
[00:21:51] well. Um, as the models get really
[00:21:53] really good, I can imagine like these
[00:21:55] are all solvable problems by by you know
[00:21:57] with with model capabilities, right?
[00:21:58] like whether it's super long and looks
[00:22:00] super like informal and like too much
[00:22:01] detail like that's also solvable. Um
[00:22:04] including like you know how do you like
[00:22:05] answer questions better that's also
[00:22:07] solvable. So I can see the future where
[00:22:10] >> it right now in my perception I think
[00:22:12] the co uh you know the agent can do like
[00:22:15] sometimes as good of a job but on the
[00:22:17] most part like maybe less than average
[00:22:18] than a human does in terms of
[00:22:20] communication but I can see very quickly
[00:22:22] that can change. It could be super
[00:22:23] human. It gets to the point super fast.
[00:22:25] It's also like very good at like
[00:22:27] understanding how humans perceive and
[00:22:29] understand information to make it like
[00:22:30] super condensed and and and and context
[00:22:33] aware. So if I'm in this channel talking
[00:22:35] about these kind of people, I will use
[00:22:37] this type of language. If they're in for
[00:22:38] people, I should talk about this, you
[00:22:41] know, like you know, really like gain
[00:22:42] the psychology even. Um and you know,
[00:22:46] other teams will have their agents that
[00:22:47] that could do the same as well. I can
[00:22:48] see that happening very quickly, but
[00:22:50] we're not quite there yet.
[00:22:52] >> Yep. Yep. That makes sense. Um maybe we
[00:22:54] could play with like one one of the
[00:22:56] things that's been underneath the
[00:22:57] conversation so far for me has been
[00:23:00] thinking about how on a platform team on
[00:23:02] the infrastructure side of things you
[00:23:05] have a different at least a potentially
[00:23:08] different set of primitives that you're
[00:23:10] working with that you're giving to
[00:23:11] agents to address and to deal with and I
[00:23:14] feel like when you talk about the need
[00:23:16] to have agents scale into the infra
[00:23:18] layer scale into the platform layer
[00:23:20] appropriately it feels like part of the
[00:23:22] conversation is basically ensuring they
[00:23:24] can work with the right primitives that
[00:23:26] scale for you versus primitives that
[00:23:28] scale at the app layer. It's it's
[00:23:30] perhaps it's an open-ended question,
[00:23:32] right? You can come back and say, "No,
[00:23:33] no, no. I think the primitives are the
[00:23:35] same." But like I wonder if you would
[00:23:36] say that. I wonder if you would say no,
[00:23:37] we have some different primitives that
[00:23:38] we want agent primitives.
[00:23:41] >> Um
[00:23:42] I I'll just like give some examples like
[00:23:45] and maybe I'm like being simplistic
[00:23:46] about like you know um a lot of other
[00:23:48] areas as well, but let's say you're
[00:23:50] you're building a front-end app, right?
[00:23:51] like you need the codebase. Um you need
[00:23:55] like a browser,
[00:23:56] you need to be able to like control the
[00:23:59] browser and whatever to test things and
[00:24:01] if you have a backend you need like you
[00:24:03] know a live service and and being able
[00:24:04] to spin that up and connect to that,
[00:24:06] right? Um but for the most part you can
[00:24:08] probably just like um use like you know
[00:24:10] like fake data or whatever uh to to stub
[00:24:13] data to to kind of test it. But if you
[00:24:16] are like supporting let's say um a spark
[00:24:19] cluster for example you know few
[00:24:22] thousand nodes and we have like you know
[00:24:24] dozens of clusters across different
[00:24:25] regions and let's say the cluster is
[00:24:28] having issues right
[00:24:29] >> the agent needs to connect to so many
[00:24:31] different tools in order to understand
[00:24:33] what's going on
[00:24:34] >> it needs to connect to like the logging
[00:24:36] the observability needs to connect to
[00:24:37] like kubernetes it needs to understand
[00:24:38] the pod it needs to control like all
[00:24:40] these things um there's you know with
[00:24:43] with a spark cluster it's not just like
[00:24:45] one service is connected to like dozens
[00:24:46] of other services. There's like the
[00:24:48] shuffle service. There's also like you
[00:24:50] know our um our our cluster routing
[00:24:52] service and there's the quota management
[00:24:54] service. So you have to connect all of
[00:24:56] those to understand those two in a live
[00:24:58] setting. It's not code right. It's not
[00:25:00] it's code yes but it's not it's it's
[00:25:02] live code running on a platform. I need
[00:25:03] to figure out very very different
[00:25:06] systems plug into all of them understand
[00:25:08] what's going on put the picture
[00:25:09] together. So just in terms of number of
[00:25:11] connectors,
[00:25:12] >> the capability that you need to have to
[00:25:14] delve into all of these different areas
[00:25:16] and also to do live operations in a way
[00:25:18] that's secure. You can't just like try
[00:25:21] different things. Oh, let's try this,
[00:25:22] you know, see see if that like solves
[00:25:24] it. It just probably break everything
[00:25:25] down.
[00:25:25] >> Doesn't go well.
[00:25:26] >> It doesn't go well. Exactly. So this is
[00:25:29] where I feel like the capabilities and
[00:25:30] the primitives will be different from
[00:25:33] >> you know um you know a lot of things but
[00:25:36] you know it's getting there. Again, the
[00:25:37] models are getting very very good, very
[00:25:39] very smart. We just need to apply them
[00:25:41] in these settings more and more um to
[00:25:43] test them out. So, it's like a little
[00:25:45] bit of chicken egg problem, which we're
[00:25:46] we're solving currently right now, which
[00:25:48] is like, you know, we don't trust it
[00:25:49] enough to do a lot of live operations
[00:25:51] and therefore like it's hard to get a
[00:25:53] lot better at it. So, therefore, we're
[00:25:54] like setting up more kind of isolated
[00:25:57] environments for it to do it. Right now,
[00:25:58] we're not quite there where we trust it
[00:26:00] to completely take over, but we've done
[00:26:01] a lot of different things with agents.
[00:26:03] So far, for example, we already have
[00:26:05] agents pull um for like statuses for
[00:26:08] different services and give us updates
[00:26:10] on how things are going during a deploy
[00:26:12] or during incidents, etc. It's very good
[00:26:15] at getting like information. We haven't
[00:26:17] gotten to the point where we fully trust
[00:26:18] it to like actually come up with like
[00:26:21] fixes and apply them quite yet, but it
[00:26:24] can. We ask it to suggest things and
[00:26:25] then we'll we'll we'll we'll monitor and
[00:26:27] look at it ourselves. Um, but again, all
[00:26:30] things solvable by model capability and
[00:26:32] we're getting there.
[00:26:34] >> Yeah, that's the other piece that like
[00:26:36] is popping out for me is like I think in
[00:26:38] a sense the the most of the
[00:26:42] conversations I'm in what I hear is
[00:26:45] conversation about models and code. That
[00:26:47] is a lot of what you've talked about,
[00:26:48] you know, generating code this and that.
[00:26:50] Um, and it's framed as a mostly solved
[00:26:52] problem these days. It's framed as
[00:26:54] something that the models have become
[00:26:55] very good at. And I think that your this
[00:26:58] conversation opens up a really
[00:27:00] interesting uh sort of more nuanced
[00:27:02] picture where you can say it's one thing
[00:27:04] to say that the model has grasped app
[00:27:07] level code bases and can kind of get
[00:27:09] into that and mostly solve that. It's
[00:27:11] very different to talk about how you
[00:27:14] support platform and infra teams and how
[00:27:16] you make sure the model is able to
[00:27:17] operate autonomously in that space. And
[00:27:20] when even when you were saying, you
[00:27:22] know, the the tool calls are there
[00:27:24] there's like many many more tool calls
[00:27:26] just to understand what's going on and
[00:27:28] to understand what's going on correctly.
[00:27:29] It sort of got me sort of chewing on
[00:27:31] this idea that effectively platform
[00:27:34] teams are on the cutting edge of where
[00:27:36] scaling laws are going and like you have
[00:27:38] maybe an order of magnitude maybe two
[00:27:40] orders of magnitude more complexity that
[00:27:41] you're dealing with and therefore as the
[00:27:43] scaling law comes up you're sort of
[00:27:45] seeing that it hit app team first but
[00:27:47] you're feeling I'm sort of feeling that
[00:27:49] cutting edge of like it's not quite
[00:27:50] there but we can see it getting there as
[00:27:52] you deal with a much more complex
[00:27:53] environment.
[00:27:55] >> Yeah. Yeah. Yeah. And it adds to the
[00:27:58] complexity that everything around you is
[00:28:01] growing very very fast. Like all the app
[00:28:03] layer like you know logic is growing
[00:28:05] very very fast. So not only do we have
[00:28:07] to deal with the complexity of like
[00:28:08] trying to upgrade our systems to be
[00:28:10] agentic. We also are dealing with a
[00:28:11] deluge of scaling problems just pure
[00:28:14] >> raining down from the app layer. Right.
[00:28:16] The app layer is like okay now we're
[00:28:18] going to just scale like crazy and like
[00:28:20] they expect platform to keep up.
[00:28:22] >> Yes. Yes. Exactly. So so we're we're
[00:28:24] kind of in a double whammy right now.
[00:28:26] Um, but but then again, I'm I'm very
[00:28:28] optimistic. We already have like really
[00:28:30] awesome like ideas and solutions in
[00:28:32] place to solve a lot of these. And we're
[00:28:34] very very hopeful. I think we're like
[00:28:36] like you like we were talking about, I
[00:28:38] think because of the complexity of kind
[00:28:40] of platform teams, the model needs to
[00:28:41] get a little bit stronger for it to be
[00:28:43] able to do this safely. Um, and we're
[00:28:45] very hopeful because we see the progress
[00:28:46] there.
[00:28:47] >> Yep. Yep. That makes sense. If you were
[00:28:49] to give some perspective, you know, I
[00:28:51] have lots of folks who are deep on data,
[00:28:52] deep on platform, deep on infra, but of
[00:28:54] course, they don't work at OpenAI and
[00:28:56] and they're in my audience. I'm I'm
[00:28:58] curious what you would sort of tell them
[00:29:01] as like their Swiss Army knife or their
[00:29:03] pocket guide to sort of how to handle
[00:29:05] some of the complexity they're dealing
[00:29:06] with because I hear from them some of
[00:29:08] the same challenges, but of course,
[00:29:09] they're not working inside a hyperscaler
[00:29:11] and so they don't necessarily have
[00:29:13] access to some of the cutting edge stuff
[00:29:16] that you're going to be able to pull
[00:29:17] from. And so in that world, you know,
[00:29:19] what would you say to an infra engineer?
[00:29:21] What would you say to someone leading a
[00:29:22] data team um who who isn't working at a
[00:29:25] hyperscaler?
[00:29:27] >> That's a really good question. Um
[00:29:30] I think a lot of us on platform teams
[00:29:33] and infert teams are feeling a little
[00:29:35] bit underwater. So I would say to those
[00:29:38] teams first try to get yourself a little
[00:29:40] bit more time so that you can innovate
[00:29:42] out of this. Um
[00:29:44] >> and and for us for example, we you know
[00:29:47] rolled out support bots. Again, this
[00:29:49] this buys us more time, right? With the
[00:29:51] delage of user requests, like at least
[00:29:53] some of these less urgent ad hoc
[00:29:55] requests can be dealt with by an agent.
[00:29:57] Um we encoded a lot of our best
[00:29:59] practices in agent MD files. Um so that
[00:30:02] you know the agents usually respect
[00:30:04] those. Um we encoded a lot of our best
[00:30:07] practices and skills. Again, hopefully
[00:30:09] like agents will hopefully respect
[00:30:11] those. And um um but agents are you know
[00:30:14] just just to to say they're very very
[00:30:16] innovative. They've they've done things
[00:30:17] where like okay that was not that's an
[00:30:20] internal API should have never been
[00:30:21] exposed. I don't know how you found out
[00:30:22] about that. Um so yeah so so even if you
[00:30:27] have it all in scales at HMD you still
[00:30:29] can do a very squirly stuff. Um and uh
[00:30:33] and just like build in if you have the
[00:30:35] resources to just build in a little bit
[00:30:37] more reinforcement and shoring up of
[00:30:39] your of your systems to ban bad actors.
[00:30:41] I think yeah I I it's it's not intention
[00:30:45] it's not intentional right um but but a
[00:30:48] a lot of these a lot of these PRs
[00:30:50] generated um they can they're almost
[00:30:52] quite adversarial like the case I
[00:30:54] mentioned before where they're like
[00:30:55] doing things they're not supposed to do
[00:30:56] changing internal APIs to do the thing
[00:30:58] that they want but you know will break
[00:31:00] everybody else um you just got to put in
[00:31:03] more systems and like maybe obiscate
[00:31:05] those APIs from them make it less
[00:31:07] accessible to to like you know
[00:31:09] potentially agent coder
[00:31:11] to kind of build that defense as well.
[00:31:13] And once you buy yourself enough time,
[00:31:15] innovate on your systems, right? Build
[00:31:17] that like harness tool so that you can
[00:31:19] have an agentic response to PRs, right?
[00:31:21] And build those systems um like for
[00:31:24] example isolated like you know testing
[00:31:26] systems so you you feel confident in
[00:31:28] like a very minimal agentic kind of
[00:31:30] operations um uh response to like you
[00:31:33] know some some critical systems and
[00:31:35] therefore hopefully roll that out in
[00:31:37] production as well. you need to invest
[00:31:38] in like wholesale upgrades of your
[00:31:40] system and so buy yourself time and like
[00:31:43] start thinking about what needs to be
[00:31:45] changed underlying to to make this
[00:31:48] possible for you to scale.
[00:31:50] >> Yeah, I that's just going to be a
[00:31:52] fascinating tibbit for a lot of folks
[00:31:53] right there. I think this that like one
[00:31:55] of the things I'm hearing really pop out
[00:31:56] is I hear a ton from people who are
[00:32:00] earlier in the AI transformation journey
[00:32:03] obviously than than folks at
[00:32:04] hyperscalers than you are. Um, and sort
[00:32:06] of the the telegraph from the future
[00:32:08] that you're sending is basically when
[00:32:11] you get this AI transformation to a
[00:32:12] certain point and it starts to take off
[00:32:14] and your app team start to widely adopt
[00:32:16] coding agents. The pinch point that
[00:32:19] starts to emerge is that you now have uh
[00:32:22] n highly goal- directed agents who are
[00:32:24] coding in your system and they are going
[00:32:27] to hit your data and platform layers
[00:32:29] really hard and they may hit it in a way
[00:32:31] that feels adversarial even if that is
[00:32:33] not the intent of the human because the
[00:32:35] agents are very good and very goal
[00:32:37] directed and really go after what they
[00:32:38] want to get.
[00:32:39] >> Yes. Yes. Exactly. Exactly.
[00:32:43] So, so exactly like you said, it's
[00:32:45] unintentionally, but sometimes it can
[00:32:47] get a little adversarial in terms of
[00:32:49] just the deluge and also in terms of the
[00:32:51] methods that the agents use to get at
[00:32:54] your systems.
[00:32:55] >> Yep. Yep. Y
[00:32:56] >> and ultimately we want to make it so
[00:32:58] that like we're like our systems are
[00:33:01] innovative enough and responsive enough
[00:33:04] and fast enough in an autonomous way
[00:33:06] where these are not problems. Like
[00:33:08] again, no bad intentions, right? What is
[00:33:10] a user trying to do? why does it need to
[00:33:12] do this and get around things like how
[00:33:14] can we make that better for the users
[00:33:15] and go faster together right that's
[00:33:17] ultimately the goal um but we just need
[00:33:20] to make sure that we are you know
[00:33:21] investing in those systems
[00:33:23] >> how how do you think about the sort of
[00:33:26] hierarchy of utility around you've
[00:33:28] mentioned uh plugins you've mentioned
[00:33:30] skills you've mentioned markdown files
[00:33:32] when you're thinking about architecting
[00:33:34] something that is intended to provide a
[00:33:36] guardrail or intended to provide some
[00:33:38] kind of input to an agentic system. How
[00:33:41] do you go about sort of segregating that
[00:33:43] out in a way that you you feel confident
[00:33:45] you've got the right form factor for
[00:33:46] that for that tool?
[00:33:50] >> It really is an iterative process. I
[00:33:52] don't think we figured it out. Like all
[00:33:54] of these are attempts to make it better
[00:33:55] and most of them have made it m much
[00:33:57] better, but we still see like gaps. Um
[00:34:01] uh
[00:34:02] >> Got it.
[00:34:03] >> Yeah.
[00:34:04] >> So it sounds like bias to ship and then
[00:34:05] you figure it out from there.
[00:34:07] >> Yeah. That's why I keep on advocating
[00:34:09] for like agentic response to like
[00:34:12] >> changes right now like skills these are
[00:34:15] these are model mediated responses yes
[00:34:17] but it's not like fully like multi- aent
[00:34:19] world where I can encode my values um
[00:34:22] separate from um you know like code
[00:34:24] creators values and then we can have
[00:34:26] like a balanced dynamic. We're not quite
[00:34:28] there yet. I think that's the missing
[00:34:29] ingredient. All of these things you
[00:34:30] described are like we still rely on one
[00:34:32] single model to do the right thing.
[00:34:35] >> One single agent to do the right thing.
[00:34:37] >> I again this is my personal opinion. I
[00:34:39] don't think that's enough.
[00:34:41] >> Yeah. You were talking about the idea of
[00:34:43] like a a need to separate incentives
[00:34:45] between a coding agent and a code
[00:34:47] reviewer agent for example.
[00:34:48] >> Yeah. Yeah. Yeah. Yeah.
[00:34:49] >> Yeah.
[00:34:49] >> Yeah.
[00:34:50] >> That makes sense.
[00:34:51] And so if you were to think about sort
[00:34:53] of buying your your team time back, the
[00:34:55] it sounds like just triaging inbound and
[00:34:58] starting to take action on inbound
[00:34:59] requests is one of the first places that
[00:35:01] you look.
[00:35:02] >> Yeah. So for a lot of platform teams
[00:35:04] like ours, like we have like literally
[00:35:06] the whole company's are user base. Like
[00:35:07] we have like 6,000 users essentially,
[00:35:09] right? Um if you look at like our
[00:35:11] support channels, like each one of them
[00:35:13] has like hundreds of questions every
[00:35:15] day. It's like, oh, you know, my service
[00:35:17] uh is missing this like access to this
[00:35:20] service. Like, can you like make that,
[00:35:22] you know, happen for me? Um, this job is
[00:35:25] broken in this way. I need someone to
[00:35:27] help take a look at this and why this is
[00:35:28] like there's just like so many different
[00:35:31] very like high cardality type of like,
[00:35:33] you know, questions being asked. Yeah.
[00:35:35] >> And um, you know, we dedicated resources
[00:35:38] to just answer those questions and we
[00:35:39] still do. Um but we're we're really
[00:35:41] heavily invested in training a model to
[00:35:43] do this better especially for things
[00:35:44] that are like more questionoriented like
[00:35:46] debugging um like why is this happening
[00:35:49] giving solutions I think there's you
[00:35:51] know we're we're we're at in this front
[00:35:53] the model is beyond the frontier it can
[00:35:55] do this you know it can debug like a job
[00:35:58] um fairly well it can connect to the
[00:35:59] sources and and do these and the users
[00:36:02] can like try those out because it's low
[00:36:03] consequences a single job you know if it
[00:36:05] fails they can try it again so the
[00:36:07] models are like very very good at that
[00:36:09] so we just need to roll that out more
[00:36:10] broadly um to all of our systems. The
[00:36:13] other thing I mentioned which is another
[00:36:14] team where a lot of requests are more
[00:36:16] feature- shaped. It's like I want this
[00:36:18] dashboard to have like be able to hide
[00:36:21] this line when I click this thing,
[00:36:22] right? That's a different type of
[00:36:24] response and we have a different agent
[00:36:25] dealing with that, right? And that agent
[00:36:27] literally just runs a whole loop and
[00:36:28] tries to like take as much off the plate
[00:36:30] of of our um of our engineering team as
[00:36:33] possible. So for every team the response
[00:36:34] will be very different in terms of what
[00:36:36] agent will solve your problem the most
[00:36:37] and and and fill in that gap and then um
[00:36:40] because the the model capabilities are
[00:36:42] changing so fast like what it can do can
[00:36:44] change so every month we have to go and
[00:36:45] reevaluate can it do this now can it do
[00:36:47] this other thing now um uh but yeah so
[00:36:52] we're very optimistic on where it's
[00:36:53] going but right now it's able to help in
[00:36:56] specific ways and we're kind of like
[00:36:57] seeing what it can do now and try to you
[00:36:59] know help ourselves a little bit in what
[00:37:01] it can do But like seeing that very
[00:37:04] quickly it's going to be able to do more
[00:37:05] and take advantage of that.
[00:37:07] >> Yeah. And that's another piece. Maybe we
[00:37:09] can tug at that thread before we close
[00:37:11] here. I It feels to me like you have an
[00:37:15] intuitive sense of where you would want
[00:37:18] to push, experiment, or play with a
[00:37:22] model where you're like, I'm not sure if
[00:37:24] the model can do this yet. It feels like
[00:37:26] it's on the edge of the capability set.
[00:37:27] Let me go and kind of nudge it and play
[00:37:29] with it and see what we get. I think my
[00:37:31] my impression as we talk is that that
[00:37:33] feels very organic for you and I'd love
[00:37:35] it if you unpack that a little bit for
[00:37:36] folks who may be struggling with and
[00:37:38] trying to understand like you know I'm
[00:37:40] in a complex codebase I'm in a complex
[00:37:42] environment I understand exactly what
[00:37:44] you say when you say the model isn't
[00:37:45] there yet on something
[00:37:47] >> how do I know when to push it how do I
[00:37:48] know when to play with it how do I know
[00:37:50] when to experiment with it
[00:37:52] >> yeah so we have um and the same for
[00:37:56] folks are using our models as well
[00:37:58] internally we have previews of models
[00:38:00] are coming up. So we do get to play with
[00:38:02] a a few more versions of them. So we do
[00:38:04] always try to test the most frontier
[00:38:06] model um with existing kind of
[00:38:08] capabilities. The other thing we're
[00:38:10] trying to do across the different teams
[00:38:11] is we actually have our EBALs library.
[00:38:14] Um so for different teams they have EBLs
[00:38:16] for the core capabilities that they want
[00:38:18] the agent to do and we're still fleshing
[00:38:20] that out because again with greater
[00:38:22] model capabilities we can add even more
[00:38:24] like types of things we can do. But for
[00:38:25] example, this eval for um you know full
[00:38:28] stack like figuring out like you know
[00:38:30] feature sets and and and deploying that
[00:38:32] um we have evalu
[00:38:40] oh it's really getting good at this
[00:38:41] maybe we should try to get it to do this
[00:38:43] you know
[00:38:44] >> um so we do have those and then we do do
[00:38:46] a lot of live testing we're always like
[00:38:48] pushing the frontier on things um you
[00:38:51] know and this may be more of a manager
[00:38:52] like you know culture thing is like at
[00:38:54] OpenAI We're always pushing people to
[00:38:56] like try more things with it. Have you
[00:38:58] tried this other thing with it? If
[00:38:59] someone comes back like, "Oh, this took
[00:39:01] me six hours to do." It's like, "Have
[00:39:02] you pushed Codeex hard enough to try to
[00:39:04] do this?"
[00:39:05] >> Why six hours? Come on.
[00:39:08] >> Yeah. And the answer maybe it's like it
[00:39:09] literally just has to take six hours and
[00:39:11] slower, but we we're pushing people all
[00:39:13] the time, right, to like try new things.
[00:39:15] Um, and there's an internal culture of
[00:39:17] experimentation as well. It's like we
[00:39:19] kind of send kudos to people who have
[00:39:20] innovative use cases. We all share with
[00:39:22] each other how we're using codecs and
[00:39:24] how it's accelerating and new workflows
[00:39:25] that's coming up and and we have um
[00:39:28] learning sessions where we swap these
[00:39:30] but also just like culturally we just
[00:39:32] like there's admiration for people who
[00:39:33] are able to do this find innovative
[00:39:35] working use cases um with agents and
[00:39:38] it's considered cool here it's
[00:39:40] considered like you know you're you're
[00:39:41] innovative here. So that itself creates
[00:39:44] this kind of culture to like people
[00:39:45] really want to try what else we can do
[00:39:47] with it. as soon as a new model comes up
[00:39:49] like people are experimenting um things
[00:39:51] that they tried and didn't really work
[00:39:53] out before they'll try again right again
[00:39:54] this is where the emails library come up
[00:39:56] you know we already have a set of things
[00:39:58] that we really would like the agent to
[00:40:00] do and we can just keep on trying um and
[00:40:02] see if it improves there
[00:40:04] >> and I will say like most of the larger
[00:40:09] teams that I talk with do not have the
[00:40:12] discipline yet of maintaining a private
[00:40:14] eval suite that is designed to test
[00:40:17] emerging model capabilities. So model
[00:40:18] drops, they're going back and they're
[00:40:20] either looking at production and they're
[00:40:21] saying do we want to try and swap it in
[00:40:23] and see what happens? Which is really
[00:40:24] scary. Um or they're saying we don't
[00:40:28] have a defined process for this. We need
[00:40:29] to assign someone at some point to look
[00:40:30] at this. And both of those are fairly
[00:40:32] inefficient ways to explore the space.
[00:40:34] And I think that one of the things that
[00:40:36] is a great takeaway is invest in that
[00:40:39] eval suite. Um and even if you're not in
[00:40:41] a hyperscaler, you're still going to get
[00:40:43] new models coming in. you will still get
[00:40:44] the chance to use that and it will be
[00:40:46] very efficient for you to understand
[00:40:48] what's going on.
[00:40:49] >> Yes. Yes. And you it doesn't have to be
[00:40:51] heavy investment. You can do a very
[00:40:52] janky email suite. It's just like you
[00:40:54] have a notion doc with like all of the
[00:40:56] emails and expected out outputs and just
[00:40:58] like run it through the model every time
[00:41:00] it comes out. It can be very janky. It
[00:41:02] doesn't have to be fancy. Um and that's
[00:41:04] kind of like you know a scrappy way to
[00:41:05] do it.
[00:41:06] >> Yeah. It's funny that you say that
[00:41:08] because one of the things that tipped
[00:41:09] for me and I love how this ties into
[00:41:11] this idea that you want to be exploring
[00:41:13] and finding new ways to use models
[00:41:15] creatively. I had a tipping point with
[00:41:17] Codeex uh just this week uh where uh
[00:41:21] it's obviously much smaller scale from a
[00:41:23] data perspective, but what I was doing
[00:41:25] was I was spending time essentially
[00:41:27] assembling a local folder um with a
[00:41:31] bunch of meeting transcripts with a
[00:41:32] bunch of uh research that the agent had
[00:41:35] done. Um, and my goal was actually turn
[00:41:37] that into a variety of documents. It
[00:41:39] wasn't just one. Uh, I think it was
[00:41:41] eight. And
[00:41:43] >> for the first time, I was able to tell
[00:41:45] CODC, okay, we've had a conversation
[00:41:46] about this. You've got a local folder
[00:41:48] with a bunch of stuff, right? It's got
[00:41:50] text of various types from different uh
[00:41:52] input settings. Like some of it is
[00:41:54] formal reporting, some of it is very
[00:41:55] informal conversation. Your task is to
[00:41:58] now simultaneously produce eight
[00:42:01] different documents. And it did it.
[00:42:04] >> Wow.
[00:42:05] Um, and those were angled. It was really
[00:42:08] >> That's kind of Yeah. Yeah. Eight
[00:42:09] different documents. That That is pretty
[00:42:11] cool. I have never tried that. I need to
[00:42:13] go try that.
[00:42:14] >> There you go. Like kids right here. It's
[00:42:15] like you're now you're the cool dog, you
[00:42:17] know? They'll have to learn from me.
[00:42:21] >> No, it was really fun. And And like I
[00:42:22] could feel like for me it feels like the
[00:42:24] the wind is like blowing my hair back.
[00:42:26] Like it's like wow, the future is here.
[00:42:28] Like I'm doing eight docks at once. Uh,
[00:42:30] and then inside the same context window,
[00:42:33] I was able to give it edits and it was
[00:42:36] able to agentically
[00:42:38] version out the eight docs and rewrite
[00:42:40] them until I got them to where I wanted
[00:42:42] them to be. It was It was really fun.
[00:42:43] >> Wow. Wow. Wow. That must have been like
[00:42:46] crazy. Also, like think about the
[00:42:47] timesaving. Eight docs in the past. Man,
[00:42:50] >> we're we're in a brave new world now.
[00:42:52] For sure.
[00:42:54] >> That's right. That's right. Uh and maybe
[00:42:56] that that leads us to the last question
[00:42:58] I have for you which is uh we talk a lot
[00:43:00] about autonomous AI, autonomous infra
[00:43:02] kind of where the models are going in
[00:43:03] this conversation. Uh human attention
[00:43:06] continues to be very scarce and so where
[00:43:08] do you allocate yours? How do you think
[00:43:10] about how your human attention scales,
[00:43:11] your team's human attention scales?
[00:43:15] >> Uh such a good question. Um I think as
[00:43:17] an infra engineer or as software
[00:43:19] engineers in general um we spend a lot
[00:43:21] of time thinking about scalability
[00:43:24] >> and I I think we're we're right in the
[00:43:26] midst of that. It's like the perfect
[00:43:28] thing for an inframinded person to think
[00:43:30] about because it's all about scalability
[00:43:32] right now. And so I I think a lot about
[00:43:34] what systems need to be upgraded in
[00:43:36] order to scale what people systems as
[00:43:38] well. like if I want my my folks to like
[00:43:40] really maximize their time here, they
[00:43:42] need to like leverage our um agentic
[00:43:44] coding a lot more or a like agentic
[00:43:47] tooling a lot more. So I encourage that
[00:43:48] also on the systems level is like what
[00:43:50] are the systems we need to fix right now
[00:43:52] and change and uplevel so that we can
[00:43:55] respond to the onslaught. Um this this
[00:43:58] is this ties into all the other things I
[00:44:00] talk about as well. And then another
[00:44:02] thing is just you know in this world
[00:44:04] there's a lot of information um and
[00:44:07] nobody really knows how this is going to
[00:44:09] play out and
[00:44:10] >> you know in my role a big part of my job
[00:44:12] is to kind of let other people including
[00:44:15] um other leaders uh at the company know
[00:44:17] what's going on on the ground right so
[00:44:20] uh you know this this kind of like
[00:44:22] difference acceleration it it could be a
[00:44:25] problem if it continues like this right
[00:44:27] it could be a problem in terms of like
[00:44:28] you know reliability or scalability may
[00:44:30] really be compromised if we don't invest
[00:44:32] in um our tooling. Uh so a big part of
[00:44:35] my job is also just like talking to
[00:44:37] various folks and making sure that
[00:44:38] people understand what's going on on the
[00:44:39] ground.
[00:44:40] >> Makes a ton of sense. Um well, if you
[00:44:43] had one thing to say and maybe we'll
[00:44:45] frame it as like if you had one thing to
[00:44:47] say as an AI powered leader to advise
[00:44:49] other leaders on like this is how you
[00:44:51] should think about your job and how it's
[00:44:52] shifting, what would it be?
[00:44:56] H I think business as usual is not going
[00:44:59] to fly anymore. If you are a leader, you
[00:45:02] need to be a visionary. You need to like
[00:45:04] wear that visionary hat and be like
[00:45:06] things are changing rapidly.
[00:45:09] How do I navigate in a world where
[00:45:11] things are changing navally? How do I
[00:45:12] get all the information I need to
[00:45:14] understand where we're going? And then
[00:45:16] give clear direction to your your own
[00:45:18] folks um and encourage them to not be
[00:45:21] scared of the brave new world. I think
[00:45:23] human a lot of times human like the
[00:45:25] first instinct is like oh my gosh it's
[00:45:26] like this is scary it's my job going
[00:45:28] away you know all these things you need
[00:45:30] to provide that positivity and like um
[00:45:34] kind of just like inspiration and kind
[00:45:37] of like a vision for them to realize
[00:45:39] that this is actually a really exciting
[00:45:41] time to be you know and we can all be at
[00:45:43] the forefront of this um so yeah just
[00:45:46] provide the support for your team.
[00:45:48] >> Love that.
[00:45:49] >> Well thank you for taking the time. I
[00:45:50] really appreciate it Emma. Thank you so
[00:45:52] much, Nate.
[00:45:53] >> Yeah, it's been really fun. I'm glad we
[00:45:55] got a chance to chat and I'm look
[00:45:56] looking forward to hearing how like the
[00:45:58] models make your job easier in the
[00:45:59] future.
[00:46:01] >> I know, right? It's going to get serious
[00:46:03] in the next few months. I know. Like we
[00:46:05] have some really awesome stuff coming
[00:46:06] up. So, uh it's it's going to be great.
[00:46:08] Codeex is like amazing. Everybody should
[00:46:10] use it.
[00:46:12] >> Yeah. Yeah. It's been a lot of fun to
[00:46:13] use for me, too. I've I've been watching
[00:46:15] the like I I actually do token burn
[00:46:17] counts every day and like I have Codeex
[00:46:19] let me know how many tokens I burn.
[00:46:20] like, "Wow, you can see the power law
[00:46:23] here because I'm suddenly using it more
[00:46:24] and more and more." So,
[00:46:25] >> yeah. Yeah. Yeah. I love it. I love it.
[00:46:28] Let's go.
[00:46:28] >> Yeah. There you go. Amazing. Thank you
[00:46:31] so much.
[00:46:32] >> Okay. Thank you so much.
[00:46:33] >> All right. Bye.
[00:46:35] >> All right. See you.
