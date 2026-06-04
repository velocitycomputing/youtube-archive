---
video_id: 57lDpTwiW6g
title: "Tokenmaxxing: How Top Builders Use AI To Do The Work Of 400 Engineers"
channel: Y Combinator
url: "https://www.youtube.com/watch?v=57lDpTwiW6g"
watched_date: 2026-06-03
watched_at: "2026-06-03T12:00:00Z"
watch_count: 1
duration_seconds: 2489
source: youtube-history-browser
history_label: Yesterday
history_order: 25
watched_at_precision: date-from-history-label
watched_percent: 68
estimated_watched_seconds: 1693
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Garry Tan, YC president, returned to coding after 13 years away and shipped hundreds of thousands of lines of code in months using Claude AI—delivering 400x more work than he did when actively coding. He built Garry's List (a full-featured blogging platform with agentic research capabilities for investigating California policy issues) in 5 days for $200, compared to the original Posterous which cost $4M and took 1.5 years with 7 people. He developed G Stack, a system of reusable Claude prompts (CEO planning, architecture review, code quality, testing, design review) that automate development workflows. The core philosophy is "token maxing"—aggressively consuming context and compute to solve problems comprehensively rather than settling for minimal solutions—and separating "markdown" (human-driven logic and decisions) from "code" (deterministic operations), with 80-90% test coverage as standard practice.

For builders: Use Claude Code's plan mode with structured prompt templates to design before implementing, and create reusable skill collections for your repeated workflows. Automate QA with browser-testing tools (Playwright) combined with AI prompts to replace manual testing. Apply token maxing to knowledge work—do exhaustive research with multiple sources, deep dives, and cross-referencing rather than surface-level answers. Choose your AI tool strategically (Claude for ADHD-friendly iteration, Codex for deep problem-solving, Claude Code for execution). Build systems with 80-90% test coverage as default. Accept that AI tools are powerful but require you to stay involved as a mechanic ready to diagnose and fix failures.

## Transcript

[00:00:00] I think that's like the defining
[00:00:02] question. Like, will you have control
[00:00:04] over your own tools or will your tools
[00:00:06] have control over you? Using open cloud
[00:00:09] these days is like driving a Ferrari and
[00:00:12] it's like exhilarating. It's insane.
[00:00:14] Like, you get to do things like it
[00:00:16] figures things out you would never think
[00:00:17] a machine could figure out and it does
[00:00:19] it so quickly, but then it's also like a
[00:00:22] Ferrari and that you better be a
[00:00:23] mechanic.
[00:00:24] Like, it's a Ferrari that will break
[00:00:26] down on the side of the road you know,
[00:00:28] when you most need it and you need to
[00:00:30] get out with your wrench and pop the
[00:00:32] hood and like fix it, you know, you're
[00:00:34] going to have to fix it yourself. And
[00:00:35] so, this is a very exciting time
[00:00:37] >> [music]
[00:00:37] >> in uh computer science and technology.
[00:00:47] Welcome back to a special episode of the
[00:00:49] Light Cone. In this episode, we're going
[00:00:51] to talk about how Garry Tan got back to
[00:00:53] building.
[00:00:55] If you follow us on Twitter, you'll know
[00:00:56] that after a multi-year hiatus to become
[00:00:59] an investor, Garry Tan is back to being
[00:01:01] a builder and in the last couple months
[00:01:03] he shipped hundreds of thousands of
[00:01:05] lines of code and built popular open
[00:01:08] source projects that have gone from
[00:01:09] nothing to more than 100,000 stars on
[00:01:11] GitHub. And he did all of this while
[00:01:13] having a very demanding job running YC
[00:01:16] full-time. A lot of people on the
[00:01:18] internet don't even think that this is
[00:01:19] possible and are somewhat like in
[00:01:21] disbelief, but it actually happened. We
[00:01:23] know because we were here to see the
[00:01:24] whole thing. And so, today we're going
[00:01:26] to talk about how he did it.
[00:01:27] >> Well, I'm relatively uh shocked myself.
[00:01:31] >> [laughter]
[00:01:31] >> I'm amazed as well. It was 13 years of
[00:01:33] not coding and then suddenly boom, I'm
[00:01:35] doing about 400x the amount of work that
[00:01:37] I was that year the last time I was even
[00:01:39] sort of like 2/3 of the time writing
[00:01:42] code. Baby, to start things off, how
[00:01:44] would we go back to the project that
[00:01:46] started it all off, which was Garry's
[00:01:47] List?
[00:01:48] >> Oh, yeah.
[00:01:48] >> And just like talk about a few months
[00:01:50] ago how you powered up Cloud Code and
[00:01:52] like started to get back to coding.
[00:01:54] >> And it was right after one of the Light
[00:01:55] Cone episodes, right?
[00:01:56] >> Oh, yeah, definitely. I realized that I
[00:01:59] wanted to bring together all the people
[00:02:01] who believed what I believed, um
[00:02:03] particularly for California. And so, I
[00:02:06] started a
[00:02:08] uh 501c4, and now it's a c3 and a PAC,
[00:02:11] which is sort of what a lot of political
[00:02:13] groups do. Um it's a very common way to
[00:02:16] bring people together. You know,
[00:02:17] everyone focuses on the money, but we're
[00:02:19] trying to bring together smart people.
[00:02:22] Um you know, what I learned in the years
[00:02:24] of working in San Francisco politics is
[00:02:26] that bringing together people is so
[00:02:28] powerful. And uh that's what a mass
[00:02:31] social movement is. And I said, "Okay,
[00:02:33] well, why don't I just make a website
[00:02:36] where we start doing that?" And it would
[00:02:37] just start with um why don't I start
[00:02:40] writing about the issues that I'm
[00:02:42] worried about. It's like, I want
[00:02:44] children in school, you know, people
[00:02:46] watching this from all around the world
[00:02:47] might find it very, very strange, like I
[00:02:50] find it strange, that uh it was not
[00:02:52] possible and still very, very hard for a
[00:02:56] seventh grader or eighth grader in
[00:02:58] middle school in San Francisco public
[00:03:00] schools to be able to take algebra. And
[00:03:04] that was,
[00:03:05] you know, a math education thing. Like,
[00:03:07] I you know, if I didn't get to do that
[00:03:08] when I was in public schools in the East
[00:03:10] Bay of the Bay Area,
[00:03:12] there's no way I would have studied
[00:03:13] engineering at Stanford. I never would
[00:03:15] have written code. I never would have
[00:03:17] been able to do any of these things. So,
[00:03:18] it was close to my heart, and I realized
[00:03:20] like, "Hey, it's time to write code."
[00:03:21] And I ended up building Posterous, my
[00:03:24] first YC startup from 2008.
[00:03:27] >> What what was Posterous for people who
[00:03:28] don't remember it? Yeah, Posterous was
[00:03:30] uh that simple blogs by email. It grew
[00:03:32] to be a top 200 website on the internet,
[00:03:34] and then Twitter ended up buying it for
[00:03:36] about $20 million. So, that was sort of
[00:03:37] like my first bag, really. I actually
[00:03:40] built it again uh as Posthaven when
[00:03:44] Twitter um you know, bought it for the
[00:03:46] amazing people that we had hired, and uh
[00:03:49] they shut down the startup. It would
[00:03:50] have cost a couple million dollars to
[00:03:52] buy it back from Twitter and at the time
[00:03:54] I had no money in the world, so the next
[00:03:56] best thing was why don't I write it
[00:03:58] again? And then in January of this year,
[00:04:01] I ended up writing it a third time.
[00:04:04] Only, you know, the first time it took
[00:04:07] about, you know, $4 million
[00:04:09] and, you know, six or seven people and
[00:04:12] about a year and a half. And then the
[00:04:13] second time it, you know, took about, I
[00:04:16] don't know, 100 grand and two people, me
[00:04:18] and my co-founder Brett Gibson, who now
[00:04:21] runs Initialized. Um, and maybe like 3
[00:04:25] months or so.
[00:04:26] And then in this case it took about
[00:04:28] $200, which was my Claude code Max
[00:04:31] account, and probably 5 days.
[00:04:34] Full-featured blog platform, does
[00:04:36] everything you want. And then on top of
[00:04:38] that, like full rag, full um, agentic
[00:04:42] retrieval, like be able to, you know,
[00:04:45] sort of go out and read all of the
[00:04:47] internet, like every tweet I've ever
[00:04:48] done. Recursive crawl, deep research of
[00:04:52] any topic. The algebra thing is just one
[00:04:54] of a whole lot of different issues that
[00:04:56] we really, really care about. And to be
[00:04:58] able to go ingest the internet, you
[00:05:00] know, see all the arguments for and
[00:05:02] against, and then to craft incredibly
[00:05:05] detailed um, reports on the back end
[00:05:08] about um, what are all the quotables?
[00:05:10] Like, I think people who are big
[00:05:12] followers of the Light Cone might
[00:05:13] remember one of our first episodes about
[00:05:16] agentic uh, systems with Jake Heller.
[00:05:19] Actually, so Jake created Case Text and
[00:05:22] he described exactly what I ended up
[00:05:25] building for basically journalistic uh,
[00:05:28] long-form articles about any, you know,
[00:05:31] sort of issue or uh,
[00:05:33] you know, piece of news that was
[00:05:34] happening. And so, you know, anyone can
[00:05:36] go to Gary's list.org today and you
[00:05:38] know, we do about two or three
[00:05:40] relatively, you know, researched, all
[00:05:42] fully sourced um, articles about what's
[00:05:45] going on in California, in San
[00:05:47] Francisco, and LA and like how do we
[00:05:49] build a better government?
[00:05:50] >> is the thing I feel like people missed
[00:05:51] about Gary's list they don't fully get
[00:05:54] is that it's like the classic thing
[00:05:55] we've been talking about here which is
[00:05:56] like software was you build software to
[00:05:59] let people use it. So it was like you
[00:06:00] build a blogging platform and people
[00:06:02] like write blogs and maybe like they
[00:06:04] start their own Substack eventually or
[00:06:06] they write articles. But Gary's list is
[00:06:08] both blogging platform but it actually
[00:06:11] does the work of a high quality
[00:06:13] investigative journalist. It's not just
[00:06:15] something that a journalist uses to
[00:06:16] publish their articles.
[00:06:17] >> Yeah, I mean basically the for the
[00:06:19] equivalent of like five or ten dollars
[00:06:21] of Opus calls, I mean I would estimate
[00:06:23] that it does the work of like, you know,
[00:06:25] a real human being that would have to
[00:06:28] like go painstakingly through dozens of
[00:06:31] articles, read entire books about
[00:06:34] certain subjects, uh annotate them. I
[00:06:36] mean going back to the case text example
[00:06:38] like the thing that Jake taught me was
[00:06:41] that you need to think about what a
[00:06:43] human would do with the context given.
[00:06:45] Like what would it retrieve? Like does
[00:06:47] it go to the library? What kind of book
[00:06:49] would it look for? What does it search
[00:06:51] on for search, you know, on the web? I
[00:06:52] mean the great thing now is like you
[00:06:54] don't have to just do that. Like you can
[00:06:55] get Perplexity's API and you can do deep
[00:06:59] research there. You have X's API, you
[00:07:01] can do deep research there. You know,
[00:07:03] Grok's API if you need to like do
[00:07:05] research on X using the Grok API is
[00:07:08] actually very, very good. And you can
[00:07:09] just grab all of the context. This is
[00:07:12] sort of going back to the philosophy of
[00:07:14] boil the ocean which is one of my
[00:07:16] essays. It's like particularly when
[00:07:17] building a Gentex software now,
[00:07:20] you don't have to settle for um
[00:07:23] what we did when we were humans writing
[00:07:25] the code. Like and that goes for
[00:07:27] research as well. What if you absolutely
[00:07:29] boil the ocean? Like what is, you know,
[00:07:32] the total completionist like if you were
[00:07:34] a human this would take you about a
[00:07:36] month to do this research, you can just,
[00:07:39] you know, zap the rocks harder.
[00:07:41] Uh you know, it you pay more money and
[00:07:44] you might be token maxing, but you
[00:07:46] should token max. Like, basically, if
[00:07:48] there is incremental work that makes
[00:07:51] something more complete, more awesome,
[00:07:53] more uh, you know, in the case of um,
[00:07:56] this type of writing, like, we want it
[00:07:57] to be more representative of reality.
[00:08:00] Like, you know, we don't just settle for
[00:08:02] one source when we can get 20 sources
[00:08:05] and we can cross-reference them. We can
[00:08:06] figure out like, well, these 13 sources
[00:08:09] say this and seven sources disagree with
[00:08:11] that. And then, you know, you want to
[00:08:13] feed all of that context into like your
[00:08:15] core prompt and then you can
[00:08:17] basically make a better decision than
[00:08:20] what you would like just, you know, a
[00:08:21] human being clicking on a link, reading
[00:08:23] a headline, and that's all you
[00:08:25] understand. And I think if you token
[00:08:26] max, like, that's actually the coolest
[00:08:28] thing you can do now. And it's not just
[00:08:30] in, you know, generating articles. It's
[00:08:33] not, you know, it's clearly in uh,
[00:08:35] writing code, right? I think now it's
[00:08:38] it's going to permeate every part of
[00:08:39] society. Like, every thing that we would
[00:08:42] call knowledge work could be token
[00:08:44] maxed. And um, I don't think that it
[00:08:47] means that we're going to get rid of
[00:08:48] people. I think it means that people
[00:08:51] need to still supply uh, the agency.
[00:08:53] Like, I need this. Like, I'm the one
[00:08:55] who's sitting here caring about algebra.
[00:08:57] Like, I want kids like me who couldn't
[00:08:59] afford private school. You know, San
[00:09:01] Francisco is the one city in the world
[00:09:04] that has the highest rate of private
[00:09:06] school attendance, um, probably in the
[00:09:08] entire country, actually. And that's not
[00:09:10] okay. Like, you shouldn't have to be
[00:09:12] rich to have a good education. And, you
[00:09:15] know, I don't know why that's
[00:09:16] controversial. And so, for me, it's like
[00:09:18] this, you know, mass sort of a shift in
[00:09:22] technology was happening and then, uh, I
[00:09:25] had a need and a want and a desire and
[00:09:28] it was a burning desire. Like, I it
[00:09:30] hurts me and pains me to think about 10,
[00:09:32] 12, 13-year-old kids who don't know
[00:09:35] algebra and like could have, but uh some
[00:09:38] bureaucrat or, you know, some
[00:09:40] virtue-signaling person in power says
[00:09:43] like actually I don't want that kid who
[00:09:45] wants to learn algebra to learn it. So,
[00:09:48] I think in this process of basically
[00:09:50] solving your own pain and need from the
[00:09:53] young Gary and building Gary's list, you
[00:09:57] sort of discover a lot of patterns on
[00:10:01] token maxing and this new way of
[00:10:02] building that led you to the next
[00:10:04] project, which was uh G stack. Like I
[00:10:08] actually did not plan to make G stack.
[00:10:11] All I did was like I uh realized that I
[00:10:14] was doing the same things over and over
[00:10:17] again, and then I got sick of typing the
[00:10:19] same thing, so I went into my Apple
[00:10:21] Notes. I typed in all the things that I
[00:10:23] found myself writing over and over again
[00:10:25] into Claude code. And it was pretty
[00:10:28] simple stuff. It's like here's the plan
[00:10:29] review. One of the things I started
[00:10:32] doing is I really love asking Claude to
[00:10:35] make ASCII art diagrams. One of the
[00:10:37] things I discovered is um sometimes
[00:10:40] Claude would just get confused and like
[00:10:42] write bugs or not be complete. But once
[00:10:45] I started saying, "Actually, before you
[00:10:47] start your work, make an ASCII diagram
[00:10:49] of all the data flows, all the inputs
[00:10:51] and outputs, what are the user flows,
[00:10:53] what are the error messages." And you
[00:10:55] can see this. It's like data flow, state
[00:10:57] machines, dependency graphs, processing
[00:10:59] pipelines, decision trees. Once it did
[00:11:01] that, it loaded all of the context in,
[00:11:04] and then it just did the work more
[00:11:06] completely. Like it boiled the ocean
[00:11:07] better. And it broke down into a bunch
[00:11:09] of different sections. Like here's
[00:11:10] architecture review, code quality, test.
[00:11:14] I mean, one of the things I learned
[00:11:15] building Gary's list was that when I was
[00:11:17] writing the code myself, I would always
[00:11:19] do the minimum amount of testing
[00:11:22] cuz it's just like not very fun. I knew
[00:11:23] I needed to have it, but I'm here to
[00:11:25] write, you know, fun new code. I, you
[00:11:28] know, did not like write to write tests.
[00:11:30] And then honestly, like I hit all the
[00:11:32] things that everyone else hits when they
[00:11:33] start bike coding, which is like this is
[00:11:35] slop, it's not working that well, like
[00:11:38] it works fine for the 80% case, but if
[00:11:40] any users actually touch it, it starts
[00:11:42] falling over. And then that's when I
[00:11:43] realized, oh, I can get to 100% test
[00:11:46] coverage. I've since learned that 100%
[00:11:48] is probably too much, like hitting 80 to
[00:11:51] 90% is usually the best practice at this
[00:11:53] point. Um but yeah, this this is
[00:11:55] basically the first version of
[00:11:58] plan-eng-review.
[00:12:00] I know everyone knows the office hour
[00:12:02] skill, uh which is, you know, what
[00:12:04] people can use and I still use when I'm
[00:12:06] trying to make a brand new product or a
[00:12:08] brand new feature. It uh simulates what
[00:12:11] a what we do when we're working with a
[00:12:13] company. It's like, how do you know that
[00:12:15] people want this, you know, who's it
[00:12:17] for, what does it do, and what's the
[00:12:19] impact, right? But this is like the
[00:12:20] proto skill, like this is I didn't even
[00:12:22] know skills existed, and I posted this
[00:12:24] and it went viral, like you know,
[00:12:26] 200,000 people saw that. And then I made
[00:12:29] another version of it that was a much
[00:12:31] more
[00:12:32] uh expensive version. I called it the
[00:12:33] mega plan, and then I ended up um
[00:12:36] renaming it to the CEO plan. We've
[00:12:39] probably talked about meta prompting
[00:12:40] before. I used meta prompting here. I
[00:12:42] took the other review plan that we had,
[00:12:45] and then uh I said, "Okay, well, let's
[00:12:48] do a version of this, but like imagine
[00:12:50] Brian Chesky sitting with you, right?
[00:12:52] Like Brian Chesky has this great line
[00:12:54] about uh what is a 10-star experience?"
[00:12:57] So, and you know, the point of it is
[00:12:59] everyone thinks about hotels in terms of
[00:13:01] like three This is a two three-star
[00:13:03] experience, is a four-star experience,
[00:13:04] and he like goes, you know, through the
[00:13:06] list, like five stars, it's like
[00:13:08] everyone, you know, yeah, cool, like
[00:13:10] he's like, "What's a six-star? And
[00:13:11] what's a seven-star? And what's an
[00:13:12] eight-star?" And like he goes all
[00:13:14] through that entire list. And um
[00:13:17] that's one of my favorite like product
[00:13:18] and design exercises to go through like
[00:13:21] as a mental exercise, and then the cool
[00:13:23] thing is like you can do that every
[00:13:24] single time now. And so, that's what
[00:13:26] this is, You know, this prompt basically
[00:13:28] tries to figure out what is the platonic
[00:13:31] ideal of
[00:13:33] what this is. These are sort of like
[00:13:34] three the two things that are pretty
[00:13:36] awesome. One is what is the 10x check?
[00:13:39] What is more ambitious and delivers 10x
[00:13:42] more value for only 2x the effort.
[00:13:46] Right? And so, for whatever reason
[00:13:47] coming out of latent space, this helps
[00:13:49] the model like really visualize. Like
[00:13:52] so, I'm plan CEO skill I actually really
[00:13:54] enjoy because I'm an ADHD CEO and I love
[00:14:00] potential, like pure potential. And so,
[00:14:02] this is like the one like I can't
[00:14:03] believe this is just literally two
[00:14:05] little sentences. But like this unlocks
[00:14:08] an incredible amount. And so, that's how
[00:14:10] G G stack started actually not as you
[00:14:13] know, I didn't want it to be anything
[00:14:14] other than like, well, I just need to
[00:14:16] make some skills. And I had heard that
[00:14:18] people were making like skill repos.
[00:14:21] But then the third thing I did was I
[00:14:23] started using these two skills so much
[00:14:26] that my conductor instance was getting
[00:14:29] very backed up. So, this is how I use
[00:14:31] conductor. This is actually my real
[00:14:33] setup like Okay. So, this is your like
[00:14:36] daily workflow. This is how you've been
[00:14:37] shipping hundreds of thousands of lines
[00:14:38] of code a month. It's all it's all in
[00:14:40] here.
[00:14:40] >> Yeah, that's right. So, I dropped like
[00:14:41] 13 PR's in the last 48 hours. And then,
[00:14:45] you know, I you just queue them up. Like
[00:14:47] anytime I come up with a new idea, I
[00:14:49] come in and here it is. You know, I love
[00:14:53] using the CEO skill. I love using the
[00:14:55] engine skill to like really make it
[00:14:57] super well tested. I did that all in
[00:14:59] plan mode. And then I'd click approve
[00:15:02] here and then, you know, Claude would go
[00:15:04] and do all the stuff. And then I did
[00:15:06] that so much that I ended up having like
[00:15:09] 15 different features that were all
[00:15:12] queued up waiting for me to manually
[00:15:14] test it. Like it passed it you know, it
[00:15:15] passed end-to-end testing. It passed
[00:15:17] integration. It passed unit tests. But
[00:15:20] like at the end of the day, I still need
[00:15:22] to, you know, for Garry's list, it's
[00:15:24] like pop open the Rails server and like,
[00:15:27] you know, load that user and like make
[00:15:29] it into that configuration for that
[00:15:30] particular user and like manually just
[00:15:33] make sure it works. And I got sick of
[00:15:35] doing that and I was trying to use um
[00:15:37] Claude in code MCP and it was very, very
[00:15:41] slow. Two to three seconds for every
[00:15:43] turn. I was like, this is not usable for
[00:15:45] QA. But I had heard that Microsoft had
[00:15:48] released Playwright, which is sort of um
[00:15:50] an alternative testing framework. In
[00:15:53] retrospect, it's like actually there was
[00:15:54] like agent uh there like agent harness
[00:15:57] and like all these other like tools that
[00:15:58] I could have used, but the upside and
[00:16:00] downside of Claude code is it's so easy
[00:16:02] to just start something that I just
[00:16:04] popped open like I literally went in
[00:16:05] here and this is probably what I did.
[00:16:08] It's like, I'm so sick of using Claude.
[00:16:10] [laughter]
[00:16:11] Claude in
[00:16:13] in Chrome MCP, it's too slow. Let's go
[00:16:17] ahead and wrap Microsoft's Playwright.
[00:16:24] Can we do that?
[00:16:26] And then I just pressed enter and then,
[00:16:27] you know, one of the things that emerged
[00:16:28] with G stack is it like this is how I
[00:16:30] create new features now. Of course, you
[00:16:33] know, what it's going to do now is like,
[00:16:34] hey dude, you already did that, which is
[00:16:36] hilarious. You know, I have bug fixes
[00:16:38] right next to giant features and then um
[00:16:41] the way G stack works, there's a CEO,
[00:16:43] there's a designer, there's actually a
[00:16:45] developer experience person in there.
[00:16:47] There's a number of design tools uh
[00:16:50] and then plan eng is the last one and
[00:16:52] then I actually usually run {slash}
[00:16:54] codex and I recently added a {slash}
[00:16:56] Claude in codex. So, one of the cool
[00:16:59] things that I actually learned from uh
[00:17:01] YC alums, I came to an event and brain
[00:17:04] totally frazzled, but you know, went to
[00:17:06] one of our batch events and we're just,
[00:17:08] you know, shooting the about what's
[00:17:10] going on with Claude code versus codex
[00:17:13] and at the time I was a total Claude
[00:17:15] code only guy
[00:17:17] and uh I realized, oh, a lot of people
[00:17:19] actually prefer Codex. Why is that? And
[00:17:21] I discovered that Claude code is ideal
[00:17:23] for the ADHD CEO. But once in a while,
[00:17:27] there's a you know, Claude code will
[00:17:28] just BS a bunch of stuff. Like Claude
[00:17:30] models are very, very good, but like
[00:17:32] they are not the smartest, it turns out.
[00:17:34] And so a lot of people, you know,
[00:17:35] explained to me that if you have a
[00:17:37] problem that's much crazier, you need
[00:17:40] the 200 IQ nearly non-verbal CEO.
[00:17:44] So you can just call in a friend, and
[00:17:46] then that's what like {slash} Codex is.
[00:17:48] It's a you know, G stack skill that
[00:17:49] takes whatever plan it your plan is, or
[00:17:52] if you're out of plan mode and you
[00:17:53] already implemented, it'll take your
[00:17:54] repo, and it'll run Codex in a command
[00:17:57] line prompt with the prompt that says
[00:17:59] find all the problems and all the bugs,
[00:18:01] and it reports it back to Claude code,
[00:18:03] and then you and Claude code can work
[00:18:05] through those that feedback.
[00:18:07] And then I have since added, if you use
[00:18:09] Codex as your main coding agent, you can
[00:18:12] actually go and type {slash} Claude and
[00:18:15] have Claude come and be the CEO briefly,
[00:18:18] if you want, as well. The cool thing
[00:18:20] about G stack is when I run it through
[00:18:22] this program, like I always I do I start
[00:18:24] with office hours CEO review, like I do
[00:18:27] design if there's UI. If
[00:18:29] I know a developer needs to use it,
[00:18:31] which is like practically all of G stack
[00:18:33] and G brain stuff, I run the developer
[00:18:35] review, and then I do end review, and
[00:18:37] then Codex. Once that plan is done, I've
[00:18:39] worked through all of the issues. The G
[00:18:42] stack relies very heavily on ask user
[00:18:44] question. So cuz you know, and that's
[00:18:46] that to me is like really important.
[00:18:48] That's where the human you know, vibe
[00:18:51] coder operator agentic engineer needs to
[00:18:54] supply their understanding of what's
[00:18:56] going on, what are we building. There's
[00:18:59] not really a substitute to that. It
[00:19:01] would surprise me very much if someone
[00:19:03] really truly did manage to make a thing
[00:19:05] that could just make software without
[00:19:07] the human in the loop. Like that you
[00:19:09] know, it's controversial take, I think.
[00:19:11] But um, I never want to be entirely out
[00:19:14] of the loop. I just want the machine to
[00:19:16] do the stuff that I don't want to do.
[00:19:18] And so, you know, basically QA is a good
[00:19:21] example. And you know, I mean, that's
[00:19:22] hilarious. Coming back to the demo, it's
[00:19:24] like I type something into the modern
[00:19:26] version of G stack, and it's like,
[00:19:28] "Dude, what are you doing? Like, we
[00:19:29] already built that. We have browse.
[00:19:32] Browse is a long-lived HTTP demon with
[00:19:34] 70 commands as a CLI." And then QA is
[00:19:37] just browse, but, um, in the prompt for
[00:19:41] QA, it says, "Look in your context. What
[00:19:44] did we do on this branch? If there's UI
[00:19:46] or any mutation of data, go and use the
[00:19:50] browser to test that thing." Which is
[00:19:53] cool. It's like having a black box
[00:19:54] browser. It blew my mind when it first
[00:19:56] worked. It's like, "Mini AGI is already
[00:19:58] here." You know, I you know, I realize
[00:20:00] this is not true AGI. A true true AGI
[00:20:03] would be like, "I'm not even here." Um,
[00:20:05] and actually, that's fine. In this
[00:20:07] respect, like, as a builder, you know,
[00:20:09] selfishly, uh, I hope that we never have
[00:20:12] to stop.
[00:20:13] >> [laughter]
[00:20:14] >> I hope that the machines never figure it
[00:20:16] out cuz that would be really cool. Like,
[00:20:17] then, you know, humans are really
[00:20:19] important, and like, engineers who know
[00:20:22] how to do this, who have taste in
[00:20:23] design, and product feedback, and, um,
[00:20:26] you know, the real [clears throat]
[00:20:27] customer in mind, like, we're going to
[00:20:29] be like, we basically have wings for as
[00:20:31] long as we do. YC Startup School is
[00:20:33] back. We're hand-selecting the most
[00:20:35] promising builders in the world and
[00:20:37] flying them out to San Francisco on July
[00:20:40] 25th and 26th to discuss the cutting
[00:20:43] edge of tech. Apply now for a spot.
[00:20:45] Okay, back to the video. I think you
[00:20:47] crystallize a lot of these thinking in
[00:20:49] this post on X about thin hardness and
[00:20:53] fat skills. Oh, yes.
[00:20:54] >> Which actually encompasses all of this
[00:20:57] philosophy on how to token max. Yeah. I
[00:20:59] mean, some of it came out of, uh, being
[00:21:01] trolled on the internet relentlessly
[00:21:03] about markdown. And like, I you know,
[00:21:05] I'm just like peddling a markdown
[00:21:06] instead of markdown. and it's like, you
[00:21:08] know, I guess my lived experience at
[00:21:09] this point is that markdown is actually
[00:21:11] code. It's just like this compiled in a
[00:21:13] different way, but like you can get the
[00:21:15] computer to do really astonishing
[00:21:17] things. Like, you mean, even this. It's
[00:21:19] like could we have imagined that I would
[00:21:21] be talking to something that has
[00:21:23] replaced Visual Studio for like I I
[00:21:27] don't use Visual Studio at all. Like,
[00:21:29] there's no reason to. Like, when I can
[00:21:30] talk to my agent and my agent can do
[00:21:32] this, right? The article actually name
[00:21:34] The name actually came from uh our
[00:21:36] partner Pete Kouwenhoven. We have had to
[00:21:38] build an internal agent, and you know,
[00:21:41] we call that the harness over and over
[00:21:43] again. And then at some point using
[00:21:45] Cloud Code all day, we realized like you
[00:21:47] know, why should we rewrite a version of
[00:21:50] that over and over again? Like, you
[00:21:52] know, we should just use the things that
[00:21:54] are really awesome as, you know,
[00:21:56] harnesses. Like, a harness is the core
[00:21:58] loop that takes the user input, gives it
[00:22:00] to the LLM, runs what the LLM does.
[00:22:02] Like, it can do tool calls and things
[00:22:04] like that. I mean, why would we build
[00:22:06] that? Like, what we should be spending
[00:22:08] all our time doing is thinking about
[00:22:10] what markdown should there be. And the
[00:22:12] way to think about markdown is if you
[00:22:14] were an event planner and throwing a
[00:22:16] wedding and you were trying to write
[00:22:17] down a checklist of how to throw a
[00:22:19] wedding again. Like, what would you what
[00:22:22] would you write in plain English to
[00:22:24] teach the next person who had to do it
[00:22:26] what to do. All of that should be in the
[00:22:28] markdown.
[00:22:29] Whereas, um all the things that should,
[00:22:33] you know, be deterministic like um I
[00:22:35] mean, or is is a real action. Like, a a
[00:22:38] wedding planner might have to call like
[00:22:40] 20 venues, right? But, you wouldn't use
[00:22:42] markdown for that. Like, you would make
[00:22:44] a, you know, a call to Twilio for
[00:22:46] instance, right? There's like a you
[00:22:47] know, sort of all of the difficulty in
[00:22:49] in agentic engineering today is when
[00:22:52] people try to do things that should be
[00:22:54] in markdown in code, and it fails
[00:22:57] because code is brittle. It doesn't
[00:22:59] understand special cases. It doesn't
[00:23:00] actually, you know, code literally
[00:23:02] doesn't understand what you want or who
[00:23:05] you are. It is like, you know, executing
[00:23:08] deterministic zeros and ones in a Turing
[00:23:11] complete loop, right? Like it doesn't
[00:23:13] know. But then now we have LLMs that
[00:23:16] have latent space and they know who you
[00:23:18] are and uh it knows what your
[00:23:20] motivations are and it can handle
[00:23:22] generic cases.
[00:23:23] And then, you know, a lot of the the
[00:23:26] magic right now as an engineer is like
[00:23:29] figuring out, "Okay, how much of it is
[00:23:31] over here in LLM land?" And how how much
[00:23:34] of it is over there in um code land? And
[00:23:38] then, you know, if you combine that with
[00:23:40] the other thing I learned, which is like
[00:23:42] get to 80 to 90% tests. Like if it's not
[00:23:44] tested and you're just throwing users in
[00:23:46] there, like it's slop. You know, 10x
[00:23:49] worse than like human-written code cuz
[00:23:51] like you just have no idea what's going
[00:23:54] to happen. Um and so that's like one of
[00:23:56] the things that people have to do. It's
[00:23:58] like, "All right, not only do you need
[00:23:59] to figure out what's going on in latent
[00:24:00] space and deterministic space, you also
[00:24:03] have to make sure that like it's, you
[00:24:04] know, unit individually tested and then
[00:24:06] the integration is tested." And then
[00:24:08] going back to uh boil the ocean, like
[00:24:11] the machine doesn't care. It'll just do
[00:24:12] it. It's amazing. Like just zap the
[00:24:14] rocks more and you can get to 90% test
[00:24:16] coverage and then you can have a system
[00:24:19] that, you know, is not quite perfect.
[00:24:21] Like, you know, Openclaw right now um
[00:24:23] there are lots of like failure cases,
[00:24:25] but it's 95% there. You know, it's uh I
[00:24:28] feel like using Openclaw these days is
[00:24:30] like driving a Ferrari and it's like
[00:24:34] exhilarating. It's insane. Like you get
[00:24:36] to do things like it figures things out
[00:24:37] you would never think a machine could
[00:24:39] figure out and it does it so quickly.
[00:24:42] Uh but then it's also like a Ferrari in
[00:24:44] that you better be a mechanic.
[00:24:46] Like it's a Ferrari that will break down
[00:24:48] on the side of the road, you know, when
[00:24:50] you most need it and you need to get out
[00:24:52] with your wrench and pop the hood and
[00:24:54] like fix fix it, you know, you're going
[00:24:55] to have to fix it
[00:24:56] And so, this is a very exciting time in
[00:24:59] uh uh computer science and technology
[00:25:01] cuz it's like this is Homebrew Computer
[00:25:03] Club uh
[00:25:05] you know, the moment when the Apple 1
[00:25:07] came out. Like the Apple 1 created by
[00:25:09] Steve Jobs and Steve Wozniak was a
[00:25:11] breadboard inside like literally a
[00:25:14] wooden case hammered together with like
[00:25:17] nails and duct tape, you know?
[00:25:20] And uh if you wanted a personal
[00:25:22] computer, that's what you had to do. And
[00:25:24] that's where we're at right now. Like
[00:25:26] you have relatively, you know, smart
[00:25:28] technical you know, people who had to
[00:25:30] study computer science have to spend
[00:25:32] like two or three hours and like maybe
[00:25:35] like $500 or $1,000 in both tokens and
[00:25:38] cloud to actually get something like
[00:25:41] that running. But like once you get it,
[00:25:42] it's like we're sort of in the kit car
[00:25:44] Ferrari phase. [laughter] It's like then
[00:25:46] you can drive and you can go anywhere
[00:25:48] and you know, you want you want to shout
[00:25:49] to the hills like, "Hey, I got a
[00:25:50] Ferrari." Even the part about fixing
[00:25:53] yourself, I feel people um
[00:25:55] is that one of those things until you've
[00:25:57] like pushed through, you just don't
[00:25:58] quite get. If I really zoom out, it's
[00:26:00] almost like things have moved so
[00:26:01] quickly. Like if you think way back,
[00:26:03] just having Stack Overflow as a website
[00:26:05] that you could consult when you got
[00:26:06] stuck on a programming problem felt like
[00:26:08] amazing. And then it's like like ChatGPT
[00:26:10] launches like, "Oh, now I've got this
[00:26:11] like interactive thing that's way better
[00:26:13] than Stack Overflow." But you're still
[00:26:14] sort of doing the same thing. You're
[00:26:16] like asking questions and you're copying
[00:26:17] and pasting code and you're running the
[00:26:18] code and seeing what happens and copying
[00:26:20] and pasting it back. And then you sort
[00:26:22] of with Claude Code, you sort of push
[00:26:23] through and you realize that you don't
[00:26:24] need to do the copying and pasting
[00:26:26] anymore. It just like actually like
[00:26:28] executes and runs the code. And then
[00:26:29] even with Open Claude, I found that when
[00:26:31] I set it up, yeah, it's annoying cuz it
[00:26:32] can like effectively brick itself and it
[00:26:34] does a bunch of annoying things. But if
[00:26:35] you actually have like Claude Code, like
[00:26:38] So, it'll fix it. Yeah, like you just
[00:26:39] have Claude Code running, it will just
[00:26:41] like fix it. And I it's clearly not the
[00:26:43] way things will be long term, but
[00:26:44] there's this mentality shift of it
[00:26:46] doesn't actually matter if it's brittle
[00:26:47] and requires fixing cuz you can actually
[00:26:49] just have another agent like sat there
[00:26:51] like fixing it all the time.
[00:26:53] >> Yeah, I feel like this evolution I was
[00:26:55] like completely Claude code pilled and
[00:26:58] still am but like probably only like 50%
[00:27:01] or 60% of my time like building product
[00:27:05] or agentic engineering is in Claude code
[00:27:08] now. At some point basically Almost half
[00:27:10] of it is through open Claude now. Yeah,
[00:27:12] which is very interesting. I mean then
[00:27:14] again I'm also spending a lot most of my
[00:27:16] time working on G brain itself. So G
[00:27:18] brain came about because I met you know
[00:27:21] obviously we had Peter on the show. And
[00:27:24] then I finally got around to it. It was
[00:27:25] like one weekend I said I got to check
[00:27:27] this out like what's going on with the
[00:27:29] open Claude. Let's get it going and this
[00:27:31] was about the time Karpathy wrote his ex
[00:27:34] post about knowledge LM wikis.
[00:27:37] And so I was like okay well I have a
[00:27:38] repo full of markdown all my you know I
[00:27:41] should put all of my context into that
[00:27:43] markdown and then at some point I
[00:27:44] realized oh shoot it's just using grep.
[00:27:48] And grep is not that good. Like it's you
[00:27:50] know wasting context as loading a lot
[00:27:53] more into context than it needs to and
[00:27:55] then I sort of fell into a rabbit hole.
[00:27:57] I just went into conductor click quick
[00:27:59] start and then I had G stack built into
[00:28:02] conductor already and then you know
[00:28:04] basically this was how I started. I you
[00:28:06] know
[00:28:07] >> [laughter]
[00:28:07] >> It was actually much more interesting
[00:28:09] than that. So
[00:28:10] I didn't start off from nothing. One of
[00:28:13] the things I've learned as you write
[00:28:15] like a larger and larger corpus of code
[00:28:17] is like you have it loaded in your
[00:28:19] brain. You're like Oh well in order to
[00:28:21] build an agentic newsroom for
[00:28:24] Gary's list I actually had to learn
[00:28:27] about vector embedding and hybrid RRF
[00:28:30] and chunking like when you're in there
[00:28:32] trying to make it work
[00:28:33] you're just like very applied. It's like
[00:28:36] I have an output that I want. I want the
[00:28:38] article to look like this. It needs to
[00:28:40] be of this quality. It needs to have
[00:28:42] these citations. Like you start building
[00:28:44] up your you know your tests and
[00:28:46] integration tests and like you end up
[00:28:48] with like a product that's like
[00:28:50] battle-tested from like the output that
[00:28:52] you want. And so, I sort of put two and
[00:28:55] two together and I, you know, and this
[00:28:56] is something that, you know, anyone can
[00:28:58] do, actually. It's like this this is why
[00:28:59] I think we're entering the golden age of
[00:29:01] open source.
[00:29:02] Uh I could just open, you know, this
[00:29:05] project in conductor and then the first
[00:29:07] thing I write is like, you know, go look
[00:29:09] at, you know, tilde/git/garyslist.
[00:29:13] Like look at how we do chunking,
[00:29:15] embedding, uh you know, hybrid RRF, rag,
[00:29:19] like all of this and then just like
[00:29:20] extract it and then I want to use
[00:29:22] Postgres with PG vector and like I want
[00:29:26] a a, you know, full rag system for my
[00:29:29] open claw.
[00:29:31] And then sort of like one thing led to
[00:29:33] another. It's like then I have, you
[00:29:35] know, 10 windows in G brain and I'm just
[00:29:37] like at it. What's cool about open claw,
[00:29:39] I mean, maybe this is a good example.
[00:29:40] This is actually my open claw. I did go
[00:29:42] ahead and ask. It's um
[00:29:45] how, you know, how did I actually get
[00:29:46] into it? January 23rd. Also, all your
[00:29:49] emails.
[00:29:49] >> a tweet that was like, "Claude code this
[00:29:51] week has awakened my 25-year-old self,
[00:29:53] the one that checked Red Bulls and
[00:29:54] stayed up till dawn coding. We're so
[00:29:56] back."
[00:29:57] >> [laughter]
[00:29:58] >> The builder identity resurfaces.
[00:30:00] >> Yeah, and you know, I'm basically back
[00:30:02] to, you know, sleeping 4 hours and, you
[00:30:04] know, coding 20 hours a day. You know,
[00:30:06] this is also when I started getting
[00:30:08] myself into trouble like talking about
[00:30:09] lines of code. I still believe this, by
[00:30:11] the way.
[00:30:12] >> might be like a good quick aside to talk
[00:30:14] about like this this idea of like lines
[00:30:17] of code being important measure has been
[00:30:19] like controversial on the internet.
[00:30:20] There's obviously the counterargument
[00:30:22] like, "Oh, lines of code doesn't like
[00:30:24] measure developer productivity." But It
[00:30:26] doesn't, right? But it also does. It it
[00:30:29] also kind of does, right?
[00:30:30] >> Yeah. Like [laughter] it does it's
[00:30:32] clearly and, you know, what's
[00:30:33] interesting is you can actually um
[00:30:34] there's well-published get repos out
[00:30:37] there that you can run to uh strip away
[00:30:39] and and standardize what is actual
[00:30:41] logical lines of code. And so, I
[00:30:44] actually did go ahead and do that. Um
[00:30:46] you know, and I got into trouble for
[00:30:48] saying like, "Oh, I'm coding at like
[00:30:50] 100x uh the rate that I was in 2013."
[00:30:54] And then after I did the logical lines
[00:30:56] of code strip down, It actually went up.
[00:30:59] >> It actually went up. So, it turns out
[00:31:01] that I was actually doing 400x the
[00:31:04] amount of code. But, you know, obviously
[00:31:06] I wasn't writing it. I was directing,
[00:31:08] you know, 15 agents at a time to do so.
[00:31:11] And then by the numbers, like it was not
[00:31:13] that it did like knock down my lines of
[00:31:16] code from Claude code a little bit. But,
[00:31:19] uh the surprising thing to me was that
[00:31:21] it knocked down the amount of lines of
[00:31:22] code that I was writing in 2013 by like
[00:31:25] 70%. And so, I think that that's sort of
[00:31:28] the mismatch here. Like, people get very
[00:31:30] upset because it's easy to like pad the
[00:31:35] lines of code if you're a human writing
[00:31:37] code. Whereas like, unless you direct
[00:31:41] Claude code to literally like pad the
[00:31:43] lines of code, it doesn't necessarily do
[00:31:46] that. Like, it'll maybe build the wrong
[00:31:48] thing. Like, you might not steer it very
[00:31:50] well. It might not do the right thing.
[00:31:53] But, like, it's not trying to optimize
[00:31:55] for lines of code the way a human
[00:31:57] working a job would, right? Which is,
[00:31:59] you know, that's just life. And then,
[00:32:02] I guess the really surprising thing is
[00:32:03] if you look at the literature about
[00:32:04] software engineering going back to like
[00:32:06] 2000, 1990, I mean, it's pretty clear
[00:32:10] that the average number of lines of code
[00:32:12] that a professional software engineer
[00:32:14] that's like tested and production ready,
[00:32:17] it's not like
[00:32:18] 100 lines of code. It's like 50. It's
[00:32:21] like 30. Yeah, a day. Yeah, a day,
[00:32:23] right? [clears throat] Like, for me it
[00:32:24] was like 14, but I was like part-time. I
[00:32:26] don't know. It's uh
[00:32:28] So, that's where the 400x actually came
[00:32:30] from. You know, the other thing I know
[00:32:32] is like, I should have said that instead
[00:32:33] of just trolling people more on the
[00:32:35] lines of code. So, I, you know, if I
[00:32:37] trolled you on the internet, I'm very
[00:32:38] sorry for that. Like, there you know,
[00:32:40] there is a deeper understanding of this
[00:32:42] and I did end up releasing a blog post
[00:32:44] about it that
[00:32:46] explains this quite a bit more. I mean,
[00:32:48] and I think it's not a little bit
[00:32:49] significant. It's very significant for
[00:32:52] people who are technical because it
[00:32:54] actually raises the bar on like what you
[00:32:56] are capable of doing. Like, all the
[00:32:58] people who are attacking me about lines
[00:33:00] of code, they particularly are the
[00:33:02] people who are most likely to get wings
[00:33:05] if you like let it rip and token max.
[00:33:08] This is sort of like the classic
[00:33:09] problem. It's like if you have taste and
[00:33:12] you understand technology, you are
[00:33:14] particularly the people who should would
[00:33:16] benefit the most from getting this. All
[00:33:19] someone has to do is
[00:33:21] you know, believe. Right. Yeah. So, stop
[00:33:24] fighting and just open Claude Code and
[00:33:26] try it, you know. I think another thing
[00:33:27] that's potentially going on is just like
[00:33:29] the experience is very dramatically
[00:33:31] depending on like the the models and the
[00:33:33] harnesses.
[00:33:34] I think something I've noticed is any
[00:33:37] sort of like semi-complicated
[00:33:40] programming task I try and do through my
[00:33:43] open claw agent just like kind of fails.
[00:33:47] Like, it's exactly the same model and
[00:33:48] it's sort of like Opus 4.7 as Claude
[00:33:50] Code, but it just like
[00:33:53] like anything above like a simple
[00:33:54] script, I just find like it's not like
[00:33:56] that great at. So, I'll go back into
[00:33:58] like Claude Code and then
[00:34:00] it was sort of a moment for me where I
[00:34:01] realized, oh like this is how it used to
[00:34:04] feel. Like, this is how like even 6
[00:34:06] months ago it used to feel like, oh like
[00:34:08] you try and like these things Yeah,
[00:34:10] these things aren't quite there yet. And
[00:34:11] then Claude Code with like Opus 4.5 was
[00:34:13] like, oh like it's actually like here.
[00:34:16] It's about to recur. Like, right now
[00:34:17] people sort of are feeling like open
[00:34:19] claw or Hermes
[00:34:21] is like not quite there or it's like a
[00:34:23] lot of work. And then I guarantee you
[00:34:25] like this time next year like everyone's
[00:34:28] going to be saying what you heard here
[00:34:30] first, which is like every single person
[00:34:32] on the planet will have their own
[00:34:34] personal AI. We could either live in a
[00:34:36] world where we have our own AI, where we
[00:34:39] have our own data, our own integrations,
[00:34:42] like we see what's happening, we write
[00:34:44] our own prompts, and we have control
[00:34:46] over what we see,
[00:34:49] uh or it's corporate controlled. It's
[00:34:51] something, you know, you go to a host,
[00:34:53] it's kind of like your Facebook feed,
[00:34:55] and like you don't know what that, you
[00:34:57] know, who wrote that algorithm and who
[00:34:59] does it benefit and like what model is
[00:35:02] behind it, like nobody knows. The most
[00:35:04] powerful idea that like was a gift was
[00:35:07] the personal computer revolution, and
[00:35:09] we're about to go through exactly that
[00:35:11] same shift with personal AI. And it's
[00:35:13] going to be a choice, like, you know,
[00:35:15] people are going to have to figure out,
[00:35:17] am I willing to write my own prompts?
[00:35:19] And, you know, I think I wish Pete
[00:35:21] Koomen were here, like that's one of the
[00:35:23] things we learned from him, too. It's
[00:35:24] like, unless you have your own prompts
[00:35:27] and you can write it for yourself, like
[00:35:30] you are,
[00:35:32] you know, below the API line for some PM
[00:35:35] or developer that is not you, who like
[00:35:38] will not understand you, will not
[00:35:39] understand your needs, will not
[00:35:40] understand what you uniquely care about.
[00:35:43] And I think that's like the defining
[00:35:46] question, like will you have control
[00:35:49] over your own tools or will your tool
[00:35:51] your tools have control over you? And I
[00:35:53] think this is the one of the disconnects
[00:35:55] that the public has, I think, is a lot
[00:35:59] of these capabilities you have to be on
[00:36:01] the latest and greatest models, and it's
[00:36:04] actually quite expensive to use them and
[00:36:07] burn all the tokens, for now. It's
[00:36:09] coming down, but I think maybe people
[00:36:11] are just trying like Sonnet or the free
[00:36:13] model or having the basic Claude Pro
[00:36:17] subscription only. Yeah. And part of it
[00:36:19] is maybe we have to address that this
[00:36:21] new way of really getting all this
[00:36:25] almost ASI AGI moment for for building
[00:36:28] is you have to be burning lots of tokens
[00:36:30] the whole token maxing paradigm.
[00:36:32] >> It actually reminds me of rent, San
[00:36:33] Francisco rent. Like one of the things
[00:36:36] that I feel like we always have to do
[00:36:38] um with YC founders is that it's like a
[00:36:41] general thing. It's like, "Oh, like I
[00:36:42] don't want to move to San Francisco
[00:36:43] because it's like so expensive to live
[00:36:45] there." But it's like it's so expensive
[00:36:46] to not live there.
[00:36:47] >> Yeah, yeah, yeah, exactly. [laughter]
[00:36:48] That's the whole point, right? Like
[00:36:49] early on in a YC batch, like I'm just
[00:36:51] used to like a founder being like, Like
[00:36:53] this like apartment is like thousands of
[00:36:55] dollars a month in rent. Like seems
[00:36:57] ridiculous. Like should I like pay it or
[00:36:59] not? And it's like, "No, you should
[00:37:00] absolutely pay it. And if anything, you
[00:37:01] should pay more to not just be in San
[00:37:04] Francisco but be in like the
[00:37:06] and just like be in like neighborhoods
[00:37:07] where you create this serendipity. Like
[00:37:09] token maxing is going to be one of those
[00:37:10] things for founders that we sort of have
[00:37:11] to teach them where it's not immediately
[00:37:13] obvious that you shouldn't This is
[00:37:15] actually like rent. Like this is one of
[00:37:17] the things where you should like spend
[00:37:19] as much as you can to like get the like
[00:37:22] most utility out of it versus treating
[00:37:24] it like the the office desk or
[00:37:26] something. Like sure, you can economize
[00:37:28] on that. Or you don't need like a super
[00:37:29] expensive like couch. But like when it
[00:37:32] comes to like actually using the models
[00:37:34] and your token spend
[00:37:35] >> you should probably be like pushing
[00:37:36] pretty hard on that.
[00:37:37] >> Yeah, one of the key maxims for YC is
[00:37:40] you know, how do you find good startup
[00:37:41] ideas? Live in the future and build
[00:37:44] what's missing, right? And so this is a
[00:37:46] profound version of that where all you
[00:37:48] have to do is commit your brain to look
[00:37:51] at, you know,
[00:37:53] spending $500 in a single day on tokens
[00:37:56] and say actually like you know, as long
[00:37:59] as I'm building something that's
[00:38:01] actually of great value to me, you know,
[00:38:03] and I'm building the right thing.
[00:38:05] Uh I'm going to do that. Garry, I have a
[00:38:06] weird question. Do you think that in
[00:38:08] some ways the fact that you tried to
[00:38:11] build all of this while also being the
[00:38:13] CEO of Y Combinator actually helped you?
[00:38:15] Because like your time is so scarce. You
[00:38:18] have to like try to figure out how to
[00:38:19] write hundreds of thousands of lines of
[00:38:20] code
[00:38:21] >> with just like spare minutes in between
[00:38:23] meetings.
[00:38:23] >> Yeah. Unlike a prof- a full-time
[00:38:25] software engineer that could, you know,
[00:38:26] just take the time to like open the
[00:38:28] website and like click around and like
[00:38:29] just test it. Like those minutes were
[00:38:31] like insanely scarce for you and so you
[00:38:34] were constantly pushing yourself to
[00:38:35] figure out how to like automate
[00:38:37] everything.
[00:38:37] >> Yeah, I I envy time billionaires. You
[00:38:40] know, sometimes look at I mean, I'm look
[00:38:42] at my kids and it's like these kids are
[00:38:43] time billionaires right now and I'm
[00:38:45] like, you know, you can just like do
[00:38:46] thing, you know, you know, run across
[00:38:47] people at Startup School all the time
[00:38:49] and it's like, you're a time billionaire
[00:38:51] right now. Like this is incredible. Like
[00:38:52] you could just do anything you like
[00:38:53] learn about anything. This is so great.
[00:38:56] So yeah, I'm you know, personally like I
[00:38:58] think my philosophy is I am in a crazy
[00:38:59] rush. In my brain I'm like probably
[00:39:02] lived 10 billion lifetimes living in
[00:39:03] this body right now and I need every
[00:39:05] single moment to count. Uh and then if
[00:39:08] you can token max, it's like I mean, you
[00:39:10] could buy millions of years of
[00:39:13] consciousness
[00:39:14] of machine consciousness. Now, I can be
[00:39:17] a time billionaire. It's not, you know,
[00:39:18] my own time.
[00:39:20] It's the time of a machine. Like doing
[00:39:23] work for me and like the human entities
[00:39:26] that I care about working on the causes
[00:39:29] that I care about, right? I care about
[00:39:30] YC. I care about builders being able to
[00:39:32] build. Even in a lot of our internal
[00:39:35] meetings last year, remember in our
[00:39:37] offsites, we would talk about like how
[00:39:39] do we teach the next generation how to
[00:39:42] use these tools? And so, you know, I'd
[00:39:44] like to I wish that I could say like
[00:39:46] that was all a part of the grand plan
[00:39:48] and that's how it started. It's not
[00:39:49] like, but you know, subconsciously I
[00:39:51] actually think it was. Like I think
[00:39:53] subconsciously from doing like cone and
[00:39:56] like talking about this stuff, like
[00:39:57] sitting side by side with uh Boris
[00:39:59] Cherney right here was a very powerful
[00:40:02] moment for me because I realized like
[00:40:05] he's he started saying things that like
[00:40:07] I could do myself. It's like he said,
[00:40:09] "Our team doesn't write a single line of
[00:40:11] code." I'm like, "Oh, actually like I
[00:40:13] can do that." And like the people who
[00:40:15] are watching right now, it's like you
[00:40:16] and I are not different, right? We're
[00:40:18] the same. Like we started in the same
[00:40:20] place. I don't think of myself as like,
[00:40:23] you know, in the sky yet, even though
[00:40:25] people seem to talk like I am, you know,
[00:40:27] like I'm just a person trying to do a
[00:40:29] thing. And if I sit next to Boris, I'm
[00:40:32] like, you know, this guy is one of the
[00:40:34] best engineers I've ever met. But also
[00:40:36] like, if I just open a prompt, we have
[00:40:39] the same prompt. We have the same
[00:40:40] MacBook Pro.
[00:40:41] And, you know, there's nothing that
[00:40:44] stands between like me or you or any of
[00:40:46] us from like drawing on millions of
[00:40:50] years,
[00:40:51] potentially, of like tokens to like
[00:40:54] serve humanity. Well, Gary, I think that
[00:40:57] was a beautiful quote that should be
[00:40:59] retweetable. It shows Got to get it on X
[00:41:02] right away. You could have infinite time
[00:41:04] by borrowing the time from the machines.
[00:41:06] Yeah, what a time to be alive. That's a
[00:41:08] beautiful thought to end on.
[00:41:10] Thanks, Gary, for showing us the future.
[00:41:12] Thanks, guys.
[00:41:13] >> All right, thanks for watching and I'll
[00:41:15] see you on the next episode of Light
[00:41:16] Code.
