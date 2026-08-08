---
video_id: AWe_4K1kAlI
title: "My Complete AI Tech Stack in 2026 (Mac Mini, Claude, Tailscale, Plaud & My Own Harness) | Prevail.sh"
channel: Fru Dev
url: "https://www.youtube.com/watch?v=AWe_4K1kAlI"
watched_date: 2026-07-18
watched_at: "2026-07-18T12:00:00Z"
watch_count: 1
duration_seconds: 1225
source: youtube-history-browser
added_date: 
history_label: Jul 18
history_order: 163
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 122
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [research, primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

Fu shares his 2026 AI tech stack built around Mac hardware: a Mac Mini as the central hub with storage expansion via Crucial SSDs (standardizing on 4TB drives) and Seagate/Western Digital HDDs following a 3-2-1 backup principle (three copies across two media types with one offsite). He connects remotely to this always-on machine using Jump Desktop and Tailscale for secure network access. For capturing data, he uses a Soundcore Anker voice recorder (chosen over Plaud for its USB-C charging simplicity). On the software side, he relies heavily on Claude via terminal access with multiple accounts to avoid hitting rate limits, explicitly avoiding most desktop apps (Claude Desktop, Codeex Desktop, etc.) in favor of a custom "Prevail" harness he built himself that integrates models, projects, MCP integrations, and skills into one workflow.

To replicate this stack: purchase a Mac Mini with external storage and standardize on 4TB Crucial SSDs for consistency; implement 3-2-1 backups using both SSDs and large-capacity HDRives with an offsite copy. Set up Jump Desktop for $20-30 as your remote-access tool and Tailscale (free tier available) to network your Macs securely. For voice capture, choose the Soundcore Anker recorder for its USB-C charging compatibility. Subscribe to Claude's API/paid tier with multiple accounts to maintain flow state without hitting rate limits. Version everything in Git repos (public and private). Most critically: build or heavily customize your own harness rather than relying on vendor-provided desktop apps—Fu argues everyone should do this to stay competitive as the space evolves at speed.

## Transcript

[00:00:00] In 2025, I went out and bought myself a
[00:00:03] Mac Mini, and life has never been the
[00:00:05] same again. If you're new to the
[00:00:07] channel, my name is Fu. I make video
[00:00:09] tutorials helping you be AI ready across
[00:00:12] YouTube. I've amassed millions of views
[00:00:14] across several different channels I run,
[00:00:17] as well as shipping real products used
[00:00:20] every day by thousands of people around
[00:00:22] the world. My goal is to unpack my tool
[00:00:25] set to showcase that and hopefully
[00:00:27] illuminate or inspire you as you're
[00:00:29] thinking about your own AI journey. Now,
[00:00:32] back to the Mac Mini. This has been
[00:00:34] indispensable in my stack. When I bought
[00:00:37] the Mac Mini back in 2025, this was
[00:00:39] preopen claw. This was pre people
[00:00:42] realizing that they could run their own
[00:00:45] AI agents at home. That investment was
[00:00:48] incredible. Now, there are several of
[00:00:50] things I use in my stack and I'm
[00:00:52] hopefully going to break them up and
[00:00:53] showcase that to you in the video so you
[00:00:56] can be inspired in your own stack. Now,
[00:00:58] if something in here stands out, let me
[00:01:01] know in the comment section below. I
[00:01:02] always love hearing from you guys. This
[00:01:05] particular video will be broken up into
[00:01:06] a couple of sections. At the very
[00:01:08] bottom, we're going to start with the
[00:01:09] hardware and I'm going to talk about the
[00:01:11] software, talk about the models, and
[00:01:13] then I'll talk about some of the
[00:01:14] projects that come out of this. So here
[00:01:17] on my screen, which is what you're
[00:01:18] seeing, is the hardware. At this point,
[00:01:21] I live in the Mac ecosystem. It makes it
[00:01:24] easy, so I'm not having to relearn where
[00:01:26] things are are just because Mac does
[00:01:29] such a great job. You will have the Mac
[00:01:31] Mini, which is literally the starting
[00:01:33] point for most people. I have several
[00:01:35] MacBook Pros, MacBook Air, MacBook Neo,
[00:01:38] you name it. I think at this point, my
[00:01:41] house could as well be a MacBook store
[00:01:43] or a Mac store or an Apple store,
[00:01:45] whatever they call it these days. But
[00:01:46] you don't have to go to that extreme. I
[00:01:48] would say just a MacBook, a Mac Mini is
[00:01:51] a good starting point for most people.
[00:01:53] Challenging part of this now is it's
[00:01:56] really hard to come by this. If you go
[00:01:58] down to your local store, your local
[00:01:59] Best Buy or wherever you go to, it's not
[00:02:01] as easy finding Mac Minis today. But if
[00:02:04] you can get your hands on it, I would
[00:02:05] say this is a good starting point. There
[00:02:07] are options of getting access to this
[00:02:10] running services in the cloud but for me
[00:02:12] owning the hardware just makes it
[00:02:14] indispensable as a starting point. Now
[00:02:17] once you have that my rig I bought this
[00:02:21] uh plastic piece it doesn't look fancy
[00:02:24] it doesn't look sophisticated but it
[00:02:25] gets the job done. So the Mac Mini sits
[00:02:28] in there and I do have several and I
[00:02:30] mean several drives attached to that for
[00:02:33] storage by the nature of what I do.
[00:02:36] Having extra storage is key. And so this
[00:02:39] storage port or storage locations in
[00:02:42] here makes it extremely extremely easy
[00:02:45] to get everything set up, bundled up and
[00:02:48] you can put away this in a closet and
[00:02:50] simply forget about it. And I'll talk
[00:02:52] through that. Now from a storage
[00:02:53] perspective I do use quite a bit of
[00:02:57] devices from Crucial and the reason why
[00:02:59] is standardization as much as possible.
[00:03:02] If you go to your local electronic store
[00:03:04] you would find all kinds of solid state
[00:03:08] drives or you will find all kinds of
[00:03:10] hard this drives. My philosophy is
[00:03:13] always to standardize where it makes
[00:03:14] sense just from a form factor
[00:03:16] perspective. It just makes it a lot
[00:03:18] easy. So, in this case, this Micron
[00:03:20] Crucial has been my go-to. If you have
[00:03:23] drives that are just the same size, the
[00:03:25] same format, it's easy to name them,
[00:03:27] it's easy to label them or carry them if
[00:03:30] if you see fit as opposed to having
[00:03:32] drives of different form factor. So, for
[00:03:35] me, Crochial has been the go-to. And I
[00:03:37] do have several of the four. They do
[00:03:39] have the 1 TB. I tend to stay away from
[00:03:41] that just because I would rather have
[00:03:43] two 4 TB that gives me 8 TB of storage
[00:03:46] as opposed to getting 8 1 TB just
[00:03:50] because now you're doubling your
[00:03:51] hardware. You're doubling physical
[00:03:52] space. And if going minimal and clean is
[00:03:55] what you care about, then I will it's
[00:03:58] the price is scary to be transparent on
[00:04:00] that. But I would rather just invest in
[00:04:02] that upfront to get the storage. So once
[00:04:04] you have that, you can imagine stacking
[00:04:07] those underneath here on this in this
[00:04:10] holder and it does make it really really
[00:04:13] work. Now my philosophy with that from a
[00:04:15] storage perspective is you can never
[00:04:18] have too much storage. So I will invest
[00:04:21] as much in the SSDs and then also in
[00:04:24] hard disk drives. So I don't have the
[00:04:26] pictures pulled up here but I'm looking
[00:04:28] at things like Seagate or Western
[00:04:30] Digital. they have several 16 terabytes
[00:04:33] or 14 terabytes from those with the idea
[00:04:36] being that you want to follow the 3 to1
[00:04:38] principle. So three copies of data
[00:04:41] whatever data it is you're working on
[00:04:44] across two different types of media. So
[00:04:46] the two different medias would be SSD is
[00:04:49] one media and had this drive is another
[00:04:51] media. So those are two different
[00:04:53] medias. then you want to at least have a
[00:04:55] copy of your content or data or asset
[00:04:59] which is offsite. So if you think about
[00:05:02] everything plugged into this at home
[00:05:05] that's not as resilient as having a copy
[00:05:08] offsite in case this gets taken away
[00:05:11] from you or something happens to that.
[00:05:13] So having that is key from a cloud
[00:05:16] storage perspective. I do use the Google
[00:05:19] Drive ecosystem but that is not the main
[00:05:22] driver for storage. Now that is for the
[00:05:25] hardware. Now there's one piece of the
[00:05:26] hardware I want to highlight to you guys
[00:05:28] as well which is the voice recorder. I
[00:05:31] do believe that when it comes to
[00:05:32] hardware, your ability to collect data
[00:05:36] that powers your AI is key. So what I
[00:05:40] use for my daily voice memo, if you
[00:05:43] haven't heard about this category, it's
[00:05:45] a device you can talk into simply by
[00:05:47] pushing a button and it will record that
[00:05:50] voice. My setup with this is and I'm
[00:05:52] moving things around. This particular
[00:05:54] one which is from Soundcore work by
[00:05:57] Anker. Anker is a company I think you
[00:05:59] might have heard of them making barries.
[00:06:02] So they do actually make this voice
[00:06:04] memos. This particular gadget is the one
[00:06:07] actually have several of them. It just
[00:06:09] comes in handy. There is a nice form
[00:06:11] factor in here with a little pin that
[00:06:14] you can push a button talking into. It
[00:06:16] captures your voice. It captures your
[00:06:18] ideas. It captures your notes. it turns
[00:06:20] that into something that AI can work
[00:06:23] with. And again, this whole setup is
[00:06:25] about being efficient with AI. So this
[00:06:27] this particular device, again, it's not
[00:06:28] sponsored, but it's indispensable for my
[00:06:31] setup. Like I said, I've had several
[00:06:33] copies of them. The closest analogy or
[00:06:36] the closest competitor to this would be
[00:06:38] Plot. I have actually had a chance to
[00:06:41] use both. I've used the anchor and I've
[00:06:44] used the plot device. Plot comes in
[00:06:46] different form factors. They have the
[00:06:49] PIN, which is what you're looking at.
[00:06:50] They have like a credit card you can put
[00:06:52] on the back of your phone and record.
[00:06:53] People have conversations around this on
[00:06:55] privacy. I'm not here to adjudicate
[00:06:57] that. I'm simply talking about the
[00:06:59] practicality and the usage of these
[00:07:02] tools. Now, I claim
[00:07:07] more expensive than Soundcore Anchor. I
[00:07:11] ended up returning my Plaw just sticking
[00:07:14] with the Anchor for for many reasons.
[00:07:16] One of them just being something as
[00:07:18] simple as the USBC right here on Anchor.
[00:07:22] This device plugs in there. You charge
[00:07:24] it from here. You can go into the
[00:07:26] details of battery life and form factors
[00:07:28] and all of that. For me, simplicity is
[00:07:30] key. My goal is when I travel or if I'm
[00:07:34] doing something, I just want to have one
[00:07:37] cable to deal with and that cable should
[00:07:39] charge everything I have. So be it in my
[00:07:42] laptop, my phone, my my AI devices, the
[00:07:46] one cable to charge it. And the fact
[00:07:47] that Ankor has this USB C in here means
[00:07:51] I'm never having to worry about some
[00:07:54] unique cable charging port to deal with
[00:07:58] that I have to carry extra with that.
[00:08:00] And unfortunately, Plaude doesn't have
[00:08:03] the same flexibility. If you look on
[00:08:06] their own device, there isn't a port
[00:08:09] there. There isn't a USBC. It does come
[00:08:11] with a little gadget which is what you
[00:08:13] see here with a pin. This pin actually
[00:08:16] has a USBC attached to it. But you have
[00:08:18] to fiddle around quite a bit to get a
[00:08:20] charge. And for me that alone was a deal
[00:08:22] breaker. But the AI for plot is very
[00:08:24] strong. And I might do a more detailed
[00:08:26] video comparing the two because I think
[00:08:28] data capture is a big part of your AI
[00:08:31] infrastructure or your AI stack. So that
[00:08:34] is the hardware. So between the Mac
[00:08:36] ecosystem, do I have any Windows
[00:08:39] computer? I think I should answer that.
[00:08:40] I have one I have a Surface that I I
[00:08:43] don't think I've used in 5 years. It
[00:08:45] exists just because I want to have
[00:08:46] something in case some my life has to
[00:08:49] depend on opening up Windows that I have
[00:08:52] that. But dayto-day is I just never use
[00:08:54] it. Mac is the go-to driver from a
[00:08:58] hardware perspective. a lot of hardware,
[00:09:00] a lot of storage devices, and then a
[00:09:03] hardware for capturing the AI notes and
[00:09:06] summaries and all of that that fits into
[00:09:07] my AI ecosystem. So, once you have your
[00:09:10] hardware figured all out, the next thing
[00:09:12] you're going to want to think about in
[00:09:13] this layer is the connectivity. So, if I
[00:09:17] have a MacBook Pro or Mac Mini or
[00:09:20] MacBook Neo or Mac, you name it, Mac
[00:09:24] Studio, whichever one you have, how do
[00:09:25] you actually connect to it? So, I'm
[00:09:27] recording this video from one of my
[00:09:29] MacBook Pros. But how do I get access to
[00:09:33] my Mac Mini? It doesn't have a screen.
[00:09:35] If you look at what the Mac Mini is, it
[00:09:36] doesn't have, of course, you can buy a
[00:09:38] screen for it or a monitor, but it
[00:09:41] really defeats the purpose if that's
[00:09:42] what you're using it for. For me, a Mac
[00:09:44] Mini is you buy it, you set it up, and
[00:09:46] you should just forget about it on its
[00:09:48] own corner for it to do its thing. So,
[00:09:49] how does it do its thing in my case?
[00:09:51] This is where Jump Desktop comes in. So,
[00:09:54] if you see here, I have this app called
[00:09:57] Jam Desktop. It does cost some money.
[00:09:59] It's a onetime fee you pay, but it's
[00:10:01] incredible. It allows you to remote into
[00:10:04] any of your Mac instances once you set
[00:10:06] up Jam desktop. So, I will grab Jam
[00:10:08] Desktop. I've done some demos on Jam
[00:10:10] desktop on the channel. You can see
[00:10:12] those videos. So, grab Jam Desktop and
[00:10:14] that's it. In my case here, I do have
[00:10:16] Jam Desktop installed. Open that up.
[00:10:19] I'll go up to the top of my screen. You
[00:10:21] can see this is my Mac Mini. So I'm
[00:10:24] getting into my Mac Mini here. Once you
[00:10:26] have your Mac Mini as such, then this
[00:10:29] you can use this for any automation, any
[00:10:32] AI agents. It's just there. It's plugged
[00:10:34] in. You can literally forget about it.
[00:10:36] Now Mac or the Apple ecosystem comes
[00:10:39] with the screen share which you can use
[00:10:42] to remote into machines within your
[00:10:44] network. The reason for jump desktop is
[00:10:48] I'm not always home. I might have my
[00:10:49] MacBook Pro with me somewhere traveling
[00:10:52] and I I still want to get into my Mac
[00:10:54] Mini and so having this using Jam
[00:10:58] desktop gives you that flexibility where
[00:11:00] from wherever you are in the world you
[00:11:02] can obviously remote into it. So that's
[00:11:04] my setup and not only can I remote into
[00:11:07] the Mac Mini, I can remote into the
[00:11:09] MacBook Pro, the MacBook Air, the
[00:11:11] MacBook Neo or any Mac appliance that
[00:11:14] needs to be accessed. So jump desktop
[00:11:17] really really key. I'm sure there are
[00:11:18] some options out there but jump desktop
[00:11:20] has been amazing for me. So I would log
[00:11:23] in here. Mac Mini is always on. Agents
[00:11:25] are running. Automations are all running
[00:11:27] and that's how this setup works. Now one
[00:11:29] additional thing and I won't show this
[00:11:31] too much is tail scale. Tails scale is
[00:11:34] indispensable as part of this setup
[00:11:36] where you can have all of your Mac
[00:11:39] machines pulled into one network
[00:11:42] securely using tail scale. So you're not
[00:11:45] having to open a port or do a lot of
[00:11:47] networking pieces especially if this is
[00:11:50] not your frontier or not your forte. I
[00:11:52] will keep it simple. Tails scale has
[00:11:54] just been indispensable. Every one of
[00:11:55] your machines registered into tails
[00:11:57] scale. The reason why I don't want to
[00:11:58] open up tail scale now is obviously you
[00:12:00] can see the icon below here is obviously
[00:12:03] I don't want to show my topology of
[00:12:05] machines and names and stuff but you can
[00:12:07] be rest assured that tail scale is
[00:12:09] indispensable and maybe in the future
[00:12:11] I'll make a dedicated video on tail
[00:12:13] scale alone and what this means is
[00:12:16] wherever be it on my phone on the road
[00:12:19] at home any machine I want I simply can
[00:12:22] pick up any machine and remote into any
[00:12:24] other machine to do work so that's the
[00:12:27] hardware piece layer with the
[00:12:30] connectivity on top. Now coming back
[00:12:33] into into this, we've seen the hardware,
[00:12:36] we've seen the connectivity layer. The
[00:12:38] next piece of it is the AI models. And
[00:12:41] this is where I'm going to switch gears
[00:12:42] here a little bit to use prel to talk
[00:12:44] about that daytoday I from a model
[00:12:48] perspective I would use the terminal. I
[00:12:52] I've tried the semox of the world. I've
[00:12:54] tried the herders of the world. I've
[00:12:56] tried so many things, but right now I
[00:12:58] essentially will come back and I
[00:13:00] essentially come back into the terminal.
[00:13:02] So for those who don't know what Simox
[00:13:04] is, Simox is a it's actually a really
[00:13:05] good tool. I've made quite a bit of
[00:13:06] videos around this. It allows you access
[00:13:09] to your AI models. So if you're using
[00:13:11] claw or the codeex or Gemini, you want
[00:13:14] an easy way to come into it, Simox gives
[00:13:16] you this almost like the browser the way
[00:13:19] Chrome is to browsing the internet. You
[00:13:22] can imagine that Simox is the browser to
[00:13:24] your AI models. You can have tabs. It
[00:13:27] just gives you a more flexible way of
[00:13:29] doing it. Name things and have those
[00:13:31] agents running. Herder is another really
[00:13:33] really good one up and coming. I've done
[00:13:36] video tutorials around Herder. And the
[00:13:39] product is is really great with the
[00:13:41] philosophy of keeping things as simple
[00:13:43] as possible. I still find myself just
[00:13:45] coming back to the plain old terminal.
[00:13:48] So opening up a terminal and having one
[00:13:51] tab, two tabs. You can see I have two
[00:13:53] tabs in here. If I need a new tab, I can
[00:13:56] simply open up that new tab and go into
[00:13:58] AGY. In this case, it's anti-gravity and
[00:14:00] just bouncing ahead. Now, why would I
[00:14:04] use this as opposed to Simox or O'Hara?
[00:14:07] Again, it just comes down to simplicity.
[00:14:09] I I think at at my scale, at my age, or
[00:14:12] whatever it is you want to make the
[00:14:14] excuse for, I just want simple things,
[00:14:16] not too complicated, not making it
[00:14:19] overly sophisticated than it needs to
[00:14:22] be. And in as much as I would have like
[00:14:25] strong praises for Simox and Herder find
[00:14:28] myself coming back just using the plain
[00:14:30] old terminal. And I think if that's what
[00:14:32] I'm doing, that's what I'm going to
[00:14:33] share with my channel. So you that's
[00:14:35] you're watching this video, you get
[00:14:36] exactly what I use. So that's that the
[00:14:40] piece I use and I'll switch back here.
[00:14:43] Daytoday I use cloth. So most of my work
[00:14:47] is done with essentially cloth. I don't
[00:14:50] have codeex. I don't have anti-gravity
[00:14:53] as much but cloth you can see I would
[00:14:56] write up to the max plan and I have
[00:14:58] several accounts. I've been very
[00:15:00] transparent with that. So, if I'm in the
[00:15:02] middle of a big project and you're
[00:15:03] burning through those tokens, hitting
[00:15:05] those daily limits or hourly limits or
[00:15:07] whatever the limits are these days, I
[00:15:09] want to be able to just simply log out,
[00:15:11] logging back into another account and
[00:15:12] just keep going. And as far as I'm
[00:15:15] paying Claude the money and I'm paying
[00:15:16] an the money, I feel good about that.
[00:15:19] So, it's it's very challenging to be in
[00:15:22] a flow state of trying to ship something
[00:15:25] out and then hit a limit that forces you
[00:15:27] to wait for 4 hours. I don't have the
[00:15:29] four hours luxury always to to wait. So,
[00:15:32] usually I can go into different accounts
[00:15:35] to use. So, if you use Claude, I would
[00:15:37] encourage or any of your favorite AI
[00:15:39] tool, I would encourage thinking about
[00:15:41] several accounts. Of course, it does
[00:15:42] cost money, but that is my my setup.
[00:15:45] Now, do I use the desktop app for Claude
[00:15:48] or Codeex or Gemini? Not really. So, you
[00:15:50] don't even see that showing up on my
[00:15:52] tray at the bottom here because I really
[00:15:54] do not use that. So the the models kind
[00:15:57] of going to the stack we're building
[00:15:58] here. You have your hardware at the
[00:16:00] bottom. You have your connectivity which
[00:16:03] is what we've talked about for tail
[00:16:04] scale and jump desktop. You have the
[00:16:08] pure model itself which I tend to use
[00:16:10] oppus models from cloth more so than any
[00:16:13] other. For the rest I do use the free
[00:16:15] tiers. I also have a bit of open router
[00:16:19] but I don't use that as much. And then
[00:16:21] on my Mac Mini, I do run like LLM studio
[00:16:25] in there with a few open- source models,
[00:16:27] but again, I don't use that as much.
[00:16:29] Now, the piece that is very very
[00:16:31] important to touch on is the layer,
[00:16:34] which is essentially your harness. And
[00:16:37] this is where I've tried all the
[00:16:39] harnesses out there, several of them,
[00:16:41] the Claw desktop, the Codeex desktop,
[00:16:44] the AGY app, and all of them. And the
[00:16:47] only thing I found to work is me just
[00:16:50] building my own my very own harness. And
[00:16:53] this is what you see here with prelink
[00:16:55] in the description below. If you want to
[00:16:57] try pre out, highly encourage it. Give
[00:16:59] it a star on on GitHub. And what this
[00:17:01] means for me is where work actually
[00:17:04] happens. The way I do work and the way I
[00:17:06] do work might be different from the way
[00:17:07] you do work. Now what the harness does
[00:17:09] is it brings together the models the the
[00:17:13] projects or the domains I work on which
[00:17:15] you can see here on the left side
[00:17:17] frameworks that I use for thinking about
[00:17:20] stuff the lenses different modes my my
[00:17:23] security primitives access to the
[00:17:26] different models like we've discussed
[00:17:27] being able to pull these models into a
[00:17:29] council and there's a whole lot of other
[00:17:32] capabilities in here from benchmarks the
[00:17:35] arena skills that are running agents
[00:17:38] that do summarizations, usage, cost, MCP
[00:17:42] integration, you name it. All of this is
[00:17:44] what this harness brings for me. So, do
[00:17:47] I use claw desktop? No, I don't. Do I
[00:17:49] use codex desktop? No, I don't. Well,
[00:17:52] why don't I use any of those? Because I
[00:17:54] have my own harness, which I think is
[00:17:56] superior for my actual workflows. And
[00:17:59] I've done videos and demos on the prel
[00:18:03] harness. Now, I think this is the the
[00:18:05] whole stack that brings it up together.
[00:18:07] So daytoday if I'm working on a specific
[00:18:09] project I'll come in to whatever that
[00:18:12] project is and this is a demo harness
[00:18:14] let's say YouTube making these videos on
[00:18:16] YouTube I would have I'll go into the
[00:18:18] YouTube project chat with that and the
[00:18:21] beauty of doing that in this is it keeps
[00:18:23] the context it learns it keeps my skills
[00:18:27] it keeps my MCP my authentication
[00:18:29] everything in in one place and so if you
[00:18:32] are in need of a harness you might
[00:18:34] really want to build your own at this
[00:18:36] point I Everybody should be building
[00:18:38] their own harness. If you're having to
[00:18:39] rely on cloth or codeex to give you a
[00:18:42] harness, I think you're probably going
[00:18:43] to be falling behind with the way and
[00:18:46] the speed at which this is going. Now,
[00:18:48] for actual coding, do I use like a
[00:18:50] cursor or things like that? No, I don't
[00:18:52] because again, I just go directly to the
[00:18:54] CLI to code. Now, for version control, I
[00:18:57] do use Git. Everything is a version into
[00:19:00] Git. So, between Git repos for the
[00:19:03] actual coding aspect. So if I'm coding
[00:19:05] here, I simply are pointing to that
[00:19:07] folder, putting in my prompt, making
[00:19:10] sure everything is in my git repo. I
[00:19:12] have quite a bit of private and public
[00:19:13] git repos. For open source projects, I
[00:19:15] do have the public git repos for for the
[00:19:18] non. I do have quite a bit dozens and
[00:19:20] dozens of private git repos that version
[00:19:22] controls every everything. So that is my
[00:19:25] current AI setup in the three stacks
[00:19:29] hardware connectivity AI models as well
[00:19:32] as the harness on top of that that makes
[00:19:35] me do work. This space is fast evolving.
[00:19:38] There's quite a bit of things that are
[00:19:39] moving. I continue to do video tutorials
[00:19:42] on new tools paperclip
[00:19:46] agent you name it. Pi agent. The reality
[00:19:49] is I do that for instructive purposes,
[00:19:52] for educational purposes because that's
[00:19:54] what this channel is all about. But
[00:19:55] dayto-day am I physically using that
[00:19:58] less and less and the reason for that is
[00:20:00] because I build my own harness and I
[00:20:03] keep everything simple for my dev
[00:20:06] development workflow. So hopefully this
[00:20:08] gives you a little bit behind the
[00:20:09] scenes. I think this was this video was
[00:20:12] actually requested by one of the viewers
[00:20:14] and I hope this this helps. If you want
[00:20:15] to see more videos like this, I'm happy
[00:20:17] to do that. As always, this is F. Thank
[00:20:19] you for watching and sticking to the
[00:20:20] end.
