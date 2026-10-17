---
record_id: "youtube:TlmTypTQFj8"
video_id: TlmTypTQFj8
title: The hidden truth inside Firstmate AI
channel: Hal Shin
url: "https://www.youtube.com/watch?v=TlmTypTQFj8"
watched_date: "2026-10-10"
watched_at: "2026-10-10T23:58:27Z"
watch_count: 1
duration_seconds: 1428
source: youtube-history-browser
added_date: ""
history_label: Oct 10
history_order: 93
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 143
transcript_status: fetched
transcript_content_hash: eb4d85fe233c97052bc7f083b6d9373c84c31e179c41937562a957e122ecfaaf
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

Firstmate is an open-source orchestration tool created by engineer Kun Chen that allows a single agent to supervise multiple worker agents operating in parallel across isolated Git worktrees. Rather than a downloaded application, it's a cloned repository containing AGENTS.md (an operating contract with five hard rules), 20 skill manifests, and 140 bash helper scripts that spawn workers, supervise their progress, and return finished pull requests for human approval. The system runs on a custom stack of eight AI-focused CLI wrappers (gh-axi for GitHub, chrome-devtools-axi for browser automation, treehouse for worktree management, and others) designed specifically for agent interactions, plus a no-mistakes validation gate that reviews work before shipping rather than requiring human approval at each tool call.

For your own workflows: wrap the CLIs you already use, tuning them for what agents actually need (gh-axi reduced GitHub CLI output by 35% while cutting agent round-trips from six to eight down to three). Build missing CLIs for your specific use cases—Kun built overcf for Cloudflare, the author built Notion Ops for workspace navigation—prioritizing meaningful error messages agents can learn from rather than perfect code. Replace token-expensive heartbeat loops with bash scripts that codify reasoning instead. Most importantly, create reusable systems with shared conventions across projects so you learn the abstraction once and benefit everywhere; don't adopt someone else's stack wholesale, but take their principles (CLI design, verification gates, automation layering) and adapt them to your own needs.

## Transcript

[00:00:00] Here's a story I find fascinating. An L8 principal engineer, one of the most senior engineers at
[00:00:06] Meta, quits his job and instead of launching a startup or raising a fund like everybody else,
[00:00:10] he spends his year building wrappers. He wraps the GitHub CLI, he wraps Chrome DevTools,
[00:00:16] he wraps Git worktrees, code validation, and there's even a tool called gnhf,
[00:00:20] which stands for goodnight, have fun, that basically babysits his agents while he sleeps.
[00:00:25] And then he stitches all of them together into something called Firstmate, an open source project
[00:00:30] that hit 3,000 stars in two months. Now, funny story, I actually started recording this video
[00:00:35] about Firstmate itself, but halfway through, I actually realized that the tool is not the
[00:00:40] interesting part. The interesting part is what Kun Chen understood that a lot of us kind of glossed
[00:00:44] over. In the age of AI agents, the highest yielding thing you can do for your productivity is to write
[00:00:49] the software that adapts to your specific workflows. So in this video, I'll show you what Firstmate
[00:00:55] actually is, the system hiding underneath it, and also the four principles that you can take away
[00:01:00] to build your own version as well. Without further ado, let's get started.
[00:01:04] So what exactly is Firstmate? The tagline is, talk to one agent and ship with a crew. You talk to a
[00:01:11] single agent, the Firstmate, and it runs a fleet for you, spawning workers into their own terminal
[00:01:16] windows and giving each one of them a clean Git worktree, supervising them, and handing back to you
[00:01:21] finished pull request. You are the captain. And yes, the whole thing is nautically themed all the way
[00:01:27] down. But here's the really interesting part. Firstmate is not an app. There's no binary to
[00:01:32] download. There's no installer, no server, none of that stuff. You literally just Git clone the repo,
[00:01:38] CD into it, launch your Claude Code or Codex or your favorite agent harness, and that's it. So the repo
[00:01:44] itself is the product. And Kun calls this an agent distro. And before you roll your eyes at yet
[00:01:49] another term in the AI space, look at what's actually inside of the clone. There's AGENTS.md,
[00:01:55] and that contains 562 lines of operating contract. That includes identity, rules, procedures, and there
[00:02:02] are 20 skill manifests plus 140 helper scripts under the bin, almost all in plain bash script, doing the
[00:02:09] deterministic work like spawning, supervising, and tearing down. And there are exactly five hard rules
[00:02:15] in priority order. The orchestrator itself is actually read-only. Only the crewmates touch the
[00:02:20] code. In fact, Firstmate crew strictly operates in Git worktree, so it never pollutes your existing
[00:02:26] repositories. Rule 2. Never merge a pull request without the captain's explicit approval. The crew can build
[00:02:33] all day long if they want, but at the end of the day, shipping is your call. Never tear down
[00:02:37] unlanded work. If a worktree still has changes that haven't landed somewhere, no agent gets to delete
[00:02:42] it. So nobody quietly throws away half a day's work. Rule 4. Crewmates never address the captain.
[00:02:47] Every worker reports up through the chain to the Firstmate, and the Firstmate talks to you. So at the
[00:02:52] end of the day, you're only talking to one Firstmate instead of 10 or 20 Crewmates. And finally,
[00:02:58] Rule 5, which is my favorite. Report outcomes faithfully. If the work failed, say so plainly.
[00:03:04] Isn't it funny that they had to write that down? Okay, let me give you a quick demonstration
[00:03:07] of how Firstmate works before we get into the more interesting parts of this. So on the left here,
[00:03:12] I have Firstmate repository. If I spin up Claude Code and say hi, you'll notice that it's responding
[00:03:18] back with the Ahoy Captain, the nautical theme, and it's spinning up fm-session-start. Basically,
[00:03:23] these are some of the binaries that run behind the scenes to kind of check on the work that the
[00:03:27] Firstmate crewmates are doing. But to actually work on stuff, we'll want a sample repository for Firstmate
[00:03:32] to register and to fix bugs on. So for that, I have fm-demo-app on the right-hand side here. And if we run
[00:03:37] npm test, you will see that we have a slugify keeps distinct pages distinct bug that is not passing.
[00:03:44] So we're going to get Firstmate to fix this for us. So we're going to say, register my local project
[00:03:49] fm-demo-app as a local only project and then fix its failing test.
[00:03:58] So as Firstmate is working, I'll show you how this is kind of working behind the scenes. If you run
[00:04:02] LS on the Firstmate repo, you'll see that there is a projects directory. If you CD into that projects
[00:04:07] directory, you'll see that it has cloned the fm-demo-app inside of here. So it's going to use this
[00:04:11] clone and create worktrees off of this. Now, if you look at what Firstmate is doing behind the scenes
[00:04:16] here, you'll notice that it's calling a lot of tools, but it's also kind of inspecting what the
[00:04:20] actual problem is before it delegates to the crewmates. And so after it has identified what the problem is,
[00:04:26] it creates a brief that it's going to pass down to that crewmates subagent. And we can see that here,
[00:04:31] fix the failing test in linkpile. It tells you exactly where it is, what the root cause is,
[00:04:36] acceptance criteria, so on and so forth. It's basically doing the delegation part here. And
[00:04:40] then it runs fm-spawn.sh, which is the part that spawns up that crewmate. And then there is that fm-session-start
[00:04:46] script that basically loops to see if the work is completed. And then if it is, it alerts the
[00:04:51] Firstmate back so that the Firstmate is able to respond back to us. And you can see here that there is
[00:04:56] something called .treehouse. And this is one of the CLIs that Firstmate uses under the hood
[00:05:01] to manage your worktrees for you. And so you can kind of start to see that there's a lot of
[00:05:05] different moving parts to Firstmate that makes this operational without it being an actually fully
[00:05:10] shipped application. And this is something that I will touch on in the next section. And the nice
[00:05:14] thing about Firstmate is that you can see the crewmates actually work. And in my case, we're using
[00:05:18] cmux here. And Firstmate has spun up the crewmate inside of a cmux terminal session. We can see the
[00:05:24] prompt, you are a crewmate, an autonomous worker agent, man. Well, I didn't get to fully finish
[00:05:29] reading it before Firstmate cleaned up that session. But you can basically see for yourself
[00:05:32] the actual AI agent working on your terminal, which is really nice. And you also saw the fact
[00:05:38] that it cleaned up the agent after the task was completed as well, which is really nice.
[00:05:42] And unfortunately, in my case, we had a little bit of an accident where the rehearsal for this video
[00:05:47] kind of created some test copies that it's kind of having a hard time distinguishing. But hopefully
[00:05:51] it's able to kind of figure it out for this actual recording. We'll see how it goes. And yeah, we can
[00:05:56] see that there is another session that has started and we can go check out the prompt now. You are a
[00:06:01] crewmate, an autonomous worker agent managed by Firstmate. Work on your own. Do not wait for a
[00:06:05] human at all. Fix the failing test and linkpile. And then there are some more context to this specific
[00:06:10] task. And you can see the rules that are passed on here. Never push to any remote or never open a PR.
[00:06:15] Work on your own. Stay inside of this worktree. Use gh-axi. And we'll talk about these CLIs that are
[00:06:22] used in Firstmate in the next section for GitHub operations and chrome-devtools-axi for browser
[00:06:28] automations. And so it has completed its work. Firstmate will be alerted of the fact that it's
[00:06:32] completed. And it says the worker reports. The fix is ready. Verifying it now. And so it's basically
[00:06:37] surfacing the change to me. And now it says say the word and I'll land it on main. Now that it's
[00:06:41] completed. Go ahead and land it. Looks good to me. Okay. And now that the first task is done,
[00:06:45] I just wanted to kind of flex how Firstmate works with the orchestration part of things
[00:06:48] to show you like multiple things working at the same time. Because that was obviously cool,
[00:06:53] but it was only one ticket being done at the same time, which is not particularly interesting for
[00:06:57] an orchestrating agent. So here I've a prompt ready for you guys where we are working on three
[00:07:02] different things in parallel. And we basically want to see Firstmate spin up multiple terminal
[00:07:06] instances and things being worked on at the same time without collision, without conflict,
[00:07:10] all in separate Git worktrees. And here we can start to see the Firstmate's being populated.
[00:07:15] We got fm-firstmate. We got three of them here. And they are most likely working on three different
[00:07:19] tasks. store.js holds pure functions. And this one's going to be add a stats command to linkpile.
[00:07:26] And finally, scout only investigate how robust error handling is. And so there you have it.
[00:07:32] The three different tasks being worked on at the exact same time, all on different worktrees.
[00:07:37] Here, I'll make it a little bit bigger for you guys to see it. But you can see that there is
[00:07:40] .treehouse/fm-demo-app. And then we got the little different worktree path
[00:07:46] directories here. And yeah, that's kind of like how Firstmate works. There's also a very robust
[00:07:51] review gate as well. So once tickets are completed, before it actually ships, there is another CLI that
[00:07:56] runs. And again, I'll get to that in a small second here. The only reason I'm not showing it is because
[00:08:00] it's very loaded. A lot of it is very CLI based. So you're not really going to see the inner workings of
[00:08:05] that CLI. It's not really easy to kind of present it for you. But we'll talk about it in a second
[00:08:09] here. And here's the reason why my video kind of changed courses. When I look at what Firstmate
[00:08:15] actually needs to run, I found something way more interesting than just a simple orchestrator.
[00:08:20] The bootstrap script checks for 11 different tools. And most of them are actually created by
[00:08:24] Kun Chen himself. gh-axi is his wrapper around the GitHub CLI. chrome-devtools-axi is his wrapper
[00:08:31] around browser automation. There's lavish-axi, tasks-axi, quota-axi. no-mistakes is his validation
[00:08:39] pipeline, which by the way has seven and a half thousand stars on its own. And there's treehouse,
[00:08:43] which I mentioned earlier as being the Git worktree manager. Now Firstmate isn't a monolith. It's
[00:08:49] actually the top layer of one person's like entire personal stack. There are eight repositories under
[00:08:54] his account ending with the suffix "-axi". He even wrote down the design principles, a repository
[00:08:59] called axi, which stands for Agent Experience Interface. And this contains the idea behind the
[00:09:05] tooling that he's writing, the 10 principles for this. And the main idea here is that the end user
[00:09:10] is an AI agent. And so because the end user is different, the way that you would actually write
[00:09:15] your CLIs would be different. But going back to the Firstmate design here, the supervision layer is
[00:09:21] actually very interesting. Firstmate is an event-driven system with a zero token watcher. Usually when you
[00:09:27] have an asynchronous coding paradigm like this, you would use something called a heartbeat.md.
[00:09:32] Popularized by OpenClaw, the way that that works is that the agent wakes up every few seconds,
[00:09:36] reads the heartbeat.md for instructions, and then carries out any relevant work. Now under this system
[00:09:41] however with Firstmate, the process is very different. The entire process is deferred to a
[00:09:46] script that runs instead. So essentially, instead of having a thinking model that costs tokens every so
[00:09:51] often, Firstmate has optimized this by codifying the whole reasoning process into a really big bash
[00:09:56] script. He basically used an AI agent to automate the AI agent thinking work. That's funny and also
[00:10:02] insightful. And one thing that I found really interesting is that we saw earlier that cmux works
[00:10:07] with Firstmate, but there's also experimental support for Herdr. And that's also another video
[00:10:12] that I covered way back. You can check that up here. Anyway, the question for me at this point
[00:10:16] wasn't whether I should use Firstmate, but rather what are some key insights that we can take away
[00:10:22] from his principles and workflow designs? Now to be crystal clear, this video is not really meant to
[00:10:28] convince you to use Firstmate. Honestly, adopting somebody else's personal stack is kind of missing
[00:10:33] the point. For decades in software engineering, we've adapted our workflows to fit specific softwares
[00:10:39] because building your own was way too time consuming. But now that just isn't the case anymore.
[00:10:45] Altering existing softwares or creating one on the fly is just a single prompt away. And with this
[00:10:51] in mind, you can tune software to your exact specification and workflows and your needs.
[00:10:56] Kun Chen said in a blog post that the quality and the speed of his thoughts is basically the only
[00:11:01] bottleneck left. And that's basically the thing here. Models are getting smarter and smarter,
[00:11:05] but your attention span doesn't really scale like that. Every piece of the Firstmate stack is basically
[00:11:12] there to help you spend less of your attention for the same amount of shipped work. Fewer agent
[00:11:17] round trips means fewer interruptions reaching you. You get one conversation instead of five different
[00:11:22] terminals. And that's really the trick behind Firstmate's design. There are a ton of moving parts,
[00:11:27] but you only ever deal with one instance. And all of that complexity gets relocated into the code so that
[00:11:32] it's not living inside of your head. And what's really funny here is that without actually meeting
[00:11:37] Kun Chen or any other people that are working on things like this, I independently spent the past year
[00:11:42] building basically the same kind of abstractions. The names are different, but the idea is the same.
[00:11:46] I have my own orchestration loops, custom CLIs built for APIs, and so on. But with that aside,
[00:11:52] let me give you the four principles that you can take away from the Firstmate repository to really
[00:11:57] take your AI workflows to the next level. Principle one, wrap the CLIs you already use,
[00:12:03] shape to your use case. Let me show you what I mean. This is the same GitHub, the same five pull
[00:12:08] requests through two different tools. On the left, you have the official GitHub CLI with JSON output,
[00:12:14] which is obviously more verbose. It has many more unnecessary fields and syntax to show the data.
[00:12:19] On the other side, gh-axi with the exact same fields comes out to be roughly about 35% less bytes.
[00:12:25] And I measured this myself on the Kubernetes repo pull requests. But here's the thing,
[00:12:29] the byte count actually isn't the most important thing here. The neat thing about the wrapper is that
[00:12:34] it is specifically tuned to the info that the agent will need. The total count of pull requests is
[00:12:39] already pre-computed. The section at the bottom suggests the next command with the repo already
[00:12:44] filled in. In Kun Chen's own benchmarks, gh-axi turns six to eight agent turns down to just three,
[00:12:51] and every round trip you eliminate is one less possibility for the agent to fail.
[00:12:55] So really, you're just wrapping the CLI for fewer round trips and for smarter failures. The token
[00:13:01] saving is just a really nice added bonus. And here's also my version of the exact same move.
[00:13:06] I built Notion Ops because my agents kept getting lost in my Notion pages. They were basically doing
[00:13:11] workspace-wide searches, giant JSON dumps, and guessed the property names. And instead, Notion Ops gives
[00:13:17] them name surfaces. It allows them to query the engineering board directly for status and for in-progress,
[00:13:23] gives them the exact number of results and compacts the outputs all within the same CLI.
[00:13:27] So all in all, the move here is identical between these two paradigms. We didn't change to the
[00:13:32] underlying service. Instead, we created a contract that really works for us. So at the end of the day,
[00:13:38] these are two different softwares with two different workflows. But what we do have is a contract
[00:13:43] to define exactly what we need and have the AI agents go and build out the infrastructure for us.
[00:13:48] Principle 2. When the CLI you need doesn't exist, just build it. Back in April, I needed my agents
[00:13:56] to manage my DNS for me on Cloudflare. And there just wasn't an official CLI for it. So I ended up
[00:14:03] building overcf. And it helps me manage my domains just fine. Now, here's the important thing.
[00:14:08] The CLI is actually not a whole lot of code. But at the same time, it's very useful for my use case
[00:14:13] because it's written just for me. And because it's written for me, the code quality and some of the
[00:14:18] rough edges or the edge cases are not all considered. And that's fine because like I said,
[00:14:24] it's personal software. But this imperfection might start to become a problem once I have external
[00:14:29] users. If the software attracts open source users, then I would say the bar has been raised. But if
[00:14:35] you don't have any intentions on publishing your CLI for open source users, then I don't really see a
[00:14:40] need to make your CLI perfect for every single use case. And here's another thing that changes when
[00:14:45] the end user is the agent. The error messages become basically a part of the interface. Watch
[00:14:51] what Chrome DevTools actually does when an agent clicks from a stale page snapshot. Instead of just
[00:14:57] saying element not found, it hands back a typed stale ref error with the exact cause and the exact
[00:15:02] command to recover. And that's the difference. As a human, you just want tools that don't fail. But for
[00:15:07] an agent, you actually want tools that fail in a meaningful way that teaches it how to recover.
[00:15:12] Principle number three, and probably the most important one. Verify the AI output instead of
[00:15:17] babysitting every tool call. Here's an interesting stat. When I was discovering Firstmate, I actually
[00:15:22] realized that one of its dependencies called no-mistakes actually has twice the number of Git of
[00:15:26] stars than Firstmate itself. And no-mistakes is his validation pipeline for agentic work. The way that
[00:15:33] works is you push the branch that you're working on to this no-mistakes branch. And that triggers an AI
[00:15:37] automated pipeline to review and assess the work being done to make sure that it actually does fix
[00:15:43] the problem. Now, every change his crew makes has to pass through this no-mistakes gate before it can
[00:15:49] be shipped. And that's what allows this process to be fully automated. And on that point, there was an
[00:15:54] interesting GitHub issue that was raised on Firstmate repository. Now, somebody opened an issue saying that
[00:16:00] the crewmates agents actually run with the harness safety turned completely off. And for Claude Code
[00:16:05] users, that basically means dangerously skip permissions hardcoded to be turned off every
[00:16:09] single time. And Kun Chen's reply was actually funny. It's actually the whole point. His argument is that
[00:16:13] safety can't come from a human approving every single tool call. It has to be established at the
[00:16:18] environment level. And look at what that environment actually is. The agent is always locked into a
[00:16:24] disposable worktree. There's a hard rule that the orchestrator itself never writes to the project,
[00:16:29] and that we have this robust no-mistakes validation gate at the exit. So he didn't actually remove the
[00:16:35] safety net. He instead moved it to a different point in time of the development cycle. Instead of you
[00:16:40] approving every call on the way in, things only get approved and checked at the very end on the way out.
[00:16:45] Now, obviously, you can absolutely disagree with this sort of trade-off. An agent is definitely capable of
[00:16:51] causing damage mid-run. And sure, you should definitely think hard before you use a software like this.
[00:16:56] But the point I'm trying to make here is the principle underneath it. You basically want to
[00:17:01] create these environments to verify the AI's workflow in a more automated way. And that is
[00:17:06] what's going to truly unlock your capabilities and your productivity as an AI engineer. And with these
[00:17:11] kind of verifications in place in your environment, it's a lot easier to give AI the autonomy that it
[00:17:16] really needs to be able to thrive. And last but not least, principle four, create systems. The hard part of
[00:17:23] automations actually isn't building it. It's remembering it. I'm definitely speaking from
[00:17:28] experience here. I have created tons of automations that I've lost track of. And as you create more and
[00:17:32] more, it becomes a whole mess. It's like writing code without design patterns. So instead, you want to
[00:17:37] document your conventions, create that single source of truth. And because AI can program things so fast
[00:17:43] for you, make your automations reusable, generalizable. This goes back to principle one and two.
[00:17:48] Creating CLIs and wrappers around CLIs is one way to create systems. You just got to take it a step
[00:17:53] further and make sure that those CLIs are reusable across the board. If you have 10 different tools,
[00:17:58] with 10 different conventions, that's actually a hundred different things to remember. You want all
[00:18:03] your tools and apps to share a single convention layer. Firstmate is a prime example of this. Every
[00:18:08] project registered with Firstmate ships with the exact same pipeline, same validation, same worktree
[00:18:13] life cycles, same delivery modes, and the exact same CLIs across all of these. So as a result,
[00:18:19] you can learn and build the abstraction once and every repository afterwards benefits from it.
[00:18:25] Let me give you an example from my personal experience. I have something called agent config,
[00:18:29] which helps me create these skills and generalizable instructions for all of my agents across all my
[00:18:34] agent harnesses. That's Claude Code, Codex, pi, open code, even Hermes agent. And with a single command,
[00:18:40] I am able to synchronize all of my skills and my commands to all of my agents at the same time.
[00:18:45] And not only that, I have the ability to sync this across computers. If you've watched my previous
[00:18:50] videos on Hermes, agent, and Herdr, you'll know that I have a robust remote development system setup
[00:18:55] where I have two computers. And the CLI is fantastic because it also allows me to add little bits of
[00:19:01] notes to my agent and just sync it just like that. It's great. But going back to Firstmate,
[00:19:06] here's the funny part. Even the guy preaching about token efficiency is fighting this battle himself.
[00:19:10] Firstmate's AGENTS.md ballooned to nearly a thousand lines in July. He had to restructure it down to under
[00:19:16] 400 and now it's back up to 500, 600 roughly. So what I'm trying to say here is shared automation
[00:19:23] isn't something you just set up once and walk away from. Even the best example I can point to is out
[00:19:28] there getting pruned every single day. You just got to keep working at it and you'll get to a better
[00:19:31] system. So should you write your own agent stack? Let me start with the good news. This pattern
[00:19:37] genuinely works. You'll find a lot of productivity gains when you start creating your own workflows
[00:19:42] and your own tooling. You can take Kun Chen's Firstmate and its sub-dependencies as a case study or the
[00:19:49] fact that even I had a lot of great success creating my own workflows. Not only that, AI has made the barrier to
[00:19:54] entry for these kind of automations just basically a prompt or two away. But that said, there are some
[00:19:59] negatives to this, some things that you should be wary of. AI has made coding cheaper but it doesn't
[00:20:04] make it free. Every tool that you write has maintenance costs associated with it and that
[00:20:10] could come in many different forms. Maybe the upstream API server has changed their shapes, maybe they
[00:20:16] published some breaking changes, or maybe even the dependencies in your npm packages have a critical
[00:20:22] security vulnerability. Whatever it is, there are small minor maintenance costs associated with every
[00:20:27] single CLI or application that you build. Now that's not to say that you can't automate parts
[00:20:32] of this. And that's another really interesting part. And for that reason, it's what draws me to AI in the
[00:20:37] first place is because you can actually start using AI to automate parts of AI work. And it's very meta.
[00:20:42] But to kind of give you an example, you can set up an AI agent that monitors for security vulnerabilities
[00:20:48] on your npm package and patches it automatically fully remote. You could even use no mistakes as part of
[00:20:53] your verification process and it just releases a security fix on its own that could be feasible.
[00:20:57] Or in the case of your upstream API services changing, what I would personally do is define
[00:21:03] a contract for your CLI that has the shape of the downstream API you want for yourself. And all your
[00:21:09] agent does is make sure that that contract is honored at all times so that no matter what happens in the
[00:21:14] upstream, your agent is able to kind of glue it together for you. That's what the contract really is
[00:21:19] all about. Now the second warning here is basically busy work. If you are somebody who only works on a
[00:21:25] single project with a single agent at all times, like I'm shocked that you've made it this far into
[00:21:29] this video, but thank you for watching. But you probably don't need a very robust system like this.
[00:21:33] This is primarily for people who are interested in using AI for parallelizing your work across many
[00:21:39] different agents, being able to work on multiple things at the same time while maintaining some level
[00:21:43] of control that really isn't manually checking every single thing all at the same time, which just is not
[00:21:49] feasible. The third warning here is that adopting someone else's personal stack means inheriting
[00:21:54] their personal choices. Firstmate, as an example, has no releases. You're basically taking in whatever
[00:22:01] main branch has at any point in the day, and that's what you get. And that's the reason why I wanted to
[00:22:05] create this video in the first place is that the whole point is not to take somebody else's software
[00:22:10] and just plug it into your ecosystem. It's to take their knowledge, take their system, take their CLI,
[00:22:16] and just like learn as much as from it. Take the parts you like, leave out the rest, and make it
[00:22:20] your own. And this is the real beauty of AI for developers in 2026 and going forward because AI has
[00:22:27] made this process of making things yours so much easier. You could clone every single subdependency
[00:22:32] that Firstmate uses, wrap them to your specific use case, and rebuild your Firstmate to your own thing.
[00:22:38] Anything is possible. And that's what makes this so much more fun. And the final point here is nobody
[00:22:43] here is going to be around to judge whatever you create. Don't worry about being a perfectionist.
[00:22:47] This code is so cheap. These workflows may not last a year, may not even last six months, may not last
[00:22:53] the next week, who knows? But the whole point is to try to experiment to see what works for you.
[00:22:58] And all of these are learnings that you will accumulate and that will make you a better developer
[00:23:01] in the future. So yeah, there you have it. Firstmate and the stack underneath it and the four principles
[00:23:07] I think you should take away from this video. Now, if you have things that you're working on,
[00:23:10] automations, workflows, or things that you really found helpful for your own workflows that you think
[00:23:15] is good to share with the rest of the community here, please let us know down in the comments below.
[00:23:19] We would love to hear what you have come up with, some ideas, whatever it is. And I really like to
[00:23:23] bring out these lesser known softwares to light as soon as possible. So if that's the kind of thing
[00:23:28] that you like to watch, do hit that subscribe and like button. It really helps out with the channel
[00:23:32] and the algorithm. I hope you found this video insightful and I hope you have a great rest of your day
[00:23:36] and I'll see you guys in the next one. Take care of you guys. Bye bye.
