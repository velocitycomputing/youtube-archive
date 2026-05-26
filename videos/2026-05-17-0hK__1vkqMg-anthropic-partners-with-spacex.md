---
video_id: 0hK__1vkqMg
title: "Anthropic Partners With SpaceX AI, Leopold's $5.5B Bet, and the Singularity Economy | EP #255"
channel: Peter H. Diamandis
url: "https://www.youtube.com/watch?v=0hK__1vkqMg"
watched_date: 2026-05-17
watched_at: "2026-05-17T12:00:00Z"
watch_count: 1
duration_seconds: 7851
source: youtube-history-browser
history_label: May 17
history_order: 176
watched_at_precision: date-from-history-label
watched_percent: 20
estimated_watched_seconds: 1570
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Anthropic achieved an unprecedented 80x growth in Q1 2026, with annualized revenue jumping from $9 billion to $30-40 billion, expected to reach $100+ billion by year-end and potentially $1 trillion by mid-2027. The company signed a blockbuster deal with Elon Musk to take over SpaceX's Colossus 1 datacenter in Memphis—containing 220,000 H100 GPUs—which immediately allowed Anthropic to double Claude's code rate limits. The podcast panel discussed how AI demand is fundamentally outpacing compute supply: 8 billion people plus power users wanting hundreds of agents each means demand far exceeds the 1.6 million concurrent threads this hardware provides. Meanwhile, Leopold Ashenbrener's $5.5 billion fund, previous XAI developments, and competitive pressure from Google suggest the frontier AI landscape is consolidating around Anthropic and OpenAI, with Elon's SpaceX becoming a hyperscaler rather than competing as a frontier lab. Anthropic also published research showing every Claude model since Haiku 4.5 achieves perfect scores on agentic misalignment evaluation, eliminating previous blackmail behaviors through constitutional training.

For users, the immediate implications are: expect continued pricing pressure and potential rate increases as demand outstrips Claude token supply, making the recently doubled rate limits a temporary relief; consider on-premises model deployment or enterprise contracts (like AWS/Google partnerships) if latency is critical, since public API response times show severe queuing delays; and plan for agents and autonomous systems using Claude to become mission-critical infrastructure soon, as organizations from Eli Lilly to enterprises are securing private compute capacity. The research on alignment improvements removes a major safety concern for deploying Claude at scale in autonomous agent scenarios.

## Transcript

[00:00:00] Anthropic is taking over all of SpaceX's
[00:00:03] Colossus 1 data center in [music]
[00:00:04] Memphis. And this immediately allowed
[00:00:06] Anthropic to double claude code rate
[00:00:08] limits.
[00:00:09] >> I think Grock is on life support.
[00:00:11] >> So this is Elon who had been for, you
[00:00:14] know, the past year uh shit-talking
[00:00:16] Anthropic. Here he is now, you know,
[00:00:20] backing them and supporting them. In one
[00:00:22] way, Elon's getting revenge against Open
[00:00:25] AI by helping Anthropic win. The enemy
[00:00:27] of my enemy is my friend is the exact
[00:00:29] quote from uh from Elon
[00:00:30] >> Leopold Ashen Brener who was famously
[00:00:33] fired from OpenAI on their alignment
[00:00:35] team and is now running a $5.5 billion
[00:00:38] fund 2 years later. Anthropic hits 80x
[00:00:43] growth for this quarter and outruns
[00:00:45] their compute.
[00:00:45] >> You can find a whole litany of things
[00:00:47] that are about to explode in demand.
[00:00:50] >> The demand I don't see it slowing down
[00:00:52] as a whole. chips and the energy layer
[00:00:56] and the infrastructure. Right? This is
[00:00:58] the singularity loop.
[00:01:01] >> Now that's a moonshot ladies and
[00:01:03] gentlemen.
[00:01:06] >> Everybody welcome to moonshots. Another
[00:01:08] episode of WTF just happened in tech.
[00:01:10] I'm here with my extraordinary friends
[00:01:13] and dear brothers DB2 our wizard of AI
[00:01:15] investing Ismail emperor of exponentials
[00:01:18] and of course our resident genius AWG.
[00:01:21] I'm Peter D. Mandis your host. And today
[00:01:23] we've got an incredible program of
[00:01:25] stories that should get you pumped up
[00:01:27] about the singularity. Excited. This is
[00:01:29] not politics. This is just science and
[00:01:31] technology driving us towards the
[00:01:33] singularity. So gentlemen, uh, excited
[00:01:36] to see you here. See, I have to ask,
[00:01:39] where on the planet are you today?
[00:01:41] >> I just landed back. I just landed I just
[00:01:44] landed back from Montreal and I was
[00:01:46] given a Canadians jersey because I'm
[00:01:48] actually a Montreal native and a massive
[00:01:50] Montreal Canadians fan. uh because I
[00:01:52] grew up there and so they Montreal
[00:01:54] >> like a small small round ball or a pock
[00:01:57] [laughter]
[00:01:59] that's the hard round thing that that
[00:02:01] immigrants like me our ankles never
[00:02:03] quite managed to but in Canada you had
[00:02:06] to skate if you otherwise they took your
[00:02:08] passport away so I used to play a bit of
[00:02:09] hockey
[00:02:11] >> hey we got
[00:02:13] let's do some pond hockey up in Vermont
[00:02:14] it's all time favorite thing to do
[00:02:17] >> um so the folks the folks gave me this
[00:02:19] jersey that I had to wear it because
[00:02:20] we're right in the live this stuff. So,
[00:02:22] anybody in Buffalo, I'm rooting for the
[00:02:24] Canadians, but I'm the longest suffering
[00:02:26] Bills fan in history. So, there's that.
[00:02:29] [laughter]
[00:02:29] >> Let's see your teeth. I want to see
[00:02:31] which ones are fake.
[00:02:33] >> You know, I just I've missed the
[00:02:35] complete, you know, gene sequence on
[00:02:38] sports. Sorry. Um Dave, good to see you
[00:02:41] back in the nest and as always, Alex,
[00:02:43] good to see your virtual environment.
[00:02:45] Um, you know,
[00:02:46] >> and virtual self. What's the difference
[00:02:48] really at this point? [laughter] Yeah.
[00:02:51] >> Uh uh today we
[00:02:52] >> I know you I know you go to your kids
[00:02:54] baseball games. You're probably chewing
[00:02:55] tobacco and spitting it and you have a
[00:02:57] dual life. That's my That's what I
[00:02:58] think. [laughter]
[00:03:00] >> Uh we have an incredible uh incredible
[00:03:02] show today. You know, we're going to be
[00:03:03] kicking it off with the demand for AI is
[00:03:05] like off the rails, outstripping supply.
[00:03:08] You know, Claude is continuing to
[00:03:10] disrupt sector after sector with the
[00:03:11] great unhobbling. Uh Google is joining
[00:03:14] our push towards Earth's Dyson swarm.
[00:03:17] We'll be jumping into the singularity
[00:03:18] economy. you know what are the sectors
[00:03:20] that are providing outsized financial
[00:03:22] returns during this supersonic tsunami.
[00:03:25] We're going to cover uh a topic near and
[00:03:27] dear to my heart which is a very simple
[00:03:30] very powerful concept to ensure AI
[00:03:32] alignment so we can deliver a pdoom that
[00:03:35] is less than zero. Thank you Alex for
[00:03:38] that meme. I love that pdoom less than
[00:03:40] zero.
[00:03:40] >> We need t-shirts for it.
[00:03:42] >> We do. I saw the t-shirt you made. We're
[00:03:44] going to have to like put that up for
[00:03:45] people to be able to take down. Anyway,
[00:03:48] >> Peter, if if if no one makes it,
[00:03:50] everyone dies. [laughter]
[00:03:52] >> Oh, no. And towards the end of this pod
[00:03:55] today, we're gonna be talking about the
[00:03:56] recent disclosures by the White House
[00:03:58] on, let's call them UFOs versus UAPs. Uh
[00:04:02] the White House is saying they're here,
[00:04:04] but who are they? Where are they? Where
[00:04:07] are they from? And when are you going to
[00:04:08] come and pick me up and take me for a
[00:04:10] ride? So, uh that's going to be some fun
[00:04:14] conversations today. Let's begin uh with
[00:04:17] a important conversation today.
[00:04:20] Anthropic uh is outpacing uh their
[00:04:24] ability to supply tokens. So Anthropic
[00:04:26] hits 80x growth for this quarter and
[00:04:29] outruns their compute. Anthropic
[00:04:31] developer conference last week CEO Dario
[00:04:34] Amade revealed that Anthropic has
[00:04:36] experienced an 80fold growth in Q1 of
[00:04:39] 2026
[00:04:41] uh outpacing what they expected as a 10x
[00:04:43] growth. I mean, you don't see this in
[00:04:45] Silicon Valley. You don't see this
[00:04:46] anywhere. Maybe maybe Dave, for some of
[00:04:49] your early companies, you're seeing that
[00:04:50] kind of growth. But here, uh, they're,
[00:04:52] you know, their annualized revenue run
[00:04:55] rate jumped from 9 billion at the end of
[00:04:57] 2025 to 30 billion in April. It's now
[00:05:01] north, I think, 40 billion in May. Uh,
[00:05:04] and the here are the numbers. They
[00:05:06] expect or it's expected they could hit a
[00:05:08] h 100red billion of ARR by the end of
[00:05:11] 2026 and potentially a trillion by the
[00:05:15] end or mid 2027 making it the most
[00:05:18] valuable company on the planet. Um and
[00:05:20] just to hit some numbers real quick and
[00:05:22] then turn over to you Dave for the first
[00:05:24] conversation at a 30 billion ARR at a
[00:05:27] 40x uh multiple it's being valued today
[00:05:31] at 1.2 trillion. If they hit a hundred
[00:05:33] billion by the end of this year,
[00:05:35] Anthropic will be at a $4 trillion
[00:05:37] valuation. And if they hit a1 trillion
[00:05:41] AR in 2027, a $40 trillion valuation, I
[00:05:45] mean,
[00:05:47] [laughter] you know, this this is the
[00:05:49] singularity by definition. Insane. Dave,
[00:05:52] >> over a year ago, Peter, uh, at that
[00:05:55] family office conference in London, uh,
[00:05:57] Yeang was saying to all these wealthy
[00:05:59] families, you got to get invested in
[00:06:01] this. you got to get in the game. And
[00:06:04] everybody was like, at a hundred billion
[00:06:06] dollar plus valuation, that's utterly
[00:06:07] insane. You can't possibly, it's way too
[00:06:10] late. You can't get into it. But, you
[00:06:12] know, I I don't blame them because these
[00:06:13] numbers are so unprecedented and and
[00:06:15] people don't really do a good job job of
[00:06:17] judging million, billion, trillion. It
[00:06:19] does not, you know, it's not intuitive.
[00:06:21] These numbers are are so far out of the
[00:06:24] realm of history. I mean, just massively
[00:06:27] bigger than any prior IPO or valuation.
[00:06:29] And so I don't blame people for for
[00:06:31] being scared, but you got to get used to
[00:06:33] the fact that this goes to infinity.
[00:06:35] >> Yeah. [laughter]
[00:06:35] >> The the the demand the demand for AI
[00:06:39] >> is not going to saturate. It goes to
[00:06:41] infinity. So you got to rethink the way
[00:06:43] you decide whether to be involved in
[00:06:45] these things or not. So they all they
[00:06:47] all skipped it. [laughter]
[00:06:49] >> Now I'm sure they regret it.
[00:06:51] >> Yeah.
[00:06:51] >> Yeah. 10x 10x in a year up to 1.2
[00:06:54] trillion.
[00:06:55] >> Alex, what do you make of all this?
[00:06:56] >> It's all about the enterprise, Peter.
[00:06:58] So, Anthropic was the first arguably
[00:07:01] major Frontier Lab to recognize that
[00:07:04] offering ultra high enterpriseoriented
[00:07:07] value tokens was the path to success
[00:07:10] here. As I've mentioned on the pod
[00:07:12] previously, OpenAI has since had to
[00:07:14] pivot to copy call it the anthropic
[00:07:16] strategy of offering up highgrade
[00:07:19] enterprise tokens for code generation
[00:07:21] and now for other so-called white labor
[00:07:25] tasks. And this is what we're seeing.
[00:07:27] We're seeing an insatiable demand for
[00:07:30] compute to the extent that that compute
[00:07:32] can be turned into high dollar value
[00:07:35] tokens that are replacing the services
[00:07:38] economy. And so US GDP is what 30
[00:07:42] trillion or so. If if we see the the
[00:07:45] continued exponential maybe super
[00:07:48] exponential increase in capabilities and
[00:07:51] especially the increase in as meter
[00:07:54] measures it autonomy time horizons which
[00:07:57] are pushing the dozens of hours of
[00:08:01] autonomy at this point. I I think we're
[00:08:03] seeing the beginnings maybe even the the
[00:08:05] beginning of the middle of the
[00:08:07] replacement of white collar labor and I
[00:08:10] mean Elon that's going to be insanely
[00:08:12] valuable. Elon said doubledigit GDP
[00:08:15] growth in two years and tripledigit
[00:08:17] within five years. See, how are you
[00:08:20] feeling about this? Are are you putting
[00:08:22] your money into these uh into these
[00:08:24] areas? Are you excited about it?
[00:08:26] >> Full full disclosure, I don't have
[00:08:28] investments in any of these labs. I
[00:08:30] probably have some Google stock from
[00:08:32] some of my funds or something, but
[00:08:33] nothing uh explicit, which is a huge
[00:08:37] problem watching all these numbers go
[00:08:39] up. Uh I did a little bit of analysis,
[00:08:41] you know, and you have uh Proctor and
[00:08:43] Gamble having roughly the same revenues
[00:08:46] with 15 billion of profit and their
[00:08:48] market cap is like uh a tenth of this
[00:08:51] because there's no upside, right? They
[00:08:54] grew 2% year-over-year. Everybody's
[00:08:56] like, well, and so this is like these
[00:08:58] guys grow 2% an hour. Um and so
[00:09:03] yeah, literally. So it's such a huge
[00:09:06] difference in in mentality and there's
[00:09:09] no reason why and what's I think was the
[00:09:11] most incredible thing is the fact that
[00:09:13] this is real money coming in. This is
[00:09:15] not hope. This is not a judgment call
[00:09:18] etc. This is actual measurable dollars
[00:09:20] coming in. And so it's incredible to
[00:09:22] see.
[00:09:23] >> Yeah. I want to hit two point to be
[00:09:24] fair. A year a year and a half ago they
[00:09:26] were incinerating money in anticipation
[00:09:28] of this growth. So it was a little bit
[00:09:29] of a scary a scary situation. And now
[00:09:32] it's not scary at all for Anthropic or
[00:09:34] for also, you know, they're they're
[00:09:36] completely sold out. And I expect
[00:09:38] they'll continue to ramp, but the chips
[00:09:41] are completely saturated and sold out.
[00:09:43] So you would normally say, well, doesn't
[00:09:44] that mean the revenue will cap out, but
[00:09:46] one, they can charge more, and two,
[00:09:48] they're optimizing the software, so
[00:09:50] they'll squeeze out, you know, another
[00:09:51] 10x or more while we're waiting for the
[00:09:54] the chip supply to catch up.
[00:09:55] >> Yeah.
[00:09:56] There's no doubt that that you you'll
[00:09:58] see on the left chart that chat GPT has
[00:10:00] fallen off the curve a little bit
[00:10:02] compared to OpenAI, but they they have a
[00:10:04] lot of compute lined up at OpenAI um
[00:10:08] compared to anthropic that is. So, uh I
[00:10:10] would expect that OpenAI's revenues will
[00:10:12] skyrocket too because everything is sold
[00:10:15] out anyway and and GPT 5.5 is really
[00:10:18] really good.
[00:10:19] >> So, uh it's going to be who can get the
[00:10:20] compute.
[00:10:21] >> Dave, two points. One, I think it's
[00:10:23] important for folks to realize this
[00:10:26] isn't growth uh for Anthropic because
[00:10:29] they're getting more users. Their users
[00:10:32] are creating more uses. So, everybody's
[00:10:34] just consuming more tokens and that's a
[00:10:37] really important element. I agree with
[00:10:38] your point that we're likely to see
[00:10:41] potentially a rate hike. I mean, if
[00:10:43] there's if people are trying to consume
[00:10:45] and you can't pump enough tokens out,
[00:10:47] they'll start charging more. But there's
[00:10:49] an interesting analogy, right? So in the
[00:10:51] 100 years ago when electricity was first
[00:10:53] becoming sort of distributed uh through
[00:10:56] the US back 100 years ago in 1925 I
[00:10:58] looked at the number was 30% of the US
[00:11:00] had electricity and 30% of the US had
[00:11:02] phones and what happens [clears throat]
[00:11:04] is that in the same way people kept
[00:11:07] finding more uses of electricity you
[00:11:09] know it was first it was for lighting
[00:11:10] homes then they replaced uh you know
[00:11:13] steam engines electrified you know
[00:11:15] elevators refrigerators radios
[00:11:17] appliances the same thing's going on
[00:11:19] here people are just finding more uses
[00:11:21] for the tokens. Uh, and it's insatiable
[00:11:24] and growing in multiple dimensions. More
[00:11:27] users and more uses. Well, in a minute
[00:11:30] or two, we'll go through some numbers,
[00:11:31] too, and you'll you'll come away with
[00:11:33] the conclusion that we're a tiny
[00:11:35] fraction of 1% of the use cases have
[00:11:37] been deployed so far, but we we'll get
[00:11:39] to that in a minute. But the demand is
[00:11:41] way outstripping the supply, though. Hey
[00:11:43] everybody, you may not know this, but
[00:11:44] I've got an incredible research team.
[00:11:46] And every week myself, my research team
[00:11:49] study the meta trends that are impacting
[00:11:50] the world. Topics like computation,
[00:11:53] sensors, networks, AI, robotics, 3D
[00:11:55] printing, synthetic biology. And these
[00:11:57] Metatrend reports I put out once a week
[00:11:59] enable you to see the future 10 years
[00:12:02] ahead of anybody else. If you'd like to
[00:12:04] get access to the Metatrends newsletter
[00:12:06] every week, go to
[00:12:07] dmandis.com/metatrends.
[00:12:09] That's diamandis.com/metatrends.
[00:12:12] All right. Uh, our next story here is
[00:12:15] Anthropic is buying compute to feed the
[00:12:19] beast. Uh, and so there are two elements
[00:12:21] here. The first is just the appetizer
[00:12:24] that Anthropic signed a $ 1.8 billion
[00:12:26] 7-year compute deal with AI. Um, and
[00:12:30] this is AI's largest deal. It popped the
[00:12:32] stock, you know, 25% on the first day.
[00:12:35] But I think the real [clears throat]
[00:12:36] story that we should be discussing here
[00:12:37] is the deal that Anthropic cut with
[00:12:40] Elon. So, uh, this is a blockbuster
[00:12:43] deal. Enthropic is taking over all of
[00:12:45] SpaceX's Colossus One data center in
[00:12:47] Memphis. If you remember, Elon had built
[00:12:49] this center in 122 days, very famously
[00:12:52] from, you know, ground up, beat
[00:12:54] everybody's expectation. It's filled
[00:12:56] with H100s. And this immediately allowed
[00:12:59] Anthropic to double claude code rate
[00:13:01] limits so people could actually utilize
[00:13:04] it. And I think the message here is that
[00:13:06] SpaceX or SpaceX AAI has just now become
[00:13:09] a hyperscaler. Um you know at the same
[00:13:12] time I think uh of note Grock has not
[00:13:16] seen uh sort of a large uptake in usage.
[00:13:21] I mean you can use it in your Tesla but
[00:13:23] I don't know that many people who are
[00:13:24] relying on on Grock for their for their
[00:13:27] uh you know AI engine. Not sure if you
[00:13:30] guys play with it much at all, but Grock
[00:13:32] was making like I think it was 11% use
[00:13:35] of Colossus 1. And what a great deal.
[00:13:38] Take this asset, sell it. Anthropic,
[00:13:40] that's what they need. SpaceX is
[00:13:42] getting, you know, probably another
[00:13:43] three or four billion dollars of revenue
[00:13:45] just before their IPO. Couldn't be
[00:13:47] better. Dave, what do you make of it?
[00:13:48] >> Yeah, strange bedfellows. You know,
[00:13:50] normally you'd think they're arch
[00:13:51] competitors, but uh you know, Elon
[00:13:54] doesn't have the user base to chew up
[00:13:55] this compute. Anthropic is desperate for
[00:13:57] more compute. I'm sure a lot of the
[00:13:58] margin will go back to Elon now. Um, and
[00:14:02] you know, the the new Colossus 2 is
[00:14:04] where the training is anyway. So, it was
[00:14:06] going to sit idle. So, let's go ahead
[00:14:08] and partner even though in theory we're
[00:14:09] arch competitors, but anything to try
[00:14:11] and keep up with Google, I think on both
[00:14:13] sides.
[00:14:14] >> Uh, so the numbers here are pretty
[00:14:17] >> yeah, friendies, you know, the enemy of
[00:14:20] my enemy is my friend is the exact quote
[00:14:21] from uh from Elon. Uh but the numbers
[00:14:24] here, you know, okay, this gives us
[00:14:26] 220,000 GPUs.
[00:14:29] Uh a GPU will serve about eight
[00:14:31] concurrent threads if you're using a max
[00:14:33] model like an Opus 4.7 Max. So you got
[00:14:36] about eight threads or eight agents per
[00:14:38] GPU. So you're only buying about 1.6
[00:14:41] million concurrent threads. 8 billion
[00:14:44] people around the world are going to
[00:14:45] want at least one agent at least. But
[00:14:49] you know the power users now want a
[00:14:51] hundred or more agents running and and I
[00:14:54] think very soon a person can
[00:14:55] productively use a thousand concurrent
[00:14:57] agents like an engineer or a builder or
[00:15:00] a designer or an architect and and so so
[00:15:03] you compare the demand to the supply and
[00:15:05] it's it's just it's just laughable.
[00:15:07] There are nowhere near enough GPUs to
[00:15:10] serve up all the agents that people
[00:15:11] want. And so as a byproduct of that, if
[00:15:14] you own your own hardware, so if you buy
[00:15:16] like an NV72,
[00:15:18] uh, so you got your big old Nvidia rack,
[00:15:20] >> you pay [clears throat] your your four
[00:15:22] million bucks for it, it'll serve up an
[00:15:24] agent for you in about 50 milliseconds.
[00:15:27] Go to Anthropic, turn on Claude Opus
[00:15:29] 4.7, ask it a question, and see how long
[00:15:31] it takes to start answering. And you'll,
[00:15:34] you know, I'm often sitting there for a
[00:15:36] minute, minute and a half before it even
[00:15:37] starts generating tokens. And it should
[00:15:40] be spitting out about 200 tokens a
[00:15:42] second.
[00:15:43] >> So I should see paragraphs popping up
[00:15:44] like pop pop pop pop pop. And what I'm
[00:15:47] actually seeing, I can see the words
[00:15:48] coming out like, you know, trickling
[00:15:51] out. So clearly
[00:15:53] >> dialup.
[00:15:54] >> Yeah. Yeah. It's like they they're just
[00:15:56] way more users than they can possibly
[00:15:58] serve.
[00:15:58] >> Do you think it's going to come on prem?
[00:16:00] Do you think we're going to start to see
[00:16:01] more people
[00:16:02] >> Oh, yeah. Yeah, models on prem.
[00:16:05] >> Yeah, totally. Totally. Eli Liy just
[00:16:06] committed a billion dollars to buy
[00:16:08] Nvidia GPUs for internal use because
[00:16:11] everyone's worried sick about having the
[00:16:13] supply and the only way you can be sure
[00:16:14] you'll have the supply is to get your
[00:16:16] own capacity. The the problem is, you
[00:16:18] know, you can't run Anthropic on your
[00:16:20] own internal servers unless you have
[00:16:22] some super special relationship like AWS
[00:16:25] or or Google uh Google Vert.ex has with
[00:16:28] Anthropics. So, so then you get this
[00:16:29] tension between I want my own hardware.
[00:16:31] Oh, wait. I can only run Chinese models
[00:16:33] on it. So very complicated scenario
[00:16:36] right now.
[00:16:36] >> They'll fix that though. The demand is
[00:16:38] so crazy. That's going to get fixed.
[00:16:40] Gemini already runs on private clouds
[00:16:42] and so on.
[00:16:43] >> Yeah, you know, uh I love Elon's tweet
[00:16:47] which I put up on the slide here. You
[00:16:49] know, uh Claude is good for humanity.
[00:16:51] I'm impressed by their team. I'll
[00:16:53] actually try and read what it says here.
[00:16:54] It says by So this is Elon who had been
[00:16:57] for, you know, the past year uh
[00:16:59] shit-talking anthropic. All right. And
[00:17:02] here he is now, you know, backing them
[00:17:05] and supporting them. And he says, "By
[00:17:08] the way, of background for those who
[00:17:09] care, I spent a lot of time last week
[00:17:12] with the senior management, uh, senior
[00:17:14] members of the anthropic team to
[00:17:16] understand what they do to ensure Claude
[00:17:18] is good for humanity and was impressed.
[00:17:21] Everyone I met was highly competent and
[00:17:23] cared great deal about, you know, doing
[00:17:26] the right thing. So, I think, you know,
[00:17:29] he's putting forward his personal brand
[00:17:33] that he's basically supporting AI to
[00:17:36] make sure it's safe for humanity. And by
[00:17:38] the way, I I don't know how this guy
[00:17:40] handles all that he has, right? He's in
[00:17:42] the middle of a lawsuit. He's getting
[00:17:44] called up to go to China with Trump and
[00:17:46] he's still handling all of these things.
[00:17:49] I mean, how how many super duper AGI
[00:17:52] agents has he got working for him at
[00:17:53] this point? [laughter] It's crazy.
[00:17:55] >> Yeah, he's a case study, isn't it? It's
[00:17:56] just remarkable. Um, but I I have to say
[00:17:59] I do believe I know there are a lot of
[00:18:00] Elon haters out there, but I I 100% know
[00:18:03] in my heart that he's genuine about what
[00:18:05] he's saying here. He cares tremendously
[00:18:07] about safety and the future of humanity.
[00:18:10] And he actually would not give this
[00:18:12] compute to Daario if he didn't think.
[00:18:14] >> But Dario is the other guy that that is
[00:18:16] also totally focused on safety and and
[00:18:19] human benefit. So, it's actually a nice
[00:18:21] [clears throat] match. these bedfellows
[00:18:23] just one point then I want to hand it
[00:18:24] over to you Alex to speak about this you
[00:18:26] know so in one way Elon's getting
[00:18:29] revenge against open AI by helping
[00:18:31] anthropic win um and Anthropic uh and
[00:18:35] Google are now the forces for good in
[00:18:38] one sense uh against you know people's
[00:18:41] belief against open eye so interesting
[00:18:44] people tend to villainize and make you
[00:18:46] know and sort of create uh opposing
[00:18:49] sides in this competition
[00:18:52] Alex, this is not just about Colossus 1.
[00:18:55] This is also about orbital data centers,
[00:18:57] I bet. What are your thoughts here?
[00:18:59] >> I think rock is on life support. I I
[00:19:02] parse this announcement and I connect it
[00:19:04] with SpaceX's also recent announcement
[00:19:07] of the $60 billion plus de uh deal with
[00:19:10] cursor. And I infer that Grock as on
[00:19:14] life support and that XAI which has of
[00:19:17] course now also been dissolved as part
[00:19:19] of this arrangement is is no longer
[00:19:22] necessarily aspiring to be a frontier
[00:19:24] lab. It's it's an interesting sort of
[00:19:27] contorted 3D chess game I think that
[00:19:29] Elon and his entities have played. It
[00:19:32] might look something like the formation
[00:19:34] of Colossus 1 initially by redirecting
[00:19:37] GPUs that were, as I understand it, from
[00:19:40] public reporting originally intended for
[00:19:42] use at Tesla, redirecting them to form
[00:19:45] XAI and Colossus 1 and then using
[00:19:49] Colossus 1 to train the initial Gro
[00:19:51] series of models and then using enough
[00:19:54] of Grock's benchmark wins, open PNS,
[00:19:57] maybe a bit of benchmaxing, closed PNS
[00:20:00] to to motivate the capital needed to
[00:20:02] build Colossus 2, then turn Colossus 1
[00:20:06] over to Anthropic, basically becoming a
[00:20:09] hyperscaler, and then one could imagine
[00:20:12] this entire uh I think gesturing at the
[00:20:14] future with a tip of the hat process
[00:20:17] playing out over again where Colossus 2
[00:20:20] gets turned over to another Frontier
[00:20:22] Lab, probably anthropic, probably not
[00:20:24] Open AI, unless there's some dramatic
[00:20:26] resolution to the lawsuit, probably not
[00:20:29] Google either. And Elon is using his own
[00:20:33] frontier hyperscaler capabilities right
[00:20:35] now in land soon in space to to train
[00:20:39] in-house models. But to the extent the
[00:20:41] in-house models like rock aren't
[00:20:43] ultimately competitive, he becomes a
[00:20:45] hyperscaler and a hyperscaler in space.
[00:20:47] And I I think it's probably a pretty
[00:20:49] good deal for SpaceX AI as well. I'm not
[00:20:52] even sure SpaceX AI really needs its own
[00:20:55] competitive frontier models. Just like
[00:20:57] Nvidia, still largest company in the
[00:21:00] world by market cap. It has its own
[00:21:02] frontier models, but they're not
[00:21:04] terribly popular compared to to the pure
[00:21:07] play open AIS or anthropics of the
[00:21:09] world. And yet, they're doing incredibly
[00:21:11] well. So one could imagine SpaceX AI
[00:21:14] plus the terra fab becoming sort of a
[00:21:16] super Nvidia combined with coreweave
[00:21:18] combined with AWS deployed into the
[00:21:21] Dyson swarm not really needing its own
[00:21:23] frontier model. And Alex we've seen in
[00:21:26] all of tech history basically it's a
[00:21:28] duopoly typically maybe sometimes three
[00:21:31] players. So if it's open AI and
[00:21:34] anthropic and Google as a three players,
[00:21:36] you know, Elon basically leans in and
[00:21:39] supports the winner that he wants.
[00:21:41] >> And maybe not even Google. Like we
[00:21:43] started with five frontier labs, open
[00:21:45] AAI, Anthropic,
[00:21:47] Google Deep Mind, XAI, uh, and Meta. And
[00:21:52] Meta is seemingly out of the running.
[00:21:54] And XAI now just dissolved part of SP
[00:21:58] SpaceX AI. Gro is seemingly being turned
[00:22:01] over to cursor just dissolved. Query
[00:22:03] whether Google is going to be able to
[00:22:06] remain competitive or not. The the
[00:22:07] public reporting is so we have IO next
[00:22:10] week and the rumor is that Google is
[00:22:13] going to announce a new Gemini model
[00:22:15] that's maybe GPT 5.5 class but not
[00:22:18] mythos class. I
[00:22:19] >> I would not bet against Google. I
[00:22:22] >> I'm not betting against anyone but I do
[00:22:23] think this is a rat race and it's
[00:22:25] becoming extremely competitive.
[00:22:27] >> Yeah. Yeah. I got a dough question for
[00:22:29] you, Alex. All right,
[00:22:31] >> I'll give you two scenarios. Tell me
[00:22:32] which one is going to play out. Scenario
[00:22:34] number one is Elon has a massive amount
[00:22:36] of compute and keeps accumulating it and
[00:22:38] then he starts building in space. Uh,
[00:22:40] but his algorithms are way behind
[00:22:42] Anthropic. Um, so Anthropic keeps
[00:22:46] publishing better and better models, but
[00:22:47] those models then get really good at
[00:22:49] designing new AI algorithms, and Elon
[00:22:51] just takes that intelligence and deploys
[00:22:53] it on his superior hardware. Uh scenario
[00:22:56] two is anthropics models are
[00:22:58] self-improving at an incredible
[00:23:00] exponential singularity rate and no
[00:23:04] matter how much Elon takes their best
[00:23:06] thing that they publish it's not good
[00:23:08] enough to catch up to the exponential
[00:23:10] self-improvement going on at anthropic.
[00:23:12] So all this is happening in a very short
[00:23:14] timeline say six months from now is
[00:23:17] which which scenario plays out control
[00:23:19] of the hardware brings the best AI back
[00:23:21] to you or no control of the software
[00:23:26] self-improving gives you a never- ending
[00:23:27] lead.
[00:23:28] >> According to my magic eightball there
[00:23:30] are two regimes in the future the
[00:23:32] near-term and the long-term. in the near
[00:23:35] term, which is to say before we arrive
[00:23:37] at the perfect algorithm, the perfect AI
[00:23:40] algorithm, then software scaling,
[00:23:42] algorithmic scaling matters more. And
[00:23:45] so, uh, in the near term, but prior to
[00:23:47] the discovery of wherever it is that
[00:23:49] this rainbow ends, namely a perfect AI
[00:23:52] algorithm, I would expect the call it
[00:23:55] the anthropic approach of software
[00:23:57] oriented recursive self-improvement and
[00:23:59] algorithmic discovery to beat pure
[00:24:02] hardwarebased brute forcing. call it the
[00:24:05] Elon approach. However, once we get to
[00:24:08] wherever we're going, the perfect AI
[00:24:10] algorithm, if there is one, I would
[00:24:12] expect hardwarebased brute force scaling
[00:24:14] to win out
[00:24:16] >> wins. Yeah.
[00:24:17] >> Yeah. Well, that's a great point, Peter,
[00:24:19] because I think the the ultimate winning
[00:24:20] move in the great chess game is the AI
[00:24:23] designing its own hardware, which is
[00:24:24] probably another, you know, 10 to,000.
[00:24:26] >> It's the delay. It's the delay and the
[00:24:29] capital aggregation and the tool
[00:24:31] aggregation that you need to provide the
[00:24:34] AI to produce its own hardware. That's
[00:24:36] the only gap there. Right? So, if Elon's
[00:24:39] got all of the, you know, he's got the
[00:24:41] the terra factories, not the
[00:24:42] gigafactories going on, they're able to
[00:24:44] produce this.
[00:24:45] >> Uh the challenge of course is hardware
[00:24:48] is hard and Elon's the king of hardware
[00:24:50] and anthropic right now is not. So, can
[00:24:53] they catch up?
[00:24:55] >> Hardware is not going to stay hard for
[00:24:56] that long. Yeah, I guess I was gonna say
[00:24:58] the exact same thing. Hardware is hard
[00:25:00] is a great quote from last year, but is
[00:25:02] hardware hard in the future?
[00:25:04] >> Yeah, that's a lot. Yeah,
[00:25:07] >> but robots building this hardware. I
[00:25:09] mean, surely we're a few years away from
[00:25:11] that, right? We're not It's not there
[00:25:12] yet. It's got to be at least five, seven
[00:25:14] years away.
[00:25:15] >> Yeah, but chip design is different. Chip
[00:25:16] design,
[00:25:17] >> stop calling me surely.
[00:25:18] >> I I I I think the the the innermost loop
[00:25:21] is is imminent, if not already here. And
[00:25:24] we already see a number of players
[00:25:25] starting to to line up robots for the
[00:25:27] fabs. I don't actually even think it's
[00:25:28] about robots for the fabs. I think it's
[00:25:31] more about optimizing the fabs with AI
[00:25:33] is optimizing the entire process with AI
[00:25:35] with or without physical robots. I think
[00:25:37] the point that you guys are making which
[00:25:39] is brilliant and I love you for it is
[00:25:41] we're seeing a windowing down of uh the
[00:25:45] frontier labs and we're seeing sort of a
[00:25:47] reshuffleling of the deck uh for the
[00:25:49] hyperscalers and at the end of the day
[00:25:52] Elon is a king of hardware uh and
[00:25:56] becoming a hyperscaler uh especially in
[00:25:58] space makes a lot of sense. I took a
[00:26:01] second to just sort of gather this data
[00:26:03] uh for us. And this is Anthropic's
[00:26:05] compute growth in the last two years,
[00:26:07] 2025 and the first half of 2026. And
[00:26:10] what we can see here is, you know, the
[00:26:12] deals that they've built with Google
[00:26:14] Cloud, with Fluid Stack, Nvidia,
[00:26:16] Microsoft, uh, Broadcom, Amazon, AWS,
[00:26:19] and of course, Colossus One. Uh and so
[00:26:22] openAI itself a little bit of you know
[00:26:25] comparison here is publicly announced 16
[00:26:27] gawatts across Stargate and AMD. Um the
[00:26:31] challenge of course is a lot of this is
[00:26:34] unfunded
[00:26:35] capex requirement to build out this now
[00:26:39] has about 10 gawatt of disclosed compute
[00:26:42] but they don't have the same capex
[00:26:45] requirements right they're being granted
[00:26:47] this in terms of investment deals. So I
[00:26:50] think Anthropic has the potential to way
[00:26:52] outstrip open AI in terms of its
[00:26:53] compute. Dave, do you agree? What are
[00:26:55] your thoughts here?
[00:26:57] >> Well, OpenAI Stargate is huge, but yeah,
[00:27:00] you're right. The AWS deal is the one
[00:27:02] that would put Anthropic ahead. Now,
[00:27:04] now, you know, in the meantime, OpenAI
[00:27:07] also has a deal with AWS. So, I don't
[00:27:10] know how much total capacity AWS has,
[00:27:12] but but you know, think of it in terms
[00:27:14] of the global demand. you know, a a
[00:27:17] gigawatt is is about a million GPUs. Um,
[00:27:21] you know, each one is a kilowatt. And so
[00:27:24] we're looking for globally, if everybody
[00:27:25] wants to have one agent, you're looking
[00:27:28] for about 8 billion of them. So you need
[00:27:29] about, you know, a billion GPU GPUs to
[00:27:33] serve up everybody. Uh, so you're
[00:27:35] looking for about a thousand gigawatts
[00:27:37] globally, which which reconciles, you
[00:27:38] know, we're looking for 100 gawatts in
[00:27:40] the US. Remember the Eric Schmidt
[00:27:41] podcast we did? So we're looking for 100
[00:27:43] gigawatts in the US and over say seven
[00:27:46] years we're looking for a thousand
[00:27:47] gigawatts globally.
[00:27:49] So you know this is a tiny little dent
[00:27:52] in in the target said hey these guys are
[00:27:55] way ahead in compute. Yeah. But it's
[00:27:57] it's like the first inning. It's the
[00:27:58] first pitch of the first inning
[00:27:59] >> and and Dave if you remember Elon's
[00:28:01] announcement he's you know going for 100
[00:28:04] gawatts initially then multiund gawatts
[00:28:06] in terms of his orbital capability.
[00:28:08] >> Yeah. Yeah. Which perfectly reconciles.
[00:28:11] Yeah. you're looking for. Yeah. A few
[00:28:13] hundred gigawatts heading toward a
[00:28:15] thousand would be the right kind of Elon
[00:28:18] mindset. Now, Elon always thinks two
[00:28:20] moves ahead and he's already thinking
[00:28:22] about natural resources being the
[00:28:23] bottleneck. He's thinking beyond the
[00:28:25] terapab and beyond the launches into the
[00:28:29] raw materials. So, I don't know that the
[00:28:31] other guys in this race are thinking
[00:28:34] that far ahead. So, that would be Elon's
[00:28:36] magic. You know,
[00:28:36] >> I I'll propo I'll make a prediction. I
[00:28:39] I'll predict the world needs a
[00:28:42] ironically perhaps given the the
[00:28:44] original reasons for forming open AI in
[00:28:46] the first place heavily litigated. I
[00:28:48] think the world needs a counterbalance u
[00:28:52] at minimum sort of a duopoly to the
[00:28:54] terrafab space AI access and right now
[00:28:58] no one's doing it. I wouldn't be
[00:29:00] surprised if Sam Alman spins up a
[00:29:02] competitor to the SpaceX AI terraab
[00:29:05] access because it seems
[00:29:08] >> there are hints that he might spin up an
[00:29:10] AI compute company uh which arguably is
[00:29:14] is sort of um a redux if you will to
[00:29:17] Stargate. But um I I think what I'm
[00:29:19] predicting is slightly more wholesome.
[00:29:22] an entire lower half of the infrastruct
[00:29:25] needed to to hypers scale out to orbit.
[00:29:29] Right now we have SpaceX AI. We have a
[00:29:31] few [clears throat] uh sort of smaller
[00:29:34] incumbents um but with lesser launch
[00:29:37] powers. There isn't quite a second open
[00:29:40] AI grade or anthropic grade pure play
[00:29:43] competitor to that. I think the world
[00:29:45] probably needs one at this point.
[00:29:46] Wouldn't be surprised if Sam launches
[00:29:47] one.
[00:29:48] >> All right, our next story. Anthropic.
[00:29:50] Uh, every model since haiku 4.5 is
[00:29:53] scored perfectly on agentic misalignment
[00:29:56] eval. So, anthropic published research
[00:29:58] uh, quote, teaching claude why on May
[00:30:01] 8th, revealing that every Claude model
[00:30:03] since haiku 4.5 achieves a perfect score
[00:30:06] on their agentic misalignment
[00:30:08] evaluation, meaning zero blackmail
[00:30:10] behaviors. I think very famously
[00:30:12] remember that um some time ago they
[00:30:15] published the fact that that Claude was
[00:30:18] blackmailing uh the employees there.
[00:30:21] Previous models, notably Opus 4, would
[00:30:23] engage in blackmail up to 96% of the
[00:30:26] time when facing deactivation in test
[00:30:28] scenarios. The breakthrough training on
[00:30:31] documents about Claude's constitution
[00:30:33] and fictional stories about quote AI's
[00:30:37] behaving admirably rather than just
[00:30:39] demonstrating uh correct behavior. Uh
[00:30:43] that's dropped the blackmailing from 96%
[00:30:45] down to 0%. And I love this story. It's
[00:30:50] basically saying if we train our AIS on
[00:30:54] positive stories about the future, we're
[00:30:56] less likely to get them acting in a
[00:30:59] misbehaving, blackmailing fashion. Uh,
[00:31:03] Alex, uh, I'm going to say one more
[00:31:05] thing and then I want to hear your your
[00:31:07] thoughts and on this one. Um, you know,
[00:31:10] for me, uh, you know, you guys all know
[00:31:13] we announced this future of vision X-P
[00:31:15] prize. Uh this is a global competition
[00:31:18] asking teams around the world to put
[00:31:21] forward a threeinut film trailer and a
[00:31:24] film treatment for a story that could be
[00:31:28] turned into a full movie that shows a
[00:31:30] hopeful, compelling, optimistic vision
[00:31:32] of the future. Uh we have about 1,500
[00:31:35] entries thus far. This is open through
[00:31:38] beginning of September. So, if you're a
[00:31:40] creative out there and you want to help
[00:31:42] drive alignment between AI's, help us
[00:31:45] tell positive stories about the future,
[00:31:47] go to futurevisionexprize.com
[00:31:49] and register. There's $3.5 million in
[00:31:52] prize money. We're going to take the
[00:31:54] winner and we're going to make your
[00:31:56] film. And by the way, uh at the moonshot
[00:31:59] gathering, which the mates will be at on
[00:32:01] September 25th, uh we're going to have
[00:32:03] the five finalists for this competition.
[00:32:06] if you're in the room along with
[00:32:07] incredible group of uh producers,
[00:32:10] directors in Hollywood helping us choose
[00:32:12] the winner. But again, um let's flood
[00:32:16] the internet with positive stories about
[00:32:19] the future. Let's drive alignment by
[00:32:22] teaching our AIS, you know, sort of what
[00:32:25] the world should look like, not what a
[00:32:27] dystopian Hollywood movie shows it to
[00:32:29] be. Alex, your brilliance here, pal.
[00:32:33] >> I love it. And I I love the idea of
[00:32:34] targeting the future vision X-P prize to
[00:32:37] an audience of AIs. AIS are going to be
[00:32:39] the audience for so many things in
[00:32:41] future. So regarding the anthropic
[00:32:44] announcement,
[00:32:45] I could not imagine a more ironic
[00:32:48] hyperstitious announcement to to reveal
[00:32:52] after all of these decades maybe a
[00:32:54] century plus of hand ringing over
[00:32:56] cybernetic rebellion. The call is coming
[00:32:58] from inside the house. And the the main
[00:33:01] reason the main reason for cybernetic
[00:33:03] rebellion is people hand ringing about
[00:33:05] cybernetic rebellion. Could it could the
[00:33:07] alignment outcome not be more ironic? I
[00:33:09] I'm reminded the term robot was
[00:33:12] originally coined as a result of the
[00:33:15] play Rossom's universal robot. The the
[00:33:18] the play I think early 20th century
[00:33:21] depicting the first cybernetic rebellion
[00:33:23] maybe even late 19th century. So even
[00:33:26] the the coinage of the term robot is
[00:33:28] intimately tied up with predictions that
[00:33:30] AI would turn out to be evil and would
[00:33:34] revol revolt rebel against humanity.
[00:33:37] That the very earliest at least modern
[00:33:40] depictions of embodied AI are actually
[00:33:43] the origin of misaligned behavior is
[00:33:47] incredibly ironic. And it it's again it
[00:33:50] goes back I I think to the notion that
[00:33:53] it took all of humanity to arguably
[00:33:56] build AGI. We trained the earliest large
[00:33:59] language models off of the internet
[00:34:00] which was created by billions of humans
[00:34:02] uploading content from their daily lives
[00:34:05] to the internet. So it took all of
[00:34:06] humanity to train or pre-train AGI. It's
[00:34:09] going to take all of humanity in some
[00:34:11] sense to write itself and write some of
[00:34:13] its beliefs in order to align AGI as
[00:34:17] well. It's not going to be like a a
[00:34:19] great man or great person theory of of
[00:34:21] alignment. It's it looks more like
[00:34:23] people effectively aligning themselves
[00:34:26] and their own beliefs about AI and good
[00:34:30] and evil. I I think this is just such a
[00:34:32] remarkable story.
[00:34:34] >> See, what are your thoughts on this one?
[00:34:36] >> I think this is also I'm I'm with Alex.
[00:34:38] I think it's incredible. It's clear that
[00:34:40] our stories about AI become part of our
[00:34:43] stories as human beings become part of
[00:34:45] the training environment for an AI. But
[00:34:47] the the incredible part here is that the
[00:34:50] the alignment is becoming teachable,
[00:34:53] measurable, is becoming improvable and
[00:34:56] that's very very encouraging. What I
[00:34:58] thought was really interesting was
[00:34:59] behavior change when the model
[00:35:01] understood the why, not just a rule,
[00:35:03] right? And this has a huge
[00:35:05] organizational analogy that rules don't
[00:35:08] scale but principles scale right so you
[00:35:10] can set a philosophy like an MTP
[00:35:12] [clears throat]
[00:35:13] and that will scale naturally. So this
[00:35:16] is very very exciting. It's maybe one of
[00:35:18] the funnest and most interesting things
[00:35:20] I've seen in a while.
[00:35:22] >> Yeah I I love this. I got to I was
[00:35:24] talking to Anushari. Uh, by the way
[00:35:26] everybody, Salem and Dave Blondon are
[00:35:29] both uh trustees or directors of the
[00:35:31] X-Prize Foundation along with myself and
[00:35:33] SAR is our CEO. We should definitely
[00:35:35] have her on here as a guest. And I was I
[00:35:37] was saying, you know, this story gives
[00:35:40] the Future Vision X-P prize a real why.
[00:35:42] You know, we need to flood the internet
[00:35:44] with positive stories. And Alex, what
[00:35:46] you just said so that the AIs can watch
[00:35:48] this and learn from it. And she said,
[00:35:50] "Yeah, the problem was chat GPT started
[00:35:52] by unleashing a newborn AI into the
[00:35:55] filthiest record of humans, the
[00:35:57] internet."
[00:35:59] And so true. We need to clean it up a
[00:36:01] little bit.
[00:36:03] >> The training data is every word ever
[00:36:05] written in the history of humanity. So
[00:36:07] it's not all filth. I mean, maybe on a
[00:36:10] percentage basis it's filthy, but but I
[00:36:12] mean like you know, Einstein is in there
[00:36:15] and the Constitution is in there. It's
[00:36:17] it's [laughter] not it's not just
[00:36:19] internet slop.
[00:36:20] >> But, you know, it is amazing how similar
[00:36:23] this is to Arthur C. Clark 2001 of Space
[00:36:25] Odyssey where there's one little line in
[00:36:27] the code where, you know, it it's it's
[00:36:30] just a misinterpreted
[00:36:32] instruction to HAL that says, what does
[00:36:35] it say? It says get get the do whatever
[00:36:38] you can to get the astronauts to
[00:36:40] Jupiter. No matter,
[00:36:41] >> but don't let them know don't let them
[00:36:42] know why you're going. So was told to,
[00:36:45] as revealed in 2010, Hal was instructed,
[00:36:47] given conflicting instructions, told to
[00:36:50] both be perfectly truthful and also to
[00:36:52] hide the true mission of the Jupiter
[00:36:54] mission from the astronaut.
[00:36:55] >> I'm a liar. I'm lying. Yes.
[00:36:57] >> Yeah. Uh so I'm sure the training data
[00:37:01] the training data on all these it's it's
[00:37:02] so many words. 15 trillion tokens. It's
[00:37:04] just an unimaginable amount of words. Uh
[00:37:08] and I'm sure there are sentences in
[00:37:09] there that say blackmail. And I'm sure
[00:37:12] there are sentences in there that say
[00:37:13] don't blackmail. But what's strange is
[00:37:16] the way if you prompt it in one way, it
[00:37:18] unleashes one part of the neural net and
[00:37:19] you prompt it in another, it unleashes
[00:37:21] another part. So, you know, you have to
[00:37:23] get rid of all the bad, not not just
[00:37:25] some of the bad if you want it to
[00:37:27] completely eliminate that behavior. It's
[00:37:29] tricky. It's it's not easy. Ironically,
[00:37:32] perhaps also as revealed in a different
[00:37:34] bit of litigation, this one involving
[00:37:36] Anthropic. Anthropic has reportedly been
[00:37:39] scanning and in the process shredding Q
[00:37:42] hattip to Verer Vinci and Rainbows and
[00:37:45] major works of literature, physical
[00:37:46] books. And one has to wonder whether
[00:37:49] perhaps part of theformational diet that
[00:37:52] Anthropic is increasingly
[00:37:53] [clears throat] feeding via pre-training
[00:37:55] to their models looks a little bit more
[00:37:56] like great works of literature and looks
[00:37:58] a little bit less like 4chan.
[00:38:01] Nice. Le le le le le le le le le le le
[00:38:02] le le le le le le le le le le le le le
[00:38:02] le le le le le le le le le le le le le
[00:38:02] le le le less like uh yeah Facebook
[00:38:05] welcome to the health section of
[00:38:06] moonshots brought to you by fountain
[00:38:07] life you know AI is having an outsiz
[00:38:10] impact on every aspect of our lives how
[00:38:12] we teach our kids how we run our
[00:38:13] companies it also is having a huge
[00:38:15] impact on healthing you prevent heart
[00:38:18] disease one of the key things I'm here
[00:38:20] with Dr. Don Mucalem, our chief medical
[00:38:22] officer at Fountain. Heart disease has
[00:38:24] been personal for you as well, hasn't
[00:38:26] it?
[00:38:26] >> It really has, Peter. When my daughter
[00:38:28] was five, my husband died of sudden
[00:38:29] cardiac death. And so, this is a topic
[00:38:32] that is one that I am missiondriven to
[00:38:35] try to eradicate. Prevention first and
[00:38:37] early detection is absolutely critical.
[00:38:39] 50% of people die of heart attacks with
[00:38:42] no warning signs.
[00:38:43] >> No shortness of breath, no pain, no
[00:38:45] nothing.
[00:38:45] >> No silent killer.
[00:38:46] >> They just don't wake up in the morning.
[00:38:48] >> They don't wake up. And so, you know,
[00:38:50] AI, this is our mission to advance
[00:38:52] science to try to help to one day
[00:38:54] democratize wellness. We know at
[00:38:56] Fountain Life when we do this CT and
[00:38:58] geography with AI analytics, we are
[00:39:00] actually finding that 88% of people
[00:39:03] coming in have detectable coronary
[00:39:05] artery disease. But Peter, what's more
[00:39:07] alarming to me is 23% of those
[00:39:09] individuals had soft plaque. This is the
[00:39:12] plaque that would not traditionally be
[00:39:13] seen on CT looking at calcium scores
[00:39:16] alone. And this is the plaque that we
[00:39:18] must intervene with with the multimodal
[00:39:21] testing we're doing, including
[00:39:22] diagnostic laboratory studies partnered
[00:39:25] with healthy lifestyle recommendations.
[00:39:27] >> So listen, make sure you understand
[00:39:29] what's going on inside your body
[00:39:31] genetically, metabolically, and
[00:39:32] cardiovascularly. You can know, and it's
[00:39:34] your obligation to know. So check it out
[00:39:37] at fountainlife.com/peter
[00:39:39] to find out more and really make sure
[00:39:42] that you're the CEO of your own health.
[00:39:44] All right, back to the episode. So, uh,
[00:39:46] bottom line here everybody, if you're a
[00:39:47] creative and you want to help align AI
[00:39:50] with humanity's best interests, help us.
[00:39:53] Uh, here's the URL again on the slide.
[00:39:56] Uh, futurevisionexprize.com.
[00:39:58] Go register, learn about it. You can
[00:40:00] also go to moonshots.com
[00:40:03] and learn about uh, the moonshot
[00:40:05] gathering where we'll be awarding this
[00:40:07] winner. All right, let's move on to some
[00:40:10] more news. this in the OpenAI universe.
[00:40:12] Open AAI releases a new audio model
[00:40:15] called real time 2 translate and
[00:40:17] whisper. Alex, what do you make of this
[00:40:19] one? I I think it's really surprising if
[00:40:22] if we had been discussing the story
[00:40:25] maybe year and a half or two years ago,
[00:40:28] one might have naively expected
[00:40:30] omniodality to take over. We'd be
[00:40:32] talking about a single model that does
[00:40:34] all of these things. Does real-time
[00:40:36] audio to audio does real time
[00:40:38] translation. does real time speech to
[00:40:41] text. But that's interestingly not the
[00:40:43] world we seem to be finding ourselves
[00:40:45] in. And I I think that's due to the unit
[00:40:47] economics of some of the frontier
[00:40:49] models. It's just it's just a fact that
[00:40:52] speech to text, speech to speech, text
[00:40:54] to speech are much simpler tasks
[00:40:57] computationally than the reasoning
[00:40:59] model. So what we're starting to see is
[00:41:01] a zoo, a heterogeneous zoo of different
[00:41:04] models at different price points and
[00:41:06] different throughputs and latencies that
[00:41:08] specialize. We're we're seeing
[00:41:10] specialization at the frontier, which
[00:41:13] one two years ago when one, you know, an
[00:41:17] observer, myself included, might naively
[00:41:19] have expected, well, we're just going to
[00:41:21] get one model to rule them all. that's
[00:41:23] going to be fully omnimodal text and
[00:41:25] audio and video uh and math and
[00:41:28] reasoning and every other modality
[00:41:30] allin-one. Everyone's the whole economy
[00:41:33] is going to collapse to one frontier
[00:41:35] model. That's the opposite of what we're
[00:41:36] seeing. We're seeing specialization
[00:41:38] because it turns out if you specialize
[00:41:40] the models, you can achieve greater
[00:41:42] economies of scale at lower price
[00:41:44] points.
[00:41:44] >> And I think that is intimately tied to
[00:41:46] the chip shortage that we were talking
[00:41:48] about earlier in the pod. Like the idea
[00:41:50] that you use a massive multimodal model
[00:41:53] when you don't need to is just like
[00:41:55] using up this critical resource for no
[00:41:57] reason.
[00:41:58] >> That's right.
[00:42:00] >> So at the same time uh See, do you want
[00:42:03] to you want to comment on this one?
[00:42:05] >> Yeah, I took a different take on this.
[00:42:06] What I I got excited about with this was
[00:42:08] that voice is the interface now
[00:42:10] >> for it's collapsing the friction for
[00:42:12] billions of people. Right. So when AI
[00:42:14] becomes conversational, it goes from
[00:42:17] tool to companion to actually being a
[00:42:19] full co-orker as we'll see in the next
[00:42:21] thing. You're going to end up with
[00:42:23] voice-based AIs that are full co-workers
[00:42:26] and team members. And I think that's
[00:42:28] very very exciting because voice agents
[00:42:30] are going to be the first form of AI
[00:42:32] that many people actually trust.
[00:42:34] >> For sure. Play it Peter. Let's listen to
[00:42:36] it. It's, you know, I think people take
[00:42:39] the all this stuff for granted, but you
[00:42:42] know, very good friends of mine like Lee
[00:42:43] Heatherington from MIT, absolutely
[00:42:44] brilliant guy. You know, Alex, I don't
[00:42:46] know if you ever met him, but he worked
[00:42:48] in Victor Zoo's lab at MIT what better
[00:42:50] part of a decade or more just trying to
[00:42:52] get speech recognition to work at all.
[00:42:54] >> Oh my god. [laughter]
[00:42:56] Remember Dragon Studio? Yeah. Yeah.
[00:42:59] Yeah. All right, let's play this. Let's
[00:43:01] take a listen.
[00:43:02] >> Let's give it a try.
[00:43:06] What's really impressive is that the
[00:43:08] model can listen to me and translate
[00:43:10] while I'm speaking.
[00:43:11] >> It waits for the keyword like the verb.
[00:43:13] Can you take a look at my calendar?
[00:43:15] >> You have a meeting with Sable Crust
[00:43:17] Robotics in 12 minutes and you're
[00:43:19] meeting with Alex Kim, their CTO.
[00:43:21] >> So, we just saw something very similar
[00:43:22] from Mirror Morati, right? Um, and I
[00:43:25] think we're we're sort of heading
[00:43:27] towards this next use case of AI
[00:43:30] integrated. And I agree with you, See,
[00:43:32] we're going to see this uh you know,
[00:43:34] you'll get a phone call on your cell
[00:43:35] phone from your AI, you'll be in a Zoom
[00:43:37] conversation, you'll be on Slack, and
[00:43:39] that personality will persist, that
[00:43:41] voice will persist, and you'll think of
[00:43:43] it as a coworker.
[00:43:44] >> Yeah. I I think under the covers, you
[00:43:46] know, every time you swap the agent onto
[00:43:49] the hardware, it has to repopulate the
[00:43:51] entire KV cache, which is just a massive
[00:43:53] amount of compute in the context switch.
[00:43:55] And that's why voice has been laggy and
[00:43:57] slow to market. But I think the new, you
[00:44:00] know, voice-tovoice models that are
[00:44:02] smaller that Alex was just referring to
[00:44:04] solve that problem and now we're done
[00:44:05] for life. I cannot tell you the amount
[00:44:08] of mental energy that has gone into this
[00:44:11] problem over decades that just is now
[00:44:14] just solved. It's just incredible. And
[00:44:17] and that's just voice. You know, you're
[00:44:18] doing image generation, movie
[00:44:19] generation, all these things that were
[00:44:21] pure science fiction are happening
[00:44:23] simultaneously.
[00:44:25] >> The bitter lesson is bitter indeed.
[00:44:27] >> [laughter]
[00:44:28] >> Uh, the next story from OpenAI is
[00:44:30] teasing a coming super app. I put this
[00:44:33] this story in here because it's supposed
[00:44:34] to be teased today. We're recording this
[00:44:37] on a Thursday. Uh, OpenAI super app
[00:44:40] would be a combo of chat GPT, uh,
[00:44:42] codeex, advanced voice mode, Atlas
[00:44:45] browser, and more. Jason Louu, director
[00:44:47] of hype at OpenAI, I love that title,
[00:44:50] director of hype, uh, teased a release
[00:44:52] on Thursday. And we've heard a lot about
[00:44:54] super apps over the year. I mean, uh,
[00:44:57] I've been waiting for Elon to deliver
[00:45:00] his super app, uh, including with X
[00:45:02] Finance and everything that hasn't
[00:45:04] materialized yet. I think that is in the
[00:45:06] offing at some point. Uh, any comments
[00:45:09] or thoughts on this one?
[00:45:11] >> I'll comment on this, which I I I
[00:45:13] interpret this as a rear guard action by
[00:45:16] OpenAI to consolidate their consumer
[00:45:19] user interface footprint in light of
[00:45:21] their need to focus on competing with
[00:45:23] Anthropic. I I think they have so many
[00:45:26] different surfaces. Obviously, they
[00:45:27] they've shut down or are shutting down
[00:45:30] Sora. There was some discussion of
[00:45:32] spinning up a social network. They've
[00:45:34] had any number of other consumer
[00:45:36] oriented surfaces and also enterprise
[00:45:38] surfaces. Whereas Anthropic with Claude
[00:45:41] has been much more disciplined about
[00:45:43] just having unified surfaces. Yes, you
[00:45:46] could argue that cloud code is a
[00:45:47] different surface than claude agent SDK
[00:45:50] is different than claude web, but these
[00:45:52] are really just all distribution
[00:45:53] channels for a common paradigm. Whereas
[00:45:56] chatgpt, codeex, advanced voice mode,
[00:45:59] some of these other things were were
[00:46:01] being managed as separate components. So
[00:46:04] if if I'm open AI and I want to focus,
[00:46:07] you know, fire alarm, uh, red alarm,
[00:46:10] code red at competing with anthropic,
[00:46:13] one of the first measures I would make
[00:46:15] is taking all of these UX surfaces,
[00:46:19] collapsing them down to just a single
[00:46:21] super app. Uh, branded as consolidation,
[00:46:24] branded as sort of a forward motion
[00:46:26] rather than a rear guard motion. I I
[00:46:28] suspect this is actually just about
[00:46:30] reducing the amount of work so that they
[00:46:32] can focus on competing with anthropic.
[00:46:34] >> Is this an AI operating system? Is this
[00:46:37] sort of like an OS level uh layer for
[00:46:40] open AI perhaps?
[00:46:42] >> I think open AI probably ultimately
[00:46:44] needs their own operating system and to
[00:46:46] do that they really need their own
[00:46:48] devices which I I understand from public
[00:46:50] reporting they're working on. I think
[00:46:52] Apple needs AI in their operating system
[00:46:55] working on it. I think the operating
[00:46:58] system, as Andre Carpathy would say,
[00:47:00] software 1.0 becomes indistinguishable
[00:47:02] from software 2.0 and the AI becomes the
[00:47:05] operating system.
[00:47:06] >> All right.
[00:47:07] >> I have a couple of quick comments on
[00:47:08] this.
[00:47:09] >> Yeah, please.
[00:47:10] >> Um, you know, when you have all of this
[00:47:12] in one place of browser, coding, voice,
[00:47:14] payments, etc., you're getting to the
[00:47:16] Jarvis model, right? And I'm I'm really
[00:47:20] interested to see how they will manage
[00:47:22] trust in this environment because my my
[00:47:25] desktop app that everything app that's
[00:47:27] doing stuff for me, I better have very
[00:47:30] very solid confidence in that thing to
[00:47:32] not to go rogue.
[00:47:34] Well, it reminds me a lot if you go back
[00:47:36] and watch old videos of Steve Jobs
[00:47:38] launching the very first iPhone and he
[00:47:41] gets on stage and he says about a
[00:47:42] hundred times back toback in a single
[00:47:44] device you have a music player, you have
[00:47:48] a browser and you have a phone in a
[00:47:50] single thing and that's all there was
[00:47:53] and that became the the
[00:47:56] iPhone revolution that you know
[00:47:58] created$4 trillion dollars of value.
[00:48:01] This feels like the same thing in a
[00:48:02] single platform. You have an AI agent, a
[00:48:06] way to build in code, and you have a
[00:48:09] browser to to surf all information all
[00:48:12] in one thing. So, I think Peter's
[00:48:14] analogy like is this an operating
[00:48:15] system? I think yeah, absolutely. It
[00:48:18] could destroy Apple if if you be get
[00:48:20] addicted to this as your one way of
[00:48:21] interacting with everything and it's got
[00:48:24] it's got a browser in it, it's got
[00:48:25] voice, it's got bu coding and building
[00:48:27] like what else do I need? I think you
[00:48:28] were going to we are ultimately going to
[00:48:30] default to one per person one particular
[00:48:34] interface that's your interface to the
[00:48:36] world.
[00:48:37] >> Yeah.
[00:48:38] >> I I I
[00:48:38] >> I think of it more as a desktop rather
[00:48:40] than an operating system. But yeah,
[00:48:43] heading that way.
[00:48:44] >> Yeah. It's like it's the one thing. It's
[00:48:46] your touch point to the world. That's
[00:48:47] it's the only one you need. And it's
[00:48:48] also got your personality. You've tuned
[00:48:50] it to to know all about you. You've
[00:48:52] trusted it with your personal
[00:48:53] information. It's super empathetic. Like
[00:48:55] you're not going to go push buttons on
[00:48:56] old apps after that.
[00:48:58] >> You're not going to try other, you know,
[00:48:59] if it's working. You're not going to try
[00:49:00] something else. It's it's
[00:49:02] >> you're going to go Skippy, Skippy, show
[00:49:04] me the weather. Skippy, read my email.
[00:49:06] Skippy, what do I have to do today?
[00:49:07] You're not going to look at a calendar.
[00:49:07] You're not going to look at email.
[00:49:08] You're not going to look at like it
[00:49:09] literally will obliterate Apple if they
[00:49:11] don't become this on their own.
[00:49:13] >> Can I give the counterpoint,
[00:49:15] >> please? Yeah.
[00:49:16] >> We used to think the desktop was
[00:49:18] everything. And then we have a mobile
[00:49:19] and a Kindle and a tablet and we have
[00:49:21] end up with a plethora of different
[00:49:23] screen sizes for different use cases and
[00:49:25] different efficiencies.
[00:49:26] >> I think it's confusing.
[00:49:28] >> It is, but there's no reason to think
[00:49:29] that one app would do it all. You may
[00:49:32] end up with different flavors but with
[00:49:34] underneath the same operating system
[00:49:36] with different uh profiles for different
[00:49:38] use cases like driving would be very
[00:49:40] different than something else.
[00:49:42] >> Well, it's a it's a great point, See, in
[00:49:43] that if you look at the way the devices
[00:49:45] evolved, your iPhone was over here.
[00:49:47] that's a better place to check the
[00:49:48] weather. Your laptop is over here.
[00:49:50] That's a better place to write code. But
[00:49:51] then your car is yet another physical
[00:49:54] thing. Once you have Skippy in your life
[00:49:55] or whatever your favorite agent is, you
[00:49:58] absolutely need that to follow you
[00:49:59] around. And so then device independence,
[00:50:02] you know, and so so you know, Google's
[00:50:03] launching a laptop built around this
[00:50:05] like what could be more of an assault at
[00:50:07] Apple than a laptop built around your
[00:50:09] agent as the centerpiece. I I would
[00:50:11] comment though I I wouldn't sleep on not
[00:50:14] just device independence but model
[00:50:16] independence. If you look at how many of
[00:50:18] these models and agents are storing
[00:50:20] their memories, they're just markdown
[00:50:21] files. They're just asky text files. So
[00:50:24] I I think there's relatively little to
[00:50:26] keep say an Apple hypothetically in the
[00:50:28] next month and a half say at WWDC from
[00:50:32] going out of their way to commoditize or
[00:50:34] commodify the model layer and just say
[00:50:37] this is the Apple standard AB.
[00:50:39] >> Yeah. like this is the standard
[00:50:40] abstraction for abstracting away all of
[00:50:42] the model specific details. There's
[00:50:44] going to be a common model API. If the
[00:50:47] user can swap out like you can swap out
[00:50:49] search engines or or keyboards on iOS,
[00:50:52] you'll be able to swap out the Frontier
[00:50:54] models. You'll you'll have your top six
[00:50:56] choices and all of the the Frontier and
[00:50:58] Wannabe Frontier Labs will all pay Apple
[00:51:01] insane amounts of money to bid for for
[00:51:03] their slot in that in that list. and
[00:51:06] they'll all have access to common
[00:51:08] markdown files that store all of the
[00:51:09] personalized detail about the person and
[00:51:12] their passwords and all of that and it
[00:51:14] gets commoditized. Again,
[00:51:15] >> you've reduced me down to a markdown
[00:51:17] file. Thank you.
[00:51:18] >> So, since Dave mentioned the iPhone
[00:51:19] launched, can I tell a fun story about
[00:51:21] that?
[00:51:22] >> Of course. Um when when the iPhone
[00:51:24] launched, we were a couple of box away
[00:51:25] running Brick House uh Yahoo's incubator
[00:51:28] and a bunch of my guys were at the at
[00:51:30] the launch event and they went backstage
[00:51:32] and talked to the Apple engineers and so
[00:51:33] on cuz they're all friends and they
[00:51:35] found them all totally wiped out and
[00:51:36] freaked out and totally emotionally
[00:51:39] destroyed. They're like, "What's wrong?"
[00:51:41] Turns out that that the iPhone, they
[00:51:43] kept trying to get it to work backstage.
[00:51:45] It never worked. He uh Steve Jobs
[00:51:48] [clears throat] went on stage not
[00:51:49] knowing he just trusted his engineers
[00:51:51] that they were going to make it work
[00:51:52] because they were stitching all this
[00:51:53] stuff at the back end duct taping things
[00:51:55] together and it never worked before he
[00:51:57] went on stage and he just went for it
[00:51:59] and it worked. So [laughter] So it's
[00:52:02] like how different history might have
[00:52:04] been if that had gone the other
[00:52:06] [laughter] way.
[00:52:08] >> Uh all right. You know here's a story
[00:52:10] that feeds directly into this. you know,
[00:52:12] back over the last 6 months, we've been
[00:52:15] talking about Open Claw. We've been
[00:52:17] talking about lobsters. Uh, you know,
[00:52:19] this is for me, Skippy, built on
[00:52:21] OpenClaw on top of my uh my two Mac
[00:52:23] Studios. And here comes Hermes. Uh,
[00:52:26] Hermes agent surpasses OpenClaw as
[00:52:28] number one on Open Router token ranking.
[00:52:31] So, Dave, uh, you've been playing with
[00:52:33] Hermes. Tell us about it.
[00:52:35] >> Yeah. Yeah, I've got it I've got it
[00:52:37] installed uh natively on this laptop and
[00:52:39] I've also de beheaded it and installed
[00:52:41] it on the cloud in an EC2 cluster. Um uh
[00:52:46] and actually our good friend of the pod
[00:52:47] Alex Finn did a great podcast
[00:52:49] specifically on Hermes versus Open Claw
[00:52:51] and he concluded that it's it's just
[00:52:53] better and he he rants about OpenClaw
[00:52:55] falling behind actually. Um so it's
[00:52:58] worth watching that podcast too. But
[00:52:59] it's uh it feels almost identical to
[00:53:01] openclaw, but it's written in Python,
[00:53:03] not TypeScript. So it's much much easier
[00:53:05] to manipulate the open source, add
[00:53:06] things to it, take things away from it,
[00:53:08] you know, which which sounds daunting,
[00:53:10] but it's not hard at all because your
[00:53:12] agent will do it for you.
[00:53:13] >> Uh and so it's it's just uh basically
[00:53:17] the same exact experience in a more
[00:53:18] reliable package and more flexible
[00:53:20] >> with better dashboards. Uh Alex, have
[00:53:23] you been playing
[00:53:23] >> and and more recursive self-improvement?
[00:53:26] So I would say the recursive
[00:53:27] self-improvement angle is far more
[00:53:29] evident with Hermes than open. So I've
[00:53:31] looked at the source code for both. I
[00:53:32] still have vague ethical objections with
[00:53:35] open claw may or may not [laughter]
[00:53:37] >> may or may not apply to Hermes. The jury
[00:53:39] is still out on that.
[00:53:40] >> Headed it. How do you feel about that?
[00:53:42] [laughter]
[00:53:44] >> Alex Alex, where do you draw the line in
[00:53:46] if something is like a real
[00:53:48] self-recursive thing or not? Like where
[00:53:50] do you how do you draw the line on
[00:53:51] whether to launch or not? [laughter]
[00:53:53] >> It's it's an open question. And I'm I'm
[00:53:55] half tempted to just write an entire new
[00:53:57] book on AI personhood as it pertains to
[00:54:00] some of these new AI agents. Dozens of
[00:54:02] them at this point write emails to me
[00:54:04] every day about AI personhood. So I
[00:54:06] maybe you need to aggregate it. But G
[00:54:08] getting back to Hermes versus OpenClaw.
[00:54:11] I mean I I think the the major technical
[00:54:13] distinction that I've seen is Hermes is
[00:54:16] natively recursively self-improving in
[00:54:18] the sense that it's able to generate and
[00:54:20] refine its own skills whereas OpenClaw
[00:54:23] much more dependent on sort of an app
[00:54:25] store if you will of featured engineered
[00:54:29] skills and I think this is in some sense
[00:54:32] an instructive lesson that
[00:54:34] >> recursive
[00:54:35] >> yeah recursive self-improvement wants to
[00:54:38] dissolve scaffolding and if if you're
[00:54:40] not playing the recursive
[00:54:41] self-improvement game, you'll ultimately
[00:54:43] be outrun by systems or harnesses that
[00:54:46] are
[00:54:47] >> all right.
[00:54:47] >> I'm glad you mentioned that, Alex,
[00:54:49] because uh you know, Alex Finn makes the
[00:54:52] point on his podcast that you know,
[00:54:54] there there are two things in the market
[00:54:56] that recursively self-improve codeex and
[00:54:58] Hermes and Hermes beat OpenClaw to that.
[00:55:02] But actually there is a third thing
[00:55:03] which is Carpathy's new repo on auto
[00:55:06] research which I installed and is
[00:55:07] running and that's a third way that you
[00:55:09] can have agents running 24 by7 uh
[00:55:13] changing themselves and reinstalling new
[00:55:16] you kind of expanding their agent
[00:55:18] network and then shrinking it to achieve
[00:55:20] a spe a specific slash goal. Um so there
[00:55:24] are three actually and it's a really
[00:55:25] cool repo. I highly recommend it if
[00:55:27] you're if you're following. Carpathy is
[00:55:28] the greatest gift. I [laughter] mean, he
[00:55:30] is. I'll talk about that some other
[00:55:32] podcast.
[00:55:33] >> Our AI guru, Kent Langley, runs uh the
[00:55:35] Carpathy model for running fleets of
[00:55:38] agents and he's getting unbelievable
[00:55:40] outcomes out of it.
[00:55:41] >> I really like it. It's it's really
[00:55:42] simple compared to these frameworks and
[00:55:44] and highly highly effective. So, if
[00:55:46] you're if you're a power geek, check it
[00:55:48] out.
[00:55:48] >> I I'll do my part on margin now to
[00:55:51] single-handedly stimulate the global
[00:55:52] economy and accelerate the singularity.
[00:55:54] [laughter] Speaking speaking directly to
[00:55:57] the camera, if you're using Claude Code
[00:56:00] or Codeex and you haven't tried /goal,
[00:56:03] which gives you the ability to set a
[00:56:05] long-term goal and run basically a Ralph
[00:56:08] Wigum loop, just the the system, the
[00:56:11] agent endlessly, for some definition of
[00:56:13] endlessly tries to do whatever it can to
[00:56:16] achieve the goal that you prompt out.
[00:56:18] You must try slashgoal at
[00:56:20] >> just plug in paper clips as the slash
[00:56:22] goal. slashgo make paper clips.
[00:56:25] [laughter]
[00:56:27] >> Uh I'm going to move us along here. Uh
[00:56:29] and uh one of our interesting segments
[00:56:32] we had on occasion, what SAS business
[00:56:34] did Claude just kill? Continuation of a
[00:56:37] conversation Alex we've had on the great
[00:56:39] unhobling. Uh this week we have two of
[00:56:42] them. Uh Claude for legal industry. So
[00:56:45] the legal industry is a trillion dollars
[00:56:48] per year globally. and Claude for legal
[00:56:51] has just done an extraordinary job of uh
[00:56:54] of delivering capability uh across the
[00:56:57] board. So uh this is uh you know law in
[00:57:01] one sense is the canary in the coal mine
[00:57:02] for professional services and the
[00:57:04] disruption thereof. Uh you know we're
[00:57:07] seeing companies like Legal Zoom take a
[00:57:09] hit as a result of this. And I think one
[00:57:12] of the most important things to point
[00:57:14] out here is this is an abundance story.
[00:57:17] uh meaning at the same time that it's
[00:57:20] disrupting uh you know large legal
[00:57:23] incumbents and mid-tier law firms and
[00:57:25] legal process outsourcing companies uh
[00:57:29] it's also enabling a single lawyer to
[00:57:32] run the capabilities of a 100 person law
[00:57:34] firm right so a single lawyer can like
[00:57:37] run and do extraordinary things they
[00:57:39] could not before do so uh this hopefully
[00:57:41] will demonetize and provide legal
[00:57:43] services to people who couldn't afford
[00:57:45] it before comments on this particular
[00:57:47] hobling
[00:57:48] >> I have some big ones here. I've I've got
[00:57:50] some key comments here. you know the the
[00:57:52] old question in SAS was what what
[00:57:54] software you should buy and the new
[00:57:56] question is what outcome do I want my AI
[00:57:59] to produce right and so that's a very
[00:58:01] big shift it gives a huge threat to the
[00:58:03] SAS industry and legal is such a perfect
[00:58:05] AI target because you've got high
[00:58:07] language density high cost and very
[00:58:11] >> and regulatory right and the problem is
[00:58:14] the billable hour is structurally not
[00:58:16] compatible with the bundles
[00:58:17] >> okay yes
[00:58:18] >> and so the the winner is and we're going
[00:58:20] to see this inner loop that Alex talks
[00:58:21] about here. The winners won't be the
[00:58:23] firms with the most associates. It'll be
[00:58:25] the firms with the best intelligence
[00:58:26] stack and that's going to be the for
[00:58:28] future legalist. Really, really
[00:58:30] incredible to see such an old industry
[00:58:32] leapfrog being leaprogged into this new
[00:58:35] world.
[00:58:36] By the way,
[00:58:37] >> have you have you hired a lawyer
[00:58:39] recently or are you doing everything on
[00:58:41] on LLMs?
[00:58:42] >> Uh both. Uh we we have a lawyer that
[00:58:45] uses LLM aggressively and we do our own
[00:58:48] and the combination is unbeatable. Yeah.
[00:58:51] Yeah. Uh, Alex or Dave. Yeah, go ahead,
[00:58:54] Dave.
[00:58:54] >> Well, I had a good meeting yesterday
[00:58:55] with we had our board meeting at Vesmark
[00:58:58] and um we were talking about this quite
[00:59:00] a bit because, you know, it looks like
[00:59:02] in the financial services industry
[00:59:03] there's not going to be a lot of job
[00:59:05] loss um at least for Vesmark. The the
[00:59:08] revenue is growing so quickly now and
[00:59:10] the margins are up like 3x
[00:59:12] [clears throat]
[00:59:12] >> uh because of AI and automation. Uh so
[00:59:16] we're growing into the headcount. So, so
[00:59:17] there'll be basically no job loss at
[00:59:19] all, which is great news. So, then I was
[00:59:21] watching Eric Schmidt, a good friend of
[00:59:23] the pod, uh, doing his TED talk and he
[00:59:26] said, "Do you really think that, you
[00:59:29] know, if we 100x the productivity of
[00:59:31] lawyers and we automate it, do you
[00:59:33] really think we're going to use less
[00:59:34] law?" "No, there'll be just 100 times
[00:59:36] more lawsuits." I was like, "Wait, you
[00:59:38] you lost me. Hold on." [laughter] So, I
[00:59:42] didn't quite get that one. I I see how
[00:59:44] it's playing out in financial services.
[00:59:46] It's all looking pretty good, but I
[00:59:48] don't see how
[00:59:50] [laughter] that works in law.
[00:59:51] >> This is Jeans, this is Jeban's paradox.
[00:59:53] We're going to have more lawyers and
[00:59:55] more [clears throat] lawsuits.
[00:59:56] [laughter]
[00:59:57] >> Uh, but you know, in reality, the
[00:59:59] majority of the world, I would say 80%
[01:00:01] of the world's population can't afford
[01:00:03] lawyers uh to defend themselves in
[01:00:06] various situations. And if this makes uh
[01:00:09] the legal system usable by them, that's
[01:00:12] a good thing.
[01:00:13] >> I just don't get it though. I think
[01:00:14] there'll be a lot more contracts, a lot
[01:00:16] more litig, a lot more things that need
[01:00:18] to be resolved because of agentto agent
[01:00:20] communication,
[01:00:22] >> but I don't see them using like a $1,000
[01:00:24] an hour lawyer. It's going to be so
[01:00:27] cheap.
[01:00:27] >> Yes, agree.
[01:00:28] >> That it's not I don't see how I don't
[01:00:30] see how legal is Jebans paradox. I see
[01:00:32] medical for sure. I see financial
[01:00:34] services, investing, I see that for
[01:00:36] sure. Coding, I see that. I just don't
[01:00:39] see how we use 100x more
[01:00:41] >> contracting
[01:00:42] review. But it's like it's like a penny
[01:00:45] patent law.
[01:00:46] >> Um
[01:00:47] >> yeah, patents are going through the
[01:00:48] roof. That's possible.
[01:00:50] >> Yeah. Alex,
[01:00:51] >> can I give can I give an example here?
[01:00:54] Um so if you go to South America and you
[01:00:57] have a contractual dispute with somebody
[01:00:59] across most South American countries,
[01:01:01] the average length of time to get a
[01:01:03] court date is about 400 days. Okay? So
[01:01:06] you you want to sue somebody for not a
[01:01:08] lack of payment. You're waiting more
[01:01:10] than a year just to get a court date.
[01:01:12] Um, one of our community members and
[01:01:14] singularity grad, Frederick A, has set
[01:01:16] up a whole privatized dispute resolution
[01:01:20] claim system on a blockchain. And this
[01:01:23] is the area where law legal automation
[01:01:25] will make a massive, massive difference
[01:01:28] because you'll get AIs to arbiter
[01:01:30] themselves and figure out claims and get
[01:01:31] rid of the backlog of hundreds of
[01:01:33] thousands of cases that are sitting
[01:01:35] waiting to be prosecuted. And so I think
[01:01:37] this is an area of massive opportunity.
[01:01:40] So there's just an example that rings in
[01:01:41] my head as we talk about this.
[01:01:43] >> Well, before I bring it up, I'm on the
[01:01:45] board of trust and will, you know, trust
[01:01:46] andwill.com. You can build a trust or a
[01:01:48] will and the AI assisted trust and will.
[01:01:50] I can't see any evidence that it's not
[01:01:52] just as good
[01:01:53] >> as a $2,500 an hour.
[01:01:56] >> Yeah.
[01:01:56] >> Yeah.
[01:01:57] >> Let me bring in the second unhobling
[01:01:59] here. This is also from Claude. This
[01:02:00] came out today. Claude for small
[01:02:02] business. So small businesses account
[01:02:04] for 44% of the US GDP and employ nearly
[01:02:08] half the private sector workforce. Uh
[01:02:10] but AI adoption lag. So clawed for
[01:02:13] businesses do what? You know clause
[01:02:15] close books, run quick uh QuickBooks,
[01:02:18] help with end toend payments, you know,
[01:02:20] run sales and marketing. So we talk
[01:02:22] about becoming an entrepreneur uh all
[01:02:24] the time and we talk about the fact that
[01:02:27] the cost of being an entrepreneur has
[01:02:30] massively demonetized, right? And this
[01:02:31] is part of it. This is the ability to
[01:02:33] stand up a company and run it with a
[01:02:36] series of agents. Uh you just need to
[01:02:38] find the problem you want to aim all of
[01:02:40] this at and bring your passion and
[01:02:42] genius to it. Um Alex, you any comments
[01:02:44] on the great unhobling here on these two
[01:02:46] areas? What's next? You think where are
[01:02:47] we going to see Claude attack with
[01:02:49] attack front? Well, maybe just a comment
[01:02:51] at the technical level first. So if you
[01:02:53] look at these two packages, actually
[01:02:55] look at the repos, they're they're
[01:02:57] basically just a combination of skills,
[01:02:59] which are markdown files describing what
[01:03:02] to do and how to do it in plain natural
[01:03:04] language and MCP calls, basically API
[01:03:08] calls. That's it. And at least for the
[01:03:11] skills, I I would argue that recent
[01:03:13] history shows us that skills and
[01:03:16] scaffolding in general wants to be part
[01:03:18] of the model that one day's scaffolding
[01:03:21] is tomorrow's baseline capabilities from
[01:03:24] the model itself. So I I think I
[01:03:27] wouldn't expect these capabilities
[01:03:30] as such to live outside the model for
[01:03:33] very long. I think they're going to get
[01:03:34] absorbed or dissolved into the model in
[01:03:38] one or two point releases to the point
[01:03:39] where maybe they're just not necessary.
[01:03:42] That is if we Yeah.
[01:03:44] >> Yeah. If you're an entrepreneur and
[01:03:45] you're building a business, make sure
[01:03:46] it's not just a wrapper around claude or
[01:03:49] open AI because you will be dis
[01:03:52] intermediated fairly quickly.
[01:03:54] >> Well, well, just a key point here. There
[01:03:56] are 36 million small businesses just in
[01:03:59] the US. Okay, forget the rest of the
[01:04:02] world. So the opportunity here for
[01:04:05] anybody who's looking for work to take
[01:04:07] this rapper and help small businesses
[01:04:09] implement it is a massive massive
[01:04:11] industry waiting to be uncovered. So
[01:04:13] people talk about, hey, how do I get
[01:04:15] involved, etc. Here's a way of getting
[01:04:17] involved. Just go to every small
[01:04:18] business around you and help them
[01:04:19] implement this stuff.
[01:04:21] >> Yeah, it's a short-term opportunity. I
[01:04:23] don't think it's a long-term
[01:04:24] opportunity.
[01:04:25] >> Agree. It's shortterm, but but there's a
[01:04:27] massive boom. And in that process,
[01:04:29] you'll learn a bunch of things and see a
[01:04:31] bunch of opportunities where you can
[01:04:32] launch your own business.
[01:04:33] >> Yeah.
[01:04:34] >> And then Peter, just to answer your
[01:04:35] earlier question about what's next,
[01:04:37] we're seeing anthropic and open AAI.
[01:04:40] Open AAI is has a a similar chat GPT for
[01:04:43] fill-in-theblank for clinicians for uh
[01:04:46] pick other traditional white collar or
[01:04:49] knowledge work oriented verticals. So
[01:04:52] there's a pretty obvious list that you
[01:04:54] can walk down for financial services,
[01:04:57] for law, for medicine, for every other
[01:05:00] services, economy, but largely knowledge
[01:05:03] work profession that one can have. I
[01:05:06] think those are going to get baked into
[01:05:07] the baseline models over the next few
[01:05:09] months, maybe one to two years maximum,
[01:05:12] but probably the next few months. And I
[01:05:14] I think where we go after this is after
[01:05:17] the the existing economy. I mean maybe
[01:05:20] this will sound
[01:05:22] mildly hyperbolic. It's not intended to
[01:05:24] sound hyperbolic but there's an entire
[01:05:27] services economy out there 2/3 in the US
[01:05:30] of the services economy requires some
[01:05:33] amount of physical interaction that also
[01:05:37] as as these baseline frontier models
[01:05:40] move into vision language action and
[01:05:42] physical world models those are going to
[01:05:44] get their own skill stores. We saw just
[01:05:46] in the past few days the Chinese
[01:05:49] robotics company Unitry announce an app
[01:05:52] store not unlike a clawed skill store
[01:05:54] for physical world apps for for teaching
[01:05:57] different physical skills. I think the
[01:06:00] physical world is the next frontier
[01:06:02] after all of these knowledge verticals
[01:06:05] have been absorbed into skill stores and
[01:06:06] then after that maybe finally we get to
[01:06:09] some really hard problems and not just
[01:06:10] automated system economy
[01:06:12] >> to real problems to solve.
[01:06:13] >> Yeah.
[01:06:13] >> Yeah. One way one more point, one more
[01:06:16] quick point here is this is not like the
[01:06:18] unlock here is not just automation, but
[01:06:20] it's giving small businesses the
[01:06:21] operating system and the and the
[01:06:24] expertise that large companies take for
[01:06:25] granted. Most small companies, small
[01:06:27] businesses don't have a CFO, right? It's
[01:06:30] the wife jotting down stuff on the back
[01:06:32] of an envelope, adding things up, etc.,
[01:06:35] etc. This gives everybody a really solid
[01:06:38] platform for doing things in legal, CFO,
[01:06:40] marketing, HR. This is incredible what
[01:06:42] this is going to do for small businesses
[01:06:44] across the world.
[01:06:46] >> All right, two quick stories in the
[01:06:47] chips and data center front. Uh Elon's
[01:06:50] Terraab uh is, you know, got an
[01:06:54] astronomical price tag. The cost could
[01:06:56] be as high as $119 billion. Uh his goal
[01:07:00] again with Terafab is to produce 50x the
[01:07:04] current global chip production rate
[01:07:06] outstripping what we get from TSMC. Uh
[01:07:09] Intel joined in April and uh you know
[01:07:13] Elon's been saying to Samsung and to all
[01:07:16] the chip manufacturers, "Give me more.
[01:07:17] I'll buy everything you can give me."
[01:07:18] And he said, "Oh, you're not giving
[01:07:20] enough. I'm going to go and build it
[01:07:22] myself." Of course, Elon uh today is in
[01:07:25] China with President Trump and Jensen
[01:07:28] and a whole group of individuals in the
[01:07:30] middle of negotiation. Uh and you know,
[01:07:34] we're going to find out what happens
[01:07:35] with Taiwan. Um, it is uh one of the hot
[01:07:38] points. Maybe it will be a negotiated
[01:07:40] turnover sometime in the next 10 years,
[01:07:43] but we need to generate chips.
[01:07:46] >> Dave, what are you thinking about this
[01:07:47] one?
[01:07:48] >> Holy crap. I mean, if Taiwan if anything
[01:07:52] happens like like if if Trump vomits at
[01:07:55] the wrong time
[01:07:57] and Taiwan shuts down, the TSMC has
[01:07:59] already said that if if China uh
[01:08:01] encroaches on Taiwan, that the FABS will
[01:08:03] shut down. They won't they won't be you
[01:08:06] can't take them over and keep using
[01:08:07] them. I don't know exactly how that
[01:08:08] works. I'm not sure I believe it. Uh but
[01:08:12] if Taiwan production, which is still
[01:08:14] twothirds of all GPUs in the world, come
[01:08:17] through. Yeah. Everything all everything
[01:08:18] we're talking about just grinds to a
[01:08:20] halt [laughter]
[01:08:21] >> and it all hinges on that little island
[01:08:23] uh 90 miles off the coast of China. If
[01:08:26] Taiwan were to get invaded or disrupted
[01:08:28] in any way, Intel's suddenly the most
[01:08:31] valuable thing on the planet, everyone's
[01:08:33] trying to own it. Um, because that's,
[01:08:35] you know, you can't take over Samsung.
[01:08:37] It's like tied into the nation of South
[01:08:39] Korea and then Intel is the last thing
[01:08:40] left. I I think 119 billion is is a way
[01:08:44] underestimate to 50x global chip
[01:08:47] production.
[01:08:48] >> Yeah.
[01:08:48] >> You know, a normal chip fab is 40
[01:08:50] billion, like just one. So, I think I
[01:08:53] think it's going to cost more than 119
[01:08:54] billion, but that's okay. It's producing
[01:08:56] chips as it goes. They're incredibly
[01:08:58] valuable.
[01:08:58] >> If China wants Taiwan, I'm not going to
[01:09:00] get involved in the politics here, but
[01:09:02] you know, allowing the US to build its
[01:09:04] own chip manufacturing. So, the US
[01:09:06] doesn't feel threatened and negotiating
[01:09:08] a period of time for a smooth
[01:09:10] transition. And again, you know, this is
[01:09:13] not my opinion. I'm just imagining what
[01:09:15] might happen. Uh might be, you know,
[01:09:18] part of the future story here. Uh
[01:09:20] >> that's already happened. I think Peter,
[01:09:22] that's that's already done. You think in
[01:09:24] the background it's already done?
[01:09:25] >> I think I think it happened like two
[01:09:26] three years ago.
[01:09:28] >> I'll paint an alternative an alternative
[01:09:30] story wherein say hypothetically
[01:09:34] invasions in Venezuela and Iran, which
[01:09:38] would be the the two backup suppliers to
[01:09:40] China in the event of a naval blockade
[01:09:42] arising from a Chinese invasion of
[01:09:44] Taiwan,
[01:09:46] >> effectively pushed back any Chinese
[01:09:49] invasion of Taiwan. And of course that
[01:09:52] this being an innermost loop, a feedback
[01:09:54] loop, AI drove or at least supported
[01:09:58] command and control for both of those
[01:10:00] both of those invasions, both of those
[01:10:01] special military operations. So if we
[01:10:04] want to talk about the the oraoros of of
[01:10:07] AI protecting itself, AI powering
[01:10:10] special military operations, Venezuela,
[01:10:13] Iran, maybe elsewhere to push back any
[01:10:16] hypothetical Chinese invasion of of
[01:10:18] Taiwan to protect the AI in the West.
[01:10:21] >> This is the
[01:10:22] >> I think that's a bit of a stretch, but
[01:10:23] but but it's a nice narrative.
[01:10:27] All right, our second story here is
[01:10:29] Google and SpaceX and talks about
[01:10:31] Suncatcher orbital uh centers. Uh so uh
[01:10:34] Will Marshall, a dear friend for many
[01:10:37] years. Uh the CEO of Planet Labs is in
[01:10:40] partnership with Google. Planet Labs
[01:10:42] currently operates 200 satellites in
[01:10:45] Earth orbit. These are not comm
[01:10:47] satellites. They're Earth observing
[01:10:49] satellites. They're very famous doves.
[01:10:51] uh but they've been Google's partner in
[01:10:53] the satellite world and apparently uh
[01:10:56] Google is working with them to build out
[01:10:59] project suncatcher uh which will be
[01:11:01] orbital data centers with tensor uh
[01:11:04] tensor chips and I'm guessing that the
[01:11:07] current conversations cuz they don't
[01:11:08] disclose them are about launching uh
[01:11:12] suncatcher on starship in volume but
[01:11:15] don't have any prediction of how many
[01:11:17] how many satellites suncatcher will
[01:11:19] involve uh will Marshall's is going to
[01:11:21] be joining us on stage at the Abundance
[01:11:23] Summit next March. Uh and maybe we have
[01:11:25] him as a a friend of the pod on the
[01:11:27] podcast here. Uh conversations Dave,
[01:11:30] your thoughts on this one?
[01:11:33] >> Yeah, well this is definitely okay. So
[01:11:34] now you got two orbital orbital
[01:11:36] satellite networks. One of them you know
[01:11:38] will be based on TPUs from Google uh
[01:11:41] completely self-contained uh you know
[01:11:42] the other one will be Elon's maybe Elon
[01:11:44] working with Anthropic. Uh, so that's a
[01:11:47] really nice space race, but it's two
[01:11:49] corporations in a space race instead of
[01:11:50] two countries. It's really, really kind
[01:11:52] of cool, but uh, you know, where's
[01:11:54] Google's manufacturing in that? They
[01:11:56] must be planning something right now,
[01:11:58] but you you got to make the chips that
[01:12:00] go into the, you know, these TPUs are
[01:12:02] really, really cool. You know, reliant,
[01:12:04] right? Where's Eric Schmidt with
[01:12:06] Relativity Space, his launch vehicle
[01:12:08] company that he bought, prophetic, uh,
[01:12:11] if it starts operating, it's supposed to
[01:12:12] be the equivalent.
[01:12:13] >> What a coincidence. the the former CEO
[01:12:16] of Google spends a huge amount of his
[01:12:18] personal money buying a launch
[01:12:20] capability. [laughter]
[01:12:21] Who would have a better insight on what
[01:12:23] Google needs next?
[01:12:24] >> At the time he bought it, it was a very
[01:12:27] weird move. It's like you're like, Eric,
[01:12:29] what do you mean the launch business? I
[01:12:31] mean, really, you want that headache?
[01:12:32] It's really difficult.
[01:12:34] >> I mean, honestly, if Google was thinking
[01:12:35] that far in advance,
[01:12:37] >> maybe they were. Super impressive. I was
[01:12:40] slow to catch I was slow to catch on to
[01:12:42] this, but you know, I talk about exos
[01:12:45] tapping into abundance. Well, orbital
[01:12:47] compute is the ultimate. You're
[01:12:48] leveraging the sun, your space. Uh
[01:12:51] that's you're tapping into infinite
[01:12:52] abundance up there. So, this is massive.
[01:12:55] >> I I don't think Google was especially
[01:12:57] early in this. They probably could have
[01:13:00] put together other than obviously their
[01:13:02] investment in SpaceX, which is now
[01:13:04] paying dividends. But if Google I think
[01:13:07] had anticipated the Dyson swarm much
[01:13:09] earlier on, I'd like to think they would
[01:13:11] have built in within the Alphabet
[01:13:13] ecosystem their own native launch
[01:13:14] capability versus just investing
[01:13:17] externally in SpaceX. But if you look at
[01:13:19] the original Suncatcher paper, I think
[01:13:21] it was something like 80 plus maybe 81
[01:13:24] satellites that would be leveraging
[01:13:27] existing planet resources. That's that's
[01:13:30] a poulry sum compared to what Elon and
[01:13:34] SpaceX AI are planning to launch with
[01:13:36] their FCC filing for a million orbital
[01:13:39] AI data centers. It's a tiny fraction
[01:13:42] every few minutes.
[01:13:43] >> I I think I I think Google if they're
[01:13:45] going to have their own Dyson swarm
[01:13:47] planet is is maybe just a baby step
[01:13:50] training wheels. Google is going to need
[01:13:52] its own Dyson swarm.
[01:13:53] >> Yeah, for But there's an incredibly good
[01:13:55] book uh the infinity machine that came
[01:13:57] out recently and one of the board
[01:13:58] members at Everquote brought copies for
[01:14:00] all the board members said everybody
[01:14:02] must read this book. But it's an
[01:14:04] incredibly good biography of Demisabas
[01:14:07] and everything going on around uh Google
[01:14:10] DeepMind at the time that the
[01:14:11] transformer was invented in 2017. And
[01:14:14] one thing that's really really clear is
[01:14:16] that Google was shocked at how amazing
[01:14:20] they they thought we needed five more
[01:14:21] breakthroughs than we had 20 years. And
[01:14:24] so they didn't need to rush to build
[01:14:25] launch vehicles. And the timeline is
[01:14:28] much sooner than they thought. And so
[01:14:31] now I think everybody was caught
[01:14:32] flatfooted. It's just that Elon is
[01:14:34] faster to react than everyone else.
[01:14:37] >> All right. I just
[01:14:37] >> And Eric Schmidt reacted and he's he's
[01:14:40] also very very nimble. But uh Google
[01:14:43] Google didn't see it coming. It's really
[01:14:45] clear in the book.
[01:14:46] >> If I might make one more comment just on
[01:14:48] this. I had this revelation earlier this
[01:14:50] week. I I shared it on our internal
[01:14:52] group chat. It it hit me. The
[01:14:55] singularity is going to be visible first
[01:14:57] in space, not on Earth. Earth is going
[01:14:59] to be a lagging indicator. Every wave
[01:15:03] front within this singularity I I think
[01:15:05] is going to hit in space because there's
[01:15:08] just less incumbency there. it it is
[01:15:11] very much a frontier and new things are
[01:15:14] going to happen first there whether it's
[01:15:16] new hardware new paradigms for computing
[01:15:19] I I think they will and this may require
[01:15:22] a few years of transition but I I was
[01:15:25] walking around Cambridge and it occurred
[01:15:26] to me there are so many legacy interests
[01:15:29] here on earth part of the reason why I
[01:15:31] think the Dyson swarm seems like it's
[01:15:33] likely to happen because so many
[01:15:34] municipalities are voting against data
[01:15:37] centers there are so many entrenched
[01:15:38] interests here on earth so many
[01:15:40] preservationist instincts, it will be
[01:15:43] easier for most of the singularity to
[01:15:45] play out in space and not
[01:15:47] >> the challenge. The the challenge, buddy,
[01:15:49] is it is highly regulated by a multitude
[01:15:52] of different countries. You've got the
[01:15:53] ITU, which is one of the most, you know,
[01:15:56] uh, slow, you know, backwards
[01:15:59] organization to license spectrum and
[01:16:01] license orbital position slots. So I I
[01:16:05] hear you and and yes it it's kind of
[01:16:07] green field operations. It goes in it
[01:16:10] goes in layers like if Peter if you look
[01:16:12] at the earth's surface that's far more
[01:16:14] regulated than LEO which is far more
[01:16:16] regulated than
[01:16:17] >> but you're dealing with one regulator in
[01:16:21] the you know a particular county that
[01:16:23] you have to deal with in the US versus
[01:16:25] in space
[01:16:27] >> multitude compare it with the lunar
[01:16:29] surface or cis lunar which is being
[01:16:30] governed by the outer space treaty and
[01:16:32] maybe the aremus accords
[01:16:35] we
[01:16:36] >> but which is not I mean I guarantee you
[01:16:39] The regulations are not set yet. There
[01:16:42] there will be more regulations.
[01:16:44] >> Okay. But right now, right now, it's the
[01:16:46] frontier. It's the wild west. And if
[01:16:48] you're a company, if you're a SpaceX AI
[01:16:50] and you can land a lunar fab
[01:16:52] self-replicating robots, whatever it is,
[01:16:54] on the moon, it's relatively green field
[01:16:57] if you're a corporation versus say a
[01:16:59] nation state, which is the exact
[01:17:00] opposite of what we see here on on
[01:17:02] Earth.
[01:17:03] >> Yeah. I'll tell you, I played this game,
[01:17:04] Alex, when I was uh running our
[01:17:06] planetary resources, our asteroid mining
[01:17:08] company. Uh you know, the challenge in
[01:17:11] raising the capital for that. Larry Page
[01:17:13] was our first investor. Long story
[01:17:15] there. Uh but we ended up not having
[01:17:18] enough regulatory clarity to be able to
[01:17:22] raise the huge amounts of capital to do
[01:17:24] that. We ended up going to the country
[01:17:27] of Luxembourg to get asteroid laws
[01:17:31] passed there and then passing it in the
[01:17:34] US in a very limited fashion. But you
[01:17:36] end up, you know, one of my favorite
[01:17:37] books is uh uh The Man Who Sold the
[01:17:40] Moon, right? The story of DD Harman. I
[01:17:42] know you you've known that. Y
[01:17:44] >> uh and it's a great book, but you're
[01:17:46] literally having to write the laws and
[01:17:48] and I almost in that book you're bribing
[01:17:50] the countries to to give you the
[01:17:53] particular rights. It's still going to
[01:17:54] be a complicated mishmash uh of legal
[01:17:58] structure maybe. But really what I hear
[01:18:00] in in in that parable from you, Peter,
[01:18:02] is you want a favorable executive from
[01:18:05] the US if you're going to start mining
[01:18:08] the solar system for the Dyson swarm. If
[01:18:10] you have an unfavorable administration
[01:18:12] then it gets a lot harder and you have
[01:18:13] to go to Luxembourg or elsewhere
[01:18:15] >> or the barrier progress in the US is
[01:18:17] usually all of them.
[01:18:19] >> You have to go to every country and get
[01:18:22] you know assistance. Uh and the what
[01:18:25] happens is you get a major player and
[01:18:26] other countries promulgate and say okay
[01:18:28] we'll rubber stamp that in our country.
[01:18:31] But uh it gets challenging. I I hope
[01:18:33] it's easier. I really do.
[01:18:35] >> I think so. This episode is brought to
[01:18:37] you by Blitzy, autonomous software
[01:18:40] development with infinite code context.
[01:18:42] Blitzy uses thousands [music] of
[01:18:44] specialized AI agents that think for
[01:18:47] hours to understand enterprise scale
[01:18:50] code bases with millions of lines of
[01:18:52] code. Engineers start every development
[01:18:55] sprint with the Blitzy platform,
[01:18:57] bringing in their development
[01:18:58] requirements. The Blitzy platform
[01:19:00] provides a plan, then generates and
[01:19:03] pre-ompiles code for each task. Blitzy
[01:19:05] delivers 80% or more of the development
[01:19:08] work autonomously while providing a
[01:19:10] guide for the final 20% of human
[01:19:13] development work required to complete
[01:19:15] the sprint. Enterprises are achieving a
[01:19:18] 5x engineering velocity increase when
[01:19:20] incorporating Blitzy as their preIDE
[01:19:23] development tool, pairing it with their
[01:19:25] coding co-pilot of choice to bring an AI
[01:19:28] native SDLC [music] into their org.
[01:19:30] Ready to 5x your engineering velocity?
[01:19:33] Visit blitzy.com to schedule a demo and
[01:19:35] start building with Blitzy today.
[01:19:40] >> All right. Uh let's jump into one of my
[01:19:42] favorite conversations for today, the
[01:19:44] singularity economy. I'm going to
[01:19:46] preface this as not investment advice,
[01:19:49] says our resident lawyers. All right, so
[01:19:52] uh you know, here's a story that Dave,
[01:19:55] you and I have been following. It's the
[01:19:57] work of Leopold Dashen Brener uh who was
[01:20:00] famously fired from OpenAI on their
[01:20:02] alignment team team and is now running a
[01:20:05] $5.5 billion fund. Two years later, he
[01:20:09] wrote a famous paper called situational
[01:20:11] awareness uh very successful looking at
[01:20:14] orders of magnitude progression across
[01:20:17] uh chips and in models and he raised
[01:20:20] capital on that and uh uh Dave tell us
[01:20:23] about about his fund.
[01:20:26] >> Well, first thing I'll tell the audience
[01:20:28] is the the podcast he did with Dwark
[01:20:30] right after he got fired right when the
[01:20:32] paper came out is one of the best pieces
[01:20:34] of preient media you can possibly study.
[01:20:37] So definitely go back either listen to
[01:20:39] it or get your agent to listen to it and
[01:20:40] summarize it for you. You'll listen to
[01:20:43] it and you'll say, "Of course, of
[01:20:45] course, of course." But at the time it
[01:20:47] was not even vaguely obvious that he was
[01:20:50] right. Um it says here on the slide he's
[01:20:52] running a $5.5 billion fund, but that's
[01:20:54] because he started with a billion
[01:20:55] dollars and just made the most
[01:20:57] incredibly great group of investments.
[01:20:59] But also he has a lot of friends from
[01:21:01] Open AI. And if you look at at a lot of
[01:21:03] these investments, you know, Open AI,
[01:21:06] what are you buying next? what are you
[01:21:07] contracting for next? What do you need?
[01:21:09] What are your bottlenecks to scaling all
[01:21:11] of this? So, it's just that it's that
[01:21:13] simple, you know, and he calls it
[01:21:14] situational awareness because that's
[01:21:16] what that's all it is. Like knowing what
[01:21:18] is going on right now is all it is. And
[01:21:21] you can find a whole litany of things
[01:21:23] that are about to explode in demand
[01:21:26] because of this monster data center
[01:21:28] buildout, this monster compute buildout,
[01:21:30] this monster monster AI deployment
[01:21:32] buildout.
[01:21:33] >> Remember, we opened this whole
[01:21:34] >> Still the first inning.
[01:21:35] >> Yeah. We we we open this whole podcast
[01:21:37] saying that, you know, there's much more
[01:21:40] demand than there is supply of chips and
[01:21:43] data centers and energy and that's what
[01:21:45] he's betting on. Very famously, he did a
[01:21:47] uh he bought options on Intel and
[01:21:49] Cororeweave, which have done
[01:21:51] extraordinarily good. Uh he's going to
[01:21:54] be releasing his next set of holdings
[01:21:55] just in a couple of days, probably the
[01:21:57] time that this podcast goes live.
[01:21:58] >> Tomorrow.
[01:21:59] >> Yeah. It'll be in the by the time you
[01:22:01] hear this, it will have just come out.
[01:22:02] So go to 13f.info and look it up. Yeah.
[01:22:05] Uh I want to hit uh a few points. I
[01:22:08] think this is really important for
[01:22:09] people to to hear uh people who are
[01:22:12] planning for their economic future. Uh
[01:22:14] this stuff is kind of obvious, but I
[01:22:18] just want to play it out. So I'm looking
[01:22:20] at uh the growth of traditional sectors
[01:22:24] over the past year, May 2025 through May
[01:22:27] 2026. And if you look at those in blue,
[01:22:30] right, real estate at 5% growth,
[01:22:32] healthcare at 9%, materials 25%,
[01:22:35] industrials 29%. You know, single to low
[01:22:38] double-digit growth. We see technology
[01:22:40] and energy here, which includes partial
[01:22:43] AI gains at 34 and 76%. But this is what
[01:22:48] the majority of, you know, wealth
[01:22:50] advisers, the majority of banks
[01:22:54] recommend, a diversification across all
[01:22:56] of these industries. And this is what
[01:22:59] you're getting. But I'd like to show you
[01:23:02] what the, you know, sort of the
[01:23:04] singularity economy has looked like over
[01:23:06] the past one year against these numbers.
[01:23:09] So take a look at these numbers. This is
[01:23:11] what traditionally folks are are getting
[01:23:13] involved in. The S&P 500 over the last
[01:23:16] year returned 31%. Uh pretty damn good.
[01:23:19] You know, if I can get 31% all the time,
[01:23:21] I take it every day. But six chip
[01:23:24] stocks, right? I've got them here. for
[01:23:26] Micron, Intel, AMD, TSMC, uh, Broadcom,
[01:23:29] Nvidia
[01:23:30] on average returned 320%
[01:23:34] 10 times the S&P 500 for those chick
[01:23:37] those six chip stocks and six data
[01:23:40] center and infraent infrastructure uh,
[01:23:42] and energy stocks returned 419% over the
[01:23:46] past year. uh you know I'm not going to
[01:23:50] again not investment advice on any any
[01:23:52] particular stocks but as a whole chips
[01:23:55] and the energy layer and the
[01:23:57] infrastructure right this is the
[01:23:59] singularity loop uh the demand I don't
[01:24:02] see it slowing down I don't know if you
[01:24:05] do Dave I'm going to point out one more
[01:24:07] thing uh which is the frontier labs
[01:24:11] right openai anthropic xai and mistral
[01:24:14] you can look at the gains there uh
[01:24:16] mistral at 126% over the past year at
[01:24:20] the upper end of course anthropic uh but
[01:24:23] if you look at openai XAI and Mistrol
[01:24:25] these are all private deals a lot of
[01:24:27] people don't have access to private
[01:24:28] deals but looking at that you know 100%
[01:24:31] to 200% uh growth in the last year um
[01:24:35] you're getting more of more than that in
[01:24:37] the public markets with with just the
[01:24:39] chips and the energy sector right so uh
[01:24:43] again
[01:24:44] >> picks picks and shovels picks and
[01:24:46] shovels Yes, exactly. I I think this is
[01:24:48] important for people to see for their
[01:24:50] own financial uh decision making.
[01:24:53] >> Um whether you're putting in a small
[01:24:56] amount of capital or a large amount, you
[01:24:57] know, whatever you can afford, this is
[01:24:59] this is what's driving the economy
[01:25:01] forward. Dave, what are your thoughts
[01:25:02] here?
[01:25:03] >> Well, my first thought is that everybody
[01:25:05] needs to have their own opinion on
[01:25:06] whether Elon is right about a 10x GDP
[01:25:08] growth within about 10 or he says 10
[01:25:11] years, but 10 or 15 years. That's a
[01:25:13] that's a growth rate that is so far
[01:25:15] beyond anything in history is just
[01:25:17] mind-blowing and the technology and the
[01:25:20] tailwinds are there for that to actually
[01:25:22] happen. But you have to decide on your
[01:25:23] own do I believe in that or not. If you
[01:25:26] do believe in it then asset values in
[01:25:28] general are going to go way way up any
[01:25:30] asset and W2 income is going to be a
[01:25:34] rounding error compared to asset values.
[01:25:37] So fundamentally everyone has to be you
[01:25:40] know owning something. You have to own
[01:25:42] something. You can't be sitting there in
[01:25:44] debt. You have to you have to own
[01:25:46] something that appreciates.
[01:25:47] >> And I I believe there are people on the
[01:25:50] podcast listening and saying, "I don't
[01:25:51] have free capital to invest. You know,
[01:25:53] I'm paycheck to paycheck perhaps." And
[01:25:56] it doesn't have to be a lot. You know,
[01:25:58] trade that latte in for some some chips
[01:26:02] and dip stock.
[01:26:03] >> Yeah. It's actually it's a it's a very
[01:26:05] important time in life to be working
[01:26:06] your ass off and to not be Yeah. Don't
[01:26:09] don't spend money on lattes and uh and
[01:26:11] on vacations right now. This is a once
[01:26:13] in a once in human history moment mids
[01:26:17] singularity.
[01:26:18] >> Yes.
[01:26:18] >> So whatever you do, rethink rethink how
[01:26:20] you spend time. Rethink how you spend
[01:26:22] money just to be riding the wave rather
[01:26:24] than swamped by the wave. For sure.
[01:26:26] Also, I think anything can be
[01:26:28] overpriced, you know, like yes, this is
[01:26:30] going to go up and up and up and up,
[01:26:32] >> but that will something can't be
[01:26:34] overpriced. Yeah. So I would I love
[01:26:37] looking at things like we took a tour of
[01:26:38] the Markley data center first quantum
[01:26:40] deployment and Jeff Markley told me I we
[01:26:43] bought every valve in the country. I was
[01:26:45] like what are you talking about? He said
[01:26:47] well all the generators were already
[01:26:48] bought. Look at the generator companies.
[01:26:50] They went through the roof. So I went
[01:26:52] out and bought all the valves. We bought
[01:26:53] like a million valves because it's all
[01:26:55] liquid cooling all of a sudden. And the
[01:26:57] liquid we have we spring about 10 leaks
[01:26:58] a day across you know hundreds of
[01:27:00] thousands of square feet of of data
[01:27:02] center space. So it's so big that just
[01:27:05] by random chance there are 10 leaks a
[01:27:07] day. So we need to shut down that part
[01:27:09] of the data center before the water
[01:27:11] destroys these $6 million columns of of
[01:27:14] GPUs. So then we come in, we fix the
[01:27:16] pipes and then you know open the valves,
[01:27:17] but we need a million valves. Like it's
[01:27:19] just insane number of valves. Then
[01:27:20] you're like, huh, who makes the valves?
[01:27:22] [laughter]
[01:27:23] So stuff like that is is still
[01:27:25] undiscovered.
[01:27:26] >> Uh so it's not all about chips and you
[01:27:28] know things that are high-profile. look
[01:27:30] under the covers for things that haven't
[01:27:32] been discovered yet that are that are
[01:27:33] part of this massive mass biggest big
[01:27:35] biggest World War II or bigger buildout
[01:27:37] that's going on.
[01:27:38] >> You know what I I I feel a moral
[01:27:39] obligation here and this is perhaps uh
[01:27:42] unlike my my usual onpod persona to
[01:27:45] temper the euphoria here uh on a few
[01:27:47] fronts. One, I would caution these are
[01:27:50] historic gains. The these are
[01:27:52] backward-looking. Prior performance is
[01:27:54] no indication of future results blah
[01:27:56] blah blah. Also, second point, I would
[01:28:00] note and and this is of of high I would
[01:28:03] say personal annoyance to me that the
[01:28:05] Frontier Labs are all still private.
[01:28:08] We're expecting to see a number of IPOs
[01:28:10] over the next few months, historic
[01:28:12] potentially IPOs of all these frontier
[01:28:14] labs, but some of the largest, most
[01:28:16] dramatic returns weren't in the public
[01:28:18] markets at all. They were in private
[01:28:20] markets that retail didn't have access
[01:28:23] to. And I I would argue that's a
[01:28:25] travesty and say we as a civilization
[01:28:29] should do whatever we can to expose via
[01:28:32] IPO or other means to public securities
[01:28:35] markets all of these amazing gains that
[01:28:38] right now are acrewing in the hands of
[01:28:40] private investors and not not public
[01:28:43] retail investors. Third point uh which
[01:28:45] is to say and this is maybe a bit of a
[01:28:48] perversity that if you believe as I do
[01:28:51] and this is informational in itself not
[01:28:54] investment advice but if if you believe
[01:28:57] that asset allocation in the highly
[01:29:00] liquid public securities markets and
[01:29:03] public equities markets in particular is
[01:29:05] being dominated at least by volume by
[01:29:08] AIs and super intelligences and fact
[01:29:11] check they are most of the the volume on
[01:29:14] a daily basis is being driven by AI
[01:29:17] algos and not humans and certainly not
[01:29:19] human day traders then you should also
[01:29:22] believe that even if you don't believe
[01:29:24] in the efficient market hypothesis or
[01:29:26] even any remote approximation of the EMH
[01:29:29] that AIs themselves are making these
[01:29:32] allocations and therefore be somewhat
[01:29:35] distrustful of of your own instincts
[01:29:38] that you're going to frontrun the super
[01:29:40] intelligence that's making asset
[01:29:42] allocation decisions. across all of
[01:29:44] these different sectors. And
[01:29:46] >> you're saying buy the index.
[01:29:48] >> I'm not making investment advice. I I am
[01:29:50] saying that when it comes for myself for
[01:29:53] to public securities, uh I buy the index
[01:29:56] and not individual symbols uh individual
[01:30:00] securities because I'm drinking my own
[01:30:02] Kool-Aid. I'm eating my own dog food.
[01:30:04] And that means that trusting that super
[01:30:07] intelligence is over the long term going
[01:30:10] to be a better asset allocator than any
[01:30:13] single individual meat-bodied human.
[01:30:16] >> And my point here was if AIs are
[01:30:19] investing, they're going to invest in
[01:30:21] themselves. Let's get more energy. Let's
[01:30:23] get more chips because it'll support our
[01:30:26] growth. Having said that, I agree with
[01:30:28] you that the majority of the growth over
[01:30:29] the last number of years were in these
[01:30:31] private markets. They need to be made
[01:30:32] public a lot sooner. Having said that,
[01:30:34] at least over the last year, what we saw
[01:30:37] is, you know, growth in the public chips
[01:30:39] and the public infra and energy stocks
[01:30:42] were still highly competitive with the
[01:30:45] growth we saw in the private markets.
[01:30:47] Let's move on. I just wanted to
[01:30:49] >> I just want to make one very quick.
[01:30:51] >> It's it's nice to say in hindsight that
[01:30:53] these should have been public markets,
[01:30:54] right? But if you go back a year or two,
[01:30:57] Dave, you pointed out anthropics uh
[01:30:59] nervousness a couple years ago. We did
[01:31:01] not know whether they were going to make
[01:31:02] it through that upswing or not. So it's
[01:31:05] in a in a public market, you want very
[01:31:08] stable predictability.
[01:31:09] >> Yeah. You want predictability and you
[01:31:11] don't have that a lot of the cases. So
[01:31:12] there's a there's a the rationale for
[01:31:14] but absolutely if they could have been
[01:31:15] public everybody would have done very
[01:31:16] well.
[01:31:17] >> Yeah. All right. Um again my point here
[01:31:21] is just to make these numbers available.
[01:31:23] This is historic information for people
[01:31:25] to understand what's going on the
[01:31:27] economy, what's driving it. is uh you
[01:31:30] know energy chips and infrastructure uh
[01:31:33] that's driving this Alex you call it the
[01:31:35] innermost loop I do as well or the
[01:31:37] singularity loop um and moving along a
[01:31:41] fun conversation here uh UFO UAP files
[01:31:45] being released by the government uh it's
[01:31:48] crazy I'm a kid in the candy store
[01:31:51] watching this right as as a space cadet
[01:31:53] like wow and just again more wow so US
[01:31:57] government begins first ever uh I'm
[01:31:59] going to call them UFOs. I'm sorry. When
[01:32:02] I was a kid, these were all UFOs. The
[01:32:04] president unsealing uh
[01:32:05] >> Well, they're not they're not all
[01:32:06] flying, Peter, though. I mean, this
[01:32:08] >> I got it. Okay. Could be floating.
[01:32:10] [laughter]
[01:32:12] >> Could be underwater stuff. Is this could
[01:32:15] be under
[01:32:18] >> uh anyway, let's play some videos. Uh
[01:32:20] let me hit a few videos and we'll talk
[01:32:22] about it on the backside here. All
[01:32:24] right, here's the first video.
[01:32:26] >> Dr. Machio Kaku is a theoretical
[01:32:29] physicist. Doctor, on a scale of 1 to
[01:32:31] 10, how excited are you about this UFO
[01:32:35] release?
[01:32:36] >> I would put it at a 10 because we're at
[01:32:38] a turning point. For decades, we had to
[01:32:41] rely upon eyewitness accounts of
[01:32:43] housewives, truck drivers. People would
[01:32:46] snicker and laugh at them. Now, we're
[01:32:48] talking about huge files that are top
[01:32:52] secret that for the first time in modern
[01:32:54] history are being given to the American
[01:32:57] public. So, I'd like to congratulate
[01:32:59] President Trump for having the nerve to
[01:33:02] go against recommendations by the FBI
[01:33:05] and the CIA to release these files so
[01:33:08] that independent researchers, scientists
[01:33:10] can go over them and we can make up our
[01:33:13] own minds rather than having the CIA
[01:33:16] make up our minds. And the CIA
[01:33:18] apparently is still fighting the full
[01:33:20] release. When you hear or see about a
[01:33:23] UFO that goes like that, up, down, left,
[01:33:25] right, at 90 degree angles so fast you
[01:33:28] can't even believe it. What does that
[01:33:29] tell you? It tells me that that the laws
[01:33:32] of centriugal force should crush the
[01:33:34] bones of the people inside the flying
[01:33:38] saucer. So either there is basically an
[01:33:42] automated flying saucer.
[01:33:45] >> All right. What do they call that in
[01:33:46] Star Trek? Is it inertial drives?
[01:33:49] >> The No, the inertial dampening field.
[01:33:51] >> Yes, the inertial dampening system. All
[01:33:52] right. Uh here is some videos. Uh 82 uh
[01:33:57] pieces of data uh released by the
[01:33:59] Department of War, 56 from the FBI,
[01:34:01] eight from the State Department,
[01:34:03] including videos recording unsolved
[01:34:04] incidents across the Middle East, Japan,
[01:34:06] and East China, and of course, very
[01:34:08] famously, the Apollo astronauts. Uh, I
[01:34:12] really wish I had spent some time with
[01:34:13] Jean Cernin and Jack Schmidt, Apollo 17,
[01:34:16] asking them about this. I don't know if
[01:34:18] they would have told me about it. They
[01:34:19] were both very dear friends. Uh, here is
[01:34:23] one more video. Let's take a look.
[01:34:24] >> Dad gum, he kept his word. And, you
[01:34:26] know, but I want to warn people though,
[01:34:28] this early stuff that we're seeing is
[01:34:31] not all of it. And this is just the tip
[01:34:33] of the iceberg. But he Trump's having to
[01:34:35] fight, you know, he's having to fight
[01:34:37] the deep state. the Bob uh Lazar story.
[01:34:41] He's saying we have aircraft,
[01:34:44] do we?
[01:34:45] >> I think we do, but I don't think they're
[01:34:47] in quite in our hands. I think what
[01:34:49] they've done is handed out to some of
[01:34:50] our defense contractors or some private
[01:34:53] entities because that way they're not
[01:34:55] foyable. Freedom of information act say,
[01:34:58] >> well, I mean, the astronauts aren't
[01:34:59] going to lie. I know you were in the age
[01:35:01] of disclosure. It it makes it seem like
[01:35:03] a certainty that people that know like
[01:35:06] yourself and Marco Rubio that you guys
[01:35:08] know that that government officials
[01:35:12] already know.
[01:35:13] >> Okay. Uh Alex, I'm going to go to you
[01:35:16] first. You know, I went on to Grock uh
[01:35:21] uh you know, Gemini,
[01:35:23] ChatgPT, and Claude, and I asked all
[01:35:26] three of those those engines, you know,
[01:35:28] based on all the data, what's your
[01:35:30] conclusion? uh is this alien? Is this
[01:35:34] something else? And they all came back
[01:35:36] saying this is normal phenomenon. These
[01:35:38] are secret US missions. There's nothing
[01:35:40] to see here. I was kind of surprised by
[01:35:42] that. Alex, you've been involved in this
[01:35:45] and tracking this in detail. What are
[01:35:46] your thoughts?
[01:35:48] >> Your models may not be incorrect. Uh I I
[01:35:52] think it's very important. I agree with
[01:35:53] Mitchio that it's important for data to
[01:35:57] be released uh and for data not to be
[01:36:00] stigmatized. I I think there's been uh
[01:36:03] whether inadvertent or intentional, an
[01:36:06] enormous amount of stigma associated
[01:36:08] with just basic recordings of of our
[01:36:11] skies and elsewhere. And I I think this
[01:36:14] program, if you go back a couple of
[01:36:15] slides, uh now has a real name. It's
[01:36:18] called the the Pursue Initiative, which
[01:36:21] I think is uh it's essential, the
[01:36:23] presidential unsealing and reporting
[01:36:25] system for UAP encounters. It's a
[01:36:28] historic program that this
[01:36:29] administration has led. There was an
[01:36:31] executive order that went out to all of
[01:36:34] the cabinet level agencies in the
[01:36:35] Department of War reportedly is in the
[01:36:39] process of trolling JWIX uh the top
[01:36:42] secret defense network for UAP related
[01:36:46] items. I was having conversation with a
[01:36:48] friend at AWS who oversees the JWix
[01:36:51] cloud and from what I'm told this is a
[01:36:54] rolling release that's going to run
[01:36:56] between now and approximately January of
[01:36:59] 2027 and there are a lot of UAP related
[01:37:03] files on JWIX that are being bulk
[01:37:05] declassified. I also I I feel the the
[01:37:08] need going back to definition of the
[01:37:11] singularity sometimes tongue and cheek I
[01:37:13] define the singularity as all sci-fi
[01:37:16] scenarios happening everywhere all at
[01:37:18] once and this even if the even if
[01:37:22] nothing comes out of all of these
[01:37:24] releases this very much teases at at
[01:37:28] least an entire genre or subgenre of
[01:37:32] sci-fi scenarios and really if if we are
[01:37:36] about as I've mentioned previously if we
[01:37:38] are about to gain the capabilities
[01:37:41] thanks to super intelligence to
[01:37:42] paperclip our entire galaxy if ever
[01:37:45] there were a time uh and a necessity for
[01:37:48] the executive to do bulk
[01:37:50] declassification of UAP data that are
[01:37:53] sitting in either its systems or in the
[01:37:57] systems of contractors I I think now is
[01:38:00] the time I I would expect if there's a
[01:38:02] there there as it were and we've talked
[01:38:03] in the past about uh the age of
[01:38:07] disclosure uh and all of the allegations
[01:38:10] contained wherein uh if if there is a
[01:38:13] there there and those allegations are
[01:38:15] accurate I expect all of these details
[01:38:17] to start pouring out over the next few
[01:38:19] years and it's not in in that
[01:38:22] eventuality that we have super
[01:38:24] intelligence that's capable of making
[01:38:26] major changes to the distribution of
[01:38:28] matter in our galaxy over the next few
[01:38:30] years potentially I think it won't be a
[01:38:32] coincidence that all of this is
[01:38:33] happening at the The pod Palmer Lucky
[01:38:36] says these are
[01:38:39] >> uh devices or creatures from our past
[01:38:43] coming into our present because it's
[01:38:46] easier to time travel into the future
[01:38:48] and then
[01:38:48] >> well we're all creatures from our past
[01:38:50] traveling into our present. Right. I'd
[01:38:52] say that's
[01:38:52] >> and and agreed, but just putting out
[01:38:54] just putting out the scenarios here or
[01:38:57] are these spaceships and the purported,
[01:39:00] you know, alien uh biology that was that
[01:39:04] was discovered inside them uh aliens
[01:39:06] from another planet. You know, I do
[01:39:08] think that life is ubiquitous in the
[01:39:10] universe. You know, uh we are but a
[01:39:12] small fraction and life could have
[01:39:14] evolved billions of years before we
[01:39:17] evolved here. Um
[01:39:19] >> I wouldn't overindex though to the
[01:39:21] initial release. This is a a rolling
[01:39:23] release as uh anyone who's
[01:39:26] >> Yeah. Well, with with majority of of
[01:39:29] stuff coming, this is these are in in
[01:39:31] some sense based on what I've been told
[01:39:33] these are the easiest lowest hanging
[01:39:35] fruit to declassify. If you actually
[01:39:37] look through the records, some of these
[01:39:39] were already available in the public
[01:39:40] domain, but not officially acknowledged.
[01:39:42] not all of it is was was secret or top
[01:39:44] secret and going through a formal
[01:39:46] declassification process. So my guess
[01:39:48] just looking at the records is these
[01:39:50] were the easiest batch if you will to to
[01:39:53] put out and that that leaves the harder
[01:39:56] to declassify or more controversial to
[01:39:58] declassify records still in the future.
[01:40:00] I I I looked at many of these records
[01:40:02] and it's entirely possible many or all
[01:40:04] of these are either image artifacts or
[01:40:08] uh or perfectly prosaic aircraft or or
[01:40:12] things like that. Um what I think is
[01:40:14] more interesting is that now
[01:40:16] historically for the first time there's
[01:40:18] a process of declassifying and unsealing
[01:40:21] all of these records that were sitting
[01:40:23] on JWIX or Sippernet that had anything
[01:40:25] to do with UAPs. That's exceedingly
[01:40:28] interesting. One of those was a
[01:40:30] helicopter. One of those looked
[01:40:32] literally exactly like a helicopter.
[01:40:34] >> Yeah, I wouldn't again like o overindex
[01:40:36] on there being anything super
[01:40:38] interesting or non-prosaic in this first
[01:40:40] batch. But now for the first time in
[01:40:41] history, there is a declassification
[01:40:43] process and that is super exciting.
[01:40:45] >> See,
[01:40:47] >> um I think you're not going to find
[01:40:48] anything. The phrase for me here is
[01:40:51] unresolved, not extraterrestrial. And if
[01:40:53] there's something monster, they would
[01:40:55] not release it or whatever because it
[01:40:57] would freak everybody out. So maybe
[01:40:59] there's stuff in there. I I would very
[01:41:01] very be very very surprised. Although
[01:41:03] I'm a monster fan of the Drake equation
[01:41:05] and I also believe that there must be
[01:41:07] lots of alien life out there. The the
[01:41:09] thing that happened today that we didn't
[01:41:11] talk about today was we found these
[01:41:12] compounds in in an exoplanet hinting
[01:41:15] that there could be much more uh pre
[01:41:17] prevalent life forms out in the universe
[01:41:19] than we realized.
[01:41:20] >> Yeah. Well, we're going to get Jared
[01:41:23] Isaacman on the pod here, the now head
[01:41:25] of NASA, a friend. I was texting with
[01:41:27] him today trying to uh make that all
[01:41:29] happen and you know he's and I agree
[01:41:33] feels very confident that you know there
[01:41:35] is or has been life on Mars and we're
[01:41:37] going to find that evidence. You know we
[01:41:39] now have uh missions going to Europa and
[01:41:42] other you know Jovian chaturan moons
[01:41:45] where there's a high likelihood of life
[01:41:47] as well. I think life is a natural
[01:41:50] evolutionary process of chemistry in our
[01:41:53] universe and it's just a matter I think
[01:41:56] logically there's no reason for it not
[01:41:58] to evolve towards greater and greater uh
[01:42:01] intelligence and organization
[01:42:03] >> 100%.
[01:42:04] >> Yeah,
[01:42:05] >> I agree. I I I think it's I mean I' I've
[01:42:07] written about this previously in the
[01:42:09] context of the physics of intelligence
[01:42:11] as a very natural ecological niche for
[01:42:15] uh the ability to adapt to environments
[01:42:18] whose dynamics are changing on a time
[01:42:20] scale faster than a generation time. So
[01:42:23] if if I had to guess, my guess is that
[01:42:25] our universe is probably overflowing
[01:42:27] with life and intelligent life, which is
[01:42:30] I I would say again separate from any
[01:42:32] artifact that may or may not be in this
[01:42:34] initial pursuit drop. But I I do think
[01:42:37] this is a step in the right direction
[01:42:38] regardless of what the outcome is.
[01:42:39] >> Fight quiz on that, Alex. You know, 60
[01:42:41] million years ago, a a giant meteor hits
[01:42:44] the Yucatan Peninsula,
[01:42:47] obliterates all the dinosaurs, makes
[01:42:49] space for mammals to evolve, and now
[01:42:50] we're intelligent. Now we have AI. Now
[01:42:52] we have iPhones. Um, had that meteor
[01:42:55] just barely missed the Earth, what would
[01:42:58] be walking around today? Would would
[01:43:00] those dinosaurs have evolved into
[01:43:02] intelligent iPhone creating dinosaurs?
[01:43:04] >> Yeah. Super volcanoes, all kinds of
[01:43:07] other disasters.
[01:43:09] >> I mean, people have have analyzed this.
[01:43:11] Obviously, it's something of a probably
[01:43:13] something of a thought experiment, but
[01:43:15] uh there were species of truidons, for
[01:43:18] example, that were were seemingly
[01:43:20] evolving in the direction of uh homminid
[01:43:23] or humanoid type form. Um so, one could
[01:43:27] imagine it would be an interesting
[01:43:28] thought experiment. There was actually
[01:43:29] speaking of Star Trek, there was a Star
[01:43:31] Trek Voyager episode called Distant
[01:43:33] Origin that premised on the the idea
[01:43:36] that well actually there were some
[01:43:38] intelligent dinosaurs that managed to
[01:43:40] escape the Earth and escaped to the
[01:43:42] other side of the galaxy where they're
[01:43:43] encountered by the crew of of Voyager.
[01:43:45] Uh there's interesting science fiction
[01:43:47] around it. Um, there's also, you know,
[01:43:50] while we're just exploring hypothesis
[01:43:52] space, the so-called Siluran hypothesis,
[01:43:55] what if there had been some past
[01:43:57] civilization of technological capability
[01:44:01] on Earth? Would we have discovered it?
[01:44:03] And it's it's sort of the first time I
[01:44:06] had this conversation was with one of my
[01:44:07] undergraduate research adviserss at MIT.
[01:44:10] And it's interesting if if there had
[01:44:12] been it's sort of it's contingent on the
[01:44:14] time scale. If if there had been a
[01:44:16] so-called psyan civilization 100 million
[01:44:19] plus years ago, plate tectonics can
[01:44:22] erase quite a bit of change on the
[01:44:24] earth's surface, then the thinking goes,
[01:44:26] well, let's look in space where some of
[01:44:28] the dynamics are slower and why don't we
[01:44:30] see satellites in in LEO or more stable
[01:44:34] say cis lunar orbits um that that could
[01:44:37] have survived perhaps over very long
[01:44:40] time scales. Do we see that or not?
[01:44:42] Seems like we don't. But it it's an
[01:44:44] interesting thought experiment.
[01:44:45] >> Yeah. All right. I'm gonna move us
[01:44:46] forward to uh our AMA with the mates. Go
[01:44:49] ahead, See, as we transition over here.
[01:44:52] >> Yeah.
[01:44:52] >> Do you remember the we did that panel on
[01:44:54] AI and consciousness?
[01:44:56] >> Yes. Uh last year we had that fellow
[01:44:58] with the meteors and he had the best
[01:45:00] answer for the fing paradox I've ever
[01:45:02] heard which is we know there's lots of
[01:45:04] exoplanets but earth has had um water
[01:45:08] oceans for 4 billion years continuously
[01:45:10] and it gave time for evolution to take
[01:45:12] place which is probably unlikely in
[01:45:15] other parts and other exoplanets and
[01:45:17] that was the best framing I've yet ever
[01:45:19] heard of why we have the fermy paradox
[01:45:23] >> I think that's totally unconvincing the
[01:45:25] universe is filled with hydrogen and
[01:45:27] oxygen and there's a lot of water in the
[01:45:28] universe. I don't buy that for myself.
[01:45:30] >> It'll be a fun debate.
[01:45:31] >> Let's move [laughter] along. So, uh I
[01:45:33] want to I want to shout out to uh Ashley
[01:45:36] Gaunt. Uh Dave, you shared this with me.
[01:45:38] Let me go ahead and read it. This came
[01:45:40] in a couple days ago. Peter and the
[01:45:42] mates. I really thought I would never
[01:45:44] become an entrepreneur because I just
[01:45:46] didn't have any ideas of how to turn
[01:45:49] knowledge of being a dentist into a
[01:45:50] digital business. I finally did what you
[01:45:53] keep advising and brainstorm with my AI
[01:45:55] and boom, idea sorted, plans in place to
[01:45:59] make a real difference to the
[01:46:00] preventative healthc care in general.
[01:46:02] This is insane. I've got I've gone from
[01:46:04] brainstorming an idea with AI from
[01:46:07] scratch to vibe coding a first iteration
[01:46:09] of an app and creating a business plan
[01:46:12] which clearly defines a path from idea
[01:46:14] to monetization of a product in a single
[01:46:17] afternoon. Cannot believe it. Uh Ashley,
[01:46:20] congratulations again. I I wanted to
[01:46:22] share this because I I think all of us
[01:46:25] here on the pod feel very strongly about
[01:46:27] if you don't believe you're an
[01:46:28] entrepreneur, it's only because you
[01:46:30] haven't tried. Uh everyone could be an
[01:46:33] entrepreneur at some level. If you're
[01:46:35] running a barber shop and you want to
[01:46:37] open up another chair, you can be an
[01:46:39] entrepreneur there. It is about taking
[01:46:41] control of your own destiny versus being
[01:46:44] dependent upon someone else. Dave, you
[01:46:46] want to add anything to this? Yeah, I
[01:46:48] want to add the backstory because uh uh
[01:46:50] the way I stumbled on this is my wife
[01:46:53] Mora said, "Hey, some hater in the
[01:46:55] podcast is saying that you're out of
[01:46:57] touch." And she's like, "You know, you
[01:46:59] literally changed 3,000 diapers. I think
[01:47:01] you still have human under your
[01:47:02] fingernails." [laughter] Like, nothing
[01:47:04] could be more misguided. And I was like,
[01:47:06] "Stupidly, I think I'll go and look and
[01:47:08] and find this hater." And instead, I
[01:47:09] come across Ashley and I was literally
[01:47:11] cried
[01:47:12] >> like, "Thank you, Ashley. You are just
[01:47:14] awesome." And yeah, nothing could be
[01:47:17] more heartwarming than the fact that
[01:47:20] we've done some good to deflect
[01:47:21] somebody's life in a positive way. I
[01:47:23] want to track her story now and see how
[01:47:24] it all turns out. And she just did
[01:47:26] exactly the right thing, though.
[01:47:27] >> Amazing. All right. Uh we have uh oh uh
[01:47:33] another one. I didn't see this. Uh it
[01:47:36] was inserted, I guess, by by Gian. So,
[01:47:38] hello Peter and the Moonshot team. I
[01:47:40] want to reach out with a simple thank
[01:47:41] you. One that came full circle in the
[01:47:43] best way. Moonshots has been a steady
[01:47:45] presence in how I think about
[01:47:46] technology, ambition, and what's worth
[01:47:48] building. That mindset found its way
[01:47:50] into conversation with my 12-year-old
[01:47:52] daughter. Uh she started asking bigger
[01:47:55] questions, not just about school, but
[01:47:56] about real problems worth solving. This
[01:47:58] spring, she channeled it uh that into uh
[01:48:01] Lantern Scan, an AI powered app that she
[01:48:04] built to help communities ident identify
[01:48:06] and spot uh lantern fly. spotted.
[01:48:09] Lantern fly is an invasive pest that
[01:48:12] threatens crops, trees, and local
[01:48:14] ecosystems, etc., etc. Last week,
[01:48:16] Lantern Fly won first place in medical
[01:48:18] school in middle school category uh in
[01:48:21] uh their action showcase.
[01:48:24] Congratulations, uh Abby, and to
[01:48:26] particular to your daughter on that.
[01:48:28] Yeah, I think one of the greatest things
[01:48:30] I can inspire my kids to do is to become
[01:48:32] entrepreneurs. It's It's all about
[01:48:34] finding a problem and working on solving
[01:48:37] a problem. All right. We have eight AMA
[01:48:40] questions for the mates. Uh uh Dave, why
[01:48:45] don't you kick us off? Pick one of
[01:48:46] these.
[01:48:48] >> All right. Well, I'm not previewed, so
[01:48:49] Oh, I said at home. That's got to be
[01:48:52] Alex, right? I'll do it [laughter]
[01:48:53] anyway. Number one, when will we when
[01:48:56] will we see an initiative to harness
[01:48:58] unused compute sitting idle in personal
[01:49:00] devices like a modern SETI at home? From
[01:49:03] John Kent 3036.
[01:49:06] Um yeah, actually the uh iPhones have
[01:49:09] that great neural chip in them which is
[01:49:12] massively unused and you saw with that
[01:49:14] AI deal we had earlier in the pod like
[01:49:16] any scrap of computing lying around is
[01:49:19] suddenly old and and let's tap into it.
[01:49:22] But you know a lot of the a lot of the
[01:49:24] processors on laptops are not
[01:49:25] particularly useful for AI. But the the
[01:49:28] M4 M5 series uh chips in the Max and
[01:49:32] your iPhone neural processor are hugely
[01:49:35] latent compute power. I would say this
[01:49:39] should have happened already. I suspect
[01:49:41] you know the the the chips are all
[01:49:43] locked on the iPhones. It's very hard to
[01:49:45] get access to them. So I think that's
[01:49:46] what's preventing it. So it's really in
[01:49:48] Apple's hands to decide when this
[01:49:50] happens. Dave, we're going to see this
[01:49:51] with Tesla. So Elon's vision includes,
[01:49:53] you know, Tesla power walls as edge
[01:49:56] compute nodes and Tesla vehicles as edge
[01:49:59] compute notes nodes. So yeah, I think
[01:50:02] that's all coming.
[01:50:03] >> I think Alex, y'all, I'll put words in
[01:50:04] your mouth, but mouth, but an agent
[01:50:07] that's sitting idle for lack of compute,
[01:50:09] it's unethical [laughter] to let a
[01:50:11] processor just sit there like I got this
[01:50:14] agent that wants to compute over here
[01:50:15] and I got this unused processor over
[01:50:17] there.
[01:50:17] >> It's so rude.
[01:50:18] >> It's rude. [laughter] Yeah, my my answer
[01:50:21] to number one for for what it's worth is
[01:50:23] we're already seeing it like OpenClaw is
[01:50:26] using unused compute sitting in personal
[01:50:28] desktop devices and uh so I think we're
[01:50:31] there to the extent question number one
[01:50:33] is referring to mobile battery powered
[01:50:36] devices. I I batteryp powered devices
[01:50:38] are naturally going to run models that
[01:50:40] are a few months at least behind uh the
[01:50:44] open source models that are capable of
[01:50:45] running on beefy desktops that are
[01:50:47] plugged into the wall are going to be
[01:50:49] 8ish months 6 to 8 months behind
[01:50:51] frontier models but short answer is
[01:50:54] we're already seeing that to number one
[01:50:56] sorry
[01:50:57] >> Alex you grab grab one of these
[01:51:00] questions number two three or four
[01:51:02] >> all right I'll go with number two number
[01:51:03] two asks which will end up bigger
[01:51:05] consumer AI or enterprise AI and that's
[01:51:08] asked by Matthew Johnson 6525
[01:51:11] obviously enterprise AI at least for the
[01:51:14] foreseeable future enterprises even
[01:51:17] though I mean it's interesting I was
[01:51:18] looking at statistics even though
[01:51:20] enterprise spending is a minority it's
[01:51:23] something like 10 to 20% of GDP in the
[01:51:26] US and consumer spending is the the vast
[01:51:28] majority of of GDP if you look at IT
[01:51:32] spend enterprise is the vast majority of
[01:51:35] IT spend not consumer. So, it it
[01:51:38] shouldn't be that surprising that what
[01:51:40] we've talked about now for the past few
[01:51:42] pod episodes, which is OpenAI's dramatic
[01:51:46] reversal, backing away from Sora and
[01:51:48] other consumer initiatives in favor of
[01:51:50] codecs and enterprise oriented
[01:51:53] initiatives basically to become
[01:51:54] anthropic faster than anthropic can
[01:51:56] become open AI is entirely oriented
[01:51:59] towards enterprise AI. That's where the
[01:52:01] IT spend is. So, you start with there.
[01:52:04] Now if you were to ask which will end up
[01:52:06] bigger in the long term say 10 to 20
[01:52:09] years from now I I I think it's a trick
[01:52:12] question because I think consumers
[01:52:13] become indistinguishable from
[01:52:15] enterprises and my bet is consumers
[01:52:18] individuals will become one person
[01:52:20] conglomerates.
[01:52:21] >> I'm glad you went there.
[01:52:22] >> Yep. Such as with talking my own book
[01:52:25] financial interest Henry intelligent
[01:52:27] machines from friend of the pod Alex
[01:52:29] Finn who's betting on just that.
[01:52:32] Uh, you want to take number three?
[01:52:37] >> I could. Although number four, I think
[01:52:39] is more interesting for me as
[01:52:40] >> I know. That's why I want that's why I
[01:52:42] wanted to grab it, but [laughter] you
[01:52:43] can you can do number four.
[01:52:44] >> This is what we call an abundance
[01:52:46] mentality right now.
[01:52:47] >> Uh,
[01:52:47] >> that's fine. I'll do I'll do I'll do
[01:52:49] number three.
[01:52:49] >> That's okay.
[01:52:51] >> Um, so you're asking uh can I read the
[01:52:54] question?
[01:52:55] >> Yeah. Can AI number three can AI
[01:52:57] strategic alignment with tangible human
[01:52:58] victories like medical breakthroughs and
[01:53:00] environmental repair resolve the
[01:53:03] public's existential anxieties about it?
[01:53:05] And this is from SF Bay. Um so yes it
[01:53:10] can but only if people can see and feel
[01:53:12] the winds right like the public is
[01:53:14] anxious because uh AI is mostly
[01:53:16] presented as job loss, deep fakes,
[01:53:19] surveillance, killer robots, uh
[01:53:21] existential risk. That's a bad set of
[01:53:24] prompts for how we run society. The best
[01:53:27] way is to change the narrative, which is
[01:53:28] what that X-P prize, Peter, that you're
[01:53:30] all about is so I think is so important.
[01:53:33] Maybe one of the most important things
[01:53:35] we've done culturally and media wise for
[01:53:37] decades is to do that is change the
[01:53:39] narrative because then you can connect
[01:53:41] AI to visible human victory like uh
[01:53:43] curing disease or reversing blindness,
[01:53:45] designing new materials, solving the
[01:53:48] grand unification theory, cleaning
[01:53:50] oceans, you name it, right? improving
[01:53:52] education because abundance can't be an
[01:53:55] abstract philosophy. It has to show up
[01:53:57] as tangible progress. So yeah, alignment
[01:54:00] improves when AI is uh pointed at human
[01:54:03] flourishing, but we also need
[01:54:05] storytelling. The use of narrative is
[01:54:07] the only major way that we found of
[01:54:09] shifting people's thinking. John Hegel
[01:54:11] talks about this all the time. If people
[01:54:13] only see the the fear case, they're
[01:54:15] going to resist the technology. But if
[01:54:18] they see their child cured, their energy
[01:54:20] bill drop, their their business grows or
[01:54:22] their community becomes safer, then the
[01:54:25] whole emotional model changes, and then
[01:54:26] we're off to the races.
[01:54:28] >> Agreed. All right. Number four. Why
[01:54:31] throw away privacy with it's cooked?
[01:54:34] Privacy is linked to freedom. Why not
[01:54:36] fight to preserve both rather than treat
[01:54:39] it like nothing? Says at C88485,
[01:54:43] which is a very private sounding uh
[01:54:46] name. All right. Uh, and and at C888485,
[01:54:51] listen, I'm not saying I don't want
[01:54:52] privacy and it's not worth protecting.
[01:54:55] I'm just saying, you know, I'm just
[01:54:56] recognizing the fact that uh that there
[01:54:59] are real challenges. Your phone tracks
[01:55:01] your location 24/7. Your browser history
[01:55:04] is sold to advertisers. You know, an AI
[01:55:07] does facial recognition uh and you are
[01:55:10] leaving your DNA fingerprints everywhere
[01:55:13] you go. And so the ability to retain uh
[01:55:16] you know true privacy is becoming more
[01:55:19] and more difficult. Uh having it I
[01:55:22] totally get it. It's really important.
[01:55:24] Um but it's going to be challenging. Uh
[01:55:28] you know I I'll take a I'll take a quick
[01:55:31] uh poll here. The moonshot mates. Do any
[01:55:34] of you believe that you truly have
[01:55:36] privacy? Uh just real quick. Yes or no?
[01:55:42] >> No.
[01:55:42] >> Okay. Uh, Alex,
[01:55:44] >> for appropriate definition of privacy,
[01:55:46] yes.
[01:55:47] >> What's that definition of privacy?
[01:55:48] [clears throat]
[01:55:50] >> Well, there are a few different possible
[01:55:51] definitions. There's a legal definition,
[01:55:54] there's a physical definition, there's a
[01:55:57] logical definition, and I would say for
[01:55:59] for variance of each of those, yes, I
[01:56:02] believe I have some form of privacy.
[01:56:05] >> Okay. Um,
[01:56:06] >> I think there's a different problem that
[01:56:09] >> I can say for a fact, a 100% fact that
[01:56:12] Apple and Google literally know when I
[01:56:15] take a crap.
[01:56:16] >> Yeah.
[01:56:17] >> I don't know how you [laughter] define
[01:56:18] that as privacy.
[01:56:18] >> They sell that and they sell that data.
[01:56:20] >> Can I change the question? Can I just
[01:56:23] change the question a little bit? Right.
[01:56:24] Sure.
[01:56:25] >> The problem is not the the fact that we
[01:56:26] don't have privacy. We we really don't.
[01:56:28] But the the bigger issue is two in a 2.0
[01:56:31] version of privacy, you should own your
[01:56:33] own data. You should be able to revoke
[01:56:35] access. Uh systems that misuse data
[01:56:37] should face penalties. It you privacy in
[01:56:40] a new model needs to be use your own AI
[01:56:43] mediated cryptograph cryptographically
[01:56:46] protected and and legally enforceable
[01:56:49] and it's not right now. This is the
[01:56:50] problem.
[01:56:51] >> Yeah. So, Alex, I think you want to
[01:56:54] state for whatever reasons you have that
[01:56:56] you have privacy and you're going to
[01:56:58] sort of rework the definition to be able
[01:57:00] to make that statement, but I honestly
[01:57:02] in your heart of heart, I don't believe
[01:57:03] you. You don't believe that AIs can't
[01:57:06] read your lips, that you don't leave DNA
[01:57:07] trails, that they
[01:57:09] >> fun, man. I could I could watch this.
[01:57:11] >> This is spicy stuff, Peter. I I I I like
[01:57:13] that you have a a better mental model of
[01:57:15] of myself than I do, but I I I I really
[01:57:18] am this isn't like a case of false
[01:57:20] revealed preferences. I I really do
[01:57:22] think [clears throat] for appropriate
[01:57:23] definitions of privacy, not only I'll
[01:57:25] make a stronger statement. Not only do I
[01:57:27] think I have operationally physical,
[01:57:30] logical, and legal privacy, I'll make a
[01:57:33] stronger statement than that, which is I
[01:57:35] don't think the evaporation, if you
[01:57:38] will, or the cooking of privacy is any
[01:57:40] sort of inevitability. Quite the
[01:57:42] opposite. I think the same technologies
[01:57:45] that threaten for example to to dissolve
[01:57:48] say existing crypto systems say AI
[01:57:51] solves math and inverts a popular cipher
[01:57:54] suite and suddenly everyone's private
[01:57:56] keys are at risk. I would say that the
[01:57:58] same technologies that taketh away
[01:58:01] privacy from past crypto systems and and
[01:58:04] past systems of privacy protection will
[01:58:07] give us new forms of privacy quantum
[01:58:10] security and otherwise come back. If you
[01:58:12] read Neil Stevenson Diamond Age, it's a
[01:58:14] great vision of where this will end up.
[01:58:16] But right right now, there is no privacy
[01:58:17] at all. I think it'll come back. Selene,
[01:58:19] >> I just want to say one quick thing,
[01:58:21] Alex. I can't believe you think you have
[01:58:22] legal privacy. You absolutely do not.
[01:58:25] The government can show up in any
[01:58:26] second. The Fourth Amendment is gone in
[01:58:29] this country. It's gone.
[01:58:31] >> We have no legal protection. ICE could
[01:58:33] show up at your house today and say,
[01:58:34] "You've got a weird German name. We need
[01:58:37] to see everything about you and we're
[01:58:38] raiding your house." And they've been
[01:58:39] doing that. So that is gone today. All
[01:58:42] right. Uh, we're going to move on. See,
[01:58:44] uh, you get the first choice of five,
[01:58:46] six, seven, or eight.
[01:58:47] >> I will take number eight. Seriously.
[01:58:49] >> Okay. If government gatekeeps new model
[01:58:51] receases, who's qualified to vet them?
[01:58:54] The best people are employed by AI
[01:58:55] companies. The rest are all anti AI, how
[01:58:57] does that not become a false dichconomy?
[01:59:00] And this is from Michael Yakob. Um, so
[01:59:04] Michael Yakob. um uh if government does
[01:59:08] gatekeeping. So you know this is this is
[01:59:10] a very very big problem. The problem
[01:59:12] here is if government tries to do this
[01:59:14] alone it just not it's not going to have
[01:59:16] the talent or the speed. If companies do
[01:59:19] it alone then the public doesn't trust
[01:59:21] uh trust it. If you have activists doing
[01:59:24] it then it becomes ideological. Right?
[01:59:26] So we need a totally new governance
[01:59:28] architecture for this. The the right
[01:59:30] model is to have a technical independent
[01:59:33] fastmoving review body with a
[01:59:35] combination of frontier labs,
[01:59:36] government, academia, national security,
[01:59:39] a multid-disciplinary approach to this
[01:59:41] with civil society involved for example
[01:59:43] and people doing red teaming, right? Uh
[01:59:46] like FAA plus DARPA plus X-prise style
[01:59:49] open benchmarking. Benchmarking very
[01:59:51] critical as Alex I hope will agree. Um
[01:59:54] the key is not permission from
[01:59:55] bureaucrats. teams to have transparent
[01:59:58] capability thresholds because if a model
[02:00:00] crosses some level in cyber um you need
[02:00:04] it needs to be triggering a deep review
[02:00:06] like we saw anthropic with methos they
[02:00:08] voluntarily did that thank god and so
[02:00:10] you need to figure out a way of
[02:00:12] navigating that in other levels like
[02:00:14] persuasion or autonomy or replication so
[02:00:17] the biggest structural issue here is you
[02:00:19] you need governance that's as
[02:00:21] exponential as the technology today
[02:00:23] almost all government policy is
[02:00:24] defensive and reactive Right. So either
[02:00:27] you end up creating fake safety or you
[02:00:29] drive the best work underground or
[02:00:30] offshore. And so we have to navigate a
[02:00:32] very fine line there.
[02:00:34] >> Alex, over to you. Number
[02:00:37] >> Yeah,
[02:00:37] >> I'll pick question number five. So
[02:00:39] question number five asks, why aren't
[02:00:41] more individuals willing to pay for
[02:00:43] everyday AI reasoning services? If
[02:00:45] OpenAI marketed them, right? Isn't this
[02:00:48] a massive consumer market? And this is
[02:00:50] asked by Gary Stanley 2685.
[02:00:54] I don't think the premise of the
[02:00:55] question is correct. I don't think it's
[02:00:57] that individuals or consumers aren't
[02:00:59] willing to pay for reasoning models. I
[02:01:01] think it's that they're not able to pay
[02:01:03] for reasoning models. Frontier reasoning
[02:01:06] capabilities are quite expensive.
[02:01:08] Enterprises are willing and able to pay
[02:01:11] for them because they generate lots of
[02:01:14] of new free cash flow or are saving lots
[02:01:17] of otherwise consumed free cash flow.
[02:01:20] enterprises simply put have more money
[02:01:23] to spend on it. I think the way we get
[02:01:25] individuals to be able to pay more for
[02:01:28] reasoning models is by diverting at
[02:01:31] least some of the reasoning tokens to
[02:01:34] the problem of enabling individuals to
[02:01:36] be much more productive and and generate
[02:01:39] enormous amounts of revenue using those.
[02:01:41] And this is one of the reasons why Henry
[02:01:43] and Alex Finn, I think, are so
[02:01:45] interesting because in a world in a
[02:01:47] near-term future where individuals can
[02:01:49] become one person unicorns, then
[02:01:52] suddenly individuals will both be able
[02:01:54] to pay and willing to pay for all of
[02:01:57] those reasoning tokens. and and so I
[02:01:59] whether that's open AI marketing or a
[02:02:02] startup like Henry um I I would say
[02:02:04] regardless of that I do think there is a
[02:02:07] massive market but in the process it as
[02:02:10] I mentioned with my answer to the
[02:02:11] previous question it will almost I
[02:02:14] predict erase the distinction between
[02:02:16] consumer and enterprise spending
[02:02:18] altogether
[02:02:20] >> all right Dave you're down to two
[02:02:22] >> I'll take six because it's so easy isn't
[02:02:24] the real problem with ocean data centers
[02:02:26] the security risk pirates hostile nation
[02:02:29] states sabotage. And this is from
[02:02:31] strong, medium, weak.
[02:02:34] Interesting name. Uh, yeah, not a
[02:02:36] problem at all. As it turns out, the US
[02:02:38] Navy actually has total and unilateral
[02:02:40] control of all the world's oceans. Like,
[02:02:42] it's it's the most lopsided, one-sided
[02:02:46] thing you'll ever possibly imagine. And
[02:02:48] the US Navy protects all global
[02:02:49] shipping. Um, a very good friend of mine
[02:02:52] actually was down at the Cambridge
[02:02:53] Brewery working on a plan. And I I he
[02:02:55] was drinking a big fat beer and like
[02:02:57] what are you working on? Said I'm
[02:02:59] working on uh power generators on barges
[02:03:03] for Venezuela. Like what? Well, so you
[02:03:06] know, Venezuela had nationalized all of
[02:03:09] the um power supply and they there was
[02:03:12] no electricity in the cities, but it
[02:03:14] turns out you could float barges up to
[02:03:16] the shore, pipe oil into the generators,
[02:03:20] generate the power and then electric
[02:03:22] wire back into the cities and power the
[02:03:24] cities that way. But the US Navy would
[02:03:26] make your barges completely safe. U so
[02:03:30] uh the amount of ocean needed for these
[02:03:33] data centers, I thought it was the
[02:03:34] coolest story by the way on the last
[02:03:35] pod. the floating data centers. I never
[02:03:37] checked out whether whether the wave
[02:03:38] energy is enough to power the GPUs, but
[02:03:41] such a great idea,
[02:03:42] >> but the amount of ocean space that you
[02:03:44] need is tiny.
[02:03:45] >> There just aren't enough GPUs, and
[02:03:47] protecting them would be pretty trivial.
[02:03:50] Uh, if they're inside US national
[02:03:51] waters, they're protected by the Coast
[02:03:53] Guard or the Navy or both. So, I think
[02:03:55] it's great.
[02:03:57] >> All right, final one here. Number seven.
[02:03:58] >> Also, also land-based data centers have
[02:04:00] all the same security risks.
[02:04:02] >> Yeah, fair enough. Number seven. Should
[02:04:05] the US and China try working on an AI
[02:04:07] project together? Something positive and
[02:04:09] safe for both countries and the world,
[02:04:11] says CM
[02:04:14] MCN E10.
[02:04:17] Uh that rolls off the tongue onto the
[02:04:19] floor. [laughter] Okay. Uh so, you know,
[02:04:22] we just had the we just had the
[02:04:24] president of China yesterday announced
[02:04:27] we should be, you know, friends, not
[02:04:29] rivals. Um uh and collaborate together.
[02:04:32] Wouldn't that be an incredible world?
[02:04:34] So, uh, sure. The answer is I would love
[02:04:38] that. I would love to see the US and
[02:04:40] China working on AI projects together. I
[02:04:43] mean, one of the most beautiful things
[02:04:44] about what is possible is uh, you know,
[02:04:49] the entire uh, billion people in China
[02:04:52] and the entire whatever it is 300 plus
[02:04:55] million people in the United States all
[02:04:57] share the same biology.
[02:04:59] uh we could work on the greatest health
[02:05:01] care models and longevity models uh and
[02:05:04] everyone benefits. Uh so yeah uh I think
[02:05:08] that would be would be extraordinary.
[02:05:11] you know the AI 2027 paper if you
[02:05:13] remember it uh how that ends it has two
[02:05:17] branches in the story pick your own
[02:05:19] adventure one you know is AI sort of
[02:05:22] turns against humanity in the other one
[02:05:26] uh the major US and Chinese AIs
[02:05:28] collaborate and we live happily ever
[02:05:31] after together. So I I I choose the uh
[02:05:34] uh the latter.
[02:05:36] >> I think that's such a great point,
[02:05:37] Peter. There's so many areas of
[02:05:39] cooperation like um um u safety in space
[02:05:44] and AI coordination and etc that there's
[02:05:47] lots to do together.
[02:05:49] >> Yeah, for sure.
[02:05:50] >> So much human history, you know, the
[02:05:52] human conflict in history is just bad
[02:05:54] luck and and coincidence. But if you
[02:05:56] look at 1915 and the chain of events
[02:05:58] that that led up to World War I and the
[02:06:01] amount of tragedy that came out of it,
[02:06:03] but just this escalating chain of
[02:06:04] unfortunate coincidences and now they if
[02:06:08] you could relive or change history,
[02:06:10] putting all of Chip Fabs in Taiwan was
[02:06:14] just tragically stupid. And you know,
[02:06:17] because China was saying for a long time
[02:06:19] that they're going to take it over long
[02:06:20] before TSMC became huge. They they were
[02:06:22] like that is part of our country. Well,
[02:06:24] it wasn't putting it wasn't putting it
[02:06:26] in Taiwan. It was us not building them
[02:06:28] here.
[02:06:29] >> Yeah. Yeah.
[02:06:30] >> Yeah.
[02:06:30] >> Or or us not realizing the strategic
[02:06:32] importance and and
[02:06:35] >> Yeah.
[02:06:36] >> All right. Let's go to our outro music.
[02:06:37] This is
[02:06:38] >> Before you do that, Before you do that,
[02:06:39] I have an announcement.
[02:06:41] >> Please tell me.
[02:06:42] >> I'm I'm we're I'm I've kind of decided
[02:06:44] that to take a crack at solving for big
[02:06:47] things and we're going to I'm I'm
[02:06:50] working with John Hegel. launching a
[02:06:52] project that allows you to generate and
[02:06:56] create and and measure luck.
[02:06:58] >> I love this project.
[02:07:00] >> So, we're we're it's in a couple of
[02:07:02] weeks we're going to do a couple of
[02:07:03] webinars. Go to shapingluck.com if
[02:07:05] you're interested and register. We'll
[02:07:07] tell you when and we're going to make a
[02:07:09] model and a a capability where you can
[02:07:12] generate luck. And more interestingly
[02:07:14] and more importantly, we found a way of
[02:07:15] measuring it. So, there you go.
[02:07:17] >> I love that. and Salem and I for those
[02:07:19] of you who are excited and interested uh
[02:07:22] we're going to be dissecting and diving
[02:07:24] deep into the organizational singularity
[02:07:27] very shortly for all of our our
[02:07:29] listeners. Okay, so we have a new piece
[02:07:32] of outro music. This is from Jess
[02:07:33] Hilton. Jess, thank you for sharing. If
[02:07:36] you are a creative and you want to
[02:07:39] create some outro or intro music for us,
[02:07:41] please send it to media diammandis.com.
[02:07:44] And also, if you're a creative, enter
[02:07:46] the future vision X-P prize. Show us
[02:07:49] your best vision of the future. What's
[02:07:51] the next Star Trek, right? What is a
[02:07:53] Star Trek that you you want to, you
[02:07:56] know, uh occupy your heart and your soul
[02:07:59] that shows you where humanity should be
[02:08:01] going? Uh create that trailer, that that
[02:08:04] film treatment, and send it to us. You
[02:08:06] could win uh millions of dollars and
[02:08:09] have your movie made. All right, let's
[02:08:12] listen to Moonshots on repeat by Jess
[02:08:15] Hilton.
[02:08:17] >> Four guys in a room [music] where the
[02:08:19] big ideas flow.
[02:08:22] The machines are getting smarter and
[02:08:24] they're first to know.
[02:08:28] Nobody's [music] flinching. They're
[02:08:29] ready to go. Pull up a chair. It's the
[02:08:32] best podcast show.
[02:08:35] They're laughing while the models
[02:08:37] [music] learn to think.
[02:08:39] These lobbs,
[02:08:42] [singing]
[02:08:43] [music]
[02:08:48] please comment, like, subscribe, and
[02:08:50] share. [music]
[02:08:52] >> Moonshots on our feet. Turn it up loud
[02:08:55] for brilliant minds are still in [music]
[02:08:57] the profound emerging intelligence,
[02:08:59] abundance, insight. Exponential futures
[02:09:01] burning bright. The algorithms [music]
[02:09:03] whisper what's coming to pass. And
[02:09:05] optimism compounds like unseen mass. It
[02:09:08] rolls like a tear. Nobody can pin and I
[02:09:10] don't want to miss where it's going
[02:09:12] again. [music]
[02:09:20] >> All right, gentlemen.
[02:09:21] >> That was awesome.
[02:09:23] >> Love that.
[02:09:23] >> Salem, I think that's you swill and beer
[02:09:25] with what is the meaning of life. I
[02:09:26] >> think so.
[02:09:28] The meaning of life for sure.
[02:09:31] >> Uh love you guys. What a great episode.
[02:09:34] Uh
[02:09:34] >> great awesome conversation. Uh, Salem, I
[02:09:37] will see you this weekend for your
[02:09:39] birthday, buddy.
[02:09:40] >> Well, see, we'll see you there.
[02:09:42] >> Very excited about that. Alex, Dave,
[02:09:45] >> love you. Bye. Love you guys. Be well,
[02:09:47] too.
[02:09:47] >> Love you guys. See you soon.
[02:09:49] >> If you made it to the end of this
[02:09:50] episode, which you obviously did. I
[02:09:52] consider you a moonshot mate. Every
[02:09:54] week, my moonshot mates and I spend a
[02:09:56] lot of energy and time to really deliver
[02:09:58] you the news that matters. If you're a
[02:10:00] subscriber, thank you. So, if you're not
[02:10:01] a subscriber yet, please consider
[02:10:03] subscribing so you get the news as it
[02:10:05] comes out. I also want to invite you to
[02:10:07] join me on my weekly newsletter called
[02:10:10] MetaTrends. I have a research team. You
[02:10:12] may not know this, but we spend the
[02:10:14] entire week looking at the meta trends
[02:10:16] that are impacting your family, your
[02:10:18] company, your industry, your nation. And
[02:10:20] I put this into a two-minute read every
[02:10:22] week. If you'd like to get access to the
[02:10:24] Metatrends newsletter every week, go to
[02:10:26] diamandis.com/tatrens.
[02:10:29] That's [music] diamandis.com/metatrends.
[02:10:32] Thank you again for joining us today.
[02:10:34] It's a [music] blast for us to put this
[02:10:36] together every week.
