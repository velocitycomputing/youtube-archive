---
video_id: Ptmt0-8cAX0
title: Industrial Controls Are a Hacker’s Dream
channel: Ryan McBeth
url: "https://www.youtube.com/watch?v=Ptmt0-8cAX0"
watched_date: 2026-05-29
watched_at: "2026-05-29T12:00:00Z"
watch_count: 1
duration_seconds: 1111
source: youtube-history-browser
history_label: Friday
history_order: 39
watched_at_precision: date-from-history-label
watched_percent: 15
estimated_watched_seconds: 167
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video discusses zero trust principles applied to operational technology (OT)—the systems controlling physical infrastructure like power plants, water treatment, pipelines, and industrial robots—which differ fundamentally from IT security. Unlike IT breaches that expose data, OT compromises can cause physical damage, contamination, or endanger lives. Legacy OT systems, designed decades ago without cybersecurity considerations, use unencrypted protocols, lack authentication, and cannot be scanned like normal devices. The presenter breaks down the NIST cybersecurity framework for OT across six domains: governance (establish decision-making authority and break-glass procedures), identification (maintain complete asset inventory including controllers and firmware versions), protection (enforce segmentation, use hardened jump hosts for remote access, separate IT and OT identity systems), detection (baseline normal behavior and alert on deviations), response (create incident playbooks before incidents occur), and recovery (test backups regularly and verify integrity against tampering).

Actionable steps include: assume attackers are already inside your network and limit their lateral movement through enforced segmentation and monitoring; implement jump hosts with multi-factor authentication and session recording for all remote access rather than allowing direct vendor connections; maintain detailed inventory of every device, its location, firmware version, and communication protocols; establish detection baselines for normal traffic patterns and create alerts for deviations; document and test incident response procedures that address unique OT constraints (isolating the wrong system could stop critical processes); back up not just files but OS configurations, application software, controller logic, and startup values, then regularly test those backups with integrity verification to catch tampering.

## Transcript

[00:00:00] If you have anything connected to the
[00:00:02] internet, you might want to pay
[00:00:04] attention to this video, especially if
[00:00:07] you're using industrial controls or
[00:00:10] something on the Internet of Things.
[00:00:12] What is the zero trust concept and why
[00:00:15] is it so important right now, especially
[00:00:18] when countries like Iran have hacked
[00:00:20] things? Like, I know you just heard the
[00:00:23] word zero trust and thought like, oh
[00:00:25] great, another freaking cybersecurity
[00:00:26] buzzword. I get it. Zero trust is one of
[00:00:29] those phrases that kind of gets thrown
[00:00:31] around by vendors who want to sell you a
[00:00:33] dashboard and a license. But in
[00:00:35] operational technology, which is the the
[00:00:39] things that run our systems that do
[00:00:42] things like control dams or water power
[00:00:44] plants or whatever, zero trust is not a
[00:00:47] buzzword. It is a real thing. It is the
[00:00:49] difference between someone stealing your
[00:00:51] email and someone turning off a water
[00:00:54] pump from inside Tehran. And those two
[00:00:56] things are very different problems.
[00:00:58] Couple of things to get started. First
[00:01:00] off, you like my shirt? This meeting
[00:01:02] could have been singing. Grab it at
[00:01:03] Bunker Branding. But the next thing to
[00:01:06] talk about is what is operational
[00:01:08] technology or OT. Well, it's not your
[00:01:11] laptop. It's not your email server. It's
[00:01:14] not your computer that that Karen in
[00:01:16] accounting uses to create a fake invoice
[00:01:19] from dhlsupport.ru,
[00:01:21] right? Operational technology is the
[00:01:24] stuff that touches the physical world.
[00:01:26] So, the stuff that controls power
[00:01:28] plants, water treatment systems,
[00:01:30] pipelines, building automation, rail
[00:01:32] systems, industrial robots,
[00:01:34] >> [sighs and gasps]
[00:01:35] >> physical access controls like your door
[00:01:37] key card, system that starts a valve,
[00:01:40] opens a valve, starts a pump, changes
[00:01:42] pressure, tells a chemical process to do
[00:01:45] something. Basically, the industrial
[00:01:46] controls that do physical stuff. So,
[00:01:48] when cybersecurity people talk about OT,
[00:01:51] operational technology, they're not just
[00:01:53] talking about data. They're talking
[00:01:55] about physical stuff that touches the
[00:01:57] real world. And that's why this is
[00:02:00] important. You know, zero trust matters,
[00:02:03] but you can't just take an IT security
[00:02:05] model, slap it into a factory, and call
[00:02:07] it good. Because in IT, if you mess up a
[00:02:09] security policy, all right, someone
[00:02:11] loses access to SharePoint. In
[00:02:14] operational technology, if you mess up a
[00:02:16] security policy, you might shut down a
[00:02:18] plant, damage equipment, contaminate
[00:02:20] water, put people in danger. And that's
[00:02:23] why zero trust in OT has to be
[00:02:25] different. Now, what is zero trust?
[00:02:27] At its core, zero trust means you can't
[00:02:30] automatically trust something just
[00:02:32] because it's inside your network.
[00:02:34] You verify identity, you verify the
[00:02:35] device, you verify the request, you look
[00:02:37] at the context. You say, "Hey, should
[00:02:39] this person from this system be doing
[00:02:42] this thing at this time?"
[00:02:44] And the big assumption here is that bad
[00:02:47] guys might already be inside. And that's
[00:02:49] not paranoia, dude. That's just good
[00:02:51] cybersecurity. Cuz the old model was
[00:02:53] basically a castle. Right? You had a
[00:02:55] moat. And the bad guys were outside of
[00:02:58] the moat. The good guys were inside of
[00:03:00] the moat.
[00:03:02] My new podcast, Mike. I keep bumping
[00:03:04] into it because I talk with my hands.
[00:03:06] Good guys inside the moat, bad guys
[00:03:08] outside of the moat, good guys inside of
[00:03:11] the castle, and you could pretty much
[00:03:13] guess that if you got inside of the
[00:03:14] castle, you could move around freely.
[00:03:17] That model is dead.
[00:03:19] In operational technology, this gets
[00:03:21] worse because a lot of systems that
[00:03:23] control these things were designed
[00:03:25] decades ago, back when cybersecurity
[00:03:27] wasn't even a priority or something
[00:03:30] people even understood. They might have
[00:03:31] understood passwords, but just in the
[00:03:34] '90s, the idea of remoting in from far
[00:03:37] away, that was the stuff of movies like
[00:03:39] The Net. You know, it just It just It
[00:03:42] just didn't happen, especially with
[00:03:44] industrial control systems. And
[00:03:46] availability was the priority back then,
[00:03:49] not ne- Well, safety as well, not
[00:03:52] necessarily cybersecurity. You know, and
[00:03:56] this system had to run for 20 or 30
[00:03:58] years. Had to survive heat and vibration
[00:04:00] and dust, weird electrical conditions,
[00:04:02] whatever the heck was going on inside
[00:04:03] that factory.
[00:04:05] And a lot of these systems used old
[00:04:06] protocols that didn't have
[00:04:08] authentication. They might not even have
[00:04:10] encryption. Almost definitely don't have
[00:04:12] encryption. And they probably don't log
[00:04:14] very much, either, because logs would
[00:04:16] create space. And a lot of them they
[00:04:18] can't be scanned like a normal IT
[00:04:20] system. And that's kind of a big point.
[00:04:22] You don't just scan legacy OT devices
[00:04:25] unless you know what you're doing,
[00:04:26] because you could hit some old
[00:04:28] programmable logic controller with a
[00:04:30] vulnerability scanner, you can knock it
[00:04:32] offline. It's not a freaking Dell
[00:04:33] laptop.
[00:04:35] You know, and then congratulations,
[00:04:36] Eric. You didn't just conduct a security
[00:04:39] assessment, now you're the incident. On
[00:04:41] the subject of zero trust, do you trust
[00:04:42] your AI provider? I don't, which is why
[00:04:45] this video is sponsored by Venice AI. If
[00:04:48] you use AI like Claude or ChatGPT, do
[00:04:50] you trust it?
[00:04:52] I mean, ChatGPT is already returning ads
[00:04:54] based on prompt requests, and it's able
[00:04:56] to do that cuz it knows you.
[00:04:58] And then there's the restrictions. You
[00:04:59] know, when I made my video about Trump's
[00:05:01] land man Iran strategy, ChatGPT wouldn't
[00:05:03] let me swap President Trump and Billy
[00:05:05] Bob Thornton's face.
[00:05:07] My Photoshop skills aren't that good, so
[00:05:09] I used Venice AI in automatic mode, and
[00:05:11] I got the image I wanted for my
[00:05:13] thumbnail. Think of Venice AI as a VPN
[00:05:15] for AI prompts. Venice AI keeps your
[00:05:18] prompts local, and then sends your
[00:05:20] prompt request out to pretty much
[00:05:21] whatever AI engine you want. But the
[00:05:23] request is from Venice AI, not from your
[00:05:25] user account.
[00:05:27] So, if the government ever tries to
[00:05:28] subpoena your prompt records, they don't
[00:05:30] have anything tying you to your
[00:05:31] identity. And depending on what you're
[00:05:34] researching, that could be pretty darn
[00:05:35] important. One subscription and you get
[00:05:38] access to all the best tools and models
[00:05:39] on the market. Go to my sponsor,
[00:05:41] venice.ai/ryan,
[00:05:44] to access the world's leading AI models
[00:05:46] privately, all in place. Use code Ryan
[00:05:49] to get 20% off any pro plan and start
[00:05:52] taking back your privacy. So, let's talk
[00:05:55] about the NIST cybersecurity framework
[00:05:58] for operational technology. Govern,
[00:06:00] identify, protect, detect, respond, and
[00:06:03] recover. This all sounds boring, it's
[00:06:06] actually the whole darn game. Start with
[00:06:08] govern here. Governance is basically
[00:06:10] answering the question, who is allowed
[00:06:12] to make decisions and who owns the risk?
[00:06:14] In IT, cybersecurity people might say,
[00:06:17] "We're enabling multi-factor
[00:06:18] authentication and killing old
[00:06:19] protocols. Awesome, right? You log in,
[00:06:22] oh, multi-factor, yay!" In operational
[00:06:25] technology, the plant engineer might
[00:06:27] say, "Yeah, that's cool, but this
[00:06:30] particular system runs safety controls
[00:06:34] and your multi-factor authentication
[00:06:36] server, if that goes down, now nobody
[00:06:38] can respond and log in in an emergency."
[00:06:42] Which is why OT governance needs to get
[00:06:45] the engineers, the operators, the IT
[00:06:47] people, and the cyber people all in the
[00:06:49] same room, right? Like a bar fight.
[00:06:53] You need to decide what happens when
[00:06:55] security controls conflict with safety
[00:06:57] and you need these break-glass
[00:06:58] procedures. You also need like
[00:07:00] escalation paths, where do these things
[00:07:02] go? And you need compensating controls
[00:07:05] for if one industrial control fails.
[00:07:07] Because that whole least privilege thing
[00:07:09] is great right up until the person who
[00:07:11] can stop a bad physical process is
[00:07:13] locked out because their identity
[00:07:15] provider is down.
[00:07:18] Then we have to move to identify and
[00:07:20] this one sounds simple,
[00:07:22] know what you have.
[00:07:24] But in operational technology, this is
[00:07:26] surprisingly hard. A company almost
[00:07:29] definitely knows how many laptops it
[00:07:31] has, right?
[00:07:32] But does it know every controller,
[00:07:34] sensor, actuator,
[00:07:36] uh engineering workstation, remote
[00:07:38] access path, vendor connection, and like
[00:07:41] weird serial-to-ethernet converter
[00:07:43] that's sitting in a cabinet somewhere.
[00:07:46] And here's the thing, you can't really
[00:07:47] predict
[00:07:49] thing you can't predict
[00:07:51] outcomes for assets if you don't know
[00:07:55] they exist, right? And that's why asset
[00:07:57] inventory matters.
[00:07:59] So, where is everything located? What
[00:08:01] version of firmware is it running? What
[00:08:03] protocols? What engineering software do
[00:08:05] you have? What talks to what? What can
[00:08:08] write commands? What can only read? What
[00:08:11] vendor is allowed to remote in? Cuz
[00:08:12] sometimes vendors remote in to take a
[00:08:15] look at their stuff. And what happens if
[00:08:17] that remote vendor link disappears?
[00:08:20] And this is where passive modern
[00:08:22] monitoring becomes important. Instead of
[00:08:25] aggressively scanning everything,
[00:08:27] observe traffic. What does normal look
[00:08:30] like? Figure out that this device is
[00:08:34] talking to this device. And if these two
[00:08:36] things stop talking and another device
[00:08:39] starts talking to this device over here,
[00:08:42] well, maybe that shouldn't be happening,
[00:08:45] right? Also, note where the dangerous
[00:08:48] connections are because in operational
[00:08:50] technology, normal is often pretty
[00:08:52] stable. You're always sending the same
[00:08:55] information to a controller. If the
[00:08:57] sluice gate on a dam only opens when
[00:09:00] water is 7 ft from the top, they
[00:09:02] probably shouldn't open any other time.
[00:09:05] And if suddenly the sluice gate
[00:09:06] controller starts receiving commands
[00:09:08] from a workstation in accounting that
[00:09:10] the water level's too low, you know,
[00:09:12] well, any
[00:09:17] So, let's talk about protect. And this
[00:09:19] is where most people think zero trust
[00:09:20] kind of lives
[00:09:22] in identity and access control
[00:09:24] segmentation, remote access, and
[00:09:25] encryption. And yeah, segmentation is
[00:09:28] foundational. Operational technology
[00:09:30] networks have used segmentation for a
[00:09:32] long time cuz you don't want a problem
[00:09:33] in one area cascading to another area,
[00:09:36] right? So, you
[00:09:37] segment those networks, but segmentation
[00:09:39] isn't magic.
[00:09:41] Air gaps can be bridged by a guy with a
[00:09:42] USB drive, right? A VLAN can be
[00:09:45] misconfigured, a firewall rule can be
[00:09:46] too permissive, uh a vendor VPN can
[00:09:49] become the front door to your entire
[00:09:51] kingdom.
[00:09:53] So, zero trust and segmentation can't
[00:09:55] just be an architecture diagram that
[00:09:57] someone made in Visio back in like 2016,
[00:09:59] right? You have to enforce it, it has to
[00:10:01] be monitored, it has to be validated.
[00:10:03] And for remote access, use jump hosts,
[00:10:05] right? A jump host, so known as a
[00:10:07] bastion host, is basically a hardened
[00:10:09] entry point
[00:10:11] in the OT environment. So, you don't
[00:10:13] just let vendors or engineers remote
[00:10:15] directly in to the fragile legacy system
[00:10:19] that they're trying to maintain, right?
[00:10:21] You force them through that controlled
[00:10:23] point, and they go to the system from
[00:10:26] the jump host. That jump host should
[00:10:28] probably have multi-factor
[00:10:29] authentication, it should be patched
[00:10:31] regularly, it should be monitored, it
[00:10:32] should record sessions. Uh access should
[00:10:35] be time-limited where possible. If
[00:10:37] normally people only come in for an
[00:10:40] hour, then maybe you need to cut them
[00:10:42] off after an hour or if you notice them
[00:10:44] idle for a while.
[00:10:46] Uh remote access is probably the biggest
[00:10:47] weakness in operational technology, and
[00:10:49] sometimes it's necessary cuz vendors
[00:10:52] have to maintain their equipment, and if
[00:10:54] you have a distributed infrastructure,
[00:10:56] you may need remote operations or vendor
[00:10:59] support. I mean, try controlling the
[00:11:00] controllers on an oil pipeline, right?
[00:11:03] You can't just have people at every
[00:11:05] single controller on a pipeline that
[00:11:07] goes 500 miles. You are remotely
[00:11:09] connecting to those nodes, but that
[00:11:12] doesn't necessarily mean those nodes are
[00:11:13] unrestricted. So, the phrase you kind of
[00:11:16] want to think of here is just enough
[00:11:18] access,
[00:11:20] just enough time.
[00:11:21] And the danger zone here is when you
[00:11:23] give a company that shared vendor
[00:11:25] account. Yeah, it's easier, right, to
[00:11:27] create vendor name at whatever your
[00:11:30] email address is, and then every one of
[00:11:32] that vendor shares a login. But if
[00:11:34] someone quits or gets fired, they might
[00:11:36] still have access to your system. So,
[00:11:38] you need to give separate vendor
[00:11:39] accounts to each vendor that's going to
[00:11:41] work to Not each vendor, but each person
[00:11:43] at the vendor who's going to work on
[00:11:44] your system.
[00:11:46] Now, there's identity. Never directly
[00:11:48] connect IT and OT identity systems.
[00:11:52] Uh this means don't casually tie your
[00:11:55] corporate active directory to the OT
[00:11:57] environment, just kind of hope
[00:11:58] everything just works out. Because if
[00:12:01] the adversary compromises IT
[00:12:03] credentials, and those credentials are
[00:12:05] also trusted in
[00:12:06] operational technology, you just built
[00:12:08] them a bridge to go from your email
[00:12:11] server to your freaking equipment.
[00:12:13] And that's how you go from, "Hey,
[00:12:14] someone clicked a phishing link." to,
[00:12:16] "Why is the plant exploding?"
[00:12:19] Now, in corruption, in IT
[00:12:20] confidentiality is often king. You want
[00:12:23] to encrypt data because you don't want
[00:12:25] people reading it. In operational
[00:12:27] technology, integrity and authorization
[00:12:29] may actually matter more.
[00:12:31] Uh you need to know the command that was
[00:12:33] sent was real. You need to know where it
[00:12:34] came from, and it came from the right
[00:12:36] system. And you need to know that it
[00:12:37] wasn't modified.
[00:12:39] Full encryption can introduce latency or
[00:12:41] complexity, and some OT systems are
[00:12:44] time-sensitive. See, you kind of have to
[00:12:45] do this carefully. And look, you know,
[00:12:48] if you're reading at an industrial
[00:12:51] control, that thing might not be set up
[00:12:53] to decrypt. So, you're going to be
[00:12:54] decrypting this thing anyway before
[00:12:56] passing it over there. And encryption
[00:12:58] from here to here is fine, but if you're
[00:13:00] listening from here to here, where
[00:13:01] there's no encryption, you really
[00:13:02] haven't gained anything. That doesn't
[00:13:04] mean never encrypt. It means you
[00:13:07] understand the process before you start
[00:13:08] changing the process and determining
[00:13:10] whether encryption really matters. Then
[00:13:13] we get to detect. This is where
[00:13:15] operational technology has an advantage
[00:13:17] and a disadvantage. The disadvantage is
[00:13:20] that a lot of OT systems have terrible
[00:13:23] logging. Some legacy systems barely tell
[00:13:26] you anything. And the advantage is that
[00:13:28] this OT behavior can be predictable. A
[00:13:31] controller that sends you the same
[00:13:32] command every 5 seconds should not start
[00:13:35] behaving like a teenager with a credit
[00:13:37] card doing weird stuff.
[00:13:38] And
[00:13:40] really you baseline that detection and
[00:13:42] you create a specification based
[00:13:45] detection. Baseline means you need to
[00:13:47] learn what is normal
[00:13:48] and you alert on deviations. And
[00:13:50] specification means that you define what
[00:13:53] is valid behavior
[00:13:55] what that's supposed to be and alert
[00:13:57] when something violates that. Plain
[00:13:59] English, the pump should only receive
[00:14:01] certain commands from certain specific
[00:14:04] systems when it's in operational mode.
[00:14:06] And if something happens, look at it.
[00:14:09] Uh
[00:14:10] uh CISA even has this open-source tool
[00:14:12] called Malcolm that can help analyze
[00:14:15] network traffic including OT protocols.
[00:14:17] But again, you know, this kind of
[00:14:18] requires engineers.
[00:14:20] A cybersecurity analyst may know what a
[00:14:23] suspicious login looks like, but an OT
[00:14:26] engineer knows whether a command
[00:14:28] sequence can damage equipment. And
[00:14:30] honestly, you need both. You need both
[00:14:32] to work on this.
[00:14:34] Next is respond. So, this question is
[00:14:36] not just how do we keep people out, but
[00:14:38] what do we do if someone gets in? And in
[00:14:40] OT, incident response is not the same as
[00:14:43] IT. In IT, you might isolate a laptop.
[00:14:46] In OT, isolating the wrong system could
[00:14:48] stop a critical process or could cause
[00:14:50] some kind of physical damage in the real
[00:14:53] world. So, you need playbooks
[00:14:54] on what to do before the incident
[00:14:56] actually happens. Can you have some sort
[00:14:58] of manual override when you disconnect
[00:15:01] from the OT? But who is authorized to do
[00:15:04] that, right? And when is that playbook
[00:15:08] employed?
[00:15:09] And what if disconnecting causes a
[00:15:11] safety issue? What are your procedures?
[00:15:14] Um what if not disconnecting lets the
[00:15:16] attacker keep moving? So, you need to
[00:15:19] have clear procedures and flowcharts for
[00:15:20] everything you're going to do cuz you
[00:15:22] don't want to be inventing the plan at
[00:15:24] 2:30 2:30 in the morning, right? When
[00:15:26] alarms are going off, right? And you
[00:15:28] someone's on the phone like, "Hey, can
[00:15:30] you give me a quick update?"
[00:15:32] Finally, there's recovery. And this is
[00:15:33] the part that nobody likes cuz backups
[00:15:35] aren't sexy. Ew.
[00:15:36] >> But backups are how you survive. I mean,
[00:15:39] uh a couple of weeks ago I did a video
[00:15:41] on Stryker, and they were able to
[00:15:43] recover their systems from backups. So,
[00:15:45] you need to do backups.
[00:15:47] But in operational technology, backups
[00:15:49] are not just files. They're operating
[00:15:50] system configurations, application
[00:15:52] software, licensing, engineering logic.
[00:15:55] What are the configurations of your
[00:15:57] controllers?
[00:15:58] You also need like all the startup
[00:16:00] values, right? Cuz if you're starting
[00:16:02] from zero, you need to know what those
[00:16:05] values have to be. If your controller
[00:16:06] dies or gets wiped, or you have to
[00:16:08] rebuild an entire engineering
[00:16:09] workstation, do you actually have what
[00:16:12] you need?
[00:16:12] And have you tested it?
[00:16:14] Cuz an untested backup is like a bedtime
[00:16:16] story that you just kind of tell
[00:16:18] yourself,
[00:16:19] right? Feel-good story.
[00:16:21] And this might mean actually hashing
[00:16:24] your backups as well to make sure
[00:16:25] someone didn't tamper with the backups.
[00:16:27] Compare create a comparison against the
[00:16:29] backup and running code. Because if the
[00:16:31] bad guy also altered the backup, you
[00:16:33] need to know it's been altered.
[00:16:35] So, what's the big takeaway here?
[00:16:36] Zero trust in operational technology is
[00:16:39] not just about buying a product. It's
[00:16:42] about It's not about installing an agent
[00:16:44] in every single device because in some
[00:16:46] cases you can't install an agent, right?
[00:16:48] And it's not about pretending you can
[00:16:49] patch a 25-year-old controller. Think of
[00:16:52] this Think of it like defense in depth,
[00:16:54] right? Zero trust is a
[00:16:57] philosophy. Assume the bad guy is
[00:16:59] already there, limit what they can
[00:17:00] reach, verify who's doing what, segment
[00:17:03] the network, control remote access,
[00:17:06] monitor for weird behavior, plan the
[00:17:08] response, practice recovery. And above
[00:17:10] all,
[00:17:11] don't break the process you're trying to
[00:17:13] protect.
[00:17:14] Because in In the mission is usually
[00:17:16] data, right? In operational technology,
[00:17:18] the mission is keeping the lights on,
[00:17:20] keeping the water clean, keeping the
[00:17:21] trains moving, not killing anyone with
[00:17:23] your machines.
[00:17:25] And if your security plan depends on
[00:17:27] nobody ever making a mistake, then you
[00:17:28] don't have a security plan, you have a
[00:17:30] wish.
[00:17:31] Hey.
[00:17:32] Grab my this meeting could have been
[00:17:34] sigint shirt from bunker branding. You
[00:17:36] can also support the channel at
[00:17:37] ryanfb.substack.com.
[00:17:40] Thank you for watching. OH, MAN. I HAVE
[00:17:42] TO WORK IN THIS SKIP. MAYBE I'LL JUST
[00:17:44] TAKE MY PHONE IN THIS SKIP. HEY KID,
[00:17:47] WHAT'S GOING ON? THINK TANK. YOU KNOW,
[00:17:49] TAKING A PHONE into the skip isn't cool.
[00:17:51] It could really hurt your friends. But a
[00:17:53] t-shirt or a hoodie from bunker branding
[00:17:55] sure is cool. Wow, this meeting could
[00:17:58] have been sigint intelligence. That's
[00:18:00] like every meeting. And bunker branding
[00:18:03] has all sorts of other merchandise.
[00:18:05] Intel light, aerosol, live laugh launch
[00:18:08] for destroyer, [music] trident, HIMARS,
[00:18:10] and patriot. Think outside the bomb.
[00:18:12] Drone sweet drone. Department of the
[00:18:14] boaty landmines, and even the tow
[00:18:17] missile. It would behoove you to grab
[00:18:19] one today. You know, I don't think you
[00:18:20] can smoke in here. I'm not smoking. I'm
[00:18:23] just holding a lit cigarette in my
[00:18:24] mouth. Now I know, and knowing is half
[00:18:27] the battle. Bunker branding.
