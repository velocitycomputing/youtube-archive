---
video_id: nLQhKkjkuWI
title: "Claude Tested Over 9,000 Trading Strategies (Here's What Works)"
channel: AI Pathways
url: "https://www.youtube.com/watch?v=nLQhKkjkuWI"
watched_date: 2026-06-29
watched_at: "2026-06-29T12:00:00Z"
watch_count: 1
duration_seconds: 1194
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 18
watched_at_precision: date-from-history-label
watched_percent: 13
estimated_watched_seconds: 155
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Brendan used Claude to run 9,000 backtests of trading strategies across 30 assets over 15 years, testing every popular approach including trend following, mean reversion, momentum, and breakouts. The rigorous validation process employed walk-forward testing, Sharpe ratio filters, drawdown limits, and overfitting checks, revealing that mean reversion was the only strategy family to consistently survive testing—while 44% of initially good-looking strategies were fake due to overfitting. Mean reversion comprised 64% of the 478 surviving strategies and held up across 20+ unrelated assets, whereas trend and momentum strategies only worked in specific market conditions on specific assets. Bootstrap stress tests confirmed mean reversion wasn't luck-dependent, while other strategies would have produced massive drawdowns if trades had occurred in different sequences.

To build your own system, Brendan created a four-layer framework using Claude: (1) build a data and strategy library for your target assets, (2) construct a backtest engine with walk-forward testing, (3) apply filters and validations including realistic transaction costs, and (4) add robustness checks and regime detection. The actionable strategy architecture starts with a base edge (mean reversion), layers on risk management and position sizing based on your risk tolerance, combines uncorrelated signals for diversification, and applies market regime detection to switch between strategies (momentum in trending markets, mean reversion in choppy markets). You can replicate this directly in Claude Code or claude.ai by copying the provided prompts, which gives you control over validation that basic platforms like TradingView lack.

## Transcript

[00:00:00] I used claw to run over 9,000 back tests
[00:00:02] of trading strategies to find ones that
[00:00:04] actually work. This included every
[00:00:07] popular one that you can think of like
[00:00:08] trend following, mean reversion,
[00:00:10] momentum, breakouts, and this was across
[00:00:13] 30 different assets and 15 years of
[00:00:15] data. Now, if it's your first time on
[00:00:17] the channel, my name is Brendan. I
[00:00:19] studied math and econ at UCLA, spent
[00:00:22] three years in investment banking at
[00:00:23] Raymond James, and have been building
[00:00:25] out trading systems for clients for the
[00:00:27] past two years. And in this video, I'll
[00:00:29] go over how I built this entire testing
[00:00:31] system with Claude. I'll go over what
[00:00:33] the results were, how you can replicate
[00:00:35] the test yourself, and how you can use
[00:00:37] it to improve your own trading
[00:00:38] strategies as well. Now, as always, this
[00:00:40] is not financial advice, and I'm not
[00:00:42] guaranteeing any profits. I'm simply
[00:00:44] showing you all the data and
[00:00:45] methodologies behind these tests and how
[00:00:47] you can leverage them as well. So,
[00:00:49] diving right in, this is a system that I
[00:00:50] built with Claude. I basically took
[00:00:52] every single strategy and ran 9,000 back
[00:00:54] tests across 30 assets. So, for each
[00:00:57] strategy, I put it through a whole stack
[00:00:58] of testing to see what actually holds
[00:01:00] up. Now, this is the complete overview
[00:01:02] of the testing system. It probably looks
[00:01:04] like gibberish, so I'll explain in more
[00:01:06] detail every single one of these tiles.
[00:01:08] What I tested was daily bars across
[00:01:10] liquid assets. So, this includes things
[00:01:12] like major ETFs like S&P 500 and NASDAQ.
[00:01:15] It also has all the sector ETFs, gold,
[00:01:18] oil, bonds, Bitcoin, and Ethereum, and
[00:01:20] large cap stocks like Apple and Nvidia.
[00:01:22] So again, these tests just covered
[00:01:24] largecale trading, right? So not
[00:01:26] intraday or futures or options. So keep
[00:01:28] that in mind because it shapes what
[00:01:30] these results mean. And now secondly, I
[00:01:32] wanted this to be purposely tough and
[00:01:33] pretty comprehensive. So that's why I
[00:01:35] ran this over the longest reasonable
[00:01:37] period, which was 15 years. The goal
[00:01:40] here wasn't to find the one strategy
[00:01:41] that works right now. It was to find
[00:01:43] what actually holds up in every single
[00:01:45] kind of market. So we took strategies in
[00:01:47] its most base stripped down form. So if
[00:01:50] something survives basically this
[00:01:52] rigorous testing across what we have
[00:01:54] here this window 15 years it means we
[00:01:56] have a real edge in the market. So at a
[00:01:58] quick glance what we have here in the
[00:01:59] top lefthand corner is the validation
[00:02:01] funnel. This is basically just going to
[00:02:03] show you how the 9,000 back test narrow
[00:02:05] down. Then we have this scatter plot
[00:02:07] here which shows overfitting. And then
[00:02:09] to the right here we have survival rate
[00:02:11] by category. So spoiler alert mean
[00:02:13] version is the only trading strategy
[00:02:16] family that really survives this whole
[00:02:18] rigorous testing. Now, I'll explain this
[00:02:20] in a lot more detail and how you can
[00:02:21] interpret the rest of the strategy
[00:02:22] families as well. And then to the left
[00:02:24] of this, we have the validation
[00:02:25] gauntlet. This actually shows you how we
[00:02:27] ran all the tests because they're pretty
[00:02:29] thorough. So, they include things like
[00:02:30] walk forwards and robustness checks. So,
[00:02:32] now let's first go through the
[00:02:33] validation funnel, which covers all the
[00:02:35] back tests of the strategies that we
[00:02:37] ran. So, here we can see that we started
[00:02:38] with over 9,000 back tests at the top
[00:02:41] and then by the time we get to the
[00:02:42] bottom of our filters, we're just left
[00:02:44] to 524. This means that thousands of
[00:02:46] strategies and back tests got wiped out
[00:02:48] simply from our six filters here. Now,
[00:02:50] for the actual back testing here, we did
[00:02:52] walk forward testing. Walk forward
[00:02:54] basically means that you build and tune
[00:02:56] the strategy on an older chunk of data
[00:02:58] and then you test it on a newer chunk of
[00:03:00] data that it's never seen before. The
[00:03:02] reason that this matters is that it
[00:03:03] stops the strategy from overfitting the
[00:03:05] past. Anyone can make a back test look
[00:03:07] perfect on previous data that it's seen
[00:03:09] before, but the walk forward makes sure
[00:03:10] to test on new unseen data. Now the
[00:03:13] first and biggest filter that we ran is
[00:03:14] the sharp filter. Sharp is just a score
[00:03:16] for how good the returns are versus how
[00:03:19] much risk you took. So ideally the
[00:03:21] higher the better. Here we just required
[00:03:22] a sharp over.5 on data that the strategy
[00:03:25] had never seen before. And this one cut
[00:03:28] removed almost 8,000 strategies leaving
[00:03:30] us with only 1,218. Then after this we
[00:03:33] added a draw down filter and we threw
[00:03:35] out basically anything that had a draw
[00:03:37] down of higher than 35%. And if you're
[00:03:39] unaware, draw down just literally means
[00:03:41] the biggest drop from a high point to a
[00:03:42] low point. So here, draw down just means
[00:03:44] that you're down 35% from your peak.
[00:03:46] Now, obviously, if you are a riskier
[00:03:48] trader, you'd have a higher draw down
[00:03:50] tolerance. And some people are
[00:03:51] completely fine with sitting through a
[00:03:53] high draw down so long as the long-term
[00:03:54] payoff is worth it. But and just to
[00:03:56] reiterate, this is a pretty general
[00:03:58] test. I wanted to set reasonable draw
[00:04:00] down limits to have this applied to
[00:04:02] almost everyone. And generally a pretty
[00:04:04] deep draw down typically means that the
[00:04:06] strategy is pretty fragile or overly
[00:04:08] risky. I wanted this to be general, but
[00:04:10] later on in the video I'll show you how
[00:04:12] you can set this to have your own risk
[00:04:14] tolerance instead. Then below this, I
[00:04:15] just added a filter for stuff that did
[00:04:17] way better in testing than out of
[00:04:19] testing. We're basically just testing
[00:04:20] for overfitting here. And then finally,
[00:04:22] we at least wanted a minimum number of
[00:04:24] trades to make sure that the strategy
[00:04:26] was actually viable. And all we're left
[00:04:28] with is 524. So basically in plain
[00:04:31] English each of these filters are just a
[00:04:33] common sense way a strategy can be you
[00:04:35] know fake, useless or just weak. Next we
[00:04:37] have an insample versus out of sample
[00:04:39] scatter plot. And this is one of the
[00:04:41] single biggest reasons strategies die
[00:04:43] which is due to overfitting. Now stick
[00:04:45] with me here because this is a core
[00:04:46] concept. Now each dot here inside this
[00:04:49] chart is a back test. So the bottom axis
[00:04:52] is how well it did on the data it was
[00:04:54] built and tuned on while the side axis
[00:04:56] shows how well it did on data that it
[00:04:58] had never seen before. So overfitting is
[00:05:00] when you tweak a strategy, the settings,
[00:05:02] the numbers until it looks amazing on
[00:05:04] past data, but all you've really done
[00:05:06] there is fit to random noise that
[00:05:08] already happened. So in those instances,
[00:05:10] it looks perfect in the past, but then
[00:05:12] completely falls apart as it gets
[00:05:14] introduced to new data or live data. So
[00:05:16] this is exactly what we're testing for
[00:05:18] here. And on the right, I've actually
[00:05:19] put some numbers on this. So of all the
[00:05:22] strategies that look strong in testing,
[00:05:24] which again is looking at past data,
[00:05:26] only 44% stayed strong out of sample,
[00:05:29] which is tested on new data. This
[00:05:31] basically means that more than half of
[00:05:33] the good-looking strategies were
[00:05:34] basically fake. So coming back to this
[00:05:36] chart here, the green dots above the
[00:05:38] line are the few where the performance
[00:05:40] actually carried over to fresh data. So
[00:05:42] that's what you're looking for,
[00:05:43] consistency between the test and the
[00:05:45] real thing, not just a good back test.
[00:05:47] And this whole reason is why we didn't
[00:05:48] use something like Trading View just
[00:05:50] because the back testing is basic. It'll
[00:05:52] pretty much show you a strategy that
[00:05:54] looks amazing and gives you none of this
[00:05:56] validation here. It doesn't correct for
[00:05:57] luck. It doesn't stress test anything
[00:05:59] and it's all just overfit. So people
[00:06:02] typically just run one back test on
[00:06:03] there, see a great number, go trade it,
[00:06:05] and then have it completely fall apart
[00:06:07] in the live market. Now on this next
[00:06:09] section, we have the main answer to our
[00:06:11] question of what strategy actually
[00:06:13] survives all this rigorous testing. So
[00:06:15] this section here groups every strategy
[00:06:17] into different types or families. And
[00:06:20] the two big families you can think of
[00:06:21] are trend and mean reversion. These are
[00:06:24] basically opposite bets. So trend bets
[00:06:27] that something moving in a direction
[00:06:28] keeps moving. So the idea here is that
[00:06:31] if a stock is climbing, you buy
[00:06:33] expecting it to continue climbing.
[00:06:35] Momentum is a version of that same idea,
[00:06:37] betting that what's been strong stays
[00:06:40] strong. But mean reversion here on the
[00:06:42] other side is the opposite. It bets that
[00:06:44] when a price stretches too far from its
[00:06:47] average, it goes back. So the idea is
[00:06:49] that it reverts to the mean. So you buy
[00:06:51] when something has dropped too far below
[00:06:53] its average expecting a bounce and vice
[00:06:56] versa. Then there's also other strategy
[00:06:58] families like volume, volatility,
[00:07:00] pattern strategies that look for chart
[00:07:02] shapes. And then inside each of these
[00:07:04] families, there's a handful of actual
[00:07:06] specific strategies. So here on the
[00:07:08] trend category, we have things like
[00:07:10] moving average, crossovers, and breakout
[00:07:12] systems. Mean reversion has stuff like
[00:07:15] uh RSI based snapbacks, Ballinger band
[00:07:17] reversions and so on across all the
[00:07:19] families and then we test all those
[00:07:21] different strategies across a range of
[00:07:23] settings because obviously the same
[00:07:24] strategy at a different setting will
[00:07:26] behave differently from one another. So
[00:07:28] that's how we arrive to all 9,000
[00:07:30] barback tests. So now the result here
[00:07:32] from our system shows that mean
[00:07:33] reversion is actually the only category
[00:07:36] of strategies that came out positive on
[00:07:38] average. everything else. So trend,
[00:07:40] volume, composite, volatility, pattern
[00:07:42] strategies are all negative on average.
[00:07:44] What this means is that in its bare
[00:07:46] stripped down form, so trading
[00:07:48] completely naked with no other rules
[00:07:50] over 15 years of every single market
[00:07:53] condition, mean reversion is the only
[00:07:55] one that holds up on its own. But again,
[00:07:57] this doesn't mean that the other
[00:07:58] strategies don't work per se. They're
[00:08:00] just a lot more situational. So it
[00:08:02] depends on the right market conditions.
[00:08:04] It might depend on the right asset that
[00:08:06] you're trading or combined with other
[00:08:07] strategies as a whole or applied at the
[00:08:09] right time. So, they can work. You just
[00:08:11] can't run them on autopilot the same way
[00:08:14] you would run mean reversion. And later
[00:08:16] on in the video, I'll show you how to
[00:08:17] actually apply some of these findings to
[00:08:19] determine when to actually use some of
[00:08:20] these other strategies. But as a whole,
[00:08:22] mean reversion really is the one that
[00:08:24] survives. Now, the final test here we
[00:08:26] did was a bootstrap. What this means is
[00:08:28] that we took every surviving strategies
[00:08:30] trades and then reshuffled them 500
[00:08:32] times. The reason for this is to see all
[00:08:34] the different ways that the trades could
[00:08:35] have played out rather than the one way
[00:08:37] that it did happen. This makes sure that
[00:08:39] a successful trade wasn't just a lucky
[00:08:41] sequence and that if we were to
[00:08:43] reshuffle this 500 times, it still would
[00:08:45] have produced a winning trade. So here
[00:08:46] in these results, we can see once again
[00:08:48] that the mean reversions, the RSI
[00:08:49] revert, still has a solid verdict,
[00:08:51] meaning that if we were to reshuffle the
[00:08:53] results, it still would have performed
[00:08:54] well. But if we were to look at dual
[00:08:56] momentum strategies like ones on Nvidia,
[00:08:58] we can see that the max draw down is
[00:09:00] actually massive. Down 61% down 51%.
[00:09:04] What this means is that if we reshuffle
[00:09:05] these possible trades in an alternate
[00:09:07] universe, this thing would have
[00:09:08] basically cut your account in half. So
[00:09:10] some of these momentum strategies, like
[00:09:11] this one in particular, only looked
[00:09:13] clean in the very exact path that the
[00:09:15] market actually took. Meanwhile, the
[00:09:17] mean reversion didn't rely as much on
[00:09:19] luck, and no matter how much we shuffled
[00:09:20] the trades, it still had a solid
[00:09:22] outcome. So now let's go into what
[00:09:23] survived and why. So mean reversion was
[00:09:25] the only category that really came out
[00:09:27] positive out of the major strategy
[00:09:29] families. And let me show you where it
[00:09:31] gets really interesting. So we
[00:09:32] originally had 524 strategies that
[00:09:35] passed all six filters. But this is
[00:09:37] further filtered down to 478. It's the
[00:09:40] same survivors. It's only on assets with
[00:09:42] over 10 years of history. So things like
[00:09:44] the XLC ETF doesn't really make this cut
[00:09:46] because it wasn't launched until mid
[00:09:48] 2018. So only has around 6.5 years of
[00:09:51] data from that 2010 to 2025 window. And
[00:09:54] then out of these 478 strategies, 64% of
[00:09:57] them are mean reversion strategies. So
[00:09:59] that's this bright green chunk. So it
[00:10:01] didn't just survive, it basically made
[00:10:02] up almost 2/3 of everything that did
[00:10:04] survive. And then like I mentioned, mean
[00:10:06] reversion again is just betting that a
[00:10:08] price that stretched too far either
[00:10:10] above or below will always snack back to
[00:10:12] its average. Now this pretty much lines
[00:10:14] up with research, right? Mean reversion
[00:10:16] is one of the most backed ideas in all
[00:10:17] of trading. There's decades of academic
[00:10:20] work behind why prices overreact and
[00:10:22] then revert tied to human psychology as
[00:10:24] well as just how the way the market
[00:10:26] works. So if you were to compare that to
[00:10:27] like say a moving average crossover
[00:10:29] which is just one line crossing another
[00:10:31] line there's no real reason that should
[00:10:34] predict anything and the data shows it
[00:10:36] mostly doesn't. Now moving on here we
[00:10:38] can see the actual top survivors by
[00:10:40] score. Number one, survivor is actually
[00:10:42] a trend strategy turtle on Apple at
[00:10:44] 1.18. And you'll see a few other trend
[00:10:47] strategies up high, too. So, trend
[00:10:49] strategies can absolutely work. It just
[00:10:51] worked in specific spots on specific
[00:10:53] strong trending names like Apple and
[00:10:55] Nvidia, not broadly across everything.
[00:10:57] And a lot of these trend scores were the
[00:10:59] fragile ones that we just looked at with
[00:11:01] the huge draw downs as well. So, the
[00:11:02] lesson here isn't that trend strategies
[00:11:04] are dead, but more so that it's
[00:11:06] situational. So on these specific assets
[00:11:08] or specific market conditions, they
[00:11:10] absolutely do outperform. It works great
[00:11:12] on specific assets, but you can't count
[00:11:14] on it everywhere like you can with mean
[00:11:16] reversion. You can think of mean
[00:11:17] reversion strategies as a broad reliable
[00:11:19] base and then trend as more of a use it
[00:11:22] when it fits kind of thing. And now this
[00:11:23] is the slide that really shows why mean
[00:11:26] reversion is so powerful. Shows the
[00:11:28] different types of means strategies that
[00:11:30] it actually worked on. So we can see
[00:11:31] that RSI meanversion didn't just survive
[00:11:34] on one ticker. It survived on 20
[00:11:36] different tickers. We have the Kelner
[00:11:38] reversion on 18 different tickers.
[00:11:40] Basically, if something only works in
[00:11:41] one place, it might be luck or just very
[00:11:43] situational. But what we're showing here
[00:11:45] is that across 20 completely unrelated
[00:11:47] assets, we have this RSI mean version
[00:11:50] essentially working everywhere. And then
[00:11:51] here we can even see this laid out by
[00:11:53] category. So as a group, mean inversion
[00:11:55] really is the only category with a real
[00:11:57] positive edge creates a trend, volume,
[00:11:59] composite, volatility, and pattern
[00:12:01] strategies. Now again, the survivorship
[00:12:03] is pretty boring. You have modest
[00:12:04] returns, controlled risk, but this is
[00:12:07] what's expected out of our test. These
[00:12:09] numbers are pretty modest just because
[00:12:10] this is honest testing across frankly
[00:12:13] like 15 years and every single kind of
[00:12:15] market. If I only tested a recent
[00:12:18] stretch or specific assets, the returns
[00:12:20] would have been significantly higher.
[00:12:22] But we're just testing for the general
[00:12:24] durability of strategies across
[00:12:26] basically every single type of asset.
[00:12:28] And then one thing I really want to
[00:12:29] stress is that we're looking at the
[00:12:30] floor, right? Not the ceiling. So, this
[00:12:32] is the most conservative possible
[00:12:34] version base strategies, completely
[00:12:36] naked, no improvements, uh, ran over 15
[00:12:39] years, including every single crash. But
[00:12:41] the moment you start dialing in on these
[00:12:42] specific strategies, like focusing on a
[00:12:44] shorter time frame that fits current
[00:12:46] conditions, combining a few of them
[00:12:48] together, adding layers that I'm about
[00:12:50] to show you in the next section, these
[00:12:51] numbers can get a lot better. So, you
[00:12:54] can think of this is just a raw
[00:12:55] foundation before you build anything on
[00:12:57] top. But just for like a plain takeaway,
[00:13:00] across every popular strategy traded on
[00:13:02] its own in its bare stripped down form
[00:13:05] over 15 years, means the only one that
[00:13:08] broadly holds up on its own. Basically
[00:13:10] survived across almost all assets made
[00:13:13] up about 2/3 of everything that passed.
[00:13:15] So now that we understand the most
[00:13:17] conservative, modest, and boring
[00:13:19] strategies, we need to know what to do
[00:13:21] with this. Right? This isn't a finished
[00:13:22] strategy. It's a foundation. So let me
[00:13:24] go ahead and show you how you would
[00:13:25] build on top of this. So the first thing
[00:13:28] is that there's a lot of nuance beyond
[00:13:29] just looking at stripped down
[00:13:30] strategies. So obviously trend and
[00:13:32] momentum strategies did show strength in
[00:13:35] certain specific situations. So I
[00:13:37] expanded the test a bit further. So if
[00:13:39] you remember momentum scored basically
[00:13:41] zero as a basic strategy on a single
[00:13:43] asset. But there's a smarter version
[00:13:45] called cross-sectional momentum where
[00:13:46] instead of asking is this one stock
[00:13:49] trending? You rank a whole basket of
[00:13:51] assets against each other and then only
[00:13:53] go long on the strongest ones and then
[00:13:54] short the weakest. I tested that version
[00:13:57] separately and as you can see here in
[00:13:59] these results, it scored way better
[00:14:00] going from basically zero. So what this
[00:14:02] means is that obviously momentum isn't
[00:14:04] broken the basic version that we tested.
[00:14:06] So all 9,000 basic versions obviously
[00:14:08] wouldn't work at its core form. So this
[00:14:11] then leads to my next point which is the
[00:14:13] framework on how you actually build a
[00:14:14] real trading strategy with Claude
[00:14:16] because it's layers, right? So at the
[00:14:18] bottom you have your base signal. So
[00:14:20] something with a real edge which we
[00:14:22] proved is something like mean reversion.
[00:14:23] Now on top of mean reversion you would
[00:14:25] add risk management and position sizing
[00:14:28] and this is the boring part that you
[00:14:30] know nobody wants to hear but it is
[00:14:31] pretty much what makes up a crux of your
[00:14:33] strategy. Everyone have a different
[00:14:35] tolerance to risk and how much they want
[00:14:36] to size their positions but this is huge
[00:14:38] for you know minimizing draw downs on
[00:14:40] specific trades that you have. And then
[00:14:42] on top of this you would combine it with
[00:14:43] more uncorrelated signals. So this
[00:14:45] allows you to diversify across signals
[00:14:47] that don't particularly move together
[00:14:49] because again we only tested all the
[00:14:51] strategies in its bearish form. So
[00:14:53] basically one weak signal alone is noise
[00:14:55] but several that don't move together can
[00:14:57] actually be something real when you
[00:14:58] combine them. And then at the very top
[00:15:00] of this foundation we have regimes which
[00:15:02] is something I cover pretty extensively
[00:15:04] on my channel. So this is where we
[00:15:06] categorize the market and then only use
[00:15:08] a strategy when the market actually
[00:15:10] suits it. So here you would use claw to
[00:15:12] basically build a hidden markoff model
[00:15:14] which is basically a model that detects
[00:15:16] what state of the market you're in right
[00:15:17] now. So, it'll tell you if it's a bare
[00:15:19] market, trending or a choppy market, or
[00:15:21] a full-on bull run. So, you would then
[00:15:24] run the momentum strategies on the
[00:15:25] trending or bull run markets, and then
[00:15:27] switch perhaps to mean reversion when
[00:15:29] it's choppy. So, the idea here is that
[00:15:31] you would take momentum strategy that
[00:15:33] fails when you just run it blindly on
[00:15:34] autopilot, and then combine it with
[00:15:36] something like targeting the market and
[00:15:38] then you would see that it's actually
[00:15:40] situationally useful in these different
[00:15:42] contexts. So, here you can see in a
[00:15:44] trending market, you would lean
[00:15:45] momentum. in a chop your ranging market,
[00:15:47] you would lean mean reversion. So
[00:15:49] although mean reversion worked almost
[00:15:51] all the time on autopilot momentum
[00:15:52] strategies with this new kind of tag,
[00:15:55] you'll be able to situationally apply it
[00:15:58] better. Now, one last point I want to
[00:15:59] end this video on before I show you how
[00:16:00] to build a system yourself is that this
[00:16:02] is very personal for building your own
[00:16:04] strategy. There's no single right answer
[00:16:06] that works for everyone because everyone
[00:16:08] has different capital. So the portfolio
[00:16:09] sizes are different. They have different
[00:16:11] risk tolerances, time horizons, and how
[00:16:13] much of a draw down they can actually
[00:16:14] stomach. So the idea is that you would
[00:16:17] take a successful strategy or a real
[00:16:19] edge like be inversion. You would then
[00:16:21] add risk management and sizing based on
[00:16:24] your own personal preferences and
[00:16:25] portfolio. You would then combine it
[00:16:27] with uncorrelated signals and then apply
[00:16:29] it based on market regimes. There's no
[00:16:31] copypaste answer because again everyone
[00:16:33] has completely different capital risk
[00:16:36] tolerance, time horizons, and draw down
[00:16:38] tolerance. Now, if you do want to learn
[00:16:40] how to best use Claw to build out your
[00:16:42] own trading strategies, trading systems,
[00:16:44] and just more robust testing, I have a
[00:16:46] school community where I run the largest
[00:16:48] AI focused trading community all about
[00:16:50] using the latest AI tools like Claude
[00:16:52] specifically for this. In there, we have
[00:16:55] full in-depth guides and active
[00:16:56] community members all building different
[00:16:58] systems across crypto, stocks, options,
[00:17:01] futures, basically every single asset
[00:17:03] class. And the important thing to stress
[00:17:04] here is that with AI, you can truly
[00:17:06] build out some very complex systems,
[00:17:08] test your own ideas in record time, and
[00:17:10] be able to just generally improve your
[00:17:12] trading over time. So, make sure to
[00:17:14] click the link in the description if you
[00:17:15] are interested. Now, let me go ahead and
[00:17:17] show you how you can build the same
[00:17:18] exact testing system yourself with
[00:17:20] Claude. So, I built this whole thing
[00:17:22] with Claude in a few layers, and each
[00:17:24] layer is just a separate prompt. The
[00:17:26] first prompt just builds the data and
[00:17:28] strategy library. So, it pulls all the
[00:17:30] assets and sets up all the strategies.
[00:17:32] The second layer builds the back test
[00:17:33] engine and the walk forward testing. The
[00:17:35] third adds the filters and validations.
[00:17:38] So we have things like the multiple test
[00:17:40] corrections and realistic transaction
[00:17:41] costs. And then the fourth just adds
[00:17:43] robustness checks and the regime
[00:17:45] changes. So here we can see that it
[00:17:47] includes every single popular strategy
[00:17:48] in its base form across 30 assets and 15
[00:17:52] years. And again, you can tweak any of
[00:17:53] these to be specific assets that you
[00:17:56] want to trade in particular or adjusting
[00:17:58] for a shorter time frame. But it does
[00:18:00] have a lot of validations that most
[00:18:01] tools skip. So the real advantage of
[00:18:03] using this over something like Trading
[00:18:05] View or any off-the-shelf back tester is
[00:18:07] that when you build it yourself with
[00:18:08] Claude, you basically control every
[00:18:10] single part of the validation. You can
[00:18:12] add things that just simply aren't in
[00:18:14] Trading View, like walk forwards to make
[00:18:15] sure you're not overfitting. You can
[00:18:17] correct for luck across thousands of
[00:18:19] tests. You can put in realistic
[00:18:21] transaction costs. And you can even
[00:18:23] stress test the survivors. This is how
[00:18:25] you can tell if a strategy is actually
[00:18:27] real, not just what a simple back
[00:18:29] testing platform would tell you. So,
[00:18:31] moving on, I'll go through all of the
[00:18:32] layers. And like I mentioned in my
[00:18:34] previous videos, if you want to build
[00:18:35] these, it's super simple. You can
[00:18:37] literally just screenshot the prompts
[00:18:38] and then feed it to an AI model. And
[00:18:40] then you can build it either in the web
[00:18:42] app, so like claw.ai or you can use claw
[00:18:44] code. It's a little bit more advanced,
[00:18:45] but you'll have one singular place to
[00:18:47] just edit all your code, make changes to
[00:18:49] the codebase, and continually update it
[00:18:51] as well. So, here's the data and
[00:18:53] strategy library. So simply copy and
[00:18:55] paste this directly to claude code. Then
[00:18:57] we have the back test in the funnel. So
[00:18:59] this is where we do the walk forwards
[00:19:00] out of sample and the six filter funnel.
[00:19:03] This is the first part of the prompt.
[00:19:05] Second part. And then again just make
[00:19:06] sure to pause whenever you need to. Then
[00:19:08] we have layer three which is robustness
[00:19:10] checks. This tests for parameter
[00:19:11] sensitivity and a bootstrap stress test.
[00:19:13] It's the first part. And then finally we
[00:19:15] have the cross-sectional momentum check
[00:19:17] if you are focused specifically on
[00:19:19] momentum based strategies. And now with
[00:19:21] these, you can test your own ideas
[00:19:22] properly instead of trusting a back test
[00:19:25] you once saw on Trading View. Now, if
[00:19:26] you enjoy this video, make sure to leave
[00:19:28] a like, comment, and subscribe as it
[00:19:29] greatly helps out the channel. And if
[00:19:31] you do want to go deeper, my community
[00:19:32] is in the description as it's the
[00:19:34] largest AI focused trading community.
[00:19:36] Everyone in there is building trading
[00:19:37] systems across stocks, crypto, options,
[00:19:40] and futures with step-by-step guides.
[00:19:42] Even if you have zero coding background.
