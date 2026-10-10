---
video_id: hQvwMj7IJe4
title: Fable 5 + Karpathy’s LLM Wiki is Basically Cheating
channel: "Nate Herk | AI Automation"
url: "https://www.youtube.com/watch?v=hQvwMj7IJe4"
watched_date: 2026-07-04
watched_at: "2026-07-04T12:00:00Z"
watch_count: 1
duration_seconds: 875
source: youtube-history-browser
added_date: 
history_label: Saturday
history_order: 60
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 88
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker demonstrates how Fable 5 creates intelligent LLM wikis—interconnected knowledge bases built from YouTube transcripts, PDFs, URLs, and meeting recordings using Obsidian as a frontend. Karpathy's LLM wiki concept uses Claude to automatically ingest sources, organize them hierarchically into markdown files with indexed concepts/entities/sources, and cross-link related information. The speaker showed ingesting two sources (Claude's Fable 5 system card + OpenAI GPT-5.6 article) which generated 20 interconnected wiki pages that revealed a key insight: Frontier Model Cybersecurity, showing how OpenAI benchmarked against different harnesses than Claude. Fable 5 excels at understanding abstract, emotional prompts (like "beginner-friendly") to create simple visualizations, outperforming Opus 4.8 on the same task and dataset.

To build your own: (1) Install Obsidian from obsidian.md and create a new vault; (2) Open it in Claude Code and paste Karpathy's LLM wiki gist as a system prompt; (3) Drop PDFs into the `/raw` folder or provide URLs directly to Claude with instructions to ingest them; (4) Claude automatically creates the folder structure (concepts, entities, sources, etc.) and cross-links pages; (5) Review results, adjust the schema rules if needed, then incrementally add more sources. Since wikis are just markdown files with routing rules, you can connect any agent (Hermes, Codex, etc.) to query them—you're not locked into Claude Code. The speaker offers a free AIOS-building course in their community for deeper learning.

## Transcript

[00:00:00] What you're looking at right over here
[00:00:01] are a bunch of my YouTube videos being
[00:00:03] ingested into an LLM wiki. This LLM
[00:00:06] wiki, as you can see if I zoom in, are
[00:00:08] different YouTube videos and what's
[00:00:09] connecting them are different relations.
[00:00:11] So, we're starting to see this actual
[00:00:13] kind of like second brain of all of my
[00:00:14] YouTube videos and how they relate to
[00:00:16] each other and all of this knowledge
[00:00:18] makes my AI OS so much smarter. And the
[00:00:21] coolest part about this is I didn't have
[00:00:22] to connect these concepts at all. I was
[00:00:24] able to just say, "Hey, Claude code, go
[00:00:26] grab my YouTube videos and then ingest
[00:00:28] them into this wiki." And this thing
[00:00:29] continuously grows and grows. If I zoom
[00:00:31] in a little bit, let's open up one of
[00:00:32] these videos. So, right here I've got
[00:00:33] Nano Banana two websites. When I open
[00:00:36] this up, we can see some information up
[00:00:37] here, but then as we scroll down, we can
[00:00:39] see, you know, summary, key takeaways,
[00:00:41] and other tools and things that are
[00:00:42] mentioned and other techniques that have
[00:00:44] been discussed. And I can follow all of
[00:00:45] these links around. Let's say I'm
[00:00:46] interested in GitHub. I can click on the
[00:00:48] GitHub. I can see what this is about and
[00:00:50] then I can see other times that we've
[00:00:51] referenced GitHub. Here's some
[00:00:52] information that connects GitHub to
[00:00:53] Vercel. Why don't I click into that and
[00:00:55] learn some more about Vercel? And then
[00:00:56] Vercel can take me back to Claude code
[00:00:58] where I once again can follow all of
[00:00:59] these backlinks until I get to where I
[00:01:01] need to go. And so, as this whole mind
[00:01:03] map of these YouTube videos starts to
[00:01:04] grow, we're able to see all of this come
[00:01:06] to life. And today I'm going to show you
[00:01:08] guys exactly how you can get up and
[00:01:09] running with something just like this in
[00:01:10] about 5 minutes. It's so much simpler
[00:01:12] than you may think. Now, what's
[00:01:13] impressive about this isn't the fact
[00:01:15] that Fable was able to ingest all of it,
[00:01:17] it's what Fable can do once you've given
[00:01:18] it the power of all of this data cuz we
[00:01:20] all know that data is king, context is
[00:01:22] king. Here's a cool example. I asked
[00:01:24] Fable in one prompt, I said, "Hey, I
[00:01:26] want you to basically turn this messy
[00:01:29] blob of YouTube transcripts connections
[00:01:31] into something that people could
[00:01:32] actually look at and understand. I want
[00:01:34] this to be a simple resource that's not
[00:01:35] overwhelming, but shows my audience how
[00:01:37] these tools and techniques and ideas
[00:01:39] connect to each other." And now we have
[00:01:41] this super cool HTML which I can click
[00:01:43] into and I can see different ideas up
[00:01:45] top, agentic workflows and what it
[00:01:46] connects to. It connects to routines.
[00:01:48] Routines connects to deterministic
[00:01:50] versus agentic automation which connects
[00:01:52] back to N&N and Claude code and all of
[00:01:54] this kind of stuff and it's just
[00:01:55] amazing. In my mind, something like this
[00:01:57] is a much more user-friendly interface
[00:01:59] than something like this. And what I
[00:02:01] think is awesome about this is that I
[00:02:03] was able to prompt it in an emotional
[00:02:05] way. I said things like, "In a way that
[00:02:07] a beginner could understand and could
[00:02:08] click through and it wouldn't overwhelm
[00:02:10] them." And something like Opus 4.8 just
[00:02:12] doesn't understand what that means as
[00:02:13] well as Fable. To show you what I mean
[00:02:15] by that, this is something that I worked
[00:02:16] on with Opus 4 almost a full day. We
[00:02:19] went back and forth, we built this thing
[00:02:20] out, and I just didn't like it enough to
[00:02:22] share it with people because it felt
[00:02:24] overwhelming. It felt confusing. And the
[00:02:25] database on the back end that powers
[00:02:27] this is the exact same one. So anyways,
[00:02:29] what we're looking for here is same
[00:02:30] thing. You can search through tools,
[00:02:32] techniques, videos. There's kind of like
[00:02:34] a layer framework that we discussed with
[00:02:35] the orchestrator, the models, the
[00:02:37] inputs, all of this kind of stuff. And
[00:02:39] it has all the same data, and I can
[00:02:40] still click into these things, and I can
[00:02:41] follow the back links, and you know,
[00:02:43] it's kind of the same idea, but once
[00:02:45] again, this version is just so much
[00:02:47] simpler to me, and I like it more. You
[00:02:49] can see as we click on a concept, we're
[00:02:51] able to see on this right-hand side
[00:02:52] videos that it pulled this data from. We
[00:02:53] can read a little bit more about it, and
[00:02:55] we can see what else it's connected to.
[00:02:57] So that's just one very small example.
[00:02:58] If you guys have been following me for a
[00:02:59] while, you know that in my AIOS, I have
[00:03:01] a few different LLM wikis. This is my
[00:03:03] YouTube transcript one. I've also got
[00:03:04] like my Herc brain one, which is pretty
[00:03:06] much where I put all of my meeting
[00:03:08] recordings. So all of my meetings,
[00:03:09] whether they're internal or external, I
[00:03:11] store them here, and that's how I'm able
[00:03:12] to see how the different concepts that
[00:03:14] I'm talking about with people have
[00:03:16] evolved and how they are going to
[00:03:17] continue to evolve. And when I'm
[00:03:18] scripting community posts, LinkedIn
[00:03:20] posts, writing emails, it takes all of
[00:03:22] this stuff into account because it knows
[00:03:24] everything about me and my business. So
[00:03:25] much so that right before this video, I
[00:03:27] said, "Hey, Mr. Fable, I want you to go
[00:03:29] ahead and just tell me a story about the
[00:03:31] past 6 months." So, you know, we're
[00:03:32] halfway through 2026. Build me a visual
[00:03:34] journey of what we've done so far in
[00:03:36] 2026. And this is what it gave me in one
[00:03:38] shot. It was able to pull this picture
[00:03:40] of me. It pulled our logo, and you can
[00:03:42] see that this thing is even feel And you
[00:03:44] can see that the branding of this even
[00:03:46] feels like AIS. It's kind of dark mode,
[00:03:48] blue graph colors, and this is what it
[00:03:51] gave me. It pulled actual stats like how
[00:03:52] many subscribers I gained. Um it has our
[00:03:55] highest revenue month, which I'm going
[00:03:56] to blur out, but it was able to look at
[00:03:58] all this data and just pull it for me.
[00:03:59] This was a big pivot I made this year. I
[00:04:01] went from pretty much doing only
[00:04:02] end-to-end content to doing a lot of
[00:04:04] cloud code content. And you can see how
[00:04:06] this was able to pay off if we look at
[00:04:07] my average views and our revenue and how
[00:04:09] the business has grown since I made that
[00:04:11] pivot. Then we look at some other things
[00:04:12] like how our churn has changed, how our
[00:04:14] conversion has changed, other things
[00:04:15] about our revenue. But look at this.
[00:04:17] This is pretty funny. It pulled this
[00:04:19] different picture of me. If you guys
[00:04:20] remember the one up at the front was a
[00:04:22] smiling one. This is one of me thinking.
[00:04:24] And so it's able to just crawl through
[00:04:26] so much of the data and the resources
[00:04:28] that it has available inside of my Herk
[00:04:30] 2 project. It shows the whole funnel of
[00:04:32] the business, which proves that it
[00:04:34] understands how people enter our
[00:04:35] ecosystem and all the decisions they can
[00:04:37] make inside of our funnel and where we
[00:04:39] try to push them to. Anyways, the point
[00:04:41] I'm trying to make there is the more
[00:04:43] data you give your projects, the better.
[00:04:46] But specifically, making sure that you
[00:04:47] route them in the right way. And that's
[00:04:49] what the LLM Wiki's are really good at.
[00:04:50] This is my Herk 2 project. You guys know
[00:04:51] that this is my AIOS, and we have so
[00:04:54] much information in here. We have
[00:04:55] different wikis, different projects,
[00:04:56] everything that I've worked on, and
[00:04:57] that's what you guys are trying to
[00:04:58] build. By the way, if you want to go
[00:05:00] through a full free course where I show
[00:05:02] you how to do that, in my free school
[00:05:03] community, link is in the description,
[00:05:04] I've got a full build your own AIOS
[00:05:06] course in there, completely free. So,
[00:05:08] link is in the description for that.
[00:05:09] Okay. So, here's where all of this
[00:05:10] started. Andre Karpathy said, "LLM
[00:05:12] knowledge bases. Something I'm finding
[00:05:14] very useful lately is using LLMs to
[00:05:16] build personal knowledge bases for
[00:05:17] various topics of research interest." He
[00:05:19] index the sources, which I'm going to
[00:05:21] show you how to do, and then he uses
[00:05:22] something like Obsidian as the front
[00:05:24] end, which is what you guys just saw.
[00:05:25] So, the first thing you want to do is go
[00:05:26] to obsidian.md and then install this for
[00:05:29] whatever operating system you're on. So,
[00:05:30] in my case, I installed this for
[00:05:31] Windows, run the wizard, get it set up,
[00:05:33] and open up the app. When you open up
[00:05:35] the app, it will look like this, except
[00:05:36] for you won't have this stuff, and then
[00:05:38] you're going to go down here and click
[00:05:39] on manage vaults. It might just pop up
[00:05:40] like this. And then you're going to go
[00:05:42] ahead and create a new vault. So, this
[00:05:44] one I'm just going to call AI test, and
[00:05:47] then you're going to choose a location
[00:05:48] for this. So, it could be on your
[00:05:49] desktop or what I typically like to do
[00:05:51] is I put my vaults inside of my Herc 2
[00:05:54] project. So, my Herc 2 is able to look
[00:05:56] at a ton of these different little LLM
[00:05:58] wikis that I have split up and separated
[00:06:00] by topic essentially. But, for this
[00:06:02] example, I'm just going to put this one
[00:06:03] on my desktop. So, I'm going to go ahead
[00:06:05] and create that wiki. You can see here
[00:06:07] or sorry, not wiki, vault. We're going
[00:06:09] to turn this into a wiki. So, right now
[00:06:11] this is what we have and then what I'm
[00:06:12] going to want you to do is you're going
[00:06:13] to go into Claude code or wherever you
[00:06:15] use Claude code. So, in this case, I'm
[00:06:17] using VS Code and you're going to open
[00:06:19] up that vault in something like this.
[00:06:21] All right. So, I've just opened up the
[00:06:23] vault. You can see that we have a dot
[00:06:24] Obsidian folder. We have a welcome.md.
[00:06:26] That's just going to be, you know, the
[00:06:28] default when you open up an Obsidian
[00:06:29] vault. And then what we're going to do
[00:06:30] is open up Claude code. So, however you
[00:06:32] like to use it, in VS Code I like to use
[00:06:34] it in the terminal. So, I'm going to go
[00:06:35] ahead and run Claude to open this up and
[00:06:38] then we're going to go ahead and get
[00:06:39] started. Now, one thing to call out here
[00:06:41] is we see that it says, "Okay, Fable,
[00:06:43] you only have it until July 7th on your
[00:06:45] limit, otherwise it will be usage
[00:06:46] credits." I did however see this tweet
[00:06:48] from Thor that said, "Yeah, that's true,
[00:06:50] but we do plan to bring it back to part
[00:06:52] of your subscription as soon as
[00:06:53] possible." As mentioned in our original
[00:06:55] blog post, which if you see at the
[00:06:56] bottom of this blog post, it does
[00:06:58] actually mention that. So, it doesn't
[00:06:59] say when, but hopefully they will be
[00:07:01] able to extend the window and bring it
[00:07:03] back as a standard part of your
[00:07:04] subscription plan. Anyways, what you're
[00:07:06] going to do after that is you're going
[00:07:07] to go to this page. I will have this
[00:07:09] link in the description. It is
[00:07:10] Karpathy's LLM wiki gist and I'm
[00:07:13] literally just going to copy this entire
[00:07:14] thing. If you want to stop and read it,
[00:07:16] feel free, but I'm going to copy this
[00:07:17] entire thing and what we're going to do
[00:07:19] is take that back into our Claude and
[00:07:21] paste that in there. And then what
[00:07:22] you're going to do is just go ahead and
[00:07:23] take a screenshot of this so you can
[00:07:25] paste it in. I said, "You are now my LLM
[00:07:27] wiki agent. Implement this exact idea
[00:07:29] file as my complete second brain. Guide
[00:07:31] me step by step. Create the Claude.md
[00:07:33] schema with my full rules. Set up the
[00:07:35] index, the log, define folder
[00:07:37] conventions, and show me the first
[00:07:38] ingest example. From now on, every
[00:07:40] interaction follows the schema." So, I'm
[00:07:42] going to go ahead and send that off. We
[00:07:44] are using Fable here. Like I said, you
[00:07:46] probably don't need Fable. Fable's
[00:07:48] probably overkill for this. It's about
[00:07:49] what Fable does after you have all that
[00:07:51] data in there. So, if you want to switch
[00:07:52] this back to Opus, run the ingest, and
[00:07:54] ingest future documents with Opus,
[00:07:56] that's probably a better call, honestly.
[00:07:58] I'm just going to be showing you Fable
[00:07:59] in this video. Now, what's really cool
[00:08:00] is as you start to put different stuff
[00:08:02] in here, it's going to sort of
[00:08:04] dynamically change the structure. So,
[00:08:06] let me show you what I mean by that. If
[00:08:07] I open up this wiki, you can see that in
[00:08:09] the wiki I have comparisons, I have
[00:08:11] concepts, I have sources, because this
[00:08:14] one is about my YouTube videos. So, it's
[00:08:15] read through them and it's analyzed
[00:08:17] that. We've got techniques and we've got
[00:08:19] tools. But, if I switch into something
[00:08:20] like my Herc brain, which is the one
[00:08:22] that's more so around like my meeting
[00:08:24] transcripts, you can see that this is
[00:08:25] pretty much a flat structure. It
[00:08:26] basically just has all of my meeting
[00:08:28] recordings right in here, and it didn't
[00:08:29] want to organize them yet. And maybe at
[00:08:31] some point if we run some, you know,
[00:08:33] sweeps through, it will find some
[00:08:34] different folders to organize them in.
[00:08:36] But, sometimes keeping this flat is
[00:08:38] actually better. And by flat what I mean
[00:08:40] is basically just having everything in
[00:08:41] the wiki, rather than having it drill
[00:08:43] down to even more folders. The reason
[00:08:45] being,
[00:08:46] you want to make sure that your AI can
[00:08:48] easily search through all this stuff. We
[00:08:50] have the raw, which is where you put
[00:08:51] stuff. Then the AI will read everything
[00:08:53] in the raw and ingest it into the wiki,
[00:08:55] and that's where it might take one
[00:08:56] source and split it up into like five or
[00:08:58] six, or maybe even 10 little wiki pages.
[00:09:01] Then we also have the index, which is
[00:09:02] like a table of contents. We have the
[00:09:04] log, and then the dot md files are all
[00:09:06] of the other wiki files. And this exact
[00:09:08] structure is how this Herc brain one is
[00:09:09] set up. As you can see, it's very flat.
[00:09:12] But, if we go back into my YouTube
[00:09:14] transcript one, this one's not flat,
[00:09:16] right? This one has all of these other
[00:09:18] subfolders, like we just talked about.
[00:09:19] And to show you what that looks like in
[00:09:20] this example, here is my index. You can
[00:09:22] see all the tools, you can see all of
[00:09:24] the uh techniques, everything that has
[00:09:26] been mapped out here with all the
[00:09:27] backlinks. And then the log, you can see
[00:09:29] that I did a few batch ingests here.
[00:09:31] I've done one there, and then every time
[00:09:33] that I've ingested another YouTube video
[00:09:34] or ingested other data sources, it will
[00:09:37] show a log of that there. The whole
[00:09:38] point of this is that the AI can
[00:09:40] incrementally build and maintain this
[00:09:42] wiki. So, it needs to be able to look at
[00:09:43] things like the index and the logs and
[00:09:45] all the backlinks to actually crawl
[00:09:46] around and find the data that you're
[00:09:48] looking for. All right, so now you can
[00:09:49] see that this is done. Our project is
[00:09:51] set up. We have our index, which is
[00:09:52] blank. We have our log, which is pretty
[00:09:54] much blank. And then we have our raw
[00:09:56] folder and our wiki folder. So, what you
[00:09:59] can see in here already is that in the
[00:10:00] raw, it processed this LLM wiki idea.
[00:10:04] This file is basically the gist that
[00:10:06] Karpathy wrote up. So, it decided to
[00:10:08] ingest that. And then in the wiki, it's
[00:10:10] already planned out to have concepts,
[00:10:12] entities, and sources. So, that is what
[00:10:15] we have to start with. Now, what I want
[00:10:17] to do is we're going to ingest two
[00:10:18] different things and I'm going to show
[00:10:19] you different ways you can do it. So,
[00:10:21] the first thing that we're going to
[00:10:21] ingest is the Claude Fable 5 and Mythos
[00:10:25] 5 system card. So, I'm going to go ahead
[00:10:26] and download this as a PDF. What I'm
[00:10:28] going to do is take this PDF and I'm
[00:10:29] going to drag it into the raw. So, now
[00:10:31] that PDF lives right there in the raw.
[00:10:33] And then what I'm going to do is we're
[00:10:34] going to take this OpenAI previewing
[00:10:36] GPT-5.6 soul and we're going to just do
[00:10:38] this as a URL instead. So, what I'm
[00:10:41] going to do is I'm going to paste in the
[00:10:42] URL and I'm going to say,
[00:10:44] "Hey Claude,
[00:10:45] read this article and then ingest that
[00:10:48] into our wiki here. And then also, I
[00:10:50] dropped in a PDF in the raw called
[00:10:52] Claude Fable 5 and I want you to also
[00:10:55] ingest that." And that is all that I'm
[00:10:57] going to tell this model. Once again, it
[00:10:59] should be understanding how this is set
[00:11:01] up. We should see a new record in the
[00:11:04] index as well as a new record in the log
[00:11:06] and some new sources in the wiki. So,
[00:11:08] whether Fable decides to turn this PDF
[00:11:10] into one or five or maybe even 50 wiki
[00:11:14] pages because of how big that PDF was,
[00:11:16] same thing with the URL, I will let you
[00:11:18] guys know when this finishes up.
[00:11:23] Okay, so that finished up. It took about
[00:11:24] 10 to 12 minutes and you can see here
[00:11:26] that out of those two sources, it
[00:11:27] created 20 wiki pages and they're fully
[00:11:30] cross-linked. Now, look at this. The
[00:11:31] connection that made this worth having
[00:11:33] as a wiki instead of two separate
[00:11:34] summaries, the two sources reference
[00:11:36] each other, and Frontier Model
[00:11:38] Cybersecurity is where that lives.
[00:11:39] OpenAI benchmarked GPT-5.6 Soul against
[00:11:42] Mythos Preview, and I flagged the thing
[00:11:44] easy to miss reading them separately.
[00:11:46] OpenAI compared to the April
[00:11:47] predecessor, not to Mythos 5, and the
[00:11:49] two labs used different harnesses, so
[00:11:51] the numbers don't line up directly. So,
[00:11:53] anyways, let's go ahead and pull open
[00:11:55] this wiki full screen and take a look.
[00:11:57] Okay, so this is what it looks like. You
[00:11:58] can see we've got OpenAI down here, and
[00:12:00] these are the ones that it relates to,
[00:12:01] like the
[00:12:03] Claude code said, it referenced Claude
[00:12:05] Mythos 5 in the article. So, that's
[00:12:06] pretty cool. And we can see sort of the
[00:12:08] distribution here. We can see how much
[00:12:10] we've got things like
[00:12:11] government-coordinated model releases.
[00:12:12] We've got layered safeguards,
[00:12:14] competitive use safeguards. And if we go
[00:12:16] over here to the wiki, we can see that
[00:12:17] we have concepts, we have entities, we
[00:12:20] have sources, and then we have topics.
[00:12:22] So, the entities is cool because in here
[00:12:24] we have models. We've got Fable, Mythos,
[00:12:26] Mythos Preview, Opus 4.8, GPT-5.6. We've
[00:12:29] got Tropic and OpenAI. And then if we go
[00:12:32] to the log, you can see this was the
[00:12:33] initial setup, and then we had the
[00:12:35] OpenAI article and the Claude Fable 5
[00:12:37] system card. So, the lesson here is that
[00:12:40] we now have this system where we have
[00:12:42] Claude code that looks at a bunch of our
[00:12:44] data sources, right? It looks at the
[00:12:46] wiki, and it looks through potentially
[00:12:47] multiple wikis. And inside the wiki,
[00:12:49] what happens is there are routing rules
[00:12:51] set up so that our agents are able to
[00:12:54] figure out where to look for what
[00:12:56] specific thing, like the data that it's
[00:12:58] looking for, because it has to crawl
[00:12:59] through basically all of this in an
[00:13:01] efficient way, so it's not wasting our
[00:13:02] time and our tokens to find the right
[00:13:04] answer. And that theory is basically
[00:13:06] what Claude code is. It's basically
[00:13:08] figuring out how can my Claude at MD
[00:13:09] work as a router to be able to look
[00:13:11] through my past projects, to be able to
[00:13:12] look through my business context, and
[00:13:14] find the right spot. And so, from here,
[00:13:16] once you've already started to get the
[00:13:17] structure figured out, you're just going
[00:13:20] to start adding more data sources, and
[00:13:21] you're going to watch how this evolves,
[00:13:22] and you're going to constantly check and
[00:13:23] see if it all makes sense. Because if
[00:13:25] you do a batch ingest, and you don't
[00:13:27] like the way that it organized some of
[00:13:28] these folders and files, then maybe you
[00:13:30] go ahead and change it up a little bit.
[00:13:32] You know, you start to open up these
[00:13:33] pages like competitive use safeguards,
[00:13:35] read about it, click through, and see if
[00:13:37] it all still makes sense. And if you
[00:13:38] don't like how things are happening,
[00:13:40] then update the rules in the way that
[00:13:41] you ingest. Like I said, every LLM wiki
[00:13:43] that I've set up, they have different
[00:13:44] structures and a little bit different
[00:13:45] rules because of the type of data that's
[00:13:47] in there. Whether that's meeting
[00:13:49] transcripts or, you know, personal data
[00:13:51] or, you know, proposals, whatever it is
[00:13:54] that you're ingesting here, make it make
[00:13:55] sense. Not only to the AI, but make it
[00:13:57] make sense to you. The whole point is
[00:13:59] that you could also go through this and
[00:14:01] follow the chain and find what you're
[00:14:02] looking for. And the greatest part about
[00:14:04] all this is once you realize, "Oh, look,
[00:14:06] everything in this wiki, it's just a
[00:14:08] markdown file. It's just markdown files
[00:14:09] with routing." That means you're not
[00:14:10] locked down to using this only in cloud
[00:14:12] code. You can connect your Hermes agent
[00:14:13] to this. You can connect Codex to this.
[00:14:15] You can connect whatever you want to
[00:14:16] this because it's just markdown files.
[00:14:18] And if you guys want to learn more about
[00:14:19] the whole idea of like building a second
[00:14:21] brain, then check out this video right
[00:14:22] here where I go over every level of
[00:14:24] building a second brain, and how you
[00:14:25] know if you actually need to like move
[00:14:26] up a little bit or move down a little
[00:14:28] bit, and figure out what's right for you
[00:14:29] and your system. So, anyways, thanks for
[00:14:31] making it to the end of the video, and
[00:14:32] I'll see you guys in the next one.
[00:14:33] Thanks, guys.
