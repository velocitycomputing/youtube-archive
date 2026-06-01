---
video_id: brB-hSiV2iU
title: The Real Reason Karpathy Joined Anthropic
channel: "Nate Herk | AI Automation"
url: "https://www.youtube.com/watch?v=brB-hSiV2iU"
watched_date: 2026-05-29
watched_at: "2026-05-29T12:00:00Z"
watch_count: 1
duration_seconds: 984
source: youtube-history-browser
history_label: Friday
history_order: 40
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 984
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video discusses Andrej Karpathy's hire at Anthropic and why it signals a fundamental shift in AI strategy. Karpathy, a founding member at OpenAI and former AI lead at Tesla, has spent the last year publicly developing and teaching concepts around "context engineering"—building the environment and data structures that make AI models useful rather than focusing on model capability alone. His recent projects (LLM Wiki for structured knowledge bases, Auto Research for autonomous optimization loops, and slash goal workflows) align perfectly with Anthropic's current direction: Claude Code, skills, memory systems, and an enterprise services layer announced via a joint venture with major financial firms. The key insight is that the model itself is no longer the differentiator—the real moat is the "wrapper" around it: your documentation, examples, workflows, MCP connectors, and project memory that allow agents to work effectively within your specific business context.

Start building a personal LLM Wiki structure this weekend by organizing your important files, meeting notes, and SOPs into a markdown-based knowledge base that Claude Code can reference and synthesize. Shift your interaction pattern from single-prompt requests to using slash goal commands to define outcomes and let agents work autonomously toward them. If you have domain expertise (accounting, real estate, content creation, etc.), begin documenting your processes and workflows in Claude-readable formats—Anthropic is moving toward a context marketplace where such specialized knowledge will be valuable and tradeable. The actionable principle: stop asking "which model is best" and start asking "how do I surround my model with data, examples, and context that makes it smarter and more useful specifically for my business?"

## Transcript

[00:00:00] All right, so today's May 19th, and a
[00:00:01] few hours ago this tweet just went up.
[00:00:03] It was Andrej Karpathy announcing that
[00:00:05] he has joined Anthropic. And if you
[00:00:07] don't know who that is, this is one of
[00:00:09] the most important people in modern AI.
[00:00:11] He was founding team at OpenAI. He ran
[00:00:13] AI at Tesla for like 5 years. He went
[00:00:15] back to OpenAI, left again, and then
[00:00:17] started an AI education company. And now
[00:00:19] he's at Anthropic. So normally the easy
[00:00:21] version of this video is, you know, big
[00:00:23] AI person joins big AI lab, and that's
[00:00:25] the headline. But I think the more
[00:00:27] interesting question here is why
[00:00:29] Anthropic and why now? Because I'm
[00:00:31] assuming all of these big AI labs have
[00:00:34] wanted a guy like Karpathy to hop on
[00:00:36] board. Because if you look at what
[00:00:38] Karpathy's been building and talking
[00:00:39] about over the last multiple months, and
[00:00:41] when you look at what Claude Code has
[00:00:42] actually been shipping already, it
[00:00:44] almost starts to feel like these two
[00:00:45] things were kind of moving towards the
[00:00:47] same direction. So in this video, I want
[00:00:50] to show you the pattern that I think
[00:00:51] most people might miss when they sort of
[00:00:53] see this news, which is like the wrapper
[00:00:55] around the model, why your data and
[00:00:58] context are becoming the real product,
[00:00:59] and where do I think Claude Code is
[00:01:01] probably heading next? So let's get into
[00:01:03] it. So real quick, just so that we're on
[00:01:05] the same page, Andrej Karpathy is like
[00:01:08] one of the goats, for sure. He's taken a
[00:01:10] really weird tour around the modern AI
[00:01:12] world because founding member at OpenAI
[00:01:14] back in like 2015, then he ran AI at
[00:01:16] Tesla, came back to OpenAI in 2023, left
[00:01:20] again a year later, and then started
[00:01:22] Eureka Labs, which was basically his AI
[00:01:24] education company. And that's where he
[00:01:25] built stuff like LLM 101N, which is like
[00:01:28] a free course that teaches you how to
[00:01:29] build a language model from scratch, not
[00:01:31] something that I know how to do. And
[00:01:33] he's also the person who like coined the
[00:01:34] term vibe coding, which is kind of what
[00:01:37] a lot of us are doing right now. You
[00:01:38] describe what you want in English, and
[00:01:40] you let the AI write the code, and then
[00:01:43] you kind of are just there vibing and
[00:01:44] steering it and editing and iterating
[00:01:47] with it. So he hasn't just been working
[00:01:48] in AI, he's been shaping how people
[00:01:51] think about and understand AI for a long
[00:01:53] time. And now he's going to be at
[00:01:55] Anthropic. And that matters for a lot of
[00:01:57] reasons, but the two that I wanted to
[00:01:59] talk about today. So, first, Anthropic
[00:02:02] already has a ton of momentum with
[00:02:04] builders, right? Like Claude Code has
[00:02:05] become one of the main tools people
[00:02:07] reach for when they want an agent or
[00:02:09] they want to code or, you know, do work
[00:02:11] like that, even just general knowledge
[00:02:12] work. And then about a week ago, Ramp
[00:02:15] put out their AI Index, which tracks
[00:02:17] like business spending across companies.
[00:02:19] And for the first time in this data set,
[00:02:22] Anthropic has passed OpenAI in business
[00:02:25] adoption. It was like 34.4% to 32.3%.
[00:02:29] Now, to be fair, this
[00:02:31] isn't the entire market. It's Ramp's
[00:02:33] customer base. And OpenAI still has a
[00:02:36] massive consumer brand and huge
[00:02:37] enterprise contracts that may not end up
[00:02:39] like on that sort of data or breakdown.
[00:02:42] So, I don't want to overstate it, but
[00:02:44] it's definitely a momentum signal. It's
[00:02:45] hard to ignore. Anthropic has obviously
[00:02:47] been moving really, really fast,
[00:02:49] shipping new things really, really fast,
[00:02:51] and getting a lot more adoption. That's
[00:02:53] clear. And part of that story seems to
[00:02:55] be Claude Code. And there's another
[00:02:57] signal here that I think really does
[00:02:58] matter, which is
[00:03:00] earlier this month, Anthropic also
[00:03:01] announced a new enterprise AI services
[00:03:03] company, kind of like a joint venture
[00:03:05] with Blackstone, Hellman & Friedman, and
[00:03:07] Goldman Sachs. And the whole point of
[00:03:09] that is to help mid-size businesses
[00:03:12] actually bring Claude into their core
[00:03:14] operations. So, if you think about
[00:03:16] what that means and why they're doing
[00:03:17] it, because they have all these
[00:03:18] impressive revenue figures from like a
[00:03:21] Claude Code subscription standpoint. But
[00:03:24] they're basically
[00:03:26] way more than just, "Hey, here's a
[00:03:27] model. Good luck, go use it." They're
[00:03:29] building the model, they're also
[00:03:30] building the product surface, they're
[00:03:31] building the partner network, and of
[00:03:33] course now like a services layer that
[00:03:35] helps companies adopt their product. And
[00:03:38] that's a completely different game, and
[00:03:39] it points to the same thesis, which is
[00:03:41] the model is not the moat forever. The
[00:03:44] moat is the application and the adoption
[00:03:46] and the IP that doesn't live in the
[00:03:47] model. But
[00:03:49] it's getting Claude embedded into the
[00:03:50] real workflows where businesses actually
[00:03:52] can make money, save time, reduce
[00:03:54] errors, scale without increasing
[00:03:56] headcount, and all of that kind of
[00:03:57] stuff.
[00:03:58] Now, Karpathy's entire public philosophy
[00:04:01] right now lines up almost perfectly with
[00:04:03] what Anthropic seems to be building. And
[00:04:05] that's the part that I think is really
[00:04:07] important to be paying attention to
[00:04:08] because the real story is not like
[00:04:10] AI famous goat joins Anthropic. The real
[00:04:13] story is
[00:04:14] the wrapper and what is actually the
[00:04:17] product at Anthropic. Because most
[00:04:19] people still talk about AI like the
[00:04:20] model is the end-all-be-all, you know,
[00:04:22] is is GPT-5.5 better or Opus-4.7,
[00:04:25] Gemini, all of these. Which one has the
[00:04:27] best benchmark? What about the
[00:04:29] leaderboards?
[00:04:30] And obviously the model matters. I'm not
[00:04:32] saying it doesn't. Like it it matters.
[00:04:34] But the longer that I use these tools
[00:04:36] and the longer that I see how good
[00:04:38] they're getting so quick,
[00:04:40] the more I realize that the model is
[00:04:41] only one small layer of the product. The
[00:04:43] thing that actually changes your
[00:04:44] day-to-day experience is the wrapper
[00:04:45] around the model. Because you see people
[00:04:47] getting crazy outputs and you see other
[00:04:49] people using the same model that are
[00:04:50] getting horrible outputs, right? Like
[00:04:51] there's obviously something going on
[00:04:52] there. And when I say wrapper, I mean
[00:04:54] like the stuff that goes into how the
[00:04:55] model gets used. So, Claude Code is a
[00:04:57] wrapper, Codex is a wrapper, skills,
[00:04:59] sub-agents, hooks, MCP connectors, your
[00:05:00] Claude-at-MD, your memory, your docs,
[00:05:02] your examples, all that kind of stuff.
[00:05:04] That is the environment that the model
[00:05:07] lives inside of and operates inside of.
[00:05:09] And this is where Karpathy has been
[00:05:10] extremely consistent. You know, he also
[00:05:12] kind of coined the term context
[00:05:13] engineering instead of prompt
[00:05:15] engineering, which basically means the
[00:05:16] real skill is not writing the perfect
[00:05:18] prompt. The real skill is building the
[00:05:20] right environment and folder structure
[00:05:22] and um
[00:05:23] documents so that the model can actually
[00:05:26] work and be useful over and over again
[00:05:28] and remember things. So, if you think
[00:05:30] about it like this,
[00:05:31] you open up a brand new chat window and
[00:05:33] you ask Claude to help you with your
[00:05:34] business and it knows nothing about you.
[00:05:36] Like these things are essentially
[00:05:37] stateless every single time you use
[00:05:39] them, meaning there's no context or
[00:05:41] memory.
[00:05:42] And it can still be useful, but it's
[00:05:44] usually guessing and you find yourself
[00:05:45] re-explaining stuff and that's where you
[00:05:46] get frustrated. But if Claude has your
[00:05:49] files and your examples and your
[00:05:50] workflows and your style guides and the
[00:05:51] actual success criteria for what good
[00:05:53] looks like, now you're playing a
[00:05:54] completely different game. So, same
[00:05:56] model, totally different outcome. And
[00:05:58] that's why I think that this hire
[00:06:00] matters.
[00:06:01] Anthropic has been building the wrapper
[00:06:03] and Karpathy has been teaching people
[00:06:05] how to think about and understand and
[00:06:07] get the most out of the model with
[00:06:09] different methods for like wrapping it
[00:06:11] in something. And those two philosophies
[00:06:13] basically just merge into one company.
[00:06:15] And once you see it like that,
[00:06:16] you also see that the last few months of
[00:06:18] Karpathy's public work, they start to
[00:06:20] look a lot less random. You know, they
[00:06:21] look like a road map of how to be using
[00:06:24] AI. So, back in April, Karpathy dropped
[00:06:27] what he called the LLM Wiki. And I made
[00:06:29] a full video breaking this down. It's
[00:06:31] doing really well. Like people were
[00:06:32] obsessed with this idea. It was going
[00:06:33] viral on X. Karpathy's LLM Wiki. So,
[00:06:36] I'll tag that right up there if you want
[00:06:37] to check it out. But the short version
[00:06:39] is basically very simple. It's that you
[00:06:40] create a raw folder with a bunch of
[00:06:42] markdown files and you have a wiki
[00:06:44] folder and the agent like synthesizes
[00:06:47] it, it builds connections and it gives
[00:06:49] you this like mind map of
[00:06:51] all of your research or documents or
[00:06:53] whatever it is. And then you give it a
[00:06:55] schema document. So, like kind of a
[00:06:56] Claude.md or Agent.md style file that
[00:06:59] tells the agent how the system works and
[00:07:00] how to look through it and how to um you
[00:07:03] know, ingest more stuff into it. So,
[00:07:06] instead of the AI just searching through
[00:07:07] a bunch of raw files or even just doing
[00:07:09] like a vector database query, it
[00:07:11] actually builds like a living evolving
[00:07:12] knowledge base where it can read the
[00:07:14] sources and understand relations between
[00:07:15] different things and it you know, people
[00:07:18] were building their second brains with
[00:07:19] this thing. And it's really important
[00:07:20] because when people say like data is the
[00:07:22] moat, I think most people picture some
[00:07:24] giant enterprise database. But for
[00:07:26] actual users, for normal builders, your
[00:07:28] data moat might be much smaller and much
[00:07:30] more practical because it could just be
[00:07:32] like your meeting notes, your internal
[00:07:34] SOPs, your customer calls, your
[00:07:36] transcripts, things like that. You know,
[00:07:38] your random internal naming conventions,
[00:07:40] the stuff that makes your frameworks and
[00:07:42] your work actually yours or your
[00:07:44] businesses. And if Claude can turn that
[00:07:46] into
[00:07:47] usable context that the model then gets
[00:07:50] to see and use, the model gets smarter
[00:07:53] and more useful to you specifically
[00:07:54] every single week. And that's kind of
[00:07:56] like the lock-in. Not because you can't
[00:07:57] switch models because you can, but
[00:07:59] because
[00:08:00] the longer that you get addicted to this
[00:08:02] operating system, the more context
[00:08:04] workflows and memory you build inside of
[00:08:06] it,
[00:08:07] the more you're going to want to use it,
[00:08:08] right? So, the LLM Wiki is more than
[00:08:10] just a cool side project. It is a clue
[00:08:12] about what Claude Code might be doing. I
[00:08:15] wouldn't be surprised if eventually
[00:08:16] there's a much more native version of
[00:08:18] this sort of like LLM Wiki
[00:08:20] structure within Claude Code or Claude's
[00:08:23] like project memory. So, you've got the
[00:08:25] agent that builds and maintains and
[00:08:26] inspects, you know, you're already
[00:08:27] seeing stuff they're doing with like the
[00:08:28] Auto Dream feature. So,
[00:08:31] that obviously is very important. And
[00:08:32] you don't have to wait for that. You
[00:08:33] know, you could build your own tiny
[00:08:34] version of this stuff this weekend by
[00:08:36] having Claude Code look through all of
[00:08:37] your documents and your important files
[00:08:39] and building a Wiki and even using the
[00:08:41] LLM Wiki style. So, something worth
[00:08:43] checking out. Because if you really want
[00:08:45] to be like AI first and have your own
[00:08:46] agentic operating system, your data is
[00:08:48] only useful if the agent knows how to
[00:08:50] find it and use it in the right way.
[00:08:52] Now, also, back in March, Karpathy
[00:08:54] released a project he was working on
[00:08:56] called Auto Research. And what that
[00:08:58] thing does basically is it sets up like
[00:09:00] an autonomous research loop. And we
[00:09:01] might have seen something similar with
[00:09:02] like the Ralph loop earlier, the Ralph
[00:09:04] Wiggum plugin,
[00:09:05] where
[00:09:06] it takes a training script, it proposes
[00:09:08] a change, it runs a short training job.
[00:09:10] So, it basically auto research, it
[00:09:11] experiments. And then it checks it
[00:09:13] against typically an objective criteria,
[00:09:16] some sort of objective metric where we
[00:09:17] can say yes, it passed or no, it didn't.
[00:09:20] And the idea is that it continuously
[00:09:21] optimizes for however long it takes
[00:09:24] to hit that. So, honestly, it's not a
[00:09:26] feature that I use a ton because I'm not
[00:09:29] like building
[00:09:30] apps or I'm not training models. So, I
[00:09:32] don't have a ton of need for like this
[00:09:34] auto research
[00:09:36] auto experimenting for some sort of
[00:09:38] metric type of deal, but it is very cool
[00:09:40] to think about the ability for agents to
[00:09:43] be long running like that and work
[00:09:44] towards a goal.
[00:09:46] And it's basically that loop of define
[00:09:47] the goal, let the agent work, and then
[00:09:48] you come back when hopefully it's done.
[00:09:50] And then very recently, we'd already
[00:09:52] seen Codex have like a slash goal. Now
[00:09:54] Hermes got a slash goal. Cloud code has
[00:09:56] their own native slash goal, which is
[00:09:58] essentially this idea of like the auto
[00:09:59] research. And I'm assuming it's going to
[00:10:01] be something that all AI models natively
[00:10:03] adopt
[00:10:05] very soon. Now I do want to be careful
[00:10:06] here because I'm not saying that
[00:10:07] Karpathy personally like invented this
[00:10:09] feature. I've no idea. And under the
[00:10:11] hood, auto research and slash goal are
[00:10:13] kind of different things, but the
[00:10:14] pattern is clearly related. You know,
[00:10:16] both are trying to move us away from one
[00:10:17] prompt, one answer. They move us towards
[00:10:19] setting the outcome. We define sort of
[00:10:22] like the what. We don't exactly define
[00:10:23] the how, which is kind of like just vibe
[00:10:25] coding on steroids and
[00:10:28] coming back to an output that's done.
[00:10:29] And that's just a massive shift.
[00:10:32] Because once you have the context from
[00:10:33] the LLM Wiki idea and you have the
[00:10:34] autonomous loops from stuff like auto
[00:10:35] research and slash goal, the whole thing
[00:10:37] stops feeling like just a chatbot. It
[00:10:39] starts feeling way more like an actual
[00:10:41] employee that knows the stuff about your
[00:10:43] business and can just work for you until
[00:10:45] you have said goal. So now let's go back
[00:10:47] to the announcement suite because
[00:10:48] there's one sentence in his actual tweet
[00:10:50] that I think
[00:10:51] we need to sort of double click on,
[00:10:53] which is the education sentence. He
[00:10:55] says, "I remain deeply passionate about
[00:10:57] education." And that matters because
[00:10:59] Eureka Labs, his last company, was
[00:11:01] basically an education play. The whole
[00:11:02] point was helping people understand AI
[00:11:05] from inside out. So beyond just like,
[00:11:06] "Hey, click this button, connect the
[00:11:08] nodes here, do this." It was more so
[00:11:10] like how do these systems actually work?
[00:11:12] And Karpathy is the one of the rare
[00:11:13] people who can take something insanely
[00:11:15] technical like that and make it feel
[00:11:17] weirdly approachable and understandable.
[00:11:20] And that's the skill. You know, knowing
[00:11:21] the thing is one skill, but teaching it
[00:11:23] in a way where other people can
[00:11:24] understand it and use it is the real
[00:11:26] skill. And I think that that's a huge
[00:11:28] clue for Anthropic because if If next
[00:11:30] phase is about context and workflows and
[00:11:32] skills and you know, memory and loops,
[00:11:34] then the bottleneck is not only
[00:11:36] technical, but it's also educational.
[00:11:39] You know, we're seeing
[00:11:40] that study that we just talked about on,
[00:11:42] you know, a previous video, the IBM
[00:11:44] study about adoption and change
[00:11:46] management and how much of a gap there
[00:11:49] is between skills and actual usage of
[00:11:51] those skills.
[00:11:53] So, having one of the best educators in
[00:11:55] your org to help get all of these
[00:11:57] businesses to adopt and get stuck and
[00:11:59] get addicted on stuff. It's interesting
[00:12:01] to think about, right? Okay, so I want
[00:12:02] to make three predictions and just to be
[00:12:04] clear, like to be very clear, these are
[00:12:06] just predictions and just things that
[00:12:08] popped in my head when I read that tweet
[00:12:09] and thought about it a little bit. So, I
[00:12:11] could very well be wrong. I don't know
[00:12:13] Anthropic's road map. You know, I don't
[00:12:14] have any insider info.
[00:12:15] But if you look at what Karpathy has
[00:12:17] been building in public and you look at
[00:12:18] what Claude code has already been
[00:12:20] shipping and has shipped, I think the
[00:12:22] direction is getting
[00:12:23] clear. So, this first prediction is that
[00:12:26] they are going to build their own app
[00:12:28] store for context. And they're kind of
[00:12:29] already doing that, right? They have
[00:12:30] their official plugins and skills. But
[00:12:32] I'm not meaning like just a prompt
[00:12:33] marketplace. I think the value of this
[00:12:35] is something deeper like skills and
[00:12:37] workflows and project memories and
[00:12:39] domain specific context and evaluation
[00:12:41] loops and connectors to real data. So,
[00:12:43] examples that teach the model what good
[00:12:46] looks like in a specific job, so that
[00:12:48] people can take these little components
[00:12:49] and plug them into their own
[00:12:51] domains and own workflows and just
[00:12:53] instantly get more value out of that
[00:12:55] model, even though the model itself is
[00:12:57] already really smart. Because like I
[00:12:58] said, that model is becoming less of the
[00:13:00] differentiator for normal users. The
[00:13:02] real question is who can surround the
[00:13:04] model with the right data and the right
[00:13:05] harness
[00:13:07] to
[00:13:09] I guess earlier I wasn't saying harness,
[00:13:10] I was saying um wrapper, to get that
[00:13:13] right, like, you know, feedback loop to
[00:13:14] actually get results that drive real ROI
[00:13:17] for a business. So, the LLM wiki was a
[00:13:19] pattern for turning messy info into
[00:13:20] usable memory {slash} goal is a pattern
[00:13:22] for turning a goal into an autonomous
[00:13:24] loop. And Karpathy's education work is a
[00:13:26] pattern for making hard AI concepts feel
[00:13:28] usable for the average person. That
[00:13:29] content is useful, but the deeper thing
[00:13:31] is that he's packaging behavior. And if
[00:13:33] Anthropic can turn that behavior and
[00:13:36] that teaching style into a real
[00:13:37] ecosystem, then Claude could start to
[00:13:38] look like a coding tool and more like a
[00:13:41] marketplace. So, prediction number two
[00:13:43] is that we're going to see way more of
[00:13:45] the slash goal style
[00:13:47] prompts and functionality. You know, I
[00:13:49] think that slash goal is probably one of
[00:13:51] just the first versions of this, but
[00:13:53] it's not the final version. You know, I
[00:13:54] can imagine so many more commands that
[00:13:56] work in a similar way with maybe
[00:13:57] research loops or debug loops or things
[00:14:00] that are specialized for not just hey,
[00:14:02] give it a goal and it will do that, but
[00:14:03] hey, give it a goal about X, Y, and Z
[00:14:05] very specifically and it will do it
[00:14:07] better. It's more specialized. And
[00:14:08] again, I don't know the exact feature
[00:14:09] names, that's not the point. The point
[00:14:11] is that the interface changes. So, you
[00:14:13] stop saying do this one step, you start
[00:14:15] saying keep going until this condition
[00:14:16] is true in this specific vertical.
[00:14:20] So, prediction number three, Anthropic
[00:14:22] ships an education layer for packaging
[00:14:24] your own workflows. This is the one that
[00:14:26] is a little bit more out on a limb, but
[00:14:28] honestly it's the one that I think is
[00:14:29] really interesting because if Anthropic
[00:14:31] wants a context marketplace,
[00:14:34] then they need to have regular people be
[00:14:36] able to not only use it, but contribute
[00:14:39] to it. So, developers, researchers, but
[00:14:41] also people with specific subject matter
[00:14:44] expertise, specific domain knowledge
[00:14:46] from normal jobs. So, the accountant who
[00:14:49] knows the monthly close process or the
[00:14:51] real estate person who knows every step
[00:14:53] about a property in take. Maybe even the
[00:14:55] YouTuber who knows good packaging versus
[00:14:57] bad packaging and how to brainstorm an
[00:14:59] idea and lay it out from beginning to
[00:15:01] end cuz all of that knowledge is really
[00:15:02] valuable. But right now,
[00:15:05] a lot of it's just trapped in people's
[00:15:06] heads or it's scattered across messy
[00:15:07] docs and slack threads or click up
[00:15:10] channels or whatever it is that they use
[00:15:12] on the day-to-day. So, I don't know what
[00:15:13] that's going to look like, but it's like
[00:15:15] how do you actually get subject matter
[00:15:16] expertise from someone in an area where
[00:15:19] you're not a subject matter expert? You
[00:15:21] know, like if I wanted to build for
[00:15:22] example, an advertising agent, it would
[00:15:24] be tough for me because I don't have
[00:15:25] that subject matter expertise. But if
[00:15:27] there was a marketplace that I could
[00:15:29] subscribe to and have like just all of
[00:15:31] this really good data and like, you
[00:15:33] know, you're seeing these people, these
[00:15:34] coaches,
[00:15:35] create their own chatbots. They're
[00:15:36] creating their own AI avatars and
[00:15:38] chatbots and charging people to talk to
[00:15:39] them because the people need to extract
[00:15:41] that data and apply it to their
[00:15:42] business. So anyways, this one might
[00:15:44] have been all over the place, but
[00:15:46] hopefully some of this made you guys
[00:15:47] think and maybe you agree with me on
[00:15:49] some points, maybe you disagree. Feel
[00:15:50] free to let me know in the comments. I
[00:15:51] think it's just really interesting to be
[00:15:53] thinking about this kind of stuff and
[00:15:55] especially when you have this new news,
[00:15:56] it's like
[00:15:57] why? Like how did we get here? Because
[00:15:59] this isn't something where you're like
[00:16:00] yesterday they called up Perplexity and
[00:16:01] they said, "Hey, do you want to come
[00:16:02] work for us?" And he goes, "Yeah." Like
[00:16:04] this was probably
[00:16:05] in discussion for a long, long time. And
[00:16:07] I just I like to try to think about when
[00:16:09] it started and why and what they talked
[00:16:11] about, you know what I mean? So anyways,
[00:16:13] that is going to do it for this one, but
[00:16:14] hopefully you guys enjoyed or you
[00:16:15] learned something new and if you did,
[00:16:17] please give it a like, it helps me out a
[00:16:18] ton.
[00:16:18] And as always, I appreciate you guys
[00:16:19] making it to the end of the video. I
[00:16:21] will see you guys all in the next one.
[00:16:23] Thanks, guys.
