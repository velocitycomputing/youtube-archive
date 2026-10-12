---
record_id: "youtube:3CUVuk7AkJQ"
video_id: 3CUVuk7AkJQ
title: Ukraine Hit Yandex. Did Russia’s Bots Go Silent?
channel: Ryan McBeth
url: "https://www.youtube.com/watch?v=3CUVuk7AkJQ"
watched_date: "2026-10-12"
watched_at: ""
watch_count: 1
duration_seconds: 538
source: manual-add
added_date: ""
history_label: null
history_order: null
watched_at_precision: null
watched_percent: null
estimated_watched_seconds: null
transcript_status: fetched
transcript_content_hash: 0f08b664ea4a43b655b8b52f2d1a2d3cbdb0ededd85040f6c581858518447eb3
analysis_mode: health
summary_source: local
model_source: local
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: Qwen3.8-Flash-Next-UD-Q4_K_XL
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
topic_domain: politics
status: new
routed_to: null
---

## Summary

The video examines claims that Ukrainian drone strikes on Yandex data centers silenced Russian propaganda bots. It notes Yandex confirmed attacks on three facilities—Sazovo in Ryazan on October 7–8, 2026, Kaluga on October 9, and Vladimir on October 11—with Reuters attributing the strikes to Ukraine and President Zelenskyy framing them as responses to Russian attacks on Ukrainian data centers. The strikes disrupted Yandex services including search, maps, taxi, mail, and Alice, with partial restoration reported by October 11; Sazovo reportedly houses two AI supercomputers, though damage was unconfirmed. A separate October 8 outage at Russian network security provider Qrator affected media organizations and a bank, complicating attribution. The Cloudflare Radar graph cited for “bots disappearing” tracks automated web requests from Yandex network AS13238, not all propaganda accounts; it shows traffic falling on October 8 and near zero on October 11, but could reflect crawlers, maps, ads, or service outages. The speaker, who has advocated treating botnet infrastructure as targets, cites the DOJ’s July 2024 case involving an AI-run Russian bot farm with 968 accounts linked to RT, and concludes the evidence supports infrastructure disruption, not proof that Russian influence operations went offline.

For follow-up, treat the bot-silencing claim as unproven and verify with primary sources: Yandex statements, Reuters, Cloudflare Radar AS13238, Qrator/RBC outage reports, and DOJ filings. Ask whether the traffic drop has a denominator, whether known propaganda accounts went dark and later resumed, and whether the missing traffic came from crawlers, maps, ads, or influence accounts. Track service restoration versus physical damage, especially the Sazovo supercomputers, repair timelines, lost data, and computing capacity. For policy or research decisions, distinguish kinetic strikes on commercial infrastructure from targeted disruption of identified influence networks, and consider legal, escalation, and civilian-service risks. Useful next steps include building account-level bot inventories, monitoring platform-specific propaganda activity, and comparing outages with unrelated technical failures before attributing them to military strikes.

## Transcript

[00:00:00] Did Ukraine just knock Russia's
[00:00:02] propaganda bots offline? You've probably
[00:00:05] seen the claim floating around that
[00:00:07] Ukrainian drones hit Yandex data centers
[00:00:10] and all of a sudden Russian propaganda
[00:00:12] bots have disappeared from the internet.
[00:00:15] There is a real attack behind this
[00:00:17] story. There's also a traffic graph, but
[00:00:20] the conclusion people are drawing
[00:00:21] actually goes further than the evidence.
[00:00:24] And I have a personal reason to be
[00:00:25] careful here. I have often argued that
[00:00:28] we should consider going after hostile
[00:00:30] botnet infrastructure kinetically. That
[00:00:32] means physically attacking the data
[00:00:35] centers or the people behind the
[00:00:38] operation, physically killing the
[00:00:40] information warfare practitioners who
[00:00:42] organized the attacks and destroying the
[00:00:44] data centers that carry out the attacks.
[00:00:46] I have advocated for that. I've given
[00:00:49] speeches about that. I am 100% serious
[00:00:52] that we need to consider information
[00:00:54] warfare practitioners as combatants and
[00:00:57] their infrastructure as targets. So,
[00:00:59] this is exactly the kind of story that I
[00:01:02] would love to believe. Which means I
[00:01:05] need to check it especially carefully.
[00:01:08] Before we get started, make sure you
[00:01:09] subscribe. If you want to support the
[00:01:11] channel, you can do so for only $2.50 at
[00:01:13] ryanbethea.substack.com.
[00:01:15] By the way, it's almost Christmas. You
[00:01:17] can grab my this meeting could have been
[00:01:19] signals intelligence shirt and bunker
[00:01:20] branding for the person in your life who
[00:01:22] hates meetings. Now, Yandex is a major
[00:01:26] Russian technology company with search
[00:01:28] and cloud computing, maps, and email, a
[00:01:30] bunch of other services.
[00:01:32] Its own Russian language statement
[00:01:34] confirms the attack on three data
[00:01:37] centers. Now, during the night of
[00:01:39] October 7th into October 8th, 2026,
[00:01:43] drones severely damaged its facility in
[00:01:46] Sazovo in the Ryazan region, southwest
[00:01:49] of Moscow. And Yandex ops operations
[00:01:53] stopped there completely uh, within
[00:01:55] minutes. On October 9th, another attack
[00:01:58] hit a data center in Kaluga, southwest
[00:02:01] of Moscow. Part of that, uh, facility's
[00:02:03] infrastructure went out of service.
[00:02:05] Then, on the night leading into October
[00:02:07] 11th, the Vladimir data center east of
[00:02:10] Moscow was attacked and shut down.
[00:02:12] Yandex reported no injuries at that
[00:02:14] facility.
[00:02:15] So, there was a sequence of attacks over
[00:02:18] several days, and Reuters attributes
[00:02:20] those strikes to Ukraine. And on October
[00:02:23] 8th, President Zelenskyy said Ukraine
[00:02:24] was responding to Russian attacks on
[00:02:27] Ukrainian data centers. He also didn't
[00:02:29] announce that Ukraine had switched off
[00:02:31] Russia's propaganda bots. People started
[00:02:34] coming to that conclusion themselves.
[00:02:37] Now, what did these strikes actually
[00:02:39] accomplish? Well, they they interrupted
[00:02:41] genuine computing services. On October
[00:02:43] 11th, Yandex said access to search,
[00:02:46] maps, taxi, mail, and its Alice
[00:02:48] assistant, uh, was gradually returning,
[00:02:52] although some functions remained
[00:02:53] unavailable. Interfax reported that
[00:02:56] statement. And that's kind of evidence
[00:02:58] of disruption followed by a recovery, at
[00:03:00] least a partial recovery. It doesn't
[00:03:02] establish that every single service
[00:03:03] failed everywhere, or that the failures
[00:03:05] were permanent. And the,
[00:03:08] Saz- Saz- Saz- the first site, uh, is
[00:03:11] particularly significant because it
[00:03:13] houses two supercomputers that are used
[00:03:15] for AI development. Uh, Reuters reported
[00:03:17] that Yandex not said whether those
[00:03:18] machines were damaged. A shut down data
[00:03:21] center and a destroyed supercomputer are
[00:03:23] two different findings, though. You can
[00:03:26] lose access to equipment without losing
[00:03:28] the equipment itself. And just because a
[00:03:31] service returned doesn't necessarily
[00:03:32] mean the original building has been
[00:03:34] completely repaired.
[00:03:35] Now, Yandex said it was still accessing
[00:03:37] the infrastructure and couldn't give a
[00:03:39] clear timetable for restoring equipment.
[00:03:41] So, we should keep the immediate service
[00:03:43] interruptions separate than the
[00:03:45] long-term repair bill for their
[00:03:47] facilities here. What we don't yet have
[00:03:49] is a complete inventory of destroyed
[00:03:51] servers and lost data and computing
[00:03:53] capacity that just can't be recovered
[00:03:56] easily.
[00:03:57] There's another complication. On October
[00:03:59] 8th, a Russian network security provider
[00:04:01] called Qrator had a separate failure
[00:04:04] during technical maintenance and
[00:04:06] according to the company's account
[00:04:07] reported by RBC, that affected customers
[00:04:10] including media organizations and a
[00:04:12] bank. So, like we can't take every
[00:04:15] single Russian website that went offline
[00:04:17] that day and count it as damage from
[00:04:19] that Ukrainian strike. Sometimes
[00:04:21] companies just go offline because of
[00:04:23] their own mistake. Now, let's get to the
[00:04:25] bots and in in order to understand this,
[00:04:27] you have to separate the propaganda bots
[00:04:30] from bots that do everyday tasks. The
[00:04:33] graph behind this story comes from
[00:04:35] Cloudflare Radar. It tracks automated
[00:04:38] web requests from a Yandex network
[00:04:40] identified as AS13238.
[00:04:43] That is a Russian internet network
[00:04:46] identifier, not the name of a Russian
[00:04:49] intelligence unit. Now, a published
[00:04:51] capture of that chart shows traffic
[00:04:53] falling on October 8th and dropping
[00:04:55] close to zero on October 11th. The
[00:04:57] timing is consistent with the
[00:04:59] infrastructure disruptions, but we need
[00:05:01] to read the label on the graph before
[00:05:03] deciding what is happening. Cloudflare
[00:05:06] is measuring web requests that reach
[00:05:08] websites served by its network. Those
[00:05:11] are your bots. It's not counting every
[00:05:14] Russian propaganda bot on every social
[00:05:17] media platform. And in this context, a
[00:05:20] bot means traffic that is classified as
[00:05:24] automated. That classification doesn't
[00:05:26] tell us whether the request was
[00:05:27] propaganda, whether the operator works
[00:05:29] for Russian intelligence, or whether
[00:05:30] somebody is trying to influence an
[00:05:32] election. Search engines use bots. You
[00:05:36] visit websites and collect information
[00:05:38] so the search engines can find pages for
[00:05:40] you. Maps might use bots to give you
[00:05:43] advertisements for restaurants near a
[00:05:46] certain area. If a if a web crawler
[00:05:49] stops visiting websites
[00:05:52] the or the the map service stops looking
[00:05:55] for restaurant reviews, then the bot
[00:05:57] traffic graph goes down.
[00:06:00] That doesn't establish that fake
[00:06:02] Americans stopped arguing about Ukraine
[00:06:04] on social media. It also wouldn't be
[00:06:06] responsible to claim that all missing
[00:06:08] traffic was harmless, but the graph
[00:06:10] doesn't give that breakdown. So, people
[00:06:12] are taking a look at this graph and just
[00:06:14] assuming
[00:06:16] it's Russian propaganda bots that
[00:06:17] disappeared and it's not.
[00:06:20] A percentage on a traffic chart needs
[00:06:22] kind of a denominator a drop relative to
[00:06:26] a recent peak isn't the the the number
[00:06:28] of Russian propaganda accounts disabled.
[00:06:31] So,
[00:06:32] this kind of supports a very narrow
[00:06:35] conclusion. Automated traffic observed
[00:06:37] from a particular Yandex network fell
[00:06:39] sharply. Turning that claim into
[00:06:42] Russia's influence operation went
[00:06:44] offline is evidence we don't have.
[00:06:47] And like in order to figure that out, we
[00:06:50] need to start we need to take a look at
[00:06:52] a set of accounts that are known bots.
[00:06:55] And notice that they have been offline
[00:06:58] for a certain amount of time and then
[00:06:59] see them pop back up online. And we saw
[00:07:02] that with the Scottish independence
[00:07:04] movement that went silent on Twitter
[00:07:07] when Iran essentially shut off their own
[00:07:09] internet so they wouldn't get cyber
[00:07:10] attacked. Iran was operating these
[00:07:12] Scottish independence uh
[00:07:15] accounts on Twitter and Facebook and
[00:07:17] Instagram and so on.
[00:07:18] So, you need to look for something like
[00:07:20] that. Did a bot go dark and then resume
[00:07:22] and services return?
[00:07:24] Uh and there is genuine honest-to-god
[00:07:27] Russian bot networks out there. I mean,
[00:07:29] July of 2024 the Justice Department
[00:07:32] found an AI run Russian bot farm
[00:07:35] involving 968 social media accounts. Uh
[00:07:38] and this was developed uh people
[00:07:40] associated with RT Russia Today, uh and
[00:07:43] operate with government objectives in
[00:07:45] mind. But, just because you really want
[00:07:48] something to be true doesn't mean that
[00:07:51] it's actually true. And in this case,
[00:07:52] unfortunately, people are
[00:07:54] misunderstanding what the bots actually
[00:07:57] are. So, no, there's no proof that
[00:07:59] attacking Yandex has eliminated Russian
[00:08:03] propaganda bot traffic. Thank you for
[00:08:05] watching.
[00:08:08] >> OH, MAN, I [screaming] HAVE TO WORK IN
[00:08:10] THE SKIFF. MAYBE I'LL JUST TAKE MY PHONE
[00:08:12] IN THE SKIFF.
[00:08:13] >> HEY, KID, WHAT'S GOING ON?
[00:08:14] >> THINK TANK.
[00:08:15] >> YOU KNOW, TAKING A PHONE into the skiff
[00:08:17] isn't cool. It could really hurt your
[00:08:19] friends. But, a t-shirt or hoodie from
[00:08:21] Bunker Branding sure is cool.
[00:08:23] >> Wow, this meeting could have been
[00:08:25] signals intelligence. That's like every
[00:08:28] meeting.
[00:08:28] >> And Bunker Branding HAS ALL SORTS OF
[00:08:30] OTHER MERCHANDISE.
[00:08:32] >> Intel life, aerosol, live laugh launch
[00:08:35] for Destroyer, [music] Trident, HIMARS,
[00:08:37] and Patriot. Think outside the bomb,
[00:08:39] drone, sweet drone, Department of
[00:08:41] [music] the Boat People, land mine, and
[00:08:43] even the TOW missile. It would behoove
[00:08:45] you to grab one today.
[00:08:46] >> You know, I don't think you can smoke in
[00:08:48] here.
[00:08:48] >> I'm not smoking. I'm just holding a lit
[00:08:50] cigarette in my mouth.
[00:08:51] >> Now I know.
[00:08:53] >> And knowing is half the battle.
[00:08:54] >> Bunker Branding
