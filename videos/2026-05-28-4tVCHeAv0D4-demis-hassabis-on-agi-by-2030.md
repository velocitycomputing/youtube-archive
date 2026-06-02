---
video_id: 4tVCHeAv0D4
title: Demis Hassabis on AGI by 2030, Curing Every Disease, Life After AGI, and More
channel: Rowan Cheung
url: "https://www.youtube.com/watch?v=4tVCHeAv0D4"
watched_date: 2026-05-28
watched_at: "2026-05-28T12:00:00Z"
watch_count: 1
duration_seconds: 1001
source: youtube-history-browser
history_label: Thursday
history_order: 106
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1001
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

Demis Hassabis discussed Google's AI progress and timeline to AGI, estimating achievement by 2030 plus or minus one year based on recent breakthroughs like Omni models and Flash 3.5. Key advances include drug discovery acceleration through Isomorphic Labs, where specialized AI models compress typical 10-year discovery timelines to months by targeting cancers and immunology first, with test compounds already in pre-clinical stages. He outlined remaining technical gaps: jagged intelligences lacking perfect world understanding, unreliable agentic systems, inadequate memory mechanisms, and gaps in long-term reasoning. Google's near-term focus includes personalized AI glasses as the killer app for a universal digital assistant, integrated across devices and health data, with democratization through efficient models like Flash Lite ensuring accessibility globally. Hassabis emphasized security and robustness as critical concerns alongside capability advances, flagging the need for standards and international cooperation as AI becomes increasingly agentic.

For practical application, develop skills in taste, creative synthesis, and design sensibility while deepening technical understanding—human creativity and judgment will become premium as AI handles routine cognitive work. If in science or medicine, expect AI-accelerated drug discovery to reshape your field within five years; prioritize learning these tools to remain competitive. For developers and creators, focus on combining technical tools with emotional connection to audiences, as AI excels at execution but not at meaningful human engagement. Anyone in security, policy, or governance should begin preparing for agentic AI systems now, as robustness and standards are emerging as critical bottlenecks. Consider that AI glasses with personalized digital assistants will reach consumer availability within one to two years—plan for how they'll integrate into your workflow and health data sharing.

## Transcript

[00:00:00] I've got a lot of faith in human ingenuity we're sort of instantly adaptable.
[00:00:04] We’re general intelligences ourselves, don’t forget.
[00:00:06] at what we built around us, it’s incredible,
[00:00:08] with our hunter gatherer brains.
[00:00:10] Why would we stop here?
[00:00:11] even the tools we have today,
[00:00:12] just a few years ago, that would have been unthinkable.
[00:00:14] But today we've just totally adapted to it.
[00:00:16] Oh yeah.
[00:00:17] You know, we chat with bots that are basically Turing test level,
[00:00:20] and we make Omni models that can create any video,
[00:00:23] and we're kind of like, yeah, you know, that's kind of normal.
[00:00:25] what separates the great scientist
[00:00:26] from the good scientist is not their technical capability.
[00:00:29] it's that creative capability, after the technology is ready.
[00:00:33] How are you thinking about democratization?
[00:00:35] it available just to the rich? How can everyone have it?
[00:00:38] How can we make it best for the world?
[00:00:41] Demis, thanks so much for being here again.
[00:00:43] It's always great talking to you. It's great to be here.
[00:00:45] So Google I/O, obviously tons of announcements.
[00:00:48] What are you most excited for?
[00:00:51] Oh, wow.
[00:00:51] It's, I mean, I think we announced a lot of really exciting things.
[00:00:56] You probably saw me pretty excited about Omni.
[00:00:58] I think this is a really interesting direction for us on World Models.
[00:01:01] I've always been a big proponent of that.
[00:01:03] But obviously, you know, I think Flash 3.5 is the big story.
[00:01:07] And integrating that into Anitgravity 2.0, I think people are going
[00:01:12] to be really pleasantly surprised.
[00:01:14] And I think it's an amazing kind of like workhorse model.
[00:01:17] And then of course, you got a lot more to come. You know, with Pro.
[00:01:21] Yeah, benchmarks are going up,  agents are here with Spark.
[00:01:24] And I think like on the consumer side, we're really starting to see like,
[00:01:28] productivity gains. Yes.
[00:01:29] Like kicking in, like even with nano banana for example,
[00:01:32] content creators are genuinely using these tools
[00:01:34] new tools in the toolkits to make more content, that sort of stuff.
[00:01:39] I'm curious, like looking at today with like
[00:01:41] Omni, for example, versus three years ago when when Gemini was first released.
[00:01:45] Yeah.
[00:01:46] How have your AGI timelines kind of shifted?
[00:01:49] Have they, has it gone according to plan or has it gone faster, or slower?
[00:01:53] I think it's going according to plan.
[00:01:55] So a few years ago you probably saw maybe we even talked about in interviews
[00:02:00] I used to say 5 to 10 years, maybe that's 2 or 3 years ago.
[00:02:03] I think we're sort of exactly on track.
[00:02:06] And, and I would say my confidence interval is narrowed.
[00:02:09] So, you know, these days I'm thinking it's 2030 plus or minus a year.
[00:02:14] Wow. Okay.
[00:02:16] So 2030 plus minus a year.
[00:02:19] That's that's. Soon. Yeah very soon.
[00:02:21] How are you guys preparing? Like, internally.
[00:02:23] We we're, you know, first of all, we've got to we've done
[00:02:27] a lot of engineering work under the hood in the last year,
[00:02:30] which you see, you see the surface of when we announced things like this.
[00:02:33] But actually you can almost think that whole stack had to be rewritten to,
[00:02:37] be sort of, AI first,
[00:02:41] model first, and now agent first.
[00:02:44] So that's quite a big change from like normal software.
[00:02:46] And obviously there's
[00:02:47] all this huge infrastructure that serves billions of users every day
[00:02:50] at lightning speed, and that's all got to work.
[00:02:53] And I think, we've made massive,  improvements on that over the past year.
[00:02:58] And that's why you can see all the goodness of, of the AI models
[00:03:02] flowing through into our product services,
[00:03:04] you know, so quickly and in such compelling ways.
[00:03:08] So I think, I think that's big and, but yeah, in terms of AGI,
[00:03:12] I think we're, we're sort of on track and, actually we're sort of on track
[00:03:17] from where we thought back in 2010 when we started DeepMind.
[00:03:21] You know, people like Shane, my co-founder, was on record saying around
[00:03:24] 2028, 2030 you know, we thought of it as a 20 year mission,
[00:03:28] and I think we're on track for that.
[00:03:30] What do you think the capabilities that are missing
[00:03:32] are still before we hit it yet?
[00:03:34] So I think there's still a few things missing.
[00:03:36] I feel like we still have kind of jagged
[00:03:39] intelligences in the sense that they're amazingly good at certain things.
[00:03:43] You're seeing that with things like Omni.
[00:03:45] I think it's kind of mind blowing.
[00:03:47] We're a little bit desensitized to all of that now, but it's you can think of it
[00:03:50] sort of like nano banana for video, this first version.
[00:03:52] And I think content creators like yourself
[00:03:54] should have a load of fun with it.
[00:03:56] But yeah, in terms of, like its understanding of physics and,
[00:04:00] and and and the way the world works,
[00:04:03] it's not perfect, but it's pretty mind blowing if you stop and think about it.
[00:04:07] And, those are all hallmarks of what we imagine an AGI to be able to do.
[00:04:12] And of course, is going
[00:04:12] to be amazingly important for things like robotics and glasses.
[00:04:16] But on the other hand, there's still a lot, the systems fail at still and,
[00:04:21] and you can see that in the agentic side of things, it's,
[00:04:24] it's starting to become, I think in the last six months,
[00:04:26] actually, genuinely really useful to people in their daily lives.
[00:04:30] But it's still not quite fire and forget for the average, you know, user.
[00:04:35] I think it's there's still some reliability and some things,
[00:04:38] these systems all get stuck on.
[00:04:40] So those things need to be, you know, consistency, continual learning.
[00:04:45] There's still some, breakthroughs that are needed in that direction.
[00:04:48] Gotcha.
[00:04:49] So this is like sort of a research problem or?
[00:04:51] Yes. So we have a ton of research on things like that.
[00:04:54] Also memory still not quite right, I would say in any of the systems
[00:04:58] it's a little bit brute force, something smarter I think is needed there.
[00:05:01] So there's a few, you know, long term reasoning and planning.
[00:05:04] There's a few areas, critical areas, only a handful, that I still think,
[00:05:09] need to be cracked before we would have something like AGI that we could call AGI.
[00:05:14] Yeah.
[00:05:14] I mean, we're it's really cool to see the personalization across the devices now.
[00:05:18] I think last year we were talking about this.
[00:05:19] And this year you guys are releasing it in the summer with the glasses.
[00:05:23] You got the watches, and it connects to your phone.
[00:05:25] Yeah. The the Fitbits and all of these things.
[00:05:27] It's slowly coming together but the memory isn't like fully there.
[00:05:30] Yeah exactly. So it's coming together.
[00:05:32] I mean, I think one of the things that was most exciting
[00:05:34] we showed is the progress
[00:05:35] we've made with glasses this year compared to last year,
[00:05:37] and soon is going to be in everyone's hands.
[00:05:39] I can't wait to, you know, have that myself.
[00:05:42] It's one of the dreams
[00:05:42] I've always had a personal assistant that helps you with you everywhere you go
[00:05:47] and just helps you in your daily life, you know, get rid of mundane admin tasks.
[00:05:51] And email would be great.
[00:05:53] You know, dealing with my emails, but it's so you have more time
[00:05:57] to do what you know, what you want in the day.
[00:05:59] And I think we're really close now to how things, really compelling things.
[00:06:03] And in some ways, I think the this idea of a universal digital assistant,
[00:06:07] in my view, is, is the killer app that the form factor of glasses
[00:06:11] was always waiting for.
[00:06:12] You know, at Google, of course, has a huge history and long history in glasses.
[00:06:16] But but I think this is the actual,  killer app.
[00:06:19] What we've been sort of building towards now
[00:06:22] and we're on the cusp of and it's very exciting.
[00:06:24] And then also integrating into all the other devices
[00:06:26] and your health, data and things like this if you want to.
[00:06:30] And then Gemini being to help you, with those kinds of things.
[00:06:34] The Gemini subscriptions quite compelling in that way, right.
[00:06:36] Because it really has everything.
[00:06:38] Yeah. Bundled into one.
[00:06:40] And that's one of the, I think beauties and of of the power of the,
[00:06:44] the full stack we have at Google, right.
[00:06:46] You know, from the chips to the models to the, to the products.
[00:06:50] Yeah.
[00:06:50] But jumping ahead here, I think a year ago, we spoke
[00:06:54] and you said that AI could help cure all diseases in our lifetimes.
[00:06:57] But since then, what are some kind of, like the biggest developments you've seen?
[00:07:01] In AI drug discovery have your timelines kind of shifted since then?
[00:07:05] Again, I would say they've not shifted, but they've hardened.
[00:07:08] They've. They've tightened.
[00:07:09] So I'm more sure let's say about those timelines now.
[00:07:13] Right.
[00:07:14] I was hoping it would be in the next decade
[00:07:16] or two we'd make these big advances in medicine.
[00:07:18] Now I'm, you know, very sure.
[00:07:20] I wouldn't say I'm certain, but I'm, I'm I'm very, confident that is the case.
[00:07:25] Seeing the progress we made in the last year on on our Gemini
[00:07:29] for science side of things at DeepMind, but also especially at Isomorphic Labs,
[00:07:34] where we're really trying to, you know, push forward,
[00:07:39] the models, the specialized models that are required to understand chemistry
[00:07:43] and biochemistry, the kinds of things you'd need to design drugs.
[00:07:46] And it's going, amazingly well.
[00:07:49] We just raised a bunch of money to accelerate even further.
[00:07:52] And,  you know, we have excitingly now, some,
[00:07:56] test compounds in pre-clinical stage,
[00:07:59] which is, you know, the beginning of them becoming real, real, cures.
[00:08:03] And I think that actually will be the biggest watershed moment in AI
[00:08:07] when that happens.
[00:08:08] So when you say like cure all diseases, is it sort of one disease at a time
[00:08:12] or are there particular diseases you think come first?
[00:08:14] Yeah, I'm meaning more like building a platform...
[00:08:17] Think of it as AlphaFold.
[00:08:19] But AlphaFold is only one small piece, but, you know, maybe like
[00:08:22] half a dozen to a dozen other AlphaFold level breakthroughs.
[00:08:25] So it's not easy, you know, we're working on all those, all together
[00:08:29] into one continuous platform that goes from the target of interest
[00:08:34] to the way you think the disease is working all the way to a,
[00:08:37] lead compound that you want to test in clinical trials.
[00:08:41] So I'm talking about, sort of compressing that average of, you know, ten years
[00:08:46] it can take to do that down to months, maybe even weeks.
[00:08:50] Of course, there's still the clinical trial stage,
[00:08:53] and there's all the downstream stuff before you get an actual drug someone can
[00:08:56] take that, can take another ten, 5 to 10 years.
[00:08:59] And I think I can help with that too.
[00:09:00] But I'm really just talking about the drug discovery engine, the bit
[00:09:03] where you go from the, you know, the disease profile
[00:09:07] to a potential cure, that then needs to be tested.
[00:09:12] And there's no specific disease
[00:09:15] I hope it could work on any type of disease type.
[00:09:18] Yeah. Yeah.
[00:09:18] I actually noticed on the keynote today it said cancers and immunology first?
[00:09:22] So we're starting on those areas for first
[00:09:25] immunology oncology.
[00:09:28] Partly because obviously some of those things are so serious.
[00:09:31] It's, it's it's more, you know, the clinical side of
[00:09:35] that is quicker because they're such serious, diseases.
[00:09:40] Anything you can do to help is essential there.
[00:09:43] And, you know, I feel a real need to I've always felt that
[00:09:47] that's what I first and most importantly, wanted to do with AI.
[00:09:51] It's it's really incredible work.
[00:09:53] I guess the follow up question to that is like, after the technology is ready.
[00:09:58] How are you thinking about democratization?
[00:10:01] You know, is it available just to the rich?
[00:10:03] How can everyone have it? How can we make it best for the world?
[00:10:05] We care a lot about that at Google.
[00:10:07] Obviously, you know, all our products are used by
[00:10:09] you know, there's I don't know,
[00:10:10] 13 products now billion user products, Gemini apps, 900 million.
[00:10:14] So we are really, take very seriously this idea of democratizing
[00:10:20] the technology to everyone around the world, in every country.
[00:10:24] And that's what Google's always done with search and
[00:10:26] and YouTube and its main products.
[00:10:27] And that's why we spend so much time on these flash level and even flash
[00:10:31] light level, very efficient, very performant models,
[00:10:35] but that are cheap and fast and can be used everywhere.
[00:10:39] Of course we have a big need for that ourselves internally,
[00:10:42] which is why we push that for all of our products.
[00:10:44] But we also think it's the sort of thing
[00:10:46] that developers and builders are going to really enjoy too.
[00:10:50] Okay, let's let's fast forward five years.
[00:10:52] Maybe let's say, and let's say we hit an AGI and we've cured
[00:10:55] some of the big diseases.
[00:10:57] Where are you focusing your time?
[00:10:58] What’s the next mission?
[00:11:00] Well, it's a couple of things I think I would be thinking about.
[00:11:02] One is, using the AI tools myself to help us understand
[00:11:08] my, my kind of overall scientific goal, which is the nature of reality.
[00:11:12] Right.
[00:11:12] That's always what I've been sort of obsessed with since a kid.
[00:11:15] And really, that means doing some physics and physics experiments,
[00:11:18] but with the help of AI. So that's one thing.
[00:11:21] Second thing I think is maybe I would pivot a little bit to more
[00:11:24] philosophical topics around, you know, what it means to be human.
[00:11:28] What's special about that?
[00:11:29] How do we want society to change and adapt to this incredible,
[00:11:34] transformation that is going to happen
[00:11:36] as we, you know, start to travel to the stars and,
[00:11:39] you know, what does that mean about society and the human condition?
[00:11:42] So I'd like to maybe try and help out there if I can.
[00:11:45] Speaking about human meaning, do you have any, like, initial thoughts there?
[00:11:49] I know you're very deep in the weeds here.
[00:11:52] Have you thought about, like, what's left for human meaning after AGI at all?
[00:11:55] Well, I think that's it's all still to be written in my view.
[00:11:58] You know, I think the next generation, they're going to be growing up natively
[00:12:02] with these tools, just like I did with computers
[00:12:05] and programing in the first place.
[00:12:06] And then we created this world
[00:12:08] that I can't wait to see what the students of today are going to do.
[00:12:12] Growing up with these sort of tools and all my superpowers in a way,
[00:12:15] and combining that with traditional skills in math and computer science,
[00:12:19] I think that's still going to be relevant,
[00:12:21] at least as far as I can see the next ten years, so that you can really
[00:12:24] understand how these systems work so you can take best advantage of them.
[00:12:29] And then, I think amazing new things are going to be created.
[00:12:32] I, I've got a lot of faith in human ingenuity
[00:12:35] where we're sort of instantly adaptable.
[00:12:37] We’re general intelligences ourselves, don’t forget.
[00:12:40] Look at what we built around us, it’s incredible,
[00:12:42] with our hunter gatherer brains. Why would we stop here?
[00:12:45] You know, it's like we're amazing at adapting to tools.
[00:12:49] Look at the way we
[00:12:50] we see even the tools we have today, these AI tools we're marveling at today,
[00:12:54] just a few years ago, that would have been unthinkable.
[00:12:56] But today we've just totally adapted to it.
[00:12:58] Oh yeah.
[00:12:58] You know, we chat with bots that are basically Turing test level,
[00:13:01] and we make Omni models that can create any video,
[00:13:04] and we're kind of like, yeah, you know, that's kind of normal.
[00:13:07] And so I think that's the good side of human adaptability.
[00:13:12] And I'm sure that will be the case.
[00:13:14] Going forwards too.
[00:13:16] It's kind of the Waymo analogy I like where like you try Waymo once
[00:13:19] and you know, you're taking a video in the car.
[00:13:21] And it's insane.
[00:13:22] Yeah. Driverless car.
[00:13:23] But then you do it a second time and it's like oh is this kind of normal.
[00:13:27] It's weird that it's normal. Right.
[00:13:29] It's the same with these AI tools now.
[00:13:30] But again, that's the sign.
[00:13:31] That's because our brains are general And so general, even though they were
[00:13:35] evolved for a particular purpose, you know, Hunter gathering.
[00:13:38] But we’re a toolmaking species.
[00:13:41] And that's what separates us from the other animals.
[00:13:43] And I think that's, led us to where we are today with modern civilization.
[00:13:48] And I think AI is just the next step.
[00:13:50] What human skills
[00:13:51] do you think get more valuable as AI increasingly gets more capable?
[00:13:55] Well, I think it's very clear in this way that certainly in the short term
[00:13:58] it's harder to predict out, you know, ten years from now.
[00:14:00] But I would say in the next five years, it's very obvious to me that taste,
[00:14:04] design sensibility, original thinking,  being able to synthesize
[00:14:09] different subjects together,
[00:14:11] I think being quite broad minded in your knowledge and skills,
[00:14:15] I think it's going to be amazing people who are kind of creative and technical,
[00:14:20] people like yourself, I think, are going to be in an amazing position.
[00:14:24] With these technical tools, but then combining it with creativity,
[00:14:28] whether that's in, in, in the arts form or the science form.
[00:14:32] You know, I've always said
[00:14:33] what separates the great scientist
[00:14:35] from the good scientist is not their technical capability.
[00:14:37] Because if you're professional scientist, you're obviously very good technically,
[00:14:40] it's that creative capability, that sort of taste and judgment.
[00:14:44] And I think,  that's going to be at the fore also,
[00:14:48] connecting with your audience, whether you're building a product
[00:14:51] or making a film or game, you know, how do you really connect
[00:14:54] emotionally with the other human beings that you're making this for?
[00:14:58] That isn't going to come from the tool, the AI tools.
[00:15:00] I think that's going to come from the from the human creator and the human expert.
[00:15:04] Right.
[00:15:05] So taste and judgment and continuing to learn the skills, the skills needed.
[00:15:09] Yeah. Combining the two.
[00:15:10] Yes. Because the deeper you understand the technology,
[00:15:13] the more you're going to better take advantage of it.
[00:15:14] And keep that at the forefront. Right.
[00:15:17] All right.
[00:15:18] So we're almost out of time.
[00:15:19] But the one thing I want to ask you is
[00:15:22] the news cycle is very much focused around agents and AI,
[00:15:25] but is there anything specific that you think is
[00:15:29] just been on your mind recently that is under hyped?
[00:15:32] Well, I think we got a I'm very excited about this new agentic era.
[00:15:35] And you can see us leaning into that.
[00:15:37] The whole of I/O is really about that, right?
[00:15:39] With spark and Antigravity and the new flash.
[00:15:43] But of course, we've also got to think about the security side of that, too.
[00:15:47] You know, that's one of the things I think we can do really well is combine
[00:15:51] really amazing frontier capabilities, but with reliability and robustness
[00:15:56] as well as connecting to,
[00:15:57] you know, the ecosystem of products people already know and love.
[00:16:00] So I think that's the next phase.
[00:16:02] But I do worry about, you know, you're seeing it a little bit
[00:16:06] with the cyber worries about,  some of the models.
[00:16:10] And I think that's just the beginning of some of the issues that we need to get
[00:16:14] that we need to make sure we guard against,
[00:16:17] as well as getting excited about all the amazing opportunities.
[00:16:20] So I think that's playing a little bit on my mind.
[00:16:22] Maybe this is the time now to, you know, to try
[00:16:25] and push some standards and maybe international cooperation.
[00:16:30] Well, thanks so much for your time.
[00:16:31] It's always pleasure. Talking.
[00:16:32] Yeah. Lovely talking to you, as always. Thanks for doing this.
[00:16:35] Thank you.
