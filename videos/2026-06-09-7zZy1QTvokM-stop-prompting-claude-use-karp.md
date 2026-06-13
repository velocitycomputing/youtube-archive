---
video_id: 7zZy1QTvokM
title: "Stop Prompting Claude. Use Karpathy's Method Instead."
channel: Austin Marchese
url: "https://www.youtube.com/watch?v=7zZy1QTvokM"
watched_date: 2026-06-09
watched_at: "2026-06-09T12:00:00Z"
watch_count: 1
duration_seconds: 798
source: youtube-history-browser
added_date: 
history_label: Tuesday
history_order: 72
watched_at_precision: date-from-history-label
watched_percent: 61
estimated_watched_seconds: 487
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What was discussed:**
Karpathy's method for 10x faster AI development consists of three layers. Layer 1 (Spec): AI fails at context-driven decisions because it has no signal to act on—bridge this by creating detailed specifications through uncovering your actual goal (not just the task), working agile with tight scopes and checkpoints, and being precise to minimize AI assumptions. Layer 2 (Verifier): Treat AI as a "robot librarian" that can only suggest answers from its training data, not a motivated human—add verification by setting precise evaluation criteria upfront, using a second AI model as a critic, and pulling external signal (data connections, historical examples). Layer 3 (Environment): Build a persistent workspace with a CLAUDE.md file that injects your rules on every prompt, create an LLM knowledge base folder system for your data, develop reusable custom skills, and establish three-tier rules (always do, ask first, never do) with hard tool-level guardrails for critical tasks.

**What's actionable for you:**
Stop prompting Claude with vague requests—instead, have Claude interview you to uncover your real goal, then break the task into agile cycles with checkpoints where you review and adjust outputs. Create a CLAUDE.md file documenting your project structure, custom skills, and key rules, then set precise evaluation criteria before Claude starts any work. Use a verification step that either runs a second AI model on the output or brings in external data to confirm success. For anything you do repeatedly, build a custom skill. For tasks where getting it wrong is costly, enforce rules at the tool level (via pre-tool hooks) rather than just in prompts—this prevents Claude from bypassing them. Remember: you can outsource thinking, but understanding your goals and bigger picture is what directs AI effectively.

## Transcript

[00:00:00] I just listened to Andrej Karpathy speak
[00:00:01] at AISN 2026, and I learned something
[00:00:04] that I wasn't expecting. Almost everyone
[00:00:06] is prompting Claude wrong. So, I decided
[00:00:08] to dig deeper and see exactly how
[00:00:09] Karpathy, the former head of AI at
[00:00:11] Tesla, uses AI in 2026. And it turns out
[00:00:14] that Karpathy's method for building 10
[00:00:16] times faster can be broken down into
[00:00:18] three simple layers. So, in today's
[00:00:20] video, I'll be breaking down each layer
[00:00:22] so that anybody can apply them. And then
[00:00:23] I'll show you the one thing that
[00:00:25] Karpathy said to focus on in the age of
[00:00:27] AI. So, layer one is the spec. AI models
[00:00:29] are incredibly smart, but they're still
[00:00:31] missing something. To showcase their
[00:00:33] current limitation, Karpathy explained a
[00:00:35] simple question AI will get wrong.
[00:00:37] >> I want to go to a car wash to wash my
[00:00:39] car, and it's 50 m away. Should I drive
[00:00:42] or should I walk? And state-of-the-art
[00:00:45] models today will tell you to walk
[00:00:46] because it's so close.
[00:00:48] >> At first, I actually didn't believe
[00:00:49] this, so I went to Claude, Gemini, Grok,
[00:00:51] and ChatGPT, asked them the same
[00:00:52] question, and they all gave me the same
[00:00:54] answer. And it reveals the whole
[00:00:55] foundation of this video. AI is
[00:00:57] brilliant at what can be measured, but
[00:01:00] for context-driven things like needing a
[00:01:02] car for a car wash, it has no signal to
[00:01:05] act on. So, how do you bridge this gap
[00:01:07] between your understanding and your
[00:01:08] contextual information and AI's
[00:01:10] computational power? That's where the
[00:01:11] spec comes in. And a spec is how you
[00:01:13] deliver your understanding to Claude in
[00:01:15] a format it can use. A term you may have
[00:01:17] heard is Claude's plan mode, which
[00:01:19] essentially can be used to help you
[00:01:20] create a plan before building anything.
[00:01:22] But Karpathy thinks that this is too
[00:01:25] high-level.
[00:01:25] >> I actually don't even like the plan
[00:01:27] mode. I I would
[00:01:28] I mean, obviously it's very useful, but
[00:01:30] I think there's something more general
[00:01:31] here where you have to work with your
[00:01:32] agent to design a spec that is very
[00:01:34] detailed.
[00:01:34] >> Now, Karpathy isn't telling you that
[00:01:36] plan mode is bad. What he's actually
[00:01:38] saying is you have to go deeper, work
[00:01:40] with these AI tools to design the actual
[00:01:42] spec. So, how do you create a spec that
[00:01:44] Claude can successfully use to build
[00:01:46] what you're trying to build? The first
[00:01:48] step is you have to uncover your goal.
[00:01:50] If you just say, "Create a end-of-month
[00:01:52] report," that's a task, but the actual
[00:01:54] goal is a conclusion you're trying to
[00:01:56] draw, the decision the report drives.
[00:01:59] And what the goal actually is is
[00:02:00] something AI will literally never be
[00:02:02] able to decide. So, to help you do this,
[00:02:04] we'll tell Claude to interview me to
[00:02:07] identify the goal of this project. This
[00:02:09] is the way to get the information out of
[00:02:11] you and into the spec. Now, step two is
[00:02:13] be agile with how you work. There are
[00:02:15] two methods of completing any task. The
[00:02:17] first is waterfall, and the other is
[00:02:19] agile. Waterfall is you take a big task
[00:02:22] and you complete the entire thing, and
[00:02:24] then you show the final product. Agile
[00:02:26] on the other hand is you break that same
[00:02:27] task into small buckets, and you show
[00:02:30] the result throughout the entire process
[00:02:32] to make sure you're going in the right
[00:02:33] direction. And people are extremely
[00:02:35] susceptible to using AI agents in a
[00:02:37] waterfall manner because they want to
[00:02:38] give them everything to do at once. The
[00:02:41] better move is agile specking. You want
[00:02:43] to have a tight scope, a clear
[00:02:45] checkpoint, you want to review the
[00:02:46] output, adjust it, and then repeat. To
[00:02:48] help with this, we'll tell Claude to
[00:02:50] bias towards smaller and more
[00:02:51] compartmentalized specs. Step three is
[00:02:54] you want to be precise and use your
[00:02:55] brain. The more precise you are, the
[00:02:57] less AI has to assume. And every
[00:02:59] assumption that AI makes is a chance for
[00:03:01] it to drift from the final product you
[00:03:03] actually want. And when you have AI
[00:03:05] create a spec for you, you have to use
[00:03:07] your brain to think critically about
[00:03:09] what that spec actually says. So, to
[00:03:12] help you use your brain, you can say
[00:03:13] "Make me verify key decisions explicitly
[00:03:16] to ensure nothing is missed." And when
[00:03:18] you put these three pieces together, we
[00:03:20] have a final prompt we can use in Claude
[00:03:22] to help create a tightly scoped,
[00:03:24] well-thought-out
[00:03:26] aligns with our actual goal. This is a
[00:03:27] process that I call modern engineering,
[00:03:29] which every successful person has to
[00:03:31] become. Now, layer two is the verifier.
[00:03:34] Layer two sits on top of the spec. This
[00:03:36] is the verification process. One of the
[00:03:38] most frustrating things about AI is
[00:03:40] reviewing and verifying the output. And
[00:03:42] unlike a human, it can't grasp
[00:03:44] non-measurable things. So, how can we
[00:03:47] help AI verify its own outputs? Well,
[00:03:49] first you need to understand the mental
[00:03:50] model behind this. And Karpathy explains
[00:03:53] it as animals versus ghosts. Here's him
[00:03:55] getting asked a question about this in a
[00:03:57] recent interview. And if it sounds
[00:03:59] confusing, don't worry, I will simplify
[00:04:00] it after.
[00:04:01] >> And the idea is that we're not building
[00:04:03] animals, we are summoning ghosts. Why
[00:04:05] does that framing matter? And what does
[00:04:07] it actually change about how you build
[00:04:09] and deploy and evaluate or even trust
[00:04:12] them?
[00:04:12] >> Yeah, I think the reason I wrote about
[00:04:14] this is because I'm trying to wrap my
[00:04:15] head around what these things are,
[00:04:16] right? Because if you have a good model
[00:04:18] of what they are or are not, then you're
[00:04:19] going to be more competent at uh using
[00:04:21] them. I think it's just um
[00:04:23] coming to terms with the fact that these
[00:04:24] things are not, you know, animal
[00:04:26] intelligences. Like if you yell at them,
[00:04:27] they're not going to work better or
[00:04:29] worse or doesn't have any impact. Um
[00:04:32] and uh
[00:04:33] it's all just kind of like these
[00:04:34] statistical simulation circuits. It's
[00:04:36] more just being suspicious of it and um
[00:04:38] figuring it out over time.
[00:04:39] >> Now, that's some gigabrain stuff, but
[00:04:41] let me simplify it. People, me and you,
[00:04:43] are used to interacting with people,
[00:04:45] which Karpathy is calling animals. These
[00:04:48] animals are driven by different
[00:04:49] motivators and emotions, which help
[00:04:51] produce the final product and output
[00:04:53] within a team setting. And if you say to
[00:04:55] a person, become an expert at SEO
[00:04:57] marketing in the next 14 days or you're
[00:04:59] fired, they're going to figure it out.
[00:05:01] That's because they have these intrinsic
[00:05:03] motivations. But AI is not that.
[00:05:05] Karpathy describes it as a ghost, but in
[00:05:07] my eyes that's a little too confusing,
[00:05:09] so throw it out the window. Instead,
[00:05:10] think of it like a robot librarian. If
[00:05:12] you ask it that same SEO question, the
[00:05:14] librarian will only suggest resources
[00:05:17] and answers based on the books in its
[00:05:19] library. If it doesn't have a book, it
[00:05:21] can't help you. And part of the
[00:05:22] challenge here is that the librarian
[00:05:24] doesn't know when it's missing a
[00:05:26] specific book. So, it may just
[00:05:28] confidently make something up. And
[00:05:29] that's what's happening when AI nails
[00:05:31] math and fumbles things with context.
[00:05:33] It's brilliant because the library has
[00:05:35] the clear answers. But if it doesn't,
[00:05:37] then it's confidently wrong or
[00:05:40] uncertain. Which means interacting with
[00:05:42] it like it's an animal, i.e. a human,
[00:05:44] doesn't help, right? Yelling at it,
[00:05:46] pleading, just saying, "Make this
[00:05:47] better." doesn't necessarily work.
[00:05:49] Really, the only lever you have, which
[00:05:50] most people don't even think to use, is
[00:05:53] the verification lever. Because by
[00:05:55] optimizing this, it makes it so that
[00:05:56] you're playing within the actual rules
[00:05:58] that the AI follows. So, how do you help
[00:06:00] AI verify the output so it's up to the
[00:06:02] standard you want? Well, there are three
[00:06:04] places to focus on. First, you want to
[00:06:06] set the evaluation criteria up front.
[00:06:08] Before Claude touches a single thing,
[00:06:10] whether that's technical or
[00:06:11] non-technical tasks, define what good
[00:06:13] looks like with precision. For example,
[00:06:16] a vague way to evaluate an output is,
[00:06:17] "Make this report look good." Whereas, a
[00:06:20] precise way would say, "The report must
[00:06:22] have three sections, each ends with a
[00:06:24] recommendation." And if you're making
[00:06:25] the connection, this is very similar to
[00:06:27] what we covered in layer one. The more
[00:06:29] precise you are up front, the less room
[00:06:30] Claude will have to make mistakes. To
[00:06:32] help enforce this, we'll add this to our
[00:06:34] verification Claude prompt. Outline the
[00:06:37] evaluation criteria you will use to
[00:06:38] ensure a high-quality final product. Be
[00:06:40] precise. The second step is use a second
[00:06:43] AI model as the critic. Think of this
[00:06:45] like a second robot librarian from a
[00:06:47] different library. You use that
[00:06:49] librarian to grade the output of the
[00:06:51] first librarian. This other librarian
[00:06:53] has a whole different set of books, and
[00:06:55] that may give them insight into why this
[00:06:57] first librarian is right or wrong. Now,
[00:06:59] a tactical way to do this, if you use
[00:07:01] Claude code, you can install the Codex
[00:07:03] plugin, which will allow you to directly
[00:07:05] ask Codex questions within your Claude
[00:07:07] code session. So, you could say
[00:07:09] something like, "If this turns into a
[00:07:10] complex build, run the final output by
[00:07:13] Codex to ensure both systems agree." And
[00:07:15] step three is pull external signal where
[00:07:18] possible. The question here is, how can
[00:07:19] you bring in additional context that
[00:07:21] will help you verify an output? Here are
[00:07:23] two concrete examples. Let's say you're
[00:07:25] deploying an app and you're not sure if
[00:07:26] it's successfully deployed. What you can
[00:07:28] do instead is connect your Claude
[00:07:29] session with your system where it's
[00:07:31] deployed, so it can verify that it has
[00:07:33] been deployed successfully. We are
[00:07:35] making a connection to pull external
[00:07:36] data to enhance our verification layer.
[00:07:40] And now, if it says that the deployment
[00:07:41] was successful, we know for certainty
[00:07:43] that it actually was. In a non-technical
[00:07:45] example, let's say you're working on a
[00:07:47] monthly report. You could bring in your
[00:07:48] historical reports to use as reference
[00:07:50] for the exact format that the final
[00:07:52] output should be in, pulling in data and
[00:07:54] empowering the verification process.
[00:07:56] Now, bringing in this concept with the
[00:07:57] first two points, combining this third
[00:07:59] point with the first two points, here is
[00:08:01] a prompt that you can run in Claude,
[00:08:03] which will help ensure that you are
[00:08:04] adding a proper evaluation layer where
[00:08:06] it makes sense. I can't stress how
[00:08:07] important this is. The creator of Claude
[00:08:09] code, Boris Cherney, said it best. If
[00:08:11] Claude has a feedback loop, it will two
[00:08:13] to three x quality of the final result.
[00:08:15] So, layer one and layer two are about
[00:08:16] creating specs and evaluating the
[00:08:18] output. The third layer, however, is
[00:08:20] where we build a foundation that can't
[00:08:21] be replicated. But, before we get to
[00:08:23] that, if this is your first video of
[00:08:25] mine, welcome to the channel. If it's
[00:08:26] your second or more, here is our
[00:08:28] anti-slop agreement. The visuals, the
[00:08:30] testing, the hours of research that went
[00:08:32] into this video, this is entirely built
[00:08:34] for humans, not for AI clunkers. So, all
[00:08:37] that I ask is that you subscribe as part
[00:08:38] of this agreement because it helps it
[00:08:39] reach more people so that I can keep
[00:08:41] making videos like this. Also, every
[00:08:43] couple of weeks, I give away a Claude
[00:08:44] Max subscription, so comment below with
[00:08:46] whatever you're building to enter. Layer
[00:08:48] three, the environment. So, layer one
[00:08:50] and layer two need somewhere to live,
[00:08:51] and that's layer three, which is the
[00:08:53] environment that you build in. Think of
[00:08:54] this layer as a workshop. The spec is a
[00:08:56] blueprint pinned to the wall, the
[00:08:58] verifier is the quality check station by
[00:09:00] the door, and then the environment is
[00:09:02] the workshop itself. You need to create
[00:09:04] the proper tooling and the proper system
[00:09:06] so that the whole thing can function at
[00:09:07] a high level. Now, the problem here is
[00:09:09] that most people use the workshop from
[00:09:10] scratch every time they use AI. And no,
[00:09:12] if you have a single chat with your
[00:09:14] entire conversation history, that is not
[00:09:16] what I'm talking about. So, how do you
[00:09:17] create a proper workspace that improves
[00:09:20] over time? First is you need to set up a
[00:09:22] proper Claude MD file. Every time you
[00:09:24] prompt Claude, your Claude.md file gets
[00:09:26] injected automatically. It's essentially
[00:09:28] the first thing that Claude reads to
[00:09:30] help determine how it should operate.
[00:09:31] For example, you can add to your Claude
[00:09:33] MD before building anything multi-step,
[00:09:35] include a verification plan. Now,
[00:09:37] verification is forced into every build,
[00:09:39] not something that you have to remember
[00:09:41] to say. This is just one of the ways
[00:09:42] that you can improve this Claude MD, and
[00:09:44] here's actually mine on the screen, and
[00:09:46] I'm going to call out a couple of
[00:09:47] sections. The first is I outline how
[00:09:49] this repo works. So, think of my repo as
[00:09:51] my workspace. It gives high-level to the
[00:09:53] details around it. I then tell it the
[00:09:55] custom skills and how they're routed,
[00:09:57] how to use them. I then outline the
[00:09:59] architecture of the training data or
[00:10:01] knowledge architecture so that the AI
[00:10:03] knows where to look for certain
[00:10:04] information. And then I have key working
[00:10:06] rules that it should follow no matter
[00:10:08] what. Make this your environment. It's
[00:10:10] your world, and AI is living in it. It
[00:10:12] should not feel like the other way
[00:10:13] around. The second step is you need to
[00:10:15] build your LLM knowledge base. Karpathy
[00:10:17] went viral for this concept on Twitter
[00:10:19] that he calls his LLM knowledge base.
[00:10:21] And this is essentially creating a
[00:10:22] folder system on your machine that
[00:10:24] you're able to ingest your own training
[00:10:26] data in a way that makes it really easy
[00:10:28] for Claude to understand where
[00:10:30] information is. This is so important
[00:10:32] because your data is your moat. And this
[00:10:35] begins the process of building out your
[00:10:37] own intellectual data property. And step
[00:10:40] three is you have to start building out
[00:10:42] your skill set. A general rule of thumb
[00:10:43] that I have is if you plan on doing
[00:10:45] something repeatedly, create a custom
[00:10:47] skill for that. Think of this like a
[00:10:49] handbook to complete a specific task.
[00:10:50] And the more you use these skills, the
[00:10:52] better they'll become. I have a saying
[00:10:53] that I tell my team, the best way to
[00:10:55] find a leak in a hose is to run water
[00:10:57] through it. And it's the same with
[00:10:58] skills. The more you use them, the more
[00:11:00] you'll realize where you need to fix
[00:11:01] them and where they're really good. Keep
[00:11:03] running water through it and your
[00:11:05] system's going to compound over time.
[00:11:07] Step four is create rules for what the
[00:11:09] AI can and can't work on. Depending on
[00:11:11] the cost of getting something wrong, you
[00:11:13] need to establish different AI
[00:11:14] guardrails. So, here's how to think of
[00:11:16] this, right? So, take the Claude.md file
[00:11:18] that I mentioned earlier. You could add
[00:11:20] a line that says, "Don't make up
[00:11:21] information," but that's a guide, not
[00:11:23] necessarily a hard rule. So, at the end
[00:11:25] of the day, AI can still ignore it. So,
[00:11:27] if you have things that are critical not
[00:11:29] to get wrong, then you need to introduce
[00:11:31] rule-based guardrails to ensure that the
[00:11:34] AI can't bypass them. To help you
[00:11:36] visualize this, imagine you have a
[00:11:37] folder called "Important, Don't Edit."
[00:11:40] You could have a rule in Claude MD that
[00:11:41] says, "Don't touch anything in the
[00:11:43] /important, don't edit folder." And that
[00:11:45] might get you 80% of the way there, but
[00:11:48] it's essentially a request, not a rule.
[00:11:51] Claude can still touch those files. So,
[00:11:53] instead, you add a pre-tool use hook
[00:11:56] before Claude uses the write or edit
[00:11:58] tool, and it checks to see the file that
[00:12:00] it's trying to edit. Now, Claude
[00:12:02] literally can't make the edit, and it's
[00:12:04] enforced at the tool level, not the
[00:12:06] prompt level. And as a result of this,
[00:12:08] this is now a concrete rule that the
[00:12:10] agent can't bypass. So, with this in
[00:12:12] mind, bucket things into three groups.
[00:12:14] The first is always do. This is things
[00:12:16] that AI should run on autopilot. The
[00:12:18] second is ask first. So, this is
[00:12:20] anything that you want to double-check.
[00:12:22] And then the third is never do. These
[00:12:24] are lines that can't be crossed that are
[00:12:26] absolutely critical not to get wrong.
[00:12:28] Here's a prompt that brings all of these
[00:12:30] four points that I mentioned to help
[00:12:32] audit your system and create an
[00:12:33] optimized environment for Claude to
[00:12:35] interact with. That's the Karpathy
[00:12:36] method end-to-end, the spec, the
[00:12:38] verifier, and the environment. But
[00:12:40] there's a question that needs to be
[00:12:41] answered. What's the one thing that
[00:12:42] Karpathy thinks we should focus on in
[00:12:44] the age of AI? Here's him getting asked
[00:12:46] this in an interview.
[00:12:47] >> What still remains worth learning deeply
[00:12:50] when intelligence gets cheap as we move
[00:12:53] into the next eight era of AI?
[00:12:55] >> You can outsource your thinking, but you
[00:12:57] can't outsource your understanding. And
[00:12:58] the thing with everything we covered
[00:12:59] here is that the three layers are
[00:13:01] centered around your understanding of
[00:13:03] the bigger picture. You need to
[00:13:04] understand your goals and what's needed
[00:13:06] to direct AI to start working for you.
[00:13:08] Now, if you like this video, you will
[00:13:09] love this one where I do a deep dive
[00:13:11] into four Claude projects that you need
[00:13:13] to build today using these three layers.
[00:13:16] I'll see you over there. Peace.
