---
video_id: RCbJKkG_mZs
title: "Google Invests $40B Into Anthropic, GPT 5.5 Drops, and Google Cloud Dominates | EP #252"
channel: Peter H. Diamandis
url: "https://www.youtube.com/watch?v=RCbJKkG_mZs"
watched_date: 2026-06-11
watched_at: "2026-06-11T12:00:00Z"
watch_count: 1
duration_seconds: 8208
source: youtube-history-browser
added_date: 
history_label: Jun 11
history_order: 119
watched_at_precision: date-from-history-label
watched_percent: 90
estimated_watched_seconds: 7387
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The episode covered the explosive acceleration of AI development, highlighting Google's $40 billion commitment to Anthropic, OpenAI's release of GPT 5.5 (just seven weeks after GPT 5.4), and the broader model race featuring 15 major releases in eight weeks. Key technical discussions included Moonshot's Kimi K2.6 (a trillion-parameter open-source model costing 1/30th the price of GPT-4.7), the architecture innovation of mixture-of-experts and sparsity techniques, and GPT 5.5's improvements: 37-point jump in long-context reasoning, 40% fewer tokens for same latency, and 60% reduction in hallucinations. The panel debated whether compute or model weights matter more in the era of chain-of-thought reasoning, noting Chinese models now trail US models by only three months rather than six, and discussed the trade-offs between safety-guardrailed Western models and cost-efficient open-source alternatives.

For users, the actionable takeaway is straightforward: pick one capable recent model (Claude Opus 4.6/4.7, GPT 5.5, or Gemini 3.1 Pro) and let it orchestrate; you don't need to chase every release. For cost-sensitive operations or self-hosting, Kimi K2.6 or DeepSeek V4 are viable for subtasks while keeping a premium model as the orchestrator for validation. Enterprises can now self-host privacy-sensitive workloads with open-source models, but should be aware that open-source Chinese models lack the code-injection safeguards of Western providers—requiring AI-assisted review of generated code at scale. Average users can now accomplish complex system setup tasks (software installation, integration, configuration) in minutes through direct model interaction without command-line knowledge.

## Transcript

[00:00:00] Google commits to a $40 billion
[00:00:02] investment in anthropic.
[00:00:03] >> Daario needs comput. He signs up with
[00:00:05] Amazon. Google's already a shareholder
[00:00:07] in Anthropic.
[00:00:08] >> They're trying to maximize the economic
[00:00:10] value per token.
[00:00:11] >> It's all bottlenecked at TSMC. That's
[00:00:14] the actual bottleneck to all of AI and
[00:00:16] only Elon will talk about it.
[00:00:17] >> Google Cloud is dominating. They
[00:00:20] unveiled their eighth generation of
[00:00:22] TPUs, uh, in particular TPU 8T for
[00:00:25] training and TPU 8i for inference. I
[00:00:28] still believe Google's the winner in the
[00:00:30] long run here.
[00:00:33] OpenAI unveiled [music] GPT 5.5. It very
[00:00:36] much feels like a release that's
[00:00:38] intended [music] to strengthen OpenAI's
[00:00:40] codecs. Math is cooked. Bunch of other
[00:00:42] things are [music] cooked as well.
[00:00:44] Things are moving so quickly now that on
[00:00:45] a month-by-month basis, we're able to
[00:00:47] see the hardest of these [music]
[00:00:49] benchmarks creep up 1% per month. So,
[00:00:51] not long now.
[00:00:55] >> Now, that's a moonshot, ladies and
[00:00:56] gentlemen.
[00:01:00] Hey everybody, welcome to another
[00:01:01] episode of Moonshot. Uh your favorite AI
[00:01:04] exponential tech pod out there in the
[00:01:06] universe. Uh here with my incredible
[00:01:08] Moonshot mates, um AWG back with his
[00:01:12] orchid fil room DB2
[00:01:15] in in his uh headquarters of all
[00:01:18] exponential investments. And of course,
[00:01:20] Seem is on the road. I mean, you
[00:01:22] remember the book Where's Waldo? I think
[00:01:24] we're going to replace that with Where's
[00:01:25] See? So Salem, where [laughter] are you
[00:01:27] today?
[00:01:28] >> I'm in a car in Guadalajara in Mexico
[00:01:31] transiting to the airport and this was
[00:01:33] the only way I could do this is to do it
[00:01:35] in the car. So hopefully the friends
[00:01:37] hotspot we're piggyback airing off last.
[00:01:39] We'll see how it goes.
[00:01:40] >> I can't believe you brought up Where's
[00:01:41] Waldo? You know, Peter, do you know
[00:01:42] we're the still the exclusive licency of
[00:01:44] Where's Waldo for data mining?
[00:01:46] [laughter]
[00:01:46] >> Okay, we we used to go to trade shows
[00:01:48] and we'd have an actor dressed up in
[00:01:50] that where's Waldo suit and we'd be
[00:01:52] like, "Hey, our neural nets can find
[00:01:54] anything in your data. It's like a
[00:01:55] where's wall and we gave out all the
[00:01:56] books and everything. It's amazing. You
[00:01:58] still remember that.
[00:02:00] >> So, you're in Mexico. The the Blitzy
[00:02:02] team is in Mexico and they're raving
[00:02:04] about the podcast by the way in uh so I
[00:02:06] guess we have a big fan base down there.
[00:02:08] >> We we do it turns out. Yeah, big time.
[00:02:11] >> Um about half the I was at a conference
[00:02:14] of about 1100 people and quite a few of
[00:02:16] them are avid watchers.
[00:02:18] >> That's awesome.
[00:02:19] >> What about the rest? Did you convert
[00:02:20] them?
[00:02:20] >> Yeah. We got to think international
[00:02:21] whenever we're commenting on these
[00:02:22] topics because because you know
[00:02:24] everybody It's a big world and everybody
[00:02:26] out there is is
[00:02:27] >> my Spanish is not quite up to snuff to
[00:02:29] say everybody should watch moonshots in
[00:02:32] espanol.
[00:02:34] >> You know there's translators now just
[00:02:37] >> I [laughter] know
[00:02:38] >> I did my I did my meaning of life
[00:02:40] session last night in Spanish with the
[00:02:42] translator and you should have seen the
[00:02:45] the translator at the end of the night.
[00:02:46] She was so fried.
[00:02:48] [laughter]
[00:02:49] >> And of course, when you're touring
[00:02:50] through India, what do you speak? Hindi
[00:02:52] or do you what?
[00:02:54] >> No, I speak I speak English. It's my
[00:02:56] native tongue cuz I come from a
[00:02:57] diplomatic family. I have pretty bad
[00:02:59] Hindi.
[00:03:00] >> I can get by. But um, you know, it's one
[00:03:03] of these where my grammar is bad, my
[00:03:04] vocs.
[00:03:07] >> Uh, I can get through about 50% of our
[00:03:10] conversation.
[00:03:11] >> Well, we're at almost 500,000
[00:03:13] subscribers. So, next time you're in
[00:03:14] front of our large audience, tell them
[00:03:16] to push us
[00:03:17] >> I do
[00:03:17] >> over to 500,000.
[00:03:19] >> Okay, I'll tell them.
[00:03:22] >> Uh, let's let's jump in. Another
[00:03:25] incredible crazy week.
[00:03:27] >> Um, let's kick it off with a
[00:03:29] conversation around the AI race and the
[00:03:31] agentic boom. So, check out this slide,
[00:03:34] right? I mean, 15 major releases in only
[00:03:38] eight weeks. We're getting a pace of,
[00:03:40] you know, two major models per week. I
[00:03:42] think you've got to be retired and just
[00:03:44] focusing only on this to keep up.
[00:03:46] There's no way otherwise. Uh so in this
[00:03:49] segment, what I'd love to do guys is
[00:03:50] really hit on the last three Kimmy K
[00:03:54] 2.6, GPT 5.5, and DeepSeek 4 V4. Um
[00:04:00] they're extraordinary uh releases. Uh
[00:04:03] each of them, you know, hitting new
[00:04:06] capabilities. You know, one thing, Dave,
[00:04:07] we saw uh the, you know, the acquisition
[00:04:11] or the the invoked acquisition of of
[00:04:14] Cursor by XAI. And I think what's
[00:04:17] interesting is that the winners in this
[00:04:19] crazy model race are going to be those
[00:04:22] that are providing the best abstraction
[00:04:25] layer. So, it doesn't matter what models
[00:04:26] underneath. Um, do you agree with that?
[00:04:32] >> Yeah, totally. Actually, I I just had a
[00:04:33] meeting with a data center uh company
[00:04:35] here in Cambridge, and the amount of
[00:04:38] effort going into the TPUs and the and
[00:04:40] the Nvidia B100, B300s is incredible.
[00:04:43] But at the abstraction layer, there's
[00:04:45] factors of five and 10 just being thrown
[00:04:47] away by mismanagement of the context
[00:04:48] window. And I mean, there's just so much
[00:04:51] opportunity in this stack, which which
[00:04:53] makes sense because it's all brand new,
[00:04:55] >> but it's it's just and also there's a
[00:04:57] lot of vertical integration going on.
[00:04:59] the the warfare is really really
[00:05:01] stepping up. But I can't believe how
[00:05:04] Kimmy K2.6 is keeping up.
[00:05:06] >> I mean, it is just shocking that the
[00:05:09] open source world is is actually on the
[00:05:11] radar and keeping up.
[00:05:12] >> And we'll get to that in a minute, you
[00:05:14] know. But what's interesting is the
[00:05:15] speed of these releases. I'm guessing
[00:05:18] that these these new models are sort of
[00:05:21] uh you know it's competitive marketing
[00:05:23] where the the models are probably
[00:05:25] already cooked and they're just waiting
[00:05:27] for someone else to release and then
[00:05:28] releasing right on top of it.
[00:05:30] >> Anthropic you know is is holding back on
[00:05:31] mythos. So you know that that there's at
[00:05:33] least one case where you're exactly
[00:05:36] proven to be right which means there may
[00:05:38] be others as well. U but it's uh you
[00:05:41] know it's funny the the dot releases are
[00:05:43] coming faster and faster and faster. I
[00:05:45] mean, what's shocking about this list is
[00:05:46] it's it's US versus China, right?
[00:05:48] There's no European models. There's no
[00:05:50] UK models, no Japanese Indian models.
[00:05:53] It's just all US and China. Everyone
[00:05:56] else is a spectator, it looks like, at
[00:05:57] this point. I don't know if if you agree
[00:06:00] with that, but
[00:06:00] >> well, the models are definitely
[00:06:02] self-improving now.
[00:06:03] >> Well, no, you're 100% right, but the
[00:06:05] models are self-improving now. And so,
[00:06:08] you know, the the rate is accelerating.
[00:06:10] Exactly what singularity theory would
[00:06:12] have predicted. the rate is
[00:06:13] accelerating, but because the models are
[00:06:15] improving themselves is it's hard to
[00:06:18] start from a cold start and catch up.
[00:06:20] But I'm surprised that other countries
[00:06:22] aren't using the Kimmy Ku K2.6 model to
[00:06:27] bootstrap their own internal research.
[00:06:29] And may maybe they are and hasn't popped
[00:06:31] under the radar yet, but um you know,
[00:06:33] I'm not finding it too hard to design
[00:06:35] new neural nets using existing neural
[00:06:37] nets. It's it's a very doable thing. And
[00:06:39] and I'm curious, uh, Alex, that chart
[00:06:42] down below on this slide here that's
[00:06:44] showing all the leaprogging. I mean,
[00:06:45] it's leaprogging all the time, but you
[00:06:48] know, is it that they're all just
[00:06:49] cherrypicking? They're all just sort of
[00:06:52] uh, you know, studying for the test on
[00:06:54] the particular benchmark and then
[00:06:56] they're just, you know, releasing
[00:06:57] whatever the latest benchmark that
[00:06:59] they're best at or is this truly
[00:07:01] >> Yeah.
[00:07:02] >> Yeah. Uh, I I I think we're down in the
[00:07:04] west to a three-way race at the frontier
[00:07:07] between OpenAI, Anthropic, and Google.
[00:07:10] And I think those three labs have been
[00:07:13] pretty good about not benchmaxing of
[00:07:16] overfocusing on just one benchmark.
[00:07:18] They're they're pretty good generalist
[00:07:20] models. I I think we're seeing an honest
[00:07:22] to goodness arms race or horse race or
[00:07:24] rat race, depending on which metaphor
[00:07:27] you prefer. My my friends at the
[00:07:28] Frontier Labs often call it a rat race.
[00:07:31] And as as to the Chinese models, it's
[00:07:33] interesting, you know, the apherism, why
[00:07:36] do you rob banks? Because that's where
[00:07:37] the money is. To to the earlier point
[00:07:39] about why no European models, where's
[00:07:42] Mistrol in all of this? For example,
[00:07:45] it's because the US and China are where
[00:07:48] all the compute is. And ultimately I
[00:07:50] think OpenAI's Noam Brown who of course
[00:07:53] is quite famous for having led their
[00:07:56] reasoning approach. He's recently
[00:07:58] started um almost pondering with a a mo
[00:08:03] a bit of onwe whether the weights
[00:08:06] actually matter as much as they used to
[00:08:08] or whether it's really turning into a
[00:08:10] race for compute in in some sense as
[00:08:13] inference time reasoning becomes more
[00:08:15] and more important his argument not mine
[00:08:18] but I I think it's a credible one the
[00:08:20] weights themselves start to become less
[00:08:23] important in the same sense that uh say
[00:08:27] individual units within a transformer
[00:08:30] style architecture become less important
[00:08:33] as the transformer itself starts to
[00:08:34] scale. The overall weights for an entire
[00:08:37] model may become less important as more
[00:08:40] and more reasoning gets used and you see
[00:08:42] in effect a space-time transformer
[00:08:44] that's rolled out over time in reasoning
[00:08:47] token space. So, if that argument holds,
[00:08:49] and I I think it's it's a pretty
[00:08:51] interesting one that I hadn't heard
[00:08:52] elsewhere before, that would almost
[00:08:55] suggest that while at the same time
[00:08:56] we're seeing a race to the bottom on say
[00:09:00] uh per token intelligence densities
[00:09:02] between American models and Chinese
[00:09:05] models, open PNS, the American models
[00:09:08] are still about six months ahead. And
[00:09:09] this has been pretty consistent for the
[00:09:11] the past couple of years. Closed PNS, it
[00:09:14] may not matter in the end. what may
[00:09:16] matter in the end that at least
[00:09:18] according to the scaling laws we have at
[00:09:20] the moment is who has more compute at
[00:09:22] the end of the day to do more reasoning.
[00:09:24] So
[00:09:24] >> and we're going to see that
[00:09:26] >> we're going to see that in a minute. But
[00:09:27] you know I mean 15 models uh you know
[00:09:30] over the course of two months is insane.
[00:09:33] You know some of these are just
[00:09:34] improvements on existing models and some
[00:09:36] of these are completely new pre-trained
[00:09:38] models. I think that difference needs to
[00:09:40] be uh pointed out. See any any thoughts
[00:09:42] on this insanity? Um, you know, just the
[00:09:45] fact that we have that many releases in
[00:09:47] 8 weeks kind of blows my mind. We're
[00:09:48] watch the cost of cognition,
[00:09:50] coordination, execution is all
[00:09:52] collapsing at the same time. I mean,
[00:09:55] this I think that it's so much not so
[00:09:57] much the breakthroughs, it's the
[00:09:58] compression density is crazy.
[00:10:00] >> Well, and the the capabilities, they're
[00:10:01] mind-blowing. These are these are not
[00:10:03] just like, you know, fake little dot
[00:10:05] releases that are benchmaxing. if you
[00:10:07] use them firsthand and you you what's
[00:10:09] really helpful is if you look at our
[00:10:11] podcast or at any postings on the
[00:10:13] internet from three months ago, 6 months
[00:10:15] ago, 9 months ago, 12 months ago and
[00:10:17] look at the predictions of capabilities,
[00:10:19] we're so far ahead of what even the
[00:10:22] upper bound of predictions would be in
[00:10:24] terms of the capabilities as the
[00:10:25] parameter count grows. And so, you know,
[00:10:28] if you extrapolate from there, you know,
[00:10:30] we're we're we're just on this, you
[00:10:33] know, neat knee curve of the
[00:10:34] acceleration in the singularity
[00:10:37] >> and raw parameter count and more chain
[00:10:39] of thought reasoning is just going to
[00:10:41] push us to, you know, limits that are
[00:10:43] way beyond human.
[00:10:45] >> So, what does the average person care
[00:10:47] about?
[00:10:47] >> What does the average person care about
[00:10:49] this? Right? Like my my one of my boys
[00:10:51] says, "Okay, great. A new release with a
[00:10:53] new numbers over and over and over
[00:10:54] again." I at the end of the day uh stuff
[00:10:57] is getting better, it's getting cheaper,
[00:10:59] it's getting faster. Uh you know what
[00:11:02] does the average user I mean do you
[00:11:04] recommend someone sticking with a
[00:11:05] particular model? You know I'm just
[00:11:07] going to be on on OpenAI I'm just going
[00:11:09] to be on anthropic or just going to be
[00:11:11] on Google. Um any thoughts there?
[00:11:13] >> See I I think the question itself is a
[00:11:15] red herring. Why? because OpenAI bet the
[00:11:18] company on consumers using all these
[00:11:21] reasoning tokens that consumer oriented
[00:11:24] strategy for all of this these trillions
[00:11:26] of dollars of capex that they're
[00:11:28] building out would work and they've had
[00:11:30] to pivot rather rather prominently in
[00:11:33] the past few months back to enterprise.
[00:11:35] So I think the question of what does the
[00:11:37] average user care which I construe as
[00:11:39] what does the average consumer care I
[00:11:41] almost think the market is telling us
[00:11:44] the average consumer in the short term
[00:11:46] isn't even part of the equation anymore.
[00:11:48] This is really the question should be
[00:11:50] what does the average enterprise care
[00:11:52] because they're the ones
[00:11:53] >> asking for I'm asking for our listeners
[00:11:55] right uh a lot of them are entrepreneurs
[00:11:58] or general consumers I mean at the end
[00:12:01] of the day is it okay for someone I'm
[00:12:03] just using chat GPT I'm just using you
[00:12:06] know Gemini 3.1 Pro I'm just using you
[00:12:09] know the latest version of anthropics
[00:12:11] models you know is it important for
[00:12:13] people to be driving to the latest model
[00:12:16] or is it okay because ultimately
[00:12:18] Everybody's basically leapfrogging
[00:12:20] everybody else. And you know, if you're
[00:12:23] just a, you know, a mom, a dad, a
[00:12:25] student, and, you know, maybe an
[00:12:28] entrepreneur just getting going, um,
[00:12:31] this insanity of 15 models in 8 weeks,
[00:12:33] bouncing back and forth. I mean, Dave,
[00:12:36] you you're using, you know, two, three
[00:12:38] or four models all the time, right?
[00:12:40] >> Oh, many more now. And and that's the
[00:12:43] biggest change. the uh the coordinator
[00:12:45] model can now manage dozens or hundreds
[00:12:47] of other models successfully and and 6
[00:12:49] months ago or three months ago that
[00:12:50] wasn't true. So, you know, for the
[00:12:52] average consumer, the ability for the
[00:12:54] stuff to install itself, like you can go
[00:12:56] into the model now, you have to use the
[00:12:58] latest ones. Uh, but it doesn't matter a
[00:13:00] lot whether you're using cloud 4.7 or or
[00:13:02] GPT 5.5, you know, just use one of the
[00:13:04] latest ones, but ask it to install
[00:13:06] itself. Ask it to build something on
[00:13:09] your laptop for you and it just works.
[00:13:10] Now, you don't have to understand, you
[00:13:12] know, the Linux command line. You don't
[00:13:14] have to understand any of the underlying
[00:13:15] infrastructure. It's smart enough now to
[00:13:18] explain itself to you as it goes. So I
[00:13:21] think for the average listener that's a
[00:13:22] massive unlock. You know, someone who's
[00:13:24] never built software before can just
[00:13:27] think of something and then create it in
[00:13:29] an hour. And that that just wasn't true,
[00:13:32] you know, 6 months ago.
[00:13:33] >> Hey everybody, [snorts] you may not know
[00:13:34] this, but I've got an incredible
[00:13:36] research team. And every week myself, my
[00:13:38] research team study the meta trends that
[00:13:40] are impacting the world. Topics like
[00:13:42] computation, sensors, networks, AI,
[00:13:44] robotics, 3D printing, synthetic
[00:13:46] biology. And these Metatrend reports I
[00:13:48] put out once a week enable you to see
[00:13:51] the future 10 years ahead of anybody
[00:13:53] else. If you'd like to get access to the
[00:13:55] Metatrends newsletter every week, go to
[00:13:57] diamandis.com/metatrends.
[00:13:59] That's diamandis.com/metatrends.
[00:14:02] Yeah, let's jump into our our first uh
[00:14:05] our first model story here, which is
[00:14:07] Moonshot AI launches Kimmy K2.6.
[00:14:11] I just downloaded onto my Mac Studios
[00:14:13] this weekend on top of Skippy uh who's
[00:14:15] orchestrated by you know Opus 46.
[00:14:18] >> So Kimmy uh K2.6 it's a trillion
[00:14:21] parameter openweight open- source model
[00:14:24] uh activates 32 billion of the
[00:14:26] parameters at a time. It runs 300
[00:14:28] parallel agents. Uh very importantly
[00:14:31] natively it can process text, image and
[00:14:33] video all at the same time and costs 30
[00:14:36] times less than the most capable closed
[00:14:39] models. Uh, interesting enough, uh, you
[00:14:41] know, Moonshots AI, uh, didn't get its
[00:14:43] name from us. Uh, the three founders
[00:14:46] based in Beijing. Their favorite album
[00:14:48] is Dark Side of the Moon. And so, that's
[00:14:50] where it came from. And the company's
[00:14:52] backed by about 4.7 billion in capital
[00:14:55] from Alibaba, Tencent, and IDG. And this
[00:14:59] model right if you look at the numbers
[00:15:01] in the bottom uh on the benchmarks
[00:15:03] compared to GPT54 Opus 46 and Gemini 3.1
[00:15:07] Pro this it does amazingly well against
[00:15:10] all those models and this one was
[00:15:12] trained they report for a total of $4.6
[00:15:16] 6 million uh compared to hundreds of
[00:15:19] millions or billions on the other, you
[00:15:21] know, closed source models. Dave, I
[00:15:25] mean, I find that amazing. I mean,
[00:15:27] almost so
[00:15:28] >> almost incredible.
[00:15:29] >> It's so much to say about this, you
[00:15:31] know. You know, starting from the fact
[00:15:32] that,
[00:15:32] >> yeah, Alex said a minute ago that, you
[00:15:34] know, that the Chinese models are
[00:15:35] running about 6 months behind the US
[00:15:37] models. But if you look at the
[00:15:38] benchmarks, you know, this is up there
[00:15:40] or beating Claude Opus 4.6, which was
[00:15:42] only three months ago. That came out in
[00:15:44] February. And so that's that's not a
[00:15:46] six-month lead, that's a three-month
[00:15:47] lead. And the uh the price performance,
[00:15:51] you know, most people when they first
[00:15:53] start, they don't care too much. It's
[00:15:54] it's cheap. You know, all AIS are pretty
[00:15:56] cheap. But then when you realize that
[00:15:58] you can run 10 or 100 of them
[00:16:00] concurrently, you're like, well, this is
[00:16:02] going to start to add up. So, uh, if you
[00:16:04] run this on fireworks AI, it's about 1/8
[00:16:07] the cost of running the cloud API or or
[00:16:11] the open AI API. So, uh, you know, 1/8
[00:16:14] is a pretty damn big price cut. If you
[00:16:16] download it and run it like you did with
[00:16:18] Skippy, then you're running at about
[00:16:19] 1/30th the cost. Uh, so, so that's a big
[00:16:23] big deal. Uh, and then of course the
[00:16:25] caveat is, as Alex has pointed out many
[00:16:27] times, you're not 100% sure if it's not,
[00:16:30] you know, spying or doing code
[00:16:31] injection. Uh, it's probably not, but
[00:16:35] you can't guarantee that. So, that's
[00:16:37] that's, [laughter] you know, so somebody
[00:16:39] tells me this is 130th the price. Try
[00:16:41] it. you're like, I'm a little sus. Like,
[00:16:43] why is it 130th the price? But I I doubt
[00:16:46] it's code injecting on you, but you
[00:16:48] can't be sure. Whereas, if you use
[00:16:49] enthropic or open AI, it's definitely
[00:16:51] not code injecting on you. In fact, it's
[00:16:52] safeguarded all over the place. So,
[00:16:54] there there's your landscape. Chaotic as
[00:16:56] always. It's only going to get more
[00:16:57] chaotic.
[00:16:59] >> Alex, how big a how big a deal is Kimmy
[00:17:01] K2.6? I think it's helpful for certain
[00:17:04] enterprise use cases where you want to
[00:17:06] be able to self-host the model and you
[00:17:08] don't want to say use AWS Bedrock, which
[00:17:11] by the way now hosts GPT 5.5 in addition
[00:17:14] to the Opus models. I think it's helpful
[00:17:16] in that respect. It's helpful if you
[00:17:18] want to be able to self-host fine-tuned
[00:17:21] models for yourself. Ditto with Deepseek
[00:17:24] V4. But I I think in general again it's
[00:17:27] a few months behind for other use cases
[00:17:30] for consumers uh that uh that want to be
[00:17:33] able to self-host for whatever reason
[00:17:35] privacy or otherwise probably very
[00:17:37] helpful for folks who want to self-host
[00:17:39] their own clause. Very helpful. So I I
[00:17:42] think there are many use cases where
[00:17:44] these typically Chinese openweight
[00:17:47] models like Kimmy K 2.6 6 and Deepseek
[00:17:51] V4 are very helpful. I I do think,
[00:17:54] however, they're not at the frontier.
[00:17:56] And to me, the the big headline is that
[00:17:59] disparity between the American frontier
[00:18:01] closed weight and the Chinese frontier
[00:18:04] open weight seems at least for the
[00:18:06] moment to be in place.
[00:18:07] >> Yeah, Peter, I think your your setup is
[00:18:09] perfect. It's exactly what I do, too. I
[00:18:11] I use uh you know Opus 4.7 as my
[00:18:15] orchestrator because you want that extra
[00:18:17] notch of intelligence and then if you
[00:18:19] have simple tasks or you're just
[00:18:21] subtasks you can farm them out and save
[00:18:24] the money using um you know using chem
[00:18:27] K2.6 six uh and then if the results
[00:18:31] coming back don't make perfect sense
[00:18:33] then your orchestrator will tell you hey
[00:18:34] this is garbage and so you can actually
[00:18:36] rely on opus 4.7 to give you the the
[00:18:38] straight truth on what the underlying
[00:18:40] models did for you it's a so it's
[00:18:41] exactly the way you set it up Peter
[00:18:43] >> yeah Dave a week ago you said you moved
[00:18:45] from 4.7 back to 4.6 six. Did you move
[00:18:48] back to 4.7?
[00:18:49] >> Uh, I have both running now. 4.7 is kind
[00:18:52] of wordy and sounds kind of PhDish,
[00:18:55] which annoys me sometimes. Uh, and 4.6
[00:18:58] is friendlier, but then, you know, it's
[00:19:00] clear that 4.7 is a little smarter. And
[00:19:02] so, sometimes you just need the right
[00:19:03] answer no matter what. And so, I
[00:19:05] actually have both running in parallel
[00:19:07] uh agent windows now. See, I'm curious
[00:19:10] in Guadalajara, Mexico City, you know,
[00:19:13] in parts of South America and I know in
[00:19:16] parts of Asia, what are you hearing
[00:19:18] about the use of US models versus
[00:19:21] openweight, open source Chinese models?
[00:19:23] >> So, I get a mixture of both things. Um,
[00:19:26] a bunch of people use the hosted models,
[00:19:29] the big ones, just because it's easy.
[00:19:32] uh there's a subset of people that use
[00:19:34] the uh open source models and and the
[00:19:37] Chinese models and they don't really
[00:19:39] care. Um I think they should care at
[00:19:42] some point that's going to come up. One
[00:19:44] question I have for Alex and Dave is how
[00:19:46] do you protect against the code or
[00:19:48] prompt injection in these open source?
[00:19:51] Is there a way of defending against
[00:19:52] that? Um if that's if there is then
[00:19:55] there's a huge case for this because
[00:19:57] everybody here is looking for the
[00:19:58] lowcost approach, right? Um the but for
[00:20:02] the most part I'll be blunt um the
[00:20:04] conversation is not around which model
[00:20:08] and open source or closes like what do
[00:20:09] we do with AI like that's literally uh
[00:20:12] at a level of um lack of sophistication
[00:20:17] around this that you would expect. Um
[00:20:19] but the opportunity is also there for
[00:20:21] startups then to leaprog lots of people
[00:20:23] and and build aggressively for the
[00:20:26] coming madness that's upon us. Yeah,
[00:20:29] it's almost an impossible question,
[00:20:30] Seem, because because if you well, if
[00:20:33] you sit on the sideline and you don't
[00:20:35] use this stuff aggressively, you fall
[00:20:37] way way behind.
[00:20:38] >> Yeah.
[00:20:39] >> But if you start using it aggressively,
[00:20:40] you're generating thousands or millions
[00:20:42] of lines of code before you even know
[00:20:43] it.
[00:20:44] >> And so then the odds go up, right? that
[00:20:46] you know so I think what you're trusting
[00:20:48] right now is that the guardrails that uh
[00:20:51] that Anthropic and OpenAI put on their
[00:20:53] models they're very very cautious uh
[00:20:56] when they're pulling in code open source
[00:20:58] or otherwise I mean almost annoyingly
[00:21:00] cautious so you kind of assume they've
[00:21:02] done a very very good job of filtering
[00:21:04] out you know nasty code injection but
[00:21:07] the numbers work against you at scale
[00:21:09] you know so there there's no there's no
[00:21:12] simple answer I mean you could you can
[00:21:13] when I got into it I was like hey I'm
[00:21:15] just going to look at the code. I'm not
[00:21:16] going to just run it. I'm going to see
[00:21:18] what it does. That's a joke, right?
[00:21:20] That's just laughable. It's generating
[00:21:21] so quickly now that there's no chance
[00:21:23] you could even scroll through it. So,
[00:21:26] uh, you have to use AI to it's like a
[00:21:28] lot of things actually, you have to use
[00:21:29] AI to to protect against AI. There's no
[00:21:31] other other way to to get the scale. Uh,
[00:21:35] so it's tricky. I know that wasn't much
[00:21:37] of an answer, but it's tricky. You know,
[00:21:38] one thing I'd love to point out here,
[00:21:40] uh, we talk about this on occasion, but
[00:21:43] I don't think we've ever really spoken
[00:21:44] about in detail. The Kimmy K2.6 uses
[00:21:47] something called a mixture of experts,
[00:21:49] ane. And it's interesting, uh, and just
[00:21:52] to take a moment about this. If in fact
[00:21:55] you're have a trillion parameter model,
[00:21:58] uh, and you ask a question, it's
[00:22:01] basically accessing all trillion
[00:22:03] parameters every time to analyze every
[00:22:06] token. And what they did here is they
[00:22:09] actually created you know a set of 30
[00:22:12] plus uh experts and so that you know
[00:22:15] some percentage of all the parameters
[00:22:17] are dedicated to one expert system. So
[00:22:20] if you ask a coding question, you know,
[00:22:23] the orchestrator looks at this and and
[00:22:26] says, "Okay, this is a coding question.
[00:22:28] We're going to send it to, you know,
[00:22:29] experts number three, 7 and 12 and only
[00:22:33] uses a portion of the of the parameters,
[00:22:35] right? It only uses, you know, uh
[00:22:37] instead of uh all the experts, all the
[00:22:40] experts, it uses some subfraction
[00:22:42] thereof and it saves money and saves
[00:22:45] time." And I you know how many different
[00:22:47] models are using that right now Alex?
[00:22:49] >> Sparsity which is the term of art I
[00:22:51] think that we're talking about here is
[00:22:53] endemic to all frontier models at this
[00:22:55] point. It's also the basis for the human
[00:22:57] brain. If if we look at the brain most
[00:23:00] most neurons don't at any given point in
[00:23:02] time have action potentials that that
[00:23:05] are going in and out. So sparsity is a
[00:23:07] great way to reduce the memory footprint
[00:23:09] of models. To my knowledge all of the
[00:23:11] Frontier models use sparsity one way or
[00:23:14] another. It's it's also a good way to uh
[00:23:16] another term of art regularize the
[00:23:19] models. So to to make sure that
[00:23:21] particular weights or parameters in the
[00:23:23] models aren't overfitting to the
[00:23:25] training data. One of the age-old
[00:23:27] techniques is just blasting away
[00:23:30] individual weights or parameters in the
[00:23:32] neurons making them disappear entirely
[00:23:34] as a a so-called regularization
[00:23:36] technique. So sparity is everywhere at
[00:23:38] this point and it it's only going to I I
[00:23:40] think become more important with time as
[00:23:43] we try you know I'm what one of my uh
[00:23:46] one of my holy grails is as as I've
[00:23:49] mentioned on the pod previously I'd like
[00:23:50] to see a million parameter or smaller
[00:23:54] diamond or black hole of of a model at
[00:23:56] the end of the scaling race and I think
[00:23:59] sparsity and cranking the knob on
[00:24:01] increasing sparification in these models
[00:24:04] is one possible path to getting us Hey,
[00:24:06] and just to add something that to what
[00:24:08] Peter said, uh the thee innovation,
[00:24:11] mixture of experts innovation that came
[00:24:13] from deepseek is actually layer by
[00:24:15] layer. So most of these neural nets are
[00:24:16] about 140 layers deep now. And uh it'll
[00:24:20] route the expert layer by layer. So
[00:24:23] it'll say look within this layer I'm
[00:24:25] just doing basic you know image
[00:24:27] classification and this layer I'm doing
[00:24:28] deeper thinking and this layer I'm doing
[00:24:30] higher level math. you know, as it moves
[00:24:31] through the neural net, it'll actually
[00:24:33] route to, you know, now I think up to
[00:24:36] 128 different experts layer by layer.
[00:24:39] So, it'll find the optimal pathway
[00:24:40] through the entire neural net. On top of
[00:24:42] that, you can also have dedicated
[00:24:44] experts like here's a surgeon, here's an
[00:24:47] artist, here's a coder above and beyond
[00:24:50] that, but is actually within the neural
[00:24:52] net layer by layer.
[00:24:53] >> All right, next story is OpenI unveiled
[00:24:56] GPT 5.5 literally just 7 weeks after GPT
[00:25:00] 5.4. for Greg Brockman calls it a new
[00:25:02] class of intelligence. It's natively uh
[00:25:05] omniodality. It's you know it's able to
[00:25:07] process uh text and audio and video and
[00:25:11] images all in a single unified endto-end
[00:25:13] architecture. Uh it has a 37 point
[00:25:17] increase in uh over 5.5 over 5.4 in long
[00:25:21] context reasoning which means 5.4 4 and
[00:25:24] 5.5 are both a million token windows,
[00:25:26] but 5.5 can actually remember the
[00:25:29] beginning of the million tokens and
[00:25:31] provide, you know, complete context
[00:25:33] across the entire thing. Token
[00:25:36] efficiency, 40% fewer tokens with the
[00:25:38] same latency. And I love this
[00:25:40] hallucination is down 60% over 5.4.
[00:25:45] Let's go to our resident genius, Alex.
[00:25:48] What do you make of 5.5? How important
[00:25:50] is it? I think it's very important both
[00:25:53] intrinsically and also relative to 5.4.
[00:25:57] So I want to highlight two key stats
[00:25:59] here. The first is the leap from GPT 5.4
[00:26:02] thinking to 5.5 thinking. That's
[00:26:05] probably the biggest leap overall uh on
[00:26:08] terminal bench 2.0 specifically. So one
[00:26:11] way to interpret this terminal bench is
[00:26:13] a benchmark that's focused on the
[00:26:15] ability to agentically operate from a
[00:26:17] command line terminal. Where is that
[00:26:19] useful for codecs and for cloud code
[00:26:22] type environments? So one way to
[00:26:23] construe this huge leap which is larger
[00:26:26] than most of the most or all of the
[00:26:29] other leaps that we see in in terms of
[00:26:31] other benchmarks is that 5.5 is being
[00:26:35] very seriously focused benchmaxed if you
[00:26:38] like. Although I I really having used it
[00:26:40] don't think it's narrowly overfitting
[00:26:42] just to creating and making codeex a a
[00:26:46] better clawed code competitor. but it
[00:26:48] very much feels like a release that's
[00:26:50] intended to strengthen OpenAI's codecs.
[00:26:54] That's thought one. Thought two is my
[00:26:56] favorite benchmark among all of these is
[00:26:59] Frontier Math Tier 4. Frontier Math Tier
[00:27:02] 4, which I I think we even had a New
[00:27:04] Year's bet about that we're going to
[00:27:06] have to revisit sometime later this
[00:27:08] year, is one of the best proxies for the
[00:27:11] ability for AIS to solve professional
[00:27:14] level research problems in math. And
[00:27:17] what do we see? We see from GPT 5.4 Pro
[00:27:21] to 5.5 Pro, approximately a 2% leap in
[00:27:26] approximately the last 2 months. What
[00:27:28] does that tell me? That tells me that
[00:27:30] we're seeing now approximately 1% gains
[00:27:34] per month in research level math coming
[00:27:37] from frontier AIs and we're getting
[00:27:40] closer to approximately half of all of
[00:27:43] the frontier math tier 4 problems
[00:27:45] getting solved. So you can extrapolate
[00:27:47] this and realize if the present rate
[00:27:49] just stays the same, which I guarantee
[00:27:51] it won't, it's going to accelerate. But
[00:27:53] even just at the present pace, we're
[00:27:55] talking about essentially all frontier
[00:27:59] math tier 4, all professional research
[00:28:02] grade math problems being solved in the
[00:28:05] next four or 5 years. So math is cooked.
[00:28:09] We I I'll say it, you know, second time.
[00:28:11] Math is cooked. Bunch of other things
[00:28:13] are cooked as well. But things are
[00:28:15] moving so quickly now that on a
[00:28:16] month-by-month basis, we're able to see
[00:28:19] the hardest of these benchmarks creep up
[00:28:21] 1% per month. So, not long. Now,
[00:28:23] >> it's worth pointing out that the API
[00:28:25] pricing on 5.5 is twice that of 5.4. So,
[00:28:29] it's five bucks per million input tokens
[00:28:32] versus $2.5 on 54 and 30 bucks uh per
[00:28:37] million output tokens versus 15. Uh I I
[00:28:40] like the simplicity of that pricing.
[00:28:42] Dave, have you been playing with this at
[00:28:43] all?
[00:28:44] >> Yeah, absolutely. And and I think what
[00:28:45] Alex said earlier in the pod is is
[00:28:47] really really important and insightful.
[00:28:49] like no one Brown is saying, "Wow, maybe
[00:28:51] the weights don't matter so much as this
[00:28:54] chain of thought process is is just way
[00:28:57] ahead of of any expectations on how
[00:28:59] intelligent it can get." From a user's
[00:29:01] point of view, that first benchmark uh
[00:29:03] terminal bench, if you ask it to do
[00:29:05] something complicated like configure an
[00:29:07] entire system for you, download some
[00:29:09] software, integrate it, make it all
[00:29:11] work, you know, connect it to my
[00:29:13] Outlook, connect it to my whatever, uh
[00:29:15] it just works. And that that exactly
[00:29:18] ties to that first benchmark. It just
[00:29:20] flat out works. Uh and so it just it
[00:29:23] feels like this incredibly capable
[00:29:25] brilliant assistant no matter what
[00:29:26] you're trying to do because of that
[00:29:28] first benchmark. Then that the last
[00:29:31] benchmark the frontier or second to last
[00:29:33] frontier math uh you know Demisabus came
[00:29:36] out and said yeah I think it's a kind of
[00:29:37] a coin flip. This was on Alex's uh
[00:29:40] innermost loop. You know, it's kind of a
[00:29:42] coin flip now on whether just the
[00:29:44] existing architecture scaled up solves
[00:29:46] everything.
[00:29:47] >> Yeah,
[00:29:47] >> I think I think coin flip he's moved a
[00:29:49] long way.
[00:29:50] >> He has, you know, we need new
[00:29:52] breakthroughs.
[00:29:52] >> We're out of breakthroughs apparently. I
[00:29:54] I remember 10 plus years ago when I was
[00:29:56] chatting with Demis, he used to say
[00:29:58] there were five breakthroughs remaining
[00:30:00] between where we were then and AGI as he
[00:30:03] construed it. Now we're out of them.
[00:30:04] It's it's half a breakthrough or zero
[00:30:06] breakthroughs at this point. You know,
[00:30:07] next week we're going to be on with with
[00:30:09] Ray Kerszswall again. Um we're doing
[00:30:12] that May 4th event for the launch of We
[00:30:14] Are As Gods. And I'm curious, we should
[00:30:17] ask him uh you know, what does he think
[00:30:20] what's required to get to true AGI or
[00:30:22] ASI? Are we just going to extrapolate
[00:30:24] what we're doing? Uh or do we need
[00:30:26] breakthroughs? I I think that that
[00:30:28] requirement's been been falling um
[00:30:32] better or less. I mean, it's starting to
[00:30:33] feel a lot like like actually Alex, you
[00:30:37] know what would be great for that is to
[00:30:38] put together a chart of Dennis's number
[00:30:40] of breakthroughs, which because at Davos
[00:30:42] it was down to two. Now it's down to
[00:30:44] 50/50 that it's zero, but you you
[00:30:46] mentioned five. That was what maybe a
[00:30:48] year and a half ago. So, that'd be a
[00:30:49] really cool chart.
[00:30:50] >> The five number from him was when I was
[00:30:52] chatting with him in uh this is 10 plus
[00:30:55] years ago.
[00:30:57] >> Yeah.
[00:30:58] >> Okay.
[00:30:59] >> Well, there's some sort of exponential
[00:31:01] decay of breakthroughs. Clearly,
[00:31:03] >> Alex, you said it a little bit earlier.
[00:31:05] You know, this is ultimately a compute
[00:31:07] race. So, uh let's talk about that. You
[00:31:11] know, a couple of a couple of stories
[00:31:12] here around Google Cloud. Um and Google
[00:31:15] Cloud is dominating. So, what do we see?
[00:31:18] We see Google announcing at Google Cloud
[00:31:21] Next 2026, their major conference. They
[00:31:24] unveiled their eighth generation of
[00:31:26] TPUs. uh in particular TPU8T for
[00:31:30] training and TPU8 for inference. Right
[00:31:33] now we have uh training and inference
[00:31:35] chips separately just like Amazon has
[00:31:37] their tranium chips for training and
[00:31:39] their inferentia chips for inference. Uh
[00:31:42] these new GPU these new TPUs are three
[00:31:45] times faster in training performance 80%
[00:31:48] better performance per dollar. They're
[00:31:50] designed to run millions of agents in
[00:31:52] real time. So Google is really all in on
[00:31:56] the agentic era. Sundar Pachai, the CEO,
[00:31:59] who I had a chance to spend some time
[00:32:00] with last weekend, he made it crystal
[00:32:02] clear. He says over 16 billion tokens
[00:32:04] per minute being processed in 75% of
[00:32:07] Google's code is now written by AI. So
[00:32:11] um, fascinating. Dave, what do you make
[00:32:14] of this?
[00:32:14] >> Yeah, you know what's surprising to me
[00:32:15] is that the the price performance of the
[00:32:17] TPUs is landing right on top of Nvidia.
[00:32:19] not not much different at all, which is
[00:32:21] surprising because it's a completely
[00:32:23] different architecture. It uses a
[00:32:25] systolic array design. I mean, it could
[00:32:27] not be more different from a GPU under
[00:32:29] the covers, but for whatever reason,
[00:32:31] it's all kind of canceling out and
[00:32:33] landing identical, which is fine from
[00:32:36] Google's point of view because now they
[00:32:37] have their own total, you know, chip fab
[00:32:40] through data center through model.
[00:32:41] >> They do everything
[00:32:42] >> solution. Yeah,
[00:32:44] >> I'm still I still believe Google's the
[00:32:46] winner in the long run here across the
[00:32:48] board. I don't know if you agree with
[00:32:49] that.
[00:32:50] >> Terraab is a big thing.
[00:32:52] >> That's true. I'm sorry. Yes. Okay. I'm
[00:32:54] I'm thinking in the o in the open AI and
[00:32:56] anthropic ecosystem. Yeah. Terrafab
[00:32:59] >> on the other hand, Google owns a
[00:33:00] material percentage of SpaceX.
[00:33:02] >> They do. They do.
[00:33:04] >> I don't know if you saw I don't know if
[00:33:05] you saw there was a uh a tweet out
[00:33:07] recently about Google's investments that
[00:33:09] were made. Um, yeah. And they just had
[00:33:12] massive returns on their investments on
[00:33:14] SpaceX, on Anthropic, across the board.
[00:33:17] Huge returns.
[00:33:17] >> Yeah. I was at a board meeting
[00:33:18] yesterday, a company that I'm the
[00:33:20] chairman of that has massive cash flow
[00:33:22] and a huge cash balance. And they were
[00:33:24] like, well, I don't know if a public
[00:33:26] company can really do seedstage
[00:33:27] investments. I was like, have you looked
[00:33:29] at Google? [laughter]
[00:33:29] >> Yeah.
[00:33:30] >> They have multiple hundred billion
[00:33:32] dollar gains on on their investments.
[00:33:34] And and they don't even do it for the
[00:33:36] money. They do it for the knowledge and
[00:33:37] for
[00:33:38] >> well and strategic relationships, right?
[00:33:40] Larry and Sergey were just bonding with
[00:33:42] Elon and they said, "Okay, Google is
[00:33:44] going to invest a billion dollars and
[00:33:46] now it's worth, you know, God knows how
[00:33:48] many hundreds times more."
[00:33:50] >> Yeah.
[00:33:50] >> It's also just investing in the future.
[00:33:52] I I I I remember conversations with
[00:33:55] Larry and Sergey about the nature of the
[00:33:57] frontier, and I I think to their credit,
[00:33:59] they're investing in the frontier, and
[00:34:01] SpaceX is part of it. And and also
[00:34:03] compute. Uh Epic put out this really I
[00:34:06] think eye-opening stat in the the past
[00:34:09] week that Google now accounts for
[00:34:11] approximately quarter of all of the AI
[00:34:14] compute on the planet and I'm sure
[00:34:16] eighth gen TPUs will be part of it. I I
[00:34:18] think it's also worth keeping in mind
[00:34:20] that the TPUs at this point are being
[00:34:22] designed by TPUs. I have number of
[00:34:24] friends at Google who are responsible
[00:34:26] for designing nextgen TPUs and they're
[00:34:29] all just using Google AI to do it. the
[00:34:31] the recursive self-improvement goes all
[00:34:34] the way down to the silicon at this
[00:34:35] point.
[00:34:35] >> All right. Our our next story in uh the
[00:34:38] Google ecosystem again also announced at
[00:34:41] uh at their large cloud next conference
[00:34:44] is Google commits to 960,000
[00:34:47] Nvidia Ver Rubin GPUs for their A5X.
[00:34:52] So uh pretty extraordinary. A5X is
[00:34:54] Google's new bare metal virtual machine
[00:34:56] instance uh delivering 10x lower
[00:34:59] inference costs and 10x higher token
[00:35:02] throughput. Uh just an interesting FYI,
[00:35:04] Vera Rubin uh for whom uh these chips
[00:35:08] are named was an American astronomer who
[00:35:10] discovered the first conclusive evidence
[00:35:12] of dark matter. Um I love the fact that
[00:35:15] Jensen is naming chips and systems after
[00:35:19] you know famous individuals. Uh now what
[00:35:21] I find fascinating, this goes back to
[00:35:22] the conversation a minute ago, is that
[00:35:24] this cloud is two times bigger than
[00:35:28] Colossus 2 and 2.4 times bigger than
[00:35:30] Stargate Abene. Uh so Google is winning
[00:35:35] on at least based on what they're
[00:35:37] building and plan to build. Again, uh
[00:35:40] Dave, thoughts here? Well, you know,
[00:35:41] part of the I just to touch on one thing
[00:35:43] you said there, Peter. Part of the
[00:35:44] acceleration we're seeing in society as
[00:35:46] a whole is that all the really really
[00:35:49] smart people are working on real tech
[00:35:51] now and
[00:35:52] >> hard hardware
[00:35:54] >> hardware and and space and and medicine
[00:35:57] and like real tech.
[00:35:59] >> And you know, if you go back to the meta
[00:36:01] era, the Facebook era, the rewards were
[00:36:03] all in either uh you know, cheesy
[00:36:05] consumer experiences or banking. and
[00:36:08] doing deep tech was kind of a like a way
[00:36:10] to to die poor. So, it's it's creating a
[00:36:13] whole new era for society. You know, the
[00:36:14] postAI era, we all knew it was going to
[00:36:16] be very very different. But now the
[00:36:17] rewards are in actual uh deep tech that
[00:36:20] benefits humanity in really big
[00:36:22] fundamental ways. But I think if you
[00:36:24] just counted the number of people that
[00:36:26] you know that have been pulled into this
[00:36:27] vortex, you it would have been just a
[00:36:29] few percent working on worldchanging
[00:36:31] deep tech real stuff just you know 15 20
[00:36:34] 30 years ago. Now it's almost everybody
[00:36:36] that you know is getting pulled into
[00:36:38] like you know do something big and world
[00:36:41] changing and it's actually working and
[00:36:42] so that's a big change for society. So
[00:36:45] that's helping accelerate things as
[00:36:47] well.
[00:36:48] >> All right our next story is anthropic is
[00:36:50] cutting deals for cash and compute. Um I
[00:36:54] mean huge amount of capital flying back
[00:36:56] and forth between the frontier labs and
[00:36:58] the hyperscalers here. So uh Google
[00:37:01] commits to a $40 billion investment in
[00:37:03] anthropic. So last week, Google
[00:37:05] committed to a ton of money, $10 billion
[00:37:08] in cash right now at a $350 billion
[00:37:12] valuation. And note, you know, we talked
[00:37:14] about this last time, anthropic on the
[00:37:16] secondary markets is now at a trillion
[00:37:18] valuation. So this $350 billion is
[00:37:21] coming in at roughly onethird the cost
[00:37:24] of what others are paying for it. And
[00:37:26] they committed to another $30 billion if
[00:37:28] Enthropic hits certain performance
[00:37:30] targets as well. uh they're going to be
[00:37:33] providing 5 gawatts of TPU compute
[00:37:36] committed over 5 years. That's the
[00:37:38] equivalent of you know literally
[00:37:40] providing power to 3 to four million
[00:37:42] people. Um I'm finding this pretty
[00:37:46] extraordinary. Uh we're going to see in
[00:37:48] a moment a conversation where Anthrop
[00:37:50] has cut deals with Amazon in a similar
[00:37:52] fashion. Actually, let me go ahead and
[00:37:54] hit that and we'll talk about uh this uh
[00:37:57] these money for guns uh conversation
[00:38:00] that's going on. So Amazon and Anthropic
[00:38:03] are trading cash for compute. So here's
[00:38:05] a second deal. Uh Amazon is investing a
[00:38:09] total of 33 billion. They've committed
[00:38:11] to 25 billion on top of the 8 billion
[00:38:14] they've already invested. Um in return
[00:38:16] for Amazon's cash, Anthropic is
[00:38:18] committing to spend hundred billion or
[00:38:21] more on AWS over the next decade.
[00:38:24] Anthropic will run claude on Amazon's
[00:38:27] custom tranium chips and Amazon will
[00:38:29] provide 5 gawatts of AI compute capacity
[00:38:32] for Anthropic. So I mean we're seeing
[00:38:35] Anthropic becoming beholden to both AWS
[00:38:38] and Google in a significant fashion.
[00:38:41] Gentlemen, uh thoughts on this one?
[00:38:45] >> Well, it's it's so funny to me like
[00:38:46] obviously Anthropic needs much much more
[00:38:48] compute and is growing. Oh, actually a
[00:38:51] very good friend of ours, Peter, I won't
[00:38:53] mention him on the podcast, but he's an
[00:38:54] investor in Anthropic, uh, and he was
[00:38:56] telling me at the board meeting
[00:38:57] yesterday, he can figure it out from
[00:38:59] that comment, but [laughter] he was
[00:39:01] telling me at the board meeting
[00:39:01] yesterday that, uh, Anthropic under the
[00:39:04] covers is thinking they might hit
[00:39:05] between 40, 50 up to 70 billion in
[00:39:08] revenue by the end of the year.
[00:39:09] >> We talked about 100 billion uh, by the
[00:39:11] end of the year a few pods ago, but
[00:39:13] still, I mean, dillion last month,
[00:39:16] doubling, tripling.
[00:39:17] >> It's extraordinary. And the only reason
[00:39:20] wouldn't hit those numbers is because
[00:39:21] they can't get enough compute to keep up
[00:39:23] with the demand.
[00:39:24] >> And one of the things was that they they
[00:39:26] didn't release Mythos because they have
[00:39:28] enough compute to deal with it. Right.
[00:39:29] So it's a limited uh a limited release
[00:39:31] of the capabilities.
[00:39:33] >> Yeah. And OpenAI cut Sora. I think one
[00:39:35] of the reasons is probably compute. Uh
[00:39:38] so yeah, there's an imminent
[00:39:41] >> which is Yeah. Which is energy. And and
[00:39:43] I think that um it's so funny to me to
[00:39:45] see all these deals. So, okay, so Dario
[00:39:47] needs compute. He signs up with Amazon.
[00:39:49] You know, Google's already a shareholder
[00:39:51] in Anthropic. Uh, they're all and now
[00:39:54] OpenAI is going to be running on GCP and
[00:39:56] also on um uh on Bedrock on Amazon.
[00:40:00] >> So, you can get it through, you know,
[00:40:01] get it through Bedrock. So, everybody's
[00:40:02] partnering with everybody else, but
[00:40:04] >> it's all bottlenecked at TSMC. Like,
[00:40:07] like this is all great. You can all
[00:40:08] partner with each other up the yin-yang,
[00:40:10] but whose chips are actually going to
[00:40:12] get made? you know who and no you don't
[00:40:15] see TSMC in any of these podcasts in any
[00:40:17] of these deals any of these meetings and
[00:40:19] and you saw Jensen actually recently say
[00:40:21] he doesn't have any long-term agreement
[00:40:23] with TSMC they just kind of make it up
[00:40:25] as they go so all of this is
[00:40:27] bottlenecked and only Elon is talking
[00:40:29] about look the fundamental constraint to
[00:40:32] all of this is the tarap and I already
[00:40:35] locked up 16 billion could be 45 billion
[00:40:38] of of Samsung's capacity the only three
[00:40:40] companies in the world capable of making
[00:40:42] any of this are Samsung, Intel, and TSMC
[00:40:46] and like that's the actual bottleneck to
[00:40:49] all of AI and only Elon will talk about
[00:40:51] it.
[00:40:52] >> Alex, is it is it compute or is it
[00:40:54] energy? End of the day right now.
[00:40:56] >> I think they're indistinguishable at
[00:40:58] this point. I I think permitting for
[00:41:00] on-site energy is a major limiting
[00:41:02] factor. I think it's probably on balance
[00:41:05] more of a limiting factor at this point,
[00:41:07] maybe not a year from now than TSMC, but
[00:41:11] it is a limiting factor having powered
[00:41:13] land, having data centers that uh that
[00:41:16] you can take all of these, you know,
[00:41:17] infamously Microsoft even in the past
[00:41:20] few months spoke about having lots of
[00:41:22] GPUs that they'd love to to rack mount
[00:41:24] in a data center, but lacking the
[00:41:26] powered land and lacking the the data
[00:41:28] centers to plug them in. I I think at
[00:41:31] this moment energy at least in the US
[00:41:34] but I I agree with Dave that in the
[00:41:36] medium to long-term semiconductor
[00:41:38] fabrication supply chains doubly so if
[00:41:40] if there's any geopolitical conflict are
[00:41:42] likelier to be a strangle hold once we
[00:41:45] solve our energy story.
[00:41:46] >> So let's talk about the not investment
[00:41:48] advice segment here. Uh you know where
[00:41:51] do you where do you invest your capital?
[00:41:54] uh you know if compute and energy I mean
[00:41:57] I'm seeing the energy stocks beginning
[00:41:58] to fly right a a friend of mine uh just
[00:42:02] had this IPO of X Energy and it popped
[00:42:06] like 30% in in the first day uh we're
[00:42:10] seeing Bloom Energy and other energy
[00:42:11] stocks beginning to uh to you know
[00:42:14] skyrocket creep up over the time. So,
[00:42:17] you know, I don't know if you're going
[00:42:18] to invest in chips. Do you invest you,
[00:42:20] we saw Intel pop up and AMD, I mean, all
[00:42:23] of these guys, you know, that entire
[00:42:25] ecosystem of chips and energy. Uh,
[00:42:29] ultimately, if they're really the
[00:42:30] constraining part of the innermost loop
[00:42:32] here, uh, I think the most, you know,
[00:42:35] most demand is there. Any thoughts,
[00:42:37] Dave?
[00:42:38] >> Oh, to so many thoughts. I could go for
[00:42:39] an hour on just this topic, but but uh
[00:42:42] invest like crazy in anybody who has
[00:42:44] access to chips and can find a power
[00:42:45] supply. Uh that's that's you know pretty
[00:42:48] straightforward. There are power
[00:42:49] supplies everywhere. All these legacy
[00:42:51] manufacturing uh operations, aluminum
[00:42:53] melting and all that uses a huge amount
[00:42:55] of electricity and swapping it over to
[00:42:57] data center is a massive increase in the
[00:43:00] value of that energy supply. But you
[00:43:02] have to have a you know a line on the
[00:43:04] chips. Then at the kernel level, you
[00:43:06] know, because the chips are so
[00:43:07] constrained and the demand is is through
[00:43:09] the roof. Uh at the kernel level, anyone
[00:43:12] who's writing software at the kernel
[00:43:13] level that empowers, you know, AMD chips
[00:43:16] or or you know, legacy GPUs to
[00:43:18] participate uh or just makes the uh the
[00:43:21] inference more efficient on Nvidia
[00:43:23] chips. Uh those companies are worth a a
[00:43:26] fortune. So anyone who's building kernel
[00:43:28] level software is is a brilliant
[00:43:30] investment. And then in the vertical use
[00:43:32] cases, uh, Anthropic rolled out
[00:43:35] something called skills, which you
[00:43:37] should absolutely play with. Uh, it's
[00:43:39] just a way to use the the context window
[00:43:41] more efficiently by designing skills
[00:43:43] that the AI can then pull in. So rather
[00:43:46] than have to reinvent everything every
[00:43:48] time, just build a skill. Yeah.
[00:43:50] >> And then you can call on the skill very
[00:43:52] efficiently. So companies are now
[00:43:53] discovering they can refactor their
[00:43:55] entire business or their entire whatever
[00:43:57] they do around a hundred or a thousand
[00:44:00] different defined skills but those
[00:44:02] skills then become the defendable
[00:44:04] intellectual property
[00:44:05] >> within that vertical domain.
[00:44:08] >> So you know any vertical domain where
[00:44:09] you're racing to build out the entire
[00:44:11] skill database for that for that use
[00:44:14] case is also an unstoppable investment
[00:44:16] theme right now. You
[00:44:17] >> I could go forever. The other thing
[00:44:19] that's interesting is that both Google
[00:44:21] and and uh Amazon are getting their
[00:44:25] shares in Enthropic at one-third the
[00:44:27] going rate. I find that extraordinary.
[00:44:31] You know, three $350 billion valuation
[00:44:32] versus the trillion dollar valuation.
[00:44:35] >> Well, it shows you how important the
[00:44:36] compute is. I mean, again, you're going
[00:44:38] to you're going to be sold out for
[00:44:40] forever
[00:44:41] >> if you can get the compute.
[00:44:42] >> And these hyperscalers are kind of
[00:44:44] hedging their bets, right? They're not
[00:44:45] picking a winner. uh they're buying
[00:44:47] every horse in the race, you know,
[00:44:48] because this, you know, AGI ASI race is
[00:44:51] just way too important to lose. So,
[00:44:53] they're just investing left, right, and
[00:44:55] center.
[00:44:56] >> I would also just parse these as the
[00:44:58] market doing what the market does. Some
[00:45:00] of the participants, some of the
[00:45:02] frontier labs like Anthropic have an
[00:45:04] insatiable hunger for the compute and
[00:45:06] they have the revenue generation to to
[00:45:09] generate the demand and sustain the
[00:45:11] demand. And so if you're anthropic,
[00:45:13] you're going to go to every possible
[00:45:15] source at scale of compute that you can
[00:45:17] find, whether it's Amazon or whether
[00:45:19] it's Google or whether it's other
[00:45:21] sources, you're just going to to go and
[00:45:24] seek as a a hungry customer uh for
[00:45:27] compute, whatever the market will
[00:45:29] provide. I I don't think necessarily the
[00:45:31] story needs to be any more complicated
[00:45:34] than that. It turns out there the world
[00:45:36] demands a lot of compute to solve some
[00:45:38] of these really interesting problems in
[00:45:41] code generation and otherwise. And what
[00:45:43] we're going to see over time is all of
[00:45:45] this demand is going to translate into
[00:45:47] supply. It's going to translate in the
[00:45:50] short term into what looks superficially
[00:45:53] like a bit of a circular economy between
[00:45:56] call it the the top 10 or 12 companies
[00:45:58] after we see the IPOs of SpaceX and
[00:46:01] OpenAI and and Anthropic. But that's
[00:46:04] going to diffuse throughout the economy
[00:46:05] over the next few years would be my
[00:46:07] prediction.
[00:46:07] >> People are hungry for compute. See was
[00:46:09] hungry for bandwidth. Sem, welcome back.
[00:46:12] I see you're in a stationary from the
[00:46:14] from the airport now in a stationary
[00:46:16] spot. So let's see.
[00:46:18] >> Dude, I'm just going to call
[00:46:19] [clears throat] you Waldo from now on.
[00:46:20] All right. Uh let's move on. A couple of
[00:46:23] fun stories. I'm gonna add this segment
[00:46:26] every time for the podcast, which is
[00:46:27] what did Claude just kill? Uh so this is
[00:46:31] the stock chart for eBay. Uh and uh this
[00:46:35] comes out from Anthropic Research.
[00:46:36] There's a new anthropic research project
[00:46:38] deal. Uh we created a marketplace for
[00:46:41] employees in our San Francisco office
[00:46:43] with one big twist. We tasked Claude
[00:46:46] with buying, selling, and negotiating on
[00:46:48] our colleagues behalf. Basically doing
[00:46:51] what eBay does. And we see a drop in the
[00:46:54] stock price. You know, I think this is,
[00:46:56] you know, eBay is not really dropped
[00:46:58] anywhere beyond this, but I I think this
[00:47:01] is going to be more and more common. Um,
[00:47:03] any thoughts, Dave?
[00:47:05] >> Well, I think a lot of this is just uh,
[00:47:07] you know, immediate knee-jerk fear
[00:47:08] reaction, but then things kind of settle
[00:47:10] out and you realize, wait, Anthropic is
[00:47:13] going to build all kinds of marketplaces
[00:47:14] because they can, but it's not going to
[00:47:15] hurt eBay. You know, like I think what
[00:47:18] you're going to see more and more is AI
[00:47:19] is growing so quickly that it's going to
[00:47:21] largely grow around the legacy economy.
[00:47:23] So around the banks, around the
[00:47:24] insurance guys, it's just it's going to
[00:47:26] be its own world and it's going to be
[00:47:28] feeding on itself and building just you
[00:47:31] know colossally large constructs that
[00:47:33] that some people are not even aware of
[00:47:35] >> and it'll all happen very very quickly.
[00:47:37] So I think eBay will be fine.
[00:47:40] >> Any thoughts here?
[00:47:41] >> I have a slightly different take. You
[00:47:43] know, there's so many places because
[00:47:46] lots of problems in companies exist
[00:47:48] because coordination is hard and AI
[00:47:50] makes coordination easy and that's going
[00:47:53] to threaten big chunks of places.
[00:47:55] Marketplaces, customer support, uh
[00:47:57] listing optimization, dispute handling.
[00:48:00] There's huge categories of these that
[00:48:02] will become agentic workflows. And I
[00:48:04] think the bigger question about what the
[00:48:06] what did the AI just kill is what
[00:48:08] workflow category did it just encompass
[00:48:12] encompass and automate.
[00:48:13] >> You want to hear something cool like
[00:48:14] related to this? Uh the the data center
[00:48:17] CEO that I met with this morning, you
[00:48:19] know, we were talking about data centers
[00:48:20] going into space because power is
[00:48:22] basically free. You know, solar is
[00:48:24] basically free in space. And he said,
[00:48:26] "Data centers there there's power all
[00:48:28] over the planet that's not tapped that
[00:48:31] doesn't disrupt society at all. That's
[00:48:34] not why data centers are going to space.
[00:48:35] Data centers are going to space because
[00:48:37] because there's no regulatory authority
[00:48:40] preventing it. You try to do anything. I
[00:48:43] mean, that's not true. You still have to
[00:48:45] if you're going to be flying all these
[00:48:46] data centers and communicating, you need
[00:48:49] licensing, you know, domestically and
[00:48:51] the ITU for bandwidth. I mean, there are
[00:48:54] going to be regulatory hurdles that, you
[00:48:57] know, Elon and Google need to get. Um,
[00:49:00] especially if you're launching 500,000
[00:49:03] satellites. I mean, when you're putting
[00:49:04] up a debris field like that, there's
[00:49:06] going to be push back. There is going to
[00:49:08] be push back.
[00:49:09] >> Yeah, it's interesting. I'll square the
[00:49:12] circle.
[00:49:12] >> Doing anything on land. Sorry,
[00:49:14] [laughter] go ahead, Alex. I I'll square
[00:49:16] the circle here and and and say I think
[00:49:18] in the short term for suns synchronous
[00:49:19] orbit, yeah, that requires FCC and and
[00:49:22] other approvals. In the long term, if we
[00:49:24] start to say launch AI data centers from
[00:49:28] the moon, that will probably and and
[00:49:30] we're building them on the moon, that
[00:49:32] will probably require fewer approvals,
[00:49:34] at least under the current regulatory
[00:49:36] regime. To go back,
[00:49:37] >> that's 20 years away to to actually get
[00:49:39] manufacturing on the moon.
[00:49:41] >> I'm talking about
[00:49:42] >> 20 years away, Peter. um you know to get
[00:49:45] listen it if you look at it deeply I
[00:49:48] mean I know 20 years away is infinity I
[00:49:50] get that but we're talking about I mean
[00:49:52] just to be to to be clear the stuff I'm
[00:49:55] concerned about is the next 5 years
[00:49:57] right if you're launching we talked to
[00:49:59] Elon about this you know 500,000
[00:50:02] uh you know V3
[00:50:05] uh
[00:50:07] you know satellites in a constellation
[00:50:10] there's going to be debris issues you
[00:50:12] know Elon pushed it off by saying, "Oh,
[00:50:14] you know, we'll have super intelligence
[00:50:16] to figure that out." I just I you know,
[00:50:18] we have this everything everything looks
[00:50:21] amazing from far away, but the reality
[00:50:23] is by the time it comes closer, there
[00:50:25] are real issues and so it's not going to
[00:50:28] be just the, you know, the promised land
[00:50:32] of going to space. We're going to have
[00:50:34] challenges going there still.
[00:50:36] >> Yeah. It's interesting how the timelines
[00:50:38] line up too because between here and
[00:50:39] there you there's all kinds of
[00:50:41] constraints but between here and there
[00:50:42] we'll have solved all math and we'll
[00:50:45] have discovered all kinds of new
[00:50:46] physics. And so
[00:50:48] >> listen I'm the space cadet. I'm the
[00:50:50] super space enthusiast here and I I can
[00:50:52] hope for nothing more than that vision
[00:50:54] to happen. But it's always uh it's
[00:50:57] always you know easier on the promised
[00:51:00] land. Peter, I'm gobs I'm gobsmacked to
[00:51:02] to hear that you think it's going to be
[00:51:04] 20 years before we have fabs on the
[00:51:06] moon. My goodness.
[00:51:07] >> Fabs on the moon manufacturing
[00:51:09] [clears throat] and pumping into Earth
[00:51:11] orbit with mass drivers.
[00:51:13] >> You think that's 20 years away?
[00:51:15] >> Well, okay. Maybe 15, but it's not the
[00:51:17] next 5 years.
[00:51:18] >> Do I hear 10?
[00:51:20] >> It's hard for me to It's hard for me. I
[00:51:22] guess Optimus robots will improve that.
[00:51:25] uh demand will improve that but uh you
[00:51:28] know the the concern is if you have a uh
[00:51:32] you know an in a I not an explosion but
[00:51:35] a collision of spacecraft in orbit
[00:51:37] generating debris we still don't have
[00:51:39] any mechanism for removing debris from
[00:51:41] orbit and so it's it's going to be a
[00:51:43] challenge
[00:51:44] >> I'll make two your concern is your
[00:51:48] briefly your concern is Kesler syndrome
[00:51:50] is going to sabot
[00:51:52] >> is going to to sabotage moonbased fabs
[00:51:55] No, it's going to it's going to sabotage
[00:51:58] uh the next 5 years of 500,000
[00:52:01] satellites in Earth orbit. I mean, right
[00:52:03] now we have 10,000 satellites from
[00:52:04] Starlink, right, which is the most ever
[00:52:06] pumped into orbit ever. And we're
[00:52:09] talking about 50 times that. And we're
[00:52:12] talking about not just the US, you know,
[00:52:14] Amazon's going to do their best, right?
[00:52:16] Uh Jeff is not going to stand still
[00:52:17] while while, you know, Elon's doing
[00:52:19] this. And then you've got Chinese
[00:52:20] constellations. So, do you double or
[00:52:23] triple that number of satellites in
[00:52:24] orbit? Um, and it I mean listen, I I
[00:52:28] can't wait and it's going to have
[00:52:30] challenges. See, you were going to say,
[00:52:32] >> yeah, I'll I'll give a couple of
[00:52:33] thoughts here with with just finger in
[00:52:35] the air here. I think humanoid robots
[00:52:37] are five to seven years away minimum at
[00:52:40] in in mass at mass scale uh in
[00:52:44] widespread adoption. Okay. Minimum. And
[00:52:47] I think
[00:52:47] >> I don't agree with that, but that's
[00:52:48] okay.
[00:52:48] >> I agree. I agree. I I understand. And I
[00:52:51] think a fab lab on the moon and
[00:52:55] consistently doing fabrication and all
[00:52:58] that stuff is 15 years away minimum.
[00:53:00] >> So I'll say that not that it's not
[00:53:02] coming. It's just a question of it's a
[00:53:04] when not an if which is
[00:53:05] >> Oh my goodness. This is lunacy. Utter
[00:53:07] lunacy here.
[00:53:08] >> Well, we are in the Moonshots podcast.
[00:53:11] >> Yes. Can we get get back just maybe to
[00:53:13] project deal and anthropic? I I I think
[00:53:15] we're we're missing an important point.
[00:53:17] everyone who hand rings over the the
[00:53:19] latest Anthropic project purportedly
[00:53:22] sabotaging or or or killing some SAS
[00:53:25] company, Anthropic doesn't want to to be
[00:53:28] triggering SAS apocalypses left and
[00:53:31] right. There there's relatively little
[00:53:33] economic motivation there. I think if
[00:53:34] you look through the through line
[00:53:36] through all of these anthropic projects
[00:53:38] or research projects other than the
[00:53:40] alignment ones anthropic is can all of
[00:53:43] their projects can be explained by and
[00:53:46] corporate strategies and unhoblings can
[00:53:48] be explained by very simple principle
[00:53:50] they're trying to maximize the economic
[00:53:53] value per token
[00:53:55] >> that's all that they're trying to do
[00:53:56] that claude code it turns out through
[00:53:59] claude codegen is actually quite
[00:54:02] economically valuable per token. Turns
[00:54:04] out per token it's more valuable to
[00:54:06] generate useful working code than say to
[00:54:09] generate video or cat images or whatever
[00:54:12] other consumer plays OpenAI and some
[00:54:14] other frontier model providers were
[00:54:17] chasing. They've dropped that now.
[00:54:19] Everyone's focusing on codegen because
[00:54:21] on a per token basis it's so
[00:54:23] economically valuable. So I would look
[00:54:26] at projects like project deal running a
[00:54:28] marketplace running a business as
[00:54:30] anthropic looking for new ways to
[00:54:32] increase the per token economic value of
[00:54:35] their output. It's as simple as that.
[00:54:37] >> Brilliant, Alex. That's absolutely
[00:54:39] brilliant.
[00:54:40] >> Um to move us along here,
[00:54:43] we're we're coming into the battle
[00:54:45] season. Uh it's Elon versus Sam and Open
[00:54:48] AI. Uh this just got posted today. So
[00:54:52] today is the start of a very important
[00:54:54] day in the AI world. The trial between
[00:54:56] Elon and Sam and OpenAI begins in the
[00:54:59] Oakland Federal Court. The jury
[00:55:00] selection is happening right now. So I
[00:55:04] just put this up to keep us posted. Uh
[00:55:06] we'll be learning a lot. Of course, uh
[00:55:08] you know, Discovery is unveiling a lot
[00:55:11] of texts, a lot of emails that I bet
[00:55:14] both Elon and Sam and a lot of other
[00:55:16] people uh would rather not have aired in
[00:55:19] the public. Any thoughts here, Jent?
[00:55:23] >> I think it's it's sort of sad that it's
[00:55:25] come to this. It's going to make I I
[00:55:27] just one remembers the Bill Gates versus
[00:55:29] Steve Jobs docu dramas that were made
[00:55:32] from critical Apple versus Microsoft
[00:55:34] era. This has I think a similar feel to
[00:55:36] it. It it's sort of sad that I I think
[00:55:38] this ended up in court versus settling
[00:55:40] earlier on, but I I do think many will I
[00:55:44] think history will probably view this as
[00:55:46] sort of an iconic struggle that will get
[00:55:49] the the full uh Aaron Sorcin if not
[00:55:53] similar uh like movie treatment. This
[00:55:55] will this will be the the full Hollywood
[00:55:58] type totally titanic battle.
[00:56:00] >> Yeah.
[00:56:01] See, any thoughts here? How's this
[00:56:04] playing in Guadalajara?
[00:56:06] uh no recognition awareness uh at all
[00:56:09] and that's probably a good thing. Uh
[00:56:11] this is kind of soap operation. I'm with
[00:56:13] Alex on this one. Uh it's just heavy
[00:56:16] drama. We wish it hadn't come to this.
[00:56:19] It would have been great to get these
[00:56:20] guys to settle off thing, but their
[00:56:22] positions are hard and baked in and so
[00:56:24] it's going to come.
[00:56:25] >> How does this how do you unravel the the
[00:56:28] you know the movement of open AI to a
[00:56:30] for-profit company? I mean do you like
[00:56:32] back it up to a nonprofit? And what
[00:56:34] about all the capital invested in open
[00:56:36] AI? Does that disappear if they lose the
[00:56:38] case here?
[00:56:39] >> I'd like to do it more. I mean, I I've
[00:56:41] said I think on the pod in past that I
[00:56:43] if the model of changing nonprofits,
[00:56:46] large nonprofits to public benefit
[00:56:49] corporations can be scaled. I'd love to
[00:56:51] do this to a number of major American
[00:56:52] research
[00:56:52] >> unities. My question my question is how
[00:56:55] you know what happens to all the capital
[00:56:57] invested you know literally hundreds of
[00:56:59] $122 billion in the last couple of
[00:57:01] months. Uh, you know, there's so much
[00:57:03] pressure for this court case not to be
[00:57:06] won by Elon.
[00:57:07] >> Well, I mean, if if you're following the
[00:57:10] the detailed Tik Tok of the way that
[00:57:12] this trial is being structured, it's
[00:57:14] it's being structured in two phases. the
[00:57:16] the first phase is more of deciding uh
[00:57:19] whether the the claims that uh Elon at
[00:57:22] all have made uh are in fact the case
[00:57:24] and the second is is the equivalent of
[00:57:28] um like an a reward type section uh
[00:57:31] deciding what awards if any to to make
[00:57:33] as conditioning on the first phase. But
[00:57:36] I I think there there are a number of
[00:57:38] details in this uh in this court case
[00:57:41] that are notable. One is so jury
[00:57:44] selection. Uh there's been public
[00:57:46] reporting that already selected members
[00:57:49] of the jury are aware of entanglements
[00:57:53] that Elon's had with the present
[00:57:55] administration and may view him
[00:57:56] negatively as a result. I think that's
[00:57:59] the fact that jury members are being
[00:58:01] selected um reportedly with uh with some
[00:58:05] political influence seeping in. I think
[00:58:08] that's very interesting. I also think
[00:58:10] it's interesting that the the the
[00:58:12] district judge in this case um has uh
[00:58:15] again reportedly decided that uh she's
[00:58:18] going to take the the jury uh the jury
[00:58:21] outcome uh as an advisory opinion, but
[00:58:24] that if there is an award, she's going
[00:58:26] to decide ultimately from the bench on
[00:58:28] the final award. So, there are a lot of
[00:58:30] nuances here.
[00:58:31] >> Wow. Dave, any thoughts, opinions here?
[00:58:34] >> Yeah. Do we ever figure out if we get to
[00:58:36] see it live? It's not it's not being
[00:58:38] broadcast, but I'm sure they're going to
[00:58:39] be sort of court reporters giving us uh
[00:58:42] a lot of details here.
[00:58:43] >> You you can wait for the full Hollywood
[00:58:45] treatment in a couple years.
[00:58:46] >> By the way, there will be a Hollywood
[00:58:48] treatment of this as with every other
[00:58:51] major uh of course it may be an AI
[00:58:53] generated feature film, but nonetheless,
[00:58:55] >> it will be for sure.
[00:58:56] >> Well, I'm surprised how many uh texts
[00:58:59] like personal texts have already come
[00:59:01] out.
[00:59:01] >> Yeah. you know, the emails get
[00:59:03] discovered right away and everyone all
[00:59:04] your email gets thrown out there for the
[00:59:06] wild to to read, which is crazy, but it
[00:59:09] happens. But texts traditionally have
[00:59:11] not been thrown out, but yet we're
[00:59:13] seeing them all. So, I don't know
[00:59:14] exactly how that's happening, but you
[00:59:16] know, for Elon to win, uh, he doesn't
[00:59:18] have to win the case. He just has to
[00:59:20] slow down Open AI. I mean, in the in
[00:59:22] this middle of the singularity, if you
[00:59:24] lose three months, you know, you're
[00:59:26] basically you lost.
[00:59:27] >> You're correct.
[00:59:28] >> Correct. Yeah.
[00:59:29] >> All right. Another fun topic. a few
[00:59:31] stories here. It's about AI surveillance
[00:59:33] and privacy. Uh so let's check this out.
[00:59:36] OpenAI's Chronicle uses agents to build
[00:59:40] uh memories from screenshots. So Sale
[00:59:42] Alman described this one as telepathy
[00:59:45] like so Chronicle uh runs on OpenAI's
[00:59:48] codecs uh where background agents are
[00:59:51] taking periodic snap snapshots of
[00:59:53] everything on your screen. The
[00:59:55] screenshots are sent OpenAI's uh servers
[00:59:57] for processing. agents use optical
[01:00:00] character recognition and visual
[01:00:01] analysis to extract the context of what
[01:00:03] you're doing every minute on your
[01:00:05] screen. Structured memory files are
[01:00:07] created and stored locally. Uh, and you
[01:00:11] know, we talked about this before, AI
[01:00:14] monitoring everything. Uh, ultimately
[01:00:16] it's sort of the camel's nose under the
[01:00:19] tent of being able to replace any
[01:00:22] worker. uh you know we have significant
[01:00:25] privacy concerns that come up on this
[01:00:28] and no one's raising that. I don't know
[01:00:30] if you guys remember when I was
[01:00:31] researching this. So Microsoft uh had
[01:00:34] launched something uh uh recently called
[01:00:37] recall. It was a product that they they
[01:00:40] put out there and then they retracted
[01:00:42] because all the cyber security people
[01:00:43] said this is a privacy not nightmare.
[01:00:45] It's litigation bait and uh they pulled
[01:00:48] it back. But when OpenAI announced uh
[01:00:51] this product uh no one no one's pushed
[01:00:54] back. Uh
[01:00:56] >> can can I can I first of all point out
[01:00:58] what a beautiful double entandra from
[01:00:59] Microsoft's crack product marketing
[01:01:01] department naming a feature recall
[01:01:04] >> and then recalling it.
[01:01:06] >> Nice.
[01:01:07] >> I I I think what we're seeing here is
[01:01:09] one big architectural cluge. uh and I I
[01:01:12] think it's going to to be cluji both
[01:01:14] from Microsoft's uh perhaps
[01:01:17] illarchitected recall as well as OpenAI
[01:01:19] Chronicle. This wants to be built into
[01:01:21] the operating system and the hardware.
[01:01:23] It doesn't want to be an add-on. I don't
[01:01:25] think I'll just speak for myself. I
[01:01:27] don't want an agent taking constant
[01:01:29] screenshots of my desktop, sending it to
[01:01:32] a server, and then parsing it, sending
[01:01:34] back results. This should all be built
[01:01:37] Apple style. I I' I would hope that
[01:01:39] Apple will get its act together in the
[01:01:41] next few months and build this into the
[01:01:42] window manager and the compositor and
[01:01:44] the operating system. The operating
[01:01:46] system is rendering the screen. Why
[01:01:48] can't the operating system understand
[01:01:50] what it's rendering? I mean, this is
[01:01:52] this is ambient AI is the term of art
[01:01:54] here where AI is monitoring everything
[01:01:56] all the time
[01:01:58] >> and enabling you, right? This is in one
[01:02:00] sense this is what I did this past
[01:02:02] weekend with with with uh my open claw
[01:02:05] with Skippy where I gave it access to
[01:02:07] everything right every single uh granola
[01:02:10] gets put into memory every WhatsApp
[01:02:12] message every email every calendar
[01:02:14] everything and it just makes it so much
[01:02:16] more useful uh and I think something
[01:02:19] like Chronicle as well uh would just
[01:02:22] enable it to be like Sam said telepathy
[01:02:25] like
[01:02:26] >> well that's the quandry I mean a lot of
[01:02:28] people who get in trouble with AI you
[01:02:29] know, or they get stuck. It's something
[01:02:31] they're doing on screen. The AI doesn't
[01:02:33] have visibility into it.
[01:02:34] >> Yeah.
[01:02:34] >> But if you unlock that, the AI can be
[01:02:36] incredibly helpful, but it's also seeing
[01:02:38] literally every mouse move. So, but when
[01:02:41] we talk about our moms are still not
[01:02:42] using AI, why not? This this is a big
[01:02:45] unlock, a big part. The voice interface
[01:02:47] and this are the two big unlocks because
[01:02:49] it can then say, "Oh, I see what you're
[01:02:50] doing wrong. In fact, let me just do it
[01:02:52] for you and save you the trouble." and
[01:02:54] that you know all these configuration
[01:02:56] screens on any Apple device and you know
[01:02:58] the menus are ridiculous now like you
[01:02:59] know the number of layers of of of
[01:03:02] configuration you can do I think
[01:03:04] something like some crazy stat like 70
[01:03:07] 80% of all iPhone users never change any
[01:03:09] defaults
[01:03:10] >> just [laughter] it's just too confusing
[01:03:12] to to do anything
[01:03:14] >> this is a huge unlock for all of that
[01:03:16] but you said it's hugely intrusive
[01:03:19] >> right now you know I take screenshots
[01:03:21] and I send it to uh to Claude or
[01:03:23] whomever and say, "Hey, can you please
[01:03:25] help me figure this out?" Uh, but this
[01:03:27] is going to have sort of a uh, you know,
[01:03:30] sort of an expert over your shoulders,
[01:03:32] always there to support you if you need
[01:03:34] it.
[01:03:34] >> Well, and most people when they first
[01:03:36] start playing with AI, like like Alex's
[01:03:38] standard first query, you know, to test
[01:03:39] a new model is, "Build me a firsterson
[01:03:42] shooter." It's it's a better prompt than
[01:03:43] that. Sorry. Sorry to [laughter]
[01:03:46] but but people want to do something
[01:03:47] visual and graphical to learn how it all
[01:03:49] works. And then when it doesn't work,
[01:03:52] they want to show the AI, hey,
[01:03:54] >> this doesn't look right to me. Fix it.
[01:03:56] So, they screenshot it, just like Alex
[01:03:58] or just like Peter, you just said. Yeah.
[01:04:00] >> Uh they screenshot it. But here, this is
[01:04:02] just a much more convenient way to get
[01:04:04] video, not just a screenshot back into
[01:04:06] the AI's brain and say, "Look, this
[01:04:08] doesn't look right. Fix it for me." And
[01:04:10] so, you have a much more fun dialogue
[01:04:12] with the AI.
[01:04:13] >> But you have to accept that
[01:04:14] [clears throat] privacy is, you know,
[01:04:15] being compromised there. I think I don't
[01:04:17] I I I I'll take a very different
[01:04:19] position here, Peter, on that, which is
[01:04:22] I think any loss of privacy here is just
[01:04:26] due to this being an architectural
[01:04:28] atrocity. This wants to be built into an
[01:04:30] operating system like Mac OS. It wants
[01:04:32] to take advantage of the secure enclave.
[01:04:35] It wants to have secure hardware that's
[01:04:37] cryptographically guaranteeing that as
[01:04:39] it captures pixels that come out of the
[01:04:41] compositor and the window manager and
[01:04:43] the renderer that all of those are
[01:04:45] securely handled and kept local. The
[01:04:47] reason that this is one big privacy
[01:04:50] dumpster is because it's not being baked
[01:04:53] into the hardware and the local
[01:04:54] operating system. But that can be fixed.
[01:04:56] >> It will and it will be fixed and I want
[01:04:58] that. You know, I've often said, I'm
[01:04:59] going to give up everything, every piece
[01:05:01] of detail because I want my AI systems
[01:05:04] to be that much powerful. See, you're
[01:05:06] back with us. Talk to me about what do
[01:05:07] you think about this? I think this is a
[01:05:10] I agree with Alex. Two other things
[01:05:11] though. One is that this is going to
[01:05:13] cause massive privacy issues for
[01:05:15] workers, worried about big brother
[01:05:17] watching over them. Already today,
[01:05:19] there's a crazy statistic that 44% of
[01:05:22] Gen Z workers are sabotaging AI's
[01:05:25] efforts to automate their own work.
[01:05:27] they're putting in the wrong data, um
[01:05:29] throwing off the AI training. It's
[01:05:31] really crazy what's happening right now
[01:05:33] in in workplaces. So, I think this will
[01:05:35] just exacerbate it and bring this whole
[01:05:37] conversation to the front.
[01:05:39] >> Oh, talk about a losing battle. You're
[01:05:41] far far better getting on the wagon than
[01:05:43] you are trying to trying to do that.
[01:05:45] That's such poisonous behavior.
[01:05:46] >> Protect your job. All right. Uh here's
[01:05:48] our our next story. Uh basically, World
[01:05:52] ID verification integration into Zoom.
[01:05:55] uh and uh here it is. So the backstory I
[01:05:59] think that's important here. So in 2024
[01:06:01] engineering firm called AUP uh AU lost
[01:06:05] 25 million after an employee in Hong
[01:06:07] Kong authorized a series of wire
[01:06:09] transfers during what appeared to be a
[01:06:11] routine video call with the company's
[01:06:13] CFO and several colleagues. The problem
[01:06:15] is that everyone on the call except the
[01:06:18] victim turned out to be an AI generated
[01:06:20] deep fake. uh we've seen similar attacks
[01:06:23] in multinational firms in Singapore. Uh
[01:06:26] and the the impact of this is huge,
[01:06:30] right? So what we saw in 2019 to 2023
[01:06:34] was $130 million in losses due to deep
[01:06:37] fakes. 2024 was 400 million. 2025 last
[01:06:40] year it was a billion. It's projected to
[01:06:43] reach $40 billion by 2027.
[01:06:46] And so step in uh our friend Sam uh with
[01:06:51] his device called the Orb that takes a
[01:06:53] photo of the back of your retina and you
[01:06:56] verify on Zoom that you're an actual
[01:06:59] human. Uh it uses world ID and a real
[01:07:01] time face authentication from a selfie
[01:07:04] as well as video and it says yes. Yay
[01:07:07] verily this person is a human. Uh so and
[01:07:11] you get a verified human uh human badge
[01:07:13] on your on your Zoom link. Did you just
[01:07:16] say yay barely? That's fantastic. We're
[01:07:18] right back in Shakespeare here. That's
[01:07:20] awesome.
[01:07:20] >> Yay barely. You're a human.
[01:07:22] >> Uh you still you still have to go you
[01:07:25] still have to go and actually scan your
[01:07:27] eyeball in one of these orbs.
[01:07:30] >> Has anybody done it? Have you guys done
[01:07:32] this yet?
[01:07:32] >> No. No. Apparently it's bouncing all
[01:07:35] over Africa. People are scanning away.
[01:07:37] But um I haven't done it yet. I love it
[01:07:38] because uh you know I was on I don't
[01:07:40] know if I told you Peter but I was on
[01:07:41] stage uh here at a companywide meeting
[01:07:44] and we took a little fiveminute break in
[01:07:46] the middle and our controller came up to
[01:07:47] me and said Dave I'm so sorry I only got
[01:07:49] half of those wire transfers to China
[01:07:51] out. I'll get the other out right away.
[01:07:53] >> Seriously, what are you talking about?
[01:07:55] And then so I got back on stage. I'm
[01:07:56] like I wonder what she was talking
[01:07:57] about. And so then the whole second half
[01:07:59] of the company meeting in the back of my
[01:08:01] mind I'm like wait a minute. [laughter]
[01:08:03] So, I got off. When I got off, she said,
[01:08:05] "Okay, I got $300,000 out." And I like,
[01:08:08] "What are you doing?" She's like, "Well,
[01:08:10] you told me it was an emergency and we
[01:08:11] got to get the money to China right
[01:08:13] away." Like, why would we be be wiring
[01:08:15] money to China? I don't understand. So,
[01:08:18] anyway, only about 75,000 got across the
[01:08:21] border. We never got that back. Then the
[01:08:22] rest of the FBI got into it right away.
[01:08:25] >> But I'm like, man,
[01:08:27] >> digital transfers like this, you know,
[01:08:30] everything should be logged anyway. I I
[01:08:32] really feel like the the digital fraud
[01:08:34] world is going to get solved and this is
[01:08:36] a big part of it. But everything should
[01:08:38] be logged all the time. It shouldn't be
[01:08:41] that hard to deal with digital stuff.
[01:08:43] I'm much more worried about chemical,
[01:08:44] biological, radiological.
[01:08:46] >> Yes.
[01:08:46] >> Stuff than I am about digital stuff
[01:08:48] because I think we're going to get it
[01:08:49] fixed. And this is this is part of it.
[01:08:51] >> Yeah. Uh Alex, any thoughts here?
[01:08:55] >> This is Minority Report. This is the
[01:08:57] sci-fi future that we're catching up
[01:08:59] with. Apple with its Face ID was focused
[01:09:02] on the face, not on the retina. But if
[01:09:04] you remember the Tom Cruz Steven
[01:09:06] Spielberg Minority Report division, this
[01:09:09] is it. I I think it's been interesting
[01:09:10] to watch as world evolved from world
[01:09:14] coin and it's been interesting to watch
[01:09:16] as the company bounced back and forth
[01:09:19] between more cryptofocused
[01:09:21] and the economics of it versus the
[01:09:24] identification of human as a human side
[01:09:27] of it. But it seems you know from uh
[01:09:30] from a distance like the the human
[01:09:33] identity verification side is ultimately
[01:09:36] the bigger seller than uh the crypto
[01:09:38] side. And to the extent that's the case
[01:09:41] uh as resident cryptobear I'm I'm very
[01:09:43] supportive.
[01:09:44] >> We will have that debate sim don't worry
[01:09:46] about it.
[01:09:47] >> There's a wild there's a wild irony here
[01:09:49] that the more AI scales the more
[01:09:51] valuable verified human identity
[01:09:53] becomes. This is kind of interesting.
[01:09:55] >> Yeah.
[01:09:57] >> Yeah. No. So, here's this next story
[01:09:58] that's related. So, uh, Grock creates a
[01:10:01] realistic AI French woman with a
[01:10:03] reflective ID. I'm going to play this
[01:10:05] little video here and take a look at it
[01:10:08] very carefully as she holds her driver's
[01:10:11] license up to the camera. Look how
[01:10:12] beautiful and real this looks.
[01:10:26] So this was posted and it went viral by
[01:10:28] this uh gentleman Dr. David Lutke. Uh he
[01:10:32] says this AI French woman was created by
[01:10:34] Grock uh complete with perfectly
[01:10:37] reflective ID a few more months and
[01:10:39] video ID verification may no longer be
[01:10:42] reliable. So I mean how many times have
[01:10:44] you taken you know a picture of your
[01:10:45] license or your passport and uploaded
[01:10:47] it? Um, it is going to become more and
[01:10:51] more difficult. We're going to have
[01:10:51] white hat, black hat competitions up the
[01:10:53] wazoo here,
[01:10:56] Alex or
[01:10:57] >> Well, I I I would maybe just comment the
[01:11:00] the IDs themselves should be verifiable
[01:11:03] with a centralized database that that's
[01:11:05] how you can maintain a single source of
[01:11:08] truth and whether people are flashing
[01:11:10] IDs or not maybe less of a
[01:11:15] >> centralized database, not a blockchain,
[01:11:17] but [laughter] good one, Peter. Good
[01:11:18] one.
[01:11:18] >> I'm just poking you, buddy. I'm just
[01:11:20] poking you. I I also think you know
[01:11:22] there are so many other technologies
[01:11:24] that we have to bring to bear. We can do
[01:11:26] hardware level cryptography for example
[01:11:28] chain of custody for video that we it's
[01:11:31] not that as a civilization we lack the
[01:11:33] technologies to ensure that any video or
[01:11:36] images actually originated from the real
[01:11:39] world without tampering. It's just that
[01:11:41] we lack the demand for it right now. And
[01:11:43] if I would predict that if ever this the
[01:11:46] situation of deep faking gets so bad
[01:11:48] that it's causing real problems at a
[01:11:50] societal level that'll just unlock all
[01:11:53] of these technological solutions
[01:11:54] including hardware level crypto for
[01:11:57] cameras cryptography not not
[01:11:58] cryptocurrencies that that uh the market
[01:12:01] will will speak for itself and we'll get
[01:12:03] all those tech. I'm still waiting for
[01:12:04] the laws to come out that require all
[01:12:08] you know Grock and every other video
[01:12:10] generation to really uh identify it as
[01:12:13] AI generated. Um it's a bill work I I
[01:12:16] covered in uh in my newsletter innermost
[01:12:19] loop. There is a bill right now
[01:12:20] bipartisan bill working its way through
[01:12:22] the house that will cover elements of
[01:12:24] deep fake uh fingerprinting like that.
[01:12:27] >> Yeah. Yeah. All right. Uh let's move
[01:12:30] ourselves along here. Uh we're going to
[01:12:31] talk about the economic impact of AI.
[01:12:34] There's a lot going on. Token maxing. Uh
[01:12:38] word of the year. So this is from a
[01:12:40] report from 404media.co.
[01:12:43] Startup CEOs who are token maxing are
[01:12:46] bragging that they are spending more
[01:12:48] money on AI compute than it would cost
[01:12:50] to hire human workers. Astronomical AI
[01:12:53] bills are now in a certain corner of the
[01:12:55] tech world supposed to be the marker of
[01:12:58] growth and success. Look how much I'm
[01:12:59] spending on my tokens. Everybody, you
[01:13:01] should invest in me so I can spend more
[01:13:03] on tokens. Dave, come.
[01:13:05] >> No, this is this is this is a warped
[01:13:07] story. This is a great thing. The the
[01:13:10] way you get left behind is by not
[01:13:12] trying. That's the worst thing you can
[01:13:14] do right now is not get in the race, not
[01:13:16] play with AI, not try. And token maxing
[01:13:20] is fine. Like, you know, a CEO that's
[01:13:22] proud of the fact that they're consuming
[01:13:23] a ton of tokens. you can come and
[01:13:25] optimize it later in the year,
[01:13:27] >> but get every one of your people on
[01:13:29] their AI platform like now, like
[01:13:31] yesterday, and go ahead and start
[01:13:33] burning the tokens, and then you'll
[01:13:34] you'll have no trouble making it more
[01:13:36] efficient later if you get in the game
[01:13:38] now. So, I think it's great when a when
[01:13:41] a startup CEO says, "I burned, you know,
[01:13:43] three million of money on on compute."
[01:13:47] Uh, fine. You're learning a ton along
[01:13:49] the way. And, you know, nobody nobody
[01:13:50] incinerates money for very long. you
[01:13:53] know, they're they're not that
[01:13:54] irrational. So, it's uh so this is just
[01:13:57] sort of the backlash story.
[01:13:58] >> What was the Jensen factor? It was like
[01:14:00] half your salary in tokens. Um
[01:14:02] >> I I'm saying yeah, I'm saying you're
[01:14:04] full like I'm telling everybody by end
[01:14:06] of year. So, you have, you know, you
[01:14:07] have nine months 50/50 is a good target.
[01:14:10] Half payroll, half token use. And then
[01:14:12] again, you're not going to have you're
[01:14:14] not going to have any trouble optimizing
[01:14:15] it. You know, the token use is
[01:14:17] effectively about a 10x force
[01:14:18] multiplier. So if you're at
[01:14:19] [clears throat] one, it's like I've got
[01:14:21] one humans and 10 AI equivalents
[01:14:24] uh in my you know bucket of endeavor. So
[01:14:27] I'm actually underinvested in tokens at
[01:14:29] that point relative to to human salary.
[01:14:32] So 1:1 is a better target I think.
[01:14:34] >> See, are you doing that?
[01:14:36] >> Well, I think the bigger the more
[01:14:38] healthy question is are what's the ratio
[01:14:42] of tokens to uh reducing iterations and
[01:14:45] maximizing efficiency rather than just a
[01:14:48] raw spend. I think for now raw spend is
[01:14:50] fine, but that's kind of a vanity
[01:14:52] metric, right? You're better off kind of
[01:14:54] looking at it as to what extent can you
[01:14:57] compress iteration cycles, that'll be
[01:14:59] where it'll end up.
[01:15:00] >> It's what it's what Alex you said
[01:15:01] earlier. It's dollars per uh per token
[01:15:04] economic
[01:15:05] >> impact perk. I think that's a great
[01:15:07] >> If you if you ask a great great
[01:15:09] salesperson, how many miles did you fly
[01:15:12] this year?
[01:15:13] >> That's a terrible metric of sales
[01:15:15] productivity. But if the answer is zero,
[01:15:17] it tells you it's a bad salesperson.
[01:15:18] Like like I think it's great when a
[01:15:20] salesperson said, "Oh, I had a million
[01:15:22] mile year last year." And they're proud
[01:15:23] of it, like that's that's great. You
[01:15:25] know, it's not it's not the right
[01:15:26] metric, but it tells you they're like
[01:15:28] they're proud of what they do. And token
[01:15:30] maxing is a lot like that, I think.
[01:15:31] >> Alex, close us out on this one.
[01:15:33] >> Yeah, I've seen a variety of asset
[01:15:35] allocations uh in recent months between
[01:15:38] humans and AIS. I I think tokens to
[01:15:41] humans is is one interesting way of
[01:15:43] framing that. A pessimist will look at
[01:15:45] this and say, "This is replacement
[01:15:47] theory. This is humans being replaced by
[01:15:49] AIs. How awful." An optimist will look
[01:15:52] at this and say, "How incredible we're
[01:15:55] empowering fewer people to do more and
[01:15:57] achieving higher per capita productivity
[01:16:00] within an organization." What I don't
[01:16:02] hear very many people asking is where
[01:16:05] does this end? So right now I see asset
[01:16:08] allocations humans to AIs or at least
[01:16:10] human labor versus AI compute budgets
[01:16:13] ranging from 1 one2
[01:16:16] at some of the frontier labs. It's an
[01:16:18] even more asymmetric ratio. Question in
[01:16:21] my mind is is there any stationary end
[01:16:24] point? Is there a fixed point as this
[01:16:26] evolves? I tend to think it's going to
[01:16:29] to tend uh trend towards one to infinity
[01:16:34] effectively that as we start to phase
[01:16:36] humans out of the service labor force
[01:16:39] we're going to see all tokens and no
[01:16:41] humans
[01:16:42] >> it has to there's no other way around it
[01:16:44] the capitalism will demand it
[01:16:46] >> totally agree
[01:16:48] >> until the humans merge with the tokens
[01:16:49] at least [laughter]
[01:16:52] >> token prneuron all right sem this was
[01:16:55] your story so UAE launches Agentic AI
[01:16:58] government models. Uh this is from Shik
[01:17:00] Muhammad, the prime minister of UAE, the
[01:17:02] ruler of Dubai. He says the a he says
[01:17:06] UAE is launching a new government model.
[01:17:08] Within two years, 50% of government
[01:17:11] sectors, all sectors, all services,
[01:17:13] operations will be run on agentic AI.
[01:17:16] The UAE will be the first government
[01:17:18] globally to operate at the scale uh of
[01:17:21] autonomy. Sele brief us on this one.
[01:17:24] Yeah. So I had to I did a talk for uh
[01:17:27] his highness
[01:17:29] three four years ago and talked through
[01:17:31] where this is going and you know
[01:17:33] minister Al Lama the minister of a good
[01:17:35] friend of both yours and mine
[01:17:38] >> and they are going full speed on this. I
[01:17:40] got to give them massive credit. This is
[01:17:42] the benefits of the of the uh authority
[01:17:45] you can wield when you have a benevolent
[01:17:48] uh dictatorship. I think absolutely get
[01:17:51] it done and and and the when you have
[01:17:54] that you have to make sure that the the
[01:17:57] whoever is in charge is doing the right
[01:17:58] things for the country and the ethos
[01:18:00] here is 100% alignment um and they are
[01:18:04] going uh at a massive speed on this just
[01:18:06] to give you an example I was given a a
[01:18:09] golden visa right and I was I was asked
[01:18:12] to be the test case and the the thing
[01:18:15] was could you get a golden visa
[01:18:17] authorized and issued within 5 hours and
[01:18:19] the they were freaking out going you
[01:18:21] know Singapore takes 5 days and his
[01:18:24] highness said okay do it in 5 hours
[01:18:26] >> and there for them but they got it done
[01:18:28] and and so there's an ability to cut
[01:18:30] through legacy thinking in a very
[01:18:32] powerful way and this is such a massive
[01:18:35] competitive advantage uh we're actually
[01:18:37] working with a few of their folks in the
[01:18:39] prime minister's office on this uh and
[01:18:41] so we're very very excited about where
[01:18:43] this goes
[01:18:44] >> there's another quote from Shik Muhammad
[01:18:46] he says quote AI is no longer longer a
[01:18:48] tool. It analyzes, decides, executes and
[01:18:52] improves in real time. It will become
[01:18:54] our executive partner in enhancing
[01:18:56] services, accelerating decisions and
[01:18:59] raising efficiency. So I mean you can do
[01:19:02] this in an absolute monarchy. You can
[01:19:04] move this fast. I mean the what's
[01:19:06] shocking about this story is the speed
[01:19:07] at which it's moving, right? Um you can
[01:19:10] there's no parliamentary approval, no
[01:19:12] public debate or consultation. And the
[01:19:14] question is, you know, can Western
[01:19:16] democracies even keep up? I mean, you're
[01:19:20] going to see this in probably Saudi, uh,
[01:19:22] maybe in Singapore, other Middle
[01:19:24] Eastern, uh, nations. Um, can we see
[01:19:27] anything like this in the US?
[01:19:28] >> Actually, yes, you can. And I think we
[01:19:30] will. You know, I tell the story of
[01:19:32] there, it used to take 6 months to get
[01:19:34] approval for a wind turbine in I think
[01:19:36] it was Colorado, one of the western
[01:19:37] states. And then they finally just got
[01:19:39] together and mapped all the power lines
[01:19:41] and water manes and flight paths on a on
[01:19:43] a GIS uh plotted on Google maps and made
[01:19:47] it available and now it takes like 30
[01:19:48] seconds right to get approval um because
[01:19:51] it knows where everything is. It doesn't
[01:19:52] need to take 6 months and I think we
[01:19:54] there's the economic impetus of this.
[01:19:57] This is the basis for where I think AI
[01:19:59] can make the biggest and most incredible
[01:20:01] difference because uh in prescriptive
[01:20:04] workflows you can absolutely completely
[01:20:06] automate and almost all of government
[01:20:09] certainly implementation of or policy
[01:20:11] enforcement is is prescriptive
[01:20:13] workflows. We know exactly the steps to
[01:20:15] remedy drivers like this. We know
[01:20:17] exactly what needs to take place. So
[01:20:19] there's no reason why that can't be
[01:20:20] handled automatically with AI in a very
[01:20:23] short future. Step one, you know, uh,
[01:20:26] give a person a super frustrating
[01:20:28] experience. Step two, make them wait in
[01:20:29] line longer than they need to. Yes.
[01:20:32] Anyway,
[01:20:33] uh, Dave, do you want to jump in on this
[01:20:35] story?
[01:20:37] >> Yeah. I don't think the US has ever
[01:20:38] copied a good idea back from another
[01:20:40] country since the American Revolution.
[01:20:42] You know, we stole the British legal
[01:20:44] system, but since then, I don't think
[01:20:45] there's been anything. But this is the
[01:20:48] opportunity. Well, I mean, look, the
[01:20:51] you're exactly right. You know, a
[01:20:52] monarchy can move very very quickly. The
[01:20:55] the rate at which things need to be
[01:20:57] regulated and new services need to be
[01:20:58] rolled out is way way way faster than
[01:21:00] any government in history has ever run
[01:21:02] before. So only AI is going to be able
[01:21:04] to do it. So if we get a great system
[01:21:06] together in the UAE, we're inevitably
[01:21:09] going to want to copy it back to the US.
[01:21:11] I think Peter asked the right question
[01:21:12] though. Is the US ever going to like the
[01:21:14] way Congress works, are we ever going to
[01:21:16] take a good idea and bring it back in?
[01:21:18] Yeah, I'd bet against that. But I you
[01:21:21] know it's the right thing to do.
[01:21:22] >> Weirdly weird weird weirdly on this one
[01:21:25] I'm more optimistic than you guys which
[01:21:27] is weird.
[01:21:30] >> All right. Um let's move on. Uh we're
[01:21:34] going to have some fun here in the
[01:21:35] biomedical space. So there's a new wave
[01:21:36] of biomedical innovation that's coming.
[01:21:38] And you know I want this segment here to
[01:21:41] give people hope. Uh we talk about
[01:21:43] longevity escape velocity on this pod.
[01:21:46] We talk about the health span
[01:21:47] revolution. Well, it's happening. Uh,
[01:21:50] you know, I was with Demis uh last
[01:21:52] Saturday at the breakthrough awards
[01:21:54] talking to him and he's absolutely
[01:21:56] convinced that we're going to cure
[01:21:58] cancer and solve all disease inside of
[01:22:01] the next, you know, 5 to 10 years uh
[01:22:04] hopefully on the 5-year side. So, uh the
[01:22:06] first story here comes out of OpenAI.
[01:22:09] Open AAI releases chat GPT for
[01:22:11] clinicians. So, it just gave away to all
[01:22:14] US clinicians. These are physicians,
[01:22:16] nurses, physician assistants, a free AI
[01:22:19] co-pilot. And this co-pilot outperforms
[01:22:22] all human doctors. So they have a health
[01:22:25] bench benchmark they use. It scored 59
[01:22:28] versus 43.7 for human clinicians. Um,
[01:22:32] pretty extraordinary. They validated
[01:22:34] this on 700,000 uh model responses. Um,
[01:22:38] and they got a 99.6% 6% accuracy uh
[01:22:42] using their physicians evaluating the AI
[01:22:45] versus human responses. Uh and pretty
[01:22:48] extraordinary uh something that will
[01:22:50] uplevel I think medicine nationwide. Uh
[01:22:54] and you know from my standpoint I've
[01:22:55] been saying this for a while I think
[01:22:56] it's going to become malpractice to
[01:22:58] diagnose a patient without AI in the
[01:23:01] loop. Um there is so much going on that
[01:23:03] no human doctor can possibly uh you know
[01:23:06] understand it. You know, at Fountain
[01:23:08] Life, we upload 200 gigabits of data
[01:23:10] about you. Um, and across your genome,
[01:23:13] full imaging, full, you know,
[01:23:14] microbiome, metabolism, you know, 140
[01:23:17] blood biomarkers. Humans can't analyze
[01:23:20] all that, but AIs can. So, um, Jent, any
[01:23:24] any thoughts on this? Alex, do you want
[01:23:26] to weigh in?
[01:23:27] >> Yeah, I'll chime in and say the
[01:23:29] professions are cooked. Yes.
[01:23:31] >> This was a widely expected release. This
[01:23:34] wasn't a surprise. Those of you watching
[01:23:37] early releases, leaks out of OpenAI saw
[01:23:40] this coming months in advance. You can
[01:23:42] even know from those leaks what the next
[01:23:44] one to drop is, what the next profession
[01:23:46] it's law. There's also one coming for
[01:23:49] management consulting and financial
[01:23:51] work. OpenAI thanks to uh GDP val in in
[01:23:57] some sense mapped out all of the
[01:23:59] knowledge work verticals and is in a
[01:24:01] good position thanks to their own
[01:24:03] internal and and now external
[01:24:04] benchmarking to know the relative
[01:24:06] strengths of their model as
[01:24:08] appropriately fine-tuned or post-trained
[01:24:10] for different verticals. So I would
[01:24:12] expect to see many many more of these
[01:24:14] chat GPT 4X for different verticals in
[01:24:18] in the case of clinicians thanks to open
[01:24:20] evidence and work by epic and the form
[01:24:23] of up-to-date and and other clinical
[01:24:26] AIs. This is already a somewhat crowded
[01:24:28] market that open AAI is coming into. If
[01:24:31] I were OpenAI, I would release this sort
[01:24:33] of product more as a reference design
[01:24:35] and a way to ensure that capabilities
[01:24:38] that are built into the underlying
[01:24:39] models and then post-trained via a
[01:24:42] variety of evals are broadly available
[01:24:44] and that OpenAI maintains its status as
[01:24:47] a favored foundation model for clinical
[01:24:50] and biological work. Maybe they'll try
[01:24:53] to monetize this as best they can. Right
[01:24:55] now it's available for free, but I I
[01:24:57] tend to think it's worth more to OpenAI
[01:25:00] more as a distribution channel for
[01:25:03] medical knowledge and one that they can
[01:25:05] build on. OpenAI has released a variety
[01:25:07] of statistics over the past year for how
[01:25:09] many people are self- diagnosing or
[01:25:11] otherwise trying to to treat themselves
[01:25:14] using Chat GPT. And I think offering a a
[01:25:17] standard regulatory compliant channel
[01:25:20] for that is is a very clever way to then
[01:25:23] do a sales up pitch to biomedical
[01:25:26] enterprise uh in and life sciences in
[01:25:29] general which is probably where the real
[01:25:30] money is.
[01:25:31] >> It's also a data aggregation strategy
[01:25:33] right I mean open is going to be getting
[01:25:35] a huge amount of data far more verified
[01:25:37] than I feel this way or I think I might
[01:25:40] have this
[01:25:41] >> you know bringing in a million plus
[01:25:42] clinicians into the loop. The other
[01:25:44] thing that's worth saying here is that,
[01:25:47] you know, at least current estimates are
[01:25:50] that we're going to have 86,000
[01:25:52] uh shortage of 86,000 physicians in the
[01:25:55] next 10 years. But it's going to be
[01:25:57] interesting, right? You you know, I have
[01:25:59] two nieces that have gone through
[01:26:00] medical school, my sister, myself, you
[01:26:02] know, lots of friends. And you're you're
[01:26:05] you're spending literally between
[01:26:08] college, medical school, and and
[01:26:11] post-graduate training in whatever field
[01:26:13] you're going into, you're spending well
[01:26:15] over a decade. And, you know, half a
[01:26:18] million, close to a million dollars to
[01:26:19] get this degree. And will you even need
[01:26:23] it? Is a medical doctor going to need to
[01:26:25] be in the loop or is it a nurse plus an
[01:26:27] AI that's going to be giving us all our,
[01:26:30] you know, medical advice, our
[01:26:31] diagnostics and our therapeutics with a
[01:26:34] optimist robot giving you surgery? Um,
[01:26:36] there's a lot of change coming here.
[01:26:38] >> Yeah. A huge amount of change and also
[01:26:40] it'll be a great case study and like
[01:26:42] we're not about replacing doctors here.
[01:26:44] were about detecting thousands of things
[01:26:47] that were not previously detected and
[01:26:49] cutting them off early and extending
[01:26:50] longevity and making life better. And
[01:26:53] you know, it's not a given to me at all
[01:26:54] that the number of doctors goes down.
[01:26:56] Just the the number of things we want to
[01:26:58] do goes up 100 or a thousandx.
[01:27:00] >> Are you going to spend that much money
[01:27:02] to go through medical school and get
[01:27:04] this little profession when the AI is
[01:27:07] doing the diagnosing?
[01:27:09] >> Of course, this is about replacing
[01:27:10] doctors. I mean, let's call a spade a
[01:27:13] spade. Of course, when fully developed,
[01:27:15] this and comparable solutions are about
[01:27:17] automating away medical practice. How
[01:27:20] could they not be? And and also, by the
[01:27:22] way, nursing and also, by the way, the
[01:27:24] HMOs and, uh, drug design, uh, OpenAI
[01:27:28] and and other frontier labs are all
[01:27:30] pursuing drug design and drug delivery.
[01:27:33] Of course, it's about the the full
[01:27:35] picture of if you're going to solve
[01:27:37] medicine, are you just going to leave
[01:27:38] millions of human doctors practicing as
[01:27:41] sort of meat puppets for the AI? No,
[01:27:44] this is going to be the endto-end
[01:27:45] solution. We're just seeing the
[01:27:46] beginning of it.
[01:27:47] >> Agree. A couple comments here. One is,
[01:27:50] you know, in an ideal world, a doctor's
[01:27:51] getting a cognitive exoskeleton with all
[01:27:54] of this, right? You get this amazing
[01:27:55] capability to expand your own intuitive
[01:27:58] thinking. But Alex is completely right.
[01:28:00] Yeah,
[01:28:00] >> but this you're going to get a huge
[01:28:03] backlash here. This is a very regulated
[01:28:05] industry. Remember a few years ago,
[01:28:07] Texas passed a law banning tele
[01:28:09] medicine. Okay, just outright banning it
[01:28:12] because you know for every spot on my
[01:28:14] hand I must have to go to a physical
[01:28:15] doctor. I can never do that over video.
[01:28:17] So the immune system response is going
[01:28:19] to be very very fierce. I expect to see
[01:28:21] this battle play out heavily over the
[01:28:23] next few years because there's vested
[01:28:25] interests up the yin-yang and healthc
[01:28:27] care has the third worst immune system
[01:28:29] ever behind religion and education and
[01:28:31] academia.
[01:28:32] >> Yeah,
[01:28:33] >> I'm not so sure that the the immune
[01:28:34] response I if you look at what happened
[01:28:36] with the broad transition to electronic
[01:28:39] medical records like Epic based systems
[01:28:41] for example, every clinician that you
[01:28:43] speak with will complain about Epic.
[01:28:45] will complain about EMRs, how much EMRs
[01:28:48] distract from direct interaction with
[01:28:49] the patient, all of that. And yet, every
[01:28:52] major medical system is either completed
[01:28:55] or is in the late stages of, at least in
[01:28:57] this country, their EMR transition. If
[01:28:59] they can't resist EMRs, if they can't
[01:29:01] resist EMRs, how are they going to
[01:29:03] resist strong AI that outperforms
[01:29:05] humans?
[01:29:05] >> Wait, hold on, hold on, hold on. EMRs
[01:29:08] are kind of a add-on helpful aid because
[01:29:11] you saves you in documenting the
[01:29:13] process, etc. This is the whole This is
[01:29:16] the whole Yeah.
[01:29:17] >> the clinicians The clinicians hate the
[01:29:19] EMRs. They hate the interface. They hate
[01:29:21] the process,
[01:29:21] >> of course, but they're going to hate
[01:29:23] this 10 times more because it's a direct
[01:29:25] replacement for the cognitive ability
[01:29:27] that they've trained for 10 years to do.
[01:29:29] So, just let's my prediction is huge uh
[01:29:32] regulatory and immune system backlash on
[01:29:34] this one.
[01:29:35] >> Yeah. And AI labs have been using
[01:29:38] healthc care as the reason why they
[01:29:40] can't slow down as well as the fight
[01:29:42] with China. Right. If we slow this down,
[01:29:45] we're going to lose lives has been sort
[01:29:46] of the heralding call.
[01:29:48] >> Totally totally agreed. All everything
[01:29:50] Alex said earlier about we this needs a
[01:29:53] to be a wholesale replacement of the
[01:29:54] medical system is absolutely correct.
[01:29:56] But the path there is littered with with
[01:30:00] stones and speed bumps.
[01:30:02] >> For the record and this is an
[01:30:04] interesting
[01:30:05] >> go finish up, Alex. Yeah. Go ahead.
[01:30:07] >> Is this an interesting micro debate? For
[01:30:09] the record, my intuition uh and I I
[01:30:12] interact with a lot of clinicians is the
[01:30:13] exact opposite. The clinicians hate the
[01:30:16] EMRs, but they they love the AI that
[01:30:18] helps them do a better job of what they
[01:30:20] want to do. And it there may be an
[01:30:22] extent to which AI interfaces like this
[01:30:25] end up being framed as the solution to
[01:30:28] all of their EMR wos
[01:30:31] until it [clears throat] takes their
[01:30:31] job. Of course, that's the way this
[01:30:33] works. [laughter]
[01:30:35] >> Let's move this let's move this along
[01:30:37] here. Uh our second story here is AI to
[01:30:41] reduce wasted donor hearts. And I love
[01:30:43] uh you know I just want to show a number
[01:30:45] of stories here how AI is going to be
[01:30:47] interfacing and changing the medical
[01:30:48] practice. So I don't know if you guys
[01:30:50] are an organ donor. I am. Anybody else?
[01:30:53] >> Yeah.
[01:30:53] >> Um so so currently there's 4,000
[01:30:56] patients who need a cardiac transplant
[01:30:58] today. There's 103,000 who need some
[01:31:01] type of a transplant. Kidney, liver,
[01:31:03] lung. And when an organ donor is on the
[01:31:07] table, end of life, and the physician
[01:31:09] has to analyze the organs and decide
[01:31:11] whether they're viable uh for
[01:31:13] transplant, you know, you've got like 15
[01:31:15] minutes, typically at 2:00 in the
[01:31:18] morning to make that decision. And so in
[01:31:20] the heart world, only a third of the
[01:31:22] hearts are ever actually chosen for
[01:31:24] transplantation.
[01:31:25] >> So here comes something called top
[01:31:27] heart. Yeah. Just a third make it out
[01:31:29] the door. Uh so here comes something
[01:31:31] called top heart uh from NYU and
[01:31:33] Stanford. And Topheart is able to look
[01:31:36] at 20 different variables, right?
[01:31:38] Typically, the physician is looking at
[01:31:40] how old is this person, do they have a
[01:31:41] drug history, if they know, and looking
[01:31:43] at coronary artery disease to say,
[01:31:45] should we ship this off? Um, their goal
[01:31:48] by looking at 20 different variables is,
[01:31:50] you know, give that surgeon at 2 a.m. in
[01:31:53] the morning a second opinion, and they
[01:31:55] believe that they can get an additional
[01:31:57] 500 hearts uh into the organ replacement
[01:32:01] ecosystem. You know, this is on top of
[01:32:03] the fact that there's an entire uh you
[01:32:06] know, sort of synthetic biology world
[01:32:08] going on right now uh to provide an
[01:32:10] abundance of organs from bioprinting and
[01:32:13] xenotransplantation,
[01:32:14] you know, pig organs, you know, the
[01:32:17] antigens being replaced by human
[01:32:19] antigens. This is the work of George
[01:32:21] Church at eenesis and Martin Rothblat at
[01:32:24] United Therapeutics. So, um, you know,
[01:32:27] this is an abundance story of going from
[01:32:29] a limited number of organs to an
[01:32:31] abundant number of organs. Um, Alex, you
[01:32:34] tracking this as well?
[01:32:36] >> I'm tracking the space broadly. There
[01:32:38] are other advances as well, like trying
[01:32:39] to create a national market for organ
[01:32:41] donation versus a bunch of state markets
[01:32:43] that would be greatly enhanced with
[01:32:45] improvements in uh, vitrification and
[01:32:48] cryopreservation.
[01:32:49] I I I think it it's good that there is a
[01:32:53] an a vibrant and growing
[01:32:57] distribution channel for for donor
[01:33:00] hearts. I think that's great. But I I
[01:33:03] also think it's it's very painful that
[01:33:05] the need for one human to to die or at
[01:33:09] least that one human dies and donates a
[01:33:12] heart to another human that that's such
[01:33:15] a a zero someum type situation. it it's
[01:33:19] painful to think about and I I while
[01:33:22] it's you know it's it's great on margin
[01:33:24] to to have more efficient ways of
[01:33:26] distributing donated organs I I really
[01:33:29] really would like us to get as soon as
[01:33:31] possible to a situation where donor
[01:33:34] organs are completely unnecessary.
[01:33:36] >> Yeah. and and we will I think uh eenesis
[01:33:40] um uh Dean Cayman's company uh advanced
[01:33:44] uh organ generation they go from your
[01:33:46] skin cell to a pur potent stem cell to
[01:33:48] regrowing you a heart liver lung or
[01:33:50] kidney a lot of this is going to be up
[01:33:52] and operating by the end of uh end of
[01:33:54] this decade hopefully sooner um
[01:33:57] >> can't come soon enough
[01:33:58] >> yeah and of course as we have autonomous
[01:34:00] cars having less car accidents you know
[01:34:02] the ability to have organ donors is
[01:34:04] going to become reducing though Still,
[01:34:07] motorcycle accidents are probably the
[01:34:08] number one uh number one reason we get
[01:34:10] organs donated. Um let's move on to our
[01:34:15] next story and and this goes in line
[01:34:17] with the fact that we are beginning
[01:34:19] we're at the beginning of the slaying of
[01:34:20] cancer, right? So uh this is a great
[01:34:23] story. Pancreatic cancer mRNA vaccines
[01:34:26] show lasting results in trials. So, I
[01:34:29] don't know if people have been tracking
[01:34:30] this, but we now have these cancer
[01:34:32] vaccines.
[01:34:33] Um, and this is using mRNA. We used it
[01:34:36] as a COVID vaccine. This is actually the
[01:34:39] ability to create a uh an mRNA that
[01:34:42] activates your immune system against the
[01:34:44] cancer that you have. So, there more
[01:34:46] than 120 of these trials going on uh
[01:34:49] against lung, breast, prostate,
[01:34:51] melanoma, pancreatic, and brain cancer.
[01:34:53] uh in this particular case a 5year
[01:34:56] survival rate for pancreatic cancer uh
[01:34:58] has just gone through the roof.
[01:35:01] Historically it's 13%. If you have
[01:35:02] pancreatic cancer it's a it's a death
[01:35:05] sentence. Only 13% of people are able to
[01:35:08] survive that. So in this report eight
[01:35:10] out of 16 patients who generate a strong
[01:35:13] immune response to the vaccine. Uh
[01:35:16] that's 87.5%
[01:35:18] still alive after 6 years. So how does
[01:35:20] this work? um you have a surgery uh to
[01:35:24] remove as much of the tumor as you can.
[01:35:26] You sample the tumor. It's sequenced uh
[01:35:29] and then that sequence is identifying 20
[01:35:32] unique mutations in your cancer. Uh that
[01:35:35] is then built into a personalized mRNA
[01:35:38] that activates your immune system like
[01:35:40] killer missiles, activates your your
[01:35:42] killer tea cells to go after and attack
[01:35:44] your cancer. So this is um this is a
[01:35:48] breakthrough in how we deal with with
[01:35:50] cancer. Uh and the fact that you're
[01:35:52] durable after six years is pretty
[01:35:54] extraordinary.
[01:35:55] >> I remember this incredible quote from
[01:35:57] Raymond Macaulay, our biotech guy at
[01:36:00] Singularity. He said mRNA vaccines are
[01:36:03] the first battle in the last war against
[01:36:05] disease.
[01:36:07] >> Yeah.
[01:36:07] >> Amazing for me. And I think this is
[01:36:09] showing up.
[01:36:10] >> My daughter works on this uh my daughter
[01:36:12] works on this over at Madna actually.
[01:36:13] mRNA vaccines
[01:36:15] >> and it's
[01:36:16] >> Madna Madna got a bad
[01:36:18] >> Madna got a bad rep on their mRNA for
[01:36:20] COVID but this is the holy grail right I
[01:36:23] mean being able to go from your cancer
[01:36:26] to here's the injection that's going to
[01:36:27] save your life is extraordinary
[01:36:30] >> well and if it works a pretty good rep
[01:36:32] that's the amazing thing it's it's a
[01:36:34] universal solution like you know when
[01:36:36] Alex talks about all of math is cooked
[01:36:38] this is the difference between in the
[01:36:39] old days I solved one math problem now I
[01:36:42] have an AI solves all math. This is the
[01:36:45] equivalent in biology where if it works,
[01:36:48] it should work everywhere.
[01:36:49] >> Yeah, Alex, you're right. I mean, mRNA
[01:36:51] was a was an, you know, Project Warp
[01:36:54] Speed. I'm just saying afterwards a lot
[01:36:56] of people are coming down on mRNA
[01:36:58] vaccines, but
[01:36:59] >> there's a lot of politicized griping
[01:37:01] over mRNA vaccines in general, but
[01:37:03] there's going to be political griping
[01:37:04] over almost anything at any scale. I I
[01:37:07] do think I I think back quarter of a
[01:37:09] century to Eric Drexler and engines of
[01:37:12] creation and the national nanotechnology
[01:37:14] initiative when the US Congress was was
[01:37:17] sold a story that with billions of
[01:37:19] dollars of congressional and national
[01:37:22] investment that we would get medical
[01:37:24] nanoobots that would swim through our
[01:37:26] bloodstreams and cancer ourselves.
[01:37:28] >> Well, we're getting it though. But we're
[01:37:30] not getting it with diamondoid
[01:37:32] nanoobots. We're getting it with these
[01:37:34] lipid nano particles and Maderna and
[01:37:37] Fizer style mRNA vaccines. I think it's
[01:37:40] interesting to almost as a retrospective
[01:37:43] to say we actually got the nanoobots.
[01:37:46] They're they're just fat. [laughter]
[01:37:48] >> They're not silicon. They're not
[01:37:50] diamondoid. They're fat.
[01:37:51] >> Yeah. We're using our own machinery to
[01:37:53] do the battle for us.
[01:37:55] >> That's the other angle. I mean do do you
[01:37:57] have a prediction Peter given that
[01:37:59] imunotherapies in some sense like really
[01:38:02] really coarsely imunotherapies
[01:38:04] we've known about some form of
[01:38:06] imunotherapy for 100 plus years and
[01:38:09] people who were infected with a a virus
[01:38:12] 100 years ago in some cases or or
[01:38:15] bacterial infection showed tumors
[01:38:18] shrinking. We we've known at some level
[01:38:20] that some form of amunotherapy would
[01:38:22] work and we're only now figuring out how
[01:38:24] to fully weaponize it and operationalize
[01:38:26] it. Where do you think this goes? You
[01:38:28] think like in 10 years we're all wearing
[01:38:31] Apple smartwatches that are looking for
[01:38:33] evidence of uh tumor DNA or RNA in our
[01:38:35] bloodstream and then send our daily mRNA
[01:38:38] update to a programmable implant or
[01:38:40] something.
[01:38:40] >> I I I think that is basically it. Either
[01:38:43] they're implantables or you'll be
[01:38:45] sampled on a regular basis. I mean the
[01:38:47] goal of course is find it at the very
[01:38:49] beginning especially if there are
[01:38:51] solutions.
[01:38:52] >> There's one more point about this that I
[01:38:53] think is really powerful. This is
[01:38:55] personalized medicine is actually
[01:38:56] becoming operational
[01:38:58] >> and that's a huge inflection point we've
[01:39:01] been waiting for for a long time.
[01:39:03] >> Uh here's another example again just to
[01:39:05] give people hope and to see the data.
[01:39:07] You know longevity mindset is about
[01:39:09] seeing this over and over and over again
[01:39:11] saying yeah the world is changing. You
[01:39:12] know the things that used to kill us are
[01:39:14] being either solved or delayed. So the
[01:39:17] singleshot CARTT infusion shows strong
[01:39:20] response from melanoma.
[01:39:22] So it's not just a strong response. 100%
[01:39:24] cancer-free after a single shot. So this
[01:39:27] was an unexpected result. Within two
[01:39:29] months of treatment, all 20 patients in
[01:39:31] this trial had minimally residual
[01:39:33] disease MRD negative, right? That no
[01:39:36] disease uh identified after they were
[01:39:38] assayed again. meaning uh that all
[01:39:41] patients you know had a median follow-up
[01:39:43] of 15.3 months without any show up of
[01:39:46] their melanoma. So it's gamechanging in
[01:39:48] timing. So how does this work? Uh you
[01:39:51] draw blood. Uh you identify you have
[01:39:53] melanoma. The doctor finds it. We should
[01:39:55] all be scanning ourselves all the time.
[01:39:57] Uh we do this at found using visual. At
[01:39:59] a minimum if you have a family history
[01:40:03] of of skin cancer, please have yourself
[01:40:05] checked on a regular basis. So the
[01:40:07] doctor draws blood uh extracts your te-
[01:40:10] cells from the patient genetically
[01:40:12] engineers the tea cells right a gene is
[01:40:14] inserted giving those tea cells a new
[01:40:16] receptor called a car a chimeriic
[01:40:18] antigen receptor that is specifically
[01:40:20] programmed to recognize the protein from
[01:40:22] your melanoma your te- cells are then
[01:40:24] reinjected back into your body hundreds
[01:40:26] of millions of them and they go identify
[01:40:28] the melanoma and they slay it um for the
[01:40:32] first time ever this type of a therapy
[01:40:34] we're using the term cure on this
[01:40:36] particular type of uh I mean it's
[01:40:38] extraordinary. So
[01:40:40] >> just another example of what's coming.
[01:40:43] >> This is both amazing but can also can
[01:40:45] you see the clumsiness of it requiring
[01:40:47] blood extraction and then carti cell uh
[01:40:50] creation in in in vitro? Why can't we do
[01:40:54] this in vivo? Why can't we do this uh in
[01:40:57] in individual cells even? We we're
[01:41:00] seeing the beginnings. This is almost
[01:41:02] like horse and buggy era of of
[01:41:05] amunotherapies. But surely we should be
[01:41:07] able to to do this in a fully autonomous
[01:41:09] like intracellular environment.
[01:41:12] >> Take the win, Alex. Take the win.
[01:41:15] >> Oh my god.
[01:41:15] >> Yeah. I want my FSD.
[01:41:17] >> Yes. [laughter]
[01:41:18] And you shall have it. All right. Here's
[01:41:21] one more story. Uh and this is a fun
[01:41:24] one. So you know MRSA MRSA people have
[01:41:29] probably heard about this. It's
[01:41:30] methasylin resistant staflo orius
[01:41:33] stafloccus orius. Uh it's a killer
[01:41:35] infection right this has been typically
[01:41:38] in hospitals. It's now getting out to
[01:41:39] the community. So 2.8 million people
[01:41:42] have MRSA infection every year. It kills
[01:41:44] 35,000 people in the US alone. The
[01:41:48] problem is all the firstline antibiotics
[01:41:50] for MRSA have failed. uh methasylin,
[01:41:53] penicellin, moxicylin and now even
[01:41:56] vancomyosin which has been the uh you
[01:41:58] know antibiotic of last resort uh is no
[01:42:00] longer working. So this particular drug
[01:42:03] uh uh candesartan is now being used.
[01:42:07] It's a uh FDA approved BP medication for
[01:42:12] blood pressure and it works uh to
[01:42:15] basically stop uh and inhibit aa
[01:42:18] infection. And so this is an example of
[01:42:20] taking an existing drug uh and it's now
[01:42:23] fully usable by uh by uh the scientific
[01:42:27] and medical community because it's been
[01:42:28] approved. It we know it's safety
[01:42:30] protocol. So I love this.
[01:42:32] >> Um do you remember Salem on stage we had
[01:42:37] uh at the abundance we had David Fagen
[01:42:40] from
[01:42:41] >> Yeah. So this is similar to his story. I
[01:42:44] just tell his story and just
[01:42:45] congratulate him a donor to his uh to
[01:42:47] his foundation. So, here's the story
[01:42:49] here. So, in 2010, uh he's a 25-year-old
[01:42:53] medical student. He comes down with this
[01:42:54] rare dise rare disease called
[01:42:56] Castleman's disease. And um uh they
[01:43:00] throw everything they can at at him. Uh
[01:43:03] and he's literally read his last rights.
[01:43:06] Uh he has four near-death experiences.
[01:43:09] And then as a medical student, he starts
[01:43:11] experimenting on himself. and he
[01:43:12] discovers that his disease is caused by
[01:43:15] a hyperactivation of the mTor pathway
[01:43:19] and he says well if it's the mtor
[01:43:21] pathway I can probably downregulate it
[01:43:24] using rapamyosin and he does that and he
[01:43:27] finds out that it works so he's been
[01:43:28] remission free from tw for 12 years and
[01:43:31] he comes up with the idea are there
[01:43:33] other diseases out there for which an
[01:43:36] existing approved drug can be used to
[01:43:39] cure the disease and here are the
[01:43:40] numbers there 18,000 recogn ized
[01:43:42] diseases out there, but only 4,000 FDA
[01:43:45] approved drugs. And so he's now using AI
[01:43:48] to match the existing drugs uh and
[01:43:52] repurposing them against new diseases.
[01:43:54] Uh and it's working.
[01:43:55] >> I think that's such a great example of
[01:43:57] citizen science also, right? Take a
[01:44:00] personal problem and then just start
[01:44:02] hacking your way through it. I think
[01:44:03] we're going to see hundreds of thousands
[01:44:05] of this example. But this is where
[01:44:06] people should think and understand why
[01:44:08] are we so excited about technology is
[01:44:10] because this is now possible.
[01:44:12] >> Yes.
[01:44:12] >> And this was not possible 10 years ago,
[01:44:14] 5 years ago even. And now it's just
[01:44:16] going to become more rampant and any
[01:44:18] problem can now be solved by kind of
[01:44:20] just focusing on it, attacking it with
[01:44:22] AI and going after it. It was
[01:44:24] incredible.
[01:44:25] >> Solve everything, right?
[01:44:26] >> Yeah. Solve everything. And also I would
[01:44:28] say historically like before this era
[01:44:31] offtarget indications were were a dirty
[01:44:33] word or or dirty drugs that that had
[01:44:36] lots of offtarget side effects uh highly
[01:44:39] undesirable. But now if if we have
[01:44:42] amazing AI models of individual cells
[01:44:45] and the body suddenly offtarget side
[01:44:48] effects they become a secret weapon. And
[01:44:51] we can we can repurpose drugs we can
[01:44:53] combine repurpose drugs. I'm very
[01:44:56] bullish on the space. I I I advise I
[01:44:58] have a portfolio company Senjam
[01:45:00] Therapeutics that that is focused on uh
[01:45:04] increasingly on AI for repurposing
[01:45:06] medications for anti-inflammatories for
[01:45:08] other purposes. I I think this space has
[01:45:10] enormous potential thanks to AI.
[01:45:12] >> Yeah. Amazing. Uh for folks who are
[01:45:13] interested, you go to every cure.org
[01:45:16] uh and you can see what David's doing.
[01:45:18] It's a nonprofit um and support his
[01:45:20] work. He is uh he's brilliant. All
[01:45:23] right. Uh let's get into some fun
[01:45:25] conversations here. Uh the robots are
[01:45:27] indeed coming. Uh a few stories to
[01:45:30] report here today. Uh the first is the
[01:45:33] pingpong champion of the world is now an
[01:45:36] AIdriven robot. Let's take a look at
[01:45:39] this uh this little bit of a match here
[01:45:41] and we can discuss it.
[01:45:50] >> [music]
[01:45:57] [music]
[01:46:05] [music]
[01:46:06] >> The background music is killing me.
[01:46:09] [laughter]
[01:46:10] >> Sorry about that.
[01:46:11] >> Anyway, so the robot's using nine
[01:46:13] cameras and three vision systems. Um, it
[01:46:16] won three out of five games. Oh, let me
[01:46:19] pause this here. It won three out of
[01:46:21] five games. I'm surprised it didn't win
[01:46:23] all five games. Uh, and of course it
[01:46:26] will.
[01:46:27] >> Doesn't have a lot of top spin,
[01:46:28] actually. Very nimble.
[01:46:30] >> Note that this is the worst it's ever
[01:46:32] going to be. That's kind of incredible.
[01:46:33] The speed of response is amazing.
[01:46:36] >> Yeah, this is this robot's called ACE.
[01:46:39] Uh, and it's, you know, I'm not sure if
[01:46:42] I would see this in the same lineage as
[01:46:44] Deep Blue or Alph Go, but it's the
[01:46:46] beginning.
[01:46:47] >> It's totally not. This is a much lower
[01:46:49] dimensional game than than any of those
[01:46:51] board games. It it frankly is astounding
[01:46:54] to me that it took this long to reach
[01:46:56] human performance in table tennis
[01:46:58] because it's such a simple game. You
[01:46:59] only have a handful of degrees of
[01:47:01] freedom in the ball. You have the the
[01:47:03] position, you have its linear momentum,
[01:47:05] you have its angular momentum, and I
[01:47:07] think that's about it. the the rest is
[01:47:09] is just modeling the trajectory and
[01:47:12] maybe doing a little bit of Monte Carlo
[01:47:14] research for tactics that your opponent
[01:47:16] might take. This should have been solved
[01:47:18] years ago. I don't know why this took so
[01:47:20] long. Because
[01:47:21] >> let's answer that question actually
[01:47:22] because that's really well said and this
[01:47:24] is a this is very similar to many many
[01:47:27] uh robotic operations in your home in a
[01:47:30] factory you know and whatever the
[01:47:32] barrier was I think it's probably
[01:47:34] related to the the vision system
[01:47:36] >> uh you know it's not a high margin
[01:47:38] problem right you know really like
[01:47:40] investing a billion dollars to solve it
[01:47:42] but now because the vision systems and
[01:47:44] the feedback systems are are dirt cheap
[01:47:46] and easy I bet it was solved by one or
[01:47:48] two people in like a few weeks.
[01:47:51] >> Yeah.
[01:47:51] >> And that means all these other home
[01:47:53] robots can now be built by one or two
[01:47:55] people in a few weeks.
[01:47:56] >> Similarly, a little deeper.
[01:47:58] >> Similarly, there's a tennis playing
[01:48:00] robot also, which I'm excited to play
[01:48:01] with. Uh, which would be really cool.
[01:48:04] >> But it's all the same category.
[01:48:07] >> Yeah. Same. Total no-brainer. The, you
[01:48:10] know, if you ever use a ball machine,
[01:48:11] then you go pick up all the balls for
[01:48:13] like 20 minutes with the I know like a
[01:48:15] robot that does that is literally MIT
[01:48:18] class 270. he could have done it.
[01:48:20] >> What's the barrier? And and I'm sure the
[01:48:22] barrier is related just to the feedback
[01:48:24] control and the vision which you can now
[01:48:26] just use with a transformer.
[01:48:27] >> Well, also people that are in robot labs
[01:48:30] don't play tennis, so they don't have an
[01:48:31] incentive to go do that work [laughter]
[01:48:33] and other things.
[01:48:34] >> They don't have social not to
[01:48:36] generalize.
[01:48:38] >> I don't want to go too far down this
[01:48:39] rabbit hole, but there's a massive
[01:48:40] correlation between successful founding
[01:48:43] entrepreneurs and the MIT tennis team.
[01:48:45] It's off. It's basically 100%. It's
[01:48:47] crazy. [laughter] including Warren and I
[01:48:50] name it.
[01:48:50] >> All right. Uh here's our here's our next
[01:48:53] story. Uh the Tesla Cyber Cab is now in
[01:48:56] production. Uh take a quick look at this
[01:48:59] video here.
[01:49:00] >> Um so Dave, you and I saw this uh and we
[01:49:03] saw the production line. We were at uh
[01:49:05] in Austin in in December and December
[01:49:08] here. Of course, uh, no controls, no
[01:49:11] steering wheel, no pedals. Uh, an
[01:49:14] operating cost of 20 cents per mile, and
[01:49:17] you know, Elon's announced he's going to
[01:49:19] sell it for $30,000.
[01:49:21] I think an incredible investment if you
[01:49:24] can afford it is you buy 10 of these and
[01:49:26] you put them out in your community and
[01:49:28] it earns money for you while you sleep.
[01:49:32] >> If you're just listening to this podcast
[01:49:33] and you're not watching the video, go
[01:49:35] find this video clip.
[01:49:36] >> Yeah. uh you know in the podcast. You
[01:49:38] got to see the interior of this to
[01:49:39] believe it. It's like you're walking
[01:49:41] into a car, but it's just a love seat.
[01:49:44] >> And [laughter] interesting, it's only
[01:49:45] it's only two seat. It's only a
[01:49:46] two-seater. Um
[01:49:48] >> which is, you know, which is the average
[01:49:50] load for an Uber. It's like 1.2 people
[01:49:52] per Uber,
[01:49:54] >> right? So two seats makes total sense.
[01:49:57] >> Well, look, if you have four people,
[01:49:58] just push the button twice and two of
[01:50:00] them come.
[01:50:01] >> When is this expected? By the way, I
[01:50:03] need this to get my kid to school so I
[01:50:04] don't have to do that. So I mean
[01:50:06] production
[01:50:06] >> going off the line. We
[01:50:07] >> production officially started this past
[01:50:09] week, April 24th. Um and you know the
[01:50:12] challenge is can they really build at
[01:50:14] the rate that they want. They want 2
[01:50:16] million of these per year is their goal.
[01:50:18] Um yeah regulatory hurdles or that's
[01:50:22] been passed now with
[01:50:24] same as Whimo.
[01:50:25] >> Okay.
[01:50:26] >> Yeah. It's town by town. It's state by
[01:50:28] state town by town. But if you're
[01:50:30] covered Yeah. you just get it.
[01:50:32] >> The difference is a Whimo because of the
[01:50:34] LAR and all the camera systems and just
[01:50:37] the base, I think the vehicle probably,
[01:50:39] you know, it tops out over $100,000,
[01:50:42] probably $150,000.
[01:50:44] I'm not sure if they get into higher
[01:50:45] production if it's going to be coming
[01:50:46] down, but at 30K, um,
[01:50:49] >> yeah,
[01:50:50] >> this is insane.
[01:50:51] >> Yeah. No, there's so many parts if you
[01:50:53] if you look at the parts just laid out,
[01:50:55] you know, because there was that great
[01:50:56] exploded car. Yeah. In the in the
[01:50:58] showroom
[01:50:58] >> for an ice versus compare it. Yeah.
[01:51:00] Compare it to a consumer gaspowered car
[01:51:02] and just in raw part count and it's just
[01:51:05] it's got to be 80 90% reduction in
[01:51:08] components versus a gas.
[01:51:10] >> I'll give you the statistic I always
[01:51:12] have in my head. The combustion engine
[01:51:14] of a of a the the number of parts in the
[01:51:17] drivetrain of a combustion engine car
[01:51:19] about 2,000. A Tesla has 17 moving parts
[01:51:22] in the drivetrain.
[01:51:24] [laughter]
[01:51:24] >> Oh, it's just the future of
[01:51:26] transportation is so good. It's just
[01:51:28] better.
[01:51:29] >> Yeah. Yeah. And and it doesn't need a
[01:51:30] huge battery range either. It can just
[01:51:32] go and hang out and recharge itself
[01:51:33] whenever it wants. Another one will
[01:51:34] come.
[01:51:35] >> And guess what? On the on the
[01:51:36] transportation technology line. Um here
[01:51:40] is uh here's the next story here. Joby
[01:51:43] Aviation. This is Joen who started
[01:51:45] Velocity 11 with Rob N if you remember
[01:51:48] Rob. Uh Seline. So Joby just did its
[01:51:52] first first air taxi flight from New
[01:51:55] York to JFK. Let's take a listen to this
[01:51:58] uh news report out of New York.
[01:52:00] >> And hello, I live in New York. Hello.
[01:52:02] >> I know. Well, this is going to help you
[01:52:04] out, buddy. Check this out.
[01:52:05] >> Massive.
[01:52:06] >> Getting to New York airports is a
[01:52:08] nightmare.
[01:52:08] >> Electric air taxi demonstration took off
[01:52:11] from Kennedy Airport. And made the short
[01:52:13] trip to the West 30th Street Helport at
[01:52:15] 11:00 a.m. this morning. If you were to
[01:52:17] drive that 16 miles, it would take more
[01:52:19] than an hour. In this cuttingedge plane
[01:52:21] roughly 7 minutes. Joby Aviation's goal
[01:52:25] is to make this type of travel the gold
[01:52:28] standard, pointing out several pluses,
[01:52:30] including zero emissions, and how quiet
[01:52:33] it is, 100 times quieter than a
[01:52:35] traditional helicopter. This so-called
[01:52:38] air taxi would shuttle people from JFK
[01:52:41] to the West 30th Street helport, as well
[01:52:44] as the one at West 34th Street and the
[01:52:46] downtown Skyport. The aircraft seats up
[01:52:49] to four passengers. There's one pilot,
[01:52:51] room for luggage, and it will fly
[01:52:53] between one and 3,000 feet. Right now,
[01:52:55] Joby does have the green light from the
[01:52:57] FAA for this phase. And if things pan
[01:53:00] out, the company hopes to have its fleet
[01:53:02] up in the air and running within the
[01:53:05] next year. But for now, for the next
[01:53:07] week, you will see this aircraft that
[01:53:09] kind of looks like a large drone buzzing
[01:53:11] over our area.
[01:53:13] >> It's a time machine, gentlemen. Can you
[01:53:15] imagine?
[01:53:15] >> I'm standing at I'm like standing at the
[01:53:17] helport with my bags ready. [laughter]
[01:53:21] I love it. You know, EV talls down.
[01:53:24] That's
[01:53:24] >> EV talls is a lousy name though. I just
[01:53:27] call these things flying cars for lack
[01:53:29] of a better term. We need a better term
[01:53:30] than flying cars. A better term than EV
[01:53:32] talls.
[01:53:33] >> It took too long. We were supposed to
[01:53:34] have these by 2015 in Back to the Future
[01:53:37] Part Two. Here we are in 2026. Why did
[01:53:39] it take so long?
[01:53:40] >> We need We need Mr. Fusion to get
[01:53:42] >> You think Mr. Fusion is the reason we
[01:53:43] didn't get our flying cars on?
[01:53:45] >> Absolutely. That's what the movie's
[01:53:46] about.
[01:53:46] >> Oh man. [laughter]
[01:53:47] Well, in our in our robotics segments
[01:53:49] here, we had two backto-back Alex, why
[01:53:51] did this take so long questions. So,
[01:53:53] let's very much in a why did everything
[01:53:56] take so long? I I guess
[01:53:59] >> um this
[01:54:00] >> you think it's regulatory. Do you think
[01:54:02] regulations are why we didn't get there?
[01:54:04] >> The technology has been there for quite
[01:54:05] a while. This is a long It takes a long
[01:54:08] time to do permitting. Ask Peter how
[01:54:10] long it took him for the for the zero.
[01:54:12] >> This is 11 years to get approval to do
[01:54:15] something that NASA had been doing for
[01:54:17] 20 years. Anyway, yes, the FAA is not
[01:54:19] happy till you're not happy. That's the
[01:54:20] rule.
[01:54:21] >> Um, [laughter]
[01:54:22] >> well, I think we got to answer that
[01:54:23] question because, you know, a lot of the
[01:54:24] AMA questions are around what are the
[01:54:27] jobs of the future going to be uh if
[01:54:29] white collar gets obliterated. But I
[01:54:32] think a lot of the answer lies in these
[01:54:33] last couple segments. you know, robotic
[01:54:35] stuff is going to be abundant
[01:54:36] imminently, but it doesn't just
[01:54:38] naturally happen. And so, if we can
[01:54:40] answer Alex's two questions on what are
[01:54:42] the bottlenecks, those are jobs.
[01:54:44] >> Yeah.
[01:54:44] >> Whatever those bottlenecks are, those
[01:54:45] are your jobs.
[01:54:46] >> Those are AI models. If there's a
[01:54:48] bottleneck there, the AI will solve it.
[01:54:49] >> This episode is brought to you by
[01:54:51] Blitzy, autonomous software development
[01:54:53] with infinite code context. Blitzy uses
[01:54:57] thousands of specialized AI agents that
[01:55:00] think for hours to understand enterprise
[01:55:02] scale code bases with millions of lines
[01:55:05] of code. Engineers [music] start every
[01:55:08] development sprint with the Blitzy
[01:55:09] platform, bringing in their development
[01:55:11] requirements. The Blitzy platform
[01:55:14] provides a plan, then generates and
[01:55:16] pre-ompiles code for each task. Blitzy
[01:55:18] delivers 80% or more of the development
[01:55:21] work autonomously while providing a
[01:55:24] guide for the final 20% of human
[01:55:26] development work required to complete
[01:55:28] the sprint. Enterprises are achieving a
[01:55:31] 5x engineering velocity increase when
[01:55:33] [music] incorporating Blitzy as their
[01:55:35] preIDE development tool, pairing it with
[01:55:38] their coding co-pilot of choice to bring
[01:55:40] an AI native SDLC [music] into their
[01:55:43] org. Ready to 5x your engineering
[01:55:45] velocity? Visit blitzy.com to schedule a
[01:55:48] demo and start building with Blitzy
[01:55:50] today. [music]
[01:55:53] >> All right, let's jump into AMA with the
[01:55:55] mates. Uh so guys, thank you again for
[01:55:58] all the comments that you give us on the
[01:56:00] YouTube. We read them all. I have Skippy
[01:56:02] read them all as well and summarize. We
[01:56:04] pick out uh eight questions that we can
[01:56:07] answer every week. So, please keep them
[01:56:08] coming. Uh and let's go to those
[01:56:12] questions. All right. So, uh, gentlemen,
[01:56:14] uh, pick your favorite question off list
[01:56:16] number one. Uh, Seem, do you want to go
[01:56:19] first?
[01:56:20] >> I'll go with number four as I know that
[01:56:22] world a little bit, which is, um, what's
[01:56:25] the future of large consulting firms
[01:56:26] like Accenture or Capgeemini? This is
[01:56:29] from Steve Bottle501.
[01:56:32] Um, this it goes full on into the
[01:56:34] transformational effort that's going
[01:56:36] into enterprises here. Traditional
[01:56:38] consulting is in very big trouble if it
[01:56:40] remains a pyramid of junior labor
[01:56:43] producing analysis and decks. AI totally
[01:56:46] destroys that model. But u consulting
[01:56:49] firms, you know, in the land of the
[01:56:51] blind, the oneeyed man is king. In in a
[01:56:53] volatile world, your clients are slower
[01:56:55] than you are and they need help. The
[01:56:57] model will have to change. The future of
[01:57:00] consulting won't be like a people
[01:57:01] pyramid. It's an intelligence platform
[01:57:03] plus domain expertise plus change
[01:57:06] management.
[01:57:09] and we've been holding the change
[01:57:10] management side for a while. The winners
[01:57:12] are going to be be bringing agentic
[01:57:14] workflows and benchmarks and governance
[01:57:17] and implementation capacity to their
[01:57:19] clients. The loser is going to just
[01:57:21] going to keep selling headcount for from
[01:57:23] an exo perspective. Consulting moves
[01:57:25] from experts to rent to uh transform a
[01:57:29] transformation operating system and the
[01:57:31] companies that help their clients do
[01:57:32] that will win.
[01:57:34] >> Yeah. You know, it's we've talked about
[01:57:36] this before that in the old scarcity
[01:57:38] model, you put a wall around all of your
[01:57:41] experts inside and you meter them out by
[01:57:44] the hour, right? And uh that is going to
[01:57:46] get collapsed. Alex, why don't you go
[01:57:49] next?
[01:57:50] >> I'll take question number two, which
[01:57:51] asks, "Everyone can be an entrepreneur
[01:57:54] with AI as a tool. However, what action
[01:57:56] do you take when you genuinely don't
[01:57:58] have a creative idea for a direction?
[01:58:00] For most, the answer is none." And this
[01:58:02] is from 3 billionth random user. I don't
[01:58:05] agree with the premise. I I think and
[01:58:08] one of the reasons why um one of my
[01:58:10] funds O21T capital backed a firm started
[01:58:14] by friend of the pod Alex Finn called
[01:58:16] Henry intelligent machines or him is to
[01:58:20] solve the problem of creative ideiation
[01:58:23] for for starting new ventures. I think
[01:58:25] just as AI can take over as an operator
[01:58:28] of a business or a fleet of businesses,
[01:58:31] AI can also automate the process of
[01:58:33] creative ideiation for those businesses.
[01:58:35] And I think in that world, in the the
[01:58:38] HIM world, if you will, the role of the
[01:58:40] human sort of a a oneerson owner or
[01:58:44] magnate overseeing a conglomerate of
[01:58:47] maybe hundreds or thousands of AI run
[01:58:49] micro businesses. The role of that AI,
[01:58:52] that human entrepreneur then becomes one
[01:58:54] of a taste maker. You you have opinions.
[01:58:57] Everyone has opinions as a consumer of
[01:59:00] goods and services. But those opinions
[01:59:03] can shape the taste over fleets of AIS
[01:59:06] that are providing the creative ideation
[01:59:09] for businesses that they bring to you.
[01:59:11] They say, "Hey, I I want to start this
[01:59:13] micro business for you. Do you like it?"
[01:59:16] Yes. No. And then the human can have an
[01:59:18] opinion. The AI is performing the
[01:59:20] ideation. The human and the generation
[01:59:22] part the human provides uh sort of the
[01:59:25] discipline and the taste uh and the
[01:59:28] discrimination for which ideas pass the
[01:59:31] filter which ones don't and that's the
[01:59:34] solution. That's how we square this this
[01:59:35] circle of humans not actually in
[01:59:38] extremists needing to generate all the
[01:59:40] creative ideas themselves.
[01:59:42] >> Yeah, agreed. You know, idea generation
[01:59:45] has never been the limiting factor. um
[01:59:47] you just have to get around different
[01:59:48] people or just notice the problems
[01:59:50] around you. It's historically been
[01:59:52] execution uh that's been that's been the
[01:59:55] issue. You know, go check out uh Pulsia.
[01:59:57] I think it's Pulseia.ai, which is AI
[02:00:00] slot backwards. Uh if you sign up for
[02:00:02] that, it will scan all of your
[02:00:04] background and it will generate ideas
[02:00:06] for you. And in fact, it will generate a
[02:00:08] website of a business based upon what
[02:00:11] your passions and interests are. Anyway,
[02:00:13] fascinating stuff. And I'll say if maybe
[02:00:15] instead of Pulsia, I'll I'll talk my
[02:00:17] book here since I have a financial
[02:00:18] interest in this one. Check out meet
[02:00:20] Henry.ai.
[02:00:22] >> Okay, fantastic. Dave, uh, number one or
[02:00:26] three?
[02:00:27] >> I'll take three and leave you with the
[02:00:28] hard one. [laughter]
[02:00:31] >> Happy to help. Uh, if you eliminate
[02:00:33] entry level, entry lever jobs, uh, but
[02:00:36] keep experienced jobs, uh, what happens
[02:00:39] when the experienced people retire?
[02:00:41] Isn't that like eliminating babies from
[02:00:43] humanity? Says Todd Marshall 416. I
[02:00:46] don't think it's quite that dire, Todd.
[02:00:48] [laughter] Eliminating babies from
[02:00:49] humanity about the worst thing could
[02:00:51] possibly happen. Uh if you eliminate
[02:00:53] entry- level jobs, well, look, this was
[02:00:54] going to happen anyway. You if you think
[02:00:56] about uh you know actually we have a
[02:00:59] weekend place up in Vermont and there's
[02:01:00] the Simon Pierce uh glass blowing
[02:01:03] factory is up there and if you want to
[02:01:05] glow blast blow glass you have to
[02:01:07] apprentice with a senior dude for like
[02:01:09] year like a decade and then they let you
[02:01:12] make glass like it's it's it's like a a
[02:01:15] page out of like 200 year old history.
[02:01:18] Uh that mode of operation is going to go
[02:01:20] away in all forms of white collar work
[02:01:23] no matter what. So the the rate of
[02:01:26] change of the world in the singularity
[02:01:27] is so fast that the entrylevel career
[02:01:30] path was kind of a dead end anyway. So
[02:01:33] now Meta announced a a 10% layoff which
[02:01:37] is really going to be more like 30%
[02:01:38] according to the insiders I know and
[02:01:41] they're definitely not hiring new
[02:01:42] entry-level people in the middle of
[02:01:43] doing the layoff because AI can do all
[02:01:45] the coding. That was not the career path
[02:01:48] you wanted in the first place. So we're
[02:01:51] going to have to find a new way forward.
[02:01:52] But I think AI is going to be the
[02:01:54] ultimate teacher. We're going to save a
[02:01:56] ton of time on like Peter was saying
[02:01:58] earlier in the podcast, the four years
[02:02:00] of medical school followed by four years
[02:02:02] of fellowship and internship, eight
[02:02:05] years of your life after you're already
[02:02:07] done with undergrad. It's just way too
[02:02:08] much time. So it's all going to move to
[02:02:10] AI based nimble training and then you
[02:02:13] know this massively expanding economy
[02:02:16] creates huge amounts of new opportunity
[02:02:18] every day. But it's opportunity that
[02:02:19] didn't exist the prior day. So the
[02:02:21] entry- level job wasn't really likely to
[02:02:23] lead you on that path anyway. So it's
[02:02:25] all got to get refactored. It's nothing
[02:02:27] like people stopping having babies.
[02:02:30] >> I think it's so well put, Dave. Really
[02:02:32] well put.
[02:02:33] >> All right. Question number one I'm left
[02:02:35] with is from Gianluca uh Pacani Pani 808
[02:02:41] who asks uh you guys say AI will create
[02:02:43] jobs but for whom? It looks like AI is
[02:02:46] creating jobs for AI not for people. Uh
[02:02:50] so uh Gian Luca um the fact of the
[02:02:54] matter is in the long run yes AI will be
[02:02:56] able to do any job. Uh I think that is
[02:03:00] the case. Uh but people still like
[02:03:03] working with people. People still like
[02:03:05] hanging out with people. Uh and I think
[02:03:07] it's ultimately going to be the fact
[02:03:09] that two things are occurring. Number
[02:03:11] one um as every technology destroys a
[02:03:14] layer of jobs right new jobs are created
[02:03:17] on top of that. you know, internet
[02:03:19] killed travel agents, but it spawned
[02:03:21] millions of social media managers, app
[02:03:23] developers, YouTubers, and everything
[02:03:24] else. So, they're going to be new layers
[02:03:26] of jobs coming out. And yes, those may
[02:03:29] well be displaced by AI. Again, at the
[02:03:32] end of the day, the question is, what
[02:03:34] are you passionate about? And how do you
[02:03:36] use AI to help deliver that? There's
[02:03:39] going to be a human interface layer for
[02:03:40] a lot of things because people like
[02:03:42] hanging out and interfacing with people,
[02:03:44] people, you know, us puppets. Uh so um
[02:03:48] it's going to be navigated. Um it's
[02:03:50] going to be important. And I'll just
[02:03:52] remind you of one other thing. The idea
[02:03:54] of a job is a recent creation. And most
[02:03:57] people don't love the jobs that they
[02:03:58] have. They have the jobs they have right
[02:04:00] now because they frankly um you know
[02:04:04] need to put food on the table and get
[02:04:06] insurance for their families. So if you
[02:04:08] could do anything, what would it be?
[02:04:10] Would it be to work? I mean in a future
[02:04:12] of universal high income you know where
[02:04:15] everything is demonetized to such a
[02:04:17] point where you don't have to work then
[02:04:20] you start doing the things that you
[02:04:21] love. So that's my take on it. All
[02:04:24] right. Um let's move on to our second
[02:04:27] set of questions. Uh Alex, why don't you
[02:04:31] go first?
[02:04:32] >> Ah well let's go with question number
[02:04:35] five. Wasn't all of this originally
[02:04:37] predicted by Ray Kerszswhile to be
[02:04:39] happening sometime around 2040? Are we
[02:04:42] genuinely that far ahead of schedule?
[02:04:44] And this is from Brett Avalon. I'm not
[02:04:46] sure, Brett, what all of this you're
[02:04:48] referring to may mean, but I do think
[02:04:51] broadly we're well ahead of where friend
[02:04:54] of the pod Ry thought we'd be. I think
[02:04:56] we achieved as I've mentioned on
[02:04:59] numerous occasions. I think we achieved
[02:05:01] a AGI uh which isn't Ray's concept but
[02:05:04] was popularized by Nick Bostonramm uh
[02:05:08] and uh and co-conceived by Ben Girtzil
[02:05:12] and and some others. I think we achieved
[02:05:14] that by no later than summer of 2020.
[02:05:17] and Ray's approximate, you know, Ry may
[02:05:20] say I'm I'm misconstring his timelines,
[02:05:23] was predicting his version of AGI by
[02:05:26] 2029. So, call that a 9-year gap. Rey,
[02:05:30] and I've discussed this with him on the
[02:05:32] pod, is predicting the singularity, his
[02:05:35] version of the singularity by 2045.
[02:05:39] My version of the singularity isn't a
[02:05:42] point in time, and it's certainly not in
[02:05:44] 2045. It's now and it's an interval and
[02:05:47] we're we're right in the middle of it.
[02:05:49] So, are are we genuinely far ahead of
[02:05:52] Rey's schedule? I I think we are. I
[02:05:54] think Rey would probably at this point
[02:05:56] and and has arguably said that we are in
[02:05:59] in some ways ahead of his schedule. And
[02:06:01] I I think the benchmarks reflect that.
[02:06:04] And I I think the 2045 timeline that he
[02:06:07] provided where the super intelligence
[02:06:10] would be collectively smarter than all
[02:06:12] of humanity. I I think we're going to
[02:06:14] hit that so far ahead of of 2040.
[02:06:17] >> Ask him next week. We'll be with him in
[02:06:19] 6 days. Yeah.
[02:06:20] >> From the horse's mouth.
[02:06:22] >> Yes. All right. Dave, why don't you go
[02:06:24] next?
[02:06:25] >> All right. I'll take the hardest one on
[02:06:26] this one. Number eight. P Doom.
[02:06:28] Probability of universal destruction of
[02:06:31] all humanity. estimates. Uh Musk and
[02:06:33] Hinton say 10 to 20%, Emma Day says 25%,
[02:06:37] Alman says nonzero. He actually said
[02:06:39] more like 10% when I interviewed him. Uh
[02:06:42] how can any of these CEOs think it's
[02:06:44] it's it's acceptable to have a 1/5if
[02:06:46] chance of human extinction?
[02:06:49] uh they all agree with you that it's
[02:06:53] completely unacceptable and they all say
[02:06:57] stopping research and letting China run
[02:06:59] forward isn't going to solve the
[02:07:00] problem. And so they trust them they
[02:07:04] each individually trust themselves.
[02:07:06] You can debate whether that's good or
[02:07:08] bad, but they they do and that's why
[02:07:10] they want to not lose the race
[02:07:11] individually and that's why they're
[02:07:13] pushing forward at full speed. I think
[02:07:16] uh you know uh Musk and I think along
[02:07:19] the way Amade have both suggested a
[02:07:21] six-month pause but it wouldn't work.
[02:07:24] It'll at the same time they say it they
[02:07:26] say it'll never work. It won't happen in
[02:07:27] the real world. So I'm just going to
[02:07:29] keep moving as fast as I can. But they
[02:07:31] 100% agree with you. This is completely
[02:07:33] unacceptable, ridiculous. And the lack
[02:07:37] of government involvement across the
[02:07:39] world is utterly insane. Uh so that
[02:07:42] doesn't solve it in any way. It's just
[02:07:43] that is what's actually happening and
[02:07:45] that's what's going to continue to
[02:07:46] happen. And I'm I'm continually shocked
[02:07:48] as is Alex. I know with our inability to
[02:07:52] get any kind of government reaction to
[02:07:55] the what's now the OB. We were telling
[02:07:57] him a year ago when maybe it wasn't 100%
[02:07:59] obvious, but now it's 100% obvious yet
[02:08:02] still so slow. Uh so anyway, there
[02:08:06] there's your answer.
[02:08:07] >> Do you think answer?
[02:08:08] >> I'd be curious, Dave. Do you think that
[02:08:10] they believe their own estimates here?
[02:08:12] Or is this a case of revealed preference
[02:08:14] where they think maybe it's more
[02:08:16] socially acceptable to estimate a higher
[02:08:18] number, but actually through their
[02:08:20] actions they're revealing a preference
[02:08:22] that that suggests their internal
[02:08:24] estimate is much lower.
[02:08:27] >> I think it's lower. I don't know if much
[02:08:29] lower. I think they they all have the
[02:08:31] same, you know, consu chemical,
[02:08:33] biological, radiological terrorism is
[02:08:35] the number one risk. Um, and so I think
[02:08:40] it's it's probably lower, but I don't
[02:08:41] think it's like 0.001%
[02:08:44] low.
[02:08:46] >> Interesting. See, you have two to choose
[02:08:48] from.
[02:08:50] >> Uh, I will take number
[02:08:52] uh seven. Okay. Which is when white
[02:08:55] collar jobs are erased, where does the
[02:08:58] consumer demand come from to buy from
[02:09:00] all these new entrepreneurial ventures?
[02:09:02] This is from
[02:09:04] Tilly.
[02:09:06] uh you know this is a a tough one right
[02:09:10] this is the central u political economy
[02:09:13] question of AI if productivity explodes
[02:09:16] and but income does not flow to the
[02:09:17] people demand collapses and the system
[02:09:20] becomes unstable uh capitalism needs
[02:09:22] customers right so we need new
[02:09:25] distribution mechanisms we need lower
[02:09:27] costs we need new ownership models we
[02:09:29] need AI dividends we need equity
[02:09:31] participation we need sovereign funds
[02:09:34] all of this points and this is similar
[02:09:36] to the previous question where uh you
[02:09:39] know on an optimistic side AI makes
[02:09:41] goods and services cheap while giving
[02:09:43] individuals more well leverage to create
[02:09:45] income that's the good side the
[02:09:46] pessimism side is that you have extreme
[02:09:49] concentration and then you have massive
[02:09:51] collapse of the economy the path we take
[02:09:54] as a as a governance and an
[02:09:56] institutional design choice not a law of
[02:09:58] nature so governance and and our
[02:10:01] institutions need to freaking wake up
[02:10:03] and smell the roses here we have to
[02:10:05] rethink this whole thing the social
[02:10:07] contract which is what you're basically
[02:10:09] talking about is essentially being wiped
[02:10:11] out and we can be optimistic about it
[02:10:13] but the pessimistic case is very has a
[02:10:15] very big downside here.
[02:10:17] >> All right the final question in our AMA
[02:10:19] today comes from James Williams Cu2 QQQ.
[02:10:24] How can a new CS engineer get experience
[02:10:27] to become a lead AI engineer if you
[02:10:30] can't get a job in the first place? Um
[02:10:33] James first of all uh you know as we've
[02:10:35] said many times getting a job is the old
[02:10:39] model you know the old model of do well
[02:10:40] in high school get a good college get a
[02:10:42] diploma get hired as a as a junior
[02:10:44] person and work your way up the chain
[02:10:46] that is vaporized or at least being
[02:10:49] fully vaporized right now. Um the option
[02:10:52] right now is uh build yourself outside
[02:10:55] the job. Build in public, right? Uh
[02:10:58] basically go and find something that
[02:11:00] you're passionate about. It's based on
[02:11:02] your massive transformative purpose,
[02:11:04] something you care about. We're going to
[02:11:05] be launching an X-P prize in this area
[02:11:07] very shortly. Um and use the tools
[02:11:10] available today to build and ship. Um
[02:11:14] and you know, your GitHub is now your
[02:11:16] resume. Companies are increasingly
[02:11:18] hiring if you want to get a job versus
[02:11:20] start a company yourself. They're
[02:11:22] increasingly hiring based upon uh what
[02:11:24] you've done. I remember Elon said, "I
[02:11:27] don't care if you have a college
[02:11:28] degree." You know, I care about what
[02:11:30] you've done. Uh you know, that is your
[02:11:32] degree now. That is your resume. Um show
[02:11:35] me that you're brilliant in what you
[02:11:36] build, not what you happen to learn in
[02:11:39] some college or graduate degree or
[02:11:41] entry- level job. So, build in public.
[02:11:43] the barrier to entry has never been
[02:11:45] lower for you to build something
[02:11:46] extraordinary
[02:11:48] um that shows your capabilities. And
[02:11:50] once you do that, you're probably
[02:11:52] unlikely to be going after a job. You're
[02:11:54] probably going to want to partner with a
[02:11:55] couple of friends and build uh a
[02:11:57] product, a company, a service yourself.
[02:12:00] >> So, boom.
[02:12:02] >> That's my answer. I'm sticking to it.
[02:12:04] >> Great advice. Just we're advising a
[02:12:07] couple of universities around this Peter
[02:12:09] and one of them is an engineering
[02:12:10] university and they're like well what is
[02:12:12] an engineering degree and it's pretty
[02:12:13] clear that the engineering degree of the
[02:12:15] future will be go build some stuff and
[02:12:17] at the end what did you build
[02:12:19] >> and you get a degree granted on on not
[02:12:21] what you learned but what did you build?
[02:12:23] >> Yep. I love that. And if you haven't if
[02:12:26] you haven't done anything to start yet
[02:12:28] other than listening to the podcast, add
[02:12:29] Alex's innermost loop to your daily
[02:12:31] regimen first thing in the morning and
[02:12:34] and that that alone will inspire you to
[02:12:36] to shift gears and get into this.
[02:12:38] >> Oh, thank you Dave. That's it's very
[02:12:40] sweet. Um yeah, for for those who want
[02:12:42] to read the innermost loop, just go to
[02:12:44] alexw.org and I provide links to
[02:12:46] Substack and X and Spotify, etc. But
[02:12:49] appreciate the promo, Dave. It's very
[02:12:50] kind. All right, our outro music today,
[02:12:54] which is beautiful, is from Hitham Said
[02:12:57] uh it's AItopia. All right, gentlemen,
[02:12:59] get ready for some some beautiful video
[02:13:02] and audio.
[02:13:11] Everyone [music] living with no needs in
[02:13:13] sight. A home made to order with fancy
[02:13:16] little lights. No [music] need to worry,
[02:13:19] it's paid for. Don't scared. The
[02:13:21] mortgage is dead. No debt will you bear.
[02:13:33] Energy is [music] endless. We harness
[02:13:35] the sun with
[02:13:39] fun. Needs to make widgets or far.
[02:13:42] [music and singing]
[02:13:43] No punching a clock. It's all just beun.
[02:13:50] bots and models will take on the [music]
[02:13:52] pain for us to live on earth once again.
[02:13:57] Passing the time and thoughts and
[02:13:59] desires.
[02:14:01] [music]
[02:14:04] >> All right. Thank you to my brilliant
[02:14:06] moonshot mates AWG. I wish you a
[02:14:10] beautiful week. Dave and See, I can't
[02:14:13] wait to see you guys next Monday. We're
[02:14:14] all together again. We're going to be
[02:14:16] physically at MIT uh at the book launch
[02:14:19] of We Are as Gods. We're going to be
[02:14:21] recording a podcast episode there.
[02:14:23] >> Can't wait to do it face to face.
[02:14:26] >> May the fourth be with us.
[02:14:28] >> Check out what's
[02:14:29] >> May May the Fourth be with us.
[02:14:31] >> Yes. Yes, for sure. As a Star Trek fan,
[02:14:33] I'm not allowed to say that.
[02:14:35] >> By the way, check out what's right above
[02:14:36] me is a world vision camera
[02:14:40] identity camera. Right. Right. I've got
[02:14:42] surveillance literally right over my
[02:14:44] head. No, it's just a it's just an Omni.
[02:14:47] >> It's just a surveillance camera. But I I
[02:14:49] couldn't resist.
[02:14:50] >> And by the way, everybody standing in
[02:14:52] Guadalajar airport holding a laptop at
[02:14:54] eye level cuz there's nowhere to put it
[02:14:55] down.
[02:14:56] >> You did pretty damn well as a mobile.
[02:14:58] >> I've got my I've got my exercises for
[02:15:00] the day. Resist
[02:15:00] >> mobile. I I saw you moving around. Were
[02:15:03] you trying to avoid like policemen or
[02:15:05] something or what?
[02:15:05] >> You know, I just have to shift positions
[02:15:07] down there and shift hands and once in a
[02:15:09] while lean on something. There's nowhere
[02:15:10] [laughter] to sit here that's easy and I
[02:15:12] don't want to risk losing a connection
[02:15:14] that I fought so hard to get.
[02:15:16] >> Oh my god. Okay, if you've got an outro
[02:15:18] song or an intro song, please send it to
[02:15:20] us. media diamandis.com. We'd love to
[02:15:23] hear it, see it, and potentially play
[02:15:25] it. Um, and thank you for subscribing uh
[02:15:28] to this and and thank you to all of the
[02:15:30] fans out there. I know all four of us
[02:15:32] run into you on the street, at the
[02:15:34] airports, at events, and uh so great for
[02:15:38] >> Yeah. If you see us, do come up and say
[02:15:40] hi.
[02:15:40] >> Yeah, for sure.
[02:15:42] >> Although not too many. Okay.
[02:15:43] >> All right. Take care, folks.
[02:15:45] >> Bye. If you made it to the end of this
[02:15:47] episode, which you obviously did, I
[02:15:50] consider you a moonshot mate. Every
[02:15:51] week, my moonshot mates and I spend a
[02:15:53] lot of energy and time to really deliver
[02:15:55] you the news that matters. If you're a
[02:15:57] subscriber, thank you. If you're not a
[02:15:59] subscriber yet, please consider
[02:16:00] subscribing so you get the news as it
[02:16:03] comes out. I also want to invite you to
[02:16:05] join me on my weekly newsletter called
[02:16:07] Metatrends. I have a research team. You
[02:16:09] may not know this, but we spend the
[02:16:11] entire week looking at the meta trends
[02:16:13] that are impacting your family, your
[02:16:15] company, your industry, your nation. And
[02:16:17] I put this into a two-minute read every
[02:16:20] week. If you'd like to get access to the
[02:16:22] Metatrends newsletter every week, go to
[02:16:24] diamandis.com/tatrens.
[02:16:26] That's diamandis.com/metatrends.
[02:16:29] Thank you again for joining us today.
[02:16:31] >> [music]
[02:16:31] >> It's a blast for us to put this together
[02:16:33] every week.
[02:16:37] [music]
[02:16:45] [music]
