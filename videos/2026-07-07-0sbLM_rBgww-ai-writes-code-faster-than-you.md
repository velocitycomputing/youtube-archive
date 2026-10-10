---
video_id: 0sbLM_rBgww
title: AI Writes Code Faster Than You. Now What?
channel: ArjanCodes
url: "https://www.youtube.com/watch?v=0sbLM_rBgww"
watched_date: 2026-07-07
watched_at: "2026-07-07T12:00:00Z"
watch_count: 1
duration_seconds: 1099
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 23
watched_at_precision: date-from-history-label
watched_percent: 19
estimated_watched_seconds: 209
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker argues that while AI generates code faster than humans, coding itself is not the hard part of software engineering. He draws parallels to doing demolition work on his house himself—the deeper understanding gained proves more valuable than outsourcing. The real challenges in software development are understanding the actual problem being solved, making sound design trade-offs, and thinking about systems holistically. He identifies five critical non-coding skills: (1) deeply understanding the real problem and domain through good questions, (2) knowing software design fundamentals to evaluate AI-generated code, (3) making intentional trade-offs based on constraints and goals, (4) communicating effectively with stakeholders and teams, and (5) systems thinking around dependencies, observability, and failure modes. The talk challenges the notion that AI makes these skills less important—it makes them *more* important because developers must now judge, validate, and integrate generated code rather than just writing it.

For a developer to stay relevant, focus on mastering the non-coding skills: invest time understanding the actual problem before building, ask clarifying questions that expose hidden assumptions, read and evaluate AI-generated code against architectural principles rather than accepting it blindly, and spend time understanding how code behaves in production systems (error handling, monitoring, integration). Use AI as a rapid prototyping tool to explore design approaches, but maintain involvement in the codebase—debugging, tracing, and modifying code deepens understanding. In team settings, improve your communication around trade-offs and technical decisions so stakeholders understand why something takes time or requires complexity. Build systems thinking by considering observability, failure modes, and the infrastructure surrounding features, not just the features themselves.

## Transcript

[00:00:00] A couple of weeks ago, I posted a video
[00:00:01] saying I was done with the AI hype. Many
[00:00:04] of you commented on that video and
[00:00:06] shared your thoughts, which I thought
[00:00:07] was really interesting to read. So,
[00:00:10] thank you so much for that. Uh by the
[00:00:12] way, you might also wonder uh I have
[00:00:14] like a bunch of uh scratches on my arms,
[00:00:16] why that is. It's It's not because I
[00:00:18] received so much hate from that AI hype
[00:00:21] video. It was not that bad, actually.
[00:00:24] No, in fact uh I bought a house a while
[00:00:27] back, like 4 months ago or something.
[00:00:30] And it's kind of a project. So, it's an
[00:00:32] old office building and there's like I
[00:00:35] don't know how many Ethernet cables and
[00:00:37] electricity from 100 years ago, three
[00:00:40] levels of ceilings that all need to be
[00:00:43] removed. So, I'm
[00:00:45] at the moment I'm actually doing uh
[00:00:47] demolition on that house. It's a kind of
[00:00:49] uh physically intense, and that's why I
[00:00:52] have these uh battle scars. I'm proud of
[00:00:54] them. Now, you might say, "Hey, Aryan,
[00:00:56] aren't you some fancy YouTuber? You can
[00:00:58] pay a contractor to do that for you. You
[00:01:00] don't have to do it yourself, right?"
[00:01:02] Well, A, I like uh destroying things, so
[00:01:05] I actually like doing this myself. But,
[00:01:08] B, the interesting thing about doing
[00:01:11] demolishing work in your house yourself
[00:01:14] is that it leads to a deeper
[00:01:16] understanding of how the house works and
[00:01:18] how the installations work, why certain
[00:01:21] uh things have been done in a certain
[00:01:23] way. And by understanding it deeper, you
[00:01:26] end up with better solutions for what
[00:01:30] comes after. So, because you understand
[00:01:32] the house well, you can better design
[00:01:33] like how you're going to
[00:01:35] uh construct it later on. And there's a
[00:01:38] surprising link with coding and AI and
[00:01:42] that
[00:01:43] I think it's really pays off as a
[00:01:45] developer to stay involved in the
[00:01:47] process and understanding the process
[00:01:50] deeper instead of just letting AI
[00:01:51] generate a bunch of code without ever
[00:01:53] looking at it. If you more deeply
[00:01:56] understand it, you're going to end up
[00:01:58] with a better system at the end. So, you
[00:02:02] know, while I'm hacking away with my
[00:02:04] hammer in the houses what I was thinking
[00:02:07] about. I thought the the link was really
[00:02:09] interesting. I wanted to share that with
[00:02:10] you. I'll come back to it later, by the
[00:02:12] way, because well, one thing I said in
[00:02:14] that video was that well, you know,
[00:02:17] actually writing code part is just a
[00:02:19] small part of what developers actually
[00:02:22] do. And that, of course, raises an
[00:02:24] important question. What do developers
[00:02:26] actually do? And if AI writes most of
[00:02:29] the code, then what skills do actually
[00:02:33] still matter? What should you focus on?
[00:02:35] So, that's what I'm going to cover
[00:02:36] today. Five non-coding skills that I
[00:02:39] think you should focus on if you want to
[00:02:42] stay relevant as software engineer. And
[00:02:45] ironically,
[00:02:46] AI makes these skills even more
[00:02:48] important than they already are. The
[00:02:51] main point of the video that I posted a
[00:02:52] couple of weeks ago is that well, coding
[00:02:55] is actually never really the hard part.
[00:02:57] And it's something that typically junior
[00:02:59] developers think that software
[00:03:00] engineering is mainly just writing a
[00:03:02] bunch of code, syntax, frameworks, APIs.
[00:03:06] But if you work on real systems for a
[00:03:08] couple of years, you quickly realize
[00:03:10] that the hard part is not typing the
[00:03:14] code. Yeah, the hard part is figuring
[00:03:16] out what code should you actually write
[00:03:19] and how everything should be connected
[00:03:20] and what are the concepts that are
[00:03:22] involved. The bugs in systems that often
[00:03:25] not syntax mistakes, even though in
[00:03:27] Python that is technically possible.
[00:03:29] Um,
[00:03:30] field projects, they're not caused by
[00:03:32] missing semicolon or something. They
[00:03:34] fail because well, requirements were
[00:03:37] unclear in the beginning, you made some
[00:03:38] wrong assumptions, uh, you introduced
[00:03:41] complexity too early into a system and
[00:03:43] that breaks a lot of other things. Or
[00:03:45] overall, the development team just made
[00:03:48] poor design trade-offs. Maybe overly
[00:03:51] focusing on improving performance where
[00:03:53] actually the main issue was keeping
[00:03:55] things simple in your system. Now, like
[00:03:57] I said, AI is getting very good at
[00:04:00] generating local solutions, but we do
[00:04:03] live in a pretty messy reality. And as
[00:04:06] software engineers, it means that we are
[00:04:08] the ones that need to deal with it. And
[00:04:10] that's also the first and most important
[00:04:12] skill in that you need to be able to
[00:04:14] understand the real problem that you're
[00:04:17] solving. This is a huge part of software
[00:04:20] development, just figuring out what
[00:04:21] people actually need. You don't get that
[00:04:23] answer if you just launch 500 agents
[00:04:26] that write features 24 hours a day. What
[00:04:30] you need to do is you need to talk with
[00:04:31] people and understand what they actually
[00:04:33] want. And if you do that, well, often
[00:04:36] your customers, stakeholders, they're
[00:04:38] going to describe solutions instead of
[00:04:40] the problems that they actually have.
[00:04:41] Maybe they say something like, "Hey, we
[00:04:44] need a dashboard for this."
[00:04:46] But actually, maybe they don't need a
[00:04:48] dashboard at all. They just need a way
[00:04:50] to visualize what went wrong in the
[00:04:53] company. It doesn't have to be a
[00:04:54] dashboard. It can be something else.
[00:04:56] And that means that if you want to be a
[00:04:58] great developer, you need to be able to
[00:05:00] ask good questions.
[00:05:02] You should ask questions that clarify
[00:05:05] constraints,
[00:05:06] what the goals are, what do people want
[00:05:08] to achieve with something without
[00:05:10] thinking about the technical details
[00:05:12] yet. What are some of the edge cases
[00:05:15] that you need to think about? Are these
[00:05:17] cases that potentially break the entire
[00:05:20] system? Or do we need to reformulate
[00:05:24] concepts and relationships so that less
[00:05:26] edge cases occur and that it's cleaner
[00:05:28] and simpler?
[00:05:30] Well, what are some of the hidden
[00:05:31] assumptions that people make about
[00:05:34] things? For example, at Iron Code, we
[00:05:36] were working on how to deal with
[00:05:38] payments in different currencies for my
[00:05:40] new course program. And initially, we
[00:05:44] were thinking about, "Okay, so we need
[00:05:46] to do currency conversion because well,
[00:05:48] I'm in the Netherlands so we have euros
[00:05:50] but people maybe want to pay in dollars
[00:05:52] or any other type of currency. So, we
[00:05:55] need a currency conversion API. So,
[00:05:58] which one should we use and how do we
[00:06:00] make sure it's done automatically so we
[00:06:02] can design some automations that are run
[00:06:04] like daily or hourly or something and
[00:06:07] then integrate it with the invoicing
[00:06:08] system. So, we were thinking about all
[00:06:10] of these things and thinking through but
[00:06:12] then we found out that oh, actually
[00:06:15] currency conversion happens behind the
[00:06:18] scenes during the payment process. It's
[00:06:20] basically completely hidden for us. So,
[00:06:23] there's no need for us to do that work
[00:06:25] at all. I like those kind of
[00:06:27] realizations because it just means that
[00:06:28] hey, I just made up a problem and
[00:06:30] actually it's not a problem at all. I
[00:06:32] don't need to do anything. But, the only
[00:06:34] way you're going to get to that
[00:06:36] conclusion
[00:06:38] is by better understanding the problem
[00:06:40] that you're trying to solve.
[00:06:41] And by doing that, we avoided doing a
[00:06:43] lot of work.
[00:06:45] Uh, it's much better to do that than use
[00:06:47] a bunch of AI tokens to generate an
[00:06:49] implementation that we actually didn't
[00:06:51] need. But, the only way we could get
[00:06:53] there is by having ourselves a deep
[00:06:55] understanding of the domain of the
[00:06:58] problem that we're trying to solve. So,
[00:07:00] that's a really important skill, being
[00:07:02] able to gain a deep understanding on a
[00:07:05] particular topic. The second skill that
[00:07:07] I think is really important is knowing
[00:07:09] the fundamentals.
[00:07:11] AI makes fundamentals more important,
[00:07:14] not less. If AI generates a bunch of
[00:07:17] code for you, you need to evaluate
[00:07:19] whether the solution is actually good.
[00:07:22] And in order to do that, well, you need
[00:07:24] to understand software design,
[00:07:26] architecture, coupling, cohesion,
[00:07:29] testing, trade-offs, why certain design
[00:07:32] fail over time. Basically all of the
[00:07:34] stuff that I talk on my channel about.
[00:07:37] If you don't do those things, then well,
[00:07:38] you're going to become completely
[00:07:40] dependent on generated code that you
[00:07:42] don't fully understand. And that becomes
[00:07:45] dangerous very quickly. I mean, we've
[00:07:47] already seen plenty examples in the news
[00:07:49] where uh development team used AI,
[00:07:52] didn't check the code, and it seriously
[00:07:54] breaks software, cost the company
[00:07:56] millions because well, nobody bothered
[00:07:58] to check. AI generates plausible code.
[00:08:02] It uses data to generate code that is
[00:08:05] similar to that data.
[00:08:07] And that's not the same as well-designed
[00:08:10] code. In my opinion, the best developers
[00:08:12] guide AI effectively because they
[00:08:14] understand the underlying principles,
[00:08:17] the underlying fundamentals really well.
[00:08:20] In my opinion, this understanding gives
[00:08:21] you a huge advantage over other
[00:08:23] developers, especially now that AI can
[00:08:25] generate code so easily. Now, if you
[00:08:27] want to go deeper into architecture,
[00:08:30] design patterns, trade-offs, how to
[00:08:32] think like a software designer instead
[00:08:34] of just a coder, check out my software
[00:08:37] design mastery program. This is designed
[00:08:39] to help you build real engineering
[00:08:41] judgment, not just learn design
[00:08:44] patterns. You can learn more at
[00:08:46] arne.codes/mastery.
[00:08:48] The link is in the video description.
[00:08:51] The third skill that's really important
[00:08:53] is to be able to make trade-offs.
[00:08:56] A lot of software design is about
[00:08:58] trade-offs. We're trading simplicity for
[00:09:02] flexibility.
[00:09:04] We're trading performance for
[00:09:06] maintainability.
[00:09:08] If you use AI to generate code, this is
[00:09:10] going to give you a solution to the
[00:09:12] problem.
[00:09:13] Uh but it doesn't really understand what
[00:09:16] your deadlines are, what your company
[00:09:18] culture is, what your budget is, what
[00:09:20] other constraints you may have. It means
[00:09:23] that you not only need to generate a
[00:09:26] bunch of code, you actually need to
[00:09:28] judge it. So, you need to know what the
[00:09:30] trade-offs are that are involved in that
[00:09:33] code. And that's one of the most
[00:09:34] valuable skills in software engineering,
[00:09:37] knowing what the trade-offs are in
[00:09:39] designing based on that. I made many
[00:09:41] mistakes with that myself in the past.
[00:09:44] For example, when I was developing a
[00:09:46] tool for university education, I built
[00:09:49] an analytic system for teachers to track
[00:09:52] student results.
[00:09:53] That's reasonable, right? But there's
[00:09:55] like a million ways, of course, that you
[00:09:56] can build an analytic system. And I
[00:09:58] thought I was being a smarty-pants by
[00:10:01] making it really generic. Uh you could
[00:10:03] literally write a piece of Python code
[00:10:06] as a user, let that run in the back end,
[00:10:09] and then generate the analytic user
[00:10:11] interface. So, really generic.
[00:10:14] Um but also very hard to use because now
[00:10:18] if you wanted analytics, well, you
[00:10:19] basically needed to know Python. It was
[00:10:21] also a bit scary to let users run random
[00:10:23] code in your back end. So, we relatively
[00:10:26] quickly backtracked that and went to a
[00:10:29] much simpler approach because we found
[00:10:31] out, well, actually most users just
[00:10:33] wanted the basic charts with the student
[00:10:36] results.
[00:10:37] Over-engineered crap. I was really good
[00:10:40] at that in the past. But that is exactly
[00:10:42] the kind of trade-off that you need to
[00:10:44] think about, right? Do you Do you want
[00:10:46] this very generic solution if your users
[00:10:49] don't need it because it also introduces
[00:10:51] a lot of problems. And that's why
[00:10:53] judgment is such an important skill. AI
[00:10:56] is not going to judge you. It's not
[00:10:57] going to decide that for you. You You
[00:10:59] basically going to tell AI what it needs
[00:11:02] to build, and it's just going to build
[00:11:03] it without really thinking about whether
[00:11:06] [clears throat] your users actually want
[00:11:07] that. And related to that
[00:11:10] is the fourth skill, which is
[00:11:11] communication.
[00:11:12] I think it's something that most
[00:11:15] developers underestimate.
[00:11:17] But if you look at software engineering,
[00:11:19] it's in essence
[00:11:21] collaborative problem-solving in most
[00:11:23] cases. It rarely happens that you are
[00:11:25] completely isolated in your room working
[00:11:28] in a silo just producing this thing on
[00:11:31] your own. You're doing it for other
[00:11:33] people. Those other people are going to
[00:11:35] have feedback and they're going to want
[00:11:37] to use your system in a certain way.
[00:11:39] They're going to have certain
[00:11:40] expectations and assumptions. So, you
[00:11:43] need to be able to listen to that and
[00:11:45] adapt your software to what people
[00:11:47] actually want. At the same time, if you
[00:11:49] work in a team or you have managers,
[00:11:51] well, you know, if you have some idea,
[00:11:53] some technical idea, you need to be able
[00:11:55] to explain that clearly so that the
[00:11:57] manager understands what you actually
[00:11:58] want. Your colleagues are going to write
[00:12:00] code. That needs to fit in with the rest
[00:12:03] of what the team does. So, you need to
[00:12:04] be able to review code and
[00:12:07] examine whether that is really a good
[00:12:10] fit for the system. If you work with
[00:12:12] multiple developers in a team, well,
[00:12:14] you're going to have meetings to align
[00:12:16] in which, well, you are going to need to
[00:12:17] communicate. You need to document
[00:12:20] decisions so that in the future, if you
[00:12:23] want to look back at what you did and
[00:12:25] make a change, so you know exactly what
[00:12:27] was decided when. You also need to
[00:12:29] discuss these tradeoffs that I mentioned
[00:12:31] [snorts]
[00:12:32] earlier with non-technical
[00:12:34] [clears throat] people because your
[00:12:36] client, your customer, needs to
[00:12:38] understand if you're building something,
[00:12:40] why you're doing that in a particular
[00:12:42] way. Why is this thing so complicated
[00:12:45] and why does it take so much time to
[00:12:46] develop? Well, because, you know, you
[00:12:49] need to do it in a way that is scalable.
[00:12:51] So, you're making a tradeoff. I'm
[00:12:53] spending more time now so that it's more
[00:12:54] scalable in the future. That means
[00:12:57] communicating about these things. This
[00:12:59] is what separates a mediocre engineer
[00:13:01] from a really brilliant one because if
[00:13:04] you're a great communicator, you can
[00:13:06] better show what your value is. You can
[00:13:08] more easily understand what somebody
[00:13:10] wants. Clarity reduces mistakes. It just
[00:13:13] means you're less likely to go on some
[00:13:16] useless side quest that the client
[00:13:18] doesn't approve of. The fifth skill that
[00:13:20] is incredibly important is system
[00:13:22] thinking. Great developers think in
[00:13:26] systems.
[00:13:27] They understand things like
[00:13:29] dependencies, deployments,
[00:13:31] observability, scalability, failure
[00:13:34] modes,
[00:13:36] managing complexity of a particular
[00:13:38] system. Just generating a bunch of code
[00:13:41] is easy, but understanding how that
[00:13:43] behaves in a large production system
[00:13:45] that already exists is much harder,
[00:13:48] especially when things fail. That always
[00:13:50] happens. This skill often translates
[00:13:53] into you spending a bit more time
[00:13:55] on the systems surrounding your
[00:13:57] software. For example, at Iron Codes
[00:13:59] when we book invoices in our accounting
[00:14:02] software, well, lots of things can go
[00:14:04] wrong. There can be wrong VAT IDs, there
[00:14:07] may be a wrong country, or address might
[00:14:10] be weird, or we can't find some company
[00:14:13] ID in the database, or there's plenty of
[00:14:16] stuff that can go wrong, and that does
[00:14:18] go wrong, by the way. So, we spend quite
[00:14:21] some time to write proper error
[00:14:24] reporting code, which in our case is
[00:14:26] linked to Microsoft Teams. So, when
[00:14:28] something goes wrong, we get a message
[00:14:30] that contains all the details we need,
[00:14:32] including clickable links, so we can
[00:14:35] quickly see what the problem is and
[00:14:37] solve it. And having this, even though
[00:14:39] it's not a direct feature of our our
[00:14:43] internal software, it makes a massive
[00:14:45] difference. It means overall our systems
[00:14:47] are easier to work on because we have
[00:14:49] this. But you'll only do this if you
[00:14:51] think about the system holistically, not
[00:14:53] just about building the feature that
[00:14:55] works for your clients. Right, there's a
[00:14:57] lot that surrounds it, that's part of
[00:14:59] the system, and you need to take that
[00:15:01] into account. Now, even though I said
[00:15:03] I'm done with AI hype, I just want to
[00:15:05] stress that I'm not against using AI. I
[00:15:08] think it changes software development in
[00:15:10] a few important ways, and also in
[00:15:13] positive ways. For example, before AI,
[00:15:16] trying out five different approaches to
[00:15:19] something could take a a time because
[00:15:20] you have to write like a bunch of code
[00:15:22] for that. But what I really enjoy about
[00:15:24] using AI
[00:15:25] is that you can explore ideas very
[00:15:27] quickly.
[00:15:28] You can easily generate a couple of
[00:15:31] prototypes. Uh you can compare a few
[00:15:33] architectures, simulate the different
[00:15:35] workflows.
[00:15:36] Overall, you can validate assumptions
[00:15:39] much faster. Uh in a sense, the code
[00:15:42] becomes part of your thinking process.
[00:15:45] And this is incredibly valuable for
[00:15:47] understanding a domain. You know,
[00:15:48] sometimes you don't fully understand a
[00:15:52] problem until you try building
[00:15:54] something. To go back to what I said in
[00:15:57] the beginning of this video
[00:15:58] is that just like with working on a
[00:16:00] house, you need to be there. You need to
[00:16:03] break a couple of things,
[00:16:05] move around a couple of things, and try
[00:16:07] a couple of things. Hey, what what
[00:16:09] happens if I disconnect this pipe, you
[00:16:11] know? And by doing that, you build a
[00:16:13] stronger, a much deeper understanding of
[00:16:16] the domain. And with building software,
[00:16:19] it's very similar. AI makes writing code
[00:16:21] very fast, but you still need to decide
[00:16:23] which direction makes sense, which
[00:16:26] trade-offs are important, and which
[00:16:28] solution is actually good. Uncle Bob
[00:16:30] said that as well. Most professional
[00:16:32] developers spend more time reading code
[00:16:35] than writing it. And that's still true
[00:16:37] with AI writing more of the code.
[00:16:39] There's just a lot more reading to do.
[00:16:41] Debugging, tracing failures,
[00:16:42] understanding how to modify a legacy
[00:16:45] system, how to integrate new feature.
[00:16:47] Uh for example, I'm currently working on
[00:16:49] dashboards uh for brands who want to do
[00:16:52] content marketing with creators. It's
[00:16:54] kind of a side project next to RM codes.
[00:16:57] Um
[00:16:58] and we generate a lot of the code with
[00:16:59] AI, obviously, but we also spend a lot
[00:17:01] of time reading and interacting and
[00:17:03] understanding the code. You need to
[00:17:05] validate correctness, security, very
[00:17:09] important, maintainability, uh whether
[00:17:11] it fits with the rest of your ideas. And
[00:17:13] by the way, if you enjoy my videos, give
[00:17:15] this one a like and subscribe to the
[00:17:17] channel. It helps me out a lot. I think
[00:17:20] AI will make great developers even more
[00:17:23] valuable, but you do need to focus on
[00:17:26] the right skills.
[00:17:28] Being able to deeply understand the real
[00:17:30] problem in a domain.
[00:17:32] Knowing the design and architectural
[00:17:34] fundamentals.
[00:17:36] Being able to make design trade-offs,
[00:17:38] and understand where the trade-offs are
[00:17:40] in the code that you write.
[00:17:42] Communication.
[00:17:43] Understanding what people want, and
[00:17:45] explaining to people what you want to
[00:17:46] do. And finally, systems thinking. Being
[00:17:49] able to look at a software system as a
[00:17:52] whole, and not just as a loose
[00:17:54] collection of features, or project that
[00:17:56] you need to finish. In my opinion, if
[00:17:59] you focus on those skills, there's
[00:18:01] always going to be a place in the market
[00:18:03] for you.
[00:18:04] But, I'd like to hear what you think. Do
[00:18:06] you agree with this?
[00:18:08] What skill do you focus on to grow in
[00:18:10] your career?
[00:18:11] Let me know in the comments. Now,
[00:18:13] YouTube thinks you might like this video
[00:18:15] next. Thanks for watching, and see you
[00:18:18] next time.
