---
video_id: J0D7qV3nl7w
title: Deepseek drops another HUGE breakthrough
channel: AI Search
url: "https://www.youtube.com/watch?v=J0D7qV3nl7w"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 1521
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 75
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1521
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

DeepSeek released DeepSpark, a new system that accelerates AI text generation by 60–85% without sacrificing output quality. The core problem is that AI models generate text one word at a time while spending most time fetching memory to check relationships between all previous words. DeepSeek's solution improves on "speculative decoding" (using a fast small model to draft multiple words ahead, then a larger model verifies them) by adding a lightweight "Markov head" that steers word predictions based on the immediately preceding word, fixing the "suffix decay" problem where later words get corrupted. They also added a "confidence head" that measures prediction certainty and stops drafting early if it drops below threshold (boosting acceptance rate from 45.7% to 96%). The system dynamically adjusts draft length based on GPU load—longer drafts during off-peak hours, shorter during peak load—balancing individual response speed against overall server throughput. In production testing, DeepSpark achieved up to 700% higher total system output under fixed throughput constraints, all while maintaining quality.

You can immediately download and use DeepSeek V4 (which includes DeepSpark built-in) from Hugging Face for faster, cheaper inference. If you run your own inference server or work with long-context tasks, the DeepSpark code is available open-source under MIT license on GitHub with full deployment instructions—this addresses one of the industry's most tightly guarded infrastructure secrets. For anyone concerned with API latency costs or serving multiple users concurrently, DeepSpark delivers measurable speed gains without the usual quality-versus-efficiency tradeoff.

## Transcript

[00:00:00] If you've been working with AI models,
[00:00:01] especially with agents that are doing
[00:00:03] some really challenging or long tasks,
[00:00:06] they take quite a while to process and
[00:00:08] generate your answer. It sometimes takes
[00:00:10] a painfully long time to wait for it to
[00:00:12] generate a response or finish a task.
[00:00:14] But what if that wait basically
[00:00:16] disappeared? What if instead of watching
[00:00:18] a loading spinner, you got your answer
[00:00:20] back almost instantly? And what if this
[00:00:22] speed boost didn't cost you anything in
[00:00:24] quality? No shortcuts or dumbed-down
[00:00:26] answers. This seems way too good to be
[00:00:29] true, right? But the genius team at
[00:00:31] DeepSeek did it again. They found a way
[00:00:33] to push AI systems to more than six
[00:00:36] times the output capacity and speed
[00:00:38] things up by over 80% without any loss
[00:00:41] in quality. This seems impossible
[00:00:44] because usually there's a trade-off
[00:00:45] between speed and quality. You can't
[00:00:48] really have both at the same time, but
[00:00:50] surprisingly DeepSeek was able to pull
[00:00:52] this off. In this video, we're going to
[00:00:54] go over this breakthrough and the clever
[00:00:56] engineering behind it. Now, this is
[00:00:58] quite a technical paper, but as always,
[00:01:00] I'll break it down and make it easy to
[00:01:02] understand for everyone. Let's jump
[00:01:05] right in. First of all, if you haven't
[00:01:07] heard of DeepSeek, this is a small
[00:01:09] Chinese lab that's incredibly
[00:01:11] resource-constrained. They have like 20
[00:01:13] times fewer employees than OpenAI. Heck,
[00:01:16] they don't even have access to the top
[00:01:18] Nvidia GPUs out there. So, they're
[00:01:20] incredibly limited in terms of compute.
[00:01:23] But the team is simply brilliant and
[00:01:25] relentless. In fact, they've already
[00:01:27] built one of the most intelligent and
[00:01:28] efficient open-source models out there,
[00:01:31] DeepSeek V4. Not only did they release
[00:01:33] the model, but they were also generous
[00:01:35] enough to reveal all the details on how
[00:01:37] this works. In fact, if you want to
[00:01:39] learn more about this, I highly
[00:01:41] recommend this video where I do a deep
[00:01:43] dive on DeepSeek V4. Anyway, because of
[00:01:46] their situation, because they are
[00:01:47] severely limited by resources, they
[00:01:50] can't just keep building bigger and
[00:01:51] bigger models. They have to be
[00:01:53] laser-focused on making them as
[00:01:55] efficient as possible. And that's why
[00:01:57] the publications from DeepSeek are so
[00:01:59] interesting. It's not just about brute
[00:02:01] force, but about smarter design. And a
[00:02:04] few days ago, they released a new system
[00:02:06] called DeepSpark. This claims to speed
[00:02:09] up AI models and increase their output
[00:02:11] capacity by over 600% without any cost
[00:02:14] in quality. That's a pretty crazy
[00:02:16] result. Now, before we go over this,
[00:02:18] it's probably helpful to first
[00:02:20] understand how current AI models work
[00:02:23] and what the bottleneck is. You see,
[00:02:25] when you prompt ChatGPT or Gemini or
[00:02:27] DeepSeek, you probably need to wait at
[00:02:29] least a few seconds before you get a
[00:02:31] response. You'll see a loading spinner
[00:02:33] as you wait. Well, this is because
[00:02:35] modern AI models generate text through a
[00:02:37] process called autoregressive
[00:02:39] generation. Basically, AI writes one
[00:02:42] word at a time. And to generate each
[00:02:44] word, it has to look at everything
[00:02:46] written so far. More technically
[00:02:48] speaking, each word has to look at how
[00:02:50] every previous word relates to it. Now,
[00:02:53] for a short sentence, that's fine. But
[00:02:56] imagine writing a really long report
[00:02:57] that's thousands of words or even
[00:02:59] hundreds of thousands of words. Every
[00:03:01] word has to look back at every previous
[00:03:03] word to see how it relates to itself and
[00:03:06] then run this through the billions of
[00:03:07] parameters of the AI model to process
[00:03:10] and generate the next word. The number
[00:03:12] of computations required is
[00:03:14] astronomical. Now, modern GPUs are
[00:03:16] already incredibly powerful. They're
[00:03:18] designed to do a ton of calculations at
[00:03:20] once in parallel. So, they can easily
[00:03:22] handle all this data flowing through
[00:03:25] billions of parameters of an AI model to
[00:03:27] generate the next word. This step is
[00:03:29] actually a piece of cake for the GPU.
[00:03:32] The real slowdown isn't these
[00:03:34] calculations through a neural network.
[00:03:36] It's that the chip needs to fetch all
[00:03:38] the saved values for the relationships
[00:03:40] of every single word and how it relates
[00:03:42] to every other word. Again, for a short
[00:03:45] sentence, it's fine. But if you're
[00:03:46] handling a ton of text and each word has
[00:03:48] to look back at all the other words
[00:03:50] before it to figure out the context of
[00:03:52] everything, well, that's the slow part.
[00:03:54] It's fetching all these values from
[00:03:56] memory for each word. And after all
[00:03:58] these values are fetched, then this data
[00:04:00] can be passed through the neural network
[00:04:02] to process. And here the GPU can process
[00:04:04] everything very quickly. It's just like
[00:04:06] a tiny burst of work to spit out the
[00:04:08] next word. But then it sits idle again
[00:04:10] waiting for the next batch of values to
[00:04:12] be fetched from memory. And because AI
[00:04:14] models are designed to generate only one
[00:04:16] word at a time, you can't begin
[00:04:19] calculating things for the next word
[00:04:20] until previous word has been generated
[00:04:23] and confirmed. And this actually creates
[00:04:26] a direct relationship between the length
[00:04:28] of the response and the time it takes to
[00:04:29] generate it. In other words, the longer
[00:04:32] the answer, the longer it'll take to
[00:04:33] generate because it needs to generate
[00:04:35] everything one word at a time and for
[00:04:37] each word it has to look at all the
[00:04:38] relationships of every other word before
[00:04:40] it. Now, of course, the industry is
[00:04:43] aware of this massive inefficiency and
[00:04:45] there are workarounds for this. In fact,
[00:04:48] the current gold standard for speeding
[00:04:50] up generation is something called
[00:04:51] speculative decoding. And the idea here
[00:04:54] is surprisingly simple. Instead of
[00:04:56] having a large model slowly generate
[00:04:58] every word one at a time, you use a
[00:05:00] faster, smaller model to guess several
[00:05:03] words ahead. Then the big model just
[00:05:05] checks those guesses. If the guesses are
[00:05:07] good, the large model can accept
[00:05:09] multiple words at once instead of
[00:05:11] producing them one at a time. Here's an
[00:05:13] easy analogy to understand this. Imagine
[00:05:16] at work there's a brilliant senior boss.
[00:05:18] This dude's pretty smart and every final
[00:05:20] decision has to go through him, but
[00:05:22] there's just one problem. His time is
[00:05:25] very expensive. He's also really slow.
[00:05:27] He insists on writing every single word
[00:05:30] one at a time. Well, this senior boss is
[00:05:32] like the full AI model. It's intelligent
[00:05:34] and we trust it to produce a good
[00:05:36] answer, but it's just really slow and
[00:05:38] expensive to use. So, to speed things
[00:05:41] up, the company hires an intern. The
[00:05:43] intern is like a tiny lightweight AI
[00:05:45] model. He's not as smart as the boss, he
[00:05:47] misses details and sometimes chooses the
[00:05:49] wrong words, but he works extremely
[00:05:52] fast. And here's how speculative
[00:05:54] decoding works. Instead of asking the
[00:05:56] boss to write everything, you actually
[00:05:57] get the intern to quickly draft a chunk
[00:06:00] of text in advance, maybe five to 10
[00:06:02] words. The intern hands this draft to
[00:06:04] the boss, and now the boss doesn't have
[00:06:07] to check words one by one. He can just
[00:06:09] verify all the words simultaneously in
[00:06:11] parallel. In AI terms, the large model
[00:06:14] can check several guessed words from the
[00:06:16] smaller model at once because GPUs are
[00:06:19] built for parallel work. So, instead of
[00:06:21] using the big model to slowly write one
[00:06:23] word at a time, we just use the small
[00:06:25] model to guess several words. And then
[00:06:27] we use the big model to check its
[00:06:30] response all at once. But what happens
[00:06:33] if the intern makes a mistake? Well, the
[00:06:35] system uses a technique called rejection
[00:06:38] sampling. The bigger model scans the
[00:06:40] intern's draft left to right and accepts
[00:06:42] all the words that align. But if the
[00:06:44] intern messes up on a certain word, the
[00:06:46] boss pulls out a red pen and rejects
[00:06:48] that word and everything after it. Then
[00:06:50] the intern starts again from there and
[00:06:52] drafts the next chunk for the boss to
[00:06:54] review again. This is basically how
[00:06:56] speculative decoding works. The small
[00:06:58] model guesses ahead, the large model
[00:07:01] checks the draft and accepts the correct
[00:07:02] words. If the word is wrong, everything
[00:07:05] else after it is rejected and the
[00:07:07] smaller model starts from there. And the
[00:07:09] process repeats again and again. The
[00:07:11] important part is that the big model
[00:07:14] always has the final say. That's why
[00:07:16] speculative decoding can be a lossless.
[00:07:19] Having a smaller model doesn't mean its
[00:07:21] answer is dumber. It doesn't mean we're
[00:07:23] lowering the quality of the output
[00:07:24] because ultimately the final answer
[00:07:27] still comes from the large model's
[00:07:29] decision. We're just using a small model
[00:07:31] to help it write faster. But the output
[00:07:33] quality is the same as if the large
[00:07:35] model had written everything itself. So,
[00:07:38] in a nutshell, that is speculative
[00:07:40] decoding. And while this is one of the
[00:07:42] standard ways to speed up AI models,
[00:07:44] there's currently a huge dilemma that
[00:07:46] this idea faces. You see, the main
[00:07:49] problem is that these interns, or the
[00:07:51] smaller models, are deeply flawed, and
[00:07:53] they fail in completely opposite ways.
[00:07:56] So, let's go over this problem. There
[00:07:58] are basically two kinds of interns. One
[00:08:00] is careful and slow, and other is fast,
[00:08:03] but unreliable. You see, the first type
[00:08:05] is called an auto-regressive drafter.
[00:08:08] This works almost the same way as the
[00:08:10] big model. It predicts one word at a
[00:08:12] time. It generates word one, then word
[00:08:14] two, then word three, and it keeps going
[00:08:16] step-by-step. The advantage here is that
[00:08:19] each new word knows what came before it.
[00:08:21] So, it's less likely to get the draft
[00:08:24] wrong. The output quality is higher, but
[00:08:27] because it's generating this one word at
[00:08:29] a time, it's also slow. The longer the
[00:08:31] draft, the longer it takes for it to
[00:08:33] generate. Well, the second type of
[00:08:35] intern is called a parallel drafter.
[00:08:38] This is a lot more aggressive. Instead
[00:08:40] of outputting words one at a time, it
[00:08:42] predicts an entire block of words at
[00:08:44] once. For example, you can get it to
[00:08:46] output multiple words in just a single
[00:08:49] pass, and this makes it way faster. It's
[00:08:51] guessing the first word at the same time
[00:08:53] that it guesses the last word. This also
[00:08:56] works well because, well, GPUs are built
[00:08:58] for parallel work. So, a parallel
[00:09:01] drafter can use more of the hardware
[00:09:02] efficiently. Now, this sounds great,
[00:09:05] right? But, there's actually a hidden
[00:09:07] weakness. Because it predicts all these
[00:09:09] words at the same time, it doesn't get
[00:09:11] to naturally build the sentence
[00:09:13] step-by-step. It suffers from something
[00:09:16] called suffix decay. Here's an example
[00:09:18] of what this is. Imagine the model is
[00:09:20] trying to agree with the user. Because
[00:09:23] there are many ways to express the same
[00:09:25] thing in natural language, it could
[00:09:26] output, "Of course." Or, it could also
[00:09:29] say, "No problem." Both are valid. But,
[00:09:31] for a parallel model, because it's
[00:09:34] generating both words at the same time,
[00:09:36] instead of sequentially, there is a
[00:09:38] chance that it could output a messed-up
[00:09:40] answer like of problem or no course. And
[00:09:44] here, it's just a very simple two-word
[00:09:46] example, but as the draft gets longer
[00:09:48] and longer, and there are more words in
[00:09:50] it, this gets even worse. The first few
[00:09:52] words might be fine, but later words are
[00:09:55] often always messed up. So, this is the
[00:09:58] suffix decay problem. To sum things up,
[00:10:00] here's the dilemma we're facing. There's
[00:10:02] currently no good solution for
[00:10:04] speculative decoding, because one type
[00:10:06] of drafter is very careful, but very
[00:10:08] slow. Another type of drafter is very
[00:10:11] fast, but it has a lot of errors. And we
[00:10:13] currently don't really have any solution
[00:10:15] to this. Well, that's exactly what
[00:10:17] DeepSeek aimed to solve in this paper.
[00:10:20] So, they proposed a system called
[00:10:21] DeepSpark, and the design is quite
[00:10:24] genius. Here's how it works. So, they
[00:10:26] took the parallel intern and built on
[00:10:29] top of that. Remember, this parallel
[00:10:31] intern can basically predict multiple
[00:10:32] words at once, so this is really fast,
[00:10:35] but it's also extremely prone to error.
[00:10:38] Well, DeepSeek added something on top of
[00:10:40] that. They introduced a tiny, incredibly
[00:10:42] lightweight loop that iterates one
[00:10:45] position at a time. It's like having a
[00:10:47] hyper-fast editor sitting next to the
[00:10:49] intern, just lightly nudging them in the
[00:10:52] right direction. For example, if it
[00:10:54] typed the word of, then it's going to
[00:10:56] bias the next word towards course. Or if
[00:10:59] it typed no, then it's going to bias the
[00:11:01] next generation towards problem. Claude
[00:11:03] Fable is back this week. And if you want
[00:11:06] to use it to turn your ideas into
[00:11:08] production-ready content, definitely
[00:11:10] check out Higgsfield, the sponsor of
[00:11:11] this video. Claude Fable 5 is already
[00:11:14] one of the smartest models out there. It
[00:11:16] can understand your idea, reason through
[00:11:18] it, and come up with really strong
[00:11:20] creative direction. But normally, it's
[00:11:22] still stuck inside a chat box. It can
[00:11:24] tell you what to make, but it can't
[00:11:25] actually make the content. Well, that's
[00:11:27] where Higgsfield comes in. With
[00:11:29] Higgsfield MCP, you can connect Claude
[00:11:32] to some of the best image and video
[00:11:34] tools in the world. So, instead of just
[00:11:36] describing a concept, it can generate
[00:11:38] the visuals, create the videos, edit the
[00:11:40] assets, and help build the full
[00:11:42] campaign. Instead of manually jumping
[00:11:44] between tools and copying and pasting
[00:11:46] stuff, you can work directly inside
[00:11:48] Claude. Claude can plan the concept,
[00:11:50] write the creative brief, generate the
[00:11:52] videos or images through Higgs Field,
[00:11:54] and even place the final assets into
[00:11:56] your folder. No switching tabs, no
[00:11:58] copying prompts back and forth, no
[00:12:00] separate creative handoff. And because
[00:12:02] Fable 5 remembers the context, your
[00:12:04] characters,
[00:12:08] across the whole project. And if you
[00:12:10] want to go even bigger, there's also
[00:12:12] Higgs Field's supercomputer. This is
[00:12:14] basically Higgs Field's full AI creative
[00:12:16] team in one chat. You can choose Fable 5
[00:12:19] as the brain, then build everything from
[00:12:21] the first idea to the final deliverable.
[00:12:24] Instead of micromanaging every tiny
[00:12:26] step, you give it the goal and let it
[00:12:28] act more like a creative director.
[00:12:30] Whether you're making ads, launch
[00:12:31] videos, social media videos, or any
[00:12:33] other content, Higgs Field is a game
[00:12:35] changer that will supercharge your
[00:12:37] production workflow. Try it today using
[00:12:39] the link in the description below. Now,
[00:12:41] if we dive deeper, here's how it works
[00:12:43] in technical terms. They used something
[00:12:46] called a Markov head. In probability
[00:12:48] theory, a Markov process assumes that
[00:12:50] the probability of the next state
[00:12:52] depends exclusively on the current
[00:12:54] state, completely ignoring any states
[00:12:57] that occurred before. This phenomenon is
[00:12:59] actually found everywhere in life. For
[00:13:02] example, when you're walking, your
[00:13:03] future position depends entirely on your
[00:13:06] current position plus which direction
[00:13:08] you step next. Everything else before
[00:13:10] that point didn't really matter. So, the
[00:13:13] Markov head in D-Spark only looks at the
[00:13:16] immediately preceding word to adjust the
[00:13:18] probabilities for the next word. In
[00:13:20] other words, it looks at the previous
[00:13:22] word to guide what the next word would
[00:13:24] likely be. And it turns out that adding
[00:13:26] this Markov mechanism fixes the suffix
[00:13:29] decay problem we had before. All right,
[00:13:32] so it seems like a good fix, but you
[00:13:34] might be wondering if we add this extra
[00:13:36] component and make it sequential,
[00:13:38] wouldn't it slow things down by a lot?
[00:13:40] Well, the cracked team at Deep Seek used
[00:13:43] a technique called low-rank
[00:13:44] factorization. It's too technical for
[00:13:46] this video, but it basically compresses
[00:13:48] the information down and makes the
[00:13:50] computations extremely fast and
[00:13:52] efficient. And it turns out that after
[00:13:54] applying this Markov head with low-rank
[00:13:57] factorization, then the compute cost is
[00:13:59] actually quite negligible. In fact,
[00:14:01] adding this tiny Markov editor only
[00:14:04] added an additional latency of 0.2 to
[00:14:07] 1.3% of the total generation speed. But
[00:14:10] the return on this tiny investment is
[00:14:13] massive. With this, it's now much less
[00:14:15] error-prone and you can boost the length
[00:14:17] of a correct draft by up to 30%, which
[00:14:21] is incredible. In fact, for this new
[00:14:23] Deep Spark model, even if we make it a
[00:14:25] shallow two layers, actually outperforms
[00:14:27] a massive five-layer pure parallel
[00:14:30] drafter across all benchmarks. It's
[00:14:32] vastly superior and more efficient and
[00:14:35] better quality, pretty much solving this
[00:14:37] drafting intern dilemma. All right, so
[00:14:40] up to now, we've kind of solved this at
[00:14:42] least in theory, at least in code. But
[00:14:44] once we deploy Deep Spark to a real data
[00:14:47] server, well, that unleashes a ton of
[00:14:50] new infrastructure problems. You see,
[00:14:52] this works completely fine if we have
[00:14:54] just one GP U serving exactly one user.
[00:14:57] This is fairly simple and
[00:14:58] straightforward. But in a real
[00:15:00] production setting, you have a data
[00:15:01] center with multiple GPUs, plus you'll
[00:15:04] have like thousands of concurrent users
[00:15:07] all using the same model at the same
[00:15:09] time. You see, the full AI model, in
[00:15:11] other words, the boss model, has a
[00:15:13] strict physical limitation known as the
[00:15:15] batch capacity. It can only process a
[00:15:18] set number of tokens at once across all
[00:15:21] users simultaneously. So, if user A asks
[00:15:24] a question, the system sends a draft
[00:15:26] from the intern model to the boss model
[00:15:28] to verify. And this draft consumes a
[00:15:31] percentage of the total compute pie. If
[00:15:33] the draft for user A was a bad guess and
[00:15:36] the boss rejects it halfway, well, all
[00:15:38] of this compute is essentially wasted.
[00:15:40] If the draft is long and contains a ton
[00:15:42] of errors, not only does this waste the
[00:15:44] boss model's batch capacity, but it also
[00:15:47] wastes the intern's compute, plus it
[00:15:49] also adds latency while the other users'
[00:15:51] queries are held in queue. So, it goes
[00:15:54] without saying, sending bad drafts to
[00:15:56] the boss model wastes compute and hurts
[00:15:58] everyone else on the server. You want to
[00:16:00] avoid sending as many bad drafts as
[00:16:03] possible. Now, to fix this, you might be
[00:16:05] thinking, maybe we can just make the
[00:16:07] drafts shorter so that we don't waste
[00:16:08] capacity, right? And shorter drafts tend
[00:16:11] to contain fewer errors, especially near
[00:16:13] the ends. Well, actually, that would be
[00:16:15] inefficient in the opposite direction.
[00:16:17] You see, the point of making drafts in
[00:16:19] the first place is for the generation to
[00:16:21] run faster. And the longer the draft,
[00:16:23] the faster it can generate the output.
[00:16:25] So, here's the trick that DeepSeek
[00:16:27] proposed. The length of the draft should
[00:16:29] actually be based on context. If the
[00:16:32] context is about content that's very
[00:16:34] predictable, for example, answering a
[00:16:36] math or coding problem, the draft length
[00:16:38] can be longer because the answer is very
[00:16:41] deterministic. It's less likely for the
[00:16:43] intern model to get the draft wrong.
[00:16:45] But, if the context is open-ended, for
[00:16:47] example, if it was prompted to write a
[00:16:49] creative story, then it's really easy
[00:16:51] for this draft to contain a ton of wrong
[00:16:54] words, or in other words, a ton of words
[00:16:55] that the boss model would reject because
[00:16:58] there could be so many possibilities of
[00:17:00] answering this. So, in this context, the
[00:17:02] draft length should be shorter or cut
[00:17:04] early. Now, how do we do this? The
[00:17:07] system needs a kind of dynamic traffic
[00:17:09] cop. It needs to look at the context and
[00:17:12] dynamically decide how long the draft
[00:17:14] should be or when to end it early. In
[00:17:16] fact, we need a mechanism that can cut
[00:17:18] the draft writing early if it detects
[00:17:21] that it's likely to make a mistake at
[00:17:23] that point. That way, it won't waste
[00:17:25] compute generating more stuff that the
[00:17:27] boss model would likely reject. So, the
[00:17:29] DeepSeek team also added a specialized
[00:17:32] lightweight module called the confidence
[00:17:34] head. This is attached directly to the
[00:17:37] drafter or the intern model. For every
[00:17:39] word that it generates, the head also
[00:17:41] outputs a confidence score ranging from
[00:17:43] zero to one. Zero would mean it's
[00:17:45] completely guessing and it's not sure if
[00:17:47] it's the right word, whereas one would
[00:17:50] means it's 100% certain that this is the
[00:17:52] right word. This is the word that the
[00:17:54] boss model would also write. And to make
[00:17:56] this work, they added a simple rule. If
[00:17:59] the word is above a threshold, let's say
[00:18:01] above a confidence score of 0.6, then
[00:18:04] keep going. If any word is below that
[00:18:06] threshold, then you end the draft
[00:18:08] writing immediately and you stop wasting
[00:18:10] compute. You only send that portion of
[00:18:12] the draft to the boss model for review.
[00:18:15] And after implementing this and testing
[00:18:16] it out, the results were staggering.
[00:18:19] After using this confidence threshold,
[00:18:21] the acceptance rate from the boss model
[00:18:23] jumped up from a dismal 45.7%
[00:18:26] to a crazy 96%.
[00:18:29] In other words, now the drafts are much
[00:18:31] more likely to be accepted by the boss
[00:18:33] model. Therefore, we're wasting way less
[00:18:36] compute. Let's trace the logic of this
[00:18:38] improvement. Let's say the AI is
[00:18:40] attempting to write a creative story.
[00:18:42] Because it's so open-ended, the draft it
[00:18:45] writes starts to have very low
[00:18:46] confidence early on. Let's say by the
[00:18:48] fourth or fifth word. At that point,
[00:18:50] based on the current mechanism, the
[00:18:52] system terminates the draft because its
[00:18:54] prediction is weak. The intern is not
[00:18:56] really confident if it continues writing
[00:18:58] the draft whether the boss model would
[00:19:00] actually accept it. And conversely,
[00:19:02] let's say the AI is trying to solve a
[00:19:04] math or coding problem. In this case,
[00:19:06] the answer is much more deterministic.
[00:19:08] And when it's writing the draft, it's
[00:19:10] very confident throughout its
[00:19:11] prediction. Its confidence values are
[00:19:13] almost always above the threshold. So,
[00:19:15] the mechanism doesn't have to cut the
[00:19:17] draft early. The draft can be longer in
[00:19:20] this case, and therefore, the generation
[00:19:21] can be faster. So, this is a mechanism
[00:19:24] that can automatically decide how much
[00:19:26] to speed up the generation while
[00:19:28] maintaining good quality and avoiding
[00:19:30] wasting any compute. But, that's not
[00:19:33] all. You see, the genius of this design
[00:19:35] is that it's also hardware aware. It
[00:19:38] looks at all active requests, gathers
[00:19:40] the confidence of all these drafts, and
[00:19:42] then compares them against something
[00:19:44] called an SBS curve. This is basically a
[00:19:47] chart showing how GPU speed changes
[00:19:49] depending on the batch size. You see,
[00:19:52] smaller drafts process quickly and are
[00:19:53] easier on the GPU, but larger drafts
[00:19:56] slow down the GPU, which could affect
[00:19:59] other concurrent users. Well, the
[00:20:01] mechanism also monitors current GPU load
[00:20:04] and decides in real time the length of
[00:20:06] the drafts it accepts. This ensures the
[00:20:09] best possible trade-off between speed
[00:20:11] and hardware performance. During
[00:20:13] off-peak hours, for example, when there
[00:20:15] are relatively few users, the system
[00:20:17] notices that it has spare GPU capacity,
[00:20:20] so it loosens up, letting the draft
[00:20:22] model guess more words at once. This
[00:20:25] uses the extra available power to make
[00:20:27] each response faster for users. But,
[00:20:30] during busy hours, it senses the added
[00:20:32] strain. GPU capacity becomes low, so it
[00:20:35] shortens how many words the draft model
[00:20:37] is allowed to guess. Individual
[00:20:40] responses do get a bit slower, but this
[00:20:41] protects the system as a whole from
[00:20:43] slowing down or crashing under load. So,
[00:20:46] we have assembled the pieces. We have a
[00:20:49] fast hybrid intern generating drafts. We
[00:20:52] have a confidence head evaluating the
[00:20:54] output of the draft and deciding when it
[00:20:57] should be cut off. We also have an
[00:20:58] algorithm that looks at the GPU load in
[00:21:01] real time to automatically adjust the
[00:21:03] drafts that it receives. This is a
[00:21:05] completely organic and self-regulating
[00:21:08] engine. It's a beautifully designed
[00:21:10] optimization for the entire stack, from
[00:21:13] software to hardware, as expected from
[00:21:15] the Deep Seek team. And if we look at
[00:21:17] the results in production, it's
[00:21:19] extremely impressive. If you compare
[00:21:21] this new D Spark method against Deep
[00:21:24] Seek's previous MTP system, which only
[00:21:27] predicts one word or token at a time,
[00:21:29] you can see that this new D Spark
[00:21:31] delivers a 60 to 85% increase in
[00:21:34] generation speed without any loss in
[00:21:37] quality. That's the key here. We're
[00:21:39] essentially getting faster speeds
[00:21:41] without any sacrifice in quality. In
[00:21:43] fact, get this. If the researchers set a
[00:21:45] fixed rule saying that every user must
[00:21:48] get at least 120 tokens per second, then
[00:21:52] the old MTP system broke down fast. It
[00:21:54] could only serve a small number of users
[00:21:57] before it crashed because the software
[00:21:59] and hardware were just not optimized. On
[00:22:01] the other hand, D Spark avoided this
[00:22:03] because it's smarter about resource use.
[00:22:06] It knows when to use longer drafts or
[00:22:08] when to end a draft early to save GPU
[00:22:11] power. As a result, it could achieve an
[00:22:14] almost 700%
[00:22:16] higher total system output, which is an
[00:22:18] insane improvement. And again, all of
[00:22:21] this did not affect output quality. In
[00:22:23] fact, because of this dynamic traffic
[00:22:25] cop system, remember this is the
[00:22:27] mechanism that allows D Spark to adjust
[00:22:29] itself automatically, it can now handle
[00:22:32] combinations of speed and user capacity
[00:22:35] that weren't possible on the same
[00:22:37] hardware before. You can see this new D
[00:22:39] Spark method is able to process way more
[00:22:42] data even as the number of concurrent
[00:22:44] requests from users increases. So, in a
[00:22:47] nutshell, that is the D Spark system by
[00:22:50] Deep Seek. When you don't have unlimited
[00:22:52] GPUs, unlimited money, or unlimited
[00:22:55] people, you're forced to be clever. And
[00:22:57] D Spark is a perfect example of this
[00:22:59] clever engineering. They solved a
[00:23:01] problem that the industry assumed was
[00:23:03] not solvable. And from that, they were
[00:23:05] able to significantly increase the speed
[00:23:08] and output of AI models without
[00:23:10] affecting quality. And that's what makes
[00:23:12] these publications from DeepSeek so
[00:23:14] fascinating to read. Their ingenuity is
[00:23:17] just out of this world. And as always,
[00:23:19] they've released the code to this
[00:23:21] already. So, I'll link to this GitHub
[00:23:23] repo in the description below, which
[00:23:25] contains instructions and the code to
[00:23:28] run DeepSpark. Plus, this is released
[00:23:30] under a very permissive MIT license.
[00:23:33] It's awesome that the DeepSeek team is
[00:23:35] willing to reveal the details to this,
[00:23:37] especially all this infrastructure stuff
[00:23:39] on how to actually deploy this to a data
[00:23:42] center and run it efficiently. This is
[00:23:45] incredibly valuable information, and
[00:23:47] it's often top secret for the closed
[00:23:49] labs out there. These are like industry
[00:23:51] secrets, which the closed labs
[00:23:53] definitely don't want you or any
[00:23:54] competitor to know about. But here,
[00:23:56] DeepSeek is revealing all these details.
[00:23:59] Plus, the awesome thing is this
[00:24:00] DeepSpark mechanism has already been
[00:24:03] implemented into their latest DeepSeek
[00:24:05] V4 model. So, I'll link to this Hugging
[00:24:07] Face page in the description below,
[00:24:09] where you can download the latest
[00:24:11] DeepSeek model with DeepSpark
[00:24:14] implemented. And in theory, this should
[00:24:16] run even faster and more efficiently
[00:24:18] compared to the previous version, which
[00:24:20] by the way, is already insanely fast and
[00:24:22] cheap. This is the fastest and most
[00:24:25] efficient frontier model out there. But
[00:24:27] they just made it even faster. Anyway,
[00:24:29] this is one of the more technical papers
[00:24:31] I reviewed so far on my channel. So,
[00:24:33] hopefully I made it easy for you to
[00:24:35] digest. In fact, the paper is jam-packed
[00:24:37] with a ton of additional technical
[00:24:39] details, which I didn't have time to
[00:24:41] cover. So, if you're interested in
[00:24:43] digging deeper, I'll link to this
[00:24:45] original paper in the description below
[00:24:47] as well. Let me know in the comments
[00:24:48] what you think of this. As always, I
[00:24:50] will be on the lookout for the top AI
[00:24:53] news and tools to share with you. So, if
[00:24:55] you enjoyed this video, remember to
[00:24:57] like, share, subscribe, and stay tuned
[00:24:59] for more content. Also, there's just so
[00:25:02] much happening in the world of AI every
[00:25:04] week. I can't possibly cover everything
[00:25:06] on my YouTube channel. So, to really
[00:25:08] stay up-to-date with all that's going on
[00:25:11] in AI, be sure to subscribe to my free
[00:25:14] weekly newsletter. The link to that will
[00:25:16] be in the description below. Thanks for
[00:25:18] watching, and I'll see you in the next
[00:25:20] one.
