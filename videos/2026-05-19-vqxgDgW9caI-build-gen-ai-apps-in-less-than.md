---
video_id: vqxgDgW9caI
title: "Build Gen AI apps in less than 5' with Genkit - Xavier Portilla Edo"
channel: Gen AI Summit EU - Valencia
url: "https://www.youtube.com/watch?v=vqxgDgW9caI"
watched_date: 2026-05-19
watched_at: "2026-05-19T12:00:00Z"
watch_count: 1
duration_seconds: 2455
source: youtube-history-browser
history_label: May 19
history_order: 181
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 246
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Firebase Genkit is an open-source, lightweight framework (~5MB) created by Google for building generative AI applications, available in TypeScript, Go, Python, Dart, and Java. The framework abstracts over multiple LLM providers (OpenAI, Anthropic, Gemini, GitHub Models, AWS Bedrock, etc.) through a unified API, eliminating provider-specific SDK differences. Core features include: a local developer UI (on localhost:4000) for testing prompts, tools, flows, and evaluations in real-time; a plugin system for LLMs and vector databases; `.prompt` files for separating prompt iteration from code; observability via OpenTelemetry and Firebase AI Monitoring; and MCP server support. Xavier Portilla Edo demonstrated building a production-ready weather app in ~60 lines of code using Express.js, GitHub Models, and the OpenWeather API, with complete tracing of model calls, tool execution, token usage, and latency visible in the dev UI.

To start using Genkit, visit genkit.dev to access documentation for your language. Install the framework, initialize it with your chosen plugins, define tools (functions with schema validation), create prompts and flows, then run `genkit develop` to spin up the local dev UI for testing before deploying. For learning, read the open-source "Mastering Genkit" book (free PDF on GitHub or physical copy on Amazon) which includes hands-on workshops in each chapter. In production, enable observability with a single flag or environment variable to stream the same traces you see locally to platforms like Google Cloud Monitoring, Datadog, or Firebase AI Monitoring—no code changes required. Use GitHub Models for immediate API access with just a GitHub token, and separate your prompts into `.prompt` files to iterate independently of your source code.

## Transcript

[00:00:03] [music]
[00:00:10] It's rare to hear a conversation that so
[00:00:12] effectively bridges the gap between the
[00:00:15] halls of the Romanian Parliament and the
[00:00:17] supercomputers at the Barcelona
[00:00:19] Supercomputing Center. The panel left us
[00:00:22] with a powerful takeaway. Governance is
[00:00:25] not a post-launch checklist. It's a set
[00:00:28] of design constraints that must be in
[00:00:31] your architecture from day one. As we
[00:00:34] move into our next session, we're
[00:00:36] shifting from the why of governance to
[00:00:39] the how of rapid development. Our next
[00:00:42] session focuses on Firebase Genkit,
[00:00:45] which is no longer just a Firebase tool.
[00:00:49] It's a uniform It's a unified platform
[00:00:51] agnostic API that works across other
[00:00:55] platforms allowing you to deploy it
[00:00:57] wherever your infrastructure lives.
[00:01:00] Sounds interesting, huh? To guide us
[00:01:02] through this, we have one of the most
[00:01:04] prolific builders in the European
[00:01:06] ecosystem. Shavier Porta Edo is the head
[00:01:09] of cloud infrastructure at VoiceFlow
[00:01:11] where he manages the massive
[00:01:13] architectural demands of one of the
[00:01:14] world's leading conversational AI
[00:01:17] platforms. But Shaveier is also a
[00:01:20] central figure in the development of the
[00:01:22] tools we use. He's a member of the
[00:01:25] Genkit core team at Google and the
[00:01:28] author of the book Mastering Genkit. His
[00:01:31] credentials speak from themselves. He's
[00:01:33] a Google developer expert in both cloud
[00:01:36] and AI, a Microsoft MVP and a GitHub
[00:01:41] star. Shavead doesn't just talk about
[00:01:43] cloud infrastructure, he builds it at
[00:01:46] scale, ensuring it also meets rigorous
[00:01:49] standards. So, please welcome to the
[00:01:51] main stage the head of cloud
[00:01:53] infrastructure at VoiceFlow at Genkit
[00:01:55] Core member Javier Portiga Edo.
[00:02:03] Right,
[00:02:07] perfect. Uh, so I've been told to do
[00:02:10] this in English, but if you have any
[00:02:12] question in Spanish or even in Valencia,
[00:02:14] feel free. Uh, well, thank you so much
[00:02:17] for inviting me to all the uh the GNI uh
[00:02:22] summit uh stuff. Uh, it's always good to
[00:02:26] to be back home. Um today well this
[00:02:29] session is going to be more hands-on
[00:02:32] session I would try to well we are going
[00:02:34] to be touching some code um and we are
[00:02:37] going to be building jenna apps in less
[00:02:39] than five minutes with jen kit um a
[00:02:43] little bit about myself really quick you
[00:02:46] can follow me on social media at
[00:02:47] shabidob uh as as she said uh I'm
[00:02:51] working at boys flow as a head of cloud
[00:02:53] infrastructure boys is a Canadian
[00:02:55] startup I'm part of the Jenkit framework
[00:02:58] at Google and I'm doing some teaching
[00:03:00] and some research at Princeton
[00:03:02] University, New Jersey. I have uh at
[00:03:06] shabby.mme that's my website uh where
[00:03:09] you can find like my books, articles,
[00:03:12] talks like this one.
[00:03:15] So what's Yankit? Uh we're going to be
[00:03:19] today we're going to be seeing what's
[00:03:20] Yenkit the features Yenkit versus the
[00:03:22] other frameworks of course and then the
[00:03:24] key takeaways.
[00:03:27] First of all, what's Jenkit? Jenkit is
[00:03:29] an open source framework to build genai
[00:03:32] apps. Uh it was built by Google by the
[00:03:35] Firebase team and now belongs to the uh
[00:03:38] Google developer X organization within
[00:03:41] Google. So that means that belongs to
[00:03:44] the same internal org as the Golan
[00:03:47] language as the Dart language as
[00:03:49] flatter. Okay. Now Jenkit is another
[00:03:53] another uh framework in there. When the
[00:03:57] Jenke started that was in 20 24
[00:04:02] um it supported two main languages that
[00:04:05] was JavaScript and Golang
[00:04:07] and uh it's built by Google but it's
[00:04:10] open source and it is not only for all
[00:04:13] the Gemini models you know like Google
[00:04:15] cloud and all that stuff it's for
[00:04:17] everything as of today. Uh, Jenkit is
[00:04:21] also available in Python. That's in
[00:04:24] preview. It's also available in Dart for
[00:04:28] Flatter developers. Any flatter debs
[00:04:31] here?
[00:04:32] Nice. Nice. I love you.
[00:04:36] Um, which is a quite interesting as a
[00:04:40] framework and also in Java. I I'm part
[00:04:43] of, as I said, I'm part of the of the
[00:04:46] core team in Yankit. I'm the principal
[00:04:48] engineer for Java and I'm leading the
[00:04:51] integrations for uh Jenkit Go and Jenkit
[00:04:54] Typescript
[00:04:56] uh with uh external cloud providers like
[00:04:59] Azure uh AWS bedrock etc.
[00:05:04] So these are the principles for the
[00:05:06] framework. The framework is uh really
[00:05:09] simple to use. I will show you in a bit.
[00:05:12] It really lightweight. We are talking
[00:05:14] about I think less than five megabytes
[00:05:17] as a framework as a library itself.
[00:05:20] Production ready. I will I will show you
[00:05:23] why Jenkit is production ready.
[00:05:25] Everything is code. Whenever you are uh
[00:05:28] building your stuff using Jenkit,
[00:05:30] everything is uh is in code. And then
[00:05:34] the developer tools. Okay. Most of the
[00:05:36] things that you are going to see here
[00:05:38] about Jenkit probably you will see those
[00:05:41] features in other frameworks like I
[00:05:44] don't know like lang chain like lama
[00:05:45] index versel SDK but where really stands
[00:05:50] out uh in Jenkit uh is the uh the
[00:05:54] developer tools okay I I'll show you in
[00:05:56] a bit as well Jenkit has three main
[00:05:59] pieces the first one is the framework
[00:06:01] itself the library the a CLI And then
[00:06:06] the dev UI.
[00:06:08] So
[00:06:10] Jenki features the this is your source
[00:06:13] code if you are not using uh a
[00:06:16] framework.
[00:06:18] Basically, as you may know, there are a
[00:06:20] bunch of uh a bunch of models. You know,
[00:06:23] there you have the OpenAI ones, you have
[00:06:25] Geminina ones, you have anthropic ones,
[00:06:27] Olama, and many more. And all of them
[00:06:31] are really good and some of them are
[00:06:32] really good to one specific thing, some
[00:06:35] of those are really good to another
[00:06:37] specific thing. And sometimes in your
[00:06:39] backend apps um in your geni
[00:06:43] applications you are using one model for
[00:06:46] one specific task and another one for
[00:06:48] another uh specific task or you know
[00:06:52] same as you like one cloud provider for
[00:06:54] one thing and another one cloud provider
[00:06:55] for another thing just because I don't
[00:06:57] know like you get some free credits and
[00:06:59] you are using cloud for example. So
[00:07:04] the the bad thing of not using any
[00:07:07] framework when uh in your source code is
[00:07:09] basically you will need to uh install
[00:07:12] the the main um SDKs and every single
[00:07:18] SDK has its way of initialize to invoke
[00:07:21] the model and all that stuff as you see
[00:07:23] here. Um even though they are using the
[00:07:26] same open API
[00:07:29] um capabilities but the uh the SDK is
[00:07:34] like you know like different teams,
[00:07:36] different companies, different
[00:07:37] libraries, different way of initializing
[00:07:39] this Jenkit uh in uh this is how you
[00:07:45] know like Jenkit resolves the issue.
[00:07:48] What you're seeing there is the the
[00:07:51] model interface is the generate
[00:07:53] function. And this is JavaScript. But
[00:07:55] again like what you are going to be
[00:07:57] seeing here in JavaScript you can uh you
[00:08:01] will have this available in in Python uh
[00:08:04] Dart Java and Go the
[00:08:09] how is it called the uh the features are
[00:08:13] exactly the same but you like in in in
[00:08:15] those specific languages. So the what
[00:08:18] you have here is essentially the
[00:08:20] generate function where you specify the
[00:08:22] model and then you specify the prompt.
[00:08:24] Again everything is code and whenever
[00:08:27] you want to change the model or whenever
[00:08:29] you want to change the cloud provider
[00:08:30] the only thing that you need to change
[00:08:31] is you know the uh that line. So from
[00:08:36] the source code perspective and
[00:08:37] maintainability and even if you want to
[00:08:39] run AB testing uh because you're like
[00:08:42] there are there are new models every
[00:08:44] single day uh you just need to change
[00:08:47] that line the prompt and everything uh
[00:08:50] from there on will will just stay.
[00:08:55] This is uh the uh deb UI. Okay, this is
[00:08:59] really cool. Whenever you are building
[00:09:02] um
[00:09:03] the uh a geni app using Jenkit and you
[00:09:07] run the Jenkit CLI, it will spin up in
[00:09:09] local host. This is really really really
[00:09:12] important here in local host in the port
[00:09:14] 4,000 a dei. The debui is essentially a
[00:09:18] playground where you can test and
[00:09:21] validate all your backends. The CLI will
[00:09:24] read all the objects, all the the Jenkit
[00:09:27] objects that you are creating under the
[00:09:29] hood. That means all your prompts, all
[00:09:31] your tools, all your evaluations,
[00:09:33] everything will be exposed by the
[00:09:36] framework and read by the CL by the CLI
[00:09:39] and you can explore them in local host.
[00:09:42] This is what uh Genkit has and not any
[00:09:47] other uh framework has in place with at
[00:09:50] least with all the capabilities that it
[00:09:52] has. uh we will show you in action when
[00:09:54] when I am uh showcasing the the the
[00:09:57] code. It's really cool. That's one of
[00:10:00] the things that I love the most of the
[00:10:02] framework.
[00:10:06] In terms of plugins available for
[00:10:08] jenkit, there are a bunch of them of
[00:10:10] course the main ones uh you know like
[00:10:12] openai as your foundry cohhere anthropic
[00:10:16] github models grog aws bero kama hagging
[00:10:19] face mistral deepseek
[00:10:22] and uh for vector databases are also a
[00:10:25] bunch of plugins for the most of the or
[00:10:29] the most used vector databases like
[00:10:32] chroma quadrant web8
[00:10:35] um pine Pine cone uh possess vectors
[00:10:39] fire store etc. As I said before the the
[00:10:44] ones that are here in green and uh sorry
[00:10:47] in black and orange are the ones that
[00:10:49] I'm maintaining mainly in Java Go and uh
[00:10:54] and JavaScript.
[00:10:56] If you see that you know you want to
[00:10:57] integrate with any external model and
[00:11:01] you don't see a plug-in available build
[00:11:03] a plug-in is really really easy and
[00:11:07] probably in I don't know like in one
[00:11:09] evening one afternoon you will have your
[00:11:12] plug-in available okay
[00:11:15] I'll show you in a bit how that works
[00:11:18] okay so what about pron how genet
[00:11:21] uh thinks about is really similar to the
[00:11:25] genetic generate function. Um what we
[00:11:28] have in here instead of the generate
[00:11:30] function we have the define pro
[00:11:33] function. Okay, in this way the for to
[00:11:37] in order to define a prompt you have to
[00:11:39] do a couple of things. First is to give
[00:11:41] a prompt. In this case it's a hello
[00:11:43] prompt and then you can specify an input
[00:11:46] schema and output output schema. Uh we
[00:11:50] are using sod for validation. So that
[00:11:53] means that whenever you are um you are
[00:11:57] calling this prompt, we are going to be
[00:11:59] validating uh the input schema and also
[00:12:03] the output schema. And whenever you are
[00:12:05] writing code within your prompt in your
[00:12:07] visual studio code or in the in the ID
[00:12:10] that you are using in the intellisense
[00:12:12] whenever you put here input dot it will
[00:12:16] show you that input has in this case for
[00:12:18] example
[00:12:20] um has a schema and that schema has a
[00:12:22] property which is a string. Okay. again
[00:12:25] because the main focus of Jenkit is uh
[00:12:28] not only you know like to make the code
[00:12:31] a little bit cleaner but also to have
[00:12:34] the best developer experience out there.
[00:12:38] >> Um
[00:12:40] so these are prompts there there are
[00:12:42] another way that you can define prompts
[00:12:46] using Yenkit. What you are seeing here
[00:12:48] is what we call aprompt file. Apr file
[00:12:53] has two main sections. The first one is
[00:12:57] the one that you specify the model
[00:13:00] configuration and you can also specify
[00:13:02] the input schema and the output schema.
[00:13:04] That's the first section. And then you
[00:13:08] have the second section. The second
[00:13:10] section is essentially the prompt
[00:13:12] itself. And it uses a handlebars which
[00:13:16] is a templating language. So that's why
[00:13:18] you are seeing here some sort of you
[00:13:21] know like between brackets uh the
[00:13:23] location or some sort of eels I don't
[00:13:26] know if you are familiar with uh hem
[00:13:29] charts is some sort of similar
[00:13:33] um
[00:13:34] so in jenkit instead of calling the
[00:13:36] define prompt and writing the prompt in
[00:13:39] the um in in JavaScript or python or
[00:13:42] whatever you can point to this file.
[00:13:47] Okay. And why we have designed the prom
[00:13:49] file. So essentially when you are
[00:13:52] building a gen a genative AI application
[00:13:54] most of the time just like you let's say
[00:13:58] that you have your source code and then
[00:14:00] you have your prompts. The source code
[00:14:02] itself that's something that you can
[00:14:04] probably build I don't know let's say in
[00:14:06] one hour and then you are iterating over
[00:14:08] and over and over again in your prompt
[00:14:12] probably two hours three hours to make
[00:14:14] the prompt work.
[00:14:16] um to make it work and also with the
[00:14:19] model that you are using
[00:14:22] also uh sometimes uh the you know like
[00:14:26] it's always to it's always important to
[00:14:29] separate what is the the prompt and the
[00:14:31] source code of your files because they
[00:14:33] they could probably have different
[00:14:35] cadence and what does that means is that
[00:14:36] you are going to be releasing you know a
[00:14:38] new version of your of your application
[00:14:42] and then you can release uh versions of
[00:14:44] the prompt without changing the source
[00:14:46] code. That's why you have to separate or
[00:14:49] it's a best practice to separate the
[00:14:50] prompts from your source code. So
[00:14:52] whenever you want to change I don't know
[00:14:54] the model or the prompt itself to to be
[00:14:57] more restrictive you just change the
[00:14:59] doprom file you publish your dom file
[00:15:02] but the source code remains the same.
[00:15:04] Okay, separations of concerns
[00:15:06] essentially.
[00:15:10] Um, again this is the local DUI. Uh, so
[00:15:14] whenever you create a flow, whenever you
[00:15:17] create a prom, whenever you create um a
[00:15:21] tool, MCB whatever it will show up here
[00:15:24] automatically and again in local host.
[00:15:28] This is open source as well. Okay, this
[00:15:31] is very similar to for instance like any
[00:15:33] other LLM observability tool like
[00:15:36] Langfuse for lang chain uh but you know
[00:15:40] running locally in local host which is
[00:15:43] um which is outstanding.
[00:15:47] Um,
[00:15:49] another thing that you can do with um
[00:15:53] with the local Deb UI is the traces.
[00:15:56] Whenever you are interacting with the
[00:15:58] with the Deb UI, I will show you in a
[00:16:00] bit in action. But essentially like
[00:16:03] whenever you invoke a flow, whenever you
[00:16:04] invoke a prompt, whenever you invoke a
[00:16:07] tool, you will show the trace. The trace
[00:16:10] in a standard way. That means that you
[00:16:12] will see when the model is invoked, when
[00:16:15] the model requests the tool, when the
[00:16:16] tool is executed and uh the and the
[00:16:20] final model aggregation with the tool
[00:16:23] output etc. You will see the the whole
[00:16:25] trace plus the metrics plus the tokens
[00:16:27] used plus the thinking tokens everything
[00:16:31] uh just in again in local host in the
[00:16:34] web UI
[00:16:36] tools. For those that are not familiar
[00:16:39] to what is a tool, it's basically the
[00:16:41] way uh to connect the LLMs with the real
[00:16:44] world. Um in this case to define a tool
[00:16:49] um
[00:16:51] we are using or Jenkit has the the the
[00:16:55] function called define tool and the the
[00:16:58] other stuff is exactly the same. You
[00:17:00] have you have to define a name. You have
[00:17:02] to define a description. The description
[00:17:04] is really important because the
[00:17:05] description is what we are using to uh
[00:17:09] to tell the LLM like okay we have this
[00:17:12] tool and this is the description. So the
[00:17:14] tool can determine when to use that the
[00:17:16] LLM can determine where when to use that
[00:17:18] tool and you specify the input schema
[00:17:21] and the output schema also with uh in
[00:17:25] JavaScript we are using salt for
[00:17:27] validation okay and also the describe.
[00:17:31] So we are not only telling the LLM this
[00:17:33] is the tool that you have available but
[00:17:35] also we are telling the LLM that uh we
[00:17:38] have an input schema with a string that
[00:17:41] is the search query. Okay. So we are
[00:17:44] essentially providing more context to
[00:17:46] the LLM while we are creating this tool.
[00:17:48] Okay. This tool is is just search uh in
[00:17:51] a database of nodes.
[00:17:55] And uh and then next uh once we have
[00:17:58] created the tool uh we in this example
[00:18:01] we call the generate and we just add the
[00:18:03] tools. Okay. Here as an array
[00:18:07] with the with the tools that we have
[00:18:09] created again in the debiere here we
[00:18:12] will we will see the the generate we
[00:18:15] will see the tool and we can uh test
[00:18:17] whatever we want uh the tool separately
[00:18:20] the the prompt separately or all
[00:18:23] together.
[00:18:25] evaluations. Yenkit also as a framework
[00:18:27] supports evaluations. Uh evaluation is
[00:18:30] basically
[00:18:31] some sort of kind of like integration
[00:18:34] test where you can uh test your geni
[00:18:38] applications to make sure that are
[00:18:42] working or performing in the way that
[00:18:44] you that they should uh be performing.
[00:18:46] Okay, that means that you know they are
[00:18:49] let's say I don't know that you have an
[00:18:52] agent that I don't know is selling uh
[00:18:55] some specific brand of cars you can
[00:18:58] create an evalu an evaluation to make
[00:19:00] sure that whenever you ask something
[00:19:02] about your competitors they uh the agent
[00:19:05] is performing properly and it is not
[00:19:07] giving you information about your uh
[00:19:10] competitors for example that's an
[00:19:12] evaluation there are way more
[00:19:14] evaluations Jenkit has also a plug-in
[00:19:17] with a evaluators and uh and evaluations
[00:19:20] that you can use. Um and again once
[00:19:24] again in the dev UI whenever you create
[00:19:26] an evaluation whenever you create a data
[00:19:28] set that will show up and you can run uh
[00:19:31] those those evaluations at any time or
[00:19:33] with the CLI in your CI/CD platforms you
[00:19:36] can also uh run those evaluations. Okay,
[00:19:40] it's a best practice to have evaluations
[00:19:42] and it's a best practice to run those
[00:19:44] evaluations in your CI/CD pil especially
[00:19:47] when you're changing your models or when
[00:19:48] you're changing your uh your prompts.
[00:19:52] This is uh what I just said in the WI.
[00:19:54] It will show up under in the evaluation
[00:19:57] section uh with all the uh all the um
[00:20:02] how's it called the uh this is the the
[00:20:05] the data set and here are the evaluators
[00:20:09] that have been executed so far. Okay.
[00:20:16] Observability. Um this is something that
[00:20:18] you can plug into the framework when you
[00:20:22] deploy when you deploy a jenkit
[00:20:24] application. Let's say that you have um
[00:20:26] a server
[00:20:28] um I don't know like in nojs um express
[00:20:31] server okay and you're using jenkit
[00:20:34] jenkit by uh by itself it expose the
[00:20:38] same traces that you are seeing in the
[00:20:40] uh in the local dev UI those are being
[00:20:43] exposed as well uh when you are
[00:20:46] deploying that application in your
[00:20:48] infrastructure and if you have in your
[00:20:50] infrastructure observability platforms
[00:20:53] that means that if you have I don't know
[00:20:54] Let's say that you have Google cloud
[00:20:56] monitoring or you have data dog or new
[00:20:57] reel. Uh whenever you deploy a genkit
[00:21:00] app with the uh with observability
[00:21:03] enabled all the traces that you have in
[00:21:06] uh that you have seen in your local debi
[00:21:09] you will see that also in your
[00:21:10] observability platform. Okay. So uh not
[00:21:14] only traces but also metrics and you can
[00:21:17] create and monitor how your geni app is
[00:21:19] performing and you don't need to do any
[00:21:22] changes in your source code. is just a
[00:21:24] flag or an environment variable that you
[00:21:27] can just turn on and uh enable the the
[00:21:30] observability to expose uh all these
[00:21:33] traces. We're using open telemetry of
[00:21:36] course because it's the uh the
[00:21:38] observability I would say um standard
[00:21:42] for these type of things.
[00:21:46] You can also use Firebase AI monitoring
[00:21:48] since uh Yenkit started in the Firebase
[00:21:51] team. If you go to Firebase, for those
[00:21:54] that are not familiar with Firebase, I
[00:21:56] would say it's a some sort of like a
[00:21:59] mini cloud and more specifically for web
[00:22:01] apps uh and mobile apps. And there's a
[00:22:04] place that you can go there uh it's
[00:22:06] called Firebase AI monitoring and you
[00:22:08] can link your uh Jenkit application to
[00:22:11] the Firebase AI monitoring. This is just
[00:22:15] in case you don't have like a huge
[00:22:17] infrastructure with I don't know like
[00:22:18] data do setup or new relic setup you can
[00:22:21] just go there and with just you know
[00:22:22] like two three clicks you can enable
[00:22:25] this uh telemetry is is is not too
[00:22:28] expensive
[00:22:30] of course Jenkit as a framework it
[00:22:32] supports MCP you can create MCP servers
[00:22:35] you can connect to MCP servers okay uh
[00:22:38] I've uh I've explained what is a tool
[00:22:41] essentially an MPC an MCP server is a
[00:22:44] way to uh pack those tools and serve
[00:22:47] those tools to the to external
[00:22:51] uh servers
[00:22:54] in uh using the model context protocol
[00:22:58] um and and and so the others can can use
[00:23:02] your tool. So again, Jenkit supports
[00:23:05] both ways creating MCP servers and uh
[00:23:09] connecting to external MPC MCP servers.
[00:23:13] Um
[00:23:16] give me one second. Okay. Jenkin versus
[00:23:20] other frameworks. So far what I've
[00:23:23] explained is uh like is
[00:23:27] very similar to other frameworks in
[00:23:29] terms of uh like the capabilities you
[00:23:32] know like chain lama index versai uh
[00:23:36] Google ADK those have kind of the same
[00:23:39] capabilities but in this case um I would
[00:23:43] say that Jenkit was designed and
[00:23:46] developed from the application developer
[00:23:48] perspective because it born in the
[00:23:51] Firebase team when we talk about for
[00:23:54] instance lang chain or lama index those
[00:23:57] were designed uh from the you know like
[00:24:00] the ML or AI engineering perspective or
[00:24:04] mindset. Okay. So the learning curve for
[00:24:07] Jenkit as you saw is very low because
[00:24:10] you know in less than 500 lines you can
[00:24:12] have a gen up running and I will show
[00:24:15] you in a bit in action. uh whereas you
[00:24:18] know like whenever you want to build
[00:24:19] something really basic with lang chain
[00:24:20] or with lang graph you will need a bunch
[00:24:23] of lines of code the learning curve is
[00:24:25] pretty high
[00:24:27] the framework itself is pretty heavy and
[00:24:30] also whenever you want to upgrade for
[00:24:32] instance lang chain from one version to
[00:24:34] another usually it breaks and it breaks
[00:24:38] really hard
[00:24:40] um the I would say that the most similar
[00:24:44] framework to yankit is the Barcelia SDK
[00:24:46] K. But the burcell SDK does not have the
[00:24:49] local debiit.
[00:24:51] And Burcell AI SDK is more is very tight
[00:24:55] to the burcell ecosystem. That means NJS
[00:24:58] that means uh SAT CNN
[00:25:02] and and all the you know like the
[00:25:04] frameworks that Burcell has right now.
[00:25:07] One cool thing of the Brazil SDK is that
[00:25:10] it has a bunch of UI components that
[00:25:13] connects really well with the Brazil
[00:25:14] AISDK backend side. Uh, and Yenkit does
[00:25:17] not have that. Okay, essentially
[00:25:22] Yenkit is more like a very lightweight
[00:25:26] framework that just works and allows you
[00:25:29] to have early feedback. Okay, it's
[00:25:32] something that we call internally the
[00:25:34] the CFL mindset.
[00:25:38] I don't know if you are familiar with
[00:25:39] Google studio. Google studio is
[00:25:42] basically a platform that you can just
[00:25:44] go there uh on AI. Studio and you can
[00:25:48] build whatever you want. You can test
[00:25:50] your agents, you can uh build promps,
[00:25:52] you can build apps etc. Uh and something
[00:25:55] that Google has uh that Google has been
[00:25:59] doing for a while is using their own
[00:26:02] technology within the technology that
[00:26:04] happened also with Kubernetes. uh
[00:26:06] Kubernetes was open source uh but Google
[00:26:09] was using Kubernetes for a while. So
[00:26:12] Google I studio under the hood uses
[00:26:14] Yenkit. Okay. So that's that's something
[00:26:17] that I thought that was really cool to
[00:26:20] see. And whenever whenever you build
[00:26:23] something using Google I studio and that
[00:26:26] application requires a connection with
[00:26:29] an LLM you will see that the code that
[00:26:31] we will generate will will use genit.
[00:26:34] will add the dependency for you and and
[00:26:37] you will see it. Um, let me do a quick
[00:26:40] demo because I have 11 minutes left.
[00:26:45] All right,
[00:26:48] this
[00:26:56] can see. Okay. So, um, what
[00:27:02] what I'm going to show you here is
[00:27:04] really kind of like a hello world using
[00:27:07] Jenkit.
[00:27:08] We are going to build an an app that um
[00:27:14] gets you the weather using the open open
[00:27:16] weather API and using genit. Okay, so
[00:27:19] let's go line by line. The first thing
[00:27:22] is the dependencies. Okay. Of course,
[00:27:25] what you need to install is the the what
[00:27:29] you need to import, sorry, is the the
[00:27:31] Jenkit framework and Jenkit has the S
[00:27:35] for for you. So, you don't need to
[00:27:36] install the S library for validations.
[00:27:39] It is within the framework already.
[00:27:43] The first thing is that we are going to
[00:27:45] our app using uh Express which is one of
[00:27:48] the most popular NodeJS servers. H so we
[00:27:51] need the express plugin. We are going to
[00:27:55] be using in this case uh GitHub models.
[00:27:58] I don't know if you have heard about
[00:28:00] GitHub models. I love them. Those are if
[00:28:04] you go to or if you search for uh GitHub
[00:28:07] models is essentially a place within
[00:28:11] GitHub that you can uh playground and
[00:28:14] test uh the latest models and and just
[00:28:18] with your GitHub token you can integrate
[00:28:21] with those instead of you know like
[00:28:23] going to the Azure route and you're like
[00:28:26] creating an Azure account and all that
[00:28:28] stuff with GitHub token uh with GitHub
[00:28:32] models Using a GitHub to token is way
[00:28:35] easier. Okay.
[00:28:37] And it belongs to the GitHub
[00:28:40] organization and not to the Microsoft
[00:28:42] organization. So that means that is more
[00:28:44] dynamic.
[00:28:47] Um okay. So um of course we are going to
[00:28:50] be getting the the weather. So we need
[00:28:53] to install the open weather API node
[00:28:55] library. And then I'm reading the uh I
[00:28:59] have a M file with all the credentials.
[00:29:01] So I'm going to be reading that from
[00:29:03] from using M okay using the M config. So
[00:29:07] first thing first the once we have
[00:29:10] imported all the things that we want uh
[00:29:12] what we need to do is uh to initialize
[00:29:16] genkit okay it's just with this function
[00:29:19] and you can list here all the plugins
[00:29:21] that you are going to use in this case
[00:29:23] and we're are going to be using only the
[00:29:25] the GitHub model plugin is just you know
[00:29:28] like it's just like this then we are
[00:29:31] going to define a global model that
[00:29:33] means that you don't need to define a
[00:29:36] model every time that to create a prompt
[00:29:38] just you know like you can put it here
[00:29:40] and that's it.
[00:29:44] Next uh I explain you this in a bit.
[00:29:49] Next we're going to create the tool.
[00:29:50] Okay, again the tool is uh with the AI.
[00:29:55] This AI instance is uh given by uh by
[00:29:59] the Yankit framework and we are going to
[00:30:01] be calling the define tool. Okay, this
[00:30:04] again you we need to specify the name of
[00:30:07] the tool, the description that we're
[00:30:09] going to be given to the LLM to instruct
[00:30:11] it as a context and then the input
[00:30:13] schema and then the output schema. For
[00:30:16] the input schema, this one is a little
[00:30:18] bit more complex and I created this
[00:30:21] above. That's an object that has a
[00:30:24] property called location and it is um
[00:30:28] the type of string. Okay. and also the
[00:30:31] describe for the LLM.
[00:30:36] One thing that I love from here is like
[00:30:39] if you if you see this exact code in
[00:30:42] Python or Go or Java or that is going to
[00:30:46] be mainly the same. Okay. So let's say
[00:30:49] that I don't know like you have your
[00:30:51] code on uh Python and using Jenkit and
[00:30:55] you want to migrate your your your
[00:30:56] libraries to another language. uh you
[00:30:59] can do so probably with uh GitHub
[00:31:03] copilot or cloud code and say okay this
[00:31:06] is on jenke java or jenky javascript
[00:31:08] migrate this to python for example at
[00:31:10] any time okay and it will do it really
[00:31:13] really well let's continue with the um
[00:31:17] with the with the tool
[00:31:20] here is uh the the tool itself and and
[00:31:24] what I'm doing is connecting to the open
[00:31:26] weather API key using an and whether API
[00:31:29] key units metrics and I'm calling the
[00:31:32] initializing the client and calling the
[00:31:34] get current. Okay, this is what I was
[00:31:36] seeing before. What I was saying before
[00:31:39] that when I do input the IntelliSense is
[00:31:42] going to tell me, okay, I saw that you
[00:31:44] have an input schema that you know you
[00:31:47] have a location which is of type string.
[00:31:51] This is one of our main focus uh the
[00:31:54] developer experience. You always know
[00:31:56] when you're using a tool, when you are
[00:31:58] invoking a prompt, when you are creating
[00:32:00] a flow, you always know uh what is
[00:32:03] required as an input and what you're
[00:32:04] going to get as an output. Okay. And
[00:32:07] then the return is just you know the
[00:32:09] current weather with uh the location and
[00:32:11] then what we get from open weather API.
[00:32:15] Next thing we are going to define a
[00:32:17] flow. A flow is just a reusable function
[00:32:19] that you can invoke in uh in uh in
[00:32:23] Jenkit. Let's say you have the flow. The
[00:32:26] flow has the generating size and what
[00:32:29] you are going to invoke is the flow and
[00:32:31] what you are going to expose in the
[00:32:34] express server are the flows. The jenkit
[00:32:36] flows.
[00:32:38] Same same stuff here to define a flow
[00:32:41] from the AI instance that we get on top.
[00:32:43] We call define flow name hello flow
[00:32:47] input schema
[00:32:49] and output the schema. and we call the
[00:32:52] generate
[00:32:54] with the list of tools. In this case, we
[00:32:56] only have one tool. Okay. And then at
[00:32:59] the very end, we start the start flow
[00:33:02] server. This is coming from the express
[00:33:05] server
[00:33:07] uh sorry from the express plug-in for
[00:33:09] Jenkit and we specify the flows that we
[00:33:12] want to expose as an endpoint. And what
[00:33:14] it does is basically uh it runs this is
[00:33:16] going to be executing um a server and
[00:33:20] exposing a flow in this case hello flow
[00:33:23] in uh I think it's going to be in local
[00:33:26] host local host 8080
[00:33:30] flows hello okay again
[00:33:35] less than 100 line of codes around 60
[00:33:38] lines of code uh if you want to build
[00:33:40] something like this probably in line
[00:33:42] chain you We're going to have not only
[00:33:45] more lines of code but a huge monster as
[00:33:47] a dependency as well. Okay.
[00:33:51] When uh when we run this with the Jenkit
[00:33:54] CLI and with uh and and we run the local
[00:33:58] debi
[00:34:03] okay this is running in local host.
[00:34:06] Okay. 4,000 and what we are going to see
[00:34:08] on the right
[00:34:12] on the on your
[00:34:15] here [laughter]
[00:34:17] it's the um the models. Okay. Uh
[00:34:20] whenever whenever you add plugins let's
[00:34:23] say that you have I don't know like the
[00:34:24] anthrop anthropic plug-in Geminina
[00:34:27] plugin and GitHub model plugins you will
[00:34:29] see all the models loaded. So you can go
[00:34:33] here and literally use this as a
[00:34:36] playground and check just play with the
[00:34:38] models from here. Okay, you can enable
[00:34:43] tools if you have tools.
[00:34:45] You can check all the traces from here.
[00:34:48] Uh again in local host. So the uh
[00:34:52] everything is in one platform. For
[00:34:55] instance, let's say I don't know like
[00:34:57] here using the GitHub mod GBD 4.1
[00:35:01] and I just say hi
[00:35:07] this is uh the the output we are going
[00:35:10] to see the the trace for everything
[00:35:12] basically that that you know like I call
[00:35:15] the generate function well I mean the UI
[00:35:18] in this case called the generate
[00:35:19] function and it invoke the G the GitHub
[00:35:22] GPT uh uh 4.1 one model and we know the
[00:35:27] output tokens uh and input tokens uh
[00:35:31] latency input output and all the things
[00:35:34] that we need. This is really cool
[00:35:35] because whenever you deploy something
[00:35:37] using genit uh and again if you have an
[00:35:40] observability platform in your
[00:35:41] infrastructure already this is the exact
[00:35:44] same thing that you're going to be
[00:35:45] seeing there.
[00:35:47] Um as I said like whenever you create a
[00:35:49] flow a prompt a tool the dev UI will
[00:35:53] read it from your source codes and you
[00:35:54] can invoke it. You can come here and say
[00:35:57] okay what's the weather in Valencia. So
[00:35:59] you can go here and you like run it. I
[00:36:02] hope it works. There we go. And you see
[00:36:06] the trace details
[00:36:09] in this case you you can see that uh the
[00:36:12] flow was invoked the the flow called the
[00:36:15] generative method called the the model.
[00:36:18] the model say okay I need a tool the
[00:36:20] tool was called which is the get weather
[00:36:22] one
[00:36:24] and then we we have the the final
[00:36:26] generate with the with the the tool
[00:36:30] output and the and and and the final
[00:36:33] output essentially because that is what
[00:36:35] we have in here. Okay,
[00:36:40] you can
[00:36:42] test your tools um just you know like
[00:36:46] tools are just functions. Okay. So you
[00:36:48] can test themsel here. Um
[00:36:52] Jenke also supports uh rack systems. You
[00:36:55] can build as I said supports a bunch of
[00:36:58] um
[00:37:01] um a bunch of vector databases. So you
[00:37:03] can build your own indexers, your own
[00:37:06] retrievers and you can test them as well
[00:37:09] in the dev UI. Okay. As as well as the
[00:37:11] evaluators that that is said plus the
[00:37:13] the evaluations everything again in
[00:37:15] local host. Okay. And open source which
[00:37:18] is very very important in these days.
[00:37:23] Um so that's the live demo. Uh if you
[00:37:26] want to learn more about Jenkit have one
[00:37:29] minute left.
[00:37:31] I'm writing these books. The first one
[00:37:33] is live. The books are also open source
[00:37:37] as a framework. So if you search for
[00:37:39] mastering gen kit go edition that's
[00:37:41] live. If you want a physical copy you
[00:37:43] can get it on on Amazon. But uh you can
[00:37:48] download that's in a GitHub repo and you
[00:37:50] can download from uh from there the PDF
[00:37:54] and there's a website with the the whole
[00:37:57] with the whole book as well. Okay, there
[00:38:00] are I think around 12 or 15 chapters and
[00:38:04] in every single chapter you have um
[00:38:07] source you have some sort of like a
[00:38:10] task. Okay. So it's not just a pure book
[00:38:13] but also um a workshop in every single
[00:38:17] chapter.
[00:38:19] Um again
[00:38:21] jenke just to summarize open source open
[00:38:25] ecosystem through plugins and available
[00:38:28] right now in typescript go python dart
[00:38:31] which is probably very unique and uh in
[00:38:36] Java and before I finalize this
[00:38:41] the place to go is jenkit.dev deb that's
[00:38:45] the main website where you can see all
[00:38:48] the models here is for example the what
[00:38:51] what we have seen today with TypeScript
[00:38:54] but if you go with Python
[00:38:56] you know the basics of the framework so
[00:38:59] if you are a Python developer it's going
[00:39:01] to be like the concepts are essentially
[00:39:04] the same the f the features are
[00:39:06] essentially the same okay in Python in
[00:39:08] Go exactly the same in Dart exactly the
[00:39:12] same in Java the same Okay,
[00:39:15] we have brought everything to all the
[00:39:17] the languages.
[00:39:21] So, thank you so much for having me.
[00:39:26] And these are the the models.
[00:39:30] Try this is um well, a couple of things
[00:39:34] here.
[00:39:36] Discord the if you go to jenki.dev, you
[00:39:40] will find all the links. Okay, here is
[00:39:43] where you can find the source code for
[00:39:45] all the frameworks
[00:39:48] for all the languages sorry the main
[00:39:50] website there you can get the this
[00:39:53] discord link because this one is not too
[00:39:55] friendly but whenever you you like let's
[00:39:57] say that you are trying the framework
[00:39:59] you find an issue or whenever you want
[00:40:01] to I don't know like add a feature like
[00:40:03] just brainstorming drop something on the
[00:40:06] discord cuz all the team like we are
[00:40:08] actively looking to the to that and any
[00:40:12] feedback is really helpful for us for
[00:40:14] the feature of the of the framework and
[00:40:18] Google Cloud credits. If you go there,
[00:40:20] you uh get $5
[00:40:24] uh in your billing. You don't need to if
[00:40:26] you don't have a Google Cloud account,
[00:40:28] you can create it for free using very
[00:40:32] important a Gmail account and you will
[00:40:34] get a $5 credits. I think it those
[00:40:36] credits expires
[00:40:39] not sure when I think 3 months or 6
[00:40:42] months and uh but you know like you can
[00:40:45] you can use it to uh to experiment with
[00:40:48] Jenkit and that's pretty much it. Thank
[00:40:50] you so much
[00:40:53] [applause]
