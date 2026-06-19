---
video_id: 8oyZB24-vAM
title: DeepMind Was Two Steps Ahead, AGAIN!
channel: Pourya Kordi
url: "https://www.youtube.com/watch?v=8oyZB24-vAM"
watched_date: 2026-06-14
watched_at: "2026-06-14T12:00:00Z"
watch_count: 1
duration_seconds: 1866
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 72
watched_at_precision: date-from-history-label
watched_percent: 38
estimated_watched_seconds: 709
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

**What Was Discussed**

DeepMind is systematically moving beyond the standard transformer-autoregressive-generative architecture that powers current LLMs, pursuing four major research directions to reach AGI. First, they're modifying transformers through architectures like Griffin (which uses gated linear recurrence and local attention instead of global attention) and Titans (which learn to selectively memorize important information), achieving both efficiency gains and longer context windows. Second, they're actively exploring diffusion-based language models instead of pure autoregressive next-token prediction—diffusion can generate text 10x faster by refining multiple tokens in parallel with built-in error correction. Third, they're building world models through generative video (VEO, Gemini Diffusion), arguing that generating realistic video forces AI to implicitly understand physics, causality, and object permanence. Finally, they're combining these with large-scale pre-training as a foundation. The core disagreement is whether these innovations plus scaling will reach AGI, or whether fundamentally different architectures (like JEPA's joint embedding approach) are needed.

**What's Actionable**

If you're building AI applications with long context or memory constraints, monitor Gemma 4 and Griffin-based models as they become available—they achieve competitive performance with far fewer parameters and longer context windows (256K tokens). If you're researching language models, consider that diffusion-based alternatives may outperform autoregressive approaches for tasks requiring parallel refinement or mid-sequence edits (like code generation). Most importantly, the signal from DeepMind's sustained bet on world models through video generation suggests this is where the next research breakthroughs will come from—building systems that understand the physical world rather than just predicting text tokens.

## Transcript

[00:00:00] For years, the Mississippians has
[00:00:01] treated AGI as a long-term scientific
[00:00:03] mission to recreate the human mind, not
[00:00:05] just a race to build a profitable
[00:00:07] software product. When the word thought
[00:00:09] go was essentially unsolvable for AI,
[00:00:12] DeepMind went all in on AlphaGo,
[00:00:14] investing heavily with no immediate
[00:00:16] return. Right now, history is repeating
[00:00:18] itself. DeepMind is pouring resources
[00:00:20] into another seemingly intractable
[00:00:22] problem that nobody else wants to touch.
[00:00:24] Depending on how this plays out, they
[00:00:27] are either executing an extraordinary
[00:00:29] vision or one of the biggest
[00:00:30] miscalculations in modern history. To
[00:00:32] understand what DeepMind is building, we
[00:00:34] need to look at the blueprint of modern
[00:00:36] AI. It is held up by four main pillars:
[00:00:39] transformer based, autoregressive,
[00:00:41] pre-trained, and generative. Most
[00:00:43] researchers agree that this is a
[00:00:45] specific combination has enormous
[00:00:47] potential, but also has theoretical
[00:00:49] limitations that prevent it from
[00:00:51] reaching human-level intelligence. And
[00:00:53] that's exactly why DeepMind is already
[00:00:55] moving beyond it. The first piece of the
[00:00:57] puzzle is replacing pure transformer
[00:00:59] models. DeepMind has been working on of
[00:01:02] serious modifications to the
[00:01:03] transformer, seen in efforts like the
[00:01:05] Griffin architecture, recurrent Gemma,
[00:01:07] Titans, and even Gemma 4. The
[00:01:09] transformer is a very powerful idea.
[00:01:11] It's basically a stack of layers where
[00:01:13] each token repeatedly looks at all other
[00:01:16] tokens in the sequence, decides which
[00:01:18] ones matter most, and uses that to
[00:01:21] update its own meaning in context. This
[00:01:24] mechanism works very well because it can
[00:01:26] dynamically decide how each token
[00:01:28] relates to every other token in the
[00:01:30] sequence, which makes it very powerful
[00:01:32] for building context of representations.
[00:01:34] But, the trade-off is that it does not a
[00:01:37] scale cheaply. As the sequence gets
[00:01:39] longer, every token has to compare
[00:01:41] itself with every other token. So, the
[00:01:43] number of interactions grows roughly
[00:01:45] with the square of the sequence length,
[00:01:47] which becomes expensive very quickly.
[00:01:49] While modern systems still use
[00:01:51] attention, they rarely use fully naive
[00:01:54] all-to-all attention. Instead, they
[00:01:55] adopt a growing range of efficient
[00:01:57] approximities, sparse patterns, and
[00:01:59] hybrid architectures to control the
[00:02:01] quadratic cost while preserving most of
[00:02:03] the modeling power. Most leading labs
[00:02:06] have largely avoided experimenting with
[00:02:08] entirely new foundations, but DeepMind
[00:02:10] is actively exploring alternatives and
[00:02:12] extensions to the transformer, including
[00:02:14] recurrent and state-space inspired
[00:02:16] architectures. You might remember back
[00:02:18] in December 2024, Google released the
[00:02:20] famous Titans paper, learning to
[00:02:22] memorize at test time. The team has
[00:02:24] since moved to publish nested learning,
[00:02:26] and more recently, Titans plus Miras,
[00:02:29] helping AI have long-term memory. The
[00:02:31] idea for this approach is, instead of
[00:02:33] remembering everything all the time,
[00:02:35] what if we develop a specific strategy
[00:02:38] to keep only part of the input? Titans
[00:02:40] showed that the model can be more
[00:02:42] selective about what it keeps by using a
[00:02:44] surprise mechanism. They taught the
[00:02:46] model to memorize unexpected things, and
[00:02:48] it was able to become more effective on
[00:02:50] common sense reasoning, genomics, and
[00:02:52] time series tasks. This approach seems
[00:02:54] like a promising direction for
[00:02:56] complementing or extending transformers,
[00:02:58] and it could even help with continual
[00:03:00] learning since part of the adaptation
[00:03:02] happens at inference time. So far, it is
[00:03:05] perhaps the most notable approach to
[00:03:07] challenge pure transformer
[00:03:08] architectures, and almost all of the
[00:03:10] research behind it is still coming from
[00:03:12] DeepMind. But in a lesser-known release,
[00:03:15] Google introduced Recurrent Gemma,
[00:03:17] moving past transformers for efficient
[00:03:19] open language models based on the
[00:03:21] Griffin architecture. The Griffin
[00:03:22] architecture mixes, and I'll explain
[00:03:25] these fancy words in a second, gated
[00:03:27] linear recurrences with local attention.
[00:03:29] If we were to compare the standard
[00:03:31] attention to Griffin, it's something
[00:03:33] like this. The transformer is performing
[00:03:35] what we call global attention. Imagine
[00:03:37] you start reading a book. When you are
[00:03:39] reading the first page, there is
[00:03:40] virtually no difference between Griffin
[00:03:42] and a standard attention. But when you
[00:03:44] get to the second page, you have to tear
[00:03:46] the first one and have it right in front
[00:03:48] of you. If you keep reading in the page
[00:03:50] 100, when you have carried 99 previous
[00:03:53] pages, this method becomes an unbearable
[00:03:56] liability. That is stack of annoying
[00:03:58] pages that you had to carry all the way
[00:04:00] is the previous context. That is called
[00:04:02] the KV cache in a standard attention.
[00:04:04] But Griffin says, instead of having the
[00:04:06] entire thing carried over, introduce an
[00:04:08] index card that is constantly rewritten
[00:04:10] for every page. And instead of global
[00:04:12] attention, the model has only local
[00:04:15] attention. Something like 2,000 tokens
[00:04:17] to understand the context of the words
[00:04:19] within the current page. The AI
[00:04:21] synthesizes the core meaning of the
[00:04:23] input into a fixed size state. There is
[00:04:26] only one word left out, which is the
[00:04:28] gated part, and that's the trickiest
[00:04:30] part. The Griffin architecture relies on
[00:04:32] a bunch of matrices called gate weights
[00:04:34] that learn during the training the best
[00:04:36] strategies to retain information. Like
[00:04:38] they might learn bold words, a specific
[00:04:41] numbers, start of a new chapter, are
[00:04:43] more important and need to be
[00:04:45] remembered. But realistically, even much
[00:04:47] more complicated strategies of what
[00:04:49] makes thing worth remembering or not.
[00:04:52] And finally, when something is decided
[00:04:54] to enter the index card, there is a
[00:04:56] recurrence gate. This part looks at the
[00:04:59] past information and the new information
[00:05:01] and decides how best it can integrate
[00:05:04] them. Hypothetically, if you learn the
[00:05:05] main character in the book is tall in
[00:05:07] the first page and has blue eyes in the
[00:05:10] page 65, the index card will contain a
[00:05:13] unified representation of a main
[00:05:15] character that is tall and has blue
[00:05:17] eyes. So, the index card is an evolving
[00:05:20] a state of past information, not a list
[00:05:22] of items. The recurrent Gemma was a jump
[00:05:24] on benchmarks, especially related to
[00:05:26] long context. One of the rare
[00:05:28] transformer challenges that was given a
[00:05:30] decent shot at proving itself. DeepMind
[00:05:32] then squeezed the golden juice out of
[00:05:35] these experiments to build a model with
[00:05:37] maximum compute and memory efficiency.
[00:05:39] Gemma 4 first of all uses some sparsity
[00:05:42] methods to make the model much lower
[00:05:44] weight. For example, the 4 billion
[00:05:46] parameter model is actually about 25
[00:05:48] billion parameters, but Gemma has two
[00:05:50] categories of A and E that reduce the
[00:05:53] number of active or effective parameters
[00:05:56] using the mixture of experts or per
[00:05:58] layer embedding methods, which we don't
[00:06:00] get into because they are a bit off
[00:06:02] topic. But after that, the real
[00:06:04] innovation is how this tiny model that
[00:06:06] runs on edge devices is not only
[00:06:09] multimodal and accepts raw video and
[00:06:11] audio. It also has a long context of up
[00:06:14] to 200 and 56K tokens. The Gemma team
[00:06:17] achieved this using a local sliding
[00:06:19] window attention for some layers and
[00:06:22] global attention for others. Imagine
[00:06:24] you're reading a paragraph inside a huge
[00:06:26] book. You first put intense attention
[00:06:29] into that single paragraph. That's your
[00:06:31] local sliding window. But then after
[00:06:33] that, you can go back and read the
[00:06:35] relevant pages again, so you understand
[00:06:37] the paragraph in the full context of the
[00:06:39] book. In a document of let's say 256K
[00:06:42] tokens, some layers only look at a
[00:06:45] sliding window of 1,000 tokens and
[00:06:47] ensure local coherence, while a limited
[00:06:50] number of other layers take the entire
[00:06:52] global attention into account.
[00:06:54] Therefore, connect the local context to
[00:06:56] the entire document. These are just a
[00:06:58] number of more well-known, more mature
[00:07:00] attempts at optimizing, extending, or
[00:07:02] outright replacing the transformer.
[00:07:04] These attempts might seem like consumer
[00:07:06] products, but more than anything, they
[00:07:08] are public experiments serving
[00:07:09] DeepMind's core strategy towards AGI.
[00:07:12] >> We need one or two more big
[00:07:13] breakthroughs before we'll get to AGI.
[00:07:15] And I think they're along the lines of
[00:07:17] things like continual learning, better
[00:07:19] memory, longer context windows, or or
[00:07:21] perhaps more efficient context windows
[00:07:23] would be the right way to say it. So,
[00:07:24] don't store everything, just store the
[00:07:26] important things. That would be a lot
[00:07:27] more efficient. That's what the brain
[00:07:29] does.
[00:07:29] >> Right alongside the transformer, though,
[00:07:31] is another key idea called auto
[00:07:33] regression. As you probably know, the
[00:07:35] generation process in GPTs is next token
[00:07:37] prediction in an iterative process. That
[00:07:40] process is so well-known that some
[00:07:41] people might assume that the transformer
[00:07:43] and even the entire LLM space is
[00:07:45] inherently next token predictors. But
[00:07:47] even the original transformer that was
[00:07:49] invented for translation wasn't a pure
[00:07:52] autoregressive model. It was only turned
[00:07:54] into a decoder only transformer that is
[00:07:57] fully autoregressive by Alec Radford to
[00:07:59] go from the original intended machine
[00:08:01] translation function to a more general
[00:08:03] self-supervised next token predictor.
[00:08:05] The main invention of the transformer
[00:08:07] was the self-attention mechanism that we
[00:08:09] talked about. And that doesn't require
[00:08:11] next token prediction or auto
[00:08:12] regression. So there is a whole area of
[00:08:14] transformer base but not auto regressive
[00:08:17] models. Diffusion language models are
[00:08:18] the best example of that. Listen to
[00:08:20] Professor Stefano Ermon, one of the
[00:08:22] pioneers of diffusion models.
[00:08:24] >> All existing or most of the existing
[00:08:26] LLMs are auto regressive, meaning that
[00:08:28] they generate text or code
[00:08:30] one word, one token at a time, left to
[00:08:33] right. On the other hand, some of the
[00:08:35] best generative models for images,
[00:08:37] video, music are diffusion based where
[00:08:40] the object is generated by an iterative
[00:08:43] refinement process where you start with
[00:08:45] a rough guess what the answer should be
[00:08:47] and then you keep refining it.
[00:08:49] And crucially, this refinement process
[00:08:51] is highly parallel. The neural network
[00:08:53] is able to modify multiple tokens at the
[00:08:56] same time.
[00:08:57] >> Why is that better?
[00:08:58] >> This generative process is significantly
[00:09:00] more efficient. It's faster, it's
[00:09:02] cheaper and because there is also
[00:09:04] built-in error correction, the network
[00:09:06] is trained to fix mistakes and that's
[00:09:08] how model is learning at inference time.
[00:09:11] What we see is it's the future where all
[00:09:13] LLMs are going to be eventually
[00:09:15] diffusion based because this is
[00:09:17] uh
[00:09:18] far superior approach.
[00:09:19] >> There are three main advantages to
[00:09:21] diffusion models and we talk about them
[00:09:23] very briefly here. Speed and efficiency.
[00:09:25] Although diffusion models loop as well,
[00:09:27] they usually need far fewer iterations
[00:09:29] to reach a final answer because the
[00:09:31] process is much more parallel which GPUs
[00:09:34] love. A reasonable number of steps for
[00:09:36] language is often in the tens or at most
[00:09:38] low hundreds as opposed to thousands or
[00:09:41] even tens of thousands of steps for
[00:09:43] auto-regressive models. That's why
[00:09:44] diffusion language models are already
[00:09:46] about 10 times faster in practice.
[00:09:49] Smarter outputs. Auto-regressive LLMs
[00:09:51] generate text from left to right. Once a
[00:09:53] token is generated, there is no
[00:09:54] opportunity to revise it. Diffusion
[00:09:56] models on the other hand can more
[00:09:58] naturally correct mistakes by working on
[00:10:00] the entire response holistically. Third,
[00:10:02] flexibility. While auto-regressive
[00:10:04] models expect the prompt to be a prefix,
[00:10:06] diffusion LLMs allow the prompt to sit
[00:10:09] at any arbitrary position. This
[00:10:11] especially makes a lot of sense for
[00:10:13] writing code. Diffusion model is
[00:10:14] naturally trained to see the entire code
[00:10:17] and complete the missing part. But
[00:10:19] auto-regressive models struggle because
[00:10:21] they don't naturally see what comes
[00:10:23] after the edit. They have to engage in
[00:10:25] this awkward computation and often
[00:10:27] rewrite the parts that they are not
[00:10:29] supposed to touch. It is not obvious
[00:10:31] that a scale is not going to just wash
[00:10:33] over all of these differences. And it
[00:10:35] might not be worth it to go back and
[00:10:37] start from the beginning. But although
[00:10:39] everyone else is essentially ignoring
[00:10:41] diffusion models, a super small lab out
[00:10:43] of a Stanford called Inception Labs has
[00:10:45] already introduced the first reasoning
[00:10:47] LLM powered by diffusion. It is
[00:10:49] ridiculously faster than models of its
[00:10:51] size while being competitive in quality.
[00:10:53] This is the sort of jump that forces
[00:10:55] reimagining the stack. Google DeepMind
[00:10:57] is the only major lab working on a
[00:10:59] diffusion language model and they
[00:11:01] introduced Gemini Diffusion mid-2025.
[00:11:04] is still out on the importance of
[00:11:06] diffusion language modeling. It might
[00:11:07] even be that a hybrid approach could
[00:11:10] work really well. But that's just one
[00:11:12] aspect of diffusion. While OpenAI and
[00:11:14] Anthropic are 100% focused on
[00:11:16] auto-regressive transformer models and
[00:11:18] OpenAI even recently shut down Sora 2, a
[00:11:20] diffusion-based model, letting go of a
[00:11:22] billion-dollar contract with Disney
[00:11:24] because of the decision to double down
[00:11:26] on the GPT technology.
[00:11:28] >> But the thing that's important to
[00:11:29] realize is technologically that the Sora
[00:11:31] models, which are incredible models, by
[00:11:33] the way,
[00:11:34] are different branch of the tech tree
[00:11:36] than the core reasoning GPT series. Mhm.
[00:11:40] They're just built in a very different
[00:11:41] way. And to some extent, we're really
[00:11:43] saying that pursuing both branches is
[00:11:46] very hard for us to do.
[00:11:48] >> Google DeepMind has lots of different
[00:11:49] projects built on different stacks.
[00:11:51] >> And their mindset is apparent in the
[00:11:53] diverse projects they maintain. We'll
[00:11:55] talk about the importance of these
[00:11:57] projects, not just as cool media
[00:12:00] generators, but as part of the core
[00:12:02] strategy towards AGI. They have VEO and
[00:12:05] Genie, Gemini diffusion, the Imagine
[00:12:07] lineup, which is diffusion-based image,
[00:12:09] Vias the Nano Banana line that is based
[00:12:12] on Gemini, the Gemma family, AlphaFold
[00:12:14] {slash} AlphaGenome line, and many more
[00:12:16] projects. Even though these models
[00:12:18] consume massive amounts of compute and
[00:12:20] research capacity,
[00:12:21] >> And so I think there's something about
[00:12:22] if you're if you branch too far and you
[00:12:23] have two different artifacts, that is
[00:12:25] very hard to sustain in a world where
[00:12:28] there is limited compute.
[00:12:29] >> DeepMind is betting they are for the
[00:12:31] next stage.
[00:12:32] >> This is one advantage we have of having
[00:12:34] such a deep and rich research bench. We
[00:12:36] can go after both of those things at
[00:12:38] maximum with maximum force, both, you
[00:12:41] know, scaling up the current paradigms
[00:12:44] and ideas and
[00:12:45] and then really new blue sky ideas for
[00:12:48] new architectures and things, you know,
[00:12:50] the kinds of things we've invented over
[00:12:51] the last 10 years as Google and
[00:12:53] DeepMind.
[00:12:53] >> So far, it might seem like that DeepMind
[00:12:55] is just keeping every possible research
[00:12:57] direction open, but that is not quite
[00:12:59] the case. They are actually making a
[00:13:01] very specific bet on a very specific
[00:13:03] vision of how AGI should look like. And
[00:13:06] the picture becomes more clear in the
[00:13:07] next two pillars, generative and
[00:13:09] pre-trained. I've been playing around
[00:13:11] with some new AI tools lately, and
[00:13:13] honestly, it is getting a scary good. I
[00:13:15] feel like most people still think AI
[00:13:17] music is where it was about a year ago,
[00:13:19] where it sounded cool for like 10
[00:13:21] seconds and then completely fell apart.
[00:13:28] But I just generated this entire song,
[00:13:30] the beats, the vocals, everything.
[00:13:34] >> It's a lonely [singing] little heaven,
[00:13:39] but it's peaceful and it will do.
[00:13:41] [music]
[00:13:42] >> Using Mubert AI and it sounds absolutely
[00:13:45] incredible. Mubert is basically an AI
[00:13:47] music creation tool that can generate
[00:13:49] full studio quality songs,
[00:13:51] instrumentals, and background tracks.
[00:13:53] The interface is really easy to get
[00:13:55] into. You can switch between an easy
[00:13:57] mode and a custom mode, depending on how
[00:13:59] much control you want. Custom mode gives
[00:14:01] you a lot more flexibility to fine-tune
[00:14:03] the results. There are two main models,
[00:14:06] O2 that is built for generating a
[00:14:08] standalone full song,
[00:14:12] and V9, which offers precise control,
[00:14:15] studio-level mixing, enhanced
[00:14:17] multilingual support, and a stronger
[00:14:19] instrumental music effects. [music] It
[00:14:21] is highly flexible and efficient for
[00:14:23] custom generation and remixing in
[00:14:25] styles.
[00:14:25] >> [music]
[00:14:25] >> As a creator, finding a background music
[00:14:27] that actually fits your videos is
[00:14:29] extremely annoying. Even if you pay for
[00:14:31] premium subscriptions. I used Mubert's
[00:14:33] V9 model to generate a custom background
[00:14:35] track for this video's intro, and I can
[00:14:37] even use the new soundtrack feature for
[00:14:40] educational content. You can upload any
[00:14:42] video and automatically generate a track
[00:14:45] that fits the composition. The music
[00:14:46] [music] is royalty-free and cleared for
[00:14:48] commercial use, which makes the whole
[00:14:50] process way easier. Just as a side note,
[00:14:53] one of my favorite use cases is remixing
[00:14:55] Persian classical music into different
[00:14:57] languages and styles. Let me play two
[00:14:59] tracks that I've had on repeat lately.
[00:15:02] >> Kiss me, my love. [singing]
[00:15:06] >> [music]
[00:15:08] >> Kiss me, my love.
[00:15:11] >> [music]
[00:15:13] >> Just for the very last time.
[00:15:17] >> [music]
[00:15:20] >> I am [singing] the harvest
[00:15:24] that sleeps in
[00:15:26] the sea.
[00:15:31] >> For
[00:15:33] >> [singing]
[00:15:33] >> I am
[00:15:34] the morning breaking the dark.
[00:15:37] >> Check out Marika and give your videos
[00:15:38] their own custom AI generated
[00:15:40] soundtrack. Link in the description.
[00:15:42] Thanks Marika for sponsoring this part
[00:15:43] of the video. Here is Demis Hassabis
[00:15:45] explaining how he disagrees with Yann
[00:15:47] LeCun and why he's doubling down on a
[00:15:50] particular vision of AGI.
[00:15:52] >> Now, it remains to be seen whether just
[00:15:54] sort of scaling up existing ideas and
[00:15:56] technologies will be enough to do that
[00:15:59] or we need one or two more
[00:16:01] really big insightful innovations. I'm
[00:16:03] probably if you were to push me I would
[00:16:05] say I would be in the latter camp. But I
[00:16:07] think no matter what camp you're in,
[00:16:10] we're going to need large foundation
[00:16:12] models as the key component of the final
[00:16:15] AGI systems. Of that I'm sure. So I
[00:16:18] don't I'm not a subscriber to someone
[00:16:19] like Yann LeCun who thinks you know that
[00:16:21] they're just sort of a some kind of dead
[00:16:22] end. I think the only debate in my mind
[00:16:25] is are they a key component or the only
[00:16:28] component?
[00:16:29] >> A lot of people might automatically side
[00:16:31] with Demis because he's so popular and
[00:16:34] is doing very practical research, but
[00:16:36] you'll also easily get Yann's point when
[00:16:38] it's laid out in simple terms. He's one
[00:16:40] of the foundational architects of modern
[00:16:42] deep learning era. His work on
[00:16:44] convolutional neural networks in the
[00:16:45] 1980s and 90s directly shaped modern
[00:16:49] computer vision and neural network
[00:16:51] research in general. Yann explains that
[00:16:53] the self-supervised method of predicting
[00:16:55] the next token works in language because
[00:16:57] language itself is a constrained
[00:16:59] notation we made to communicate.
[00:17:01] >> So in the case of text, that's a very
[00:17:03] simple problem because you only have a
[00:17:04] finite number of words in the
[00:17:06] dictionary. And so you can never predict
[00:17:09] exactly what word follows a sequence,
[00:17:11] but you can
[00:17:12] predict a probability distribution over
[00:17:14] all words in the dictionary.
[00:17:16] Um and that's good enough. Uh, you can
[00:17:18] represent uncertainty in your
[00:17:19] prediction.
[00:17:20] >> The model has only about 50 to 100,000
[00:17:23] possible tokens for the output, and it
[00:17:25] can assign probabilities to them. But,
[00:17:27] when it comes to something like video, a
[00:17:29] natural modality, training a model on
[00:17:31] self-supervised video frames is
[00:17:33] impossible because the number of
[00:17:34] possible frames for a full HD video
[00:17:37] dwarfs the number of atoms in the
[00:17:38] observable universe. The number of
[00:17:40] possible futures is mathematically
[00:17:42] intractable.
[00:17:43] >> You can't do this with video. We do not
[00:17:46] know how to represent appropriate
[00:17:47] probability distribution over the set of
[00:17:49] all images or video frames or video
[00:17:51] segment. It's actually a
[00:17:53] mathematically intractable problem.
[00:17:55] So, it's not just a question of like we
[00:17:58] don't have big enough computers. It's
[00:17:59] just like intrinsically intractable.
[00:18:01] >> But, this argument is actually a bit of
[00:18:03] a straw man because no one is trying to
[00:18:05] predict every pixel on the screen. This
[00:18:08] is evidenced by all of these successful
[00:18:10] AI video generators, such as Sora,
[00:18:12] SeeDance 2.0, or VEO. The debate is
[00:18:14] actually far more nuanced than that. And
[00:18:16] this is probably the most fascinating
[00:18:18] argument at the center of AI right now.
[00:18:20] One of those defining disagreements that
[00:18:22] people will be still writing books about
[00:18:23] a decade from now.
[00:18:24] >> In a normal video diffusion model,
[00:18:26] researchers don't jump straight into
[00:18:28] predicting pixels. Instead, the process
[00:18:31] is more like this. You use an encoder to
[00:18:34] move the image into the latent space.
[00:18:36] You're essentially building a compressed
[00:18:38] visual language, a compact
[00:18:39] representation that is still allows for
[00:18:42] reconstruction. And this word is very
[00:18:44] important, reconstruction. Second, train
[00:18:46] a second model, like a diffusion model,
[00:18:49] inside this frozen latent space. You're
[00:18:51] essentially teaching it to write in this
[00:18:53] compressed visual language. It learns to
[00:18:55] denoise random noise into a valid
[00:18:58] latent, which you then decode back into
[00:19:00] pixels. Let me rephrase all of that
[00:19:02] outside the technical jargon and go into
[00:19:05] the philosophy of it. Instead of
[00:19:07] predicting inside the space of all
[00:19:09] possible future frames, modern video
[00:19:11] models do something much smarter. A cat
[00:19:14] walking across a room is not just any
[00:19:16] possible image. There are physics,
[00:19:19] geometry, object permanence, lighting,
[00:19:21] motion continuity, and camera
[00:19:23] constraints that massively reduce the
[00:19:25] space of plausible futures. So, the
[00:19:27] encoder compresses videos in a way that
[00:19:30] preserves the underlying regularities of
[00:19:32] the real world. It exploits the fact
[00:19:34] that real-world videos occupy an
[00:19:37] extremely tiny, structured subset of all
[00:19:40] possible frames, making the diffusion
[00:19:42] process vastly more tractable. But, here
[00:19:44] is the trillion-dollar question. Who
[00:19:46] cares? Why would Google DeepMind jump
[00:19:49] through so many hoops just to create a
[00:19:51] realistic-looking video? Strangely
[00:19:53] enough, this slot machine may be the
[00:19:56] clearest path we currently know toward
[00:19:58] AGI. In this part of the video, I have
[00:20:00] to bring so many different ideas
[00:20:02] together, so just bear with me. The
[00:20:04] biggest flaw in the current state of the
[00:20:06] art language models is a phenomenon
[00:20:08] called jagged intelligence. Today's
[00:20:10] models can achieve a gold medal in math
[00:20:12] olympiad and solve open mathematical
[00:20:14] conjectures, but still tell you to walk
[00:20:17] to a car wash because it is close
[00:20:19] enough. Other labs are publicly
[00:20:21] accepting this jaggedness, focusing on
[00:20:23] building narrow, but useful and probable
[00:20:26] tools.
[00:20:26] >> We are going to have AGI within the next
[00:20:28] couple years in a way that
[00:20:31] it's still going to be jagged, but that
[00:20:33] the the floor of task will just be
[00:20:36] almost for any intellectual task of how
[00:20:37] you use your computer. The AI will be
[00:20:40] able to do that.
[00:20:40] >> Um, but it's one thing that I think
[00:20:42] Anthropic have fully focused on. You
[00:20:44] know, they don't make image models,
[00:20:45] multimodal models, world models. They
[00:20:47] just do, you know, coding and language
[00:20:49] models. And um, they're very, very good
[00:20:51] at that.
[00:20:52] >> But, if the goal is AGI, we must solve
[00:20:54] this. The issue is spoken language, and
[00:20:57] especially written language, are just
[00:20:59] artificial artifacts of the human mind.
[00:21:01] Language is a super lossy compression of
[00:21:04] our inner model of the world, and it is
[00:21:06] not a fundamental part of human
[00:21:07] intelligence. Think about the difference
[00:21:09] between someone who has read a thousand
[00:21:11] books on Formula 1 racing and Lewis
[00:21:14] Hamilton. The reader knows all the facts
[00:21:16] and physics, but the driver has
[00:21:18] developed such a deep and robust
[00:21:20] understanding of how the machine works
[00:21:23] that the car essentially feels like an
[00:21:25] extension of his own body. The human
[00:21:27] mind relies on a wordless internal
[00:21:29] representation of reality. That is the
[00:21:31] core of intelligence. Generating the
[00:21:33] words to approximate that internal
[00:21:35] understanding is the trivial part in
[00:21:37] comparison. And this leads us to the
[00:21:39] holy grail of modern AI, the world
[00:21:42] model. The first step to building it,
[00:21:44] teaching machines to predict basic
[00:21:46] physics across primary natural human
[00:21:48] modalities, vision, sound, and touch.
[00:21:51] >> So, if you show a video to a computer,
[00:21:54] um and train some big neural net to
[00:21:56] predict what's going to happen next in
[00:21:57] the video,
[00:21:58] if the system is capable of learning
[00:22:00] this and doing a good job at that
[00:22:01] prediction, it will probably have
[00:22:03] understood a lot about the underlying
[00:22:05] nature of the physical world.
[00:22:07] Things that, you know, objects move
[00:22:09] according to
[00:22:11] uh particular laws, right? So, animate
[00:22:13] objects can move in things that are more
[00:22:15] unpredictable, but still, you know,
[00:22:17] satisfying some constraints.
[00:22:18] >> Now, Demis Hassabis' core argument is
[00:22:21] generative AI video can force AI to
[00:22:24] develop a physics-based natural world
[00:22:26] model.
[00:22:27] >> But, how is an image generator close to
[00:22:29] AGI?
[00:22:30] >> Oh, well, of course. Look, let's take
[00:22:31] image generators, but also uh let's talk
[00:22:34] about our video generator VO, which is
[00:22:36] the state of the art in video
[00:22:37] generation. I think that's even more
[00:22:38] interesting and from an AGI perspective.
[00:22:41] You know, you can think of a video model
[00:22:42] that can generate you 10 seconds, 20
[00:22:45] seconds of a realistic scene. It's sort
[00:22:47] of a model of the physical world.
[00:22:49] Intuitive physics, we sometimes call it
[00:22:51] in physics land. And it's sort of
[00:22:53] intuitively understood how uh liquids
[00:22:56] and and and and and objects behave in
[00:22:59] the world. And that's um and obviously
[00:23:02] one way to exhibit understanding is to
[00:23:04] be able to generate it at least to the
[00:23:06] to the to the human eye being accurate
[00:23:08] enough to to be satisfying to the human
[00:23:10] eye. Obviously, it's not completely
[00:23:12] accurate from a physics point of view
[00:23:13] and we're getting it we're we're going
[00:23:14] to improve that. But it's it's it's
[00:23:16] steps towards having this idea of a
[00:23:18] world model a system that can understand
[00:23:21] the world and the mechanics and the
[00:23:22] causality of the world. And then of
[00:23:24] course that would be I think essential
[00:23:26] for AGI because that would allow these
[00:23:28] systems to plan long-term plan in the
[00:23:31] real world.
[00:23:32] >> But although we now know empirically
[00:23:34] that even generative models have to
[00:23:36] develop some model of the world, Jan
[00:23:38] argues that this is not really a world
[00:23:41] model. The point of contention is that
[00:23:43] the whole encoder diffusion decoder
[00:23:46] stack we talked about is trained with
[00:23:48] one purpose to reconstruct the original
[00:23:51] image. And Jan's view is if the training
[00:23:54] objective is reconstruction at pixel
[00:23:56] level, then the model is wasting the
[00:23:58] vast majority of its compute trying to
[00:24:00] predict the random movements of leaves
[00:24:02] on a tree. That's not only useless, but
[00:24:05] impossible to predict. Joint embedding
[00:24:07] architectures that Jan is advocating for
[00:24:10] do something very different. Jepa is not
[00:24:13] a generative model, and right now it is
[00:24:15] one of the few serious alternatives to
[00:24:18] purely generative approaches. The latest
[00:24:20] implementation of this architecture
[00:24:22] consists of three main parts: a context
[00:24:24] encoder, a target encoder, and a
[00:24:26] predictor. The target encoder processes
[00:24:29] the whole image. The context encoder
[00:24:31] sees the visible part of the image. Then
[00:24:33] the predictor tries to predict the
[00:24:35] target representation of the missing
[00:24:37] patch from the context representation.
[00:24:40] The most important thing to understand
[00:24:41] is that the learning signal comes from
[00:24:43] the pressure for the context and target
[00:24:45] encoders to agree on a similar latent
[00:24:48] representation because both are derived
[00:24:50] from the same underlying scene. So this
[00:24:53] whole generative versus Jepa argument
[00:24:55] comes down to this very nuanced point.
[00:24:57] Both architectures learn some model of
[00:24:59] the world, but the key difference is in
[00:25:01] a generative setup, the final objective
[00:25:03] is usually keep enough information to
[00:25:05] reconstruct the original input as
[00:25:08] accurately as possible. In Jeppa, the
[00:25:09] objective is predict a compatible
[00:25:12] representation of a missing part. The
[00:25:13] model only needs to match
[00:25:15] representations in embedding a space.
[00:25:17] With video, the same principle applies.
[00:25:19] If a ball rolls behind a wall, Jeppa
[00:25:21] must predict a compatible future
[00:25:23] representation where the ball emerges on
[00:25:26] the other side. Over enough examples,
[00:25:27] the model can develop an implicit
[00:25:29] understanding of object permanence
[00:25:31] without ever generating the video
[00:25:33] itself. Now, this raises an obvious
[00:25:35] question. If Jeppa sounds so reasonable,
[00:25:38] why isn't everyone just switching?
[00:25:39] Theoretically, architectures like this
[00:25:41] should eventually outperform purely
[00:25:43] generative systems, but empirically,
[00:25:45] generative models are still performing
[00:25:47] much better across many important
[00:25:49] domains. Yann argues that predictive
[00:25:50] world models are the more scalable
[00:25:52] long-term path toward human-level
[00:25:54] intelligence. Meanwhile, DeepMind is
[00:25:56] saying generative training may already
[00:25:58] contain enough pressure to learn
[00:26:00] surprisingly deep world models
[00:26:02] implicitly. I know it has already been
[00:26:05] pretty hard to follow this part, but it
[00:26:07] is incomplete without this final point.
[00:26:09] The generative diffusion model itself is
[00:26:12] not the final product for DeepMind. The
[00:26:14] approach is to build a hyperrealistic
[00:26:16] and grounded simulation of the world
[00:26:18] using generative diffusion models. Then,
[00:26:21] use that simulated world to train the
[00:26:23] multimodal AI model Gemini to develop an
[00:26:27] explicit evolving model of reality
[00:26:29] internally. Essentially, a multimodal,
[00:26:32] probably autoregressive model gathering
[00:26:34] experience in diffusion-based simulated
[00:26:37] worlds. That's Gemini Omni, by the way.
[00:26:39] It isn't just another diffusion-based
[00:26:42] video generator. It is an early
[00:26:44] iteration of DeepMind's world model, an
[00:26:46] autoregressive multimodal core built for
[00:26:49] anything to anything capabilities
[00:26:52] starting with video. Finally, the only
[00:26:54] big idea remaining is larger-scale
[00:26:56] pre-training as the foundation of the
[00:26:58] whole system, which DeepMind has been a
[00:27:00] really big fan of. But, highly respected
[00:27:03] researchers like Ilya Sutskever and
[00:27:05] Richard Sutton suggest that larger-scale
[00:27:07] pre-training is probably a dead end. The
[00:27:09] core issue is that larger-scale
[00:27:11] pre-training almost by definition
[00:27:13] already assumes an inefficient learner.
[00:27:16] Ilya Sutskever's and Richard Sutton's
[00:27:18] argument can be divided into two parts.
[00:27:20] First, learning from experience. The
[00:27:22] physical world is a messy environment
[00:27:25] full of unorganized goals, very subtle
[00:27:28] learning signals, and super dynamic
[00:27:30] interactions. Performing all of the
[00:27:32] training in an isolated lab with rigid
[00:27:34] arbitrary goals will never result in a
[00:27:37] truly intelligent and robust system. The
[00:27:39] model should require only minimal
[00:27:41] pre-training paired with an extremely
[00:27:43] efficient learning algorithm. Argument
[00:27:45] number two is biological plausibility.
[00:27:48] >> The thing
[00:27:49] that happened with AGI and pre-training
[00:27:51] is that in some sense they overshot the
[00:27:53] target. If you think about the term AGI,
[00:27:56] you will realize, and especially in the
[00:27:58] context of pre-training, you will
[00:27:59] realize that a human being is not an AGI
[00:28:02] because a human being Yes, there is
[00:28:05] definitely a foundation of skills. A
[00:28:07] human being lacks a huge amount of
[00:28:09] knowledge.
[00:28:10] Instead, we rely on continual learning.
[00:28:13] It's a process as opposed to you drop
[00:28:16] the finished thing.
[00:28:17] >> The thing you're pointing out with
[00:28:18] superintelligence
[00:28:20] is not some finished
[00:28:24] mind which knows how to do every single
[00:28:26] job in the economy cuz the way, say,
[00:28:30] the original, I think, OpenAI charter or
[00:28:31] whatever defines AGI is like it can do
[00:28:34] every single job that a every single
[00:28:36] thing a human can do.
[00:28:37] You're proposing instead
[00:28:39] a mind which can learn to do any single
[00:28:42] every single job.
[00:28:43] >> Yes.
[00:28:43] >> And that is superintelligence. And then
[00:28:45] but once you have the learning
[00:28:47] algorithm,
[00:28:49] it gets deployed into the world the same
[00:28:50] way a human laborer might join an
[00:28:52] organization.
[00:28:53] >> Most current learning systems operate
[00:28:55] with extremely rigid objectives. Reach
[00:28:58] the target and you receive a reward.
[00:29:00] Fail and you get punished. Learning
[00:29:02] becomes a harsh binary process. Human
[00:29:04] learning works very differently. You do
[00:29:07] not need to crash the car to understand
[00:29:09] danger. You do not need endless miles of
[00:29:12] driving before receiving feedback. The
[00:29:14] moment you sit behind the wheel, you
[00:29:16] already have a sense of what optimal
[00:29:18] should feel like. You have a sense of
[00:29:20] balance, control, confidence,
[00:29:22] uncertainty, and whether something feels
[00:29:25] wrong. The brain is constantly
[00:29:27] evaluating itself long before any
[00:29:29] catastrophic outcome occurs because the
[00:29:31] learning signals are so rich. Humans
[00:29:33] learn with astonishing efficiency and
[00:29:35] are surprisingly robust. Google
[00:29:37] DeepMind, however, has been advocating
[00:29:39] for larger-scale pre-training as part of
[00:29:42] the core recipe for AGI.
[00:29:43] >> I think by far, probably my betting
[00:29:46] would be the quickest way to get to AGI
[00:29:47] and the most likely plausible way is to
[00:29:50] use all the knowledge that's existing in
[00:29:51] the world right now on things like the
[00:29:53] web, ingesting all of that information,
[00:29:55] and I don't see why you wouldn't start
[00:29:58] with a model as a kind of prior or or to
[00:30:00] build on and to make predictions that
[00:30:02] helps bootstrap your learning. I just
[00:30:04] think it
[00:30:05] doesn't make sense not to make use of
[00:30:07] that. So my my betting would be is that
[00:30:10] you know, the final AGI system will have
[00:30:13] these large multi-modal
[00:30:16] models as part of the the overall
[00:30:17] solution, but probably won't be enough
[00:30:20] on their own. You will need this
[00:30:21] additional planning search on top.
[00:30:23] >> This is the same philosophy that built
[00:30:25] AlphaGo. That breakthrough proved deep
[00:30:28] learning could solve near infinite
[00:30:30] problems using deeply efficient pattern
[00:30:32] recognition. It gave DeepMind the
[00:30:34] conviction that AGI, despite seeming
[00:30:37] impossibly vast, can be solved using
[00:30:39] those same principles. From one angle,
[00:30:41] Google DeepMind is doubling down on
[00:30:43] generative AI and massive pre-trained
[00:30:45] models. From another, they are actively
[00:30:48] pushing research far beyond the standard
[00:30:50] transformers and auto-regressive models.
[00:30:52] It is a highly specific bet on exactly
[00:30:55] what AGI should look like. Fortunately,
[00:30:57] it will only take a couple more years
[00:30:58] for us to understand who is right.
[00:31:00] Honestly, what an odd time to be alive.
[00:31:03] Thank you for watching and I see you in
[00:31:05] the next one.
