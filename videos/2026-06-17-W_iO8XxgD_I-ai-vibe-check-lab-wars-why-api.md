---
video_id: W_iO8XxgD_I
title: "AI Vibe Check: Lab Wars, Why APIs Might Vanish & Future Predictions"
channel: "Unsupervised Learning: With Jacob Effron"
url: "https://www.youtube.com/watch?v=W_iO8XxgD_I"
watched_date: 2026-06-17
watched_at: "2026-06-17T12:00:00Z"
watch_count: 1
duration_seconds: 3996
source: youtube-history-browser
added_date: 
history_label: Jun 17
history_order: 100
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 400
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

# Summary

The episode features Ari (ex-DeepMind/Meta, now at Datlogy) and Rob (Radical VC) discussing major AI trends over the past six months. Key topics include: coding agents now working effectively at longer time horizons and driving massive token consumption; the shift from open-source to proprietary models as Meta and Chinese labs close their frontier models behind APIs for economic reasons; the collapse of open-source AI as a viable business model without recurring revenue; OpenAI losing momentum to Anthropic, with Rob's earlier prediction of Sam Altman being replaced looking increasingly plausible by June; Anthropic's silent limitations on Fable for AI development work (seen as competitive positioning rather than safety); and the debate over whether SaaS applications are truly doomed—consensus suggests they're not, though many categories face existential pressure from labs' direct competition.

**For users:** Cost optimization is urgent—frontier models like Opus now have expensive token outputs, making smaller open models with good scaffolding/harnesses viable alternatives for many tasks. If building AI products, focus on vertical niches where you have domain expertise labs lack, not horizontal generalist categories labs dominate. Don't assume open-source models will remain available long-term; plan for proprietary dependencies and consider building or licensing your own models. The real innovation isn't just in models but in the "harness layer"—how you structure, scaffold, and orchestrate model usage—which remains competitive territory for startups.

## Transcript

[00:00:00] I'm Jacob Efron and this is Unsupervised
[00:00:02] Learning. We've had a bunch of new
[00:00:03] subscribers, uh, over our last few
[00:00:05] months. And so, uh, wanted to welcome
[00:00:08] you to the show. We basically probe the
[00:00:10] sharpest minds in AI on everything
[00:00:12] that's happening today, what's real, and
[00:00:14] what's coming up, where the space is
[00:00:16] headed. And today's episode is one of my
[00:00:18] favorite formats we do. It's an AI vibe
[00:00:20] check uh, that we do with Ahri from
[00:00:22] Datlogy. Ari was a former researcher at
[00:00:24] DeepMind and Meta now runs a really
[00:00:25] exciting AI startup and Rob at Radical
[00:00:28] uh one of the great AI venture firms.
[00:00:30] The three of us talk about everything
[00:00:31] happening in the AI world today. We
[00:00:33] talked about Fable of course uh and the
[00:00:35] reaction around the release as well as
[00:00:36] model capabilities. We talked about how
[00:00:38] close we are to RSI. We hit on some
[00:00:40] pretty spicy predictions uh including
[00:00:42] that the labs may actually get rid of
[00:00:44] their API business as the compute crunch
[00:00:46] continues. Uh and we just got to hit on
[00:00:48] all the main topics of today. Uh just
[00:00:50] really fun to sit down with two friends
[00:00:52] and and great minds in AI. I think folks
[00:00:54] really enjoy this. Without further ado,
[00:00:56] here's our conversation.
[00:00:59] It's time for another roundup episode. I
[00:01:01] always love doing this with you guys,
[00:01:02] Ari and Rob. Uh I feel like we had a ton
[00:01:05] of fun in the last one, but like god
[00:01:07] it's AI world. Things have changed. Uh I
[00:01:09] feel like we we last sat down after
[00:01:10] Nurups and I think since then we've had
[00:01:12] IPO filings. We've had you know uh
[00:01:14] models not launched and then launched.
[00:01:16] We've had uh you know SpaceX becoming an
[00:01:18] AI info company. Uh no shortage of
[00:01:21] headlines to uh to discuss here. So
[00:01:22] excited to have you both back on the
[00:01:24] show.
[00:01:24] >> Excited to be here.
[00:01:25] >> Yeah, thanks for having us.
[00:01:26] >> So I I I think to kick it off uh you
[00:01:29] know 6 months is an eternity in AI
[00:01:30] world, but I figured I'd start at the
[00:01:32] highest level. Uh what's like the single
[00:01:34] biggest thing that has changed in how
[00:01:36] you're thinking about the landscape
[00:01:37] since we last talked? And maybe uh Ari,
[00:01:39] I'll start with you. Yeah, I mean I
[00:01:41] think the the most obvious thing that
[00:01:42] has changed uh over the last six months
[00:01:44] is starting to see the coding agents
[00:01:45] really start to work at longer time
[00:01:47] horizons. Um right I think that was just
[00:01:49] starting when we recorded our last
[00:01:51] episode at the end of uh 25.
[00:01:53] >> Feel like everyone went away over
[00:01:54] Christmas break and was like holy crap
[00:01:56] like these things really work.
[00:01:58] >> Yeah. And and I think it it starts to
[00:02:00] show how there are these thresholds
[00:02:02] where if you go beyond a threshold it
[00:02:04] can become a lot more valuable. Um, and
[00:02:06] obviously that's driven the the massive
[00:02:08] rise in in token spending and the whole
[00:02:10] token maxing idea and and all this
[00:02:12] stuff. Um, but I think we're really
[00:02:14] starting to now see the shift of
[00:02:16] engineers at least kind of almost all
[00:02:19] moving from IC's to managers of agents.
[00:02:21] Um that's been something that's been
[00:02:23] very noticeable within Datlogy for
[00:02:25] example um over the last uh number of
[00:02:27] months is seeing more and more people
[00:02:29] starting to now context switch between
[00:02:30] managing different agents uh rather than
[00:02:32] just kind of you know working on the one
[00:02:33] thing and that was enabled by having
[00:02:35] these um you know agents be able to run
[00:02:37] long enough and actually be useful in
[00:02:39] various ways.
[00:02:39] >> I mean everyone likes to ask top AI
[00:02:41] researchers like yourself like how much
[00:02:42] more productive has it made you in your
[00:02:44] uh in your work. I think that it's
[00:02:45] interesting. It makes you a lot more
[00:02:46] productive in some ways, right? But it
[00:02:48] also um produces a lot of challenges as
[00:02:50] well. Like one of the things that we're
[00:02:51] struggling with is now um it's a lot
[00:02:53] easier to produce a massive amount of
[00:02:56] code that can do something, but now you
[00:02:58] have this pretty massive understanding
[00:02:59] gap and it's a lot easier to put slop uh
[00:03:01] into your codebase. So it's definitely
[00:03:04] made um made us more productive. I think
[00:03:06] a lot of times though the kind of
[00:03:07] topline numbers tend to be overestimated
[00:03:10] um because it doesn't take into account
[00:03:12] some of these like later costs of like
[00:03:14] we now have big bottlenecks on reviews
[00:03:16] um and we don't want to go fully to like
[00:03:18] oh you just like but my agent will
[00:03:19] review your agent's output you know the
[00:03:21] bottlenecks just seem to shift um you
[00:03:23] know whatever uh it's hard to improve on
[00:03:26] an entire process uh because of because
[00:03:28] of that. What about you Rob? There are
[00:03:29] early signs that seem to suggest over
[00:03:32] the past six months that that make me
[00:03:34] question whether openweight AI is going
[00:03:37] to continue to be a really meaningful uh
[00:03:40] force in the ecosystem going for at
[00:03:42] least like near frontier
[00:03:43] >> opening for the jugular feri like right
[00:03:46] off the uh right off the top here. I
[00:03:47] like it.
[00:03:48] >> There's Yeah. Yeah, we can we can dig in
[00:03:50] more detail, but I think like Yeah. six
[00:03:53] months ago or for the past few years,
[00:03:54] like my kind of working assumption had
[00:03:56] been that the closed source proprietary
[00:04:00] models would advance the frontier and
[00:04:01] there are a lot of structural reasons
[00:04:02] for that. But the open frontier would is
[00:04:05] only would only be a few months behind.
[00:04:08] Uh and that gap might widen a little
[00:04:10] bit. I didn't think it would shrink
[00:04:12] altogether, but like I thought it would
[00:04:13] persist as as being relatively small.
[00:04:15] And I think there are signs now that
[00:04:17] like there it seems like there's a real
[00:04:19] risk of of near frontier openweight AI
[00:04:22] falling off altogether. Um I think meta
[00:04:25] which historically has been the the the
[00:04:28] openw weight champion in the west is is
[00:04:31] pulling back and it see it seems likely
[00:04:33] that they're not going to continue with
[00:04:34] their open source strategy. And then
[00:04:37] more recently, obviously, the Chinese
[00:04:39] labs have been the ones driving
[00:04:41] state-of-the-art open research. And
[00:04:42] there it seems like there's strong
[00:04:44] indications that they may also be
[00:04:45] pulling back from that. And they're uh
[00:04:48] you know, whether it's Quen or Deepseek
[00:04:50] um or uh or others their most high
[00:04:54] performing models, they're now keeping
[00:04:56] proprietary behind an API and just open
[00:04:58] open sourcing, open waiting, you know,
[00:05:00] smaller, less performant versions. And I
[00:05:03] think there's like real compute
[00:05:04] incentives behind that. like it's just
[00:05:06] very expensive to to uh service these
[00:05:10] open way models with no revenue coming
[00:05:11] in. Uh and I think there's also
[00:05:13] geopolitical and and competitive
[00:05:15] considerations. But it's interesting to
[00:05:17] contemplate what a world might look like
[00:05:19] where like if you want real frontier
[00:05:22] artificial intelligence like you have to
[00:05:23] pay a company for a proprietary model as
[00:05:26] opposed to being able to you know have
[00:05:28] access to the weights yourself
[00:05:30] >> or or build your own. Uh but I I'd
[00:05:34] actually agree with that. I the second
[00:05:36] one this other one I was imaging about
[00:05:39] as a you know what changed I don't think
[00:05:41] that we've seen a major change in in the
[00:05:43] capabilities or the trend line of the
[00:05:44] capabilities of the open weight models.
[00:05:46] Um I actually think if anything we
[00:05:48] started to converge and we continue to
[00:05:49] see that. Um I do think though the
[00:05:52] economic decision-m around building and
[00:05:54] releasing open models has definitely
[00:05:56] changed um over the last uh six months
[00:05:58] which I think is what Rob was really
[00:06:00] getting at. Um, and I I am a lot more
[00:06:02] bearish on how many open models there
[00:06:04] will be going forward. It seemed like,
[00:06:07] you know, there was uh this kind of
[00:06:09] cornucopia of open models that was only
[00:06:11] ever growing in 2025. And I think we're
[00:06:13] now definitely starting to see that we
[00:06:15] probably hit the peak number of open
[00:06:17] models and it's now going to kind of get
[00:06:19] less and less. And because the financial
[00:06:21] incentives just don't make sense once
[00:06:23] you've already kind of achieved
[00:06:25] credibility, it makes sense to invest a
[00:06:26] lot of money to do that. But after that
[00:06:28] point, you want to start selling hosted
[00:06:29] inference of your model. Um, and opening
[00:06:32] it up just fully undermines your
[00:06:34] business, which so I I so I think we're
[00:06:35] are going to see like other Chinese labs
[00:06:37] start with like big open models, but
[00:06:39] then probably close up after that once
[00:06:41] they've kind of gotten enough press and
[00:06:42] PR. Is there a business model for an
[00:06:44] open source model company or is it
[00:06:45] literally just it's marketing uh to, you
[00:06:48] know, to as you're on your way to the
[00:06:49] frontier and then once you're once
[00:06:51] you're kind of close, uh, it makes it
[00:06:53] inevitable to want to go close source? I
[00:06:55] don't think there's a business model
[00:06:56] honestly. Uh there you know different
[00:06:58] things have been tried the kind of like
[00:07:00] premium enterprised like uh you know Red
[00:07:04] Hat um model but I just I don't think
[00:07:07] that it it works in AI given the just
[00:07:11] the massive upfront investment required
[00:07:13] to to get to the frontier close to the
[00:07:15] frontier in the first place. We'll see
[00:07:16] what I like uh you know we can come back
[00:07:18] and revisit this soon but I I very
[00:07:21] curious to see if you know first of all
[00:07:23] if reflection when reflection releases a
[00:07:25] model and uh what business model they
[00:07:28] aim to pursue with it. Um but I yeah I
[00:07:32] remain skeptical that like a great
[00:07:33] business model exists for open AI open
[00:07:36] source AI. It's funny because I was
[00:07:38] going to say one of the one of the
[00:07:38] trends we've actually seen happen you
[00:07:40] know in in the past like month or two is
[00:07:42] that it finally you know forever I think
[00:07:43] people have been like everyone will use
[00:07:45] smaller cheaper open source models for
[00:07:46] tasks that those models can do and uh
[00:07:48] you know it felt like the vast majority
[00:07:50] of usage and tokens was still just like
[00:07:52] at the frontier pushing capabilities
[00:07:54] like figure out what you know models can
[00:07:56] do in different industries and then
[00:07:57] finally I feel like we have a movement
[00:07:59] now toward like gez these bills are
[00:08:01] pretty expensive uh or our usage is
[00:08:03] pretty high like wouldn't it be nice to
[00:08:05] to have something that was that is, you
[00:08:07] know, cheaper and and faster and smaller
[00:08:08] to use. Uh, but it's funny that it's
[00:08:10] happening at the same time that we're
[00:08:12] kind of seeing this real uh, you know,
[00:08:14] the closed source models, you know, run
[00:08:15] ahead of of of open source models. And
[00:08:17] Ari, I know you spend a lot of time
[00:08:18] thinking about this stuff, like how do
[00:08:20] we think about those like
[00:08:21] counterveailing forces that seem to be
[00:08:22] happening at the same time? Yeah, I I
[00:08:24] mean I think that first off I I've
[00:08:26] definitely seen a lot of the the former
[00:08:28] that you were talking about. Like it's
[00:08:29] been very interesting um the combination
[00:08:33] of the you know extreme computed
[00:08:35] environments that we're operating in. um
[00:08:37] the rise of capabilities of uh the
[00:08:40] coding models in particular um and then
[00:08:43] even just seeing you know from release
[00:08:45] to release models changing their token
[00:08:46] efficiency their output token
[00:08:48] efficiencies um has resulted in you know
[00:08:51] a lot of companies that were happy using
[00:08:54] Frontier models all of a sudden even
[00:08:56] just going from like Opus 46 to 47 there
[00:08:58] was a big difference in token efficiency
[00:09:00] um and a lot of people's bills just
[00:09:01] doubled overnight and you've now I'm now
[00:09:04] starting to see talking to a lot of
[00:09:06] enterprises in particular
[00:09:07] really strong desires to start cutting
[00:09:09] the cost of of using the models. Um, and
[00:09:12] I think that wasn't there nearly uh to
[00:09:14] the same extent a year ago um because
[00:09:17] the models weren't being used at a scale
[00:09:19] where those costs were you know
[00:09:20] meaningful enough but now they've really
[00:09:22] reached that point where they are
[00:09:23] meaningfully meaningful enough um and
[00:09:25] you can just consume budgets so quickly
[00:09:26] because the models think for a long time
[00:09:28] um and that's now driving a lot of
[00:09:30] demand to say okay how can we make this
[00:09:33] much cheaper. I think that you can do a
[00:09:35] lot of that with open models as well.
[00:09:36] Like like I think one very notable thing
[00:09:38] right is that like a lot of people were
[00:09:40] able to reproduce um the same or similar
[00:09:43] level of kind of you know vulnerability
[00:09:45] finding um that mythos used with open
[00:09:48] models by just putting scaffoldings
[00:09:49] around. I think that's another one of
[00:09:50] the big changes right is that a model is
[00:09:52] not just a model anymore it's the model
[00:09:54] combined with the harness and the
[00:09:56] scaffolding and a lot of innovation is
[00:09:58] happening on the harness and scaffolding
[00:09:59] layer. I think that's also possibly how
[00:10:01] open source models can have a business
[00:10:02] model. you open source the model, you
[00:10:04] don't open source the scaffolding in the
[00:10:05] harness. Um, and you, you know, then
[00:10:07] have an API where people can access the
[00:10:09] full system. Um, I think that could
[00:10:11] potentially work. Kimmyy's kind of doing
[00:10:13] that, right? Like moonshot, I think, is
[00:10:14] is at a couple hundred mill through the
[00:10:16] the API and and kind of the chat
[00:10:18] interface. Um, and that's to some extent
[00:10:20] what they're doing. Um, so I think that
[00:10:22] we will continue to see strong um, open
[00:10:24] models. Um, but probably fewer and
[00:10:27] fewer. Um, and I think that, you know,
[00:10:29] this is going to motivate a lot of folks
[00:10:31] where they, you know, they have to now
[00:10:33] think, how do we survive in an era where
[00:10:36] there aren't going to be reliable open
[00:10:38] models? Um, and I think that pushes
[00:10:40] people more and more towards actually
[00:10:41] starting to think about, okay, how do I
[00:10:42] make sure I have the capability to build
[00:10:44] a model um, in some way to maintain a
[00:10:46] model to do that repeatably. Um, I think
[00:10:48] that's a huge part of the reason that
[00:10:49] Nvidia has been pushing so hard through
[00:10:51] reflection and others, right, to uh,
[00:10:53] have open model providers in the west.
[00:10:55] >> Yeah. I mean certainly like the more
[00:10:57] model providers the marrier for uh for
[00:10:58] them. Um and it's interesting. I mean it
[00:11:00] kind of almost feels like uh you know
[00:11:02] you saw an early manifestation of this
[00:11:03] with meta right where it's like early on
[00:11:05] you know they you know the idea of
[00:11:06] having this controlled by a bunch of
[00:11:08] companies that weren't them was was kind
[00:11:09] of like it you know would never work for
[00:11:11] them as a business. And so it's like we
[00:11:12] have to have something here to be
[00:11:14] competitive even if we're not going to
[00:11:15] be you know uh the leading model
[00:11:17] provider just for our own business. Like
[00:11:19] we want to have something that uh that
[00:11:20] that we can use ourselves. If you are
[00:11:22] one of these companies that's, you know,
[00:11:24] potentially threatened by this, you kind
[00:11:25] of have two options. Like option one is
[00:11:27] that you uh go and work with a frontier
[00:11:30] model provider. You share your data and
[00:11:31] your domain expertise with them. They
[00:11:33] use that to improve the model with you.
[00:11:35] Maybe you're able to sign some agreement
[00:11:37] that gives you some long-term certainty
[00:11:39] uh around that, but eventually they just
[00:11:40] out compete you uh because you've given
[00:11:42] up, you know, any of your proprietary
[00:11:43] advantages. The only other option is
[00:11:45] that you try to really compete on the
[00:11:47] niche that is your focus and where you
[00:11:49] have uh you know, unique capabilities.
[00:11:51] Um, and I think we're starting to see
[00:11:52] that across the board, right? Look at
[00:11:53] what's happened with cursor. Look what
[00:11:54] happened with lots of other folks where
[00:11:56] they're realizing, okay, we have to kind
[00:11:57] of move away from this. Um, there's also
[00:12:00] a margin perspective from that as well,
[00:12:02] right? Where just like fundamentally if
[00:12:03] you're competing against somebody who
[00:12:04] has better margin than you do, um, then
[00:12:07] it's very hard to win.
[00:12:08] >> Yes. They will always give themselves
[00:12:09] better rates than they give you, uh, as
[00:12:11] a as an app company on top. Rob, what
[00:12:13] was your whole reaction to the, you
[00:12:15] know, the apps are cooked and and SAS
[00:12:16] apocalypse uh, you know, narrative of
[00:12:18] the past months?
[00:12:19] >> Yeah, that's interesting. I think like
[00:12:22] market narratives have a way of like
[00:12:24] swinging so far in one direction or the
[00:12:27] other to the to the extent that a lot of
[00:12:29] the nuance is lost. So I do think like a
[00:12:31] couple things are true simultaneously.
[00:12:32] Like I I do think a lot of traditional
[00:12:35] software companies and even categories
[00:12:38] potentially are at real existential risk
[00:12:41] on account of the frontier labs and
[00:12:43] their and their product road maps. And
[00:12:45] so I think like a lot of that rerating
[00:12:48] was rational. Um, and there I think
[00:12:50] there are a lot of big companies that
[00:12:52] have big revenues and big customer bases
[00:12:54] that are in real trouble based on how
[00:12:56] OpenAI and Anthropic are executing and
[00:12:59] performing. I also think it like for
[00:13:01] sure was an overreaction and an oversell
[00:13:03] and like painted with too broad of a
[00:13:05] brush. Um, and I think like you know in
[00:13:08] our field of venture capital uh it
[00:13:11] certainly is like the the kind of
[00:13:14] prevailing narrative is apps are so
[00:13:17] challenging to invest in. stay away from
[00:13:19] them. Like deep tech and hardware and so
[00:13:21] forth have all become more appealing and
[00:13:23] consensus over the past few months. And
[00:13:26] again, I think there's a lot there's a
[00:13:27] lot that's real there and there are a
[00:13:28] lot of deep tech categories that I'm
[00:13:30] super excited about that we're both
[00:13:31] investing in that I'm sure we'll talk
[00:13:32] about. But I also think there are still
[00:13:34] I think just fundamentally there's no
[00:13:37] way that one or two or three companies
[00:13:40] will win every single important market
[00:13:43] and and important category in the world.
[00:13:45] just no no no company can have that span
[00:13:47] of influence and execute excellently so
[00:13:49] broadly. So for sure there are some
[00:13:52] categories that I think uh open I would
[00:13:54] bet on open eye and anthropic being very
[00:13:56] well positioned in coding obviously is
[00:13:58] the first and there are others which we
[00:13:59] can talk through. Um, and I think that
[00:14:02] that these sort of like horizontal
[00:14:04] crosscutting areas are the ones that
[00:14:06] make the most sense for the labs to
[00:14:08] focus on and go after versus like, you
[00:14:11] know, vertical software for pet stores
[00:14:14] or something like this.
[00:14:16] >> I I do wonder if like VCs are just, you
[00:14:17] know, pushing themselves into a corner
[00:14:18] of like damned if you do, damned if you
[00:14:20] don't. If if you're like if you're only
[00:14:21] going to go invest in, you know, pet
[00:14:23] stores because like that's small enough
[00:14:24] for the models, like I don't know if
[00:14:26] that actually ends up being a super
[00:14:27] interesting end category, right? But it
[00:14:29] turns out no matter anywhere you look in
[00:14:31] AI world there are existential CL you
[00:14:33] can't avoid them like there's no there's
[00:14:34] no just like I mean maybe if you want to
[00:14:36] go invest in like a data center builder
[00:14:37] and you're like they will just build
[00:14:39] data centers and there will be demand
[00:14:41] like but sure then you still have to
[00:14:42] figure out like you know how what makes
[00:14:44] you a better data center builder than
[00:14:45] the other 10 people that will compete
[00:14:46] with aggressive financing for the same
[00:14:48] site. There's no question that we are at
[00:14:49] a at a period of max uncertainty and
[00:14:52] volatility and yeah I I mean I totally
[00:14:54] agree with you on the on the hard tech
[00:14:55] point like it it there again I I I do
[00:14:58] believe there are a lot of really
[00:15:00] exciting opportunities in categories in
[00:15:03] hardware and deep tech where there's a
[00:15:04] lot of interesting innovation happening
[00:15:05] right now. Yeah, to your point, it turns
[00:15:07] out hard tech is also very very hard and
[00:15:10] like the failure rates are much higher
[00:15:12] and there's a lot of unsolved problems
[00:15:13] and like that there's going to be a lot
[00:15:15] of I think pain and lost money down that
[00:15:17] road in the years to come. Um, and then
[00:15:20] yeah, on the application side, I think
[00:15:22] as you said, like I I think there's
[00:15:24] there's still tremendous value in that
[00:15:26] last mile and like the labs are also
[00:15:29] starting to try to tool up and stand up
[00:15:31] these deploy codes and and lean in on
[00:15:33] the implementation side. But I think
[00:15:35] there will be so many pockets and
[00:15:36] opportunities for companies that are
[00:15:39] delivering applications to also thrive
[00:15:41] and continue to grow.
[00:15:43] >> I think also it's interesting to like
[00:15:44] like ultimately why does startups ever
[00:15:46] win, right? like why didn't why didn't
[00:15:47] Google do everything right um it's hard
[00:15:50] for a a massive company to do many
[00:15:53] different things well fundamentally like
[00:15:55] you know a counterargument to this is
[00:15:57] actually like open AAI shuttering uh or
[00:16:00] suspending their video efforts right um
[00:16:03] like that was very surprising to me I
[00:16:05] will say uh given their access to
[00:16:07] effectively infinite capital um given
[00:16:10] the and effectively you know infinite
[00:16:12] talent and they had a great team there
[00:16:14] um that was leading that like but they
[00:16:17] they had to make the hard choices here.
[00:16:19] Um now some of that a lot of that is
[00:16:21] likely driven by compute constraints
[00:16:22] fundamentally. Video training is very
[00:16:23] expensive relative to text training and
[00:16:25] so on. Um but it it goes to show that
[00:16:29] they can't do everything.
[00:16:31] >> They needed to focus and and strip down
[00:16:33] and just focus on acquiring TBPN and
[00:16:35] adding that to the company.
[00:16:37] >> I I heard actually it was that they they
[00:16:39] had listened to our last episode and
[00:16:40] read your article and they were like,
[00:16:41] "Oh, Rob's predicting Sam's out. like
[00:16:43] this is uh this is really uh you know
[00:16:46] that that that spicy prediction has
[00:16:47] gotten to our hearts. We really need to
[00:16:49] make sure we uh we avoid that. How how
[00:16:51] you feeling about that one 6 months into
[00:16:53] the year? I guess you got six months
[00:16:54] still to be right.
[00:16:54] >> It's looking a lot more likely today on
[00:16:57] June, you know, mid June than it was
[00:16:59] when I shared it with you guys. Uh it's
[00:17:01] been interest. Yeah, I mean when I yeah
[00:17:03] when I when I unveiled that prediction
[00:17:04] in December, I feel like everyone was
[00:17:06] like what are you talking about? That
[00:17:07] makes no sense. Including you guys. You
[00:17:08] were like, oh that's interesting, but
[00:17:09] that doesn't seem very likely. And yeah,
[00:17:12] I mean like you know, needless to say,
[00:17:14] like the vibes have shifted against
[00:17:16] OpenAI this year and there's been this
[00:17:19] realization whereas this time last year
[00:17:21] was like, oh, OpenAI is doing
[00:17:22] everything. They're such an amazing
[00:17:23] company. They're going to win and chips
[00:17:25] and data centers and robots and
[00:17:26] everything. Now, I think now there's a
[00:17:28] realization like, oh, we really do need
[00:17:30] to focus. And I think there are a lot of
[00:17:32] elements of Sam's leadership that are
[00:17:33] increasingly under question. And I think
[00:17:35] that the Elon Musk trial, even though uh
[00:17:37] Elon Musk lost, I think that like was
[00:17:40] damaging of first Sam's reputation uh
[00:17:42] and his trustworthiness and so on and so
[00:17:44] forth. Uh so, you know, who knows? I
[00:17:47] like it was it was a provocative and
[00:17:49] like purposely somewhat low likelihood
[00:17:52] prediction at the beginning of the year.
[00:17:54] I I would say odds have gone up for
[00:17:55] sure. One thing that one thing that's
[00:17:57] changed is at the time that I made and I
[00:18:00] published that in Forbes like my my
[00:18:02] hypothesis was that Fiji was the obvious
[00:18:05] most likely successor and kind of was
[00:18:06] being groomed to be the next CEO. Um and
[00:18:10] she obviously has now had to take a step
[00:18:11] back given some health concerns and so
[00:18:14] uh I think that the question around who
[00:18:16] the successor would be is different.
[00:18:17] Like I I am actually like I think this
[00:18:20] theory which I'm heard you I'm sure you
[00:18:22] guys have heard made the round make the
[00:18:23] rounds around Brett Taylor I think is
[00:18:26] quite plausible. Um you know for folks
[00:18:28] who aren't familiar Brett is the
[00:18:30] chairman of the board at OpenAI the CEO
[00:18:31] of Sierra you know one of the most
[00:18:34] respected and revered leaders in Silicon
[00:18:36] Valley. Um and I like I think it would
[00:18:39] just honestly make so much sense for
[00:18:41] OpenAI to acquire Sierra and to make
[00:18:43] Brett the CEO. I think it I think it
[00:18:46] would be in the best interest of
[00:18:46] OpenAI's shareholders honestly and like
[00:18:49] to this discussion around uh the like
[00:18:52] the vibes have really shifted against
[00:18:53] OpenAI and towards Anthropic in the
[00:18:55] leadup to the IPO like that is a
[00:18:58] decisive change that I think could be
[00:18:59] like a total game changer for OpenAI
[00:19:01] because like people just trust Brett and
[00:19:04] respect him and admire him and think
[00:19:06] he's like an admirable leader and I
[00:19:08] think if someone like that was at the
[00:19:10] helm of OpenAI I think it would do a lot
[00:19:12] to change their fortune. So anyway,
[00:19:14] we'll see. There there are many months
[00:19:16] to go, but like I don't know. I'm I I
[00:19:18] feel like that one might actually come
[00:19:19] to fruition. We we'll see.
[00:19:20] >> I think also like the this notion of
[00:19:23] opening I going to like an alphabet like
[00:19:24] structure seems a lot more plausible uh
[00:19:27] in general now that like they they shift
[00:19:30] to a holding company. Maybe Sam stays
[00:19:32] CEO of the holding company and then you
[00:19:34] have somebody take over you know OpenAI
[00:19:36] or Chat maybe ChatgPT becomes uh its own
[00:19:38] product you know or or something to that
[00:19:40] effect. Uh that would make sense as
[00:19:43] well.
[00:19:44] >> Yeah. No, I mean you mentioned it, but
[00:19:45] obviously I feel like these past months
[00:19:47] the the dominant vibe. It's unbelievable
[00:19:49] to see Anthropic on this like
[00:19:51] unprecedented vibe run, right? I think
[00:19:53] they're, you know, uh they've they've
[00:19:55] kind of had uh just, you know,
[00:19:57] completely sucked up the oxygen.
[00:19:58] Probably the most consensus around one
[00:20:00] company we've we've had. Um and
[00:20:01] obviously that's come at the expense of
[00:20:02] of OpenAI in many ways. um you're maybe
[00:20:05] starting to see some some light cracks
[00:20:07] in that uh in this week with the with
[00:20:09] some of the reaction to the release of
[00:20:10] Fable, but I'm I'm curious for both of
[00:20:12] you like do you think this is a a vibes
[00:20:14] trend that continues or like many things
[00:20:17] in our culture, are we inevitably going
[00:20:19] to have some sort of backlash or or flip
[00:20:21] in in fortune of these two companies uh
[00:20:23] in in the next 3 six months?
[00:20:25] >> There'll definitely be some amount of
[00:20:26] backlash. There's always backlash to
[00:20:27] whoever's winning, right? That's that's
[00:20:29] just like a truism of life. Um, I would
[00:20:31] say, um, that said, I think, you know,
[00:20:35] Enthropic is is also potentially
[00:20:37] starting to to to make moves that will
[00:20:39] alienate people. Like I think clearly
[00:20:40] with limiting the use of Fable for
[00:20:43] anything to do with AI development. And
[00:20:44] I think in particular, I don't think
[00:20:46] people are incredibly upset at the core
[00:20:49] with just a limitation. It's the fact
[00:20:52] that it's a silent limitation. Yeah.
[00:20:54] That I think people are really upset
[00:20:56] about, right? That it doesn't give you a
[00:20:57] refusal. It doesn't say, "I'm not going
[00:20:59] to help you with this." it just does a
[00:21:00] poor job on that um without you knowing.
[00:21:04] Um
[00:21:06] they can say that's because of safety.
[00:21:07] That's
[00:21:09] tenuous. I would say it's it seems
[00:21:11] pretty clear that's a competitive
[00:21:12] positioning uh you know move rather than
[00:21:16] a safety move. Um you know and I think
[00:21:18] to that end like like I I think I
[00:21:20] mentioned earlier right that like a lot
[00:21:21] of people were able to find many of the
[00:21:23] same vulnerabilities in zero days that
[00:21:25] Methus found with open models and good
[00:21:28] harnesses. Um so so I also think there's
[00:21:30] not necessarily a unique safety risk um
[00:21:33] you know to to this um but but I've seen
[00:21:36] more people who have been incredibly
[00:21:39] bullish on anthropic and positive
[00:21:41] anthropic um truly pissed off uh as a
[00:21:44] result of of just the fable of the last
[00:21:46] day than I'd ever seen. Um and and it
[00:21:49] does seem like a bit of a step change.
[00:21:50] So I think if they continue to make
[00:21:52] moves like that we will definitely see
[00:21:54] more and more of a shift um I think
[00:21:58] against anthropic.
[00:21:58] >> I mean obviously so many open source
[00:22:00] models have been trained on just like
[00:22:01] distilling you know anthropic models
[00:22:03] like do you think this will have an
[00:22:04] impact on the on like the open source
[00:22:05] community?
[00:22:06] >> Depends if they litigate it right like
[00:22:08] it's not going to do anything in China
[00:22:09] to to to limit anybody there. Um you
[00:22:12] know and then for US models like I think
[00:22:14] people tend to be very careful like you
[00:22:16] know we we we did data did all the data
[00:22:18] curation for RC's trendy large model and
[00:22:20] we were very cognizant to not use any
[00:22:22] closed source APIs at any point um in
[00:22:25] any of the development there um also
[00:22:27] only public data. So like you can build
[00:22:29] a really powerful model without that.
[00:22:30] But I think also looking at the MAI uh
[00:22:32] model that they just released, right?
[00:22:34] They made a huge point of of um not
[00:22:36] going so far as actually not use any
[00:22:38] synthetic data at all to avoid um you
[00:22:41] know any any ability to kind of sneakily
[00:22:43] be distilling um from another model. And
[00:22:45] then I think they've said they now
[00:22:46] they're going to start using synthetic
[00:22:47] data from those models to kind of
[00:22:49] bootstrap them. Um
[00:22:51] but uh I don't know if it's going to
[00:22:53] fundamentally change it. like as so long
[00:22:55] as people can actually use an API to get
[00:22:56] to your models, you can't actually stop
[00:22:59] them from trying to do some amount of
[00:23:01] distillation. Um, that all said, I think
[00:23:04] distillate this this claim is is is like
[00:23:06] overblown to some extent. Like it's
[00:23:07] true, but it also like you you can build
[00:23:10] still great models. You don't need to
[00:23:12] distill to build a great model. I think
[00:23:14] that the notion that like, oh, the only
[00:23:16] way that any open model can catch up
[00:23:18] with a closed model is by effectively,
[00:23:20] you know, distilling or stealing from
[00:23:21] it, uh, reads a little bit like copium
[00:23:24] to me.
[00:23:24] >> I feel like when these models come out,
[00:23:26] everyone's, you know, on on on Twitter
[00:23:27] trying to figure out what what happened.
[00:23:28] And you obviously have a lot of people
[00:23:30] on the on the anthropic side saying,
[00:23:31] "Hey, this is the biggest step change in
[00:23:32] capabilities. You know, I can remember
[00:23:34] in a while." Um I'm not sure like you
[00:23:36] know uh to the extent you've you've
[00:23:37] played around with it, but like what
[00:23:39] what are your early reads on like how
[00:23:41] much of a of a step change in
[00:23:42] capabilities this really is?
[00:23:44] >> I only um played with it a little bit
[00:23:45] last night uh since Fable released. Um I
[00:23:48] didn't personally see massive
[00:23:50] differences from where 48 was. Um but
[00:23:55] and talking to people, it's it it seems
[00:23:57] like the the the takes have been quite
[00:23:59] varied uh around that. It's it's pretty
[00:24:01] hard to to tell honestly. My take on
[00:24:04] Fable is I kind of feel like it it is
[00:24:06] and also is not that big of a deal. Like
[00:24:09] I think it's it's the latest
[00:24:10] state-of-the-art model that was released
[00:24:12] that happened to be released yesterday,
[00:24:13] like a day before we're recording this,
[00:24:15] but like if we recorded this 3 weeks
[00:24:17] from now or seven weeks from now, there
[00:24:18] would probably be another model from
[00:24:20] another provider that we would be
[00:24:21] talking about. Um I do think like just
[00:24:24] based again based on the benchmarks and
[00:24:27] the quantitative data which is far from
[00:24:28] perfect. Um, but it like it does seem
[00:24:31] like it is a it is a meaningful step
[00:24:34] change improvement relative to the
[00:24:36] previous state-of-the-art which I think
[00:24:38] is meaningful again not because it's
[00:24:40] some like discontinuity like I think
[00:24:42] this kind of gradual improvement will
[00:24:44] continue you know going forward but I
[00:24:47] think it's it's meaningful in the sense
[00:24:49] that like I think it really does
[00:24:51] undermine this narrative that people
[00:24:53] have already shifted away from it that
[00:24:54] had a lot of currency a year or so ago
[00:24:57] that like pre-training is really hitting
[00:24:59] a wall. Things are plateauing like we
[00:25:02] now it just we it has to be you know RL
[00:25:05] and test on compute to carry us forward
[00:25:07] because you know we've hit this data
[00:25:08] wall like I just think that's clearly
[00:25:09] not true and uh like the gain the gains
[00:25:13] are continuing to come in very richly
[00:25:15] and it like I don't think there's any
[00:25:16] good reason to think that they will
[00:25:18] plateau anytime soon.
[00:25:19] >> Yeah, I think we also saw a lot of push
[00:25:20] back to that narrative over the last uh
[00:25:23] six to nine months and like it's it's
[00:25:24] pretty clear that pre-training did not
[00:25:27] hit a massive wall. uh we were just
[00:25:29] waiting for new chips. I think some of
[00:25:31] that I think also just like naive
[00:25:33] scaling doesn't work like yeah if you
[00:25:34] just take exactly the same stuff that we
[00:25:36] were doing and you just multiply it by a
[00:25:38] factor of 10 or 100 um which was kind of
[00:25:40] like what you know four or five was
[00:25:42] aiming at or or you know llama 35b at
[00:25:45] the time like that didn't work extremely
[00:25:47] well um but I think people took a much
[00:25:50] overgeneralized take from that
[00:25:53] especially because like one of the
[00:25:54] things that's actually really
[00:25:54] challenging about deep learning I have
[00:25:56] found um is that that you really need to
[00:26:00] get all the details right often for
[00:26:02] something to really work. If you have
[00:26:04] kind of like 95% of it right, um it kind
[00:26:07] of rectifies to like just not working.
[00:26:09] Um a lot of the time um there are a
[00:26:11] couple methods that are robust, but like
[00:26:13] you can like be doing almost everything
[00:26:15] right and not get like no real
[00:26:16] improvement and then you turn you tweak
[00:26:18] the last knob and now all of a sudden
[00:26:20] you get a step change. um like you know
[00:26:22] that that happens a lot in deep in deep
[00:26:24] learning and and one of the things
[00:26:25] that's challenging about that is it just
[00:26:26] makes it fundamentally difficult to
[00:26:28] interpret a negative result. Um okay you
[00:26:31] tried scaling everything up and it
[00:26:32] didn't work. Is that because scaling
[00:26:34] doesn't work or is that because you just
[00:26:35] did one thing wrong? Um and that often
[00:26:38] happens. It also makes it very hard to
[00:26:40] decide when to abandon a project. Uh
[00:26:42] because it easy to also then always be
[00:26:44] like well like maybe if I just make one
[00:26:46] more tweak this thing will work. Um when
[00:26:48] you know often times that's not the
[00:26:50] case. I mean, I guess you to hit the
[00:26:52] other players um in the space. I mean, I
[00:26:54] feel like Rob in our December episode,
[00:26:56] you said like, you know, which I think
[00:26:57] is a feeling all of us have that Google
[00:26:59] is like incredibly well positioned,
[00:27:00] right? I mean, obviously they've got
[00:27:01] talent, they've got compute. Um it
[00:27:04] doesn't feel like things have gone super
[00:27:06] well for Google in the last 6 months. Um
[00:27:08] you know, feel free to push back, but uh
[00:27:10] what's what's going on over there? And
[00:27:11] like why haven't they been able to catch
[00:27:13] up on coding, I guess, most notably?
[00:27:15] Yeah, I think I I think I would disagree
[00:27:17] a bit that like Google has fallen behind
[00:27:20] or isn't executing as well. Like I I
[00:27:23] again I think it like in part it goes to
[00:27:26] this reality that I think the three labs
[00:27:28] are all kind of in this process of
[00:27:30] leaprogging one another continually and
[00:27:32] any given month any one of them may have
[00:27:34] the like quote unquote state of the
[00:27:36] model.
[00:27:36] >> It's been a while for Google though.
[00:27:38] >> I think there's no question that they're
[00:27:39] behind on coding and I and I but I think
[00:27:40] that's just it reflects prioritization.
[00:27:43] like it's clear that Anthropic like
[00:27:45] leaned in on that as their northstar for
[00:27:47] years and that proved to be obviously an
[00:27:49] incredibly savvy move. Um that has
[00:27:52] really catapulted them and you know
[00:27:54] OpenAI more recently has really double
[00:27:56] tripled quadruple down on it and you're
[00:27:58] seeing a lot of positive love for codeex
[00:28:00] and I think it just hasn't been as much
[00:28:01] of a priority for Google. Um but I like
[00:28:04] everything we talked about previously I
[00:28:06] still stand by and feel very confident
[00:28:08] in the sense that like Google has an
[00:28:10] incredibly deep bench of talent unlike
[00:28:12] OpenAI Anthropic. Google has this
[00:28:15] massive cache machine. And then lastly
[00:28:16] is compute. Like I think Google has
[00:28:18] benefits so much from being totally full
[00:28:20] stack. They design their own chips. They
[00:28:22] have their own cloud. You know no one
[00:28:23] has access to infinite compute and
[00:28:24] Google is also you know would love to
[00:28:26] have more but they have a massive
[00:28:28] >> Would they love to have more? I don't
[00:28:30] know. They sold some they sold some of
[00:28:31] it off to to Anthropic. Yeah, I mean,
[00:28:33] yeah, they have a they have a cloud an
[00:28:35] external cloud business, but I think
[00:28:36] they're better positioned when it comes
[00:28:37] to compute than either anthropic or
[00:28:40] open. So, yeah, I'm I continue to be
[00:28:41] very bullish on Google.
[00:28:43] >> What do you think, Ari?
[00:28:44] >> I tend to share the same view. I am a
[00:28:46] little surprised that they haven't uh
[00:28:48] improved as much uh since 31. Um I I
[00:28:51] would have expected a bigger launch at
[00:28:53] IO. Uh, and I I wonder if, you know, in
[00:28:57] a couple months we'll find out there was
[00:28:58] one planned and then something went
[00:28:59] wrong and it was scuttled or or or
[00:29:01] whatever the case may be there. Um,
[00:29:02] beyond just the flash model, but I do
[00:29:04] think they have all the structural
[00:29:05] advantages. I think having access to the
[00:29:07] money printing machine um like I think
[00:29:09] that's a really interesting way to kind
[00:29:10] of think about the XAI SpaceX merger um
[00:29:13] is like it's a way for XAI to get
[00:29:14] attached to a money printer to the
[00:29:16] extent that SpaceX is a money printer
[00:29:17] which less so certainly uh than than
[00:29:20] Google or or or Meta is. Um so I think
[00:29:22] they are are well positioned there. Um I
[00:29:24] think also like I don't know if if
[00:29:28] Google's market is the same as what
[00:29:29] Anthropic is going after like with
[00:29:31] respect to the focus right like
[00:29:33] fundamentally
[00:29:34] models are going to be commoditized for
[00:29:36] consumers like I think that's just like
[00:29:38] quite clear that for the consumer use
[00:29:39] case of I'm just asking my my model a
[00:29:42] question about you know the world or or
[00:29:44] having it be a tutor or any of kind of
[00:29:46] the standard things that most consumers
[00:29:48] are going to use that's going to be
[00:29:50] commoditized and people are going to use
[00:29:51] the model on their phone like I I think
[00:29:53] that just seems very clear.
[00:29:55] >> What about like some of the computer use
[00:29:56] stuff or like it feels like there's
[00:29:57] still frontiers of of like consumer
[00:29:59] right uh that that that models can't do
[00:30:01] yet.
[00:30:01] >> I think there will be certainly um and I
[00:30:04] think you will see more of that but I
[00:30:05] think first off like most people will
[00:30:07] not use that level of
[00:30:10] of software. I think like the power
[00:30:12] users will but like you know most people
[00:30:14] are just going to be using it um as an
[00:30:16] answer engine. Um, and Google's now
[00:30:19] quite well optimized to be the kind of
[00:30:20] default provider both on Android phones
[00:30:22] and iOS phones. Um, until, you know,
[00:30:25] eventually, uh, Apple builds its own
[00:30:26] models there, which I've been pushing a
[00:30:27] lot there. So, I think Google's actually
[00:30:29] going to be in a strong position to that
[00:30:31] even if they don't necessarily have the
[00:30:33] best model. I think that's another big
[00:30:34] part here. It's like I don't know if the
[00:30:36] best model necessarily wins in the
[00:30:38] consumer space. Well, what about even in
[00:30:39] the in the in the coding space, right?
[00:30:41] Like I mean, this is this is honestly
[00:30:42] been most surprising to me is like I
[00:30:44] actually think Codex is like clearly an
[00:30:46] amazing product. it doesn't seem to be
[00:30:47] making a a huge dent. I mean, obviously,
[00:30:49] it's growing, but cloud code remains the
[00:30:51] the dominant, you know, coding tool. And
[00:30:53] I wonder, it's interesting to see kind
[00:30:55] of like this first mover like, hey, you
[00:30:57] introduce people to the paradigm
[00:30:59] advantage in in like, you know, I always
[00:31:01] thought of of of developer tools as like
[00:31:03] the most meritocratic like, you know,
[00:31:04] would switch on a in a second like best
[00:31:07] model always wins. I don't know what you
[00:31:09] guys make of of of, you know, of that.
[00:31:11] >> I think that's generally still true. I
[00:31:13] think I I I do think that developers are
[00:31:15] the most mercurial uh consumers in some
[00:31:18] ways and they are going to switch to
[00:31:19] whatever the best thing is. That said
[00:31:21] like there's a question of how much
[00:31:23] better is it uh and and I think clo
[00:31:25] claude and and codecs have stayed close
[00:31:27] enough and there hasn't been a massively
[00:31:30] compelling reason why you need to switch
[00:31:32] to codeex um such that a lot of people
[00:31:34] have stuck with cloud. I expect that at
[00:31:35] least amongst AI developers um you're
[00:31:38] going to see a massive set of of shifts
[00:31:40] now to to codeex from claude uh given
[00:31:43] the uh way that they're limiting Fable
[00:31:45] and and and whatnot. Um I I think that
[00:31:48] honestly this is a pretty nice gift for
[00:31:50] OpenAI uh with respect to a lot of the
[00:31:52] people who are the loudest voices on
[00:31:54] Twitter and whatnot um becoming will
[00:31:57] likely be spending a lot more time with
[00:31:58] codeex uh in the immediate future guess.
[00:32:00] But I mean is open so when 56 comes out
[00:32:03] and opening eyes you know presumably as
[00:32:04] to counterposition is going to have to
[00:32:06] give people more access like are they
[00:32:08] just ultimately going to eat you know
[00:32:09] way worse margins and like you know for
[00:32:11] for vibes and like for usage or like
[00:32:13] what what structurally is going to allow
[00:32:15] them to provide you know better access
[00:32:17] for you know as as you know a model
[00:32:19] that's on par.
[00:32:20] >> It's a good question. Um I mean I think
[00:32:22] ultimately it's like in any market where
[00:32:24] you have kind of a couple players like
[00:32:25] so long as the the models are are close
[00:32:27] enough um that can make a big
[00:32:29] difference. It could also be compute
[00:32:30] access, right? Entropic just got a lot
[00:32:32] of access here. But I think that's
[00:32:33] another one of the things circling back
[00:32:34] to earlier conversation around how like
[00:32:36] there might be fewer open models uh
[00:32:38] going forward. I I think part of that
[00:32:40] could also actually be that there could
[00:32:41] be fewer closed models uh access going
[00:32:44] forward. Like it is not hard to imagine
[00:32:46] a world in which anthropic is so compute
[00:32:49] constrained that they actually cut off
[00:32:50] the API. Um because obviously they're
[00:32:53] going to prefer cloud code to the API
[00:32:56] with respect to how much money they
[00:32:57] make. Um, and you start to see this now
[00:32:59] with like OpenAI starting to sell like
[00:33:01] futures of like, hey, you get guaranteed
[00:33:02] access to inference tokens uh going
[00:33:05] forward. Like that's actually a huge
[00:33:07] existential threat uh to anybody that
[00:33:09] that builds on top of these models. And
[00:33:10] I think that was not really a plausible
[00:33:12] thing six months ago, but now feels very
[00:33:14] plausible that actually the APIs go
[00:33:16] away. Um, not as a business decision,
[00:33:18] but just purely because of compute
[00:33:19] constraints.
[00:33:20] >> Yeah. And what do you what do you think
[00:33:21] of that, Rob?
[00:33:22] >> Yeah, I think it's totally feasible. Um,
[00:33:24] I think Yeah, I think a few different
[00:33:25] things could happen. I think um you know
[00:33:27] cutting off their API access altogether
[00:33:30] is it would be an extreme move. But you
[00:33:32] can imagine for instance uh open AI or
[00:33:35] anthropic uh rather than you know not
[00:33:39] just not open open sourcing their models
[00:33:41] but only making them available via API.
[00:33:43] You could imagine them actually not even
[00:33:45] making their most powerful models
[00:33:47] available to anyone publicly and and
[00:33:48] reserving them for internal use. Um and
[00:33:52] uh and yeah and you you can um you know
[00:33:55] I so much of this depends I think on the
[00:33:57] compute bottleneck and how long it stays
[00:34:00] this acute. um which I think is is
[00:34:03] interesting to reflect on and this you
[00:34:06] know this again this gets to some of
[00:34:07] these like deeper tech topics which I
[00:34:09] think are becoming increasingly relevant
[00:34:11] like there are uh on the horizon there
[00:34:14] are efforts uh and startups that are
[00:34:16] trying to like break the semi
[00:34:18] semiconductor supply chain wide open
[00:34:20] build cutting edge fabs in the US
[00:34:22] challenge ASML challenge TSMC etc. Elon
[00:34:25] Musk obviously has this terapab concept
[00:34:27] which is fascinating and honestly I feel
[00:34:30] like people should be talking about more
[00:34:31] uh just given how transformative it
[00:34:33] would be if it if he pulls it off. So I
[00:34:35] think a lot of those variables will will
[00:34:38] influence like how long is compute the
[00:34:41] the limiting factor and that in turn I
[00:34:43] think like if it remains this compute
[00:34:45] constraint I think some of these
[00:34:46] possibilities that AR is sketching out
[00:34:48] like you could totally imagine them
[00:34:49] being real. It's hard to imagine though
[00:34:51] how we actually unblock like if we
[00:34:53] continue even remotely on this
[00:34:54] trajectory. Uh it's it's hard to imagine
[00:34:57] how we relieve the compute constraint uh
[00:34:59] within the within the next handful of
[00:35:01] years. I think
[00:35:03] >> yeah it's yeah I think it's not a it's
[00:35:05] not a two to threeyear thing where like
[00:35:07] TSMC is not displaced but like augmented
[00:35:11] by many other players that can provide
[00:35:13] comparable chips but like you can
[00:35:15] imagine over five like it doesn't have
[00:35:17] to be the case that there's only one
[00:35:18] company in the world that can make
[00:35:20] cutting edge like it's actually kind of
[00:35:21] crazy that that's the current market
[00:35:22] structure that there's like one company
[00:35:24] that knows how to do this and no one
[00:35:25] else can do it and that one company that
[00:35:27] can do it the most important machine
[00:35:29] that goes into the process is made by
[00:35:31] one other and no one else could do it.
[00:35:33] Like it doesn't have to be that way and
[00:35:34] I don't think it will be that way for
[00:35:36] them.
[00:35:36] >> What what a wild version of uh of the
[00:35:38] many worlds that we could live in that
[00:35:39] we live in now. That is uh it is it is
[00:35:41] pretty nuts.
[00:35:42] >> Are there clear upstarts going going
[00:35:44] after ASML? There are a lot going after
[00:35:46] TSMC, but I haven't seen as many going
[00:35:48] against ASML.
[00:35:49] >> There are. Yeah, it's it's an
[00:35:51] interesting it's an interesting new area
[00:35:53] of research. like uh in a nutshell, ASML
[00:35:56] OB their their focus is obviously
[00:35:58] extreme ultraviolet lithography EUV uh
[00:36:01] and EUV is like starting to hit physical
[00:36:03] limits in terms of how small of
[00:36:05] transistors it can print on the chips.
[00:36:08] And so there are a couple really
[00:36:09] interesting new research directions. One
[00:36:10] is um rather than using light like
[00:36:13] moving away from using light altogether
[00:36:15] and instead using matter it's called
[00:36:17] atom lithography where like you use you
[00:36:19] use a beam of atoms to print uh these
[00:36:22] features on the on the chips which lets
[00:36:24] you get like way lower resolution. And
[00:36:26] so there are a couple startups doing
[00:36:27] really interesting work in atom
[00:36:28] lithography. And then there's also a
[00:36:31] handful of startups um that are
[00:36:33] basically looking to like leapfrog EUV
[00:36:36] and move even further out on the
[00:36:38] electromagnetic spectrum to the thing
[00:36:39] that's like has even shorter wavelengths
[00:36:41] which is X-rays. So like this this whole
[00:36:43] concept of X-ray lithography is is
[00:36:45] getting a lot of momentum. There's a
[00:36:47] couple startups in each of these buckets
[00:36:48] that have raised like a ton of money and
[00:36:51] are running at this and and to state the
[00:36:53] obvious like they're still in they're
[00:36:56] still very much in development mode and
[00:36:57] like it remains to be seen whether
[00:36:58] either of these will prove to be
[00:37:00] commercially viable but if they work
[00:37:02] like I think honestly I think especially
[00:37:04] atom lithography there are so many
[00:37:05] advantages in terms of like the machine
[00:37:07] can be way simpler way fewer parts way
[00:37:10] cheaper way smaller obviously much
[00:37:12] better resolution so anyway yeah I do
[00:37:14] think there may be like real technology
[00:37:16] disrup disruption coming here.
[00:37:17] >> It looks like that's at least five years
[00:37:19] away probably given uh
[00:37:21] >> where it is right currently.
[00:37:22] >> I think this thread is fascinating to
[00:37:23] pull on like what are the actual
[00:37:25] implications of a year or two from now
[00:37:26] like where like we're even more compute
[00:37:28] constraint than we are today. And
[00:37:29] obviously you know it feels like there's
[00:37:30] lots of you know people what do they
[00:37:32] call it like using a Ferrari to go down
[00:37:33] the street to the grocery store. Like
[00:37:35] there's probably like overusage of of of
[00:37:37] powerful models for for what people need
[00:37:39] today. But even if we figure all that
[00:37:40] stuff out and route people perfectly to
[00:37:42] their you know uh daty built models or
[00:37:45] however the world ends up working like
[00:37:46] feels like we'll still be in this kind
[00:37:47] of you know uh overall compute shortage
[00:37:49] and you know it's fascinating. I mean
[00:37:51] one implication of that is is obviously
[00:37:53] the labs themselves you know
[00:37:54] prioritizing first party products or
[00:37:56] prioritizing their own development. Um
[00:37:59] any other implications? I don't I'm just
[00:38:00] thinking on the spot here, but I'm
[00:38:01] curious if there's other implications
[00:38:03] that come to mind for either of you uh
[00:38:04] of like what that might mean for even
[00:38:06] businesses, you know, in in competitive
[00:38:08] industries that get access or don't get
[00:38:10] access or
[00:38:10] >> it pushes towards efficiency, right?
[00:38:12] Like generally, especially the frontier
[00:38:14] labs have not cared too much about
[00:38:16] efficiency because of said infinite
[00:38:18] capital access. Uh and like you will get
[00:38:21] to physical constraints where you have
[00:38:23] to figure out how to be more more
[00:38:24] efficient. So I think it'll drive um a
[00:38:26] lot more interesting innovation.
[00:38:27] Frankly, um, one of the directions that
[00:38:29] I've just always been very bullish on
[00:38:31] and I think we've seen consistently is
[00:38:33] that like you do not need trillion plus
[00:38:35] token parameters in order to achieve the
[00:38:37] capabilities that we we currently see
[00:38:39] um, in the abstract like at the moment
[00:38:41] that like you need it to get that
[00:38:43] frontier level but like we consistently
[00:38:44] see that smaller and smaller models can
[00:38:46] match the largest models of even one to
[00:38:48] two years ago, right? Um, so I think
[00:38:51] that will only accelerate as a result of
[00:38:53] that. will be more and more push towards
[00:38:55] how do you make models as small as
[00:38:57] possible. Um you'll probably see a lot
[00:38:59] more investment in areas that can help
[00:39:01] like that like distillation uh and and
[00:39:03] things like that to try towards get
[00:39:05] towards really reducing um the inference
[00:39:07] costs. Um I think if you can do that
[00:39:10] that that can alleviate a fair amount of
[00:39:13] this. I would still expect that the
[00:39:15] usage is going to grow faster than what
[00:39:17] you can do to alleviate this.
[00:39:18] >> Yeah, I definitely agree with Ari on the
[00:39:20] efficiency point. I think another
[00:39:22] interesting implication of this like
[00:39:24] massive supply constraint world is it
[00:39:27] will be it will be a very good thing for
[00:39:29] other chip providers other than Nvidia.
[00:39:31] Um I think basically pretty much
[00:39:33] everyone would probably prefer to use
[00:39:35] Nvidia GPUs and anything else. Uh you
[00:39:38] know maybe other than people at Google.
[00:39:39] Uh but there just aren't enough GPUs to
[00:39:42] go around. And so you're you're already
[00:39:43] seeing like companies are are doing what
[00:39:45] they have to do to adapt to use AMD GPUs
[00:39:49] and to use Amazon tranium and Cerebras
[00:39:52] obviously is seeing massive tailwinds
[00:39:54] because of this. I think basically like
[00:39:55] any chips anyone could get their hands
[00:39:56] on will uh be in massive demand and so I
[00:40:00] think it's not a bad thing for Nvidia
[00:40:02] but I think it's a good thing for other
[00:40:04] chip holders. I actually do think that's
[00:40:05] one of the big themes of the of the last
[00:40:07] uh you know six nine months is like the
[00:40:09] rise of these you know as inference is
[00:40:11] dominated and you can kind of split
[00:40:12] these inference workloads into pre-fill
[00:40:14] and decode and other things like you you
[00:40:16] really can use you know heterogeneous
[00:40:18] chips. Um the question I have is like do
[00:40:20] these other chips really like help us on
[00:40:22] the compute shortage given like this
[00:40:25] exact theme we keep talking about like
[00:40:26] there's you keep shifting bottlenecks
[00:40:28] and so it's like there is a bottleneck
[00:40:29] upstream of the chips which are like the
[00:40:31] components that go into the chips or the
[00:40:32] production of the chips at TSMC. um you
[00:40:34] know ASML all this stuff like does
[00:40:37] having more chips actually solve that
[00:40:38] fundamental bottleneck energy all these
[00:40:40] things um or is it just like uh similar
[00:40:43] to Jeff every space we look at all these
[00:40:44] vendors are very happy to have you know
[00:40:47] more players than just Nvidia I don't
[00:40:48] know if if the rise of all these other
[00:40:50] chips actually gives us like more
[00:40:51] compute I'd be curious for for your
[00:40:53] thoughts on that
[00:40:53] >> I think that intuition makes sense
[00:40:55] because right like if you imagine a
[00:40:56] world in which there's there's no there
[00:40:58] are no you know there's no cerebrus
[00:41:00] there there's no dmatrix there's no one
[00:41:02] else who's kind of making competitive
[00:41:03] ships Presumably Nvidia just eats up the
[00:41:05] TSMC capacity in that world, right? Um
[00:41:07] and the total number of chips stays
[00:41:10] constant uh in the world. So likely it
[00:41:12] just acruse value to not Nvidia as a
[00:41:15] result of that uh rather than actually
[00:41:17] changing the the situation
[00:41:18] fundamentally.
[00:41:19] >> Yeah. Yeah. Yeah, I I think the
[00:41:20] alternative chip providers aren't a
[00:41:23] solution to the compute constraints, but
[00:41:26] will be a beneficiary of the compute
[00:41:27] constraint in the sense in the sense
[00:41:29] that uh Nvidia doesn't get all of TSMC's
[00:41:34] uh like production capabilities and and
[00:41:37] all of you know all of the supply chains
[00:41:39] production. And so like you know if if
[00:41:41] in a world where there is a surplus of
[00:41:43] chips, everyone would rather use Nvidia,
[00:41:45] people can buy Nvidia, there just isn't
[00:41:46] that much demand for these other chips.
[00:41:48] But in a world where you just can't get
[00:41:50] your hands on enough Nvidia chips, then
[00:41:52] like people are going to pay a lot for
[00:41:53] AMD chips and pay out for Amazon chips
[00:41:55] and it won't to your point like the the
[00:41:58] overall um the overall supply of chips
[00:42:01] won't be changed as a result of them,
[00:42:03] but I do think they'll see massive
[00:42:04] tailwinds,
[00:42:05] >> right? TSMC doesn't want a monopony.
[00:42:07] >> Totally. But it's a fascinating parallel
[00:42:08] to the NeoCloud world too, right? um
[00:42:10] where you basically have uh the same
[00:42:12] thing like it's not like you're miss not
[00:42:13] necessarily increasing the number of of
[00:42:15] overall chips but like they've certainly
[00:42:17] been shuffled among a bunch of different
[00:42:19] players and as long as the uh capacity
[00:42:21] constraint is there uh you know every
[00:42:23] one of those is a very solid business.
[00:42:24] Do we actually given what's happening
[00:42:26] expect uh you know there not to be a
[00:42:28] compute constraint anytime soon? Like
[00:42:30] are we really talking about like 2035 or
[00:42:32] like you know hey in 15 years maybe
[00:42:34] someone we'll figure out what happens to
[00:42:36] these businesses.
[00:42:38] It's probably not in the next couple
[00:42:39] years. Like I would be surprised if
[00:42:41] anything happens before 2030. That said,
[00:42:43] like if when when all of the different
[00:42:45] methods that people are working on to
[00:42:47] try to relieve these bottlenecks all
[00:42:49] start hitting at the same time, which is
[00:42:51] probably what will happen, right? We'll
[00:42:52] have like a several years where it'll be
[00:42:53] like several big unblocks probably in
[00:42:55] like the early 2030s would be my guess.
[00:42:57] Um that's probably when the merrygoround
[00:43:01] uh starts. I think the other question is
[00:43:03] like as more chips are produced like to
[00:43:06] what extent can we start to continue to
[00:43:08] get a lot of value out of older chips.
[00:43:11] Um and that can also I think one huge
[00:43:13] thing that you know has been like the
[00:43:14] the or like the the leading indicator of
[00:43:17] this is is has been that H100 prices
[00:43:20] reversed their drops and that happened I
[00:43:22] think right around when we recorded the
[00:43:23] last episode was when that started to
[00:43:25] happen in December but like H100 prices
[00:43:27] have gone up dramatically uh over the
[00:43:30] last number of months. So I think
[00:43:31] there's also a lot of uh there are a lot
[00:43:34] of chips there that that that can be
[00:43:35] used but I do wonder what happens when
[00:43:37] the merry go round stops on that and
[00:43:39] they ultimately are all selling the
[00:43:40] exact same product with you know minimal
[00:43:42] differentiation.
[00:43:43] >> Well well speaking of what uh the
[00:43:44] neocloud space I mean obviously I I
[00:43:46] think the the biggest headline in that
[00:43:47] world is SpaceX right and and like just
[00:43:49] you know coming into the space in a in a
[00:43:50] huge way. Uh what do you guys like make
[00:43:53] of uh what is the future of of XAI? Do
[00:43:55] you think I mean obviously do they just
[00:43:57] lean into to continue to do this at
[00:43:59] scale? you think the model business uh
[00:44:01] has any legs? I guess it not a not a bad
[00:44:03] time to bring up the uh the cursor uh
[00:44:05] potential acquisition and and how that
[00:44:07] fits in. Um but would love to hear, you
[00:44:09] know, one of you riff on that.
[00:44:10] >> Yeah, it's a good it's a good question.
[00:44:12] I um I I would say I'm not super
[00:44:16] optimistic for XAI's future trajectory
[00:44:20] in terms of them being a frontier lab.
[00:44:23] And I do like I think the you know these
[00:44:26] massive deals that SpaceX signed to to
[00:44:28] rent compute to anthropic um into Google
[00:44:32] I think on the one hand yes it's like
[00:44:35] patting the numbers uh of the patting
[00:44:37] the revenue numbers ahead of the IPO and
[00:44:39] that like that obviously plays a role
[00:44:40] but I also do it's hard not to interpret
[00:44:43] it as a signal that like the company's
[00:44:45] foremost priority is not doing frontier
[00:44:47] AI research and fueling XAI's research
[00:44:50] because if it was it just to to this the
[00:44:52] last 20 and it's discussion around how
[00:44:54] how much uh the world is compute
[00:44:56] constrained like you just wouldn't be
[00:44:57] giving away uh
[00:44:59] >> pretty hard business to IPO if all those
[00:45:01] chips were being used uh for for
[00:45:03] training right uh without a without like
[00:45:05] much revenue to show for it on the on
[00:45:06] the product side
[00:45:08] >> Elon companies aren't valued on
[00:45:09] fundamentals like I don't know it's
[00:45:11] totally different with an Elon company
[00:45:12] so who knows
[00:45:14] >> and kind of to Ari's point I think that
[00:45:16] like the thing that Elon Musk is amazing
[00:45:18] at and his companies are amazing at is
[00:45:20] like incredibly operationally intense
[00:45:23] real world like atoms, not just bits uh
[00:45:27] undertakings. Obviously, we saw that
[00:45:28] with we've seen that with Tesla, we've
[00:45:30] seen that with SpaceX. And so, it's not
[00:45:31] surprising to me that like in the world
[00:45:32] of AI, the one wedge where this SpaceX
[00:45:36] XAI like behemoth is going to have a
[00:45:39] real durable advantage, I think, will be
[00:45:41] on the data center side. I think they
[00:45:43] will excel at like and they already have
[00:45:45] Excel that's standing up massive massive
[00:45:47] clusters super fast getting them up and
[00:45:48] running and I think that will be a great
[00:45:51] business for them and it may turn them
[00:45:52] into like the world's biggest cloud
[00:45:55] especially as you know in the years
[00:45:56] ahead the company starts putting more
[00:45:57] and more compute into orbit. Um but I
[00:46:00] don't I I don't know I guess I just I
[00:46:02] don't it doesn't seem to me like
[00:46:03] organizationally
[00:46:05] being at the frontier of of the AI model
[00:46:08] race is a priority or is necessarily
[00:46:10] realistic. Obviously, we've seen just
[00:46:11] like the insane attrition from XAI over
[00:46:14] the past year or so. And like I think it
[00:46:16] makes sense for the the overall, you
[00:46:18] know, Elon Elon code to have a model arm
[00:46:21] that's doing model stuff. But do I like
[00:46:23] I guess I'm not if I had to bet I
[00:46:25] wouldn't be super bullish that like they
[00:46:27] will crack back into the, you know, the
[00:46:29] top echelon alongside Google opening
[00:46:32] anthropic.
[00:46:32] >> So what are they doing? Like why why uh
[00:46:34] why why cursor?
[00:46:36] >> I think why cursor is to get all the
[00:46:38] traces. um like I I think that would be
[00:46:40] the and to have a hedge against the fact
[00:46:42] that they have um struggled to produce a
[00:46:44] very competitive coding model uh
[00:46:46] fundamentally. So are traces for coding
[00:46:48] worth $60 billion?
[00:46:50] >> I'm not sure if they're worth $60
[00:46:51] billion, frankly. Um but if you if you
[00:46:55] if you make the if you think that that's
[00:46:57] what can leaprog you and accelerate you
[00:46:59] to having a strong coding model, um I
[00:47:02] can see where that comes from. 60
[00:47:03] billion is probably quite high relative
[00:47:06] to that. Um, but I don't think Elon has
[00:47:09] given up the ambition probably of trying
[00:47:11] to of wanting to have the best models. I
[00:47:13] do think that when you look at the
[00:47:14] practical aspects of it, it's hard to if
[00:47:17] your pure goal is to build the best
[00:47:19] models, then you would not be giving
[00:47:21] away massive amounts of compute. Um, not
[00:47:23] giving away selling massive amounts of
[00:47:25] compute. So, I think that it does go to
[00:47:26] to Rob's point that it's not their top
[00:47:28] priority. And, you know, cursors even
[00:47:30] especially given the way that that deal
[00:47:31] was structured, like it is an option.
[00:47:34] It's kind of like hey we want to
[00:47:35] maintain some amount of optionality for
[00:47:37] the next uh number of years.
[00:47:39] >> Yeah. Till we till we see uh if traces
[00:47:41] actually are the most important thing to
[00:47:42] to make a really good coding model.
[00:47:44] >> And on the cursor point I sure you guys
[00:47:47] all saw and laughed at the like the
[00:47:48] SpaceX TAM chart in the S1 where like I
[00:47:52] think they estimated like the total
[00:47:54] space.
[00:47:54] >> I never laugh at a big TAM chart. Got to
[00:47:56] love Got to love the ambition.
[00:47:57] >> You just salivate. Um like
[00:48:00] >> 28 trillion sounds good to me.
[00:48:02] >> Oh yeah. All of space was like I don't
[00:48:03] know five or six hundred billion and
[00:48:05] then comms basically Starlink was like
[00:48:08] one or two billion and then yeah
[00:48:09] enterprise AI was like 20 trillion or
[00:48:11] something.
[00:48:12] >> I think it's always good when like all
[00:48:13] of space is you know not uh close to you
[00:48:16] know uh like it's like a few percentage
[00:48:18] points of your of your TAM.
[00:48:20] >> Yeah. Yeah. Exactly. So anyway, I think
[00:48:22] that points to why cursor like they
[00:48:24] certainly like the narrative again a lot
[00:48:26] of this goes into the IPO narrative is
[00:48:27] around like we're going to win
[00:48:29] enterprise AI and an asset like cursor
[00:48:32] because before adding cursor they really
[00:48:34] had no like application or product
[00:48:37] surface area. Um whether or not they'll
[00:48:39] actually succeed in that undertaking I
[00:48:42] think is a lot less clear. Uh but I
[00:48:45] think that's the I think so much of it
[00:48:47] is just that like the the positioning
[00:48:49] and narrative. We've made it through a
[00:48:50] good chunk of the episode here and we
[00:48:51] haven't mentioned anything Andre
[00:48:52] Carpathy related which I think is you
[00:48:54] know I think we've done it pretty much
[00:48:55] every episode he's like he seems to be
[00:48:57] the unifying theme you know first he
[00:48:58] says that everything's slopp decides to
[00:49:01] go join one of the labs um you know
[00:49:03] obviously he went to join this this
[00:49:05] rehearsal self-improvement team and it
[00:49:06] feels like there's you know I think both
[00:49:08] labs have been very vocal hey we're
[00:49:10] going to have you know a R&D by 2028 um
[00:49:13] it feels like you know there's all these
[00:49:15] Twitter vague posts about hey we're
[00:49:17] getting really close Um, how close do
[00:49:20] you guys think we actually are? Um, and
[00:49:21] like, you know, is is Andre deciding
[00:49:23] it's time to go back in? Like, how much
[00:49:25] of a signal is that?
[00:49:26] >> I think we're closer. My estimate is
[00:49:28] that we're much closer now than we were
[00:49:29] 6 months ago. Um, I I I would say so I
[00:49:32] do think this is something that has
[00:49:33] changed and that I become one of the
[00:49:35] places where my mind has changed a
[00:49:36] little bit where, you know, I've become
[00:49:38] more bullish on this direction. I do
[00:49:40] still think that the bottlenecks are in
[00:49:41] compute fundamentally. Um I think we
[00:49:44] talked about this in maybe the last
[00:49:45] episode that like ideas are not
[00:49:48] necessarily the challenge. Even
[00:49:49] execution is not necessarily the
[00:49:51] challenge. Um it's you have to actually
[00:49:53] then go and run the experiments. Um and
[00:49:57] that takes compute. Um so I I do think
[00:50:00] there's going to be some bottleneck on
[00:50:02] the pace of improvement. Um
[00:50:06] but we are we are clearly getting to the
[00:50:08] point where models can improve
[00:50:10] themselves. you know, we've we've
[00:50:11] started to do a number of experiments
[00:50:13] here around, you know, just having
[00:50:14] agents uh do the curation itself uh in
[00:50:17] various ways with various amounts of
[00:50:18] guidance and like seen far more
[00:50:19] promising results out of that than I
[00:50:21] would have expected. Um so there's like
[00:50:23] a lot in this direction. I think there
[00:50:25] is a lot of reason to be very excited um
[00:50:27] about it. Um I do think though that lots
[00:50:31] of people will be able to do the same
[00:50:33] thing. So, I think like the the the flip
[00:50:34] side of this is there's this like view
[00:50:35] of RSI where it's like, okay, now like
[00:50:37] there's one player that's going to go
[00:50:39] super duper fast and run away and then
[00:50:41] nobody can compete with it, right? Um
[00:50:44] I'm still very skeptical of that uh view
[00:50:48] because I think there are just like
[00:50:49] fundamental compute bottlenecks that can
[00:50:50] prevent the speed and also like there
[00:50:53] are 10 companies at least at this point
[00:50:56] that have the funding, the talent and
[00:50:58] the knowhow to to to work on this. Um,
[00:51:01] it's not something that I think is going
[00:51:03] to be like fundamentally limited to a
[00:51:05] small group of people.
[00:51:06] >> I was expecting you to be more
[00:51:08] skeptical, Ari, on the whole notion of
[00:51:10] recursive self-improvement, but it's
[00:51:11] interesting that you are a believer in
[00:51:14] it and yet you don't buy into this kind
[00:51:16] of like takeoff narrative like what
[00:51:18] would that look like for for allowed to
[00:51:21] like crack true RSI and yet not have
[00:51:23] this sort of uh exponential takeoff? Is
[00:51:26] is it just the compute as a limiter
[00:51:28] basically? I think that's where a lot of
[00:51:30] it like compute is a is a fundamental
[00:51:32] limiting factor with respect to this and
[00:51:34] and also like getting having just like
[00:51:37] more humans only makes you go faster to
[00:51:39] a certain point. Um and I think there is
[00:51:42] a question of like how much better than
[00:51:44] humans is it going to be. It's clearly
[00:51:45] coming to the point where it can be
[00:51:46] comparable to a you know junior AI
[00:51:49] researcher. Um
[00:51:52] having just an army of junior II
[00:51:54] researchers get you get you so far. So
[00:51:55] will it continue past that? Um and then
[00:51:58] I think there will be some speed
[00:51:59] limitation but I will say like I was a
[00:52:01] lot more skeptical uh of it uh you know
[00:52:04] 6 months ago and I think you know we
[00:52:06] have seen some clear progress here. I
[00:52:08] think also you look at some of the
[00:52:09] actions that some of the labs are taking
[00:52:10] anthropic is slowing down on hiring a
[00:52:12] lot of junior folks um that starts to to
[00:52:15] to drive uh you know more confidence
[00:52:18] that this is possible but I think it's
[00:52:19] going to be a lot slower than than
[00:52:20] people say. Well, I always like to end
[00:52:22] our our our our sessions with like a uh
[00:52:24] a rapid quickfire where we get your, you
[00:52:26] know, to to to to drum up the last bit
[00:52:28] of spice which provides fodder then for
[00:52:30] the next episode. So, uh I figure, you
[00:52:32] know, maybe maybe to start uh curious
[00:52:34] for both of you like what do you
[00:52:36] disagree with most that's kind of a a
[00:52:37] common trope in the in the broader
[00:52:39] discourse right now?
[00:52:40] >> Um I'm happy to start. Um I think this
[00:52:43] is like a bigger picture observation
[00:52:47] but relates to a lot of the discussion
[00:52:48] we've been having around like the chip
[00:52:50] shortage, the capex buildout, the you
[00:52:52] know the m the gigawatt scale data
[00:52:54] centers. Um to me it seems so clear that
[00:52:58] like in in some in you know say five to
[00:53:01] 10 years we're going to look back on the
[00:53:03] current era of AI and it's going to it's
[00:53:08] going to be laughable how resource
[00:53:10] inefficient today's AI systems are. like
[00:53:13] the fact that we need to build 2 gawatt
[00:53:15] scale data centers that's like twice as
[00:53:17] much power as all of the city of San
[00:53:19] Francisco to run these state-of-the-art
[00:53:21] models and you know get to like return
[00:53:24] to one of my favorite hobby horses like
[00:53:26] compare that to the human brain as an
[00:53:28] existence proof and the fact that human
[00:53:31] intelligence which is what we're trying
[00:53:32] to achieve at the end of the day with AI
[00:53:33] runs on 20 watts of power um I just I
[00:53:36] think that like and I don't think
[00:53:38] there's going to be one silver bullet
[00:53:39] breakthrough but I think there will be
[00:53:40] massive advances at the hardware level
[00:53:42] you things like Naveen Rouse company
[00:53:44] that he's working on uh analog computing
[00:53:47] you know efforts like that that lead to
[00:53:48] fundamental breakthroughs and the energy
[00:53:50] efficiency of chips I think for sure
[00:53:52] there'll be a lot of uh algorithmic
[00:53:54] breakthroughs and optimization
[00:53:56] breakthroughs but I think like and and I
[00:53:59] think it has complex uh and not obvious
[00:54:03] intersections with this question of like
[00:54:05] the demand shortage how long does it
[00:54:07] last the capex build out
[00:54:08] >> yeah it's interesting obviously like I
[00:54:09] mean two things you know that come out
[00:54:10] of that one is you know if if things do
[00:54:12] go that way, then the the moes on the
[00:54:14] leading model providers are far less
[00:54:16] compelling, right? I mean, obviously a
[00:54:17] huge part of the mode today is just
[00:54:18] access to capital and and and scale. Um,
[00:54:21] and so, you know, you've had all these
[00:54:23] like folks spin out of of Neolabs and
[00:54:25] like I think a lot of them, you know,
[00:54:26] similar inspiration of of what to go
[00:54:28] chase. Um, and I've never been convinced
[00:54:30] that even if they do figure that out, it
[00:54:31] ends up being like a great business. Um
[00:54:33] because to our you know point we've
[00:54:35] always talked about is like these ideas
[00:54:36] do diffuse and other people it's very
[00:54:38] unlikely that for a long period of time
[00:54:40] you'll have an idea that looks
[00:54:41] fundamentally different than these other
[00:54:42] folks and so uh it'll be really
[00:54:44] interesting is you know if the world
[00:54:46] does go that way and then you know I
[00:54:47] think the the second point and Ari you
[00:54:49] always hit on this I think in our first
[00:54:50] episode you talked about this in the
[00:54:51] context of the Chinese open source
[00:54:52] models is like you know uh constraints
[00:54:55] breed that innovation and I wonder you
[00:54:56] know you like the incentive at if you're
[00:54:58] at open or anthropic right now is just
[00:55:00] like keep pushing the current I mean the
[00:55:02] current paradigm and getting better at
[00:55:03] it is so so valuable. And so you've had
[00:55:05] folks like Jerry Twark spin out of of
[00:55:07] Open AI and be like, well, I want to
[00:55:08] focus on something that feels more akin
[00:55:10] to to what you're talking about, Rob.
[00:55:11] And it'll be fascinating to see whether
[00:55:13] uh these advances, you know, the next
[00:55:14] big advance around this happens in in in
[00:55:17] one of the big labs or uh or you know,
[00:55:19] maybe in an ancillary place. I don't
[00:55:20] know if you have a a prediction on that,
[00:55:22] Ari.
[00:55:23] >> I think you'll see it come from many
[00:55:25] places simultaneously.
[00:55:27] uh there's this notion of of uh multiple
[00:55:30] independent discoveries uh where like
[00:55:32] you know how many times are things
[00:55:34] discovered independently and there's a
[00:55:36] really interesting Wikipedia page about
[00:55:37] this uh where you can go and look there
[00:55:39] were a lot like basically every major
[00:55:41] sign of discovery was discovered by
[00:55:42] several people simultaneously um and
[00:55:44] then as communication bandwidth um
[00:55:47] increased uh and and latency decreased
[00:55:49] where now you know what's happened
[00:55:50] across the world the next day that that
[00:55:52] uh got a lot faster and now you see that
[00:55:54] a lot less often but I think like you
[00:55:55] clearly see that ideas are just ready
[00:55:57] like OpenAI didn't invent the idea of
[00:55:59] test time compute many people were
[00:56:01] working on test time compute you know 01
[00:56:02] just came out first um I think for you
[00:56:05] know anything we're seeing with
[00:56:06] recursive self-improvement or any other
[00:56:07] aspects you're going to see the same
[00:56:08] sort of thing the space of ideas isn't
[00:56:10] that massive and like ideas do become
[00:56:12] ready so you know whatever ends up
[00:56:14] working I would bet that uh you know
[00:56:16] several other people will will be
[00:56:17] working on the same thing simultaneously
[00:56:19] so I think it'll be a little bit of both
[00:56:22] >> and what do you disagree most with in
[00:56:24] the broader discourse right now probably
[00:56:26] the thing I I I disagree with the most,
[00:56:27] although this could be co potentially uh
[00:56:30] is the notion of the permanent
[00:56:32] underclass and just like this idea that
[00:56:35] um you know all AI is going to take all
[00:56:39] human jobs in a decade are really going
[00:56:41] to laugh hard. Uh
[00:56:42] >> yeah, I'm doing poorly at Roko's
[00:56:44] basilisk here, but um you know and it's
[00:56:47] like kind of interesting, right, that
[00:56:48] Enthropic is even like going around and
[00:56:49] like saying this very very visibly and
[00:56:51] so on. Um my the reason I tend to think
[00:56:55] that this is I is overblown um is uh
[00:57:00] that fundamentally
[00:57:02] just humans are slow at dissipating
[00:57:04] things through the economy. Uh like it's
[00:57:07] going to take a long time for you know
[00:57:09] even the tools we're seeing to really
[00:57:11] fully percolate and and and you know
[00:57:12] we're seeing that now such that and so
[00:57:15] much of of of business and everything is
[00:57:17] actually about humanto human interaction
[00:57:19] and trust and so on. Those are like
[00:57:22] barriers that I think technocrats tend
[00:57:24] not to consider. Um, you know, and I I
[00:57:28] think a lot of the folks that are
[00:57:29] projecting kind of the really fast
[00:57:31] timelines around this uh are
[00:57:33] underestimating how slow the world can
[00:57:36] be um in in various ways. Um so I I I
[00:57:40] tend to think that that's that's
[00:57:41] overblown. That's probably the thing I I
[00:57:43] disagree with the most. But it's also
[00:57:44] possible that I just want humans to to
[00:57:46] still matter for longer.
[00:57:47] >> Yeah. Um I I think Ari you mentioned
[00:57:49] kind of you know what you change I think
[00:57:50] actually both of you had mentioned
[00:57:52] changing your mind on uh on open source
[00:57:54] you know models uh and and kind of you
[00:57:56] know the how many players there would be
[00:57:57] actually in that space and going after
[00:57:59] it. Anything else that like I I feel
[00:58:00] like you know we're constantly getting
[00:58:02] new information and having to to shift
[00:58:03] things like anything else in the last
[00:58:04] few months you feel like you've shifted
[00:58:05] your perspective on?
[00:58:06] >> I'm more bullish on RSI I think than I
[00:58:08] was uh that that's that's a change. Um
[00:58:11] but I think I think that and and and
[00:58:13] then like yeah I'm quite I think this
[00:58:16] notion that the open models are are
[00:58:17] going are going to go away to some
[00:58:19] extent I I I believe quite strongly now
[00:58:21] and I think I I didn't uh didn't really
[00:58:24] see that coming six months ago in the
[00:58:26] same way that I didn't see the rise of
[00:58:27] the open source models uh coming I think
[00:58:29] we were all very surprised by that past
[00:58:30] llama I think now the opposite is the
[00:58:33] same but nothing nothing beyond those
[00:58:35] >> one thing I've changed my mind on is is
[00:58:38] uh I think I've really pulled in my
[00:58:40] timelines in terms of the performance
[00:58:43] and improvement rate for robotic AI and
[00:58:46] and and robotic models. Um I would say
[00:58:50] six months ago, you know, whenever we
[00:58:51] chatted last, I probably would have been
[00:58:53] in the camp of like this is inevitable
[00:58:55] and it's massive market opportunity, but
[00:58:57] who knows how long it's going to take.
[00:58:58] It could be 18 months or it could be
[00:59:00] five years to this sort of, you know,
[00:59:02] mythical like GPT3 moment for general
[00:59:05] purpose robotics AI. And I feel like in
[00:59:08] just the past
[00:59:10] handful of months like these models have
[00:59:12] really crossed a threshold in terms of
[00:59:13] how well they're working. Um there's
[00:59:16] obviously still a long way to go but I
[00:59:17] think they've like robotic foundation
[00:59:20] models have reached a point now where
[00:59:22] they they are capable enough to be
[00:59:24] commercially viable across a lot of
[00:59:25] different use cases and like as they
[00:59:28] start to be deployed with customers and
[00:59:29] that data flywheel starts to spin like I
[00:59:31] think it's just going to accelerate. So
[00:59:33] I do I do now think that like we aren't
[00:59:35] far from this like so-called GPT3 moment
[00:59:38] in in robotics.
[00:59:39] >> I mean music to my ears but certainly I
[00:59:41] I think uh I think it's been really
[00:59:43] exciting to see uh a bunch of the
[00:59:44] progress in that space and um obviously
[00:59:46] yeah there's been a ton of activity
[00:59:47] around you know obviously in robotics I
[00:59:50] mean I think in bio material sciences I
[00:59:51] think people are definitely feeling uh a
[00:59:53] lot of progress in some of these other
[00:59:55] spaces. Um and so will be fascinating to
[00:59:57] to to see these next years. Um I guess
[01:00:00] my my last question for you guys is just
[01:00:01] you know I'm I'm shameless now going to
[01:00:03] ask for for an additional spicy
[01:00:05] prediction for the second the back half
[01:00:07] of the year um you know uh of of
[01:00:09] something you think by the end of the
[01:00:11] year uh will'll we'll all be realizing
[01:00:13] was uh was actually true.
[01:00:14] >> You know I'll take I'll take the API bet
[01:00:16] actually and this is a bit aggressive
[01:00:18] for it to happen this year versus next
[01:00:19] year. I feel a lot more confident saying
[01:00:21] that by the end of 27, but I I think
[01:00:23] it's I think there's a a very reasonable
[01:00:25] chance that we see probably anthropic.
[01:00:28] Um, but it could be open AI uh suspend
[01:00:30] API access for some period of time or or
[01:00:34] or or or heavily or otherwise heavily
[01:00:36] limit API access um for like a brief
[01:00:39] period. Um and that maybe is like the
[01:00:41] precursor to starting to see this happen
[01:00:43] more frequently uh down the line.
[01:00:46] >> That is a spicy take. I like that one.
[01:00:47] Yeah, if that it seems so it seems so
[01:00:49] unlikely today that if that does happen
[01:00:51] that'll yeah that'll be that'll be a
[01:00:52] pressure call.
[01:00:53] >> Timing is hard on that one. Uh I'm I'm
[01:00:55] confident that'll happen at some point
[01:00:57] whether it'll be in the back half of 26.
[01:00:59] This is the the downside of uh of
[01:01:00] options pricing but uh
[01:01:03] >> it's going to be hard to top the
[01:01:05] predicting same Alman's ouster.
[01:01:07] >> Yeah. Who else is out?
[01:01:08] >> Yeah, I think I think my predict Daria
[01:01:11] will still be at Antropic at the end of
[01:01:13] the year. Um, no, I think this is this
[01:01:15] yeah, this is a le less um less uh
[01:01:18] dramatic one and maybe this is probably
[01:01:21] less spicy these days because I think
[01:01:23] it's becoming increasingly evident to
[01:01:25] folks, but I think by the end of the
[01:01:26] year it will be like very obvious that
[01:01:29] anthropic is like a fledgling juggernaut
[01:01:33] in the making in the life sciences and
[01:01:36] and biology. Like it seems clear to me
[01:01:39] that that is like the next big direction
[01:01:41] that Anthropic is focusing on and and
[01:01:43] Anthropic has rightfully gotten a lot of
[01:01:45] praise and admiration for its focus and
[01:01:48] for like being so dialed in on coding
[01:01:51] and just knocking that out of the park
[01:01:53] and using that as like the stepping
[01:01:55] stone where where to leaprog OpenAI
[01:01:57] whereas OpenAI was kind of all over the
[01:01:59] place. Um and so I think that focus has
[01:02:01] been really valuable. I do think that
[01:02:03] like it's clear that life sciences is
[01:02:05] their next big bet and so you know on
[01:02:07] the one hand you could say does that
[01:02:09] represent like a fragmentation of focus
[01:02:11] that's going to be problematic for them.
[01:02:13] I I I kind of think that like it's their
[01:02:16] next big chapter after coding and it
[01:02:18] will be for the for the next several
[01:02:19] years to come. Um, and I think the
[01:02:22] really interesting question is like, and
[01:02:23] I know Jacob, you like you you are deep
[01:02:25] in the healthcare world, and I'm sure
[01:02:26] you have a lot of thoughts on this, but
[01:02:28] I I think really interesting question is
[01:02:30] like how far down that value chain is
[01:02:33] anthropic planning to go? Like there are
[01:02:35] plenty of rumors that I'm sure folks
[01:02:37] have heard that like Anthropic is
[01:02:39] setting up their own wet lab facilities
[01:02:41] uh to run and run their own experiments
[01:02:43] and collect data and like is that just
[01:02:45] to collect data to train models or are
[01:02:47] they thinking about or will they
[01:02:48] eventually be thinking about developing
[01:02:50] their own assets? Uh and it obviously as
[01:02:53] is generally the case in the space like
[01:02:55] it'll be a progression over time. But I
[01:02:57] do think though like you know may maybe
[01:02:58] this is more suited for like a
[01:03:00] three-year prediction but like I think
[01:03:02] in in the course of in the fullness of
[01:03:04] time Anthropic will become like one of
[01:03:07] the most important life sciences
[01:03:08] companies in the world.
[01:03:09] >> How much of an advantage do they have
[01:03:10] from what they've already done to date
[01:03:12] uh you know within life sciences right I
[01:03:14] mean obviously like you can use LMS to
[01:03:16] to be a co-pilot for for research but um
[01:03:19] it seems like the models themselves are
[01:03:20] actually quite different right?
[01:03:22] >> Yeah I I don't think they have a huge
[01:03:24] advantage today. I think their only
[01:03:26] advantage is like they're they're
[01:03:27] arguably the best AI research
[01:03:29] organization in the world and if they
[01:03:30] choose to point that capability at
[01:03:33] >> if only there was like a visionary CEO
[01:03:35] uh at a top AI lab who had been
[01:03:37] interested in bio for some time and like
[01:03:39] actually spent some time on it and
[01:03:40] started a company on it years ago. Uh
[01:03:42] that that might be pretty interesting to
[01:03:44] uh to
[01:03:45] >> Okay, that's I'll revise my prediction.
[01:03:47] Anthropic and Isomorphic Labs will be
[01:03:50] two of the most important life sciences
[01:03:51] companies because you're you're right
[01:03:53] about ISO but I think anthropic can get
[01:03:55] there and I do I do think Daario has
[01:03:57] also been passionate about biology for a
[01:03:59] long time and you know who's a
[01:04:00] neuroscience uh PhD and so forth.
[01:04:02] >> Totally. I mean I think like the the
[01:04:03] thing I do take in your in in that that
[01:04:05] is real is I think bio actually probably
[01:04:08] is one of the only opportunities that is
[01:04:10] large enough. I mean I obviously the
[01:04:11] anthropic folks are interested in it
[01:04:12] from a mission perspective. been so
[01:04:13] consistent in that and it's one of the
[01:04:15] coolest impacts of of AI from like an
[01:04:17] impact. Uh it also is probably one of
[01:04:18] the only TAMs that is large enough to
[01:04:20] justify like that level of you know you
[01:04:22] got code you've got like your general
[01:04:24] co-pilot for knowledge work and like
[01:04:26] >> I don't know there's not that many that
[01:04:27] are as uh that that are as large and so
[01:04:29] I also think the you know the
[01:04:30] opportunity could be massive. We'll see
[01:04:32] the the you know bio's hard. Um there's
[01:04:34] there it doesn't you the feedback loops
[01:04:36] on on data and and actually getting
[01:04:38] longitudinal data just has a a you know
[01:04:41] a time to it that is uh that is isn't
[01:04:43] even you know even something like
[01:04:44] robotics is much easier right because
[01:04:46] you can at least immediately get the
[01:04:47] feedback loop on whether something
[01:04:48] worked or not.
[01:04:49] >> Yeah
[01:04:49] >> I think domain expertise also matters a
[01:04:52] lot more than many AI folks often think.
[01:04:55] So I think there's a question of how
[01:04:56] enthropic approaches this is anthropic
[01:04:58] approach this by going to hire a bunch
[01:04:59] of like really fantastic um biologists
[01:05:02] and then pair them with the really
[01:05:03] strong AI researchers and and do as much
[01:05:05] there um versus just trying to throw the
[01:05:08] AI researchers at it. Uh I think that is
[01:05:11] one thing that uh you know Demis did
[01:05:14] very well with alpha fold and then
[01:05:16] isomorphic is is not assuming that kind
[01:05:19] of the AI researchers alone can can do
[01:05:21] that and I've seen lots of other uh labs
[01:05:23] kind of make that mistake. Um, but I I
[01:05:26] think the domain expertise matters a
[01:05:27] lot. I think it's gonna be a hard a hard
[01:05:28] one for Anthropic to do, but if they can
[01:05:30] do it, if they can hire that team, it's
[01:05:31] obviously a huge uh huge boom, but I
[01:05:33] would bet probably more an isomeorphic
[01:05:35] right now.
[01:05:36] >> Well, guys, this has been a ton of fun.
[01:05:38] I really appreciate you uh you you both
[01:05:40] taking the time to jam on this and we
[01:05:42] had to do better. You know, no six
[01:05:43] months in between this one and the next
[01:05:44] R. You're closing too many candidates.
[01:05:46] Uh next time we'll uh we'll do it
[01:05:48] sooner.
[01:05:49] >> R is the only one with an actual job
[01:05:50] that we have to schedule around.
[01:05:52] >> Yeah. I don't know. you came in with
[01:05:53] some some really good takes on uh on
[01:05:55] lithography there. I was like that
[01:05:56] someone's been doing some work over
[01:05:58] there. I I was out of left field.
[01:06:00] >> Yeah, seriously. Til I I I learned I
[01:06:02] learned a lot about alternate alternate
[01:06:04] approaches.
[01:06:04] >> I'm Jacob Efron and this has been
[01:06:06] Unsupervised Learning, a podcast where I
[01:06:08] get to talk to the smartest people in AI
[01:06:10] and ask them tons of questions about
[01:06:12] what's happening with models and what it
[01:06:13] means for businesses in the world. As I
[01:06:15] hope is clear, I have a ton of fun doing
[01:06:17] this. It's a nights and weekends project
[01:06:19] in addition to my day job as an investor
[01:06:21] at Redpoint. But our ability to get
[01:06:22] these incredible guests on really comes
[01:06:25] from folks like you subscribing to the
[01:06:26] podcast, sharing it with friends. It's
[01:06:28] really what ultimately makes this whole
[01:06:29] thing work. And so, please consider
[01:06:31] doing that. And thank you so much for
[01:06:33] your support and listening. We'll see
[01:06:34] you next episode.
