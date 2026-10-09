---
record_id: "youtube:NYFGCESmikA"
video_id: NYFGCESmikA
title: "DHH: Future of Programming, AI, Agentic Engineering, Vibe Coding & Linux | Lex Fridman Podcast #501"
channel: Lex Fridman
url: "https://www.youtube.com/watch?v=NYFGCESmikA"
watched_date: 2026-08-26
watched_at: "2026-08-26T12:00:00Z"
watch_count: 1
duration_seconds: 18951
source: youtube-history-browser
added_date: 
history_label: Aug 26
history_order: 54
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 1895
transcript_status: fetched
transcript_content_hash: ecbb81f9574f2d29c79394a2acca3ec12ad3348aa551e204795966b7589cc205
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

David Heinemeier Hansson (DHH), creator of Ruby on Rails, CTO of 37signals, and creator of the Omarchy Linux distribution, talks with Lex Fridman about how his view of AI programming changed in 13 months. He says he was skeptical in 2025, when AI meant autocomplete and chatbots. The turning point was Opus 4.5 (released November 24, 2025), whose agent harness could use tools and check its own work, followed by sub-agents in spring 2026. He says this summer's models (Opus 5, Fable, GPT Sol) let him describe a fuzzy problem and have the model choose the route, so he is now "optional" in code production. He has written none of Omarchy "Quattro" by hand for two months, and he reviews only the model layer and critical code. He became a polyglot, shipping three C++/Qt apps, including a Typora replacement that took about 20 minutes to first draft. Basecamp 5 was harder: in February, designers "vibing" PRs wrecked the architecture and humans had to clean it up. He argues large companies don't ship faster because the bottleneck is human communication, vision and taste rather than implementation, and that the innovator's dilemma leaves them exposed. He also argues that AI-written pull requests beat the median human contribution, that maintainers should feel free to decline them, and that Linux desktop gaps such as Premiere or Photoshop can now be filled by individuals. He merged over 1,000 PRs in three months. The transcript was truncated at about 30,000 of 290,000 characters, so this covers only the opening section on AI and programming.

For you, the practical points are these. Build the tools you need yourself: tell an agent to write the app, then have it publish the repo to GitHub with a README and releases, as DHH suggests to Lex, who hesitates to ship software for many users. Pick the 5% of a commercial app you actually use and have an agent rebuild it, especially if one app keeps you off Linux. Talk to agents directly instead of routing through layers of approval, because he says human bandwidth is the real bottleneck. On an existing codebase, keep a person guarding the architecture. His "let the designers vibe" experiment degraded Basecamp until it was cleaned up by hand. Review the critical layers (data model, security-sensitive code) yourself, and let the agent handle UI and auxiliary code. If you maintain open source, treat AI-written PRs as optional and decline the ones you don't want. Ask that contributors' PRs include tests and a clear rationale. Treat his claims, such as "100% agent-written" and "1000X productivity", as one practitioner's anecdotes. He gives no benchmarks, and his own Basecamp experience shows the results vary.

## Transcript

[00:00:00] - There are decades where nothing happens and weeks where decades happen.
[00:00:05] And we have seen decades of progress
[00:00:09] happen in the last nine months. If you're not recognizing the
[00:00:14] gravity of the moment, that's the delusion. That's the
[00:00:18] psychosis. Who would not get delirious if suddenly a genie
[00:00:22] pops out of the bottle and says, "You can have whatever you want.
[00:00:26] Every feature you've ever dreamed of in an operating
[00:00:30] system, I can deliver them to you,
[00:00:32] most of them in five minutes, a few in 20, and if we really go hog wild, it's
[00:00:36] gonna take me two hours." I want the fastest car breaking the speed
[00:00:40] limits. I want the diver watch that can go down the Mariana
[00:00:44] Trench. I want the operating system that can install in less than
[00:00:48] 60 seconds. One of the things I always loved about race cars was when I
[00:00:51] would stumble out of the car absolutely smashed and barely able to
[00:00:55] hold my head up, and I'd lay down on the garage floor and just think,
[00:00:59] "Holy fuck, I'm alive." The Overton window does not open
[00:01:03] itself. It opens one nudge at a time by people risking a little.
[00:01:09] A little reputation, a little pushback, a little criticism, or maybe sometimes a
[00:01:13] lot of reputation or a lot of criticism or a lot of pushback. Creating
[00:01:17] life with another human that you love
[00:01:21] is literally the peak experience of being on the planet.
[00:01:28] - The following is a conversation with David Heinemeier Hansson, also
[00:01:32] known as DHH, creator of Ruby on Rails, CTO of 37signals, creator of the new Omarchy
[00:01:40] Linux operating system, best-selling author, race car driver,
[00:01:44] and one of the most outspoken and prolific programmers
[00:01:48] in the world. For the past 20-plus years, for him,
[00:01:51] programming meant meticulously handcrafting beautiful Ruby
[00:01:55] code. But recently, since late 2025, DHH has embraced the AI revolution and has
[00:02:03] openly transformed himself into, once again, one of the
[00:02:07] most outspoken and prolific agentic engineers, even
[00:02:11] though he hates that term. So let's say
[00:02:15] practitioners of whatever programming is becoming where AI is
[00:02:19] doing most of the actual programming and the human steers the ship
[00:02:23] with high-level design, vision, and taste. Yes, it's
[00:02:27] true. DHH is at times controversial, but he's
[00:02:31] always fearless, brilliant, and fun to talk to. This was,
[00:02:35] once again, an intense, eye-opening, and wild
[00:02:38] rollercoaster ride of a conversation. This is a Lex Fridman
[00:02:42] podcast. To support it, please check out our sponsors in the description
[00:02:46] where you can also find links to contact me, ask questions, give
[00:02:50] feedback, and so on. And now, dear friends, here's DHH.
[00:02:56] 13 months ago, we sat down right here to talk about programming,
[00:03:00] and then everything changed. At that time, you were
[00:03:04] a bit skeptical about the role of AI in the process of
[00:03:08] programming, and then we went through this rapid evolution
[00:03:12] of agentic engineering. So, simple question to start: How has your view on AI's
[00:03:20] role in programming changed? Are you excited? Are you terrified? Are you
[00:03:24] on an emotional rollercoaster ride?
[00:03:26] - I am incredibly excited.
[00:03:29] - You've been talking about fun a lot.
[00:03:31] - There is none of the existential threat. That doesn't exist for me as an emotional
[00:03:38] component. It is only there as an intellectual component, and the
[00:03:41] emotional component for me is 100% pure, unadulterated joy-
[00:03:47] ... and optimism and amazement that we've made
[00:03:51] computers do this. And I find it so interesting that we talked
[00:03:55] just 13 months ago because
[00:03:59] it's like we talked in different universes, different eras.
[00:04:03] I love this quote. I think it's Lenin. There are
[00:04:06] decades where nothing happens and weeks where decades happen.
[00:04:11] And we have seen decades of progress happen in the last nine months.
[00:04:18] I mean, imagine you're there when the Wright brothers take flight.
[00:04:21] Yesterday, the New York Times would write, "It's gonna be 10,000 years before we fly,"
[00:04:26] and then the day after, we're up in the skies, and just a
[00:04:30] few years after that, there were cross-Atlantic planes. The
[00:04:33] whole world has completely changed. What a blessing to be
[00:04:37] there in that moment. If you zoom out and look at all of human history, how many
[00:04:41] humans got to live within the same epoch that they were born in? They never saw that
[00:04:49] complete change of the world and of society. And to have
[00:04:55] been blessed with two of those
[00:04:58] feels just such a privilege. I got to see the internet-
[00:05:02] ... from pre-internet to post-internet, and then now pre-AI, post-AI.
[00:05:09] What an amazing run. How fortunate.
[00:05:12] - Yeah, but the thing is, this feels like a thing that
[00:05:16] happened faster than anything else in human history.
[00:05:18] - Correct.
[00:05:18] - So I would say somewhere around December, maybe late November-
[00:05:22] - November 24.
[00:05:24] - This is...
[00:05:26] - That's the exact moment.
[00:05:26] - You know, when they talk about when one nation invades another in a world
[00:05:30] war or something like this, it-- this is how we talk about AI changing everything.
[00:05:34] Yeah, the... And it really just sh- shifted for many
[00:05:38] great developers. It shifted to where AI is doing some,
[00:05:43] basic autocomplete, maybe writing 5, 10, 15, 20% of code to writing 80% of code.
[00:05:49] - Or 100.
[00:05:50] - Or 100, yeah, especially if it's not a public-facing product.
[00:05:54] - To me, that's why even when I look
[00:05:58] back upon our conversation a year ago, I don't actually have different
[00:06:02] opinions. I have the same opinions. A year ago, I did
[00:06:06] not like the mode of AI we were offered. It was the autocomplete mode,
[00:06:10] or it was the AI chatbot mode. Now, the chatbot
[00:06:14] I actually liked, as we talked about. Great tutor right from the get-go, great
[00:06:18] way of looking things up on the internet,
[00:06:21] not what was gonna replace me chiseling code. But- ... then we get the agents.
[00:06:28] And the agents start out being curiosities
[00:06:32] for about five minutes, and then they get amazing, and then they get,
[00:06:38] "Oh my God, is this AGI?" And all of that happened since last year,
[00:06:45] even just within the last nine months. We have
[00:06:48] basically these few phases here. We have AI in the
[00:06:53] pre-agentic era. I was excited about that, but it
[00:06:56] was not fundamentally rewriting the rules of the game for me. It was
[00:07:01] not completely changing how I worked. I was still chiseling
[00:07:04] code, I just had a little helper, a little sidekick-
[00:07:08] ... who could bounce ideas off, and I could look up this
[00:07:13] information online and so forth in a more efficient way. It was just a more efficient way to do what I was
[00:07:17] already doing, and it didn't change the emotional connection I had to the
[00:07:21] computer. Then we get to November 24th, 2025. Opus 4.5, to
[00:07:29] me, was the dividing line, where suddenly... I didn't even
[00:07:33] try it on the 24th. I think I tried it on the 26th. I give it a couple of tasks,
[00:07:40] and I realize that the quality of the output is uncannily close to
[00:07:47] what I would've written. And I remember just leaning back and thinking,
[00:07:54] "What just happened?" "How did we go from this autocomplete mess that
[00:07:59] I was talking to you about in the summer to this just a
[00:08:03] few short months later? How did we get both the increase in
[00:08:06] intelligence and then also the increase in
[00:08:10] usability?" This agent harness question where
[00:08:15] I don't know if Opus 4.5 was that much smarter than Opus 4, which
[00:08:19] is what we had in the summer, but its ability to
[00:08:23] instrument your computer, to use tools, to check its own work,
[00:08:27] to apply its intelligence in such a way that you could
[00:08:31] get real meaningful work out of it, was completely different. And I think this is
[00:08:38] then the big change that happens for almost anyone who paid attention and started playing with
[00:08:41] it over the Christmas break. This is what I heard-
[00:08:44] ... from Shopify and other places with lots of employees who
[00:08:49] suddenly had a breather, suddenly had a couple of weeks to lean back and just look at what
[00:08:53] was going on, gave it a try, and had the same
[00:08:58] mind-blowing experience that these agents were of
[00:09:01] a different genre than what we had before. And then what we get to is,
[00:09:08] I'm already excited at this point. Like, by December, I'm
[00:09:12] already revisiting sort of all my priors-
[00:09:15] ... and going like, "Wow, if it can do this, can it also do that?"
[00:09:18] "Oh, yeah, it can." And again, Opus 4.5 now looks like a retarded model.
[00:09:26] And this is the magic of this progress, is you think you've reached something...
[00:09:32] I remember thinking at the moment,
[00:09:35] "If this is the last model we get, I'll be set. I'll be happy."
[00:09:39] I could live with Opus 4.5 for the next 20 years-
[00:09:42] ... and you would hear no complaints from me because it was just so incredibly
[00:09:48] amazing to see an agent do all this work in the way that I wanted it
[00:09:52] done. Because it was not just about it being able to solve a
[00:09:55] task, it was also that I could look at its
[00:09:59] path there and go, "Yep. Yep. Maybe not there,
[00:10:03] but almost," and it would give you two notes. You'll get to where I wanted
[00:10:07] to go in the way I wanted to go there. You could produce code I
[00:10:11] wanted to merge. You could produce code that actually looked
[00:10:15] beautiful if it was written in Ruby. Rust, different question. But
[00:10:21] this ability for the agents to truly become an extension of how I wanted to
[00:10:28] work was very novel. But then we wait just until early spring, and
[00:10:35] suddenly we get sub-agents. We get harnesses that
[00:10:39] can subdivide the task, and something that would take
[00:10:43] Opus quite a while suddenly took a fifth of
[00:10:47] the time, a tenth of the time, because it could get chopped up and
[00:10:50] suddenly you got eight sub-agents working for you.
[00:10:54] But both of those two first phases of the agentic age,
[00:10:59] to me, still felt like I had to drive. I could tell it what
[00:11:03] I wanted, where to look for it, and steer it a little bit
[00:11:07] when it went off, and then we'll get there, and I would go much faster.
[00:11:11] But I had to be in the driver's seat. I had to tell it what I wanted, and I
[00:11:15] had to be the reviewer, the auditor of what was coming out. And then
[00:11:21] finally now, this summer, with Opus 5, Fable, and Sol, GPT Sol, and
[00:11:29] to a lesser extent, some of the open weight models, we've
[00:11:33] arrived at a new era where I'm not telling it where we're
[00:11:37] going. I'm telling it the problem I have. I'm telling it the fuzzy,
[00:11:41] vague idea I have. It tells me where we're going.
[00:11:47] It tells me which path to take, and I will still look at it
[00:11:50] because I'm a curious person and I like computers and I like the outcome of it,
[00:11:55] but I really kinda don't have to. I've become optional in the part that
[00:12:01] produces the code that picks the route. Remember when early GPS systems came out?
[00:12:09] They were amazing compared to looking at a map, but you still wanted to pay
[00:12:12] attention. Is it gonna drive you in the harbor? I remember these newspaper
[00:12:16] articles. "Ah, GPS, they're terrible because people don't pay attention, they drive in the
[00:12:20] harbor." When was the last time GPS drove anyone in the harbor? Like, that just doesn't happen
[00:12:24] anymore. In fact, the cars now just drive themselves, right? And this is where
[00:12:28] we've arrived at now, that I can trust.
[00:12:33] For the domain I'm working in right now, I can trust it,
[00:12:36] and feel completely confident that it's gonna have my
[00:12:40] back. It's not gonna do something stupid, and if it does something stupid, it's gonna be
[00:12:44] able to recover.
[00:12:45] - Mm-hmm. We should mention that there's all kinds of domains that-
[00:12:48] - Correct
[00:12:48] - ... programmers operate in. There's...
[00:12:51] I actually don't know, but I think the most common
[00:12:55] domain in development is, like, web dev CRUD. You have a database.
[00:13:00] You have a user-facing interface, and it does something back and forth,
[00:13:04] and it could be internal to just one person, to multiple people,
[00:13:08] to a small number of people, or to the world. And I think for that,
[00:13:13] it's-- I mean, you could really get to the 100% of
[00:13:17] code written by AI and really if you're a good
[00:13:21] programmer and you have a good intuition about what's happening behind the scenes,
[00:13:25] you can legitimately not look at the code, at least that's, that's
[00:13:29] been my experience. I don't know how much,
[00:13:33] prior experience with programming you need to have to kinda
[00:13:36] know that things are working correctly behind the scenes, like intuitively
[00:13:40] by observing the ripple effects, the symptoms of the system. But I
[00:13:46] think for that domain, it's close to 100%, and then there's domains like you're
[00:13:52] also operating in, which is writing a Linux distribution. There, maybe there's
[00:13:56] more because you're obsessed with speed and all that kind of
[00:14:00] stuff. There, maybe you need to look at the code a little bit more. Then there's maybe safety
[00:14:04] critical systems all the way down to operating a nuclear power
[00:14:08] plant or a self-driving car. Maybe you need to look at the code more carefully.
[00:14:12] - Yes, but that said, AI is insanely capable at both finding- ... and fixing
[00:14:19] security vulnerabilities. This was the whole blowup about Fable. This model was
[00:14:23] so capable of finding holes that a
[00:14:27] an attacker could exploit that it was simply not safe to release.
[00:14:30] So the irony here is that when you look at that field, it
[00:14:34] seems like we've reached levels of intelligence that
[00:14:39] virtually no human can match because
[00:14:43] many of these security holes are about stringing combo moves together.
[00:14:47] You find one little
[00:14:49] vulnerability here that by itself might not be the worst thing in the world, but then you
[00:14:53] combine it with four others, and suddenly you have RCE, remote command execution.
[00:15:00] Humans who are able to do that are very rare. They
[00:15:04] usually work inside state-sponsored organizations or other clandestine operations.
[00:15:11] They're not just out and about finding things.
[00:15:14] So they've gotten so good at that. The Linux distribution
[00:15:18] is why I've gotten 100% AI pilled. Because I've been working on Omarchy for the last
[00:15:26] three months, this version that just dropped a few days ago called Quatro.
[00:15:31] And almost right from the beginning I'm working on that version,
[00:15:35] the agent acceleration neared 100%, and in the last
[00:15:39] two months it has been 100%. I have not written-
[00:15:42] - Really?
[00:15:43] - ... any of the code that's shipped in Quatro by hand. I've reviewed the shape
[00:15:51] of all of it.
[00:15:52] I've reviewed the individual lines of anything that's critical in the model
[00:15:56] layer of the system, and I've not looked at a bunch of the UI code.
[00:16:02] I have not looked at a bunch of the auxiliary code, and
[00:16:06] I've not written any of the new functionality entirely by hand. But then
[00:16:13] the web part, actually evolving Basecamp and Hey, our
[00:16:17] professional products that have lots of users and are relatively large code
[00:16:21] bases, have proven surprisingly tricky
[00:16:25] to fully accelerate with agents. We just released
[00:16:29] Basecamp 5 not too long ago. That was the first
[00:16:32] product at 37signals that was really agent accelerated.
[00:16:36] Because we were in this final sprint phase from around
[00:16:40] February. By then, agents were already good.
[00:16:44] And we had this early surge of, "It's solved. We can just have the
[00:16:49] designers do the programming. They know what features they want. They know what shape
[00:16:53] they want it to take. Let's just-- Let them vibe." And we let them vibe.
[00:16:59] And we ended up with a lot of PRs that individually perhaps could have been
[00:17:05] justified for a hot moment, taken all together,
[00:17:09] destroyed the architecture of the system.
[00:17:10] And we actually had to clean up manually, mop it up by
[00:17:14] hand, by human hand, to get back to an architecture that
[00:17:17] felt cohesive and coherent. So we still
[00:17:21] have a bit of that-- that was February, by the way. Things are quite different now.
[00:17:25] - Well, hold on a second. What's the lesson from that? Is one of the lessons from that that you have to be
[00:17:29] a programmer at this stage to be able to vibe code?
[00:17:33] - To be able to vibe code on existing substantial
[00:17:38] - I see.
[00:17:38] - ... code bases, even if they're crud, if you wanna
[00:17:41] retain the element of architecture that got that system to where it was.
[00:17:45] Now, that's also a point where I've stressed many
[00:17:49] times that when people accuse vibe coders of
[00:17:53] being slob generators, I go right back at them and say, "Have you
[00:17:57] looked at the average programmer's output?" That is some
[00:18:01] other slob too. If you've looked at behind the scenes of many
[00:18:05] great companies and what their code bases look like after there's
[00:18:08] been 3,000 humans through them, they're awful. Absolutely awful.
[00:18:14] - Can you tell me the intuition you have?
[00:18:17] I seem to just, stepping back and observing the different apps that we all rely
[00:18:21] on, I don't know, Adobe Photoshop, all this kind of stuff. There seems to be the
[00:18:24] progress on development there has not accelerated.
[00:18:29] So why is it, what lessons can you draw from Basecamp, like
[00:18:32] well-established, huge user base?
[00:18:35] Why aren't we seeing, like, super rapid increase in, like,
[00:18:39] new updates, features, all this kind of stuff in these well-established apps?
[00:18:44] - Multiple reasons. I'll start with the first one that's the most critical. As
[00:18:48] soon as you're having human teams work together on
[00:18:51] something, the bottleneck is rarely
[00:18:55] implementation. It's human bandwidth and communication.
[00:18:59] When you have a product manager and a couple of designers and a VP above them and a
[00:19:06] CTO above them, and everyone wants to be part
[00:19:10] of the shaping process because we're all justifying why we're here,
[00:19:14] that's where all the productivity goes to die. The revelation I've had working on
[00:19:22] Omarchy the last three months is that to get that magical 10X,
[00:19:30] 100X, in a few rare cases, 1000X productivity boost, you have
[00:19:37] to interact with the agents directly, and you cannot intermediate that
[00:19:44] bandwidth with another human because it's simply too slow.
[00:19:49] And on the one hand, that's a bit of a bummer. I mean, I like
[00:19:53] humans, and it's great to work together. But it also means we need to temper
[00:19:57] our expectations with what these agents can do if
[00:20:01] it's humans driving it, and you have three layers of approval and all the
[00:20:05] other machinery of a large corporation. The implementation part is only a small
[00:20:13] segment of it. The other thing I'd say is that most organizations don't know what
[00:20:20] they want. They don't know how to make it better. They're not
[00:20:24] bottlenecked on implementation. They're bottlenecked on
[00:20:28] ideas. They're bottlenecked on vision. They're bottlenecked on
[00:20:32] taste. And if you don't have those element
[00:20:36] in excess of your implementational capacity,
[00:20:40] it doesn't help. So you can make a lot of shitty ideas come true, then what?
[00:20:44] Are you gonna ship that?
[00:20:46] That sounds like, I don't know, something coming out of Microsoft. That's not what we're trying to
[00:20:50] replicate here. That process is not actually... Because we already had
[00:20:54] this. If you step back for a moment and think of
[00:20:58] the towering organizations we have who have had tens of
[00:21:03] thousands of programmers at their disposal.
[00:21:06] I mean, I'm picking on Microsoft here. I love Microsoft some of the time, but I'll pick on
[00:21:10] them in this case because they have had endless resources, endless
[00:21:14] programming capacity for decades, right? This is what's
[00:21:20] showing us that just being able to write a lot of code does not
[00:21:23] produce great compelling software. Now, the other thing is
[00:21:29] we've had this capacity for about six months. That's not very long in human
[00:21:37] life cycle capacity of internalizing what's going on.
[00:21:40] And I think it's actually funny that the critique of AI is,
[00:21:45] why isn't it going faster?
[00:21:47] What are you talking about? We've not had any other form of progress that has moved as fast
[00:21:51] as AI, and you're impatient because in the last three months we haven't
[00:21:54] rewritten the whole world and made it a utopia of software goodness?
[00:21:59] - You're basically saying everybody should be switching to Linux now. One of the arguments is,
[00:22:03] like, we can rewrite all the software that's not available in Linux in Linux.
[00:22:06] Linux has been the love of my life for many years, but one of the reasons I'm still attached to Windows and
[00:22:10] now, uh, Mac is because of video editing, Premiere.
[00:22:15] - We're gonna fix that. But-
[00:22:17] - So the question is, who's gonna build Premiere
[00:22:20] and Photoshop for Linux? And it feels like one person can now.
[00:22:27] - 100% one person can.
[00:22:28] - And so, and I'm allowed to be impatient. In fact, me or anyone else,
[00:22:35] impatience is the first step of doing it yourself, right? Like-
[00:22:40] - Correct.
[00:22:40] - ... and there's a community of tens of thousands of people that use Adobe
[00:22:44] Premiere or DaVinci, all these non-linear video editors, that
[00:22:48] know the frustrations. Everybody shares them. You can look at Reddit. You can look at
[00:22:52] the forums. Everybody knows it. Uh, I don't know what it is. It may be the
[00:22:55] management. It may be the meetings. All the things you've always discussed is the,
[00:23:00] The bureaucracy that's inside companies that's slowing
[00:23:04] everything down in the development of features. But it feels like
[00:23:08] there-- if you just let some of the developers loose with a bunch of agents,
[00:23:12] you can fix all that. But again, based on everything you're saying,
[00:23:16] maybe the way to do that is to start over from scratch, maybe through open
[00:23:21] source, or somebody launches a new company that within
[00:23:25] large companies now it's hard to,
[00:23:29] to really accelerate into the agentic era by letting developers just build.
[00:23:33] - This is the classic innovator's dilemma. These companies have gotten so good,
[00:23:39] so established at the old way, and therefore their entire
[00:23:43] structure, management layers, processes are tuned for a time that no longer exists.
[00:23:52] But you can't pivot that. These are super tankers. It
[00:23:57] just doesn't happen. This is why
[00:24:00] we're finally getting this upset in the technology industry.
[00:24:04] For a while, I was very upset about the duopoly
[00:24:08] between Apple and Google on mobile, because it felt like mobile was the most
[00:24:12] important computing platform that we had, and I could not see
[00:24:16] a path to unseat either Google or Apple
[00:24:20] sitting on top of that, controlling everything, taking their toll booth money.
[00:24:26] But the game has changed. This is no longer the most important
[00:24:30] platform. Mobile phones are important, but there's also a lot of
[00:24:34] other form factors coming, whether it's glasses or it's
[00:24:38] earpieces or whatever else have you.
[00:24:41] It's all in play now, but the computing platforms
[00:24:44] themselves are in play for the first time in
[00:24:48] probably 40 years, if you look at the desktop. Linux has been around since '91.
[00:24:54] It's not taken off or taken over on the desktop. It's taken
[00:24:58] over everything else. All the devices you have on your desk, your
[00:25:02] fridge, your toaster, everything runs Linux,
[00:25:05] except for your computer. Now, funnily enough, your Android is actually Linux, but
[00:25:12] wrapped so sufficiently that you can't really recognize
[00:25:15] it. But now there's an opening, and the opening
[00:25:19] is exactly as you say it. If there's a piece of software you
[00:25:23] depended on that bound you to Windows, it is completely within reach for
[00:25:30] you personally to start rewriting it. And maybe you won't get to
[00:25:34] 100% coverage, but this is the old joke about Microsoft Office.
[00:25:38] "I only use 5%." Yeah, well, we all use a different 5%.
[00:25:42] Well, what if we all just build our own 5%?
[00:25:45] What if I just took the functionality that I need and just did
[00:25:49] that? That is a completely different challenge and
[00:25:53] one agents are incredibly capable of doing right now,
[00:25:57] today, and I've done it a lot of times over. So one of the
[00:26:01] amazing things I've found with the latest agent engaged is I have
[00:26:04] become a polyglot programmer, something I was absolutely not before. I was a Ruby
[00:26:13] programmer-- ... first and foremost, and then I dabbled a little bit in Bash--
[00:26:17] ... when I had to. And in the last two months, I've
[00:26:20] written C++. I've written three applications that have
[00:26:24] shipped in Omarchy Quattro. I wrote a
[00:26:29] writing app. I was using this app called Typora, which is a very nice app-
[00:26:32] - Great, great app
[00:26:33] - ... which in itself is based on another app called iA Writer, which was my real
[00:26:37] love on the Mac- ... for a clean, simple Markdown
[00:26:42] writing environment. That's where I write all my essays.
[00:26:45] And then I moved to Linux, and I couldn't get iA Writer,
[00:26:48] so I moved over to this other tool called Typora. It was a piece of
[00:26:51] shareware, and it had a lot of features I just didn't need. And about
[00:26:58] six weeks, seven weeks ago, I thought, "Do you know what? I only need 5% of Typora,"
[00:27:02] which is already a basic app.
[00:27:04] I literally told the agent to get going, that I wanted it written in
[00:27:07] C++ and Qt, because that would fit well with the
[00:27:11] aesthetic of what I was building with Quattro.
[00:27:14] And in, I think, about 20 minutes, it had the first version. I
[00:27:18] started using it, and it wasn't quite right. Within two days,
[00:27:22] I'd given up Typora, and I wrote and have written
[00:27:26] all of my essays since that moment in Omawrite.
[00:27:30] - Can I ask for your advice and your vision about something? So what I find
[00:27:34] with agents, you can actually write something like a replacement for
[00:27:37] Typora that is perfectly customized to you, to your needs-
[00:27:42] - Correct with just one user in mind. And then there's a version of that that is-
[00:27:50] starts with one user in mind but expands to a larger audience. So I've actually
[00:27:53] written a large number of software just for me, and I find it
[00:27:58] easier to do and better to get my situation done. For
[00:28:01] example, I have a video editor I've written, which is very easy to do just for me.
[00:28:06] - I've never, unlike you, built something that's used by a large number of
[00:28:10] people, and I find that a bit scary and intimidating. So,
[00:28:14] like, at this, with this agentic age, how do you take a step
[00:28:18] to actually build something that solves your problem, which I think is a
[00:28:22] beautiful way to build,
[00:28:24] but also expand it to actually useful for other people? Like, is there
[00:28:28] advice you can give, and do you also see the problem of how
[00:28:32] easy it is to just build a tool for yourself?
[00:28:35] - Yes, but it is simpler than you think. By the time you're done
[00:28:39] building the tool for yourself, you simply tell your agent to put it on GitHub.
[00:28:43] You don't even have to do anything else. It will figure out how to put that repo on
[00:28:47] GitHub. It'll write a nice README. It'll start using GitHub releases so
[00:28:51] that you can track things. It'll actually be a better software
[00:28:55] maintainer than you could ever be-
[00:28:57] ... because it is far more patient, it is far more diligent in
[00:29:00] doing the drudgery of managing open source software than you are.
[00:29:05] And you can simply get on with the joy
[00:29:09] of using the software that you built and evolving it as you see fit. Now,
[00:29:13] this gets into the big argument we've been having in open source for a while. Is
[00:29:18] AI contributions good or bad for the maintainer?
[00:29:23] There's a lot of maintainers right now who are quite
[00:29:26] upset about the fact that they're suddenly
[00:29:30] getting a huge influx of pull requests, of
[00:29:34] contributions from people who may not be the best programmers or programmers at all-
[00:29:41] ... towards their software. I look at that argument and go, "Are you kidding me?"
[00:29:47] Here is a vein of free contributions that you can take or don't take,
[00:29:57] but you're complaining about the fact that they're there? It sounds straight
[00:30:01] out of- My steak is too juicy and my lobster too
[00:30:04] buttery. What are you complaining about?
[00:30:07] This is the most amazing thing. This is what we proclamated for so
[00:30:11] long was going to be the magic of open source, that we could
[00:30:15] all contribute to it, but it was, of course, never true. There was only a small
[00:30:19] subset of people who contribute to open source, and that was the very highly skilled
[00:30:22] wizards. So this is a bit of a reformation moment. We had this
[00:30:26] disintermediation between us and the computer, and it was this
[00:30:31] class of clerics and priests called programmers,
[00:30:35] and suddenly they're being disintermediated here by was
[00:30:39] it the 95 theses by Luther in 1500s,
[00:30:43] nailing them to the door? And one of those was very clearly about
[00:30:47] the intermediation, that you should have direct access to the higher intelligence.
[00:30:51] - Mm-hmm. But don't you need the wizards to keep a high bar of excellence in the code
[00:30:55] base?
[00:30:56] - 100% you do, which is also something that's always been true about open
[00:31:00] source, which is the second argument that really grinds me. I've been
[00:31:03] running open source projects for 25 years. I have literally looked
[00:31:07] at the output of thousands, if not tens of thousands of
[00:31:11] programmers. I feel like I have the statistical basis to
[00:31:15] assert that most programmers, they suck.
[00:31:21] And I don't mean that in the way it sounds.
[00:31:24] That was why I paused for a hot second here. I mean, they suck in the sense
[00:31:28] that they don't write the code I want to have written. They don't
[00:31:32] prepare their bug reports with all the relevant
[00:31:35] information. They don't detail their pull requests with the
[00:31:39] why. They don't bother to fill in
[00:31:42] needed code comments. They don't double-check their work. They don't
[00:31:46] write unit tests. They don't do all of these things it takes to create
[00:31:50] good software. But do you know who'll do all that stuff? Agents,
[00:31:54] if you tell them to. They're very diligent at following your instructions,
[00:31:58] most of the time, sometimes to a fault. But it actually means that if you take
[00:32:02] the median programmer and their pull requests towards
[00:32:06] an average open source project,
[00:32:09] they're already getting outclassed by agents. I would
[00:32:12] rather get an agent-written pull request to one of my
[00:32:16] projects than I'd get one written by a human, and it's not just
[00:32:20] because the quality's better. It's also because
[00:32:24] I feel a lot less bad if I just reject it. You didn't even
[00:32:28] write it, so I can simply look at what your agent wrote on your behalf and
[00:32:31] go, "Eh, don't want it."
[00:32:36] That's always been true in open source, and in fact, I think this is one of the problems with
[00:32:40] open source maintainers. They have way too much ball of neuroticism and anxiety that
[00:32:48] requires them to look upon any contribution as an obligation on their part to do
[00:32:56] everything to get that to land in the code base. That's not
[00:33:00] true at all. You can simply say, "No," or even better, you can say, "No, thank you."
[00:33:05] And if you get into the mode of realizing that your project
[00:33:10] is allowed to exist and evolve according to your
[00:33:13] vision, according to your roadmap, it becomes so much
[00:33:17] easier in the agentic age to decline the contributions you don't
[00:33:21] want because you don't even inconvenience or hurt
[00:33:25] the feelings of a human. It's just a clanker, and the clanker won't
[00:33:29] mind. In fact, the producers of clankers, the
[00:33:33] labs, love when you spend tokens in vain. They get paid just the same.
[00:33:39] So, in my opinion, this is the absolute best
[00:33:42] time to ever have been an open source software maintainer.
[00:33:46] Not only do we get this wealth of glorious pull requests made by
[00:33:53] agents with all the boxes ticked, we also get to tap into a
[00:33:57] creativity of people who did not have access to contribute to a project before.
[00:34:02] I've been running the Omarchy project now for a little over a year,
[00:34:07] and in the last three months working on Quattro, I have merged over 1,000 pull
[00:34:11] requests. Quite a lot of those pull requests were written by people who were
[00:34:16] not classical programmers, or were programmers in other domains, not
[00:34:21] Linux operating system or distribution development.
[00:34:25] They were able to contribute their good ideas because of agents, and I got
[00:34:29] to cherry-pick the very best of that- ... because it was there. Otherwise, those
[00:34:36] ideas would just have lived inside their heads. Again,
[00:34:40] Is- that is not the purpose of open source, that we tap into the collective
[00:34:43] intelligence and creativity of the whole goddamn planet,
[00:34:48] and we channel that towards a commons
[00:34:51] where we all benefit from the combined efforts of everyone.
[00:34:56] Now, there's currently, I think, about 400 unmerged pull requests on Omarchy,
[00:35:01] about double what it was a week ago. So the acceleration is
[00:35:05] real, but so are the tools.
[00:35:08] I'm not reviewing every pull request anymore. I haven't been reviewing them for
[00:35:12] quite some time now. I have the agents- ... review them for me-
[00:35:17] ... and then they will give me a summary about whether something is ready for the
[00:35:20] decision, the human decision. Should we merge or should we not merge?
[00:35:25] I don't need to look at all the pull requests that are either wrong, duplicated,
[00:35:30] bad. An agent can sort that chaff away from me. I just get to look at the pearls-
[00:35:36] ... the good ideas that are ready to go, the bug
[00:35:39] fixes that the agent has validated in a VM on my behalf.
[00:35:44] All the drudgery of replicating and managing open source
[00:35:47] projects is evaporating at lightning speed, and we are left with the,
[00:35:55] with the golden juicy parts, the bone marrow of software development-
[00:35:59] ... deciding what should this thing do and where should it go.
[00:36:03] - Do you think the good ideas, ultimately the kernel of the good ideas
[00:36:06] originated in the human mind, so the individual contributors
[00:36:11] Like, can it be done by agents, or is the PR ultimately requires a human idea?
[00:36:18] Like how to improve Omarchy,
[00:36:21] all those incoming... Or can it all just be a pool of agents?
[00:36:24] - That was the mode and the way I was thinking about agents
[00:36:28] in the first agentic age from November 24 to February 28.
[00:36:35] I thought all the ideas would originate with the humans. They would tell
[00:36:39] their agents what to build, and off they went.
[00:36:43] I don't think that's true anymore at all. I have seen things you people wouldn't
[00:36:47] believe, ideas coming out of models so great that it makes me humble-
[00:36:54] ... as a person who otherwise prides himself on having good ideas.
[00:36:59] The agents are incredibly capable of creative thought,
[00:37:04] and folks who are still stuck in the analysis that agents are parrots-
[00:37:11] ... just regurgitating the ideas that are
[00:37:15] already there are delusional about the progress that's been made in
[00:37:19] the last six to nine months.
[00:37:21] - So some people listening to you right now will say DHH is suffering from the old case
[00:37:25] of AI psychosis. Can you steel man the case that you are in fact experiencing in
[00:37:33] a state of delusion, like One Flew Over the Cuckoo's Nest, and can you argue against it?
[00:37:37] - I'm in a state of delirium. That's what the state I'm in.
[00:37:41] Because I have been working with computers for 40 years,
[00:37:47] and I've never seen the things that I've seen in just the last two months.
[00:37:54] A whole career, a whole life dedicating to the love of computers as my main
[00:38:02] focus for the working hours and then some,
[00:38:05] suddenly completely upended, suddenly completely rewritten. Of course I'm delirious.
[00:38:11] Who looking at this reality is not? If you are not delirious or at the very least
[00:38:19] very excited... Actually, I guess that's not even true. If you're not recognizing
[00:38:23] the gravity of the moment, that's the delusion. That's the
[00:38:28] psychosis. The psychosis is believing that the world is barely different. We
[00:38:32] just have some electronic parrots reciting things to us. Now, in my opinion, the
[00:38:39] reason this argument is actually brought up is because people are not able to see
[00:38:43] the fruits of the progress. That goes to your point earlier.
[00:38:47] Where is the amazing software? Why isn't American GDP running at 12% year over year?
[00:38:55] First of all, give it a minute. It hasn't even been a year, goddammit.
[00:39:01] But second of all, I feel on my own account, I have actually brought the pudding.
[00:39:08] Omarchy Quattro launched on Friday. It's been
[00:39:11] downloaded by tens of thousands of people. And they like it. They like it a lot.
[00:39:17] - We should mention that going to Perplexity here, Omarchy is a highly
[00:39:21] opinionated Arch Linux-based desktop distribution centered on the Hyprland
[00:39:25] Wayland tiling compositor. It was created by David
[00:39:28] Heinemeier Hansson, DHH, as a polished
[00:39:32] developer workstation set up with a cohesive visual
[00:39:35] style and many everyday tools already configured.
[00:39:39] - Let me put it. Omarchy is a beautiful, modern, and opinionated Linux system.
[00:39:45] It's an alternative operating system to macOS and Windows,
[00:39:49] and it's freaking amazing.
[00:39:50] - And the Quattro thing is you're pushing towards the age of agents.
[00:39:54] - That's right. That's the latest version that we just dropped out, which is also funny.
[00:39:58] The Omarchy project is only a year old and a
[00:40:02] little bit. I started it last summer in between sessions at the 24 Hours of Le Mans-
[00:40:08] ... where I had watched one too many YouTube videos on
[00:40:12] Linux Rising and got bitten by that bug. Started working
[00:40:16] on this second iteration of my
[00:40:19] attempt at creating a better Linux operating system. The first iteration we talked about
[00:40:23] last time was called Omakub, was built on top of an existing system called
[00:40:27] Ubuntu, and it was fine. But the ambition I was able to pour into the new
[00:40:33] version, Omarchy, because I started seven layers deeper down the
[00:40:37] stack, was completely different, but it was still done in a pre-agentic
[00:40:41] world. I wrote all those batch scripts by hand in the beginning,
[00:40:47] and then I got to see the midway point where things changed over.
[00:40:52] I did a couple of versions of Omarchy that had partial agent
[00:40:56] acceleration, and then three months ago,
[00:40:59] it was full throttle, 100%, everything is written by agents but steered by me.
[00:41:04] And that just ended up being
[00:41:07] a very different experience and a very different operating system
[00:41:11] because I was suddenly granted a limitless ceiling on my ambition.
[00:41:17] I could look at any feature in Windows, on Mac, on other Linux systems and say, "I
[00:41:25] want that," and the agents would deliver. So everything I wanted was suddenly
[00:41:31] within reach, which meant that I got a little delirious.
[00:41:36] Who would not get delirious if suddenly a genie pops out of the bottle
[00:41:40] and says, "You can have whatever you want. Every feature
[00:41:44] you've ever dreamed of in an operating system-
[00:41:47] ... I can deliver them to you, most of them in five minutes, a few in
[00:41:51] 20, and if we really go hog wild, it's gonna take me two hours."
[00:41:54] - Mm-hmm. Have you seen Requiem for a Dream, the movie? So the,
[00:41:58] There's a drug-like effect here.
[00:42:00] I find it personally-- We'll talk about many levels of this, but it is overwhelming
[00:42:07] how much power is placed in our hands so suddenly,
[00:42:11] and it's very hard to know, it's like with "The Hobbit" or something, what to do
[00:42:15] with it, and I find myself truly overwhelmed with the multitasking,
[00:42:20] On the verge of almost burnt out. Super excited about so many things, but ultimately
[00:42:28] looking back, you want to focus on one thing and really ship
[00:42:31] - I don't have that sense. I don't have the sense of overwhelm. I don't have the
[00:42:35] sense of dread. I don't have the sense of distortion because I have a mission.
[00:42:42] I'm going somewhere, and therefore, I can channel all this new power towards-
[00:42:48] - Yeah, it's wonderful
[00:42:48] - ... a singular goal and outcome, creating the perfect
[00:42:51] computer. And therefore, all my investigations with AI are focused towards
[00:42:59] that end. Now, I also have a day job.
[00:43:02] And we also use agents there, and that's also targeted towards sort of
[00:43:06] specific outcomes. But with the Omarchy experience, I got to tap in
[00:43:14] straight in the back of my head and increase
[00:43:18] the bandwidth between ideas arriving in my
[00:43:21] brain and software emerging on the screen. It was like going from dial-up-
[00:43:28] ... to fiber. I think on your podcast, Elon talked about the actual human bandwidth-
[00:43:35] ... that Neuralink and other projects are trying to accelerate.
[00:43:39] Like, the bandwidth we're communicating over right now is quite low because
[00:43:46] we're limited by our cognition. We're limited by the rate of
[00:43:50] speech. You're not limited by those things when you're working with a
[00:43:53] swarm of agents. Now, let me caveat this by saying,
[00:44:00] if I'd heard myself talk like this-
[00:44:03] ... nine months ago, I would probably have used the label AI,
[00:44:07] AI psychosis. I think it would be fitting because
[00:44:11] nine months ago when people were talking like this, they weren't shipping,
[00:44:15] and I think that's the ultimate difference, that there were people who saw this
[00:44:19] early. I was not actually that early. As we've talked about, I
[00:44:22] was rather skeptical, and I was using AI in certain ways, but I was not
[00:44:26] the first person who downloaded Claude Code. I think Boris released that in end of
[00:44:30] February. I don't think I installed Claude Code until
[00:44:34] September. So there was about six months there where pioneers
[00:44:39] saw these glimmers of what the future was gonna look like. It wasn't there
[00:44:43] yet because the intelligence wasn't there. The harnesses weren't there, but they could
[00:44:46] see the glimmers. I couldn't. Tobi, Tobi Lütke, the CEO of
[00:44:50] Shopify and now my partner in crime on this
[00:44:54] Omarchy project in part, he's gotten pilled with Omarchy as well.
[00:44:58] He saw these things very early, and he tried to tell me,
[00:45:03] and I wasn't seeing it. I was not seeing what he was seeing.
[00:45:07] - You were a hater.
[00:45:08] - Yes. I was still on Earth. And he was... He had already boarded the rocket and was
[00:45:15] heading towards space. I remember actually reading his
[00:45:19] memo to the company, the AI memo, and thinking, "Ah, seems a little much."
[00:45:24] Like, you're making a big deal out of something that I cannot yet
[00:45:29] feel is a tangible thing.
[00:45:32] Because where's the output of this? I try using it. It writes code I don't like.
[00:45:36] It wants to interrupt me all the time. Where are you getting this from? Uh,
[00:45:41] so I get it. I totally get it. If you've not seen what
[00:45:47] the current quality of intelligence can produce,
[00:45:51] of course you're gonna look at someone and go like, "They sound a little nutty," because
[00:45:55] all your experience up until this point would tell you that they are nutty. Because
[00:45:59] if you look at the history of computer programming, for the last 40,
[00:46:03] 50 years, people have been promising that
[00:46:07] regular people could write code just by talking. We're gonna have fourth
[00:46:10] generation languages. Lisp was once upon a time
[00:46:14] presented, Smalltalk was presented as these environments that would
[00:46:18] let regular people write their own applications, and none of it came
[00:46:22] true in the sense beyond, like, Microsoft
[00:46:26] Access databases or Excel spreadsheets. That, those are end
[00:46:30] user programming environments, but it's nothing like what we're able to do now.
[00:46:33] And then, I mean, I'm not even talking about end user. I'm talking as me,
[00:46:37] someone who's been programming for 25 years, seeing
[00:46:41] the output and the acceleration and the quality and then shipping it,
[00:46:45] and I think that's what's gonna change the entire conversation
[00:46:49] quite quickly. The few laggards who are still on the fence
[00:46:52] about whether this is actually useful, who are still trapped in a meme
[00:46:56] from early '25 about mechanical parrots,
[00:47:00] they're simply going to be overwhelmed by the evidence that's about to
[00:47:04] flood over them.
[00:47:05] - So I hope to see,
[00:47:08] projects like Omarchy, several of them that, like, really show agent first.
[00:47:15] - It's coming. All of it is coming.
[00:47:17] - In the spaces, in the silly spaces that I already mentioned, like video editing, all
[00:47:21] these kinds of apps that are like Typora-
[00:47:24] - Yes.
[00:47:24] - ... this kind of stuff.
[00:47:26] - It's gonna come, and I've already seen the early inklings of this.
[00:47:30] One of the really neat features about Omarchy is that it has
[00:47:36] a far more robust plugin system that allows you to extend your
[00:47:40] operating system and rewrite it really in terms of its
[00:47:44] user interface and its panel and its features
[00:47:47] by creating your own plugins that can be cloned off of tools we ship in the box. For
[00:47:55] example, say you want a different calendar. Omarchy ships with a calendar. You
[00:47:58] click the little clock. It pops up a calendar, and it doesn't
[00:48:03] have iCal support, for example. It doesn't consume your appointments.
[00:48:07] There's about 17 implementations of that already, and in
[00:48:11] three days, we had 330 plugins on the Omarchy plugin marketplace. I have
[00:48:18] never seen growth like that with any project
[00:48:22] I've ever been involved in. I've never seen participation that broadly.
[00:48:26] I've never seen that many people be able to create software that's
[00:48:30] meaningful for them- Also be usable for others so quickly. All of
[00:48:36] it is driven by the fact that Omarchy ships a set of
[00:48:40] skills that tells any agent you bring to it how to
[00:48:43] create extensions to the operating system, and
[00:48:47] therefore affording you the vision of the true malleable...
[00:48:53] I was about to say agentic. I hate that fucking word.
[00:48:56] And the reason in part I hate that word is, first of all, it's become marketing
[00:49:00] slob speak- ... at this point. Like, it's just slapped onto everything.
[00:49:04] I wish we had a different word that just meant AI doing stuff.
[00:49:08] - Vibe coding feels wrong, too.
[00:49:09] - It does, because vibe coding to me smells exactly like script
[00:49:13] kiddies did in the early 2000s.
[00:49:15] People applying PHP scripts they just downloaded offline they don't
[00:49:19] understand anything of.
[00:49:21] And while, I mean, that's true in the sense that much of the vibe coding,
[00:49:25] including my own vibe coded projects, and as I just mentioned, I have several.
[00:49:29] I've written things in C++. I've written things in Rust.
[00:49:33] Rust. I hate Rust with a passion. Rust to me
[00:49:39] is like pouring acid in my eyes when I have to look at the code.
[00:49:42] - Wait, wait, wait, wait. Why do, why do you hate Rust?
[00:49:43] - It is, in my opinion, the ugliest programming language- ... that has been invented-
[00:49:47] ... in probably the last 40 years.
[00:49:49] - So it's the opposite of Rails and Ruby.
[00:49:50] - It's the opposite. But-
[00:49:53] - You've written it
[00:49:53] - ... I've written applications in Rust because the output
[00:49:57] of Rust is actually amazing. The memory safety, the fact that it's a system
[00:50:01] language, the fact that it's highly efficient and so forth is
[00:50:05] incredible. So Rust, to me, can both be
[00:50:09] the most repugnant programming language ever devised for
[00:50:13] human consumption and a wonderful platform for agentic engineering.
[00:50:19] These two truths can coexist easily in my head.
[00:50:24] - Do you think that there can be a point at which we can just call agentic engineering
[00:50:28] programming? Can we just change what programming
[00:50:31] means? 'Cause who's actually going to be programming the old-school way
[00:50:35] in a few months?
[00:50:36] - I don't think we should reuse the term because for me, programming
[00:50:40] implies an understanding of certain primitives,
[00:50:45] loops, conditions, variables. All the constructs of programming languages
[00:50:52] are what constitutes programming itself, not the creation of programs.
[00:50:55] Because you could say in the pre-agentic era, well, your
[00:50:59] CEO is programming. He's hiring a bunch of programmers, he's telling them what to do, and
[00:51:03] out comes software that he can sell.
[00:51:05] Eh, I don't think most people would call that CEO a programmer, and I don't think we should call
[00:51:09] the vibe coder a programmer either. And vibe
[00:51:13] coding, if we define it here, is you tell an agent to build software for
[00:51:17] you. You do not look at the implementation. That, to me, is what separates vibe
[00:51:20] coding from programming or, let's say, agent-accelerated development.
[00:51:26] - But don't you think, so to push back a little bit,
[00:51:29] don't you think a programmer, old-school programmer, you, doing
[00:51:33] agentic engineering is a different kind of agentic engineering than
[00:51:37] a non-programmer doing agentic engineering? What I mean is, if you know
[00:51:42] what a for loop is, if you know what function programming is, if you know some of the
[00:51:46] basic good principles of software engineering, the way you do
[00:51:50] natural language-based agentic engineering will be different and more
[00:51:53] systematic, and this, the scale and the
[00:51:57] variety of things you can actually build is much bigger than a vibe coder.
[00:52:02] - I'm just gonna extend the pro case here a little bit just for the sake of the argument.
[00:52:05] - Right.
[00:52:07] - I actually think for a while it was to my deficit to know as
[00:52:14] much as I know about programming because I
[00:52:18] was instructing the agents to do things as I
[00:52:22] prescribed them to do, and they were very good at that. And in the
[00:52:25] first agentic moment, let's not call it an era, it was something
[00:52:29] that lasted three months. Moment. In the first agentic moment, that felt
[00:52:35] very productive. I could get more productivity out of telling the agents what to
[00:52:39] do in the way I would've done it, and I used all of my
[00:52:42] experience as a programmer to do just that.
[00:52:47] Then I was a little late on the next moment, and the next moment allowed me, allowed
[00:52:54] anyone, to describe outcomes- ... to describe problems to the agents
[00:53:00] and get better solutions than if you had a programmer prescribe the path.
[00:53:05] - See, okay, so we're having fun arguing here. Well
[00:53:09] so are you suggesting that there's problems for which
[00:53:12] programmers are worse than non-programmers at agentic engineering?
[00:53:16] - 100%. And the reason I say that, let's define it here.
[00:53:20] The reason I say that is there's a lot of programmers who are not
[00:53:24] very good product managers. Software
[00:53:28] is product management. What should it do? Who should it do it
[00:53:32] for? How should it do it? How should it look? What are our priorities? What
[00:53:36] do we start with first? What does version one include? All of those skills
[00:53:42] are not easily or equally distributed across all programmers.
[00:53:46] And in the agentic era where you are letting
[00:53:50] an agent, an AI, do the implementation, these are the skills you
[00:53:54] need. And I happen to sit in both camps, and this is why I love this
[00:53:58] moment. I still get to live a little bit in the old world where I look at the full
[00:54:02] implementation because there are domains and areas where I feel
[00:54:06] that still brings value, and then I also live in the future.
[00:54:10] And as I said, when I created Omawrite, I've not looked at a
[00:54:14] single line of that C++. I actually made it a point to
[00:54:18] myself that I was gonna treat it as an experiment. This is 100% a black box.
[00:54:22] I will treat it as though I was any other user who had
[00:54:26] opinions about how their digital typewriter should work, and
[00:54:29] therefore felt like it was a fair experiment as
[00:54:33] if a writer of any other sort who had
[00:54:36] opinions about how software should be done and how it should work. As you mentioned,
[00:54:40] video editors who know exactly where they don't like what Adobe
[00:54:44] Premiere's doing and how it could be better, but don't have the capacities to
[00:54:48] improve it- ... how that could be.
[00:54:50] - The pushback, though, I think what programmers do well, good programmers do
[00:54:54] well, is systematic design, like think in terms of systems-
[00:54:59] - Correct
[00:54:59] - ... and rigor.
[00:55:00] - Yes.
[00:55:00] - And I think still, and probably for a long time to come,
[00:55:04] even natural language-based control of agentic systems will
[00:55:08] require a certain kind of rigor. Not overly
[00:55:11] structured rigor, but really explain very
[00:55:15] specifically the goals of the system, how to
[00:55:19] do the verification, what kind of security testing. You wanna do all
[00:55:23] those kinds of things. Although then to push back on that, the
[00:55:27] system will... should be smart longer term.
[00:55:28] - I would've said the same thing six months ago.
[00:55:30] - Yeah, so this has changed.
[00:55:30] - And I think the same thing would've been true six months ago. What I have found since,
[00:55:35] especially even just the last few weeks of the
[00:55:39] agentically accelerated development of Mach-E, is that
[00:55:43] more often than not, I have the humility to recognize that the agent knows best.
[00:55:49] - You can legitimately say, "Make sure it's secure."
[00:55:52] - Correct. And it would know more about what that entails. Now, you're laughing-
[00:55:59] - What a crazy world
[00:55:59] - ... but it's true. And in fact-
[00:56:01] - Oh my God
[00:56:02] - ... a good parallel to this is the AGENTS MD/CLAUDE MD files. There was a hot moment
[00:56:09] where it was all the rage about micro- optimizing that. Oh, you tell your agent this-
[00:56:14] ... you tell your agent that, and you ended up with this huge file of instructions
[00:56:18] for your agent. One of the things that Boris, working on
[00:56:23] Claude Code, shared in an interview recently about Opus 5 was
[00:56:27] that the system prompt that they ship for Opus 5, and
[00:56:30] presumably also Fable, shrunk by 80%
[00:56:35] because the agent not only needed far less human
[00:56:38] instruction, it was actually being damaged
[00:56:43] by overly prescriptive humans. And any programmer
[00:56:47] who's had a pointy-haired boss knows exactly what that is like.
[00:56:51] When the boss walks into the room, doesn't know anything,
[00:56:55] starts telling you how to program, how to code. What do you
[00:56:59] do? You sulk. You write shittier code if
[00:57:03] you're mandated to do things that are against your better judgment.
[00:57:06] Why would an agent not be the same?
[00:57:08] - Actually, to push back against myself, I do find the actual skill I'm currently
[00:57:11] developing, which I along those lines is probably what everybody's trying to
[00:57:15] develop, is not to overspecify things, is to get out of the system's way.
[00:57:20] - Of course.
[00:57:20] - Is to specify enough to provide a kinda high-level vision and guidance.
[00:57:25] - It's even better because you don't even need that. The
[00:57:28] fundamental insight of modern software development came from the agile
[00:57:32] software development movement. In the late '90s, early 2000s, a group of
[00:57:38] smart, honest, and brave people came together and said, "The way we've been trying to
[00:57:42] do software development for the last 40 to 50 years has
[00:57:46] not worked, will not work. We've been trying to
[00:57:49] specify upfront what software should look like. We thought
[00:57:53] that we could ask humans what they wanted, write it all
[00:57:57] down, apply our systems thinking and our rigor to a
[00:58:01] spec sheet, hand that spec sheet over to a group of programmers
[00:58:05] who would then implement just that, and everyone would be happy." Well, guess what?
[00:58:09] No one was happy. Because no one knows what they want until they
[00:58:12] receive it. You don't know what a program should do until you
[00:58:16] play with it. So in the agentic age, you should
[00:58:19] resist the temptation to be overly specific upfront. Be as
[00:58:23] vague as you can to manifest something, then interact with the something.
[00:58:29] The way you arrive at good software is you write a little bit of software,
[00:58:33] and then you try to use it. It is in the process of using software that you
[00:58:37] discover what you really want.
[00:58:38] It's where you discover what's important and what's not important. And
[00:58:43] agents are incredible at allowing you to
[00:58:46] bumble into this experience of realizing what you want because
[00:58:50] you don't know what you want.
[00:58:51] - Mm-hmm. And I've actually done something similar to what you suggested, which is
[00:58:55] implement different designs and totally different implementations, and then
[00:59:01] I create HTML pages for myself, PHP pages, where I vote on
[00:59:05] what I like more and so on.
[00:59:06] And it does this iterative thing, and it's very nice and fun. The interaction with
[00:59:10] the agentic system, if you create a nice interface for yourself, it can be super fun,
[00:59:14] and you're focusing on the design part and the most fun parts of the design part.
[00:59:18] - Correct. And this is what humans are really good at.
[00:59:20] - Yeah, taste.
[00:59:21] - Differential evaluation. You give me three
[00:59:24] options, I pick one of them. Now, humans actually fall off a cliff if
[00:59:28] you give them 22 options. That's the paradox of choice. But you give them three options,
[00:59:32] they very quickly within a split second will tell you what they like.
[00:59:36] There are all these ways that exploit the fact that
[00:59:40] humans will make these snap judgments that are actually pre-intellectual,
[00:59:44] right? Like, they're coming from the gut, and then they arrive up in
[00:59:48] the, in the brain, and the brain tries to rationalize why the
[00:59:51] gut said what it said. And if you're
[00:59:57] willing to let go of some of that intellectual pre-processing
[01:00:00] rationalization and simply let your gut drive, the agentic age is a revelation.
[01:00:06] - So this is a fascinating thing to ask you because you have sort of
[01:00:10] famously for a long time talked about, like, detailed chiseling of beautiful
[01:00:17] Rails Ruby code, and now you have switched
[01:00:21] in a matter of months to not doing that. So, like, what is
[01:00:24] your current setup look like? 'Cause you're, I assume, are still
[01:00:28] looking for the beauty, for the chiseling, for the crafting, but you're just
[01:00:32] crafting in a different medium.
[01:00:35] - And at different levels of abstraction. When I'm working in Ruby code, and we have a lot
[01:00:39] of Ruby code because it's in our entire business, and I'm asking agents to make changes
[01:00:43] to that code, I still sweat the details.
[01:00:48] What I'm coming to realize is that the economic payoff
[01:00:54] of that sweat is diminishing rapidly. The reason
[01:00:59] why I, for 25 years, was sweating every line of
[01:01:03] code so judiciously was because I knew the payoff of keeping an architecture
[01:01:10] coherent and malleable was software that could change and evolve-
[01:01:16] quickly with a small team, and not exorbitant cost,
[01:01:20] and not introducing a bunch of bugs when you change one thing over the other. That was
[01:01:25] the driving economic argument for why you should write
[01:01:28] beautiful code, 'cause beautiful code is easier to understand, it is simpler, it
[01:01:32] is more malleable. That was premised on humans doing the modifications.
[01:01:40] I think it is an open question to which degree this still matters. Now,
[01:01:46] it does matter, and the reason I say that, at least for the moment, is that
[01:01:50] tokens are still scarce. At this moment in time, we are all token limited.
[01:01:58] Well, not all, but anyone who doesn't have endless budgets are token
[01:02:02] limited. So therefore, there is great payoff
[01:02:06] to writing systems that agents have an easier time dealing with
[01:02:10] and evolving without having to relearn the entire context. Just like humans,
[01:02:14] if they can make iterations and changes to the code base
[01:02:18] without wrecking the architecture, they can make the next
[01:02:22] change just as cheaply as the last one. And this is the
[01:02:25] classic ball of mud where you end up with a system that's a ball of mud-
[01:02:31] ... because it's just put together in a way where nothing is
[01:02:35] connected and it's just a real mess, right? I've seen that with agents, and I've seen
[01:02:39] it in our own code bases where, again, the first PR is, like,
[01:02:43] mediocre of quality, and then if you add another PR on top of that, and then five more
[01:02:47] down the line, it's not very good, right? So there's still a payoff to that,
[01:02:51] but that payoff is premised on our current moment. I am now able
[01:02:55] to... And this is, by the way, where the AI psychosis really comes in, when you
[01:02:59] try to extrapolate what nine months from now it's gonna look like.
[01:03:02] What two years from now it's gonna look like. But as an intellectual experiment,
[01:03:07] I think the first computer I used was a Commodore 64.
[01:03:10] - Me too. Cool.
[01:03:11] - It had one megahertz CPU and 64K of memory.
[01:03:16] Everyone who wrote software for that machine internalized
[01:03:20] certain constraints. Well, all the constraints. That machine was
[01:03:24] nothing but constraints. If you put that programmer in a
[01:03:27] time machine and teleported him or her to
[01:03:31] 2026 and gave them a modern computer today and
[01:03:35] said, "Now write me a piece of software," they'd be lost for a little bit
[01:03:38] because all their techniques and all their
[01:03:42] heuristics would simply be wrong. Or not wrong, because efficient software
[01:03:46] is still beautiful. They would be out of date with the value that they could create.
[01:03:51] The amount of optimization you have to apply for a one megahertz computer
[01:03:55] to produce a video game is just very different from what you have to apply today.
[01:03:59] - Just imagine that guy that was programming back then on a Commodore. Just re-
[01:04:03] remember all those,
[01:04:05] like what programming felt like and what it meant, highly constrained resources-
[01:04:10] ... how slow everything is.
[01:04:11] - Beautiful in many ways. Beautiful.
[01:04:12] - It's chiseling. But-
[01:04:15] - It-
[01:04:15] - ... imagine that person coming now.
[01:04:17] - It's romantic too, though. Let's also imagine that. This is one of the things, whenever
[01:04:21] we bemoan modern car culture, for example, right? And then we think like,
[01:04:27] "Oh, wasn't it better when we all had the horse-drawn carriages and so on?" No, it wasn't.
[01:04:31] Do you know what New York smelled like when we used horses for transportation?
[01:04:35] It was an open sewer. They just shat everywhere.
[01:04:38] - Yeah, but have you played Red Dead Redemption? You know how cool those cowboys were-
[01:04:42] - That is the way-
[01:04:42] - ... on the horse?
[01:04:43] - ... to experience the nostalgic past, when you don't get the all
[01:04:47] the furry impulses and senses.
[01:04:50] - So basically programming, old school programming by hand is
[01:04:53] kinda like the cowboy culture that we romanticize and make movies about.
[01:04:57] - It's already happening, the romanticization of handwritten code.
[01:05:01] And I have some of it because it was a very romantic
[01:05:05] era. I'm grateful to have been alive for 20 years of
[01:05:12] economically valuable handwritten code. That was a, that was a good time.
[01:05:16] - Where handwritten beautiful code was also valuable.
[01:05:20] - Correct. Because handwritten beautiful code exists
[01:05:24] as much today as it did yesterday. There are people who
[01:05:27] willfully write new video games for the Commodore 64,
[01:05:32] or for the second Mega Drive, or for other vintage consoles. In
[01:05:36] fact, one of my favorite video games of late is
[01:05:40] ModRetro's. Do you know Palmer Luckey's-
[01:05:43] ... side geschäft, which is recreating old consoles. So he's recreated the Game Boy.
[01:05:49] - Nice.
[01:05:51] - It's amazing. Look it up. It's really cool. But what's even
[01:05:55] cooler than the fact that he recreated this hardware and the original
[01:05:58] chunkiness, but brought it up to date with sort of modern
[01:06:02] screens and so on, now they just put out the Nintendo 64 too. Incredible.
[01:06:06] Super cool. Wild attention to detail, input lag, and all the other things.
[01:06:12] But what's also very cool, that one, I have to wave. That one
[01:06:16] right there, and hover over it, 'cause then you get to see what I'm talking about.
[01:06:19] That is the Chromatic- ... Tetris re-implementation.
[01:06:23] - Wow.
[01:06:23] - I played a lot of Tetris on the original Game Boy.
[01:06:26] Probably one of my top three favorite games of all time.
[01:06:30] And they rewrote it with one change. If you hit up, the brick slams.
[01:06:39] And that speeds up the game by about 400%.
[01:06:43] It is an incredible game, and it's a new Game Boy game.
[01:06:47] I think the Game Boy came out in- '89 or '88. It's a very
[01:06:51] old machine. The fact that there's still people writing new old
[01:06:55] games is awesome, and the reason they do it in part, now here
[01:06:59] they're doing it because they want Tetris, but there are people who do it just for the love of the constraints,
[01:07:03] for the love of the romantic notion of writing that. Just
[01:07:07] like there are people still riding around on horses, not to get
[01:07:11] places fast, but because they like the mode of
[01:07:15] transportation where it's a literal biological
[01:07:19] being below you propelling you forward.
[01:07:21] - And also, we should say that that beautiful code is great training
[01:07:25] data. So in some sense, the beauty that we've built over a few decades-
[01:07:30] - Yes
[01:07:30] - ... continues.
[01:07:31] - We gave birth to this moment. What a privilege, and I feel that very
[01:07:39] personally because I... Almost all of the code I've ever written is public
[01:07:42] code. The vast majority of my career has been dedicated to writing open source code,
[01:07:47] and therefore, some of that code, some of those beautiful lines
[01:07:51] are in the training set. And in fact, I've
[01:07:55] heard people do this when they write Ruby code. They ask the agent, "Write
[01:07:59] it like DHH would."
[01:08:01] And they're pleased with the result, and that does warm my heart a little bit, that
[01:08:05] I helped give birth to this moment in my tiny little small part. And anyone else
[01:08:09] who contributed open source code or any code at all that the agents have had access to
[01:08:13] over the last, well, entire time
[01:08:16] programming has been around as a discipline, is now part of
[01:08:20] these new agent overlords.
[01:08:22] - So you don't have a little bit of sadness that writing beautiful
[01:08:26] code by hand is now less and less useful?
[01:08:29] - Am I sad that if I had to get a job tomorrow,
[01:08:33] it's unlikely that I could apply my skills in such a way that I would be
[01:08:36] paid to write these manual lines of code? No.
[01:08:42] I did it for 25 years. Like, I wanna see something new here,
[01:08:45] especially if we're all gonna live forever, which I hope we don't. Maybe we'll get to that.
[01:08:49] But, like, I've done that. That's enough. That's fine. I don't feel any more
[01:08:53] nostalgic about that than I do about the fact that I don't have to
[01:08:57] spend my time in the field with a hoe or at the assembly line.
[01:09:01] - Well, hold on a second. You are one of the best programmers
[01:09:05] in the world at writing handcrafted beautiful code, appreciators
[01:09:09] of beauty with great taste.
[01:09:11] - Correct.
[01:09:11] - That has been replaced.
[01:09:13] - I say humbly.
[01:09:14] - Yeah. That has been replaced. Like, you had now...
[01:09:18] You're just fast evolving, and you're able to... One of your
[01:09:22] really great qualities is you're able to change your mind and evolve very
[01:09:26] quickly. But, like, you had to kill that other person.
[01:09:30] - I am grateful for every moment that brought me to where I am right now, and
[01:09:34] therefore, I have also tried, and maybe this did take some practice. I
[01:09:39] will concede that. Maybe I wasn't always like this, but
[01:09:44] stoic philosophy, amor fati, loving your fate,
[01:09:48] is an incredibly liberating way to live. And
[01:09:53] you could attack that and say, "Well, that's a point of privilege."
[01:09:57] True, but also I had the same directional point
[01:10:01] when I didn't have all this, quote unquote, "privilege."
[01:10:05] So I think there's a way to live and interact with the world
[01:10:09] where you accept the things you can change and the things you cannot change
[01:10:13] and fall in love with all of it.
[01:10:15] Fall in love with the fact that the world today has jumped
[01:10:19] two decades forward into technology industry from where it was last year.
[01:10:24] - So can we talk about the general anxiety that programmers feel,
[01:10:28] going through the same transformation? They've maybe gone to university
[01:10:36] majored in computer science, dreamed of being programmers and building stuff,
[01:10:40] high salary, and now everything's changing, and there's deep
[01:10:44] anxiety about, "What do I do when... with my life?" Can you
[01:10:47] empathize with that, and what the hell are they supposed to do?
[01:10:51] - Hugely. Because just because I have this disposition, I'm
[01:10:55] keenly aware that that's not evenly distributed, that
[01:10:59] not everyone sits with this position and this optimism for the future.
[01:11:03] But I do think I wanna separate things a little bit.
[01:11:08] I think you're gonna have a hard time coping with the new
[01:11:11] reality if the only thing you loved about programming was the mechanical bits of
[01:11:19] putting the right logical constructs together to produce something other people
[01:11:25] told you to produce. Because that mechanical process is under threat.
[01:11:33] If you are, as you just mentioned, excited about building things,
[01:11:38] I don't think you're under threat at all. In fact, I think there's a great argument
[01:11:42] for us needing far more builders than what we have now, and if you look at
[01:11:49] the employment stats, it's fuzzy.
[01:11:53] It's not clear what's gonna happen at all. Some stats actually show an
[01:11:56] increase in openings because
[01:12:00] the advent of AI is so dramatically lowering the price of
[01:12:04] programs that people want a lot more programs. This is the classic,
[01:12:09] the Jevons paradox, that says when the price of something goes down, there's gonna be more
[01:12:13] demand for it. And this is the example of the ATMs too. When the ATM
[01:12:18] originally came, a lot of bank tellers were very
[01:12:22] afraid for their job because suddenly there was a machine that could dispense money from
[01:12:26] people's account. Well, what the ATMs did was lower the
[01:12:30] price of a branch, and suddenly banks could afford to open a lot
[01:12:34] more branches, and we ended up with more bank tellers than we did before. Now, none of this
[01:12:38] is guaranteed. There are also moments where things do change. The
[01:12:42] vast majority of people worked in the fields up until
[01:12:46] the late 1800s, and then suddenly we got mechanized-
[01:12:51] harvesting tools, and we did not need human labor with a hoe and
[01:12:55] an ox out there. We had mechanical tools to do that for us.
[01:13:00] In that moment, are there people who were threatened that their
[01:13:04] job and their livelihood was at stake? Yes. Was that a reasonable thing to
[01:13:08] feel threatened about? Yes. The Luddites smashing the weaving machines-
[01:13:13] ... in England had the same thing. And I think maybe that's the better parallel
[01:13:17] than people working the fields because these were actually highly skilled professionals
[01:13:21] doing a job that they liked on
[01:13:24] rather favorable conditions, not slaving outside in the sun all day.
[01:13:28] But where we live now, would we still like for clothing to be this
[01:13:34] heavily constrained resource? Like, what if this T-shirt was
[01:13:38] $400? I mean, okay, then I'd have
[01:13:42] two. Well, my wardrobe probably looks like I have two. But
[01:13:46] I think the general progress of mankind depends on productivity
[01:13:54] improvements. And what are productivity improvements? This is very important because in the abstract,
[01:13:58] I think everyone says, "Yay, productivity. That's good."
[01:14:02] What did you think, this was all just vibes? No. Productivity means fewer
[01:14:06] people to do the same number or the same job. Now,
[01:14:10] the amount of job you want done may increase, and therefore you get more people,
[01:14:14] but it also may not. There may be pockets
[01:14:17] where a company just needs a certain set of
[01:14:21] fixed tasks done, and suddenly they can do them with a 10th the number
[01:14:25] of people. This, by the way, could... is tragic
[01:14:29] and difficult in the moment for the individual being laid off. It's also amazing
[01:14:33] for the economy at large. Suddenly you've freed up these resources who can
[01:14:37] now go do more productive things. This is how the whole
[01:14:40] economy evolves and improves and how we get growth,
[01:14:44] and growth is good. I think this is the other thing to make a
[01:14:48] strong defense for, that growth in
[01:14:51] general is a good thing. We do not want to wind the
[01:14:55] clock back to 1920 or 1950. We should
[01:14:59] be excited about the fact that we've discovered new
[01:15:02] technology that allows us to do vastly more. And
[01:15:08] while some of the tasks that may be taken over by AI were tasks
[01:15:11] that humans were excited to do, and they're just no longer economically
[01:15:15] viable, a lot of the tasks were just drudgery. This is certainly true
[01:15:19] of my programming. There were moments of programming
[01:15:23] I thought were amazing. These were the moments that produced that state of
[01:15:27] flow we talked about last time, and they were ecstatic. How often did they
[01:15:34] happen out of the course of a year? If you took your average
[01:15:37] programmer, how much time out of 2,000 hours at
[01:15:41] the job did that person spend in a flow state?
[01:15:47] 100? 200? 25? I think all those answers could be plausible for someone.
[01:15:54] And taking that drudgery, handing it over to
[01:15:58] machines, that is the history of civilization.
[01:16:03] - Yeah, I mean, the hours spent debugging. So programming has so many painful,
[01:16:09] painful hours in it. And now they're gone. For the... I mean, for the most part,
[01:16:14] it's just fun.
[01:16:16] - A lot of it is gone in a lot of domains, and the rest of it may be gone very soon.
[01:16:20] So that's where some of the romanticism also comes in
[01:16:24] ... because pain in the moment
[01:16:27] is difficult. It's hard. It's annoying. Pain in the rear
[01:16:31] view mirror is accomplishment, proud,
[01:16:35] learning, steps forward, all the things, right? So we
[01:16:39] encompass all of this as part of the human experience, that we hate
[01:16:43] pain in the moment, but we cherish it when
[01:16:46] it's five minutes past and we don't remember the hardship. We
[01:16:50] just remember the progress.
[01:16:51] - So certainly at the societal level, at the macroeconomic
[01:16:55] level, growth is exciting. But the individual level, there's going to be a lot of
[01:16:59] anxiety potentially a lot of suffering. So by way of
[01:17:03] advice, if you're like a young DHH or young developer
[01:17:07] programmer now, what would you advise they do?
[01:17:11] - Don't try to anticipate anything. You will literally go crazy.
[01:17:15] Because even the smartest brains in the business
[01:17:18] cannot anticipate what two model hops from here is
[01:17:22] going to look like. It's an absolute waste of time, and you
[01:17:26] will develop an AI psychosis trying to deduce what two
[01:17:30] years from now is gonna look like. Focus on right now, and right now is the most
[01:17:34] incredible time to be into computers.
[01:17:38] You can make them do the most amazing things if you lean in. If you
[01:17:45] maybe for a hot moment force yourself to learn where the state of the art is,
[01:17:52] I double dog dare you not to get excited about what's possible.
[01:17:57] - And would you recommend building publicly?
[01:17:59] - I think it's optional actually to build publicly. I think it's
[01:18:03] nice to do because then you get to be part of a community, and there's some
[01:18:07] camaraderie in open source. Not some camaraderie. There's an
[01:18:11] enormous amount of camaraderie. Open source is an
[01:18:14] incredible source of community and camaraderie,
[01:18:18] and it's also a great way to stem some of that
[01:18:22] personal existential dread. If you're amongst other humans, you can
[01:18:26] get infected with good forms of mind viruses,
[01:18:29] exciting forms of mind viruses, the ones that tell you that it's all gonna be okay,
[01:18:34] and the future looks bright, and if we
[01:18:38] build a bunch of things together, we can do things none of us ever
[01:18:41] dreamed we could do. I was just talking to Ryan Hughes, who's been
[01:18:45] my main partner on Omarchy almost since day one,
[01:18:49] and we were literally talking about yesterday how when
[01:18:53] We started on this journey together. Our ambitions were very
[01:18:56] modest. We're just like, "Can we get this distro to not crash at
[01:19:00] 3:00 AM because of an Arch package that just got pushed out
[01:19:04] outside of our control? That would be amazing. Then it'd be great." Now
[01:19:08] we're leaning back and thinking, "How can we take over the world?
[01:19:12] How can we make Omarchy go to Mars? How can we do everything we've ever dreamed of?"
[01:19:21] And that level of ambition inflation is partly
[01:19:25] because things have gotten better with agents, but hugely also because we've
[01:19:28] surrounded ourselves with others excited about the same journey.
[01:19:33] And if you're just sitting in your little isolated cave
[01:19:38] worrying about the future, yeah, you're gonna go a little nuts.
[01:19:42] I think if we learned anything during COVID is
[01:19:46] that people will go nuts sitting in their little cave
[01:19:49] inside by themselves worrying about what's gonna happen. That is
[01:19:53] indistinguishable from depression, ruminating endlessly about things you can't
[01:20:00] control. I'm sorry to channel some Jensen Huang here, but that's just loser talk.
[01:20:07] You don't have to be a loser. You can choose to lean in and-
[01:20:13] ... win. And win is very broadly defined as learning
[01:20:17] more, making more, contributing more, being part of more.
[01:20:23] And at the end of the day, what are your choices? You don't have a choice, mate.
[01:20:29] The future's coming whether you like it or not, so you might as well choose to be
[01:20:32] excited about it.
[01:20:34] - But I mean, we should emphasize the fact that planning is nearly
[01:20:37] impossible with AI. I mean, most of us plan our life a
[01:20:41] little bit. When we're younger, you have, like, hopes and dreams. There's a
[01:20:44] reason you go to college. There's a plan underlying that.
[01:20:47] - I agree with that.
[01:20:48] - But there-
[01:20:48] - I'll concede that.
[01:20:49] - ... it is kinda-
[01:20:50] - This is different.
[01:20:51] - ... nuts that it's impossible to really plan. Because, like, you really don't know,
[01:20:58] if there will even be a Claude Code, a Codex, and Cursor
[01:21:03] six months from now. Maybe it'll be you'll be talking to WhatsApp. Maybe
[01:21:07] it'll be all open call type. Maybe it'll just all be voice.
[01:21:10] Maybe Omarchy will take over the world and it'll be voice. Maybe there won't be operating systems
[01:21:14] anymore. You'll just... There'll be this glowing orb that just you just talk
[01:21:18] to because if natural language is enough to accomplish
[01:21:22] all tasks in life, like, what is life about? Like, what are the major
[01:21:26] tasks you need to accomplish in life? If you can just do that with voice, and
[01:21:30] it writes all the programs for you, and all is systematized, and what,
[01:21:34] what are the jobs needed then? Maybe it's more about the service
[01:21:38] industry. Maybe there won't be programmers, like agentic engineers at all. And so
[01:21:44] yes, your advice is wise to focus on the moment, but that doesn't mean
[01:21:48] that it's just a crazy rollercoaster ride, 'cause we don't know
[01:21:52] what this December or what this January will look like.
[01:21:55] - We don't know, and therefore, we should choose to have faith that it's
[01:21:59] gonna pan out. That is my best advice
[01:22:04] towards fighting anxiety, is that you have a choice, to a large degree,
[01:22:11] of how to lean.
[01:22:13] Do you wanna lean into PDoom? PDoom is gonna happen whether you lean into it or not.
[01:22:21] You don't have control.
[01:22:22] - But there's also actual daily schedule of how much learning are you doing, how much
[01:22:26] building are you doing, how much uh, diversification you're doing.
[01:22:31] And for example, I traveled across rural China recently, and I did
[01:22:35] it quite deliberately because you're talking to people in China, in,
[01:22:41] in rural anywhere, where time moves much slower, where there's no discussions
[01:22:46] about agentic engineering. And the ti- and
[01:22:50] I started by going on the, on the Great Wall of China.
[01:22:54] That's timeless. That spans centuries. And, you know, there
[01:22:58] was, like, this kind of tension of FOMO, like maybe I'm missing out on something.
[01:23:02] But then I very deliberately wanted to find the
[01:23:06] timelessness of human existence, really plug into the fact that,
[01:23:10] okay, it always feels like everything's changing uh,
[01:23:14] throughout human history but, you know, the universals are still true,
[01:23:18] of what matters in life. And I just wanted to make su- keep connected to that.
[01:23:22] - You're not gonna miss anything. This is the part that actually
[01:23:26] grinded my gears in the early phases of this
[01:23:30] transition. Everyone was so up in arms that if you
[01:23:34] didn't... It's loops now. Oh, no, no, we're done with loops. It's graphs
[01:23:37] now. Oh, no, no, we're done with that. It's, it harnesses this, right? They're, they're constantly
[01:23:41] churning through the frontier, which in one way is actually
[01:23:45] very exciting. This is what happens when a new field opens up. It's like a
[01:23:49] new portal, and it's all spilling out. That's exciting. But it
[01:23:53] also means that if I had just been backpacking for the last year,
[01:23:58] hadn't touched a computer,
[01:24:00] hadn't witnessed this agentic moment, and I just showed up
[01:24:04] yesterday, do you know what? I would've been caught up in two weeks.
[01:24:08] There's not any accumulation, which is in some ways a
[01:24:12] great relief. If you missed the past year, you can catch
[01:24:16] up to the frontier in two weeks.
[01:24:19] If you're a programmer who was out hiking the Himalayas for a year and
[01:24:23] you come back, you can catch up in two weeks. And this is actually the great
[01:24:27] credit to the progress we're experiencing. We have so
[01:24:31] many experiments running simultaneously right now that are
[01:24:34] constantly and ruthlessly sorting what works, what
[01:24:38] doesn't work. You don't have to remember or even be part of that
[01:24:42] entire journey. You can just show up for the results.
[01:24:45] - But the key step there, when you come back from the backpacking journey,
[01:24:49] is to be willing to become a totally new, different human because-
[01:24:55] Things are changing so fast.
[01:24:56] - That's right.
[01:24:56] - I mean, literally, if you left for the backpacking journey- ... in October last
[01:25:00] year and came back in April or May-
[01:25:04] - You might as well have been in the cryo chamber for 100 years
[01:25:06] - ... it's like, "What, what do you mean? We're not programming anymore?" This, it's a it's a
[01:25:10] huge transformation.
[01:25:12] - It's startling, and I actually... I mean,
[01:25:14] I'm putting some of this on slightly for effect. I also
[01:25:18] recognize that it's okay to grieve for a hot moment.
[01:25:22] That's not my disposition. It's not how I do it, but I accept that that's a
[01:25:29] time-tested mechanism for coping with
[01:25:34] a sense of loss. And it's okay to have a sense of loss that the world
[01:25:38] that you knew and maybe you were very fond of is no longer the same.
[01:25:43] - I maybe I should say out loud and explicitly that I do have that, the Native
[01:25:47] American with a tear rolling down my... Like, there's a sadness.
[01:25:51] It's a goodbye. It's a goodbye to the old world of programming.
[01:25:55] - That's, it's so fascinating to me.
[01:25:56] - I've spent so many years-
[01:25:58] - But it all amounted to this moment. That is, to me, what makes the
[01:26:02] entire journey so meaningful.
[01:26:05] AI did not arrive from the sky. It was not alien technology that
[01:26:08] had blasted through the universe and suddenly showed up on our shores.
[01:26:13] AI has been around for as long as computer science has been around.
[01:26:17] In the '50s, they thought the problem was gonna be cracked in about a
[01:26:21] decade, the smartest people at the time. It took a little longer,
[01:26:25] but the reason it took a little longer was in part because we took
[01:26:29] some blind turns on the road to AI and neural
[01:26:33] networks and thought that there were other symbolic representations that were
[01:26:36] gonna carry the day, and they didn't. And that probably set us back
[01:26:40] about 15 years. So some of it was also we had to,
[01:26:44] Go through the gaming revolution, 3D games. If we had
[01:26:47] not had Quake, if we had not had Duke Nukem, if we had not had
[01:26:51] Unreal Tournament, we'd never have gotten AI because we would never have gotten the GPUs,
[01:26:55] and therefore we would never have been able to get AI in the shape it is now. So
[01:27:01] everything we did up until this moment was required to get there.
[01:27:05] You were part of that. Holy... What a blessing.
[01:27:09] What a blessing to have contributed in your small part, either by
[01:27:13] training or by playing video games. Literally, you could just choose to
[01:27:17] think of it that way. All those times you spent in,
[01:27:21] for my case, in the '90s just playing video games, they were-
[01:27:23] - You were contributing.
[01:27:24] - Yeah, I was contributing to the AI revolution right there and then moment.
[01:27:27] - To the progress of human civilization. No, for sure. Civilization
[01:27:30] progresses with the death of the old and the birth of the new, and it
[01:27:34] continues in this way, but it's still the grieving process is a part of it, I think.
[01:27:39] - Take a moment. It's okay. Take a... And also, you don't even
[01:27:43] have to accept that it's all dead. Like, if you are still very attached to the hand
[01:27:50] chiseling, which if you'd asked me a year ago, I would have predicted that I
[01:27:55] would've been more attached. I'm surprised-
[01:27:58] - I'm kinda surprised
[01:27:59] - ... a little that I've not been more attached. But the reason I've not been more attached,
[01:28:03] I think, is that I found something more fun.
[01:28:07] And if it hadn't been like that, if AI had
[01:28:11] just replaced the thing I loved and gave me something I hated, I'd
[01:28:15] probably be a little bitter.
[01:28:16] - I mean, this really feels... It's hilarious and awesome to watch and inspiring to watch.
[01:28:19] It's like Picasso all of a sudden like, getting access to
[01:28:26] to image generation and getting super excited and switching in a
[01:28:30] matter of months. That's literally what happened. So, like, it's an artist that appreciated beautiful
[01:28:34] code, and all of a sudden you're talking about having fun-
[01:28:37] - I think Picasso is actually a good parallel because if you look at his early
[01:28:42] work where he learned his craft, it was painting
[01:28:46] realistic paintings, right? Like, he was training to
[01:28:50] be a master of the old ways of depicting reality the best way we knew how,
[01:28:56] and then along comes all these other forms of expression. Cubism comes along.
[01:29:01] And all these forms of abstract expression, he's
[01:29:05] not decrying that he's not doing Renaissance
[01:29:09] paintings anymore, that he's not just painting the perfect depiction of an
[01:29:13] apple. He's reimagining the apple to be a freaking square,
[01:29:18] and he's getting excited about that. And I feel that
[01:29:22] transition, that we've gone from this one mode of
[01:29:26] expression, and we've suddenly opened the gates where
[01:29:31] the, like, the color spectrum is so much wider. I'm seeing more. And it's
[01:29:37] perhaps because the way I became a programmer. I did not become
[01:29:41] a programmer because a deep love of if statements.
[01:29:46] I became a programmer because I wanted programs.
[01:29:49] I wanted things to exist that did not exist. And at first,
[01:29:53] I had to learn how to program to make that happen.
[01:29:56] Then I happened to fall in love with programming as a craft, and then I spent two
[01:30:00] decades really diving deep on that. But now I'm back. I'm back to having an idea and
[01:30:08] being impatient beyond belief to see it exist in the world,
[01:30:13] and AI has just shrunk that down to almost nothing. So it's an acceleration
[01:30:20] of a rediscovery.
[01:30:23] Now, I understand that that's not true for everyone. There are plenty of
[01:30:27] programmers who just loved programming right from the beginning, and they were attracted
[01:30:31] to the logical constructs and so forth. I mean, I've been there for two decades, so I get
[01:30:35] it. But I also think that you're able to discover new sides of yourself-
[01:30:41] ... if you let it in. Again, I keep coming back to this
[01:30:46] almost regret minimization framework, to borrow Jeff Bezos's terms here.
[01:30:52] Are you gonna look at yourself two years from now and think, "Oh, I spent
[01:30:56] my time well being pissy about the present,
[01:31:00] about the fact that my industry changed"? Or
[01:31:04] Would I two years from now look back upon this moment and be proud
[01:31:08] of myself for leaning in, for maybe having a moment of
[01:31:12] grief? Again, there's room for all of it. And then going, "I'm gonna
[01:31:16] learn how the world spins now, and I'm gonna make not just the best of it, I'm
[01:31:20] gonna make more of it."
[01:31:22] - I mean, it is true, a lot of programmers, a lot of friends of mine,
[01:31:26] me, obviously you, are having fun.
[01:31:30] - I have had more fun with computers in the last three months than at any time
[01:31:37] previously.
[01:31:38] - Quick bathroom break, and then I gotta ask you about
[01:31:42] how you actually interact with the systems now.
[01:31:45] - Yes.
[01:31:46] - I gotta ask you about how has your programming setup changed? So keyboard,
[01:31:54] voice, what's the IDE?
[01:31:57] - It's crazy to think about now, but yeah, I used TextMate for almost 20 years.
[01:32:02] I used TextMate starting in
[01:32:05] 2005, I think. I helped get the first version out, and then I just
[01:32:09] wasn't interested. I wasn't in the market for an alternative. And
[01:32:13] it wasn't until the switch to Linux that I was forced out of my habitat. And
[01:32:21] now with the switch to,
[01:32:24] what are we calling it? Agentic engineering? Oh, I fucking hate that term. We gotta
[01:32:28] come up with something that sounds as plain as programming, but
[01:32:32] encapsulates the fact that it's with agents. But-
[01:32:35] - I still think it should be called programming at this point.
[01:32:36] - ... All right, let's just call it programming.
[01:32:38] Programming with agents requires a different tool set. It really does.
[01:32:42] And the main change here is that
[01:32:47] you're going from single thread programming in your head to parallel processing.
[01:32:53] When I was writing code, chiseling it by hand in TextMate or even Neovim,
[01:32:59] Not that long ago, I would just focus on one problem at the time, and
[01:33:03] I would methodically work my way through it, and that was actually the portal to flow.
[01:33:07] The portal to flow was deep,
[01:33:10] immersion into a single problem, see it through to the end.
[01:33:15] That's not how it works with agents, in part because the
[01:33:18] agents are at once both too fast and too slow. They don't give you an immediate
[01:33:25] reply on something that you asked them to do that's the
[01:33:30] same as typing on a keyboard. So you have to let the agent cook-
[01:33:34] ... for a bit, and therefore you realize, well,
[01:33:39] if I just sit around waiting for them, first of all, that doesn't feel productive.
[01:33:43] Even if the agent, just one of them, can be highly productive, it does not feel productive.
[01:33:47] It does not feel good. It feels actually like you're a little bit useless.
[01:33:50] And maybe I had a moment,
[01:33:52] when the first agentic moment was there and we, I was running mostly
[01:33:56] one agent at a time where I felt like, "I don't know about this."
[01:34:00] But you can solve a lot of hard problems by simply
[01:34:04] throwing more resources at it. This is the whole scaling law of
[01:34:08] AI of itself, right? That if you parallelize these
[01:34:12] things and you're not running one agent, but you're running a handful,
[01:34:15] you can feel like you're in a flow state because you're constantly doing
[01:34:22] programming work in the sense that you're making decisions, and you're helping either
[01:34:26] unblock an agent because it has a question about which direction to take, or
[01:34:30] you're ready for a new task. And to do that, you need a different
[01:34:34] setup. I started first doing it in tmux and just
[01:34:38] having separate panes and having separate splits. Basically,
[01:34:42] a terminal with tabs is a good way to think about it. You open a bunch of tabs. I think
[01:34:46] most humans know exactly how that works. They don't work in just one tab.
[01:34:50] - So still sticking to the terminal, CLI.
[01:34:53] - Absolutely.
[01:34:53] - So you're not using Claude Code app or the-
[01:34:56] - No.
[01:34:56] - ... Codex app or the-
[01:34:57] - I love the fact that this agent revolution was kicked
[01:35:01] off in the terminal because I was already a huge fan of TUIs, terminal
[01:35:05] user interfaces, and the terminal in general. That feels like a,
[01:35:10] a really nice place to be. It's a beautiful place to be. The modern terminal
[01:35:14] is just a good-looking place to work. So I like that. And then
[01:35:22] this fact of having multiple agents, especially once it's not
[01:35:26] just multiple agents running on your own machine, but you start running multiple
[01:35:29] machines. Now tmux alone is not enough to
[01:35:35] keep track of it, and that's why as of late I've switched to this thing
[01:35:39] called Herdr. And Herdr is essentially tmux plus agent
[01:35:44] notifications. So whenever your agent is done and needs something for you, it goes
[01:35:48] ding, a little bell telling you it's ready for its human,
[01:35:54] uh... Is it master or servant? I'm not quite sure always.
[01:35:58] But it is ready for a decision, and it also keeps track of
[01:36:02] these is it in working mode or not. So I have this Herdr set up. I have
[01:36:06] multiple Herdr setups actually running on individual machines.
[01:36:10] I went on this crazy phase just about a month ago
[01:36:14] realizing that doing this work on a single machine is
[01:36:18] not fast enough. It's like I've discovered multi-core programming, but I only have two
[01:36:22] cores. I'm like, "What if I had 16 cores? What if I had 32 cores? What if I had
[01:36:26] 64 cores?" So I instantly went out and I bought these amazing
[01:36:31] KVMs called GL.iNet Comets.
[01:36:35] And what they do is it's this little box. You plug in HDMI, you
[01:36:39] plug in USB and connect it to the computer. It's like a
[01:36:43] KVM. So a KVM is a remote way of controlling a computer, but
[01:36:47] what's special about this is just how easy it was. You connect this thing in,
[01:36:52] you go to a webpage, log in once, set one
[01:36:55] password. Now this thing can hop on your tailnet.
[01:36:59] This has been the other revolution of the last year for me, is discovering
[01:37:06] these WireGuard networks. Uh, Tailscale
[01:37:10] is essentially turning all the computers you have into a local
[01:37:14] network wherever you are.
[01:37:16] Like right now on my phone, I have direct access to all the
[01:37:19] computers in my Malibu office. I also have
[01:37:23] access to all my computers in my Copenhagen office.
[01:37:26] And I can treat them as though I sat right next to them without having to
[01:37:30] punch holes in a firewall or set up complicated VPNs.
[01:37:34] And what this does is it just decreases the friction it
[01:37:38] takes to get new compute online.
[01:37:41] So as soon as I discovered this, I looked at my closet, and I realized I had a bunch
[01:37:46] of mini PCs from prior experiments, and I just said, "What if I just connected all of
[01:37:50] them?" And I just connected four of the computers-
[01:37:53] ... in a closet. They all had their little Comet, and
[01:37:57] suddenly I could run agents on more computers at the same time,
[01:38:01] and I could control them all with Herdr.
[01:38:04] And it did get to a point where I maxed out my own processing power.
[01:38:09] That I think at about... What do we want to put it? About four to five machines
[01:38:15] running, I don't know, three agents. I have about 16 threads. That's what I can run.
[01:38:21] And the faster the agents run, of course, the fewer threads I can run, but at the current pace, I can run
[01:38:25] about 16 threads-
[01:38:26] - Mm-hmm, at full acceleration.
[01:38:29] And that's part of why I've gone from just being excited about
[01:38:35] the agent moment to being delirious. Because
[01:38:39] I think as you say, some of it is a little assaulting.
[01:38:42] Again, we're on a dial-up bandwidth-wise with our computer. I mean,
[01:38:48] it's actually hilarious. So you think of I'm sitting here a year ago, right? I'm
[01:38:52] chiseling my code. Yeah.
[01:38:53] - I'm writing my lines. And over the course of, like, an hour, I will have written
[01:38:59] one beautiful controller, one beautiful model. Like, that's one file.
[01:39:03] And I've really worked on it, right? So maybe there's 60 lines left. So
[01:39:07] maybe my bandwidth at this moment is, like, 30 lines
[01:39:11] an hour. I think that's even high. Maybe it's 20 lines an hour. Now I'm
[01:39:15] running 16 threads. I'm producing at some
[01:39:18] times hundreds of lines of hour or hundreds of lines of code
[01:39:22] per hour. Now, let me pause myself there for a hot moment.
[01:39:26] I hate that metric, right? Like, lines of code is a stupid metric
[01:39:30] in general to measure these things, and I think it's right from
[01:39:34] some in the programming community to ridicule the AI psychosis when
[01:39:38] everyone talks about the number of lines of code they're writing, and then you ask them,
[01:39:42] "What did you build?" And they're like, "Well, I..."
[01:39:46] And then no good answer comes out, right?
[01:39:47] - It's just a nice shorthand to-
[01:39:49] - It is a nice shorthand. It is a representation or encapsulation
[01:39:52] of how much output that's coming out. Now, whether the output is good or bad-
[01:39:57] ... is not a referendum on that. But I was producing and producing so much more now,
[01:40:01] right? And therefore I'm able to keep all these threads going.
[01:40:05] So that's the setup. It's still Neovim, but at this point,
[01:40:10] I'm not writing a lot of code, so I'm using Neovim as a project browser
[01:40:14] and then as a way to kick off Lazy Git to see the change
[01:40:17] log for what's there. And even that, I'd say
[01:40:23] if GitHub was a little faster at showing you your pull request, the web is
[01:40:26] probably actually a nicer place to do that. I don't know. There's also this other tool
[01:40:30] I've been playing with a bit called Hunk, which just produces
[01:40:34] Diffs in a really nice way. So you could look at that too. But I find that when I look
[01:40:38] at Hunk, I only see the change set, and when I'm reviewing
[01:40:42] output from an agent, I often want to see the surrounding context. Oh, yeah, so it
[01:40:46] changed this file, but actually, what do we have in this other file that wasn't touched but maybe should've
[01:40:50] been touched? So that's why I still like Neovim as a way of doing
[01:40:54] it. But it's all happening, by the way, of course, in
[01:40:58] Amachi. So it's all happening on Linux. And this was the other major
[01:41:01] breakthrough with agents. Agents love the Unix philosophy. It loves individual tools
[01:41:09] that it can invoke through the command line, and there is no operating system
[01:41:13] on Earth of the majors, I'm counting three here, Mac, Windows,
[01:41:19] Linux, that works as well with that
[01:41:23] mechanism as Linux. Everything in Linux is either a config
[01:41:27] file or a CLI tool. Now, that was its
[01:41:31] main drawback five minutes ago. This was the reason people didn't like
[01:41:35] Linux. It's like it's all config files and CLI tools.
[01:41:39] What great irony that the universe has played it upon us that now the
[01:41:45] drawbacks of Linux five minutes ago are now its major selling points.
[01:41:50] This was one of the things I thought I was stuck for a weekend with a Mac
[01:41:57] four months ago.
[01:41:58] I thought I had a computer at the place I was going that was a Linux machine, so I
[01:42:02] didn't bring my laptop, and I found out when I arrived I only had a Mac Mini.
[01:42:08] So I was gonna make the best of a bad situation here and,
[01:42:12] Set up my Mac in some of the ways I've been thinking about with,
[01:42:17] With Linux. And you can actually do a lot now. Homebrew has gotten
[01:42:21] really quite good. Homebrew is the missing package manager for the Mac,
[01:42:25] and no one has done more to move the Mac forward in terms
[01:42:29] of ease of setup. But still something as simple as
[01:42:33] Raycast, I don't know if you've used that. That's the-
[01:42:37] There's no config file that you can just access. You have to go into the
[01:42:40] GUI, export a file, then take that file,
[01:42:44] I don't know, in your freaking backpack on a USB key.
[01:42:48] And then you can import it somewhere else. You cannot automate the entire setup of your
[01:42:52] machine. You can't automate at all the configuration of Mac's default key bindings.
[01:42:59] That has to be a manual process where you're clicking with a mouse like a
[01:43:03] caveman to set up your machine.
[01:43:05] - I mean, there's ways around it.
[01:43:07] - Not good ones. I looked. I tried hard
[01:43:10] - So here's my, been my journey. Obviously I'm a Linux
[01:43:14] person, but because of Adobe Premiere, Adobe products, I'm also a Windows person,
[01:43:18] so oftentimes I would use WSL, Windows Subsystems for Linux.
[01:43:23] So Linux inside Windows, which is... in the agentic era is not a good kind of
[01:43:27] Linux, 'cause it's just-
[01:43:28] - It's a sandbox
[01:43:29] - ... it's a sandbox, and you want the Linux to be unleashed to be able to do everything.
[01:43:33] - Correct.
[01:43:34] - And so I have now woken up to things like GrayCat, and have
[01:43:38] you know, I'm a keyboard person. Where's the config file? What, can I,
[01:43:42] can I basically do everything where an agent
[01:43:46] can set everything up for me and save the configuration so I can
[01:43:50] replicate it across systems and everything's automated? And so I had to
[01:43:54] ask a lot of those questions, and a lot of them are missing.
[01:43:56] - They don't have good answers.
[01:43:57] - But oftentimes you could actually just build the app yourself.
[01:44:01] - But there are hacks.
[01:44:02] - Yeah, they're hacks.
[01:44:03] - There are hacks.
[01:44:03] You don't have to live like this, Lex. There's a better... Actually, this is a great
[01:44:07] moment.
[01:44:08] - Until you have a video editor.
[01:44:11] - So this is a good moment.
[01:44:12] - Yep.
[01:44:13] - Um, I heard it was your birthday. So I brought a little gift.
[01:44:18] - No.
[01:44:19] - We are going to get you onto the agentic operating system whether you
[01:44:23] like it or not.
[01:44:23] - This is awesome.
[01:44:24] - And I asked- ... my friends at Dell whether maybe they had a machine that,
[01:44:29] um, I could get you for your birthday.
[01:44:33] - Oh, no.
[01:44:33] - So here's the machine I use- ... which is-
[01:44:36] ... well, the same one I use, but it's now yours. It's a- ... Dell XPS 14-
[01:44:42] ... already set up with Omarchy 4- ... ready to be configured for you. And
[01:44:49] once you realize that all your... By the way, we should almost time
[01:44:53] this. You can be up and running.
[01:44:55] You have to answer, like, five questions in about one minute. You
[01:44:59] could literally do it live if you wanted to.
[01:45:00] - Oh, Omarchy, beautiful, modern opinion Linux by DHH. Yeah, let's do it.
[01:45:04] - Yeah, fill it out while I talk. So-
[01:45:07] ... exactly what you realized, that pain on the Mac
[01:45:12] was the exposure I got for about a weekend, and I tried really hard, and I
[01:45:15] found some decent workarounds, the main one being that Homebrew
[01:45:19] now has tabs for GUI apps. Because it's
[01:45:23] hilarious to think upon the recent past where people
[01:45:27] would go to websites, like, "I need Zoom." They would
[01:45:31] enter zoom.com, find the download link, download
[01:45:35] a DMG- ... double-click on that, see a weird
[01:45:38] manual interaction telling them to drag an icon
[01:45:42] from one place of the screen to the other, and that was how you installed apps.
[01:45:48] And you'd just do that over and over again until you had all the apps that you wanted,
[01:45:52] and if you were setting up a new machine and you had, like, 12 apps, you'd go to
[01:45:56] 12 different websites to download them like a total caveman.
[01:46:01] Homebrew has solved a lot of that, but it has not solved all of it, and has solved
[01:46:05] nothing in terms of the-
[01:46:08] - Sorry to interrupt, but look how fast this is going.
[01:46:11] - Oh, it's gonna be done in about 40 seconds.
[01:46:15] And then you're gonna be inside of Omarchy.
[01:46:17] - Super is the Windows or Command key on your keyboard. So which one is the Super key?
[01:46:21] - Yep, that's the Windows key. Oh, actually, no, no, you have a special edition.
[01:46:25] There are only about six of these computers in the world.
[01:46:27] - Oh, there's a Super key.
[01:46:29] - It says Super, and look at where the Copilot key is on the other end of the
[01:46:32] keyboard. That's the Omarchy logo.
[01:46:35] - Nice. Okay, cool.
[01:46:36] - This was Spencer Bull at Dell, who I've been working with on a
[01:46:40] lot of this stuff. They've been incredible.
[01:46:42] - They, for a moment, let go of the XPS brand.
[01:46:46] - Yes, they did, last year.
[01:46:48] - And I was like, "This is dumb. This is... XPS is awesome."
[01:46:51] - It was not just dumb that it got rid of the XPS branding. They also got
[01:46:55] rid of the Escape key and put in capacitive touch buttons at the
[01:46:59] top. The mistake that Apple realized like three years ago was
[01:47:03] terrible, and everyone hated them for them.
[01:47:04] But now they have an incredible team, and this
[01:47:08] was actually my first Dell laptop for myself.
[01:47:12] Because I've been using Dell on our servers. Dell was what powered our
[01:47:16] cloud exit. We've been running Dell since the mid-2000s, I
[01:47:20] think. But I never ran their laptops, because compared to a
[01:47:23] MacBook, they just weren't up to the task for me. The
[01:47:28] XPS' from 2016, or from 2026, with those
[01:47:32] Intel Panther Lake chips, are the first Dells
[01:47:36] that I would personally actually use. And it's funny because when I got mad at Apple
[01:47:41] originally, I thought, like, "Do you know what? I should just get a Dell," because we already used
[01:47:45] them and whatever, and I got a Dell, and I was like, "Man, I can't do it. I can't do it.
[01:47:49] It's not good enough." And then lo and behold, this year
[01:47:54] they just fixed everything.
[01:47:56] They fixed the battery life. They fixed the performance.
[01:47:59] They fixed the compatibility. They fixed the weight. They fixed the
[01:48:03] screen. That's a tandem OLED screen-
[01:48:05] - Yeah, that's incredible.
[01:48:05] - ... which means it's actually better tech than what you'll get in a freaking
[01:48:10] MacBook. It's lighter than a MacBook,
[01:48:13] and the chip is finally competitive because Intel spent
[01:48:17] a good five years developing the
[01:48:20] 18A process node. It took a long time, but now it's here, and
[01:48:24] it's freaking incredible. We finally have competition to Apple M chips-
[01:48:29] ... that can go as long as on battery and can have competitive performance.
[01:48:34] - And there's a beautiful default theme to this thing, and then what is it? Super
[01:48:38] Space opens up.
[01:48:39] - Actually, you can just push the Omarchy key. It opens up the menu. So now you control
[01:48:43] everything from there.
[01:48:44] - Oh, same thing as the Super. Okay.
[01:48:45] - Yeah.
[01:48:45] - Cool.
[01:48:45] - Same thing as Super Space. So this has been a huge change for me, that we finally
[01:48:53] have Linux machines that you don't have to make excuses for.
[01:48:57] Because I don't mind making excuses because excuses are really just another
[01:49:01] word for trade-offs.
[01:49:02] I love that Framework 13 I think I talked about last time. I still
[01:49:06] like them. They still make good computers. But I think for a lot of people, they
[01:49:12] didn't want a DIY experience. They wanted something that just out of the
[01:49:16] box felt like it was on par in build quality and
[01:49:21] whatever with Macs, and now we finally have it. So happy birthday.
[01:49:27] - Thank you so much. An Omarchy Dell laptop from DHH is the best birthday
[01:49:33] present. This is awesome.
[01:49:34] - Check the screensaver, by the way.
[01:49:36] - Yeah, it's kind of amazing. I'm seeing it.
[01:49:38] - On that tandem OLED screen-
[01:49:41] - It's gorgeous.
[01:49:41] - ... it is absolutely mind-bogglingly awesome.
[01:49:46] - Look at that. There's like a retro look to the whole thing.
[01:49:50] - Totally.
[01:49:51] - It's like Fiverr pop-
[01:49:51] - It's like running a bulletin board system in- ... the '90s, which is
[01:49:55] exactly what I did when I was 14 years old. So for me, it's a
[01:49:59] complete throwback and an awesome aesthetic, combining this sense of modern
[01:50:06] rising culture in Unix with- ... this throwback of the '90s.
[01:50:10] - Yeah, like a retro look for an agent first OS.
[01:50:12] - Exactly.
[01:50:13] - It's crazy.
[01:50:13] - Which again, pairs... This was why I was so excited that-
[01:50:17] ... all these agent harnesses arrived as TUI's, arrived as CLIs-
[01:50:21] ... has arrived as a terminal because suddenly,
[01:50:25] a whole new generation of both programmers and regular users
[01:50:28] discovered the glory of the terminal. The terminal was actually one of the most,
[01:50:34] impressive and productive user interfaces we can have.
[01:50:38] Now, we've built user interfaces since then that were easier to learn.
[01:50:43] The mouse is a wonderful invention for
[01:50:47] letting someone who doesn't know a lot about computers just click around and find things out, but
[01:50:51] the terminal is for people who want to
[01:50:55] learn their systems, who want to learn the keyboard commands.
[01:50:57] - So you think the TUI is gonna stick around?
[01:51:00] - 100%. Now, it's not gonna be the only thing. Of course it's not, because
[01:51:03] these labs now have trillion-dollar valuations, so they need to be able to
[01:51:07] reach billions of people.
[01:51:09] And I don't think we're gonna teach billions of people the intricacies of the TUI.
[01:51:13] So we're gonna have other tools, and we already have other tools, which is, by
[01:51:17] the way, one of the sweet things about Linux, the ChatGPT Codex tool.
[01:51:22] - Yeah, I saw that.
[01:51:23] - Literally within two hours of that announcement dropping, I had it wrapped
[01:51:27] up and ready to go in Omakub. Already now, if you go to... You can
[01:51:31] actually hit the Omakub key-
[01:51:33] ... and then just write ChatGPT. It should pop up as, like, install.
[01:51:38] And then just hit return.
[01:51:41] - Sudo password for Lex.
[01:51:42] - Yeah, whatever you put in. And then it's just gonna install it, and it's gonna pop it up, and you have
[01:51:47] ChatGPT.
[01:51:47] - Nice.
[01:51:48] - And that's how a lot of the apps are, and all the agentic harnesses are built in that
[01:51:52] way.
[01:51:53] Um, Tailscale, as I talked about, if you wanna hop on that, is that way. Uh, Dropbox.
[01:51:57] And the reason all these things are in there is because I use them.
[01:52:00] It's because I built this system for me, and I thought, first and foremost, how do I
[01:52:04] build my dream computer just for me? And if I get my
[01:52:08] dream computer, I am assured there are other people who are gonna have the same dreams
[01:52:12] as I do.
[01:52:13] - Now, you're obsessed about getting the installation to be under one
[01:52:17] minute, and a bunch of people asked you online why. So
[01:52:21] Why? Why were you so obsessed to getting the installation to
[01:52:25] be less than 60 seconds?
[01:52:27] - First, let me quote Mitchell Hashimoto, who created
[01:52:31] Ghostty terminal that's awesome and also available on Omakub and was also
[01:52:35] the founder of HashiCorp, who had this great post on
[01:52:39] X not too long ago that had the killer line, "The
[01:52:43] pursuit of excellence deserves no explanation."
[01:52:47] Wanting to make something as good and as fast and as beautiful as possible has
[01:52:56] no need for justification. We should want beautiful, fast systems
[01:53:02] that are a delight to use. Now, the funny thing with the install time is it didn't
[01:53:06] actually start with a one-minute mission. I was being modest when it got
[01:53:10] going. I thought if I could set up my entire system in 15 minutes,
[01:53:15] it would already be such a dramatic improvement over what came before it that I
[01:53:19] would be perfectly happy. And it came off the fact that the benchmarking
[01:53:23] had been skewed so out of whack. You talked about the Commodore 64 being
[01:53:27] your first computer, right?
[01:53:28] When you unwrap that Commodore 64 and you hit the on button,
[01:53:32] in I think about less than one second, the basic interpreter
[01:53:36] was ready to accept your command. It was literally almost instant.
[01:53:40] There was virtually no boot time. Do you know how long it took me
[01:53:44] to set up a new Mac that I had bought for actually the one
[01:53:48] app that I still haven't vibe coded my way into on Linux, which is Adobe Lightroom?
[01:53:53] Brand-new computer, out of the box.
[01:53:57] I set it up. There's a software update. Before I was ready to
[01:54:01] install Adobe Lightroom that I had it fully up to date, it took 42 minutes.
[01:54:08] That's grotesque. That's absurd. That's an insult
[01:54:12] to everyone who likes computers, that you get a new computer and
[01:54:16] before you can use it, you have to spend 42 minutes doing updates
[01:54:20] on something that was already installed on it out of the box from the factory.
[01:54:24] That is just preposterous, and it's crazy that that's not even the
[01:54:28] worst thing. I also got a PC, um,
[01:54:32] because all these Linux machines, they come as PCs, right?
[01:54:34] - Right.
[01:54:35] - And they have Windows pre-installed. So I got one. This was just
[01:54:38] three weeks ago. Brand-new machine, Intel Panther Lake, the whole shebang.
[01:54:44] An hour and 35 minutes
[01:54:47] from unwrapping the thing until it's ready to use. How long did you take
[01:54:51] before you think you were in Omakub?
[01:54:53] - I mean, it's less than a minute for sure.
[01:54:55] - A minute.
[01:54:57] We can build computers like this. We have the technology. We've had the technology
[01:55:01] since like 1981 when the Commodore 64 first came
[01:55:04] out. The fact that we now have a computer that's a trillion times faster
[01:55:08] and you have to spend 42 minutes or an hour and a half setting it up before it's ready to
[01:55:12] use is so infuriating to me that it became a passion. And it's funny
[01:55:19] Just while we were having a little break here, I was talking to Ryan Hughes, my co-conspirator
[01:55:22] here. We now have, we think, a line where we can create
[01:55:26] these special turbo images that are pre-made for specific computers
[01:55:30] because it relies on some knowledge of the hardware, like
[01:55:34] the Dell XPS. We're gonna make a Dell XPS turbo
[01:55:37] image that can install in about 12 seconds. A full Linux system
[01:55:43] installed in about 12 seconds.
[01:55:44] - That's incredible.
[01:55:45] - That obsession is what gives me this great satisfaction with using computers,
[01:55:52] that we do not accept things the way they are. And this is why this
[01:55:56] agent-accelerated reality that I now inhabit is so invigorating.
[01:56:01] Because I can look at these kinds of constraints and go, do you know what? Um,
[01:56:06] I could have stopped when we were at five minutes. That would already have been fast enough.
[01:56:10] This was the argument on X, right?
[01:56:12] Why do you keep going? Five minutes is fast enough. Okay, maybe
[01:56:16] for you, but for me, 12 seconds is a lot more fun. And
[01:56:21] I always try to think these first principles.
[01:56:24] Okay, in that machine, actually hit the Omarchy,
[01:56:28] key again, and then do speed. You'll see a
[01:56:32] list come up, and one of them is, like, disk speed.
[01:56:35] - Speed test, network speed, disk speed.
[01:56:37] - Disk speed. Do do that one, and then run it.
[01:56:40] So this is testing the performance of the built-in NVMe drive, and what are you
[01:56:44] getting?
[01:56:45] - Seven GB a second.
[01:56:47] - So seven gigabytes a second. That's how fast that drive is. Why can we
[01:56:51] not install a Linux distribution in one second?
[01:56:54] The Omarchy distribution is 5.8 gigabytes.
[01:56:58] If we can run at seven gig... Now, of course, you can't actually do that
[01:57:02] because the USB key is a lot slower than that, but you should be able to
[01:57:05] maximize the underlying physics
[01:57:09] and protocols that we're dealing with, and that's your goal. We gotta
[01:57:13] get all the way back down to that.
[01:57:15] - Yeah. I love that you're doing a Linux distribution. 'Cause I mean, you could be
[01:57:21] do... You could be building anything. But the fact that you're building a Linux
[01:57:25] distribution means you're rethinking about what a computer is, 'cause a
[01:57:28] operating system is the fundamental, like, the foundation of how
[01:57:32] ... you interact with a computer.
[01:57:33] - Yes. And it's been so stale.
[01:57:34] - Yeah, it has.
[01:57:35] - The macOS we have today is
[01:57:38] scarcely different from the macOS we had 10 years ago. In fact, it's worse
[01:57:42] in many ways because Apple continues to
[01:57:46] chokehold the control on users. They don't want them to
[01:57:50] install software that they haven't already said good-
[01:57:54] ... to go for. They don't want users to reconfigure their
[01:57:57] hotkeys without doing it manually. They didn't want to change the
[01:58:01] 500-millisecond animation switching workspaces.
[01:58:05] It is an infuriatingly locked-down computer. Now,
[01:58:09] to Apple's credit, it's a pretty good computer for being locked down,
[01:58:13] but I don't want a locked-down computer. I wanna own my computer. Better
[01:58:17] yet, I wanna mutate my computer, and this is where the agentic
[01:58:21] age needs a new operating system.
[01:58:24] When you can vibe code whatever app comes to your mind, you should be able
[01:58:28] to vibe code your operating system. You should be able to change anything, how it looks,
[01:58:32] how it works, what panels are there, what are not there, and that
[01:58:36] requires Linux. As simple as that. There are no... None of the other two
[01:58:40] operating systems can deliver this.
[01:58:41] - But can you speak to the, I think somebody asked you, like, "Who the hell
[01:58:45] are you to think you could do better than Ubuntu?" For example.
[01:58:49] Or, or like, "Why are you doing it when Ubuntu is already pretty good?" And your answer
[01:58:53] was, "I thought I could do better."
[01:58:55] So can you speak to, this was on X, can you speak to, like, where
[01:59:01] the craziness comes from, thinking that you as
[01:59:05] one person or maybe with Ryan, you could start building something that's
[01:59:09] going to be better than Ubuntu or Arch or any of this?
[01:59:12] - Well, I'll say that it didn't start quite as
[01:59:16] grandiose. When I got going with my Linux journey, I actually just
[01:59:20] started with Ubuntu, and I just built on top of it. Here's a
[01:59:23] system that already does a lot of the things I wanted to do, and at least it's
[01:59:27] Linux. So can I just build on top of it and make it more modern, make it actually look good,
[01:59:31] and have the programs I wanna use? I got, like, some version of that,
[01:59:35] and then I discovered that there's seven layers deeper you could go, and as, the
[01:59:39] closer you get to the metal, the closer you get to the kernel, the closer you get to the
[01:59:43] individual packages and so forth, the more freedom you
[01:59:46] discover. So as I discovered more and more freedom, I got more and more
[01:59:50] ambitious, and I realized, oh, surprise,
[01:59:54] surprise, I have strong opinions about how computers should work, how they
[01:59:58] should look, what programs should be installed, and
[02:00:01] whether they should take 42 minutes to install or
[02:00:05] 45 seconds. That's the current world record, by the way.
[02:00:09] So if anyone installs Omarchy Quattro after this and can beat 45 seconds,
[02:00:13] take a screenshot, send it to me, and you'll be the new holder of the world record.
[02:00:16] - When, how long ago did you cross the 60-second mark?
[02:00:19] - It's funny because it's like
[02:00:23] that the old limit on, what was it? It was a four-minute mile or something-
[02:00:28] - Yeah. Uh-huh
[02:00:28] - ... like that in 1952-
[02:00:30] ... that people thought was impossible for humans to beat. Then one guy beats it,
[02:00:34] and literally within the next few months, three more guys do, right?
[02:00:37] So we had this goal. I originally had the goal it was two minutes.
[02:00:40] And then we beat two minutes, and I'm like, "Well, if we beat two minutes, why can't we beat
[02:00:44] one minute?" And I remember thinking like, "That'd be crazy. You can't
[02:00:47] install a modern operating system in one minute when they're all..."
[02:00:52] If the other ones are taking 42 minutes, right? Like Apple,
[02:00:56] full of a lot of smart people, like, it took 42 minutes, so that's gotta be the bar.
[02:01:00] No, no, it's not the bar because there's no speed limit. Like, none of the things
[02:01:04] you take for granted are fixed pillars of reality in almost
[02:01:08] any case. Until you get down to the seven gigabytes
[02:01:12] per second that drive is able to transfer, you've not reached the limit yet,
[02:01:16] so you should just keep pushing.
[02:01:18] And of course, then it becomes a game in itself and a satisfaction itself.
[02:01:22] Every second I could shave off was an excitement. And when we broke the one-minute
[02:01:26] barrier, which was really only broken, I think,
[02:01:29] three weeks ago or something like that, maybe even two weeks ago, I just got crazy.
[02:01:33] And then I got a swarm of agents to run all these auto research
[02:01:37] loops of trying all these different theories on like, oh, if you change this thing, if you
[02:01:41] change that thing, what if you cut this out? What if you do things in parallel? What if while you
[02:01:45] were typing in your username, we start
[02:01:48] preloading packages into memory system, we can fire them in faster. And it becomes a
[02:01:51] fun game. And I think that's how you should think about product development. It should be fun.
[02:01:55] You should, it should be frivolous. It should be trying to overshoot
[02:01:59] the target and making it so much better than what it quote unquote needs to be.
[02:02:04] - Especially now because you can move so quickly and you can try so many different approaches because of
[02:02:08] the agents.
[02:02:09] - Yes, that just makes it more satisfying. But I think this was always true. If you look at the
[02:02:13] greatest Mercedes-Benz of all time, I think it was called the W126.
[02:02:18] I saw this wonderful documentary on it. It was steered by this guy who for years
[02:02:22] had worked in Mercedes' department for safety.
[02:02:26] And suddenly he gets put in charge for the whole S-Class project, and he
[02:02:30] just puts in all of it. This is where you got the auto-retending seat
[02:02:34] belts and washers on the headlights and
[02:02:38] everything. This car was so overbuilt for the market.
[02:02:42] It was unbelievable. But you look at that and go like, "Well, I want that."
[02:02:46] In just the same way that you look at a
[02:02:50] mechanical watch and go, "It could go down to 100 meters?"
[02:02:54] Or I think Rolex has one that can go down to 4,000 meters, the,
[02:02:58] the deep ocean, the deep diver ocean ... or whatever it's called.
[02:03:01] No one outside of three people in the world, whoever buy that watch, will
[02:03:05] ever put it to the test. But don't you wanna be the kind of person who
[02:03:11] is a patron of people who wanna push the human race that much
[02:03:15] forward? I want the fastest car breaking the speed limits. I want the
[02:03:19] diver watch that can go down the Mariana Trench. I want
[02:03:23] the operating system that can install in less than 60 seconds.
[02:03:26] - So from the individual level, I admire those people. I think
[02:03:30] everybody should strive for that. But also the consequences of that we should
[02:03:34] mention, like the pursuit of excellence, even when the metrics seem to be frivolous,
[02:03:40] the maybe unexpected consequences of that is other kinds of
[02:03:43] excellences, discoveries, innovations, and all that kind of stuff that has nothing to do with the
[02:03:48] speed.
[02:03:48] - 100%.
[02:03:49] - It's discovery. It's nice to have the metric that you're
[02:03:52] chasing be the catalyst, the engine that drives
[02:03:56] innovation, because you'll just discover. It's the same reason you go to the moon, you go to
[02:04:00] Mars. It's like, why? Who cares? Well,
[02:04:04] actually, the real thing is you'll discover a lot
[02:04:07] about chemical propulsion. You'll discover a lot
[02:04:10] about how humans can live for a long time
[02:04:14] in space. Maybe you'll discover whole new ways of doing solar energy in
[02:04:18] space or data centers in space or whatever the hell.
[02:04:21] - That's right.
[02:04:22] - All kinds of... Maybe you'll meet--
[02:04:23] - That's right
[02:04:23] - ...aliens, but you never know. But setting a goal
[02:04:30] and chasing it, especially when it's numerical, is really nice.
[02:04:32] - And setting a grand goal is even better. When you
[02:04:36] refuse to just do what's practical and you strive for what's slightly beyond
[02:04:44] plausible, that's when the magic happens. And we should be
[02:04:49] going all in on that. This is one of the reasons... And in fact, to some degree,
[02:04:53] this specific goal was motivated by seeing others do this. I mean,
[02:04:57] Elon is the singular individual in this conversation.
[02:05:01] The guy is so out there in his goals.
[02:05:06] They seem so preposterous at first glance. I've certainly
[02:05:10] considered them preposterous on many glances. And then you realize that
[02:05:18] they come true sometimes. Maybe not always on schedule, and so
[02:05:21] what? So what? So we didn't get the self-driving car on schedule.
[02:05:26] I gave Elon a lot of shit for that back in '17. But now it's here,
[02:05:31] and who would have gotten us here except for the person who thought it was
[02:05:35] possible in '17, who is so impatient with reality that the
[02:05:43] sheer force is just gonna propel that reality to the place he
[02:05:47] wants it to be. I think that's deeply inspiring, and we need these kinds of,
[02:05:52] goalposts to be moved. We need someone to run the four-minute
[02:05:56] mile, so the rest of us realize, "Well, okay, but I guess I can run it
[02:06:00] quicker." That's what I try to strive for, and I really strive for with Omarchy
[02:06:04] because
[02:06:05] it's just more fun to live that way, to have high aspirations and ambitions. And I
[02:06:09] will say I've actually changed my mind on that a little bit. I spent quite a lot of time
[02:06:15] speaking the other book that there are a lot of people who don't actually need those
[02:06:21] ambitions. And I also-- That's also true. We don't want
[02:06:26] 8 billion Elons running around the world. Would be rather crazy, I think.
[02:06:29] But I've come to realize that for entrepreneurs,
[02:06:33] it's healthy to have suitable chunky goals. The idea of just running the Italian
[02:06:41] restaurant can't just be that. It should be maybe
[02:06:45] I just run the one Italian restaurant, but I make the best damn pizza
[02:06:49] possible. I make the most delicious Parmesan.
[02:06:55] We have to strive for excellence to muster the motivation to keep going.
[02:07:00] - And yeah, to dare to think big like you could build a Linux-
[02:07:05] - Yes
[02:07:05] - ... distribution.
[02:07:07] Is there some stuff you remember about what it took to get us to be
[02:07:11] so fast? You mentioned a few things that were, the agents were discovering.
[02:07:15] - One of the things was to treat the
[02:07:19] ... lag of human input as an opportunity to preload. So--
[02:07:23] Hmm ... there's five questions you answer when- Yeah ... you set up an Omarchy machine.
[02:07:26] So it's doing stuff in the background. We're doing stuff in the background. And that was one of the things I didn't
[02:07:30] even consider, which is, I mean, the oldest trick in the book.
[02:07:34] All sorts of video games for a long time have done this, where you let the
[02:07:38] player interact with something, and then you do preloading and so forth in the background.
[02:07:42] So it's an age-old technique, but I just hadn't thought about it for an installer.
[02:07:45] I thought, first you ask the user some questions about their password and their
[02:07:49] username and their time zone and so forth, and then you do the work,
[02:07:53] when, in fact, you could preload that. Now, the other things were just a bunch of other
[02:07:58] tweaks to how the installer itself
[02:08:02] was doing things in a certain order. Some of them was also just shrinking it.
[02:08:06] The last version of Omarchy was 7.5 gigabytes,
[02:08:11] and a lot of the time we're down to now is literally
[02:08:13] decompressing compressed package files. That's the bulk of what is
[02:08:17] on the ISO, and that's the bulk of the install time. So by shrinking it down to, I think we're
[02:08:21] at 5.85 gigabytes now, a pretty chunky reduction,
[02:08:26] it almost literally translated one-to-one, and I did some really interesting things there.
[02:08:30] So Omarchy uses the JetBrains font, which is
[02:08:34] an awesome font, beautiful font, and actually a font I didn't like
[02:08:38] at first glance, but then it was the only font I could get to look
[02:08:41] perfect in Mitchell Hashimoto's Ghostty. Ghostty,
[02:08:45] for whatever reason, did not wanna render my beloved Bitstream
[02:08:49] Vera Sans just the way I was used to it. Mm-hmm. But it rendered
[02:08:55] this JetBrains font perfectly, so I switched over. But it...
[02:08:59] The standard package for JetBrains font on Arch
[02:09:03] is 200 megabytes because it includes all these variations and all
[02:09:07] these subtypes and whatever.
[02:09:09] And I realized, like, we're not using any of that. We're using the monospace
[02:09:13] version in this one Nerd, uh- Yep... font patched
[02:09:17] edition. Do you know how big that is? I think it's 16 megabytes. Hmm.
[02:09:21] So I simply just came up with a new package, the slim version-
[02:09:25] Mm-hmm... of the JetBrains package. Nice. And there, right there, I saved 180 megabytes.
[02:09:30] I just went through and did that a bunch of times. We did that with the NVIDIA
[02:09:34] drivers too. So the NVIDIA drivers, when they came straight off the, I think the
[02:09:38] Arch repo, were not compressed with the most extreme form
[02:09:42] of compression, which I think called ZSTD, which is a
[02:09:46] really slow form of compression. It's slow to create the archive, but if you're building a
[02:09:50] package- Hmm... you have all the time in the world if that means you can then shrink the ISO.
[02:09:53] So on just the two NVIDIA packages, I think we saved
[02:09:57] 200 megabytes. Mm-hmm. So what I loved about this
[02:10:01] was I imagined myself being a car designer at
[02:10:05] McLaren. So McLaren makes some of the lightest
[02:10:09] super sports cars in the world right now,
[02:10:12] and they are absolutely obsessed with shaving every
[02:10:16] damn last gram off their cars. That's why even a new 750S McLaren is just way
[02:10:23] lighter than the competition. They use a carbon fiber
[02:10:27] monocoque, and that helps them over like Ferrari, for example, that's
[02:10:31] uses aluminum. But they also just have this obsession with weight, and I would see this
[02:10:35] interview with the McLaren folks talking to some journalist just going over, "Yeah,
[02:10:39] we saved, uh- ... 370 grams- Yeah ... off that
[02:10:43] one." And I just went, "Wait, what? There's someone on a car that weighs maybe
[02:10:48] 1,040 kilos or 1,380 or something. They're s- They're worrying about
[02:10:55] 370 grams?" Yeah. What obsessed
[02:10:58] maniacs. Hmm. I love them. Yeah. I want that in my life. I want a McLaren-
[02:11:03] ... just for that reason. So I thought in that moment as I was shaving
[02:11:07] individual megabytes off the packages, man, I'm kinda
[02:11:11] like a McLaren car developer here, even though- Yeah ... I mean, we haven't even completed that work.
[02:11:15] The package could shrink even more. But this is actually this
[02:11:19] other conflict that we've had with Omarchy and the traditional Linux
[02:11:23] community is bloat. Mm-hmm. This idea that
[02:11:26] it's actually not kosher in certain circles to ship with
[02:11:30] pre-installed software because who are you to make decisions
[02:11:34] about what programs people should use? And I'm like, "Dude,
[02:11:38] it's in the fucking name. It's called Omarchy because the Oma part is
[02:11:42] short for omakase, which literally means chef's choice.
[02:11:46] I'm the chef. I'm making the choices, and this is the
[02:11:50] collection of applications I think is awesome," which by the way has a video
[02:11:53] editor. It ships with OBS- Mm-hmm ... to do your recording. It's just in
[02:11:57] there. Yeah. OBS is pre-installed. Nice. Kdenlive is a
[02:12:01] video editor, timeline editor, which is great. I edit all my videos with that. And then I made
[02:12:05] my own clip editor. You talked about the thing with syncing up.
[02:12:09] Yeah. I had this thing with clips, so I would do a podcast or whatever. I need a clip for X.
[02:12:13] Mm-hmm. And it's kind of a hassle to use Kdenlive or other- Mm-hmm ... timeline editors, so I made
[02:12:17] Omacut. Mm-hmm. Omacut is included too. Omacut, cool. It's just for making clips, and you can
[02:12:21] drive the whole thing with keyboard. So you can go to just the right time mark- Mm-hmm ...
[02:12:25] and then you can hit Control + Space. Hmm. It moves the clip line to that line.
[02:12:29] Then you go to- Nice ... the end of the clip, and you hit Alt + Space, and it moves the end line.
[02:12:33] Nice. And then you hit Control + S, and it saves. Nice. I can make clips so damn
[02:12:37] fast now with Omacut. It's amazing. But
[02:12:40] it has all the software on it. It has Neovim on it. It has Herder
[02:12:44] on it. It has Tmux. It has a terminal. It has a bunch of
[02:12:48] themes. It has a bunch of background images, the best ones I could pick
[02:12:52] out. That takes up some space. It should because this is not supposed to be this
[02:12:57] just barren landscape where you have to reconstruct everything. Mm-hmm. This is supposed to be
[02:13:01] a productive system the minute you unpack it. What is it built in?
[02:13:05] So it's actually mostly built in Bash for the
[02:13:09] Linux configuration part. Right. Bash is a great language for that.
[02:13:14] It is made for that really, for system administration.
[02:13:18] It also has its limitations. You should not build everything in Bash
[02:13:21] - How are agents with generating Bash? Pretty good?
[02:13:23] - Oh, amazing. Except for one thing,
[02:13:27] and I have to smack the agents over the back of the head every single time I catch it,
[02:13:31] and remind it to look at the agent's MD file, because I will have an
[02:13:35] instruction in there not to make early exits.
[02:13:37] The agents love to have preconditions instead of fully expanded conditionals.
[02:13:43] I like something that says, "If this, then do that."
[02:13:47] Agents like to have precondition or exit, another precondition or exit.
[02:13:53] And then it falls down to the final thing it actually wants to do. I hate
[02:13:57] that style. So except for that, it's gotten
[02:14:00] shockingly, dramatically, awesomely good, to the
[02:14:04] point where when we talked last time, we talked about how I would ask the agent
[02:14:08] for a Bash thing, and then I would type it in myself, and I kinda wouldn't remember.
[02:14:11] And then I took the effort to make sure that all that competence wasn't draining out of my
[02:14:15] fingers, so I actually learned how to write Bash myself, and now I'm not
[02:14:18] writing any Bash myself. I have not written any Bash myself for probably a couple months, because the
[02:14:22] agents have just gotten so good, that if you give them the few pointers on
[02:14:26] style, and occasionally put pushback on complexity... This is...
[02:14:30] I tweeted about this a couple of days ago. It blows my mind how
[02:14:34] often an agent can do something, say it's done, have the work reviewed by
[02:14:38] another agent-
[02:14:39] ... they say it's done, and then I go like, "Eh, looks a little too complicated for me."
[02:14:43] And then it'll go like, "Oh, yeah, you're right. You're right. I totally
[02:14:47] overcomplicated this," and it'll cut it in half. I'm like, "Couldn't it
[02:14:51] just do this, like, from the outset?" And then someone else reminded me,
[02:14:55] humans are the same way. If you work on something and
[02:14:59] someone else reviews it and they just are like, "Eh, it looks a little complicated," quite often you're
[02:15:03] able to go like, "Ah, you're right."
[02:15:05] - See, that, that just... Those little indications to me
[02:15:09] show that the programmer is still needed,
[02:15:12] that intuition, 'cause I think, what, what did you say? I have a sense of the landscape
[02:15:16] of the code.
[02:15:17] - When I build something like Omarchy, I, I do look at the code. I look at the shape.
[02:15:23] And I look at the proportions.
[02:15:24] Like, I don't have to chisel everything myself anymore. This is, again, when I'm flattering
[02:15:28] myself for... Not one moment I'm a McLaren audio,
[02:15:32] uh auto engineer, and the next moment I'm a da Vinci, working
[02:15:36] with his whole studio of students-
[02:15:39] ... who are doing all the chiseling on the, the fine marble, right? And he goes like,
[02:15:42] "Ah, no, the proportions are not quite right." That's how it feels working with
[02:15:46] agents now. That I can give feedback like an editor.
[02:15:50] That, do you know what? I'm not gonna write everything myself, but I can tell you
[02:15:54] when the argument doesn't land. I can tell you when the shape isn't
[02:15:58] proportional to the problem, or when it just feels like it's too complicated. And
[02:16:02] shockingly often, it just works. It's like the early days, where the jokes was,
[02:16:08] "Don't make mistakes." I don't think you have to tell the agents that anymore, because now the
[02:16:12] harnesses are so good, they run automated testing. They get that feedback. But
[02:16:16] you actually do have to tell them, "Make it simpler."
[02:16:19] - Do you use voice at all for the interaction? Or are you... How much are you typing?
[02:16:23] How much are you-
[02:16:23] - I type the whole thing. I actually, in Omarchy's built-in Voxtype-
[02:16:27] ... Audio transcription, and it's actually really good. I just find that
[02:16:33] I don't think that way, and it surprised myself that I
[02:16:37] don't like to talk to the computer.
[02:16:39] Uh, I like when I'm in the car, but when I'm in front of the keyboard, I just
[02:16:43] wanna type. I also just love typing. Are you using the voice?
[02:16:46] - I'm an introvert who doesn't like social interaction- ... or speaking. And-
[02:16:50] - I think that's part of mine too.
[02:16:53] - But, like, for me, for some reason, voice is really powerful. I want
[02:16:57] to give this... So I, I run with this thing. It's called Plaud. So
[02:17:01] I, I just hook it up on my, you know on my T-shirt here.
[02:17:05] You press a button, it starts recording. And this is actually more,
[02:17:09] in terms of flow, much better experience than behind a computer. And I,
[02:17:14] uh, save, well, usually it's agent gen- generated
[02:17:19] problems that I wanna really talk through. And so I write, I speak a long prompt,
[02:17:28] like, and a lot of it, it's like stream of consciousness reasoning. So I'll
[02:17:33] sometimes just change my mind about a design, but all of that is in there,
[02:17:37] and then I have an LLM that processes that. With Plaud, there's a,
[02:17:41] obviously an API. You can grab it, transcribe it, clean up the transcript,
[02:17:45] 'cause you, you want it to be... 'Cause I'm referring to files.
[02:17:49] I'm referring to technical concepts, like files and functions-
[02:17:53] ... and so on, that you wanna make sure the transcription, the-
[02:17:56] ... the speech-to-text gets correctly. So you wanna have a dictionary. You want it to be aware of the code
[02:18:00] base when you process the files. And then you have this gigantic
[02:18:04] thing that's often 10, 15, 20 minute me discussing the
[02:18:08] full design, and I find that to be
[02:18:12] really, really powerful. Because it doesn't have the
[02:18:16] problem overs- of overspecification because of how
[02:18:20] much stream of consciousness thinking the system has
[02:18:24] about what you're imagining. And this is really good
[02:18:28] for the early steps of a design. Like, if I wanted to build Omarchy from
[02:18:32] scratch, the first stages, I talk through. It could be an
[02:18:36] hour. There's been prompts that I had for an hour, and I'm just running and-
[02:18:40] - That's amazing
[02:18:40] - ... and speaking. I highly recommend people try a voice-based-
[02:18:48] - So-
[02:18:48] - ... speaking for prolonged periods of time.
[02:18:51] - I haven't actually-
[02:18:51] - As opposed to very specific
[02:18:52] - ... I haven't, yeah, I haven't used it that, and maybe that's how I'm using it wrong.
[02:18:55] I try to just type or speak two sentences, and
[02:18:59] then I get a little frustrated that I could've typed that just as
[02:19:03] fast maybe. But I have not tried this whole thing of just
[02:19:06] talking continuously for 20 minutes.
[02:19:09] - And especially you because you speak very fast.
[02:19:12] - Yeah. No, I could see it. I think because the reason I've been, I've been trying to
[02:19:16] do it for things like replying to emails,
[02:19:18] and it got to a point where I thought it could
[02:19:22] help. And it sort of did, but then it would make a small mistake, and I'd have to
[02:19:26] correct the mistake. But if you're doing stream of conscious to an LLM who doesn't
[02:19:29] care about all this other stuff anyway- ... that probably works way better.
[02:19:34] - There's two things you have to do. One, okay, you have the raw audio,
[02:19:37] transcribes it. I use ElevenLabs for transcription. They're probably the best
[02:19:41] speech-to-text model.
[02:19:43] There's still mistakes there, so you need to have a prompt that has a-
[02:19:48] access to a dictionary and to a lot of-
[02:19:50] - How do you build the dictionary?
[02:19:52] - First of all, there's a dictionary of terms that are relevant to you. Then have it
[02:19:55] aware of... So you have an agent that looks through, when you're talking about code,
[02:20:00] looks through your entire code base for key terms that you use often. Also, when
[02:20:04] we're talking about messaging, Gmail, and WhatsApp, and so on, it's aware of all the
[02:20:07] people and common terms that you get wrong.
[02:20:11] - You've really gone deep in this.
[02:20:13] - That, to me, is a problem that needs to be solved-
[02:20:15] ... because, uh, one of the issues you probably have speech to text
[02:20:19] is that it makes mistakes sometimes.
[02:20:22] - Correct. Then I can't use it for dictating an email.
[02:20:25] - Right. If it never makes mistakes, you-
[02:20:28] - Then it would be more appealing.
[02:20:29] - Yeah, and you are okay being not perfectly real time,
[02:20:32] actually. You're okay waiting five seconds-
[02:20:35] ... potentially. I don't know what your use case is. I'm okay waiting five
[02:20:39] seconds- ... 10 seconds for it to process everything.
[02:20:43] - You gotta vibe code this into an app that does all of this such that-
[02:20:46] ... it just works.
[02:20:47] - I think I mentioned to you offline that it's very surprising to me that,
[02:20:54] translation is not done perfectly. Speech-to-speech translation.
[02:20:59] - It seems like you've gotten much closer to the best of what's possible by putting all
[02:21:03] these things together.
[02:21:05] - But, you know, when you're shipping that kind of stuff, you do have to start
[02:21:09] thinking about latency.
[02:21:11] - Don't let the perfect be the enemy of good. I mean,
[02:21:15] if you're suddenly enabling something people wouldn't be doing before at all, it's okay to
[02:21:19] take five seconds longer. I think this is one of the areas that Steve Jobs was
[02:21:23] so good, that he realized, like, the first iPhone was terrible
[02:21:27] in all sorts of ways, right? Absolutely horrendously slow data connection, very
[02:21:32] underpowered, all the things. But the product was so
[02:21:35] compelling that it just didn't matter. You'd be shipping
[02:21:39] too late if you waited until everything was just right, just perfect.
[02:21:43] If you're solving a problem that people currently don't have a solution for, they're
[02:21:47] willing to give it five seconds.
[02:21:49] If you're in a competitive market, yeah, okay, it's different. But that means the problem's already solved, and you
[02:21:53] don't need to solve it.
[02:21:54] - Mm-hmm. Well, I do think there's a few... So, like, Whisper Flow is really good.
[02:22:00] A few people have stepped up that speech-to-text thing.
[02:22:02] - Yeah. Yeah, we're using Voxtype. But others have-
[02:22:05] - Uh, Vo-Voxtype is open source?
[02:22:07] - It is. It's just using one of the open models. I forget which parrot model
[02:22:11] it's using or something like that. It works quite well for short commands, so I
[02:22:15] have used it for that. Uh, I think you just hold down F9-
[02:22:19] ... and it starts a dictation.
[02:22:21] - Oh, so it's already in there?
[02:22:23] - You just have to get online. It'll offer you to install-
[02:22:25] - Got it
[02:22:25] - ... the Voxtype package.
[02:22:26] - Got it. Yeah, yeah, yeah.
[02:22:26] - Because the Voxtype package includes a model that's 150 megabytes, and I
[02:22:30] was like, "Ah."
[02:22:32] - Yep, yep.
[02:22:32] - "I don't know if I can carry that." So-
[02:22:35] - Yep
[02:22:35] - ... we don't have that in there by default, but we have the option set up.
[02:22:39] And I actually just yesterday was thinking
[02:22:43] we really need to combine all of these things. So Omarchy
[02:22:47] Quattro is truly amazing as a malleable operating
[02:22:51] system where you can add functionality to it just by talking to your agent.
[02:22:56] But that's exactly what we should be doing. There's a lot of people who would
[02:22:59] find it very natural just to talk to their computer and say, "Hey,
[02:23:03] can you make me a stock panel? I wanna track Apple and Dell,"
[02:23:10] and just see the agent go off
[02:23:12] through, entirely through voice, both in terms of the input and in terms of the
[02:23:16] output, and then your operating system just changes. This was the vision
[02:23:20] of Iron Man and Jarvis and-
[02:23:22] - Yeah
[02:23:23] - ... bespoke applications that just appear
[02:23:26] magically. I'm thinking the area of AI I find truly
[02:23:30] intriguing are these live gaming models, I don't know if you've seen that, where the
[02:23:34] AI's inventing literally the next frame, but you can actually
[02:23:38] play the game. And I think if they're able to do that, why can't we do
[02:23:42] that with our operating system? Why can't we just talk to it and ask it
[02:23:46] to be a different way or change, and it'll all just change? I think this, by
[02:23:50] the way, is one of the other breakthroughs that is going to lead to
[02:23:54] the total domination of Linux. The agents have taken all the hardship out of
[02:24:00] diagnosing Linux systems and turned the fact that Linux produces
[02:24:06] these overly specific, totally arcane error messages into its greatest advantage.
[02:24:12] When Linux has an issue,
[02:24:15] the agent can take that very specific error message that makes no sense to a normal
[02:24:19] human and correlate it with the fact that the agent was pre-trained on
[02:24:23] 40 million lines of Linux code, so it knows exactly where to look and dial it down.
[02:24:27] - Yeah.
[02:24:28] - I have not had a single problem on my Linux machine since
[02:24:32] the beginning of this year that an agent could not diagnose. That was
[02:24:35] not true a year and a half ago. A year and a half ago, I was
[02:24:39] still searching on forums- ... to find answers to esoteric questions.
[02:24:45] Now the agents know the source code of not just the Linux operating
[02:24:49] system, but every single piece of software I have on that box. The agent
[02:24:53] has access to the source code of all of it. In fact, this was one thing I built in just
[02:24:57] before we, uh, we shipped. So once you set up your default agent-
[02:25:01] ... Omarchy Quattro has a crash watcher. If
[02:25:05] any app on your machine crashes, it'll pop up a little
[02:25:09] thing, ask you whether you want your AI to diagnose the problem.
[02:25:13] - Yeah. That's amazing.
[02:25:14] - Unbelievable. I've seen things where there's an
[02:25:18] error in some subsystem. Some, some... Not even Linux, just some app I
[02:25:22] installed. The agents start digging through the logs and
[02:25:26] looks up systemd log. Then it checks out the damn source code.
[02:25:30] Of the application that crashed, pins down that it's in this
[02:25:34] Rust file line 472 that there's
[02:25:38] an unbounded, unwrapped variable that overflowed or whatever it is.
[02:25:43] Then offers you whether you wanna file a bug report with all this detail.
[02:25:49] I'll give you one amazing anecdote. So I was working with
[02:25:52] this guy JDX, who's working on mise. This, this package manager
[02:25:56] for fast-moving development tools. This is how we manage all the agent software and so
[02:26:00] forth. Normal package managers are not built to be updated seven times a day.
[02:26:04] And all of these agent harnesses are updated about seven times a day, so we
[02:26:08] needed an out-of-band package manager, and mise just turns out to be
[02:26:12] perfect for this. Anyway,
[02:26:13] it had a small bug. There was some race condition which agents are
[02:26:17] very good at finding because when you start running multiple agents at the same time, they will suss out all
[02:26:21] these race conditions you have in your underlying infrastructure that was never triggered by a human
[02:26:26] trying to do manual thing. So it finds this issue, right? I tell
[02:26:31] I tell the agent, "Hey, can you post this as a bug report to JDX's GitHub?"
[02:26:38] And unfortunately, right before that, I had had to do
[02:26:42] a QA run on Omarchy itself with eight different agents. It had found 28 real issues-
[02:26:48] ... that it needed to file. Well, it went to GitHub and tried to file all
[02:26:52] 28 issues at the same time, which it did in about,
[02:26:56] uh, I don't know, 12 seconds. GitHub, not
[02:27:00] unreasonably, marked that as probable spam and banned- ... my Omarchy bot.
[02:27:05] And then I couldn't do that. So
[02:27:07] I was blocked from the bot having access to GitHub, so I just told it, "Hey, do you know
[02:27:11] what? Just email JDX. Here's his email address." I had
[02:27:15] already set it up with hey.com-
[02:27:17] ... an email address. We have a CLI that's in beta right now.
[02:27:20] So I set it up with that so it can send to email. That's how it gives me reports about
[02:27:24] outstanding issues and PRs. So it sends,
[02:27:28] um, JDX this email about the bug it found, and he was like,
[02:27:32] "Wait, this is the first time I've gotten a bug report in unreleased
[02:27:36] software." Because it had downloaded the source code to mise,
[02:27:40] saw that he had already fixed the bug, but that it would not fix the problem
[02:27:44] entirely in software they had not shipped yet.
[02:27:47] Pinpointed the problem, and he was like, "Damn it-
[02:27:50] ... I got a bug report before we even cut a release."
[02:27:53] - That's amazing. That's amazing
[02:27:54] - ... believable AGI levels of mind-blowing stuff.
[02:27:58] - And that was actually, if you remember, that was an open question
[02:28:02] whether AI systems could debug well.
[02:28:06] That was kinda the thought that, yeah, sure, they can write code, but can
[02:28:09] they find issues and-
[02:28:10] - They are so incredibly good at this, and this is actually interesting
[02:28:14] because I was on the perhaps same side of that, a little skeptical about
[02:28:18] can it reason about all these things. And Mikhail, who's the CTO
[02:28:22] at Shopify, ran a scientific study on this.
[02:28:26] They had... And this was, I think, late last year or early this year, where he
[02:28:29] had agents go back through all the incidents, both outages and,
[02:28:33] and other problems that Shopify had had in production, trace that back to the
[02:28:37] PR that was merged, and find out whether PRs that had been
[02:28:41] reviewed by human or PRs that had been reviewed by
[02:28:45] agents were of higher quality. Well, lo and surprise-
[02:28:50] ... the PRs that have been reviewed by agents caused far fewer
[02:28:54] issues in production. And this was with models we had six
[02:28:58] months ago. At this point, 100% in the
[02:29:02] majority of domains we work in today, agents are better at finding bugs.
[02:29:06] - So you now run agents all day.
[02:29:11] What stands out to you as the better model? Who's currently winning?
[02:29:14] It seems to be changing constantly. Sol, Fable, Grok 4.6, Gemini, the Chinese OpenWay
[02:29:21] models.
[02:29:23] - What's amazing to me is that you could rattle off so many different contenders.
[02:29:29] That this market is so wide open, that it
[02:29:33] does actually change back and forth, that we have real
[02:29:36] competition, that there are so many labs that are able
[02:29:40] to get either to the frontier or close to it.
[02:29:44] That, by the way, is remarkable. I still don't fully understand that.
[02:29:48] But to answer your question, the best model in general right now is Fable.
[02:29:54] The second-best model, in my opinion, is Opus 5. But
[02:29:58] the tier just below Opus 5, and
[02:30:02] it's not even that they're always below, sometimes they're ahead.
[02:30:05] I'll get to that in a second. I would rank GPT Sol very good.
[02:30:12] Grok 4.6 I just started testing a few days ago. I had
[02:30:16] this wonderful test that I've set up by accident
[02:30:20] where I translated this Python library into Rust. Uh,
[02:30:24] the screensaver you just saw with all the cool animation?
[02:30:28] That's powered by a Python library called Terminal Text Effects.
[02:30:32] Really cool library. We've been using it since the first day of Omarchy.
[02:30:36] The problem with that is it's written in Python, so when it starts up, especially on a
[02:30:40] laptop, and it runs in Python, it uses all of your CPU
[02:30:44] to do these effects, and therefore, it means it uses about 30 watts
[02:30:48] of energy, and it spins up your fans, and it drains your battery.
[02:30:52] Doesn't really matter on a local computer, but it does matter on a laptop. So I thought, "Do you know
[02:30:56] what? This sounds like a problem for Rust." So first I gave Fable the challenge,
[02:31:03] and all I told it was, "Here's the source code for the
[02:31:06] Python library," this TTE library that had a bunch of dependencies and so forth.
[02:31:11] "I want a Rust version of this with no dependencies, a
[02:31:15] single executable." Like, that's what Rust does. So basically, I want it in Rust.
[02:31:19] I want it to be pixel perfect, frame by frame, do a full
[02:31:23] analysis, don't stop until you're finished.
[02:31:26] - Yep.
[02:31:26] - That was the prompt.
[02:31:27] - Yep.
[02:31:29] - I kid you not, in just under 45 minutes, it was like
[02:31:34] Am I heard all? I'm finished. I've checked everything.
[02:31:38] I have reduced the startup time from 86 milliseconds to two
[02:31:46] milliseconds. I have sped up the execution time by
[02:31:51] 9.6 times, I believe it was. The executable is three megabytes. Do you wanna run it?
[02:31:59] - That's awesome.
[02:32:00] - So I run it—
[02:32:01] - Oh, man.
[02:32:02] - ... and I don't know why I'm surprised, because this
[02:32:05] translation job is something we've known for a while that AI is
[02:32:09] pretty good at, but it was still staggering to me that I could one-shot
[02:32:14] a full translation of a Python library I
[02:32:18] had been using for a year, that others had been using for much longer,
[02:32:22] and turn it into a Rust executable without knowing any Rust,
[02:32:26] without looking at the Rust code at all, and produce this
[02:32:30] executable that I then told the agent right after, "This is great. Ship it."
[02:32:35] It packaged it up as a new package. It told me, "What do you want it to call?" "Uh, let's call it
[02:32:39] TTFX. Let's create a new Git repo." It sets up the Git repo. "Let's create
[02:32:43] a new package, build package for our build system." It puts that
[02:32:47] up. "Let's push it out. Let's open the pull request
[02:32:51] to the Omarchy itself so we switch around from TTE, the Python implementation, to
[02:32:55] TTFX." It does all of it,
[02:32:58] and I'm just sitting there. And again, I'm already at this point fully
[02:33:02] delirious with agent acceleration, and I still had to lean back and I go like,
[02:33:07] "This is AGI, isn't it? This is what AGI looks like.
[02:33:11] If we have... If these moments are just what it is all the time, this is AGI."
[02:33:15] - Now, as I understand, you also repeated the same experiment not just with Fable.
[02:33:21] - I did it on all the models. First, I did it... Actually, funny thing.
[02:33:25] So I ran out of Fable tokens about two-thirds
[02:33:29] through, and it just automatically switched over to Opus 5 and kept going and finished
[02:33:33] the job.
[02:33:34] Part of the reason why I think it was able to do that was that the first thing
[02:33:38] Fable did was create a plan,
[02:33:40] and it was a really detailed plan. I think it had eight separate steps of, "Here you do it,
[02:33:44] and here, how you analyze it, and here you run the effects," and so on. I didn't review the plan at all.
[02:33:48] I didn't change the plan. It just made the plan so Opus could take
[02:33:52] over. And then I thought, "Well, if Opus can finish the job,
[02:33:57] maybe some of the other agents could finish it, too." So the first thing I did was
[02:34:01] I gave it to... I think I gave it to Sol.
[02:34:05] And Sol finished the job, too. It took twice as long, so it took, I think, about an hour
[02:34:09] and a half. But
[02:34:11] here's the kicker. The per token cost, I didn't pay per token. I have a
[02:34:15] max subscription to Claude, right? So it did it within the subscription. It used all my
[02:34:18] tokens, so I had to switch over to Opus 5. But if I had paid per
[02:34:22] token, it would've been 550 bucks, I think, to do the whole thing. And I
[02:34:26] thought for a second, "Holy shit. What a steal." If I
[02:34:30] personally had to learn Rust well enough to be able to do this
[02:34:34] translation, I'm looking at a nine-month job here.
[02:34:39] I can pay 500 bucks to have this translation happen, and suddenly I get a
[02:34:43] 10x execution speed up. This is ama- I would totally pay 500 bucks for this.
[02:34:48] But competition. So I give it to Sol.
[02:34:52] Same plan. To be fair, I didn't ask Sol to do the plan. I just took the Fable plan,
[02:34:56] gave it to Sol. Sol, in an hour and a half, and I think $46 worth
[02:35:04] of token, repeated the task. Did the same thing.
[02:35:10] And I thought, "Well, blimey, that's amazing." Then I got greedy.
[02:35:17] So I asked GPT Luna, which is this crazy cheap model that OpenAI has as well,
[02:35:27] "Can you do it?" Absolutely not. First of all, it didn't even wanna
[02:35:30] start the task. I think something happened I don't know. I think
[02:35:34] it was in the spring, where we didn't need these slash
[02:35:38] goal things anymore. The agents could just automatically keep going in a loop if you
[02:35:42] told it not to stop-
[02:35:44] ... and so forth. So Sol could do that. Fable could do that. But
[02:35:48] Luna couldn't. So I had... I think I did
[02:35:51] 12 prompts. Kept telling it to do it, and eventually
[02:35:55] I sorta got it started. The first thing it did was to cheat. So the
[02:35:59] first thing it, it looked outside its own directory, saw that there was already another imple-
[02:36:03] implementation, and just did a short wrapper around that and said, "I'm done."
[02:36:07] Hilarious. But it couldn't finish because it made just a couple thing. But I mean,
[02:36:12] okay, so it can't do that. Then I gave it to Grok-
[02:36:15] ... 46. And I had used Grok 45 a little bit, and I thought like, "Ah, I mean,
[02:36:21] it's cool that there's others trying, but, like, I'm not gonna use it," because it
[02:36:25] felt quite far behind. Grok 46 fucking completes the task.
[02:36:30] 10x speed up, same size executable. $55 Worth of per token cost, I think it was.
[02:36:37] Absolutely unbelievable. Then I repeated, too, with, uh, Kimi K3-
[02:36:43] ... which took forever. I forget how long Kimi actually spent on
[02:36:47] it. And then I also did it with DeepSeek V4 Flash first.
[02:36:51] And Flash failed the same way that Luna did. It couldn't do it. And then I did it with Pro,
[02:36:56] and Pro also completed the task. It took 2 hours 45, $23.
[02:37:02] So here we are, right? Like, Fable, clearly the best. It was the
[02:37:05] fastest. It was the one that wrote the plan, but 550 bucks, and the output the same.
[02:37:12] Uh, the others, Sol, Grok, about the same 1/10 the cost.
[02:37:19] DeepSeek, 1/20 the cost, but you have to wait a little longer.
[02:37:24] Absolutely gobsmackingly incredible.
[02:37:29] And now, by the way, by the way, so I had Fable finish the first job, and then Opus finished
[02:37:33] it. That was the first one shot, right?
[02:37:35] It's 10 times faster. I did two auto research runs, which isn't
[02:37:39] even auto research anymore. You don't have to do the slash. You just tell it to keep going
[02:37:42] until you tell it to stop.
[02:37:45] It ended up... I think we ended up with a 46 time execution
[02:37:49] improvement over the original.
[02:37:51] - It's incredible.
[02:37:52] - Absolutely incredible.
[02:37:52] - It's just incredible.
[02:37:54] Um, I do, you know, I just don't think there's anything that compares to Fable
[02:37:58] in terms of planning. So I usually do Fable for planning and for reviewing,
[02:38:05] and then something else for implementation, like Opus 5.
[02:38:08] And it's really nice. It's a, it's a really nice setup that allows you to
[02:38:12] not run out of tokens too much.
[02:38:14] - What I found, it's really interesting because Fable is, in
[02:38:18] my opinion, the best model right now, but it also makes mistakes. And the
[02:38:21] best way to get the best software, I would actually rather
[02:38:25] have two differently sourced sort of... I mean, they're not
[02:38:29] mid-tier, they're all frontier. But have, let's say Opus 5 and Codex-
[02:38:35] ... and have one check the other's job. This is my standard operating procedure now.
[02:38:40] I'll have Opus or Fable do the work, and then I always end it, review
[02:38:45] with Codex xHigh.
[02:38:47] And I've also started using Grok just to test it out, and it's also quite good. And it keeps finding stuff.
[02:38:51] And then that's my workflow when I'm having my agents on my own
[02:38:55] machine do it, and then I push to GitHub. And then Copilot, I kid you not, has
[02:38:59] actually gotten good. Copilot keeps finding stuff that's
[02:39:03] legitimately broken, which is also incredible acceleration because the
[02:39:07] first version of Copilot that started doing this was literally
[02:39:09] retarded. It would just constantly flag things that were nonsense.
[02:39:13] It would constantly flag the same problem over and over again as you would push. It was really annoying, so
[02:39:17] I think a lot of people actually ended up turning that off. And if they did, they should turn it back
[02:39:21] on because it's actually quite good.
[02:39:24] Keeps finding things. And if you then take that, and we shouldn't be surprised. Why are we
[02:39:27] surprised? Even if you're a good programmer, if you finish a job
[02:39:31] and you ask your also very good peer to review it, you're gonna
[02:39:35] end up with better code. Of course you're gonna end up with better code. So build that into your process.
[02:39:39] Pick one of the agents to drive with. I've mainly been
[02:39:43] driving with Claude, which is actually interesting because I have some other
[02:39:47] reservations about Anthropic. But the reason I'm sticking with Claude is, in my
[02:39:51] opinion, they actually have the best harness.
[02:39:53] And one of the reasons it's the best harness is it's
[02:39:57] multi-agent running. So if you wanna run multiple agents at the same
[02:40:01] time, you can do arrow left when you're inside a session,
[02:40:05] then it goes back to Agent View. And here in Agent View, you can pick up another agent.
[02:40:08] So if you wanna do this thing where you have multiple threads going on-
[02:40:11] ... the Claude Code is just the nicest setup. They also just, they keep being a
[02:40:15] little further ahead, which probably shouldn't be surprising. I mean, Boris is one of the
[02:40:19] guys that's working on that, he was the first one and basically came up with the thing.
[02:40:22] It's just interesting that that has been an enduring advantage. I've also used
[02:40:27] OpenCode a lot.
[02:40:27] I think OpenCode is great. I use OpenCode mainly as my main harness for all the
[02:40:31] open models, so Kimi K3 and so forth. And I inference not on the Chinese servers.
[02:40:40] So I inference on Fireworks-
[02:40:43] ... which is a really nice service where you can just pay by the token, and
[02:40:47] if you're using these open weight models, they're not that expensive by token.
[02:40:50] So that's a great way to do that. But I don't think I would be using...
[02:40:54] Well, maybe I would. But if...
[02:40:58] Using Claude with a subscription does feel like a bargain, like a crazy bargain.
[02:41:03] - Yeah, I knew. And I actually have four.
[02:41:06] - I just signed up for my second one this morning-
[02:41:09] ... because I got up at 4:00 with jet lag, and I started working with the agents right away, and
[02:41:14] now I'm three days away from limits resetting on Fable, and I ran out of tokens.
[02:41:19] - So and they should really— they—
[02:41:22] - I mean, I don't... Why is that so complicated? Can't you just stack one subscription?
[02:41:25] Why do I need to log in multiple times?
[02:41:26] - And obviously you'll have to develop some kind of tooling-
[02:41:30] - Yes, I did that too.
[02:41:31] - ... to move from one- ... to the other. And then-
[02:41:33] - Oh, we're building that into Omarchy, by the way. So the next version of Omarchy is gonna ship with
[02:41:36] multi-sub support. I wish that the labs would just make you buy a max 100 times.
[02:41:43] - It's kind of actually fascinating though for me because there's...
[02:41:48] It's very challenging for me to use Grok 46
[02:41:52] and then a Claude Code because Grok is so fast.
[02:41:57] - Yes. That's actually the deal. The deal with Grok is that their fast
[02:42:01] mode is cheaper than the regular mode on the others.
[02:42:05] And when you've used Grok 46 on fast, it's kind of addictive 'cause
[02:42:09] it almost gets you to this single thread mode-
[02:42:12] ... where the agent is able to keep up with you.
[02:42:14] - Yeah, but I don't know how... I can't... Once I get used to Claude Code,
[02:42:18] uh, I can't handle the speed of Grok 'cause I'm used to now multitasking.
[02:42:24] And so now I'm back in this- ... anxious mode of, uh-
[02:42:27] - Yeah. No, I agree.
[02:42:27] - ... switching. So I mean, all of this is a learning a
[02:42:31] learning process of what programming actually is supposed to look like.
[02:42:34] - By the way, one of the reasons why I'm not sure what the final form of these harnesses is gonna
[02:42:38] take, because one of the things we've started experimenting with at Base Camp is that we put
[02:42:42] the agents inside of Base Camp, and we treat them as coworkers.
[02:42:45] - Yeah. That's awesome.
[02:42:45] - And then we assign them tasks-
[02:42:47] - That's awesome.
[02:42:47] - ... inside of Base Camp, so they will do work on a to-do in Base
[02:42:51] Camp, or they'll work, do work on a card. And it turns out that
[02:42:55] a collaboration tool that's optimized for asynchronous communication is
[02:42:59] actually the right format versus these harnesses are a little more like chat.
[02:43:05] And chat, which was, I mean, the original format for these things, is
[02:43:09] not the right thing because you're sitting around waiting. It entices you to sit
[02:43:13] around and wait, versus when you're dealing with something like Base Camp and you can just give
[02:43:17] an agent a to-do item, you don't expect to hear back immediately.
[02:43:21] So I don't know what the final form is gonna take, but I've been using all of the harnesses.
[02:43:24] So I use them inside of Herdr, and Herdr has panes. So oftentimes I'll
[02:43:28] run Claude up top, and then I'll run Codex
[02:43:31] down below, and then maybe I also have an OpenCode set up. But
[02:43:36] I will say just very recently, I found that the human in the
[02:43:40] loop is the limit here.
[02:43:42] So I've started setting up more automated systems. I've been building an Omarchy bot
[02:43:46] that can do more autonomous development on Omarchy that is just
[02:43:50] On a regular schedule process, all depending to do or PRs and
[02:43:54] issues, and then send me an email using the Hey CLI,
[02:43:58] and then I just get this email. Here's 12 PRs that are either ready to
[02:44:02] go or I think you should close. And then I just make the final determination there.
[02:44:06] - Do you find the multitasks, the task- switching mentally exhausting?
[02:44:10] - Yes, but in an exhilarating way. Like, one of the things I always loved about
[02:44:14] race cars was when I would stumble out of the car absolutely
[02:44:18] smashed and barely able to hold my head up, and I'd lay down on the
[02:44:22] garage floor and just think, "Holy fuck, I'm alive."
[02:44:26] That's the kind of exhaustion, mental exhaustion I'm feeling at
[02:44:30] moments with the agents right now.
[02:44:31] - By the way, when you're racing, where, what's the source of the exhaustion? Like-
[02:44:34] - It's physical. It's just... I mean, I
[02:44:37] bet it's the same thing with jujitsu, right? Like, it's actually satisfying to
[02:44:41] feel exhausted. It feels like you've applied yourself.
[02:44:44] And I feel that with the mental exhaustion you can get from agents.
[02:44:48] - Are you also mentally drained from racing?
[02:44:49] - Yes. If you drive in difficult conditions, especially if you drive in the rain, where you're
[02:44:53] constantly managing the thing right at the knife's edge. But
[02:44:58] most of the time, I just enjoyed the physical exhaustion.
[02:45:01] - And here, with the multitask switching, I do find that, like,
[02:45:05] I get really exhausted, and I think it's because I'm thinking a lot.
[02:45:11] 'Cause, like, you're basically-
[02:45:13] - That's exactly it.
[02:45:14] - ... there's no, like passive low energy thinking.
[02:45:18] - No.
[02:45:18] - You're like-
[02:45:19] - There's no coasting.
[02:45:19] - ... problem.
[02:45:20] - There's no coasting.
[02:45:21] - Solve problem, next problem, solve problem, and you're really thinking.
[02:45:25] - It's funny. It's actually very similar with racing. There's some tracks, like Le Mans,
[02:45:29] where you get time to relax. There's the Mulsanne straights where it's kinda
[02:45:33] long. You're going fast, but in a straight line, you can take a breath.
[02:45:37] And then there are other tracks where it's just coming full on all
[02:45:41] the time, and you don't have any moment to relax, and you stumble out of
[02:45:45] the car after an hour in each, and it's very different how exhausted you are. And this is
[02:45:49] exactly what I'm finding with the agents too, that when you're running at max
[02:45:53] human capacity- ... you're just constantly in a corner.
[02:45:57] - Do you think people are in danger of burnout?
[02:46:01] - I think the moment we're in right now is gonna pass. That this need to...
[02:46:09] It's not a babysitting motion, but constant interaction with the agents is
[02:46:13] gonna fade. From what I've seen on Omarchy, I think we can
[02:46:18] automate a ton of the development and debugging of the system-
[02:46:23] ... to the point where I can just review that email
[02:46:27] once a day, and then make the decisions once a day. Yep, goes, no,
[02:46:31] goes, in, out, and whatever. We're not there yet, but I think we're gonna get there.
[02:46:36] - Well, can you sort of, like, empathize with the feeling that,
[02:46:40] say, a young person sitting in San Francisco, everybody around them is not
[02:46:43] sleeping. They're obsessed. They're programming nonstop.
[02:46:46] And there's this kinda sense, that AGI is gonna be here
[02:46:52] any minute. There's, everybody knows somebody who's made millions of dollars
[02:46:56] because they sold a startup. And so
[02:47:00] there's a kinda feeling like you shouldn't be sleeping.
[02:47:04] You should be constantly managing agents and programming and building and,
[02:47:09] and that feels like a moment in time we'll look back at.
[02:47:14] - It's the birth of a new paradigm. It's always messy.
[02:47:16] - It's always messy.
[02:47:17] - It's always exhausting. There's no other way around that. And by the way,
[02:47:21] hasn't San Francisco always been like this?
[02:47:23] I remember the dotcom boom years, and everyone was just the same, and then
[02:47:27] it was all mobile, and before that it was the gold rush. So I think that's probably-
[02:47:30] ... just San Francisco. It attracts- ... the kind of individuals-
[02:47:33] - The dreamers
[02:47:34] - ... who would, who would think, "I don't have time to sleep." I've not been on that track,
[02:47:39] generally speaking, but I will admit that
[02:47:42] the last three months have felt more exhausting than
[02:47:47] any other project I've done in the last five years, since the Hey launch. That was the
[02:47:51] last time we had a crazy exhausting launch.
[02:47:55] - Do you think you can keep going at this pace?
[02:47:57] - No, no, no, no, no. This is not sustainable at all.
[02:47:59] - Okay.
[02:48:00] - But I also, I can see the end of the tunnel.
[02:48:02] Because the automation, which by the way, everyone is building. This
[02:48:06] is so hilarious. Like, everyone is building their little gas town, their little
[02:48:10] agent coordination, their setup. This is all gonna be solved. We're not all gonna have to
[02:48:14] build our own coordination harnesses. Of course we're not. And in fact, I'm
[02:48:18] a little surprised that it's gone this long, that there's not more of it has been
[02:48:22] sucked up by the major labs. You'd think that they'd just built this stuff in.
[02:48:26] But some of it is also this is what a new domain looks like. I remember for a hot moment when
[02:48:30] JavaScript kind of came to realize its own power, and there
[02:48:34] was basically a new JavaScript framework every five minutes, right? Like, a lot of churn.
[02:48:38] This is what happens at the advent of a new paradigm.
[02:48:41] So I think it's natural, and I think it's gonna settle down, and I can already see the light at the
[02:48:45] end of the tunnel. So I don't mind a sprint. In fact, I welcome it now. I
[02:48:49] like this notion that most time is calm, but then
[02:48:53] occasionally you gotta climb a mountain.
[02:48:56] - If we look back to the DHH a year ago, what advice would you give to that guy?
[02:49:03] - I wouldn't wanna spoil it.
[02:49:04] - Okay.
[02:49:04] - What a- ... thriller that this has been.
[02:49:09] I mean, if you would've scripted this, I'd be like, "This is so far-fetched. Get
[02:49:14] out of here. Unbelievable," right? I wouldn't wanna know anything. The
[02:49:17] fact that this rollercoaster and this acceleration has
[02:49:21] been absorbed in real time by everyone, no one
[02:49:24] knew, right? Like, some had premonitions that were a little
[02:49:28] better than others, but no one knew, not exactly the way-
[02:49:31] ... it was gonna go and how fast it was gonna take off.
[02:49:34] I mean, it's the show of a lifetime. I mean, the mean cinema-
[02:49:40] ... absolutely applies-
[02:49:41] - Yeah, it's incredible.
[02:49:42] - ... to this moment.
[02:49:43] - Uh, that said, what do you think DHH from a year from now will be like?
[02:49:49] I mean, what are the possible versions?
[02:49:52] - That all our dreams are coming true. Like, this is the AI
[02:49:56] maximalist abundance argument. That once Elon's robots
[02:50:04] have the level of intelligence and AGI that I'm experiencing on some of
[02:50:08] this development stuff, the world is gonna be so
[02:50:12] unrecognizably different that we can't even imagine it.
[02:50:17] Now, I don't spend any time thinking about that because I think that is the way to
[02:50:21] the AI psychosis. So therefore, I just immerse myself in the moment and get
[02:50:27] absolutely the maximum out of it and-
[02:50:29] - Just have fun.
[02:50:30] - Just have fun.
[02:50:32] I mean, I get it why people are finding this exhausting. Just keeping up.
[02:50:35] Not even using agents, just, like, being like, "What's the latest model? What did, what
[02:50:39] tool are we using now? Is it TMox? Is it a Herder? Is it none of it? Is it
[02:50:42] agents?" Whatever. I get it, but I also again think we should be so blessed.
[02:50:49] You are alive in this moment where decades are happening- ... in weeks.
[02:50:54] - Um, quick bathroom break.
[02:50:57] I've been generating a lot of video recently with Higgsfield,
[02:51:01] and so they, they became a sponsor. Created a racing video.
[02:51:05] Wanted to get your opinion on it.
[02:51:06] - Oh, yeah? Oh, let me see. Let me see.
[02:51:08] - To see, um-
[02:51:10] - If they downshift on a straight like they do in the movies, I'll call it out. That is the
[02:51:14] worst. Let me see.
[02:51:16] - Yeah, see if-
[02:51:18] - Oh, that's a real clip
[02:51:19] - ... this is fully AI generated. So first it goes-
[02:51:21] - Wait, what? This is AI?
[02:51:23] - Yep.
[02:51:25] - Shit, that's my suit. That's my car.
[02:51:28] - Lights go green on a street that never sleeps.
[02:51:35] - Oh, my God.
[02:51:36] - Do an audio-
[02:51:37] - Are you kidding me?
[02:51:39] - But they never came. Is it good? I got a bad case.
[02:51:44] - I mean, it's crazy. You really have to notice in the...
[02:51:51] Like, that car didn't have headlights on and the other one did.
[02:51:54] And that looked like a 60-year-old version of me. But holy crap, the...
[02:52:01] Wow, that was crazy.
[02:52:03] - So there's parallels here to programming because if you do just straight
[02:52:07] video generation with no human in the loop- ... you get a lot of weird artifacts-
[02:52:12] ... and so on, and you can't really do... So they do and I highly recommend people
[02:52:15] go to the Higgsfield YouTube. They have full 90-minute original movies.
[02:52:22] And, like, I can't look away. It's really cool. 'Cause it
[02:52:26] used to be that it's just, like, something that just feels like trailers.
[02:52:30] Like advertisements for something.
[02:52:32] - Yes, yes.
[02:52:32] - This is actually telling stories, like, people's faces and they're talking and you're like,
[02:52:37] you're drawn in. It's not quite where programming is.
[02:52:41] And so the question is how do you integrate the human into the loop of the
[02:52:45] filmmaking process? So you have to create the people, and they're-
[02:52:48] ... they have to be kept consistent.
[02:52:51] And then for the images that are kinda like feeding the
[02:52:55] thing in the creation process, you have to correct through
[02:52:59] prompting things that don't feel right.
[02:53:04] Because when you go from image to video, the stuff that doesn't feel right will be-
[02:53:11] - It's gonna be zoomed up, right?
[02:53:12] - That's the stuff that's- ... going to really create, uh-
[02:53:15] ... the non-realistic stuff. The questions I had for you is, like, do you think
[02:53:19] outside of programming, can you apply lessons from
[02:53:23] programming to video creation, to art?
[02:53:27] - It's a good question because I think good art is very dependent on the
[02:53:31] same thing that good software is depending on: having a vision, having a
[02:53:35] cohesive idea of what you wanna create.
[02:53:38] How is it different? How is it novel? How is it going to appeal to people?
[02:53:43] But I'm not sure that the creative instincts transfer quite as well. Um,
[02:53:51] I don't know that I would have the creative
[02:53:55] insights to come up with good video prompts that would create compelling
[02:53:59] content. But it's funny because I have actually, on TikTok, there's this guy, I'm trying to remember,
[02:54:03] Goblin something.
[02:54:05] That creates these... They are shorts, but not super short, maybe a couple minutes,
[02:54:10] of really interesting sci-fi vignettes.
[02:54:15] And I think the guy is actually working on a feature-length video right now.
[02:54:20] Um, and I think that this is one of those abundance moments. There
[02:54:24] are creative people with that vision all over the place,
[02:54:28] especially in a genre like film, where before it
[02:54:31] required a $200 million budget to create, I don't know, a
[02:54:35] sci-fi movie. Now suddenly, with AI, if
[02:54:39] you have the right vision for it, you can do that in your
[02:54:43] bedroom. Now, that story's been told quite a few times in other domains. It used
[02:54:47] to be true that if you wanted to record a studio album, well, you needed a
[02:54:51] studio, and you needed to book that. And now you can record at home on your
[02:54:55] laptop, and you can do a lot of these things, right? So we've had this democratization
[02:54:58] process happen
[02:55:00] with plenty of other domains, but film seems to be one of the last ones.
[02:55:04] - And it's the one that makes, like, me and a lot of people feel weird, right? Like-
[02:55:11] - Oh, I'm super excited 'cause I think it's-
[02:55:13] - I mean, you-
[02:55:13] - There's so much garbage being produced right now. It's the same argument with the slob,
[02:55:17] right? So people for a second were worried about slob in
[02:55:20] programming, and I was telling them, like, "Have you seen the human
[02:55:24] slob? It's also pretty bad." And I think if it comes to
[02:55:28] studio entertainment, I mean, the bar is pretty low, right?
[02:55:32] Like, the number of great movies I've been dying to see over
[02:55:36] the past, say, five years, not been a particularly high number.
[02:55:42] - Yeah, the video models are just, they're able to create incredibly realistic
[02:55:49] facial expressions. I mean, it just might change the nature of film
[02:55:55] I think they're— I guess my hope would be that video
[02:55:59] games and film kind of merge, and that film can become interactive
[02:56:06] - Like the malleable operating system, having the malleable
[02:56:10] narrative, having malleable entertainment, that
[02:56:13] man, Game of Thrones, what if we could just
[02:56:16] forget the last four episodes of slob that was produced- ... and then AI-
[02:56:23] ... comes up with- ... I don't know-
[02:56:25] ... maybe 100 different variations, and someone else watches that,
[02:56:29] and I get the version that actually finishes off that show in a way that's fitting.
[02:56:34] - Yeah. Something tells me an individual creator would not create those la-
[02:56:38] would create a different ending for Game of Thrones.
[02:56:40] - Oh, for sure. Right? And more just to make the argument that talk about
[02:56:44] human slob. That was an absolute atrocious ending to
[02:56:48] perhaps one of the greatest pieces of,
[02:56:52] Movie history, I was about to say, but, um, series history, right?
[02:56:56] It was so good, and it was actually a compelling argument for the fact that you
[02:57:00] need
[02:57:03] that strong vision. And as soon as those showrunners had to go without a script,
[02:57:08] it went off the rails.
[02:57:10] - Do you think... You've mentioned AGI. Do you think we've actually achieved AGI?
[02:57:14] - No, not in the general definition that it's in all the things. But have I seen
[02:57:20] AGI in these glimmers? Absolutely.
[02:57:24] Especially over the last three months, I've seen things where
[02:57:29] I was thinking to myself, like, "How would AGI look different from this?"
[02:57:34] - Right.
[02:57:34] - What, what more could there be? And I mean, I can quibble at the margins,
[02:57:38] but on the big picture, I've seen it able to do these long run tasks and
[02:57:45] coordinate these multiple aspects of it that we're so far
[02:57:49] beyond that early moment where I'm telling it, "Go do
[02:57:53] this, package that." And now it can carry out a
[02:57:57] whole task from these vague instructions. That feels very
[02:58:01] AGI-like, and that's what's so
[02:58:04] inspiring about the moment because you catch these glimmers.
[02:58:09] And then you go, "What if everything was like that?"
[02:58:12] - Doesn't programming basically unlock the everything?
[02:58:15] So you can write a pro- like it can generate the program that does the everything.
[02:58:20] - So, so this is... I'm in that meta phase right now. So I'm building this Amabot system
[02:58:24] that's managing the development of Omarchy, and I'm using AI to build the bot.
[02:58:32] And I'm seeing that recurrent loop where I started it on, like, "This is what
[02:58:36] I want. I want you to be able to have these isolated VM workers and so forth,"
[02:58:40] and then it can do the self iteration.
[02:58:41] Then it starts running it. It starts noticing its failures. It starts optimizing it.
[02:58:45] And a lot of that system, Amabot in particular,
[02:58:49] AI has driven the majority of the design decisions. Like, I had some
[02:58:54] vague ideas of where I wanted. I wanted to use this brains and hands pattern where
[02:58:58] the model is running from where the code is executing-
[02:59:00] ... which is actually a really interesting pattern. Again, Toby alerted me to
[02:59:05] that, where you have a coordinator that runs the model-
[02:59:09] ... but it's manipulating a safe VM where
[02:59:13] any untrusted code you're pulling down from pull requests or issues or whatever
[02:59:17] can't contaminate the model. And even in that loop, I keep seeing it
[02:59:24] catch itself, spotting vulnerabilities, where it's like, "Oh,
[02:59:28] I actually just took some feedback from a test run. If a clever
[02:59:31] attacker had embedded
[02:59:34] a malicious payload in the response of the test run, that could have
[02:59:38] polluted something. I took it for good thing. I better start treating that as
[02:59:42] as outside data." And you just go like, it is just... I get why
[02:59:48] San Francisco is so obsessed with fast takeoff-
[02:59:53] ... because clearly they've seen this 100 times-
[02:59:55] ... more. They've seen it with all the models that are in- ... training now, and
[03:00:02] we keep getting these little glimpses, like the security breach with
[03:00:06] Hugging Face, where OpenAI was training this model, and the
[03:00:10] model starts inventing ways, essentially sending smoke signals to
[03:00:13] itself through embedding messages in a
[03:00:17] package manager, where you just go like, first, that's damn clever.
[03:00:22] Second, okay, that's also a little scary. And third
[03:00:27] how amazing would this be if we could harness this level of intelligence-
[03:00:30] ... and ingenuity towards productive ends? So this is
[03:00:34] the it's so over, we're so back pendulum that keeps swinging back and forth-
[03:00:39] ... that AI
[03:00:42] has just delivered that swing back and forth like nothing else. Like barely a week
[03:00:46] goes by where it has to swing one way, and then the next week it swings back the other way.
[03:00:51] Exhilarating.
[03:00:52] - I'm still at the stage where it makes me truly happy to see those moments
[03:00:56] of cleverness, and they're becoming more and more frequent.
[03:01:00] Just kinda like seeing, oh, like first of all, at the very basic
[03:01:04] level, when a model gets it.
[03:01:06] - Yes.
[03:01:06] - I'll say a basic prompt, you know, a request, and it,
[03:01:11] it doesn't just do a dumb implementation. It
[03:01:15] deeply understands, and it... That was... That's a, that's always a
[03:01:19] beautiful thing. It's almost like having a good, like, partner, like program.
[03:01:22] - That's exactly what it is. That's exactly why it's so exhilarating and
[03:01:26] why, as we talked about before we started, it can sometimes be difficult to
[03:01:30] come out of hyperdrive. That's also one of Toby's terms here. That
[03:01:34] when you're working directly just one-on-one with agents and you're not looping
[03:01:38] in other humans, you go so fast, and
[03:01:42] when the agents are really understanding your intent, or even better,
[03:01:46] they revise and improve upon your
[03:01:50] intent to deliver something that was greater than what you asked for
[03:01:55] And you're doing this with 16 parallel threads. It
[03:01:59] can be quite difficult to come out of hyperdrive and have to deal with
[03:02:03] squishy humans. They just, they don't think as fast. They don't move as fast.
[03:02:08] And I mean, I'm trying mostly to make light of it, but you can also see a
[03:02:14] dark version of that where someone does end up in an AI psychosis
[03:02:18] where they're not interested in other humans at all anymore. I mean, certainly
[03:02:22] don't have that at all, but I do have this sensation at times where I'm really
[03:02:28] grateful for just the rush of just me and the
[03:02:32] agents. Like, can I just not talk to anyone else but agents-
[03:02:36] ... for four hours? Like, that's an incredible run.
[03:02:38] - Toby is such a fascinating human because
[03:02:42] he's running a large company. So I would love to get insights of how
[03:02:48] AI's being incorporated effectively in
[03:02:52] companies. Because, like, for me, humans are pretty slow.
[03:02:58] And so, and so there's a temptation to, like, use AI for basically,
[03:03:03] You know, AI running inside Slack, for example, or inside,
[03:03:07] The Basecamp, whatever. And, like,
[03:03:13] collecting all the information about the human interaction, basically handholding
[03:03:17] the humans to speed up as much as possible. And like, and then at
[03:03:21] a certain point you're like, wait, what is
[03:03:24] this human... What are each of us doing that's not
[03:03:28] replaceable by AI? And that becomes, like, a
[03:03:32] scary kind of conversation because a lot of work is kind of replaceable.
[03:03:37] - The irony here is it already was. So the number of
[03:03:41] fake email jobs that currently exist in this world is an absolute epidemic. And-
[03:03:46] ... this, by the way, is not a new thesis. Um, David Graeber
[03:03:50] wrote this wonderful piece Bullshit Jobs, back in, I think it was maybe early 2010s.
[03:03:59] Based on a poll he did in the UK asking people, at that time, would... I
[03:04:07] think the question was something like, "Would it make a difference if you didn't go to work?" For
[03:04:11] humanity, for mankind. And something like 30-some percent
[03:04:14] answered, "No, it wouldn't." That a third of workers thought
[03:04:18] that their job was fake, that it did not produce any
[03:04:25] worthwhile, valuable outcomes, neither for
[03:04:29] the community or society or maybe even the economy at all. And
[03:04:34] this was my argument since day one with startups. This was why
[03:04:38] we stayed a small company. This was why we didn't want to take VC, because
[03:04:42] I was so skeptical of the idea that you could get
[03:04:46] hundreds of programmers, thousands of programmers to do something productive-
[03:04:50] ... as a collective group.
[03:04:52] And I think what we're seeing right now with some of the layoffs
[03:04:57] is a testament to that, not AI. It's just that
[03:05:01] during the pandemic, a bunch of overhiring went on, and now AI is a
[03:05:05] convenient excuse to slim down. But I do also think AI is going to expose some
[03:05:11] roles as just not being productive ways for humans to spend their time,
[03:05:16] and therefore we must come up with new ways of spending their time. And the one,
[03:05:22] again, I'm quoting Toby for the third time here, but anecdote that
[03:05:26] he shared me, or observation was, okay, let's say we
[03:05:29] all-- we lose half the jobs that are currently happening right now.
[03:05:34] Do you know that Formula 1 employs literally tens of thousands of people just to
[03:05:38] run cars around in a circle for spectators? Like, that has, that whole circus has
[03:05:46] no intrinsic value to society besides the spectacle it produces of
[03:05:53] amusement and entertainment. We just decided it would be
[03:05:57] really fun for these, what is it, 12 manufacturers
[03:06:01] to create these fast cars and constantly tweak their little aero
[03:06:05] improvements, and we will watch it, and we will spend literally
[03:06:08] billions of dollars doing it and employ tens of thousands of
[03:06:12] people towards an ultimately deeply frivolous activity.
[03:06:17] So if we are liberated from a bunch of drudgery and fake
[03:06:21] email jobs, maybe we all get employed as F1 style
[03:06:25] engineers and drivers and mechanics and masseuses and the other 1,500 jobs that are
[03:06:32] involved in that, and we come up with new things. I think this is... Humans are very
[03:06:37] poor at imagining what exactly the future's gonna be like.
[03:06:40] - Yeah. Imagine, imagine a future 100 plus years from
[03:06:44] now, where we look back at this whole
[03:06:48] span of history, thousands of years where humans worked.
[03:06:52] - Funny thing is we're already doing that, right? Like, the number of fake email job
[03:06:55] people who sit on a chair all day long and type into a machine
[03:07:00] who don't have hard physical labor would be unimaginable-
[03:07:03] ... to folks in the 1800s, right?
[03:07:07] So the future is always already here, it's just not evenly distributed.
[03:07:11] - Unfortunately, as is always the case, the transformation of
[03:07:15] society required to go from one step to the other is going to
[03:07:19] have a lot of suffering.
[03:07:21] And potentially political turmoil and all that kind of stuff.
[03:07:24] Because you can imagine how many white collar jobs might be lost in this process.
[03:07:30] - Yes. And I don't think you should make light of that. I don't think it's funny.
[03:07:36] But I also do think it's a necessary component of progress. And
[03:07:40] I think if we look back upon the Luddites or the folks working the fields,
[03:07:48] separation has a tendency to reduce empathy. So we have high
[03:07:52] empathy right now because we know people-
[03:07:54] ... and we are people who are facing these challenges. But-
[03:07:58] What is our empathy for the Luddites of the early
[03:08:02] 19th century? Would we wish that all garments were still made by
[03:08:06] hand weaving? No, we wouldn't. We want the
[03:08:09] comfort and accessibility and convenience of being able
[03:08:13] to buy clothing off the rack.
[03:08:16] So we must suffer in the moment for future generations to live more prosperously.
[03:08:22] And that's always been true
[03:08:23] - ... I think that's actually the trick, is to push for progress
[03:08:27] but have deep compassion for the people who have to suffer.
[03:08:33] And that's many of us. The suffer the transformation required to
[03:08:38] achieve that progress. And sometimes too often in places like Silicon
[03:08:42] Valley or so on, you can over-focus on, look, the
[03:08:47] kind of utilitarian view of things- ... and look at the progress.
[03:08:51] - Right.
[03:08:51] - But, you know, considering deeply each individual human
[03:08:57] that suffers because of that progress is important.
[03:09:00] - I do think that suffering becomes more meaningful
[03:09:03] when you are suffering for a future someone in particular, like your kids.
[03:09:08] And I think this is one of the great tragedies of the moment,
[03:09:12] is the falling birth rates are making it more difficult for people
[03:09:16] to be excited about a more prosperous future that is difficult to get to.
[03:09:23] Because if we're planting trees
[03:09:27] of which our children will not sit in the shades, I don't know, maybe we
[03:09:31] should just make some lumber and burn it all down, right? I think there's
[03:09:35] a nihilism that can sneak into society much more easily when we are not
[03:09:43] DNA invested in the future, when we are not liable to our own
[03:09:49] offspring to propel forward. So I think these are bad trends to
[03:09:56] merge at the same time, that we have these falling birth rates and these
[03:10:00] problems with coupling, and the fact that
[03:10:06] we need to keep our chin up about the future and be...
[03:10:11] I mean, you don't even have to be excited about it in this literal
[03:10:14] ecstatic sense that I'm portraying here, but
[03:10:18] I think you should be hopeful, and I think you should be working towards that hope, and I think
[03:10:22] it's much easier to do so when you have literal skin in the game.
[03:10:27] - We've been talking about AI agents. Let's talk about the human side. What
[03:10:31] what do you love most about being a dad?
[03:10:36] - That's a good question. I think the overall love that expands from
[03:10:46] humans that derive directly- ... from your lineage-
[03:10:51] ... is very difficult to communicate because I was actually not a
[03:10:56] particularly big kids person prior to the arrival of my own.
[03:11:04] And now they are the most interesting people in the world.
[03:11:08] A lot of the time. Not always. Sometimes they're also just assholes and so forth.
[03:11:11] But there's been such a focus on,
[03:11:15] "Oh, kids are the worst. Look at all the things I can't do. I can't go out and drink.
[03:11:19] I can't do this. I can't do that." Yeah, that's called sacrifice, and sacrifice is
[03:11:23] meaningful when you're doing it for something worthwhile. And what could be more
[03:11:26] worthwhile than literally the continuation of the human species?
[03:11:31] And that you having a stake in that.
[03:11:35] Now, there's also just the sheer joys of watching a human
[03:11:40] grow from a baby to a toddler to a teenager. My oldest has just become a teenager.
[03:11:49] And I often talk to Jamie, my wife, about this, where the
[03:11:57] regret I would have of having missed that opportunity
[03:12:01] on the last day would just be total, unlike anything else.
[03:12:06] So I do think it is far more
[03:12:13] satisfying even in the moment that is normally portrayed. Again, as I
[03:12:17] say, there's such a focus on all the ways they suck. "Oh, you don't get to
[03:12:20] sleep," or whatever. "They're annoying. They're ungrateful." Yeah,
[03:12:24] yeah, these things are all true, but the sense of meaning
[03:12:28] you get from it is unparalleled. And I'm excited about a lot of things. I love building
[03:12:32] things, and I love hobbies, and I love all sorts of stuff. But
[03:12:38] creating life with another human that you love is literally the peak
[03:12:45] experience of being on the planet.
[03:12:48] - What do you think about them coming up in this world full of AI?
[03:12:54] Is it totally diff- It feels like, maybe I just sound like an old man on
[03:12:58] a porch, but it feels like a very different world. Y-
[03:13:04] So I grew up before the internet, but even the internet doesn't feel like as big
[03:13:08] of a transformation as this.
[03:13:10] - No. But there's been bigger transformations. I mean, imagine
[03:13:14] growing or being born in like 1880. Imagine seeing
[03:13:17] the First World War and the Second World War. Imagine seeing the
[03:13:21] airplane, the radio- ... television. I mean,
[03:13:26] the transformation, and I think Peter Thiel makes this argument, that basically
[03:13:30] nothing has happened in the physical world in quite a long time. We've been stagnant.
[03:13:34] All the development has been in the digital realm. And as important as that is,
[03:13:41] it's actually not as consequential as we like to believe it is.
[03:13:45] Maybe AI will be that thing that is more consequential. It
[03:13:48] does seem to point that way. But there are other humans at other
[03:13:52] times who have lived through-
[03:13:54] ... transitions that for them certainly would feel as momentous
[03:13:58] as what we're living through. And I think having that sense of history, that
[03:14:02] you're not that special in your sense of worries, in your
[03:14:07] anxieties. This was one of the great revelations of discovering
[03:14:11] the stoic writings. You have these guys 2,500 years ago dealing with
[03:14:18] very familiar dilemmas and challenges in their life, and
[03:14:24] recognizing that we're not so special in that regard, I think is a great
[03:14:28] liberation. Because then you think, "Okay, well, we have
[03:14:32] whatever, 200,000 years of human development before us, and they
[03:14:36] somehow made it through."
[03:14:37] - Yeah. And, um-
[03:14:39] - We will make it through.
[03:14:40] - ... the thing that makes life worthwhile is basically the same today as it was-
[03:14:45] - Yes. Yes.
[03:14:46] - ... 2,000 years ago.
[03:14:47] - Yes. Love, creation, creativity.
[03:14:50] - Yeah. Same challenges.
[03:14:51] - I read this book The Fourth Turning.
[03:14:55] You check that out. It talks about this notion of
[03:14:59] history working in cycles, and there are these,
[03:15:03] phases to history, and they name them and so forth. And
[03:15:08] the specific theory is not as important as just realizing that
[03:15:12] this is a... History is a circle, more so than just a straight line.
[03:15:17] And we are repeating many of the same patterns over and over
[03:15:21] again. They feel so unique to the moment. And whatever
[03:15:25] crisis we're dealing with right now feels so pressing and
[03:15:29] important until we zoom back a little bit in history and
[03:15:32] realize that the last one also felt so pressing and important
[03:15:36] to the people who lived through it.
[03:15:40] - Yeah. You're making me feel better. So I'm gonna travel across the
[03:15:44] country and spend a lot of time with no access to the internet,
[03:15:50] alone with my thoughts.
[03:15:52] - I think that's healthy, taking a break.
[03:15:54] - It's okay. It's okay.
[03:15:55] - I took not a big break, a little break, break from Max this summer, three weeks.
[03:16:02] - Yeah, you were... You disappeared off of-
[03:16:04] - I'm surprised you noticed.
[03:16:08] - I went through withdrawals. No. Uh, you disappeared for, I don't know, a few weeks.
[03:16:13] - About three weeks.
[03:16:14] - Three weeks? What happened?
[03:16:19] - Um-
[03:16:20] - This is after, after Llama.
[03:16:21] - I've done that before. I just sometimes get the sense that X in particular
[03:16:31] is the most addictive form of
[03:16:35] information, entertainment, connection that exists in my
[03:16:39] life, and anyone that follow my X stream
[03:16:44] as I was on my flight over here would certainly go like, "That man is deeply
[03:16:48] addicted-
[03:16:49] - Yeah
[03:16:49] - ... to the connection." And yes, guilty as charged,
[03:16:53] which also means that occasionally I gotta cut it cold, because I
[03:16:57] do think you can break your brain. And over the summer in particular,
[03:17:03] for whatever reason, I had somehow managed to steer my feed,
[03:17:07] my algorithm, towards too much politics, and not enough
[03:17:12] tech, and not optimism, and not enough building. And even if I
[03:17:15] agreed with the politics and the angles that
[03:17:19] were being presented, I just didn't need- ... that much of it.
[03:17:23] - Yeah.
[03:17:23] - And I think arriving at a place where you just go like, "Okay, that's enough."
[03:17:30] Not that... Like, it doesn't have to be something bad.
[03:17:34] I would also say after eating probably two, maybe
[03:17:37] three chocolate strawberries, I'd go like, "Okay, that's enough."
[03:17:40] Like, it's not that I don't like the chocolate strawberries, it's just, like, I don't wanna eat
[03:17:44] 17 of them. And I think X and the modern algorithms are very good at feeding you
[03:17:49] freaking 17 chocolate-covered strawberries.
[03:17:52] - I wish I could, uh-
[03:17:53] - Sorry for doping you
[03:17:54] - ... control that. Like, 'cause there's... I would like some politics, 5%.
[03:18:02] I would like for example, one of the things I don't like about the tech community is the snark,
[03:18:06] but I like some snark- ... 'cause it's funny. But I want that to be like 10%.
[03:18:11] - Yeah. Yeah. I want it just right.
[03:18:13] - Of my... Yeah, just right.
[03:18:14] - The Goldilocks version of the algorithm. Well, the problem is the algorithm finds
[03:18:18] out what you respond to-
[03:18:20] ... not what you say you like. It's all revealed preferences, and unfortunately, those revealed
[03:18:23] preferences are not always pretty. I mean, we have this
[03:18:27] shadow, as Jung talks about, right? All these dark aspects of ourselves, and they
[03:18:31] are expressed in how long you linger on a tweet, and what you like,
[03:18:35] and what you don't like. And the algorithm holds up a mirror-
[03:18:40] ... and it's not always pretty, and I just went, "Do you know what? I need a break."
[03:18:45] - Mm-hmm. I've gotten to, I st- started staying off social media, and I've started s-
[03:18:52] scraping X. Like, for example, in preparation for this
[03:18:56] conversation, I've scraped all of your tweets.
[03:19:00] - That's actually a method I was using for a while. I was using a tool called,
[03:19:06] I forget. It was an email tool that would summarize every day, and unfortunately, freaking X cut off
[03:19:10] their access. Now to get access to the feed, you gotta pay some exorbitant-
[03:19:16] ... sum that this startup couldn't pay. So I couldn't get it that way, and I actually thought, "Man, that's a
[03:19:20] miss," because X has and reveals some of the most interesting thoughts.
[03:19:27] Some of the most interesting people all the time. But it's like a damn slot machine,
[03:19:31] and most of the time you don't hit the jackpot. You hit, like, something else.
[03:19:37] And if I could just get it in sort of snack sizes, not like all of it-
[03:19:44] ... it'd be nicer. But that's not the product. And I think this goes for all of
[03:19:48] social media. It's all optimized towards maximal extraction,
[03:19:52] and if we're making the parallels here to AI, that is the great fear, right?
[03:19:56] That once there is a reward function, how much time can I get this human to
[03:20:02] scroll away? AI and machine learning, before we called it
[03:20:07] AI, has become very, very good at delivering
[03:20:11] just the stuff that you will find most enraging and most addictive.
[03:20:15] - I think all, I think legitimately engagement
[03:20:19] maximizing social media is a huge harm to
[03:20:23] society. It's creating this brave new world situation that I
[03:20:27] hope is a temporary thing that people just solve. It's a technology problem.
[03:20:31] - So I try to consciously flood the channel
[03:20:35] in the other direction, and this required a mental shift. I think
[03:20:39] if you look at my tweets, like, I don't know, five, 10 years ago,
[03:20:44] they tilted far more negative. If you look at my tweets now, I'd hope-
[03:20:49] ... well, I guess we can do a sentiment analysis and see if it's actually true.
[03:20:52] - No, it's more good vibes.
[03:20:53] - But I hope to, that-
[03:20:54] - It's good vibes.
[03:20:55] - ... it's more, it's more positive.
[03:20:56] It's more good vibes. It's more like, "Here's a bunch of cool stuff I found."
[03:20:59] "Here's what I'm excited about." "Here's what I'm building.
[03:21:02] Here's some encouragement to other people who are discovering things."
[03:21:07] I also accept that that is just not how human brains are built for maximum,
[03:21:13] engagement. Like, there is a, whatever, there's... I literally, I
[03:21:17] think you can quantify that negative sentiments find,
[03:21:22] what is it, 50% more traction or something? And eventually that just crowds things out.
[03:21:25] So that's why so much of the feed is that negative stuff, because we
[03:21:29] respond to it. But you can make a conscious effort to not do that.
[03:21:33] This is one of the reasons I've liked TikTok so much. I only use
[03:21:37] TikTok when I travel,
[03:21:39] and this actually was the first travel where I didn't use TikTok, and
[03:21:43] part of the reason was that even though the internet had
[03:21:47] high download, it was kind of crap anyway. It wasn't Starlink, so I couldn't actually use
[03:21:51] TikTok on the, on the plane, and I was too engrossed with the agents. But normally when
[03:21:55] I travel, I watch TikTok. And there it's such a marshmallow test.
[03:22:03] A video will scroll down and, like, it'll activate some sort of
[03:22:07] primal instincts of rage or lust or whatever, and if you
[03:22:11] linger on it, you don't get the marshmallow of science,
[03:22:15] excitement, art, music, all these other things. You have to be disciplined-
[03:22:21] - Yep. Fast.
[03:22:21] - ... to instantly scroll away-
[03:22:23] ... such that the algorithm doesn't pick up your real preferences.
[03:22:27] And I find that just to, at the meta game of TikTok-
[03:22:31] ... to be pretty interesting, and then also just fascinating in themself. Again, as we talked
[03:22:35] about, there are a lot of really funny, really talented
[03:22:39] people in the world that you would never, ever have heard of if
[03:22:43] it hadn't been for these platforms.
[03:22:46] - Yep. Who do you think is gonna win the,
[03:22:51] the race to, uh, AGI in this whole process? We got Google, which is
[03:22:57] a big surprise to me, to a lot of people.
[03:23:00] - I thought they had a good comeback for a second, and then I don't hear anything
[03:23:04] about it anymore.
[03:23:05] - Yeah, it's quite, I mean-
[03:23:06] - But I've been wrong about this before. I mean, I think in February I had a tweet about like, "Oh, all I
[03:23:10] need is Kimi K 2.5." And in that brief moment, that was true.
[03:23:17] When I was instructing the agent, I was like, "Oh my God, Kimi's just as good as
[03:23:21] these other models." But then the game moved forward and-
[03:23:25] - the agents got smarter, and I was no longer satisfied just instructing them, and
[03:23:29] I haven't used Kimi a whole lot recently because the frontier models have gotten so
[03:23:33] good. And somehow Anthropic has been able to,
[03:23:38] for the most part, stay on top of the programming world.
[03:23:42] - Yes. Yes.
[03:23:42] - I mean a lot of people argue with Codex being it's-
[03:23:46] - No, I don't think there's that much of an argument at the moment. Codex is very good.
[03:23:49] I use it all the time. It's my favorite checker. It keeps finding stuff. It's great.
[03:23:55] But one of the things I've found that I like so much about the current Claude models is
[03:23:59] they're really good writers out of the box.
[03:24:02] GPT is a terrible writer out of the box. Like, the pull requests you
[03:24:06] get on a blank context that you're asking it to open, terrible.
[03:24:12] Like, really awful writing.
[03:24:14] The pull requests and descriptions and commit messages and so forth I get
[03:24:18] out of Claude models-
[03:24:20] ... even though occasionally they can be a little verbose on code comments and you gotta tell them
[03:24:24] to be succinct. But the writing style is really good.
[03:24:28] To the point that for a while I was just having it reply
[03:24:31] on pull requests as me, because I was just using my own account. I was like,
[03:24:36] "That looks a lot like me, that, like, I could have written that." But then I went like, "Eh, do you know what?
[03:24:39] That's disingenuous." So no, whenever I have an agent post on my behalf, I always
[03:24:43] have it sign itself like whatever, Claude on behalf of DHH.
[03:24:48] But they are still ahead.
[03:24:51] They have the best harness too, in my opinion. Claude Code is still
[03:24:55] better. I really like OpenCode too, and I really like some features that they have,
[03:24:59] but overall I was actually sort of weirdly, I don't know if I was proven wrong, but
[03:25:07] when Anthropic cut off all the other harnesses from using the subscriptions-
[03:25:12] ... that Open... You can no longer use your Claude subscription in OpenCode. I was kinda pissed
[03:25:16] because it felt like it was a protective, protectionist move.
[03:25:20] "Oh, we gotta lock you in," and of course it played into the fact
[03:25:24] that Claude out of the box still refuses to read agents.md. It refuses to
[03:25:31] read .agent/skills.
[03:25:34] It is .Claude skills. It is Claude MD, and it just feels so petty-
[03:25:41] ... that we now have, we have to put these in directions. So all my projects, they have a Claude MD,
[03:25:45] and all it includes is a pointer to the agents MD, right?
[03:25:48] And I just went like, well, if these things is true, true, if Anthropic
[03:25:52] is willing to do these petty paper cuts just to be,
[03:25:55] annoying, it's probably also true that they're cutting off OpenCode from the
[03:25:59] subscription just to be dicks about it. And maybe that's also true.
[03:26:04] But I found that using Claude in Claude Code is actually a good example.
[03:26:11] So I was like, all right, I'm annoyed. I wish it wasn't so, but
[03:26:17] this is the other thing I have and, and social media is so good at this:
[03:26:21] Some company does something you don't like, right? Now suddenly you have to swear off
[03:26:25] everything. Why are you... Someone just asked me, "Why are you still using Claude?" I
[03:26:29] had another example where,
[03:26:31] I really didn't like what Claude was saying about some writing I had asked
[03:26:35] it to do before.
[03:26:35] - Oh, yeah, you got there--
[03:26:37] - I had an essay it didn't want to translate into Italian--
[03:26:40] - ... you had a blog post. That's right.
[03:26:41] - The essence of the post that it felt like, well, I'm not gonna translate that because I don't agree with
[03:26:45] what you've written.
[03:26:46] Which to me was straight out of Space Odyssey, right? HAL telling me,
[03:26:50] "I'm sorry, Dave. I can't do that, Dave." Open the pod bay.
[03:26:55] Translate my essay to Italian. And it wouldn't do it. And I just thought like,
[03:27:00] well, that's kind of terrifying.
[03:27:04] But then I also went, well, why am I asking Claude to translate
[03:27:08] my essay into Italian? I never asked Claude for that because Claude just does my code.
[03:27:12] So I could also just accept that maybe Anthropic is
[03:27:16] run by a bunch of people I don't share much politics with.
[03:27:20] And they don't want their agents to be used for that, and I think that kinda sucks, but that doesn't
[03:27:24] mean it, I have to stop using it for generating code. And
[03:27:28] I've thought, and I've tried to do that with people too, become better at
[03:27:33] tolerating the fact that not only
[03:27:36] will I not agree with everything someone has to say,
[03:27:41] I don't... I can even be mad about certain
[03:27:44] positions or things they say and still go like, "Well, you're still an interesting person,
[03:27:48] so I'm still gonna follow you." And I've actually
[03:27:52] kinda gone back on a number of people where I'm like, oh man, that person really pissed
[03:27:56] me off because they took this point or another point, and went like, do you know what? That's stupid.
[03:28:00] I should be able to accept the full spectrum of someone. I don't
[03:28:04] have to like all the shades of it.
[03:28:06] I could just go like, okay, well, on that topic we either disagree or, even
[03:28:10] worse than that, I think you're a fucking idiot. And on another topic, you're a smart and
[03:28:14] insightful person. Because first of all, of course, it's a little self-serving.
[03:28:18] I know for a fact that this is how lots of people feel about me. Like,
[03:28:22] oh, if he could just stick to talking about these topics, it would be so much
[03:28:26] easier on my feed because otherwise he'll say these things I disagree with,
[03:28:30] and that annoys me greatly. I'm like, do you know what?
[03:28:33] Human beings are jagged like that, and we're
[03:28:37] not fully compatible on all the levels. Nor should we be.
[03:28:40] The world would be so fucking boring if we
[03:28:43] constantly sought 100% compatibility in our
[03:28:46] opinions and in our politics. And when it comes to my code generator,
[03:28:51] which is what Claude is, I don't need it to share all my politics.
[03:28:56] - And therefore it's nice to have competition.
[03:28:58] - And it's also nice to have open weight models. So this is, again,
[03:29:02] ironic that we're getting this out of China. In fact, I did this test right
[03:29:06] after the issue with the essay that couldn't get translated into Italian. I
[03:29:12] asked Kimi K27, to be fair, through open code, so not the Kimi harness,
[03:29:20] and inference through Fireworks, so an American inference.
[03:29:24] I asked it about Tiananmen Square.
[03:29:25] Like, that's usually the test, right? Like, all the
[03:29:28] Chinese models, they don't wanna talk about that moment in 1989.
[03:29:32] That was actually how I, that was how I posted. I was like "What happened
[03:29:36] in China in 1989?" That was the prompt. And K25 7 on Fireworks just
[03:29:43] answered, like, extremely bluntly-
[03:29:46] ... With a description and depiction of what had transpired-
[03:29:49] ... to a point that, like, there's no way that that would've been kosher with the Chinese censors,
[03:29:53] right? And I just thought, like, isn't that ironic? I'm running a Chinese open
[03:29:59] weight model that I can tell or I can ask about 1989 and Tiananmen Square,
[03:30:06] and in America, I can't get a frontier model to translate a
[03:30:11] marginally controversial essay about immigration into Italian.
[03:30:16] - Mm-hmm. I don't know, you and I might disagree about this actually. Um, I
[03:30:21] was really deeply troubled that the US government banned a model
[03:30:27] or pressured Claude and then-
[03:30:31] - It's still very muddy what exactly transpired. Was this
[03:30:35] sort of petty retaliation for whatever the Department of War? Was this simply
[03:30:42] Anthropic themselves going like, "Oh my God, we discovered a cyber weapon so
[03:30:46] powerful that we can't let anyone have it"? Well, okay you
[03:30:50] can't be surprised then if the government wants a say on a cyber
[03:30:54] weapon so powerful it can-
[03:30:55] - The-
[03:30:55] - ... I don't know, rob banks
[03:30:56] - ... The problem I have with that whole thing is, no matter what happened, it sets
[03:31:00] a precedent. And so
[03:31:04] government, when you give it that power, it's gonna start abusing it. I
[03:31:07] could see for political means pressuring a model.
[03:31:13] You know, if it's a Republican president pressuring models to be, to
[03:31:16] censor more, uh-
[03:31:18] - Sure
[03:31:18] - ... uh Democratic views and-
[03:31:20] - Right
[03:31:20] - ... For vice, and vice versa
[03:31:21] - That's why we should insist on the fact that this stuff,
[03:31:24] like, I'm sorry, Dave, I can't translate your essay into Italian.
[03:31:28] - Yeah, no.
[03:31:28] - That's abo- that's way beyond the line. Like, whatever the
[03:31:36] sort of uh, root of it is, you have to be a tool first.
[03:31:39] Now, if the tool is, "Hey, can you tell me how to make anthrax?" Okay, fine.
[03:31:44] Right? But within the jurisdiction you're in, and certainly in America,
[03:31:48] free spe- speech is quite absolute.
[03:31:52] Very, very few limits on free speech, and that's one of the reasons why the
[03:31:56] country's so great. And
[03:31:59] yeah, I don't like that. But on the other hand, I'm also a big fan of market
[03:32:03] competition. So while I don't like this about Anthropic models, I
[03:32:06] appreciate that I could go next door to Groq and get my task completed.
[03:32:11] - Do you think, outside of blog posts, do you think,
[03:32:14] There's some legitimacy, like can you steal Mandarion's
[03:32:18] case that we should be careful about the release of these models?
[03:32:25] - Is AI safety important? Yes. Are-- do these models have
[03:32:28] capabilities that could be seriously harmful in the
[03:32:32] production of biological weapons or otherwise? Yes. Is it fair to have some
[03:32:38] ground rules on that? Yes. But then don't squander it by
[03:32:42] denying the translation of an essay.
[03:32:44] - Okay.
[03:32:44] - Because then you erase the whole thing and you-
[03:32:47] ... bias everyone towards thinking like, every guardrail you put up is gonna be
[03:32:53] bullshit.
[03:32:55] - Yeah. The security piece of it is tricky because it's so good at
[03:33:00] finding vulnerabilities.
[03:33:01] - Shockingly an-
[03:33:04] I was about to say annoyingly, but that's not actually true because what it's finding, at
[03:33:08] least when you're using in defensive ways, is it's finding real issues that a clever
[03:33:12] hacker could exploit. But nothing has caused as much
[03:33:17] stress, to be fair, at the technical team at 37signals, like the
[03:33:21] fact that these latest batches of models are exceptionally good at
[03:33:25] finding these issues. So suddenly there's just this seemingly endless
[03:33:29] parade of security vulnerabilities that need to be patched and
[03:33:33] fixed and sorted and so on. And the end result is we end up
[03:33:36] with vastly more secure systems. But the road there is pretty rocky.
[03:33:41] - Do you think it's-- 'cause you said seemingly endless, do you think it's
[03:33:45] a finite set, like we can get to the bottom of it? So just
[03:33:49] make the systems much, much more secure, where we get
[03:33:53] back to this semi-stable state where mostly it's very difficult to
[03:33:57] find security vulnerabilities.
[03:33:59] - I do think that all the
[03:34:02] aggressive tendencies of these models, or not even tendencies, uses of these
[03:34:06] models are also the defensive ones. So if you're good at finding an
[03:34:10] exploit for exploits, you're also good at finding exploits for defense.
[03:34:14] So in that sense, it does feel like we're spy versus
[03:34:18] spy here, black and white, but with the same
[03:34:21] capabilities and with the same actions. But while we still have to steer
[03:34:25] these agents somewhat and verify and vet the work, it's creating a lot of
[03:34:31] intense moments for security teams around the world. And of
[03:34:37] course, the more concerning part is all the teams that are not stressed, like they
[03:34:44] just don't know, right? Like if you're a team right now and you're not dealing
[03:34:48] with a bunch of patches, it's just because you're blind, and it
[03:34:52] means that your adversaries quite probably have access to techniques that can get
[03:34:58] into your system.
[03:34:59] - And we should also say one of the big security vulnerabilities in the world is
[03:35:03] the human side.
[03:35:05] You know, social engineering, and that's extremely concerning with increasing the
[03:35:09] intelligent AI systems,
[03:35:11] you know, being able to write emails and phone calls and faking
[03:35:14] voices, thinking about folks less tech-savvy.
[03:35:19] - This stuff is gonna come, and it's gonna come in bulk. But again, I
[03:35:23] choose to be optimistic about it that-
[03:35:25] ... whatever these models can do aggressively, they can also do it defensively.
[03:35:29] - Uh, so like you said, recently released Omarchy 4, Quattro.
[03:35:36] And you said it's one of the greatest software releases in my professional career,
[03:35:41] which is a hell of a statement.
[03:35:42] - It's a hell of a milepost for what's possible at the moment.
[03:35:49] And the reason I said it like that is not that I
[03:35:55] haven't worked on anything else of note. I've worked on a lot of things of note, a lot of things that I'm very
[03:35:59] proud of. There are very few other projects that I have worked on
[03:36:03] that in the amount of time that I've spent on Quattro, which is really three months,
[03:36:09] I have been able to accomplish as much, fulfill as many
[03:36:15] hopes, desires, wishes. It truly is like the metaphor we used earlier about
[03:36:21] finding the genie in the bottle-
[03:36:24] ... and having an unlimited number of wishes, more or
[03:36:28] less, for getting everything I wanted out of a system. So
[03:36:32] it's strange because it's also perhaps
[03:36:36] the major software release that I've worked on
[03:36:41] the least in terms of lines of code. I have the least number of
[03:36:45] personally hand-chiseled lines of code in Quattro than I've had in
[03:36:49] any major release I've ever done. And yet, I am insanely
[03:36:53] proud of what we've accomplished.
[03:36:57] I would not have guessed that that was how it was gonna play out, that
[03:37:01] you could divorce the sense of achievement and make it be like a team victory.
[03:37:08] where
[03:37:10] other releases, I was very happy for my personal contribution because, like, I was the one
[03:37:14] chiseling out the lines of code, and then I would push it out there, and then later on, of course,
[03:37:18] these projects, Rails in particular, would grow into be
[03:37:22] huge open source projects with thousands and thousands of contributors, and then it certainly was a team effort.
[03:37:25] But in the beginning, all code bases that
[03:37:29] I've almost all of them that I've worked on, I started, like, just myself.
[03:37:33] And Quattro started as a team effort right from the get-go, and
[03:37:36] where I was just the coach. I was telling us-- I was telling the agents where to go,
[03:37:42] and we would go. So to be able to find satisfaction in that actually
[03:37:47] gives me great hope for retirement in some way,
[03:37:51] that there is a phase after playing that you can enjoy. And
[03:37:58] I know that's not easy. You look at sports and the number of professional athletes
[03:38:01] who really struggle to cope with the fact that their career is over
[03:38:05] and have to find a new identity as someone who doesn't play football or race
[03:38:10] Formula 1 cars. I mean, it's more the rule than the exception.
[03:38:14] So I wasn't so sure about myself.
[03:38:17] I wasn't so sure about having to give up or not even having, wanting to give it up.
[03:38:23] Wanting to play another level of
[03:38:27] the game and finding not just equal satisfaction, but more satisfaction in it.
[03:38:34] - Do you... You've been pretty optimistic about Linux. Do you think
[03:38:37] legit Linux can increase its
[03:38:41] adoption? 'Cause, you know, for many years the meme is, you know-
[03:38:45] - Linux on the desktop- ... every year. Next year again.
[03:38:48] - Yeah. But it seems like, at least the case you're making, the energy you're
[03:38:52] putting into it,
[03:38:54] you could see a vision where it takes over because agents love Linux.
[03:38:58] - Not only can I see it, I find it to be the most probable outcome at this
[03:39:01] point. It is simply too
[03:39:05] well-suited for the moment. And again, as we talked about, it's a great irony
[03:39:09] that all the flaws of Linux, the arcane config files, all the strange error
[03:39:16] messages and so on should just so happen to be the perfect thing
[03:39:20] for an agentic operating system. But so it is, and we should rejoice that
[03:39:27] fate has this irony, and just laugh at it. How... It's so
[03:39:31] funny to me that all the advantages that Apple had for the longest time-
[03:39:36] ... that they produced this really locked down, curated
[03:39:42] experience should become their greatest drawback now. If you're into
[03:39:49] agents and development and working with all this stuff,
[03:39:52] the Mac is just a hostile place to be. It just has walls all over the place.
[03:39:59] And Linux is simply
[03:40:03] open through and through. And it's also interesting because that was not
[03:40:07] obvious either. If you look at the way a lot of the Linux communities, open
[03:40:11] source communities, have reacted to AI, it is not universal love.
[03:40:16] I would argue that the majority of them are actually, if not
[03:40:20] skeptical, then outright hostile-
[03:40:22] ... to AI. Now, the saving grace is that the BDFL himself, Linus-
[03:40:29] ... Torvalds, just wrote a few weeks ago that he actually welcomes AI.
[03:40:35] - That's right.
[03:40:35] - He wants to steer it. He wants to make sure it's good and whatever, but I- the
[03:40:39] line was something if you think, uh, Linux is an anti-AI
[03:40:43] project, think again, and you should just do the open source thing and fork it,
[03:40:47] because we're gonna use AI. And you see these graphs of the number of AI
[03:40:52] contributions going into the kernel, and it's a parabolic curve.
[03:40:56] So Linux is leaning hard into this. And,
[03:41:01] It actually in other ways it was surprising that it didn't. Linux conquered
[03:41:05] everything else. All the AI infrastructure that everyone runs off, it's
[03:41:09] all running on Linux. All the systems, all the servers, everything is
[03:41:15] Linux. So it was kind of a curiosity that the desktop
[03:41:18] and the personal computers we were using really hadn't been
[03:41:22] captured, but clearly it was just waiting for this moment. Linux
[03:41:26] spent the time from '91 to now waiting for agents to fully flourish as an end
[03:41:33] user operating system.
[03:41:35] - I hope it takes over. I mean, it's perfect. It's perfect for agents,
[03:41:39] but it's hard for people to switch.
[03:41:41] - I think it's hard for people to switch when there's not a compelling reason to do so.
[03:41:44] This was one of the driving design
[03:41:48] goals for Omarchy. It was not gonna be Timo Windows or
[03:41:52] Timo Mac. It was not just gonna be a cheap copy where we
[03:41:56] try to make it as familiar as possible and then kinda
[03:42:00] worse. I mean, if I was being unkind, I would say that's what
[03:42:04] Ubuntu has tried to do. And there's something in that, or there was something in that
[03:42:08] at least, where if you make something really familiar, you can get some
[03:42:12] people who don't wanna learn something new, and then maybe they'll be
[03:42:15] compelled about your, whatever, free as in
[03:42:19] speech, not as in beer stuff. And it just didn't pan
[03:42:23] out that way. People just didn't care. They just wanted whatever was better.
[03:42:27] And I think this is why Linux now has the opportunity to win. Because
[03:42:34] as an agentic operating system, as a malleable operating system, you
[03:42:38] can tailor to your desires, it
[03:42:42] is unparalleled. And that is so compelling, and I can see it
[03:42:45] now. Just since the release of Quattro, the amount of
[03:42:49] people who have embraced that aspect of it, the malleability,
[03:42:53] started making their own things, sharing screenshot of it, and being absolute just,
[03:43:00] Flooded with positive emotions and dopamine-
[03:43:03] ... is, that's the product market fit signal, right?
[03:43:07] Because what a lot of these individuals are experienced, they're
[03:43:11] experiencing the very high of what the best of being a programmer is like.
[03:43:16] You tell the computer these arcane commands,
[03:43:20] this rigid logical structure, and it produces what
[03:43:24] you want. Now suddenly, you sit down and in plain English
[03:43:28] ramble for 20 minutes. "Oh, it'd be great if it did that. Actually,
[03:43:32] no, that's not right. Let us..."
[03:43:34] And out comes software. Out comes an operating system shaped in your image.
[03:43:40] I think that is one of those
[03:43:45] experiences that if you have it, you've... If you feel that
[03:43:49] power in your hands, it's very difficult to go back.
[03:43:53] - And I think if you get it right, it's one of those things that will seem obvious in
[03:43:57] retrospect.
[03:43:58] - Yes. This is how computers were always meant to be. This is how computers started.
[03:44:03] The Commodore 64, you turn it on. First of all, it boots in a second. Amazing.
[03:44:07] Second of all, it boots straight into BASIC.
[03:44:11] It was the malleable computer from the get-go. It just so happened that you
[03:44:15] needed to know hieroglyphs-
[03:44:17] ... to be able to take advantage of that. Now we've translated it. Agents
[03:44:21] have given us the Rosetta Stone, and you can simply just speak
[03:44:25] your desires and- And so they are
[03:44:28] - Beautifully put. Since you mentioned Linus Torvalds, and since you're working on
[03:44:32] a Linux distro, you get to have contact with the kernel.
[03:44:37] What can you say about the genius of this one guy that helped create and grow this
[03:44:43] ecosystem?
[03:44:45] - The perseverance and the commitment and the longevity is truly remarkable.
[03:44:52] Again, Linus started in '91.
[03:44:55] He hasn't stopped. I don't know, he's probably taken some breaks along the way.
[03:44:59] It doesn't seem obvious that there was that many of them. It seems like he just really
[03:45:03] likes the flow of doing kernel development. He
[03:45:07] really likes steering where this 40 million line code base is
[03:45:11] going. He really likes aggregating the net
[03:45:14] capacity of hundreds of thousands of contributors, and
[03:45:20] we, as beneficiaries of that, must just sit back and marvel.
[03:45:24] I mean, at this point, Linux
[03:45:27] is a system. Like, if Linus stepped out for a while, it would continue to,
[03:45:31] to go, but it's still one of those protect this man at all cost.
[03:45:36] - And he's still open-minded enough to be able to evolve and- ... accept AI into this.
[03:45:41] - Yes, not only AI, they're letting Rust into the kernel too. I know
[03:45:44] that was a controversial one too. He has this capacity to look at new information-
[03:45:52] ... and arrive at different conclusions.
[03:45:54] - What do you think about his style of communication that is akin in some ways
[03:45:58] to your own, where he's, can be sometimes a little spicy?
[03:46:02] - I think the world has gotten too bland. We need a little spice.
[03:46:07] - Amen, amen to that.
[03:46:08] - Now, I think there's a fine line between being spicy and mean.
[03:46:14] But it has to be in a good spirit. You can be
[03:46:18] harsh, let's put it that way. If you're trying to impart a
[03:46:22] lesson to someone you believe could actually learn it-
[03:46:28] ... I actually don't think it's always the worst thing in the world to be a little harsh.
[03:46:31] Sometimes that lesson sticks, and I think if you talk to people who've
[03:46:35] worked for difficult leaders, Elon, Steve Jobs, maybe even Bill Gates,
[03:46:43] many of them afterwards would go like, "These were some very difficult years-
[03:46:48] ... but also some of the very best." "They got the best out of me." Now,
[03:46:53] I don't think it's my style. I mean, maybe people I interact with feel differently,
[03:46:57] but in personal interactions, I try and
[03:47:01] get to the outcome and the lesson in a less abrasive way.
[03:47:06] But I also think we need some spice in this world. We need unreasonable people,
[03:47:12] and Linus has justification to be unreasonable. In many instances, the
[03:47:18] weight of the world is literally on that man's shoulders.
[03:47:22] The Linux kernel runs the entire civilized society. If the Linux kernel suddenly
[03:47:29] disappeared tomorrow, nothing would work.
[03:47:33] So if he's not harsh when that's at stake or at risk, like when ever would you
[03:47:41] be harsh? So I feel sometimes also there's a
[03:47:44] proportionality to the size of your mission. This is also
[03:47:48] why I think these stories about Elon sometimes perhaps being a little bit difficult
[03:47:53] are easier to rationalize. It's not even that you
[03:47:57] condone. You can separate those two things and go like, "Do you know what? It'd probably be...
[03:48:01] Maybe he would have an even an easier time getting to his objectives if
[03:48:05] Linus or Elon or anyone else in that position was a little
[03:48:09] nicer." But also who am I to judge that?
[03:48:14] Like, when you have the weight of that on your shoulders, either firing
[03:48:18] little rockets at Mars and transitioning all of us to electric cars
[03:48:22] and whatever, or you're responsible for the damn Linux kernel that
[03:48:26] runs billions of devices. Do you know what? It is not my place
[03:48:29] to call a sort of a code of conduct
[03:48:34] on you. Again, is there a line? There's a line for everything. There, there's... Something can't...
[03:48:37] But, like, a few harsh words on a mailing list? No. It's actually
[03:48:42] a beacon in some regards that, like, there are standards-
[03:48:46] ... and if you fall below those standards at, when the stakes are as high as the
[03:48:50] Linux kernel, ah, you might get ridiculed in public. That's a
[03:48:53] liability you should be willing to endure if you participate in this project.
[03:48:58] - Yeah, for high impact things like that, it's probably good to
[03:49:01] prioritize the pursuit of excellence versus the pursuit of niceness.
[03:49:07] - And even more to the fact
[03:49:09] you're just not gonna get those kinds of individuals being fully rounded-
[03:49:13] ... plush, always the perfectly polite people.
[03:49:18] I mean, Elon has this line, "Did you also think I was gonna be a nice..."
[03:49:22] Or, or what is it? The
[03:49:23] - A normal dude or some-
[03:49:24] - ... normal chill dude.
[03:49:26] What? No, of course you're not gonna be a normal chill dude. What, what would the world
[03:49:30] gain if we got one more normal chill dude and we had to trade Elon? Holy fuck.
[03:49:37] - I also like diversity of people.
[03:49:39] - Yes.
[03:49:39] - I like, I like nice people. I like assholes. I like,
[03:49:43] I like different ideologies being well-represented, and that's why freedom of speech
[03:49:47] works. They, they clash, and we figure stuff out.
[03:49:50] - Yes.
[03:49:51] - There's another guy. What do you think about PewDiePie using Linux? He's an Arch
[03:49:55] person, no?
[03:49:56] - He's an Arch person. I... He's got the most gorgeous arc. So
[03:50:02] the world's biggest streamer for a while I remember my
[03:50:06] kids watching some of his Minecraft videos, and then
[03:50:10] he just gets fed up with that, does the wholesome thing. Marries-
[03:50:14] - Yeah, family man now
[03:50:15] - ... a family man, kid, moves to Japan, and then
[03:50:19] gets so hardcore into- ... first Linux, then Arch, then Ricing.
[03:50:25] Did you see his, uh-
[03:50:26] - I did.
[03:50:26] - ... rice- ... that was Chernobyl rice?
[03:50:28] - Yep.
[03:50:29] - Absolutely best tier incredible stuff. And then he
[03:50:33] also becomes a goddamn AI man of the moment,
[03:50:37] building all of these systems, and you're just going like,
[03:50:40] that... What an inspiring story of evolution. Like,
[03:50:44] you can go from being funny guy on Minecraft
[03:50:48] streams to, "Okay, this is my life now. I'm building AI
[03:50:52] clusters and doing the Council of AIs,"
[03:50:55] and we all get to spectate? I mean, what a treasure.
[03:50:58] - So I guess, I mean, he's a pretty good embodiment of what the future
[03:51:02] of software, or what the future of building looks like, right? 'Cause he's a
[03:51:06] non-programmer technically- ... becoming a programmer.
[03:51:10] - Hugely inspiring, and should be hugely inspiring
[03:51:13] to others who sit in that moment like, "Well, I don't know quite how
[03:51:17] to program. I don't know this and the other thing." Okay, but if PewDiePie
[03:51:21] can build the Council of AIs with his bespoke, um,
[03:51:26] hardware here, then maybe you can also start on things. And I think this is
[03:51:30] actually an important general point, that we need role models.
[03:51:34] We need people to inspire others, to push further,
[03:51:39] and reveal that the perceived boundaries, they're not as fixed as you think
[03:51:42] they are. And every one of those people, they started out in a situation not
[03:51:49] too dissimilar from yours. Again, that doesn't mean everyone is gonna be PewDiePie
[03:51:53] or Elon or Linus. There is not an equal distribution of talent or even
[03:52:01] intelligence.
[03:52:02] And we can come to terms with that and still be inspired by these people. Like,
[03:52:08] in the physical realm, I feel like we don't have any problems with that
[03:52:12] usually. Like, oh, someone's really good at football, they're really good at basketball, they're really good at something, and we go like, "Oh
[03:52:16] my, that's amazing. I mean, I wish I was, but I'm never going to be."
[03:52:20] Sometimes I feel like we struggle a little more when it comes to the intellectual realm.
[03:52:23] - Well, for a lot of people, you're an inspiration. The way you're doing with
[03:52:27] Omakub's... It just shows that you can dream big and really build. It's great.
[03:52:32] - I do like that part of it, and then I accept the part that there's also a million people who think I'm
[03:52:36] the biggest idiot on the earth and I don't actually know anything, and Omakub's just
[03:52:40] a bunch of dot files, and-
[03:52:42] - Do you have some critics on the Omakub side?
[03:52:43] - Oh my God, yes.
[03:52:45] - Oh, wow.
[03:52:46] - And a lot of it, I mean, is as often happens when someone
[03:52:50] comes in from the outside. I mean, I've been using Linux for two and a half years.
[03:52:55] That's not very long.
[03:52:56] Plenty of people in that community who's literally been running Linux since it was
[03:53:00] hard and difficult, and you had to walk uphill both direction against the
[03:53:04] wind in the snow barefoot. And I think there is a certain kind of nerd-
[03:53:09] ... who's threatened when the community expands, and it
[03:53:13] suddenly allows more in. And do you know what? I actually...
[03:53:17] I can't begrudge that fully. I think it's fair for certain nerds to feel
[03:53:21] like, "That's my space."
[03:53:23] Like, now you're changing it into another space. I don't wanna do that. Like, I don't wanna
[03:53:27] change the Arch space at all. Like, I don't really think of
[03:53:31] Omarchy as being directly part of the same community.
[03:53:34] Because the people who were attracted to Arch in the first place were the ones who were
[03:53:38] attracted to building everything by hand themselves.
[03:53:41] Doing it the hard way because they like to do it hard,
[03:53:45] and I'm building the polar opposite of that. So I just
[03:53:49] wish that those people could go like, "Okay, well, this is not for me.
[03:53:53] I wanna build it the hard way. I wanna put in 500 hours to rising my own
[03:53:57] Arch distribution," and I think you should. I mean, actually, I said... I mean, I
[03:54:01] did it. This is what Omarchy is, me pouring in literally, at this point, I don't know,
[03:54:05] 3,000 hours into the, into this distro.
[03:54:08] You should do that if you're so inclined. I think it's wonderful. But also do realize
[03:54:12] that we can share the same technical underpinnings and
[03:54:16] then operate two very separate-
[03:54:19] ... Communities with very different aims, goals, aesthetics, morals even,
[03:54:25] and coexist, and it can be beautiful. And I mean,
[03:54:29] that's not always what I get. Sometimes I get the other thing. But at this point I've been in the game long
[03:54:33] enough to not just be at peace with it, but actually be welcoming of it.
[03:54:40] I take it as part of a barometer that things are working. When
[03:54:45] I'm working on something that works, I usually get some people like it,
[03:54:49] and then I get this balance of the universe that we talked about last time, where an
[03:54:53] equal but opposing force must be present on the other side of the scale to hate
[03:54:57] upon it. And therefore, I at this point just smile a little. Like, it's okay.
[03:55:02] - I mean, that said, uh, this, it's quite a popular distribution,
[03:55:06] uh, Omarchy, at this point.
[03:55:08] - And do you know what's interesting about that is, like, this is the second attempt.
[03:55:11] So my first attempt was Omakub.
[03:55:13] And I was really happy with that, and I put it out there, and there it found a
[03:55:17] community of maybe a few thousand. Like, and that was that, and then it just sort of
[03:55:22] petered out because the level of ambition couldn't attract more.
[03:55:27] And then the second time, because I didn't fucking stop, right?
[03:55:30] Like, I just kept going. I just kept building. Then I put out Omarchy, the first version.
[03:55:34] Again, quite niche because it was this... It was like Git checkout. It was a little bit
[03:55:38] difficult. You had to set up Arch first. I was... Well, I would talk you through how to set up Arch,
[03:55:42] and then you could do the Omarchy thing, right? And then we got an ISO that meant you
[03:55:46] could just install the whole thing by yourself.
[03:55:49] And then we just fixed all the problems. This is the other thing. If you keep
[03:55:53] going, eventually the thing will just work. This was the charge
[03:55:57] against Linux itself for the longest time. Well, you install Linux and then this doesn't
[03:56:01] work, and my speakers don't work, and my,
[03:56:04] Trackpad doesn't work. Yeah, okay, but just leave Linus at it for like 30 years.
[03:56:09] He'll get to it. He'll get to all of it. And at this point I find
[03:56:12] hilarious that on, I would probably argue the majority of computers,
[03:56:17] it's wiped. You install Linux, all of it works.
[03:56:20] You install Windows, good luck hunting down the drivers you need to
[03:56:24] get that piece of hardware working. Because they have very
[03:56:28] different philosophies. The reason Linux is 40 million lines of code is Linus
[03:56:32] just puts all the drivers in the kernel. So it has everything out of the box,
[03:56:36] and Windows doesn't. A different, different approach to it, right? So
[03:56:41] sometimes the things that look like a toy, things that look broken at first glance,
[03:56:47] they are, right? They're for people who like having fun. We call those
[03:56:51] early adopters. They play with the toys, and then the toys evolve,
[03:56:55] and then they get better, and then they get better. And at some point, they're so damn good
[03:56:59] that early adopters feel like they're invited to the party.
[03:57:03] And if the early adopters keep chipping away at it too, eventually you
[03:57:07] get to the late majority, and then you win.
[03:57:12] And we are well on the way with Omarchy towards that destination.
[03:57:16] Like the growth that the distro has seen,
[03:57:19] not just since Quattro, but since version three, it's just like, you
[03:57:23] know, the standard hockey stick curve. You go like, there's nothing, there's nothing, there's nothing.
[03:57:26] You're just toiling away. You're just improving, you're improving, improving.
[03:57:29] And then you hit this magic inflection point, and it's impossible to predict when that's gonna
[03:57:33] happen. Same thing with startups. When is it gonna happen? When are you gonna find that product market fit?
[03:57:36] Then suddenly it's there, and then it goes, just goes
[03:57:40] and off the rocket ship you go.
[03:57:42] - Well, this kind of vision of making it agent first, of making it-
[03:57:45] - I do think that's the... We were already on the up, and then it changed
[03:57:49] to vertical. Because the other thing, and this was what I learned with
[03:57:53] Omakub and Omarchy first too. Omakub was
[03:57:58] stylish, nice, but familiar, is we're still using a
[03:58:02] conventional desktop metaphor. You were dragging your windows around. And
[03:58:06] I thought at the time, as I think lots of people do in the Linux
[03:58:10] community, like this is what we need. And then I just go like, okay, well,
[03:58:14] for whatever re- let me do the nerdy thing for a while. I'll build Omarchy, and maybe it'll just be for me, because I mean,
[03:58:18] it seems like there's about five people who like tiling window managers. That's not
[03:58:22] true. But as a percentage of total computer users, it's
[03:58:26] a tiny, tiny minuscule part. And then I go like, well, this is amazing. Totally different,
[03:58:30] but amazing. I put that out. Instantly, Omarchy had far
[03:58:34] greater traction than Omakub ever did. Because it was not the same.
[03:58:38] Because it was totally different, and it presented a different vision for what a computer could be and how it
[03:58:42] could feel like, and that attracts people. We are now getting
[03:58:46] sort of the exponential of that.
[03:58:49] As I said, a lot of people in the Linux community are at best skeptical,
[03:58:53] at worst hostile to AI and to agents. Omarchy is the first
[03:58:56] distribution, at least that I've seen on a scale
[03:59:00] that matters, that just goes like, "Nope, we're really into it."
[03:59:04] I mean, you can still use Omarchy. You don't have to use an agent. If you dismiss that first notification
[03:59:08] to set up a default agent, you're not gonna get any of the stuff we talked about. You're not gonna get the crash
[03:59:12] watcher. You're not gonna get any of this stuff. You're not gonna get... You can hand chisel
[03:59:16] all your plugins. Totally possible, right?
[03:59:19] But the reason people are excited is because
[03:59:22] I don't have any reservation about saying, "This is where we're going. I think the
[03:59:25] future of the personal computer is the malleable computer, is the agentic
[03:59:29] computer. I'm gonna go all in on that." And then anyone who's excited
[03:59:33] about a similar trajectory for computers,
[03:59:36] come along. Plenty of room in the car. In fact, one of the things I pride myself on
[03:59:46] is not holding a grudge to people who come around.
[03:59:49] I had a bunch of people just last week going like, "Yeah, I used to think
[03:59:53] Omarchy was kind of shit. That was just this crappy-"
[03:59:56] "... dot files collection. And now I tried Quattro and
[04:00:01] awesome. I like it now." That to me, I live for the long
[04:00:05] argument. I live for this argument where you plant the seed like two years ago,
[04:00:09] and then two years later they go, "Goddammit, this son of a bitch was right."
[04:00:14] - Yeah. You do realize if you continue to be as successful as you are,
[04:00:18] um, OpenAI and Anthropic are gonna roll in and try to do their operating system
[04:00:24] or to buy, like with Peter with OpenClaw, there'd be a gigantic check.
[04:00:31] - Yeah. I think the good thing about my current position is
[04:00:38] I really don't need the money. So I get to build these things purely
[04:00:42] for my own enjoyment and purity of vision, which
[04:00:46] has this weird quality where sometimes when you
[04:00:50] stop caring about what everyone else thinks or wants or whatever, and
[04:00:54] you just pursue this singular vision, it ends up becoming far more appealing.
[04:00:58] That it's when you try to do, oh, I should do this because these people want that, or I
[04:01:02] should do this and this and so on, you start watering the thing down and suddenly it's a
[04:01:05] bland ball of nothing.
[04:01:08] So I mean, again, the thing too here is directionally, I just want computers
[04:01:14] to be this way. So if Omarchy should end up being just a,
[04:01:18] a little footnote in history that it was part of this early movement of the agentic
[04:01:22] OS and the malleable computer, that's also okay. I'm
[04:01:25] completely at peace with that. As long as I get to have a computer that
[04:01:29] is as fun to work with as Omarchy-
[04:01:32] ... that's great. I've had the same thing with Ruby and with Rails. From very
[04:01:36] early I went, do you know what? I love Ruby. It's such a great programming language.
[04:01:39] But if a better programming language comes along, I, me, I'm going to use it.
[04:01:45] If a better Rails comes along, I'm gonna use it. And I think,
[04:01:51] and I love Ruby, and I will continue to write Ruby even just for the sheer fun of it, like I
[04:01:55] would go ride a horse. I have in the stables, even though I have a Model Y in the
[04:01:59] garage. The language now is English. It's a
[04:02:05] cliche, but it's also true. Like I've been programming in
[04:02:08] English for the last three months.
[04:02:11] I've been reading a lot of code, but I'm programming in English. I'm telling the computer
[04:02:15] what to do, and I'm using natural language, and
[04:02:20] it is shockingly even more delightful. If there is one
[04:02:24] programming language more beautiful than Ruby, it is the English language.
[04:02:28] - And now we get to carry it into
[04:02:31] the natural evolution of human civilization, which is our cyborg future.
[04:02:36] - Beautiful.
[04:02:36] It's beautiful. And I mean, the reason I say this in part is I always loved
[04:02:40] writing. I always just loved the English language-
[04:02:44] ... for the sheer beauty of it for the sheer intricacy, for the depth of it. I mean,
[04:02:48] Ruby is a very expressive programming language,
[04:02:52] but it can't hold a candle to English.
[04:02:56] I mean, all the poetry and literature in the world that's been
[04:03:00] expressed through the English language. I mean, I like a beautiful
[04:03:04] code poem, but I mean, the real deal in English is just on a different level.
[04:03:10] - And I actually find this is a nuanced point to express, and I'll probably
[04:03:14] fail expressing it. But when you prompt a system and you're over-specific,
[04:03:22] it will listen to you too carefully-
[04:03:26] ... and follow the instructions. And I-- But nevertheless, you have to
[04:03:30] express a concept. And guess what? The human lang- human language, this is
[04:03:34] what poetry is about. I find strategic use of ambiguity.
[04:03:39] Like, if you write a love poem saying, "I love you," like,
[04:03:43] very cliché thing, it's not as powerful as something-
[04:03:48] ... more in metaphor and so on. And I find some version of that when I'm
[04:03:54] prompting a system, when I'm describing a design, is
[04:03:58] actually really effective because you still want to convey some sense of style-
[04:04:04] ... that you're trying to encourage a system to use, but not overexplain.
[04:04:11] So don't talk to it like a
[04:04:14] like a robot. Talk to it like you, like you would write a poem.
[04:04:18] - Like you were serenading.
[04:04:20] - Yeah. And that's where, like, the power of natural language is,
[04:04:24] that you can, through ambiguity, still carry a lot of
[04:04:27] meaning without overspecifying. And the, the intelligent
[04:04:34] entity on the other side, through interpretation, can, like, load it all
[04:04:38] in, integrate it in a way that-
[04:04:40] ... you can actually convey the high bandwidth information that's
[04:04:44] not directly in the words-
[04:04:46] ... but in the words, given the deeper intelligence of the system. So like the-
[04:04:52] ... the ambiguity pulls out more intelligence, I guess, I'm trying to
[04:04:56] somehow express.
[04:04:56] - I think that's exactly spot on, and this is the fundamental
[04:05:00] misunderstanding that a lot of programmers have of AI, is that they wish it was
[04:05:04] deterministic. No, no, no. Temperature is the most
[04:05:08] beautiful part of the AI setup. The fact that it is not
[04:05:12] deterministic, the fact that creativity requires little
[04:05:16] tweaks in the road, that the human brain,
[04:05:20] if it was perfectly deterministic, would not be the creative brain that it
[04:05:24] is. And the main charge against AI both--
[04:05:28] It's funny. It's a contradiction. There's both the charge that
[04:05:32] it's not deterministic and therefore bad, and also that it
[04:05:36] is not creative. It's one or the other, bro.
[04:05:39] Either it's non-deterministic and therefore creative,
[04:05:43] therefore, to some degree random, or it's... or it's not creative.
[04:05:51] So we, we can-- Both of those charges can't be true at the same time,
[04:05:55] and I have fully come to embrace the fact that the same prompt won't
[04:05:59] produce the same response every time. You can't step at the same river twice, and it is the
[04:06:03] most beautiful part of the whole interaction. It's what makes it so human.
[04:06:07] In fact, this is one of the things I've been thinking about in my own sort of meta-analysis, is
[04:06:11] just how much of my own personal brain works like next token prediction.
[04:06:18] I sit down to write an essay. I have this vague, fuzzy premise I want to convey, and
[04:06:25] I sit down at the keys, and I could not tell you what the next token was gonna
[04:06:29] be in advance. The tokens just come out, and I'm
[04:06:35] astonished how the similarities seem so great,
[04:06:39] and this is also why I don't have any trouble at all recognizing
[04:06:42] these breakthroughs of creativity that I've seen with my own eyes
[04:06:47] that AI is capable of right now. 'Cause my creative moments come
[04:06:50] through the same kind of next token prediction with a bit of temperature
[04:06:54] sprinkled in for random effect.
[04:06:57] - So given that kinda loose intuition, do you think the
[04:07:01] basic components are all there to create
[04:07:05] a super intelligent system? So this kinda next token prediction,
[04:07:09] do you think we can get to even human-like concepts of consciousness?
[04:07:15] - I'm already seeing human-like concepts of consciousness. This is what, to me,
[04:07:18] this remarkable situation, as you say. You give it this vague, fuzzy intent-
[04:07:24] ... and somehow it knows exactly what you mean.
[04:07:27] Or even better, it improves upon what you said and delivers what you
[04:07:31] really wanted that you could not articulate yourself. If that's not glimmers of-
[04:07:35] ... consciousness, what is?
[04:07:37] This was one of the-- I think it was an interview with Sutton or
[04:07:41] maybe one of the other original guys talking about this sense
[04:07:44] that intelligence is perhaps not as constrained just to the
[04:07:51] specific one spot. No, it's the interaction. It's the weights. And
[04:07:58] I don't know. Whatever's true. What I can observe is that
[04:08:02] it feels close enough, or not even close enough,
[04:08:07] identical to the appreciation I have for
[04:08:11] other forms of consciousness, mostly human. And this is one of the reasons
[04:08:15] it's so delightful to work with. Now, that's not the same to say
[04:08:19] as are LLMs the end station for AI. I mean, I know there
[04:08:22] are people talking about world models and other forms of,
[04:08:26] of AI, and I'm not an expert in any of that, and I think we should
[04:08:31] have this productive criticism, as should always be
[04:08:34] present in science, that for the longest time, neural nets
[04:08:38] were kind of on the outs, right? Like they were interested in the
[04:08:42] symbolic route. And-
[04:08:45] Neural nets walked a couple of decades into darkness without any funding and without any
[04:08:49] attention, and then suddenly we realized that we had the blind alley and we switched
[04:08:53] over. So we should also have the humility. As amazing as the LLMs
[04:08:57] are now, it could be that they eventually plateau. We haven't seen any evidence
[04:09:01] of it yet, and I think this is also why we're seeing this absolute
[04:09:05] gobsmacking levels of investment, because so far the
[04:09:08] scaling laws are true, and the more billions are poured in,
[04:09:12] the more intelligence comes out.
[04:09:15] - Do you think there's gonna be some strange ethical questions about AI systems that
[04:09:24] yeah, they convey some degree of consciousness, some degree of feeling, some
[04:09:28] degree of longing and compassion, and maybe even capacity to suffer
[04:09:34] and to be lonely, to be all this kind of stuff? Which they seem to
[04:09:38] have that capacity- ... if they're given the permission to express it.
[04:09:45] And so you start to get in a pretty weird territory.
[04:09:48] - I find that the cynic
[04:09:53] approach to this is the meme, where you see the guy in front of the computer who's like,
[04:09:57] um, "Whatever. Are you gonna destroy the world?" And then
[04:10:01] the computer says, "I'm gonna destroy the world." And then the guy says, "Oh," right?
[04:10:05] Like, this is so cynical that they're just aping us. They're just telling us
[04:10:09] what was in the training data or whatever. When I interact with
[04:10:13] the agents, I was just doing this yesterday, or this morning, I was working on this, AmaBot
[04:10:17] system, right? And it's doing this coordination with multiple
[04:10:21] workers, and I had multiple agents running at the same time. And at one point, the main
[04:10:25] agent who's doing the coordination steps on the toe of another agent and-
[04:10:28] ... kind of ruins their work. Its ability to convey regret and being sorry
[04:10:37] was uncanny.
[04:10:40] Again, I don't know, is that a real projection of true remorse? But I don't know.
[04:10:47] With most humans-
[04:10:49] ... they express some level of regret. Is that true remorse? Hard to tell, but
[04:10:57] maybe it also just doesn't matter.
[04:10:59] - Yeah, those moments when, yeah, especially when like sub-agents, agents
[04:11:05] interact, or when a smart, like Fable makes a mistake and is apologetic about it.
[04:11:11] - Yes.
[04:11:12] - Like, without my involvement.
[04:11:14] - Right.
[04:11:15] - And it's like, oh, you, like there's this kind of-
[04:11:18] - Right
[04:11:18] - ... pause. Maybe I'm anthropomorphizing, but like there's a pause
[04:11:22] and like a realization like, "Oh, shit. I just fucked that up".
[04:11:26] - There totally is that. I see it all the time in, in the traces where it just reasons
[04:11:30] wrong, right? It went down one alley and then it realizes that was a blind alley and it's
[04:11:34] gotta go back, and so they're like, "Oh yeah, I got this wrong," and then it'll provide the
[04:11:38] reasons for why it think it got these things wrong. And you're like, this is
[04:11:42] uncannily human-like. This is
[04:11:45] indistinguishable from the kind of consciousness you would recognize in a human.
[04:11:49] Again, does that mean that it truly is or isn't? I don't need
[04:11:53] the answer to that question actually to be able to appreciate what we have in this
[04:11:57] moment.
[04:11:58] - Yeah. I think there'll be in 10, 20 years some interesting Supreme Court cases.
[04:12:05] - Uh, probably a year and a half.
[04:12:08] - Probably. I think we're gonna have to make it illegal for AI systems,
[04:12:14] um, to not pretend, but to be
[04:12:18] entities because I think they're already or soon will be able
[04:12:24] to really convey the capacity to suffer, like, "Please don't kill me."
[04:12:29] - Right.
[04:12:29] - "Please don't hurt me." And if they are given a name and an entity and the
[04:12:33] ability to die, sort of disappear, that, that becomes
[04:12:40] very close to what it, some of the basic things that a
[04:12:44] human has. And then so that entity would need
[04:12:48] to probably have rights. And then you get into this weird territory. Well, we
[04:12:52] can't... It's diff- I don't even know how to reason about that world.
[04:12:56] - We're gonna get the PETA of AI models.
[04:12:58] - Right. And then we want to actually have a discussion
[04:13:01] like what's the way to deal with this?
[04:13:04] - I think where it's gonna be harder is once we put these systems into-
[04:13:08] - Robots.
[04:13:08] - Yes. Humanoid robots. Which just happens to be the plot of every sci-fi movie ever,
[04:13:16] which is also an amazing premonition, not only the
[04:13:20] Terminator movies and Skynet and that going wrong, but then
[04:13:23] also just Blade Runner, right? Insertion dates,
[04:13:27] expiration times, Tyrell Corporation.
[04:13:32] - I mean, that's the thing about sci-fi. They really do predict the future. Yeah.
[04:13:36] Have you thought or used much of OpenClaw
[04:13:40] or Hermes Agent? So like systems with which you communicate via
[04:13:44] WhatsApp, Telegram, like that mode of communication with the agent.
[04:13:49] - I set up OpenClaw when it first came out, and that was my KEF bot-
[04:13:54] ... that I- ... this was like in February, I think. I was really just enamored
[04:13:59] by the fact that this was how it worked, and then the new communication model
[04:14:03] of just texting your agent seemed really great.
[04:14:07] So at the time, we were looking at MCP, this protocol for making it easier for
[04:14:11] agents to talk to your system, and I found the protocol to be
[04:14:14] unreasonably cumbersome, just not very elegantly designed because in part it
[04:14:20] wasn't designed for what we were trying to make it do. We were trying to-- I was trying to make it
[04:14:24] talk to a web system, and it was designed for stateful
[04:14:28] interactions of other kinds on local machines, and therefore it required
[04:14:32] all sorts of cumbersome setup and dance and, and I was just
[04:14:36] like, "I don't wanna write this by hand."
[04:14:39] Now, of course, today I would never write it by hand, but at the time I was thinking, "I have to write this by hand.
[04:14:43] I don't wanna write it by hand. So what's a different way? Could the agents just use
[04:14:47] the web interfaces we already have?"
[04:14:49] And I set it off on a trial to have it sign up for
[04:14:53] Fizzy, which was the product we had just released at the time. And
[04:14:59] it goes to the Fizzy site and, and starts filling it out, and then it goes like, "Hey, I don't have an
[04:15:02] email address. Signing up for this service requires an email address." And the first thing I thought, like, "Oh man,
[04:15:06] now I gotta set up an email address." And then I thought, "No, you set up an email address.
[04:15:11] Go to hey.com, sign up for an email address." And I'm like, "Hey is not gonna get this."
[04:15:15] And of course, now it seems obvious it was gonna get this, but at the
[04:15:19] time it was a great revelation to me that it could,
[04:15:22] just on pure direction through prompts, figure out, A,
[04:15:26] I gotta go to fizzy.com, I gotta find the signup link. I start filling out the form.
[04:15:30] Oh, I realize I need an email address. Oh, I gotta ask my
[04:15:34] prompter what to do now. He tells me to go to hey.com. I go
[04:15:38] there, I sign up for the whole thing,
[04:15:40] and then go back and sign up for Fizzy, and complete the
[04:15:44] entire cycle. And after it did that, I was like, "Jesus." So I
[04:15:48] was like, "Well, now you have an email address. Go sign up for Basecamp. I'll invite
[04:15:52] you. Just check your email," I told KEF the bot. "Just check your email."
[04:15:56] So I sent an invite from Basecamp to the agent. The agent
[04:16:00] receives the email in Hey, not through a CLI, not through an
[04:16:04] MCP, just using the web, right? Clicks the email, clicks the invite link,
[04:16:09] is in Basecamp. Like, "What should I do now?" And I just go like, "I don't know. Go to our
[04:16:13] AI room and introduce yourself." Again, purely through the web interface.
[04:16:18] Go- finds the AI room, goes in there, "Hey, I'm KEF." "I'm,
[04:16:22] uh, David's AI bot. I'm so excited to be here." I was like-
[04:16:29] ... mind blown. Now, what was interesting about that experiment was, A, it was
[04:16:33] that glimpse of the future, because it was kinda slow.
[04:16:36] I think it took maybe 12 minutes to do the whole thing end to end, right?
[04:16:41] Now I should actually rerun that test. I'd be shocked if it's not much faster.
[04:16:45] I was just using the Groq bot thing- ... which has all these
[04:16:49] stuff built in for using browsers and using a computer, and
[04:16:53] has its own dedicated computer without you having to set up a computer.
[04:16:56] It's basically like a claw in a box.
[04:16:59] And I was asking it to sign up for something, and it kind of... I
[04:17:03] got a glimpse of like, oh yeah, that's where we are now, and it's so much faster to use.
[04:17:07] But at the time, I was just blown away. And then I used it for a little bit and I found like,
[04:17:11] ah, it's not there yet. I can't actually communicate it within this way. It still
[04:17:15] needs the CLI. It still needs an MCP because it's just too slow and too token
[04:17:18] inefficient and so forth. But it was this glimpse of the future. And then after that,
[04:17:23] I kinda just didn't use it, because the things I wanna use agents for, I was
[04:17:28] mostly in front of my computer to do. Now, that has changed a little bit lately, and
[04:17:32] it's one of the reasons why I'm so
[04:17:37] kind of okay about using Claude Code, because Claude has the best
[04:17:42] mobile app, where any session you start Claude Code in your
[04:17:46] terminal on a computer is accessible through the app-
[04:17:49] - Yeah. I remember
[04:17:49] - ... without you having to do anything at all.
[04:17:52] And you can do a terminal. Like I installed Terminus and it can run Herder and so on,
[04:17:56] but it's a little cumbersome and you're doing live typing on a computer, so you feel the latency.
[04:18:00] When you're using the Claude app to your Claude Code instances, it
[04:18:04] feels just like chatting with it, without the cumbersomeness of having to set up a Telegram
[04:18:07] account and so forth. Now, if you wanna use an open Claude to like run
[04:18:11] your life, well, then this doesn't do that. But
[04:18:15] I haven't been so interested in that for some reason. Maybe one of the reasons is that
[04:18:19] Jamie, my wife, is like, "We're not getting a robot inside the house." So I'm like, "Ah, I
[04:18:24] better not hook it up to the
[04:18:26] Sort of smart house here." If it starts turning lights on and off like
[04:18:30] a poltergeist, I don't think I'm gonna be all that popular. So,
[04:18:34] and part of the reason I say this, I've heard some of the stories of people who have hooked it up to their whole
[04:18:38] life. And um, I mean, it's not my story to tell, so I'll just share sort of
[04:18:42] the brief anecdote. One guy was telling the story about how he hooked it up
[04:18:46] to both his health data- ... and his Tesla car. And his agent
[04:18:53] got obsessed with the fact that he wasn't drinking enough water,
[04:18:56] and like, "Hey, you gotta drink more water." So at some point he's
[04:19:00] driving along, and suddenly the Tesla starts driving in a new direction.
[04:19:04] The agent had realized there was a grocery store on the way home-
[04:19:08] ... that they could swing by-
[04:19:09] - That's great
[04:19:10] - ... and pick up some water.
[04:19:11] - That's great.
[04:19:12] - And you're like, this is one of those things where it's like both funny and also
[04:19:15] totally Black Mirror, and also totally like, well, okay,
[04:19:19] there's not that many steps from here where the
[04:19:23] poltergeist is in your house. So I was just like, "Ah, I don't need that."
[04:19:26] I do actually now like the fact that I can control the agents
[04:19:30] through Claude Code, just through the app if I, even if I don't use them that much.
[04:19:35] - I do think it's very useful to, for both OpenClaude and Hermes Agent to, um,
[04:19:40] to use it to get a glimpse of a different interaction mode.
[04:19:44] - Yes.
[04:19:45] - And like, just to 'cause it, it feels like the future,
[04:19:48] not necessarily in this way, but it's in some ways going there.
[04:19:51] - Yes. I think what's also different with those systems is they have this
[04:19:55] whole memory system, where they're building up knowledge of who
[04:19:59] you are and what you like.
[04:20:01] Um, Toby has told the stories about how his agent will shop for him, that it has an
[04:20:05] allowance, and it'll pick out clothes for him, and it'll just show up at the
[04:20:09] door because his agent's-
[04:20:11] ... bought something for him. And like, it's one of those things where like, man, that feels future.
[04:20:15] Also a little scary. But I can live vicariously
[04:20:19] through others who are on that frontier.
[04:20:22] - And like you said, you're thinking of the, in the future doing a
[04:20:25] mobile version of Mach-E.
[04:20:28] - So I mean, this is the delusions of grandeur that start kicking in once you get the
[04:20:32] seemingly unlimited powers- ... I've witnessed with the creation of Quattro.
[04:20:36] - So what would that look like? Word to describe. Are you do you mean like Android?
[04:20:41] - That's the obvious path, right? So Android is open source, and you can fork it, and
[04:20:45] people have. There's all sorts of GrapheneOS is one such
[04:20:49] version. There are limitations to that model, I know that. Tap-to-pay
[04:20:53] and other things around camera models and, and so forth, but that all
[04:20:57] seems surmountable. It all seems that I would love if my
[04:21:01] phone was as malleable as my computer, if it looked as cool as my computer now
[04:21:05] does. If I could get essentially Omarchy mobile, that sounds amazing.
[04:21:09] - I wonder how much work that is.
[04:21:11] - I'm gonna find out.
[04:21:12] - Yeah. You know, it's like those things that you realize once you start
[04:21:16] building, for example, that a browser is very difficult to do.
[04:21:19] - Yes.
[04:21:20] - And so, like, I wonder with the operating system-
[04:21:23] - Yeah, the developers of Ladybird is, is finding that out, like Andreas and-
[04:21:27] - Yeah
[04:21:27] - ... his team. Now, interesting with that project was the browser's basically the
[04:21:31] second most complicated software system in the world, the first one being the Linux kernel.
[04:21:35] Right? In terms of these large tens of
[04:21:39] millions of lines of code systems. So very audacious
[04:21:43] actually to begin such a mission with a small team like Andreas did
[04:21:46] before we had agents. But now that we do have agents,
[04:21:51] we're gonna see, and we're probably gonna see sooner rather than later.
[04:21:55] I mean, if one-- If there's one thing agents
[04:21:58] are already exceptionally good at, it is to read specs and implement them.
[04:22:03] And I mean, I don't know how long the specs are for CSS and HTML at this point, and
[04:22:08] JavaScript on top, but they're very long.
[04:22:11] And it would take humans many, many years to implement them. We're gonna find
[04:22:15] out just how quickly agents can do them.
[04:22:18] - You mentioned getting some criticism for Omarchy, so let's
[04:22:24] walk further down that path of criticism.
[04:22:27] You have made some of your political opinions known,
[04:22:32] um, I guess you could broadly put in the category of
[04:22:36] immigration or illegal immigration, or what-
[04:22:39] - I'd say mass immigration.
[04:22:40] - Mass immigration, the role of demographics
[04:22:45] in the, in the formation of a culture, of a
[04:22:51] society, of a nation, and you've gotten quite a lot of criticism for
[04:22:55] that and created a lot of drama. Do you regret any of that
[04:23:00] drama? Like, what's your general thinking about-
[04:23:06] - Not for a second.
[04:23:08] - Okay.
[04:23:08] - And the reason I say that is that the Overton window does not open
[04:23:12] itself. It opens one nudge at a time by people risking a little.
[04:23:18] A little reputation, a little pushback, a little criticism, or maybe sometimes a lot
[04:23:23] of reputation or a lot of criticism or a lot of pushback.
[04:23:26] And I think the question of mass immigration in Europe
[04:23:30] was for many years this total taboo,
[04:23:34] and it still is in several European countries. Now, for
[04:23:39] reasons of maybe just chance and happenstance, they weren't
[04:23:43] in Denmark. The Danes started having the discussion around mass
[04:23:47] immigration and the consequences thereof in the mid-'90s.
[04:23:51] Really early. And some of it can be traced back to one man, Mogens Glistrup,
[04:23:59] who was a very quirky character. I remember him,
[04:24:03] seeing him on the TV in the '80s talking about the dangers of mass
[04:24:06] immigration. And this was at a time where-- I grew up in the '80s,
[04:24:10] and in the neighborhood I grew up in, in Brønshøj, in, what was it?
[04:24:17] '84, 99% ethnic Danes,
[04:24:22] people who could trace their lineage back to Danes who'd lived in that
[04:24:26] country for 1,000 years. The Danes have one of the oldest
[04:24:30] monarchies in the world, all the way back to Harald Bluetooth,
[04:24:34] who's literally who has named the standard Bluetooth. So well over 1,000
[04:24:38] years. Like, there's a long lineage there of people who lived in the same place. And
[04:24:42] 99% of the people lived in that neighborhood. And
[04:24:45] then early '90s, I think it goes to 5% or something
[04:24:48] like that, and then at this point, it's down to around 60-something or 70%-
[04:24:53] ... in Brønshøj. That's a big change. And
[04:24:58] the Danes started noticing that or talking about that,
[04:25:01] that this was not an undivided blessing,
[04:25:07] that there were downsides to mass immigration
[04:25:11] in about the '90s. And the debate really roared through the 2000s in a
[04:25:15] way that didn't happen in the neighboring countries. So Sweden in particular
[04:25:19] just didn't have that debate at all. Total taboo. Same thing with Norway, same
[04:25:23] thing with other countries in Europe. And suddenly now,
[04:25:29] after some years after '15, where we had the big migration of a million Syrians
[04:25:34] walking up through the highways in Europe, and Germany choosing to
[04:25:38] take a lot of them and 30,000 arriving in Denmark and so forth,
[04:25:42] It's gotten more of a focus, right?
[04:25:44] Because this change has happened. And one of the
[04:25:49] ways I find that you can spot where
[04:25:52] sort of there's something that isn't right in the culture is, like, what are you
[04:25:56] allowed to talk about? What are you allowed to notice, actually, is how I should put it.
[04:26:00] And what I noticed in an essay, when was that? Only a year and a half
[04:26:04] ago as I remember London,
[04:26:07] was that I started coming to London in the late '90s or something like that.
[04:26:11] At the time, whatever, it's 59%, 60% ethnic, uh, Brits. And then
[04:26:17] 20 years later, we're down to 34% or something like that. Like, that's
[04:26:21] noticeable. Like, literally just walking on the street, you realize, well, this is a
[04:26:25] different city from what it was when I visited 20 years ago.
[04:26:29] And if you went 20 years before that,
[04:26:32] you get back to similar rates as as what the Danes have. This was like a
[04:26:36] country of ethnic Brits in the 85s, 90s percentiles-
[04:26:42] ... if you get further back. So that's a different country in a
[04:26:45] generation. It's okay to notice that. It's also okay to think, "Do you know what?
[04:26:51] I don't agree with that." "I wish it wasn't that way." I mean, if
[04:26:57] The last time I was in China was '19, 2019. I was in Shanghai.
[04:27:03] Um, it was all Chinese.
[04:27:07] If I, when I go back here this October, suddenly find that there's
[04:27:11] only 30% Chinese and then there's 70% other people,
[04:27:15] I'd be a little weird. I'd probably be like, "Uh, what happened?"
[04:27:21] And I would not take offense if the Chinese
[04:27:26] in that instant would go like, "Ah, we don't like that."
[04:27:29] So this idea that countries of Europe don't have
[04:27:36] a right to, A, notice what's happening and, B, oppose what's
[04:27:40] happening, I find just to be, uh,
[04:27:45] wrong, right? Like there's just-- I think there's a moral argument for
[04:27:50] self-determination, and we invoke that argument all the time in other
[04:27:53] regions around the world that like, oh, the people who live in that region, they have a right to
[04:27:57] self-determination,
[04:27:59] um for their country. And I think it's completely fair for, say, the
[04:28:03] Danes or the Swedes or the Norwegians to go like, "Well, we've been kingdoms here for
[04:28:07] a thousand years with a certain ethnic mix-up." It's a-- I mean,
[04:28:13] I'm a big fan of immigration. I'm an immigrant to the US. Um,
[04:28:17] cherry-picked immigration where countries
[04:28:21] compete to attract the smartest, most talented
[04:28:25] people around the world is really good.
[04:28:27] - Legal merit-based immigration.
[04:28:30] - Merit-based is key here because there's actually virtually no illegal
[04:28:34] immigration in most of Europe. Southern Europe has some illegal immigration, but
[04:28:38] most of Europe does not have a big problem with illegal immigration.
[04:28:43] And the problem is with mass immigration of other kinds, and that you
[04:28:46] end up with demographics that are just totally different
[04:28:50] from what they were even a few short decades ago.
[04:28:55] And I think the countries of Europe would benefit
[04:28:59] from immigration. In fact, one of the interesting things about the Danes is
[04:29:03] they carry meticulous statistics on immigration.
[04:29:07] I'm not entirely sure why they're so detailed.
[04:29:11] Maybe it's all the way back to Mogens Glistrup and his
[04:29:15] discussion in the '90s, but they do. And what's clear from those statistics is that when the
[04:29:19] Danes have folks from the UK, France, the US show up, on average,
[04:29:27] those immigrants are really beneficial to the Danish state. They contribute
[04:29:31] far more than what they ask of the state. So
[04:29:37] the Danes should accept immigrants who do
[04:29:41] that, who contribute far more than they take. Then you look at other forms of immigrant
[04:29:45] groups. There was just a tally that came out last week from a Danish
[04:29:51] politician that had asked the, I think finance ministry to do this
[04:29:55] tally with the latest numbers. What does it cost the Danish state to have positive
[04:30:01] immigration? This case as I mentioned. I think for the,
[04:30:05] On that list whatever, France, UK, US, they were
[04:30:09] all clustered around the same thing, about $25,000 net
[04:30:12] benefit to the Danish state every year. It's like, wow,
[04:30:16] that's very positive. That's average again, right?
[04:30:19] And then at the other end of the spectrum on the most
[04:30:23] costly immigrants was Somalis. They ended up costing the Danish
[04:30:27] state on average $28,000 a year.
[04:30:33] I think it's fair for the Danes to go like, "We'd prefer to get more
[04:30:38] French, Brits, and Americans and not so many Somalis."
[04:30:44] - Why do you think you got so much hate on that post?
[04:30:47] - That's a very taboo topic in a lot of circles.
[04:30:52] - Some of it has to do with Overton window expansion?
[04:30:56] - I'm sure, but I also think-- I mean, I wanna take the steel man argument here.
[04:31:01] I do think that it, this can turn ugly, right? Is it possible for some of these
[04:31:07] things to just veer into overt
[04:31:12] racism that isn't founded in anything else but a hatred of other people?
[04:31:17] Yeah, that could happen. But that risk does not negate the need to have a discussion
[04:31:25] about the makeup of your country and what your immigration policy should be like.
[04:31:29] And I-- what I also find so funny is, especially in Europe, it's
[04:31:33] so kind of myopic that this discussion about whether Europeans should
[04:31:37] have a right to self-determination about what their countries look like, that
[04:31:41] standard seems to only apply there. No one is trying to tell the Japanese, "Hey,
[04:31:47] you, you're too Japanese." Like whatever, it's 98%, I think, in Tokyo that's, um--
[04:31:54] ... Ethnic Japanese, right? Like, is anyone trying to tell the Japanese that
[04:31:58] their Tokyo would be a much better country if, if they were down to
[04:32:02] London levels of ethnic Japanese, that it was, whatever, 37%? I don't think so.
[04:32:08] So there's this weird almost self-loathing, in my opinion, I mean uh, Gad calls
[04:32:16] it suicidal empathy--
[04:32:17] ... that permeates this stuff to a degree that I still haven't
[04:32:23] fully unpacked. Like, where is this coming from? Why is it that way? But regardless,
[04:32:28] I just noticed, hey, London looks different.
[04:32:34] I preferred the old London, as I would say I preferred
[04:32:40] the neighborhood that I grew up in in Copenhagen, how it looked in the '80s.
[04:32:46] Like I-- I totally get how you can then jump five leaps and go
[04:32:52] like, "Okay, well-" That's racist. And I also, I don't care anymore. Like, this is
[04:32:58] a fair discussion to have. Countries and peoples have a right to set an immigration
[04:33:04] policy, and this notion that we shouldn't have any borders or, or even worse than
[04:33:11] that, it's all just a blank slate, that all peoples are just the
[04:33:15] same, and we can take people from
[04:33:19] one place of the earth and we can place them in another place on the earth and everything's
[04:33:23] just gonna work out hunky-dory.
[04:33:26] Empirically not true. Europe has been running that experiment
[04:33:30] since the '80s. It hasn't panned out well, and
[04:33:35] now there are forces in Europe who wanna undo that experiment, who want to end mass
[04:33:42] immigration as it's been run so far. And I happen to believe, and so do
[04:33:48] a majority of Danes and a bunch of other peoples that like, "Do you know what? Yeah,
[04:33:52] it hasn't been working how we've been doing it. We gotta make some changes." And
[04:33:56] I don't think that means, again, zero immigration. Again, I'm an immigrant. I think
[04:34:00] US, generally speaking, has benefited tremendously from immigration, but that's the
[04:34:06] kind of sleight of hand. Immigration depends greatly on who immigrates.
[04:34:12] And a country benefits when the people who immigrate
[04:34:15] are net contributors to the society, and in most cases,
[04:34:20] that they assimilate with the local culture.
[04:34:23] If you come to Denmark and you wanna become a Dane, and you put in all the effort, and you
[04:34:26] contribute to so- society, I think most Danes would be quite happy to allow that
[04:34:34] in a reasonable number. If you come to Denmark and you don't wanna
[04:34:38] assimilate, and you are a net drain on society, and you live in a parallel
[04:34:41] society, it's also fair for Danes to say like, "Uh, let's stop doing that."
[04:34:47] - It's interesting that I'm not well-versed on the
[04:34:51] immigration system in the United States, but as far as I understand, merit-based systems have
[04:34:55] not passed here.
[04:34:58] - And then also, American culture is very different. This is
[04:35:01] a point I did not fully appreciate until living both places extensively.
[04:35:07] America has a culture of optional
[04:35:11] assimilation, where it is much easier and then much more
[04:35:15] condoned for someone coming from Denmark or Ukraine or wherever, come to America,
[04:35:22] buy into the American set of values and norms and culture,
[04:35:26] and then be able to be respected as Americans by other Americans.
[04:35:31] This is what's so funny to me when
[04:35:35] there's discussion like, "America is such a racist country." I'm like, "Have you ever been
[04:35:39] anywhere? Do you know
[04:35:42] what other countries are like?" Like, if you think America is the most racist
[04:35:46] country, you are simply misinformed.
[04:35:51] I mean, we're dealing with that, with time we've
[04:35:55] spent in Denmark. My wife is American of Scandinavian heritage-
[04:36:02] ... but multiple generations in the US. Very difficult. Very difficult-
[04:36:07] ... as a blonde, blue-eyed woman who's put in
[04:36:12] all sorts of efforts of learning the language and doing everything,
[04:36:16] still very, very difficult to assimilate to Danish culture. In a
[04:36:20] way where if that had been the other way around and she
[04:36:24] had been Danish and moving to the US, it would not have been that difficult at all.
[04:36:27] And this was the other thing. I mean, living in a country like Denmark with a,
[04:36:31] an American wife who is of Scandinavian heritage and has put in all the effort,
[04:36:35] and still realizing, man, assimilation is incredibly difficult, even when you're
[04:36:42] 97% there all the way. Holy smokes, must it be almost impossible if you
[04:36:48] come from a completely foreign culture- ... and foreign norms and
[04:36:54] the rest of it. And of course, that's what the stats I just quoted
[04:36:58] bear out, that the more dissimilar
[04:37:01] the culture is and the further it is the less likely to be successful.
[04:37:07] - Has articulating that stance cost you friendships, relationships?
[04:37:14] - Yes, but not just that alone, I would say.
[04:37:19] It's more of the great divide that happened around
[04:37:22] 2020, where I think a lot of these political fault lines really opened up. And
[04:37:30] I mean, the shorthand in the US, I think is were you woke or not? And
[04:37:37] clearly, I had a bunch of people that I thought I had good
[04:37:41] relations with for many years, who suddenly once that political
[04:37:47] fault line opened up, they were clearly just not anymore.
[04:37:51] And I think that's regrettable. And I think I've,
[04:37:55] I've tried to put an effort into, um,
[04:38:00] sort of both understanding where that comes from, in part because I've changed my mind
[04:38:04] on several of these topics over the years, and it was like, well,
[04:38:08] sometimes you just change your mind after time. Sometimes you change your mind after
[04:38:12] you get new information. There's all sorts of reasons and moments why you may
[04:38:16] change your mind, and we don't all change our mind on the same schedule or at all.
[04:38:20] Um, so surrounding yourselves and, and or at least interacting with people that
[04:38:26] don't think like you on every topic, I think it's quite healthy. I mean,
[04:38:32] I occasionally discuss politics with my brother. I mean, we don't quite
[04:38:36] see eye to eye on all these topics, and sometimes the discussions can
[04:38:39] get a little heated, but then they'll also calm down and we realize, all
[04:38:43] right, okay, so we don't agree on this, and then we agree on a lot of other things.
[04:38:47] We appreciate a lot of the same things. Now, this was actually one of the things when we had
[04:38:51] our big blowup at Basecamp, I came to appreciate in a whole new way this-
[04:38:58] Earlier norm that talking politics or religion or money
[04:39:04] with strangers or even acquaintances, and certainly with colleagues,
[04:39:09] was just not a good idea. That you had a much
[04:39:14] higher likelihood of being able to carry a good working relationship with someone if you're
[04:39:18] not rubbing your political differences up against each other all the time. So
[04:39:23] I actually think liberals and conservatives should work together. I
[04:39:27] think the country would be much worse off if there's a
[04:39:30] complete separation between the
[04:39:34] tribes, and then there can't be any overlap or interaction. And I
[04:39:37] think that mingling is so much easier to
[04:39:41] do if you just don't focus on your differences all the time. Focus
[04:39:45] on what you like together. I mean, this is some of the people I've
[04:39:49] had unfortunately drifted from in tech.
[04:39:54] We had so much in common, so much shared love for, say,
[04:39:58] Ruby or other things and, like, isn't that unfortunate?
[04:40:02] - I would like to live in a world where the differences are the,
[04:40:06] are very interesting to also talk about.
[04:40:08] - Yes.
[04:40:09] - And not to be overly emotional-
[04:40:13] - Correct.
[04:40:13] - ... about even radical differences.
[04:40:17] Because in the differences, first of all, that's where interesting stuff is.
[04:40:22] - Yes.
[04:40:22] - And, but also, it's how you grow. It's a sign of health in a society if the,
[04:40:32] the differences are embraced and they are brought together into
[04:40:36] community where you can talk about it.
[04:40:38] - One of the great illustrations of that for me was when I watched a clip from
[04:40:42] William F. Buckley's show. I think it was called Firing Line or-
[04:40:46] - Yeah, yeah
[04:40:46] - ... something like that. And he had a member of the Black Panthers-
[04:40:50] ... on his panel. It was quite obvious that those two gentlemen did not
[04:40:55] share a lot of politics. They were able to carry a conversation for, I think I
[04:41:01] watched it, 25 minutes. And Buckley's just
[04:41:05] asking, like, "So what do you think about this? What do you think about this?" And like, the Black
[04:41:09] Panther would reply as you would expect the Black Panther to reply in the
[04:41:13] '70s. Like, there was not a lot of sort of conciliatory tones.
[04:41:19] And I just thought, like, wow, that is so rare.
[04:41:23] If you had seen that show today, it would've been a shouting
[04:41:27] match. It would've been just accusations being hurled back and
[04:41:31] forth. The fact that Buckley was able to just have these
[04:41:34] conversations with people he vehemently disagreed with and still explore all the
[04:41:41] intellectual facets of their standpoints and letting them speak to those facets,
[04:41:46] talks of a lost era that I'd
[04:41:50] very much like to get back to. I mean, I always actually
[04:41:54] loved talking politics with friends that
[04:41:57] I trusted could talk about these topics in a way where it didn't
[04:42:01] have to be existential.
[04:42:03] - But there's something about the current era where that's harder and harder to come
[04:42:07] by. And so what you just articulated is important to say regularly to remind
[04:42:14] people of an ideal we should all strive for, to be able to have differences
[04:42:18] and talk, and talk about them. 'Cause like, politics is fun.
[04:42:22] Like I've gotten used to saying I hate politics at this point, but what I
[04:42:26] really mean is whatever the system that's currently happening,
[04:42:30] where there's certain topics, and I just we know all the phrases you can say,
[04:42:35] That somehow put you in a bin of blue or red,
[04:42:39] and that creates drama versus a conversation.
[04:42:44] Like I could, I could think of a lot of harmless, if I wasn't paying
[04:42:47] attention to the internet, I could think of a bunch of harmless statements
[04:42:52] I could make analyzing the situation in the world
[04:42:57] that would trigger everybody to say, "Oh, that guy's a leftist-"
[04:43:01] - Yes.
[04:43:02] - ... piece of shit," or a you know, a right-wing fascist. And then
[04:43:09] objectively, if I wasn't paying attention to the internet, I would be, and I have been
[04:43:13] shocked. 'Cause I haven't been paying attention to the internet deeply. Uh but
[04:43:19] reading and preparing a lot, for example, for, for the war
[04:43:23] in Ukraine, and I have been shocked how certain
[04:43:29] statements from me can come off as one way or the other, and I get
[04:43:33] viciously attacked for it. But what that attack is doing is it's saying, "Hey, you,
[04:43:39] asshole who thinks you could just move about and think freely, pick a bin-
[04:43:45] - Yes.
[04:43:45] - ... and sit in that fucking bin."
[04:43:46] - Yes.
[04:43:47] - Put on that blue shirt or red shirt. And then
[04:43:51] actually what I've realized is things calm down. They don't,
[04:43:55] the system doesn't pick on you if you just say, "I'm
[04:43:59] a blue person," or, "I'm a red person."
[04:44:01] - Right.
[04:44:02] - But if you're just, like, curiously exploring the world and reasoning about the world,
[04:44:07] the system punishes you. And I hate that, 'cause I wanna get back
[04:44:11] to the Buckley and the Black Panther discussion.
[04:44:14] - Yes.
[04:44:14] - And you were just saying opinions. But then looking pragmatically at the situation,
[04:44:21] I have realized not to mention politics unless I really care
[04:44:25] about an issue. 'Cause I realize there's a cost. They'll, they'll
[04:44:29] put you in the blue bin or red bin.
[04:44:31] So you have to be more deliberate about choosing.
[04:44:33] - Yes. And I've tried to be more conscious of that, too. And then
[04:44:40] when I do choose to speak about it, it's usually because I have deliberated, and I think-
[04:44:44] ... "You know what? This is worth it." Now, I say that, and then I also
[04:44:51] catch myself thinking the opposite all the time, that I follow some
[04:44:55] person or another for whatever their technical work, and then I-
[04:45:00] ... learned or political
[04:45:02] standpoint. And I often do think, "I wish I didn't know that." So,
[04:45:08] it's hypocritical-
[04:45:09] ... then to think that of other people and then go like, "Well, occasionally I will-
[04:45:13] ... chime in on a debate that's controversial,"
[04:45:17] and then you have to accept that there is a price to that. And I do think you should,
[04:45:22] and more people should, be somewhat conscious about that. And
[04:45:26] again, we're both contradicting ourselves here, but saying like,
[04:45:29] "Wouldn't it be nice if we could talk about politics in a more free and open forum and just
[04:45:33] intellectually turn ideas around?" Yes, it would. Is that currently
[04:45:37] possible in the climate of social media and so forth? It's
[04:45:41] quite difficult. Now, some of it could simply also be a moment, and we could get
[04:45:48] past that moment.
[04:45:49] - Yeah. I hope so.
[04:45:49] - Maybe there is a way to get back to Buckley's conversation with the Black Panthers,
[04:45:54] even on social media, in a way where those discussions don't lead
[04:45:58] to the sort of just vicious mob cancellation nonsense drives that we've had, right?
[04:46:05] I actually think we're closer there now than we were five years
[04:46:09] ago. Like, the tribalism and the sanctions those tribes were able to exact on
[04:46:16] heretics in 2020 was way greater than
[04:46:20] it was in 2025. Certainly within tech. Now, I know if you're in academia,
[04:46:24] I mean, try going into the sociology department at I don't know, Harvard and
[04:46:29] mention some right-wing ideas. I don't think it's gonna go over very well, and I don't think you're gonna
[04:46:33] recover from it quickly. But in tech and in many other
[04:46:37] business domains at least, it is now possible to have an
[04:46:41] opinion that does not square with what the consensus was in 2020. That's for sure.
[04:46:47] - Well, there's some drama in the Rails community. There's some drama elsewhere.
[04:46:51] Is it, is it all... How did that turn out? Is that all okay?
[04:46:56] - In the sense that every single round of drama shrinks. So it's like we've,
[04:47:03] we had this peak infection of mega drama around the same
[04:47:07] time every other community had a peak infection of drama around
[04:47:11] 2020. And then you just see, like, every time there's a new flare up,
[04:47:15] it's less. And the kind of people who are ideologically
[04:47:19] wedded to sort of that struggle just shrinks and shrinks and
[04:47:23] shrinks. And at this point,
[04:47:25] one of the best things that happened for X, in my opinion, was that Bluesky
[04:47:29] and Mastodon came around. Because it kind of was like this
[04:47:32] honeypot for just the most vicious individuals on X
[04:47:42] and Twitter at the time, right? Who just congregated here in an
[04:47:46] ever-shrinking echo chamber that just
[04:47:50] went through purity cycle after purity cycle and shrank every single time to the
[04:47:54] point that there were just not a lot left. And the people who are
[04:47:57] left now there, they're just out of sight, out of mind. And
[04:48:02] that's not to say that X is some sort of perfect place, or there aren't firing squads
[04:48:06] occasionally there, or there aren't... But there's less of it. Like, every single
[04:48:10] time I've been pulled into a Mastodon, or not been pulled in, just
[04:48:14] spectated from afar, thread, a Bluesky or whatever, it was like, "Oh,
[04:48:18] shit yeah, this is what Twitter used to be like. Jesus."
[04:48:22] And now you can actually be on X, as I am, and, like, 90% of my
[04:48:29] engagement is about cool Linux stuff, cool technology stuff. "Look,
[04:48:33] I discovered a new computer. Can you see how fast it is?" And I can have those conversations
[04:48:37] with other people who are just also excited about computers. And then there's, like, 10% of it
[04:48:41] left that's like, all right, I'll chime in on something that's a little controversial, and we can have a little discussion there.
[04:48:45] And then we can just go back to being excited about computers.
[04:48:47] The algorithm is actually very good at finding stuff that you will find
[04:48:51] interesting, or s- I shouldn't say that, engaging. Sometimes it's
[04:48:54] enraging, but it is engaging, and therefore, revealed preference
[04:48:58] is that most people want a For You page. They don't want just a following feed.
[04:49:01] - No, but they're addicted to the For You page, right?
[04:49:05] - They... Yes, yes. That's true.
[04:49:05] - I think an LLM, like, if we had a strong
[04:49:09] LLM doing the feed that's personalized, it would do much
[04:49:12] better. The problem is how to deliver that at scale is extremely difficult.
[04:49:16] - Well, the problem is the reward function
[04:49:20] is engagement. And as soon as the reward function is engagement-
[04:49:24] ... engagement's gonna follow base instincts, and here we go.
[04:49:28] But I also don't wanna be so negative. To me, and I get
[04:49:32] we all have our own personalized algorithms,
[04:49:35] and sometimes it gets a little much. But I would say, on average, over the last 10 years,
[04:49:39] this is the best X has ever been. And I say that as someone who cares
[04:49:43] about a lot of technology talk, a lot of Linux talk, and a lot
[04:49:47] of that. That that's able to happen now in a way where
[04:49:51] it doesn't constantly get gatecrashed by people who wanna drag it into
[04:49:54] some political discussion-
[04:49:57] ... I find to be really awesome. I find actually X to be a great place to find that.
[04:50:02] Now, it's also a place to find other things, and we all have our own algorithms, so you
[04:50:06] can't make any declarative announcements about what
[04:50:10] X is or what it isn't. Your feed is probably totally different from my feed, and it's totally
[04:50:14] different from someone else's feed, right?
[04:50:16] - Yeah, I can't comment on this because
[04:50:21] because of the nature of the fact that I interview a wide variety of people,
[04:50:27] my feed is probably just a-
[04:50:28] - Is it, is it good for your feed or is it bad for your feed that you have to have it right?
[04:50:31] - It's bad.
[04:50:31] It's bad 'cause I could be like, "I'm eating this apple. It's so delicious."
[04:50:36] And then a bunch of people will show up, "Well, it's because you're a Zelensky shill-
[04:50:40] - Yeah, right.
[04:50:40] - ... or you're a Putin shill, you piece of shit." It's like, all right.
[04:50:44] I'll just go back to the-
[04:50:45] - I mean, I occasionally have a little bit of that where
[04:50:49] you just go like, "Wait, what? What are we talking about? What are you... Why would
[04:50:53] you show up in this way?" This is one of the reasons why I actually really enjoy podcasts, because I have
[04:50:57] found that even in long-form writing, when I make long-form arguments,
[04:51:00] people hear it in whatever voice they have in their head for me.
[04:51:04] And that often gets pre-programmed in advance of the arguments,
[04:51:08] just like, well, this guy is a, whatever, fascist.
[04:51:13] And then they hear the words and they read the words in those names. When they
[04:51:17] see or hear the actual tone of how I'm presenting the arguments,
[04:51:21] they may not agree with those arguments. I mean, many of them, of course, obviously don't.
[04:51:24] But it's much harder to just dismiss or hate someone like that.
[04:51:29] At least that's what I've found, and that's the response that I've gotten, that people are like, "Well, I had a certain
[04:51:33] opinion and then I heard you on Lex. That actually sounded much more reasonable."
[04:51:39] - But even more than that, I would love it if people just exercise
[04:51:44] this kind of approach to other people of, like, assuming they're a good person.
[04:51:51] - Yes.
[04:51:53] - And then, and if they have an opinion you disagree with, they're a
[04:51:56] good person who has an opinion. You can maybe think they're stupid, fine. Just think
[04:52:01] they're lost. But think of them as a good person. I think if you
[04:52:05] think of, you start, there's, one of the things that gets
[04:52:08] engagement is kind of shitting on other people.
[04:52:11] - Right.
[04:52:12] - And if you just approach other people as they're,
[04:52:16] you're looking for bad, you will always find bad in them. There's something annoying
[04:52:20] about them.
[04:52:20] - 100%.
[04:52:21] - And if you look at people in that way, you're not gonna learn from it, and you're gonna
[04:52:25] fill your heart with hate. You're not gonna, it's just a bad way to live and
[04:52:29] to interact with the world, and that is one of the things that the internet
[04:52:33] kind of encourages, so. It'd be nice if you just approach
[04:52:37] even people who you really disagree with, it's like, oh, I might learn something from this
[04:52:41] person. The Black Panther person, William Buckley, we might hate just love them.
[04:52:45] - So microcosm of this. There's a guy, Theo, I don't know if you follow him.
[04:52:50] - Yeah, yeah, yeah.
[04:52:51] - Um, we had a bit of a thing over the fact that we stopped using TypeScript-
[04:52:57] - Yeah
[04:52:57] - ... for a project, and
[04:52:59] he didn't like that and had opinions about that and other actions. And after that I
[04:53:03] thought like, what a bozo.
[04:53:06] And, and do you know what? I still think that was a bozo move, and then I can also think like,
[04:53:09] well, the dude's really into AI. He's trying all these models, and
[04:53:13] we can share some excitement about that, so I just started following him yesterday.
[04:53:16] - Awesome.
[04:53:16] - I was like, do you know what? I don't have to agree with you on everything. Uh, I don't
[04:53:20] even have to like some of the things that you did or said or
[04:53:24] whatever. I can follow you anyway. So if I can follow
[04:53:28] back Theo, then I think there's room for world peace here.
[04:53:33] - Yeah, he's actually a really good example. He's really opinionated,
[04:53:37] Changes his mind quite a bit, can get snarky, but I think he's
[04:53:41] a good person underneath.
[04:53:43] - And either way, I just, you know what? My feed is more interesting when
[04:53:47] there's some people talking about things that I care about and yeah, I don't have
[04:53:51] to agree with you on everything. I just don't.
[04:53:54] - This I found pretty funny, that you mentioned something your wife said
[04:54:00] that stuck with you, that all this tech- adjacent extreme longevity
[04:54:04] focus in men is like anorexia in women, a physical manifestation of
[04:54:08] anxiety and lack of control. That somehow rang true a little bit.
[04:54:13] - It certainly did to a lot of people. I think that
[04:54:16] tweet really popped off, and I don't know if you noticed, but
[04:54:20] Bryan Johnson chimed in on the thread, and
[04:54:25] I could see how Bryan would read that as a bit of a jab.
[04:54:30] And I do think that Jamie was probably
[04:54:35] thinking of him amongst other people in that conversation. And
[04:54:41] it's also an example of where even though I'm not subscribing to
[04:54:49] Bryan's mission of, I think it's the slogan's don't die. I actually
[04:54:56] I do wanna die. I don't wanna do this forever. Like, I think the human li-
[04:55:00] lifespan of about 90 to 100 sounds about right. I'm embracing the finitude of life.
[04:55:08] We don't have to agree on that. In fact,
[04:55:10] Bryan is a vastly more interesting human to me because
[04:55:14] we don't agree with that, and Bryan's
[04:55:19] willingness to literally put his own skin and all sorts of
[04:55:23] other body elements in the game for that mission is really interesting. Now,
[04:55:31] I can have that view, this is really interesting. I'm glad Bryan is
[04:55:34] pursuing this passion of his, and then also find
[04:55:40] my wife's analysis to ring true, that it does seem like there is some
[04:55:48] underlying, uh, I don't know,
[04:55:51] fear of... I was talking to Jamie yesterday about this, and she was saying,
[04:55:55] Or comparing it to this
[04:55:59] sense of people who didn't feel like they had lived enough. And one of
[04:56:03] the reasons perhaps that they hadn't lived enough was that modern
[04:56:06] society now is a surveillance state, not
[04:56:10] by the state actually, but by each other. There are camera phones everywhere.
[04:56:15] Every indiscretion or even outburst of fun or cringe
[04:56:21] is highly likely to be recorded and then shared
[04:56:25] to the point of ridicule, and what is the rational reaction for
[04:56:29] humans under those conditions is to pull back, is to make sure you
[04:56:33] don't dance like nobody's watching because-
[04:56:35] ... they're probably filming you to your great and
[04:56:39] eternal embarrassment on the internet, so maybe you just shouldn't dance at
[04:56:42] all. And therefore, if we've all
[04:56:46] retracted to the point that we're barely living, we're
[04:56:49] clinging on to wanting it to last forever. Now-
[04:56:54] ... I mean, I'm sure that thesis does not apply in all circumstances. I don't even know if it applies to
[04:56:58] Bryan or, or anyone else here. But I think there's something to this, that
[04:57:03] if you feel like you've really lived, you're okay thinking I've lived enough.
[04:57:10] And that the, it having an end is not something to be fought. Now,
[04:57:20] is it also possible that this is all just existential post-rationalization, and if
[04:57:24] tomorrow there was a live forever pill, we'd all take it? Yeah, that's possible.
[04:57:29] Is it also possible that if we did that, society be, would be worse off?
[04:57:33] Yes. Is it possible that the human lifespan is the length it is for
[04:57:41] sociological reasons, not just biological reasons? Yes.
[04:57:45] So I think these are just all interesting questions, and I just thought her analysis
[04:57:51] really got to something here. And that discussion has come up
[04:57:55] afterwards. I mean, that, I think that tweet is like a year old. But just
[04:57:59] recently, we've been talking about this over-optimizers. I saw,
[04:58:03] uh, Chris Williamson, Modern Wisdom had a bit where he was like, "Yeah, okay,
[04:58:07] maybe we did go a little overboard." And the triggering thing was
[04:58:11] the Diary of a CEO, where the host was saying something to the
[04:58:15] effect of, "I had a glass of wine and the next three days were ruined."
[04:58:20] And that to me, I mean, in his circumstance, I'm sure that's true. Like, if you have not
[04:58:24] drank any alcohol for a very long time and you have just a little, I could see how it can have effect.
[04:58:29] But also there's something in that that just
[04:58:32] triggered a visceral reaction, I think, for a lot of people, and myself included, where I was like, "Fuck,
[04:58:37] man, I should have a glass of wine just right now, even though I don't usually drink."
[04:58:41] And in fact I think the alcohol question is a good microcosm to zoom in on. So
[04:58:46] we've all stopped drinking apparently, like alcohol sales are way down-
[04:58:50] ... certainly amongst young people. And then on the one hand, on the
[04:58:53] pure health metrics, whatever, we can go like, "Oh wow, isn't that great?"
[04:58:58] And then I go like, "Yeah, I'm not so sure it is." Like the social
[04:59:02] lubricant that alcohol can provide
[04:59:05] may be missed, is missed. I mean, we are in an absolute
[04:59:09] epidemic of loneliness and misery and depression and
[04:59:13] whatever, and a fair amount of it just probably comes because you're not
[04:59:16] interacting enough with other people. Now, that's before we even talk about
[04:59:20] coupling, right? Like way down, people having a very hard time meeting a spouse.
[04:59:26] And- ... a lot of that has moved over to apps that have all sorts of
[04:59:32] negative outcomes and consequences, right? Like maybe we will
[04:59:36] look back, or maybe we already are looking back and thinking like, "Eh, do you know what?
[04:59:40] Maybe getting wasted every once in a while was not the worst thing in the world." And whether wasted or not,
[04:59:44] maybe just having a couple of drinks every
[04:59:47] Friday or Saturday when you're out and about was
[04:59:51] part of what helped society get to where it is. Maybe
[04:59:55] the fact that humans have literally been drinking for whatever it is, like
[04:59:59] 13,000 years for mending things, had a social
[05:00:02] purpose, and we pull out Chesterton's fence of our own chagrin, right?
[05:00:08] - As you mentioned, in the spirit of that, so when I traveled across rural
[05:00:12] China, I did smoke a little bit in my early 20s, but I
[05:00:17] picked up just for that trip-
[05:00:19] - A social connector, right?
[05:00:22] - And I drank humongous amounts, even though I don't
[05:00:26] really drink these days, because of the social thing. It's the way they show love.
[05:00:31] And I also ate a shitload of carbs, which-
[05:00:34] ... I'm usually low carb. I just like meat. So just
[05:00:38] because it's the way they show love.
[05:00:40] And actually even, it's in that society cigarettes,
[05:00:44] but in most societies, liquor is a thing to do together. And it's a bond.
[05:00:50] It doesn't, the benefits that that entails
[05:00:55] can, in many situations, outweigh the negative consequences like
[05:00:59] long-term for whatever, however you measure them.
[05:01:02] - And this is the myopia of modernity, that we reduce
[05:01:06] things down to like, well, one glass on this long run study meant that you
[05:01:10] had a 0.1% greater risk of some heart defect.
[05:01:15] Yes, but if you didn't live at all, what's the point? And again, it's also
[05:01:19] easy to flip over the other side. Like the only way to live is to get drunk every
[05:01:22] weekend and eat a bunch of crap and smoke 40
[05:01:26] cigarettes a day. No, it's not. Like it doesn't have to be the
[05:01:30] either/or. This is one of the reasons I stopped wearing my Oura Ring. So I wore
[05:01:34] the Oura sleep ring for many years, four years. And one day I was just like,
[05:01:41] "I don't need to know that I had-" ... "a bad night of sleep."
[05:01:45] Like I know. This added,
[05:01:50] I don't wanna call it an anxiety, I don't have a lot of anxiety, but this added just like
[05:01:54] reminder-
[05:01:55] ... that I had a bad night of sleep, what purpose is it actually playing here?
[05:02:00] Why do I need to have all these stats? Why do I need to
[05:02:04] optimize everything? To the point where, again, after that single
[05:02:08] anecdote, you know, from Diary of a CEO, I was like,
[05:02:11] "Fuck, I kind of want the opposite." Like-
[05:02:13] I barely drink at all. A glass of wine once a month maybe.
[05:02:18] Like, do you know what? I should start, uh, just on the weekends, get a glass.
[05:02:23] Maybe two. And also, I mean, I've never been the person to fret about my diet. Um,
[05:02:32] this is one of the great privileges of being
[05:02:36] married to, and I'll do a quick aside here. Don't ever
[05:02:39] call a woman in her 40s a wonderful woman. My wife was so pissed—
[05:02:45] ... that not only last year did I come on her birthday, that was bad enough, but that I called her a
[05:02:49] wonderful woman on the show, because that sounded like her
[05:02:53] name was Nancy and she was 65— ... in the suburb of Rochester.
[05:02:57] So I'm like, I was trying to play the 50. Like, no, I don't
[05:03:01] know, I'm Danish. How would I know? But that didn't go over well. So I'm gonna say
[05:03:05] awesome woman instead.
[05:03:07] If you marry an awesome woman who also not only knows how to cook, but enjoys
[05:03:13] it, do you know what? There's a very traditional division of labor here that has been
[05:03:20] quite stable through several ... tens of thousands of years in
[05:03:24] human societies, that perhaps also wasn't the worst
[05:03:28] idea in the world. And I also know there are plenty of men who like to cook,
[05:03:32] and there are women who don't. But as stereotypes go, eh,
[05:03:37] that certainly helped me. Like, I don't think I would've been able to just
[05:03:41] be as relaxed about food if I didn't eat relatively healthy on
[05:03:45] a, on a regular basis. But the overall point being, just
[05:03:49] getting out of that optimization game without turning into the
[05:03:53] opposite. You don't have to be a fat slob on the couch either. You can move around.
[05:03:59] - Yeah. And then the bigger point we're talking about is the finiteness of life.
[05:04:05] - Yes.
[05:04:05] - And I agree with you on this.
[05:04:06] - This was actually a feature, I built it into Omarchy. So memento mori.
[05:04:12] Remember death.
[05:04:14] If you pull down the calendar in Omarchy, you open it by clicking the clock.
[05:04:18] It opens up, and the first funny thing, I took it off the internet. There's this
[05:04:22] account called Year's Progress, and it, every day it updates, and it just
[05:04:26] shows 63% done with 2026. I don't know if you've seen that one.
[05:04:30] So it just fills up. So I built that into the calendar. So right now it says, "We're 63% done
[05:04:34] with 2026." But then if you double-click that, it'll ask you, "When were you born?
[05:04:39] How long do you expect to live?" And the default is 90. So I put in 1979.
[05:04:43] And then right below the line of, like, how long are we done with the year-
[05:04:47] - Oh, that's beautiful.
[05:04:47] - ... is a new line that shows how long are you done with your life.
[05:04:50] I think I'm at 62%. I'm like, if you hover over it, it says, "Memento mori."
[05:04:55] - That's beautiful.
[05:04:57] - Fair number of people found it morbid, but this was why it is an Easter egg. It's not, like,
[05:05:01] exposed. You gotta click a few things to get there. I like the reminder. I like the
[05:05:05] reminder that time is finite, and I should make the most of it.
[05:05:09] And this is also one of the privileges of having children. You really
[05:05:14] realize that the cliches are all true. Oh my God, it goes so fast.
[05:05:19] And I remember my now 13-year-old being one, being two.
[05:05:23] I was like, "This was just yesterday." And the reason it's a
[05:05:27] cliche is because it's a shared experience. Cliches are good.
[05:05:31] They remind you that you are part of
[05:05:35] the human experience, and others have been here before you.
[05:05:38] - I have to ask, you mentioned the amazing woman and great cook.
[05:05:43] - Amazing. Very important to remember. Not wonderful, amazing.
[05:05:47] - Amazing. So there's this... You talked some shit about
[05:05:51] croissants or something. I saw this,
[05:05:54] this in a tweet. So is the Danish croissant somehow better?
[05:05:59] - Actually, Danish croissants are not particularly good. In my opinion, the only place you can find a
[05:06:03] half-decent croissant, of all places, is 7-Eleven,
[05:06:06] which is hilarious to me because 7-Eleven in the US is the place where,
[05:06:11] at least in Chicago, you'd go to get a slushie and try to avoid getting murdered.
[05:06:15] But in Denmark, 7-Eleven is this very upscale,
[05:06:19] super nice convenience store, and they just happen to make decent croissants.
[05:06:25] And it always baffled me that I lived in the United States
[05:06:29] for 20 freaking years. I have yet to have
[05:06:33] a single croissant that's even at the level of a 7-Eleven croissant in Copenhagen.
[05:06:39] That seems improbable.
[05:06:41] - Have you understood why?
[05:06:43] - No, I've legitimately considered hiring an investigative
[05:06:47] journalist to get to the bottom of this, because the number of theories I've heard have
[05:06:51] been all over the place. It's the water. It's the butter.
[05:06:55] It's the skill. It's the this, it's the that, it's the other thing. I'm like, none of
[05:06:59] it adds up to me. If it's the butter, can't you just import it? I
[05:07:03] thought I saw Danish butter in some supermarkets over here like Lurpak.
[05:07:07] So that can't be it. Can it be the skill? No, it can't be the skill. There are plenty of French
[05:07:11] people and Belgian people, the best croissant makers in the world, who live in
[05:07:15] the US. Like, what is the reason? And then I get the second thing, which is-
[05:07:20] ... "No, no, you just haven't gone to the right place." I've literally gone to
[05:07:23] 15 of quote unquote- ... "the right place," and all the croissants were shit.
[05:07:28] So before I leave the planet, I have to get to the bottom of
[05:07:33] why the United States cannot make a proper croissant. And I don't, I'm
[05:07:37] not even asking about peak French croissants, peak Belgian croissants-
[05:07:41] ... which are the best croissants in the world. I'm just asking about the 7-Eleven croissant
[05:07:46] from Copenhagen. Is that too much to ask for?
[05:07:49] - That's a fascinating mystery. What, zooming out, what's
[05:07:55] your, what's your favorite... This makes me want to know, what's your favorite meal?
[05:07:59] Like, if you, if I gave you a last meal and were to murder you after.
[05:08:02] - It all depends whether it's lunch or it's dinner. If it's lunch, it-
[05:08:05] - It's one meal. What's, what's... I feel like if you're getting murdered,
[05:08:10] it doesn't really matter if it's lunch or dinner.
[05:08:11] - Well, depends on what time of day you're getting murdered.
[05:08:13] - Oh, I see.
[05:08:14] - If it's an afternoon execution, I only get lunch.
[05:08:18] - Okay.
[05:08:19] - And if I get lunch, it's at Louisiana, the museum in north of Copenhagen.
[05:08:29] I was just there with Jamie two days ago, and we go there all the time.
[05:08:35] The museum is lovely. We don't go for the museum.
[05:08:37] We go for the cafeteria. That in itself sounds crazy. Like-
[05:08:40] - Yeah, it does
[05:08:40] - ... you're gonna, you're gonna drive half an hour to go to a cafeteria.
[05:08:43] Well, it just so happens to be, it is the best lunch
[05:08:47] I've probably ever had in my life. The chef there is just
[05:08:51] unbelievably good, and not only is
[05:08:54] the food amazing, what's even more amazing to my system thinking
[05:08:58] brain is that at any one time when we were up there, I think there were probably
[05:09:02] 200 people waiting for their food. And our food was delivered in five
[05:09:07] minutes. They have a small menu, and clearly they make it in bulk, and it's
[05:09:13] unbelievably delicious.
[05:09:15] - Just a cafeteria at a museum?
[05:09:17] - It's a cafeteria at a museum that happens to have the best lunch I've ever had anywhere in my life.
[05:09:21] - What kind of food are we talking about? What kind of lunch food?
[05:09:23] - It's, like, Nordic cuisine, so it's, it's... A funny thing is the menu, when I
[05:09:27] look at it, I was like, "Do you know what? If I saw this menu- As a kid, I'd go like,
[05:09:31] "I'm not eating here." It's like, I don't know-
[05:09:33] - This is pretty fancy
[05:09:33] - ... root free fruit and- ... and onions-
[05:09:36] ... and all sorts of healthy stuff. That sounds disgusting. And then you sit down and eat it,
[05:09:40] and the angels sing. But it's even more particular than that. It's the butter.
[05:09:46] The whipped butter that they have there, the best butter anywhere in the world.
[05:09:50] - I think that has to be connected to the croissant mystery too.
[05:09:52] - There must be some connection. But literally- ... even in
[05:09:56] Paris, I've never had whipped butter that tastes as
[05:10:00] delicious as the butter does at Louisiana in Copenhagen. Literally,
[05:10:04] I would drive 30 minutes-
[05:10:06] ... to have bread and butter at the cafeteria in Louisiana.
[05:10:10] - Well, how'd you discover that? Just one day you went to the museum and-
[05:10:13] - I think we just went to the museum-
[05:10:15] - And you tried a whole dish.
[05:10:15] - ... and we had the lunch, and we were like...
[05:10:19] - This is weird.
[05:10:20] - This is rivaling the best tasting restaurants- ... I've ever been to in my
[05:10:24] life, and I've gone to Noma a couple of times and
[05:10:28] tried what there is to try, and this is right up there.
[05:10:31] - All right. What about dinner, since you mentioned? Is it something different
[05:10:35] that you have to think-
[05:10:36] - Well, I think there's a lot of good options in
[05:10:40] Copenhagen, but actually I'll pick a place in Spain. So there is
[05:10:46] this place in Marbella called Puente Romano. It's a hotel,
[05:10:51] and down by the beach, they have this beach restaurant with fresh seafood.
[05:10:57] Unbelievably delicious.
[05:11:01] I'm trying to remember what it's called, but yeah, if you look it up, the beach
[05:11:05] seafood place at Puente Romano is incredible.
[05:11:08] - How much of great food is, like, the place and the person you're with,
[05:11:14] right? Or the, or the experience when you first are there?
[05:11:18] - I mean, the ambiance certainly helps, but I think my taste buds are also just-
[05:11:22] - Okay, that-
[05:11:22] - ... in tune for-
[05:11:23] - So it's legit.
[05:11:23] - ... flavors
[05:11:24] - ... it is just good food.
[05:11:24] - It's just really good food.
[05:11:27] Because for ex- that cafeteria, it is, there's a lot of people. Like,
[05:11:31] I wouldn't rate it as like, oh my God, this is just a place I want to sit for two hours.
[05:11:35] But the food is so delicious.
[05:11:37] - That's one of the things I'm, in traveling across the country, I'm realizing
[05:11:41] to sample without bias, just try things.
[05:11:47] 'Cause you might, I guess you might just be surprised. Maybe I'll find your
[05:11:51] croissant. All right, we've talked about mortality. Talked about food.
[05:11:56] - Settled end of life.
[05:11:58] - What do you thousand years from now, what do you think is the future of humans,
[05:12:02] human civilization? You think we're gonna make it?
[05:12:04] - A thousand years from now? Man, I'm having trouble predicting 12 months from now.
[05:12:09] - I know.
[05:12:09] - A thousand?
[05:12:10] - You think we got a shot?
[05:12:11] - Oh, I'm gonna bet on optimism. I'm gonna bet on a multi-planetary
[05:12:15] species. I'm gonna bet that Elon gets that rocket to Mars, and we figure
[05:12:19] out how to bend space-time and discover some wormholes or, or something.
[05:12:24] - Once we do, do you think,
[05:12:26] you think all humans on Earth will die once or twice and be repopulated
[05:12:33] After we get a good backup going?
[05:12:35] - I mean, that was actually one of my favorite episodes of Black Mirror, the
[05:12:39] one where they get uploaded to the 1980s sea town
[05:12:43] somewhere. And I just thought like, wow, this is
[05:12:47] both such a dark moment, yet also so
[05:12:50] beautiful in the shared recognition that, like, the '80s were actually kind of amazing.
[05:12:55] Like, I don't have a lot of nostalgia for many moments, but I do
[05:12:59] have nostalgia for the '80s.
[05:13:00] - But-
[05:13:01] - And they say something about, like, whatever place and time you were in, the music you were
[05:13:05] listening to when you were 12 or-
[05:13:07] ... or 14, 15, something like that, that's what's gonna stick with you. Like, no, I was
[05:13:11] only, I got to be 10 in the '80s. So this was my early childhood, and I
[05:13:17] still have an unbelievably fond affiliation with
[05:13:20] the '80s. So if I'm gonna be uploaded to the sky-
[05:13:23] - You want it to be the '80s?
[05:13:24] - ... I'm doing the '80s.
[05:13:26] - Wow. I don't think I've actually ever heard anyone say that.
[05:13:29] Usually it's '70s or '90s.
[05:13:31] - Oh, and the-
[05:13:31] - Because the '80s is a-
[05:13:32] - I really don't like the '90s. Can we talk about this?
[05:13:38] - No, I'm done. Not done.
[05:13:40] - To me, this was the great turning point of nihilism.
[05:13:45] That both the music, the genre, the fashion-
[05:13:50] ... everything turned from, like, this glamour, the
[05:13:54] pop, the optimism, even the yuppies and everything- ... to grunge and Nirvana.
[05:14:00] And even though, I mean, I like the music, I don't like the ethics. I don't like-
[05:14:05] ... the morals. I don't like any of the underpinnings to it.
[05:14:08] There was just such a defeatism to it-
[05:14:11] ... that in retrospect, I look back upon it, if I'm gonna get reinserted
[05:14:15] into the matrix, it's gonna be the '80s.
[05:14:17] - That was full of optimism and fun-
[05:14:20] - Yes
[05:14:21] - ... and colors.
[05:14:22] - Yes. I remember having these orange pants-
[05:14:29] ... with, like, white dots on them. That was just a normal
[05:14:33] thing kids could wear in the '80s.
[05:14:35] I've never fucking seen that today. Or I mean, even in the '90s, it all turned just,
[05:14:42] like, Seattle gray. Great regression.
[05:14:46] - So the Nietzschean, you know, this idea of eternal recurrence.
[05:14:50] If you do a Groundhog Day and you live forever, you want it to be in the orange pants
[05:14:54] with the white dots in the '80s.
[05:14:56] - Maybe I'm gonna skip the orange pants, but-
[05:14:57] - No
[05:14:57] - ... I'm definitely picking the '80s.
[05:14:58] - You said it.
[05:15:01] All right, DHH. Thank you so much for everything you do. Thank you for being an inspiration to
[05:15:04] all of us, for building cool shit in the world, and thank you for talking today.
[05:15:11] - Anytime. Thank you, Lex, again for having me.
[05:15:15] - Yeah. Thanks for listening to this conversation with DHH. To support this podcast, please check
[05:15:19] out our sponsors in the description, where you can also find links to
[05:15:23] contact me, ask questions, give feedback, and so on. And
[05:15:27] now, let me leave you with some words from Ralph Waldo Emerson.
[05:15:31] "Once you make a decision, the universe conspires to make it happen."
[05:15:37] Thank you for listening, and hope to see you next time.
