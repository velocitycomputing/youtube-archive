---
video_id: c0gVowvMR-g
title: "Anthropic Just Dropped the Update Everyone's Obsessed With: Dynamic Workflows"
channel: Ray Amjad
url: "https://www.youtube.com/watch?v=c0gVowvMR-g"
watched_date: 2026-06-16
watched_at: "2026-06-16T12:00:00Z"
watch_count: 1
duration_seconds: 910
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 49
watched_at_precision: date-from-history-label
watched_percent: 41
estimated_watched_seconds: 373
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Anthropic released a new Workflow tool for Claude Code that uses JavaScript-based deterministic code to orchestrate multiple sub-agents instead of having the main session pass results back and forth. This solves the previous "token tax" problem where every intermediate result consumed context and reduced orchestrator quality over time. Workflows use JavaScript files with phases, agent definitions, schemas, and logic (loops, conditionals, pipelines). Instead of results bouncing through the main conversation, they pass directly between agents. The tool supports parallel execution, structured output schemas, visibility into all running agents, automatic retries, and token budgets to control costs.

To use it: enable the feature via environment variable, create `.claude/workflows/` folder with JavaScript files defining your workflow's meta (name, description, phases), schemas, and agent stages. Use `/workflows` command to browse history and run workflows. Workflows are best for repeatable daily tasks, parallel agent fan-outs, conditional logic, or multi-stage processes that might fail partway through (they're automatically resumable). For one-off tasks, skip workflows. You can ask Claude Code to identify workflow opportunities in your previous sessions or download a workflow creator skill to help you build them.

## Transcript

[00:00:00] Okay, so a few hours ago, Anthropic
[00:00:01] added a brand new feature that may
[00:00:03] fundamentally change the way that you
[00:00:05] use Claude Code going forwards. And that
[00:00:07] is by adding the workflow tool for
[00:00:09] deterministic multi-agent orchestration.
[00:00:12] Now, they haven't yet made an
[00:00:13] announcement about this feature, so by
[00:00:14] watching this video, you're going to be
[00:00:16] ahead of the curve. So, I'll be going
[00:00:17] through exactly what the feature is and
[00:00:19] how you can use it to be a Claude Code
[00:00:21] power user. So, they do say that it is
[00:00:23] off by default and we have to set this
[00:00:25] environment variable to enable it. So, I
[00:00:27] will copy this over, go to the terminal,
[00:00:29] paste this in, add a space, and then run
[00:00:31] Claude. And after doing that, you will
[00:00:33] see we have a brand new slash command,
[00:00:35] which is slash workflows. And this will
[00:00:37] allow you to browse your workflow
[00:00:38] history, running and completed. So,
[00:00:40] going over here, I have no workflows I
[00:00:42] have run in this session. So, we
[00:00:44] basically got to go ahead and make
[00:00:46] ourselves a workflow. But essentially, I
[00:00:48] can go back to a previous session where
[00:00:49] I was testing out the workflows feature,
[00:00:51] and if I do slash workflows inside of
[00:00:53] here, then I can see that these are all
[00:00:55] the workflows that I previously ran. So,
[00:00:57] I ran this like triage workflow for
[00:00:59] century, and I can see that it looks
[00:01:00] like this. So, we have different stages
[00:01:02] of a workflow that I predefined, where
[00:01:04] each workflow is running as a individual
[00:01:06] sub-agent. Then I can press enter on any
[00:01:08] of these workflows, and then I can see
[00:01:10] the run that happened, all the tool
[00:01:12] calls that were made, the prompt, and so
[00:01:13] forth. And then I can go over to any
[00:01:15] stage of the workflow and see all the
[00:01:17] different agents that have run inside of
[00:01:18] the workflow, how many tools they used,
[00:01:20] tokens, and so forth. Okay, so before
[00:01:22] actually going ahead and making a
[00:01:24] workflow, I want to talk about what
[00:01:26] people have been doing until now before
[00:01:28] the update, and why this new approach is
[00:01:30] better and solves a lot of the problems
[00:01:31] that people have been previously facing.
[00:01:33] So, until now, you may have had some
[00:01:35] kind of skill that described a set of
[00:01:37] steps, a workflow, whereby Claude, your
[00:01:40] main session, would be the orchestrator,
[00:01:42] and then tell a sub-agent to do
[00:01:43] something, like implement a feature. It
[00:01:46] would then pass that information back
[00:01:47] into main session, and that would then
[00:01:49] go into the next sub-agent, that would
[00:01:51] then do a review, pass it back to main
[00:01:53] session, go to next sub-agent, and so
[00:01:55] forth. So, essentially, the orchestrator
[00:01:57] is deciding what to run next and holding
[00:01:59] every intermediate result. And this is
[00:02:01] the old laissez-faire way of making
[00:02:03] workflows that people have been doing
[00:02:05] until now. Now, this can have some
[00:02:06] drawbacks. The first of all being a
[00:02:08] token tax. So, every time Cloud Code
[00:02:11] spins up a sub-agent and then it gets a
[00:02:13] result back, that goes into the main
[00:02:15] context window of the orchestrator and
[00:02:17] then it's passed again into next
[00:02:18] sub-agent, goes back, and so forth. And
[00:02:20] this can consume quite a lot of tokens
[00:02:22] in your main session, especially if you
[00:02:24] have something like 10, 15 sub-agents
[00:02:26] that run. And your main orchestrator
[00:02:28] would do worse over time as a context
[00:02:30] window fills up with all these results.
[00:02:32] And these tokens are going back and
[00:02:33] forth unnecessarily between the main
[00:02:36] orchestrator and the sub-agents. So,
[00:02:38] ideally, they should be passed directly
[00:02:39] from one to the next without ever
[00:02:42] entering the context window of the
[00:02:43] orchestrator. We also have some other
[00:02:45] problems whereby you may trigger a
[00:02:46] workflow and you have no visibility to
[00:02:49] what is going on. You basically see some
[00:02:51] kind of like wall of text scroll by as a
[00:02:53] workflow is triggering over the next 20,
[00:02:55] 30 minutes. And finally, because the
[00:02:56] orchestrator's context window is filling
[00:02:58] up, by passing tokens back and forth
[00:03:00] between different sub-agents, eventually
[00:03:02] just starts forgetting and acts more
[00:03:04] sloppy and lazy, which is not what you
[00:03:06] want from an orchestrator. And this
[00:03:07] forgetting in the orchestrator can be
[00:03:09] even worse if you have conditionals. So,
[00:03:11] you may have a conditional like, "If we
[00:03:13] get this particular result, then spawn
[00:03:15] another sub-agent to verify it. If not,
[00:03:18] don't do that." So, then the Cloud Code
[00:03:19] team were like, "Okay, so what if
[00:03:21] instead of having a non-deterministic
[00:03:23] model being a wrapper of all these
[00:03:25] sub-agents, we had a code wrapper
[00:03:27] instead? Since it have a model passing
[00:03:29] information back and forth between
[00:03:30] sub-agents and incurring a token tax
[00:03:33] every single time, and also getting
[00:03:34] sloppier the longer it runs, what if we
[00:03:37] just had a workflow file, some kind of
[00:03:39] code that could pass the result directly
[00:03:41] without ever entering the main
[00:03:43] conversation? Which means that you can
[00:03:44] have like 20, 30, 100 agents run one
[00:03:47] after another and the context of the
[00:03:49] main orchestrator never actually filling
[00:03:51] because the orchestrator is now code
[00:03:53] instead. So, the way that the workflow
[00:03:55] tool works is we have a workflow.js
[00:03:58] file, which is a JavaScript file, and
[00:04:00] this basically defines how our workflow
[00:04:02] is going to look. So, we have phases
[00:04:04] that we can define. So, for example, we
[00:04:06] can have a review phase, and then we can
[00:04:08] define an agent that runs, like does a
[00:04:10] basic review, this is a prompt, and then
[00:04:13] if the review passes, it would just end
[00:04:15] as it is by doing a return. If it
[00:04:17] doesn't, then it will fix the issues.
[00:04:19] And because this is code, we can also
[00:04:20] implement loops as well. So, you can see
[00:04:22] in this example, we would have like
[00:04:24] implement the feature, and then over
[00:04:26] here it would do up to three reviews,
[00:04:28] and if the review passes, then it would
[00:04:29] just break. If it doesn't pass, then it
[00:04:31] would fix it with a different agent. So,
[00:04:33] every time you see agent over here, that
[00:04:35] is a different sub-agent running. And
[00:04:37] what's interesting about this as well is
[00:04:38] that we can define schemas as well. So,
[00:04:41] we want this review sub-agent to return
[00:04:43] schema of like either past or issues
[00:04:46] that we can then reference in the next
[00:04:48] agent. Okay, now let's go through the
[00:04:50] process of actually making a workflow.
[00:04:52] So, I'll be manually going through the
[00:04:53] file so you can see what it's like
[00:04:55] behind the scenes, but ideally you would
[00:04:57] be getting Cloud Code to make your
[00:04:58] workflows instead. So, you want to go to
[00:05:00] your .cloud folder in your project and
[00:05:01] make a brand new folder, which is a
[00:05:03] workflows, and then inside of this we
[00:05:05] can define a workflow. So, I'm going to
[00:05:07] call this triage-sentry.js.
[00:05:10] So, this will be a JavaScript file, and
[00:05:12] essentially at the very top we have to
[00:05:14] define a meta for the workflow. So, the
[00:05:16] workflow meta looks kind of like this.
[00:05:18] We have the name, the description that
[00:05:20] will appear inside of Cloud Code, and
[00:05:22] then we have the different phases as
[00:05:24] well. So, then we can define some
[00:05:25] schemas. So, this will be one of our
[00:05:27] schemas, which is an issues schema. So,
[00:05:30] you can see over here it has the issue
[00:05:32] ID, the title, and the user count of how
[00:05:34] many users are affected. Then we will
[00:05:36] define another schema here, verdict,
[00:05:38] which is whether or not it was fixed and
[00:05:40] any notes about this. And then because
[00:05:42] we can pass in arguments into our
[00:05:44] workflows, for For you can see an
[00:05:46] argument would be passed in kind of like
[00:05:47] this. Minimum number of users affected,
[00:05:50] 20 users. We have to then pass the
[00:05:52] arguments so they are loaded in
[00:05:54] properly. So it looks kind of like this.
[00:05:56] So what happens here is that 20 will be
[00:05:58] the default. So any issue that affects
[00:06:00] more than 20 users on Sentry will be
[00:06:02] loaded in unless we have specified an
[00:06:05] argument instead. So firstly, we'll
[00:06:06] define our first phase that will load in
[00:06:09] the issues. So phase over here will pull
[00:06:12] in issues. So we define an agent. So you
[00:06:14] can see that it says use a Sentry MCP to
[00:06:16] list unresolved issues. For each return
[00:06:18] its ID, title, and affected user count.
[00:06:21] And the schema that we define up here
[00:06:22] for issues is also passed into agent so
[00:06:25] it knows what kind of schema to return
[00:06:27] back. Now the interesting thing is that
[00:06:28] we can now define some plain JavaScript.
[00:06:30] So if we were to write something like
[00:06:32] this, then we can basically filter down
[00:06:34] the issues that are returned from to
[00:06:36] ones that are above the threshold that
[00:06:38] we defined earlier. So this will then
[00:06:40] log inside of the workflow for us to
[00:06:42] see. And if no issues are present that
[00:06:44] are big enough, then it will just end
[00:06:46] the workflow as it is right over here.
[00:06:48] So it'll say fixed, no issues affecting
[00:06:50] more than the threshold number of users.
[00:06:53] And now next up, we can define a
[00:06:54] pipeline. So this is our pipeline. And
[00:06:57] essentially, all the big issues that we
[00:06:59] have will be passed into a two-stage
[00:07:01] process. The first stage, what it will
[00:07:03] do is that for each of the issues that
[00:07:05] are returned, so let's say we have five
[00:07:07] issues are returned, it will then
[00:07:09] investigate and fix the issue. And then
[00:07:11] it will go to next stage of verifying
[00:07:13] that the fix is actually real and
[00:07:14] working. And then finally, at the very
[00:07:16] bottom, we can see this of how many
[00:07:18] issues were actually fixed, how many uh
[00:07:20] issues we found, and their final
[00:07:22] results. So the interesting thing that
[00:07:24] you will notice is that we're basically
[00:07:25] mixing in plain JavaScript with the
[00:07:28] sub-agents that will be running inside
[00:07:30] of Cloud Code. So the issue ID from
[00:07:32] earlier, the title, and the user count
[00:07:35] are being passed directly into the
[00:07:36] prompt. So they're not going back in
[00:07:38] through the main orchestrator, they're
[00:07:40] going in through the prompt instead. So
[00:07:41] after that, triage sentry, then you will
[00:07:43] see that it appears over here with the
[00:07:46] workflow tag next to it. And if I press
[00:07:48] enter, then you will see that it begins
[00:07:50] to trigger a workflow. So, it's
[00:07:51] triggering the triage sentry workflow,
[00:07:54] and it's running with zero out of one
[00:07:56] agents right now. It has one out of
[00:07:58] three phases, and then I can see it
[00:08:00] right over here as a background
[00:08:01] workflow. So, if I go over here, then I
[00:08:03] think I have to zoom out. I can see
[00:08:05] right now it's pulling the issues. If I
[00:08:07] press enter, then I can see that it's
[00:08:11] running here. Press enter again. I can
[00:08:13] see the different tools that it's
[00:08:14] calling and the prompts and stuff like
[00:08:16] that. And then I can go back, or I can
[00:08:18] pause this workflow as well by pressing
[00:08:20] the P command. So, let me go back to
[00:08:21] workflows and then press P again to
[00:08:23] resume it. And you can see the workflow
[00:08:25] has now returned a result of 25
[00:08:28] unresolved sentry issues. So, if I go
[00:08:30] back and then go over to next stage
[00:08:32] here, which is a fixing stage, then I
[00:08:33] can see that it only decided to spin up
[00:08:35] three sub-agents because only three of
[00:08:37] them were affecting more than 20 users.
[00:08:40] So, all of these sub-agents are running
[00:08:41] in the background right now, and I can
[00:08:43] skip any of these sub-agents by pressing
[00:08:44] X or retrying them. And one nice thing
[00:08:47] about this is that we have automatic
[00:08:49] retrying. So, if one of the sub-agents
[00:08:50] were to fail for any reason, like the
[00:08:52] MCP server stopped working, then Cloud
[00:08:55] Code would then retry that particular
[00:08:56] sub-agent. And then if I press down, I
[00:08:58] can see that the verifying has not been
[00:09:00] started yet. So, while this workflow is
[00:09:01] running in the background, I can just
[00:09:03] continue to send messages to Cloud and
[00:09:05] work with Cloud, or I can trigger
[00:09:06] another workflow as well. So, I can have
[00:09:08] multiple different workflows running at
[00:09:10] the same time. So, by default, it's
[00:09:12] using the Opus model of the main
[00:09:13] session, but I can define a different
[00:09:15] model. So, while we're waiting on this,
[00:09:17] let's go through a different workflow.
[00:09:19] So, here is another workflow that I
[00:09:21] made, what's called dead code sweep. So,
[00:09:24] find and remove unused code round by
[00:09:26] round. So, we don't have any arguments.
[00:09:29] We have the meta defined over here, so
[00:09:30] the name and description. Then we have
[00:09:32] some types defined over here. And then
[00:09:34] we define our own variables. So, how
[00:09:37] many rounds do we want in this loop? So,
[00:09:39] then we have a while loop right over
[00:09:41] here, whereby one agent will find unused
[00:09:44] code in the code base. It will then list
[00:09:46] it out according to a schema that we
[00:09:48] defined earlier. If no dead code has
[00:09:50] been found, then it would basically end.
[00:09:52] But, if dead code has been found, then
[00:09:54] for each of those issues, each of that
[00:09:56] dead code, it would then remove it one
[00:09:58] by one. And then once this is over, it
[00:10:00] will then run another time up to eight
[00:10:03] times, and it will exit out if it finds
[00:10:05] out there's no more dead code available.
[00:10:07] So, that's a pretty good example of
[00:10:08] combining loops inside of these
[00:10:10] workflows and adding some conditional
[00:10:12] logic as well. Another example is for
[00:10:14] personalizing outreach. So, you may want
[00:10:17] to load a set of leads from a file,
[00:10:19] research them inside of subagents, and
[00:10:21] then draft and save a personalized
[00:10:22] message. So, we have our leads object up
[00:10:25] here, then it loads in any arguments,
[00:10:28] such as the leads file, where we want
[00:10:30] our emails to be stored after we have
[00:10:31] written it, and then we have the
[00:10:33] different phases. So, first phase will
[00:10:35] load in the leads from the file. We
[00:10:37] could also load it in programmatically
[00:10:39] if we have structured data like a CSV.
[00:10:41] So, the first pipeline will research the
[00:10:43] lead, and you can imagine this like does
[00:10:45] research with a cheap API or cheap MCP
[00:10:48] server. If it can't find anything for
[00:10:50] that lead, then it would switch over to
[00:10:52] a more expensive one in a conditional.
[00:10:55] And you can see this first model is
[00:10:56] running with high Q over here, and then
[00:10:58] any information will be passed into the
[00:11:00] next stage, where it will basically
[00:11:02] write that copy. Now, of course, this is
[00:11:04] a simple example. You may want to make
[00:11:06] it more complicated for your own
[00:11:07] workflows that you have defined. And now
[00:11:09] the workflow has completed. So, it used
[00:11:11] seven subagents, 400,000 tokens, and
[00:11:14] this was the stage that I went through.
[00:11:16] So, we verified each of those fixes
[00:11:18] successfully, and yeah, this looks
[00:11:20] pretty good. Now, let's actually do our
[00:11:22] personalized outreach workflow. So, I
[00:11:24] have a list of leads over here that I'm
[00:11:26] going to be contacting, and this is
[00:11:28] completely for demo purposes. And now
[00:11:30] our workflow is underway. So, going over
[00:11:32] to workflow, we can see that it's
[00:11:34] loading the leads right now. And now we
[00:11:36] have eight research agents, all high
[00:11:38] queue ones, spawning parallel with one
[00:11:41] agent per lead. And that's because we
[00:11:42] have eight leads inside of our CSV. And
[00:11:45] now after it researches all of them, so
[00:11:47] it seems to be going pretty fast, then
[00:11:49] it will move on to the next stage, where
[00:11:50] it will write eight different messages,
[00:11:53] uh ideally, for each of the leads
[00:11:55] separately. And you can kind of imagine
[00:11:56] a workflow whereby like it couldn't
[00:11:59] really find the contact details using a
[00:12:01] lighter model, and then it switches over
[00:12:03] to a heavier model, and it uses more
[00:12:04] expensive APIs to get those details for
[00:12:07] the leads. So, finished writing the
[00:12:08] personalized outreach with the Opus
[00:12:10] model. So, we can then see we have a
[00:12:12] brand new folder with the output, and
[00:12:14] then we have all the personalized
[00:12:16] outreach for Bill Gates or whatever,
[00:12:18] blah blah blah, like this is outreach.
[00:12:19] And of course, I don't think this would
[00:12:21] get a reply, but like this is for demo
[00:12:22] purposes. Now, to make making a workflow
[00:12:25] easier for you, I have a workflow
[00:12:27] creator skill that you can download from
[00:12:29] below from my GitHub. And this teaches
[00:12:31] Cloud Code how to make a workflow file,
[00:12:33] all the functionality that is available,
[00:12:35] and stuff like that. But I think once
[00:12:36] the feature is officially announced,
[00:12:38] then maybe Infropic will add their own
[00:12:40] official workflow creator skill, in
[00:12:42] which case you should use that once it
[00:12:44] is released. Anyways, so to summarize,
[00:12:46] we have a toolkit over here. We have a
[00:12:48] agent where we spawn one fresh Savage
[00:12:50] agent every time. We can run them in
[00:12:52] parallel. So, we can batch like 10
[00:12:54] agents parallel, wait for all of them to
[00:12:56] complete. We can use pipeline where
[00:12:58] streams items through stages instead.
[00:13:01] So, for example, with the lead outreach
[00:13:03] workflow, if you were paying close
[00:13:05] attention, you may have noticed that as
[00:13:07] soon as one research agent was done,
[00:13:09] then the next writing a message agent
[00:13:11] would start immediately, rather waiting
[00:13:12] for all eight research agents to be
[00:13:14] done. And that is because of the
[00:13:15] pipeline here. So, we can combine these
[00:13:17] both together, parallel and pipeline.
[00:13:19] Then we have a schema, so we get a
[00:13:21] structured answer back. We have the
[00:13:23] phase log, which basically gives us a
[00:13:25] live view of what is happening. And then
[00:13:27] finally we have the arguments that would
[00:13:29] be passed in as well. Now, we also have
[00:13:31] budgets when it comes to our workflow,
[00:13:33] too. So, there is a budget parameter.
[00:13:35] So, for example, in this case, we can
[00:13:37] have a while loop, and while the budget
[00:13:39] remaining is more than 50,000 tokens, we
[00:13:42] can try and find end of a bug, for
[00:13:44] example. So, this can kind of keep your
[00:13:45] workflow structured and prevent them
[00:13:47] from growing out of control. Now, I
[00:13:49] would suggest basically getting Claude
[00:13:50] codes to look for your previous
[00:13:52] sessions, identify any opportunities for
[00:13:54] making workflows, and make workflows
[00:13:56] around them. So, for example, if you're
[00:13:58] a big fan of Ralph loops, and you like
[00:14:00] using Ralph loops to quickly go through
[00:14:02] a backlog of issues, for example, then
[00:14:04] you can make a workflow where it loads
[00:14:06] in the issues from GitHub. It will then
[00:14:09] go through a loop, whereby for each
[00:14:11] issue it will then make a fix, it will
[00:14:13] do verification, it may also do an
[00:14:16] adversarial review as well, and then it
[00:14:18] will move on to the next issue. So, I've
[00:14:20] made a whole bunch over here that I'm
[00:14:21] testing myself, like implement and
[00:14:23] review. So, when should you be reaching
[00:14:25] for a workflow? Firstly, anytime you
[00:14:27] want to do something repeatable, so you
[00:14:29] will be doing it over and over again,
[00:14:30] probably every single day. Anytime you
[00:14:32] want to fan out agents, for example,
[00:14:35] based on conditionals or loops, or
[00:14:37] getting some data in some way, and
[00:14:38] anything that may seem long enough to
[00:14:40] fail halfway. So, you can split that
[00:14:42] down into workflow, which is
[00:14:44] automatically resumable, because Claude
[00:14:46] code will retry each sub-agent up to
[00:14:48] three times if it does fail. But, for
[00:14:50] any one-off task, you probably should
[00:14:52] just let Claude do it manually, there's
[00:14:53] no point making a workflow. Because we
[00:14:55] get to take advantage of the fact that
[00:14:57] the results aren't being passed back and
[00:14:59] forth from the main session and the
[00:15:01] sub-agents, it just goes directly
[00:15:03] because of the code. And if you want to
[00:15:04] get free insights delivered from me on a
[00:15:06] regular basis, then you may want to join
[00:15:08] my newsletter as well, link down below.
