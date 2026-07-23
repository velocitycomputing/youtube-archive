---
video_id: 88B6DimMD2g
title: "How This Ex-Meta L8 Engineer Ships 40 PRs a Day with AI Agents | Kun Chen"
channel: Peter Yang
url: "https://www.youtube.com/watch?v=88B6DimMD2g"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 3378
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 72
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 338
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Kun Chen, an ex-Meta L8 engineer now solo building with AI agents, demonstrated a three-phase workflow: detailed planning (human-led with agent input), autonomous coding (entirely agents), and validation (agents with human judgment). He ships 20–40 PRs daily by running 5+ concurrent sessions with 20–30 agents in parallel, maximizing time agents work unsupervised. Key innovations include Lavish, an interactive visual-planning tool using HTML artifacts instead of text walls to make feedback faster and more intuitive; Treehouse, a worktree manager eliminating cognitive overhead; and explicit testing instructions in project-specific `agents.md` files (end-to-end browser tests, screenshots) since agents default to shallow unit tests. He strategically spawns sub-agents to prevent context bloat and run parallel experiments.

**For you:** (1) Write detailed specs with measurable goals before delegating to agents—the planning investment directly extends how long agents can work unsupervised; vague prompts force re-prompting cycles. (2) Parallelize sessions aggressively using worktrees and automation; context-switching between independent threads is faster than waiting. (3) Replace text-based planning feedback with visual HTML artifacts (Lavish, Claude artifacts, or simple HTML) so you can annotate directly and click to approve options. (4) Add explicit end-to-end and visual validation instructions to your agent system prompt or project docs (how to run the app, drive it via browser, capture screenshots), since agents won't do this by default. (5) Use sub-agents to isolate high-context exploration or parallel experiments, returning only conclusions to keep the main session lean.

## Transcript

[00:00:00] If you review every single line of code,
[00:00:02] you become the bottleneck. So I don't
[00:00:04] reveal this first pass code from the
[00:00:06] agent. Eventually I got to a point where
[00:00:09] I find myself never catching anything
[00:00:11] the agents don't catch. I typically have
[00:00:13] like at least five different sessions
[00:00:15] actively running. On average, there's
[00:00:17] like 20 to 30 agents running. Most of
[00:00:19] the time, uh, it's like 20 to 40 kind of
[00:00:22] PRs every day. Our workflows and how our
[00:00:25] teams work were built at a time when we
[00:00:28] spend most of our time coding. But when
[00:00:30] you start to write like 10 times more
[00:00:32] PRs, we are not ready for that to really
[00:00:35] scale up how much we can get from the
[00:00:37] agents. We have to move ourselves out of
[00:00:40] the loop as much as possible.
[00:00:44] Hey everyone, today I'm really excited
[00:00:46] to welcome my friend uh, an L8
[00:00:48] engineer from Meta at Microsoft who's
[00:00:50] now a solo AI builder. is going to
[00:00:53] show us exactly how he builds products
[00:00:55] using agents. I've been asking him a lot
[00:00:57] of dumb questions about all this. So,
[00:00:58] we're really excited for him to show us
[00:01:00] live. So, welcome, sir.
[00:01:02] >> Thanks for having me here, Peter.
[00:01:04] >> All right. So, uh let's get right into
[00:01:05] it. Maybe you can start uh by kind of
[00:01:08] walking through at a high level how
[00:01:09] you're building products with agents.
[00:01:12] >> All right. Um that is my workflow. Um
[00:01:15] plan, code, and validates. Uh I don't
[00:01:17] think this is too different from uh what
[00:01:19] everybody does. Um, so I'll probably
[00:01:21] talk through the parts where I think I'm
[00:01:23] doing something unique. Um, so I think
[00:01:26] typically when we build something
[00:01:27] meaningful, we typically go through
[00:01:29] these phases, right? We plan what the
[00:01:31] requirements are. Um, and then we let
[00:01:33] the agent code and then we uh have to do
[00:01:35] some validation to make sure the agent
[00:01:37] actually did what we wanted them to do.
[00:01:39] Um, so this uh the high level workflow I
[00:01:41] think is pretty standard. Um, where I
[00:01:44] think I do something different uh is uh
[00:01:46] how much time I spend in each phase. Um
[00:01:49] so currently I think I spend more time
[00:01:51] in the planning phase. Uh so planning is
[00:01:54] like mostly me with assistance from uh
[00:01:57] the agents. The coding phase is pretty
[00:01:59] much entirely the agents. Um so I once
[00:02:01] the requirements are planned very
[00:02:03] clearly. Um I trust the agents to do
[00:02:06] most of the work. Um and then in
[00:02:08] validation phase uh I use agents a lot
[00:02:10] as well. Um and agents do most of the
[00:02:12] work with some judgment from me when
[00:02:15] things are ambiguous. And I think uh the
[00:02:18] the the part the part about this is that
[00:02:21] um if we actually uh start to delegate
[00:02:25] most of the coding to agents.
[00:02:27] >> Mhm.
[00:02:28] >> What I um the way I think u I can uh get
[00:02:31] agents to do more for me is to try to
[00:02:34] increase the amount amount of time
[00:02:36] agents spends in this phase because this
[00:02:38] is entirely agents right so if we can
[00:02:40] get the agents to do to go for longer uh
[00:02:43] then I'll get more done. So this is one
[00:02:46] area where I tried a lot of things to
[00:02:49] just scale up the amount of time I can
[00:02:51] let the agents run autonomously.
[00:02:53] >> Yeah. It's almost like the code and the
[00:02:55] validation is a loop that the agent can
[00:02:57] run itself, right? And and so that it
[00:02:59] can actually code for a longer time
[00:03:01] period.
[00:03:01] >> Yeah. Yeah. And also I think it depends
[00:03:03] on how much time we spend in the
[00:03:05] planning phase. So if I uh spend a lot
[00:03:07] of time crafting a very detailed plan
[00:03:09] then I can let the agents go for longer.
[00:03:12] um if I uh only write a very very short
[00:03:15] prompt then what I'll find is that uh
[00:03:17] very quickly the agents will get work
[00:03:18] done and then I'll need to go back and
[00:03:20] prompt them again. So uh like how much
[00:03:23] time we invest in the planning phase
[00:03:25] actually affects this a lot.
[00:03:26] >> Okay, that's a really good point because
[00:03:28] I I've gone like super lazy with these
[00:03:29] agents. I don't actually like I just
[00:03:32] give them like one line prompts and yeah
[00:03:34] it never works for hours. So yeah would
[00:03:36] love to kind of see each face.
[00:03:39] >> Yeah. Yeah. So yeah, I think the things
[00:03:41] that we we can do differently in the
[00:03:42] planning phase is like go from a short
[00:03:44] prompt uh to say what is the next action
[00:03:47] you should take to something more like a
[00:03:49] spec where um you you write down a more
[00:03:52] uh a more comprehensive set of details
[00:03:54] of the requirements and then go from
[00:03:56] spec to a goal. So if you can actually
[00:03:59] craft a measurable goal, you can let the
[00:04:02] agents do a lot of experimentation.
[00:04:04] >> Okay. Okay. So can you show us how this
[00:04:06] works? like maybe we can start with the
[00:04:08] planning phase like
[00:04:10] >> some some example plans that you write.
[00:04:11] Yeah.
[00:04:12] >> Yeah. Actually uh there's another uh
[00:04:14] dimension of how I optimize this flow as
[00:04:16] well. Uh which is like if you look at
[00:04:18] this uh this uh timeline, right? Um the
[00:04:22] parts that need me is only like this
[00:04:24] beginning and the end, right? Uh so what
[00:04:27] I do is like I I make sure I can
[00:04:29] paralyze a lot of sessions. Um so so
[00:04:32] that's I'm always spending my time
[00:04:34] productively um uh while the agents are
[00:04:37] doing the work. So I think increasing
[00:04:39] the the amount of concurrent parallel
[00:04:42] sessions that's also a very important
[00:04:43] aspect of how I get more done.
[00:04:46] >> And do you parallelize sessions in the
[00:04:47] same uh project and product or like
[00:04:49] across products or both?
[00:04:51] >> Uh both both. Uh so I have a hybrid of
[00:04:53] different projects. Uh but even within
[00:04:55] the same project I sometimes have
[00:04:57] multiple sessions doing different
[00:04:58] things.
[00:04:59] >> Yeah. It's funny. It's funny because we
[00:05:00] used to uh like you know both of us used
[00:05:02] to work in big tech and um it used to be
[00:05:05] a lot of context switching between
[00:05:06] meetings but now you're context
[00:05:08] switching between different threads or
[00:05:09] [laughter]
[00:05:10] you know it's actually it's actually
[00:05:12] faster context switching in some ways.
[00:05:14] >> Yeah. Yeah. Totally. I I think uh it's
[00:05:16] kind of like a um someone that's
[00:05:18] overseeing a very large scope, right?
[00:05:20] There's always different things
[00:05:21] happening and there are different things
[00:05:23] escalating to you and you need to jump
[00:05:25] into different things depending on what
[00:05:27] is the where you are needed the most. Uh
[00:05:29] so this is very much alike.
[00:05:31] >> Okay, this episode is brought to you by
[00:05:33] linear. When engineers use tools like
[00:05:35] cursor, clock code and codeex, a lot of
[00:05:38] work happens invisibly. Someone can go
[00:05:40] from a bug report in Slack to a shipped
[00:05:43] fix without creating any record of what
[00:05:45] happened outside of the code editor. And
[00:05:47] that's fine for speed, but it makes
[00:05:48] coordination harder as you scale. Linear
[00:05:51] integrates with the very best agent
[00:05:53] coding tools directly like cursor and
[00:05:55] codeex. That way, anyone can see what an
[00:05:58] agent is working on and who assigned
[00:06:00] them to the task. You get the speed of
[00:06:02] agents without losing visibility across
[00:06:04] the team. Product teams at OpenAI, Ramp,
[00:06:07] and Block are all using Linear to
[00:06:09] collaborate with AI agents. And I use
[00:06:11] LIR myself to run my creator business.
[00:06:13] So, check it out at linear.app/
[00:06:17] aents. That's linear.app/
[00:06:20] aents. Now, back to our episode.
[00:06:22] >> Can you show us your, you know, AI stack
[00:06:23] or agent decoding setup?
[00:06:25] >> Yeah. Yeah, let's do it. Uh, so this is
[00:06:28] my terminal. Uh, this is where I I do
[00:06:30] like all of my work pretty much. uh
[00:06:32] occasionally I I switch to a GUI or a
[00:06:34] browser uh but most of the time uh I'm
[00:06:37] spending here. Uh so yeah I'm using a
[00:06:39] project here as an example to walk
[00:06:41] through it. Um so this is this is a
[00:06:43] project called hybits. Uh this is the AI
[00:06:46] tutor I'm building for my son. Uh it's
[00:06:48] an AI uh agentic uh harness uh for kids
[00:06:52] basically. And I just um built a new
[00:06:55] screen. Um so let me let me show you
[00:06:57] what that looks like. Um I revamped uh
[00:06:59] the um the main screen a little bit. Um
[00:07:02] but this is very messy because I just
[00:07:04] did this this morning. Uh and it's not
[00:07:06] looking good. Uh this is like this is
[00:07:08] not how I want this to look like. Um so
[00:07:11] I uh what I'll do uh like very typical
[00:07:14] workflow. I'll take a screenshot of
[00:07:15] this,
[00:07:17] right? Uh take a screenshot and then I
[00:07:20] come to my agent.
[00:07:22] Um I use open code a lot. Uh so I'm
[00:07:25] going to just launch open code in here.
[00:07:27] >> Mhm. And you use it because you can use
[00:07:29] multiple models.
[00:07:30] >> Yeah. Yeah. Exactly. So I I can very
[00:07:32] quickly try different models when the
[00:07:33] new models come out. Uh that is the uh
[00:07:36] big benefits I get from these open
[00:07:37] source tools.
[00:07:38] >> Makes sense.
[00:07:39] >> Um so yeah so what I'll do here is I'll
[00:07:41] just say hey look at this uh this
[00:07:45] screen. I'll paste uh the image here. Um
[00:07:49] and uh I'll say uh the things we saw on
[00:07:52] the screen. The things that I'm I was
[00:07:54] not very happy about was there is uh too
[00:07:56] much technical details not uh that are
[00:08:01] not friendly for kids. Uh also there is
[00:08:05] a big area of white space uh unused
[00:08:09] right those were the problems that we
[00:08:11] saw on the screen that's were like
[00:08:13] clearly not uh uh ideal. Uh so I'll I'll
[00:08:16] point out these problems um and I'll say
[00:08:19] hey uh can you propose
[00:08:23] uh some options for how we improve right
[00:08:27] so this is my uh the request I sent to
[00:08:29] the agent so because I sent the
[00:08:32] screenshot uh the um the model is going
[00:08:34] to be able to see visually uh what is
[00:08:37] going on there and then it's going to uh
[00:08:40] look at uh the codebase as well this so
[00:08:42] yeah it's very quickly came up uh with
[00:08:44] this plan So it says like best
[00:08:46] direction, option one, option two. The
[00:08:48] thing with this plan is that it's not
[00:08:51] very easy to read, right? Um so like
[00:08:53] when you look at this long wall of text,
[00:08:55] I like this I I I I will spend so much
[00:08:59] time reading this text. Um so what I do
[00:09:02] instead uh let me just try a new
[00:09:05] session. Uh what I actually do uh is I
[00:09:08] use a visual editor to uh do the
[00:09:10] planning. So uh I'll say the same thing.
[00:09:13] uh look at this screen there is too much
[00:09:15] uh technical details same thing right uh
[00:09:19] I will just add one bit to say use
[00:09:22] lavish uh to
[00:09:25] discuss this with me uh along with any
[00:09:29] questions you have um so lavish is a is
[00:09:34] a visual editor uh I built um after I
[00:09:37] read the article about HTML uh over
[00:09:40] markdown uh have you seen Yeah. Yeah.
[00:09:43] The from the Yes.
[00:09:45] >> Yeah. Yeah. Um, initially when I saw the
[00:09:47] article, I was not very sure about that
[00:09:50] because I I felt like HTML uh is going
[00:09:53] to be so token inefficient, right? Uh
[00:09:55] the models will have to write a lot more
[00:09:57] than a simple markdown. Um but when I
[00:10:00] tried it, it's actually super useful. Um
[00:10:02] so I'll show you once uh once we uh have
[00:10:05] this result from here. um the HTML as an
[00:10:08] artifact can be a lot richer in terms of
[00:10:11] like supporting this collaboration
[00:10:13] between human and agent. Um so it's not
[00:10:15] going to be a long wall of text I have
[00:10:17] to read through. Uh it's going to be
[00:10:19] like very visually um things I can just
[00:10:21] interact with.
[00:10:22] >> So Lavish is a is is like a app that you
[00:10:24] build to create the HTML in the format
[00:10:26] that you want. Is that
[00:10:27] >> Yeah. Yeah. It's a um it's a tool I
[00:10:30] built. Uh so what I do is like I uh
[00:10:32] every time I encounter any kind of a
[00:10:34] friction in my workflow and I don't find
[00:10:36] anything that can solve the problem for
[00:10:38] me I just build something myself.
[00:10:41] >> Yeah, Lavish is a is a tool I built. Uh
[00:10:43] it's a tool for
[00:10:45] >> both generating the HTML artifact and
[00:10:48] also supporting the uh back and forth
[00:10:51] interactive experience between human and
[00:10:52] agents on that. Um because what you um
[00:10:55] what we could do is I can just ask the
[00:10:58] agent to generate a HTML file, right? Uh
[00:11:00] and I and then I can open up the HTML
[00:11:02] file in the browser and it works. Um the
[00:11:04] problem with that approach is that once
[00:11:06] the HTML file is open and I I look at
[00:11:09] the HTML file and I see that there are
[00:11:12] some things I don't like, it's very hard
[00:11:14] for me to then tell the agent, hey,
[00:11:17] please change this part. U please
[00:11:19] iterate on this aspect. Right? So that
[00:11:21] back and forth is what um Lavage Editor
[00:11:24] is trying to solve.
[00:11:26] >> Oh, awesome. Yeah. Really excited to see
[00:11:27] what what it is. Yeah.
[00:11:29] >> Yeah. Yeah. So now it's writing uh the
[00:11:31] HTML. Uh it'll probably take a little
[00:11:33] while because uh that's uh usually a lot
[00:11:35] of content to write. Uh so uh let's see
[00:11:38] what I um maybe uh one thing I can show
[00:11:40] here um is that uh while the agents are
[00:11:42] working uh typically agents either
[00:11:44] coding or planning can spend quite some
[00:11:47] time doing this work. Um so what I do is
[00:11:49] I'll just spin up another parallel uh
[00:11:51] terminal tab uh a window right I use
[00:11:54] t-mox so this is a new t-mox window um
[00:11:57] and in this window I will do something
[00:11:59] else um and we can see it's in the same
[00:12:02] directory the problem here is that uh if
[00:12:04] I spin up another agent to work in the
[00:12:07] same directory they will run into each
[00:12:09] other right so what this agent does in
[00:12:11] this session will like step on toes of
[00:12:14] the other agents that were that's
[00:12:16] already doing the work um Yeah.
[00:12:18] >> So this is where people uh started using
[00:12:20] work trees. So typically people uh what
[00:12:23] people do is like get work tree ad and
[00:12:25] give another directory uh like high bits
[00:12:28] and spend like five minutes thinking
[00:12:30] about the name. Uh but I'm just going to
[00:12:31] say h high high bit too. Um so the the
[00:12:35] thing the problem with this approach is
[00:12:37] that once I create a work tree like this
[00:12:40] next time I come to this work tree I
[00:12:42] have to think about what is hybrid 2
[00:12:44] doing uh like what is this this work
[00:12:46] tree doing right is it still being
[00:12:48] worked on is it like okay to like use
[00:12:51] for something else it's very hard to
[00:12:53] keep track of
[00:12:55] >> um and the other problem is like when we
[00:12:56] create a new work tree the dependencies
[00:12:59] are not installed in the in the work
[00:13:01] tree. So in this work tree we have
[00:13:03] things like node modules right like
[00:13:05] these are dependencies downloaded on the
[00:13:07] fly and these dependencies won't exist
[00:13:10] in the new work tree until you install
[00:13:13] all of them again. Um so there were many
[00:13:15] problems like that
[00:13:16] >> and just for people who don't know like
[00:13:18] like what's our definition of the work
[00:13:19] tree is it like a copy of the codebase
[00:13:21] right or
[00:13:22] >> yeah yeah so a work tree is basically
[00:13:24] like you can think of it as a clone of
[00:13:26] your current uh git repo um in another
[00:13:30] directory. So it's going to be a
[00:13:31] parallel direct directory and they don't
[00:13:34] directly interfere with each other. Um
[00:13:36] so you can do um a different kind of
[00:13:38] work different set of work in the work
[00:13:39] tree and it won't affect what you were
[00:13:41] doing in the main repo.
[00:13:43] >> Okay. But but you're saying that there's
[00:13:44] like a many issues with the work tree.
[00:13:46] So what do you do instead?
[00:13:48] >> Yeah.
[00:13:48] >> Yeah. Basically there's a very heavy
[00:13:50] like cognitive load to maintain the work
[00:13:53] trees. You have to think about which
[00:13:55] work tree is which uh and which ones are
[00:13:57] okay to clean up etc etc. Um, so what I
[00:14:00] did was I have a tool called Treehouse.
[00:14:03] Uh, so Treehouse is basically like a a a
[00:14:06] no-brainer like uh a a very like dead
[00:14:10] simple way to manage work trees. Um, so
[00:14:13] every time I have to spin up a new work
[00:14:15] tree to do something new, right? I don't
[00:14:17] need to think about uh do I have another
[00:14:19] work tree I can use? Do I uh create a
[00:14:21] new one? I just type treehouse and
[00:14:23] treehouse will basically set up the work
[00:14:25] tree for me and drop me into the new
[00:14:27] work tree. Uh so now it you can see it's
[00:14:29] set up a work tree in this directory
[00:14:32] right and uh it dropped me into it and
[00:14:35] the the good thing is that this
[00:14:37] directory um is a is from a pool of
[00:14:40] managed work trees. So um so the
[00:14:44] dependencies are already installed here
[00:14:46] because I have used this work tree
[00:14:48] before um so I don't have to like
[00:14:50] reinstall dependencies rebuild the
[00:14:52] project every single time. Uh it also
[00:14:54] saves on the efficiency aspect. So yeah,
[00:14:57] just like reduce the mental load a lot.
[00:14:59] I don't need to think about anything. I
[00:15:00] just type treehouse every time I want to
[00:15:02] start a new session.
[00:15:03] >> That makes sense. Okay. All right, dude.
[00:15:05] Well, let's go back to the other tab.
[00:15:07] >> Yeah. So this is uh what's the HTML
[00:15:09] looks like. Um so it's saying, hey, uh
[00:15:13] redesign discussion. Uh it's basically
[00:15:15] there's a tiny icon here, not available.
[00:15:18] Not sure what happened there, but u
[00:15:20] basically it's uh it wrote the proposal
[00:15:23] in in a visual artifact, right? Um, so
[00:15:27] what's going what's feeding off? The
[00:15:29] screen is doing like grown-up work in
[00:15:31] kids space. Exactly. Right. Um, and
[00:15:34] these things uh there's uh unused space.
[00:15:37] Um, yeah.
[00:15:38] >> This is easier to scan and read for a
[00:15:41] human basically.
[00:15:42] >> Yeah.
[00:15:43] >> Yeah. Yeah. And uh if if there's
[00:15:45] something I uh I look at the uh this
[00:15:47] artifact and I if I see something that
[00:15:50] doesn't feel right, I can just annotate.
[00:15:52] Um so bit has no visible body. I can say
[00:15:55] I just click on this and say I don't
[00:15:58] care about this. Um and give the
[00:16:01] feedback to the agents this way. Um
[00:16:03] >> Oh, I see. So this is your app. Okay.
[00:16:05] Got it. Okay, that makes sense.
[00:16:06] >> Yeah. So this is a lot more difficult to
[00:16:08] do when it's a long wall of text, right?
[00:16:11] Uh when it's a wall of text, you have to
[00:16:13] say to the agent, hey, I I I I don't I'm
[00:16:16] not happy about this part of the spec.
[00:16:18] Uh and you sometimes have to copy paste
[00:16:20] a lot.
[00:16:21] >> Got it.
[00:16:21] >> Yeah. So it basically proposed a bunch
[00:16:23] of things. Uh, copy, clean up. Uh,
[00:16:27] >> yeah, some of the layout things is not
[00:16:29] ideal, but yeah, I I get it. It's it's
[00:16:31] easier to read for sure. Yeah.
[00:16:32] >> Yeah. And I I I think there's probably
[00:16:34] like something that went wrong in this
[00:16:36] uh page. Uh, let me let me let me just
[00:16:38] check. Uh, I can just ask the agent as
[00:16:41] well. Um, because uh when I look at
[00:16:43] this, I think the agent is trying to
[00:16:44] give me a visual representation of the
[00:16:47] layout. Um, but because of the CSS is
[00:16:49] not quite working or something. Um, it
[00:16:52] seems the CSS styles uh not working. Let
[00:16:58] me fix it. Um, so yeah, I can just send
[00:17:01] feedback back to the agent uh this way
[00:17:03] and um I don't have to keep switching
[00:17:05] between the HTML artifact and the agent
[00:17:08] uh in the terminal. Uh I can just talk
[00:17:10] to the agent here. Um and I can easily
[00:17:13] annotate everything uh and just point uh
[00:17:15] the pinpoints exactly where I mean.
[00:17:18] >> Can you show folks where they can
[00:17:20] download this tool? It's it's open
[00:17:21] source, right?
[00:17:22] >> Uh so it's uh in my GitHub repo lavishi
[00:17:28] uh in this repo. Uh and it has uh it's
[00:17:31] actually very simple uh to start using
[00:17:34] it. Just tell your agent use npx lavish
[00:17:37] axi to write the technical plan or do
[00:17:39] whatever you want.
[00:17:41] >> Um and the agent will go uh invoke this
[00:17:43] and everything goes on from there. And
[00:17:46] uh you have to do you have to hook up
[00:17:47] your own uh API key for the LM?
[00:17:50] >> No, you you just use whatever agent you
[00:17:52] are already using. Um this lavish editor
[00:17:55] itself does not uh run another agent.
[00:17:58] >> Uh it runs within your agent session. So
[00:18:01] actually
[00:18:01] >> Okay, got it.
[00:18:02] >> Yeah. So you can see here um the agent
[00:18:05] calling lavish axi uh to pull like this
[00:18:08] uh this artifact.
[00:18:09] >> Okay, that makes sense.
[00:18:11] >> So let's come back to it. Um yeah. So,
[00:18:13] so now uh it fixed the CSS problem,
[00:18:16] right? This is what what is supposed to
[00:18:18] look like. Uh so you can see like this
[00:18:20] is a lot uh like more visual and easier
[00:18:23] to understand.
[00:18:24] >> Looks a lot better. Yeah.
[00:18:26] >> Yeah. So this is like pointing out the
[00:18:27] current layouts, current uh problems and
[00:18:30] then uh it's probably like proposed a
[00:18:33] new thing. Okay. So it proposed four
[00:18:35] directions for using the space better.
[00:18:38] Option A looks like this. This is like
[00:18:41] this is so much easier to see, right?
[00:18:44] Like than like the long wall of text we
[00:18:46] have in the uh in the uh terminal. Um so
[00:18:50] here we can see okay it's uh moved the
[00:18:52] layout a little bit. Uh now this is the
[00:18:54] chat this is some other area. Okay
[00:18:56] that's one option.
[00:18:57] >> Um and it even gave me buttons. So uh if
[00:19:01] I like option A I can just click this
[00:19:03] button and I get the option A. Um got
[00:19:05] it. So option B looks like this. Uh
[00:19:08] today's goal. Okay. Um, option C, uh, is
[00:19:12] this. Okay. Option C is very simple. I
[00:19:14] actually like this. Um, option D. Okay.
[00:19:18] Yeah. So, let's say I like option C. I
[00:19:21] can just click this
[00:19:22] >> and it basically killed a uh a piece of
[00:19:25] feedback to the agent saying I like
[00:19:27] option C. Um, so it's just so easy to
[00:19:29] interact with. Um, I don't have to keep
[00:19:31] typing uh every time I want to tell the
[00:19:33] agent something. Everything can be done
[00:19:35] interactively.
[00:19:36] >> Okay. Okay. So, and and this is uh the
[00:19:38] plan phase for like building a new
[00:19:40] feature on top of an existing app,
[00:19:42] right?
[00:19:42] >> Yeah.
[00:19:43] >> I'm curious and maybe not to show this,
[00:19:44] but I'm just curious like how you plan
[00:19:46] something from scratch initially. Like
[00:19:47] did you like spend a lot of time
[00:19:49] planning like the the milestones and the
[00:19:51] tech stack and that kind of stuff?
[00:19:53] >> Yeah. Yeah. So, if it's something from
[00:19:55] scratch, uh I usually have to spend a
[00:19:57] little bit more time. Um so, what I do
[00:19:59] is that I use the same lavish editor.
[00:20:02] Um, I tell the agent that I I want to
[00:20:05] brainstorm a new idea with you. Um, and
[00:20:08] uh, I'll probably like talk through some
[00:20:10] of my initial thinking for what things I
[00:20:13] think um, are the core parts of my idea.
[00:20:16] And then I'll ask the agent to um,
[00:20:18] criticize that and uh, come up with like
[00:20:21] areas of risks uh, or weaknesses I
[00:20:24] haven't uh, may uh, maybe I haven't
[00:20:26] thought through yet. Um, and then come
[00:20:28] back with it uh, its opinion. Um and the
[00:20:31] agent will then come back with a uh HTML
[00:20:34] artifact like that and I can look at the
[00:20:36] artifact to uh basically like work with
[00:20:39] the agent to refine the idea to a point
[00:20:42] where it becomes a spec basically.
[00:20:44] >> Do you always like include some certain
[00:20:45] sections in your spec like build it in
[00:20:47] three phases or like here's the
[00:20:49] milestones or like here's a tech tech
[00:20:51] stack I want you to use like that kind
[00:20:52] of stuff.
[00:20:53] >> Yeah. Yeah. So uh for some projects, for
[00:20:55] some ideas, I already have uh some uh
[00:20:58] opinions on things to use and things to
[00:21:00] do. Uh in those cases, I'll just write
[00:21:02] them down and say these are my
[00:21:04] preferences. Um but I always tell the
[00:21:06] agents that it's okay for you to push
[00:21:08] back if you see something that is not
[00:21:10] right. Um because I want to give the
[00:21:13] agents the flexibility and I want to see
[00:21:15] more options as well. Um so yeah, I I I
[00:21:17] basically like give my ideas to the
[00:21:19] agents uh but let the agents give more
[00:21:21] back. So, so then do you have like a
[00:21:23] user level agent.mmd or something that
[00:21:25] like uh has some of these best practices
[00:21:28] like you know you can push back on me or
[00:21:30] it's just more natural through the
[00:21:31] conversation?
[00:21:32] >> Yeah. Uh so I um I actually built a lot
[00:21:35] of those instructions into uh lavish
[00:21:38] editor.
[00:21:39] >> Um so whenever the agent is is using uh
[00:21:41] the lavish editor to work with me, the
[00:21:44] agent already knows uh a lot of those um
[00:21:46] like those best practices.
[00:21:48] >> Got it. Okay. And how about how about
[00:21:50] like uh if you're building like a userf
[00:21:51] facing product, how do you think about
[00:21:53] the design? Do you have like another
[00:21:54] tool for design or you just you have
[00:21:56] some skills?
[00:21:57] >> For design uh you mean visual design?
[00:21:59] >> Yes.
[00:22:00] >> Yeah. So for visual design, I like cloud
[00:22:03] design a lot. Um since it came out, I
[00:22:06] use that a lot. Uh and uh very often I
[00:22:08] I'll use a lot of the quota they have uh
[00:22:10] for me. So if you look at this uh this
[00:22:13] this bar where I track my quota um cloud
[00:22:17] I mostly used up my weekly quota already
[00:22:19] I'm waiting for the reset and cloud
[00:22:22] design I used um like uh twothirds of it
[00:22:26] um okay because I yeah I just find it
[00:22:28] very useful to um especially for new
[00:22:30] projects I use this a lot to build a new
[00:22:33] design system um because once I get the
[00:22:36] design system built I can apply that to
[00:22:39] many many different components in my
[00:22:41] project uh very easily.
[00:22:42] >> Yeah. Okay. May maybe you can show that
[00:22:44] later later, but why don't why don't we
[00:22:45] finish this work worker first? Yeah.
[00:22:48] >> Yeah. Cool. So yeah, we basically we
[00:22:49] chose option C, right? Um so now we can
[00:22:52] just say hey uh build option C now. Um
[00:22:56] and uh because we already have the plan
[00:22:59] uh written uh in the HTML artifacts, the
[00:23:02] agent already has the context on what
[00:23:03] that means and uh what's the choices uh
[00:23:06] were made. Uh right. So, uh, the agent
[00:23:08] can just like go ahead and, uh, and
[00:23:10] implement that. Now,
[00:23:11] >> how many like, uh, since you're just
[00:23:12] like building solo now at home, like how
[00:23:15] many of these agent building sessions do
[00:23:17] you have going? Like, like the agent
[00:23:18] actually building something for you at
[00:23:20] any given time like Yeah.
[00:23:21] >> Yeah. Yeah. So, I I like closed as many
[00:23:24] sessions as I could before I uh started
[00:23:26] this session. Uh, but uh, I typically
[00:23:29] have like at least uh five different
[00:23:31] sessions actively running. Um, and in
[00:23:34] each session there are usually like a
[00:23:36] bunch of sub agents uh or different uh
[00:23:38] agents working. Uh, so in total I never
[00:23:41] like really counted but I I would guess
[00:23:43] on average there's like 20 to 30 agents
[00:23:46] running.
[00:23:47] >> Okay, got it. Okay, so you mentioned you
[00:23:49] have sub agents running like you
[00:23:51] actually specifically ask it to run sub
[00:23:52] agents or like it just decides to like
[00:23:55] when when when do you actually need a
[00:23:56] sub agent versus just using one agent?
[00:23:58] >> Yeah. Yeah, great question. Uh so I
[00:24:00] think the u most of the models today uh
[00:24:02] and the harnesses they are not very
[00:24:05] great at proactively using sub aents. Um
[00:24:08] there are only a few cases where like
[00:24:10] cloud code or codeex will proactively
[00:24:12] use the sub aent. It's when like they
[00:24:14] have the their built-in agents like
[00:24:17] explore. Um so when you uh ask a complex
[00:24:20] question uh cloth code will often run a
[00:24:23] explore sub agent right to do some
[00:24:25] exploration in the codebase and come
[00:24:26] back with some investigation results. Um
[00:24:29] those are the cases where the models
[00:24:31] will proactively use a sub agent. But in
[00:24:33] a lot of cases uh because the models I
[00:24:35] think they are not trained uh enough yet
[00:24:38] to use sub aents in various different
[00:24:40] kind of cases you often have to prompt
[00:24:42] it to do so.
[00:24:44] >> Got it. Okay. What are some cases where
[00:24:46] you actually want to prompt it to use
[00:24:47] sub aents like to for like validation or
[00:24:49] >> Yeah. So um the reason uh I think the
[00:24:52] main reason I would use a sub agent is
[00:24:54] to avoid context um context window
[00:24:56] blowing up in the main agents uh
[00:24:58] session.
[00:24:59] >> Oh I see.
[00:25:00] >> Yeah. So uh what I uh what I do what I
[00:25:03] uh I think the time when I choose to use
[00:25:05] sub agents is when I realize what I'm
[00:25:07] about to do uh is going to use a lot of
[00:25:10] context and most of the context is going
[00:25:12] to be uh like investigation kind of
[00:25:16] exploration kind of uh scenario and most
[00:25:18] of the exploration may be not meaningful
[00:25:21] for the main session. Uh so in those
[00:25:23] cases uh basically I like carve out
[00:25:25] those sub agents to do those
[00:25:26] investigations and only come back with
[00:25:28] their conclusion. Okay. So it's like uh
[00:25:30] like hey spin up a sub agent to look at
[00:25:33] this codebase or do some research on
[00:25:34] this topic and summarize it and give it
[00:25:37] back to the main a agent like that kind
[00:25:38] of stuff right.
[00:25:39] >> Yeah. Yeah. Or like there are cases
[00:25:41] where I have like 10 experiments ideas
[00:25:44] to run and each experiment uh I each
[00:25:47] experiment can be done in isolation. Uh
[00:25:50] right so in those cases I also like just
[00:25:52] say uh hey like spin up 10 sub agents to
[00:25:54] do that. Um, if I do that all in the
[00:25:56] main agent, it's going to just like blow
[00:25:58] up the context window and take a lot of
[00:26:00] time and uh and uh tokens as well.
[00:26:02] >> When you say experiment ideas, you mean
[00:26:04] like like AB testing stuff or or or what
[00:26:07] like like different ways to build
[00:26:08] things?
[00:26:08] >> Yeah, so there are various kind of uh
[00:26:10] experiments I run. Uh there's one
[00:26:12] example here I can show. Um so this is
[00:26:14] one uh something I'm running. Uh this is
[00:26:17] the one I didn't uh kill. Um so this is
[00:26:20] a this is a a benchmark I'm running to
[00:26:24] evaluate the effectiveness of different
[00:26:26] programming languages when given to
[00:26:28] agents
[00:26:29] >> and uh there was this benchmark that
[00:26:31] were that was published like two weeks
[00:26:33] ago called program bench uh it's called
[00:26:35] program bench uh it's built by the same
[00:26:38] people that built Swebench um and it's
[00:26:41] their new thing and program bench
[00:26:42] basically ask the agents to build uh a
[00:26:46] bunch of programs like ffmpeg
[00:26:48] like these tools from scratch and see
[00:26:51] whether the agent can actually get all
[00:26:53] the requirements done uh and pass all
[00:26:56] the test cases.
[00:26:57] >> So that is the that was the benchmark.
[00:26:59] Um but I thought the benchmark can be
[00:27:01] very useful for evaluating different
[00:27:04] harness uh harness techniques and also
[00:27:06] different uh programming languages. Uh
[00:27:08] so right now what I'm evaluating here is
[00:27:11] I'm I'm running program bench on codeex
[00:27:14] and I I force codeex to use these
[00:27:18] programming languages like typescript,
[00:27:20] javascript, python and see when they use
[00:27:23] different languages do they get
[00:27:25] different results right uh is there a
[00:27:27] programming language that will that will
[00:27:29] lead to the agent getting uh more
[00:27:32] requirements done and passing more tests
[00:27:34] and use less tokens etc etc. Um so so
[00:27:38] this is a very large amount of uh
[00:27:40] experiments. Um basically like there are
[00:27:42] um like 200 multiplied by uh eight right
[00:27:48] uh so there's that that's a lot of
[00:27:49] things to run and in those cases I I
[00:27:52] basically like have sub agents uh
[00:27:53] running and uh if I run all these in a
[00:27:56] single main agent it's just going to
[00:27:58] keep running compaction and uh not going
[00:28:00] to be very efficient.
[00:28:01] >> That makes sense. Okay cool. Let's go
[00:28:02] back to the kit.
[00:28:03] >> Yeah. So it looks like it's running a
[00:28:06] bunch of tests right now, right? So like
[00:28:07] is that just the model knows to run
[00:28:09] tests or you actually you have some
[00:28:10] instructions to have it built unit test
[00:28:12] and stuff like that each time?
[00:28:15] >> Yeah.
[00:28:15] >> Uh I typically um in my um agents MD in
[00:28:19] each project I I will like have some
[00:28:21] instructions for how to uh perform
[00:28:24] tests. Uh so uh here for example
[00:28:27] uh I can show the agents MD here. So in
[00:28:31] this is the agents MD for the high bit
[00:28:33] project uh we were looking at. Um and in
[00:28:35] here we'll just have some like high
[00:28:37] level context on the structure of the
[00:28:39] project. Um and then I'll have some uh
[00:28:41] testing instructions. This is actually
[00:28:44] super helpful. Um so previously I didn't
[00:28:47] do this and I let the agent decide what
[00:28:49] to do and the agent will just do the
[00:28:51] like kind of do the minimum. Um and uh
[00:28:54] they they they are trained to run some
[00:28:56] basic testing uh but they are not going
[00:28:58] to be comprehensive enough. Um so I have
[00:29:01] here is like instructions for how to do
[00:29:03] end to end testing. This is important
[00:29:05] for like building uh front end and UI
[00:29:08] kind of projects. Uh right we were
[00:29:11] looking at hybrids which had a GUI. Um
[00:29:13] so in this case I tell the agents hey uh
[00:29:18] this is a electron app you can drive
[00:29:20] this uh this app by running a browser
[00:29:24] and uh and blah blah blah how to do this
[00:29:27] testing how to actually test things end
[00:29:28] to end. So with that instruction here
[00:29:31] the agent will uh will like just once
[00:29:34] it's done its work it will actually
[00:29:36] validate things end to end for me. Um,
[00:29:38] so that can save me a lot of time from
[00:29:40] like running the app myself and visually
[00:29:43] validating is that actually what I want.
[00:29:46] >> Okay. So it's basically like uh using
[00:29:47] browser use and checking out the app,
[00:29:49] see if it looks okay. Maybe checking
[00:29:50] some browser errors.
[00:29:52] >> Yeah, exactly.
[00:29:53] >> Yeah. And take screenshots as well. Take
[00:29:55] screenshots and look at these things
[00:29:56] visually and see whether it's actually
[00:29:58] aligned with what we talked about. I
[00:30:00] think if you use the codeex app, I I
[00:30:02] think it does it by default, but like
[00:30:05] let's say like I'm not very technical,
[00:30:06] like how do I even know to include this
[00:30:08] stuff? Should I just tell the agent to
[00:30:10] run a lot of tests or
[00:30:11] >> Yeah. Yeah. Yeah. So typically um what I
[00:30:14] uh one thing I one thing that's really
[00:30:16] interesting I found is that
[00:30:18] >> uh by default the agents like to write
[00:30:20] unit test like very uh purely uh code
[00:30:24] based unit tests and those unit tests
[00:30:27] often don't actually validate things end
[00:30:29] to end. So for example uh even in codeex
[00:30:32] I think codeex by default likes to use
[00:30:34] the builtin uh inapp browser right?
[00:30:37] >> Yeah. Um so when you work on some front
[00:30:39] end changes uh it will use the inapp
[00:30:42] browser to uh look at the change and uh
[00:30:45] have you look at that as well. Um but
[00:30:47] this is an electron app. It's a desktop
[00:30:49] app. So it actually requires a different
[00:30:51] set of uh yeah facilities to validate
[00:30:54] that. Um so the instructions here are
[00:30:57] basically how I would test this thing
[00:31:00] myself.
[00:31:01] >> Um
[00:31:01] >> okay.
[00:31:02] >> Yeah. So basically like the more um the
[00:31:04] more things uh that I find myself doing
[00:31:07] that I can delegate to an agent, I turn
[00:31:09] them into instructions and then let the
[00:31:12] agents do the work uh instead of me like
[00:31:14] operating the app myself manually.
[00:31:16] >> Okay. Got it. Okay. So so I guess like
[00:31:18] someone who maybe is not as
[00:31:19] knowledgeable as you can just like like
[00:31:21] I guess a general principle is like if
[00:31:22] you're doing something manually like
[00:31:24] you're manually opening the app and
[00:31:25] looking at the screens just ask the
[00:31:27] agent, hey can you just auto automate
[00:31:29] this for me, right? just just ask it and
[00:31:31] hopefully it can figure some something
[00:31:32] out too.
[00:31:33] >> Yeah. Yeah. So yeah, if you are like not
[00:31:34] trying to dig into the technical
[00:31:36] details, uh then the principle the high
[00:31:37] level principle is like if you find
[00:31:40] yourself manually doing something, then
[00:31:42] try to turn that into something the
[00:31:44] agent does for you. Um and you can very
[00:31:47] likely like with today's models, you can
[00:31:49] very likely just ask the agent um to
[00:31:52] like to do what you were trying to do.
[00:31:54] Uh and the agent will figure out, oh, I
[00:31:56] should do this, I should do that.
[00:31:57] >> All right. Well, it looks like it's done
[00:31:59] now in
[00:31:59] >> Yeah, it's done now. So, uh, so now,
[00:32:02] good question, right? Like it's done.
[00:32:04] The agent says it's done and we can look
[00:32:05] through what it did, right? It said it
[00:32:08] changed this, change that. How do we
[00:32:10] know this is actually, uh, a good
[00:32:12] change, right? How do we know there's no
[00:32:14] like bugs and everything? Um, so the
[00:32:16] validation phase is where um, like I see
[00:32:18] a lot of people spend a lot of their
[00:32:20] time. Um so the default approach is like
[00:32:23] people will open up their IDE and start
[00:32:25] to review the code like they will start
[00:32:27] to review the diff right. Yeah.
[00:32:29] >> Um but the the thing is that uh AI can
[00:32:33] write so much code. Um so if you review
[00:32:35] every single line of code you become the
[00:32:37] bottleneck.
[00:32:38] >> Um so what I do here is I I don't even
[00:32:41] review the code. Um
[00:32:43] >> I don't review this uh this first pass
[00:32:45] code from the agent. I use something I
[00:32:48] call no mistakes. Um, so no mistakes is
[00:32:51] another tool I built uh just to help uh
[00:32:54] make this part of the uh my life easier.
[00:32:57] Um so what it does I I'll show you. Um I
[00:33:00] actually made a um alias uh so every
[00:33:02] time I got some change uh like some code
[00:33:04] changes done from the agent I just nm
[00:33:06] and uh it will go through a few steps.
[00:33:09] First it will uh ask the agent to create
[00:33:12] a branch for me. Um so I don't even need
[00:33:14] to think about the branch name. Um
[00:33:16] otherwise I need to think about the the
[00:33:18] branch name the commit message like I
[00:33:20] all those things just f it's just
[00:33:22] wasting time um and I get the agent do
[00:33:25] that the agent basically did that fix
[00:33:27] kit chat workspace that's right right
[00:33:30] >> um and the agent is now analyzing my
[00:33:33] session to understand my intent um so
[00:33:36] the the agent here uh no mistakes is
[00:33:39] reading the session uh where we did the
[00:33:41] work to understand my intent uh so now
[00:33:43] it's understood what I I was trying to
[00:33:46] it will do the all these steps for me.
[00:33:48] Uh so it will rebase my change on top of
[00:33:50] the latest main branch on the remote. So
[00:33:53] there's not going to be merge conflict
[00:33:55] later on. Uh it's going to review my
[00:33:58] change. Uh so this is where uh I
[00:34:00] actually did a lot of um prompt
[00:34:02] engineering to get the agents to uh
[00:34:05] really scrutinize the change very very
[00:34:07] hard. Um
[00:34:09] >> okay. So any kind of edge case or bugs
[00:34:11] uh like uh logical errors things like
[00:34:13] that will get caught. Uh so this is a
[00:34:16] very very high recall um uh phase. I mo
[00:34:21] uh I when I initially built no mistakes
[00:34:23] I did uh a lot of parallel testing where
[00:34:26] I let the agents review the change and I
[00:34:28] also review the change myself and see
[00:34:31] how often I catch something the agents
[00:34:33] uh don't right um and I use that phase
[00:34:36] to uh iterate on this uh the prompts and
[00:34:40] the uh the workflow within this phase so
[00:34:43] eventually I got to a point where I find
[00:34:45] myself never catching anything the
[00:34:47] agents don't catch Um so in in this case
[00:34:50] the agents act it actually didn't find
[00:34:52] any uh material problems uh so it's just
[00:34:55] passed but if if it found some problems
[00:34:58] uh it will uh categorize that into uh
[00:35:01] two categories.
[00:35:03] >> One is obvious bugs. So if it's a just a
[00:35:06] obvious error uh it will just autofix by
[00:35:09] itself. It won't even bother me.
[00:35:11] Another category is like when it
[00:35:13] realized there's an error but fixing the
[00:35:16] error will have some product
[00:35:18] implications. Um and then it will ask me
[00:35:21] instead of just autofixing that um so in
[00:35:24] those cases it will escalate to me and
[00:35:26] it will basically pause at this phase
[00:35:28] and ask me to uh judge do I actually
[00:35:32] want to make that fix or do I want
[00:35:33] something else.
[00:35:34] >> This is like the PR review basically the
[00:35:36] agent doing PR review right?
[00:35:37] >> Yeah. Yeah. a PR review between the
[00:35:39] agent and the author
[00:35:41] >> and this no mistakes is like a whole new
[00:35:43] context window, right? It's like a new
[00:35:44] agent looking at your other
[00:35:46] conversation.
[00:35:48] >> Yes. Uh so this is a fresh context
[00:35:50] window and uh and actually did that
[00:35:53] deliberately. Um I think that's an
[00:35:54] important thing to do which is to use a
[00:35:57] fresh context window to review the
[00:35:58] change that was done. uh because uh a
[00:36:00] lot of people what they do is like they
[00:36:02] will just ask hey can you review the
[00:36:05] change uh in the same session uh when
[00:36:08] you do that the agent is very heavily
[00:36:10] biased by what was already done um
[00:36:13] because it it it saw all the context uh
[00:36:15] it saw every every step along the way so
[00:36:18] it's biased into believing that what was
[00:36:21] done was correct um and it will because
[00:36:24] of that it will sometimes miss something
[00:36:27] um so if you uh I I I tested this a lot.
[00:36:30] Um, and when you use a fresh context
[00:36:31] window, you get just get a lot more edge
[00:36:33] cases caught.
[00:36:34] >> I guess the only problem is like uh the
[00:36:36] no mistakes agent has to does it have to
[00:36:38] look at your whole code base again to
[00:36:39] even understand what this app is about.
[00:36:41] >> Uh, that's what this intent face was
[00:36:43] doing. Uh, so it basically analyzed your
[00:36:45] session uh to understand what was your
[00:36:48] original intent and uh some of the
[00:36:50] surrounding context as well.
[00:36:52] >> Um, but it's not copying the entire
[00:36:54] session uh into this new context window.
[00:36:57] It's like it's like you know like some
[00:36:59] senior engineer builds some feature and
[00:37:00] then you're asking the principal
[00:37:01] engineer to come in with fresh fresh
[00:37:03] eyes to look look through everything
[00:37:05] right
[00:37:06] >> yeah with fresh eyes but you usually you
[00:37:08] will ask the senior engineer to explain
[00:37:10] a little bit of context to the principal
[00:37:12] right
[00:37:13] >> that's right yeah
[00:37:14] >> yeah so this intent phase is basically
[00:37:15] that it's basically like explaining the
[00:37:18] basic context of what this change is
[00:37:20] trying to do
[00:37:21] >> okay and why don't we walk through the
[00:37:23] rest of the phases too like um
[00:37:24] documenting is what is writing what is
[00:37:27] obser observing.
[00:37:28] >> Yeah. So, yeah. So, each phase what it
[00:37:30] does is like review is just reviewing
[00:37:32] the code. Um, and test is running tests.
[00:37:35] Um, and the test phase is very different
[00:37:37] from what the agent does by default. Um,
[00:37:40] so the agent what the agent does by
[00:37:42] default is running some tests. Um, and
[00:37:45] uh validating locally like uh was the
[00:37:48] change um was the change tested and was
[00:37:51] that working. Um, but this test phase is
[00:37:54] a little bit different. is more like CI
[00:37:56] um it's validating did this regress
[00:37:58] other things as well uh etc etc and uh
[00:38:02] this test phase will actually present
[00:38:03] some evidences uh evidences of uh the
[00:38:07] change actually working it will paste
[00:38:09] screenshots or like sometimes a video to
[00:38:12] capture this thing is actually working
[00:38:14] so it's easier for me to review I can
[00:38:16] just look at uh the artifact and see oh
[00:38:20] okay it's actually working
[00:38:21] >> oh that that's actually really
[00:38:22] interesting so yeah because sometimes
[00:38:24] when I shift stuff with codeex like the
[00:38:26] stuff I'm shipping works but then it
[00:38:27] breaks some something else it breaks
[00:38:28] like another core work workflow in the
[00:38:31] app
[00:38:31] >> so so this test base will actually look
[00:38:34] through all that and try
[00:38:35] >> yeah it look through all that yeah and
[00:38:37] uh just like present very easily
[00:38:39] digestible artifacts for me to like have
[00:38:42] confidence it's actually working as I
[00:38:43] expected
[00:38:44] >> this is maybe a dumb question but like
[00:38:46] for example I'm I'm trying to build like
[00:38:47] a fitness app right and like and like
[00:38:49] there's like a few core workflows that I
[00:38:51] want to make sure that it tests each
[00:38:52] time like creating a workout tracking
[00:38:54] your workouts, you know, like so like do
[00:38:56] you do you have to manually define the
[00:38:58] stuff or is the AI enough smart enough
[00:39:00] to figure it out
[00:39:02] >> to to test the stuff each time you make
[00:39:03] a change?
[00:39:04] >> Yeah. Yeah. Yeah. I typically like try
[00:39:06] to get AI uh the agent to turn those
[00:39:09] things into an automated end to end
[00:39:11] test.
[00:39:12] >> Okay.
[00:39:12] >> Um Yeah. Because then it will be very
[00:39:14] easy to run that every single time,
[00:39:16] right?
[00:39:16] >> And the automated end to end test is
[00:39:18] basically just like it uh lastly is like
[00:39:20] a browser app. So it it just kind of
[00:39:21] like actually beat the user and click
[00:39:23] click through stuff, right? and see if
[00:39:24] see if anything breaks.
[00:39:25] >> Yes. Yes. Uh so there are various kind
[00:39:27] of like end to end browser testing tools
[00:39:29] like playright. Um so but but yeah you
[00:39:32] can just ask the agent uh you can say
[00:39:34] hey like write an end toend test uh for
[00:39:37] this scenario or this user work uh this
[00:39:39] user flow and make sure it's actually
[00:39:42] working end to end. Uh it will typically
[00:39:43] be able to figure out what kind of
[00:39:45] frameworks or tools uh that needs to be
[00:39:46] used. I think the trade-off here, dude,
[00:39:48] is like it just takes a lot longer to
[00:39:51] actually ship a feature, right? Because
[00:39:54] [laughter]
[00:39:54] you're running all all these stages. But
[00:39:56] but I guess you have way more confidence
[00:39:57] that the feature you ship actually
[00:39:58] doesn't break anything. So So I guess if
[00:40:00] you're like if you have a lot of users
[00:40:02] because a lot of stuff I work on don't
[00:40:04] doesn't have any new users. It's just
[00:40:05] me.
[00:40:07] >> But if you have a lot of users that you
[00:40:08] ship the product, you want to make sure
[00:40:09] it actually works, right? It's like
[00:40:11] software engineering 101.
[00:40:13] >> Yeah. So I I I would argue like even if
[00:40:15] it's only for yourself, uh like probably
[00:40:18] you can make the trade-off, right? How
[00:40:19] much you want to u prefer just making
[00:40:22] changes very fast versus making sure
[00:40:25] things actually work. Um because
[00:40:26] sometimes there's like a little bit of a
[00:40:28] cost to you as well if things broke. Um
[00:40:31] yeah, so um yeah, so this uh this phase
[00:40:34] taking uh longer time is actually okay
[00:40:37] because I never look at this like I I I
[00:40:40] never uh just stare at this screen and
[00:40:42] uh wait for every phase to pass, right?
[00:40:45] Every time I uh launch no mistakes, I
[00:40:47] just immediately switch to another
[00:40:49] session.
[00:40:49] >> Uh like I I don't even look at this. Um
[00:40:52] what I uh have here um I I'll show you
[00:40:55] now. I switch to another session, right?
[00:40:57] I can just look at the terminal screen
[00:40:59] here to see what phase uh is that no
[00:41:02] mistakes pipeline uh at. So I can see
[00:41:05] it's working on the linking pipeline and
[00:41:07] if it's like if it's uh waiting for me
[00:41:10] uh to like make a judgment or something
[00:41:12] it will change the status here. So I can
[00:41:14] just like very easily see do I need to
[00:41:16] jump back into that session.
[00:41:18] >> Do you run no mistakes after like almost
[00:41:20] every change or or like if because if
[00:41:22] you do that then why don't just
[00:41:24] automatically run it.
[00:41:25] >> Ah yeah yeah. So uh I run that on most
[00:41:28] changes but not not every single one
[00:41:30] because there are changes where uh for
[00:41:32] example I make a very simple
[00:41:34] documentation updates and I know like it
[00:41:37] doesn't need like so much validation. Uh
[00:41:39] it's going to use a lot of my tokens as
[00:41:41] well. So I make some judgments on
[00:41:43] whether the change just justifies this
[00:41:45] kind of a heavy validation phase. Yeah.
[00:41:47] It's kind of like Yeah. When you work
[00:41:49] within a team and some of your changes
[00:41:52] don't like it's not that every PR will
[00:41:54] go to a QA team, right? Yeah,
[00:41:56] >> only some like milestones, some
[00:41:58] meaningful things will go there.
[00:41:59] >> Dude, do you think it feels weird like
[00:42:01] after spending you know your career in
[00:42:03] big tech? Because in big tech when you
[00:42:05] push a change, you have like a teammate
[00:42:06] come and review your PR, right? And then
[00:42:08] you run some t tests and and now you're
[00:42:10] just by by yourself. So it's like
[00:42:12] [laughter] so so I guess like you have
[00:42:14] all these agents, but like like how do
[00:42:16] you feel like do you feel like
[00:42:18] unshackled or or do you feel like uh you
[00:42:20] kind of miss the teammates?
[00:42:22] >> I uh so it's a bit of both. Uh but I
[00:42:24] would say like uh largely speaking I
[00:42:27] feel liberated.
[00:42:28] >> Liberated.
[00:42:29] >> Yes. Uh so I I think uh teammates are
[00:42:32] great uh especially in the brainstorming
[00:42:34] phase. Um so when we are like thinking
[00:42:37] about an idea if it's just me uh it's a
[00:42:41] very like it's not a very diverse
[00:42:43] perspective, right? So I may not think
[00:42:45] through everything and I may not realize
[00:42:47] problems others can see. Um, AI can help
[00:42:50] to a degree, but I don't think AI is
[00:42:52] like quite there yet to replace uh like
[00:42:55] a really smart team that uh can ideate
[00:42:58] together. Um, so that is like one the
[00:43:01] part I miss. The part I don't quite miss
[00:43:03] is like everyone is busy and if I write
[00:43:06] like 20 PRs every day, no one's going to
[00:43:09] reveal that. Um, so yeah, that already
[00:43:12] happened before I uh left my uh last
[00:43:15] company. And what I uh found myself
[00:43:18] doing was like I I have to write less
[00:43:21] PRs. Um Got it. And spend my time
[00:43:25] elsewhere because the bottleneck is like
[00:43:27] really on on the rest of the team.
[00:43:28] >> Yeah. Because the your teammates aren't
[00:43:30] actually reviewing the PRs. Like they
[00:43:32] don't have to have a lot of things going
[00:43:33] on, but like if you submit a PR to AI,
[00:43:35] it's always going to start work working,
[00:43:37] >> right?
[00:43:37] >> Yeah. So this is something that I think
[00:43:39] uh is going to like fundamentally change
[00:43:41] uh as we progress on AI adoption. Um so
[00:43:45] our workflows and how our teams work
[00:43:48] were built uh at a time when we spent
[00:43:52] most of our time coding and uh the
[00:43:55] average stats of like a average software
[00:43:58] team an engineer is like an engineer
[00:44:01] will write 10 to 15 PRs every month.
[00:44:04] That's like the velocity of an average
[00:44:06] software engineer uh team. So um when
[00:44:09] that's the case uh you spend like it's
[00:44:12] okay for everyone else to do code
[00:44:14] reviews and all these uh processes
[00:44:16] because the velocity is not that that
[00:44:18] massive
[00:44:19] >> but when you um when you start to write
[00:44:21] like 10 times more PRs we are not ready
[00:44:24] for that like our processes and our um
[00:44:27] like human team composition and
[00:44:29] everything is not built with that
[00:44:31] assumption in mind. So what's going to
[00:44:33] happen is like uh things are starting to
[00:44:35] break. A lot of teams are starting to um
[00:44:39] change their practices in order to fight
[00:44:41] that. Um so some teams es especially
[00:44:44] smaller teams in startups they basically
[00:44:47] stopped doing PR reviews. Um they still
[00:44:49] raise a PR but mostly for like a
[00:44:52] formality or for like leaving a record
[00:44:55] they don't actually wait for another
[00:44:57] peer to review. um they sometimes just
[00:44:59] merge the PR and later on if there's a
[00:45:01] problem they can go back to it. Uh
[00:45:03] that's the kind of changes I'm starting
[00:45:04] to see.
[00:45:05] >> Yeah, they they get the agents to
[00:45:06] review, right? I do think it does lead
[00:45:08] to like a little bit more unstable uh
[00:45:10] products. Yeah. Um but you know
[00:45:12] >> uh that's because they are not using no
[00:45:14] mistakes. [laughter]
[00:45:17] >> Yeah, it looks like it's done.
[00:45:19] >> Yeah, this pipeline just completed. Uh
[00:45:20] right. So uh it went through all these
[00:45:22] steps. uh and uh there was actually one
[00:45:25] thing fixed in documentation phase. This
[00:45:27] is uh yeah this is something I uh we can
[00:45:30] look at whether uh it's actually a legit
[00:45:32] change but um this is something I find
[00:45:34] super useful and something both me and
[00:45:37] my agents often don't do automatically.
[00:45:40] Um so it's like when you make a change
[00:45:42] can you actually find all the places uh
[00:45:45] in our documentation that can be
[00:45:48] affected by that change?
[00:45:49] >> Okay, got it.
[00:45:50] >> Yeah. So documentation linting uh and
[00:45:53] push and create a PR. So I can just open
[00:45:55] up the the PR and uh let's look at what
[00:45:58] it does. So it created this PR. Uh the
[00:46:00] PR summarized uh the intent uh that was
[00:46:03] understood from my original session in
[00:46:06] open code. Uh it summarized what
[00:46:08] changed. Uh it did a risk assessment as
[00:46:10] well. Um so like what this is very
[00:46:12] useful as well. uh when I look at a
[00:46:14] lowrisk change I spend less time when
[00:46:17] the agent is flagging this is a medium
[00:46:19] risk or high risk change I spend more
[00:46:21] time on this PR right so I can like
[00:46:24] decide where I spend my time more uh
[00:46:27] intelligently um so uh and testing uh
[00:46:31] yeah it did some test it had had a
[00:46:33] evidence uh so let's see what this is
[00:46:36] uh it renders the workspace
[00:46:39] okay yeah basically like the um this
[00:46:42] evidence uh is uh is about presenting
[00:46:44] like actual results um from the change.
[00:46:48] Uh so uh we can look at this and see is
[00:46:50] that what we want.
[00:46:51] >> Okay.
[00:46:51] >> Um and there is the pipeline and there
[00:46:53] is the documentation phase. Uh what did
[00:46:55] it find? Uh it found that the design
[00:46:58] system example copy was not updated.
[00:47:02] Okay. Yeah. So it actually it actually
[00:47:04] caught a inconsistency. Uh so that's
[00:47:07] great. Yeah. So, so because it's a
[00:47:09] lowrisk change, I don't even go into the
[00:47:12] diff here.
[00:47:13] >> I don't go there. Um, I I just merge it.
[00:47:16] >> Um, okay.
[00:47:16] >> And, uh, when it's a medium risk or high
[00:47:19] risk change, um, then I go into the diff
[00:47:21] and start to look at things myself.
[00:47:23] >> Okay. But you you pretty much uh always
[00:47:26] uh somewhat look at the PR, skim the PR,
[00:47:28] and then you hit the button to merge,
[00:47:30] right?
[00:47:30] >> Yeah. Yeah. I still look at this PR uh
[00:47:32] because I think looking through the risk
[00:47:34] assessment and uh what the agent
[00:47:36] actually did uh what was the fix uh
[00:47:38] those things are actually still useful.
[00:47:40] >> That's the mistake that I'm making,
[00:47:41] dude. I I don't look at the PR some
[00:47:43] sometimes. I just I just tell it to
[00:47:44] merge. [laughter] So I just need to be a
[00:47:47] little bit more thorough. Yeah.
[00:47:48] >> Also after the agent made some code
[00:47:50] changes, you just uh just get it merge.
[00:47:52] >> Well, I actually run some tests and
[00:47:54] stuff. I I don't use no mistakes and
[00:47:56] then I I I I get to merge and then um
[00:47:59] yeah, inherently like you know like a
[00:48:01] day later I'll find something else
[00:48:03] broke. So [laughter]
[00:48:04] yeah, it's it's probably not the most
[00:48:06] efficient way to do it. Yeah.
[00:48:07] >> Uh yeah. So yeah, I think some some
[00:48:09] validation and then some uh some like uh
[00:48:12] review, but it's not a line by line code
[00:48:15] review. I think some review on what's
[00:48:17] changed and um what um kind of risks
[00:48:20] exist. That's still useful. And and
[00:48:22] you're probably submitting 10 15 PRs a
[00:48:24] day, right? Or like doing doing this.
[00:48:27] >> Yeah. So I um I I uh actually do a lot.
[00:48:30] Uh so I um like [laughter]
[00:48:34] 26 uh 14 27 30. Yeah, that's like the
[00:48:37] average. Uh so it's uh yeah, most of the
[00:48:40] time it's like 22 40 kind of PRs every
[00:48:43] day. Sometimes I do more. Um like
[00:48:46] >> I can I can tell I can tell when when uh
[00:48:48] you became unemployed. It's like it's
[00:48:50] around March. very very very clear on
[00:48:52] this chart.
[00:48:53] >> All right. So that so I guess we just
[00:48:54] walked through the whole plan build and
[00:48:56] validation process, right? Like that's
[00:48:57] basically it, right?
[00:48:58] >> Yeah. So uh yeah, we went through like
[00:49:01] uh building a plan interactively uh
[00:49:03] implementing that with the agents and
[00:49:05] then going through this validation
[00:49:06] pipeline. Um this basically uh if you
[00:49:08] think about it, I didn't spend much time
[00:49:11] in the uh coding and validation phase at
[00:49:14] all. Right? Most of my time was actually
[00:49:16] on the HTML artifact iterating with the
[00:49:19] agent. Um so that's kind of how I um how
[00:49:21] I do these things now and as soon as I
[00:49:24] send the agent to do implementation I
[00:49:26] just switch to something else uh and
[00:49:28] work on that in parallel.
[00:49:29] >> Okay so I guess we we can provide the
[00:49:32] links to lavish the HTML PL planner and
[00:49:34] also no mistakes the validation uh we'll
[00:49:37] provide it in the description of this
[00:49:39] episode. Uh I guess let dude let me ask
[00:49:41] you one last question.
[00:49:42] >> Yeah
[00:49:43] >> I mean you you know you're like an LA
[00:49:45] engineer you've been doing this for a
[00:49:46] while. There's there's like a lot more
[00:49:47] builders now, right? Like there's a lot
[00:49:49] more people trying to get into this
[00:49:51] stuff and learning how to build a AI.
[00:49:53] >> Yeah.
[00:49:54] >> How do you think do you have any advice
[00:49:55] for people to actually ramp up the
[00:49:57] technical skills and and also like what
[00:49:58] kind of technical skills do they
[00:50:00] actually need to learn? Like obviously
[00:50:02] like testing and validating everything.
[00:50:04] Uh but also there's like there's like
[00:50:06] stuff like for example like if you don't
[00:50:07] set up your database properly in the
[00:50:09] beginning like it's harder to change it
[00:50:10] later. Just like just stuff that you
[00:50:11] learn over time. So, so like do you have
[00:50:14] any thoughts on how people can actually
[00:50:16] scale up as they build more stuff?
[00:50:18] >> Yeah. Yeah, good question. Um I I think
[00:50:20] there's a few things come to mind. One
[00:50:23] is that uh I think just play a lot. Um
[00:50:26] build a lot of things. Uh even if it's a
[00:50:28] throwaway toy, uh build it and through
[00:50:31] that process you will like often often
[00:50:33] discover things you can do better or
[00:50:36] things the agents didn't quite do very
[00:50:38] well and start to reflect on that. Uh so
[00:50:40] do think do a lot of things. I think
[00:50:42] that's like probably the first uh step.
[00:50:44] Um some people I think they uh what I
[00:50:47] see at least from some people is like
[00:50:49] they only they they spend a lot of time
[00:50:52] trying to decide what do they do and
[00:50:55] then uh they only do one thing and that
[00:50:57] thing didn't work. They then they stop.
[00:50:59] Um I think uh the mindset I would
[00:51:02] encourage is to just like build every
[00:51:04] single idea you have. Um whenever you
[00:51:06] have some idea um like send the prompt
[00:51:08] to the agent and see what it does. Um
[00:51:10] and um whenever like you you have some
[00:51:13] uh like inspiration or idea you you
[00:51:16] think might be interesting um just give
[00:51:18] that to the agent and have it run for
[00:51:20] you. Um I think through that like
[00:51:22] process uh a lot of learnings can be uh
[00:51:25] derived. Um that's one. Uh another I
[00:51:28] think is to um like try to challenge
[00:51:31] yourself to use like more tokens and run
[00:51:35] more agents in parallel. Um like I think
[00:51:38] that is a forcing function for people to
[00:51:41] like upgrade their workflow. Um because
[00:51:44] when we by default work with one agent
[00:51:46] uh at a time, we are still kind of like
[00:51:50] being a bottleneck. Uh we are putting
[00:51:52] ourselves into the loop too much. Um and
[00:51:55] I think to really scale up um how much
[00:51:57] we can get from the agents, we have to
[00:51:59] like move ourselves out of the loop as
[00:52:02] much as possible. Um, so that's like I
[00:52:05] think using more tokens and running more
[00:52:06] agents in parallel kind of forces us to
[00:52:09] do that. Um, that's probably like
[00:52:11] another uh thing I can think of. Um,
[00:52:14] >> got it.
[00:52:15] >> Yeah, maybe like the last thing is to uh
[00:52:17] like try to adopt AI in every part of
[00:52:20] your workflow, not only writing code.
[00:52:23] Um, so what we could see there like AI
[00:52:25] did a lot of validation and uh
[00:52:26] documentation all those things for me,
[00:52:28] right? And raising the PR and
[00:52:30] everything. I don't need to do anything
[00:52:31] there. Um I think um like when uh when
[00:52:34] we work through a project whenever we
[00:52:37] find something manual what we talked
[00:52:38] about earlier like something we are
[00:52:40] spending time ourselves just try to
[00:52:42] think about uh can we delegate that to
[00:52:44] the agent as well uh and through that uh
[00:52:47] people I think we'll find a lot more
[00:52:49] useful like workflows that can uh handle
[00:52:51] automation and reduce our workload.
[00:52:54] >> Yeah, maybe there's like some sort of a
[00:52:55] skill or like some something we can
[00:52:57] build where because the AI remembers uh
[00:52:59] it conversations with you. Like maybe
[00:53:01] the AI can actually proactively suggest
[00:53:03] like hey you should auto you should
[00:53:04] automate this. It's like the second time
[00:53:05] we're talking about this. Yeah,
[00:53:09] >> that exist that exists. So I can show
[00:53:11] you um okay
[00:53:12] >> so uh if I run cloud code
[00:53:15] >> cloud code has this slash command called
[00:53:17] insights.
[00:53:19] These insights will basically analyze
[00:53:21] your cloud code sessions and generate a
[00:53:23] report for what uh what can be done
[00:53:26] better like what can what what kind of
[00:53:28] skills can you uh add what kind of uh
[00:53:31] things can you tweak in your like memory
[00:53:33] files etc etc to make cloud code work
[00:53:36] more efficiently for you.
[00:53:37] >> All right.
[00:53:38] >> Oh
[00:53:39] >> yeah. Yeah. So this is super cool but
[00:53:40] it's going to use a lot of tokens. I'm
[00:53:42] already out of tokens so I'm not going
[00:53:43] to [laughter] demo that now.
[00:53:45] >> Yeah.
[00:53:46] >> Yeah. But this is something I definitely
[00:53:48] recommend people trying. This is a very
[00:53:50] cool thing.
[00:53:50] >> Okay. Yeah. I'm going to write right
[00:53:52] now. Um yeah, I I I think the token
[00:53:54] maxing thing is kind of like a meme. But
[00:53:56] I think basically like just summarize
[00:53:58] your advice. Number one is like putting
[00:54:00] the reps like try different things, try
[00:54:01] to build different things. Number two is
[00:54:03] like if you use multiple agents, you can
[00:54:05] put in more reps, right? Because you
[00:54:06] don't have to wait for one a agent to do
[00:54:07] anything.
[00:54:08] >> Yeah.
[00:54:08] >> And then and and then the third one is
[00:54:10] is u sorry what was the third one again?
[00:54:13] >> Part of your Yeah. Not only writing
[00:54:15] code. Yeah, I think the second one is
[00:54:17] especially hard, dude, because like I
[00:54:19] don't know like growing up as an Asian
[00:54:20] person, I have like a scarcity mindset.
[00:54:22] I try to save money and stuff and
[00:54:24] [laughter]
[00:54:25] >> and like just trying to burn our tokens.
[00:54:26] It doesn't feel it doesn't feel right.
[00:54:29] >> Uh but there's a so most of us uh like
[00:54:32] working as individuals, we have uh the
[00:54:35] subscription, right?
[00:54:37] >> So at least try to make the most out of
[00:54:39] the subscription and exhaust the quota.
[00:54:42] >> Okay. Yeah. So, I guess it's kind of
[00:54:43] like going to a buffet and like trying
[00:54:45] to eat all the crab legs. [laughter] I
[00:54:47] guess I can.
[00:54:48] >> Yeah. But I I I I would say like uh
[00:54:52] there's the token maxing thing. Uh I I
[00:54:54] think uh we shouldn't just use tokens
[00:54:56] for the sake of using tokens, right? We
[00:54:58] want to get actual work done. Uh so I I
[00:55:01] think uh it's more about pushing
[00:55:03] ourselves like my my point about number
[00:55:05] two was more about pushing ourselves to
[00:55:08] figure out ways to scale up um and
[00:55:12] really like get more done with agents
[00:55:14] instead of uh finding ourselves into the
[00:55:16] loop and only do one thing at a time.
[00:55:18] >> That makes a lot of sense. That makes a
[00:55:19] lot of sense. All right, cool. Well,
[00:55:21] thank thanks so much, man. Uh where can
[00:55:22] people find your like all the free stuff
[00:55:24] you've been shipping and also yourself?
[00:55:26] >> Yeah. Yeah. So I'm very active on uh X
[00:55:29] and YouTube. I'm I plan to share a lot
[00:55:32] of my workflows and tools and setups
[00:55:34] over there. Um and I also uh my GitHub
[00:55:37] uh is also a good place uh to uh look at
[00:55:40] my projects.
[00:55:41] >> Your your GitHub is just uh slashkun,
[00:55:43] right?
[00:55:44] >> Kungchan GUID. So I I have this uh let
[00:55:46] me uh let me move my window here.
[00:55:48] >> Oh, there is. Yeah.
[00:55:48] >> Uh yeah, this is my uh handle almost
[00:55:51] everywhere. Uh so uh YouTube X and
[00:55:54] GitHub, LinkedIn, it's all this handle
[00:55:57] UID.
[00:55:58] >> Yeah, I think it's like a blessing to
[00:56:00] all of us that you're shipping all the
[00:56:01] stuff for free and like we can all try
[00:56:02] it. So uh yeah, I'm definitely going to
[00:56:05] try no mistakes and um you know every
[00:56:07] everything else that you built.
[00:56:09] >> Cool. Cool. Thanks, Peter. Yeah, if you
[00:56:10] run into anything, let me know. I I I'm
[00:56:12] constantly trying to improve these tools
[00:56:14] as well.
[00:56:15] >> Cool. All right, take care, man. Bye.
[00:56:17] Fitter.
