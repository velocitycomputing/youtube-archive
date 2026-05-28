---
video_id: HQEm4rBKdec
title: "Graphify Solves Claude's Biggest Limitation (Finally)"
channel: Eric Tech
url: "https://www.youtube.com/watch?v=HQEm4rBKdec"
watched_date: 2026-05-19
watched_at: "2026-05-19T12:00:00Z"
watch_count: 1
duration_seconds: 711
source: youtube-history-browser
history_label: May 19
history_order: 173
watched_at_precision: date-from-history-label
watched_percent: 38
estimated_watched_seconds: 270
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Graphify is a tool that converts codebases and documentation into structured knowledge graphs, reducing LLM token usage by 70% and enabling faster, more accurate queries. Inspired by Andrej Karpathy's work on LM knowledge bases, it's designed for research and exploration tasks. The video demonstrates installing Graphify (requires Python 3.10+ and UV), building a knowledge graph from a large codebase with `graphify build`, and exploring the results through an interactive HTML visualization that shows nodes (files/components), edges (connections), and metrics. Key features include path finding between files, explain functionality to understand code concepts, querying capabilities, and the ability to generate multiple output formats like Obsidian vaults, wikis, Neo4J databases, and MCP servers for other LLMs.

To start using Graphify, install Python 3.10+ and UV on your machine, then install Graphify via UV. Run `graphify build` on your project folder and choose your extraction level (code only recommended for quick exploration, code + docs for broader context, or full with images if visual elements matter). Use the interactive graph.html to visualize and toggle file connections, run the `path` command to find shortest paths between files, use the `explain` command to understand code functionality, and query the graph with custom questions. For iterative development, use `graphify build --update` to re-process only changed files rather than rebuilding the entire graph.

## Transcript

[00:00:00] If you're using large language model,
[00:00:01] here's how you do research on your
[00:00:02] project, then you definitely need to
[00:00:03] check out this repository called
[00:00:05] Graphify. And this repository is
[00:00:07] inspired from this ex post that Andrej
[00:00:09] Karpathy wrote about the LM knowledge
[00:00:11] base. And for those who don't know who
[00:00:13] Andrej Karpathy is, he is the former
[00:00:15] director of AI at Tesla and a founding
[00:00:17] member of OpenAI. And essentially what
[00:00:19] he's saying here is that we can index
[00:00:21] our raw file here to make a large
[00:00:23] language model here to query information
[00:00:24] and also be able to maintain it. And
[00:00:26] this repository here, you can see it
[00:00:28] does exactly that. For example, let's
[00:00:29] say if you have a folder here that
[00:00:30] contains code, documentations, you
[00:00:32] simply just using the Graphify command
[00:00:34] scale and it's going to convert it into
[00:00:36] a knowledge graph. And once you convert
[00:00:38] that into a knowledge graph, this will
[00:00:39] reduce the large language model token
[00:00:41] usage by 70%. So instead of having AI
[00:00:44] agent here to reading the raw files or
[00:00:46] documentations every single time,
[00:00:48] Graphify here is going to index it for
[00:00:49] you and compiles your code base into a
[00:00:52] structured knowledge graph so that the
[00:00:53] large language model here is going to be
[00:00:55] much more faster, consumes less tokens,
[00:00:57] and much more accurate when finding
[00:00:59] information from your local folders
[00:01:01] because it's already creating a graph.
[00:01:02] And honestly, this is mostly for people
[00:01:04] who wants to read more than write,
[00:01:05] especially for doing research or
[00:01:07] exploring new code bases. And that's why
[00:01:09] in this video, we're going to explore
[00:01:11] this Graphify repository and we're going
[00:01:12] to see how we can be able to install
[00:01:14] this onto a local machine, how we can be
[00:01:15] able to use it like converting our raw
[00:01:17] files here into a knowledge graph, and
[00:01:20] later on I'm going to show exactly how
[00:01:21] we can be able to add any informations,
[00:01:23] how we can query informations, how we
[00:01:25] can be able to add this to different
[00:01:26] large language model, extracting
[00:01:28] documentations, and so much more. So by
[00:01:31] the end of this video, your large
[00:01:32] language model here can have higher
[00:01:33] accuracy, lower token consumptions, and
[00:01:35] faster output. So with that being said,
[00:01:37] if that sounds interesting, let's get
[00:01:39] into the video. Now, before we continue,
[00:01:41] I recently launched our school community
[00:01:43] where I help you to master AI agents,
[00:01:44] automations, and so much more. And
[00:01:46] that's all coming from someone who used
[00:01:48] to work as a senior AI software engineer
[00:01:50] at companies like Amazon and Microsoft.
[00:01:53] And in this community, you're going to
[00:01:54] get over 100 plus video materials like
[00:01:56] templates and workflows that I
[00:01:58] personally built and sold over 100 plus
[00:02:00] times. On top of that, you're also going
[00:02:02] to get access to our weekly live calls.
[00:02:04] And just give you an idea, this week
[00:02:05] we're actually running a Claude
[00:02:06] Masterclass where we're going to dive
[00:02:08] into how to improve Claude's accuracy
[00:02:11] when we're going to use it to build the
[00:02:12] applications. Plus, you're also going to
[00:02:13] get full community support where you're
[00:02:15] going to get a chance to ask questions
[00:02:16] and get direct answers back. So, if
[00:02:18] you're ready to level up, make sure you
[00:02:19] jump right in and I'll see you in a
[00:02:21] community. All right. So, to get
[00:02:22] started, first we're going to do here is
[00:02:23] to install the prerequisites. So, right
[00:02:25] here you can see there's a couple of
[00:02:27] things we need. One is we need the
[00:02:28] Python onto your local machine, which is
[00:02:30] version 3.10 above. And simply just
[00:02:33] going to go to the python.org and just
[00:02:35] going to install it onto your local
[00:02:36] machine. The other one here is we have
[00:02:38] is UV. And we can also use the PIPX, but
[00:02:41] I'm just going to use UV for now. So,
[00:02:43] essentially we can do here is that you
[00:02:44] can just copy the repository and paste
[00:02:47] it to Claude Code or Codex and try to
[00:02:49] have your AI agent here to install it on
[00:02:50] your behalf. But, I'm just going to
[00:02:52] install this manually here so you can
[00:02:53] see here the first one we need to is to
[00:02:55] install the Python and UV onto your Mac
[00:02:58] OS. So, simply I'm just going to head
[00:02:59] over to a new terminal session, paste
[00:03:01] that command, and you can see it's going
[00:03:03] to install Python here and UV onto our
[00:03:05] local machine. And the next thing I'm
[00:03:07] going to do here, as you can see, we're
[00:03:09] going to use UV here to install the
[00:03:10] Graphile. Now, UV is kind of like NPM
[00:03:13] for uh Python, right? So, instead of
[00:03:16] having Node.js, which is using NPM,
[00:03:18] Python here is using UV. So, now if I
[00:03:21] were to clear terminal and just going to
[00:03:22] do the install for Graphile, and now you
[00:03:24] can see it's going to install the
[00:03:25] Graphile NPM or in this case the package
[00:03:27] onto our local machine. And then what's
[00:03:29] going to happen here is that we're going
[00:03:30] to register skills with our AI assistant
[00:03:32] by simply just going to run the Graphile
[00:03:34] install.
[00:03:35] This way we're going to have our skills
[00:03:37] added onto our project, which you can
[00:03:38] see here. So, we have our skill
[00:03:40] installed and also it's going to be
[00:03:41] living in this .claude folder. And then
[00:03:43] we also have the claude.md file, which
[00:03:46] rows on how to use the skill. And of
[00:03:48] course, if you're using different
[00:03:49] platforms, by default the installation
[00:03:51] here is going to install claw code, but
[00:03:53] if you're using code x, you can simply
[00:03:55] just going to do the platform code x. If
[00:03:57] you're using open code, there's also a
[00:03:58] command for that and open claw as well
[00:04:01] as the Hermes agents. So, there's tons
[00:04:03] of options if you're using different AI
[00:04:04] agents framework, so you can just follow
[00:04:06] that as well. Okay, so once we have this
[00:04:08] installed, the next thing we're going to
[00:04:09] take a look at is the commands. So, we
[00:04:11] scroll all the way down, you can see
[00:04:12] there's a common commands where we
[00:04:13] simply just going to do the graph by
[00:04:15] dots and it's going to build a graph for
[00:04:17] the current folder. Now, like I said,
[00:04:19] this is the bookkeeping application that
[00:04:21] I built. These are tons of folders that
[00:04:23] we have, tons of MD files or code files
[00:04:25] that we have here. And this is basically
[00:04:27] the platform that I built, which is book
[00:04:28] zero.ai and essentially what this
[00:04:31] platform does is using AI to help
[00:04:33] businesses here to manage receipts and
[00:04:35] bank statements. And here you can see
[00:04:36] there's bunch of code base, which has
[00:04:38] the app, the assets, the components, the
[00:04:41] content, docs, and so much more. And
[00:04:44] essentially, all I had to do here just
[00:04:45] going to do the {slash} graph by dots.
[00:04:47] And what's going to happen here is that
[00:04:48] it's going to take the current folder
[00:04:50] that we have, which is huge, huge code
[00:04:52] base, and I'm just going to do a {slash}
[00:04:54] graph by dots. And it's going to build a
[00:04:55] knowledge graph around this code base.
[00:04:58] So, in this case, what I'm going to do
[00:04:59] here is I'm going to wait for a bit
[00:05:00] until everything is set up. And then
[00:05:02] we're going to take a look at what the
[00:05:02] result look like. Okay, so now you can
[00:05:04] see it's asking us a question. In terms
[00:05:07] of the full map that we're trying to
[00:05:08] build, right, the full knowledge graph,
[00:05:10] should we only process the code only or
[00:05:13] the code plus documentations but skip
[00:05:15] images or the full extractions including
[00:05:18] the images. So, you can see that if we
[00:05:20] were to do the full extractions, that's
[00:05:22] going to take anywhere around 200k all
[00:05:24] the way to 400k tokens. But depends on
[00:05:26] what you're trying to do. If you're
[00:05:28] doing like research on the code base for
[00:05:30] existing functionalities, then my
[00:05:31] recommendation is just the first option,
[00:05:33] which is code only. If you're looking to
[00:05:35] go through the documentation as well,
[00:05:37] you can also do with the second option.
[00:05:39] But if images are anywhere that help you
[00:05:41] to do the research, then you can also do
[00:05:43] the full extraction as configured as
[00:05:45] well. But for my case here, I'm going to
[00:05:46] go with something that's much more
[00:05:47] quicker and just do the code only
[00:05:49] instead. So, in this case, I'm going to
[00:05:50] choose that option for now. Okay, so
[00:05:52] finally, you can see the graph here is
[00:05:54] fully generated and it has generated
[00:05:56] three things. One is the graph.html,
[00:05:58] which is an interactive knowledge graph
[00:06:00] that we can interact it with it, which
[00:06:02] I'll show you later on this video. And
[00:06:04] there's also the graph.reports,
[00:06:06] as well as the graph.json, which is
[00:06:08] basically the raw JSON for the graph
[00:06:11] data. So, there you can see we have uh
[00:06:14] 70,000 for nodes and 33 for the edges.
[00:06:18] So, edges is basically the connection
[00:06:19] between the nodes and nodes are
[00:06:21] basically the individual files or
[00:06:23] individual components that we have. And
[00:06:24] you can see that for the token cost
[00:06:26] here, this is how much it cost, and this
[00:06:28] is the benchmark. So, roughly, you can
[00:06:30] see we're saving 25 or sorry, 27 times
[00:06:34] token reductions for any questions that
[00:06:36] we're going to ask to large language
[00:06:38] model about our code base. So, this is
[00:06:40] the impact that we have here. And you
[00:06:42] can see that these are the got nodes.
[00:06:43] Got nodes are basically the edges that
[00:06:45] we have. They're basically the edge
[00:06:47] nodes that we have inside our graph. So,
[00:06:50] kind of like the children nodes, right?
[00:06:51] The which is which don't have any
[00:06:53] children itself. Uh furthermore, you can
[00:06:55] see these are the surprising
[00:06:56] connections, the suggested questions,
[00:06:58] and furthermore, you can see there's a
[00:07:00] bunch of stuff that it has find. And
[00:07:02] what we're going to do here is I'm going
[00:07:03] to navigate to the HTML, and you can see
[00:07:04] that this is the entire knowledge graph.
[00:07:06] I can simply just going to toggle on or
[00:07:08] off or just like let's say if I want to
[00:07:10] I'm very interested about the admin
[00:07:12] layouts, I can just toggle everything
[00:07:14] off and just show the admin layouts and
[00:07:17] the API routes, and I can be able to see
[00:07:19] all the edges, all the graph, all the
[00:07:21] nodes that are connected to that
[00:07:22] relations. And by doing so, this way is
[00:07:25] much more easier for me to understand
[00:07:26] the connections for all the files, all
[00:07:29] the code that we have in our code base.
[00:07:31] And this will help me to understand or
[00:07:32] speed up the process to make me
[00:07:34] understand the code base here much more
[00:07:36] faster. And furthermore, if I were to
[00:07:37] head over to the repository back really
[00:07:39] quickly, you can see that there's couple
[00:07:41] functionality that we can trigger. So,
[00:07:43] for example, there's one functionality
[00:07:44] called path. For example, let's say if I
[00:07:46] want to know the path between two files
[00:07:49] or two functionalities that we have. One
[00:07:51] is the admin panel and the other one is
[00:07:53] AI chat. And you can see here that it's
[00:07:55] going to trigger the graphify here. And
[00:07:58] by the end of it, you can see it's going
[00:07:59] to show us the shortest path between
[00:08:01] those two connections. So, one is the
[00:08:03] admin panel and the other one is AI
[00:08:05] chat. So, you can see that these are the
[00:08:06] files that I jump through, right? To see
[00:08:10] from going from the layout for the admin
[00:08:12] all the way to the AI page. And you can
[00:08:14] see that the connection between the two
[00:08:15] is actually from the index.ts, which is
[00:08:18] a file that calling both of those
[00:08:20] layouts or both of those TX files,
[00:08:22] right? So, you can see that's exactly
[00:08:24] the connection between the two. And here
[00:08:25] is the shortest path. And furthermore,
[00:08:27] there's also another functionality
[00:08:28] called explain. Like, let's say if I
[00:08:29] don't know the rate limiting or how does
[00:08:32] the AI chat functionality works in our
[00:08:34] application, right? So, for example, I
[00:08:36] wanted to ask and say, "Hey, let me Why
[00:08:38] don't you explain to me the inbound and
[00:08:40] outbound inside of our admin console."
[00:08:42] And you can see it's going to look
[00:08:43] through that and it's going to try to
[00:08:45] explain to you the concept based on the
[00:08:46] knowledge graph. And you can see this is
[00:08:48] the answer that it has found. So, the
[00:08:49] inbound versus the outbound and the main
[00:08:51] admin here, this is the dashboard and
[00:08:54] split by two sides of the sign-up they
[00:08:56] measure. So, one is the outbound
[00:08:57] analytics, which is where the visitor
[00:08:59] come from and where they drop off. The
[00:09:01] inbound here you can see is what users
[00:09:03] do after the sign-up and where they
[00:09:05] charm. So, you can see this is the
[00:09:07] entire difference between two and where
[00:09:10] they split. And you can see it gives you
[00:09:11] a clear definition of how it works. And
[00:09:14] furthermore, you can see there's also
[00:09:15] the query where let's say if you have
[00:09:17] any questions, you can also put your
[00:09:19] question here and ask about it, right?
[00:09:21] Let's say if you want to also adding
[00:09:23] additional, for example, information.
[00:09:25] Like, for example, I want to add a
[00:09:26] research paper onto this graph. I can
[00:09:28] also do that. But let's just say that
[00:09:30] you have added bunch of stuff. Let's say
[00:09:31] if you want to re-restructure only the
[00:09:33] changed files that you have. Let's Let's
[00:09:35] if you modify some files here on your
[00:09:36] local machine, you have a bunch of
[00:09:37] files, not just one, not just two, but
[00:09:39] like actually like 10 or 20. Instead of
[00:09:41] just adding them one by one, what you
[00:09:43] can also do here is that you can also do
[00:09:45] graph 5.raw {hyphen} {hyphen} update,
[00:09:47] which will re-extract only the changed
[00:09:49] files and add them onto your knowledge
[00:09:51] base. And that's how you can do it.
[00:09:53] There's also the Obsidian, which is
[00:09:55] really cool. Like you can also be able
[00:09:56] to generate the Obsidian vaults based on
[00:09:59] your code base. So for example, like
[00:10:00] let's say if you're interested about the
[00:10:02] docs that you have, I'm going to do this
[00:10:04] really quickly. So I'm just going to go
[00:10:05] to a new terminal and do the cloud
[00:10:08] again. And I'm just going to do the
[00:10:11] graph 5 here for the Obsidian. And this
[00:10:13] time I'm going to say I'm only
[00:10:14] interested for doing this inside for our
[00:10:17] doc folder. So I only want you to touch
[00:10:20] what we have in our docs folder, which
[00:10:21] is this path right here, and I want you
[00:10:23] to do this. So you can also be able to
[00:10:25] give it a prompt and let it try to do
[00:10:27] the Obsidian parts for the docs folder.
[00:10:30] So if you don't want to do this for the
[00:10:32] entire code base, you can also do this
[00:10:33] for the entire doc folder. You can put
[00:10:35] in that. And just mention that I want
[00:10:37] you to generate a Obsidian vault for
[00:10:39] this, right? So there's a lot of things
[00:10:41] you can do. There's also wiki, there's
[00:10:43] also SVG,
[00:10:45] um there's Neo, Neo for J, if you want
[00:10:47] to generate a like a rag system, right?
[00:10:50] So there's a lot of things you can do.
[00:10:51] There's also like you can generate a MCP
[00:10:53] server for this. So that any other large
[00:10:55] language model here can query for this.
[00:10:57] There's also a option for you to do
[00:10:58] that. So honestly here you can see the
[00:11:00] possibility here is endless, and I don't
[00:11:03] want to go over this in video, but you
[00:11:04] can see the core functionality here is
[00:11:06] you can use this to query information,
[00:11:08] to extract informations, to show the
[00:11:10] connection between the two, to help you
[00:11:11] to understand the code base here much
[00:11:13] more faster. And I'll make sure to drop
[00:11:14] this repository here in the links in the
[00:11:16] description below for you to check it
[00:11:18] out. And don't forget, if you're looking
[00:11:19] to up your level on how you can use
[00:11:21] Claude code or any other coding agent
[00:11:23] here to develop applications, because we
[00:11:25] do have courses and also weekly live
[00:11:27] calls that you can check it out. So with
[00:11:29] that being said, that you do find value
[00:11:30] in this video, please make sure to like
[00:11:32] this video, consider subscribing for
[00:11:33] more content like this. But with that
[00:11:35] being said, I'll see you in the next
[00:11:36] video.
