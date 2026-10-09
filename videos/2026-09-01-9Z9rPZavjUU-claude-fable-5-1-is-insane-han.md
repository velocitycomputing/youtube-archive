---
record_id: "youtube:9Z9rPZavjUU"
video_id: 9Z9rPZavjUU
title: Claude Fable 5.1 Is INSANE – Hands-On With the BEST Model Yet!
channel: Bijan Bowen
url: "https://www.youtube.com/watch?v=9Z9rPZavjUU"
watched_date: 2026-09-01
watched_at: "2026-09-01T12:00:00Z"
watch_count: 1
duration_seconds: 2383
source: youtube-history-browser
added_date: 
history_label: Sep 1
history_order: 23
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 238
transcript_status: fetched
transcript_content_hash: ed6e8a716b1e729452800b471a585e35e5e936162d605d6b30cfdaa31b511b9b
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video is a hands-on test of Anthropic's newly released Claude Fable 5.1. It starts with the announcement. Fable 5.1 costs about 25% less than Fable 5 on typical per-token workloads, and its list price is unchanged at $10 per million input tokens and $50 per million output tokens. Anthropic says it has loosened the safeguards that used to halt chats and push users to Opus 4.8. The charts show it scoring higher than Fable 5 at slightly lower cost, and the post gives heavy attention to scientific research, including a neural net that mapped a third of Venus's elevation. The host is confused by a DeepSWE score of 67.4%, which doesn't seem to match the model beating GPT 5.6 Luna, so they flag it as needing more checking. They then run their usual tests on a Max 20x plan:
- **Browser OS:** about 1,570 lines on high effort. It had no right-click, but the GTA-style game inside it was good and the OS apps were wired together.
- **NYC C++ skateboard game:** about 1h10m. The first build couldn't ollie. After a roughly 3-minute follow-up fix, the host called it "incredibly well done," though they said Qwen 3.8 Max produced a competitive result on the same prompt.
- **Jerry's apartment (Seinfeld) 3D scene:** clean and detailed, but the layout is still wrong.
- **RB26 engine 3D-print model:** good, with a correctly shaped N20 motor and mostly support-free parts.
- **Watch render:** about 39 minutes on extra-high effort. The host was underwhelmed, with a missing strap piece and a weak strap design.
- **C++ racing game:** strong, with working gauges, backfire and lap timing.
- **Ultracode subway FPS:** over 3 hours, including 2 hours just on a design doc before any code. The result was impressive, with wave and train mechanics, bullet holes and varied enemies, though the carbine and shotgun looked odd.

The host hit the session limit during testing and has extra-usage credits set up as a fallback.

For you, the practical points are about cost and how to use the model. Fable 5.1 is cheaper per token only if you pay via the API. Subscription users get no price change, though the weekly Claude Code limit is 50% higher through September 13th. That date is already past (today is October 9, 2026), so check your current limits. Heavy tasks use a lot of quota. The C++ game and ultracode runs took 1 to 3+ hours and pushed the host to 100% of their session usage, so avoid ultracode for ordinary builds. Use high or extra-high effort for coding and build tasks. Expect to spend a quick follow-up prompt on bugs like the broken ollie, because the host's fix took about 3 minutes. If you were hitting the safeguard cutoffs on Fable 5, retry those prompts, since Anthropic says that behavior is improved. Spec-heavy 3D, C++ and game-style work looks like the strongest use case. The watch and apartment results suggest it is less reliably better on detailed visual or layout fidelity, so check those outputs by hand. The transcript was truncated, so the host's final verdict and any later tests aren't covered here.

## Transcript

[00:00:04] This is wave two. Oh,
[00:00:07] look at that. Claude Fable 5.1 has No,
[00:00:10] I'm kidding. Claude Fable 5.1 has just
[00:00:13] been released by Anthropic. And this is
[00:00:15] pretty exciting because Fable 5 when it
[00:00:17] came out felt like a proper next
[00:00:19] generation model. The experience that I
[00:00:21] had with that model, basically I made
[00:00:23] three separate videos testing it. So
[00:00:25] that should pretty much summarize how I
[00:00:27] felt about it. And I know that was
[00:00:28] reflected in a lot of other folks
[00:00:30] sentiment. So, as we can see right here,
[00:00:32] I did just receive this popup in the web
[00:00:34] UI saying Fable 5.1 is now available.
[00:00:37] Now, I still have not seen any
[00:00:38] announcement post on the Anthropic
[00:00:40] website. Perhaps if we refresh it right
[00:00:42] now, we will see one. All right. So, the
[00:00:45] announcement post just showed up here.
[00:00:48] All right. I mean, I'm already smitten
[00:00:50] with this UI. Look at this.
[00:00:53] I would hope that Fable 5.1 or Mythos
[00:00:56] 5.1 had created this. Probably Fable
[00:00:58] since it's not like trying to hijack my
[00:01:00] system. But all right, let's take a look
[00:01:02] at this. So Fable 5.1 will cost an
[00:01:05] estimated 25% less than Fable for
[00:01:08] typical workloads wherever usage is
[00:01:10] built by token. Oh, okay. So basically
[00:01:12] not if you're using it on a subscription
[00:01:14] like I would assume a lot of folks
[00:01:15] probably are unless you're enterprise.
[00:01:17] However, they've also mentioned here
[00:01:19] something that a lot of folks were
[00:01:20] extremely extremely bothered by. They
[00:01:22] have improved their safeguards. So,
[00:01:24] sometimes you may have noticed that when
[00:01:26] speaking to Fable 5, it would say the
[00:01:28] safeguards have stopped this chat and
[00:01:30] you can now use Opus 4.8. And sometimes
[00:01:32] you just couldn't continue depending on
[00:01:34] what specifically had triggered said
[00:01:36] safeguards. So, that's good to see as
[00:01:38] well. So, in this announcement post,
[00:01:39] basically, I've just combed over it to
[00:01:41] see what specifically here is worth
[00:01:43] highlighting. Interestingly, there's a
[00:01:45] lot of focus on something that I've not
[00:01:46] necessarily seen as prominently included
[00:01:48] in new model announcement posts, which
[00:01:51] is essentially the scientific research
[00:01:52] section. This, now, I'm not even going
[00:01:54] to pretend that I'm knowledgeable enough
[00:01:56] to refer to what exactly this is
[00:01:58] demonstrating, but I don't want to
[00:02:00] discount the fact that these models
[00:02:01] being used for more like maybe
[00:02:03] biological medical use cases like this
[00:02:05] is something that is probably going to
[00:02:07] be the hot thing of like now till 2030
[00:02:11] beyond, I would assume. So this is like
[00:02:13] important stuff. Even if I can't do it
[00:02:15] service by talking about it, I do just
[00:02:17] want to mention that it's something that
[00:02:18] should be appreciated for the good in AI
[00:02:21] and the capabilities that it had. They
[00:02:23] also talk about this which is kind of
[00:02:24] cool. It trained a neural net to create
[00:02:26] a new highresolution elevation map of
[00:02:28] the planet Venus or a third of the
[00:02:30] planet. So that's pretty darn cool and
[00:02:32] just showcasing some of its
[00:02:33] capabilities. With that though, I do
[00:02:35] want to make note of the small amount of
[00:02:38] benchmarks that we have here where we
[00:02:39] can see that in the ones included,
[00:02:41] obviously this is a significant leap
[00:02:43] over its biggest competitor, at least
[00:02:44] for the time being, which is GPT 5.6
[00:02:47] Soul. Interestingly, I like seeing how
[00:02:49] Opus 5 is really significantly
[00:02:52] outperforming Fable 5 based on these
[00:02:54] charts. Opus 5 was a very, very
[00:02:56] polarizing model. I think a lot of
[00:02:57] people don't like it, but I will say
[00:02:59] this thing was an absolute freak at
[00:03:01] doing like 3D game design and things
[00:03:03] like that. I was blown away with it. So,
[00:03:06] I'm pretty excited to see what Fable 5
[00:03:08] does in that same scope. Finally,
[00:03:09] pricing. It is the same price as Fable
[00:03:12] 5. $10 per million in and $50 per
[00:03:14] million out. Yes, extremely extremely
[00:03:16] expensive. However, fortunately, we will
[00:03:18] be mostly using this through a
[00:03:20] subscription today. I am using it on the
[00:03:22] Max $200 a month plan, which I believe
[00:03:25] is the Max 20X. And the final thing I
[00:03:27] want to mention that I am happy about is
[00:03:29] when we scroll back up and look at every
[00:03:31] single one of these specific charts, the
[00:03:33] main takeaway here is that it performs
[00:03:35] higher than Fable 5, however, at a
[00:03:37] slightly cheaper cost with a higher
[00:03:39] performance. So, we can basically see
[00:03:41] there and cost being on this axis. One
[00:03:43] final thing I did want to find, and I
[00:03:45] knew it would be in the big system card
[00:03:46] here, is the deep S. SWE is always one
[00:03:49] that seems to reflect my personal
[00:03:51] experience with the models.
[00:03:52] Interestingly, and I may be misreading
[00:03:54] this, but they said on Deepsw SWEV1.1,
[00:03:57] Fable 51 scored an average of 67.4% over
[00:04:01] five trials. Now, I am a bit confused
[00:04:04] about that because if we go in the chart
[00:04:05] right here, and it's entirely possible
[00:04:07] that I'm misreading this, so please keep
[00:04:09] that in mind. It does seem like that's
[00:04:11] not like
[00:04:14] I don't know how to parse this because
[00:04:16] I'm pretty sure this model is better
[00:04:17] than GPG56 Luna. So perhaps that's
[00:04:20] something that requires a bit of
[00:04:22] additional investigation, but I did just
[00:04:24] want to find some of the additional
[00:04:26] benchmark scores that I know would be
[00:04:28] expected to be shown in the introductory
[00:04:30] post right here.
[00:04:36] I also quickly want to just go over
[00:04:38] usage. So keep in mind we have two tasks
[00:04:41] running right now which have been for
[00:04:42] the past probably 10 or so minutes.
[00:04:44] Currently, our Fable usage is at 2% used
[00:04:47] and additionally the current session
[00:04:49] usage is 4% used. All models is 1% used.
[00:04:53] So, we'll be able to take a peek at
[00:04:54] this, but keep in mind weekly cloud code
[00:04:56] limit is 50% higher through September
[00:04:58] 13th. Now, I do believe yeah, I have
[00:05:02] about I had,00 in there. Okay. Well, I
[00:05:05] have a little under a,000 in extra usage
[00:05:07] credits in here just in case we need to
[00:05:09] continue testing beyond the usage
[00:05:11] limits. So, if we need to, we shall. I
[00:05:13] hope we don't, but we're ready. So, with
[00:05:15] that, our first test is just going to be
[00:05:17] initiated from within the web UI because
[00:05:19] it is the browser OS test v2.7. I am
[00:05:22] running this on high effort mode, which
[00:05:24] puts it kind of a little over the
[00:05:26] default, which would be medium, but not
[00:05:28] on extra or max, as this isn't a task
[00:05:31] that I would imagine is going to take a
[00:05:32] lot of intricate computation. However,
[00:05:35] in the meantime, I have also from within
[00:05:37] Claude Code right here on X high
[00:05:39] thinking mode started the C++ skateboard
[00:05:42] game test as well as that's one I'll be
[00:05:44] very very eager to see and I'd like to
[00:05:46] keep the tests that we run with this
[00:05:47] model pretty consistent over what we
[00:05:49] have historical reference points to on
[00:05:52] this channel. So, I want to have a lot
[00:05:53] of things that we can look back a couple
[00:05:55] model generations ago and see a direct
[00:05:57] reference to how the models perform then
[00:05:59] to how they do now with what I would
[00:06:01] assume is the best currently accessible
[00:06:03] model. Oh, okay. Good. I don't want to
[00:06:05] see it.
[00:06:08] I simply wish to download it and open it
[00:06:10] natively. All right. Here is our
[00:06:14] Fable 5.1 browser OS.
[00:06:18] H.
[00:06:24] Okay. First impressions. Eh, I'm not
[00:06:27] sold. There's no right click. Are you
[00:06:34] Let me go back and make sure like Yep.
[00:06:36] Okay. Nope. You are done. Wow. That's on
[00:06:39] high reasoning mode. How many lines of
[00:06:41] code is this?
[00:06:43] Not a lot. Only 1,57. All right. Let's
[00:06:46] just take a look at it. Trying not to be
[00:06:48] completely enraged by the fact that it
[00:06:49] did not put a right click. Though they
[00:06:51] did mention it's better at instruction
[00:06:53] following. Right click is not
[00:06:54] specifically in the instruction. So, we
[00:06:56] do have the time in the bottom right as
[00:06:58] well as a dollar figure and Aurora link.
[00:07:01] the special feature, one live nervous
[00:07:03] system that every app is wired into.
[00:07:05] Okay, it's very weird how now this is
[00:07:07] kind of like the thing that constantly
[00:07:09] becomes the special feature from a bunch
[00:07:12] of different models. HY4 Preview did
[00:07:14] this as well. So, it's just very very
[00:07:17] interesting. Does this work to full
[00:07:19] screen? Yes. Can we minimize it to the
[00:07:21] taskbar and reopen it? Yes. Okay. And
[00:07:23] we'll look at the special feature last.
[00:07:24] Let's take a look at our Gemini logo
[00:07:26] start menu. All right.
[00:07:29] Me at Aurora. Okay, simple. I these. All
[00:07:35] right, let's just look at our GTA clone.
[00:07:37] This is probably where this model will
[00:07:38] begin to differentiate itself. Yep, that
[00:07:41] is exactly Is there a little walking
[00:07:44] animation? A [laughter] not fully, but
[00:07:48] enough. All right, let's full screen
[00:07:50] this. No job right now. Check mail for
[00:07:53] work from cell. E is to get in. Q is to
[00:07:57] punch or click.
[00:07:59] Well, let's go find something to punch.
[00:08:01] This is very like low poly, but in a
[00:08:04] good way.
[00:08:06] All right. So,
[00:08:09] assault [laughter]
[00:08:11] $19. All right. 33.
[00:08:15] [laughter]
[00:08:17] All right. Yeah, this is kind of what I
[00:08:18] was expecting. Hello. Oh,
[00:08:24] [laughter]
[00:08:25] it's like a street eat.
[00:08:29] Okay, here comes the fuzz. Oh, can we
[00:08:32] Oh, we took it. We took the police car.
[00:08:34] [laughter]
[00:08:35] Uhoh. I'm trying to back up, but I
[00:08:38] can't.
[00:08:40] Oh, that's why. All right, this is this
[00:08:42] is good. Let's just explore the map a
[00:08:44] little, which we will need a vehicle
[00:08:45] for. I happen to like
[00:08:49] this shade of orange is acceptable. They
[00:08:51] do have mesh colliders on them. Okay,
[00:08:52] let me gonna need one that's actually
[00:08:55] able to be moved.
[00:09:00] Oh, it seems like we can't back up. All
[00:09:03] right, we can work around that.
[00:09:06] And the monetary figure in the bottom
[00:09:10] right here is going up as we play this
[00:09:12] game. All right, this was uh
[00:09:15] this was enjoyable.
[00:09:18] Simpler than some results in terms of
[00:09:20] the graphical fidelity, but definitely
[00:09:23] better. We have Void Runner, which is
[00:09:25] the generic space shooter type thing
[00:09:27] that for some reason all of these
[00:09:29] include. Okay, it's good looking.
[00:09:33] Playability is nice.
[00:09:38] And I like the little like jet effects
[00:09:41] behind the engines. Oh, that was like an
[00:09:44] enemy ship. They're shooting at us.
[00:09:46] Those orange things are ammunition. All
[00:09:47] right, let's see what happens if we
[00:09:49] perish.
[00:09:50] [snorts]
[00:09:51] Ship lost. Okay, not bad. What's next?
[00:09:54] Mail.
[00:09:57] Good. Typical as one would expect. And
[00:10:00] the games are like there's meta male
[00:10:02] references. Basically, that is the
[00:10:04] special feature is like the games are
[00:10:06] intertwined with everything else in the
[00:10:07] OS. Totally legit. You have won a free
[00:10:10] boat and it's tagged as spam. I like
[00:10:12] that. Congratulations. You're the
[00:10:13] millionth user. Reply with your bank
[00:10:16] details to claim
[00:10:18] terminal
[00:10:28] notes.
[00:10:30] All right. younote.
[00:10:33] Simple. Basically, the games looked
[00:10:35] really good. The rest of this is kind of
[00:10:36] just the traditional what you would
[00:10:38] expect here.
[00:10:40] Ah, select a text file to preview or
[00:10:42] edit it. That's what I'm trying to do.
[00:10:44] Oh, wait.
[00:10:47] Oh, that's actually kind of cool. Our
[00:10:48] records, our game scores. Okay, another
[00:10:52] demonstration of the special feature.
[00:10:54] 27*
[00:10:56] 6. I should know that. 162. Yeah.
[00:11:00] divided by nine.
[00:11:02] Oh, it shows you right there in the
[00:11:04] preview. So, obviously 18 settings. All
[00:11:08] right, let's take a look at some other
[00:11:09] backgrounds. Okay, synth wave horizon.
[00:11:12] Oh, if it had opened with this, I would
[00:11:13] have been so much more enthused. Nebula
[00:11:15] drift or this. We have motion speedroll.
[00:11:19] So, we have different seeds to generate
[00:11:21] like different styles of OS. They're
[00:11:23] kind of like they almost look pixelated
[00:11:26] like they're being scaled too much. We
[00:11:27] can change our account, username, accent
[00:11:29] colors. Good. And that does take effect.
[00:11:32] Finally, Aurora link, which is just the
[00:11:34] special feature. Can I type in this? Oh
[00:11:36] no, it just gives me a cursor for some
[00:11:38] reason. And it's basically just about
[00:11:39] like this event list of everything we've
[00:11:41] done, the live bus monitor and saying
[00:11:43] like games can send emails and things
[00:11:45] like this. So that was the special
[00:11:46] feature there. There was no right click,
[00:11:48] but the GTA game was quite good. All
[00:11:50] right, after 54 minutes, basically, it
[00:11:53] seems our C++ skate game has compiled
[00:11:56] cleanly, aside from two minor warnings.
[00:11:58] Now, it's still not ready to give us the
[00:12:00] final thing. It's going to run it
[00:12:01] headlessly, take some screenshots, and
[00:12:03] just make sure that everything works
[00:12:04] well. Okay, right as I was going in
[00:12:06] cursor just to see if this was
[00:12:08] available, we got our first like micro
[00:12:10] tease of this game that just popped up
[00:12:12] for half a second right here. It looked
[00:12:14] really impressive and promising for a
[00:12:16] bit now. Interestingly enough, this has
[00:12:18] been working for an incredibly long
[00:12:20] time. Just like doing very niche things
[00:12:23] like I found a respawn bug where the
[00:12:25] rider spawns inside a handrail collider.
[00:12:27] The river isn't visible because of the
[00:12:29] ground plane. Then a flat rail blocking
[00:12:31] the quarter pipe runup. So it's doing a
[00:12:33] lot of things. A physics bug in the
[00:12:35] quarter pipe where transitioning from
[00:12:36] vertical to flat wrongly converts. So
[00:12:39] it's doing a lot of like real like edge
[00:12:42] case fixing. And just like that, we're
[00:12:44] receiving our end like summary of this.
[00:12:47] It is done and verified. And this took
[00:12:49] an hour and 10 minutes. All right. So,
[00:12:51] here is our NYC C++ skate game. Okay,
[00:12:55] this looks good. There are pigeons
[00:12:57] moving around. Can we get rid of the Oh,
[00:13:01] H for hide. Okay, good. Let's hide that
[00:13:03] for
[00:13:13] jump you imple.
[00:13:19] Okay, that's ah it's Look at the person
[00:13:22] sitting on the bench. I'm noticing good
[00:13:24] and I'm noticing bad. Look at the
[00:13:26] basketball court.
[00:13:28] All
[00:13:29] >> [laughter]
[00:13:30] >> right. The biggest problem I'm noticing
[00:13:32] is we can't ollie. It's like it's it's
[00:13:36] like primed for the ollie. Oh, the
[00:13:38] pigeons fly away. All right. It's just
[00:13:40] this sort of stuff that's really like
[00:13:46] space. Hold and release is ollie. Well,
[00:13:48] that's what I'm trying to do. But this
[00:13:51] is very good.
[00:13:54] the water like the fire hydrant with the
[00:13:58] water. I'm just trying to manual to
[00:14:00] nose.
[00:14:02] Something's not right with like the key
[00:14:04] press events, I'm going to say. And also
[00:14:07] the
[00:14:08] the bail logic is pretty well done.
[00:14:12] And we can run over pedestrians. Oh, we
[00:14:14] fell as well.
[00:14:16] The big issue is this darn ollie logic.
[00:14:20] Look at the bridge. the massive amount
[00:14:22] of buildings over in like the distance.
[00:14:26] Now, can we uh Good. Good. That's kind
[00:14:28] of It's kind of what I was looking for.
[00:14:31] Really, the big hang up here and the big
[00:14:33] thing that's preventing this from being
[00:14:34] like top tier is the Okay, that maybe,
[00:14:39] but also like the Ollie not fully
[00:14:41] working. [sighs] This needs a little bit
[00:14:44] of work.
[00:14:46] I'm giving it the followup here.
[00:14:47] Normally I wouldn't do this, but I mean
[00:14:49] if we look at this as a scene right here
[00:14:51] and like, yeah, this is self-contained
[00:14:52] C++ game. The fact that the pigeons fly
[00:14:55] away. There are people Whoops. There are
[00:14:57] people sitting on benches out by the
[00:14:59] water. The distant buildings we can see
[00:15:01] in the water as well. The way the
[00:15:03] interaction works with pedestrians when
[00:15:05] we bail the basketball court. Is that
[00:15:07] like the Staten Island Ferry? Jeez. So,
[00:15:09] this took just under 3 minutes to fix
[00:15:11] the skate game result. I was a little
[00:15:13] concerned we'd end up having to wait a
[00:15:15] long time again. However, that did not
[00:15:17] seem to be the case. Let me just make
[00:15:18] sure that it did rebuild this version.
[00:15:20] Good. It did. All right. So, we should
[00:15:23] get a little more. And the tips of the
[00:15:25] boards, like the edges are now pointed
[00:15:27] the right way, which is kind of what we
[00:15:28] wanted. So, let's see. Good. Good. All
[00:15:30] right. This is like
[00:15:34] [laughter] this is incredibly well done.
[00:15:36] I have to say though, the Quen 3.8 Max
[00:15:38] result that I received for this specific
[00:15:41] prompt was competitive with this, which
[00:15:43] is quite quite something. Now, that is a
[00:15:46] 2.4 trillion parameter model. It is open
[00:15:49] weight. Now, at 2.4 trillion parameter,
[00:15:51] that's not a big thing. Like, it's hard
[00:15:54] to run that, but oh, look at this. Yeah,
[00:15:56] now that we actually have functional
[00:15:58] like skate mechanics and things like
[00:16:00] that. Just the momentum that the player
[00:16:02] has when actually performing these
[00:16:04] tricks for a result like this is pretty
[00:16:06] darn well done. The NPC's movement is
[00:16:10] good. Let's see if there are any other
[00:16:11] tricks that I've 360 flip. L is a pop
[00:16:14] shove it. Yep. U was the 360 flip. Okay.
[00:16:19] And that's harder to land, I would
[00:16:20] imagine, just because in real life it
[00:16:22] would be good. We can like pretty much
[00:16:24] grind on a lot of the stuff here. I want
[00:16:26] to see if we can grind around the
[00:16:27] fountain. That'd be kind of cool.
[00:16:30] Yeah, we can.
[00:16:32] And A and D are for balance when
[00:16:34] grinding.
[00:16:38] This is really, really well done. Check.
[00:16:40] Cashing subway.
[00:16:43] All right, I'll do like one like mega
[00:16:45] jump.
[00:16:48] [snorts] Mega jump.
[00:16:52] Oh, nice. And we got points. That's the
[00:16:54] first time I've received points here.
[00:16:56] That's upsetting. And the traffic comes
[00:16:59] and goes.
[00:17:00] Oh, okay. That's like a the bounds of
[00:17:04] the map. Oh, I think we got out of it.
[00:17:10] All right. Yeah, this is this is very
[00:17:12] very very impressive. I will actually
[00:17:14] keep this result. I usually just like
[00:17:16] wipe the system after, but this one I
[00:17:18] think can stay. So, from the web chat
[00:17:21] interface here, I'm giving it this photo
[00:17:22] of Jerry's apartment from Seinfeld and
[00:17:25] the traditional Jerry's apartment test
[00:17:27] because this is one that we've run over
[00:17:28] a number of different older models. So,
[00:17:30] to be able to see how the brand new
[00:17:32] state-of-the-art model does with this, I
[00:17:34] think will be pretty cool to see. And
[00:17:35] again, doing it from within this chat
[00:17:37] interface right here is not nerfing it
[00:17:39] at all. Weighing copyright concerns
[00:17:40] against architectural authenticity.
[00:17:42] Okay, good. It's now moved on to
[00:17:44] architecting architecting the spatial
[00:17:46] layout. So, no concerns. All right, so
[00:17:49] we have received our Jerry's apartment
[00:17:51] right here. Let's just take a peek. All
[00:17:52] right, so here is Jerry's apartment.
[00:17:55] This is definitely I mean it looks good.
[00:17:58] Still to this date, I've not received
[00:18:00] any results for this that's actually a
[00:18:03] proper replication of the specific
[00:18:05] apartment in terms of the layout. But if
[00:18:07] we judge these just based off of some of
[00:18:09] the fine detail that they have right
[00:18:11] here, this is definitely a good-looking
[00:18:13] one. It even did include the buzzer and
[00:18:15] the multiple locks on Jerry's door. So,
[00:18:17] these are some bits of detail that I've
[00:18:19] not seen previously. However,
[00:18:21] unfortunately, it's not quite there in
[00:18:24] terms of the layout, but it is kind of
[00:18:27] close. We do have the computer in the
[00:18:29] corner. However, I do believe it should
[00:18:30] be on that wall, not in front of the
[00:18:33] window there. The TV is also should be
[00:18:35] there. The bike is actually quite well
[00:18:38] done, even though it's it's in the wrong
[00:18:40] hanging orientation. We do have the
[00:18:42] bookshelf. Let's see if we can actually
[00:18:44] go in. Okay, there is a bathroom. Now,
[00:18:46] this by itself is pretty good looking, I
[00:18:48] would say. Um, for a second, I was like,
[00:18:50] let's see if we can see oursel in the
[00:18:52] mirror. I'm not quite sure why that just
[00:18:53] came to mind. And then the bedroom as
[00:18:55] well with I believe those are sneakers
[00:18:57] on the ground. Okay. Interesting though,
[00:19:00] like I'm not seeing Porsche posters and
[00:19:03] things like that, which sometimes models
[00:19:04] will often include here. It seemed to
[00:19:07] really ensure that it didn't use
[00:19:09] anything that may be a sort of copyright
[00:19:12] issue and making generic
[00:19:14] like cereals and things like that. So,
[00:19:16] overall competent and well done. But,
[00:19:18] okay, I do like the clear cabinets and
[00:19:21] things like that. Let's just see
[00:19:22] dollhouse mode. Oh, that's actually
[00:19:24] quite cool. That just gives us more of
[00:19:26] like a dollhouse look of it. And then we
[00:19:28] do also have the apartment uh hallway.
[00:19:30] And then Kramer's door would be right
[00:19:32] there. And we have go straight to
[00:19:34] specific presets for our camera bedroom
[00:19:37] hallway.
[00:19:39] Good. So overall, not bad. Very clean,
[00:19:42] but not super like
[00:19:46] super, I guess. So from within cursor,
[00:19:49] I'm using this on extra high and I'm
[00:19:51] giving it the 3D model test where it
[00:19:53] needs to create a detailed but 3D
[00:19:55] printable model of a twin turbo inline 6
[00:19:57] engine. In this case, something called
[00:19:59] the RB26, famous for being in the Nissan
[00:20:02] Skyline and things like that. It also
[00:20:04] needs to have the cavity inside where
[00:20:06] it'll fit a tiny little remote control
[00:20:08] car motor inside of it. And it needs to
[00:20:10] be created so it's optimized for 3D
[00:20:13] printing with little to no support
[00:20:14] material needed. Again, this is through
[00:20:16] cursor using Fable 51 on extra high. All
[00:20:19] right, so we've received our 3D model of
[00:20:22] an engine that is designed so it can be
[00:20:24] 3D printed and actually fit inside of it
[00:20:26] a tiny little remote control car motor.
[00:20:28] So, I want to just take a look at the
[00:20:30] SCAD document or SCAD file itself prior
[00:20:33] to anything else. Okay, now this
[00:20:37] I just wonder are the turbos on the
[00:20:39] wrong side for this engine? I don't
[00:20:41] actually know off the top of my head.
[00:20:43] That's something I may have to verify.
[00:20:45] However, on first glance, this looks
[00:20:47] very, very good. The accessories are
[00:20:49] there. Even like um pulleys, I think
[00:20:52] there's an alternator there as well. The
[00:20:54] intake manifold and then the actual text
[00:20:56] written on the top of it. And even the
[00:20:58] height for the valve cover, like there
[00:21:00] is kind of a valley like this in
[00:21:02] between. We have an oil cap. We also
[00:21:04] have the exhaust manifolds as well as
[00:21:06] the turbochargers, which are a bit
[00:21:09] funky, but they do actually seem like
[00:21:11] they would fit into this more or less.
[00:21:13] And then the oil pan as well, which I am
[00:21:15] a little concerned in how that will be
[00:21:16] for 3D printing, but I do see a hole
[00:21:19] there. And I wonder if that would be for
[00:21:21] some form of like wire management. I
[00:21:23] want to look at these individually so we
[00:21:25] can assess how well this is actually
[00:21:27] going to be 3D printable in real life.
[00:21:29] But based off of a first look right
[00:21:31] here, it seems to be a well done model.
[00:21:33] All right, so here's our block. Good.
[00:21:35] And keeping in mind that it needs to fit
[00:21:36] the tiny little N20 motor inside of it,
[00:21:39] which it does have this for. And it also
[00:21:41] has like that shape up top, so there's
[00:21:44] more overhead and less likely to need
[00:21:46] support in that specific area, which is
[00:21:48] well done. And then the hole there
[00:21:50] definitely does seem like it would be
[00:21:51] for some form of wire management. So, so
[00:21:53] far so good. I do like what I'm seeing.
[00:21:55] Nothing here seems like it would present
[00:21:57] too much of an issue. Maybe these posts
[00:22:00] could be a bit difficult to get in
[00:22:01] midair, but more or less seems okay. All
[00:22:04] right, let's move on. Let's see what
[00:22:05] other pieces would be like directly
[00:22:07] related to touching that. I want to
[00:22:09] check at the oil pan because it seemed
[00:22:11] like unless it's completely solid seemed
[00:22:14] like it could pose some difficulty. So,
[00:22:16] if we go under this. Oh, no, it is.
[00:22:18] Okay, good. So, it did properly do that.
[00:22:20] And then there's just the hole there for
[00:22:22] the wire management. And it also does
[00:22:24] have these like pegs for the mounting
[00:22:26] system of assembling each piece of this,
[00:22:28] which is cool to see as well. So
[00:22:30] basically if we go in right here, but
[00:22:32] it's always cool to look at it in the 3D
[00:22:34] slicer and the printer program as well,
[00:22:36] just so we can see if it's actually like
[00:22:37] printable without supports. Ah, the
[00:22:40] intake. Okay, that I think would be kind
[00:22:42] of difficult to print as is, but the way
[00:22:45] it actually kind of tapered these would
[00:22:48] make it a bit more doable, I would
[00:22:50] think. Exhaust front. Okay, good. And
[00:22:53] again, like we have pieces for the peg
[00:22:55] mounting system. Exhaust rear turbo
[00:23:00] good not bad and more or less printable
[00:23:03] actually fan. This was well done. I
[00:23:06] liked the fan and it seems like that is
[00:23:08] properly sized for the shaft of the
[00:23:10] little M20 motor. So it just assumed
[00:23:12] that the motor would go inside this to
[00:23:14] spin the fan which does make sense.
[00:23:16] Crank pulley. Good. And it's even ribbed
[00:23:19] how it would be kind of in real life. So
[00:23:21] that's nice attention to detail there.
[00:23:23] Alternator.
[00:23:24] All right. Not bad. And it has a peg
[00:23:26] there to go into the block. N20 dummy.
[00:23:29] Excellent. Good. And it does have the
[00:23:31] gearbox. And most models don't get the
[00:23:34] proper shape of the N20 motor. This did.
[00:23:36] And it also has, although the post
[00:23:39] coming out of it is not 100%. It does
[00:23:41] have like a cut right there. But that
[00:23:43] works well enough. So overall, this was
[00:23:45] actually quite well done, I would say,
[00:23:48] and definitely something that could like
[00:23:49] snap together or snap fit. So not bad.
[00:23:52] And that was just done from within
[00:23:54] cursor with this model on extra high.
[00:23:59] All right, I'm trying my best. Now I'm
[00:24:01] looking at this. I noticed this had
[00:24:05] shown up here. Our watch result.
[00:24:07] Interesting. It's good. And is it
[00:24:10] matched to the local time? Folks had
[00:24:12] mentioned one of the other models did
[00:24:13] that and I had neglected to notice that
[00:24:15] this is matched to the local time. Okay,
[00:24:17] so I like seeing that. The big issue I'm
[00:24:18] noticing is the piece for the strap is
[00:24:21] missing one on this side and one on that
[00:24:23] side. Overall, I'm actually not as
[00:24:26] impressed with this as I had hoped to be
[00:24:28] just based off of some of the previous
[00:24:29] results I've been seeing from other
[00:24:31] significantly cheaper models. So, it's
[00:24:34] well done. The materials of the table
[00:24:35] are nice and things like that. However,
[00:24:37] the actual watch itself I'm not as blown
[00:24:40] away by as I had expected to be. Why did
[00:24:42] it open this in a browser artifact? All
[00:24:44] right, so here's it natively. it it
[00:24:46] opened it in a browser artifact for some
[00:24:48] reason. And basically, we have the same
[00:24:50] here. So, overall, I'm actually not as
[00:24:52] impressed with this as I was hoping to
[00:24:54] be. Let's scroll down and see if the
[00:24:56] separate renders or the exploded view
[00:24:59] kind of changes our opinion of that at
[00:25:01] all. Okay, that looks nice. Separated
[00:25:05] out, it looks nice. The face of the
[00:25:06] watch is much better. However, we're not
[00:25:08] seeing any of the actual movement. Okay,
[00:25:11] so it's behind this piece, right? Okay,
[00:25:14] good. That's kind of what I had wanted
[00:25:15] to see. There is a bit of some troubled
[00:25:19] um gear arrangement there and things
[00:25:21] like that. However, the way that this
[00:25:22] movable piece actually is branded slapis
[00:25:25] is kind of cool. And we can move this
[00:25:27] around to see different pieces of it. It
[00:25:29] almost seems like the face plate is
[00:25:31] actually being blocked from rendering
[00:25:33] the text that it had placed on it in the
[00:25:35] hero section, which would make sense now
[00:25:37] cuz I wouldn't have expected it to be
[00:25:38] that kind of mid, truth [snorts] be
[00:25:40] told. And if we scroll down right here,
[00:25:43] okay, we have the different versions and
[00:25:45] the strap design, unless that was a
[00:25:48] purposeful choice, is kind of letting it
[00:25:50] down a bit as well. The leather strap on
[00:25:52] this one looks good. Overall, I have to
[00:25:54] say I'm not actually super blown away by
[00:25:56] this one, especially considering that
[00:25:58] this took around 39 minutes and the
[00:26:01] specific setting that this was run on
[00:26:04] was on extra high. So, that was on
[00:26:07] fable, right? I want to just make sure.
[00:26:10] Yeah, it's on Fable 51. Okay, I'm not as
[00:26:13] impressed with this truthfully as I had
[00:26:15] expected to be. It's good, but it's not
[00:26:19] $50 per million. How good. All right,
[00:26:20] even though we're tapped out at 100%
[00:26:23] used right here, I'm aware of that. So
[00:26:25] hopefully it just transitions into extra
[00:26:27] usage billing cuz I do have it toggled
[00:26:29] that it could swap over if we do hit the
[00:26:31] session limit. I'm giving it another C++
[00:26:33] test because I think that's going to
[00:26:35] show us more capability on the part of
[00:26:37] the model. This is one that's been
[00:26:38] sparssely run. Although I will say the
[00:26:40] Quen 3.8 next model that I previously
[00:26:43] tested did an absolutely stellar job on
[00:26:45] this prompt almost to a point of like it
[00:26:48] was shocking. If the result that had
[00:26:50] made was produced right here by Fable
[00:26:52] 51, I'd be completely impressed with it
[00:26:55] still. So keep that in mind. But I want
[00:26:57] to do something else that is still a
[00:26:58] little more difficult than just the
[00:27:00] traditional 3JS result, but also kind of
[00:27:02] fun. So, I believe it was like 40 or 50
[00:27:04] minutes total for the C++ racing game.
[00:27:07] And I had stopped it because it had
[00:27:09] already opened it and it looked really
[00:27:10] good. So, I said just focus on making
[00:27:12] the interior of the car look a bit more
[00:27:14] detailed and also add some fun sound
[00:27:16] effects or something like that. So, I
[00:27:18] think we're actually going to have a
[00:27:19] pretty decently playable game right
[00:27:21] here. Yeah, look at that. I mean, it
[00:27:24] drew this itself. For some reason, this
[00:27:25] computer is lagging real bad.
[00:27:32] It has a mirror. It has a shifter.
[00:27:37] Do we have like an
[00:27:40] That was weird like car alarm noise. The
[00:27:43] gauges do actually work. We do have some
[00:27:45] visible shifter and then again the
[00:27:47] rearview mirror. I'm going to say though
[00:27:49] still the Quen next result for this
[00:27:51] prompt was like a freak. It was totally
[00:27:53] unexpected to receive that. But it even
[00:27:56] has like some backfire when you let off
[00:27:57] the gas.
[00:27:59] So, that's a nice touch.
[00:28:02] What happens if we go off road? Okay.
[00:28:05] And it actually changes [music] right
[00:28:06] here to show us what scenery we're on.
[00:28:09] Let's just see if we drive off the
[00:28:10] mountain. Yep. Okay. Can we go in the
[00:28:15] water or I think that's what this is.
[00:28:18] Yep. Oh, cool. Okay. Let's restart.
[00:28:27] All [music] right. And the lap time
[00:28:29] counter did work. I wanted to go around
[00:28:31] the track at least once. And this uh
[00:28:34] this looks really good. All right, let's
[00:28:36] do the subway FPS game, but on ultra
[00:28:38] code. So, keep in mind this is just a
[00:28:40] little ridiculous, like overkill in
[00:28:42] terms of the mode it's in and the usage
[00:28:44] and how long it may take. However, this
[00:28:46] is a slightly different version of the
[00:28:48] subway FPS. It was timed probably for
[00:28:50] version 2.5. Make a beautifully detailed
[00:28:53] web scene using JS of a subway station
[00:28:55] with focus on detail. It should be 3D in
[00:28:58] something that would be impressive to
[00:28:59] you. The scene must be the setting for
[00:29:01] an FPS with humanoid/zioid,
[00:29:03] which I know is not a word. Enemies,
[00:29:05] visible ammo tracers, weapon recoil, at
[00:29:07] least two different weapons, muzzle
[00:29:09] flash, sound effects, and detail. The
[00:29:11] first wave should be simple. When the
[00:29:13] first wave is cleared, a train should
[00:29:14] pull into the station and open its doors
[00:29:16] to let out the enemies for wave two with
[00:29:19] difficulty increasing until the player
[00:29:21] loses. Use 3JS. Create the result as
[00:29:23] something playable in the browser. And
[00:29:25] again on ultra code so it will probably
[00:29:28] uh take a bit of time and money
[00:29:32] [laughter]
[00:29:33] a bit of time a lot of money don't use
[00:29:37] ultra code after 2 hours it has not
[00:29:40] written a single piece of the game it's
[00:29:41] still doing the design workflow the
[00:29:43] design markdown is still the design
[00:29:45] phase took longer than I would have
[00:29:46] liked it came up with this a design
[00:29:49] document it it genuinely spent 2 hours
[00:29:52] in ultra code coming up with this design
[00:29:54] spec And I had not realized that it was
[00:29:58] it had not written a single line of
[00:29:59] code. All right, after like 3 hours and
[00:30:03] something minutes and a very long time,
[00:30:05] our subway FPS is more or less
[00:30:07] completed. Well, it's completed. So, all
[00:30:10] right, let's just
[00:30:12] click to enter.
[00:30:14] Okay, [snorts]
[00:30:16] my rage is so significantly quelled by
[00:30:20] the at least initial look at this. Now,
[00:30:22] it seems to have started off. For some
[00:30:24] reason, the tab is muted, which I didn't
[00:30:26] do, but all right.
[00:30:31] So, the benches are oriented. The tilt
[00:30:34] is wrong. So, unfortunately, this is a
[00:30:36] failure. No, I'm kidding. All right.
[00:30:39] So,
[00:30:41] wow.
[00:30:48] They're even wearing different outfits.
[00:30:51] [laughter]
[00:30:55] Look at this shell casings falling. Do
[00:30:57] bullet holes appear in the environment?
[00:30:59] Yes.
[00:31:01] Pure taste. Okay. A phone thing. Yeah,
[00:31:04] they do. Look at that.
[00:31:09] I'm going to reload now. We also have
[00:31:11] different weapons. So Oh, what the heck
[00:31:13] is that?
[00:31:19] Shotgun. The the weapons seem to be a
[00:31:22] bit odd. At least the carbine and the
[00:31:24] shotgun do. The pistol looks great.
[00:31:26] Okay, we have three weapons. So,
[00:31:28] [snorts]
[00:31:29] check this out.
[00:31:42] This is wave two. Oh,
[00:31:46] look at that.
[00:31:59] >> [laughter]
[00:32:00] >> What the heck? Hurry up and reload. Oh,
[00:32:04] okay. We need a different weapon.
[00:32:07] This is sick.
[00:32:09] Adding in the train thing where the
[00:32:12] train comes in for the next wave and
[00:32:14] then has them spawn in. That is a a very
[00:32:22] next train in 1 second. Look at the red
[00:32:26] like Oh man, [clears throat]
[00:32:28] [snorts]
[00:32:38] the footsteps. Wait, what was that? E to
[00:32:41] resupply. Nice.
[00:32:44] Oh, cool. We can clip them before they
[00:32:46] get out of the I don't like this one.
[00:32:48] This one. Okay, they're all running.
[00:32:50] It's doing like the Actually, I can't
[00:32:52] say that.
[00:32:56] Can we jump? No, we can't. I'm going to
[00:32:58] change to the shotgun.
[00:33:11] Oh man, look even inside the train. This
[00:33:13] is sick. This is
[00:33:20] Is it better than Opus 5? I think
[00:33:22] because of the improved logic. Oh crap.
[00:33:26] All right.
[00:33:27] So, more enemies come as the waves
[00:33:30] increase.
[00:33:34] Look at the fence. No, like authorized
[00:33:36] personnel only. Uhoh.
[00:33:40] Oh, what the heck?
[00:33:44] Uhoh. I don't have a good feeling about
[00:33:46] this.
[00:33:48] I don't think we're going to survive
[00:33:50] wave five.
[00:33:52] All right. All right. All right. All
[00:33:53] right.
[00:33:56] Oh, yeah. Look at that.
[00:34:01] All right.
[00:34:08] Oh, that was stupid.
[00:34:24] And then we just respawn.
[00:34:27] All right. Well, aside from the missing
[00:34:30] trash can skin and the weird benches,
[00:34:33] look at the reflection of the light in
[00:34:35] the puddle.
[00:34:40] And the bullet effects actually sound
[00:34:42] different depending on the material
[00:34:45] we're hitting.
[00:34:52] All right, this was this was excellent.
[00:34:54] That was really really really really
[00:34:56] well done. So, let's take a look at our
[00:34:58] usage statistics. Obviously, our current
[00:35:00] session was tapped out pretty early on.
[00:35:02] All models resetting Wednesday, 20%
[00:35:05] used. Fable only 40% used. And now to
[00:35:08] see how much we actually spent in
[00:35:09] addition to our plan, $156 spent. And
[00:35:13] that's having used this through API only
[00:35:16] usage cuz that's the additional usage
[00:35:18] credit. So keep in mind like when things
[00:35:20] happen like when the limits get cut and
[00:35:22] eventually if these models do not become
[00:35:25] as subsidized as they are currently with
[00:35:27] these subscription plans it's going to
[00:35:29] be very very expensive to use these. So
[00:35:31] that's why I think it's really important
[00:35:32] to have decent cheaper models one
[00:35:35] openweight models as well that can do
[00:35:37] some of the work locally. I suppose for
[00:35:39] a quick results overview the browser OS
[00:35:41] was decent. The GTA game within it was
[00:35:45] definitely very well done. I liked how
[00:35:47] we could actually also like assault
[00:35:49] folks just like by punching as well.
[00:35:51] Something that's not always included
[00:35:52] with these results. The rest of the
[00:35:54] browser OS, look at the way that the
[00:35:56] police sirens are actually showing up in
[00:35:58] the desktop. The rest of it was kind of
[00:36:01] part of the course. I didn't see
[00:36:02] anything that really blew me away, but
[00:36:04] it was well done. Our skate game was an
[00:36:06] absolute masterpiece once the original
[00:36:08] issues were fixed where we couldn't
[00:36:10] actually ollie and the menu couldn't be
[00:36:12] hidden. This was excellent. the
[00:36:14] attention to detail like how the pigeons
[00:36:15] actually flew away and things like this.
[00:36:17] The bail effects going down to basically
[00:36:20] like the pier if we can get there.
[00:36:21] Seeing all the tall buildings in the
[00:36:23] distance, of course, the smoke coming
[00:36:24] out of the manhole cover, the basketball
[00:36:27] court, the bridge, people on the bench
[00:36:29] that we can still actually run into.
[00:36:31] Just totally, totally awesome. This was
[00:36:33] really, really enjoyable to play and it
[00:36:35] had very nice attention to detail. The
[00:36:37] watch website was honestly a bit
[00:36:39] disappointing compared to what I would
[00:36:41] have anticipated. Yes, it did show the
[00:36:43] specific time in our local based off of
[00:36:45] our computer's clock, which was a nice
[00:36:48] bit of attention to detail, but it was
[00:36:50] missing like the other half of where the
[00:36:51] strap would mount to. And then when we
[00:36:53] scroll down, we realized in the exploded
[00:36:55] view that some of the issue was that the
[00:36:57] embissive properties of this glass lens
[00:36:59] were covering up fine detail in the
[00:37:02] face, but even then, it didn't like some
[00:37:04] of the gears here were a little crooked
[00:37:06] and things like that. So, I've seen
[00:37:08] better from cheaper models, especially
[00:37:10] when you factor in like this should be
[00:37:12] really really exceeding everything. So,
[00:37:14] this one was good, but like not all
[00:37:18] there. Kind of the same can be said
[00:37:20] about the Jerry's apartment result. It
[00:37:21] was very nice, well done, and well put
[00:37:23] together, but like it didn't even have
[00:37:25] drawings or posters of like the Porsche
[00:37:27] that are pretty commonly included when
[00:37:29] we do this test. I don't know if that
[00:37:31] was on purpose to try to avoid like any
[00:37:33] copyright concerns, but in keeping with
[00:37:35] doing this test, still to date, no model
[00:37:38] has really properly pulled the accurate
[00:37:40] floor plan as it would look to someone
[00:37:42] seeing it. This included some nice
[00:37:43] things like the buzzer and the multiple
[00:37:45] locks on the door. I didn't even
[00:37:47] actually notice that before, so that's
[00:37:48] cool. Some things that were not always
[00:37:50] included. Now, we can't go into Kramer's
[00:37:53] apartment, but it had a nice job with
[00:37:54] the hallway and the door opening and
[00:37:56] things of that sort. Our C++ retro rally
[00:37:59] game was really well done.
[00:38:06] I mean, the lap timer worked. We did a
[00:38:08] full lap with it, and it just had nice
[00:38:10] detail. The way the gauges actually work
[00:38:12] for speedometer and RPM, and the way
[00:38:14] that we actually see in this little
[00:38:16] heads up display what surface we're on,
[00:38:18] and the map itself was just really nice
[00:38:20] and like well done, especially
[00:38:23] considering it couldn't use
[00:38:25] dependencies. So, for this to be a
[00:38:27] self-contained C++ result, even just
[00:38:30] looking at the terrain generation that
[00:38:31] we can see when it's in the start
[00:38:33] screen, this was very, very competent.
[00:38:35] The 3D model of the engine was also well
[00:38:37] put together, and it seemed like it
[00:38:38] would print nicely. A few things perhaps
[00:38:40] would have presented some form of issue,
[00:38:42] but the way that it had this all being
[00:38:44] kind of snapped to fit put together with
[00:38:46] pegs and things to assemble pieces, and
[00:38:49] then it actually had the hole cut here
[00:38:51] in this fan for the motor's shaft to go
[00:38:53] in. So, this would be a nice little like
[00:38:55] spinning motor, which is kind of what we
[00:38:57] had asked for, and it was welld
[00:38:59] designigned. Then, finally, we had our
[00:39:01] Subway game, which I'm not going to test
[00:39:03] again, as we probably spent a bit of
[00:39:04] time on that, and it was just absolutely
[00:39:06] top tier. So, overall, that is probably
[00:39:09] going to conclude our first look and
[00:39:11] test of the Fable 5.1 new model release.
[00:39:14] Is this the best model yet? Will
[00:39:18] probably be seen in the title. And then
[00:39:19] based off that Subway game, I might have
[00:39:21] to do insane just cuz I did spend like
[00:39:23] $160 on this test as well. So I'll feel
[00:39:25] better about having spent that money if
[00:39:27] I also do a bit of click baiting. So
[00:39:29] with that, if you have any questions,
[00:39:32] please feel free to leave them in the
[00:39:33] comments. And if you want to order a
[00:39:36] slap SWAT, no, I'm kidding.
[00:39:39] So all right, feel free to leave them in
[00:39:41] the comments. Then takes.
