---
video_id: 3blQcTttmnE
title: Can We Tackle Security & Compliance in Our Deployment Pipeline?
channel: Modern Software Engineering
url: "https://www.youtube.com/watch?v=3blQcTttmnE"
watched_date: 2026-05-16
watched_at: "2026-05-16T12:00:00Z"
watch_count: 1
duration_seconds: 1243
source: youtube-history-browser
history_label: May 16
history_order: 174
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 124
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode discusses how security and compliance can be integrated into deployment pipelines rather than treated as heavy, adversarial processes. Through real-world examples—including Siemens Healthcare (medical device systems), a German investment bank, and LMAX exchange—the hosts demonstrate that regulatory compliance and continuous delivery are not only compatible but mutually reinforcing. The key insight is reframing compliance not as bureaucratic gatekeeping but as genuine safety mechanisms (e.g., "my job is to make sure nobody dies"). Automation is central: compliance checks, audit trails, and release documentation can be baked into the pipeline as build artifacts by linking deployment systems with issue trackers, enabling one organization to move from idea to production safely in under half a day while remaining fully compliant. Security follows similar principles—building "securable" systems through domain-driven design, clear APIs, small components, and layered testing—though it merits deeper exploration as a separate topic.

For your deployment pipeline, automate compliance documentation generation by connecting your CI/CD system to your issue tracking system, making release notes authoritative build artifacts that update automatically with commits and closed tickets. Establish lightweight criteria for a "fast path to production" (small changes, good test coverage, clear requirements) and enforce compliance rules via the pipeline itself rather than manual review, making it harder to deploy non-compliant code than compliant code. For security, focus on building systems with minimal attack surface and clear boundaries, then invest in both automated security testing (threat modeling, SAST/DAST) and periodic human penetration testing—crucially, treat pentesting findings as learning opportunities by automating tests to catch the same issues in your pipeline.

## Transcript

[00:00:00] Welcome to the modern software
[00:00:01] engineering channel. Today's one big
[00:00:03] question is can we tackle security and
[00:00:06] compliance in our deployment pipelines?
[00:00:08] I'm joined by Dan here and Dan's been a
[00:00:11] naughty boy. He's been making very long
[00:00:14] responses to one big question episodes.
[00:00:17] So today we're putting a timer on him.
[00:00:19] It's true.
[00:00:20] >> [laughter]
[00:00:21] >> It's true.
[00:00:22] Today there is a clock.
[00:00:24] Today there's a clock. Now however what
[00:00:26] Dave had what Dave doesn't know is is
[00:00:28] whether or not I will actually
[00:00:30] adhere to the clock in any way or
[00:00:32] whether it's purely decorative. I I
[00:00:34] think Dave does know that to be honest
[00:00:37] >> [laughter]
[00:00:37] >> and the answer is no you won't. To be
[00:00:40] fair Dave Dave also has the pull the
[00:00:42] stop button so he can just cut me off.
[00:00:44] >> [laughter]
[00:00:45] >> This episode is sponsored by Octopus
[00:00:48] Deploy. Octopus makes it easy to deploy
[00:00:51] software to Kubernetes, multi-cloud,
[00:00:53] on-premises infrastructure and anywhere
[00:00:56] else really. They automate the release,
[00:00:58] deployment and operations of your
[00:00:59] software and AI workloads with a tool
[00:01:02] that can handle continuous delivery at
[00:01:03] scale. Octopus also have tools that can
[00:01:06] help you to achieve regulatory
[00:01:08] compliance and that improve the security
[00:01:10] of your systems. So very relevant to
[00:01:12] today's question. So do check out their
[00:01:15] links in the description and thank you
[00:01:17] to Octopus for their ongoing support of
[00:01:20] our work on the modern software
[00:01:21] engineering channel.
[00:01:22] I I've got to say I want to jump
[00:01:24] straight in here. I love this topic.
[00:01:25] This is as someone who's been
[00:01:28] particularly consulting and advising as
[00:01:30] well as much as delivering software in
[00:01:33] what we would loosely call an agile way
[00:01:34] for north of two decades. This is one of
[00:01:37] the ones that comes up a lot. I think
[00:01:38] probably in order of frequency of this
[00:01:42] won't work here. It's trunk based
[00:01:44] development, pair programming and
[00:01:46] compliance. Right? They just they seem
[00:01:48] to be the big thing. Right? We can't do
[00:01:50] trunk based development. We have 80 live
[00:01:52] branches. Right?
[00:01:53] >> Yeah. Pair programming won't work
[00:01:55] because it's twice as expensive. Yeah.
[00:01:57] Or I hate working with juniors cuz I'm
[00:02:00] brilliant or something. The compliance
[00:02:02] one is really close to my heart. I've I
[00:02:04] just want to start with two I I've
[00:02:06] worked with a lot of compliance people
[00:02:08] and regulatory people. I just want to
[00:02:09] start I as I tend to Dave with
[00:02:12] definitions. Is mostly when I talk to
[00:02:14] engineering folks about compliance or
[00:02:16] regulatory, they kind of do the sucking
[00:02:17] in through the teeth and the
[00:02:19] you know, adversarial, you know,
[00:02:21] numbshell paths with the clipboards. I
[00:02:23] got talking to some compliance people. I
[00:02:25] I worked with I think it's long enough
[00:02:28] now that I can name names.
[00:02:29] In Erlangen in Germany, working with
[00:02:31] Siemens Healthcare. And Siemens is vast,
[00:02:34] right? It's a huge huge organization.
[00:02:35] Siemens Healthcare, this bit of it, they
[00:02:37] do MRI scanners, CT scanners. So the
[00:02:39] control systems for like proper safety
[00:02:41] critical systems. And they invited me in
[00:02:45] because they wanted to adopt they
[00:02:47] wouldn't have called it that because it
[00:02:48] wasn't called this yet, but continuous
[00:02:50] delivery for MRI and CT systems, which
[00:02:53] many folks would say was impossible. So
[00:02:55] I went in there and went through what I
[00:02:58] now call my path of greatest resistance.
[00:02:59] It's like it's a technique I use. Where
[00:03:01] you go in and Dave invites me in. Dave's
[00:03:03] head of engineering. He says we want to
[00:03:05] do this thing. And I propose stuff like,
[00:03:07] you know, continuous delivery. And Dave
[00:03:09] says, "This is great. I love this except
[00:03:11] so-and-so won't let us." Like so-and-so
[00:03:13] is like the release manager. Let's go
[00:03:14] meet the release manager. Go and meet
[00:03:16] the release manager. The release manager
[00:03:17] is fine. Loves the idea, but so-and-so
[00:03:20] won't let us. Right, well who won't let
[00:03:22] us? So you you basically you navigate
[00:03:23] the organization through the people that
[00:03:25] are going to say no. And at Siemens
[00:03:27] Healthcare, the ultimate person who was
[00:03:29] going to say no was Dr. Vera. And Dr.
[00:03:31] Vera was head of regulatory for, you
[00:03:33] know, these safety critical systems. And
[00:03:36] I get an audience with Dr. Vera and I go
[00:03:38] into her office. She's a very serious,
[00:03:40] austere-looking woman
[00:03:42] who it turns out has a brilliant sense
[00:03:43] of humor, but I didn't know this at the
[00:03:45] time. And and she and I said, "So now so
[00:03:47] what what what do you do?" She said,
[00:03:49] "I'm I'm head of regulatory." And I
[00:03:51] said, "So what does that mean?" She
[00:03:52] goes, "My job is to make sure that
[00:03:54] nobody dies."
[00:03:56] >> [laughter]
[00:03:57] >> That's someone with a mission, right?
[00:04:00] It's not, you know, we have to adhere to
[00:04:01] these regulations, blah blah. My job is
[00:04:04] to make sure nobody dies.
[00:04:05] So, that was, I don't know, 20 years
[00:04:08] ago, 15 years ago.
[00:04:09] Roll it on a few years. I'm in a yet
[00:04:12] another large investment bank, and they
[00:04:15] are looking to basically get better at
[00:04:17] compliance, or what is the thing that we
[00:04:19] now call continuous compliance, as a nod
[00:04:21] to continuous delivery. So, the the idea
[00:04:23] was, can we make a lot of the compliance
[00:04:26] stuff that is always, you know,
[00:04:27] backloaded and heavy process at the end,
[00:04:30] can we kind of make some of that go
[00:04:32] away, or make some of that lighter? And
[00:04:34] we set up a workshop. It was like a two
[00:04:36] full days of workshop with all the
[00:04:38] senior compliance folks and all the
[00:04:39] senior engineering folks in a room. We
[00:04:41] started the two days by printing out all
[00:04:44] the regulations, right? It turns out
[00:04:46] there's not that many when you just go
[00:04:47] and get at the bullet level. And we
[00:04:49] stuck all the pieces of paper up on on
[00:04:50] this big wall, and the first morning, we
[00:04:53] said, "Right, okay, everyone, we want
[00:04:55] everyone to read all of these bullets,
[00:04:57] right? And if there's anything on there
[00:04:58] that you think is stupid, just say so,
[00:05:00] and we'll get rid of it." And they went,
[00:05:01] "Okay." And meanwhile, you know, the the
[00:05:03] head of compliance person introduces
[00:05:05] himself. We say, "So, you know, tell us
[00:05:06] about compliance. What's it for?" And he
[00:05:09] said, and again, Dave, you've probably
[00:05:11] said these same words, he said, "We have
[00:05:14] compliance so it's safe to be a bank."
[00:05:16] Mhm. Right? If I know that it's safe to
[00:05:18] be a bank, you can go as fast as you
[00:05:20] like.
[00:05:21] Yeah. [laughter] Like, really? And then
[00:05:23] where it went from there is like, well,
[00:05:25] okay, so how come there's so much like
[00:05:26] paperwork? How come there's so much And
[00:05:28] they said, you know, we know we could
[00:05:30] automate a lot of this, but we we don't
[00:05:31] have any engineers, right? We're
[00:05:32] compliance. And the engineers are, we've
[00:05:34] got engineers. Yeah.
[00:05:36] >> [laughter]
[00:05:36] >> So, they So, we went back to this wall
[00:05:37] that had all the stuff on it, and it
[00:05:39] turned out out of all the things It was
[00:05:41] things like, you should write code
[00:05:42] because you have a requirement, right?
[00:05:44] [laughter]
[00:05:45] You should know why you're writing the
[00:05:46] code. The The requirement should have an
[00:05:48] owner. It came from somewhere. Right?
[00:05:50] You should know when you're done. Like
[00:05:52] none of this is rocket science. And
[00:05:53] everyone's going actually, yeah, that's
[00:05:55] pretty sensible. So so you know, the the
[00:05:57] compliance piece was like, is it safe to
[00:05:59] be a bank? Is Is Is anyone going to die?
[00:06:02] Right? And I think those are reasonable
[00:06:04] reasonable requests to make. I've often
[00:06:07] had the same kind of conversation. So so
[00:06:09] I've I've done a lot of work in in
[00:06:11] regulated industries in including
[00:06:14] interestingly enough at Siemens
[00:06:15] Healthcare several times, but other
[00:06:17] health care providers, too. And as you
[00:06:21] say, there's there's this great tension
[00:06:23] very often between software development
[00:06:26] groups and compliance because they seem
[00:06:28] adversarial from the outside very often.
[00:06:31] But actually, it is exactly that. If you
[00:06:34] stop and think what compliance is for,
[00:06:36] we're trying to produce software that
[00:06:38] could do great damage. You know, in
[00:06:40] these safety-critical systems, they
[00:06:42] could kill people. It could lose
[00:06:44] billions of pounds worth of other
[00:06:46] people's assets or whatever it is. You
[00:06:48] know, that's why they're regulated. It's
[00:06:50] to stop us doing dangerous stupid
[00:06:53] things. And that seems reasonable.
[00:06:55] Usually, it seems to me that compliance
[00:06:57] is focused on two two groups of things.
[00:07:01] One is, let's adopt some behaviors
[00:07:05] to avoid the things that we know are
[00:07:07] stupid. So we know it's stupid to just
[00:07:09] wander in and be randomly building stuff
[00:07:12] without an idea of what it is that we
[00:07:14] want we want to achieve and those sorts
[00:07:17] of things and you know, let's organize
[00:07:19] in ways that will on the whole give us
[00:07:21] the best chance of doing sensible
[00:07:23] things. So that's one set of things that
[00:07:25] I think that compliance is often useful
[00:07:27] for putting in some of those guardrails
[00:07:29] in place. And the other thing is when
[00:07:33] something goes wrong cuz things will go
[00:07:35] wrong,
[00:07:36] how will we be able to recognize that
[00:07:38] something went wrong? And how will we be
[00:07:40] able to stop that same kind of thing
[00:07:42] going wrong again in future. And that's
[00:07:45] about what audit is for and traceability
[00:07:47] and those sorts of aspects of of
[00:07:49] compliance are really about. It's to
[00:07:51] give us that insight. And all of those
[00:07:54] things seem to me very strongly aligned
[00:07:57] with what I would think of as good
[00:07:59] software engineering. It's It's It's
[00:08:01] what doing a good job looks like. We
[00:08:04] want all of those things. So So that the
[00:08:06] trick is to how do we do that without
[00:08:09] heavy weight bureaucracy and paperwork.
[00:08:12] And as you've already alluded, that's
[00:08:14] largely about automating these things
[00:08:16] and you can
[00:08:18] So So at Siemens and in other places, we
[00:08:21] did some of that stuff. We did the
[00:08:22] continuous compliance thing. And I am
[00:08:26] now now so convinced that not only is
[00:08:28] the answer to the original question, is
[00:08:30] it possible, I would actually go
[00:08:32] further. I would say I don't believe
[00:08:34] that you can actually be regulatory
[00:08:35] compliant properly in the absence of
[00:08:38] continuous delivery because I don't
[00:08:39] think you can collect enough data and
[00:08:41] enforce the rules strongly enough to be
[00:08:43] able to be compliant strictly. I've
[00:08:46] never seen an organization that was as
[00:08:48] compliant as a continuous delivery
[00:08:50] organization in my career.
[00:08:52] >> Yeah, I think that's a fair fair
[00:08:53] observation. Um it's worth teasing
[00:08:55] apart, I think, the With any regulation,
[00:08:58] you have like the motivation. So
[00:09:00] Sarbanes-Oxley, we don't want one rogue
[00:09:02] person being able to put code into
[00:09:04] production, right? Seems like a
[00:09:05] reasonable thing to do. So they have the
[00:09:07] two pairs of eyes rules and things like
[00:09:09] that. Or method, you know, you you need
[00:09:11] to know who's Which is your money and
[00:09:13] which is someone else's money and so
[00:09:14] you're only trading your money. All
[00:09:16] those kind of things. The motivation
[00:09:17] generally is is something bad happened
[00:09:20] and we don't want the bad thing to
[00:09:21] happen again. Then the regulation is
[00:09:24] some As you say, some guardrail, some
[00:09:26] constraint. But then you have the
[00:09:27] implementation of that regulation and
[00:09:30] that, I think, is where we get into the
[00:09:31] adversarial stuff and the process
[00:09:34] theater and the the theater. The classic
[00:09:36] example to me is and pointed this out to
[00:09:38] me, it's like one of these hiding in
[00:09:39] plain sight things, right? But so, very
[00:09:42] often, the implementation of
[00:09:44] Sarbanes-Oxley, for folks who aren't in
[00:09:46] finance, was in the wake of the 2007
[00:09:50] crash, was to say, basically, we can't
[00:09:54] any software, any software change in a
[00:09:56] banking system, someone else has to look
[00:09:58] at it. Yeah. Dave can't go and just do
[00:10:01] stuff. Daniel has to at least, you know,
[00:10:02] get some pair of eyes on it. And they
[00:10:04] called it the two pairs of eyes
[00:10:05] principle. Now, what that generally
[00:10:07] transpired to was that a dev person
[00:10:09] would write the code, and an ops person
[00:10:11] would then release the code. So, that
[00:10:12] they had the release button. At which
[00:10:14] point, it all becomes a bit theater,
[00:10:17] because the ops person is has a binary,
[00:10:21] so unless the ops person can decompile
[00:10:24] and understand bytecode,
[00:10:27] or or a C, you know, a C++ whatever
[00:10:29] compiled binary, an elf executable, then
[00:10:32] they they have zero oversight and zero,
[00:10:35] you know, insight into what just
[00:10:36] happened there. By far the best way of
[00:10:38] doing two pairs of eyes is two pairs of
[00:10:39] eyes, is pairing. And then the
[00:10:42] the the second by a long way is code
[00:10:44] reviews, which we've discussed before.
[00:10:46] But the idea that that that that that
[00:10:49] the generally accepted way of doing X is
[00:10:52] to do X badly, because everyone else is.
[00:10:54] Yes. And and then we end up with with
[00:10:56] the the particularly the document
[00:10:58] theater. You know, we have to have this
[00:10:59] document. And for me, one of the
[00:11:01] earliest places, and I have a feeling,
[00:11:03] Dave, we might have been on the same
[00:11:04] project. Certainly it was around the
[00:11:06] same time, where we had There was a
[00:11:08] release document. The release document
[00:11:09] was a Word doc. And part of the release
[00:11:12] process was that the Word doc had to
[00:11:14] have Yeah, you had to have the Word doc
[00:11:15] up to date, and it was like, changes
[00:11:17] since the last release, and the big
[00:11:18] template.
[00:11:19] >> Mhm. And someone observed that a Word
[00:11:22] document is a zip file containing XML
[00:11:24] files.
[00:11:24] >> Yeah. And we went, okay, well, we can
[00:11:26] explode that. We can template up the
[00:11:28] bits that matter. And And we would
[00:11:30] generate And then if if people put
[00:11:32] whenever they did a get commit if people
[00:11:34] put the issue number the Jira ticket
[00:11:36] whatever as part of the the commit and
[00:11:39] if we use words like close fixes you
[00:11:41] know the kind of things that GitHub will
[00:11:42] recognize then we could do a round trip
[00:11:44] thing where I could go into a Jira I
[00:11:46] could look at all tickets all work items
[00:11:49] that are closed since the last release
[00:11:51] right pull out all the and I can
[00:11:52] basically generate you your release
[00:11:54] stock and so what we'd do is we'd have
[00:11:55] the release stock was a build artifact.
[00:11:57] >> Yes. So every viable build part of the
[00:12:00] things that came out with you know the
[00:12:02] jar files or whatever was the word doc
[00:12:04] that said this is everything that's in
[00:12:05] this release. Yeah and it can be and it
[00:12:07] can be much more detailed it I mean And
[00:12:09] it was exactly as you say David it was
[00:12:11] it was more likely to be current because
[00:12:13] of continuous delivery than anyone
[00:12:15] trying to keep it up to date. And if
[00:12:16] your deployment pipeline is the one
[00:12:18] route to production it can be completely
[00:12:20] authoritative about that if you link
[00:12:22] your
[00:12:23] pipeline information systems with your
[00:12:27] development management systems like Jira
[00:12:29] or whatever then you can track whose
[00:12:31] idea it was who came up with the idea
[00:12:33] who worked on it all of the commits that
[00:12:35] added up to this change what the feature
[00:12:38] was that you were working on all of
[00:12:39] those things you can kind of glue all of
[00:12:41] those things together and you can build
[00:12:43] a complete auditable picture. Well and
[00:12:45] from the commits you can say this is the
[00:12:47] test code for this feature this is the
[00:12:48] production code for this feature. These
[00:12:50] were all the tests that ran and passed.
[00:12:52] >> Yeah. And so on and these are the
[00:12:54] performance scores and whatever else
[00:12:56] yeah. So so so roll this forward and it
[00:12:58] turns into at one large German bank we
[00:13:01] built a platform where the guy who led
[00:13:03] this I won't name him because I don't
[00:13:05] want to embarrass him he's he's
[00:13:06] brilliant but he's very shy and very
[00:13:08] modest and he his mantra was idea to
[00:13:12] production safely in a day. Yes. Right
[00:13:15] so I want to take a thing I want it to
[00:13:16] be live and safely was the key it was
[00:13:19] all of the all of the regulatory bits
[00:13:20] and so we built this platform and he
[00:13:23] ended up exceeding his goal you could
[00:13:25] now go from idea to production safely in
[00:13:28] half a day. Put it in the morning, it'll
[00:13:29] be live by lunchtime. Yeah. As part of
[00:13:31] that was nothing to do with the
[00:13:32] platform. Part of that was lots and lots
[00:13:34] and lots of conversations at higher and
[00:13:36] higher levels. Yeah. Where they agreed a
[00:13:39] lightweight path to live Yeah. for code
[00:13:42] that had certain characteristics. Small
[00:13:44] changes, good test coverage, clear
[00:13:47] definition, da da da da. Basically this
[00:13:48] criteria. And if you had this criteria,
[00:13:50] you were allowed to use the continuous
[00:13:52] compliance platform. And the rule was no
[00:13:54] one has to use it. Yeah. Right? If you
[00:13:57] do use it, basically all of your
[00:13:58] homework is done. If you don't, that's
[00:14:00] fine, but you've got to do all the
[00:14:01] admin. And suddenly now, he was managing
[00:14:04] a huge queue of people that were
[00:14:06] clamoring to get onto this platform.
[00:14:08] >> Yeah. Yeah. And there was one brilliant
[00:14:10] exchange that that I was there for that
[00:14:11] just made me chuckle. This very senior
[00:14:14] uh serious senior German engineer who
[00:14:16] was running this huge program, he said,
[00:14:17] "I'm running this large program of work
[00:14:19] and I can't use your platform." He said,
[00:14:21] "That's right, yeah." He said, "But I I
[00:14:23] can game this." He says, "Well, how are
[00:14:24] you going to game me?" He goes, "I can
[00:14:26] slice my project into lots of small
[00:14:27] projects and each of those can use your
[00:14:29] platform." Yeah. And he's like, "You got
[00:14:31] me."
[00:14:32] >> [laughter]
[00:14:34] >> Yeah. It was gorgeous. As long as you
[00:14:35] can deploy them independently. So,
[00:14:37] driving exactly the behaviors that you
[00:14:39] wanted. Yeah. So, we did at LMAX, we did
[00:14:42] pretty much all of the same things. So,
[00:14:44] we would generate we our deployment
[00:14:47] pipeline, if you measured everything,
[00:14:48] took just under an hour to do everything
[00:14:51] in performance testing, scalability
[00:14:54] testing, the the lot uh everything. And
[00:14:56] that include regulatory compliance. So,
[00:14:59] we could generate
[00:15:01] a a release note and all of the
[00:15:02] documentation that was required. But
[00:15:04] you're an exchange, right? You're a
[00:15:05] You're a very regulated product. Yeah,
[00:15:07] we were a heavily regulated financial
[00:15:09] exchange. So, we could do all of that in
[00:15:11] an hour. So, theoretically, depending on
[00:15:13] the you know, the nature of the change,
[00:15:15] we could do from idea to production in
[00:15:18] probably a couple of hours, you know, if
[00:15:19] it took you an hour to do the to think
[00:15:21] about the problem and to solve it. But,
[00:15:24] all of the all of the compliance stuff
[00:15:26] was wholly automated and it was more
[00:15:29] difficult to for us to release something
[00:15:31] that wasn't regulatory compliant than
[00:15:34] for us to release something that was
[00:15:36] because all of the compliance was
[00:15:37] enforced by our pipeline and our our
[00:15:40] systems. It It That's just how we worked
[00:15:42] all of the time. I'm going to make an
[00:15:44] observation. We've been exclusively
[00:15:46] talking about regulatory and compliance.
[00:15:47] We haven't touched on security. I'm
[00:15:49] going to We're we're nearly 2 minutes
[00:15:51] over time. Yes, I'm going to suggest
[00:15:53] that I think it's significantly enough a
[00:15:54] topic to be a separate one big question.
[00:15:57] I think it is, but we should probably
[00:15:58] give a very fast answer to So, so can we
[00:16:01] build security into our deployment
[00:16:04] pipelines? And the answer I would say
[00:16:06] the answer once again is yes. So, I
[00:16:08] Yeah, I I I I look at it slightly
[00:16:09] differently. I I don't I don't talk
[00:16:11] about security. Security is the
[00:16:13] consequence. I talk about securability.
[00:16:16] So, if you can build a securable system,
[00:16:19] a system of of that which you can reason
[00:16:21] about its security, the rest of it is
[00:16:23] gravy, right? So, you know, small
[00:16:25] components, uh small attack surface
[00:16:28] areas, high-definition, clear clear
[00:16:30] APIs, small you know, high power to
[00:16:32] weight. There's a wonderful book that I
[00:16:34] that I had the privilege of writing the
[00:16:36] forward for called Secure by Design by
[00:16:38] three three Dans.
[00:16:40] >> [laughter]
[00:16:40] >> Dan Dan Berg Johnson um and two other
[00:16:43] Dans. And I wrote the forward on the on
[00:16:44] the on the basis there weren't nearly
[00:16:46] enough Dans involved yet. Yeah. And it's
[00:16:48] gorgeous. It's It takes It takes um
[00:16:50] domain-driven design and it says, "How
[00:16:52] can you use domain-driven design to
[00:16:53] build systems that are inherently
[00:16:55] secure?" And when you start looking at
[00:16:57] your
[00:16:57] >> [clears throat]
[00:16:57] >> your architecture as a securable thing,
[00:17:00] your domain model as a securable thing,
[00:17:02] and then you look at uh your supply
[00:17:04] chain of dependencies as being a
[00:17:06] securable thing. So, you got you know,
[00:17:07] your chain guards and there are other
[00:17:09] folks out there doing this, but Chain
[00:17:11] Guard do it brilliantly, where and then
[00:17:13] you have something like Octopus where
[00:17:14] you've got your you know, you you've got
[00:17:16] your nice build technology, if you like
[00:17:18] that I once it goes in there, I know
[00:17:21] exactly what's going to happen. I know
[00:17:23] exactly how the sausage gets made.
[00:17:25] >> Yeah. Then you can have much more
[00:17:28] confident discussions about the security
[00:17:30] of that kind of system. Yes, yeah,
[00:17:32] absolutely. And the one thing that you
[00:17:35] didn't mention that I would also mention
[00:17:37] is testing for all of those things.
[00:17:39] Absolutely. Yeah. So multi-layered
[00:17:42] stacked testing as part of evaluating
[00:17:46] your you know, the risk the security
[00:17:48] behaviors that you are building into
[00:17:50] your system, evaluating the threat
[00:17:52] surface area and all of those kinds of
[00:17:54] things as well. So absolutely you can do
[00:17:57] that. I would say yes and Yes. I would
[00:17:59] say yes and human beings. I was at a I
[00:18:01] was working at one trading firm and they
[00:18:04] you know, very very deliberately they
[00:18:05] they invited some some white hat folks
[00:18:07] in to to basically try and punch into
[00:18:09] their systems because they wanted
[00:18:10] someone to punch into their systems. And
[00:18:12] they had a large very well-known
[00:18:15] consulting firm in and And And literally
[00:18:17] with a clipboard and did a review and a
[00:18:19] report and they said everything looked
[00:18:21] okay and and tickety-boo and stuff. And
[00:18:23] then um the the following day a guy came
[00:18:26] in he was kind of sitting in reception
[00:18:28] and had a baseball cap on I remember I
[00:18:29] was there this day in the office. He's
[00:18:31] sitting with a baseball cap on and he's
[00:18:33] you know, he's just tapping on a laptop
[00:18:34] or something and the receptionist is
[00:18:35] like who are you here to see? He goes oh
[00:18:37] you know, I'm here to see so-and-so like
[00:18:39] the CIO. Oh, I'm really sorry we cuz
[00:18:41] we're having the lift service we thought
[00:18:42] you were the lift guy. Yeah. And he goes
[00:18:44] no no he goes I get that a lot don't
[00:18:46] worry. And then anyway so then by the
[00:18:48] time the CIO comes out he goes I have to
[00:18:50] show you just show you something. And
[00:18:51] while he's been sitting in reception
[00:18:53] he's on the Wi-Fi he's got through the
[00:18:55] firewall he's got through the DMZ he's
[00:18:57] on to production servers.
[00:18:58] >> [laughter]
[00:19:00] >> And he's done this in the 15 minutes
[00:19:01] he's been sitting in reception. Yeah.
[00:19:03] He's like we need to talk about your
[00:19:04] hard shell not being that hard. And you
[00:19:06] know, you do you absolutely need human
[00:19:08] beings. Yeah. In in this in the security
[00:19:11] story as well. Absolutely, absolutely,
[00:19:13] yeah. The the other the other thing that
[00:19:14] we used to do was So So as an exchange,
[00:19:18] a regulated exchange, one of our
[00:19:21] regulatory requirements was that we had
[00:19:23] to do a penetration test every 6 months.
[00:19:25] So So we we had an external third party
[00:19:28] that would come in and do
[00:19:30] attempt penetration tests on our on on
[00:19:33] our system. And we'd we we'd allocate a
[00:19:37] pair of developers to work with them and
[00:19:39] support them and give them anything that
[00:19:41] we need. But also, part of what they
[00:19:43] were doing was looking at what they were
[00:19:45] doing so they could learn what they were
[00:19:47] doing. And then we'd automate the we'd
[00:19:49] write tests to do what they'd been
[00:19:51] doing, and we'd run those as part of our
[00:19:53] deployment pipeline. They'd never find
[00:19:55] the sa- same mistake twice. But but this
[00:19:58] again goes absolutely back to the what
[00:20:00] what the regulation says and how you
[00:20:01] implement it. Yes.
[00:20:03] Yeah yes, you have to have pen testing
[00:20:05] done. And if you get, you know, Jay
[00:20:07] friendly pen tester who just gives you
[00:20:08] the clean sheet, that's brilliant. Box
[00:20:10] checked. No, you're Dave Farley. So
[00:20:12] you're going to say, "Right, I want to
[00:20:13] find the meanest, nastiest person I can,
[00:20:16] and I want to let them go nuts on my
[00:20:17] network cuz I want to learn. Yes. I want
[00:20:19] to learn what's weak here because I want
[00:20:20] to run a good ship." Yeah, I want to
[00:20:22] stop people being hurt by losing their
[00:20:24] all their money. Yeah. Uh we we have now
[00:20:27] overrun by 6 minutes and 46 seconds. So
[00:20:31] now's probably time to stop. Thanks
[00:20:33] everybody to uh watching. Thanks to our
[00:20:35] patrons for supporting us. And thanks
[00:20:38] for Octopus once again for sponsoring
[00:20:39] this episode. Thank you. Wonderful.
[00:20:41] Thanks, Dave.
