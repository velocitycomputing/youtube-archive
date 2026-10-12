---
record_id: "youtube:wRY9XCrT0eg"
video_id: wRY9XCrT0eg
title: "Palmer Luckey: Autonomous Weapons Are Ancient and Why Anduril Won't Build Humanoids | EP #295"
channel: Peter H. Diamandis
url: "https://www.youtube.com/watch?v=wRY9XCrT0eg"
watched_date: "2026-09-29"
watched_at: "2026-09-29T23:57:15Z"
watch_count: 1
duration_seconds: 2188
source: youtube-history-browser
added_date: ""
history_label: Sep 29
history_order: 165
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 2188
transcript_status: fetched
transcript_content_hash: 5a7be072830c431c42f6f2c859dc1cbfacdde191e1bb024d28df42da00e25100
analysis_mode: health
summary_source: local
model_source: local
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: Qwen3.8-Flash-Next-UD-Q4_K_XL
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
topic_domain: politics
status: new
routed_to: null
---

## Summary

Palmer Luckey accepted the X Prize for autonomous wildfire response, winning $2.2 million for Anduril, including $1 million from Lockheed, and described Anduril’s autonomous firefighting tank started in 2017 and finished in 2019; the system’s core problem is not just detecting fire but classifying it, rejecting false positives such as cigarettes, campfires, and road flares, then matching the fire type and growth rate to the most cost-effective response asset, because a 10-minute versus 1-hour response changes the required tools. Luckey announced a new $10 million X Prize focused on understanding animal intelligence and enabling communication with wild animals at least 10 times better than current state of the art, arguing biological intelligence may teach AI systems to be more efficient. He said he is less worried about AI itself “dooming” humanity than about evil people using moderately competent AI, and argued autonomous weapons are not new: Aegis, SeaRAM, mines, torpedoes, traps, and even mythological golems fit broad definitions of autonomy. He emphasized that centralized command and control is vulnerable to jamming, interception, hacking, or strike, so forward autonomy is necessary, while also saying foundation models are poorly suited for weapons because they are non-deterministic and non-auditable, whereas defense systems need specialized models for radar, sonar, and sensor data. He rejected building humanoid robots for defense because combat favors extreme specialization, but said humanoids could automate legacy military platforms designed for humans, and discussed Pentagon acquisition centralization, noting historically about 80% of major defense acquisition programs went to five companies, while Anduril positions itself as a product company rather than a traditional contractor; he also referenced John Carmack, Armadillo Aerospace, Oculus, Meta’s new VR glasses, and the “B boys” billionaire group.

Actionable takeaways: if evaluating autonomous systems, focus on the full pipeline—detection, classification, false-positive rejection, asset matching, latency, and response effectiveness—rather than raw AI capability; for defense or robotics work, treat communication vulnerability, jamming resistance, auditability, deterministic safety behavior, and human control over intent as primary design constraints. Research leads include autonomous firefighting, biological intelligence, animal communication, low-power AI inspired by non-human cognition, edge autonomy under denied communications, and Pentagon acquisition reform. Decisions to consider: whether to track Anduril’s products and X Prize announcements, whether to prioritize specialized robots over general-purpose humanoids for a given mission, and whether to invest in or study systems that retrofit legacy platforms with humanoid interfaces instead of replacing them. Follow-up questions should ask: what are the measured false-positive and false-negative rates in wildfire detection? How are kill decisions constrained legally and technically? Can autonomous systems remain safe when communications are jammed? What benchmarks would prove “10x better” animal communication? And which defense problems are better solved by specialized machines than by generalist robots? Health implications are indirect but real: faster autonomous fire response could reduce smoke exposure, evacuation trauma, and fire-related casualties, while animal-intelligence research may eventually inform more efficient AI systems rather than direct medical applications.

## Transcript

[00:00:05] Wow, it's so much brighter out here.
[00:00:07] >> It is. It's, you know, the future is
[00:00:09] bright.
[00:00:10] >> There's lens flare in the future.
[00:00:12] >> Yeah.
[00:00:13] So, welcome everybody to the Oscars of
[00:00:15] optimism. That, of course, we're opening
[00:00:18] up the summit with the king of
[00:00:20] AUTONOMOUS WEAPON SYSTEMS.
[00:00:22] >> [laughter]
[00:00:26] >> ALL RIGHT. SO,
[00:00:29] I'M GOING TO start with the fact that
[00:00:31] we're awarding three X prizes this week.
[00:00:34] Palmer, congratulations for winning our
[00:00:37] wildfire X prize.
[00:00:39] >> Thank you so much.
[00:00:41] >> [applause]
[00:00:42] >> This one's been a long time in in the
[00:00:44] works.
[00:00:45] >> Let's get Let's get the the the slide up
[00:00:47] here. So, Palmer won $2.2 million for
[00:00:50] Anduril.
[00:00:51] >> As if you needed it.
[00:00:52] >> Um a million of
[00:00:54] a million of that from Lockheed,
[00:00:57] which was kind of interesting.
[00:01:00] >> We do a lot of work with Lockheed. We
[00:01:01] also compete with them, but we
[00:01:04] in the in the defense space, it's you
[00:01:06] know, we we we compete with their
[00:01:07] fighter jet division and we partner with
[00:01:09] them on some of their payloads. And so,
[00:01:11] we do a lot of stuff together. But, you
[00:01:12] me and you have both been trying to get
[00:01:13] this autonomous firefighting stuff going
[00:01:15] for a long time.
[00:01:16] >> mean, you got this prize announced back
[00:01:18] in 2019. It's been a long time.
[00:01:20] Anduril's one of our first two products
[00:01:22] was an autonomous firefighting tank that
[00:01:25] we started building in 2017, finished in
[00:01:27] 2019.
[00:01:28] >> It's insane that we let fires become
[00:01:30] conflagrations before we put them out.
[00:01:32] >> And it well, and it's and it's kind of
[00:01:33] insane that people are saying, "Oh, the
[00:01:36] you know, the technology's finally made
[00:01:37] it possible." And I don't know, I'm not
[00:01:39] going to correct them too often in
[00:01:41] public, but it's I mean, this has been
[00:01:42] possible for over a decade. It's
[00:01:44] >> Yeah. All right.
[00:01:44] >> It's just that
[00:01:45] it's become politically politically
[00:01:47] impossible to ignore the problem now.
[00:01:49] >> We'll watch a 1-minute video clip of
[00:01:51] what your team achieved. And if you walk
[00:01:53] us through it here.
[00:01:56] >> Sure. So, you
[00:01:57] this was
[00:01:59] an example of what we were doing at the
[00:02:00] test site where we were
[00:02:02] detecting fires, classifying fires. What
[00:02:05] you don't really see in here is that you
[00:02:06] also need [music] to reject false fires.
[00:02:08] That was part of the test as well. So,
[00:02:10] you have to know, you know, who's the
[00:02:11] guy smoking a cigarette? Who's the guy
[00:02:13] What's What's What's a campfire? What's
[00:02:14] a road flare? And then what's something
[00:02:16] that shows the characteristics of real
[00:02:17] fire? That's what you need to flag to
[00:02:20] people. That's what you need to flag to
[00:02:22] emergency services. Uh and then you need
[00:02:24] to match make the type of fire to the
[00:02:27] right asset that's in the area. And so,
[00:02:29] you want to basically use the most
[00:02:31] cost-effective thing that can respond
[00:02:34] and get there in time. And if
[00:02:36] something's growing faster, you might
[00:02:37] need something different. If it's in
[00:02:39] woods versus on a brush hill, you might
[00:02:41] need something different. And so, you
[00:02:42] know, it's it's about detection,
[00:02:44] classification, rejection, matchmaking,
[00:02:47] and then going and and hitting the
[00:02:48] target. And the last thing I'll say is
[00:02:49] that with most of what we do,
[00:02:52] uh our work with the military,
[00:02:55] you'd go through many of these same
[00:02:56] steps,
[00:02:57] but if you find a target, let's say it
[00:03:00] takes you, you know, an hour to an hour
[00:03:03] to to get to somebody versus 10 minutes,
[00:03:05] it usually doesn't make as much of a
[00:03:08] difference. When you're talking about
[00:03:10] fire, though, the difference between 10
[00:03:12] minutes and an hour response, totally
[00:03:15] different tools you're going to need to
[00:03:16] respond with. You know,
[00:03:18] a bomb is is is a is a bomb whether or
[00:03:20] not it takes a day or an hour or a
[00:03:22] minute to get there. Uh but when you
[00:03:24] when when a fire is is is is
[00:03:25] metastasizing, you need to pick the
[00:03:27] right thing that can put it out before
[00:03:29] it gets too large.
[00:03:30] >> Amazing.
[00:03:31] >> You know, uh
[00:03:32] we're going to be announcing something
[00:03:33] in a month's time
[00:03:35] uh that you're funding a new X Prize,
[00:03:39] and uh it's going to be secret until
[00:03:41] then, but we're going to tease it now.
[00:03:44] Uh
[00:03:45] another $10 million prize. Would you
[00:03:47] share share with us what we're going to
[00:03:49] do?
[00:03:50] >> Sure, you know, uh
[00:03:52] the
[00:03:53] you know, we we should we should keep
[00:03:54] the details secret cuz there's there's
[00:03:56] some there's some good twists, but
[00:03:58] suffice to say that I'm not I'm not
[00:04:01] interested in joining the race to push
[00:04:04] AI forward with my money. I think that
[00:04:07] the
[00:04:08] the artificial intelligence side of
[00:04:10] models is is is pretty well covered by
[00:04:12] plenty of people. I think we've not been
[00:04:14] doing enough understanding biological
[00:04:16] intelligence particularly beyond people
[00:04:18] and so this is going to be a prize
[00:04:20] around understanding how animals think
[00:04:23] and making so that we can communicate
[00:04:25] with them 10 times better than the
[00:04:27] current state of the art for the current
[00:04:29] smartest species and not just trained
[00:04:30] animals, but wild animals in their own
[00:04:33] in their own language.
[00:04:34] >> Amazing. [applause and cheering]
[00:04:36] >> And I think that there's actually a lot
[00:04:37] that we're going to be able to learn. I
[00:04:38] mean, if you look at large language
[00:04:40] models, they're kind of this, you know,
[00:04:42] they're they're they're based on
[00:04:44] humanity's way of thinking and
[00:04:46] communicating distilled and I think that
[00:04:48] there's plenty to learn from all of the
[00:04:51] other species that are on this planet
[00:04:53] and I wouldn't be surprised if it has
[00:04:54] applications for AI particularly AI
[00:04:58] where you need to be
[00:04:59] more efficient, you know, more power
[00:05:01] efficient, more time efficient,
[00:05:03] you know,
[00:05:04] a different point of view, two heads are
[00:05:06] better than one, whichever whatever
[00:05:09] metaphor you want to use.
[00:05:10] >> Love it. Love it. All right, I'm going
[00:05:11] to kick off the first official question
[00:05:13] here.
[00:05:14] P-doom, you're in the AI industry, the
[00:05:16] defense industry, what's your P-doom?
[00:05:20] >> I'm just not worried
[00:05:23] about AI dooming
[00:05:25] the I guess I'm not worried about AI
[00:05:28] doing the killing. I'm very very worried
[00:05:30] about evil people
[00:05:31] >> Yes.
[00:05:32] >> using moderately competent AI to do evil
[00:05:35] things.
[00:05:35] >> Exactly.
[00:05:36] >> And I am s-
[00:05:39] kind of frustrated by a lot of people
[00:05:41] who are new to the dooming hobby.
[00:05:45] It's It's It's sort It's sort of like
[00:05:48] how we had to deal with
[00:05:49] the war in Ukraine happens and all of a
[00:05:51] sudden all these people who have had the
[00:05:53] dumbest opinions you've ever heard about
[00:05:55] the military for their whole life
[00:05:58] and people who believed we lived at the
[00:05:59] end of history that we had moved past
[00:06:02] conflict that we lived in a world where
[00:06:04] you could just write a nasty letter in
[00:06:06] the UN forgetting that that only works
[00:06:08] if it's backed up by credible threat of
[00:06:10] violence and then all of a sudden they
[00:06:11] change their minds. You're seeing this
[00:06:12] with AI. People who have not thought
[00:06:15] about this problem for more than
[00:06:17] a couple years or maybe even just a
[00:06:19] couple months
[00:06:21] are saying oh my god this is the biggest
[00:06:23] threat to humanity. These are people who
[00:06:25] have spent almost no time actually
[00:06:27] analyzing what the largest threats to
[00:06:29] humanity are. They haven't spoken to any
[00:06:31] of the experts in this area. They
[00:06:33] certainly weren't buying freeze-dried
[00:06:34] food and building prepper bunkers, you
[00:06:37] know, like like like like me and many of
[00:06:39] my my my buddies who who have who have
[00:06:42] indulged fantasies about what doom could
[00:06:44] look like and also thought realistically
[00:06:46] about it. And so yeah, the AI doom is
[00:06:49] way down the list for me. I'm I'm I'm
[00:06:51] I'm a big optimist. I think it's going
[00:06:52] to massively reduce the cost of resource
[00:06:54] extraction, processing, transformation.
[00:06:57] You're going to see every part of
[00:06:58] society become subject to the same
[00:07:01] economies of scale and efficiency that
[00:07:03] automated industries that automated
[00:07:05] without AI have seen. So think like
[00:07:08] agriculture or or textiles. You can buy
[00:07:12] 2 weeks of calories for less than 1 hour
[00:07:17] of federal minimum wage labor. That's
[00:07:19] crazy.
[00:07:20] >> Let's give it up for
[00:07:21] Palmer here. You're going to see that
[00:07:23] for everything.
[00:07:24] >> David [applause]
[00:07:26] >> So I I got a really
[00:07:27] um
[00:07:28] pressing question on my mind. I'm kind
[00:07:29] of a feeds and feeds and ships and AI
[00:07:31] foundation models guy.
[00:07:33] And so when you're putting systems in
[00:07:35] the field, weapons in the field, uh
[00:07:37] you can you can put the intelligence
[00:07:39] inside it and it this has always been a
[00:07:41] big problem for the Air Force, like if
[00:07:42] we're going to start flying drones
[00:07:43] instead of pilots, who's going to
[00:07:45] unleash the weapons and how's that
[00:07:46] decision going to get made? And the the
[00:07:48] downside of transmitting it back to
[00:07:50] headquarters is you have latency.
[00:07:53] Uh the upside is you have a lot more
[00:07:54] compute. Uh what you can put locally in
[00:07:57] a device, in a robot in the field, in a
[00:07:58] plane is limited, but it's really really
[00:08:01] fast. So what's your philosophy on like,
[00:08:03] you know, I think a lot of people would
[00:08:04] say, well, are we going to have
[00:08:06] self-contained decision-making weapons
[00:08:08] wandering around enemy territories or
[00:08:10] are we going to have like are we going
[00:08:11] to have you know, control at the
[00:08:13] headquarters?
[00:08:13] >> Yeah, more or less. The the real concern
[00:08:15] isn't so much the latency or or the
[00:08:19] speed of computation. The problem is
[00:08:21] that if you rely on
[00:08:24] you know, a central a central location
[00:08:25] to do your compute, you now need to have
[00:08:28] command and control that has a good
[00:08:31] high-bandwidth communication back and
[00:08:33] forth between you and potentially
[00:08:35] thousands or tens of thousands of active
[00:08:37] assets. And if your enemy jams your
[00:08:39] communications or intercepts your
[00:08:41] communications or hacks your
[00:08:42] communications, you're done.
[00:08:44] Uh or worse, they just skip targeting
[00:08:47] all the stuff in the field and they go
[00:08:49] for the place where it's all being
[00:08:51] controlled. You know, we saw we saw this
[00:08:53] I there was a there was a there there
[00:08:55] was there was this documentary that
[00:08:57] George Lucas was working on and and the
[00:08:59] Trade Federation, they had they had
[00:09:01] their central AI command and control
[00:09:03] blown up and that was how the Battle of
[00:09:05] Naboo actually resolved was all all the
[00:09:08] battle droids lost
[00:09:09] >> Oh yeah, they all fell over.
[00:09:10] >> That's right, they all fell over. And so
[00:09:12] I think that that's that that's the
[00:09:13] practical reality that's driving the
[00:09:15] need to have autonomy living not back
[00:09:18] home, but forward. There's other areas
[00:09:20] like you go underwater, you can't talk
[00:09:23] to things. And sometimes you could talk
[00:09:25] to things, but you don't want to. Having
[00:09:27] radio emissions actually exposes you
[00:09:29] necessarily. And so what what you
[00:09:32] for better or for worse, you're going to
[00:09:33] need this. I actually don't think it's
[00:09:34] as much of a shift as people think.
[00:09:37] I there's a lot of people who look at
[00:09:38] this and say, "Oh my god, Pandora's Box
[00:09:40] is being opened. You're going to have
[00:09:41] weapons that are making their own kill
[00:09:43] decisions." And they don't recognize the
[00:09:46] reality, which is that that's been the
[00:09:47] case for decades. You look at the You
[00:09:49] look at the You look at the Aegis system
[00:09:51] on destroyers. It has a fully autonomous
[00:09:53] mode. You can flip a button and it will
[00:09:55] shoot down anything that comes within
[00:09:57] whatever range you programmed it with
[00:10:00] without any human confirmation. You look
[00:10:02] at SeaWiz and SeaRAM for shooting down
[00:10:05] incoming missiles, incoming incoming
[00:10:07] artillery fire, incoming missiles, or
[00:10:10] incoming speedboats.
[00:10:11] Same thing. You can put them in fully
[00:10:13] autonomous modes. And I mean, it Going
[00:10:15] back to into Vietnam, we had missiles
[00:10:17] that you could launch from an aircraft.
[00:10:18] They flew over the horizon, tried to
[00:10:20] identify the right radio emitters that
[00:10:22] they believed corresponded with a
[00:10:24] surface-to-air missile launch site, and
[00:10:26] then struck them without any The person
[00:10:28] had to decide, "I'm going to send it in
[00:10:29] this area. They're going to look for
[00:10:31] this signal, and I know that there's
[00:10:32] this probability they're going to get it
[00:10:34] right." That decision is going to remain
[00:10:36] with people. But, autonomous weapons are
[00:10:39] widely widely There's a whole other talk
[00:10:42] we're not going to have today, but I
[00:10:43] will I I do have a rant about this where
[00:10:46] actually autonomous weapons have existed
[00:10:47] for thousands of years. If you look at
[00:10:50] Defined as kind of weapons that can
[00:10:53] execute the intent of what you
[00:10:55] programmed to do independent from the
[00:10:57] operator to the engineer. You look at,
[00:10:59] for example, pitfall traps that allow
[00:11:01] people to walk over them, but then
[00:11:02] capture the commander on his horse when
[00:11:04] he walks by and it's heavier. You look
[00:11:06] at certain poison traps that would that
[00:11:09] would kill people who had who had
[00:11:12] certain characteristics, not kill people
[00:11:14] who had other characteristics, or not
[00:11:15] kill animals.
[00:11:17] You look
[00:11:18] many types of landmines and sea mines
[00:11:21] and even even torpedoes. And so,
[00:11:23] it depends on on your exact definition.
[00:11:26] But, even going into myth where people
[00:11:27] are creating golems that can you go out
[00:11:29] and fight on their fight on their behalf
[00:11:31] or or defend you defend their city.
[00:11:33] I I guess my argument is we've had
[00:11:35] autonomous weapons for a very very long
[00:11:37] time. It's just a new set of technology
[00:11:40] that's that's making them better.
[00:11:41] >> So, technical question on that. The
[00:11:42] foundation models that go into those
[00:11:44] those remote systems
[00:11:46] >> Or the pit traps.
[00:11:47] >> Yeah, well so that that
[00:11:49] right right now the open source models
[00:11:51] are all Chinese. So, I'm pretty sure
[00:11:53] you're not going to be putting Chinese
[00:11:54] models into remote weapons. Are you
[00:11:56] going to build Anduril foundation models
[00:11:58] or how how are you going to get AI in
[00:12:00] those devices?
[00:12:01] >> I mean, we've been doing it since 2017.
[00:12:03] So, we're way ahead of everybody. We're
[00:12:05] we're a decade beyond that question.
[00:12:08] Um
[00:12:09] I think that we also don't the
[00:12:11] foundation models that people are
[00:12:12] building are not the types of models you
[00:12:14] want to be doing this. They're non that
[00:12:16] they're largely non-deterministic.
[00:12:17] They're non-auditable. It it's it's a
[00:12:19] very different category. The thing that
[00:12:21] we are building, unfortunately, has very
[00:12:23] few consumer applications.
[00:12:25] >> Mhm.
[00:12:25] >> And vice versa.
[00:12:27] Um there of course are LLM use cases for
[00:12:30] defense that make a lot of sense, but
[00:12:31] it's not guiding my missile or or
[00:12:34] classifying radar your radar radar radar
[00:12:36] feeds. I mean, and we we're also we
[00:12:38] can't build models that ingest text and
[00:12:40] then spit out text. I need to process
[00:12:43] raw data radar data feeds. I need to
[00:12:45] process sonar data from passive
[00:12:47] listening stations on submarines. That's
[00:12:49] it's it's pretty highly specialized. And
[00:12:51] I I will take some credit here.
[00:12:53] Uh all these people who are talking
[00:12:55] about how AI is going to change
[00:12:56] everything
[00:12:57] they are mostly uh
[00:12:59] recent converts.
[00:13:01] Anduril Industries, you might notice the
[00:13:03] acronym is AI. Um so, and that that was
[00:13:06] not that was not a mistake.
[00:13:07] >> Okay.
[00:13:08] >> Alex, jump in.
[00:13:09] >> Yeah,
[00:13:10] I think maybe dovetailing on our
[00:13:12] discussion of driving bench, we're now
[00:13:14] in an era when it's possible to take
[00:13:16] frontier models, drop them into a
[00:13:17] robotic embodiment, and get pretty
[00:13:20] stunning results. So, I'd love to ask
[00:13:21] you a question maybe about the scaling
[00:13:23] hypothesis as it applies to autonomous
[00:13:26] weapon systems or autonomous systems in
[00:13:28] general. If you have to extrapolate out,
[00:13:30] is there a Moore's law? Is there an
[00:13:32] experience curve for what as obviously
[00:13:36] the capabilities of underlying frontier
[00:13:37] models, whether they're from Frontier
[00:13:39] Labs proper or from AI,
[00:13:42] as as those progress,
[00:13:44] do we see any equivalent of a Moore's
[00:13:47] law for the autonomous systems
[00:13:49] themselves? And and maybe the the second
[00:13:52] half of the question would be, do you
[00:13:54] think ultimately we achieve some sort of
[00:13:56] convergency? Anduril it makes a variety
[00:13:59] of embodiments in a variety of different
[00:14:01] form factors. Do you see ultimately some
[00:14:04] general purpose category killer robot
[00:14:07] that is equivalently the generalist
[00:14:10] robotic embodiment just like we now have
[00:14:12] generalist models that are capable of
[00:14:14] doing substantially any task?
[00:14:16] >> No, I don't think so on the defense
[00:14:18] side. I think that for manufacturing and
[00:14:21] for hospitality and medicine, you might
[00:14:23] see this because you get economies of
[00:14:25] scale that uh that that that that that
[00:14:27] are really that are really material for
[00:14:29] those types of businesses and you know,
[00:14:30] a humanoid robot may not be the optimal
[00:14:33] form for a burger griller and it may not
[00:14:35] be the optimal form for a firefighter.
[00:14:37] It may not be the optimal form for a for
[00:14:38] a nurse [laughter] or an assembly
[00:14:40] technician.
[00:14:41] >> I see you're smiling.
[00:14:42] >> But even if it's not optimal, the fact
[00:14:45] that it is shared with humanity in its
[00:14:47] form makes it a really really good form
[00:14:50] factor. And now I can make one robot
[00:14:52] that does all of these things and I I
[00:14:54] would probably rather have a let's say
[00:14:56] robot that's 5% slower or or you know,
[00:15:00] less reliable than the optimal burger
[00:15:02] flipping robot if I can share
[00:15:04] commonality with that with that nurse.
[00:15:07] In defense, that's not really the case
[00:15:11] because you are in this constant race to
[00:15:13] not just barely beat your adversary, but
[00:15:15] to massively overpower them. To try and
[00:15:18] make it where you know, the goal is is
[00:15:20] to just barely win a conflict on the
[00:15:22] margins. It is to fight unfair, to have
[00:15:26] overwhelming threat of violence
[00:15:28] underpinning whatever diplomatic
[00:15:30] overtures or negotiations you have. And
[00:15:32] and and everyone was always pushing the
[00:15:34] limits. So, if if if I if I have a jet
[00:15:37] that has a reliable 5% every time edge
[00:15:40] over the enemy, that's worth paying a
[00:15:42] lot of money for, right? Like I I I and
[00:15:45] and I I I think the the
[00:15:48] the loss in performance you would see
[00:15:49] through lack of specialization probably
[00:15:52] makes it non-viable. Like to to to go to
[00:15:54] the to the extreme like a you know, I
[00:15:56] build robot submarines and those have a
[00:15:58] specialized form that needs to dive to
[00:16:00] 6,000 m depth and and sit on the bottom
[00:16:03] of the ocean for months at a time. And
[00:16:05] then I have other stuff that's on the
[00:16:07] surface and and you know, they're
[00:16:09] robotic systems that you know, roll up a
[00:16:10] hill and and they loiter and then I have
[00:16:12] other things that are you know, aerial
[00:16:13] vehicles that are doing very specialized
[00:16:15] tasks and I just can't imagine a
[00:16:16] convergence that would make sense.
[00:16:18] Unless you're telling me that we're
[00:16:19] going to get some cool like like
[00:16:20] humanoids that have like you know,
[00:16:22] on-board fusion reactors and they can
[00:16:24] dive to 6,000 ft depth.
[00:16:26] >> So, Palmer, why aren't why aren't you
[00:16:27] building those? I mean, if anybody, you
[00:16:30] should
[00:16:31] >> [laughter]
[00:16:32] >> Look, you could potentially build such a
[00:16:33] thing, but then very quickly you realize
[00:16:35] that specialization would allow you to
[00:16:37] build something even better. You say,
[00:16:39] "Okay, I've built something that can
[00:16:40] dive to the bottom of the ocean and fly
[00:16:42] to the moon." Man, it could get to the
[00:16:44] moon a lot faster if it didn't have to
[00:16:46] also dive to the bottom of the ocean.
[00:16:47] So, I think I think defense is going to
[00:16:48] be this one where kind of like a
[00:16:51] you know, you you look at for example
[00:16:52] the difference between cars where
[00:16:54] everything has shared platforms within a
[00:16:56] manufacturer you know, manufacturer and
[00:16:58] they also share a lot of the same
[00:17:00] standards
[00:17:01] and the interfaces.
[00:17:03] I think that you compare that with like
[00:17:05] a motorsport where it's all completely
[00:17:07] different and it's continuously pushing
[00:17:09] forward. I I think the defense side is
[00:17:12] probably always going to be this this
[00:17:14] weird branch of exotic highly
[00:17:16] specialized robotic systems.
[00:17:18] >> You know, Palmer, I expected if anybody
[00:17:20] was going to be building humanoid
[00:17:21] robots, it would be you.
[00:17:22] >> No, no, no.
[00:17:22] >> just you you said you said absolutely
[00:17:24] not.
[00:17:24] >> I've I've opted out because um I because
[00:17:27] I believe in them. If I didn't believe
[00:17:29] that humanoid robotics had such a
[00:17:30] powerful future, then I would probably
[00:17:32] build them. But I want Anduril to build
[00:17:34] things that wouldn't exist otherwise.
[00:17:36] That's what I generally want to do.
[00:17:40] Correct. All the other people are
[00:17:41] already doing a great job. Like I I I
[00:17:44] want to use their robots.
[00:17:45] >> And and and do things with them. Like I
[00:17:47] think humanoids are going to be an
[00:17:48] incredible general artificial
[00:17:51] intelligence interface between AI and
[00:17:54] remote systems and a lot of legacy
[00:17:56] platforms that were designed for a
[00:17:57] person to you know pull the lever, push
[00:18:00] the button, read the screen. Like we're
[00:18:02] going to be able to take all those and
[00:18:03] automate them without replacing them
[00:18:05] entirely. So, you have a lot of things
[00:18:07] like
[00:18:08] radar systems that cost millions, tens
[00:18:10] of millions, even hundreds of millions
[00:18:11] of dollars.
[00:18:12] Uh nobody wants to man them during a hot
[00:18:14] conflict cuz they're the first thing
[00:18:16] that's going to go. But if I can put
[00:18:17] humanoid robots in them, I've now been
[00:18:20] able to automate them without that. So,
[00:18:21] yeah, I'm not going to build humanoids.
[00:18:23] Uh this is also why Anduril is not
[00:18:25] building like small quadcopter attack
[00:18:27] drones. Too many other companies doing a
[00:18:28] great job. There's a there's a lot of
[00:18:30] a lot of areas. And and we're not going
[00:18:31] to do space launch. Like we do space
[00:18:33] products. We have a lot we operate a lot
[00:18:35] of our own satellites and a lot of our
[00:18:36] own sensors in space. Uh but I don't
[00:18:38] want to be a launch provider. That's for
[00:18:39] all the other billionaires to
[00:18:41] >> Yeah, yeah, let let them handle that.
[00:18:42] That's fantastic. Salim,
[00:18:44] um you know, when you're operating
[00:18:47] Anduril Industries, you're uh
[00:18:49] decentralizing defense, right? The
[00:18:52] Pentagon and ministries of defense
[00:18:55] globally have been the most centralized
[00:18:57] entity in the history of humanity.
[00:18:59] Uh you're sitting on the edge dealing
[00:19:01] with that. Uh
[00:19:03] you must have a massive immune system
[00:19:05] problem where people inside the entity
[00:19:07] are going, "Nah, we've done that before.
[00:19:09] We can do it better." They either try
[00:19:11] and suck you in or they try and spit you
[00:19:13] out. How are you navigating that
[00:19:15] interface because you're doing it in a
[00:19:16] way that I've never seen anybody succeed
[00:19:19] do it.
[00:19:22] >> I think that this is a problem that's
[00:19:23] very, very hard at the beginning.
[00:19:26] >> Oh, I said the wrong thing.
[00:19:28] >> [laughter]
[00:19:28] >> Wow.
[00:19:29] >> No idea what the
[00:19:30] >> Well, until someone gets on the intercom
[00:19:31] and tells us to
[00:19:33] >> Someone won a million dollars.
[00:19:34] Congratulations.
[00:19:36] >> Um what were we talking about? What what
[00:19:38] what what was it?
[00:19:44] Seriously, I knew the intercom was going
[00:19:46] to come on.
[00:19:47] What were we talking about again?
[00:19:48] >> Centralization of Pentagon versus
[00:19:50] decentralized government.
[00:19:52] >> I'm going to I'm going to keep talking
[00:19:53] till somebody tells me that I can't. Um
[00:19:55] So, we've gotten through this a bit. I
[00:19:57] think early on there was that concern
[00:19:59] that Anduril was not going to be able to
[00:20:01] get through that. Our Our hardest
[00:20:03] problem raising money
[00:20:04] >> Skippy, would you please shut this down?
[00:20:06] >> [laughter]
[00:20:08] >> I've been through enough of these to to
[00:20:09] know how it's going to work.
[00:20:11] >> There we go.
[00:20:11] >> I imagine.
[00:20:12] >> One of our early problems was that our
[00:20:14] investors said, "Palmer, you potential
[00:20:16] investors." They said, "Look, we believe
[00:20:18] that you'll be able to build things that
[00:20:19] work. We believe you'll be able to build
[00:20:21] products that are great, but we don't
[00:20:23] believe the government is capable of
[00:20:25] actually purchasing them at scale." Cuz
[00:20:26] I mean, you talk you talk about
[00:20:27] centralization, you know about the
[00:20:29] issues. For people who don't, uh until
[00:20:32] just a few years ago, you had about 80%
[00:20:35] of MDAPs, major defense acquisition
[00:20:38] programs. So, the basically anything
[00:20:41] that that that matters, uh 80% of MDAPs
[00:20:44] went to five companies, and that's it.
[00:20:48] And I mean, you've seen incredible
[00:20:50] consolidation, centralization. Anduril
[00:20:52] has been successful because we use we're
[00:20:54] we're we're less of a contractor and
[00:20:55] more of a product company. We use our
[00:20:57] own money to build products, then we
[00:20:58] sell them, and we've gotten to the point
[00:21:00] now where people in government have done
[00:21:02] very, very well betting on Anduril, and
[00:21:04] then miraculously we finish on schedule,
[00:21:07] we finish on time, and then the next
[00:21:09] program manager says, "I know how I can
[00:21:11] make my job easy. I just I just give the
[00:21:14] contract to Anduril."
[00:21:15] >> Got it.
[00:21:16] >> So, it it's got to take guts to enter
[00:21:18] the defense industry, right? The most
[00:21:20] incestuous,
[00:21:21] you know, self-licking ice cream cone on
[00:21:23] the planet.
[00:21:24] >> Yeah.
[00:21:25] >> And and and what insanity,
[00:21:28] you know, gave you the balls to do that?
[00:21:31] >> The insanity was the reason that I got
[00:21:33] into it.
[00:21:35] Uh the first page of our pitch deck said
[00:21:37] Anduril will save taxpayers hundreds of
[00:21:39] billions of dollars a year by making
[00:21:42] tens of billions of dollars a year. The
[00:21:43] idea being we're not just making
[00:21:45] products that we're selling, but we are
[00:21:46] displacing the systems that cost
[00:21:49] needlessly 10 times what they should.
[00:21:52] And
[00:21:53] Yeah, thank you.
[00:21:54] >> [applause]
[00:21:56] >> And so, it does seem crazy, but, you
[00:21:58] know,
[00:21:59] I don't I I I can't put myself on the
[00:22:01] same pedestal as him, but one of my
[00:22:03] mentors and idols growing up and then
[00:22:06] also early in my career was John
[00:22:07] Carmack, the founder of id Software.
[00:22:09] >> John is great.
[00:22:10] >> John is incredible. And for people who
[00:22:11] don't know, he's basically the inventor
[00:22:13] of the modern modern 3D game engine,
[00:22:16] first-person shooters, also started a
[00:22:18] rocket company that competed in the
[00:22:20] >> He he was competing in the X Prize, and
[00:22:21] I I remember
[00:22:22] >> And he was one of the, if not the only
[00:22:25] one to be doing reusable
[00:22:27] >> Exactly, he was doing vertical takeoff,
[00:22:28] vertical landing.
[00:22:29] >> else was even trying to do. He did it.
[00:22:31] >> I remember there's this this name on the
[00:22:33] side of his vehicles, Armadillo
[00:22:35] Aerospace.
[00:22:36] How do you pronounce that thing? I
[00:22:37] thought you'd only know. That's right.
[00:22:38] He was using So, yeah, he was using uh
[00:22:39] he was using uh he was building his own
[00:22:40] sensor fusion algorithms. He was
[00:22:41] processing them on modern, you know, or
[00:22:43] on you know, commercial-style graphics
[00:22:45] card hardware using his game programming
[00:22:50] experience. Anyway, the point is it was
[00:22:52] called Armadillo Aerospace. That's
[00:22:55] right. And the thing and yeah, they were
[00:22:57] doing vertical takeoff and landing long
[00:22:59] before SpaceX was
[00:23:01] was was was I mean, doing anything.
[00:23:03] >> Yeah. No, before it existed, for sure.
[00:23:06] >> And but anyway, the the point is he he
[00:23:10] I I he ended up becoming the CTO of
[00:23:12] Oculus VR. I managed to poach him away
[00:23:14] from Id, but after he left, he went to
[00:23:18] work on AI actually even before I did.
[00:23:22] And so he started he started his own
[00:23:23] company to work on on on AGI. And
[00:23:27] and I said why why are you why are you
[00:23:29] doing this?
[00:23:30] >> You know, that the odds of you
[00:23:30] succeeding and to be clear, I still
[00:23:32] believe AI was going somewhere, but he
[00:23:34] said, "I'm going to start a company
[00:23:35] that's just going all in on the end
[00:23:38] state. Like I'm not trying to
[00:23:39] incrementally get there. It's just all
[00:23:40] in on AGI." And the point that he made
[00:23:42] was, "Palmer, even if I've got a 1%
[00:23:45] chance of succeeding, which maybe is an
[00:23:47] overestimation, but suppose I have a 1%
[00:23:49] chance of succeeding, and suppose that I
[00:23:51] could pull it off,
[00:23:55] the the risk-adjusted
[00:23:57] outcome kind of demands that I do it.
[00:24:01] And that was how I felt about defense.
[00:24:02] If there was a 1% chance that I could
[00:24:05] help solve this problem, then it was one
[00:24:07] that would be massively impactful to
[00:24:09] work on versus, let's say, starting
[00:24:11] another gaming company, getting into
[00:24:13] space launch,
[00:24:15] you know, building a car company, which
[00:24:18] it it all of the billionaires, they end
[00:24:20] up doing the same thing. You don't have
[00:24:21] enough people getting into defense or or
[00:24:23] putting on a bat suit. It's just it's
[00:24:26] just cars and rockets and and they just
[00:24:28] go in circles like that for for for
[00:24:31] >> So, you know, when I interviewed you on
[00:24:32] the on the Moonshots podcast last time,
[00:24:34] you mentioned that you're part of a
[00:24:36] billionaire's boys club chat.
[00:24:38] >> Yeah, yeah.
[00:24:39] >> [clears throat]
[00:24:39] >> Oh, yeah.
[00:24:39] >> Are they working on anything worthwhile
[00:24:41] at this point? I mean, I gave I gave
[00:24:43] them for saying like, "God, you got
[00:24:44] all this capital. Solve the world's
[00:24:46] biggest problems."
[00:24:47] >> I think the B boys are doing a lot
[00:24:48] better now than we were a few years ago.
[00:24:50] >> Okay.
[00:24:51] >> Um
[00:24:51] >> They're they're stepping up.
[00:24:53] >> And and for people you think we're
[00:24:54] talking about is I I was giving a lot of
[00:24:56] people a hard time, especially some
[00:24:57] retired B boys. And uh I was telling
[00:25:01] them what are you what are you doing?
[00:25:01] You have cuz money is one of the
[00:25:04] resources they have. But one of the
[00:25:06] resources people don't talk about,
[00:25:07] especially for the retired B boys, is
[00:25:09] that they have credibility, which would
[00:25:11] allow them to gather people around them,
[00:25:13] teams around them, and capital. Like
[00:25:16] they could and it's just sitting there
[00:25:17] underutilized if they're doing nothing.
[00:25:20] They have the credibility in that people
[00:25:22] trust them as a leader to be able to
[00:25:23] lead an organization like that.
[00:25:26] They could have the same ideas and the
[00:25:28] same words as somebody who's equally
[00:25:30] smart or smarter and they'll still do
[00:25:33] better for that. And so my point to them
[00:25:34] is you have a responsibility not only as
[00:25:36] someone who's who's got a lot of capital
[00:25:38] yourself, but who's got this
[00:25:39] underutilized resource of the ability to
[00:25:41] do more.
[00:25:44] If if you're not doing that, then are
[00:25:46] you really like what are you even doing?
[00:25:48] Anyone can sit on a boat. Few people can
[00:25:51] start another multi-billion dollar
[00:25:53] company that does something that
[00:25:54] matters.
[00:25:54] >> [applause]
[00:25:56] >> And the good news is most of them I
[00:25:58] think I I I think a lot of people have
[00:26:00] have gotten the itch to to solve some of
[00:26:02] these problems that are out there.
[00:26:04] Nihilism is is is on is on the down.
[00:26:10] >> [laughter]
[00:26:10] >> Yeah, that's an interesting point.
[00:26:12] Although
[00:26:13] Like I said, I think most of the B boys
[00:26:15] I think they seem like they keep pretty
[00:26:17] busy.
[00:26:18] I don't I don't I don't have a problem
[00:26:20] with B boys who don't do enough. Like to
[00:26:22] some people they mis- mistake what I
[00:26:23] what I say like oh Palmer wants other
[00:26:25] billionaires to work on defense or
[00:26:27] energy or or biology.
[00:26:30] You like
[00:26:31] my point is not that people need to
[00:26:33] distract themselves by doing more
[00:26:34] things. A lot of people can only do one
[00:26:36] thing.
[00:26:37] You know, and that was what I did for a
[00:26:38] long time.
[00:26:40] It's what I hate is the people who are
[00:26:42] not doing anything. That's that that is
[00:26:44] that is like a repulsive to me.
[00:26:46] >> So maybe message to the audience, you
[00:26:48] get to join the B boys slack group or
[00:26:50] whatever this is,
[00:26:51] Telegram, if you're doing something new
[00:26:54] and differentiated.
[00:26:55] >> The group actually got shut down and uh
[00:26:57] we've been we've been talking about now
[00:26:59] that we need to do a B boys 2.0.
[00:27:01] Um but I think I think people post
[00:27:03] >> some B girls as well.
[00:27:04] >> I think people posted the wrong memes a
[00:27:05] few too many times.
[00:27:07] >> Boom.
[00:27:08] >> I I look uh there there was there was a
[00:27:10] time where there were no there were no B
[00:27:12] girls and then there was this Business
[00:27:14] Insider article uh whining about it and
[00:27:17] uh the the reality is like it's just
[00:27:18] like me and some guys.
[00:27:20] >> Like you know, it's not like there's
[00:27:21] this isn't like the Illuminati
[00:27:22] conference.
[00:27:23] >> [laughter]
[00:27:23] >> You know, it's like they're they're like
[00:27:25] oh, there's a group and you know, but no
[00:27:27] women have been invited. I'm like I it's
[00:27:28] not that no women have been invited.
[00:27:30] It's just like me and some some of my
[00:27:32] boys. But
[00:27:33] >> [laughter]
[00:27:33] >> uh but actually there there was a there
[00:27:35] was a there was a there was a girl in it
[00:27:37] by the end. So, uh we need Yeah, we need
[00:27:39] to we need to restart that. We need to
[00:27:40] restart that group.
[00:27:41] >> So, you're in Facebook commercials now.
[00:27:44] >> Oh, yeah. Yeah, yeah.
[00:27:45] >> Yeah, so so the new Meta VR is out, uh
[00:27:49] how does it compare against your vision
[00:27:50] of what you wanted to achieve? Is it
[00:27:53] Yeah.
[00:27:54] >> Look, it does a lot of the things that
[00:27:56] uh it's not exactly what I would make
[00:27:57] were I the guy who's waving the magic
[00:27:59] wand and and and and you got lots of
[00:28:01] magic wands spinning the CAD, but
[00:28:04] uh
[00:28:04] look, the new Meta VR glasses are a lot
[00:28:07] closer in a lot of ways. Uh so, I've
[00:28:09] long been a believer that you need to
[00:28:11] decouple the compute and the battery
[00:28:14] from the head. You should it should not
[00:28:16] be that and and I'm not even saying the
[00:28:18] head totally, it's more of the front.
[00:28:19] So, uh before Oculus Quest. So,
[00:28:22] Oculus Quest was the last thing that I
[00:28:24] worked on before they fired me. And uh
[00:28:26] the prototypes at the time were
[00:28:28] a prototype series code named Santa Cruz
[00:28:31] and uh we were sure actually showing
[00:28:33] that publicly before they fired me. And
[00:28:36] uh Santa Cruz had the battery and
[00:28:37] compute on the back of the head and then
[00:28:40] the light, you know, the part on the
[00:28:41] soft tissue on the front of your head
[00:28:42] was kept as light as possible. And then
[00:28:44] at some point after they got rid of me,
[00:28:46] they they jammed it all into one big
[00:28:48] giant lump in the front and they ruined
[00:28:49] the ergonomics. They forgot why you need
[00:28:51] a top strap. Uh,
[00:28:53] but you know, it it it it bothers
[00:28:55] >> Serve them right.
[00:28:56] >> It bothers me most Look, it bothers me
[00:28:59] mostly at this point because uh
[00:29:01] the Oculus Rift CV1, which was the first
[00:29:03] modern consumer VR headset, it got the
[00:29:06] ergonomics more or less perfect in 2016
[00:29:10] and you know, we we were showing it off
[00:29:11] in 2015 and literally nobody has done as
[00:29:16] good of as it and it's been over a
[00:29:17] decade. Every single person screws it
[00:29:20] up, even Apple. And I I I just I don't I
[00:29:23] can't comprehend it. How how could it be
[00:29:25] that the ergonomic design led by a
[00:29:28] 19-year-old kid with no experience is
[00:29:32] better than anything that anyone has
[00:29:34] come up with since. Anyway, the new Meta
[00:29:36] VR glasses are the closest thing.
[00:29:39] And they're very lightweight. They've
[00:29:40] off-boarded the computer. They've
[00:29:41] off-boarded the batteries. They have
[00:29:43] really high-quality pass-through.
[00:29:45] Um they they It has a feature that I
[00:29:47] invented for CV1 called Transformo
[00:29:49] Fabric, which they do not call it.
[00:29:51] The basically using uh fabric uh a a a
[00:29:55] a soft flexible fab black black
[00:29:58] light-absorbing matte fabric to one
[00:30:00] minimize reflections, but two uh
[00:30:02] basically seal the cavity between and
[00:30:04] around the lenses. That means that you
[00:30:06] can move them uh and the fabric just
[00:30:08] stretches to meet where the lenses are
[00:30:10] for different interpupillary distances
[00:30:12] rather than having like sliding
[00:30:13] mechanical interfaces and plastic and
[00:30:16] they brought Transformo Fabric back for
[00:30:18] the first time since my my era. So, I'm
[00:30:20] I'm I'm a huge fan and uh you know, it's
[00:30:22] it's a third of the price of Apple's
[00:30:24] product and uh somewhat higher higher
[00:30:27] pixel density. I I think that's pretty
[00:30:29] extraordinary. Oh, and and and 1/8 the
[00:30:32] weight.
[00:30:32] >> Yeah. Amazing.
[00:30:33] >> Pretty amazing. Pretty good.
[00:30:36] >> Let's close on Let's close on this.
[00:30:38] We've got, you know, 1,500
[00:30:39] entrepreneurs, moonshot visionaries, and
[00:30:43] tens of thousands watching on the live
[00:30:44] stream.
[00:30:46] Uh
[00:30:46] what's your advice?
[00:30:48] What, you know, what did you learn in
[00:30:50] high school that made you succeed at the
[00:30:54] speed you did?
[00:30:55] We were talking about this on the plane
[00:30:56] right back.
[00:30:57] >> I I was really lucky to uh I guess maybe
[00:31:00] not lucky. I did it. Uh but
[00:31:02] >> Well, you are you are lucky.
[00:31:04] >> That's right.
[00:31:05] >> I am [laughter] lucky.
[00:31:06] >> It's in the name.
[00:31:06] >> I started an online community called
[00:31:09] ModRetro when I was 14 or 15. Uh it was
[00:31:12] an internet forum for people who were
[00:31:15] modifying vintage game consoles and
[00:31:17] computers, building handheld units,
[00:31:19] improving the performance in a variety
[00:31:21] of ways. We had a few thousand active
[00:31:22] members.
[00:31:24] And uh and a whole team of volunteer
[00:31:26] moderators and administrators with with
[00:31:28] me me at me at the top of it for some
[00:31:30] reason.
[00:31:31] And uh I learned a lot of valuable
[00:31:33] lessons about how you can build an
[00:31:35] organization, how you market an
[00:31:37] organization, how you get people to
[00:31:39] believe in what you're doing. I learned
[00:31:41] a lot about dealing with the types of
[00:31:44] problems you deal with when you're
[00:31:45] running a company, you know.
[00:31:46] >> With humans.
[00:31:47] >> Well, I mean, you you have you have two
[00:31:48] It's a tale as old as time. You've got
[00:31:50] two people.
[00:31:51] They're both brilliant. They're both
[00:31:53] very good at what they do.
[00:31:54] And they hate each other. And they
[00:31:56] disagree over something. You need to
[00:31:58] somehow mediate the conflict or separate
[00:32:02] them in a way that allows you to get the
[00:32:03] value that that allows both of them to
[00:32:06] contribute value to the greater project,
[00:32:08] uh but not have them hate you, not have
[00:32:11] them lose faith in the broader thing,
[00:32:12] but also you not not kill each other.
[00:32:15] Sometimes that means you need to
[00:32:16] reconcile things between the two.
[00:32:18] Sometimes it means that you need to put
[00:32:20] one guy over here and one guy over here.
[00:32:22] And sometimes you need to make sure that
[00:32:23] they don't know that that's what you're
[00:32:24] doing as you do it. That's just
[00:32:26] [laughter] I'm not saying that's the key
[00:32:27] to running a successful business is the
[00:32:29] management of the two problem,
[00:32:31] but it's
[00:32:33] Yeah, and then and once you make it a
[00:32:34] three-body problem, now I'm out.
[00:32:36] >> [laughter]
[00:32:37] >> But uh but but it's it's that and a
[00:32:39] hundred things like it that I learned
[00:32:42] running Mod Retro that I was able to
[00:32:44] take into starting Oculus, to carry
[00:32:46] forward into what I'm doing in my other
[00:32:48] companies. And uh that that's why I'm a
[00:32:50] I'm a strong believer that the the the
[00:32:52] kids should should should get a job. And
[00:32:54] I I I also had a job starting when I was
[00:32:56] 14, so I learned how the real world
[00:32:57] works, too. But I I So, I'm a huge fan
[00:33:00] of people doing things at a scale that's
[00:33:02] larger than just themselves. In other
[00:33:04] words,
[00:33:05] don't just do a project, do a project
[00:33:07] with someone else. Do a project with
[00:33:09] other people. Build in the open, learn
[00:33:12] the the the the good parts of that, the
[00:33:14] bad parts of that. It it it's been
[00:33:16] extremely useful to me. And
[00:33:18] >> Has building changed in the age of AI?
[00:33:19] What advice do you have? Again, you
[00:33:21] know, we've been saying on the pod for a
[00:33:23] while now, you know, forget about grad
[00:33:25] school, you know, even college is a is a
[00:33:27] maybe. You didn't go to college. You
[00:33:29] know, and high schoolers should what?
[00:33:32] Find a a purpose they care about and use
[00:33:35] AI to go and code it. What's your your
[00:33:37] closing advice here on that?
[00:33:40] >> You know, one of the reasons I have not
[00:33:42] been as upset as some people about uh
[00:33:48] Now, it's funny. There's something on
[00:33:49] the screen. It's like it's to not talk
[00:33:51] about
[00:33:52] >> [laughter]
[00:33:53] >> Just wanted to make sure you saw that.
[00:33:54] >> I I I did. We're not going to talk about
[00:33:55] Don't think about it. All right,
[00:33:56] company. All right, great. Great.
[00:33:59] >> [laughter]
[00:34:00] >> The uh
[00:34:02] There's the There's a lot of people who
[00:34:03] who who love their craft and they love
[00:34:05] what they do. And uh and and they are
[00:34:08] rightfully mourning uh the end of, for
[00:34:11] example, coding things by hand top to
[00:34:13] bottom, start to finish as anything but
[00:34:15] like a craft endeavor. Um and and I and
[00:34:18] I understand that. It's it's the same
[00:34:19] way that a lot of artists felt when the
[00:34:21] camera was invented. They They whined
[00:34:23] and complained about how it ruined art
[00:34:25] and it made it so that anybody could
[00:34:26] push a button. And and you know, the
[00:34:28] these things are always painful for the
[00:34:29] people who are masters of their craft.
[00:34:32] Um I already got screwed in that way a
[00:34:34] long time ago. When you're a founder,
[00:34:35] you don't get to actually work in any of
[00:34:36] the tech anyway. All the other people
[00:34:38] get to have all the fun. And so, you
[00:34:40] know, I I like electrical engineering. I
[00:34:42] like optical engineering. I like
[00:34:43] mechanical engineering. I don't get to
[00:34:45] do any of it cuz the job of a founder is
[00:34:47] to
[00:34:48] hire people to to displace them. And and
[00:34:51] and to do what they thought they could
[00:34:53] do or what they like they do like doing
[00:34:56] better. The job, I've said many times to
[00:34:58] people, if you want to work on
[00:34:59] technology
[00:35:01] work for somebody else. If you want to
[00:35:03] work on nonstop start a
[00:35:05] company.
[00:35:07] And so and so what I would say to people
[00:35:08] is AI doesn't actually change the
[00:35:11] part of the job very much.
[00:35:13] You're still on the hook legally. You're
[00:35:15] still on the hook for all the
[00:35:16] interpersonal stuff. And you could you
[00:35:18] you can delegate some of it, but at the
[00:35:19] end of the day it's your call, it's your
[00:35:21] decision. It's the same thing for
[00:35:23] fundraising. It's the same thing for
[00:35:24] general product architecture. And when
[00:35:26] people make the wrong decisions, it's
[00:35:27] your choice
[00:35:29] as to when you need to overrule them,
[00:35:31] override them, replace them. I don't see
[00:35:33] AI replacing that part of it anytime
[00:35:36] soon. Not because it couldn't, but
[00:35:38] because the gains everywhere else are so
[00:35:40] much larger that I think we've got a
[00:35:42] good 10 years of speed running
[00:35:45] all of the other parts of the business
[00:35:47] before they before they come to that.
[00:35:48] So, look, AI changes a lot, but I I I'm
[00:35:51] telling you there's a lot of people you
[00:35:52] are in for a rude awakening if you are
[00:35:54] like a hobbyist coder or a hobbyist
[00:35:56] engineer and you think you're going to
[00:35:58] start a company and you think you're
[00:35:59] going to be doing all that stuff? No,
[00:36:01] you're going to learn a hard lesson. It
[00:36:04] Being a founder was was always like AI
[00:36:06] took your job. It's just that other
[00:36:08] people took it.
[00:36:09] >> Yeah.
[00:36:10] Ladies and gentlemen, let's give it up
[00:36:12] for Palmer Luckey.
[00:36:19] >> [music]
