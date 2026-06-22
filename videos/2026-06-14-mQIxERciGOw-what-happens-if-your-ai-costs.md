---
video_id: mQIxERciGOw
title: What happens if your AI costs jump 10x?
channel: Axel Molist
url: "https://www.youtube.com/watch?v=mQIxERciGOw"
watched_date: 2026-06-14
watched_at: "2026-06-14T12:00:00Z"
watch_count: 1
duration_seconds: 816
source: youtube-history-browser
added_date: 
history_label: Jun 14
history_order: 115
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 82
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker explores the parallels between the current AI investment boom and the dot-com bubble. Most major AI companies—OpenAI, Anthropic, and XAI—are losing substantial money (XAI burned $1B/month; OpenAI projects $14B losses this year) despite filing for IPOs, signaling private funding is drying up. Current AI pricing is artificially subsidized: customers pay a fraction of actual costs, with OpenAI losing money on its $200/month plan and Anthropic revealing power users consumed $1,000/day in value. Tech giants are pouring $700B annually into GPU data centers and chips, building infrastructure ahead of actual demand, mirroring how telecom companies laid dark fiber before the internet had cars to drive on it. Money circulates between AI companies (Nvidia lends to OpenAI, who buys from Nvidia), inflating their apparent health.

The actionable takeaway: don't become a hostage to a single AI provider. First, architect your systems to switch between providers if pricing jumps or service fails. Second, measure your true AI costs—not the subsidized ones you pay, which understate real spending. Third, run models locally on your own infrastructure wherever possible; the speaker's company transcribes phone calls using open-source models in their own data centers rather than cloud APIs, protecting against future price spikes and avoiding privacy exposure. Build this backup plan now before you need it, betting that as AI matures, more computing moves to devices and local servers, not just distant data centers.

## Transcript

[00:00:00] One day, people will ask what it was
[00:00:02] like to be alive today. What it was like
[00:00:04] to watch the three most valuable
[00:00:07] companies in history go public, one
[00:00:09] after the other. Except, if you're using
[00:00:12] AI, and I use it everywhere, you're
[00:00:13] you're not really watching it, you're in
[00:00:15] it.
[00:00:16] SpaceX is going public this week at a
[00:00:19] valuation of nearly 1.8 trillion
[00:00:21] dollars. And OpenAI and Anthropic have
[00:00:24] both just filed to go public straight
[00:00:26] after. So, when I say you're in it, what
[00:00:29] I mean is like, if you're anything like
[00:00:30] me, you spent the last couple of years
[00:00:32] deploying these products in your
[00:00:34] companies and and businesses. And if
[00:00:36] you're in software, you you you've gone
[00:00:38] even deeper. You know, you think about
[00:00:39] it. You got Copilot, Claude Code, Codex.
[00:00:43] You use these tools every single day.
[00:00:45] And these tools are these companies.
[00:00:48] Every API call you make ends up at one
[00:00:50] of them. I run three companies, and we
[00:00:52] have 140 people between them. And my
[00:00:55] software team uses AI. My marketing team
[00:00:58] uses AI. My finance team uses AI. All my
[00:01:02] teams across all my companies lean on it
[00:01:04] now. And I'm actually pushing them to
[00:01:06] use it even more. So, I'm not just
[00:01:08] in it, I'm at the deep end. I am
[00:01:11] swimming in it. And here's what really
[00:01:13] makes me worry.
[00:01:15] All but one of these AI companies we're
[00:01:18] that we're relying on
[00:01:19] are losing money, and a lot of it. And
[00:01:22] now, they're trying to go public to get
[00:01:25] more money from us.
[00:01:26] Uh so, are we in an AI bubble?
[00:01:29] Probably, but that's not really that I'm
[00:01:31] asking here. If you're a founder and CEO
[00:01:34] or software engineer, or if you're
[00:01:36] building anything with AI, you're
[00:01:37] probably asking yourself the same thing.
[00:01:39] How much of our business now depends on
[00:01:43] these AI companies? And what happens if
[00:01:45] one of them has a wobble, or just
[00:01:47] decides to charge us 10 times more?
[00:01:49] Because we've seen this kind of thing
[00:01:51] before. Look at the dot-com bubble. I'm
[00:01:53] not the financial side with all those
[00:01:54] overinflated valuations. I'm talking
[00:01:56] about the infrastructure side, the full
[00:01:58] fiber, the actual cables in the ground.
[00:02:01] Most of it sat unused for like 7 years
[00:02:03] after it was installed, and something
[00:02:05] very similar is happening now. So, in
[00:02:07] this video, I want to show you why this
[00:02:10] whole AI bubble is a replay of the
[00:02:12] dot-com crash, why your AI bill is a
[00:02:15] fraction of what it really costs, and
[00:02:18] what I'm actually doing to protect my
[00:02:19] companies before the bubble pops. Let me
[00:02:22] get into it.
[00:02:25] So, let me take you back to the year
[00:02:26] 2000. While the headlines were full of
[00:02:28] dot-com websites crashing and going to
[00:02:31] zero, something bigger was going on
[00:02:33] underneath it all. By this point, the
[00:02:35] whole world was convinced that the
[00:02:37] internet was going to be a huge thing.
[00:02:39] And if the internet was going to be
[00:02:40] huge, it needed to be connected up. And
[00:02:43] at the time, that meant cable.
[00:02:45] Tons of it. In the ground, under the
[00:02:48] sea, everywhere. So, the companies
[00:02:50] connecting it all up started borrowing a
[00:02:52] ton of money to lay as much fiber as
[00:02:53] they could as quickly as they could. And
[00:02:56] I mean quick. That at the peak, they
[00:02:58] were laying something like 180,000 km a
[00:03:01] day or something like that around the
[00:03:02] world. That actually means four loops
[00:03:04] around the planet every single day. They
[00:03:06] were building the roads before anybody
[00:03:08] owned the car, and the cars took like 7
[00:03:11] years to show up. So, all that cable
[00:03:13] just sat there in the ground unused. In
[00:03:15] telecoms, you got a name for that. We
[00:03:16] call it dark fiber. The cable that's
[00:03:18] been laid, paid for, but never actually
[00:03:21] been lit. At one point, only 3% of all
[00:03:24] the installed fiber in the US was
[00:03:25] actually lit. 3%. The rest of it just
[00:03:28] sat there in the dark, but somebody had
[00:03:30] to pay for it, and it was paid for with
[00:03:32] borrowed money. Most of the companies
[00:03:34] that connected up the internet ended up
[00:03:36] going bust. Some of the biggest
[00:03:38] bankruptcies in US history. But, here's
[00:03:40] the key point. When it all came crashing
[00:03:42] down, it didn't just take out the
[00:03:43] companies that laid the cable. It took
[00:03:45] out everyone who built their business on
[00:03:47] the internet. Now, there are people that
[00:03:49] made a ton of money out of it, but they
[00:03:51] came later. They walked in after the
[00:03:53] bubble burst and bought all that cable
[00:03:55] for a fraction of its cost. One undersea
[00:03:57] network cost $3.5 billion to build and
[00:04:01] it sold for $130 million.
[00:04:04] And on top of that cheap salvage wiring,
[00:04:06] they built the internet that we know
[00:04:07] today. YouTube, Netflix, Google, all of
[00:04:11] it. And this is my arena. We run our own
[00:04:13] network at Circle Cloud and that
[00:04:14] infrastructure is what enabled our
[00:04:16] business. The wiring never disappeared.
[00:04:19] It got reused. The technology was real.
[00:04:22] So, we did need it eventually. It just
[00:04:25] got built too early on too much borrowed
[00:04:28] money, on too much hype. So, when I look
[00:04:30] at AI right now, I'm not thinking about
[00:04:32] valuations and share prices. I'm
[00:04:34] thinking about the layer underneath, the
[00:04:36] technology itself. And more importantly,
[00:04:39] who owns it?
[00:04:42] So, let's talk about that lower layer,
[00:04:44] the technology, the infrastructure.
[00:04:46] Because if you swap fiber optic cables
[00:04:47] with GPUs, you start to see the
[00:04:49] symmetries. This year alone, big tech
[00:04:52] are pouring something like $700 billion
[00:04:54] into AI data centers and chips. Amazon
[00:04:57] is investing like $200 billion, then
[00:04:58] Microsoft, then you got Google, then you
[00:05:00] got Meta, building as fast as they
[00:05:03] physically can. It's the same belief as
[00:05:05] last time. Everyone thinks we're going
[00:05:07] to need an infinite amount of AI
[00:05:09] compute. And maybe we will
[00:05:12] eventually, but nowhere near as fast as
[00:05:14] they're building for. Every big
[00:05:16] technology gets ahead of itself like
[00:05:18] this. The internet looked unstoppable in
[00:05:21] the night in 1999. Then it took like 20
[00:05:23] years until smartphones, social media,
[00:05:26] cloud software arrived before it really
[00:05:28] paid off. I think AI is the same. The
[00:05:30] demand for it will come, just not at the
[00:05:32] speed that we're betting on.
[00:05:35] But forget about the data centers for a
[00:05:36] second. Let's talk about the companies
[00:05:37] that we're actually working with,
[00:05:39] because that's the part that actually
[00:05:40] matters to us. These big AI companies,
[00:05:43] the models that we plug our business
[00:05:44] into, you know, the ones behind Cursor,
[00:05:46] Copilot, Claude Code, the models we API
[00:05:48] into, most of them lose money.
[00:05:51] A lot of money. Not investing for growth
[00:05:54] money. They're hemorrhaging cash. Take
[00:05:57] XAI, Elon's AI company, now part of
[00:05:59] SpaceX. Last year, back in 2025, it was
[00:06:02] reportedly burning through a billion
[00:06:04] dollars a month.
[00:06:05] A billion. Every single month.
[00:06:08] Now, to be fair, that's a bit different
[00:06:11] today since SpaceX merger, now they've
[00:06:14] uh started renting their data centers
[00:06:15] out. So, it's one Anthropic and Google.
[00:06:17] Uh so, there's real money coming in now,
[00:06:19] not just pouring out. But still, these
[00:06:21] are tremendous numbers either way.
[00:06:23] OpenAI, by their own projections, is on
[00:06:25] track to lose something like 14 billion
[00:06:27] this year. And Anthropic, the only one
[00:06:30] that's close to profit, is forecasting
[00:06:32] its first ever profitable quarter for Q2
[00:06:35] this year. But it's already told
[00:06:36] investors that it doesn't expect it to
[00:06:38] last. And there's something else going
[00:06:40] on with all this money. Something that's
[00:06:41] making me a little bit uncomfortable.
[00:06:43] Most of the money is just going around
[00:06:45] in circles. Nvidia promised a hundred
[00:06:48] billion dollars to OpenAI. But then
[00:06:50] OpenAI is going to spend that money on
[00:06:52] Nvidia chips. Nvidia then books that
[00:06:54] income as sales, making their stock go
[00:06:56] up so they can invest even more. And
[00:06:58] it's not just Nvidia and OpenAI, they're
[00:07:00] all at it, investing in each other, then
[00:07:02] using the money to buy from each other.
[00:07:04] It props everyone's numbers up. It makes
[00:07:07] the whole thing look like they're way
[00:07:09] healthier than it actually is. And we
[00:07:10] saw something similar happen in the
[00:07:12] dot-com bubble. The companies making the
[00:07:14] kit, uh like Cisco, would lend the
[00:07:17] telecoms carriers money to buy their
[00:07:19] equipment. Cisco still exists today, but
[00:07:23] don't know about the others. So, the
[00:07:24] question I'm asking myself is, why now?
[00:07:27] Why go public now when private money has
[00:07:29] been flowing to them like there's no
[00:07:30] tomorrow? It's because they need more, a
[00:07:33] lot more. And the biggest pot left is
[00:07:36] public money, money from people like you
[00:07:38] and me, our index funds, our pensions.
[00:07:41] So, what does that tell you? You know,
[00:07:42] when a bunch of private companies
[00:07:44] suddenly come to you asking for money at
[00:07:45] the same time, it tells you something
[00:07:47] about market momentum. It tells you
[00:07:49] about how something about how stable
[00:07:50] these companies really are. I was this
[00:07:52] guy speaking to Bloomberg the other day.
[00:07:54] I think his name is Ed Zitron. He runs a
[00:07:56] tech PR company and he got a He's
[00:07:58] basically got a famous newsletter and a
[00:08:00] podcast that he runs where he talks
[00:08:01] about he pulls finances apart for these
[00:08:04] AI companies. And his view is that these
[00:08:06] companies don't survive. Not that they
[00:08:09] go through a rough patch or something.
[00:08:11] No, they they don't make it. And he's
[00:08:13] even ripped apart Anthropic's one single
[00:08:15] profitable quarter projection. He said
[00:08:17] the numbers were manipulated to get
[00:08:18] there.
[00:08:19] Whether that's true or not, I don't
[00:08:21] know. But I will not stop using AI. I am
[00:08:24] embedded into this. I love using it. I
[00:08:26] use it every day. I'm like addicted to
[00:08:28] this stuff. But you don't have to listen
[00:08:30] to Ed to see that we have a real problem
[00:08:32] here. Once these companies are public,
[00:08:35] we'll get to see the real numbers of how
[00:08:36] much they're making. And I don't think
[00:08:38] we're going to like what we're going to
[00:08:39] see.
[00:08:40] Quick one before the next bit. If this
[00:08:42] is useful, hit like and subscribe. It
[00:08:43] really helps the channel further. So,
[00:08:46] here's the one thing that hits closest
[00:08:48] to home.
[00:08:49] The price you're paying for AI today
[00:08:51] isn't real.
[00:08:53] The price per token keeps dropping,
[00:08:55] sure. But they're selling it to you for
[00:08:57] less than it cost them to run it. Sam
[00:08:59] Altman said they're losing money even on
[00:09:01] their $200 a month plan. Anthropic said
[00:09:04] that people on his $200 a month plan
[00:09:07] were actually using a thousand dollars
[00:09:09] worth of usage a day.
[00:09:11] A day. They had to bring in new limits
[00:09:13] just to slow them down. And if you build
[00:09:15] software, you've probably had this thing
[00:09:17] where you're using your coding on Claude
[00:09:19] code or something and you get a
[00:09:20] notification saying you run out of
[00:09:22] tokens or you're you're
[00:09:24] or you need to upgrade your plan. It's
[00:09:26] so annoying, but you know exactly what I
[00:09:27] mean. So whatever you're paying for AI
[00:09:29] right now, it's a fraction of what it
[00:09:32] actually costs. Their investors are
[00:09:34] covering the rest.
[00:09:35] And even as the price of tokens drops,
[00:09:37] your bill will keep on going up because
[00:09:39] you keep using more. But one day the
[00:09:42] discount will end. The investors who've
[00:09:44] been funding this all along will want
[00:09:46] their money back with interest. And that
[00:09:49] money will inevitably be added to your
[00:09:50] bill.
[00:09:53] So what do you actually do about it? I
[00:09:55] want to be straight with you. I'm not
[00:09:56] some local AI guru that's quit the
[00:09:58] cloud. I I I live in this stuff. I use
[00:10:00] it every day. I'm probably more
[00:10:01] dependent on it than you are. So I'm not
[00:10:03] telling you to rip it all out. That's
[00:10:05] what I'm saying is much simpler. Don't
[00:10:07] be a hostage. I was speaking to a CEO of
[00:10:09] an AI agency earlier this week and he
[00:10:11] put it perfectly. He said, "I want a
[00:10:14] backup plan before I need one." So what
[00:10:17] does that even look like? For me, it's
[00:10:19] three things. One, don't anchor your
[00:10:22] whole business on a single provider.
[00:10:24] Build it so you can switch. So if one of
[00:10:26] them doubles their prices or isn't
[00:10:27] available anymore, you can simply switch
[00:10:29] to the next one available. Two, know
[00:10:32] exactly how much you're using and what
[00:10:34] it actually costs, the real cost, not
[00:10:36] the subsidized one because if your
[00:10:38] business is running on a subsidized
[00:10:40] cost, you don't really have a business,
[00:10:42] you have a discount. And three, run it
[00:10:45] locally whenever you can, on your own
[00:10:47] kit. And this is actually one we
[00:10:48] followed from day one with Alati. Alati
[00:10:50] is our business phone system product.
[00:10:52] And every phone call that goes through
[00:10:54] the platform gets transcribed and
[00:10:56] summarized, but we don't ship that off
[00:10:58] to a big cloud model. We run it on open
[00:11:00] source models in our data centers. And
[00:11:01] I'll tell you why.
[00:11:03] It's not some grand philosophical
[00:11:05] reason. It's down to money. Sending
[00:11:07] every call off to a state-of-the-art
[00:11:09] model costs a fortune and customers
[00:11:11] expect this kind of stuff for free now.
[00:11:13] So local was the only way we could make
[00:11:15] it work. But that actually turned out to
[00:11:16] be a great hedge because it doesn't
[00:11:17] matter what the AI companies charge us
[00:11:19] next month, our core AI services will
[00:11:22] still keep on working. And there's also
[00:11:24] another reason why people are running
[00:11:25] local AI and it's got nothing to do with
[00:11:27] cost. It's privacy. A lot of people
[00:11:29] don't want to hand over their data or
[00:11:31] their customers' data to one of these
[00:11:32] big AI companies. And that's a valid
[00:11:34] concern. When you run it yourself, your
[00:11:36] data doesn't have to leave your network.
[00:11:38] But here's the bigger picture. This
[00:11:40] whole build-out is a giant bet. A bet
[00:11:43] that future AI lives in a data center
[00:11:46] that's miles away from you. I'm not sure
[00:11:49] it does. I think more and more of it
[00:11:50] ends up running right here on your
[00:11:52] phone, or in a little box in the corner
[00:11:54] of your office. And I'm not the only guy
[00:11:56] thinking this. It's actually the bet
[00:11:57] that Apple's making. Do everyday stuff
[00:12:00] on the device, and then hand over what's
[00:12:02] more powerful and needs more more power
[00:12:04] to the cloud. Now, to be clear, I'm not
[00:12:06] betting my whole company on local AI,
[00:12:08] but there's definitely a place for it.
[00:12:10] And we're going local as much as we can.
[00:12:14] So, let me bring all this together. This
[00:12:16] week, SpaceX goes public in the biggest
[00:12:18] IPO in history. And two of the biggest
[00:12:21] names in AI right now, Anthropic and
[00:12:23] OpenAI, which are both still losing
[00:12:25] money, have just filed to do the same.
[00:12:28] Whether that's the start, the top, or
[00:12:31] the beginning of the pop, who knows. But
[00:12:33] here's what I do know. Most of us have
[00:12:35] already built AI into our business, or
[00:12:37] we're in the process of doing it. Which
[00:12:39] means that we're building on top of
[00:12:40] these companies' products. And if one of
[00:12:42] them fails,
[00:12:44] it won't fail alone. It will drag
[00:12:46] everyone who built on top of their
[00:12:47] products with them, people like us. So,
[00:12:50] I'm not trying to time the market. I
[00:12:52] just want to make sure that if the
[00:12:53] prices rise exponentially, or one of
[00:12:56] these companies has a wobble, my
[00:12:58] businesses don't go down with it. That's
[00:13:01] why local AI is important. That's why we
[00:13:04] need a backup plan. So, if this
[00:13:05] resonated, hit like and subscribe. It
[00:13:07] really helps. And if you want more, head
[00:13:09] over to accentmalice.com and join my
[00:13:11] free newsletter. Once a week, I write
[00:13:13] about what's actually working inside my
[00:13:15] companies and what is not. And remember
[00:13:17] one thing, the technology always
[00:13:20] survives. The people who bet everything
[00:13:22] on owning it normally don't. So, I'm not
[00:13:25] trying to own the future of AI. I just
[00:13:28] want to make sure I'm still standing
[00:13:30] when the bubble pops, and I'm able to
[00:13:32] build on whatever it leaves behind.
[00:13:35] See you in the next one.
