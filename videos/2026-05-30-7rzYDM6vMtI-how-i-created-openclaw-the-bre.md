---
video_id: 7rzYDM6vMtI
title: "How I Created OpenClaw, the Breakthrough AI Agent | Peter Steinberger | TED"
channel: TED
url: "https://www.youtube.com/watch?v=7rzYDM6vMtI"
watched_date: 2026-05-30
watched_at: "2026-05-30T12:00:00Z"
watch_count: 1
duration_seconds: 1056
source: youtube-history-browser
history_label: Saturday
history_order: 23
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 106
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

Peter Steinberger, a burnt-out entrepreneur, rediscovered his purpose in early 2025 by experimenting with AI coding agents. He realized that AI could handle all software development's boilerplate and tedious work, freeing humans to focus on thinking—the part he'd enjoyed for 25 years. He built a WhatsApp bot that autonomously solved problems he never programmed, like processing voice messages in 9 seconds by chaining multiple APIs together. Released as OpenClaw, his open-source project exploded into one of the fastest-growing on GitHub despite trademark disputes forcing a rebrand. Across the globe, non-programmers used it to build real businesses: a father-son team automated beer brewing and launched an e-commerce site, teenagers built tutoring services, and Chinese businesses automated daily employee tasks. Steinberger positioned OpenClaw as fundamentally about democratizing access to builders of all skill levels.

If you're seeking to boost productivity, experiment with AI agents to automate routine cognitive work (email management, calendar coordination, task coordination) instead of handling them manually. If you deploy agents, implement proper sandboxing—Steinberger recommends dedicated hardware like a Mac mini rather than running agents on your primary machine—to contain what agents can access. Identify bottlenecks in your own workflow where AI agents could free your energy for higher-level thinking; the real transformation isn't the technology itself but the shift from execution constraints to design constraints, letting anyone prototype an idea in an hour.

## Transcript

[00:00:04] What's OpenClaw?
[00:00:06] I've been programming since I was 14.
[00:00:11] Building software felt like playing a video game.
[00:00:16] I couldn't stop.
[00:00:19] Until I did.
[00:00:23] I created a company,
[00:00:25] I poured a decade of my life into it.
[00:00:29] No venture capital,
[00:00:32] every weekend.
[00:00:34] And then I sold the dream.
[00:00:38] And I felt absolutely nothing.
[00:00:43] For three years,
[00:00:46] I was wondering,
[00:00:48] did therapy, traveled,
[00:00:51] I changed countries twice.
[00:00:55] Nothing, nothing clicked.
[00:00:57] Now I wake up every morning
[00:01:00] with everything I was supposed to want
[00:01:02] and no reason.
[00:01:04] No reason to get out of bed.
[00:01:07] And then in early 2025,
[00:01:13] I tried an experiment.
[00:01:14] I wanted to see what these new AI coding agents are all about.
[00:01:21] And I had what I can only describe as a "holy shit" moment.
[00:01:28] The boilerplate, the plumbing,
[00:01:31] all the boring parts that was software development,
[00:01:36] AI could do all of it.
[00:01:39] The bottleneck is no longer typing.
[00:01:42] It's thinking.
[00:01:43] And thinking was the part I did [for] 25 years.
[00:01:50] Building software felt like playing a video game again.
[00:01:54] I was back.
[00:01:56] I built 44 projects in just a few months.
[00:02:02] And the latest one was a WhatsApp bot.
[00:02:07] I put it on my computer,
[00:02:09] it talks through the apps that you already know.
[00:02:17] And then I took it on a trip to Marrakesh.
[00:02:21] You know, just to navigate around, to find restaurants, do translations.
[00:02:28] And at first, it didn't really feel right.
[00:02:32] It felt too much like a tool,
[00:02:36] not like a friend.
[00:02:39] You know, too many bullet points, too many tables.
[00:02:43] So I told it,
[00:02:45] because those modern models, they are so smart,
[00:02:48] they know what WhatsApp is, they know how people talk.
[00:02:51] I just had to tell it.
[00:02:53] And then it felt right.
[00:02:57] And you know how you talk to friends --
[00:02:59] at some point I was walking around and I was sending it a voice message.
[00:03:05] And then I froze because I actually,
[00:03:10] I didn't build voice in there.
[00:03:13] I added support for images, yeah, but even that took hours.
[00:03:16] So I was looking at the typing indicator,
[00:03:20] and then the agent responded.
[00:03:23] And I very vividly remember this situation
[00:03:25] where I was standing there and I was like,
[00:03:28] how did you do that?
[00:03:30] And the agent replied, I'm not kidding you,
[00:03:32] "The mad lad figured it out on its own."
[00:03:36] (Laughter)
[00:03:37] And then it walked me through every single step:
[00:03:39] how it got a message from me
[00:03:41] but there was no file ending, so it inspected the file,
[00:03:44] it found that it was audio, but a weird format, so it converted it.
[00:03:48] And then it was looking for something to translate the audio,
[00:03:52] but I didn't have it installed.
[00:03:54] But then it found an OpenAI key, it sent the whole thing to the server,
[00:03:58] it got it back, and then it replied.
[00:04:01] All of that in nine seconds.
[00:04:04] Can you imagine? I didn't build any of that.
[00:04:07] For me, this was the moment where I thought,
[00:04:11] this is something new.
[00:04:12] This is not a chatbot.
[00:04:14] Chatbots give up.
[00:04:16] Agents improvise.
[00:04:20] And, you know, I was sold.
[00:04:22] I wanted to share this.
[00:04:23] I wanted to like, tell people on Twitter.
[00:04:26] And nobody really got it.
[00:04:28] It's like, it's almost like you have to experience an agent.
[00:04:33] It's kind of hard to explain.
[00:04:37] It took me a few weeks.
[00:04:39] And then I did something stupid.
[00:04:42] And remember, this agent, by default,
[00:04:47] can do anything that you can do on your computer.
[00:04:52] So obviously I put it in a public Discord, and I invited random people.
[00:04:56] (Laughter)
[00:04:57] And I was looking at it the whole night.
[00:05:00] People were talking with it,
[00:05:02] people were having fun with it, people tried to hack it.
[00:05:06] And when my eyes were like, falling off almost,
[00:05:12] I exited the process, and I went to bed.
[00:05:19] Though I forgot -- I built a system to be resilient.
[00:05:23] So while I was walking to the bedroom,
[00:05:25] the agent happily booted up again and talked to everyone in the world.
[00:05:31] The next morning I woke up --
[00:05:33] over 800 messages.
[00:05:36] I panicked.
[00:05:37] I pulled the plug,
[00:05:38] I read every single message
[00:05:42] just to see if the agent leaked my private life.
[00:05:45] (Laughter)
[00:05:47] Nothing happened.
[00:05:48] But it could have.
[00:05:50] But that was the moment where it went viral.
[00:05:54] Today, the project is called OpenClaw.
[00:05:58] It's pretty much the fastest-growing open-source project.
[00:06:03] Its mascot is a lobster.
[00:06:05] It claws into your machine.
[00:06:09] Jensen Huang calls it the operating system for personal AI.
[00:06:15] But by far, my favorite quote is from a friend
[00:06:18] who looked at this statistic and said,
[00:06:20] "Peter, this is not hockey-stick growth.
[00:06:23] This is stripper pole."
[00:06:25] (Laughter)
[00:06:34] And I, I was not ready.
[00:06:38] You know, when something blows up like this,
[00:06:41] everything explodes.
[00:06:43] Hundreds of messages,
[00:06:44] reporters calling me in the middle of the night,
[00:06:47] security vulnerabilities.
[00:06:50] And then
[00:06:53] the AI company whose model most of my users loved
[00:06:57] sent me a trademark claim.
[00:06:59] I had to rename the whole thing while it was taking off.
[00:07:04] You know, they even tried to push me away from the lobster.
[00:07:09] (Laughter)
[00:07:11] Like, I was staring at the message.
[00:07:13] It was like, it's not even the same animal.
[00:07:18] And then they also cut off the model most of my users loved.
[00:07:23] You know, first the name,
[00:07:27] then the lobster,
[00:07:29] then the model.
[00:07:32] I was that close to just deleting the whole thing.
[00:07:36] But then I learned what people are building with it.
[00:07:42] So at ClawCon in Vienna,
[00:07:45] because yes, we have conferences already --
[00:07:47] (Laughter)
[00:07:49] And people wore lobster headbands,
[00:07:52] I met Stefan
[00:07:54] and his 60-year-old dad, Gerhard,
[00:07:58] a beer sommelier who never wrote a single line of code.
[00:08:04] They connected OpenClaw via Bluetooth,
[00:08:08] sent it one prompt,
[00:08:09] and the agent did the whole 90-minute brew:
[00:08:13] temperature ramps, hop additions, everything.
[00:08:16] And then they were like, what are we doing with all this beer?
[00:08:22] And the agent was, "Let's make a website."
[00:08:25] So they built a website, and then they added payments,
[00:08:28] and now they have a real product.
[00:08:30] And almost all of it was just done via the phone.
[00:08:36] In China,
[00:08:39] installing OpenClaw is called raising lobsters.
[00:08:44] (Laughter)
[00:08:46] Thousands of people were lining up at the Tencent office in Shenzhen
[00:08:51] to get their lobster installed.
[00:08:54] Shenzhen even gives out subsidies for people running businesses on OpenClaw.
[00:09:01] Now
[00:09:03] if you install OpenClaw on your work machine,
[00:09:07] at least with the default settings,
[00:09:09] you might get fired.
[00:09:12] And then I met an entrepreneur in China
[00:09:16] who showed me a spreadsheet.
[00:09:19] Every employee, every day,
[00:09:21] one task automated by OpenClaw.
[00:09:25] If you miss too many days, you're fired.
[00:09:28] So fired for using it,
[00:09:32] fired for not using it.
[00:09:37] After Marrakesh,
[00:09:39] I thought, this is incredible.
[00:09:42] And it's also a little bit scary.
[00:09:45] How can we make it more scary?
[00:09:47] (Laughter)
[00:09:49] So I added a new feature, a heartbeat.
[00:09:53] You know, by default,
[00:09:54] the agent would only wake up when you send it a prompt.
[00:09:58] With the heartbeat,
[00:09:59] the agent would just wake up periodically,
[00:10:02] check your emails,
[00:10:04] check your calendar, follow up on loose ends.
[00:10:07] My initial prompt was simply "surprise me."
[00:10:12] And yes, that's kind of as scary as it sounds.
[00:10:16] So no large company would ship something like that.
[00:10:20] But I'm a random builder from Austria.
[00:10:23] I don't have a legal department.
[00:10:25] (Laughter)
[00:10:28] I built this sandbox, this sandcastle, for me,
[00:10:33] and I made it open-source so other people could play with it
[00:10:37] and other people could raise their imagination.
[00:10:41] Imagine putting an agent into a meeting.
[00:10:45] Not for notes, we figured that out.
[00:10:48] A bidirectional model that can listen and hear at the same time.
[00:10:55] Somebody mentions a statistic,
[00:10:57] a subagent can spin off and check it for you.
[00:11:00] A decision is made,
[00:11:01] the agent can send a follow-up
[00:11:03] before the meeting even ends.
[00:11:06] In the future,
[00:11:08] we're not just going to have one agent.
[00:11:11] You might have your work agent,
[00:11:14] your personal Claw, maybe one for health,
[00:11:16] maybe one for relationship.
[00:11:19] And they all should work together in a secure way.
[00:11:23] Because how did humanity level up?
[00:11:26] By specializing and collaborating.
[00:11:30] And agents are about to do the same.
[00:11:34] Imagine a company, a small business
[00:11:38] that has ten agents that are all specialized,
[00:11:41] taking over various parts of the business.
[00:11:44] We don't even have a name for what it might become,
[00:11:47] but we are about to find out.
[00:11:50] So I created the OpenClaw Foundation,
[00:11:54] a nonprofit, open-source forever.
[00:11:58] Because what OpenClaw did for many people
[00:12:02] was it moved AI from this scary,
[00:12:07] nebulous thing
[00:12:09] into something that is fun
[00:12:12] and useful and maybe a bit weird.
[00:12:15] You know, lobsters and headbands and beer businesses.
[00:12:20] Because what we need in the future is more people spending more time with AI
[00:12:27] to better understand how powerful
[00:12:29] and transformative this technology really is.
[00:12:34] In New York,
[00:12:37] at ClawCon ...
[00:12:40] (Laughter)
[00:12:41] Yes, they're everywhere now.
[00:12:44] There were thousands of people that were discussing
[00:12:48] what the lobster did this week.
[00:12:52] A retiree in Shenzhen who automated their groceries.
[00:12:58] A teenager in Sao Paulo
[00:13:00] who built a tutoring business on OpenClaw.
[00:13:04] Gerhard and his beer machine.
[00:13:07] None of them are programmers.
[00:13:10] All of them are builders.
[00:13:13] Because that's the real transformation.
[00:13:16] It's not a technology.
[00:13:18] It's the access.
[00:13:20] Agents change who can build things,
[00:13:23] and that door is not closing again.
[00:13:27] Because when you can prompt a prototype into existence
[00:13:33] in one hour,
[00:13:35] anything is possible.
[00:13:37] The next breakthrough can come from anyone,
[00:13:41] any country,
[00:13:43] any cafe.
[00:13:46] When even a burnt-out founder,
[00:13:50] staring at the screen,
[00:13:53] wondering if his spark is gone
[00:13:57] can do something like that.
[00:14:01] It's not gone.
[00:14:03] It's just waiting.
[00:14:05] The lobster is loose,
[00:14:07] and it's not going back into the tank.
[00:14:10] Thank you very much.
[00:14:12] (Applause)
[00:14:21] Chris Anderson: Come here.
[00:14:24] I mean.
[00:14:27] I think I want to say something personal to you.
[00:14:30] With love, but truth.
[00:14:33] You really terrify me.
[00:14:35] (Laughter)
[00:14:37] CA: I’m serious.
[00:14:39] If Hollywood was to ever make a movie
[00:14:41] in which humanity opened Pandora’s box,
[00:14:45] and everything went crazy,
[00:14:46] like, you seriously could be cast as the star character.
[00:14:50] (Laughter)
[00:14:51] CA: Because the story we’re told
[00:14:54] is that AI researchers are doing all this great stuff,
[00:14:57] but they're taking all these great efforts to ensure safety
[00:15:01] and make sure nothing bad could happen.
[00:15:04] You take glee in seeing what might happen if you just put it out there.
[00:15:10] Like, is any part of you feeling that that's a little bit reckless?
[00:15:17] Peter Steinberger: I wouldn't say so.
[00:15:19] I see my work as a ...
[00:15:20] (Laughter)
[00:15:22] PS: I see it as a window into the future.
[00:15:24] Like, in the very beginning, there were all these scary moments.
[00:15:31] Now we have proper security layers.
[00:15:33] You can have your sandbox,
[00:15:35] you can put your lobster into a very small, tiny box
[00:15:41] and really control what it can do.
[00:15:43] There are still some issues that we need to figure out,
[00:15:46] but the fact that so many people want this now
[00:15:49] will help to figure this out much faster.
[00:15:52] CA: So I'm glad you mentioned the security layers.
[00:15:56] I mean, you're making a huge bet on human ingenuity using this.
[00:16:01] This is an incredible tool that suddenly can maximize the power
[00:16:05] of what any human can do.
[00:16:12] How many people in your community
[00:16:15] are taking the safety issue seriously
[00:16:17] and want to use OpenClaw, for example, to find smarter ways?
[00:16:20] Just checking whether anything might be going wrong
[00:16:24] and giving an early alarm to someone or something like that?
[00:16:28] PS: Most people are not as reckless [as] --
[00:16:30] number one, putting it into a public Discord --
[00:16:33] strongly don't recommend.
[00:16:36] Number two, I think I single-handedly increased
[00:16:40] Mac mini sales by multiple percent.
[00:16:43] So most people give it their own little Mac mini.
[00:16:46] Mine's a little princess.
[00:16:48] Mine got a Mac studio.
[00:16:49] It calls it “The Castle.”
[00:16:51] And that greatly reduces the actual risk
[00:16:55] because you can only access what's on that computer.
[00:16:57] And maybe all your pictures are not there.
[00:17:00] CA: Well, definitely, if humanity goes down,
[00:17:02] I'll be very grateful for at least the rise in Mac mini sales
[00:17:05] for a period of time.
[00:17:07] You are amazing.
[00:17:08] You are amazing,
[00:17:10] and I think you're actually right at the cutting edge
[00:17:13] of whether AI is going to be the biggest boon ever
[00:17:17] or possibly a serious problem.
[00:17:19] And, you know, I hope you continue conversations with people here
[00:17:23] and just help us get smarter on how to do this the right way
[00:17:27] because it is absolutely incredible what you've built.
[00:17:29] Thank you for sharing so honestly.
[00:17:31] PS: Thank you so much.
[00:17:32] (Applause)
