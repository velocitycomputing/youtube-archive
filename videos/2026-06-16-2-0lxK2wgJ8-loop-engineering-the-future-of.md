---
video_id: 2-0lxK2wgJ8
title: "Loop Engineering: The Future of AI Coding?"
channel: Ray Amjad
url: "https://www.youtube.com/watch?v=2-0lxK2wgJ8"
watched_date: 2026-06-16
watched_at: "2026-06-16T12:00:00Z"
watch_count: 1
duration_seconds: 964
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 50
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 96
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video presents a paradigm shift in AI development: moving from manually prompting Claude for each task to designing automated loops that continuously prompt Claude themselves. The speaker describes three evolutionary stages—hand-coding with AI autocomplete, juggling multiple agents manually, and the emerging stage 3 where loops autonomously drive agents. Examples include a Sentry loop that runs daily to detect and auto-fix critical issues, competitive monitoring loops that feed new features into build loops, and ML optimization loops that test strategies from archive.org. The core pattern involves inner loops (specific workflows like feature implementation) managed by outer loops (that supply tasks, like competitor analysis), with memory systems (Git, Slack, Airtable) keeping state across runs to prevent redundant work and track decisions.

To implement this, start using Claude Code's `/loop` and `/goal` commands to automate multi-step workflows that you currently drive manually—spec → implement → code-review → fix → verify → merge becomes one autonomous loop rather than six separate prompts. Use Slack channels as memory and decision surfaces where loops post results and you react with emoji to guide next steps. Add verification steps (test runs, adversarial code reviews, production error monitoring) to prevent quality degradation. Monitor external sources like competitor websites to supply new specs to your build loops. Track whether loops generate economic value relative to token cost before scaling. The creator's "Loopy AI" masterclass launches next week with 30% discount for early signup.

## Transcript

[00:00:00] Okay, so over the last 24 hours, almost  everyone has been having a paradigm shift
[00:00:04] where they realize that they should no longer be  prompting their agents, but instead prompting and
[00:00:09] designing loops that in turn prompt their agents  for them. Now, this was started last week because
[00:00:14] Brosz Czerny said this in an interview. Now  it's actually leveled up, I think, again to
[00:00:18] the next wave of abstraction where I don't prompt  Claude anymore. I have loops that are running.
[00:00:23] They're the ones that are prompting Claude and  kind of figuring out what to do. My job is to
[00:00:26] write loops. And then this was repeated again  by the creator of OpenAI saying that you should
[00:00:31] be designing loops that prompt your agents. Now  what's causing a lot of frustration with people
[00:00:35] is that no one has taught folks how to do this. It  feels both evidently the future and also somehow
[00:00:40] gatekept. So I'll be focusing on the higher level  picture and then going through a few examples
[00:00:45] inside of this video. Now before getting started,  I wanna quickly mention that I have been teaching
[00:00:49] this for over 3 months inside of my masterclass.  So I made a bunch of videos about this back in
[00:00:54] February and I'm still making more. And I have  been running loops pretty much every single day.
[00:00:59] So for example, I ran this loop that ran for  about 19 hours and verified over 500 different
[00:01:05] user flows inside my new application. And then I  ran another loop after that that basically fixed
[00:01:11] a whole bunch of the issues that the previous loop  identified over the course of 11 hours. Now before
[00:01:16] reaching this level, let's quickly go back to  where we were. So about a year, 2 years ago,
[00:01:21] we were hand coding with AI autocomplete. So  we would be writing in like a line of code
[00:01:26] and then it would complete the function for  us. And then about a year ago, 6 months ago,
[00:01:30] we started juggling many different agents  together. So you've probably seen people with like
[00:01:34] 6 different agent windows open and they're jumping  between each of them, prompting one after another,
[00:01:39] but they're still inside of the loop of each  agent actually prompting each one individually.
[00:01:44] Now most people are at stage 2 and if you are  at that stage and completely happy with that,
[00:01:48] then you can end the video right now.. But if  you wanna move on to stage 3, kind of like Boris,
[00:01:52] then you gotta be writing loops. Now Boris has a  couple different loops that he mentioned in the
[00:01:57] video. He didn't go into too much detail about  it, but he has some that look through GitHub,
[00:02:02] find any issues, flag those issues and make any  fixes. He has other ones that go through Slack and
[00:02:07] identify what other people are doing. And then  he also has some that go through Twitter as well,
[00:02:11] different agents running on a loop that kind of  decides what to build next for Claude Code. Now
[00:02:16] to give you a really simple example of a loop that  I have running is a scheduled task where every 24
[00:02:22] hours it looks through Sentry, identifies  any issues affecting more than 20 users,
[00:02:27] and then automatically creates a brand new  PR fixing that particular issue. And besides
[00:02:31] Claude Code routines, we've seen this in a couple  of different ways. So we have the /loop command
[00:02:36] inside of Claude Code. We also have /goal,  which I made a previous video about inside
[00:02:41] of Codex and Claude Code. So what I showed  you previously where Claude Code tested over
[00:02:45] 300 user flows over 19 hours, that was a slash  goal. And in the case of that loop, I had Claude
[00:02:51] Code automatically do a screen recording  for every single user flow that it tested,
[00:02:55] and it stored it all into a folder over here.  So I can just watch through all the recordings
[00:03:00] and make sure that it did a good job. So  here is one of the recordings that it did,
[00:03:04] where it's basically testing out this like lead  collection modal. We have also seen this in the
[00:03:08] form of Andrej Karpathy's AutoResearch, where we  have a loop optimizing some code and then scoring
[00:03:15] it against a benchmark. And if the optimization  led to a better result, it would keep it. If not,
[00:03:19] it would discard it. And interestingly enough,  Microsoft have also applied the same idea of like,
[00:03:24] what if instead of changing code, we changed  agent skills instead and had self-improving
[00:03:29] agent skills? I'll have a separate video about  this coming soon, so do stay subscribed for that.
[00:03:34] But I have also been using auto research  quite a lot recently in the form of /goal,
[00:03:39] whereby I was basically optimizing Gemma 4 to  run locally on my machine. And you can see that
[00:03:44] it tried a whole bunch of things and then it kept  what worked and reverted what didn't work. And we
[00:03:48] saw this in a different form in January by having  the RALPH loop. So we would break down a big task
[00:03:53] into many small tasks and then do each in a brand  new context window. But the same principle still
[00:03:58] applies whereby we have some kind of trigger and  that can be a prompt, a time of day, or like an
[00:04:04] event happening at a data source. We would have  some kind of variation running and that could be
[00:04:08] a goal/loop, auto research, a RALPH loop. We would  check whether it's done and if it's not done,
[00:04:14] then it would basically repeat again. Okay,  now let's go for a more concrete example of
[00:04:18] something you may have been doing until now. So  you may have worked back and forth with a coding
[00:04:23] agent to come up with a spec. And once you have  that ready, you then tell the agent like, "Hey,
[00:04:28] implement this for me please." And this would  be your prompt. And then after it's implemented,
[00:04:32] you may say like, do /code-review, or you may have  another code review skill. So we already have one
[00:04:37] inside of Claude Code, which is /code-review, and  it would spin up a bunch of subagents and find any
[00:04:42] issues with the implementation. And then next  up, you would prompt it and be like, Hey, hey,
[00:04:46] fix these issues for me. So fix these issues  for me. And then after it's fixed the issues,
[00:04:51] you may do another code review and you may kind  of like go back and forth between these two stages
[00:04:56] 2 or 3 times until you're happy. Then you may  have prompted it again being like run the tests,
[00:05:02] open like Claude in Chrome, for example. And  then it would open Claude in Chrome, test it out,
[00:05:07] do everything for you, maybe record some like  screen recordings for you to check later. And
[00:05:11] then for anything that's broken, it would then fix  those issues again. So you can see right now we
[00:05:16] already have two loops happening that you're kind  of doing manually and you're driving manually.
[00:05:20] So we have this loop over here of the code review  fix going back and forth. And then we have another
[00:05:26] loop over here of the verification, like fix going  back and forth. And then you would say something
[00:05:31] like open and merge PR. And then you may prompt  your agent after the PR has been merged, saying
[00:05:37] something like /loop 2 minutes check for errors.  So like check if there are any increase in errors
[00:05:44] because this feature has now been merged. And then  if it identified some kind of error, you may have
[00:05:48] prompted it being like, okay, cool, fix this error  for me. So you can see in this white text, this is
[00:05:54] where you're prompting Claude Code, Codex every  single time. And then when it fixes the error,
[00:05:59] it may go back over to the implementation stage  right all the way over here. So you can see this
[00:06:04] is now a bigger loop that's happening. Now, if  you have been doing something like this until now,
[00:06:08] you are in the middle of a manual loop and a unit  of work for you was the prompt itself. But now if
[00:06:15] we're moving on to stage 3, we want to have a unit  of work being the loop itself rather than just a
[00:06:20] prompt. So we have an input and then it goes  through the cycle that we just showed and then
[00:06:25] it makes an output which can be a merged PR and  some screen recordings that you can be confident
[00:06:30] to know the feature works. So essentially this  entire process over here should be one big loop
[00:06:35] instead. So we have some smaller loops which  are inside of this bigger loop and our input,
[00:06:41] so loop over here is a spec that we will still  write ourselves because we want to kind of decide
[00:06:46] how a feature should look. And then the output of  the loop here would be a screen recording with a
[00:06:51] merged PR to show the feature works as intended.  And this is exactly what the BigLabs are talking
[00:06:56] about. We should be designing a system kind of  like this, a loop, which is now a single unit of
[00:07:01] work. So all of this here is now a unit of work.  And of course you don't have to design a loop like
[00:07:06] this alone. You can design it with the help of  an agent. So you decide what the inputs would be,
[00:07:11] which can be a spec, what kind of actions they  would take, what kind of checks they would do,
[00:07:15] where any memory would be stored, when it  would exit the loop and decide that it's done,
[00:07:20] and then where it would surface anything that has  been done for you. So that could be by sending you
[00:07:24] a Telegram message, it could be sending you a  message on Slack or something else. So you can
[00:07:29] kind of imagine at the very end of this loop over  here, our agent sent us a message on Slack with
[00:07:39] releasing a brand new class in my masterclass  all about agent engineering. Called Loopy AI.
[00:07:45] And I have been working on this for the last  couple of weeks because I noticed that this
[00:07:49] was going to be the future. So if you wanna go  into much more detail in a lot of the concepts,
[00:07:53] then this class will be available on  Monday next week. And if you sign up now,
[00:07:57] then you can get 30% off lifetime. By signing up,  you also get access to all the previous videos,
[00:08:02] about 300 that I made about Claude Code, Codex,  a bunch of fundamental and advanced techniques.
[00:08:09] When it comes to using these agents, context  engineering, prompt engineering, and a bunch
[00:08:13] more stuff. Many people have found a lot of what  I covered in the class to be many months ahead of
[00:08:17] the curve, and you may find that too. So the Loopy  AI class will be exactly like that because this
[00:08:23] is a direction we're going to be seeing going  forwards. And finally, for the Loopy AI class,
[00:08:27] there will be some live office hours that you  can bring your questions if you're interested,
[00:08:30] and there is also a 30-day money-back guarantee if  you don't feel satisfied for whatever reason. Now
[00:08:35] experimenting around, learning a bunch, and then  sharing my insights in this class will be my focus
[00:08:40] for the next couple of months. So if you wanna  sign up now at a discount, then the link will
[00:08:44] be down below. Now we wanna take this loop to the  next level, and that would be by making an outer
[00:08:50] loop that manages the inner loop. So we can kind  of imagine it like this. So the inner loop that we
[00:08:56] defined earlier is basically implementing a spec,  but we may want like new specs being regularly
[00:09:01] delivered to the inner loop to implement. And  we could have another loop that is monitoring
[00:09:05] our competitors. So it automatically goes to our  competitor's website, notices any new feature that
[00:09:11] was added, and then automatically passes this into  the inner loop to then implement that feature.
[00:09:17] So essentially the outer loop to our inner loop  could look something kind of like this. We check
[00:09:21] our competitor's LinkedIn, X, their changelogs  every single day to know when they announced a new
[00:09:27] feature. We then use like browser use or computer  use to click around and find out how the feature
[00:09:32] works. We could also inspect like network logs and  stuff like that. And then based on that, we would
[00:09:37] write a brand new spec being like, hey, we'll  implement the same feature ourselves as well. So
[00:09:42] this could also be another smaller inner loop as  well, where we have a good inner loop for writing
[00:09:47] specs. Then we may have some kind of a human in  the loop to approve. And if you do approve it,
[00:09:51] then you trigger the inner loop that would then  trigger the entire build for us, this build
[00:09:57] over here. And if you don't approve it, then it  would just wait until tomorrow. Okay, so let's go
[00:10:01] through two more examples of inner loops and outer  loops. So you may have an inner loop running /goal
[00:10:07] to kind of find performance improvements for an ML  model that you're working on. And then you would
[00:10:12] have an outer loop that monitors archive.org every  single day for any new strategies that may apply
[00:10:18] to the ML model you're working on to get better  performance. So it could look something kind of
[00:10:23] like this. Anytime it finds a new strategy, it  passes it down to inner loop.. And then once
[00:10:28] an inner loop like beats your existing strategy  by a certain like percentage, then it will notify
[00:10:33] you on the channel you care about, like Slack.  As a non-technical example, let's say you're
[00:10:37] running some kind of cold email campaign. You may  have some kind of inner loop that is doing auto
[00:10:42] research to improve the email copy on 10% of the  list. And that would be like asking for feedback,
[00:10:48] human in the loop kind of every single day. And  then you would have a longer-term outer loop
[00:10:53] that may run every single week. And it monitors a  bunch of fake inboxes that you set up to receive
[00:10:58] campaigns from any competitors in your niche. And  that could be feeding into the inner loop to kind
[00:11:03] of see if it would beat your existing campaigns in  a way. Now, every single time a loop runs, it will
[00:11:08] be stateless, which is why we want to have memory  for our loops. Now, this could be some kind of
[00:11:12] file system or Git, for example. So the loop that  I have set up to fix Sentry issues every single
[00:11:18] day, it knows which ones have already been fixed  yesterday. Because it can just look at the commits
[00:11:23] from yesterday. But it could also be an external  memory layer, kind of like Slack or Airtable. So
[00:11:29] you may have Airtable set up and then you connect  it to your Claude Code schedule routine via the
[00:11:34] connectors over here. And then when you define  your loop inside of the instructions over here,
[00:11:38] you would tell it, hey, first, can you check  the Airtable to make sure that we haven't done
[00:11:42] this before? Now, one thing I personally like  to do is to have Slack as a memory layer and
[00:11:48] a decision surface for many of my longer-term  loops that would run every day or every week,
[00:11:53] for example. So I have a channel over here which  is for optimizing my landing page in this project,
[00:11:59] and then I have many different channels, each  belonging to a different loop. Now I have a bot
[00:12:04] that automatically posts to channel, so this one  is analyzing my landing page and be like, hey,
[00:12:09] these are some of the issues, here are some of the  recommendations I have for fixing them, and uplift
[00:12:14] by fixing them. So for example, it says, okay,  do this. And every time the loop runs, it can
[00:12:20] see any previous messages that it sent yesterday.  And then I can also make decisions from here. So
[00:12:25] I like this suggestion over here, which is number  4. I can basically right-click, do add reaction,
[00:12:30] choose number 4. And then the next time the  loop runs, it will look at the previous message,
[00:12:35] my reaction to it, and then make that change and  automatically send a message. To that channel. So
[00:12:40] this is both a memory layer for the loop, 'cause I  can see the previous messages, and also a decision
[00:12:45] surface for me because I can leave reactions,  which automatically tell it like what it needs to
[00:12:50] be doing next. Now memory is really great for our  loops because it means that they can compound over
[00:12:55] time. But one of the problems with that is that  we can have our slop compounding as well. So if
[00:13:00] you don't keep your loops in check, you can just  lead to way more slop over time. And this is one
[00:13:05] of the problems that many people face. And the way  that I see it is that entropy is slowly increasing
[00:13:09] over time anyway. And agents, because they can do  a lot of work, basically collapse that into a much
[00:13:15] shorter time. So the amount of entropy we're  facing on a day-to-day basis is much greater than
[00:13:20] it was like 2 years ago. And there are a bunch of  things that you can do about it. So for example,
[00:13:24] you can have outer loops that can kind of ground  like your inner loop that is increasing entropy
[00:13:29] in like external sources, for example. But one  thing that I like to do, especially when it comes
[00:13:34] to coding, is having adversarial code reviews. So  for example, the reason I have this code review
[00:13:40] in the previous loop redefine over here and the  verification step is to reduce the entropy from
[00:13:44] increasing a lot over time. So ideally you want  some kind of oracle outside of the model, and that
[00:13:50] could be like test passing, the real production  errors, Stripe revenue, like actual reply rates,
[00:13:56] for example, that kind of keeps the loop in check  and prevents slop from accumulating. Now the way
[00:14:00] that Boris kind of talks about this is that loops  are the next evolution. So he kind of talks about
[00:14:06] punch cards being a thing in the 1940s. Then we  moved up one layer to assembly, and then we moved
[00:14:11] up to higher level languages like C, and then we  moved over to libraries and frameworks like Rails,
[00:14:18] Next.js, and so forth. And then we moved over to  prompts, and now we finally have loops, which are
[00:14:23] then running our prompts for us. So eventually  you stop being the thing that runs You design
[00:14:28] the thing that runs and the leverage moves up one  more layer. And I think one thing that we will be
[00:14:32] seeing over the next couple of months is having  loops that check up on your work and your loops
[00:14:37] to find opportunities for future loops. So it's  kind of like having a meta loop. So for example,
[00:14:42] when making this loop, you may give it access  to everything inside of your organization,
[00:14:47] as well as the ability to view existing  loops. And then it could kind of identify
[00:14:51] which loops are working and making impacts  on the bottom line. Which are not working,
[00:14:55] and then also create new loops for you as well,  with your approval, of course. And I don't think
[00:15:00] we've quite reached the stage where the models  have enough taste to decide what should be good
[00:15:05] loops and not good loops, for example. So maybe  it would give you like 10, 20 recommendations and
[00:15:09] then you apply your own taste and filter it down,  for example. But if you do want to compound over
[00:15:14] the next couple of months, then this is what  you should be thinking about. Now, of course,
[00:15:18] this can end up using a bunch of tokens if you're  not careful and wasting them. So that's why, like,
[00:15:23] you got to be mindful of like, hey, are these  tokens actually economically valuable? Are
[00:15:28] they making a difference to my bottom line  for my business over here? So for example,
[00:15:32] in this situation I used 4.1 million tokens, but  I know these tokens were economically valuable
[00:15:37] because I will make more money back from the  kind of work that was done here than the amount
[00:15:42] of money that was spent on the tokens. Anyways, if  you do like this kind of stuff, then do subscribe
[00:15:47] to the channel because I only upload videos when  I feel like there's something worth saying. And
[00:15:51] if you do want to stay in the loop, quote unquote,  you can also join my email newsletter that will be
[00:15:56] linked down below. And remember that if you  do want to save money on my Loopy AI class
[00:16:00] that will be launching next week, then there  will be a link down below for that as well.
