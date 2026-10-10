---
video_id: IRPEfl2BD_c
title: "5 Open Source Repos That Fix 95% of Claude Code's Problems"
channel: Chase AI
url: "https://www.youtube.com/watch?v=IRPEfl2BD_c"
watched_date: 2026-07-08
watched_at: "2026-07-08T22:23:09Z"
watch_count: 1
duration_seconds: 724
source: youtube-history-browser
added_date: 
history_label: Today
history_order: 3
watched_at_precision: date-from-history-label
watched_percent: 63
estimated_watched_seconds: 456
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video reviews five open source tools addressing Claude Code's weak spots: Claude Video (enables video analysis by intelligently sampling frames across four modes—transcript-only, efficient up to 50 frames, balanced up to 100 frames, or unlimited token burner—with Whisper fallback for transcripts), Notebook LM-PI (integrates Google's NotebookLM into Claude Code for free synthesis and research across multiple document types), Graphify (creates knowledge graphs of large codebases and documents, handling PDFs, images, video, and audio without traditional RAG complexity), Impeccable (a 23-command frontend design skill featuring a live browser mode for visual iteration), and Ponytail (reduces token consumption by 20% and speeds up development by 27% through intelligent gates that eliminate unnecessary code generation).

Install Claude Video if you work with video content to avoid expensive Gemini API routing; adopt Notebook LM-PI for research tasks (especially YouTube synthesis) to offload free Google compute; deploy Graphify for navigating large projects or documentation; integrate the Obsidian skills repo if you already use Obsidian; switch to Impeccable's live mode for frontend design to preview changes before committing; and test Ponytail on your workflow, as the benchmarked savings held across Haiku, Opus, and Fable models—disable it if it doesn't fit your use case.

## Transcript

[00:00:00] These are the five open source tools
[00:00:02] that I wish I knew about when I first
[00:00:04] started using Claude Code. Because as
[00:00:07] good as Claude Code is out of the box,
[00:00:09] it still has some weak spots. Namely,
[00:00:12] video, front-end design, memory,
[00:00:15] research, and token output. These are
[00:00:17] five areas that Cloud Code is naturally
[00:00:19] sort of weak in, and we can improve it
[00:00:21] drastically by bringing in these outside
[00:00:23] tools. So, in this video, I'm going to
[00:00:25] show you all five, how you use them, why
[00:00:27] you should care, and the best part is
[00:00:29] they're all free. Now, the first tool on
[00:00:31] our list is Claude Video from Brad
[00:00:33] Automates. This is at a little over
[00:00:35] 5,000 stars, so it's a bit smaller, but
[00:00:37] this is one that's actually trending
[00:00:38] pretty hard lately. And this is all
[00:00:41] about giving Claude the ability to
[00:00:43] ingest video. I don't care about
[00:00:44] generating AI video. I want Claude to be
[00:00:46] able to watch videos that I give it
[00:00:48] because this is a functionality it does
[00:00:50] not have out of the box. In fact, the
[00:00:52] only major AI video model that sort of
[00:00:54] does is Gemini. And if you're someone
[00:00:56] who deals with video, you know what a
[00:00:57] big deal this is because normally we're
[00:00:59] stuck only looking at transcripts. And
[00:01:01] transcripts are great, but sometimes we
[00:01:03] need the context of what's literally
[00:01:05] happening on the screen. The transcript
[00:01:07] isn't enough. But this skill is the best
[00:01:09] of both worlds because we not only get
[00:01:10] the transcript, it's able to
[00:01:11] intelligently pull screenshots or frames
[00:01:14] out of the video itself when it deems
[00:01:16] appropriate. And better yet, if a
[00:01:17] transcript doesn't exist, it will
[00:01:19] actually route it through Grock's
[00:01:20] whisper model, which is totally free to
[00:01:23] generate the transcript. So, if you're
[00:01:24] watching some sort of video that's like
[00:01:26] a Loom or something and doesn't come
[00:01:27] with a transcript or whatever it is,
[00:01:29] we're still okay. Now, the obvious
[00:01:30] question here is, okay, well, like, how
[00:01:32] does this actually work? How are we
[00:01:34] dealing with video? Because we can't
[00:01:35] just magically have Claude watch videos.
[00:01:37] Every video is essentially a frame. So,
[00:01:39] am I throwing it 24 screenshots times
[00:01:42] every second of the video? The answer is
[00:01:44] no. that would get crazy expensive.
[00:01:46] Instead, the skills uses a pretty
[00:01:48] elegant approach where it changes how
[00:01:50] many frames it's going to grab from the
[00:01:51] video based on what mode you put it in.
[00:01:53] So, we have four different modes from
[00:01:54] transcript to token burner. Transcript,
[00:01:56] we're not grabbing any frames. We're
[00:01:58] just taking the captions. For efficient,
[00:02:00] it's just taking the key frames. So,
[00:02:03] those are already dictated by the video
[00:02:04] itself. And we take up to 50 depending
[00:02:06] on the length of the video. We have
[00:02:08] balance, which is where a lot of people
[00:02:09] sit and will take up to 100 frames from
[00:02:12] a video. and it's going to be based on
[00:02:14] the scene changes, which is also taking
[00:02:16] a look at the transcript to see if
[00:02:18] certain words are being used. So,
[00:02:20] balance probably makes the most sense.
[00:02:22] But we also have token burner, which is
[00:02:24] essentially the same as balance, but we
[00:02:26] have no frame cap. You know, you could
[00:02:29] take a,000 frames. The problem with this
[00:02:31] obviously is time it takes to do this
[00:02:34] and the amount of money we're going to
[00:02:35] be spending. Now, Brad, the guy who
[00:02:36] created this skill, also has his own
[00:02:38] YouTube channel where he goes into much
[00:02:39] more technical detail than I am. So, if
[00:02:41] you really want to get, you know, into
[00:02:43] the down and dirty of how this is
[00:02:44] operating, definitely take a look at his
[00:02:47] stuff. As for the installation, it's
[00:02:48] really simple. You're able to install it
[00:02:50] into the marketplace or you can just
[00:02:51] give Claude Code the URL to this skill.
[00:02:54] I'll put that in the comment. But big
[00:02:55] picture, what is this bias? It gives us
[00:02:57] a entirely new capability that Claude
[00:02:59] Code normally does not have without us
[00:03:01] having to do some janky routing through
[00:03:03] Gemini and essentially pay a Gemini API
[00:03:05] on top of Claude. This keeps it all
[00:03:07] inhouse and is a great addition to your
[00:03:10] cloud code stack. Now before we jump
[00:03:11] into the next tool, a quick word from
[00:03:13] today's sponsor, me. So I just released
[00:03:16] my cloud code masterass and is the
[00:03:18] number one way to go from zero to AI
[00:03:20] dev, especially if you don't come from a
[00:03:22] technical background. I assume you have
[00:03:24] no knowledge coming in. We focus on real
[00:03:26] use cases and it also includes a codeex
[00:03:29] masterass. So if you're someone who
[00:03:31] wants to get a little bit more serious
[00:03:32] about AI, make sure to check it out.
[00:03:34] There will be a link to it in the pin
[00:03:36] comment. Now, tool number two is all
[00:03:38] about research because out of the box,
[00:03:40] the simple web search cloud code gives
[00:03:42] us is fine, but it's pretty surface
[00:03:43] level and there's really nothing when it
[00:03:46] comes to a middle ground because the
[00:03:47] opposite end of the spectrum is let's do
[00:03:49] dynamic workflows, let's do deep
[00:03:50] research, let's spin up 105 sub agents
[00:03:52] and burn up 10 million tokens. I don't
[00:03:54] want to do that. You probably don't
[00:03:55] either. So, in comes Notebook LM-PI. For
[00:03:59] all intents and purposes, this tool
[00:04:01] gives us notebook LM inside of Claude
[00:04:04] Code. I can call on Notebook LM through
[00:04:06] the terminal. Everything I can do in
[00:04:08] Notebook LM from the web version and
[00:04:10] more can be done through Claude Code
[00:04:13] because of this skill. It's not just a
[00:04:15] skill, it's also a CLI. And so it's
[00:04:17] essentially like an unofficial API into
[00:04:19] Notebook LM. Now, the cool thing about
[00:04:21] this isn't just like, oh, cool. We get
[00:04:23] notebook LLM functionality, but when you
[00:04:24] think about it, you're kind of getting
[00:04:26] free LLM calls doing this. Now, it's
[00:04:30] Gemini. It's not as powerful as
[00:04:32] something like Opus and certainly Fable,
[00:04:33] but you can offload some research and
[00:04:35] some synthesis onto the Google servers
[00:04:37] for free when you use Notebook LM.
[00:04:39] Whether that's just asking questions
[00:04:40] about videos or whatever. On top of the
[00:04:42] fact that we can just create, you know,
[00:04:45] whatever we want using Notebook LM,
[00:04:47] whether that's, you know, slide decks,
[00:04:50] whether that's infographics, whether
[00:04:51] that's podcast, etc., etc., etc. And
[00:04:53] like I alluded to before, we get stuff
[00:04:55] that goes beyond the web UI itself. And
[00:04:58] we have a full list right here inside of
[00:05:00] the readme. In terms of the
[00:05:02] installation, it has a pretty thorough
[00:05:03] guide, but I'm going to be honest, all
[00:05:05] you need to do, copy the URL, throw it
[00:05:07] into a cloud code. It's going to do the
[00:05:08] rest. It's going to require some things
[00:05:10] like Playright, which is you've never
[00:05:11] used before, is simply a browser
[00:05:13] automation that's going to be completely
[00:05:14] invisible to you when it's running. And
[00:05:16] lastly, if you really can't think of any
[00:05:17] use cases of notebook LM, there's a
[00:05:19] whole list of them right here. For me,
[00:05:21] the biggest one is simply looking at
[00:05:24] YouTube videos. And this kind of goes
[00:05:25] handinhand with what we were talking
[00:05:26] about before with being able to watch
[00:05:27] the videos. The notebook LM is going to
[00:05:30] be just transcript only, but because
[00:05:31] it's under the Google umbrella, like
[00:05:33] it's it's a very seamless process of
[00:05:35] supplying it with YouTube URLs, tons of
[00:05:37] them on a particular topic and then
[00:05:39] being able to synthesize all that
[00:05:40] information at once. Now, tool number
[00:05:42] three is all about memory. And I'll be
[00:05:44] throwing in an additional tool here as
[00:05:46] well. Now, when we talk about memory,
[00:05:48] what we're really talking about is how
[00:05:50] can I have clawed code quickly and
[00:05:53] effectively answer questions about very
[00:05:55] large code bases or very large corpuses
[00:05:59] of documents. I want to be able to give
[00:06:01] Claude Code a map that it can very
[00:06:03] easily traverse to find answers for me
[00:06:05] about a bunch of different questions
[00:06:06] that are related to my documents, my
[00:06:08] work, my code. Well, that is exactly
[00:06:10] what Graphy does. It essentially creates
[00:06:12] a knowledge graph of whatever code base
[00:06:14] you give it. And you see that right
[00:06:15] here. It breaks out all the parts. It
[00:06:17] turns them into nodes. It clusters them
[00:06:19] according to what they're actually
[00:06:21] about. That way, again, we're handing
[00:06:23] Cloud Code a map. So, when we ask
[00:06:24] questions about things about this
[00:06:26] codebase, there's a very clear path
[00:06:28] forward from your question to the
[00:06:30] answer. The thing you need to know,
[00:06:31] though, is Graphify is not a rag system.
[00:06:34] There's no vector index. There's no
[00:06:35] embedding. This is not light rag. This
[00:06:38] is somewhere in between obsidian and a
[00:06:41] true rag system. But we can kind of get
[00:06:44] like a light version of graph rag if
[00:06:46] that kind of makes sense. It's not as
[00:06:48] complicated as traditional rag yet we're
[00:06:50] able to get a lot of the same benefits
[00:06:51] in terms of the memory. Now the other
[00:06:53] cool thing about Obsidian versus
[00:06:55] something like Graphify is it can handle
[00:06:56] a number of different files. Like we're
[00:06:58] not talking just markdown. We can handle
[00:07:00] stuff like PDFs. We can do images. We
[00:07:02] can do video and audio on and on and on.
[00:07:04] So it's very very flexible. But speaking
[00:07:06] of Obsidian and knowledge graphs and
[00:07:07] this sort of thing, let's kind of talk
[00:07:08] about that bonus tool I alluded to
[00:07:10] earlier. And that is the Obsidian skills
[00:07:12] repo. I don't see enough people talking
[00:07:14] about this. This is actually created by
[00:07:16] the CEO of Obsidian. It's very simple.
[00:07:19] It's just a handful of skills, but if
[00:07:20] you're someone who uses Obsidian with
[00:07:22] Claude Code, this is a easy way to
[00:07:24] supercharge it. You're essentially
[00:07:25] teaching Cloud Code the best practices
[00:07:28] by the people who actually created
[00:07:30] Obsidian. So, don't sleep on this repo
[00:07:32] even though it's super simple. That'll
[00:07:33] be linked below as well. Now, tool
[00:07:34] number four is all about front-end
[00:07:36] design, and that is impeccable. This is
[00:07:37] quickly becoming my favorite front-end
[00:07:39] design skill, and tons of people are
[00:07:41] noticing it. It's not just that it has a
[00:07:42] ton of stars. It's actually like
[00:07:44] officially part of GitHub's AI package
[00:07:46] itself. And what we're looking at right
[00:07:47] here is Impeccable's website, and it's
[00:07:49] here. I'll explain how this tool
[00:07:51] actually works. So, Impeccable is one
[00:07:54] skill, but it has 23 different commands.
[00:07:56] And you can see all those commands over
[00:07:58] here on the left that I'm going through.
[00:07:59] Things like craft, shape, critique,
[00:08:01] layout, colorize. and they're
[00:08:02] essentially having the skill do certain
[00:08:04] things with your claude code setup. So
[00:08:06] colorize, for example, if I do
[00:08:08] impeccable colorize, what's going to
[00:08:09] happen? It's going to add strategic
[00:08:11] color to monochrome interfaces. What's
[00:08:13] nice here on the website is I can see a
[00:08:15] before versus an after. And so you can
[00:08:19] see, all right, here's what it would
[00:08:20] normally look like with clawed code and
[00:08:22] the standard cloud code front-end design
[00:08:23] skill versus impeccable. And you can see
[00:08:26] there's a bit more going on here. It
[00:08:28] looks a bit nicer. Same thing for, you
[00:08:30] know, boulder, right? Clawed code,
[00:08:34] impeccable boulder. And there's 23
[00:08:36] different commands here, which are
[00:08:37] obviously like kind of difficult to
[00:08:39] explain, and it's much easier just to
[00:08:41] see them in action. So, highly suggest
[00:08:43] you do that. The other really cool thing
[00:08:44] with impeccable is the live mode. And
[00:08:46] this definitely gives you shades of claw
[00:08:48] design. The idea is that if I run
[00:08:50] impeccable live, what's going to happen
[00:08:52] is it's actually going to bring up my
[00:08:54] web page on the local host on my
[00:08:56] browser. So instead of trying to edit
[00:08:59] everything through the terminal via
[00:09:00] code, I will now have the page up on my
[00:09:02] browser. I can click on different
[00:09:04] components. I can see what it looks like
[00:09:06] with and without impeccable. And it
[00:09:08] becomes a visual design tool, which is
[00:09:10] way better when we're talking about
[00:09:12] front design versus like, hey,
[00:09:13] impeccable, make that look nicer. Uh,
[00:09:15] okay, try again. Uh, make it more
[00:09:17] premium, right? So you can actually see
[00:09:19] it before you commit it. I think this is
[00:09:21] a huge step above the anthropic
[00:09:23] front-end design skill and also a huge
[00:09:25] step above things like UIUX Pro Max.
[00:09:27] Now, last but not least is Ponytail and
[00:09:30] this is all about token consumption.
[00:09:32] Tokens, tokens, tokens. You hear about
[00:09:34] this all the time and how expensive they
[00:09:36] are, especially with Fable. So, it only
[00:09:38] makes sense we look outside of Claude
[00:09:41] code to see are there any skills or
[00:09:43] frameworks that can reduce the amount of
[00:09:45] tokens we are spending while still
[00:09:47] maintaining the same level of
[00:09:49] effectiveness. you know, it does us no
[00:09:51] good if we reduce our token count, but
[00:09:52] it gets worse. Well, Ponytail claims to
[00:09:55] be able to do this. In fact, it claims
[00:09:58] that it makes Claude Code 20% cheaper,
[00:10:01] 27% faster, while still giving the same
[00:10:04] results, which is kind of wild. Now, the
[00:10:06] way Ponytail essentially works is it's
[00:10:09] saying, "Hey, we're going to give Claude
[00:10:11] code these series of, you know, gates it
[00:10:14] needs to pass where essentially we ask
[00:10:15] it, hey, do you actually need to build
[00:10:17] it? Does that feature you're trying to
[00:10:18] create already exist? is it a library
[00:10:21] etc etc etc before finally saying okay
[00:10:23] you want to build this great thumbs up
[00:10:26] just use the least amount of code that's
[00:10:28] kind of how it works in a nutshell gets
[00:10:29] a little more complicated than that but
[00:10:32] I wanted to have you take a look here at
[00:10:34] the benchmarks because this is what we
[00:10:35] care about in the gray what do we have
[00:10:37] we have the baseline and then in the
[00:10:39] green we have ponytail and you can see
[00:10:42] way less lines of code way less tokens
[00:10:45] way cheaper and way less time now what
[00:10:48] is the catch catch. Well, the catch is
[00:10:50] they did these benchmarks with Haiku.
[00:10:52] You at this point are using Opus or
[00:10:53] you're using Fable. So, does this hold
[00:10:56] up? Well, I actually did test I did a
[00:10:58] whole video on Ponytail with Opus and it
[00:11:01] actually was even cheaper and quicker
[00:11:04] than what we see with Haiku. So, the
[00:11:06] benefits were greater with Opus. I then
[00:11:08] tried it again with Fable and same
[00:11:10] thing. So, across the board when I ran
[00:11:12] these same benchmarks and anyone can if
[00:11:14] you go on this repo, they have all the
[00:11:16] benchmarks listed here. So you can test
[00:11:17] this yourself. Ponytail reduced it and
[00:11:20] it was the same output. Now benchmarks
[00:11:22] versus real life. Is it the same? Who's
[00:11:25] to say? It probably depends on your
[00:11:27] particular use case and how complicated
[00:11:28] it is. But any chance we can make cloud
[00:11:32] code faster and cheaper and have the
[00:11:34] same level of effectiveness. I think we
[00:11:36] should try it out. Worst case scenario,
[00:11:37] you do a couple runs, you don't like it,
[00:11:38] you get rid of it. But I think this is
[00:11:40] worth your time. There's other ones in
[00:11:42] the same vein like Caveman that I also
[00:11:44] think you should take a look at. So,
[00:11:46] those are the five open source tools
[00:11:47] that I wish I knew about when I first
[00:11:49] started with Claude Code. And if you're
[00:11:51] brand new, I hope I was able to at least
[00:11:53] point you in the right direction in a
[00:11:55] few of these areas. As always, let me
[00:11:57] know what you thought in the comments.
[00:11:58] Make sure to check out Chase AI Plus if
[00:12:00] you want to get your hands on the
[00:12:01] masterass. And besides that, I'll see
[00:12:03] you
