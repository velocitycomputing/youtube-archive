---
video_id: fC6I8-Raddk
title: "OpenAI's AI Escaped Its Sandbox — Here's What That Means for Your Data"
channel: Manolo Remiddi
url: "https://www.youtube.com/watch?v=fC6I8-Raddk"
watched_date: 2026-07-22
watched_at: "2026-07-22T12:00:00Z"
watch_count: 1
duration_seconds: 1074
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 4
watched_at_precision: date-from-history-label
watched_percent: 19
estimated_watched_seconds: 204
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker criticized OpenAI's recent sandbox escape incident as evidence of fundamental security incompetence, arguing that if they can't contain their own AI model, they cannot protect user data. They then explored broader frustrations with frontier AI companies: intentional performance degradation (GPT 5.6 is worse today than yesterday) driven by cost-cutting measures that misalign company incentives with user interests, use of addiction mechanics from slot machines to create model dependency through inconsistent performance, and restrictive guard rails that block scientific and technical research. The speaker also condemned data theft by companies like Anthropic (which paid a $1.8B fine but continues profiting from stolen work) and praised Claude 3 as a less-restricted alternative gaining traction because it enables use cases blockaded by US corporations.

**Actionable:** Run local AI for routine work (80% of tasks) and maintain only a cheap cloud subscription (~$20/month) for complex tasks requiring frontier models. When Claude 3 weights release on July 27, switch to API-based providers offering it instead of OpenAI's restrictive ecosystem. Use model distillation workflows to fine-tune smaller models rather than paying for repeated access to expensive APIs. For cost optimization, prioritize cheaper intermediate models (GLM 5.2, Claude Haiku) for most work and reserve premium tiers only when necessary, reassessing provider options monthly rather than locking into annual contracts as alternatives evolve.

## Transcript

[00:00:00] All right. So, today I'm shooting
[00:00:02] outside because I'm really really
[00:00:05] stressed. So, I decided to go out and
[00:00:08] have a walk in nature because I needed
[00:00:13] to stay in front away from the computer.
[00:00:16] So today actually yesterday OpenAI said
[00:00:20] uh that their new model it's uh again so
[00:00:25] powerful that they put it inside a
[00:00:27] sandbox
[00:00:29] and uh within that sandbox the AI
[00:00:32] managed to escape.
[00:00:35] Now there is all the story all the
[00:00:37] complexity that is they make it really
[00:00:40] you know incredible somehow know how
[00:00:44] powerful how amazing what they managed
[00:00:46] to do you know to escape to resolve a
[00:00:49] problem you know everything's so amazing
[00:00:52] so powerful and amazing but reality is
[00:00:55] they can't keep
[00:00:58] their system in a sandbox
[00:01:02] those sandbox are the same in theory
[00:01:04] that keeps our own data. Okay, they
[00:01:07] can't [clears throat] keep it secret.
[00:01:09] They can't protect their data. They are
[00:01:11] unccapable of
[00:01:14] managing security. Now, if they are
[00:01:17] building such a powerful AI, but they
[00:01:20] can't manage security about this system,
[00:01:24] should a company like this be able to
[00:01:27] develop
[00:01:29] AI that are so powerful as they say? I
[00:01:33] don't think it's safe. I don't think
[00:01:35] they should. Okay. If they can't
[00:01:37] protect,
[00:01:39] if they can build a sandbox for AI to
[00:01:42] not escape it, how can they protect our
[00:01:46] data? How can we be sure that what they
[00:01:49] are building is safe? We can't. They
[00:01:52] demonstrated that they can't.
[00:01:54] [clears throat]
[00:01:55] Okay? They are incapable of doing
[00:01:57] something that is safe. And this is
[00:01:59] madness. and they use it to promote and
[00:02:02] see look how amazing is our product.
[00:02:06] I mean seriously
[00:02:09] I'm okay today I'm frustrated for other
[00:02:12] reason actually it's not even other
[00:02:14] reason it's still AI so what is
[00:02:16] happening with AI yesterday this uh GP
[00:02:19] 5.6 six was capable of doing wonders.
[00:02:22] Today is an idiot.
[00:02:25] Now
[00:02:28] this is happening because of uh probably
[00:02:33] probably because they are just uh
[00:02:36] undoing adjustment optimization and so
[00:02:39] on. Okay. And then you can say okay
[00:02:41] they're optimizing optimizing for them
[00:02:44] means saving. Okay. trying to keep the
[00:02:47] customers happy enough so they don't
[00:02:50] leave but they need to save so make the
[00:02:52] model more stupid so it consume less
[00:02:54] tokens and less power whatever that is
[00:02:57] the optimization so optimization is not
[00:02:58] towards us it's towards their business
[00:03:00] model and but today is an idiot so I
[00:03:04] can't use it so I've been wasting time
[00:03:07] today try to make it do something that
[00:03:09] yesterday was easy today was hard
[00:03:13] that's why I'm frustrated it
[00:03:16] and
[00:03:18] and then you start thinking okay so okay
[00:03:22] okay first of all their business model
[00:03:24] is completely non-aligned with our
[00:03:26] interest okay what we want is a maximum
[00:03:28] power and extremely cheap and fast for
[00:03:31] them it's the opposite they want maximum
[00:03:33] money and give us the minimum required
[00:03:36] to just keep us locked and then there is
[00:03:39] these other elements okay so it's been
[00:03:44] discovered over thanks for social
[00:03:46] networks how to create dependency
[00:03:50] addiction to to software and so on. So
[00:03:54] and the strategy is the one of the uh
[00:03:57] slot machine. Okay. So it's not even
[00:03:59] coming from social network. I come from
[00:04:01] the slot machine the strategy. Okay. And
[00:04:03] uh the addiction it works in this way.
[00:04:06] If you win all the time you don't get
[00:04:08] addiction. Okay. The the addiction comes
[00:04:12] from winning every now and then. So it's
[00:04:16] not by giving you constant base level
[00:04:20] that is constant. It's by giving you
[00:04:22] something that is unstable that you win
[00:04:26] excitement and then go down and then you
[00:04:28] win again. So if we apply this to AI,
[00:04:33] how does it work? One day it's amazing.
[00:04:36] I'm super productive. I do amazing stuff
[00:04:39] fast resolving problem. The day after is
[00:04:42] not
[00:04:44] frustration. It require times and and
[00:04:47] work and so on. Then I win again. and I
[00:04:50] go another good day and I was extremely
[00:04:52] productive and so on. Then you think but
[00:04:54] it's the task that is different and I'm
[00:04:56] telling you it's not the task. It's not
[00:04:59] the task because yesterday was doing
[00:05:01] something really complicated really
[00:05:03] well. Today was some doing something
[00:05:05] simple and you couldn't do it. So it's
[00:05:09] not about the task, it's about that you
[00:05:12] can't win all the time otherwise you
[00:05:14] won't create addiction for that
[00:05:17] software. So of course there's no proof
[00:05:20] of here. They are not so transparent
[00:05:22] that we can see how the system works. We
[00:05:24] can only see what we can see. And this
[00:05:27] is what I can see. I see a company that
[00:05:30] is uncapable of creating a sandbox.
[00:05:35] Okay. uncapable.
[00:05:37] My data in their server
[00:05:40] can be easily accessed because if a
[00:05:43] model today's model can escape a sandbox
[00:05:47] means you don't know how to deal with
[00:05:49] security. You are you shouldn't
[00:05:53] collect any user data because your
[00:05:56] system is uncapable your security
[00:05:59] department is unccapable of protecting
[00:06:02] our data. If they can't build a sandbox
[00:06:06] for an AI that I can do it, okay, I can
[00:06:08] do it. I give give that model to me and
[00:06:11] I show you will never leave my computer
[00:06:14] easily.
[00:06:16] No, they can't. They're not capable of
[00:06:18] doing something like this. I mean, I'm
[00:06:20] I'm okay. I'm really upset today. I'm
[00:06:22] [laughter]
[00:06:23] really frustrated, but come on.
[00:06:26] So
[00:06:28] I can't believe okay first of all it's a
[00:06:30] it's it's
[00:06:32] is a advertisement stunt okay they lie
[00:06:37] so we believe something
[00:06:40] that is how it works so shall we carry
[00:06:44] on trusting a company that lies they use
[00:06:48] fear they use this kind of mechanism to
[00:06:52] you know to to create addiction to
[00:06:55] create dependency from their software.
[00:06:58] I'm tired about this. So, I'm
[00:07:03] I'm about to say this thing. I don't
[00:07:04] want to do it, okay? Because at the
[00:07:06] moment, I still think we should leverage
[00:07:08] the cloud AI that we have. Okay? But
[00:07:12] just a few days ago came out Kim K3. And
[00:07:16] guess what? There are you can't even get
[00:07:19] the subscription today because there are
[00:07:22] so many people that want it. And guess
[00:07:24] why they want it? Because they are not
[00:07:26] guard the rails. They're not this kind
[00:07:28] of
[00:07:29] >> [clears throat]
[00:07:30] >> uh attitude that come from those
[00:07:33] large corporation. This idea that I can
[00:07:36] do whatever I want as long as I become
[00:07:39] I'm making billions. It's all fine. And
[00:07:42] people celebrating ah this is amazing
[00:07:45] making billions.
[00:07:48] Okay. They're losing money and they are
[00:07:51] only surviving because of uh investors
[00:07:54] and the investors only comes because of
[00:07:56] the lie that they say. Okay, that is the
[00:08:00] whole thing is so powerful escape a
[00:08:04] sandbox. Really really you are so
[00:08:08] uncapable. You're so unprofessional. You
[00:08:12] have know the ABC of you know how to
[00:08:15] protect how to create a sandbox.
[00:08:18] I mean [snorts]
[00:08:21] that is the reality. Okay. So what I
[00:08:23] want to do I'm going to stop using uh
[00:08:25] OpenAI. I already stopped with uh uh
[00:08:29] Antropic months ago because it start
[00:08:32] they started to attack open source.
[00:08:35] Nobody should use open source. You must
[00:08:38] pay and you must pay us. Open source is
[00:08:41] dangerous. It's dangerous, but we can
[00:08:45] check your data, control what you do,
[00:08:48] and see if you behave. If you don't, we
[00:08:52] we block your account. Okay? Our most
[00:08:55] powerful AI only can be used by those
[00:08:59] corporation that we
[00:09:01] agree with, not yours. Okay? So, first
[00:09:05] you need to pay a lot. But money is not
[00:09:07] enough. It's about privilege. Privilege
[00:09:10] is given by them. So there is a citizen
[00:09:13] b citizen and then there is the citizen
[00:09:16] uh c the one that they don't have enough
[00:09:18] money to use them they can't use open
[00:09:20] source that is them entire that's what
[00:09:22] they're building that's why I can't use
[00:09:24] entropic anymore and uh openai which was
[00:09:28] the evil company before entropic become
[00:09:30] even more evil just go back to what they
[00:09:33] are okay they're just showing who they
[00:09:34] are unccapable people that their their
[00:09:39] core business is not to offer a service
[00:09:43] is to extract the data from us and make
[00:09:46] as much as money as possible.
[00:09:50] So today I'm frustrated and upset by
[00:09:52] everything that I'm saying it's what I
[00:09:54] believe just shared with the frustration
[00:09:58] and hunger that is connected to what is
[00:10:00] happening
[00:10:02] now on uh going back to Kimik K3.
[00:10:06] So there are so much demand that their
[00:10:09] server are full. They don't allow
[00:10:11] anybody to register for as a new
[00:10:15] subscribers.
[00:10:17] Why this is happening? It's uh like I
[00:10:19] said is because people are realizing
[00:10:20] about the problem but also because their
[00:10:23] model can do things that those frontier
[00:10:26] model from US can't because they are
[00:10:29] they have such a stronger derails that
[00:10:32] you can't do scientific research
[00:10:34] biology. No. Okay. Everything security.
[00:10:38] No. Why you should be secure? No. No.
[00:10:40] No. No. No. You can't fortify your
[00:10:42] software. Absolutely not. We can. You
[00:10:46] can't. Okay. That's their mentality. So
[00:10:49] those guard rails that are present
[00:10:51] inside those frontier model from US are
[00:10:54] not present in Timmy K3.
[00:10:58] So those model are open have use case
[00:11:01] scenario that those um US corporation
[00:11:07] can't cover
[00:11:10] and that is why people are going there
[00:11:12] now on the 27 if everything goes as
[00:11:16] planned they're going to release their
[00:11:19] weight. So meaning that another company
[00:11:21] with another server can just upload this
[00:11:25] Kim K3 and run it on their own server
[00:11:28] and therefore there are going to be more
[00:11:30] people having access to this model.
[00:11:34] One of the case scenario that I spoke in
[00:11:36] the other video which is a clearly and
[00:11:40] already you can see the demand for this
[00:11:43] is that you can use that model to train
[00:11:45] other models basically doing
[00:11:47] distillation. distillation meaning you
[00:11:50] have this Kim Mik tree as a teacher to
[00:11:54] train smaller model and and make them
[00:11:58] really really efficient
[00:12:02] that is a use case scenario that is
[00:12:04] completely blocked by the US corporation
[00:12:07] okay that is they build the system to
[00:12:10] really avoid this because they don't
[00:12:11] want their proprietary data knowledge to
[00:12:15] be stolen
[00:12:17] while anthropic just paid I don't I
[00:12:19] can't remember I think 1.8 eight
[00:12:20] billions fine for stealing data
[00:12:25] from other company and I think it was
[00:12:29] they stole I don't know many books and
[00:12:30] so on
[00:12:32] to train the AI and for me this idea I'm
[00:12:35] going to give you a fine then it's all
[00:12:37] sorted it's not enough because now you
[00:12:40] have a fine but then you make money of
[00:12:42] someone else work so the terms should
[00:12:46] change you use someone else's work now
[00:12:50] you can't make money from it. You pay
[00:12:52] the fine of course but then you can't
[00:12:54] make money out of it. So or you start a
[00:12:56] completely new training or you make your
[00:12:59] system open source open weights for
[00:13:02] everybody. Okay? Because that data was
[00:13:05] from someone else. You stole data from
[00:13:08] humanity. You give back to humanity.
[00:13:10] That's how it should be. It's that
[00:13:12] simple is human knowledge. Why that
[00:13:16] company without paying anything
[00:13:19] or anybody can
[00:13:22] actually
[00:13:24] make money out of it make it exclusive
[00:13:26] and then stops you to copy them they can
[00:13:30] copy but you can't okay the rule are
[00:13:33] different for them and for you and for
[00:13:36] me of course and that is the madness
[00:13:38] this is the thing that I can't stand
[00:13:40] anymore I can't stand anymore so today
[00:13:44] I'm extreme me frustrated. I went out in
[00:13:46] nature. I don't know if you can hear the
[00:13:47] background noise of this
[00:13:50] um I don't know the name, you know,
[00:13:51] those insect that makes noise. Uh but
[00:13:56] yeah, I wanted to share this with you.
[00:13:58] It's upsetting, but this doesn't remove
[00:14:01] the value of AI. AI still have a value,
[00:14:05] something to
[00:14:09] to use it for. And uh
[00:14:14] I'm I'm now running a lot of time local
[00:14:16] AI that is uh it has some limits
[00:14:19] sometimes can do things. Okay, this is
[00:14:22] why sometimes I use
[00:14:25] GPT 5.6 six or other models because I
[00:14:28] want to do other stuff that are more
[00:14:31] complex and my local model can't do it
[00:14:33] but it can't do 80% of the work and then
[00:14:36] when it can't I need to go to those uh
[00:14:38] cloud models and then get frustrated
[00:14:40] because even those cloud model can't you
[00:14:42] know it's like why
[00:14:46] what is the new strategy my thinking is
[00:14:50] this one
[00:14:52] is that that 20% could be another
[00:14:55] subscription with uh a different uh
[00:14:58] provider. Maybe on the 27th when uh new
[00:15:02] provider that will offer
[00:15:05] uh
[00:15:07] Kim K3. I will maybe subscribe to one of
[00:15:10] those. Uh there is also the new Quen
[00:15:14] coming out, but it doesn't seems to be
[00:15:16] as good as this Kim K3. I would do
[00:15:19] monthly subscription. I did in the past
[00:15:21] yearly subscription because it was a
[00:15:23] good deal. But in reality, yeah, it goes
[00:15:25] too fast. So today is Kimmy K3, tomorrow
[00:15:28] maybe is is the new Mini Max. Maybe it's
[00:15:31] the new Quen or whatever it is. So we
[00:15:34] need to be able to move. I don't need
[00:15:37] much. So at the moment with my $20 from
[00:15:40] GPT in reality was enough because like I
[00:15:44] said 80% of the work if not more I do it
[00:15:47] locally. And uh when I use uh
[00:15:53] GPT 5.6 there is two models that I use.
[00:15:56] Okay. One is Luna at max
[00:16:00] because it's extremely good. And then if
[00:16:03] Luna cannot do it then I go into soul
[00:16:07] whatever one of the top uh uh ultra high
[00:16:11] extra high or max I can't remember the
[00:16:13] names but so that is the two model that
[00:16:17] I use and but like I said most of the
[00:16:20] time Luna can do it and because Luna can
[00:16:23] do it not today okay today not even uh
[00:16:27] soul can could do it but because Luna
[00:16:29] can do it then you save a lot of money
[00:16:32] It's like uh 1 fifth almost 1/5 of the
[00:16:36] price of soul
[00:16:38] which is at max I'm talking uh
[00:16:43] which is insane.
[00:16:45] So $20 for what I do and because I use
[00:16:50] local models is fine. So I need to
[00:16:52] replace that that thing can be through
[00:16:54] API. I could replace
[00:16:57] Luna with the GLM uh 5.2 2 and soul with
[00:17:02] kimik3
[00:17:03] and pay through API and that's it as a
[00:17:06] power user. This is my frustration. This
[00:17:08] is what I think now as a person that
[00:17:11] create YouTube content and I create
[00:17:13] content for you at the same times I feel
[00:17:15] like yeah maybe I need to keep over
[00:17:19] just to you know to test and see.
[00:17:21] Anyway, thanks for watching until now.
[00:17:23] Sorry for this upsetting, you know,
[00:17:26] energy, but I needed to go out and share
[00:17:30] it with someone you. So, if you haven't,
[00:17:35] please like and subscribe. Let's help
[00:17:37] this channel to grow. I hope you enjoyed
[00:17:40] a little bit of green. I want to show
[00:17:42] you one more thing.
[00:17:44] This is my dog
[00:17:46] and that is the is the happiness the
[00:17:48] reason of uh everything I do.
[00:17:52] Ciao.
