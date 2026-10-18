---
record_id: "youtube:MSbacZ99E14"
video_id: MSbacZ99E14
title: High Throughput Agentic Engineering with Kun
channel: Kun Chen
url: "https://www.youtube.com/watch?v=MSbacZ99E14"
watched_date: "2026-10-07"
watched_at: "2026-10-07T23:58:00Z"
watch_count: 1
duration_seconds: 3237
source: youtube-history-browser
added_date: ""
history_label: Oct 7
history_order: 120
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 324
transcript_status: fetched
transcript_content_hash: 27b771448e8a729e66e0db4ab91f1bf5d5968ccd86711d3561738b4658409406
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: claude-haiku-4-5
tagging_model: skipped
proposed_tags: []
proposed_entities: []
topic_domain: other
status: new
routed_to: null
---

## Summary

**What was discussed:**
Kun demonstrated his high-throughput agentic workflow centered on "First Mate," an open-source orchestration system that manages a fleet of parallel AI agents (crew mates) through a single agent session. He showed how First Mate automatically routes tasks to the best model based on dispatch rules (Fable for UI design, Opus for complex planning, Sonnet for bug fixes), monitors quota availability across Claude, Codex, Cursor, and Grok, and scales across multiple machines using "Second Mates" that own specific domains. The workflow includes tools like Herder (multiplexer), Lavish (interactive visual review), Bearings (task/decision tracking), and integrations with Discord and X to relay work requests back to the central First Mate session. Kun manages 36+ projects and spawns up to 7 crew mates in parallel, with a custom UI that hides tool-call noise and shows only a "boat" indicator that work is proceeding.

**What's actionable for you:**
Clone First Mate from its open-source repo and configure `crew_dispatch.json` to define which models handle which task types (design, planning, bug fixes, etc.). Set up quota monitoring so your orchestrator automatically selects the model with available capacity. Use follow-up prompts (Alt+Enter in PI) to queue tasks without interrupting orchestration. Create Second Mates for high-activity domains to scale beyond a single orchestrator. Integrate Discord/X bots to relay incoming requests into your agent session so all work flows through one place. Use voice input for faster prompting and toggle a "calm mode" extension to hide tool calls and maintain focus on what matters next.

## Transcript

[00:00:00] Hi everyone, or should I say hi
[00:00:02] captains. Many of you might have already
[00:00:04] watched my previous videos because they
[00:00:06] got more than a million views. If you
[00:00:08] haven't yet, my name is Kun. I was an L8
[00:00:11] principal engineer previously at Meta,
[00:00:13] Microsoft, and Atlassian. My previous
[00:00:16] videos shared a lot of the basics about
[00:00:19] agentic engineering. So this time I'm
[00:00:21] hoping to share a more advanced workflow
[00:00:24] focusing on high throughput multitasking
[00:00:27] through a large number of agents. I'll
[00:00:29] walk through it by just showing you how
[00:00:31] I get some real work done. Let's jump
[00:00:33] in. As always, we will start with a
[00:00:36] clean terminal. And the first thing I'm
[00:00:37] going to launch is Herder. Herder is
[00:00:40] basically my new T-Max. Uh it's a
[00:00:42] multiplexer. It manages all my agent
[00:00:44] sessions and allows me to easily
[00:00:45] navigate between the sessions. You will
[00:00:47] see that in a bit in this video. And
[00:00:49] then I'm going to go into my first mate
[00:00:52] directory. Uh if you haven't heard of
[00:00:54] first mate yet uh it is a open source
[00:00:57] project that I created uh it's got quite
[00:00:59] some popularity uh a lot of people are
[00:01:01] using this. This is basically my
[00:01:03] workflow. First mate is the essence of
[00:01:05] my workflow and uh the core idea is that
[00:01:09] uh I only talk to one agent which is the
[00:01:11] first mate and the first mate will
[00:01:13] orchestrate all the other agents for me
[00:01:15] so that I don't have to juggle between
[00:01:17] all the sessions and context switch all
[00:01:19] the time. uh is first mate doing that
[00:01:21] and you will see that in a bit. Um the
[00:01:23] way to set up first mate is super easy.
[00:01:25] You just just clone this repo and launch
[00:01:27] your agent in this repo. Uh so now that
[00:01:30] I'm in the first mate directory, I just
[00:01:32] launch my agent. Uh I use pi. Um I I use
[00:01:35] both pi and cloud code. Uh I basically
[00:01:38] use cloud code for whenever I want to
[00:01:40] use an anthropic model uh like opus and
[00:01:42] fable. And I use pi for everything else
[00:01:45] because pi uh basically it can use any
[00:01:48] other model. Uh allows me to switch
[00:01:50] between models very easily as well. Uh I
[00:01:52] actually um right now I'm using grock
[00:01:54] 4.5. Um right now uh as of this day um
[00:01:58] Grock 4.6 is already available but I
[00:02:01] actually like 4.5 better because Grock
[00:02:04] 4.5 is uh faster and more efficient and
[00:02:07] more straight to the point. Uh 4.6 is a
[00:02:10] little bit like Opus 5. uh it's got uh
[00:02:13] this weird uh personality where it
[00:02:16] doesn't quite speak uh like a human. Um
[00:02:18] so I like 4.5 better. Uh and that's
[00:02:21] something I recommend in general that
[00:02:23] when the new model comes out, don't
[00:02:25] assume the new model is always better
[00:02:27] than the last. Uh just use it for a bit
[00:02:29] and get a sense for how the model
[00:02:31] behaves uh by yourself and uh look at
[00:02:34] how other people have summarized their
[00:02:35] learnings as well. Uh so yeah, this is
[00:02:38] first mate and this agent session is
[00:02:40] where I literally do everything. All my
[00:02:43] projects, all my tasks, I just use this
[00:02:45] single agent session to do it. And maybe
[00:02:47] to show you what that looks like, I'll
[00:02:48] just ask first mate list all the
[00:02:51] projects that we manage through this
[00:02:53] fleet.
[00:02:57] Um yeah, and you notice that I use voice
[00:03:00] input by default. Uh and that's how I
[00:03:02] work. uh voice input is just faster than
[00:03:04] uh typing uh most of the time like this
[00:03:06] kind of natural language prompts. Uh the
[00:03:09] only case where I don't use voice is
[00:03:11] when I have to um type a URL or
[00:03:13] something like that. Yeah. And you can
[00:03:14] see first mate has already listed all
[00:03:16] the projects that I currently manage
[00:03:18] through first mate. Uh it's a lot of
[00:03:20] projects. Uh right uh this is like how
[00:03:22] many 36 projects in total. Um so this is
[00:03:25] uh I do everything uh across these 36
[00:03:28] projects. I do a lot of tasks. Uh most
[00:03:30] of these are open source projects that I
[00:03:32] uh published. Some of them are private
[00:03:34] projects as well. And I do everything
[00:03:36] just through first mates. And to show
[00:03:37] you how I do that, uh maybe I just like
[00:03:39] walk through some real tasks. Uh the
[00:03:41] first thing I probably want to do is u
[00:03:43] this project called backpass. Um
[00:03:46] backpass is a um tool that you can use
[00:03:49] to help you improve your agent um
[00:03:53] agents.mmd or cloth.md. The way this
[00:03:56] tool works is that it will analyze all
[00:03:58] your agent sessions in the past and use
[00:04:00] that to detect what can we improve about
[00:04:04] your agents.mmd and cloud.md so that
[00:04:06] your agents can work better next time.
[00:04:09] Um, and this tool uh I'll probably do a
[00:04:11] dedicated video about this in the
[00:04:13] future. Uh, but right now I just want to
[00:04:15] do one improvement which is uh something
[00:04:18] I'll just tell first mate. Hey first
[00:04:20] mate, previously we planned an idea for
[00:04:23] backpass which is to allow backpass to
[00:04:26] collect agent sessions across multiple
[00:04:28] remote machines. Um uh I think the plan
[00:04:30] is already there. Can we pull that out
[00:04:33] and then dispatch a crew mate to work on
[00:04:35] that?
[00:04:38] All right. Uh so that's how I uh ask
[00:04:41] first mate to do one task. Uh and first
[00:04:43] mate will look into um the projects uh
[00:04:46] and figure out which project this is
[00:04:48] about and how to uh find the previously
[00:04:52] um already made plan and use that to
[00:04:54] delegate to another implement uh agent
[00:04:57] to do it. Um you will notice that um
[00:05:00] first made agent is already working. Um
[00:05:02] but we don't see any tool calls. We
[00:05:04] don't see anything in in this uh pi
[00:05:06] agent terminal, right? Um and the uh and
[00:05:09] the only thing we see is this little
[00:05:11] boat uh that is like floating around and
[00:05:13] sometimes the agent uh chain of thoughts
[00:05:15] is showing up as well but it quickly get
[00:05:17] dismissed. Um this is done by a custom
[00:05:21] PI extension that I built. Uh uh it's uh
[00:05:24] it comes with a first mate repo. Um and
[00:05:27] the reason I do this is that I really
[00:05:29] don't need to look at what's the agent
[00:05:32] is doing. It's making all those tool
[00:05:33] calls. It's reading files. It's doing
[00:05:35] this and that. um I don't actually need
[00:05:38] to know that most of the time those
[00:05:40] things are distractions and noise. Uh so
[00:05:42] I built this uh little custom uh
[00:05:45] extension called com uh com um and this
[00:05:49] calm uh command in pi will basically
[00:05:51] allow me to hide all those noise and
[00:05:54] just show this little boat that I uh can
[00:05:56] allow me to know the agent is working.
[00:05:59] It's not stuck. Um, if I do want to see
[00:06:01] uh what's kind of tool calls were being
[00:06:03] made, I can just type uh com uh slashcom
[00:06:07] to toggle uh this uh details. So now I
[00:06:10] can see, oh, it's making this tool call.
[00:06:11] It's uh spawning a crew mate, right? Um
[00:06:14] so yeah, that's what the agent is doing.
[00:06:16] But most of the time I just turn on com
[00:06:18] mode and I just uh uh don't need to look
[00:06:21] at all those noise. Um and then that
[00:06:24] allows me to focus. that allows me to
[00:06:26] actually think about what do I actually
[00:06:28] need to do next, right? Uh so that's
[00:06:31] what's important in not looking at the
[00:06:32] tool cost and everything. Um so one
[00:06:35] thing I do want to uh show here um okay
[00:06:39] uh first mate said uh it's found uh the
[00:06:42] plan and dispatched it. Um so now we can
[00:06:45] see there is a crew mate here uh right
[00:06:47] uh in the left hand side panel uh where
[00:06:49] we can look at all the uh sessions all
[00:06:51] the agents. Uh we can see here there is
[00:06:53] a backpass SSH u this is basically
[00:06:56] another terminal tab uh where u another
[00:06:59] agent has spawn up uh and it's running
[00:07:01] opus 5 uh it's got the requirements and
[00:07:04] it's now building the thing uh it's
[00:07:06] building uh what we uh what I asked this
[00:07:08] is basically a crew mate uh that's spun
[00:07:10] up by first mate earlier um and the
[00:07:13] reason uh we're using opus 5 here is
[00:07:16] that uh if we look uh if we toggle com
[00:07:20] mode off uh and Let's see if we can find
[00:07:23] the uh previous uh tool calls. Um we can
[00:07:28] probably see that um before first mate
[00:07:32] decided to um launch the crewmate, it
[00:07:35] caught a few things. It called this
[00:07:36] quotota axi uh and it used a skill
[00:07:40] called quotota array dispatch. Uh this
[00:07:42] is something that's really important. Uh
[00:07:44] and uh that's why I want to talk through
[00:07:46] this. Um, first mate, uh, when first
[00:07:50] mate is about to dispatch a crewmate to
[00:07:52] do something, it will look at a bunch of
[00:07:55] rules to decide which agent and which
[00:07:57] LLM to use for that crewmate. Um, so let
[00:08:01] me uh turn this back off and uh let me
[00:08:03] show you and let me go find the config
[00:08:06] file. Uh, it's a config file in the
[00:08:08] config directory called crew
[00:08:09] dispatch.json.
[00:08:11] Um, this is my dis uh dispatch rules.
[00:08:14] You can configure yours. Um, and I
[00:08:16] actually don't write this rule file by
[00:08:19] by hand. I ask first mate to uh do this.
[00:08:22] I just tell firstmate what my
[00:08:23] preferences are and first mate will
[00:08:25] configure this file for me. Um, and the
[00:08:27] rules uh we can look through this for
[00:08:29] new feature development work on uh this
[00:08:32] iOS app that I I have always use Fable.
[00:08:35] Um, Fable is like really good at
[00:08:37] building good UI. Um, and this iOS app
[00:08:40] actually uh is a paid app. I really want
[00:08:42] to make sure it's taken good care of. Uh
[00:08:45] so I use Fable for that. Um and the task
[00:08:49] requires uh generating images. Uh if it
[00:08:52] needs images then I use codeex as the
[00:08:54] harness and then GPT 5.6 soul. Um codeex
[00:08:58] has a native tool for generating images
[00:09:00] because openai has the uh image
[00:09:02] generation model right. Uh so I use
[00:09:05] codeex to do that. Um there is also uh
[00:09:08] when the task is technical product
[00:09:10] design architecture um or planning work
[00:09:12] that is like genuinely very difficult.
[00:09:15] Uh so it's a difficult planning work. I
[00:09:17] use fable I use uh Kim K3 I use Astra.
[00:09:22] Uh so I basically allow these three
[00:09:24] models to do this kind of very complex
[00:09:26] and ambiguous planning for me. Uh and
[00:09:28] there's like Y as well. Uh so it helps
[00:09:30] the model uh make the decisions. uh and
[00:09:33] then if the task is a simple bug fix uh
[00:09:36] whose root cause and expected behavior
[00:09:38] is already well defined then I use Luna
[00:09:40] I use Sonnet I use uh cursor uh Gro 4.6
[00:09:46] um and then the default if uh a task
[00:09:48] doesn't fall under any of those rules
[00:09:50] then the default is uh claude opus and
[00:09:53] uh this uh cursor and gro 4.6 six high.
[00:09:57] Uh so that's basically my uh rules for
[00:09:59] how I dispatch uh the crewmates and uh
[00:10:02] when you see I have multiple models
[00:10:05] defined here right so when uh this rule
[00:10:07] matches there is three models that's uh
[00:10:10] available and when this happens uh the
[00:10:14] first mate will look at which uh model
[00:10:18] has the most quotota available and
[00:10:20] choose the one that has the most
[00:10:21] quotota. So I'll show you um how I look
[00:10:24] at my quota as well. I use this tool
[00:10:27] called quota axi. That's another project
[00:10:29] I built. Uh it can give us um this data
[00:10:33] uh where I can just easily monitor how
[00:10:35] my quota is doing. I have a subscription
[00:10:37] from cloud. I have a codeex. I have a
[00:10:40] cursor. I have a gro as well. Uh and
[00:10:43] this is where they uh sit currently. Uh
[00:10:45] I actually took a vacation right before
[00:10:47] this and I have a ton of kota available
[00:10:50] uh which is awesome. Uh so I can build a
[00:10:52] lot of stuff and this quotota axi is
[00:10:54] actually um this TUI is for human but uh
[00:10:58] the default COI is for agent to use. Uh
[00:11:00] so first mate will call quota axi to get
[00:11:03] access to all my quota information and
[00:11:06] use the model that has the most quota
[00:11:08] available so that I don't waste any
[00:11:11] quota. Uh so this is like really useful
[00:11:14] because otherwise I have to constantly
[00:11:16] look at this myself. Um and with like
[00:11:18] people like Tibo constantly resetting
[00:11:21] codeex quota it's really hard to keep
[00:11:23] track of that right uh so that's why uh
[00:11:25] I use uh this um way uh left first mate
[00:11:29] to manage all this dispatching for me uh
[00:11:31] and first mate for this case uh it
[00:11:33] decided to use an opus 5 uh so that's
[00:11:36] why uh it launches uh this opus 5
[00:11:38] crewmates uh under this uh first mate
[00:11:40] structure um so I yeah I don't actually
[00:11:43] look at the the um crewmates um most of
[00:11:46] the
[00:11:47] uh I just think about what I want to do
[00:11:49] next. Uh there is another project um
[00:11:51] that I want to uh make some improvements
[00:11:53] on. Uh I'll show you. There is a project
[00:11:56] I recently built. I really uh find quite
[00:11:59] interesting. Uh it's called Fry with Me.
[00:12:02] Uh and this project uh is a uh it's a
[00:12:05] game basically. Um and let me show you.
[00:12:08] Uh I'll launch a new seed. Uh it's
[00:12:10] basically a game, but it's kind of uh
[00:12:13] it's something to help me relax. I I I
[00:12:15] usually put this on my uh second monitor
[00:12:18] uh when I'm coding and it's just like uh
[00:12:21] I'll turn off sound. Uh it's just like a
[00:12:23] really relaxing uh bird that is flying
[00:12:27] across the world. Uh and this whole
[00:12:29] world is u procedurally generated. Uh so
[00:12:32] it's always different. Uh and I can just
[00:12:34] put this on a second monitor and like uh
[00:12:37] keep focusing on my work. Um, so the
[00:12:40] thing I want to do with this uh with
[00:12:41] this game right now uh is that I want to
[00:12:44] improve some of the visuals uh in this
[00:12:46] game. Uh so I'll just go back to um my
[00:12:50] first mate and say uh tell first mate
[00:12:52] some of the ideas.
[00:12:54] Hey um I want to make some uh
[00:12:56] improvements to uh fry with me. Uh I
[00:13:00] have three ideas. One is that I want to
[00:13:03] prototype uh some better looking snowy
[00:13:06] mountains. Uh so when there's a mountain
[00:13:09] with snow uh right now it doesn't look
[00:13:12] as good. Uh I want to prototype a few
[00:13:14] really goodlooking uh mountains um that
[00:13:17] we can uh render. Uh so that's one.
[00:13:20] Another idea I have is that uh at night
[00:13:23] right now uh we just show a uh night
[00:13:27] sky. We have the Milky Way which is
[00:13:29] good. Uh but I also want to have
[00:13:31] northern lights. Um they should show up
[00:13:33] kind of rand randomly. uh not always uh
[00:13:36] but uh they should look like uh
[00:13:38] realistic northern lights. Um the third
[00:13:41] idea is that right now there's only one
[00:13:43] bird and we cannot choose between
[00:13:45] different kind of birds. Uh I want to
[00:13:47] prototype uh a few different kind of
[00:13:49] birds that people can choose. Um so yeah
[00:13:53] for each of these ideas I want you to um
[00:13:56] prototype three different variants. Uh
[00:13:58] so I can choose uh which one uh I like.
[00:14:02] Um and uh once the prototypes are ready,
[00:14:07] uh ask the crew mates to give me uh that
[00:14:10] in lavish for me to review. And each
[00:14:13] idea should be done by a fable crew mate
[00:14:16] uh in parallel.
[00:14:20] All right. Uh so basically I gave a long
[00:14:22] ramble of uh ideas that I have. Uh I
[00:14:25] like to do this a lot. Um and you can
[00:14:27] see I asked for prototypes. Um and I
[00:14:30] asked the prototypes to be given to me
[00:14:33] uh through lavish which we'll look at uh
[00:14:35] in a bit. Uh it's a really good way to
[00:14:37] visually validate uh the ideas and just
[00:14:40] pick uh very easily and give feedback as
[00:14:42] well. Um and I specifically asked for
[00:14:45] fable uh because uh the reason uh was
[00:14:48] like uh I was looking at the quota,
[00:14:50] right? We have a whole bunch of fable
[00:14:52] quota available. Uh so why not uh use
[00:14:54] that? Uh so I use fable uh to do this
[00:14:57] prototypes uh and uh they usually uh can
[00:14:59] give really good results. Yeah. So um
[00:15:02] this is basically uh while the previous
[00:15:04] backpass uh task is still ongoing uh the
[00:15:07] crew mate is still working on that. uh I
[00:15:09] just keep giving more and more ideas to
[00:15:11] first mate and first mate uh is not uh
[00:15:15] because first mate is not the one that's
[00:15:17] actually doing the work uh it's always
[00:15:18] available to talk to me uh and whenever
[00:15:21] there is some more work uh first mate
[00:15:22] will just spin up more crew mates to do
[00:15:24] that and then come back to me uh and I
[00:15:26] can talk to it as well um if I have more
[00:15:28] like more ideas although first mate is
[00:15:31] working like this boat is still moving
[00:15:33] uh that's saying like first mate is
[00:15:35] working I can just keep typing more
[00:15:36] ideas here I can just talk to first mate
[00:15:39] type more and more prompts and kill
[00:15:40] those prompts. All right, so I don't
[00:15:42] actually have to wait for first mate to
[00:15:45] uh finish up or anything. Uh I just keep
[00:15:47] giving more and more prompts. Um and
[00:15:50] that's how I uh work with first mate uh
[00:15:52] to like get a lot of tasks spun up in
[00:15:55] parallel. Um something else that I also
[00:15:58] uh like to do is um when I work through
[00:16:00] so many projects, there's usually a lot
[00:16:03] of decisions that were previously
[00:16:04] discussed but haven't been made. Uh
[00:16:07] right. Um and and sometimes it's really
[00:16:09] easy to like lose track of which things
[00:16:12] we talk about that have been done versus
[00:16:15] have not been done yet. Um in first mate
[00:16:17] there is a built-in skill called
[00:16:19] bearings that can do this. Uh this will
[00:16:22] basically allow first mate to collect a
[00:16:24] snapshot of all the uh active tasks
[00:16:28] across the fleet and give me a snapshot.
[00:16:30] Um but uh the default bearings will give
[00:16:33] me that uh in the terminal. Uh which
[00:16:36] sometimes is like a little bit hard to
[00:16:37] read. Uh so I actually have a variant of
[00:16:39] that called bearings lavish which will
[00:16:42] get first mate to give me that report in
[00:16:44] lavish. Uh so I'll just show you. Um I
[00:16:47] used the follow-up prompt to cue this uh
[00:16:49] right u behind the current actions. Uh
[00:16:52] so first mate will not run this yet. Uh
[00:16:54] it's queued as a follow-up. So only when
[00:16:57] first mate has done the current set of
[00:16:59] actions then it will uh do the follow-up
[00:17:02] prompt. Uh so this is a good way to make
[00:17:04] sure first mate is not being distracted
[00:17:06] uh it's actually doing things one by
[00:17:08] one. Um if I need to uh actually steer
[00:17:11] first mate uh to do something I can also
[00:17:13] steer instead of follow-up. Uh so
[00:17:15] followup I think is alt enter and steer
[00:17:18] is just enter. So if I type a prompt and
[00:17:20] enter it will become a steer that will
[00:17:22] immediately send to first mate. Um
[00:17:25] that's a PI feature actually. Um and uh
[00:17:28] it's very handy to have a distinction
[00:17:30] between follow-up and steer. Um so we
[00:17:32] can see here first mate has spun up uh
[00:17:35] backpass this crew mates um and
[00:17:37] [clears throat] three uh other fly
[00:17:39] something crew mates right these are the
[00:17:41] three ideas uh that I asked um just now
[00:17:44] and first mate is just finishing up uh
[00:17:46] dispatching all the crew mates uh and we
[00:17:48] can check right it's using fable uh so
[00:17:50] just as we asked u that is something
[00:17:53] that's very useful is like I can
[00:17:55] specifically ask for a certain uh agent
[00:17:58] harness or a certain model to be used uh
[00:18:01] for the task task that I uh am about to
[00:18:03] do. Um this is useful when I have some
[00:18:07] opinion or judgment on what is the right
[00:18:09] model. Um and um yeah uh for different
[00:18:13] tasks I can just easily uh get the right
[00:18:15] model to work on them. Uh and right
[00:18:17] right now uh first mate said all those
[00:18:19] three um fly with me prototypes uh
[00:18:21] underway. Uh and now the follow-up
[00:18:24] prompt bearing stavish uh just uh got
[00:18:26] sent right. Uh so that's how a follow-up
[00:18:28] prompt work. All right. First May just
[00:18:31] brought up this uh lavish uh report um
[00:18:33] this uh bearings report in lavish um and
[00:18:36] it's a really uh nicely structured um
[00:18:39] like uh interactive HTML that has uh
[00:18:43] what's uh what's charted next uh what is
[00:18:45] currently underway. Uh these are the
[00:18:47] things that's already happening and uh
[00:18:49] what's recently landed at the top
[00:18:51] there's like all these captain's call
[00:18:53] these are the decisions I have to make.
[00:18:55] Uh so let me look through this. These
[00:18:58] were usually like things that were
[00:18:59] previously discussed uh and haven't been
[00:19:02] done. So uh it's good to u make a
[00:19:04] decision on. So there's a workaround for
[00:19:07] lavish onboard. Uh this one yeah I
[00:19:10] remember this one but I don't want to do
[00:19:11] that right now. Uh I just decide claude
[00:19:14] exit confirm dialogue. Uh this is for
[00:19:16] first mate. Uh and uh Claude recently
[00:19:18] introduced a new dialogue where um when
[00:19:21] you try to exit claude when some
[00:19:23] background tasks are running uh it will
[00:19:25] show up a dialogue that blocks the exit
[00:19:27] which is really annoying. Uh so I think
[00:19:29] we actually have to do this uh treat as
[00:19:32] non uh non wedge. Yep.
[00:19:36] Uh this le props up sub uh yeah this one
[00:19:39] I remember I I don't want to do that
[00:19:41] right now. Um uh and I'll just look
[00:19:44] through like all these decisions. These
[00:19:45] were usually like things that we
[00:19:46] previously discovered. Uh herder missing
[00:19:49] end points recreate. Yep, that's a bug.
[00:19:51] Uh keep refuse escalate. Um
[00:19:56] yep, that's the right behavior. Uh URL
[00:20:00] wrap. Uh this is for the ship app. Um
[00:20:02] and this is a bug uh will uh we'll fix
[00:20:05] now. Uh ship a follow-up. Um this is a
[00:20:09] another improvement for ship uh for a uh
[00:20:12] first-time user experience uh to teach
[00:20:14] user about the multiplexer. Uh this is
[00:20:16] quite complex. Uh so I'm going to keep
[00:20:18] that held uh and discuss that a little
[00:20:21] bit deeper. Uh this is the diaglide
[00:20:23] banner. Um yeah, this one I actually
[00:20:25] want to build now. Uh so I'll do that.
[00:20:28] Uh design kit mock removal. Yep, I
[00:20:31] remember this one needs to be done. Uh
[00:20:33] I'll decide as well. Um yeah, you can
[00:20:36] see there are quite some decisions,
[00:20:38] right? Uh because I'm walking through a
[00:20:39] lot of different projects and uh these
[00:20:42] projects as I walk through them uh I
[00:20:44] usually have like a lot of discussions
[00:20:46] with first mate and some of the
[00:20:47] decisions I just haven't made. Um so uh
[00:20:50] it's good to have this like first mate
[00:20:52] keeping track of that for me. Um dial
[00:20:55] nested fan editor. Yep, I need that now.
[00:20:58] Um what else? Drag into group. Uh yeah,
[00:21:03] this is uh where like um users can
[00:21:06] customize uh the dial in the ship app.
[00:21:09] Um I will do that later. Um so okay, so
[00:21:13] all the decisions uh we have recorded uh
[00:21:16] the follow-up. Uh so I'll just send this
[00:21:18] back. Yeah, we can see here this working
[00:21:20] spinner. That means uh the feedback uh
[00:21:22] was sent back to first mate. Uh and uh I
[00:21:25] can actually just end the session now.
[00:21:27] Uh if I go back to first mate, yep,
[00:21:29] first mate is now um having a boat. uh
[00:21:31] which means first mate is working. Um so
[00:21:34] it's likely that first mate just
[00:21:35] received the feedback and is now acting
[00:21:37] on them. Uh we'll give first mate a bit
[00:21:40] of time to see uh what first mate does.
[00:21:42] Okay, here we can see uh first mate just
[00:21:44] got back to us. Uh it said um the uh the
[00:21:48] four uh decisions about first mate uh is
[00:21:50] listed here. Uh actually there's like
[00:21:52] nothing needed. Uh the one thing I
[00:21:55] decided to build was actually already
[00:21:56] released. It's already in the codebase.
[00:21:59] Um so uh ship uh we decided to um build
[00:22:04] this now build this now and fix that and
[00:22:06] prioritize this. Uh so there's a lot of
[00:22:08] work on this ship project and we can see
[00:22:12] um the work is actually being routed to
[00:22:14] this uh second mate. We can see there's
[00:22:16] a crew mate under here that's uh
[00:22:18] currently running. Um second mate is
[00:22:21] basically a way to scale up uh first
[00:22:23] mate's charter. Um so you can see as we
[00:22:25] give more and more tasks to first mate
[00:22:28] uh we already have four tasks right um
[00:22:30] if we keep giving more and more tasks um
[00:22:32] to first mate at some point you will
[00:22:35] realize oh first mate is like way too
[00:22:37] busy uh because it's always
[00:22:38] orchestrating those tasks and have no
[00:22:40] time to even talk to me um so at some
[00:22:43] point you will have to scale up and this
[00:22:45] is uh what I did I basically created a
[00:22:48] whole bunch of second mates to own
[00:22:50] different domains um of the charter so
[00:22:52] these second mates uh ship
[00:22:54] uh owns everything related to this ship
[00:22:57] app. So every uh piece of work that's on
[00:23:00] this ship app will get routed to this
[00:23:01] second mate. So first mate doesn't have
[00:23:03] to orchestrate all that. Uh it can just
[00:23:05] send the ask to this second mate and the
[00:23:08] second mate will do it. Um and we can
[00:23:10] see here first this second mate is
[00:23:12] already has already spun up this crew
[00:23:14] mate uh for the URL rep bug fix. Uh
[00:23:17] there's a few more that will likely be
[00:23:19] spun up soon as well. Um, every second
[00:23:22] mate is actually a first mate by itself.
[00:23:25] Um, so I can actually just go into this
[00:23:28] second mate and see what it's doing. Uh,
[00:23:30] I can talk to it just like a normal
[00:23:31] first mate. Um, and uh, maybe uh, let me
[00:23:35] show one example. Uh, this is uh, a
[00:23:37] second mate for the Edis wallets app.
[00:23:39] Uh, this app was the app I built in my
[00:23:41] last video. This app is actually already
[00:23:43] released in the app store. U, but I
[00:23:45] actually forgot uh, which features got
[00:23:48] in versus not. So, I'll just ask uh
[00:23:51] which features have already landed
[00:23:54] that's not released to the app store
[00:23:56] yet,
[00:23:59] right? Um so I can just talk to this
[00:24:01] second mate. Every second mate is also a
[00:24:04] first mate. Uh so it will manage its own
[00:24:06] crew mates. Uh it has its own memory and
[00:24:08] uh instructions and everything. Um so I
[00:24:11] can just talk to it. Uh I can also talk
[00:24:14] to it through first mate, right? I can
[00:24:16] ask first mates the same question here
[00:24:18] and first mate will route the question
[00:24:20] to that second mate uh whenever
[00:24:22] appropriate. Most of the time uh I
[00:24:25] actually go with the easy route where I
[00:24:26] just talk to first mate. Yeah. So this
[00:24:28] second mate is now uh trying to answer
[00:24:30] our question uh and we can let it do its
[00:24:33] work. Um and you can see here um there
[00:24:36] is a local versus mini. Uh this is a
[00:24:39] herder feature. So Herder has the
[00:24:41] ability to manage all the agent sessions
[00:24:44] across multiple machines. Um so this
[00:24:47] mini is my Mac Mini uh which is uh uh
[00:24:50] actually on my shelf right now. Um it's
[00:24:52] running headlessly. Uh so I don't
[00:24:55] connect any monitors or mouse or
[00:24:56] keyboard to the Mac Mini. I just let it
[00:24:58] run uh headlessly. And this mini
[00:25:01] actually manages a lot of uh have a lot
[00:25:03] of second mates running on it. Uh so um
[00:25:06] the mini has the second mate for first
[00:25:08] mate development for ship for Eddie's
[00:25:10] wallet for axi for uh there's a default
[00:25:13] one as well. Um so the mini uh has uh
[00:25:16] basically more hardware resources than
[00:25:19] my MacBook. This current local machine
[00:25:21] is a MacBook. Uh it has uh a little bit
[00:25:24] less power uh than what my mini has. Uh
[00:25:26] so I assigned a lot of domains uh to the
[00:25:29] Mac Mini uh so it can do more work.
[00:25:32] Okay. Uh there's actually a lavish board
[00:25:34] that's just brought up to me. Um and we
[00:25:36] can see it's the bird kinds for fly with
[00:25:39] me. Uh this is what I asked earlier,
[00:25:41] right? Uh and it's done by Fable. Uh so
[00:25:43] now it's ready for review. Um it's
[00:25:45] really nice to have this lavish uh
[00:25:47] interactive artifact. You will see um
[00:25:49] the current bird, right? This is the
[00:25:51] current bird. It took screenshots so
[00:25:53] that I can see what's the current bird
[00:25:55] looks like. Uh and
[00:25:58] board soaring raptor. Okay, this is the
[00:26:01] prototype, right? So, this is a new kind
[00:26:02] of bird. Uh, and it's giving me this
[00:26:05] preview. Uh, this is really nice. Uh, I
[00:26:07] I really like um looking at this
[00:26:10] previews. Um, so I actually like this
[00:26:12] one. Uh, this this is okay. Uh, what is
[00:26:15] this slender swallow? Uh, what is a what
[00:26:19] is a slender swallow? I I don't know
[00:26:21] either of those words. Um, but uh it it
[00:26:25] looks nice. Uh, it's okay. This one I
[00:26:28] probably will also keep. Uh there is a
[00:26:30] large ocean glider. Okay, this is just
[00:26:34] like the current one, right? Like it's
[00:26:35] uh a little bit different but very
[00:26:38] similar. Okay, there's a long necked
[00:26:41] crane. Oh, cranes. I like cranes. Uh
[00:26:44] they are good. What is this soft night
[00:26:48] owl? Wow, it has so many prototypes.
[00:26:50] It's done a lot of work for us. Um so,
[00:26:53] okay. Uh so there's an owl. I kind of
[00:26:55] like this owl as well. It's like round
[00:26:57] and cute. Um, so, uh, what do we need to
[00:27:01] look at here? Each kind closer. Okay,
[00:27:03] closer. Uh, okay, that's closer. Um, it
[00:27:08] actually explained, uh, like the key
[00:27:10] features, um, of each, um, bird. Uh,
[00:27:13] that's really nice. Uh, but I think I
[00:27:15] already like have seen enough about
[00:27:17] these birds to know what I like. Uh,
[00:27:19] usually at the bottom it will list uh,
[00:27:21] the decisions for me to make, right? So,
[00:27:23] recommendations. Uh, carry forward,
[00:27:25] carry forward. Uh oh, it actually um it
[00:27:30] actually recommended to iterate before
[00:27:32] deciding um okay so uh let's pick right
[00:27:37] um current bird uh current birds we
[00:27:40] don't need to do anything right um broad
[00:27:44] this raptor yes uh the swallow I uh I I
[00:27:49] like it um the glider uh the glider is
[00:27:53] kind of like uh the same as the current
[00:27:55] one so I'm not going uh want it. Uh I
[00:27:57] need the crane. I need the owl. Okay. Uh
[00:28:00] so yeah, these are our decisions. And
[00:28:03] we'll just kill this uh and send it
[00:28:06] back. Uh I'll just say like uh let's
[00:28:08] build uh the birds we decided. Okay. And
[00:28:13] send it an end. And that's it. That's my
[00:28:16] feedback back to Fable. and Fable um
[00:28:18] that crewmate who uh prototyped this
[00:28:21] should uh receive my feedback about
[00:28:24] which birds that we wanted to forward.
[00:28:26] Um and uh that's it. Uh so that's the um
[00:28:29] only thing we had to do with that
[00:28:32] prototype. Um we can see here uh ship
[00:28:35] has already spun up three ship crew
[00:28:37] mates, right? Uh working on three things
[00:28:39] in parallel. So right now how many do we
[00:28:41] have? We have one, two, three, four, uh
[00:28:44] five, six, seven. We have seven crew
[00:28:45] mates working in parallel. Um, and we
[00:28:48] can keep giving more. Like first mate is
[00:28:50] idle right now, right? First mate is not
[00:28:52] doing anything. We can just keep giving
[00:28:53] more ideas. Um, I uh that's what I will
[00:28:56] typically do. I just keep giving more
[00:28:58] and more. Um, and this edi wallet just
[00:29:01] answered our question as well. The
[00:29:03] second mate, uh, it landed since this
[00:29:06] not released. Uh, there's a few Okay,
[00:29:08] there's a few new userfacing features
[00:29:10] that's landed but not released. Uh, auto
[00:29:13] pay local. Oh, these are not released
[00:29:15] yet. Okay. Uh yeah. So now I can decide
[00:29:18] uh do I want to like release those
[00:29:20] features. Uh but I'll probably put that
[00:29:22] aside for now. Uh we have enough uh to
[00:29:25] like work through here. Yeah. So while
[00:29:27] we wait for these current uh work items
[00:29:29] to uh finish, uh something I want to
[00:29:30] show you that's really cool uh is that
[00:29:33] uh I have a Discord channel here uh
[00:29:35] built with We actually have a lot
[00:29:37] of cool people uh in this server now. Uh
[00:29:39] there's a lot of people online and uh I
[00:29:42] think there's like more than a thousand
[00:29:43] 2,000 people now uh in the server. Um so
[00:29:47] um we have um like constant discussions
[00:29:49] about first made about uh models and
[00:29:51] harnesses uh as well. Uh it's a really
[00:29:54] cool community um and if you uh want to
[00:29:57] build with agents uh you enjoy
[00:29:59] discussing like tips and tricks with
[00:30:00] others uh this discord server is a
[00:30:02] really good place. Uh but the thing I
[00:30:04] want to show you is like uh I have this
[00:30:06] bug reports channel uh that I usually
[00:30:09] come here uh to look at what things uh I
[00:30:11] should be fixing. Um let me see uh what
[00:30:14] I haven't looked at yet. Um I think this
[00:30:17] one I um probably haven't looked at yet.
[00:30:19] So this one uh what is this? Um
[00:30:22] [clears throat] uh it's a treehouse.
[00:30:23] Okay. Treehouse is another project I
[00:30:25] have. Uh and uh it's a bug report saying
[00:30:28] this uh hook is not firing. Okay. So uh
[00:30:32] it seems there's a lot of debug
[00:30:33] information already available. So
[00:30:35] something I will show you here is that I
[00:30:37] can actually add my first mate. Uh so I
[00:30:40] can just uh there's a bot here. Uh
[00:30:42] that's my first mate. I can just ask my
[00:30:44] first mate uh to uh investigate this,
[00:30:48] right? Uh so I can just uh add my first
[00:30:50] mate here. And this bot is actually
[00:30:54] relay uh relaying this uh message back
[00:30:58] to my actual first mate here running
[00:31:00] this local session. Uh so this uh boat
[00:31:02] that's moving is likely uh from that
[00:31:05] mention. So u I can just like basically
[00:31:08] summon my first mate uh this single
[00:31:11] agent session that I have from different
[00:31:13] places. Uh I can right now it supports
[00:31:16] discord and uh x as well. Uh maybe I can
[00:31:19] also show you that. Uh so on X uh I also
[00:31:22] sometimes uh when people report problems
[00:31:24] uh right so this uh uh a person
[00:31:27] reporting something uh saying confused
[00:31:30] by settings send feedback uh in this
[00:31:32] ship app uh okay so here I can also just
[00:31:36] uh add my first mate uh right and say uh
[00:31:43] let's improve uh this confusing uh
[00:31:47] message.
[00:31:52] All right. Um, [clears throat] yeah. So,
[00:31:54] this at uh this mention will also get
[00:31:57] relayed to my first mate session. Yeah.
[00:32:00] So, now if we come back to this Discord
[00:32:02] thread, uh we should see first mate
[00:32:05] reply uh very soon. Now, yeah, it just
[00:32:07] replied uh I captain looking into the
[00:32:09] treehouse predestroy hook uh not firing
[00:32:12] on destroy. Uh we'll report back. Yeah.
[00:32:14] So now if we come back to this X thread,
[00:32:16] uh first mate also replied uh saying I
[00:32:18] captain clarifying that send feedback
[00:32:19] version message. Uh right. So uh that's
[00:32:22] really good. Uh this is just like how I
[00:32:24] uh work across different surfaces. It's
[00:32:27] so nice to have all these messages from
[00:32:29] all these different channels and
[00:32:30] surfaces all funneled into this single
[00:32:33] agent session. Right? So this first made
[00:32:35] agent session literally holds all my
[00:32:37] intent and all the context across every
[00:32:40] project that we have. Uh so it can play
[00:32:42] a really good role in coordinating
[00:32:44] across everything and orchestrating all
[00:32:46] the crew uh to get things done for us.
[00:32:49] Okay, while we wait for um the other
[00:32:51] crew mates to come back to us, uh maybe
[00:32:53] one thing that I want to uh quickly talk
[00:32:55] through here is the context window. Um
[00:32:58] so here you can see um the Gro 4.5 uh
[00:33:01] the default context window limits is
[00:33:03] 500k tokens. So here it says we already
[00:33:05] used more than 40% of that. Um and a lot
[00:33:08] of people ask me um whether uh they
[00:33:11] should u manually manage this context
[00:33:14] window and when they should compact when
[00:33:16] they should reset uh and everything to
[00:33:18] keep uh the context window uh efficient
[00:33:20] and optimized. Um so my take on this is
[00:33:24] that there's a lot of things you can do
[00:33:27] uh to manage this context window and
[00:33:29] optimize that and get some savings. Um,
[00:33:32] sometimes you can get the agent to use
[00:33:34] less context to do the same things uh
[00:33:36] and get things done with less cost. Uh,
[00:33:38] sometimes you can also um uh optimize
[00:33:42] this uh so that the agent is a little
[00:33:44] bit smarter because uh if you have a lot
[00:33:46] of context loaded, it can degrade your
[00:33:48] agent's performance as well. Um, so
[00:33:50] there's a lot of things you can do. Um,
[00:33:52] but my take is that I actually advise
[00:33:55] against uh managing that yourself
[00:33:57] manually. The reason is that our most
[00:34:00] precious resource right now, the biggest
[00:34:02] bottleneck across everything we do with
[00:34:04] agents is our attention and time. Uh our
[00:34:08] human attention and time. So uh if you
[00:34:10] use your mental bandwidth to deal with
[00:34:13] this like little optimizations here and
[00:34:15] there, then you don't have enough time
[00:34:17] and enough uh energy to think about what
[00:34:20] should we build and that is actually the
[00:34:23] most important thing. Um so I actually
[00:34:25] think you can just waste a little bit.
[00:34:27] It's okay to not be optimal about
[00:34:30] everything, right? Um there's um there's
[00:34:32] going to be tools, there's going to be
[00:34:34] things that will help us manage that
[00:34:36] automatically. Um and uh eventually
[00:34:38] things will just catch up and those
[00:34:40] features will get built into the harness
[00:34:43] and we don't have to worry about that
[00:34:44] anymore. So right now uh I actually
[00:34:47] suggest what you do is that you set a
[00:34:49] constant threshold. Um so 500k for grock
[00:34:52] is actually a very reasonable threshold.
[00:34:55] Um for codeex uh for cloud uh cloud code
[00:34:58] may be a little bit different uh because
[00:35:00] cloud code uh has a default of 1 million
[00:35:02] tokens as the context window limit. That
[00:35:05] is a little bit too high I would say. Um
[00:35:07] so uh cloud code uh there's different
[00:35:09] settings. I think there's a environment
[00:35:11] variable you can set to uh limit your
[00:35:14] context window size. Uh let me see if I
[00:35:16] can find it actually. Um I have that in
[00:35:18] my dot files. uh files uh if I search
[00:35:23] for auto compaction
[00:35:25] uh yeah so this is the environment
[00:35:28] variable you can set cloud code autoco
[00:35:30] compact window uh and I have that set to
[00:35:33] 500k um so that means every time the
[00:35:36] session reaches 500k tokens it will
[00:35:38] automatically compact um and that's all
[00:35:41] I suggest right now um you just set a
[00:35:44] threshold that allows the agent to
[00:35:46] automatically compact uh the session so
[00:35:49] it doesn't become too expensive and too
[00:35:51] uh inefficient. Um otherwise just forget
[00:35:54] about it. Don't think about the context
[00:35:56] window too much. If your brain is
[00:35:58] thinking about the context window all
[00:36:00] the time, you don't have enough time to
[00:36:02] think about what to build. Um so I want
[00:36:05] you to optimize your time and attention
[00:36:08] on what is the right thing to build
[00:36:10] because that is the most important
[00:36:12] thing. If you do that right, you will
[00:36:14] get back much much more value than what
[00:36:17] you can save with this little tricks. Uh
[00:36:20] I hope that makes sense. Oh, and here uh
[00:36:22] actually first mate reported uh the
[00:36:24] treehouse finding right. So uh treehouse
[00:36:27] investigation is done. Finding is here
[00:36:29] not a destroy bug. Uh real defect is
[00:36:31] hooks uh intentionally discarded for
[00:36:34] safety. What? Uh and that drop is
[00:36:37] silent. We dropped hooks. Uh
[00:36:41] okay. Oh, so hooks in the repo is being
[00:36:44] discarded. Uh destroy never run.
[00:36:48] Keep ignoring repo hooks. Uh I now
[00:36:51] remembered that is a security thing.
[00:36:53] Yes. Um so emit a one-time warning. Um
[00:36:58] okay. Uh
[00:37:01] yes. Uh let's ship the warning fix and
[00:37:03] also reply uh to that Discord thread uh
[00:37:06] for what is happening here.
[00:37:10] Um yeah so uh we'll do that uh and that
[00:37:14] is the closure for the treehouse uh buck
[00:37:17] report. Um so there there's a lot of bug
[00:37:19] reports coming in discord uh in GitHub
[00:37:21] issues. Uh I just funnel them all into
[00:37:24] my agent session uh here in the first
[00:37:26] mates and that first mate helped me do
[00:37:28] the investigations uh and all the stuff.
[00:37:30] Uh I didn't even have to look into the
[00:37:32] crew mates that did the investigation
[00:37:34] here right uh so that is the benefit of
[00:37:36] first mate. I just talk to first mate
[00:37:38] and first mate will orchestrate
[00:37:40] everything for me. Uh I don't have to
[00:37:42] like actually juggle between all these
[00:37:43] sessions. uh how many sessions like we
[00:37:46] had like uh I think at some point we had
[00:37:47] nine sessions or 10 sessions and most of
[00:37:49] the time I don't really look at any of
[00:37:51] them. Oh, first mate gave another
[00:37:53] update. Uh so um there is this uh
[00:37:56] treehouse warning fix is dispatched. Uh
[00:37:58] discord update is posted. Um fry with
[00:38:01] [clears throat] me bird clients merged.
[00:38:02] Okay. Uh if you missed it, I did miss
[00:38:05] it. Uh so there's a PR and we can see uh
[00:38:08] this PR didn't even ask for my review.
[00:38:11] Uh and I'll show you why. um is because
[00:38:13] uh I told first mate to do do that. Uh
[00:38:16] I'll show you the rules. Uh so in first
[00:38:18] mate uh I think it's in config uh config
[00:38:24] or in data in data um projects
[00:38:29] uh MD. Uh so in this project MD there is
[00:38:33] a policy being set on every single
[00:38:35] project. Uh so if I search for fly with
[00:38:38] me uh this is uh policy that I set is
[00:38:41] called direct PR plus yolo. Um so this
[00:38:45] basically says first mate you make your
[00:38:48] judgment calls on this uh and every
[00:38:50] change should raise a PR um without
[00:38:53] going through no mistakes uh and just
[00:38:55] yolo merge if it looks good. Um so this
[00:38:58] is for projects where uh I don't think
[00:39:01] uh an a problem will actually cause any
[00:39:04] harm uh because this fly with me uh
[00:39:06] project is just like a toy u no one is
[00:39:08] actually depending on it. So yeah so you
[00:39:11] can see every project has a different
[00:39:12] policy here uh for most of the project I
[00:39:15] have uh I have no mistakes on uh and uh
[00:39:19] some of them have yolo some of them
[00:39:20] don't have yolo. The ones that have YOLO
[00:39:23] on is usually the projects where a code
[00:39:25] change will not get released
[00:39:27] immediately. Um and we have a chance to
[00:39:29] test them out before we uh release them.
[00:39:32] Uh so yeah, this is where um the
[00:39:34] policies are being managed and you can
[00:39:36] tell your first mate as well which
[00:39:38] projects actually need no mistakes,
[00:39:40] which projects actually uh need your
[00:39:42] eyes before merging a PR. Um so this is
[00:39:45] very um helpful for managing different
[00:39:48] levels of uh guardrails. Uh not
[00:39:50] everything need no mistakes. Not
[00:39:52] everything need uh a uh human review. Uh
[00:39:55] depending on how high stake that is. Uh
[00:39:57] and for no mistakes uh for those of you
[00:40:00] who are already familiar with that no
[00:40:02] mistakes uh is a very strong validation
[00:40:06] pipeline that will do adversarial review
[00:40:08] and uh make sure the code change is
[00:40:10] really safe to merge. Uh that takes a
[00:40:13] long time and use a lot of tokens. So I
[00:40:15] don't actually always use no mistakes uh
[00:40:17] for every change I do. A good way to
[00:40:19] think about this is like for this code
[00:40:22] change, would you have asked a another
[00:40:24] human to review this code? Uh if you
[00:40:27] would not have have another code
[00:40:29] reviewer, then you probably don't need
[00:40:30] no mistakes. Um if the code change is
[00:40:33] risky and high stake enough that you
[00:40:36] would otherwise ask a human peer to
[00:40:38] review, then it's probably worth uh
[00:40:40] activating no mistakes to make sure
[00:40:42] that's really good. Um, and I'll
[00:40:44] probably like show you an example of a
[00:40:46] PR that's merged through no mistakes for
[00:40:48] you to see what that looks like. Um,
[00:40:50] there's actually another uh ship uh
[00:40:52] change that's landed as well. Uh, the
[00:40:54] design kit mock removal. Uh, good.
[00:40:57] That's good. Um, I think we just had
[00:41:00] another uh lavish artifact ready for
[00:41:03] review as well. This is the snow capped
[00:41:05] mountains uh that I asked for. Uh, I'm
[00:41:07] very excited to look at what this looks
[00:41:09] like. Uh, what the snow does today.
[00:41:12] Okay. Yeah, I don't need to know that.
[00:41:14] Uh yeah, today uh it's good to uh for
[00:41:16] you to see that it's uh like this and
[00:41:18] it's not like very mountain uh looking,
[00:41:21] right? That's the reason I asked for a
[00:41:24] better snowy mountain. Uh Fable Fable is
[00:41:28] like really uh careful here. It's like
[00:41:30] done some calculations and everything.
[00:41:33] Uh and it's it's got a good like climate
[00:41:36] model. Uh interesting. um three shading
[00:41:40] studies. I did a lot of studies. That's
[00:41:43] why it took so much time. So there is
[00:41:45] this like painted alpine. Okay. There's
[00:41:48] this uh story book cap. Okay. Ah
[00:41:51] interesting. Uh
[00:41:55] uh there's this glacial jade. Uh how's
[00:41:58] this different from the other ones? It
[00:42:01] looks like kind of similar. Uh and uh
[00:42:04] what's this? Carved peaks. The terrain
[00:42:07] study. Oh. Okay.
[00:42:11] Uh oh, this looks good. Uh this is uh
[00:42:15] like it'll go above the cloud. Uh that
[00:42:17] is also nice.
[00:42:20] Uh compare. We can actually um preview
[00:42:22] these different uh variants.
[00:42:29] This is so nice. like um
[00:42:33] uh it's just really good to have this
[00:42:35] visual uh validation for what this is
[00:42:38] actually going to look like. Uh it's a
[00:42:40] really good way to discuss prototypes.
[00:42:42] Um I actually quite like uh these curved
[00:42:45] peaks. Uh this uh look pretty nice. Um
[00:42:48] but I don't uh want to accept this just
[00:42:51] yet. Um I think I actually want this uh
[00:42:55] the mountain peaks to look more like
[00:42:58] Mount Everest. that kind of mountain if
[00:43:00] you know what I mean. Um so I will uh
[00:43:03] give some feedback here.
[00:43:06] Uh this is mostly good. This is a good
[00:43:08] improvements. Uh but I actually want the
[00:43:11] mountain peaks to look more like Mount
[00:43:13] Everest. Uh can you go like find some uh
[00:43:16] photos of Mount Everest uh and K2 um
[00:43:20] those mountain peaks and try to get our
[00:43:23] uh mountains to be closer to that
[00:43:25] looking
[00:43:28] All right. Uh, so that feedback goes
[00:43:30] back to the fable crew mates. Uh, so
[00:43:32] that's my feedback. Um, and let's, uh,
[00:43:35] come back here and we can see, uh,
[00:43:37] treehouse warning fix, uh, is also
[00:43:39] underway. Maybe one thing I'll show you
[00:43:41] is like, uh, you can see like we went to
[00:43:44] the lavish artifact to review stuff,
[00:43:46] right? Uh, and while we are reviewing,
[00:43:48] uh, the first mate has already like
[00:43:50] printed a lot of information. Uh, right?
[00:43:52] It's got so many things. uh and across
[00:43:55] this whole session, did I miss
[00:43:57] something, right? Did I actually look
[00:43:59] through everything First Mate told me?
[00:44:01] It's really unclear. And this is where
[00:44:03] the chat UX is a little bit limiting. Um
[00:44:06] so what I have here is like in First
[00:44:08] Mate repo, there is a built-in skill
[00:44:11] called AOY. It's just a really good way
[00:44:13] to catch up on things. Um so a Hoy
[00:44:16] basically tells First Mate to summarize
[00:44:18] what First Mate has told you since your
[00:44:21] last message. and uh also pull out any
[00:44:24] open decisions that you haven't made
[00:44:26] yet. Right? So uh here we can see uh it
[00:44:28] uh told us uh it's landed uh this bird
[00:44:31] kinds uh this uh mock removal uh there's
[00:44:34] a bunch of things still underway uh and
[00:44:36] there's still some things waiting for
[00:44:38] me. Uh and these things uh I actually
[00:44:40] directly gave feedback uh to the crew
[00:44:42] mate. So uh it should be okay. Uh
[00:44:45] there's an open call uh snowy mountains.
[00:44:47] Yep. Uh so um the uh the reason uh first
[00:44:51] mate doesn't know we already made a
[00:44:52] decision on snowy mountains uh I already
[00:44:55] gave feedback uh to uh the crew mates is
[00:44:57] because I gave that directly through
[00:44:59] lavish and that goes straight to the
[00:45:02] crew mates and doesn't uh go through
[00:45:04] first mate uh so first mate thinks uh
[00:45:06] it's still open uh which is okay um and
[00:45:09] uh very soon the crewmate will give an
[00:45:10] update and first mate will catch up as
[00:45:13] well. Uh so this is basically a good way
[00:45:15] for uh me to get a sense uh did I miss
[00:45:18] something? Is everything okay? Uh just a
[00:45:21] hoy and I can just keep spamming a hoy.
[00:45:23] It's a very cheap uh call. It's this
[00:45:25] skill doesn't cost too many tokens. Uh
[00:45:28] it's basically a summarization across
[00:45:29] the previous session. Just uh make it a
[00:45:32] lot easier uh for me to um keep uh
[00:45:36] getting a very clear sense of what is
[00:45:38] the next step. Yeah, I think for now I
[00:45:40] just want to wait for at least one PR
[00:45:42] that went through no mistakes pipeline
[00:45:45] so I can show you what does a PR that
[00:45:48] went through no mistakes uh and has done
[00:45:50] the more rigorous validation looks like.
[00:45:53] Uh it's very different from the YOLO PR
[00:45:55] that we merged earlier. Oh, here we can
[00:45:57] see something interesting is happening.
[00:45:59] the treehouse warning fix. Uh it's
[00:46:01] already validated uh pushed to this
[00:46:03] commit but we couldn't create a PR
[00:46:05] because GitHub seems to be returning
[00:46:07] internal server error. Um so first mate
[00:46:10] received this update and it basically
[00:46:13] authorized a retry asking the crew mates
[00:46:16] to just try again. Uh it seems it's
[00:46:18] healthy now. Um and gave me this updates
[00:46:20] and I didn't have to do anything. Um I
[00:46:22] didn't uh I may not even be looking at
[00:46:24] this message right now. So this is one
[00:46:26] of the values that you can get from
[00:46:28] firstmates which is that it's an
[00:46:30] orchestrator that will take care of
[00:46:31] these things for you. So you don't have
[00:46:33] to worry about oh there's a GitHub error
[00:46:36] and uh I need to retry. You don't need
[00:46:38] to think about that. First mate will
[00:46:40] just take care of it. Okay we have a new
[00:46:42] lavish board to review. Uh let's take a
[00:46:45] look. Um five kinds. This is a followup
[00:46:50] uh on the five birds. Um I think yeah so
[00:46:55] it's figuring out how do we let people
[00:46:57] choose the birds uh and it proposed uh
[00:47:00] all these different colors as well. Uh
[00:47:02] so each kind of bird can have many many
[00:47:05] different kind of colors. This is pretty
[00:47:06] cool. Um okay.
[00:47:11] Yeah. Looks nice, right? Looks really
[00:47:13] nice. Um okay. So this is pretty
[00:47:16] straightforward. I would say we just do
[00:47:17] it. Um the word opens. Uh oh. How how
[00:47:21] does it open? Okay. Um
[00:47:26] I think that's pretty straightforward.
[00:47:29] Yeah.
[00:47:31] Um
[00:47:33] let's see what decisions do we have. Oh,
[00:47:35] it's even made sure um the UI will work
[00:47:37] well on the phone. Um that's very
[00:47:40] thorough.
[00:47:41] Uh cool. So decisions, recommendations,
[00:47:46] uh decisions for the captain. What does
[00:47:48] the corner word do?
[00:47:50] Uh, opens the strip. Yeah. Uh, grouped
[00:47:54] by kind on colors first. Keep cycling
[00:47:58] kinds. Yeah, I think we should do a
[00:48:01] Yeah, just a straightforward chooser.
[00:48:04] Whose colors fly when nobody chooses?
[00:48:08] Each kind has its own color. Yeah,
[00:48:10] that's good. Uh, what should be promoted
[00:48:13] from this scout? Uh we want uh I want to
[00:48:16] build this um and together with the list
[00:48:20] under Yeah. everything. Okay. Uh send it
[00:48:23] back. Let's build it. Uh oh, another
[00:48:27] board, the Snowy Mountains. Okay. Uh
[00:48:29] that's also ready for review. Okay. So,
[00:48:32] it looked at some real photos of uh
[00:48:35] Mount Everest, right? Uh that's what I
[00:48:36] asked. And it's got these reference
[00:48:39] images. Uh it like this made sure the
[00:48:42] agent actually understood what I mean by
[00:48:45] like goodlooking mountains. Um so this
[00:48:48] is um good. Uh so uh okay.
[00:48:54] Uh oh yeah, this is starting to look
[00:48:56] better because it's got like the rocks
[00:48:58] and um the snow. Um Oh yeah.
[00:49:04] Um okay.
[00:49:08] What else do we need to review?
[00:49:11] Um, okay. So, these are the previous
[00:49:13] variants, right? And I think, uh, the
[00:49:15] agent just introduced this new variants
[00:49:18] D, uh, here.
[00:49:22] Uh, okay, cool. I think this is better.
[00:49:25] Um, so let's probably make a decision on
[00:49:27] this as well. Um,
[00:49:31] compare.
[00:49:35] Uh, okay. Let's see. Uh, I think the
[00:49:38] variant D is the new one. Um, and yeah,
[00:49:41] I think it's like better than the other
[00:49:43] ones. Um, so let's do it.
[00:49:48] Uh, let's do it. Let's do it. Um, D.
[00:49:53] Wait.
[00:49:55] Uh, yeah, it's just straightforward D,
[00:49:58] right? Uh, okay. Let's just choose D.
[00:50:01] Should the mountains themselves change?
[00:50:04] Uh
[00:50:07] what? How does the mountain change?
[00:50:09] Pyramid peaks as shown. Uh taller. Yeah,
[00:50:13] I do want the shapes to change. Uh
[00:50:17] taller and sharper.
[00:50:20] Um okay, cool. That's it as well. So
[00:50:25] yeah, this is basically how I make
[00:50:27] decisions. uh the agents will bring
[00:50:28] these decisions to me with a lot of
[00:50:31] context with a lot of the um uh the
[00:50:33] homework that I can see um and the
[00:50:36] visuals the prototypes as well. This
[00:50:38] process really helps me understand what
[00:50:40] the agent has done what we are actually
[00:50:42] choosing between and also helps the
[00:50:44] agent get to a good implementation that
[00:50:47] I will be happy with as well. Uh so
[00:50:49] let's get back to this. Um yeah the
[00:50:51] choices are locked in. I think I might
[00:50:53] have made a mistake in the beginning and
[00:50:55] I didn't actually get the northern
[00:50:57] lights uh prototype to start uh because
[00:51:00] there's no crew mates that's doing the
[00:51:02] northern lights. Uh yeah, I guess that's
[00:51:05] okay. I'll do that later. Uh for now uh
[00:51:07] we'll just ignore that. Okay, we just
[00:51:09] have two more PRs landed. Uh the bird
[00:51:11] varants uh selector and the treehouse
[00:51:13] warning fix. Uh let's look at the
[00:51:15] treehouse one. Um because I think this
[00:51:18] one went through no mistakes. Uh and I
[00:51:20] also let um first mate do yolo merge for
[00:51:23] this one because treehouse does not
[00:51:25] automatically release. Uh every time I
[00:51:27] create a new release I will test things
[00:51:29] out as well. Um but even at this PR
[00:51:31] level um no mistakes does a lot of heavy
[00:51:34] lifting for us. Uh so I'll just walk
[00:51:36] through the PR structure here. The
[00:51:38] intent was basically my requirements uh
[00:51:40] for this task. Um and what changed
[00:51:42] there's a quick summary uh uh the
[00:51:45] duplicated uh warning. Yep. Uh that's
[00:51:48] what we asked. Uh and there's a risk
[00:51:50] assessment. This is very helpful because
[00:51:52] um usually when the PR is having a uh
[00:51:56] big blast radius or having some kind of
[00:51:58] unresolved uh problem, it will have a
[00:52:01] medium or high uh risk assessment for
[00:52:03] me. When I see this is low, I already
[00:52:05] know like I don't I probably don't need
[00:52:07] to take too much look. Um and there's a
[00:52:09] testing section. Uh these are the live
[00:52:11] validation that um no mistakes the
[00:52:14] agents in the no mistakes pipeline did.
[00:52:17] Uh so it did uh nine out of 10
[00:52:19] scenarios. Uh and these scenarios are
[00:52:21] basically the things that prove this
[00:52:24] change does work according to our
[00:52:26] intent. Right? So uh it said get this um
[00:52:30] uh this lease will wants on std error um
[00:52:34] repository level hooks remain untrusted
[00:52:36] uh not executed. Yeah. So it basically
[00:52:38] like validated everything that we care
[00:52:41] about this live with the product end to
[00:52:43] end. Uh and there's evidence as well. Um
[00:52:46] and I think there's like yeah there is
[00:52:48] further like uh logs that we can look at
[00:52:51] to uh understand uh what was really
[00:52:54] tested. There was one scenario skipped
[00:52:57] uh and this one is untested uh
[00:52:59] repository config configuration
[00:53:01] documentation directs user to places. Oh
[00:53:04] documentation okay yeah documentation
[00:53:06] does not need a live testing. So uh
[00:53:09] that's probably it. Yeah. So this risk
[00:53:11] assessment and testing uh this
[00:53:12] validation is basically how I develop uh
[00:53:15] confidence in a code change without
[00:53:18] having to look through every single line
[00:53:19] of the code. Usually when the risk
[00:53:21] assessment is not low then I will go
[00:53:23] take a look at the code as well. Uh but
[00:53:25] when it's low and it's well tested I
[00:53:27] don't even look at the code. Uh it's
[00:53:29] usually just good. Okay. We are probably
[00:53:31] not going to wait for every single uh
[00:53:33] crew mate to finish. Hopefully this
[00:53:35] video so far has already given you a
[00:53:37] look into how I work, how I direct a
[00:53:39] large number of agents to work in
[00:53:41] parallel without going insane. I will
[00:53:44] drop a link to everything I mentioned in
[00:53:46] the description of this video. And if
[00:53:47] you have any questions, please just
[00:53:49] leave a comment or join my Discord
[00:53:51] server and I'll try to get back to you.
[00:53:53] Thank you for watching and see you next
[00:53:55] time.
