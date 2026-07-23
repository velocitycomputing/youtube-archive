---
video_id: B1sYKOWVHR0
title: You Only Have 1 Day Left With Fable 5. Maximize It.
channel: Ray Amjad
url: "https://www.youtube.com/watch?v=B1sYKOWVHR0"
watched_date: 2026-07-07
watched_at: "2026-07-07T12:00:00Z"
watch_count: 1
duration_seconds: 948
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 25
watched_at_precision: date-from-history-label
watched_percent: 57
estimated_watched_seconds: 540
summary_model: claude-haiku-4-5
tagging_model: failed
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Fable 5's unique strength is its ability to think through multiple levels of consequences (4th–6th order effects) unlike Opus 4.8, making it ideal for architectural decisions rather than grinding through backlogs. High-value uses include: identifying load-bearing code areas using a Git churn × complexity scoring framework, then asking Fable to suggest architectural fixes that will amplify cheaper models' effectiveness later; rebuilding frequently-used skills from scratch (Fable generates better new code than edits); creating "golden reference" implementations for patterns you reuse across projects; and running Daniel's system-analysis prompts to surface systemic improvements in your harnesses that Opus 4.8 would miss.

Before Fable 5 reverts to API pricing, (1) audit your top 10 highest-churn, highest-complexity files using Fable's scoring, then ask Fable to recommend architectural changes for each; (2) rebuild your three most-used Claude Code skills by having Fable recreate them from your original session prompts (set settings.json cleanup period high to preserve history); (3) generate canonical examples of messy patterns you repeat (e.g., MCP server interfaces) that you'll later point cheaper models at; (4) run Fable against Daniel Feldman's "prompts for prompts" list to identify your single biggest bottleneck and one-way-door risks; and (5) once in API pricing mode, use Fable as a delegating orchestrator that assigns tasks to Haiku/Opus based on learned rules, saving it only for architectural review and harness engineering.

## Transcript

[00:00:00] Okay, so we all know that in a few days
[00:00:02] Fable 5 will be going back to API
[00:00:04] pricing and right now there's a lot of
[00:00:06] noise on YouTube people saying stuff
[00:00:08] like, "Oh, you should be building a
[00:00:09] Whisper Flow clone or you should be
[00:00:11] building an Agent Quest with Fable 5."
[00:00:13] Even though you can do those tasks
[00:00:15] pretty easily with Opus 4.8. So in this
[00:00:17] video I basically want to focus on what
[00:00:19] you should actually using Fable 5 for in
[00:00:22] the remaining few days. It will be split
[00:00:24] up into two sections. The first section
[00:00:26] will be for those who want to use Fable
[00:00:27] 5 only on the subscription plan and the
[00:00:30] second one will be for those who want to
[00:00:31] continue using it with API pricing, but
[00:00:34] they want to be using effectively. Now
[00:00:36] what I'm seeing a lot of people doing
[00:00:37] right now on X is that taking that
[00:00:39] backlog of tasks and then feeding it all
[00:00:41] into Fable 5 hoping for the best and
[00:00:43] then they get another subscription and
[00:00:45] then keep repeating that. And once they
[00:00:46] go back to Opus 4.8 they'll just be
[00:00:48] stuck in that old habits again. So they
[00:00:50] basically haven't gained any lasting
[00:00:52] value from this short period. And by the
[00:00:54] way, if you are looking for a
[00:00:56] open-source Whisper Flow, then I
[00:00:58] recently open-sourced my own version Hyp
[00:01:00] Whisper, which I've kind of been working
[00:01:02] on off and on for the last 10 months. It
[00:01:04] is available on Mac OS and Windows and
[00:01:06] it will be coming to iOS very soon as
[00:01:08] well. So if you are interested, then it
[00:01:09] will be a link down below and you can
[00:01:11] also leave a star on the GitHub. I
[00:01:13] really appreciate it. Anyways, to begin
[00:01:15] with I want to talk about what I think
[00:01:16] makes Fable 5 special and that is the
[00:01:18] fact that's able to think many more
[00:01:20] steps ahead than previous models. So
[00:01:23] previously we had Opus 4.8 over here and
[00:01:26] you can kind of imagine that in many
[00:01:27] situations it can think about five, six
[00:01:29] steps ahead. So it can consider the
[00:01:31] effects of making a change throughout
[00:01:33] the code base, throughout the code stack
[00:01:35] and then eventually it misses some
[00:01:37] things, which is why you have to go
[00:01:38] through a verification stage or do some
[00:01:40] kind of code review at the very end. But
[00:01:41] I found that with Fable 5 recently it's
[00:01:43] able to think even more steps ahead and
[00:01:45] think about four, fifth and sixth order
[00:01:47] effects. And this often means that it's
[00:01:49] able to make better and smaller
[00:01:51] architectural decisions. Of course, not
[00:01:53] as good as a real system designer quite
[00:01:55] yet, but it means that it has better
[00:01:57] judgment and it's able to see around
[00:01:59] more corners than the previous Opus
[00:02:01] model was able to. And because of this,
[00:02:03] whatever work that I'm giving to Fable 5
[00:02:05] should ideally take advantage of this
[00:02:07] fact. So, for example, with my
[00:02:09] application agent stack, if you do want
[00:02:11] to deploy customer support agents for
[00:02:13] your business, then there will be a link
[00:02:14] down below, or you can contact me about
[00:02:16] it. Essentially, I have a whole bunch of
[00:02:18] issues over here. I will actually blur
[00:02:20] them out because they should not be
[00:02:21] seen. Instead of me saying something
[00:02:23] like, "Hey, can you look through the
[00:02:25] backlog of issues and then make a brand
[00:02:27] new PR fixing each of them and then
[00:02:29] merging any that have a small blast
[00:02:30] radius?" It would be much better to give
[00:02:32] a prompt that takes advantage of this
[00:02:34] fact over here, where it can think many
[00:02:36] more steps ahead. And that would be by
[00:02:38] saying something along the lines of,
[00:02:39] "Hey, can you look through the backlog
[00:02:41] of issues and then consider any
[00:02:43] architectural changes or fixes that
[00:02:45] should be made to application to make it
[00:02:47] easier for a less powerful model to
[00:02:49] close and fix those issues." And I will
[00:02:51] find that I will have made some
[00:02:52] architectural changes to my application,
[00:02:55] which means that when I fall back to
[00:02:56] Opus 4.8, then I can get even better
[00:02:58] output from Opus 4.8 than I previously
[00:03:00] could have because the application now
[00:03:02] has better architecture. I've also been
[00:03:04] doing this for High Post Pass as well
[00:03:05] because I'm making the iOS application
[00:03:07] and the Android one, and it would be
[00:03:09] better for me to share as much logic as
[00:03:11] possible between all four versions of
[00:03:13] the application. So, I've been using
[00:03:15] Fable 5 to make a shared core inside of
[00:03:17] Rust that I can then apply to all four
[00:03:19] versions of the application. And one way
[00:03:21] that I kind of think about this is that
[00:03:23] many codebases, especially ones in which
[00:03:25] you have been using coding agents for a
[00:03:26] long time, are kind of like geological
[00:03:29] layers. So, you probably have like Opus
[00:03:30] 4.1 code somewhere, Opus 4.5 code
[00:03:33] somewhere, like decisions that Opus 4.6
[00:03:35] made somewhere, and then you have like
[00:03:37] some Sonic ones, you experimenting
[00:03:39] around with GLM 5.2 for a while, so you
[00:03:41] have some there, too. And then finally,
[00:03:43] you have Fable 5 at the very top. And
[00:03:45] because many of these coding agents,
[00:03:46] when they're exploring your codebase,
[00:03:47] they copy existing patterns, they will
[00:03:50] often copy bad architectural patterns
[00:03:52] like Opus 4.1 patterns, Opus 4.5
[00:03:54] patterns. And what some people do for
[00:03:56] really small applications is that they
[00:03:58] get rid of all of it, and then they
[00:04:00] rebuild it from scratch. And that's fine
[00:04:02] for small applications. You can rebuild
[00:04:04] it with Fable 5 with much better
[00:04:06] architecture. But if you have a really
[00:04:07] big code base, then it's a much bigger
[00:04:09] problem. So usually in those situations,
[00:04:11] I like to identify the load-bearing
[00:04:12] parts of the code base, the ones that
[00:04:14] require the most amount of attention
[00:04:16] from Fable 5. And because they all
[00:04:18] load-bearing, takes advantage of the
[00:04:20] fact that Fable 5 can think many more
[00:04:23] steps ahead than other models. So I'm
[00:04:25] going to go through a quick example so
[00:04:27] you can see what this looks like in one
[00:04:29] of my code bases. So the framework that
[00:04:31] I like to use here is impact times by
[00:04:33] opportunity. Of like, if we actually
[00:04:36] made that change, if we made that fix,
[00:04:38] then how much impact would it have
[00:04:39] inside of our code base? If it has a
[00:04:41] high amount of impact, then that's
[00:04:43] really great because we got a lot of
[00:04:44] value from Fable 5. And then opportunity
[00:04:46] is how fixable this is. So ideally, we
[00:04:49] want to be focusing on this hotspot
[00:04:50] region over here. Now this is an idea
[00:04:52] that I teach inside of my agent to
[00:04:54] coding school, which actually has a 4th
[00:04:56] of July sale going on right now for this
[00:04:58] weekend. So if you do want to get 30%
[00:05:00] off, then it will be linked down below.
[00:05:02] And it is the most comprehensive set of
[00:05:03] classes that you will find online about
[00:05:06] agent to coding. And it does come with a
[00:05:08] 30-day money-back guarantee. And despite
[00:05:10] that, less than 0.2% of people have
[00:05:13] asked me for refund. So because so few
[00:05:15] people ask me for refund, that's how I
[00:05:17] know it's good. So anyways, we want to
[00:05:18] kind of like define these parameters
[00:05:20] over here. What is the impact or what is
[00:05:22] opportunity? And one metric that I like
[00:05:23] here is Git churn times by complexity.
[00:05:26] So I can get something like Fable to
[00:05:28] look for my code base or even Opus 4.8
[00:05:31] and score the files and find these
[00:05:33] opportunities for me. So let's actually
[00:05:35] go ahead and do this right now. Hey, so
[00:05:36] explore my code base, can you rank files
[00:05:39] one to five on both Git churn and
[00:05:42] complexity, and then multiply them
[00:05:44] together to give yourself a score so we
[00:05:47] can identify the parts that have the
[00:05:49] highest tech debt inside of our code
[00:05:51] base that need like architectural
[00:05:53] changes. Give me a list of the top 10
[00:05:55] files with the score for each parameter,
[00:05:58] as well as their overall score. And it
[00:05:59] seems I actually ran out of Fable on
[00:06:01] this account, so I'm going to have to
[00:06:02] switch over to my other account. Okay,
[00:06:04] let's send that prompt off, and
[00:06:05] sometimes people ask me like how many
[00:06:07] Claude 20X Max subscriptions do you
[00:06:09] have? And right now I have about four,
[00:06:12] and that's mostly because of Fable 5. Uh
[00:06:14] but I think it will probably go down to
[00:06:15] about three soon. So I can see that it
[00:06:17] gave me a ranking over here, and the two
[00:06:20] highest files are this chat endpoint,
[00:06:22] and also the Stripe Webhook. So I'm
[00:06:24] going to say, "Okay, looking at the top
[00:06:26] two files, what kind of architectural
[00:06:28] fixes would you recommend making here to
[00:06:31] reduce the complexity going forward,
[00:06:33] especially in light of the issues that
[00:06:34] we have inside of the GitHub backlog?"
[00:06:36] So now Fable will be using its judgment
[00:06:38] to kind of like figure out here what
[00:06:39] changes we should make here. Anyways, I
[00:06:41] won't be going through the recommended
[00:06:42] fixes because I don't want to reveal too
[00:06:44] much of that code base. But the next
[00:06:45] thing that I have been doing recently is
[00:06:47] basically rebuilding any skills I use on
[00:06:50] a regular basis. So if you go to {slash}
[00:06:52] usage inside of Claude Code, then you
[00:06:54] can see which skills that you have been
[00:06:56] using the most. So for some reason it
[00:06:58] only shows the top three right now. So I
[00:07:00] can switch down to like Sonic for
[00:07:01] example, and then say, "Hey, which of
[00:07:03] the skills I use the most can you look
[00:07:05] through my previous transcripts, give me
[00:07:06] the top 20?" And then basically for any
[00:07:09] of these skills I use the most, instead
[00:07:11] of repairing the skill, I basically
[00:07:13] rebuild it brand new with Fable instead.
[00:07:16] Because you will find that for many
[00:07:17] models, they are much better generating
[00:07:19] new code, generating new stuff, than
[00:07:22] editing existing stuff. So what I have
[00:07:24] been doing is getting Fable to rebuild
[00:07:26] many of the skills using the initial
[00:07:28] prompts that I made to make that skill
[00:07:30] to begin with. And you may want to tell
[00:07:32] Claude Code to look for your prompt
[00:07:33] history to find the initial prompt and
[00:07:35] the seed data that you used to make the
[00:07:37] skill. And in case you don't already
[00:07:39] have the set, you want to set your
[00:07:40] cleanup period inside of your
[00:07:42] settings.json uh to a really big number
[00:07:45] because right now inside of Claude code
[00:07:47] it's set to 30 days by default. So, any
[00:07:50] transcripts that is older than 30 days
[00:07:52] will be deleted from your disk
[00:07:53] automatically. So, you should add this
[00:07:55] to top of your settings.json. So,
[00:07:56] anyways, I get the model to go back,
[00:07:58] find the initial session that made that
[00:08:01] skill, and then remake it with Fable 5
[00:08:04] using the same initial prompt and data.
[00:08:06] And I also got to prevent it from
[00:08:07] accidentally cheating and looking at the
[00:08:09] current skill. So, I like to do this in
[00:08:11] a brand new folder instead in which it
[00:08:13] doesn't have access to that skill. And
[00:08:14] then I do a quick comparison between the
[00:08:16] old skill and the new skill, read
[00:08:18] through it, and then I have a much
[00:08:19] better skill that I can continue to use
[00:08:22] even once Fable is gone. If you want to
[00:08:23] make sure your skill is kind of adapted
[00:08:25] for Opus 4.8 because you will be using
[00:08:27] it with Opus 4.8, you can tell Fable 5
[00:08:30] to do a few trial runs inside of a sub
[00:08:32] agent, which is Opus 4.8 sub agent,
[00:08:35] using that skill and then judge the
[00:08:37] outputs and then readjust accordingly.
[00:08:39] So, you would have the skill that Fable
[00:08:41] 5 made, and then that would be mostly
[00:08:43] for Fable 5 because I made a skill, and
[00:08:45] then you can tell Fable 5 to fine-tune
[00:08:47] that skill for Opus 4.8. So, you can see
[00:08:50] that these are my most used skills. I
[00:08:52] have this one over here, which doesn't
[00:08:54] really need Fable 5 attention. I have
[00:08:56] this one over here, which probably does
[00:08:58] need Fable 5 attention. This one, too.
[00:09:00] This one as well. This one, too. And
[00:09:02] then a bunch of others as well. And
[00:09:04] honestly, this is pretty good
[00:09:05] maintenance because some of these skills
[00:09:07] have not been updated since like Opus
[00:09:09] 4.6 for me. Now, as I said, the models
[00:09:11] are much better at generating new code
[00:09:13] than editing existing code, which means
[00:09:15] that you can use Fable 5 to generate you
[00:09:18] some golden references, golden examples
[00:09:21] of anything that you do on a regular
[00:09:22] basis. So, for example, for many of my
[00:09:24] applications, I use Better Off, and when
[00:09:27] I'm making a hosted MCP server for the
[00:09:29] application, it kind of like interfaces
[00:09:31] in a really janky way, and there isn't
[00:09:33] really a good canonical example online
[00:09:35] about this. And because I keep reusing
[00:09:37] this code amongst many applications,
[00:09:39] I've turned that into a golden reference
[00:09:42] which I can then point any cheaper model
[00:09:44] at in the future. For example, like Opus
[00:09:46] 4.8 at the Fable 5 golden reference, and
[00:09:49] then I can just copy it and then change
[00:09:50] a few things around to implement it into
[00:09:52] the application. So, for example, if
[00:09:54] you're dealing with web sockets or some
[00:09:56] pretty complicated concurrency things,
[00:09:58] you may want to ask Fable 5 to generate
[00:10:00] you a canonical example of how that
[00:10:02] would be done inside of a brand new
[00:10:04] folder inside of a brand new project,
[00:10:06] and then have a Opus 4.8 agent that
[00:10:09] would then reapply that example to all
[00:10:11] the other places where it matters. So,
[00:10:13] this can be really handy for situations
[00:10:14] where you have many different services
[00:10:16] in one application or many different
[00:10:18] applications all sharing similar logic.
[00:10:20] Something else I've been doing is
[00:10:22] running Daniel's prompts for prompts to
[00:10:25] run when Fable 5 comes back. Now, I
[00:10:26] would highly recommend following him
[00:10:28] because he's one of the highest signal
[00:10:29] voices in the AI space. I personally
[00:10:32] follow like four or five people in the
[00:10:34] AI space, and he's one of the ones that
[00:10:36] I always listen to and watch. And this
[00:10:38] will be linked down below, but these are
[00:10:39] the 10 prompts to run when Fable comes
[00:10:41] back. And the one that I really like
[00:10:43] over here is a better lesson
[00:10:45] optimization. So, deeply study Richard
[00:10:47] Sutton's better lesson essay and how it
[00:10:49] applies to over-engineering specifically
[00:10:51] for AI and coding harnesses, and do a
[00:10:53] full analysis of our harness in its
[00:10:55] entirety looking for every place we're
[00:10:58] violating better lesson engineering, and
[00:11:00] give me a comprehensive plan for
[00:11:01] upgrading the system to to make it more
[00:11:03] flexible for future improvements in the
[00:11:04] models we use. So, I can copy this over
[00:11:07] and then go to my Ray OS folder over
[00:11:09] here, and then paste it in for Fable 5.
[00:11:12] You may want to first run it with Opus
[00:11:14] 4.8 because you may find the Opus 4.8
[00:11:17] answer to be satisfactory on its own,
[00:11:19] but you may want to double-check it with
[00:11:20] the Fable 5 answer as well just to be
[00:11:22] sure like it actually is better. So, I
[00:11:24] will run it with both, and then we'll
[00:11:25] come back to this later. I also like
[00:11:27] some of the other prompts as well here.
[00:11:29] So, for example, there's one called the
[00:11:31] one real constraint out of everything
[00:11:33] limiting my life and work, find the
[00:11:34] single biggest binding constraint, the
[00:11:36] actual bottleneck not the loudest
[00:11:38] problem, show me where I'm pouring
[00:11:40] effort into things that aren't the
[00:11:41] constraint, and tell me the one move
[00:11:42] that relieves it, and what becomes
[00:11:44] possible once it's gone. So yeah, this
[00:11:46] article will be linked down below if
[00:11:48] you're interested in using them. Okay,
[00:11:49] so running the prompts with Fable 5, it
[00:11:51] gave me a really interesting insight
[00:11:52] over here of add a revisit if expiration
[00:11:56] tag to every workaround inside of Claude
[00:11:58] MD and skills that nothing silently. And
[00:12:02] honestly, I think this is a really good
[00:12:03] idea that will be baked into all my
[00:12:06] skills going forwards, especially for
[00:12:08] ones that deal with weird workarounds in
[00:12:10] some way. Meanwhile, it seems that the
[00:12:11] Opus 4.8 response for the same prompt
[00:12:14] was not as good because it did not give
[00:12:16] me the same thing over here about a
[00:12:19] expiration tag to any workarounds that I
[00:12:21] have. Okay, now this section of the
[00:12:22] video will be for those who want to use
[00:12:24] Fable 5 in moderation once it goes back
[00:12:27] to API pricing. So because I think it's
[00:12:29] a really good model for many tasks, I
[00:12:31] will still be paying for API pricing,
[00:12:33] but I will not be using it all the time.
[00:12:35] So firstly, you can have Fable 5 as your
[00:12:37] main orchestrator and have it delegate
[00:12:39] everything to smaller models. And this
[00:12:41] comes from Simon Willison's blog who
[00:12:43] shared yesterday that one of the
[00:12:45] interesting tips that he got from his
[00:12:47] fireside chat with Kat Woo who is the
[00:12:49] head of products for Claude code and
[00:12:51] Tariq who is an engineer was to let
[00:12:53] Fable 5 and to some extent Opus use
[00:12:56] their own judgment rather than dictating
[00:12:57] how they should work. And then he said
[00:12:59] this to Fable, which is for all coding
[00:13:02] tasks, use your own judgment to decide
[00:13:04] an appropriate low-power model and run
[00:13:06] that in a sub-agent. And you can take
[00:13:08] this a bit further at the very beginning
[00:13:10] and say something like, "Hey, can you
[00:13:12] look at that particular sub-agent's
[00:13:13] output and determine whether it was good
[00:13:15] enough?" And if it wasn't, next time use
[00:13:17] a more powerful sub-agent. And then
[00:13:19] eventually, you can have a thing inside
[00:13:22] of your Claude MD file that tells it
[00:13:24] when to use which sub-agent and for what
[00:13:26] task and for which part of the code
[00:13:28] base. And then eventually, once you have
[00:13:30] this table formed, you can get it to
[00:13:32] remove the loop over here where it's
[00:13:34] evaluating every subagent's output. And
[00:13:36] then it can just run with that set of
[00:13:37] subagents, and then you can keep it that
[00:13:39] way until a newer generation of models
[00:13:41] come out. Now, with Fable 5, I will also
[00:13:43] be getting it to review every one-way
[00:13:45] door going forward. So, there are many
[00:13:47] doors that are two-way doors, so these
[00:13:48] are reversible changes. And this is
[00:13:50] stuff like UI copy, styling, some
[00:13:53] feature flags, which are easily
[00:13:55] reversible. And then you have one-way
[00:13:56] doors, which are irreversible changes.
[00:13:58] So, if you're maintaining some kind of
[00:13:59] public API, as soon as you make the
[00:14:01] announcement, people will start using
[00:14:03] it, and then it's much harder to go back
[00:14:05] and change it. Now, finally, there are
[00:14:06] many cases where you may not even need
[00:14:08] to be using Fable. In the sense, often
[00:14:11] you're finding that a better harness can
[00:14:13] beat a bigger model on some set of
[00:14:15] tasks, especially when it comes to bug
[00:14:17] hunting and security changes. So, this
[00:14:19] is where you can use dynamic workflows
[00:14:21] because a dynamic workflow is basically
[00:14:23] a harness that has been written for that
[00:14:25] particular task. And there are many ones
[00:14:27] that you can use, so you can have a
[00:14:28] builder reviewer go back and forth like
[00:14:30] five times, have some kind of verifier,
[00:14:33] do like ranking of different files to
[00:14:35] find security issues and stuff like
[00:14:36] that. Honestly, I think that this
[00:14:38] deserves a separate video in the future
[00:14:40] because we're seeing many stories of
[00:14:41] Chimera 2.7 and GLM 5.2 achieving very
[00:14:45] similar, sometimes better performance
[00:14:47] than these models when you wrap them in
[00:14:49] the right harness. Now, I am thinking of
[00:14:51] making much more videos like this on
[00:14:52] YouTube, but I'm currently making them
[00:14:54] for my class right now. So, once my
[00:14:56] class all about Loop AI is completed,
[00:14:58] then I will be releasing a harness
[00:15:00] engineering class. And if you do want to
[00:15:02] get access to current classes, as well
[00:15:04] as the upcoming harness engineering
[00:15:05] class, then if you sign up during the
[00:15:07] July 4th sale, then you'll get access to
[00:15:09] those. But yeah, all I can say is good
[00:15:11] luck, and do make the most of Fable 5
[00:15:13] whilst you still have it for cheaper in
[00:15:15] your subscription. And if you uncover
[00:15:16] anything interesting, then do let me
[00:15:18] know either in the comments or by email.
[00:15:20] I really like getting emails about this
[00:15:22] because I love thinking about this kind
[00:15:23] of stuff, and I pretty much spend like
[00:15:25] 12 hours every single day using these
[00:15:27] agents. Of course, I will be continuing
[00:15:30] to use Fable 5 even on API pricing, so
[00:15:33] that when they do add it back to the
[00:15:34] subscription once they have like more
[00:15:36] capacity unlocked, then I will have a
[00:15:38] whole set of best practices for using
[00:15:40] Fable 5 for all sorts of situations.
[00:15:43] Because currently, everyone, including
[00:15:45] the Inflection employees, are still
[00:15:47] figuring all of this stuff out.
