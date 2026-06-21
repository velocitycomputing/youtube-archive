---
video_id: t7L6-fMpxFc
title: "Apple WWDC 2026: The AI Story Everyone is Missing"
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=t7L6-fMpxFc"
watched_date: 2026-06-12
watched_at: "2026-06-12T12:00:00Z"
watch_count: 1
duration_seconds: 1114
source: youtube-history-browser
added_date: 
history_label: Jun 12
history_order: 142
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 1114
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Apple announced at WWDC 2026 that its AI strategy is to move intelligence from cloud services into the device itself, backed by private cloud compute for harder tasks. The announcements include Siri AI, Apple Intelligence, on-device and server models built with Google's Gemini technology, App Intents (allowing developers to expose app actions to the OS), and expanded private cloud compute using Nvidia GPUs in Google Cloud. The deeper story is that Apple is betting the next trillionaire in AI won't be whoever builds the best frontier model—it's whoever owns the "trusted action surface" where users actually interact with AI: the device, OS, app platform, and permission layer that lets people do real work without feeling stripped for data.

For developers and product teams, the actionable shift is decisive: stop adding chatbots as a checkbox feature and instead make your app's data, permissions, and actions legible to the OS through App Intents. For regular users and workers, look for the unglamorous features—password auto-fixes, page-change notifications, natural-language shortcuts—that reduce context switching; these drive real productivity, not model benchmarks. If you manage a team, the budget conversation is no longer "which AI model do we buy" but "where does our work live and what must stay private." If you build on Apple platforms, the winning apps will be those whose internal architecture is clean enough that Apple Intelligence can safely operate them, not the ones with flashy demos.

## Transcript

[00:00:00] Apple used WWDC to show Siri AI,
[00:00:02] confirmed the Google Gemini Apple
[00:00:05] Alliance story, and to expand private
[00:00:07] cloud compute into Google Cloud using
[00:00:09] Nvidia GPUs. And that sounds like it's
[00:00:11] three separate headlines, doesn't it?
[00:00:13] But I think it is Apple answering the
[00:00:15] question that may decide who becomes the
[00:00:17] first trillionaire in AI history. When
[00:00:19] AI starts doing real work for you all
[00:00:21] day long, where does that work run? Does
[00:00:25] it run in a chatbot tab? Does it run in
[00:00:27] a giant cloud service where every
[00:00:29] serious task burns tokens and GPU time
[00:00:31] and power and data center capacity? Or
[00:00:33] does more of it start inside the
[00:00:35] computer you already bought? The iPhone
[00:00:37] in your hand, the Mac on your desk, the
[00:00:39] chip inside that Mac, the operating
[00:00:41] system, the apps, the files, the photos,
[00:00:43] the messages, the screen, and then
[00:00:46] private cloud behind it when the device
[00:00:48] is not enough. That is Apple's vision.
[00:00:51] That is the WWDC story. Sure, the
[00:00:54] feature list is Siri AI and Apple
[00:00:56] Intelligence and Google Gemini family
[00:00:58] tech and app intents and foundation
[00:01:00] models and visual intelligence. The list
[00:01:02] goes on. But the story is that Apple is
[00:01:05] trying to turn AI from something you
[00:01:07] rent in the cloud into something built
[00:01:09] into the computer you bought. And that
[00:01:12] is why this WWDC matters. Because if you
[00:01:14] were trying to understand AI without
[00:01:16] turning your life into a model provider
[00:01:18] spreadsheet, this gives you a clean map
[00:01:22] to the future. So, stop asking which AI
[00:01:26] model is ahead or if Siri is catching
[00:01:27] up. Ask who owns the place where AI sees
[00:01:30] your work and touches your apps and
[00:01:32] remembers your context and does
[00:01:34] something. If you run a team, this
[00:01:37] changes the budget conversation. It is
[00:01:39] not just should we buy ChatGPT or should
[00:01:42] we buy Claude or Gemini? It's where does
[00:01:44] our work live? Which systems can AI
[00:01:46] safely touch? What has to stay private?
[00:01:48] Who gets permission to act, right? Those
[00:01:51] are the larger questions for 2026. If
[00:01:53] you build software, this changes the
[00:01:55] product conversation. It's not enough to
[00:01:57] bolt AI onto the app. Obviously, the app
[00:02:00] has to be legible to the operating
[00:02:01] system. That's the new challenge, and
[00:02:03] that's the challenge Apple is going
[00:02:04] after with WWDC. If you're drowning in
[00:02:07] email and tabs and files and passwords
[00:02:09] and copying and pasting, then this is
[00:02:11] the part that matters. That's the fight
[00:02:14] Apple picked at WWDC. So, this is the
[00:02:16] story of what Apple announced, what Siri
[00:02:18] now sits on top of, why the developer
[00:02:21] layer matters, why Google and Nvidia
[00:02:23] make the story more interesting, and
[00:02:24] what this changes if you are trying to
[00:02:26] make AI useful in actual work.
[00:02:29] Let's start with the announcements.
[00:02:31] Apple announced the next version of
[00:02:32] Apple Intelligence, new Siri AI, new
[00:02:34] Apple Foundation models, new on-device
[00:02:36] models, new server models running
[00:02:38] through private cloud compute, Google
[00:02:40] Gemini family tech underneath part of
[00:02:42] the model stack, and a private cloud
[00:02:44] compute expansion into Google Cloud with
[00:02:46] Nvidia GPUs. They also announced App
[00:02:49] Intents becoming much more important to
[00:02:50] Siri and Apple Intelligence, uh
[00:02:52] Foundation models as a developer
[00:02:54] framework, Core AI so developers can run
[00:02:56] local models in apps using Apple
[00:02:58] silicon, and Xcode agents with model
[00:03:01] choice. Natural language shortcuts,
[00:03:03] Safari features that can watch web pages
[00:03:05] and organize tabs, passwords doing more
[00:03:07] adjunctive work to fix your weak
[00:03:09] accounts, and then they did the normal
[00:03:10] WWDC platform stuff, too, right? New OS
[00:03:13] versions, design refinements,
[00:03:15] performance improvements, search
[00:03:16] improvements, betas now, final releases
[00:03:18] in the fall. So, yes, so many
[00:03:20] announcements it's easy to lose track of
[00:03:22] it all. But, the AI announcements all
[00:03:24] point in the same direction. Apple is
[00:03:27] trying to make AI part of the computer
[00:03:29] again. Not a separate chat tab, not a
[00:03:32] model picker, not some cloud product
[00:03:34] that you visit. The computer That's
[00:03:36] Apple's vision. The thing in your hand,
[00:03:38] the apps you use, the files, the photos,
[00:03:40] the message, the password, the calendar,
[00:03:42] the browser, the screen context where
[00:03:44] your life already is. That's the AI. And
[00:03:47] that's a very different strategy than
[00:03:49] build the best chatbot. And that is
[00:03:51] where most of the
[00:03:53] seems to be missing the point because
[00:03:55] the easy WWDC question is did Siri get
[00:03:58] smarter? It's a fair question, right?
[00:04:00] Siri matters. Normal people are going to
[00:04:01] judge Apple AI through Siri. If Siri
[00:04:04] feels dumb as it has, the whole thing
[00:04:06] feels dumb. But Siri's not the AI
[00:04:08] strategy for Apple. Siri's just the
[00:04:10] face. The better question is what is
[00:04:12] Siri sitting on top of, right? And the
[00:04:14] answer gets really interesting. Siri now
[00:04:17] sits on top of personal context and
[00:04:19] screen awareness and app actions and
[00:04:21] spotlight semantic index and Apple
[00:04:23] foundation models and private cloud
[00:04:25] compute and app intents. And that's not
[00:04:27] just a voice assistant story. That's
[00:04:29] Apple trying to make the operating
[00:04:31] system itself feel agentic. And by that
[00:04:33] I mean something really simple, right?
[00:04:35] Can the system see your screen? Can it
[00:04:37] understand your files and photos? Can it
[00:04:40] talk to the apps where your work
[00:04:41] happens? Can it take action and do it
[00:04:43] without spraying your life into a random
[00:04:45] cloud service? That is the product
[00:04:47] they're trying to build. It's not some
[00:04:49] benchmark they're hitting. It's not a
[00:04:50] demo they want to sort of make flashy
[00:04:53] even though WWDC has demos. The real
[00:04:56] product is whether your computer can
[00:04:58] finally take the hint, right? Can it
[00:05:00] find the thing? Can it move the file?
[00:05:02] Can it watch the page? Can it build the
[00:05:03] shortcut? Can it draft the message in
[00:05:05] the app where it will actually be sent?
[00:05:07] This is what ordinary consumers want,
[00:05:10] right? It's what my aunt wants. They
[00:05:12] don't want to manage six models or or
[00:05:14] think about tokens or context windows or
[00:05:17] local versus cloud. None of that
[00:05:19] matters. They want the computer to do
[00:05:21] the right thing and not leak their life
[00:05:23] in the process. Apple's always been good
[00:05:25] about it. That is an Apple problem. It's
[00:05:27] a better problem for Apple than beating
[00:05:29] OpenAI at frontier model speed. Look,
[00:05:31] Apple has not had the best assistant.
[00:05:34] Apple has not had the best model. They
[00:05:36] don't have those today. But you don't
[00:05:38] need to be the best frontier lab if you
[00:05:41] own the place where personal AI becomes
[00:05:43] useful. And that's what's going to
[00:05:44] matter to my aunt and and my cousins and
[00:05:47] people who are not deep in AI. The AI
[00:05:49] industry has trained us to think the
[00:05:51] model is the product. But for most
[00:05:53] consumer AI, I think the product is the
[00:05:55] model plus context plus permissions and
[00:05:58] interface and actions and trust in a
[00:05:59] package you believe in. That's what
[00:06:02] Apple is trying to own. And that brings
[00:06:04] us to the developer story, which is
[00:06:06] probably the least sexy part of the
[00:06:07] keynote and maybe the most important
[00:06:09] one, too. App Intents is how developers
[00:06:12] make their apps contents and actions
[00:06:14] available to the system. In plain
[00:06:16] English, it is how an app tells Apple
[00:06:18] Intelligence, here's what I have, here's
[00:06:20] what the user can do with it, and here
[00:06:21] are the actions you are allowed to take.
[00:06:24] That matters because an AI assistant
[00:06:26] that cannot act inside apps is not
[00:06:28] really an assistant, is it? It can just
[00:06:30] suggest things, advise on things, write
[00:06:32] things, summarize things, but all the
[00:06:34] work lives elsewhere. Apple spent the
[00:06:36] last 15 or 20 years teaching every
[00:06:38] company on Earth to become an app. And
[00:06:41] you see that even now when people are
[00:06:43] vibe coding and the number of apps in
[00:06:45] the App Store is skyrocketing. But usage
[00:06:48] isn't, right? Apple knows that. Now it's
[00:06:50] trying to teach the operating system to
[00:06:52] do the thing the app used to do. Apple's
[00:06:55] trying to self-destruct. The old world
[00:06:57] was open the app, learn the interface,
[00:06:59] tap around, do the thing. The agentic OS
[00:07:01] world is ask the system and the system
[00:07:03] uses the app for you. That is Apple
[00:07:06] trying to move past the app world it
[00:07:08] built. But the catch is this, it can't
[00:07:10] move too far because the app ecosystem
[00:07:13] is also the tollbooth.
[00:07:15] So App Intents is the compromise
[00:07:17] architecture, right? Apple gets to make
[00:07:19] apps callable by the OS while keeping
[00:07:21] the app, the developer relationship,
[00:07:24] permission layer, the App Store with all
[00:07:26] that money, and the distribution inside
[00:07:27] Apple gray. That is why this is not
[00:07:30] actually Apple killing apps. It is Apple
[00:07:32] turning apps into things the operating
[00:07:34] system can call. And this changes what
[00:07:36] developers ought to care about. For the
[00:07:37] last couple of years, a lot of AI
[00:07:39] product strategy has been, you know, you
[00:07:42] have to at least add a chatbot. And if
[00:07:44] you think I'm making that up, I have sat
[00:07:46] in rooms where people say, "Well, at at
[00:07:47] a minimum we have to do that." And it
[00:07:49] really is something people have done,
[00:07:51] and everything gets AI-washed, right?
[00:07:53] And everything gets AI-washed, right?
[00:07:54] Now now we can put AI in the headline,
[00:07:56] we can write a press release, we're
[00:07:57] done.
[00:07:58] So much of that is lazy, right? The
[00:08:02] Apple version of AI here is a lot more
[00:08:04] than a lazy press release. Apple is
[00:08:06] getting very structural with their
[00:08:07] approach to AI. If the OS is becoming an
[00:08:11] AI surface, your app has to become
[00:08:13] legible to the OS. So, for developers,
[00:08:16] your data model matters, your
[00:08:17] permissions matter, your actions matter,
[00:08:19] your integration with Spotlight and Siri
[00:08:21] and shortcuts matters a lot. The winning
[00:08:24] apps might not be the apps with the
[00:08:26] flashiest chatbot. They might be the
[00:08:28] apps whose data and actions are clean
[00:08:30] enough that Apple intelligence can
[00:08:32] actually use them. And that is not super
[00:08:34] exciting to demo, but it's super
[00:08:37] important in practice.
[00:08:39] And foundation models matter for the
[00:08:40] same reason. Apple is opening model
[00:08:42] access through a native Swift framework,
[00:08:44] right? On-device Apple models, private
[00:08:46] cloud compute models, and other
[00:08:47] providers that conform to that
[00:08:50] framework.
[00:08:50] Apple is not saying we built every model
[00:08:52] and you should only use us. Apple is
[00:08:54] saying we want to own the native model
[00:08:56] interface on Apple platforms. It's a
[00:08:58] different kind of control, right?
[00:09:00] Core AI matters because it gives
[00:09:02] developers a path to run other local
[00:09:04] models using Apple silicon. Xcode agents
[00:09:07] matter because Apple's pushing the same
[00:09:09] agent story into the developer workflow
[00:09:11] itself. So, this is not a story about
[00:09:14] Siri. It is Apple trying to make AI
[00:09:16] native across the platform, consumer
[00:09:18] surface, developer surface, app surface,
[00:09:20] device surface.
[00:09:21] The deeper WWDC story is that Apple is
[00:09:24] turning everything in the system into a
[00:09:28] pipeline to enable an AI layer for
[00:09:31] consumers over the existing Apple OS.
[00:09:35] And they're betting that that's enough
[00:09:37] to self-disrupt. I don't know if it is.
[00:09:39] And the question around whether Apple is
[00:09:41] doing enough brings us to the Google
[00:09:43] Gemini piece of this story. A lot of
[00:09:45] people are going to treat this as
[00:09:47] humiliating for Apple. At some level, it
[00:09:50] is, right? Apple would obviously prefer
[00:09:52] the clean mythology, the clean story.
[00:09:54] Our hardware, our software, our chips,
[00:09:56] our models, our magic. Instead, the
[00:09:58] story is the next generation of Apple
[00:10:01] foundation models was built in
[00:10:03] collaboration with Google using Gemini
[00:10:05] family tech. That's significant, right?
[00:10:08] But the cheap take is not as strong as
[00:10:10] it sounds. The cheap take is Apple
[00:10:11] failed and had to use Google. I think
[00:10:13] the stronger take is Apple may not care
[00:10:16] who supplies raw model capability. It's
[00:10:18] commoditizing. Apple wants to own the
[00:10:21] layer the user touches. Who owns the
[00:10:23] device, the OS, the app platform, the
[00:10:25] permission prompts, the Siri surface.
[00:10:27] Apple wants to own that. So, yeah,
[00:10:29] they'll let Google provide the model
[00:10:30] capability. Nvidia can provide the
[00:10:32] private cloud infrastructure. Apple
[00:10:34] still wants to own the experience and
[00:10:36] they're betting they can. You can source
[00:10:38] model capability. You cannot easily
[00:10:40] source a billion devices, a mature
[00:10:42] operating system, a developer ecosystem,
[00:10:44] and the trust people have in the
[00:10:45] computer they carry around. Now, private
[00:10:48] cloud compute is where that argument
[00:10:49] gets a little bit more complex. Follow
[00:10:51] me here, right? The super easy version
[00:10:53] is the Apple hardware thesis is local AI
[00:10:56] inference moves off the cloud, it moves
[00:10:57] onto the device. You have Apple silicon
[00:10:59] with unified memory and neural engines.
[00:11:01] You have local models, it's all fixed
[00:11:03] cost. That is still a part of the story.
[00:11:06] But WWDC made it clear that the larger
[00:11:09] version of that story is really a device
[00:11:11] plus private cloud. Apple is saying run
[00:11:14] what you can on the device and when the
[00:11:16] request is too difficult, trust us,
[00:11:18] we'll route it to private cloud compute.
[00:11:20] And now private cloud compute is
[00:11:21] expanding beyond Apple's own data
[00:11:23] centers into Google Cloud using Nvidia
[00:11:25] GPUs for really hard workloads,
[00:11:27] including agentic tool use and
[00:11:28] complicated reasoning. This puts Jensen
[00:11:30] in a very interesting position. Nvidia
[00:11:33] may still be inside the infrastructure,
[00:11:35] Google may still supply the model
[00:11:36] capability, the cloud may still handle
[00:11:38] the hardest workloads, but Apple wants
[00:11:40] to be the front door and stay the front
[00:11:42] door. The device is going to decide what
[00:11:44] runs locally. The OS is going to decide
[00:11:46] when context is available, the app layer
[00:11:48] exposes the actions, private cloud
[00:11:51] compute is relegated to handling
[00:11:53] overflow. Apple is going for one of the
[00:11:55] two core bottlenecks in AI here, right?
[00:11:57] In AI we have at least two major
[00:11:59] bottlenecks. One bottleneck, of course,
[00:12:00] is raw compute. GPUs and power in data
[00:12:04] centers and networking and memory
[00:12:05] bandwidth, all that stuff that Nvidia is
[00:12:08] incredible at.
[00:12:09] And that's a very real bottleneck. The
[00:12:11] other bottleneck is the trusted action
[00:12:14] surface. That's what's getting fought
[00:12:16] over now. Where does the AI meet the
[00:12:18] user? Where does the AI touch apps?
[00:12:20] Where does the AI get permission to act?
[00:12:23] And that bottleneck is real, too, and
[00:12:25] Apple's trying to own that one. And that
[00:12:27] is that is a trillionaire question,
[00:12:29] people. It's not who has the cleanest
[00:12:32] demo, it's not who has the best frontier
[00:12:33] model, it's who owns the default meter
[00:12:36] for everyday intelligence. If the future
[00:12:39] of AI is mostly bigger models and bigger
[00:12:41] data centers, Jensen wins and keeps on
[00:12:44] winning.
[00:12:45] Nvidia becomes the tax collector on
[00:12:47] intelligence. That That is just one
[00:12:50] path, but if a huge amount of useful
[00:12:52] personal AI happens through the device
[00:12:54] and operating system, the economics get
[00:12:57] a lot more complicated for Jensen. The
[00:12:58] device becomes the default, the cloud
[00:13:00] becomes a specialist, the thing in your
[00:13:03] pocket becomes just part of the larger
[00:13:05] AI compute experience, and that's a very
[00:13:07] different world. And if Apple pulls that
[00:13:09] off, it changes who gets paid at scale.
[00:13:12] Sure, Nvidia still wins in frontier
[00:13:14] training and enterprise inference and
[00:13:16] robotics and scientific computing and
[00:13:18] data centers, and that build-out is is
[00:13:20] real, but Apple can shift a meaningful
[00:13:23] part of the consumer AI value chain
[00:13:26] toward hardware it sells, toward
[00:13:27] software controls, and toward services
[00:13:30] it can meter or bundle through iCloud
[00:13:31] and the App Store. This is why we're
[00:13:34] talking about trillionaire level
[00:13:35] territory here. Because the first
[00:13:36] trillionaire is probably not just the
[00:13:39] person with the smartest model. It is
[00:13:41] the person who owns the meter when
[00:13:44] intelligence becomes economically
[00:13:46] unavoidable. Maybe that's Jensen because
[00:13:48] every path runs through GPUs. Maybe
[00:13:51] that's Apple because personal AI becomes
[00:13:54] native to Apple devices and Apple turns
[00:13:56] the iPhone upgrade cycle into the AI
[00:13:58] upgrade cycle. And maybe it's both. WWDC
[00:14:02] is trying to give us a flashlight to get
[00:14:04] through that fog. It's trying to give us
[00:14:06] clarity around what ordinary folks
[00:14:08] around the Thanksgiving dinner table are
[00:14:10] going to talk about as AI. And if you
[00:14:13] want to get ahead of that story, I would
[00:14:14] encourage you to watch the surfaces,
[00:14:16] right? Watch device surfaces, OS
[00:14:18] surfaces, browser and search surfaces,
[00:14:21] how files are handled. This tells you
[00:14:23] more about where personal AI is going
[00:14:26] than another leaderboard argument or
[00:14:28] even than the press releases around
[00:14:29] WWDC.
[00:14:31] If you already use ChatGPT as a billion
[00:14:34] people do just about or Gemini and
[00:14:36] you're trying to turn that into real
[00:14:38] work, the takeaway is even more blunt.
[00:14:41] Look, Apple is not all the way there.
[00:14:44] But WWDC is about building the rails to
[00:14:46] make that kind of default experience
[00:14:48] possible. Because if your day is full of
[00:14:51] context switching, if it's full of email
[00:14:53] and Slack and documents and tabs and
[00:14:55] you're always going back and forth,
[00:14:56] those boring features that make life
[00:14:59] feel seamless with AI really matters.
[00:15:01] Because really the value of AI is not I
[00:15:04] wrote a paragraph, the value is
[00:15:06] intelligence that lets you get more work
[00:15:08] done with less context switching, less
[00:15:10] handoff, fewer administrative papercuts.
[00:15:13] The computer just notices that the page
[00:15:15] changed. The password is weak, so the
[00:15:17] computer fixed it. The shortcut gets
[00:15:19] built in plain English so you can
[00:15:22] understand what the computer is doing.
[00:15:23] None of this is AGI, right? It is just
[00:15:25] the machine becoming less useless at the
[00:15:27] work sitting in front of you. Apple's
[00:15:29] whole product claim is the claim that
[00:15:31] the computer can now know a lot about
[00:15:33] you without making you feel like you're
[00:15:35] being stripped mine for data. And I got
[00:15:37] to ask, do you think Open AI is someone
[00:15:39] you trust with that? Does is Anthropic a
[00:15:41] company you trust like that? I don't
[00:15:43] know. People tend to have different
[00:15:44] answers to those questions. But that's
[00:15:46] the lane we're talking about. And that
[00:15:48] trust lane is extremely valuable as AI
[00:15:51] agents start touching more and more of
[00:15:52] our work.
[00:15:54] And if you're building software in this
[00:15:56] space, right? If you're building in the
[00:15:57] Apple ecosystem anywhere, the future of
[00:16:00] an app on Apple platforms is not going
[00:16:03] to be can I get this app launched and
[00:16:05] get it approved? It's going to be can I
[00:16:07] expose the actions? Can I clean up
[00:16:09] permissions? Can I make the workflow
[00:16:11] safe? Can I expose the objects so app
[00:16:13] intents work? The apps that win are not
[00:16:16] the ones with the flashiest demos. It's
[00:16:17] going to be the apps work that have data
[00:16:19] and and actions that are clean enough
[00:16:21] for the operating system to actually
[00:16:23] operate them. And the question from a
[00:16:25] brand perspective is are you stuck
[00:16:27] enough in people's heads that they will
[00:16:29] actually ask for you by name when they
[00:16:31] talk to Apple. So sure, the surface WWDC
[00:16:35] story is about Google sucking the AI
[00:16:36] features in Siri AI.
[00:16:38] The bigger story is that Apple is trying
[00:16:41] to turn the iPhone and Mac and iPad into
[00:16:44] the default place for consumers where
[00:16:46] personal AI runs and sees and decides
[00:16:48] and acts. And by the way, if it's
[00:16:51] default for consumers, it may well
[00:16:53] become default for workers because we
[00:16:55] all bring our own devices everywhere.
[00:16:57] And so the question is going to become
[00:16:59] if it's that seamless on Apple, are you
[00:17:01] going to start demanding that kind of
[00:17:03] seamlessness at work?
[00:17:05] That's the play.
[00:17:06] It's not Apple built the smartest model.
[00:17:09] It's not Apple killed Nvidia. It's not
[00:17:11] everything runs locally. The play is
[00:17:13] Apple wants to own the computer where
[00:17:15] personal AI becomes useful and by
[00:17:18] extension Apple wants to own the
[00:17:20] computer where AI is valuable.
[00:17:23] And and if that works, the AI race stops
[00:17:26] being only about who has the biggest
[00:17:27] cloud cluster. It's it's about who owns
[00:17:30] the trust in the system. Who owns the
[00:17:33] surface that agent works against. And
[00:17:35] that that is why Jensen should be
[00:17:38] watching. And frankly, the other major
[00:17:41] AI player should have been paying
[00:17:42] attention here. Because I don't think
[00:17:44] the first trillionaire is going to get
[00:17:45] decided by who IPOs this summer. I think
[00:17:49] it's going to be more useful to ask
[00:17:51] ourselves, if you want to create lasting
[00:17:53] wealth from AI, who is going to own the
[00:17:56] surface that a billion people touch AI
[00:17:59] through?
[00:18:00] Apple has a path to that. Apple is
[00:18:02] building that path. WWDC exposed for all
[00:18:05] of us the roadmap they're using to build
[00:18:08] that path. Pay attention.
[00:18:10] Because if you don't, you're going to
[00:18:12] get distracted by the headlines tomorrow
[00:18:14] and the next day and the next day about
[00:18:16] frontier model this and that. Apple
[00:18:18] wants to be synonymous with AI for
[00:18:20] billion people. If they are, the rest of
[00:18:24] the AI race is going to change entirely
[00:18:26] because they will have won the last mile
[00:18:28] that drives actual trust.
[00:18:30] So, let me know what you think in the
[00:18:31] comments and I'll see you next time.
