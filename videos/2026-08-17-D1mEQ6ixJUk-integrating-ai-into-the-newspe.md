---
record_id: "youtube:D1mEQ6ixJUk"
video_id: D1mEQ6ixJUk
title: Integrating AI into the Newspeak IDE
channel: Gilad Bracha
url: "https://www.youtube.com/watch?v=D1mEQ6ixJUk"
watched_date: 2026-08-17
watched_at: "2026-08-17T12:00:00Z"
watch_count: 1
duration_seconds: 1138
source: youtube-history-browser
added_date: 
history_label: Aug 17
history_order: 64
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 114
transcript_status: fetched
transcript_content_hash: a7a0c5924d25b4a92542d5a8501c614ed8e26db5d7b0c743ebe31e744e081673
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video is a demo by the creator of the Newspeak web IDE (a Smalltalk-family live programming environment). It shows an AI integration of about 4–5,000 lines, written entirely by Claude Code (Opus 4.7) under light architectural supervision. The default chat model is Sonnet 4.6, and Gemini is also supported. Each IDE presenter (class, method, workspace, debugger) has a "brain" icon. Clicking it makes that presenter the AI's focus, so you can ask "what does this method do?" or "what's the problem?" without spelling out the context. The AI isn't preloaded with code. It browses namespaces and classes on demand, as a human would. In the demo it changed a class-heading background colour in live Newspeak code, and the change took effect system-wide. It evaluated an expression in a workspace (`platform mirrors`). It diagnosed a `doesNotUnderstand` error from the debugger's call stack, then did fix-and-continue by defining `foo` to return 42 and resuming execution. It also explained a method in the `ducts` module. It never changes code without asking for permission. You can run several chats and switch between them, and the model can be changed between turns but not while it is thinking. The browser sandbox is what makes live evaluation safe enough. The main downside is cost, because API usage is much more expensive than a flat Claude Code plan. API keys are stored in browser local storage. Planned next steps are local model providers, source-control integration, autonomous multi-change change sets without per-edit approval, and UI polish.

For you, the useful points are about design and are not tied to Newspeak. First, give the AI a focus or context marker tied to what you're looking at in the IDE. Lazy, on-demand code lookup also works better than loading everything into context. Second, live-system tools (evaluate, inspect stack frames, fix-and-continue) let an AI debug directly, so any Smalltalk, Pharo, or REPL-style tooling you build or use could copy this approach. Keep approval gates on edits until the tooling matures. Third, if you try this yourself, budget for per-token API costs, since they add up faster than a subscription. Expect to supply the architecture and catch anti-patterns yourself. The creator did that while Claude wrote all the code, and also told it to avoid CSS/HTML so it would use the native framework. If you use Newspeak, you can check the AI access and AI IDE support classes in the system to confirm the key handling. You'll need your own Anthropic or Gemini key to run it. Local-model support is still only planned, so don't count on it yet.

## Transcript

[00:00:03] Hello.
[00:00:04] This video is about the AI integration
[00:00:08] into the new speak web IDE.
[00:00:11] And so I'm going to spend a few minutes
[00:00:12] showing you the features that developed
[00:00:15] in the past couple of weeks with
[00:00:17] Claude's help.
[00:00:18] You can see there are a couple of
[00:00:19] classes here, AI access, AIID support,
[00:00:23] and there's a bit more code scattered in
[00:00:25] other places, mainly in the UI
[00:00:27] framework. Uh just a bit, altogether
[00:00:30] four, maybe 5,000 lines of code, all
[00:00:33] written by Claude.
[00:00:35] Uh slightly supervised by me.
[00:00:38] But uh
[00:00:39] apart from sort of, you know,
[00:00:41] architectural supervision and the
[00:00:43] occasional uh
[00:00:45] instruction to avoid an anti-pattern
[00:00:47] looking at things and so forth, it's
[00:00:49] largely it's entirely coded by Claude. I
[00:00:52] never actually wrote a line of code in
[00:00:55] in in this project. Uh the design is
[00:00:57] sort of a collaboration between me and
[00:00:59] Claude. It really provides uh
[00:01:02] good advice on how to do this kind of
[00:01:03] integration if you if you give it the
[00:01:06] provision.
[00:01:07] Uh so let's kind of see how this works.
[00:01:11] Uh you have these uh brain icons
[00:01:13] everywhere as you can see.
[00:01:15] When you click on one,
[00:01:18] go the background goes yellow. This
[00:01:20] tells you that this is the active brain
[00:01:22] as it were. What it really means is that
[00:01:24] the AI is focused on the presenter that
[00:01:26] has this brain, in this case the class
[00:01:28] presenter.
[00:01:30] Uh for uh
[00:01:32] for class AI access.
[00:01:34] So, let's try and do something fun like
[00:01:39] uh
[00:01:41] I want to change
[00:01:43] the color
[00:01:45] of classes, of I would say background
[00:01:48] color to be clear.
[00:01:59] And I also tell it I do not
[00:02:03] want
[00:02:05] to touch
[00:02:07] CSS or HTML cuz otherwise I found that
[00:02:10] it tends to to think that's the standard
[00:02:13] way of doing things. We want to use just
[00:02:16] use
[00:02:17] new speak.
[00:02:22] And uh
[00:02:24] let's see what it will make of that.
[00:02:27] It might take it a while.
[00:02:29] As you see, once you typed in the
[00:02:31] the query, it goes up into the chat
[00:02:34] record here,
[00:02:35] and the answer will show up
[00:02:38] once it's ready. In the meantime, it
[00:02:39] says thinking.
[00:02:41] And this will take a little while, and
[00:02:45] uh hopefully not too long.
[00:02:47] Uh
[00:02:48] in the meantime, I'll point out that the
[00:02:49] model is Sonnet 4.6. That's the default
[00:02:52] we're using right now. Here, the answer
[00:02:54] has come back. Uh before we look at the
[00:02:56] answer, notice that now the model isn't
[00:02:57] grayed out again. You can change models
[00:03:00] on the fly, but not while it's thinking,
[00:03:03] because that would confuse the hell out
[00:03:04] of things. But you have a choice of
[00:03:07] models here, so I wanted to
[00:03:09] to note that.
[00:03:10] So, here, what does it have to say? Let
[00:03:12] me explore the ID, right? It's going to
[00:03:15] try and figure this out. Uh
[00:03:17] it doesn't know the API. It has access
[00:03:19] to all the code in the live system. It
[00:03:21] hasn't gotten all of that loaded into
[00:03:24] its context necessarily. It has a
[00:03:26] protocol where it can go and ask for
[00:03:28] code that it feels is relevant uh is
[00:03:30] relevant.
[00:03:31] So, here, it seems to have found where
[00:03:35] to do this.
[00:03:37] Uh and it has a suggestion of changing
[00:03:40] it, so it'll get a green color right
[00:03:42] here. So, it realized that the heading
[00:03:44] definition in minor class headings are
[00:03:46] place which control the colors,
[00:03:49] and they uh
[00:03:51] it has an idea of what, uh, what to
[00:03:53] change it to.
[00:03:55] So,
[00:03:56] it always asks before it changes code.
[00:03:59] Uh, and this is one of the key things
[00:04:01] about having a new speak integration,
[00:04:03] unlike an integration into, you know,
[00:04:05] IDs for for dead languages,
[00:04:08] uh, you in a in a live system, you can
[00:04:10] change the code on the fly.
[00:04:12] And, uh, this is one of the things that
[00:04:14] we can do here. So, it asks and we'll
[00:04:16] say yes. Sh- It says, "Shall I apply
[00:04:18] this here?"
[00:04:20] And
[00:04:21] we'll say go ahead.
[00:04:27] And, uh,
[00:04:29] you notice that changed.
[00:04:33] Right? So, that's the color added and it
[00:04:36] changed it.
[00:04:37] And, of course, it's changed everywhere.
[00:04:40] If we go
[00:04:42] and look at the chorus class for, you
[00:04:45] know, a random other class, yeah,
[00:04:47] everywhere in the system this is
[00:04:49] changed.
[00:04:52] And this is where our chat was.
[00:04:55] Uh,
[00:04:58] and we can tell it
[00:05:00] I don't like it.
[00:05:03] Try, uh,
[00:05:06] lighter.
[00:05:08] Less saturated.
[00:05:19] And we'll see what, uh,
[00:05:24] And yes, it never does anything without
[00:05:26] permission. At some point I'll change
[00:05:28] that when when we're
[00:05:30] when things are a bit more mature. But
[00:05:32] for now,
[00:05:33] uh, I'm going to do that and yes.
[00:05:37] Let's see if we see a result here.
[00:05:44] Yeah.
[00:05:45] So, there.
[00:05:46] Uh, yeah, that's not as offensive. This
[00:05:48] is kind of
[00:05:50] a more uh
[00:05:52] a less saturated, more in your face uh
[00:05:54] less in your face, I should say, green,
[00:05:57] just as we asked for. So, the ability to
[00:05:58] change code on the fly
[00:06:00] is is one of the unusual aspects.
[00:06:02] Obviously, it was able to read code on
[00:06:05] the fly. It can access everything in the
[00:06:06] system. And as I said, none of this was
[00:06:09] essentially
[00:06:10] uh preloaded into the context. It goes
[00:06:12] and figures out what it should look at.
[00:06:15] It can get uh it can list what's in the
[00:06:17] ID, what's in the name spaces. Then it
[00:06:20] can look by names of classes and figure
[00:06:22] out what seems relevant, go look at
[00:06:23] them, just as sort of a human poking
[00:06:25] around would, really.
[00:06:27] The other thing that's very unusual,
[00:06:31] uh let's go and look at a workspace.
[00:06:36] And uh we're going to
[00:06:38] click here. So, again, now our focus is
[00:06:40] on the workspace. Not that's essential,
[00:06:42] but we want to see
[00:06:44] uh results here.
[00:06:46] Uh so, in fact, we're not going to do it
[00:06:48] in this workspace for now. We're going
[00:06:50] to Oh, we don't have it yet. It will
[00:06:51] open on AI workspace then, which is kind
[00:06:54] of nice, but for now we're going to say
[00:06:56] something like um
[00:07:02] tell me what
[00:07:05] platform
[00:07:07] mirrors returns.
[00:07:12] And
[00:07:15] we'll do
[00:07:16] uh
[00:07:17] or to evaluates to. I don't know,
[00:07:20] otherwise it might go for a return type
[00:07:22] or something.
[00:07:26] Uh let's see. And
[00:07:29] as we get that running,
[00:07:31] it's thinking again.
[00:07:34] And it tells me platform mirrors value
[00:07:36] string instance of mirrors for prime
[00:07:38] origin soup. That's the mirrors library
[00:07:39] for this new speak platform. It's an
[00:07:42] entry point for reflective operations
[00:07:44] giving you access to class mirror,
[00:07:46] object mirror, etc. So you can have it
[00:07:47] explain the code, etc.
[00:07:50] And yeah,
[00:07:52] you can see here that there's an
[00:07:54] instance of
[00:07:56] mirrors for primordial soup. So it
[00:07:57] actually evaluated otherwise, you know,
[00:07:59] it wouldn't know this. It actually did
[00:08:02] do the evaluation. So you can do
[00:08:03] evaluation live in the IDE or other the
[00:08:05] AI can do it. You of course can do it.
[00:08:08] That's a bit different some some of the
[00:08:10] other small talk
[00:08:12] sort of AI integrations I've seen though
[00:08:14] they may have changed that. It's a
[00:08:15] constantly moving thing. But um
[00:08:19] in the advantage of working in the web
[00:08:21] browser is that we're in a sandbox and
[00:08:23] we don't have to worry so much about
[00:08:24] security. It's sort of for better or
[00:08:26] worse taken a lot of it is taken care of
[00:08:28] for us. That also restricts sometimes
[00:08:31] what we can do.
[00:08:32] But it means that we're not too worried
[00:08:34] about evaluating. We're already in a
[00:08:35] code evaluation sandbox and so we can
[00:08:39] run things and
[00:08:41] evaluate them.
[00:08:43] And they work. And so that's pretty much
[00:08:47] unique to to small talk environments,
[00:08:49] right? You can't do this in in your
[00:08:51] regular AI integrated into a vanilla
[00:08:53] dead code kind of environment.
[00:08:56] So another thing you can do which is
[00:08:59] interesting
[00:09:00] is let's try and evaluate
[00:09:04] foo.
[00:09:06] So there is no foo in the workspace. So
[00:09:08] that's an error and we got a link to a
[00:09:11] debugger.
[00:09:12] And if we click here
[00:09:16] we can just ask it and it'll do it. Tell
[00:09:19] me what went wrong.
[00:09:24] And how
[00:09:25] to fix it.
[00:09:29] This is really the do what I mean
[00:09:30] button, the do what I mean button. How
[00:09:32] do you you've got a bug? Tell me what
[00:09:34] what it is and how I'm going to fix it.
[00:09:37] And so let's see.
[00:09:43] It will come back to us in not too long,
[00:09:45] I hope.
[00:09:54] Yeah, here. Here's what went wrong. The
[00:09:56] message foo was sent to the workspace
[00:09:57] one instance, but it doesn't understand
[00:09:59] it.
[00:10:00] And here's what the call chain shows,
[00:10:02] right? So it actually knows that
[00:10:04] you know, it it can look at all the
[00:10:07] calls here in the stack, can traverse
[00:10:10] the stack, and understand what actually
[00:10:12] went wrong with this particular bug. It
[00:10:13] can also inspect those stack frames,
[00:10:16] what their state is like. It can even
[00:10:18] actually step through the debugger and
[00:10:20] run run commands. This case is is a very
[00:10:22] simple situation, but it's telling you,
[00:10:25] yeah, it it tried to call this, uh does
[00:10:28] not understand in workspace. In fact, uh
[00:10:31] since it doesn't understand it itself,
[00:10:32] it tries to look it up in the root
[00:10:34] namespace. That's how we get access in
[00:10:36] the workspace conveniently to
[00:10:38] to what's in the system. It didn't find
[00:10:40] that, and eventually went to
[00:10:41] objects.notUnderstand.
[00:10:43] And now the fix. Well, it's not defined,
[00:10:46] and you can either define it,
[00:10:49] or if it was a typo and you meant
[00:10:50] something else, then do that. And that's
[00:10:53] correct.
[00:10:54] So
[00:10:56] assume
[00:10:58] foo
[00:10:59] should return 42.
[00:11:04] Fix it.
[00:11:05] Fixes the problem.
[00:11:08] And continue
[00:11:13] executing.
[00:11:23] Right. Okay, since it's not allowed to
[00:11:24] change code without asking, it's asking
[00:11:27] add foo it returns 42 to workspace one.
[00:11:29] Shall I apply it. Yes.
[00:11:43] Okay, and now it's resumed execution
[00:11:46] and we're
[00:11:48] back here.
[00:11:50] Uh
[00:11:52] so we can continue and here's the result
[00:11:56] 42.
[00:11:57] And if we go back to our workspace
[00:12:01] just to be sure
[00:12:03] and re-evaluate this
[00:12:06] and we get 42 right here.
[00:12:08] So, yeah, we can do fix and continue
[00:12:11] debugging or rather the AI can do fix
[00:12:13] and continue debugging. It can control
[00:12:15] the debugger. It can change the code. It
[00:12:18] can look at the state of the of the
[00:12:20] system.
[00:12:21] And so that's uh all kind of cool. What
[00:12:25] else can I show you? Obviously the the
[00:12:27] idea here is the of the selecting these
[00:12:31] uh
[00:12:32] brain thingies, right? I should say a
[00:12:35] few more words about that. So, let's
[00:12:37] look at a class like
[00:12:39] ducts.
[00:12:41] And okay, well, let's look at a nested
[00:12:43] class.
[00:12:45] And
[00:12:47] let's say
[00:12:51] with this method.
[00:13:01] So, we'll ask it what the method does.
[00:13:13] And it's going to have to read up about
[00:13:15] ducts and figure out what they're all
[00:13:17] about and then understand.
[00:13:20] And so send packet delivers a packet to
[00:13:23] all outlets connected to this ducts.
[00:13:25] Here's how it works. There's an
[00:13:27] explanation, etc. So, as you'd expect,
[00:13:30] it can explain the code to you. It
[00:13:32] understands New Speak uh pretty well.
[00:13:35] And uh
[00:13:37] the nice thing about this mechanism with
[00:13:39] uh every every presenter like method
[00:13:41] presenters, class header presenters,
[00:13:43] class presenters, debuggers, uh all
[00:13:46] these things, workspaces, they all have
[00:13:47] their brain icon. And when you click on
[00:13:49] it, it gets a yellow uh background,
[00:13:52] which means that's the current focus.
[00:13:54] And that means that it now has some
[00:13:56] context to know what you're looking at.
[00:13:57] So, I didn't have to tell it, "Uh look
[00:13:59] at the method send in class duct inside
[00:14:02] the ducts module and tell me what it
[00:14:04] does." I just told it, "What does this
[00:14:06] method do?" Same thing when I looked in
[00:14:08] the debugger and says, "What's the
[00:14:10] problem?" It can look and say, "Oh, I'm
[00:14:12] in a debugger. That's what the user
[00:14:13] means by a problem." And so forth. So,
[00:14:16] providing that context is another kind
[00:14:18] of neat nice feature, which plays well
[00:14:20] with a with a structured nature of New
[00:14:22] Speak and Smalltalk environments where
[00:14:25] uh you're not just browsing a file, but
[00:14:27] you're actually looking in a structured
[00:14:28] way at a particular construct.
[00:14:31] Uh
[00:14:32] other things, yeah, if you go to the top
[00:14:35] brain,
[00:14:37] it'll take you to a document here,
[00:14:40] which is uh includes the the chat. And
[00:14:43] that has a few other features.
[00:14:46] Uh you can, of course, change the model
[00:14:48] as as we saw before.
[00:14:51] But, it also lets you add chat. So,
[00:14:54] let's add a chat.
[00:14:56] Uh
[00:14:57] we'll call it chat two.
[00:14:59] And this tells you, yeah, this is
[00:15:01] Anthropic. Uh
[00:15:03] and you if you don't have an API key,
[00:15:05] it'll ask you to fill in the key, but we
[00:15:07] do have it and it hides it.
[00:15:09] And so, we'll just tell it to start
[00:15:12] chat. And we have chat two.
[00:15:14] And now when we look at chats, we have
[00:15:16] both chat and chat two, and we can
[00:15:18] alternate among them.
[00:15:19] Uh we can also create chats with uh
[00:15:23] Google, so Gemini.
[00:15:25] Uh,
[00:15:26] and so
[00:15:28] we'll call that G chat.
[00:15:32] And start that one, and that's a
[00:15:33] distinct one.
[00:15:35] Um
[00:15:38] What AI providers
[00:15:42] can I use in this
[00:15:46] environ
[00:15:51] So, let's see what Gemini can tell us
[00:15:53] about my choice of AI providers. You can
[00:15:56] use Anthropic and Gemini. That's true.
[00:15:59] Uh,
[00:16:00] so
[00:16:02] uh, you can ask it to explain the AI
[00:16:04] architecture and so forth. The point
[00:16:05] being, yeah, well, currently we support
[00:16:07] Google and uh and Anthropic.
[00:16:11] And uh the next phase is probably to
[00:16:13] experiment with local providers, which
[00:16:15] is good because
[00:16:17] uh unfortunately, the one big downside
[00:16:18] of this whole thing is it costs real
[00:16:20] money. All right, you uh you're paying
[00:16:22] for this. That's why you have to fill in
[00:16:24] your API key.
[00:16:26] Uh, I have API keys in the browser here.
[00:16:29] If you uh access the system, say from
[00:16:31] the web,
[00:16:32] uh it when you try to click on the
[00:16:34] brain, it will take you to a um this uh
[00:16:36] setup dialogue that we had before. Uh,
[00:16:40] let's see. I think we have some We
[00:16:42] should have AI chat. It'll take you to
[00:16:44] an AI chat setup. And the thing is this
[00:16:47] will be open, and you'll have to fill in
[00:16:48] your API key. It's stored in local
[00:16:51] storage in the browser, doesn't go
[00:16:53] anywhere. Uh, if you don't believe me,
[00:16:55] you don't believe me, but you can
[00:16:56] actually check all the code uh in the
[00:16:58] Newspeak system and uh and see that
[00:17:01] that's the case.
[00:17:03] Uh, so
[00:17:04] um if you're Basically, the point and
[00:17:06] bottom line is you have to pay for it.
[00:17:08] And uh these costs, they do add up. Uh,
[00:17:12] it's a lot more costly to use the APIs
[00:17:14] than it is to use um you know, a fixed
[00:17:16] plan with, uh, with Claude code or
[00:17:18] something.
[00:17:20] But, uh, that'll change and the point of
[00:17:23] this is to make this whole system ready
[00:17:26] for,
[00:17:27] the future that's already almost here
[00:17:29] where, uh,
[00:17:31] AI is is is doing all your coding. So, I
[00:17:34] will also add that all of this stuff,
[00:17:37] uh, the AI access and AI ID support
[00:17:39] classes and the changes elsewhere in the
[00:17:41] system were all coded by Claude code.
[00:17:45] Uh, some were debugged live with with
[00:17:48] the system itself.
[00:17:49] Uh, generally speaking, uh, you know, it
[00:17:52] does a great job with Opus 4.7.
[00:17:56] I have not written a single line of the
[00:17:58] AI integration code. I have looked at it
[00:18:01] go by, reviewed, made suggestions for a
[00:18:04] better style or changes once in a while.
[00:18:06] Uh, the whole design is something I
[00:18:08] worked out with Claude in sort of, uh,
[00:18:11] collegiate conversation.
[00:18:13] Uh, this stuff is is, uh, really
[00:18:16] impressive and, uh, I expect to do a
[00:18:19] whole lot more with this, integrating it
[00:18:20] into source control, uh, getting it into
[00:18:24] a mode where it can do whole change sets
[00:18:26] and, uh, just motor automatically,
[00:18:29] right? We not not asking every time it
[00:18:31] has to change, uh, piece of code uh, as
[00:18:34] it does now.
[00:18:36] And, uh,
[00:18:37] and, as I said, add more providers,
[00:18:40] uh, polish the UI in various ways, but,
[00:18:44] uh, this is the essence of it and I
[00:18:45] figured it was, uh, kind of a nice thing
[00:18:47] to show. Uh, so, thank you for
[00:18:49] listening.
