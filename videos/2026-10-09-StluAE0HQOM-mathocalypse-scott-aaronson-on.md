---
record_id: "youtube:StluAE0HQOM"
video_id: StluAE0HQOM
title: "Mathocalypse! Scott Aaronson on OpenAI's flood of AI math breakthroughs"
channel: Dr. Samuel Allen Alexander
url: "https://www.youtube.com/watch?v=StluAE0HQOM"
watched_date: "2026-10-09"
watched_at: "2026-10-09T23:58:12Z"
watch_count: 1
duration_seconds: 2028
source: youtube-history-browser
added_date: ""
history_label: Oct 9
history_order: 108
watched_at_precision: date-from-history-label
watched_percent: 13
estimated_watched_seconds: 264
transcript_status: fetched
transcript_content_hash: 60fdf30cf778c9d033327fcbd8ff09a4a6e2613076e876b600db0449fcb6f4ce
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: claude-haiku-4-5
tagging_model: skipped
proposed_tags: []
proposed_entities: []
topic_domain: other
status: new
routed_to: null
---

## Summary

OpenAI released approximately 372–400 major mathematical breakthroughs, including proofs of decades-old open problems: the Unique Games Conjecture (which complexity theorist Dana Moshkovitz spent her career pursuing), L=BPL, Hilbert's 10th problem over the rationals, improvements to integer multiplication, and partial progress on the Riemann Hypothesis and other Millennium Prize problems. The proofs are extraordinarily difficult to parse—so cryptic that even expert mathematicians describe them as "alien"—and no human has fully understood most of them yet. The model solved these through vanilla inference at ~3 hours of compute per problem, achieving roughly 5% success on the 8,000 hardest open problems tested. Anthropic took a contrasting approach by paying expert mathematicians (Virginia Williams and Josh Almond) to write and explain their own breakthroughs, while OpenAI simply dumped the raw results publicly.

For researchers and mathematicians, the actionable shift is clear: the field must transition from problem-solving to problem-explanation. The race now is to understand, verify, and digest these AI proofs—work that will require sustained collaborative effort across institutions. Mathematicians should engage directly with this archive, working through proofs using AI assistance where needed, since understanding the "paths" to these peaks (not just teleporting to the summit) remains valuable for the discipline. Watch cryptography especially, as its absence from the release suggests AI companies may be privately investigating whether they can break existing protocols—a development with immediate practical and security implications.

## Transcript

[00:00:00] A couple days ago, OpenAI shattered
[00:00:03] mathematics with a massive publication
[00:00:06] of almost 400 major results. And among
[00:00:09] those were some key results about
[00:00:12] complexity theory. So, let's see what
[00:00:14] world's leading complexity theory expert
[00:00:16] Scott Arensson has to say. I love the
[00:00:19] title of this post, The Math aocalypse.
[00:00:22] I'm imagining angels with glowing eyes
[00:00:25] and comets and rivers of blood. I think
[00:00:28] that's kind of the sense a lot of elite
[00:00:30] mathematicians have of this whole turn
[00:00:32] of events. I'm Dr. Samuel Allen
[00:00:35] Alexander, mathematician and philosopher
[00:00:38] still here. Let's see what Scott Aronson
[00:00:41] has to say. He quotes from friend of the
[00:00:44] blog Omar Reinold. Then they came for
[00:00:47] Navier Stokes and I said nothing because
[00:00:49] I never worked on Navier Stokes. But
[00:00:51] when they came for RL versus L, I
[00:00:54] realized that things are serious. This
[00:00:56] is some complexity theory business here.
[00:00:59] I'm not sure what RL and L stand for.
[00:01:01] It's not reinforcement learning.
[00:01:04] Last night, my 9-year-old son was
[00:01:06] taunting my wife, complexity theorist
[00:01:09] Dana Moshkovitz, as follows. Mommy, I
[00:01:12] heard you got cooked. I heard that a
[00:01:14] robot solved the math problem you worked
[00:01:16] on for your whole career. O.
[00:01:18] Hey, kids can be merciless, can't they?
[00:01:20] And so can AIS.
[00:01:24] While my son was being a brat, he also
[00:01:26] wasn't wrong. Whether you're thrilled
[00:01:28] like me, depressed,
[00:01:31] angry, or whatever else about it,
[00:01:34] yesterday was surely one of the biggest
[00:01:37] days in mathematical history. Uh missing
[00:01:39] word here, yet. He's missing the word
[00:01:43] yet at the end of this sentence. And
[00:01:46] yes, among the 372
[00:01:48] huge results released yesterday by
[00:01:51] OpenAI on the recommendation of its
[00:01:52] advisory group of Timothy Gowowers,
[00:01:54] Edward Written and other distinguished
[00:01:56] mathematicians was a proof of subash's
[00:01:58] unique games conjecture or UGC. A
[00:02:02] statement that my wife has worked toward
[00:02:04] proving for the entire time I've known
[00:02:06] her. The unique games conjecture implies
[00:02:10] that a whole slew of optimization
[00:02:13] problems really are NP hard, even if you
[00:02:16] just want an approximation that's
[00:02:18] slightly better than what you get from
[00:02:19] semi-definite programming relaxation,
[00:02:21] which is one of our main tools.
[00:02:24] Or at least we're pretty sure it's a
[00:02:26] proof. There's a lean certificate, as
[00:02:29] there are for some of the other 372
[00:02:31] breakthrough results. But it also
[00:02:34] appears that no human has understood
[00:02:36] just about any of these proofs yet. The
[00:02:39] race to do so has just started. If you
[00:02:42] want an on the ground sense of what the
[00:02:44] race is going to be like, here's some of
[00:02:46] what Dana texted me last night. So, this
[00:02:48] is Scott Aronson's wife's text. And this
[00:02:50] is a woman who is working for much of
[00:02:52] her life. She she's a professional
[00:02:54] complexity theorist herself, and she's
[00:02:56] been working much of her life on proving
[00:02:57] the unique games conjecture. And then
[00:03:00] open AI proved that in something like
[00:03:03] about 3 hours apparently.
[00:03:05] Wow. So here's her text. It feels like
[00:03:09] something written by someone who's on
[00:03:11] psychedelics.
[00:03:14] So much unclear and doesn't make sense.
[00:03:17] Lots of named dropping of previous work
[00:03:18] without discussing why it can be used
[00:03:20] despite impossibility results.
[00:03:23] Basically, the paper is so horribly
[00:03:25] written that it's impossible to read it
[00:03:27] without AI help.
[00:03:29] I wonder if that's actually OpenAI's
[00:03:31] angle. Deliberately publish the papers
[00:03:34] so obfiscated that you have to use AI to
[00:03:36] read them and that means you have to pay
[00:03:38] the big tech companies to read them.
[00:03:40] Wow, fantastic strategy. She the text
[00:03:44] continues, I asked Astra for reasonable
[00:03:46] completeness and soundness claims of the
[00:03:48] noise gadget and it gave them by
[00:03:50] combining claims from all over the
[00:03:52] paper. They also have direct optimal NP
[00:03:55] hardness of approximation proofs for the
[00:03:57] main applications of the unique games
[00:03:59] conjecture max cut and all CSP that
[00:04:01] bypass the unique games conjecture.
[00:04:04] So the unique games conjecture was
[00:04:07] wanted among other things to prove
[00:04:09] various other results which were known
[00:04:11] to follow from it. But apparently open
[00:04:13] AI found proofs of those things not even
[00:04:15] requiring the unique games conjecture.
[00:04:19] The unique game's conjecture proof
[00:04:20] invents a completely new bizarre code
[00:04:23] with a noise test. It's some crazy
[00:04:25] recursive construction. Well, so much
[00:04:28] for all those mathematicians who keep
[00:04:30] going on and on about how AI can't
[00:04:32] invent new things, right? How AI can't
[00:04:34] isn't creative. It just combines
[00:04:37] existing things. Rest in peace,
[00:04:39] gentlemen.
[00:04:42] It's not the long code, not the short
[00:04:44] code. Some alien craziness. I still
[00:04:48] think that there maybe is a proof that
[00:04:50] uses the half space code which is
[00:04:52] natural. The citations are often
[00:04:54] irrelevant and confusing.
[00:04:56] Well, maybe that's because uh what we're
[00:04:59] talking about here is the Platonic realm
[00:05:01] of ideals which contains all these
[00:05:03] theorems which are eternal and
[00:05:05] independent of humans. Whereas the
[00:05:07] citations reside in what neoplatonists
[00:05:10] call the sensible world, which is not
[00:05:14] eternal and unchanging and is not
[00:05:17] independent of humans. I'm semi- joking
[00:05:19] there, of course, but also semi-serious.
[00:05:22] She continues, "A possible future is a
[00:05:25] math world that's heavenly if you have
[00:05:27] vision/creative ideas that AI could help
[00:05:29] check and implement." Yeah. Yes. Yes. I
[00:05:32] keep saying this on the channel. I'm
[00:05:34] living in heaven right now. I'm thankful
[00:05:36] I'm not one of those highly paid elitist
[00:05:38] mathematicians because they're living in
[00:05:40] hell right now,
[00:05:42] she concludes. And of course, there's a
[00:05:44] lot for us to learn from the aliens.
[00:05:46] Yeah, that pretty solidly knocks down
[00:05:50] the whole it's not really creative
[00:05:52] crowd.
[00:05:54] Uh what's more creative than something
[00:05:57] that strikes an expert in the field as
[00:05:59] literally alien? This is literally as if
[00:06:03] we made contact with an alien species
[00:06:06] with their flying saucers lifting cows
[00:06:08] up with their tractor beams and we get
[00:06:11] to peek into their math textbooks.
[00:06:14] Scott then says, "If you're wondering
[00:06:16] what emotions Dana is feeling, his wife
[00:06:19] who just found out that a whole bunch of
[00:06:22] her whole professional career was
[00:06:25] essentially wasted. Well, probably all
[00:06:29] of them and feel all the emotions. Even
[00:06:32] while a central career aspiration has
[00:06:35] fallen to a robot, there are at least
[00:06:37] two mitigating factors for her. First,
[00:06:40] she can feel vindicated that the unique
[00:06:42] games conjecture was true after all.
[00:06:44] Something she never doubted, even while
[00:06:46] many of her colleagues did.
[00:06:50] Second, all of us in math and in
[00:06:52] theoretical computer science and
[00:06:53] mathematical physics, at least those who
[00:06:55] cared about solving crisply stated
[00:06:56] problems, are now in the same boat.
[00:06:59] Yeah, it's the great equalizer.
[00:07:01] Elite mathematicians are now in the same
[00:07:03] boat as the rankest of amateurs. And
[00:07:06] that is a good thing because elite
[00:07:09] elitists are never good for a field.
[00:07:11] They always lead it to become inbred and
[00:07:16] exclusive. all kill all elitists or in
[00:07:21] Minecraft in Minecraft.
[00:07:24] Next section. Besides the unique games
[00:07:26] conjecture, here's a small sampling of
[00:07:28] the treasures from Aladdin's cave. I
[00:07:31] love that metaphor there. Here's a small
[00:07:34] sampling of the treasures from Aladdin's
[00:07:36] cave that I'll probably paying the most
[00:07:38] attention to over the coming weeks.
[00:07:40] Weeks? How about years? L equals BPL,
[00:07:44] i.e. probabilistic log space and
[00:07:45] deterministic log space are the same
[00:07:47] thing. One of the great dandomization
[00:07:49] conjectures short of P equals BPP,
[00:07:52] though its truth was never in serious
[00:07:53] doubt, there was a whole sub community
[00:07:55] focused on proving this. Yeah. And I
[00:07:58] predicted when I read through the
[00:08:01] through OpenAI's release on live stream,
[00:08:04] I predicted we would see Scott talking
[00:08:06] about exactly this result because this
[00:08:09] is exactly the bread and butter of
[00:08:11] complex of complexity theorists. And by
[00:08:14] the way, you can get a flavor of what
[00:08:16] complexity theory is like looking at all
[00:08:17] this stuff. All these acronyms and
[00:08:19] they're they're saying which ones are
[00:08:20] subsets of the others. Of course, the
[00:08:22] one everybody knows about is P equals MP
[00:08:25] or P not equal to MP. That's a famous
[00:08:27] open problem. But if you actually get
[00:08:29] into complexity theory, P and MP are
[00:08:31] just the tip of the iceberg. There's
[00:08:32] millions of these BPP plus BPL mod
[00:08:38] L. They just basically they're churning
[00:08:41] out papers because they have a million
[00:08:42] PhD students and they got to write
[00:08:44] something and they they don't know how
[00:08:45] to prove P is not equal to MP. So let's
[00:08:48] vary things and blah blah blah. But a
[00:08:51] whole sub community devoted to this
[00:08:53] particular part of complexility theory
[00:08:56] has apparently become obsolete. L equals
[00:08:59] BPL. And I'm almost certain that between
[00:09:02] L and BPL there was a whole crystal
[00:09:04] latice of intermediate
[00:09:07] uh objects which has all now been
[00:09:09] collapsed. They're all the same thing.
[00:09:13] Next bullet point. The fier transform
[00:09:14] and integer multiplication in less than
[00:09:17] bigo of n login time breaking a barrier
[00:09:19] that had stood since the 1960s. The new
[00:09:22] running time, if you're curious, is bigo
[00:09:24] of n log to the 0.9999999,
[00:09:28] give or take some nines. Well, I think
[00:09:30] you're uh we need to give a lot more
[00:09:32] nines. The actual bound is hard to
[00:09:36] express in plain English. Positive
[00:09:38] solution to the unitary synthesis
[00:09:40] problem which Greg Cooperberg and I
[00:09:42] posed back in 2007. For every n cubit
[00:09:45] unitary transformation u, there exists a
[00:09:48] classical oracle a such that u can be
[00:09:50] implemented in quantum polinomial time
[00:09:52] with access to a.
[00:09:55] This is the opposite of what most of us
[00:09:57] expected and could have implications for
[00:09:59] eg the computational problem of decoding
[00:10:01] hawking radiation from a black hole and
[00:10:04] many other problems in quantum
[00:10:05] complexity theory if we had an efficient
[00:10:09] way to construct the oracle a which this
[00:10:11] paper doesn't give. And then he added
[00:10:13] later a link to a beautiful blog post by
[00:10:16] friend and colleague Dakshida Kurana
[00:10:18] about the years she spent working on
[00:10:20] this problem. Unlike me and most others,
[00:10:22] she believed correctly in a positive
[00:10:24] answer to it and her current feelings as
[00:10:26] she works through the AI's proof.
[00:10:28] Another person whose life work was just
[00:10:30] done in three hours by AI. Hey, my
[00:10:34] decision to be lazy all these years has
[00:10:36] finally paid off and I'm vindicated.
[00:10:40] Parody is not in QAC0. One of the great
[00:10:43] questions of quantum complexity theory
[00:10:45] since 1999 that many of my colleagues
[00:10:47] had been closing in on. Well, not
[00:10:49] closing in on fast enough, I guess.
[00:10:52] Nearly fourth power separation between
[00:10:53] randomized and quantum query complexity
[00:10:55] for total boolean functions. A favorite
[00:10:57] problem of mine since 1998 when we knew
[00:11:00] only that the optimal separating
[00:11:02] exponent was between two and six. For
[00:11:04] the past few years, we knew it was
[00:11:05] between three and four. So this finally
[00:11:07] closes that story. A super quadratic
[00:11:10] separation between sensitivity and block
[00:11:12] sensitivity.
[00:11:14] Aerial law for 2D gapped Hamiltonians.
[00:11:16] One of the main open problems in
[00:11:18] Hamiltonian complexity.
[00:11:20] Matrix multiplication in big O of N to
[00:11:22] the 9/4s time. A rational exponent for
[00:11:25] once and via a completely different
[00:11:27] approach than was used for big O of N to
[00:11:29] the 2.373 and so forth. Reading between
[00:11:32] the lines here, another steak into the
[00:11:35] chest of those vampires who keep
[00:11:38] whining. Oh, AI is just combining
[00:11:40] disparage results. It's not really
[00:11:42] creative. It's not really doing anything
[00:11:44] new. They are huh they are not looking
[00:11:48] in a good light right now. Big omega of
[00:11:51] nub lower bound on the determinant
[00:11:53] complexity of the permanent improving
[00:11:55] the previous best bound which was
[00:11:57] quadratic.
[00:11:58] a randomized polytime algorithm to
[00:12:00] approximately count the number of
[00:12:02] perfect matchings in a general graph as
[00:12:04] well as a randomized nearly linear time
[00:12:05] algorithm for finding a maximum
[00:12:07] switching in I'm sorry a maximum
[00:12:09] matching in such a graph.
[00:12:12] And last but not least, uncomputability
[00:12:15] of solving polomial equations over the
[00:12:17] rational numbers. Yes, this is my
[00:12:19] favorite one of the whole bunch.
[00:12:20] Everybody who was watching my live
[00:12:22] stream saw me just lose my mind when I
[00:12:24] saw that. Hilbert's 10th problem over
[00:12:26] the rationals finally resolved. I spent
[00:12:29] an entire semester at Ohio State
[00:12:32] University studying Hilbert's 10th
[00:12:34] problem over the naturals under teacher
[00:12:38] Dr. Harvey Freriedman who's probably
[00:12:42] neglected his duty by devoting the
[00:12:44] entire logic seminar to just that one
[00:12:47] result. But I think it was worth it and
[00:12:49] it gave me a background so that now I
[00:12:52] can appreciate that Hilbert's 10th
[00:12:54] problem is solved over the rationals.
[00:12:57] Uh Scott says this was arguably the
[00:13:00] biggest open problem in computability
[00:13:02] theory. Yeah, not arguable at all. It's
[00:13:04] it flat out is there's no arguing it
[00:13:07] whatsoever. Note that uncomputability of
[00:13:10] solving dofantine equations i.e.
[00:13:12] polomial equations over the integers was
[00:13:13] proved in the 1970s giving a negative
[00:13:15] answer to Hbert's 10th problem.
[00:13:18] I actually wrote a undergrad paper about
[00:13:21] this in Desh That's
[00:13:23] number theory class at University of
[00:13:26] Arizona. Deshakur is a student of John
[00:13:28] Tate, the very famous number theorist.
[00:13:30] Uh, of course, nothing original. It was
[00:13:32] just an undergrad like book report
[00:13:33] basically. But yeah, I've been following
[00:13:35] Hilbert's 10th for a long time.
[00:13:39] How many of the DPRM people are even
[00:13:41] still alive? I know that Davis passed
[00:13:44] away just a couple years ago. I was
[00:13:45] actually very very lucky to be able to
[00:13:48] talk to him at a conference Martin Davis
[00:13:52] shortly before he died and that
[00:13:54] conversation is actually preserved
[00:13:56] somewhere in the internet because it was
[00:13:57] one of those during lockdown
[00:13:59] conversations so it was all recorded. Um
[00:14:02] but yeah, how many of the people of DPRM
[00:14:04] Davis, Putnham, Matt Seavich, and
[00:14:07] Robinson, how many of them are still
[00:14:08] alive even?
[00:14:11] Anyway, any of the above alone could
[00:14:13] easily have been result of the year in
[00:14:15] some area and in some cases like unique
[00:14:17] games and L equals BPL in all of CS
[00:14:20] theory.
[00:14:22] And there's a lot that I've left out.
[00:14:24] Feel free to share in the comments
[00:14:25] whatever is making your eyes bug out.
[00:14:27] There are equally astounding wonders in
[00:14:29] number theory, combinotaurics, algebraic
[00:14:31] geometry, analysis, and pretty much
[00:14:33] every other area of math, most of which
[00:14:35] I'll never understand. Although I'll
[00:14:37] note that it includes partial progress
[00:14:38] toward the Reman hypothesis and the
[00:14:40] Hodgej conjecture and the BSD
[00:14:41] conjecture, i.e. the majority of the
[00:14:44] remaining millennial pro millennium
[00:14:46] problems.
[00:14:48] Um let's see.
[00:14:50] Yeah. uh here where he's saying like uh
[00:14:54] that
[00:14:56] these could have been result of the year
[00:14:57] in some areas. If you had proved
[00:15:01] Hilbert's if you had settled Hubert's
[00:15:03] Hilbert's 10th question over the
[00:15:05] rationals in 2025
[00:15:08] that would have been unquestionably
[00:15:11] the result of the year in all of
[00:15:13] mathematics.
[00:15:15] And that was just one of almost 400
[00:15:17] results that OpenAI released a couple
[00:15:19] days ago. Scott says we can take solace
[00:15:22] in what's missing from the list. P not
[00:15:24] equal to NP isn't there nor even P= BPP
[00:15:28] or next proper subset of P mod. See what
[00:15:32] I was saying earlier? This is this is
[00:15:33] complexibility theory. Are you hungry
[00:15:36] yet?
[00:15:38] If if you love lots of acronyms and
[00:15:40] inclusions and exclusions, then
[00:15:42] complexity theory is for you. and surely
[00:15:45] not for lack of trying. He goes on,
[00:15:47] apparently the greatest open problems of
[00:15:48] theoretical computer science are indeed
[00:15:50] pretty hard. I've also seen people in
[00:15:53] various forums talking about how there's
[00:15:55] a lack of anything related to big
[00:15:58] cardinals in the release. I haven't
[00:16:01] fully read through the whole release.
[00:16:02] I've read through about I think about
[00:16:04] 50% of it, but I didn't see anything
[00:16:06] about big cardinals. Is that because
[00:16:08] large cardinals are somehow inherently
[00:16:11] above what AI can do? Probably not.
[00:16:14] Probably just that it's a very obscure
[00:16:16] field. Next section, Scott says, "Oh,
[00:16:18] lest I forget, one day before the open
[00:16:21] AI dump, meaning Monday evening,
[00:16:23] Virginia Williams and Josh Almond posted
[00:16:25] an archive preprint that solves the
[00:16:28] threesome problem in bigo of n to the
[00:16:30] 1.9992 time and the all pairs shortest
[00:16:32] paths problem in big of n to the 2.995
[00:16:35] time, refuting half century old
[00:16:38] conjectures that the correct answers
[00:16:39] were nus little of one and n 3 - little
[00:16:43] of one respectively. In this case, it
[00:16:44] wasn't an open AI model that supplied
[00:16:46] the crucial idea. It was an anthropic
[00:16:48] one. But anthropic then took a different
[00:16:50] approach from open AAI. Rather than post
[00:16:52] the undigested solutions to the world,
[00:16:54] it gave Virginia and Josh the
[00:16:55] opportunity to write and denounce a
[00:16:57] digested version in exchange for
[00:16:59] compensation.
[00:17:01] That's actually very interesting. So,
[00:17:04] OpenAI and Anthropic took very different
[00:17:06] approaches. Anthropic followed more
[00:17:10] closely the suggestions by the math
[00:17:12] elitists. The math elitists were
[00:17:15] basically saying, "Please give us money
[00:17:17] to explain these results." And Anthropic
[00:17:20] apparently did exactly that. I wonder
[00:17:22] how they chose Virginia and Josh. I
[00:17:24] guess Virginia and Josh I guess Virginia
[00:17:26] Williams and Josh Almond were probably
[00:17:27] experts in the field. It probably also
[00:17:29] helps that Virginia Williams is a member
[00:17:31] of a notable minority demographics wise
[00:17:35] in the mathematical community.
[00:17:38] Conspiracy theorists make of that what
[00:17:40] you will. Uh but it's interesting to see
[00:17:44] the two companies gambled and you see
[00:17:46] which company got the payoff.
[00:17:49] PR-wise, OpenAI's move was definitely
[00:17:53] won the contest. Anthropic followed the
[00:17:56] experts advice, gave money to experts to
[00:17:59] explain their result and that PR move
[00:18:04] vanished in obscurity. Open AAI dumped a
[00:18:07] massive collection of results without
[00:18:09] paying any experts to explain them and
[00:18:13] OpenAI won. Uh I think Anthropic is
[00:18:16] probably due to win the next round. I I
[00:18:19] think Anthropic is a very strong company
[00:18:21] and it's kind of unfortunate in some
[00:18:24] sense that Anthropic lost that little
[00:18:25] contest. Anthropic took the elitist
[00:18:28] mathematicians on good faith. The
[00:18:29] elitist mathematicians suggested pay us
[00:18:32] to explain your results before he
[00:18:34] published them. Anthropic followed that
[00:18:36] advice and didn't gain a lot of PR from
[00:18:39] it. It was bad advice.
[00:18:42] Scott says, "These have emerged as the
[00:18:44] two main models for communicating AI
[00:18:46] math breakthroughs, and they both have
[00:18:48] strengths and weaknesses. The OpenAI
[00:18:51] model sets up a crazy race among humans
[00:18:52] to digest and explain a messy AI proof.
[00:18:55] Work that could easily be some
[00:18:57] combination of thankless, barely
[00:18:58] credited, competitive, and unfun. While
[00:19:00] the anthropic model puts a private
[00:19:02] company in the position of picking and
[00:19:04] choosing which human mathematicians get
[00:19:06] to be the emissaries of the AI. Don't
[00:19:08] know. What do you guys think? Well, good
[00:19:10] question. But I for one think open AI
[00:19:12] has the better approach there. And
[00:19:14] that's not saying anything about the
[00:19:16] strength of the models. I'm not
[00:19:18] qualified to weigh in on which models
[00:19:20] are stronger. But as far as PR strategy,
[00:19:22] I think Open AI is the better one. Look,
[00:19:26] we've had hundreds of years of elitists
[00:19:28] getting all the money and all the glory
[00:19:30] and being basically given the keys to
[00:19:32] the gates to keep. And what has it
[00:19:36] gotten us compared to what we got from
[00:19:39] OpenAI just a couple days ago?
[00:19:42] Basically, all of the major advances in
[00:19:44] mathematics in the last hundred years,
[00:19:46] almost all of them came out a couple
[00:19:48] days ago thanks to OpenAI
[00:19:51] and [clears throat] not thanks to those
[00:19:52] elitist gatekeepers.
[00:19:55] Next section. For those who are
[00:19:57] wondering, apparently the AI model that
[00:19:59] produced all these wonders was not
[00:20:02] bespoke contraption of 10,000 agents
[00:20:04] burning millions of dollars worth of
[00:20:05] compute as was used for example to
[00:20:07] construct a finite envelope for the
[00:20:08] Navier Stokes equations. Instead, it was
[00:20:11] simply the latest internal OpenAI model,
[00:20:13] one that might be released to paying
[00:20:15] ChatGpt customers within the next couple
[00:20:17] of months depending on the
[00:20:18] recommendations of OpenAI's safety
[00:20:20] board.
[00:20:22] and he puts in parenthesis, "My
[00:20:23] nine-year-old son says,"Oh, they
[00:20:25] definitely shouldn't release that. If it
[00:20:26] could solve all those math problems, it
[00:20:28] can't possibly be safe."
[00:20:30] Hey, if we survived the Cold War, then
[00:20:32] there must be some guardian angel
[00:20:34] looking out for us, so I think we'll be
[00:20:36] okay. Scott says, "Apparently, they used
[00:20:39] about three hours of GPT prolevel
[00:20:40] compute on average per problem solved."
[00:20:43] Yeah. So, what he's talking about here
[00:20:44] was for the solution to the Navier
[00:20:47] Stokes Millennium problem. Apparently,
[00:20:50] open AI had thousands of agents burning
[00:20:53] millions of dollars worth of compute to
[00:20:55] solve Navier Stokes. Whereas for this
[00:20:58] latest slew of almost 400 major results,
[00:21:02] they just had the models just running in
[00:21:05] the vanilla way apparently and they each
[00:21:07] model ran for about on average three
[00:21:10] hours in order to solve its respective
[00:21:12] problem. Also, Scott says, "If you were
[00:21:15] wondering, apparently they tried the
[00:21:17] model on about 8,000 problems. So, right
[00:21:19] now it merely solves about 5% of the
[00:21:22] long-standing open mathematical problems
[00:21:24] that it's asked about. The problems that
[00:21:26] whole communities have spent years on
[00:21:28] after a single three-hour attempt on
[00:21:29] them. Yeah, it's not that good. It's
[00:21:32] only 5%. It only gets about 5% of the
[00:21:36] hardest problems in mathematics when you
[00:21:38] run it in vanilla mode. Yeah. So, what
[00:21:40] will the percent percentage be if you
[00:21:42] devote as much attention as you spent on
[00:21:44] Navier Stokes on all of those 8,000
[00:21:45] problems?
[00:21:48] He also says, "I've been glad to see the
[00:21:50] computer science theory community rising
[00:21:53] to the occasion at the Simons Institute
[00:21:54] in Berkeley here at UT Austin and
[00:21:56] elsewhere. I've heard stories of
[00:21:59] researchers rushing to pour over the
[00:22:01] manuscripts and make sense of them and
[00:22:03] explain them because what else do we do?
[00:22:05] How else do we continue the craft to
[00:22:06] which we've devoted much of our lives?"
[00:22:09] If you want some sense of what things
[00:22:10] feel like now in math, imagine a hunter
[00:22:13] gatherer who's spent his entire life
[00:22:15] learning to survive deep in an
[00:22:17] unforgiving rainforest. Then a giant
[00:22:19] resort hotel springs up right next to
[00:22:22] him with a helellipad and heated pools
[00:22:24] and Airbnbs. And without missing a beat,
[00:22:26] the hunter gatherer says, "All right,
[00:22:28] fine. So now my new job is to run
[00:22:29] wilderness retreats for the tourists or
[00:22:31] something." [laughter]
[00:22:32] Yeah, that's what mathematicians will be
[00:22:34] doing in the future. Mathematicians will
[00:22:36] be the tour guides to the Platonic realm
[00:22:38] of ideals. You can get a tour guide to
[00:22:40] guide you around. Over on your left, you
[00:22:43] see the Pythagorean theorem. And here on
[00:22:45] the right is the solution to the Navier
[00:22:47] Stokes equation.
[00:22:49] In quantum magazine, Jordana Chapel
[00:22:52] attempted a different metaphor. It's as
[00:22:54] if you were teleported to the peak of a
[00:22:56] tall mountain surrounded by fog. You
[00:22:58] have no idea where you are or what's
[00:23:00] around you. You do not know how your
[00:23:02] mountain connects to others, and you
[00:23:04] have no equipment to help you explore,
[00:23:06] no way to help someone else join you. If
[00:23:08] you had climbed the mountain yourself,
[00:23:09] you would have experienced how the human
[00:23:10] body adapts to altitude and changes in
[00:23:13] oxygen levels. You might have had to
[00:23:16] invent tools to navigate, to climb steep
[00:23:18] cliffs, or to make a shelter. You might
[00:23:20] have encountered a fellow explorer,
[00:23:22] gotten lost together in a hidden valley,
[00:23:23] and found a plant that could be turned
[00:23:25] into a life-saving medicine. Instead,
[00:23:27] you're perched at the peak but in the
[00:23:29] dark. While the maker of the
[00:23:30] teleportation machine tells you that you
[00:23:32] can explore the wilderness better than
[00:23:33] any human.
[00:23:35] For any of these mountains, if we care
[00:23:37] enough, I feel optimistic that we can do
[00:23:38] as we always have. Clear the fog and
[00:23:41] figure out the path except now using the
[00:23:42] teleportation machine to help guide us.
[00:23:45] The bigger challenge will be to nurture
[00:23:47] a community that still cares about the
[00:23:49] heroic adventure of finding the paths of
[00:23:51] these mountains in the world with the
[00:23:52] machine.
[00:23:54] Um well, if this metaphor holds true,
[00:23:57] then it actually ties in very nicely to
[00:23:59] the tour guide metaphor above. Um you
[00:24:02] know, because right now you can get to
[00:24:04] the top of Mount Fuji quite trivially.
[00:24:06] Just take a helicopter or whatever. Um
[00:24:09] but, uh that doesn't stop tons and tons
[00:24:12] of tourists from climbing it constantly
[00:24:14] every day. Well, every day when the
[00:24:16] weather permits. And I think it won't I
[00:24:19] think that in mathematics we're not
[00:24:21] going to have people just stop studying
[00:24:23] mathematics. I think we're going to have
[00:24:24] more people interested in mathematics
[00:24:26] than ever before. And we're already
[00:24:29] seeing that. We're seeing more people
[00:24:31] more attention paid to mathematics, more
[00:24:33] interest in mathematics in recent days
[00:24:36] than in the whole past 10 years
[00:24:38] combined. It's literally on the front
[00:24:40] pages of websites that are not related
[00:24:43] to mathematics. It's going mainstream.
[00:24:47] Scott also says, "Experience has shown
[00:24:49] that even now there will still be people
[00:24:52] explaining in patronizing tones why none
[00:24:54] of this is real and none of it counts.
[00:24:56] La I can't hear you." If such people
[00:25:00] were capable of being impressed by
[00:25:02] anything that happens in the empirical
[00:25:03] world of updating on anything, they
[00:25:06] would have already been impressed and
[00:25:08] already updated several years ago, long
[00:25:10] before things had reached the point of
[00:25:11] an actual mathocalypse. I love that word
[00:25:14] mthocalypse.
[00:25:16] So they'll say maybe the alleged
[00:25:18] solutions are not solutions at all but
[00:25:19] just AI slop. Or maybe none of the 372
[00:25:22] well-known open problems that were
[00:25:24] solved were real math problems. They
[00:25:25] just got glorified. They were just
[00:25:27] glorified puzzle contest contest puzzles
[00:25:30] and trivialities. Uh well I wouldn't
[00:25:33] call Hilbert's 10th problem for over the
[00:25:36] rationals a contest puzzle. Good grief.
[00:25:38] Talk about moving the goalposts. Moving
[00:25:40] the goalposts. They they're putting the
[00:25:42] goalposts into a giant howitzer and
[00:25:46] firing it into a neighboring country.
[00:25:48] After all, he says in parenthesis,
[00:25:50] there's still no Remon hypothesis. Yeah,
[00:25:52] until we get the Remon hypothesis, this
[00:25:54] AI is just overhyped junk, right? Gosh,
[00:25:57] what are they going to say when AI does
[00:25:58] prove the Remon hypothesis? Oh, it's
[00:26:01] just the Remon hypothesis.
[00:26:03] It's just overhyped.
[00:26:05] Or maybe the entire 4,000-y old
[00:26:07] discipline of mathematics needs to be
[00:26:08] jettisoned. Turns out that it was all
[00:26:11] just puzzle solving and trivialities.
[00:26:13] All that's different is that now the
[00:26:14] triviality stands unmasked. In any case,
[00:26:17] what really matters is that the true
[00:26:18] inner sanctum of human creativity hasn't
[00:26:20] been breached and probably never will
[00:26:22] be. And also that Sam Altman and Dario
[00:26:24] Ammoday are contemptable little nerds.
[00:26:28] Uh well, they're contemptable little
[00:26:30] nerds with a lot more money and power
[00:26:32] than you have.
[00:26:34] [clears throat] If you're still a
[00:26:36] proponent of that doomed worldview,
[00:26:38] still aboard the sinking ship, I
[00:26:40] encourage you in the strongest possible
[00:26:41] terms to read yesterday's other great
[00:26:43] contributions to AI discourse besides
[00:26:45] the open AI math aocalypse dump, namely
[00:26:47] Scott Alexander's open letter to Steven
[00:26:49] Pinker. I feel some responsibility for
[00:26:51] this as the person who first introduced
[00:26:53] Steven Pinker to the existence of the
[00:26:54] rationalist community and who also first
[00:26:57] introduced Steven Pinker to and Scott
[00:26:58] Alexander to one another. They had both
[00:27:01] been fans of each other's writing. And
[00:27:03] now Scott is challenging Steve to a
[00:27:04] literal duel with guns. What? I'm gonna
[00:27:07] have to go read that. For whatever it's
[00:27:09] worth, Steve is a longtime intellectual
[00:27:11] hero of mine, just as he is for Scott.
[00:27:13] And I also have to priv have the
[00:27:15] privilege of calling Steve my friend.
[00:27:17] But I found Scott's post to be one of
[00:27:18] the most devastating rejoinders to
[00:27:20] anything I've ever read. And I thought
[00:27:22] Scott's conclusion was exactly right.
[00:27:23] When it comes to AI risk, Steve's great
[00:27:25] challenge is now to accept and start
[00:27:26] using a more pinkerite epistemology.
[00:27:30] Uh
[00:27:32] interesting little glimpse into the
[00:27:35] internal drama of the field there. I
[00:27:38] don't I don't even know exactly what
[00:27:40] he's talking about. Haven't followed all
[00:27:42] that business. Uh that's more of the
[00:27:44] rationalist camp than the math science
[00:27:47] camp. Anyway, next section. Last night,
[00:27:49] while I should have been pouring over
[00:27:51] some of OpenAI's hundreds of papers and
[00:27:53] or writing this post, I decided to spend
[00:27:54] some time with my kids instead. Hey,
[00:27:56] it's never a bad idea to spend more time
[00:27:58] with your kids. They wanted a movie
[00:28:00] night, so I suggested something they'd
[00:28:02] never seen before, and that seemed chalk
[00:28:04] full of nononsense, practical guidance
[00:28:06] for the world in which they're going to
[00:28:07] grow up. [laughter]
[00:28:09] Terminator 2. Perfect. Oh, man. Very
[00:28:13] droll, sir. Very droll. I love it.
[00:28:17] Um
[00:28:18] uh yeah, what other movies would be
[00:28:22] appropriate? Uh there's always Stephen
[00:28:24] Spielberg's AI. And don't forget 2001
[00:28:26] Space Odyssey. Although that's not
[00:28:28] exactly appropriate for little kids.
[00:28:30] [laughter]
[00:28:31] Update. As several people have pointed
[00:28:33] out, cryptography is a sub field that's
[00:28:35] extremely conspicuous by its absence
[00:28:38] from Open AI's list of 376 papers. Ah,
[00:28:41] hot take on this, not mine, something
[00:28:42] I've seen people talking about on Hacker
[00:28:44] News and so on. If Open AI found major
[00:28:48] breakthroughs in cryptography, they
[00:28:50] might not be including those in the
[00:28:51] things they publish. they might be
[00:28:53] guarding those to use for themselves.
[00:28:56] You know, a lot of people are pointing
[00:28:59] out, hey, all these breakthroughs have
[00:29:00] absolutely no practical applications.
[00:29:02] Well, if something had practical
[00:29:03] applications, maybe Open AI wouldn't
[00:29:05] include that in the list because Open AI
[00:29:07] would like to have a monopoly on those
[00:29:08] applications. Anyway, Scott continues,
[00:29:11] "But my sources tell me that the AI
[00:29:13] companies have now started gingerly and
[00:29:15] discreetly investigating whether their
[00:29:17] latest internal models can break
[00:29:18] important cryptographic protocols and
[00:29:20] primitives. If they can, then it would
[00:29:23] certainly be nice to get ahead of things
[00:29:24] before the rest of the world figures out
[00:29:26] the same. Uh, nice. That's an
[00:29:28] understatement.
[00:29:29] For example, say you figured out that
[00:29:34] strong cryptography used in certain uh
[00:29:38] financial applications was in fact
[00:29:40] broken, then you could shortrun certain
[00:29:43] things and make an absolute
[00:29:46] slaughtering. And it wouldn't even be
[00:29:48] insider trading because all of this
[00:29:51] knowledge is right there in the Platonic
[00:29:53] realm of ideals. It's all public. All
[00:29:56] you have to do is walk to the
[00:29:57] appropriate part of the platonic realm
[00:29:58] of ideals and pick it up off the ground.
[00:30:01] Another update. The statement put out
[00:30:04] the advisory group on mathematics and
[00:30:06] the statement put out by the advisory
[00:30:08] group on mathematics and AI is very
[00:30:10] carefully phrased neither endorsing nor
[00:30:12] condemning what open AI did and is worth
[00:30:14] a read. Hinty quotes from it.
[00:30:18] As announced a few weeks ago, OpenAI has
[00:30:20] released a large collection of
[00:30:21] mathematical results generated by an
[00:30:22] internal model reporting solutions to
[00:30:24] hundreds of open questions. This is an
[00:30:27] important event for mathematics with
[00:30:29] consequences both for mathematics and
[00:30:31] for the mathematical community that
[00:30:32] extend far beyond the individual
[00:30:34] results. An important event. That's
[00:30:37] putting it rather mildly. This is a
[00:30:39] seismic 9.0 earthquake. It's a 10.0
[00:30:42] earthquake. We're shaking apart here.
[00:30:45] Agmi's advisory role should be
[00:30:47] interpreted as a judgment of the impact
[00:30:49] of these results. Uh should not be
[00:30:51] interpreted as a judgment of the impact
[00:30:53] of these results or an endorsement of
[00:30:54] the process by which OpenAI obtained
[00:30:56] them. We do not speak on behalf of the
[00:30:58] entire mathematical community and only
[00:31:00] the mathematical community can undertake
[00:31:01] the assessment that is needed. Making
[00:31:04] this work public is a first step. This
[00:31:06] releases the beginning not the
[00:31:08] completion of the process of human
[00:31:09] understanding and the incorporation of
[00:31:10] the work into mathematical knowledge. At
[00:31:12] the same time, the future of
[00:31:13] mathematical research cannot consist
[00:31:15] only of understanding results produced
[00:31:17] by AI labs. Mathematicians must also be
[00:31:20] able to formulate their own questions,
[00:31:22] develop their own approaches, and
[00:31:24] explore directions that have not been
[00:31:26] selected as examples of an AI systems
[00:31:28] capabilities. Equitable access to
[00:31:30] powerful research tools and adequate
[00:31:31] computational resources are essential to
[00:31:33] that freedom. Now, I assume because
[00:31:36] these mathematicians are saying that
[00:31:38] equitable access is required etc. I
[00:31:41] assume that means, for example, that
[00:31:42] they're going to be opening the doors of
[00:31:44] the science libraries at their
[00:31:46] respective institutions to the wide
[00:31:48] unwashed masses, people who have no
[00:31:50] affiliation at their institutes. Right.
[00:31:52] You're going to So, like at MIT, MIT is
[00:31:55] going to throw open the doors of their
[00:31:56] library and invite the mass in freely.
[00:32:00] Right. Right. Uh uh I'm I'm holding my
[00:32:04] breath here. When will that happen?
[00:32:07] Finally, they conclude. We reaffirm our
[00:32:09] published recommendations on responsible
[00:32:10] release. We have discussed them with
[00:32:12] OpenAI and appreciate the company's
[00:32:14] willingness to engage. While we consider
[00:32:17] these discussions constructive, it is
[00:32:20] ultimately up to the mathematical
[00:32:21] community to assess the extent to which
[00:32:23] our recommendations were followed
[00:32:24] successfully and whether there are
[00:32:26] others we should suggest. We remain
[00:32:28] committed to engaging with any Frontier
[00:32:30] AI lab on these questions and have
[00:32:31] already been in contact with several of
[00:32:33] them. Wow, fantastic article by Scott
[00:32:37] here. And
[00:32:39] it I love his overall optimistic
[00:32:43] attitude. You know, Scott is facing an
[00:32:48] existential crisis here. He is one of
[00:32:51] the elitists that I keep talking about.
[00:32:53] He is one of the world experts on
[00:32:55] complexity theory. And much of
[00:32:58] complexity theory has just been
[00:32:59] swallowed up by robots. And suddenly the
[00:33:04] gates that he's been keeping is a gate
[00:33:06] with no wall around it. It's just a gate
[00:33:08] standing in the middle of nowhere. And
[00:33:10] he's standing there holding his keys
[00:33:11] awkwardly like looking like right and
[00:33:13] left while people are just walking right
[00:33:15] past the gate. But nevertheless, Scott
[00:33:17] is very optimistic and very generous and
[00:33:21] so on and so forth. Major hat tip to
[00:33:22] Scott Aronson. I've always loved this
[00:33:24] guy's blog. I've been following this
[00:33:26] guy's blog for is it plural decades? It
[00:33:29] might be plural decades by this point.
[00:33:31] I'm not sure. Certainly more than one
[00:33:32] decade.
[00:33:34] And I love this expression, the
[00:33:36] mathocalypse.
[00:33:38] I'm Dr. Samuel Alen Alexander,
[00:33:39] mathematician and philosopher, reporting
[00:33:41] live from the mathocalypse. Please like,
[00:33:44] comment, and subscribe, and I'll see you
[00:33:46] in the next video.
