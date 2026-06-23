---
video_id: ChskqGovoHg
title: "This Open Source Repo Just Solved Claude Code's #1 Problem"
channel: Chase AI
url: "https://www.youtube.com/watch?v=ChskqGovoHg"
watched_date: 2026-06-21
watched_at: "2026-06-21T12:00:00Z"
watch_count: 1
duration_seconds: 804
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 31
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 804
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Graphify is an open-source tool that converts repositories—including code, documentation, PDFs, images, and videos—into a knowledge graph that Claude Code can query instead of searching through files. It works in three passes: first parsing code structure deterministically using tree-sitter to extract classes, functions, imports, and call graphs; second transcribing any audio/video files; and third applying semantic analysis to documents and images. The resulting graph consists of nodes (individual elements), edges (connections), and communities (clusters of similar nodes) that create a map of how everything relates and why. Unlike Graph RAG systems, Graphify uses no embeddings and is specifically optimized for code repositories, delivering 40% token savings in real-world demos while providing equally accurate answers compared to traditional grep-based exploration.

To use Graphify, install it from the GitHub repo (Claude Code can automate this with a simple ask) and run `/graphify .` in your project directory. Once installed, you can query the knowledge graph with `/graphify query` or `/graphify explain` for explicit graph-backed answers, or use `/graphify install` to automatically enable it as a hook that always uses Graphify for answers. The knowledge graph auto-rebuilds after each commit at no cost, works in team environments with parallel contributions, and can even generate Obsidian vaults for non-code repositories using the `--obsidian` flag—giving you a persistent, living map that Claude Code can leverage for cheaper, more accurate responses to any future questions.

## Transcript

[00:00:00] Graphify just solved Claude Code's
[00:00:02] memory problem. It's able to turn any
[00:00:04] repository and turn it into a wild
[00:00:05] knowledge graph just like the one you
[00:00:07] see here. And in the process, it allows
[00:00:10] Claude Code to give you more accurate
[00:00:11] answers at a fraction of the token
[00:00:13] costs. It's able to do this by
[00:00:15] traversing your entire code base,
[00:00:17] mapping all the connections, and
[00:00:18] discerning the why behind the
[00:00:20] connections. And the best part is, it's
[00:00:22] also open source and completely free.
[00:00:24] And so today, I'm going to show you how
[00:00:26] you can get this working yourself and
[00:00:28] what's actually going on under the hood
[00:00:30] so you can start leveraging it right
[00:00:31] away. So Graphify came out a couple
[00:00:33] months ago. It's at nearly 60,000 stars,
[00:00:35] and what it does is it allows your AI
[00:00:38] coding assistant doesn't have to be
[00:00:39] Claude Code, but that's what we're using
[00:00:41] today to map your entire project, code,
[00:00:43] docs, PDF, images, and videos into a
[00:00:46] knowledge graph that you can query
[00:00:47] instead of grepping through the files.
[00:00:49] So we are able to take Graphify and
[00:00:52] point it at any sort of repo we want,
[00:00:54] and it creates this sort of knowledge
[00:00:55] graph. The reason we care about this is
[00:00:58] when we create a knowledge graph, it
[00:01:00] allows Claude Code to more easily answer
[00:01:02] questions about that repository because
[00:01:04] everything's already mapped out. It's
[00:01:06] very clear how A connects to B, how B
[00:01:08] connects to C, and why those connections
[00:01:10] matter. This is in contrast through
[00:01:12] grepping through files, which is how AI
[00:01:14] coding assistants like Claude Code
[00:01:16] normally work. Kind of a simplistic
[00:01:17] analogy, but it's as if it's just doing
[00:01:19] control F and trying to search for it
[00:01:21] versus having a clearly mapped out path
[00:01:23] of how everything's going, right? This
[00:01:25] gives Claude Code a map, while grepping
[00:01:27] through files doesn't at all. So because
[00:01:29] of that, it costs less tokens to get
[00:01:32] more accurate answers with something
[00:01:34] like Graphify. Now, how significant are
[00:01:36] those token savings? Well, some people
[00:01:38] are claiming up to 70x, which I found to
[00:01:39] be a little on the high side, and as
[00:01:41] you'll see when we demo it today, it's a
[00:01:42] bit lower than 70x, but still
[00:01:45] significant. So that's the why you
[00:01:46] should care. Now, let's talk about how
[00:01:47] it actually works. How do we go from a
[00:01:49] code base to some sort of knowledge
[00:01:51] graph like this, which looks very, very
[00:01:52] similar to something like a graph rag
[00:01:55] knowledge base. Are they the same? How's
[00:01:56] this related to RAG? We'll talk about
[00:01:58] that. Well, the way it works is through
[00:01:59] three different passes. On the first
[00:02:01] pass, we are looking at the code
[00:02:03] structure, and this is completely free.
[00:02:05] Everything you see right here, this is
[00:02:07] just through pass one. This is
[00:02:09] deterministic. This isn't AI doing a
[00:02:11] guessing game. It is literally going
[00:02:13] through the code itself and saying,
[00:02:15] "This piece of code relates to the
[00:02:16] second piece of code." And that's
[00:02:19] literally how the code base is written
[00:02:20] out. These are established connections.
[00:02:22] As it says here, a tree-sitter parses
[00:02:24] your code files and extracts classes,
[00:02:26] functions, imports, call graphs, and
[00:02:28] inline comments. This runs locally with
[00:02:30] no LLM involved. On pass number two,
[00:02:32] it's looking at video and audio if those
[00:02:34] files exist at all, and if they do
[00:02:36] exist, they're going to be transcribed
[00:02:38] with faster-whisper. And so, once
[00:02:40] they're actually broken down into text,
[00:02:42] they will also be injected into the
[00:02:43] knowledge graph. Lastly, it does a third
[00:02:45] pass on docs, papers, and images. So, if
[00:02:47] your code base includes things that
[00:02:49] isn't true code, whether that's just
[00:02:51] like PDF files, documentations, images,
[00:02:53] whatever, this gets hit on pass number
[00:02:55] three. And this is where the large
[00:02:57] language model actually comes in and
[00:02:58] does some sort of like semantic
[00:03:00] analysis. AKA, what does this document
[00:03:02] actually mean, and where should it fit
[00:03:04] in this larger knowledge graph? This
[00:03:07] third pass is kind of similar without
[00:03:10] true embedding to what a RAG system
[00:03:11] does. Once it does all that, it then
[00:03:13] begins to create the actual knowledge
[00:03:16] graph itself. It goes into a little bit
[00:03:18] more technical detail in here, but all
[00:03:20] of you need to understand is it's going
[00:03:21] to create nodes, which are these little
[00:03:25] circles, right? Each one of these
[00:03:27] circles is a node. We then have edges,
[00:03:30] which are the line between two nodes,
[00:03:33] two things that are connected, and then
[00:03:34] communities. Communities are simply
[00:03:36] large groupings of nodes that are
[00:03:38] similar in nature. What you see here are
[00:03:41] 486
[00:03:42] communities. So, that's kind of the
[00:03:44] overview of how the data is actually
[00:03:46] extracted and turned into a graph. And
[00:03:47] remember, we care about turning into a
[00:03:49] graph because for all intents and
[00:03:50] purposes, it's a map to Claude code, so
[00:03:52] it can more quickly answer questions.
[00:03:54] Now, you probably have a few questions
[00:03:56] at this point. One, what if there is no
[00:03:57] code structure? What if I'm pointing at
[00:03:59] a repository full of markdown files?
[00:04:01] It's just like a bunch of documents that
[00:04:02] I want to create a knowledge graph of,
[00:04:03] and I don't want to go full rag. Can I
[00:04:05] do that? Yes, in fact, you can actually
[00:04:07] turn it into an Obsidian vault through
[00:04:08] Graphy. We'll talk about that a little
[00:04:10] bit at the end. The second question you
[00:04:12] probably have is
[00:04:13] yeah, this actually does look super
[00:04:15] similar to something like Graph rag.
[00:04:17] What's actually the difference, and when
[00:04:19] should I use one or the other? Well, the
[00:04:21] biggest difference between Graphy and a
[00:04:23] graph rag system like light rag or rag
[00:04:26] anything or Microsoft graph rag is
[00:04:28] really going to be the embeddings,
[00:04:29] right? Graphy isn't using any embedding
[00:04:32] system whatsoever. The second biggest
[00:04:34] difference is the use cases. So, Graphy
[00:04:36] is best and we get the most out of it
[00:04:37] when we're talking about code bases. If
[00:04:39] we see some sort of huge repo, whether
[00:04:40] it's a new one or one we've been working
[00:04:42] on, and we want to figure out how it's
[00:04:43] wired, Graphy is perfect for that. Graph
[00:04:47] rag on the other hand is great for
[00:04:48] something that's more un structured.
[00:04:50] Let's say you have tens of thousands of
[00:04:52] documents that are all PDF files or
[00:04:54] markdown files, and you just want to ask
[00:04:56] about them. You know, imagine they're
[00:04:58] all policy documents, and you're asking
[00:04:59] like, "What does the policy say about
[00:05:00] X?" Right? It could be anywhere amongst
[00:05:03] any of these documents that aren't
[00:05:04] necessarily connected. It's very
[00:05:06] unstructured. That's where Graph rag or
[00:05:08] really any rag system shines. That being
[00:05:10] said, the division between those two
[00:05:12] here is kind of murky because, like I
[00:05:14] mentioned on that third pass, we can
[00:05:16] kind of do that with Graphy. It's almost
[00:05:18] like a rag light system in that sense.
[00:05:21] So, that's what Graphy is, how it works,
[00:05:23] and why you should care. Now, let's talk
[00:05:25] about actually installing this thing and
[00:05:27] using it for real. But before we jump
[00:05:28] into that demo, a quick word from
[00:05:30] today's sponsor, me. So, not too long
[00:05:33] ago, I released the Claude code
[00:05:34] masterclass, and it is the number one
[00:05:36] way to go from zero to AI dev, no matter
[00:05:38] your technical background. This course
[00:05:39] gets updated weekly, and it also
[00:05:41] includes additional masterclasses like
[00:05:44] the Codex masterclass and the Claude OS
[00:05:47] masterclass. So, if you're someone who
[00:05:49] wants to take this a little more
[00:05:50] seriously, definitely check it out. You
[00:05:52] can find it inside of Chase AI Plus.
[00:05:53] There is a link in the pinned comment.
[00:05:55] So, installing Graphy is relatively
[00:05:57] simple. We have a few prerequisites as
[00:06:00] well as instructions for how to install
[00:06:02] it. If you're using Claude Code, I
[00:06:03] suggest you make it very easy on
[00:06:05] yourself. Just go to the Graphy GitHub
[00:06:07] link. I'll put that down below. Copy it,
[00:06:10] paste it into Claude Code, and just tell
[00:06:11] it, "Hey, install Graphy for me." But,
[00:06:14] if you want to do it manually, you can
[00:06:15] just follow the steps as they are laid
[00:06:17] out. And again, Graphy is platform
[00:06:19] agnostic and it works with any coding
[00:06:21] agent out there. And once you have
[00:06:23] Graphy installed, the next question
[00:06:24] becomes, "Okay, how do I use this? What
[00:06:25] are the commands?" Well, there are quite
[00:06:28] a few commands. And there's so many
[00:06:30] commands, in fact, you are not going to
[00:06:32] remember any of these. Luckily, when you
[00:06:34] install Graphy, it's going to come with
[00:06:36] a Graphy skill. The skill is going to
[00:06:38] teach Claude Code how to use Graphy and
[00:06:41] when it should use which commands
[00:06:42] depending on the natural language you
[00:06:44] use. So, that being said, I suggest you
[00:06:47] take a look at the GitHub repo, somewhat
[00:06:49] familiarize yourself with what is
[00:06:51] possible because there is a lot, but
[00:06:53] understand you don't have to have this
[00:06:54] memorized. Claude Code understands what
[00:06:56] to do.
[00:06:57] But, there are a few we should be aware
[00:06:59] of. If I do {forward-slash} Graphy,
[00:07:00] that's going to run the whole thing on
[00:07:02] whatever directory I'm currently on.
[00:07:04] There are also Graphy commands for
[00:07:05] querying the knowledge graph. So, if I
[00:07:07] do Graphy query or Graphy explain, it's
[00:07:10] going to explicitly tell Claude Code or
[00:07:12] whatever coding agent you're using to,
[00:07:14] "Hey, take a look at the knowledge graph
[00:07:16] when you answer this question. Don't be
[00:07:17] lazy and just try to answer it on your
[00:07:18] own." Furthermore, we have commands to
[00:07:20] make sure it's always on. So, if I do
[00:07:22] Graphy Claude install, that means it's
[00:07:24] always going to use Graphy to answer the
[00:07:27] questions. I don't have to be explicit.
[00:07:28] It literally becomes a hook. And there
[00:07:30] are some other interesting flags like
[00:07:31] the Obsidian flag, which will with one
[00:07:33] command create an entire Obsidian vault
[00:07:35] for you and fill it with whatever Graphy
[00:07:38] comes up with. But again, remember the
[00:07:40] skill is installed. So, if you ever get
[00:07:42] confused about what makes sense, just
[00:07:43] ask Claude Code. It will understand. So,
[00:07:45] now let's actually run this. For the
[00:07:47] demo, we are going to be pointing Claude
[00:07:50] Code at Open Design, which is a
[00:07:52] relatively large code base. If you've
[00:07:54] never used Open Design, it's essentially
[00:07:56] Claude Design, but open sourced. So,
[00:07:59] I've cloned it on my machine, and I'm
[00:08:01] going to open Claude Code inside that
[00:08:02] directory. So, we're inside the
[00:08:04] directory, and all I'm going to do is
[00:08:05] /graphify
[00:08:07] and then {dot} and it's now going to run
[00:08:09] graphify on this entire folder. So,
[00:08:12] after running for 6 minutes, this is
[00:08:14] what we got. It took a look at 203
[00:08:16] files. It got 1,907
[00:08:19] nodes, 3,447
[00:08:22] edges, and 109 communities, and output
[00:08:25] tokens was just under 120K.
[00:08:27] So, it lists the god nodes. The god
[00:08:29] nodes are pretty much like the most
[00:08:31] prominent nodes, the most prominent
[00:08:33] connections inside whatever it
[00:08:35] traversed. We have surprising
[00:08:37] connections I didn't expect, and
[00:08:40] suggested questions. So, if we want to
[00:08:42] take a look at the graph, I can say, "Go
[00:08:44] ahead and bring up the graph
[00:08:48] for me."
[00:08:49] So, here's a look at the knowledge graph
[00:08:51] it built, and you can kind of see the
[00:08:53] communities. There it created 109
[00:08:55] communities, and that's really just all
[00:08:56] of these clusters. As we scroll in on
[00:08:59] them,
[00:09:00] we can see the nodes, which are the
[00:09:02] actual dots, and then the edges are the
[00:09:05] connections between them. When I click
[00:09:07] on the node, you can see over here on
[00:09:09] the top right, it's type, so it's a code
[00:09:11] node, its community, its source, as well
[00:09:14] as its neighbors. But remember, as cool
[00:09:16] as this visualization is, and it does
[00:09:18] look neat, the real value here isn't the
[00:09:20] knowledge graph. Like this is cool
[00:09:22] looking, but the actual value is the
[00:09:25] fact that now we have handed Claude Code
[00:09:27] a map to the Open Design repository. And
[00:09:29] I And I can now ask questions about it
[00:09:31] and get accurate responses. So, what
[00:09:33] we'll test now is we'll ask it a a about
[00:09:35] something to do with the repo, and we're
[00:09:38] going to have it use graphify, so have
[00:09:39] it actually use the knowledge graph, and
[00:09:41] then we'll ask pretty much the same
[00:09:43] question not using graphify. So, just
[00:09:45] have it like grep the answer, and we'll
[00:09:46] take a look at what the token difference
[00:09:48] looks like. So, to take a look at the
[00:09:49] token difference with and without
[00:09:51] graphify, we're going to ask the same
[00:09:52] question to Claude Code about the repo.
[00:09:55] The first one is, "Trace how a design
[00:09:57] request flows from the web app to a
[00:09:59] coding agent and back." So, we're trying
[00:10:00] to understand how this application
[00:10:03] actually works. And in the first tab,
[00:10:05] we're going to say, "Use graphify." And
[00:10:07] in the second tab, with the same
[00:10:08] question, we're saying, "Do not use
[00:10:09] graphify." So, we can see the graphify
[00:10:11] skill being loaded right away, and then
[00:10:14] we can see commands like graphify query
[00:10:16] asking the question we just gave Claude
[00:10:18] Code. Over here on the non-graphify
[00:10:20] side, we see that Claude Code has
[00:10:22] spawned two explore agents to take a
[00:10:24] look at the codebase, and right off the
[00:10:26] rip, we've already used 100,000 tokens
[00:10:28] between them. Now, in terms of the
[00:10:30] actual answers we got, they were the
[00:10:31] same. They both identified how this app
[00:10:34] actually works, but with the
[00:10:36] non-graphify version, we needed to run
[00:10:38] those explore agents, so we were looking
[00:10:40] at about 150,000 tokens, give or take,
[00:10:43] with the explore agents, plus an
[00:10:44] additional 50,000 tokens on the main
[00:10:47] session. So, you know, about 200,000
[00:10:49] tokens total versus over here on the
[00:10:52] non-graphify version, we only used
[00:10:57] about 80,000. So, about 40% of the total
[00:11:01] cost of the non-graphify, which is
[00:11:02] significant savings. Now, since this
[00:11:05] non-graphify version has now sort of
[00:11:07] crawled through the repo itself, if I
[00:11:10] ask additional questions, the token cost
[00:11:12] won't be as off. However, since we have
[00:11:16] the knowledge graph built, whenever we
[00:11:18] want to ask questions about it via
[00:11:19] graphify, well, we're not going to have
[00:11:21] to deal with that token cost of going
[00:11:23] through it again and again, and that
[00:11:24] kind of leans into the whole memory
[00:11:26] piece. Like, we've built it out already,
[00:11:28] we can always query it for cheap. Now,
[00:11:30] the question then becomes, if this is a
[00:11:31] living, breathing repo, what happens
[00:11:33] when we make updates to the repo? Will
[00:11:35] this knowledge graph also be updated?
[00:11:37] Well, the answer is yes. We see this
[00:11:38] spelled out in the workflow in the
[00:11:40] readme. If we run graph if I hook
[00:11:42] install, it's going to auto rebuild
[00:11:44] after each commit. And that is the AST
[00:11:46] only. There's no API cost associated
[00:11:48] with that. It's literally just looking
[00:11:49] at what actually changed, what is it now
[00:11:52] connected to, and it rebuilds that tree,
[00:11:54] but it's at no cost to you. Like this is
[00:11:56] all done in a determinate deterministic
[00:11:58] way. Furthermore, this also works in a
[00:12:00] team setup. So if you had two devs
[00:12:02] working on the same repo in parallel, it
[00:12:04] also deals with that situation. So in
[00:12:06] the end, you get this persistent yet
[00:12:08] living map of whatever repo you want
[00:12:10] that you can give the cloud code so you
[00:12:12] can get more efficient answers. And
[00:12:14] lastly, we hinted at it a little bit
[00:12:16] here with the Obsidian flag, we can do
[00:12:18] all of this with a repo that is not
[00:12:19] code-based. It's a little bit different,
[00:12:21] and we are actually going to do that in
[00:12:22] another video where we drill down on
[00:12:23] Graph AI and Obsidian, and sort of what
[00:12:26] that connection looks like. But just
[00:12:27] understand, we aren't pigeonholed into
[00:12:29] code only. This is a pretty flexible
[00:12:32] tool. But that is where I'm going to
[00:12:33] leave you guys for today. I think this
[00:12:35] is a really cool tool, and when you look
[00:12:37] at the spectrum of sort of these like
[00:12:39] memory adjacent applications and plugins
[00:12:42] that we can use alongside things like
[00:12:43] cloud code and codex, I think Graph AI
[00:12:45] sort of falls somewhere in between
[00:12:47] Obsidian and a true rag system. And I
[00:12:50] think that's great. The more options we
[00:12:51] have, the more tools we have at our
[00:12:53] disposal, the better we can choose the
[00:12:54] right one for the job. We don't have to
[00:12:56] only use Obsidian, you know, we might
[00:12:58] not just be doing something in markdown.
[00:12:59] And we don't have to go crazy and
[00:13:01] generate some huge rag infrastructure.
[00:13:04] This is again, it's a cool little middle
[00:13:05] ground that I think is worth exploring.
[00:13:07] So as always, let me know what you
[00:13:08] thought. Make sure to check out Chase AI
[00:13:10] Plus if you want to get your hands on
[00:13:12] the cloud code masterclass. Speaking of
[00:13:14] Obsidian, I'm actually going to be
[00:13:15] running a free live webinar next week
[00:13:17] about Obsidian and cloud code. I'll put
[00:13:19] a link to that down there as well.
[00:13:21] And besides that, I'll see you around.
