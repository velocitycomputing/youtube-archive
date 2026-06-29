---
video_id: 9PUaEj0pMYE
title: The Skill vs Prompt Problem Everyone Gets Wrong
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=9PUaEj0pMYE"
watched_date: 2026-06-19
watched_at: "2026-06-19T12:00:00Z"
watch_count: 1
duration_seconds: 1065
source: youtube-history-browser
added_date: 
history_label: Jun 19
history_order: 126
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1065
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video presents Open Skills, a response to "procedural debt"—the problem that even when AI agents have access to your context and memory, they still don't know *how you work*. The speaker identifies four friction points: prompt bloat (stuffing every rule into giant system prompts), reexplanation tax (redescribing your voice/testing standards in each new agent), instruction fragmentation (scattered rules across tools), and weak verification (automation turning into review work). Open Skills solves this by packaging procedures as portable, composable, verifiable markdown files with defined triggers, boundaries, outputs, and proof standards. Skills are primitives; runbooks combine them into workflows. The key differentiation is scope—personal skills (voice, habits) live globally; project skills (repo rules) live locally—preventing both prompt bloat and team instruction drift.

To use this: stop maintaining separate instruction sets per tool (Cursor, Claude Code, etc.) and instead build a reusable skill library. Document any recurring procedure that survives a session as a skill candidate rather than letting it disappear into chat history. For one-off tasks, use prompts; for patterns you repeat, author a skill that specifies when to trigger it, which tools it needs, what success looks like, and what proof is required. This lets you carry procedures between jobs and AI tools without vendor lock-in, composing them into larger workflows as your work evolves.

## Transcript

[00:00:00] A lot of us have an AI agent with a
[00:00:02] brain now. It still probably doesn't
[00:00:04] know how to work as well as it should.
[00:00:05] So, a few weeks ago, I made a video
[00:00:07] called Open Brain. The argument was
[00:00:09] simple. Agents are becoming real, and if
[00:00:11] they're going to do useful work for you,
[00:00:12] they need access to your context in a
[00:00:14] way that works for you. They need to
[00:00:16] know what you're working on. They need
[00:00:17] to know what you decided last week. They
[00:00:19] need to know who the important people
[00:00:21] are. They need to know what you already
[00:00:23] tried. and they need memory that's not
[00:00:25] trapped inside one app, one SAS product,
[00:00:28] one model provider, one brain for every
[00:00:31] AI. And that video struck a chord
[00:00:32] because it named a bottleneck that we
[00:00:34] were all feeling, right? Every serious
[00:00:36] AI workflow still started with the same
[00:00:39] miserable ritual. Let me reexplain my
[00:00:41] life to this machine again. But there is
[00:00:44] a second problem that shows up as soon
[00:00:46] as you solve the memory problem. And
[00:00:48] I've seen it enough that I want to talk
[00:00:50] about it here and talk about how I'm
[00:00:51] solving it. Even if the agent knows what
[00:00:53] you know, it may still not know how you
[00:00:56] work. It may know the project. It may
[00:00:58] know the people. It may know the
[00:01:00] decision history thanks to open brain.
[00:01:02] And then you still have to explain the
[00:01:04] procedure from scratch. And you still
[00:01:05] have to say when you research this,
[00:01:07] don't trust stale model memory. You
[00:01:09] still have to say when you write for me,
[00:01:10] don't sound like a generic AI
[00:01:12] newsletter. You still have to say when
[00:01:14] you test this page, actually open the
[00:01:16] browser and check mobile and capture
[00:01:17] evidence and don't just tell me it looks
[00:01:20] good. You still have to say when you
[00:01:22] publish something, verify the live
[00:01:24] result. All of these things you have to
[00:01:26] reexlain and that is not a memory
[00:01:28] problem. You can have a perfect open
[00:01:30] brain setup and it still works that way.
[00:01:32] It's a procedure problem. And people
[00:01:34] using agents seriously are starting to
[00:01:36] feel it as a procedural debt. And you
[00:01:38] can see this in at least four different
[00:01:40] places across serious workers workflows.
[00:01:43] First in prompt bloat. People keep
[00:01:45] stuffing more rules into giant system
[00:01:48] prompts or markdown files and then
[00:01:50] wondering why the agent gets worse. And
[00:01:52] it's because every preference and edge
[00:01:54] case and repo note and safety reminder
[00:01:56] and formatting and structure fights the
[00:01:58] others for attention. At some point that
[00:02:00] stops being clarity and it just adds
[00:02:02] weight. Second, the reexlanation tax.
[00:02:05] Every new chat, every fresh agent
[00:02:07] session, every switch from cursor to
[00:02:09] claude code to codeex means you have to
[00:02:11] explain your voice and your testing
[00:02:13] standard and your project patterns and
[00:02:14] your safe commands and your definition
[00:02:16] of done all over again. That's not work.
[00:02:19] That's setup work pretending to be work.
[00:02:21] Third, instruction fragmentation. You
[00:02:23] end up with one set of rules in one
[00:02:25] tool, another set in another tool, repo
[00:02:27] specific nodes somewhere else, and
[00:02:28] custom instructions that slowly drift
[00:02:30] away from each other. Fourth, weak
[00:02:32] verification turns automation into a
[00:02:35] pile of review debt for you and me
[00:02:37] because the agent will say done, but the
[00:02:38] source is stale and the link is broken
[00:02:40] and the mobile view is bad or the change
[00:02:42] was never tested. So, the human still
[00:02:44] has to inspect so much. The agent didn't
[00:02:46] remove the work in some cases, it just
[00:02:48] moved the work into the review stage.
[00:02:50] This is the problem space open skills is
[00:02:52] built for and I'm launching it today.
[00:02:54] It's not that prompts are annoying. It's
[00:02:56] that agent work is developing procedural
[00:02:58] debt at exactly the moment agents are
[00:03:01] becoming capable of persistent action.
[00:03:03] Take a small product team at a startup
[00:03:05] that ships with both cursor and claude
[00:03:07] code on the same codebase. Let's say
[00:03:08] they spent weeks tuning a solid set of
[00:03:10] cursor rules, security boundaries,
[00:03:12] window to write tests, get workflow
[00:03:14] expectations, how to handle large
[00:03:15] refactors in the project's architectural
[00:03:18] patterns, and it worked really well
[00:03:19] inside cursor. Then they started using
[00:03:21] clawed code for bigger multifile changes
[00:03:24] and the rules didn't travel very
[00:03:25] cleanly. So one engineer ended up
[00:03:27] maintaining two versions of the same
[00:03:28] guidance. One in cursor rules and
[00:03:30] another in a claw.markdown file. Over
[00:03:33] time those files tended to drift. One
[00:03:35] got updated with a new testing rule
[00:03:37] after a painful incident. The other
[00:03:39] still said the old thing. And then a
[00:03:40] contractor joined the project and got
[00:03:42] handed a long onboarding prompt that
[00:03:44] tried to summarize both files. and it
[00:03:46] sounded comprehensive, but it was vague
[00:03:48] on the details that actually prevented
[00:03:50] bad deaths. The team is not short on
[00:03:52] intelligence in this situation, and
[00:03:54] they're not short on context. They're
[00:03:56] short on a portable way to carry the
[00:03:58] procedure itself. That is the gap Open
[00:04:00] Skills is designed to close. It's a gap
[00:04:02] in a multimodel world. That's what this
[00:04:04] video is about. It's not a prompt trick.
[00:04:06] It's not a list of clever AI hacks. It's
[00:04:08] not another folder of reusable wording.
[00:04:11] Open Skills is a public library of
[00:04:13] reusable agent procedures. The current
[00:04:15] version has 31 skills in seven
[00:04:17] categories and seven runbooks. Each
[00:04:19] skill comes with a copype setup prompt
[00:04:21] and the pattern is designed to work
[00:04:22] across codecs, claude code, and any
[00:04:25] other agent harness that can load a
[00:04:26] skill.mmarkdown style convention. And I
[00:04:29] want to be precise about differentiation
[00:04:31] here because this is not happening in a
[00:04:32] vacuum. A lot of the agent world is
[00:04:34] moving toward modular instructions.
[00:04:36] Individual tools have their own rule
[00:04:38] systems. Coding agents have their own
[00:04:39] markdown files. People are sharing tool
[00:04:41] specific skills and cursor rules and
[00:04:43] agent instructions. and those SIG
[00:04:45] scripts that keep those files from
[00:04:46] drifting. That is all the right
[00:04:48] direction. But open skills is making a
[00:04:50] more specific bet. The differentiated
[00:04:52] piece here is not skills exist. You can
[00:04:54] find skills. The differentiated piece is
[00:04:57] portable procedures as an operating
[00:05:00] layer. One markdown source of truth,
[00:05:02] narrow skills as primitives, run books
[00:05:04] as compositions, and verification as
[00:05:07] part of the contract, personal scope
[00:05:09] when the procedure belongs to you, and
[00:05:10] project scope when the procedure belongs
[00:05:12] to the repo. and a flywheel that turns
[00:05:14] repeated work into reusable skill
[00:05:16] candidates instead of letting the
[00:05:18] pattern disappear into old chat history.
[00:05:20] So if open skills becomes just another
[00:05:22] list of useful prompts, I failed. It
[00:05:25] blends into everything else. That's not
[00:05:26] what this is. But if it stays focused on
[00:05:28] portability and composition and
[00:05:30] verification and scope and compounding,
[00:05:33] it's a different layer. It's a needed
[00:05:35] layer. So what is a skill? Right? A
[00:05:37] skill is usually a small folder with a
[00:05:39] skill.mmarkdown file inside it. That's
[00:05:40] the simple version. The file tells the
[00:05:42] agent when to use the skill, when not to
[00:05:44] use the skill, what job the skill owns,
[00:05:46] what tools or files it should use, what
[00:05:48] boundaries apply, what output should
[00:05:49] look like, and how to verify the
[00:05:51] results. That's the unit, not a clever
[00:05:53] paragraph, not a vibe, not a one time
[00:05:54] chat, not a prompt. A reusable procedure
[00:05:56] an agent can load when the situation
[00:05:59] calls for it. A prompt is something you
[00:06:01] say once. And a skill is something your
[00:06:02] agent knows how to do from now on. If I
[00:06:04] give an agent a prompt that says, "Fact
[00:06:06] check this article," that's a request.
[00:06:08] If I give an agent a current information
[00:06:09] search skill, that's a procedure. It can
[00:06:12] say use live search when the claim is
[00:06:13] recent, when pricing might have changed
[00:06:14] and a software version matters or when
[00:06:16] training data might be stale. It can say
[00:06:18] compare sources and show the data.
[00:06:19] Separate consumed facts from inferred.
[00:06:21] If I give an agent a current information
[00:06:23] search skill, that's a procedure. It can
[00:06:25] say use live search when the claim is
[00:06:27] recent, when pricing might have changed,
[00:06:28] when the software version matters, or
[00:06:30] when training data might be stale. It
[00:06:32] can say compare sources and show the
[00:06:33] date and separate confirmed facts from
[00:06:35] inference and let uncertainty block
[00:06:37] publishing if needed. Same thing with
[00:06:39] voice. If I say write this in my voice,
[00:06:41] the model has to guess. If I have a
[00:06:43] personal voice skill, it can tell the
[00:06:45] agent which real samples to read, which
[00:06:47] phrases to avoid, how long the sentences
[00:06:49] are, what argument structure works, and
[00:06:51] what fake AI language ought to be
[00:06:52] stripped out. Same thing with testing.
[00:06:54] If I say test the page, the agent may
[00:06:56] tell me it looks fine. If I have a
[00:06:57] browser QA skill, it can say open the
[00:07:00] actual route. Check the console. Check
[00:07:02] mobile. Verify the changed workflow.
[00:07:03] Capture screenshots and report the
[00:07:05] evidence. The procedure is the valuable
[00:07:07] part. That's the thing to take away from
[00:07:08] these three. The words are not enough.
[00:07:11] This is the same structural mismatch I
[00:07:14] talked about in the open brain video,
[00:07:16] but one level higher. OpenBrain said
[00:07:18] most secondbrain tools were built for
[00:07:20] human readers. That was true. They were
[00:07:22] useful, but they were not designed as
[00:07:24] agent readable memory infrastructure.
[00:07:26] Open Skills says most SOPs and prompts
[00:07:28] and checklists and docs and preferences
[00:07:30] have the same problem. They may be
[00:07:33] readable by a person, but they're not
[00:07:35] packaged as agent operable procedures.
[00:07:37] They don't have trigger rules. They
[00:07:39] don't say when not to run. They don't
[00:07:41] identify required tools. They don't
[00:07:42] define the output. They don't define the
[00:07:44] verification. And they don't travel
[00:07:46] cleanly from one agent harness to
[00:07:48] another. This is why the current world
[00:07:51] feels so painfully repetitive, so copy
[00:07:54] and paste. You have five AI tools and
[00:07:57] five separate piles of procedural sticky
[00:07:59] notes. One tool knows a little about how
[00:08:01] you write, another has a project
[00:08:02] instruction, another has repo rules,
[00:08:04] another has a custom instruction box,
[00:08:06] and another one has a chat history where
[00:08:08] you explained everything perfectly and
[00:08:09] you can never find it again. That is not
[00:08:12] a working system. That is just
[00:08:14] procedural sprawl. The answer is not a
[00:08:16] giant magical instruction block that
[00:08:19] says, "Be my perfect employee." That
[00:08:21] doesn't work. It's too broad. It's too
[00:08:23] vague. It can't be tested. It just isn't
[00:08:25] practical. The better path, the
[00:08:26] practical path is a library of small
[00:08:29] inspectable procedures that can be
[00:08:31] called from anywhere when needed. That's
[00:08:33] the answer to prompt bloat. Don't put
[00:08:36] every rule in the agents head all the
[00:08:37] time. Give it a clean way to load the
[00:08:39] right procedure when the work falls for
[00:08:41] it. And once you have skills that are
[00:08:43] transferable, the next step is runbooks.
[00:08:46] Skills are primitives. Runbooks are
[00:08:48] composition. Both are part of open
[00:08:50] skills. A skill answers, what can this
[00:08:52] agent do? A runbook answers, what can
[00:08:54] the system reliably produce? Take the
[00:08:56] creator workflow. A voice memo becomes a
[00:08:58] published page. That sounds like one
[00:09:00] task, but it's really a chain. Media
[00:09:02] transcription turns the audio into a
[00:09:04] transcript. Brain dump processing
[00:09:06] separates the real ideas from the
[00:09:07] rambling. Personal voice turns the best
[00:09:10] idea into a draft that sounds like the
[00:09:12] person. HTML artifact builder turns the
[00:09:14] draft into a usable page. Personal site
[00:09:16] publisher ships it with the right route
[00:09:18] and the right metadata and the link
[00:09:20] preview and verification. That is a
[00:09:22] runbook. Or take release day. Something
[00:09:24] important ships and you want to publish
[00:09:25] a useful accurate briefing while the
[00:09:27] facts still matter. Current information
[00:09:29] search gathers the facts. New release
[00:09:31] briefing turns those facts into a
[00:09:32] publishable package. Image prompting and
[00:09:35] generation create the visual. site
[00:09:36] publisher ships the page and stakeholder
[00:09:38] update closes the loop when something is
[00:09:40] actually live. That is speed with a
[00:09:42] quality bar. The point is not that one
[00:09:45] giant agent or giant skill knows
[00:09:46] everything. The point is that each skill
[00:09:49] owns a piece and those skills are Lego
[00:09:51] blocks and they're composable. So in
[00:09:53] that world, the transcription skill
[00:09:55] doesn't need to know how to publish,
[00:09:56] right? The voice skill doesn't need to
[00:09:58] know how to test a browser. The
[00:10:00] publisher doesn't need to know how to
[00:10:01] generate visuals. Each skill owns a
[00:10:04] specific contract. The runbook owns the
[00:10:06] flow. That's how real work gets done.
[00:10:08] And this is where the word open matters
[00:10:10] a lot. Open does not mean every skill is
[00:10:12] public by default. Open doesn't mean you
[00:10:15] paste secrets into a shared file. Open
[00:10:17] doesn't even mean every agent should be
[00:10:18] able to do everything. The skill becomes
[00:10:21] the source of truth. Cursor rules and
[00:10:23] clawed files and codeex instructions or
[00:10:25] whatever comes next can read from it or
[00:10:27] be generated from it instead of becoming
[00:10:29] separate drifting copies. Some
[00:10:31] procedures are personal. My voice is
[00:10:33] personal. My publishing habits are
[00:10:34] personal. My standards for a stakeholder
[00:10:36] update are personal. Other procedures
[00:10:39] are project local. The way you test a
[00:10:41] specific app should live with that app.
[00:10:43] The safe commands for one repo should
[00:10:45] not become universal rules for every
[00:10:47] repo. The known selectors and seed data
[00:10:49] and cleanup steps and deployment quirks
[00:10:51] should live where the project lives.
[00:10:53] That is another reason skills are not
[00:10:55] just prompts. They can be placed in the
[00:10:57] right scope, global when the procedure
[00:10:59] belongs to you, local when the procedure
[00:11:01] belongs to the project, and that is how
[00:11:02] you keep the system clean instead of
[00:11:05] turning into a giant pile of preferences
[00:11:06] that are a mixture of yours and the
[00:11:08] teams. The other big thing skills give
[00:11:10] you is verification. This is where the
[00:11:12] agent conversation needs to get much
[00:11:13] more serious. As long as AI was mostly
[00:11:16] writing text, a lot of people tolerated
[00:11:18] vague confidence. Just being honest
[00:11:20] here. But with agents, vague confidence
[00:11:22] is not enough. If the agent edited code,
[00:11:25] what test passed? If I built a page,
[00:11:27] what browser did it open? If it
[00:11:28] published something, what URL did it
[00:11:31] check? If it summarized a source, what
[00:11:33] source did it actually read? If it used
[00:11:34] current facts, what date did it verify?
[00:11:36] A good skill can define that proof ahead
[00:11:39] of time. It can say, "Do not call this
[00:11:41] done unless this evidence exists." That
[00:11:44] one sentence changes a lot because
[00:11:45] agents are very good at producing
[00:11:47] plausible completion language, and
[00:11:48] they're less reliable when the
[00:11:50] definition of done is vague. So, don't
[00:11:52] make it a vibe. put it in the skill.
[00:11:54] That's how you turn automation from
[00:11:56] review debt into leverage. And there's
[00:11:58] one more piece that matters, the
[00:11:59] flywheel. One skill in the library I'm
[00:12:02] launching today is called sessiontoskll
[00:12:04] extractor. The idea is simple, but it's
[00:12:06] very powerful. At the end of a
[00:12:07] substantial agent session, ask, did we
[00:12:10] learn a recurring non-obvious procedure
[00:12:12] worth preserving? Most of the time, the
[00:12:14] answer should be no. And that's part of
[00:12:15] the quality bar. You don't want to turn
[00:12:17] every little preference into a skill.
[00:12:19] But sometimes the answer is yes.
[00:12:20] Sometimes you discover a testing pattern
[00:12:22] or or a publishing checklist or a way to
[00:12:24] process transcripts or a repeatable
[00:12:26] source gathering process. And when that
[00:12:28] happens, the procedure should not
[00:12:30] disappear with that chat into the
[00:12:31] compost pile. It should become a skill
[00:12:33] candidate. That is the same compounding
[00:12:35] logic as open brain, but applied to
[00:12:37] procedures that help you work. Open
[00:12:39] brain compounds because every thought
[00:12:41] you capture makes future retrieval
[00:12:43] better. That's how it works. Open skills
[00:12:46] compounds because every good procedure
[00:12:48] you preserve makes future work more
[00:12:51] reliable. And that's where the leverage
[00:12:53] is now. And the real power is when the
[00:12:55] two systems come together. Open brain
[00:12:57] gives the agent the context, the
[00:12:58] project, the audience, the decisions,
[00:13:00] the prior work, the constraints. Open
[00:13:02] skills gives the agent the procedure,
[00:13:04] how to research, how to write, how to
[00:13:05] build, how to test, how to publish, and
[00:13:07] how to report what changed in a
[00:13:09] multimodel world where you can't be sure
[00:13:12] what model's going to be best next. And
[00:13:14] look at how this changes things for us.
[00:13:16] Right now, we humans are not spending
[00:13:18] the whole session saying, "Here's the
[00:13:20] background. Here's how I like this done.
[00:13:22] We humans can do the real work." And
[00:13:24] that gap, the ability to focus on real
[00:13:27] work, that compounds every week with
[00:13:29] open skills. It compounds every time a
[00:13:31] new model shifts. And you don't have to
[00:13:33] switch and cost yourself so much time.
[00:13:34] It compounds every time you try a new
[00:13:36] agent tool and you can bring open skills
[00:13:38] over because you are less locked into
[00:13:40] the memory and workflow assumptions of
[00:13:42] any one vendor. They don't deserve to
[00:13:44] have that. You do. You can move your
[00:13:46] context. You can move your procedures.
[00:13:47] You can plug better tools into the same
[00:13:50] operating layer. That is what open is
[00:13:52] supposed to mean here. Not vague
[00:13:54] openness, practical portability, your
[00:13:57] thoughts, every AI free for you to use
[00:14:00] your workflows, every agent. That is the
[00:14:02] call back to open brain here. It's the
[00:14:03] same spirit. And that's why open skills
[00:14:05] is not a prompt library. A prompt
[00:14:07] library is way too small for this
[00:14:09] problem. It just doesn't work in 2026 in
[00:14:11] the same way. Open Skills is more like a
[00:14:13] public operating manual for agent work.
[00:14:16] The value of Open Skills is not really
[00:14:18] in the 31 markdown files, although
[00:14:21] they're really good. The value is that
[00:14:23] every single file has a job, a scope, a
[00:14:26] trigger, a boundary, and a proof
[00:14:28] standard. That's what separates open
[00:14:31] skills from the broader wave of skills
[00:14:32] and rules. We need to have and we
[00:14:35] deserve to have skills that are
[00:14:36] transferable with clear runbooks
[00:14:39] associated because this is bigger than
[00:14:41] skills. You can build with these skills
[00:14:44] once and you can recombine them forever
[00:14:46] in any AI you want. That is the heart of
[00:14:49] what open skills is about. Skills don't
[00:14:52] make Asians perfect. Runbooks still
[00:14:54] require human judgment. AI skills are
[00:14:57] not magical autonomy people. But the
[00:14:59] real promise of open skills is still
[00:15:02] incredibly powerful because open skills
[00:15:04] means you don't have to explain the same
[00:15:05] procedure forever. It means you don't
[00:15:07] have to keep your working style in your
[00:15:08] head. You don't have to accept that
[00:15:09] every agent tool has its own separate
[00:15:11] pile of instructions. You can write the
[00:15:14] procedure down in a way an agent can
[00:15:15] load. That's open skills. You can
[00:15:17] inspect it. You can improve it. You can
[00:15:19] put it in the right scope and you can
[00:15:20] compose it into larger workflows and you
[00:15:22] can carry it forward as the tools
[00:15:24] change. That matters. So the decision
[00:15:27] rule is simple. If you do something with
[00:15:29] an agent once, a prompt is fine. If you
[00:15:32] are comfortable living in a world where
[00:15:33] you have to reacquire skills all the
[00:15:35] time and manually remember to set up
[00:15:37] loops to add to your skills as you go
[00:15:40] and then you have skill drift as you
[00:15:42] have codecs and cloud code and cursor in
[00:15:43] the mix, great. More power to you. If
[00:15:46] you want a solution that you can
[00:15:48] control, that's open skills. And that's
[00:15:51] what I'm launching today. If you want
[00:15:52] more information, you can check out the
[00:15:54] URL I'm showing right on the screen
[00:15:56] right now. you'll get all set up to go
[00:15:59] from there. I can't wait to see you
[00:16:00] there. Open brain has been just an
[00:16:03] incredible opportunity for the community
[00:16:05] to collaborate around building a memory
[00:16:07] system that is ours to control, not some
[00:16:09] SAS companies. I want open skills to be
[00:16:12] the same thing. It's a chance for all of
[00:16:14] us to contribute to a building set of
[00:16:18] skills that help us to be in charge of
[00:16:21] our work even as tools evolve and
[00:16:24] change. So we can stay flexible, so we
[00:16:26] can grow, so our skills come with us.
[00:16:28] You know, a few weeks ago I shared the
[00:16:31] reflection that one of the big
[00:16:33] challenges of the AI era is how a
[00:16:35] skilled knowledge worker moves from job
[00:16:38] to job and what they do with their
[00:16:40] skills that they acquire with AI along
[00:16:42] the way. Open skills is that answer.
[00:16:45] Bring your open skills to work and then
[00:16:47] take them with you when you go. Open
[00:16:49] skills help you be more effective across
[00:16:52] any AI tool that your work is going to
[00:16:54] throw at you and across your personal
[00:16:55] tools as well. If you're a company, open
[00:16:58] skills is a way for you and your teams
[00:17:00] to be more productive because we
[00:17:02] anticipate the team level. That's an
[00:17:04] important part of how we build
[00:17:05] meaningful things in the AIH. I do not
[00:17:07] believe the future is just a oneperson
[00:17:09] billion-dollar company. As much as
[00:17:11] that's fun, there will be some of them.
[00:17:12] I think a lot of the future is humans
[00:17:14] building cool things together and open
[00:17:16] skills is a powerful way to do that as
[00:17:18] well. So check out Open Skills. I'm so
[00:17:20] excited for it. I think it solves one of
[00:17:21] the most persistent and painful issues
[00:17:23] I've seen in the skills ecosystem. It
[00:17:26] should not be hard to move your skills
[00:17:28] between different AIs. It should not be
[00:17:31] hard to evolve your skills over time and
[00:17:34] it should not be hard to compose your
[00:17:36] skills into runbooks. Open Skill Solves
[00:17:39] for all of that. Check it out. Have fun
[00:17:41] with it and contribute to the build.
[00:17:43] Let's make it great together. Cheers.
