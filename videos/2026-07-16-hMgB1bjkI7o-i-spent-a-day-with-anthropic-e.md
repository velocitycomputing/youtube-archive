---
video_id: hMgB1bjkI7o
title: "I Spent a Day With Anthropic Engineers. Here's Their REAL Workflow."
channel: Ray Amjad
url: "https://www.youtube.com/watch?v=hMgB1bjkI7o"
watched_date: 2026-07-16
watched_at: "2026-07-16T12:00:00Z"
watch_count: 1
duration_seconds: 1232
source: youtube-history-browser
added_date: 
history_label: Jul 16
history_order: 84
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1232
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The creator spent a day with Anthropic engineers and discovered they don't follow one "perfect" workflow—instead, everyone experiments differently with their own approaches. The key workflow they mostly follow is: describe the desired change (with some interviewing), specify essential constraints without over-engineering the spec, create a plan, execute it, then verify end-to-end with automatic testing and code review. Senior engineers differ from junior ones not by prompting differently, but by having lived experience to recognize when models are wrong despite their output seeming correct. The creator also learned that overly strict specs can actually limit model judgment; Fable 5 often reaches 95% implementation with just a simple description. He adopted a philosophy of loopifying work—setting up automated systems that continuously find issues, generate PRs, run verification tests (like browser-based screenshots), and propose fixes around the clock.

**Actionable for you:** Test whether your current workflow (detailed specs/plans/issues) or a looser approach works better by applying the same task two ways with Fable 5. Set up automatic verification for where users actually encounter your changes—use browser testing for UI, API calls for endpoints, terminal agents for CLI tools. Increase your Claude Code cleanup period setting beyond the default 30 days to retain transcripts longer. Replace trying to catch everything upfront with 2–3 rounds of `/code-review` (at medium or max reasoning effort) instead. Build a personal library of high-quality insights to seed idea generation in Claude, asking it to branch into 30+ variations—some will be gems. Finally, invest time automating verification environments and issue generation so you can run continuous loops of improvement without manual review for small changes.

## Transcript

[00:00:00] Okay, so about 3 weeks ago I went to a Code  with Claude event in Tokyo the day after Fable
[00:00:05] 5 was released, and there were a whole bunch of  Anthropic employees at the event. I think like
[00:00:09] over 20 or something, and I got a chance to speak  to many of their engineers about Claude Code,
[00:00:14] their workflows, skills, loops, and a bunch  more stuff. And I'll be sharing many of my
[00:00:18] learnings inside of this video. But before getting  started, I want to quickly show you this cute
[00:00:22] Claude plushie that I got at the event. It's like  a Claude scientist chemist kind of like plushie,
[00:00:26] uh, so I'm pretty happy about that. But anyways,  uh, my expectation when going to the event,
[00:00:30] I had this like idea in my mind of like, oh  man, I'm gonna find like the perfect workflow
[00:00:34] or strategy and then like be a 10x power user or  something. And I felt like they were like hiding
[00:00:39] the strategy internally behind the scenes or  something like that. And everyone was using the
[00:00:43] perfect workflow. And I guess in hindsight, that  was a naive assumption because one of the first
[00:00:48] things that Anthropic employees said to me at the  event was that everyone at Anthropic is living in
[00:00:52] the future, but in like 4 different futures. And  one of them may be directionally correct. And no
[00:00:57] one is really acting like they have it all figured  out. Everyone is trying something a bit different.
[00:01:01] So you have people at Anthropic who are using  like crazy multi-agent stacks or whatever. Some
[00:01:06] people are just doing their work in Claude CoWork.  Some are doing like pretty vanilla terminal stuff.
[00:01:10] Basically everyone is kind of running their own  experiment and no one is acting like they have
[00:01:14] the perfect workflow or solution, which likely  means that whatever you are doing right now,
[00:01:19] there's probably an Anthropic employee doing  something very similar to it. Now of course
[00:01:22] there are some best practices that many people  follow, such as having their reviewer agent being
[00:01:27] different from their builder agent to not  be biased. But generally everyone is doing
[00:01:31] something a little bit different. So this was a  time when Boris was saying he was making loops
[00:01:36] and orchestrating all these loops. And I asked a  Nova and Anthropic employee at the events like,
[00:01:40] "Oh, have you set up loops yourself? What kind  of loops do you have?" And she was like, "No, not
[00:01:44] really. Like, I don't know what Boris is talking  about, but I want to ask him as well." And even
[00:01:48] though everyone there is working in the future,  especially because they're experimenting and
[00:01:52] getting models as soon as they finish training,  every session that people do is still flowing back
[00:01:56] into a central system whereby analysis can be done  over those sessions where they can watch together
[00:02:02] and kind of figure out what works. So this is  what I was told of. And also sometimes in Slack,
[00:02:06] someone may have an idea and then quickly send  a message being like, hey guys, can you run this
[00:02:10] prompt for us? People would run the prompt and  then give the result back. So there's a lot of
[00:02:14] experimentation happening internally. And I think  having a central vault for everyone's transcripts
[00:02:19] generally seems to be a good idea. We've seen many  other companies doing this as well internally.
[00:02:24] They're collecting everyone's transcripts with  Claude Code. And for your personal Claude Code,
[00:02:28] I'd recommend editing your settings.json by  going to VS Code or whatever. And then adding a
[00:02:33] line kind of like this at the very top for cleanup  period days and set it to like a really big number
[00:02:38] because by default it's 30 days, which means  your local session transcripts will be deleted
[00:02:43] automatically from your disk after 30 days. And  ideally you don't want that because you want to
[00:02:48] spot patterns over a longer time horizon time  period. So this video is sponsored by myself
[00:02:53] and my agentic coding classes. After popular  demand, there is a 4th of July sale on right
[00:02:59] now, which means that you will save 30% on the  lifetime plan. And also for the first time ever,
[00:03:04] you will save money on the team and enterprise  plans as well. It is the most comprehensive class
[00:03:08] that you will find online about agentic coding,  covering Claude Code, Codex, loop engineering,
[00:03:14] prompt engineering, context engineering, and a  lot of techniques to get even better output out
[00:03:19] of these agents. And what's actually funny is  I mentioned two of the techniques that I teach
[00:03:22] in the class. To one of the Anthropic engineers  who works on the Claude desktop app, I think it
[00:03:27] was. And he was like, "Oh wow, that, like, I had  never actually considered that before." So I know
[00:03:31] it's good when Anthropic engineers themselves  are like impressed with some of the things that
[00:03:35] are being taught. Now you have probably heard of  spec-driven development frameworks like OpenSpec,
[00:03:40] SpecKit, or BMAD. And I think there's like a new  one almost every month now. And I never really
[00:03:45] made videos about them because they felt limiting  in some kind of weird way. And reassuringly, none
[00:03:49] of the Anthropic employees that I spoke to at the  event used any kind of framework like this. Often
[00:03:54] it was just a case of, They describe the feature  they want, specify a few constraints, have the
[00:03:59] model interview them with a bunch of questions,  and then maybe make a design mockup. They pick
[00:04:03] the one they like, and then it goes back into the  plan mode, and then the plan is implemented. And
[00:04:07] then there's like a code review at the very end to  catch anything that may have been missed. And just
[00:04:12] to be clear, I think it's kind of an axis like  this. So some people have every single safeguard,
[00:04:17] edge case, exception inside of their spec. And at  that point they basically just have code written
[00:04:22] in English instead. And for me, the ideal spec,  quote unquote, or a plan would basically be, hey,
[00:04:28] we just describe the goal that we want, what we  want our users to be able to do. We then define
[00:04:33] any constraints that we want to have in mind, such  as like rate limiting or something. And then the
[00:04:37] model will figure out the rest. And over the last  few days since Fable 5 has returned, I found this
[00:04:42] to be especially true with Fable 5. And that is  because as a Nova Anthropic engineer said to me,
[00:04:47] the map is not the territory. So if you have  a really overly strict spec kind of like this,
[00:04:52] there may be points when the code coding agent is  editing the codebase where it has to deviate from
[00:04:57] the spec. And if it's forced down whatever spec  that you chose at the beginning, it'll lead to
[00:05:02] worse results than trusting the agent's judgment  to adapt as it encounters any obstacles or
[00:05:07] difficulties. And I think this is kind of related  to a bit of a lesson whereby as we are noticing
[00:05:12] the models getting better, many of the constraints  and structures that we have specified around the
[00:05:17] models are now actually limiting the models from  reaching their full potential. And it would just
[00:05:21] be easier if we gave a pretty simple prompt, some  things that we absolutely don't want the model to
[00:05:26] do, and then have it figure out the rest. And over  the last few days, I noticed this especially with
[00:05:31] Fable 5. So for some of my projects, I deleted my  Claude MD files and also my memory files and also
[00:05:37] my skills. And I just had the raw experience  of using the model. And I just described, hey,
[00:05:42] can you add this? It asked me a bunch of questions  and then implemented it like 95% of the way there
[00:05:48] every time. So I think it's worth considering,  do you still need to be doing the same thing you
[00:05:52] were doing 3, 6 months ago? And I think the only  way to really appreciate this is to try it and
[00:05:57] experience it yourself. So I would recommend like  applying the same task using your current workflow
[00:06:03] and that could be like having a PRD, spec, issues,  whatever. And then doing the same thing again, but
[00:06:09] deleting all your skills or like moving them to a  different folder and then just describing simply
[00:06:14] what you want to Fable 5 and then seeing what it  does instead. But you may want to still go through
[00:06:18] the usual flow of having a plan mode, having  execute, and then finally doing some verification
[00:06:24] at the end. Now something else I realized that  is way more important is taking the time to set
[00:06:29] up good automatic verification environments. So  for example, for the Claude desktop application,
[00:06:34] whenever a change happens, then it's automatically  verified on a cloud container running the desktop
[00:06:40] application. So Claude is automatically verifying  that change with some kind of computer use. So
[00:06:46] that means whenever you have some kind of change  happen in your code, you want to consider where
[00:06:50] is a user actually meeting this change? Are they  meeting it via a browser? In which case you may
[00:06:55] want to use Cloud and Chrome or Playwright to  actually verify that change has been implemented
[00:07:00] and is working successfully. If you made a change  to some kind of API surface, in that case you want
[00:07:05] an agent to make a request to the API endpoint  and verify everything works as intended. Or if
[00:07:10] it's some kind of terminal surface, then you may  want to use an agent to drive a terminal. So I
[00:07:15] imagine that the Claude Code terminal version of  the application is actually verified with Claude
[00:07:21] running its own terminal in some kind of computer  use thing. So after thinking about that, I was
[00:07:26] like, okay, I gotta put in more effort to make my  own automatic verification environments. So what I
[00:07:31] did, at least my application AgentStack, is every  time there is a brand new PR that makes a change,
[00:07:37] then Claude automatically considers where is  a user meeting the change. And then for each
[00:07:42] of those, it automatically verifies using some  kind of browser use, whilst doing a recording
[00:07:48] to be like, hey, here is a user meeting the  change and here is a change actually working.
[00:07:53] So you can see over here, it changes the like  header color, it scrolls down, it's as expected,
[00:07:58] changes this as well. And then it shows properly  inside of the UI. So this is all verification
[00:08:03] that it's doing automatically on the cloud. And  then it sends me a GIF on the appropriate Slack
[00:08:08] channel. Now it totally depends on your stack, but  I would recommend investing the time to make these
[00:08:12] verification environments because they will pay  dividends over the long term. And if you're doing
[00:08:16] any kind of browser verification, then you may  want to simply install Playwright onto some kind
[00:08:21] of remote server and then have Claude connect to  that remote server automatically. Or use something
[00:08:25] like the browser-based MCP. I know a bunch of  companies use that. And I think there's also like
[00:08:30] BrowserUse as well, which is another company.  And you can just use that to verify your own
[00:08:35] sites. Ideally, I would recommend one that kind  of allows for some kind of recording functionality
[00:08:40] and you can have those recordings automatically  delivered to you on Slack, for example. So from
[00:08:45] what I gathered, the workflow that they mostly  seem to follow is describing what change needs
[00:08:49] to be made that may require some interviewing or  prototyping, then specifying any constraints that
[00:08:55] may need to be considered, having that in some  kind of plan mode, having that plan executed,
[00:09:00] then doing some kind of verification end to end  with where the user would actually meet that
[00:09:05] change. And then also doing some code reviews as  well to make sure everything has been accounted
[00:09:09] for. Now I also do talk about workflows like this  in way more detail inside of my brand new Loopy AI
[00:09:15] class. So you'll find a whole bunch of covering  this kind of stuff in way more detail. And a
[00:09:19] brand new feature that I added to class to make it  even easier to apply the ideas to your projects is
[00:09:24] basically this button over here where you can go  down, choose Claude Code or Codex, and then click
[00:09:30] on this button and it will automatically open  up Claude Code for you with a relevant prompt
[00:09:35] so you can start applying the ideas immediately.  And basically to my knowledge, no other class has
[00:09:40] this kind of feature available. So if you are  interested, it will be linked down below with
[00:09:43] the sale going on right now. Anyways, a conclusion  that I had from many of my discussions there was
[00:09:48] basically like going for the spec-first approach  will often break in interaction with the real
[00:09:54] codebase. And it's better to have more of a fuzzy  idea, have it navigate through the real codebase,
[00:10:01] build the PR, and then go through a code review  to catch any edge cases, any like surprises,
[00:10:08] mismatches, or any other problems. So I usually go  through a couple rounds of code review and that is
[00:10:15] by using the built-in code review inside of Claude  Code. So I found this prompt to be really good.
[00:10:20] So you can do /code-review and then choose your  reasoning effort. So I usually like going for max
[00:10:26] if it's a really big feature or medium or medium  if it's just a small change. And when you do this,
[00:10:31] it will automatically find any of the edge  cases that haven't been considered. So it's
[00:10:34] a case of like, do you want to try to like have  the edge cases happen at the very beginning with
[00:10:39] some kind of perfect plan? Or do you want it to  happen at the very end instead? Now this means
[00:10:44] that you may go through multiple rounds of code  review. So for example, with this PR over here,
[00:10:48] it went through many more rounds of back and forth  with the Codex code review that left comments on
[00:10:53] the PR. So you can see that Codex left some  comments over here and then it automatically
[00:10:57] replied with a follow-up commit. It left more  comments and it just went back and forth,
[00:11:02] I think like 13 times almost or 12 times. So maybe  I should have set some kind of cap or like a blast
[00:11:08] radius limit. But eventually Codex was happy and  it didn't leave any more code review comments
[00:11:13] on the PR. So for me personally, I usually like  having Codex doing code reviews on my PRs. I have
[00:11:18] tried using stuff like GrubTile and CodeRabbit,  but one time I got Claude Code to look through all
[00:11:23] the previous PRs and determine whether GrubTile  or CodeRabbit had actually said anything useful.
[00:11:29] And it just concluded, not really. The Codex code  review was more useful than the GrubTile and the
[00:11:34] CodeRabbit ones. So yeah, essentially once you  have the code review and then you have the fixes,
[00:11:38] you may want to go in this loop like 2 or 3 more  times and then you basically have a ready PR that
[00:11:43] would have covered even more things than any kind  of initial spec that you could have created. So
[00:11:47] I guess the conclusion for me is I usually don't  worry about my like initial prompt or my initial
[00:11:53] plan covering every single like thing because  I know the code review, if I have it on a high
[00:11:58] setting and go through a couple of rounds of it,  will catch almost everything that I have missed.
[00:12:03] And sometimes it just turns out the change was  wrong overall and then I discard the PR and I
[00:12:08] come up with a better one. With a better initial  prompt that has an architectural fix instead of
[00:12:14] some kind of like local fix. And I also do talk  about architectural and local fixes in more detail
[00:12:19] in my class. Now, because this part is essentially  a loop that is happening up to 3 times, what's
[00:12:24] going back and forth between a code review  and making changes based on the code review,
[00:12:29] my thinking since the event has kind of been,  how can I loopify as much of the work that I'm
[00:12:34] doing as possible? So what I have happening  on a regular basis is I have one loop that is
[00:12:40] automatically finding issues with my application  on a regular basis by interacting with it and just
[00:12:46] generally running code reviews on different  sections and automatically making issues. And
[00:12:52] then I have this backlog of issues and then I have  them automatically addressed around the clock. And
[00:12:57] you can see this has literally been happening as  I have been recording the video. It seems that I
[00:13:01] actually ran out of credits whilst recording.  So I'll have to do a reset. But essentially
[00:13:06] I had all these threads happening on a cloud  version on Hetzner. So I have Codex set up on a
[00:13:12] dedicated server and then I have my local version  automatically making brand new PRs on the remote
[00:13:18] server. And then it's automatically going back  and forth, making any fixes from the code review,
[00:13:23] also getting code reviews from Claude as well  by using the Claude P in headless mode too.
[00:13:28] And then it's making all those changes. Now I  can take this one step further and think like,
[00:13:33] okay, now it has to deploy the changes to the  preview environment, has to set up a new database,
[00:13:39] seed the database with data, and then have some  kind of browser use agent in the cloud actually
[00:13:45] verifying that change has been made. But in this  case, it can't verify the change because it's to
[00:13:50] do with an MCP server. So I'd have to set up an  environment where I can automatically verify any
[00:13:56] MCP server connections to AgentStack. So more  of my thinking since the event has been, Okay,
[00:14:01] how can I loopify as much of the work as possible?  And what kind of environments do I need to set up
[00:14:06] so that I can regularly produce work for the agent  to do, which are automatically filed as issues,
[00:14:12] and then regularly go through the issue backlog  and open up brand new PRs? In my particular case,
[00:14:16] I usually like to have like 20, 30 PRs open all  at once, and then it automatically merges PRs in,
[00:14:22] in order of how small the blast radius is. And  oftentimes many of these changes are really small
[00:14:27] and very rarely require my own review, so they  can be merged in automatically. Once I get to
[00:14:33] batch merging them in. And one of the cool things  inside of Codex is if you go to personalization,
[00:14:38] they have Chronicle Research Preview over here,  whereby it regularly takes screenshots of your
[00:14:42] screen and then you can use it to automatically  derive any new loops that you should be doing. So
[00:14:48] for example, one of the loops that it identified  for me is like automatically pulling in data from
[00:14:52] the PostHog session replays and then automatically  making and proposing changes to UI that would
[00:14:59] address those frustration signals. So sessions  with any rage clicks or errors in the last 3 days.
[00:15:04] And my thinking going forwards for the rest of  the year is what kind of loops can I have running
[00:15:09] automatically on a regular basis? And then for  them to deliver information to me regularly on
[00:15:14] Slack. And then I just have that as my decision  surface. And then I make all my decisions
[00:15:19] via Slack and I focus on setting up the right  environments for these loops to automatically run
[00:15:24] without me as much as possible. Now, so far, many  of my loops have been scoped to small changes. For
[00:15:30] example, only changing like less than 500 lines  or so. But I imagine that as the models get even
[00:15:36] better, then I will have loops that are working  on more ambitious tasks as well. Now, one of the
[00:15:41] questions I was really interested in asking and  managed to ask a couple of Anthropic employees
[00:15:44] at the event is that with each generation, as  the models are getting better, what is now the
[00:15:50] difference between a junior and a senior? What  makes a senior researcher, a senior engineer still
[00:15:56] better than a junior engineer, junior researcher?  Surely with you guys using the best models in the
[00:16:00] world internally, models better than Fable, better  than Mithras right now, surely there shouldn't be
[00:16:05] much of a difference between the two. So to be  a bit more specific, what exactly is a senior
[00:16:10] engineer doing differently from a junior engineer  when working back and forth with these models? Are
[00:16:15] they like prompting differently or doing something  else? And the general response that I seem to have
[00:16:20] gotten was whilst they did agree that the gap is  closing between junior and seniors, it's not a
[00:16:26] case of them promising the model differently. It's  more of a case of they still know that the model
[00:16:30] is wrong in many cases, even Fable, like Miphas  level models, because when they're reading through
[00:16:35] the output of the model, a senior researcher  has more lived experience to go on to determine
[00:16:40] that the model may have come to the wrong  conclusion, have some kind of hidden assumption,
[00:16:44] and then just generally better at reading through  the output of the model based on their own lived
[00:16:48] experience that they can then push it into a  different direction. Whereas a junior engineer,
[00:16:53] junior researcher would kind of read through the  output and be like, oh, everything checks off,
[00:16:56] makes sense, because they don't have the lived  experience to go off. But eventually the models
[00:17:00] will end up being so good that the junior would no  longer be required, and then eventually the senior
[00:17:05] would no longer be required because the models  would be improving themselves automatically. And
[00:17:09] at that point I was like, oh, so what are you  gonna do? And often the answer was like, I'm
[00:17:12] gonna retire, and I guess they can do so because  they would have enough equity from like the value
[00:17:17] of Anthropic shares or something like that. Now,  one thing that I have become more interested in
[00:17:22] lately is using AI models like Claude to generate  good ideas reliably. And I had a conversation with
[00:17:28] an Anthropic employee about this. I think he was  one of those who was acquihired into Anthropic.
[00:17:33] And basically we were talking about this workflow  of like having one really good insight. And this
[00:17:38] is either one insight that you uncovered yourself  or you may have found online in some kind of like
[00:17:43] really high signal tweet or video. Or you may have  come across in some kind of book. And usually what
[00:17:48] I do is I paste that insight in as a first message  into Claude, and then it kind of like puts a model
[00:17:55] in a certain state. So by putting this in as a  very first prompt, it's kind of like a seed for
[00:18:00] the model in a way. It's kind of like if you have  played Minecraft before, you kind of had a seed
[00:18:05] for generating a brand new world, and that world  may have had tons of diamonds under the surface,
[00:18:10] for example. It's kind of like that. And once I've  kind of activated a state in the model by giving
[00:18:15] it one really good insight at the beginning,  then I can kind of say, hey, so what are the
[00:18:19] implications of this? Can you give me like 30  different variations? And I can have a bit of back
[00:18:24] and forth discussion with the model about this new  idea. But usually I find that after about 50,000,
[00:18:29] 60,000 tokens, it kind of saturates and I got  to start again. Because it seems that when it
[00:18:34] comes to generating new ideas, the magic wears  off really quickly. Which is why you should not
[00:18:39] be putting any new insights that you have into an  existing chat. It should always be a brand new one
[00:18:45] instead. Because by doing that, you can avoid any  pollution from the existing chat. And by actually
[00:18:49] using the --system_prompts flag, you can also  remove the default system prompt inside of Claude
[00:18:55] Code if you want to use that. Now I find that  during this stage of telling it to branch into
[00:18:59] different possibilities, I still have to specify  a number like 30 or 50 or something. Because most
[00:19:05] of the ideas that the model ends up giving me  are bad and it feels like a slot machine in a
[00:19:09] way. But some of the ideas end up being like  really insightful, even more insightful than
[00:19:13] the original idea because they kind of touch  on something even deeper or they spot a like
[00:19:18] meta-level pattern or trend instead. So usually  what Claude Code, the slot machine, is producing
[00:19:23] here is a bunch of garbage, but occasionally  there's a hidden gem here. So it still takes
[00:19:29] my human lived experience to know which insights  are gems and which ones aren't. And it also takes
[00:19:34] human lived experience to have a good insight to  begin with. And that can even be your own insight,
[00:19:40] or it can be that of someone you found online from  Twitter or YouTube or something. Now what this
[00:19:44] means for me is I only try to consume content  from people who I know reliably deliver good
[00:19:50] insights. And then I usually end up unfollowing  people or muting people who don't deliver good
[00:19:55] insights on a regular basis. Now I find that  one of the implications of this for me is that
[00:19:59] a library of insights or a library of seeds is  exceptionally valuable because there's so many
[00:20:05] different things that I can load into Claude  Code to generate more ideas, figure out how I
[00:20:09] can improve my workflows and so forth. And that's  why I also made it much easier in my class because
[00:20:13] many people consider my class to be filled with  insights. And that's why I made it really easy for
[00:20:18] you to explore any of the ideas inside of Claude  Code by simply pressing this button over here.
[00:20:23] So yeah, this video is getting a bit long, but  there are still many more things that I learned
[00:20:27] from the event through my chats. And I will be  making more videos about it inside of my class.
