---
video_id: _9V_Hbe-N1A
title: Adam Marblestone – AI is missing something fundamental about the brain
channel: Dwarkesh Patel
url: "https://www.youtube.com/watch?v=_9V_Hbe-N1A"
watched_date: 2026-06-10
watched_at: "2026-06-10T12:00:00Z"
watch_count: 1
duration_seconds: 6593
source: youtube-history-browser
added_date: 
history_label: Wednesday
history_order: 63
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 659
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Marblestone discusses how the brain fundamentally outperforms LLMs despite receiving less data, arguing that the key difference lies not in architecture alone but in three overlooked components: complex, evolved loss functions (not just next-token prediction); omnidirectional inference (the brain can predict any variable from any subset of inputs, while LLMs only predict forward); and a two-system organization where a "Learning Subsystem" (cortex) learns predictive models and connects them to innate reward signals in a "Steering Subsystem" (older brain structures). He explores Steve Byrnes' theory that the brain solves the problem of wiring learned abstractions to primitive reward signals by having cortical areas predict the outputs of innate reflexes, enabling generalization (learning to fear "spider" as a concept, not just the physical stimulus). The evidence includes the genome's compactness—3GB contains relatively little brain-wiring code, suggesting evolution invested in the learning algorithm and reward function design rather than pre-learned features.

To advance AI, researchers should train models with: (1) multiple, diverse loss functions operating simultaneously rather than uniform cross-entropy, (2) omnidirectional inference at test time by removing masks during training so the model learns bidirectional prediction across modalities, and (3) energy-based or probabilistic inference methods that may better approximate how the brain generalizes. For practitioners, this suggests that improving LLM cross-domain reasoning requires richer representational spaces where video, audio, and text intermingle at compatible abstraction levels, and that building AI systems aligned with human values requires understanding how to wire learned world-models to a small set of core reward functions—insights directly relevant to AI safety and sample-efficient learning.

## Transcript

[00:00:00] The big million-dollar question that I  have, that I've been trying to get the
[00:00:03] answer to through all these interviews with  AI researchers: How does the brain do it?
[00:00:07] We're throwing way more data at  these LLMs and they still have a
[00:00:11] small fraction of the total capabilities  that a human does. So what's going on?
[00:00:15] This might be the quadrillion-dollar  question or something like that.
[00:00:20] You can make an argument that this is  the most important question in science.
[00:00:24] I don't claim to know the answer. I also don't think that the answer
[00:00:30] will necessarily come even from a lot of smart  people thinking about it as much as they are.
[00:00:36] My overall meta-level take is that we have  to empower the field of neuroscience to
[00:00:40] just make neuroscience a more powerful  field technologically and otherwise,
[00:00:45] to actually be able to crack a question like this. Maybe the way that we would think about this now
[00:00:53] with modern AI, neural nets, deep learning,  is that there are certain key components of
[00:01:00] that. There's the architecture. There's  maybe hyperparameters of how many layers
[00:01:04] you have or properties of that architecture. There is the learning algorithm itself. How
[00:01:10] do you train it? Backprop, gradient descent,  is it something else? How is it initialized?
[00:01:18] If we take the learning part of the system, it  still may have some initialization of the weights.
[00:01:24] And then there are also cost functions. What is it being trained to do? What's the
[00:01:28] reward signal? What are the loss  functions, supervision signals?
[00:01:32] My personal hunch within that framework  is that the field has neglected
[00:01:39] the role of these very specific loss  functions, very specific cost functions.
[00:01:45] Machine learning tends to like  mathematically simple loss functions.
[00:01:49] Predict the next token, cross-entropy, these  simple computer scientist loss functions.
[00:01:57] I think evolution may have built a lot of  complexity into the loss functions actually,
[00:02:01] many different loss functions  for different areas turned on at
[00:02:04] different stages of development. A lot of Python code, basically,
[00:02:09] generating a specific curriculum for what  different parts of the brain need to learn.
[00:02:13] Because evolution has seen many times what was  successful and unsuccessful, and evolution could
[00:02:17] encode the knowledge of the learning curriculum. In the machine learning framework, maybe we can
[00:02:23] come back and we can talk about where do  the loss functions of the brain come from?
[00:02:27] Can different loss functions lead  to different efficiency of learning?
[00:02:31] People say the cortex has got the universal  human learning algorithm, the special sauce
[00:02:35] that humans have. What's up with that? This is a huge question and we don't know.
[00:02:39] I've seen models where the cortex… The cortex  typically has this six-layered structure,
[00:02:45] layers in a slightly different  sense than layers of a neural net.
[00:02:48] Any one location in the cortex has six physical  layers of tissue as you go in layers of the sheet.
[00:02:54] And those areas then connect to each other  and that's more like the layers of a network.
[00:03:00] I've seen versions of that where what  you're trying to explain is just,
[00:03:04] "How does it approximate backprop?" And what is the cost function for that?
[00:03:09] What is the network being asked to do, if you  are trying to say it's something like backprop?
[00:03:13] Is it doing backprop on next token prediction or  is it doing backprop on classifying images or what
[00:03:18] is it doing? And no one knows. But one thought  about it, one possibility about it, is that it's
[00:03:30] just this incredibly general prediction engine. So any one area of the cortex is just trying to
[00:03:36] predict… Basically can it learn to predict  any subset of all the variables it sees
[00:03:43] from any other subset? Omnidirectional  inference, or omnidirectional prediction.
[00:03:50] Whereas an LLM is just seeing everything in  the context window and then it computes a
[00:03:55] very particular conditional probability which  is, "Given all the last thousands of things,
[00:03:59] what are the probabilities for the next token." But it would be weird for a large language
[00:04:05] model to say "the quick brown fox blank blank  the lazy dog" and fill in the middle versus
[00:04:16] doing the next token, if it's doing just forward. It can learn how to do that stuff at this emergent
[00:04:22] level of the context window and everything, but  natively it's just predicting the next token.
[00:04:27] What if the cortex is natively  made so that any area of cortex
[00:04:32] can predict any pattern in any subset of  its inputs given any other missing subset?
[00:04:38] That is a little bit more like "probabilistic AI". A lot of the things I'm saying, by the way, are
[00:04:45] extremely similar to what Yann LeCun would say. He's really interested in these energy-based
[00:04:50] models and something like that is like, the  joint distribution of all the variables.
[00:04:55] What is the likelihood or unlikelihood  of just any combination of variables?
[00:05:01] If I clamp some of them and I say that  definitely these variables are in these states,
[00:05:05] then I can compute, with probabilistic sampling  for example—conditioned on these being set in
[00:05:13] this state, and these could be any arbitrary  subset of variables in the model—can I predict
[00:05:20] what any other subset is going to do and sample  from any other subset given clamping this subset?
[00:05:25] And I could choose a totally different subset and  sample from that subset. So it's omnidirectional
[00:05:30] inference. And so there could be some parts of  the cortex, there might be association areas
[00:05:36] of cortex that predict vision from audition. There might be areas that predict things that
[00:05:42] the more innate part of the brain is going to do. Because remember, this whole thing is riding on
[00:05:46] top of a lizard brain and  lizard body, if you will.
[00:05:50] And that thing is a thing  that's worth predicting too.
[00:05:53] You're not just predicting do  I see this or do I see that.
[00:05:55] Is this muscle about to tense? Am I about to have a reflex where I laugh?
[00:06:01] Is my heart rate about to go up? Am I about to activate this instinctive behavior?
[00:06:06] Based on my higher-level understanding… Like I can  match somebody has told me there's a spider on my
[00:06:13] back to this lizard part that would activate if  I was literally seeing a spider in front of me.
[00:06:21] You learn to associate the two so that  even just from somebody hearing you say
[00:06:24] "There's a spider on your back" Well, let's come back to this.
[00:06:27] This is partly having to do with Steve Byrnes’  theories, which I'm recently obsessed about.
[00:06:31] But on your podcast with Ilya, he said, "Look,  I'm not aware of any good theory of how evolution
[00:06:41] encodes high-level desires or intentions." I think this is very connected to all of
[00:06:50] these questions about the loss functions and  the cost functions that the brain would use.
[00:06:55] And it's a really profound question, right? Let's say that I am embarrassed for saying
[00:07:04] the wrong thing on your podcast  because I'm imagining that Yann LeCun
[00:07:07] is listening and he says, "That's not my theory. You described energy-based models really badly."
[00:07:12] That's going to activate in me  innate embarrassment and shame,
[00:07:16] and I'm going to want to go hide and whatever. That's going to activate these innate reflexes.
[00:07:22] That's important because I might otherwise get  killed by Yann LeCun's marauding army of other…
[00:07:28] The French AI researchers  are coming for you, Adam.
[00:07:30] So it's important that I have  that instinctual response.
[00:07:33] But of course, evolution has never seen Yann  LeCun or known about energy-based models or
[00:07:37] known what an important scientist or a podcast is. Somehow the brain has to encode this desire to
[00:07:47] not piss off really important people in the tribe  or something like this in a very robust way,
[00:07:54] without knowing in advance all the things  that the Learning Subsystem of the brain,
[00:07:59] the part that is learning cortex and other parts…  The cortex is going to learn this world model.
[00:08:05] It's going to include things  like Yann LeCun and podcasts.
[00:08:09] And evolution has to make sure that those neurons,  whatever the Yann-LeCun-being-upset-with-me
[00:08:15] neurons, get properly wired up to the shame  response or this part of the reward function.
[00:08:22] And this is important, right? Because  if we're going to be able to seek status
[00:08:25] in the tribe or learn from knowledgeable  people, as you said, or things like that,
[00:08:28] exchange knowledge and skills with friends but  not with enemies… We have to learn all this stuff.
[00:08:33] It has to be able to robustly wire these learned  features of the world, learned parts of the world
[00:08:38] model, up to these innate reward functions,  and then actually use that to then learn more.
[00:08:44] Because next time I'm not going to try to piss off  Yann LeCun if he emails me that I got this wrong.
[00:08:52] We're going to do further learning based on that. In constructing the reward function, it has to
[00:08:55] use learned information. But how can evolution,
[00:08:59] which didn't know about Yann LeCun, do that? The basic idea that Steve Byrnes is proposing
[00:09:08] is that part of the cortex, or other areas like  the amygdala that learn, what they're doing is
[00:09:14] they're modeling the Steering Subsystem. The Steering Subsystem is the part with
[00:09:17] these more innately programmed responses  and the innate programming of these series
[00:09:21] of reward functions, cost functions,  bootstrapping functions that exist.
[00:09:26] There are parts of the amygdala, for example,
[00:09:27] that are able to monitor what those  parts do and predict what those parts do.
[00:09:32] How do you find the neurons that  are important for social status?
[00:09:37] Well, you have some innate heuristics of social  status, for example, or you have some innate
[00:09:42] heuristics of friendliness that  the Steering Subsystem can use.
[00:09:47] And the Steering Subsystem actually has  its own sensory system, which is crazy.
[00:09:51] We think of vision as being  something that the cortex does.
[00:09:54] But there's also a Steering Subsystem,  subcortical visual system called the
[00:09:59] superior colliculus with innate ability  to detect faces, for example, or threats.
[00:10:06] So there's a visual system that  has innate heuristics and the
[00:10:11] Steering Subsystem has its own responses. There'll be part of the amygdala or part
[00:10:14] of the cortex that is learning  to predict those responses.
[00:10:17] What are the neurons that matter in the  cortex for social status or for friendship?
[00:10:23] They're the ones that predict those  innate heuristics for friendship.
[00:10:26] You train a predictor in the cortex and you  say, "Which neurons are part of the predictor?"
[00:10:32] Those are the ones that, now you've  actually managed to wire it up.
[00:10:36] This is fascinating. I feel like I still don't  understand… I understand how the cortex could
[00:10:42] learn how this primitive part of the brain would  respond to… Obviously it has these labels on,
[00:10:51] "here's literally a picture of a spider,  and this is bad, be scared of this."
[00:10:57] The cortex learns that this is bad  because the innate part tells it that.
[00:11:00] But then it has to generalize to,  "Okay, the spider's on my back.
[00:11:05] And somebody's telling me the spider's  on your back. That's also bad."
[00:11:07] Yes. But it never
[00:11:08] got supervision on that. So how does it…? Well, it's because the Learning Subsystem
[00:11:15] is a powerful learning algorithm that does have  generalization, that is capable of generalization.
[00:11:20] The Steering Subsystem, these  are the innate responses.
[00:11:23] You're going to have some built into your Steering  Subsystem, these lower brain areas: hypothalamus,
[00:11:29] brainstem, et cetera. Again, they have their
[00:11:33] own primitive sensory systems. So there may be an innate response.
[00:11:38] If I see something that's moving fast toward my  body that I didn't previously see was there and
[00:11:44] is small and dark and high contrast, that might be  an insect skittering onto my body. I am going to
[00:11:50] flinch. There are these innate responses. There's  going to be some group of neurons, let's say,
[00:11:56] in the hypothalamus, that is the I-am-flinching  or I-just-flinched neurons in the hypothalamus.
[00:12:05] When you flinch, first of all, it’s a  negative contribution to the reward function.
[00:12:09] You didn't want that to happen, perhaps.
[00:12:12] But that's a reward function that  doesn't have any generalization in it.
[00:12:16] I'm going to avoid that exact situation  of the thing skittering toward me.
[00:12:21] Maybe I'm going to avoid some actions  that lead to the thing skittering.
[00:12:24] That's a generalization you can get, what  Steve calls downstream of the reward function.
[00:12:29] I'm going to avoid the situation where  the spider was skittering toward me,
[00:12:34] but you're also going to do something else. There's going to be a part of your amygdala,
[00:12:37] say, that is saying, "Okay, a few milliseconds,  hundreds of milliseconds or seconds earlier,
[00:12:49] could I have predicted that flinching response?" It's going to be a group of neurons that
[00:12:52] is essentially a classifier  of, "Am I about to flinch?"
[00:12:56] And I'm going to have classifiers for that  for every important Steering Subsystem
[00:12:59] variable that evolution needs to take care  of. Am I about to flinch? Am I talking to a
[00:13:03] friend? Should I laugh now? Is the friend high  status? Whatever variables the hypothalamus,
[00:13:07] brainstem, contains… Am I about to taste salt? It's going to have all these variables and for
[00:13:14] each one it's going to have a predictor. It's going to train that predictor.
[00:13:17] Now the predictor that it trains,  that can have some generalization.
[00:13:20] The reason it can have some generalization is  because it just has a totally different input.
[00:13:24] Its input data might be things like the word  "spider", but the word "spider" can activate
[00:13:29] in all sorts of situations that lead to the  word "spider" activating in your world model.
[00:13:36] If you have a complex world model  with really complex features that
[00:13:39] inherently gives you some generalization. It's not just the thing skittering toward me,
[00:13:42] it's even the word "spider" or the concept of  "spider" is going to cause that to trigger.
[00:13:47] This predictor can learn that. Whatever spider  neurons are in my world model, which could even
[00:13:53] be a book about spiders or somewhere, a room  where there are spiders or whatever that is…
[00:13:58] The amount of heebie-jeebies that this  conversation is eliciting in the audience…
[00:14:03] Now I'm activating your Steering Subsystem,  your Steering Subsystem spider hypothalamus
[00:14:08] subgroup of neurons of skittering insects  are activating based on these very abstract
[00:14:13] concepts in the conversation. If you keep going, I'm going
[00:14:14] to put in a trigger warning. That's because you learned this.
[00:14:18] The cortex inherently has the ability to  generalize because it's just predicting
[00:14:22] based on these very abstract variables and  all these integrated information that it has.
[00:14:26] Whereas the Steering Subsystem  only can use whatever the superior
[00:14:29] colliculus and a few other sensors can spit out. By the way, it's remarkable that the person who's
[00:14:34] made this connection between different pieces of  neuroscience, Steve Byrnes, is a former physicist.
[00:14:39] For the last few years, he’s  been trying to synthesize—
[00:14:40] He's an AI safety researcher.  He's just synthesizing. This
[00:14:43] comes back to the academic incentives thing. I think that this is a little bit hard to say.
[00:14:47] What is the exact next experiment? How am I going to publish a paper on this?
[00:14:50] How am I going to train my grad student to  do this? It’s very speculative. But there's
[00:14:53] a lot in the neuroscience literature and  Steve has been able to pull this together.
[00:14:56] And I think that Steve has an answer to Ilya's  question essentially, which is, how does the brain
[00:15:01] ultimately code for these higher-level desires  and link them up to the more primitive rewards?
[00:15:05] Very naive question, but why can't we achieve  this omnidirectional inference by just training
[00:15:12] the model to not just map from a token to next  token, but remove the masks in the training so
[00:15:19] it maps every token to every token, or come up  with more labels between video and audio and
[00:15:27] text so that it's forced to map one to each one? I mean, that may be the way. It's not clear to
[00:15:34] me. Some people think that there's a different  way that it does probabilistic inference or a
[00:15:41] different learning algorithm that isn't backprop. There might be other ways of learning,
[00:15:45] energy-based models or other things like that,  that you can imagine that is involved in being
[00:15:50] able to do this and that the brain has that. But I think there's a version of it where what
[00:15:54] the brain does is crappy versions of backprop to  learn to predict through a few layers and that
[00:16:01] it’s kind of like a multimodal foundation model. LLMs are maybe just predicting the next token.
[00:16:11] But vision models maybe are trained in learning  to fill in the blanks or reconstruct different
[00:16:16] pieces or combinations. But I think that
[00:16:19] it does it in an extremely flexible way. If you train a model to just fill in this
[00:16:23] blank at the center, okay, that's great. But what if you didn't train it to fill
[00:16:26] in this other blank over to the left? Then it doesn't know how to do that.
[00:16:30] It's not part of its repertoire of predictions  that are amortized into the network.
[00:16:35] Whereas with a really powerful inference  system, you could choose at test time,
[00:16:41] what is the subset of variables it needs  to infer and which ones are clamped?
[00:16:46] Okay, two sub-questions. One, it makes you wonder  whether the thing that is lacking in artificial
[00:16:53] neural networks is less about the reward function  and more about the encoder or the embedding… Maybe
[00:17:02] the issue is that you're not representing video  and audio and text in the right latent abstraction
[00:17:11] such that they could intermingle and conflict. Maybe this is also related to why LLMs seem bad
[00:17:19] at drawing connections between different ideas. Are the ideas represented at a level of generality
[00:17:24] at which you could notice different connections? Well, the problem is these questions
[00:17:27] are all commingled. If we don't know if it's
[00:17:28] doing a backprop-like learning, and we don't  know if it's doing energy-based models, and we
[00:17:32] don't know how these areas are even connected  in the first place, it's very hard to really
[00:17:36] get to the ground truth of this. But yeah, it's  possible. I think that people have done some work.
[00:17:41] My friend Joel Dapello actually did something  some years ago where he put a model—I think it
[00:17:49] was a model of V1, specifically how the  early visual cortex represents images—as
[00:17:58] an input into a convnet and that improves  some things. It could be differences. The
[00:18:02] retina is also doing motion detection and  certain things are getting filtered out.
[00:18:09] There may be some preprocessing  of the sensory data.
[00:18:11] There may be some clever combinations of which  modalities are predicting which or so on,
[00:18:17] that lead to better representation. There may be much more clever things than that.
[00:18:19] Some people certainly do think that there's  inductive biases built in the architecture
[00:18:23] that will shape the representations differently  or that there are clever things that you can do.
[00:18:30] Astera, which is the same organization that  employs Steve Byrnes, just launched this
[00:18:34] neuroscience project based on Doris Tsao's work. She has some ideas about how you can build vision
[00:18:42] systems that basically require less training. They build into the assumptions of the design
[00:18:48] of the architecture things like objects are  bounded by surfaces and surfaces have certain
[00:18:56] types of shapes and relationships of how  they occlude each other and stuff like that.
[00:19:00] It may be possible to build more  assumptions into the network.
[00:19:03] Evolution may have also put  some changes of architecture.
[00:19:08] It's just I think that also the cost functions  and so on may be a key thing that it does.
[00:22:20] I want to talk about this idea that you just  glanced off of which was amortized inference.
[00:22:29] Maybe I should try to explain what I think  it means, because I think it's probably wrong
[00:22:34] and this will help you correct me. It's been a few years for me too.
[00:22:39] Right now, the way the models work is that  you have an input, it maps it to an output,
[00:22:44] and this is amortizing a process, the real  process, which we think is what intelligence is.
[00:22:52] It’s that you have some prior over how  the world could be, what are the causes
[00:22:58] that make the world the way that it is. And then when you see some observation,
[00:23:03] you should be like, "Okay, here's  all the ways the world could be.
[00:23:07] This cause explains what's happening best." Now, doing this calculation over every possible
[00:23:14] cause is computationally intractable. So then you just have to sample like,
[00:23:19] "Oh, here's a potential cause. Does this  explain this observation? No, forget it. Let's
[00:23:24] keep sampling." And then eventually you get the  cause, then the cause explains the observation,
[00:23:31] and then this becomes your posterior. That’s actually pretty good. Bayesian inference
[00:23:37] in general is of this very intractable thing. The algorithms that we have for doing that tend
[00:23:42] to require taking a lot of samples, Monte  Carlo methods, taking a lot of samples.
[00:23:46] And taking samples takes time. This is like  the original Boltzmann machines and stuff.
[00:23:51] They're using techniques like this, and still  it's used with probabilistic programming,
[00:23:57] other types of methods often. The Bayesian inference problem,
[00:24:02] which is basically the problem of perception,  given some model of the world and given some data,
[00:24:06] how should I update my… What are the  missing variables in my internal model?
[00:24:13] And I guess the idea is that neural networks  are hopefully… Obviously, mechanistically,
[00:24:20] the neural network is not starting  with, "Here is my model of the world,
[00:24:25] and I'm going to try to explain this data." But the hope is that instead of starting with,
[00:24:30] "Hey, does this cause explain this observation?  No. Did this cause explain this observation? Yes."
[00:24:35] What you do is just like observation… What's the cause that the
[00:24:38] neural net thinks is the best one? Observation to cause. So the feedforward
[00:24:42] goes observation to cause to then the output that… You don't have to evaluate all these energy values
[00:24:48] or whatever and sample around  to make them higher and lower.
[00:24:51] You just say, approximately that  process would result in this being
[00:24:57] the top one or something like that. Exactly. One way to think about it
[00:25:00] might be that test-time compute, inference-time  compute is actually doing this sampling again.
[00:25:07] You literally read its chain of thought. It's actually doing this toy example we're
[00:25:11] talking about where it's like, "Oh,  can I solve this problem by doing X?
[00:25:13] Nah, I need a different approach." This raises the  question. I mean, over time it is the case that
[00:25:19] the capabilities which required inference-time  compute to elicit, get distilled into the model.
[00:25:26] So you're amortizing the thing which  previously you needed to do these rollouts,
[00:25:30] these Monte Carlo rollouts, to figure out. In general, maybe there's this principle that
[00:25:36] digital minds which can be copied, have  different tradeoffs which are relevant,
[00:25:40] from biological minds which cannot. So in general, it should make sense
[00:25:44] to amortize more things because you can  literally copy the amortization, or copy
[00:25:48] the things that you have sort of built in. This is a tangential question where it
[00:25:55] might be interesting to speculate about. In the future, as these things become more
[00:25:58] intelligent and the way we train them becomes more  economically rational, what will make sense to
[00:26:06] amortize into these minds, which evolution did not  think was worth amortizing into biological minds?
[00:26:12] You have to retrain every time. First of all, I think the probabilistic
[00:26:16] AI people would be like, of course you need  test-time compute, because this inference
[00:26:20] problem is really hard and the only ways we know  how to do it involve lots of test-time compute.
[00:26:24] Otherwise it's just this crappy approximation  that's never going to… You have to do infinite
[00:26:27] data or something to make this. I think some of the probabilistic
[00:26:30] people will be like, "No, it's  inherently probabilistic and amortizing
[00:26:33] it in this way just doesn't make sense." They might then also point to the brain and say,
[00:26:37] "Okay, well the brain, the neurons are stochastic  and they're sampling and they're doing things.
[00:26:41] So maybe the brain actually is doing more like  the non-amortized inference, the real inference."
[00:26:48] But it's also strange how perception can  work in just milliseconds or whatever.
[00:26:52] It doesn't seem like it uses that much sampling. So it's also clearly doing some baking things
[00:26:58] into approximate forward passes  or something like that to do this.
[00:27:03] In the future, I don't know. Is it already a trend to some
[00:27:11] degree that things that people were having to  use test-time compute for, are getting used
[00:27:16] to train back the base model? Now it can do it in one pass.
[00:27:26] Maybe evolution did or didn't do that. I think evolution still has to pass
[00:27:31] everything through the genome to build  the network and the environment in which
[00:27:35] humans are living is very dynamic. So maybe, if we believe this is true,
[00:27:43] there's a Learning Subsystem per Steve  Byrnes, and a Steering Subsystem,
[00:27:46] that the Learning Subsystem doesn't have a  lot of pre-initialization or pretraining.
[00:27:51] It has a certain architecture, but  then within lifetime it learns.
[00:27:55] Then evolution didn't actually  amortize that much into that network.
[00:27:59] It amortized it instead into a set of innate  behaviors in a set of these bootstrapping
[00:28:03] cost functions, or ways of building  up very particular reward signals.
[00:28:08] This framework helps explain this mystery that  people have pointed out and I've asked a few
[00:28:14] guests about, which is that if you want  to analogize evolution to pretraining,
[00:28:20] well how do you explain the fact that so little  information is conveyed through the genome?
[00:28:25] So 3 gigabytes is the size  of the total human genome.
[00:28:28] Obviously a small fraction of that is  actually relevant to coding the brain.
[00:28:33] Previously people made this analogy, that actually  evolution has found the hyperparameters of the
[00:28:38] model, the numbers which tell you how many  layers there should be, the architecture,
[00:28:42] basically, how things should be wired together. But if a big part of the story is that increased
[00:28:48] sample efficiency aids learning, generally makes  systems more performant, is the reward function,
[00:28:54] is the loss function—and if evolution found  those loss functions that aid learning—then
[00:29:03] it actually makes sense how you can build  an intelligence with so little information.
[00:29:06] Because the reward function, in Python  the reward function is literally a line.
[00:29:11] So you just have a thousand lines like this,  and that doesn't take up that much space.
[00:29:15] Yes. It also gets to do this generalization  thing with the thing I was describing where
[00:29:20] we were talking about the spider, where it  learns just the word "spider" which triggers
[00:29:23] the spider reflex or whatever. It gets to exploit that too.
[00:29:29] It gets to build a reward function that  actually has a bunch of generalization
[00:29:32] in it just by specifying these innate  spider stuff and the Thought Assessors,
[00:29:36] as Steve calls them, that do the learning. That's potentially a really compact solution
[00:29:42] to building up these more complex  reward functions too, that you need.
[00:29:45] It doesn't have to anticipate everything  about the future of the reward function.
[00:29:47] It just has to anticipate what variables  are relevant and what are heuristics
[00:29:50] for finding what those variables are. And then it has to have a very compact
[00:29:55] specification for the learning algorithm and  basic architecture of the Learning Subsystem.
[00:30:00] And then it has to specify all this Python code  of all the stuff about the spiders and all the
[00:30:04] stuff about friends, and all the stuff about  your mother, and all the stuff about mating
[00:30:09] and social groups and joint eye contact. It has to specify all that stuff.
[00:30:15] So is this really true? I think  that there is some evidence for it.
[00:30:21] Fei Chen and Evan Macosko and  various other researchers have
[00:30:25] been doing these single-cell atlases. One of the things that scaling up
[00:30:32] neuroscience technology—again, this is one of my  obsessions—has done through the BRAIN Initiative,
[00:30:40] a big neuroscience funding program, is  they've basically gone through different
[00:30:44] areas, especially of the mouse brain, and  mapped where the different cell types are?
[00:30:50] How many different types of cells are  there in different areas of cortex?
[00:30:53] Are they the same across different areas? Then you look at these subcortical regions,
[00:30:57] which are more like the Steering Subsystem  or reward-function-generating regions.
[00:31:02] How many different types of cells do they have? And which neuron types do they have?
[00:31:05] We don't know how they're all connected  and exactly what they do or what the
[00:31:08] circuits are or what they mean, but you can just  quantify how many different kinds of cells there
[00:31:14] are with sequencing the RNA. And there are a lot more weird
[00:31:22] and diverse and bespoke cell types  in the Steering Subsystem, basically,
[00:31:26] than there are in the Learning Subsystem. Like the cortical cell types, it seems like
[00:31:30] there's enough to build a learning algorithm  up there and specify some hyperparameters.
[00:31:34] And in this Steering Subsystem, there's like  a gazillion, thousands of really weird cells,
[00:31:40] which might be like the one for the spider flinch  reflex and the one for I'm-about-to-taste-salt.
[00:31:45] Why would each reward function  need a different cell type?
[00:31:49] Well, this is where you get  innately wired circuits.
[00:31:53] In the learning algorithm part, in the Learning  Subsystem, you specify the initial architecture,
[00:31:59] you specify a learning algorithm. All the juice is happening through
[00:32:04] plasticity of the synapses, changes of  the synapses within that big network.
[00:32:08] But it's a relatively repeating  architecture, how it's initialized.
[00:32:13] It's just like how the amount of Python  code needed to make an eight-layer
[00:32:18] transformer is not that different from one  that makes a three-layer transformer. You're
[00:32:21] just replicating. Whereas all this Python code for  the reward function, if superior colliculus sees
[00:32:27] something that's skittering and you're feeling  goosebumps on your skin or whatever, then trigger
[00:32:32] spider reflex, that's just a bunch of bespoke,  species-specific, situation-specific crap.
[00:32:41] The cortex doesn't know about  spiders, it just knows about layers.
[00:32:45] But you're saying that the only way to write this  reward function is to have a special cell type?
[00:32:51] Yeah, well, I think so. I think you either  have to have special cell types or you have to
[00:32:55] somehow otherwise get special wiring rules  that evolution can say this neuron needs
[00:33:01] to wire to this neuron, without any learning. And the way that that is most likely to happen,
[00:33:06] I think, is that those cells express  different receptors and proteins that say,
[00:33:10] "Okay, when this one comes in contact  with this one, let's form a synapse."
[00:33:16] So it's genetic wiring, and  those need cell types to do it.
[00:33:20] I'm sure this would make a lot more sense  if I knew 101 neuroscience, but it seems
[00:33:25] like there's still a lot of complexity, or  generality rather, in the Steering Subsystem.
[00:33:31] So if the Steering Subsystem has its own visual  system that's separate from the visual cortex,
[00:33:39] different features still need  to plug into that vision system.
[00:33:46] So the spider thing needs to plug into it and  also the love thing needs to plug into it,
[00:33:54] et cetera, et cetera. So it seems complicated. It's still complicated. That's all the more
[00:33:59] reason why a lot of the genomic real estate  on the genome, and in terms of these different
[00:34:05] cell types and so on, would go into wiring  up the Steering Subsystem, pre-wiring it.
[00:34:10] Can we tell how much of the  genome is clearly working?
[00:34:14] So I guess you could tell how many  are relevant to producing the RNA
[00:34:18] that manifest or the epigenetics that manifest  in different cell types in the brain. Right?
[00:34:22] Yeah. This is what the cell types help you get at. I don't think it's exactly like, "Oh, this percent
[00:34:26] of the genome is doing this", but you could say,  "Okay, in all these Steering Subsystem subtypes,
[00:34:30] how many different genes are involved in  specifying which is which and how they wire?
[00:34:35] And how much genomic real estate do those  genes take up versus the ones that specify
[00:34:42] visual cortex versus auditory cortex? You're just reusing the same genes to
[00:34:46] do the same thing twice. Whereas the spider
[00:34:48] reflex hooking up… Yes, you're right. They have to build a vision system and they
[00:34:52] have to build some auditory systems and  touch systems and navigation-type systems.
[00:34:58] Even feeding into the hippocampus and stuff  like that, there's head direction cells.
[00:35:02] Even the fly brain has innate  circuits that figure out its
[00:35:06] orientation and help it navigate in the world. It uses vision, figures out its optical flow of
[00:35:11] how it's flying and how its flight  is related to the wind direction.
[00:35:16] It has all these innate stuff that I think  in the mammal brain we would all lump that
[00:35:21] into the Steering Subsystem. There's a lot  of work. So all the genes that basically go
[00:35:24] into specifying all the things a fly has to  do, we're going to have stuff like that too,
[00:35:29] just all in the Steering Subsystem. But do we have some estimate of like,
[00:35:32] "Here's how many nucleotides, here  are many megabases it takes to—"
[00:35:37] I don't know. I mean, I think you might  be able to talk to biologists about this.
[00:35:47] I mean, we have a lot in common  with yeast from a genes perspective.
[00:35:51] Yeast is still used as a model for some amount of  drug development and stuff like that in biology.
[00:35:57] And so much of the genome is just going towards  you having a cell at all, it can recycle waste,
[00:36:02] it can get energy, it can replicate. And then what do we have in common with a mouse?
[00:36:09] So we do know at some level that the differences  between us and a chimpanzee or something—and that
[00:36:13] includes the social instincts and the more  advanced differences in cortex and so on—it's
[00:36:18] a tiny number of genes that go into this  additional amount of making the eight-layer
[00:36:23] transformer instead of the six-layer  transformer or tweaking that reward function.
[00:36:28] This would help explain why the  hominid brain exploded in size so fast.
[00:36:35] Presumably, tell me if this is  correct, but under this story,
[00:36:40] social learning or some other thing increased  the ability to learn from the environment. It
[00:36:47] increased our sample efficiency. Instead of  having to go and kill the boar yourself and
[00:36:52] figure out how to do that, you can just be like,  "The elder told me this is how you make a spear."
[00:36:57] Now it increases the incentive to have a  bigger cortex, which can learn these things.
[00:37:01] Yes and that can be done with a relatively few  genes, because it's really replicating what
[00:37:06] the mouse already has, making more of it. It's maybe not exactly the same and there
[00:37:10] may be tweaks, from a genome perspective,  you don't have to reinvent all this stuff.
[00:37:16] So then how far back in the history of the  evolution of the brain does the cortex go back?
[00:37:23] Is the idea that the cortex has always figured  out this omnidirectional inference thing,
[00:37:27] that's been a solved problem for a long time? Then the big unlock with primates is that we
[00:37:32] got the reward function, which increased the  returns to having omnidirectional inference?
[00:37:36] It’s a good question. Or is the omnidirectional inference
[00:37:40] also something that took a while to unlock? I'm not sure that there's agreement about that.
[00:37:43] I think there might be specific  questions about language.
[00:37:45] Are there tweaks, whether that's  through auditory and memory,
[00:37:48] some combination auditory memory regions? There may also be macro-wiring where you need
[00:37:56] to wire auditory regions into memory regions or  something like that, and into some of these social
[00:38:01] instincts to get language, for example, to happen. But that might also be a small number of gene
[00:38:07] changes to be able to say, "Oh, I just  need from my temporal lobe over here,
[00:38:12] going over to the auditory cortex, something." There is some evidence for the Broca's area,
[00:38:16] Wernicke's area. They're connected with the
[00:38:17] hippocampus and so on and prefrontal cortex. So there's like some small number of genes
[00:38:22] maybe for enabling humans to  really properly do language.
[00:38:26] That could be a big one. But is it that something changed about the
[00:38:36] cortex and it became possible to do these things? Or is that that potential was already there,
[00:38:41] but there wasn't the incentive to expand  that capability and then use it, wire it
[00:38:46] to these social instincts and use it more? I would lean somewhat toward the latter.
[00:38:51] I think a mouse has a lot of similarity  in terms of cortex as a human.
[00:38:57] Although there's Suzana Herculano-Houzel's  work on how the number of neurons scales
[00:39:06] better with weight with primate brains  than it does with rodent brains.
[00:39:11] So does that suggest that there actually was some  improvement in the scalability of the cortex?
[00:39:16] Maybe, maybe. I'm not super deep on this. There may have been changes in architecture,
[00:39:23] changes in the folding, changes  in neuron properties and stuff
[00:39:27] that somehow slightly tweak this. But there's still a scaling. either way.
[00:39:30] That's right. So I'm not saying
[00:39:33] there isn't something special about humans in the  architecture of the Learning Subsystem at all.
[00:39:40] But yeah I think it's pretty widely  thought that this is expanded.
[00:39:44] But then the question is, "Okay, well, how  does that fit in also with the Steering
[00:39:48] Subsystem changes and the instincts  that make use of this and allow you
[00:39:51] to bootstrap using this effectively?" But just to say a few other things,
[00:39:58] even the fly brain has some amount, even very far  back… I mean, I think you've read this great book,
[00:40:05] A Brief History of Intelligence, right? I think this is a really good book.
[00:40:08] Lots of AI researchers think this  is a really good book it seems.
[00:40:13] You have some amount of learning going back  all the way to anything that has a brain.
[00:40:20] Basically you have something like  primitive reinforcement learning,
[00:40:28] going back at least to vertebrates. Imagine a  zebrafish. Then you have these other branches.
[00:40:37] Birds may have reinvented something cortex-like. It doesn't have the six layers,
[00:40:41] but they have something a little bit cortex-like. So some of those things after reptiles, in some
[00:40:47] sense birds and mammals both made a somewhat  cortex-like, but differently organized thing.
[00:40:53] But even a fly brain has associative learning  centers that actually do things that maybe look
[00:40:59] a little bit like this Thought Assessor concept  from Byrnes, where there's a specific dopamine
[00:41:03] signal to train specific subgroups of neurons  in the fly mushroom body to associate different
[00:41:09] sensory information with, "Am I going to get  food now?" or "Am I going to get hurt now?"
[00:41:15] Brief tangent. I remember reading in one  blog post that Beren Millidge wrote that
[00:41:21] the parts of the cortex which are associated with  audio and vision have scaled disproportionately
[00:41:31] between other primates and humans, whereas  the parts associated, say, with odor have not.
[00:41:37] And I remember him saying something like  that this is explained by that kind of
[00:41:41] data having worse scaling law properties. Maybe he meant this, but I think another
[00:41:49] interpretation of actually what's happening  there is that these social reward functions
[00:41:55] that are built into the Steering Subsystem  needed to make use more of being able to
[00:42:01] see your elders and see what the visual  cues are and hear what they're saying.
[00:42:05] And in order to make sense of these cues  which guide learning, you needed to activate
[00:42:12] the vision and audio more than odor. I mean, there's all this stuff.
[00:42:15] I feel like it's come up in  your shows before, actually.
[00:42:19] But like even the design of the human eye where  you have the pupil and the white and everything,
[00:42:24] we are designed to be able to establish  relationships based on joint eye contact.
[00:42:28] Maybe this came up in the Sutton episode. I  can't remember. But yeah, we have to bootstrap
[00:42:33] to the point where we can detect eye contact  and where we can communicate by language.
[00:42:38] That's like what the first couple  years of life are trying to do.
[00:42:42] Okay, I want to ask you about RL. So currently, the way these LLMs are trained,
[00:42:49] if they solve the unit test or solve  a math problem, that whole trajectory,
[00:42:53] every token in that trajectory is upweighted.  What's going on with humans? Are there different
[00:42:58] types of model-based versus model-free that  are happening in different parts of the brain?
[00:43:02] Yeah, I mean, this is another one of these things. Again, all my answers to these questions,
[00:43:06] any specific thing I say, it’s all just saying  that directionally we can explore around this.
[00:43:10] I find this interesting, maybe I feel  like the literature points in these
[00:43:14] directions in some very broad way. What I actually want to do is go and
[00:43:17] map the entire mouse brain and figure this  out comprehensively and make neuroscience
[00:43:21] a ground-truth science. So I don't know,  basically. But first of all, I think with
[00:43:29] Ilya on the podcast, he was like, "It's weird  that you don't use value functions, right?"
[00:43:33] You use the dumbest form of RL basically. Of course these people are incredibly smart
[00:43:38] and they're optimizing for how to do it on GPUs  and it's really incredible what they're achieving.
[00:43:42] But conceptually it's a really dumb form of RL,  even compared to what was being done 10 years ago.
[00:43:48] Even the Atari game-playing stuff was  using Q-learning, which is basically
[00:43:54] a kind of temporal difference learning. The temporal difference learning basically
[00:43:58] means you have some kind of a value function of  what action I choose now doesn't just tell me
[00:44:04] literally what happens immediately after this. It tells me what is the long-run consequence
[00:44:08] of that for my expected total  reward or something like that.
[00:44:14] So you would have value functions  like… The fact that we don't have
[00:44:17] value functions at all in the LLMs is crazy. I think because Ilya said it, I can say it.
[00:44:26] I know one one-hundredth of what he does about  AI, but it's kind of crazy that this is working.
[00:44:34] But in terms of the brain, I think there are  some parts of the brain that are thought to do
[00:44:45] something that's very much like model-free RL,  that's parts of the striatum and basal ganglia.
[00:44:54] It is thought that they have a certain  finite relatively small action space.
[00:44:58] The types of actions they could take, first  of all, might be like, "Tell the brainstem
[00:45:03] and spinal cord to do this motor action?  Yes or no." Or it might be more complicated
[00:45:09] cognitive-type actions like, "Tell the thalamus  to allow this part of the cortex to talk to this
[00:45:13] other part," or "Release the memory that's in the  hippocampus and start a new one or something."
[00:45:19] But there's some finite set of actions  that come out of the basal ganglia,
[00:45:23] and that it's just a very simple RL. So there are probably parts of other
[00:45:28] brains and our brain that are just doing  very simple naive-type RL algorithms.
[00:45:34] Layering one thing on top of that is that  some of the major work in neuroscience,
[00:45:38] like Peter Dayan's work, and a bunch of work that  is part of why I think DeepMind did the temporal
[00:45:43] difference learning stuff in the first place. They were very interested in neuroscience.
[00:45:50] There's a lot of neuroscience evidence that  the dopamine is giving this reward prediction
[00:45:53] error signal, rather than just reward, "yes  or no, a gazillion time steps in the future."
[00:45:59] It's a prediction error and that's consistent  with learning these value functions.
[00:46:06] So there's that and then there's  maybe higher-order stuff.
[00:46:09] We have the cortex making this world model. Well, one of the things the cortex world
[00:46:13] model can contain is a model of  when you do and don't get rewards.
[00:46:18] Again, it's predicting what  the Steering Subsystem will do.
[00:46:20] It could be predicting what  the basal ganglia will do.
[00:46:23] You have a model in your cortex that has  more generalization and more concepts and
[00:46:27] all this stuff that says, "Okay, these types of  plans, these types of actions will lead in these
[00:46:33] types of circumstances to reward." So I have a model of my reward.
[00:46:37] Some people also think that  you can go the other way.
[00:46:40] So this is part of the inference picture. There's this idea of RL as inference.
[00:46:45] You could say, "Well, conditional  on my having a high reward,
[00:46:49] sample a plan that I would have had to get there."
[00:46:53] That's inference of the plan  part from the reward part.
[00:46:56] I'm clamping the reward as high and inferring the  plan, sampling from plans that could lead to that.
[00:47:02] So if you have this very general  cortical thing, it can just do.
[00:47:05] If you have this very general model-based  system and the model, among other things,
[00:47:09] includes plans and rewards, then  you just get it for free, basically.
[00:47:14] So in neural network parlance, there's a  value head associated to the omnidirectional
[00:47:22] inference that's happening in the— Yes, or there's a value input.
[00:47:26] Oh, okay. Interesting. Yeah and it can predict.
[00:47:29] One of the almost sensory variables it can  predict is what rewards it's going to get.
[00:47:34] By the way, speaking about amortizing things,
[00:47:39] obviously value is like amortized  rollouts of looking up reward.
[00:47:46] Yeah, something like that. It's like a  statistical average or prediction of it.
[00:47:52] Tangential thought. Joe Henrich and others have  this idea for the way human societies have learned
[00:48:00] to do things like, how do you figure out that this  kind of bean, which actually just almost always
[00:48:08] poisons you, is edible if you do this ten-step  incredibly complicated process, any one of which
[00:48:14] if you fail, at the bean will be poisonous? How do you figure out how to hunt this seal in
[00:48:19] this particular way, with this particular weapon,  at this particular time of the year, et cetera?
[00:48:24] There's no way but just like  trying shit over generations.
[00:48:29] And it strikes me this is actually  very much like model-free RL happening
[00:48:32] at a civilizational level. No, not exactly. Evolution is the simplest algorithm in some sense.
[00:48:39] If we believe that all of  this can come from evolution,
[00:48:41] the outer loop can be extremely not foresighted. Right, that's interesting. Just hierarchies
[00:48:49] of… Evolution: model-free… So what does that tell you?
[00:48:53] Maybe the simple algorithms can just  get you anything if you do it enough.
[00:48:56] Right. Yeah, I don't know.
[00:48:57] So, evolution: model-free. Basal ganglia:  model-free. Cortex: model-based. Culture:
[00:49:09] model-free potentially. I mean you pay  attention to your elders or whatever.
[00:49:13] Maybe there's like group selection or whatever  of these things is like more model-free.
[00:49:18] But now I think culture, well,  it stores some of the model.
[00:50:32] Stepping back, is it a disadvantage or an  advantage for humans that we get to use
[00:50:42] biological hardware, in comparison  to computers as they exist now?
[00:50:47] What I mean by this question is, if there's  "the algorithm", would the algorithm just
[00:50:51] qualitatively perform much worse or much  better if inscribed in the hardware of today?
[00:50:56] The reason to think it might…. Here's  what I mean. Obviously the brain has
[00:51:00] had to make a bunch of tradeoffs which  are not relevant to computing hardware.
[00:51:04] It has to be much more energetically efficient. Maybe as a result it has to run on slower speeds
[00:51:09] so that there can be a smaller voltage gap. So the brain runs at 200 hertz,
[00:51:13] it has to run on 20 watts. On the other hand, with robotics
[00:51:17] we've clearly experienced that fingers are way  more nimble than we can make motors so far.
[00:51:23] So maybe there's something in the brain that  is the equivalent of cognitive dexterity,
[00:51:27] which is maybe due to the fact that  we can do unstructured sparsity.
[00:51:30] We can co-locate the memory and the compute. Yes.
[00:51:33] Where does this all net out? Are you like, "Fuck, we would
[00:51:35] be so much smarter if we didn't have to  deal with these brains." Or are you like—
[00:51:39] I think in the end we will get  the best of both worlds somehow.
[00:51:42] I think an obvious downside of  the brain is it cannot be copied.
[00:51:45] You don't have external read-write access  to every neuron and synapse, whereas you do.
[00:51:50] I can just edit something in the weight matrix in  Python or whatever and load that up and copy that.
[00:51:58] In principle. So the fact that it can't be  copied and random-accessed is very annoying.
[00:52:06] But otherwise maybe it has a lot of advantages. It also tells you that you want to somehow do
[00:52:11] the co-design of the algorithm. It maybe even doesn't change it
[00:52:16] that much from all of what we discussed,  but you want to somehow do this co-design.
[00:52:19] So yeah, how do you do it with  really slow low-voltage switches?
[00:52:24] That's going to be really important for energy  consumption. Co-locating memory and compute. I
[00:52:31] think that hardware companies will probably  just try to co-locate memory and compute.
[00:52:35] They will try to use lower voltages,  allow some stochastic stuff.
[00:52:39] There are some people that think that all  this probabilistic stuff that we were talking
[00:52:43] about—"Oh, it's actually energy-based models,  so on"—it is doing lots of sampling. It's not
[00:52:48] just amortizing everything. The neurons  are also very natural for that because
[00:52:53] they're naturally stochastic. So you don't have to do a random
[00:52:57] number generator in a bunch of Python  code basically to generate a sample.
[00:53:02] The neuron just generates samples  and it can tune what the different
[00:53:05] probabilities are and learn those tunings. So it could be that it's very co-designed with
[00:53:13] some kind of inference method or something. It'd be hilarious…. I mean the
[00:53:17] message I'm taking from this interview is  that like all these people that folks make
[00:53:21] fun of on Twitter, Yann LeCun and Beff Jezos and  whatever, I don’t know maybe they got it right.
[00:53:28] That is actually one read of it. Granted, I haven't really worked on AI at all
[00:53:33] since LLMs took off, so I'm just out of the loop. But I'm surprised and I think it's amazing how
[00:53:40] the scaling is working and everything. But yeah, I think Yann LeCun and Beff
[00:53:44] Jezos are kind of onto something about the  probabilistic models or at least possibly.
[00:53:48] In fact that's what all the neuroscientists and  all the AI people thought until 2021 or something.
[00:53:54] Right. So there's a bunch of cellular stuff  happening in the brain that is not just about
[00:54:00] neuron-to-neuron synaptic connections. How much of that is functionally doing
[00:54:07] more work than the synapses themselves are doing  versus it's just a bunch of kludge that you have
[00:54:15] to do in order to make the synaptic thing work. So with a digital mind, you can nudge the synapse,
[00:54:22] sorry the parameter, extremely easily. But with a cell to modulate a synapse
[00:54:29] according to the gradient signal, it  just takes all this crazy machinery.
[00:54:33] So is it actually doing more than it  takes extremely little code to do?
[00:54:36] I don't know, but I'm not a believer in  the radical, "Oh, actually memory is not
[00:54:42] synapses mostly, or learning is mostly  genetic changes" or something like that.
[00:54:48] I think it would just make a lot of sense, I  think you put it really well for it to be more
[00:54:52] like the second thing you said. Let's say you want to do weight
[00:54:54] normalization across all the weights coming  out of your neuron or into your neuron.
[00:55:00] Well, you probably have to somehow tell  the nucleus of the cell about this and
[00:55:04] then have that send everything back  out to the synapses or something.
[00:55:08] So there's going to be a lot of cellular changes.
[00:55:10] Or let's say that you just had a lot of  plasticity and you're part of this memory.
[00:55:16] Now that's got consolidated  into the cortex or whatever.
[00:55:20] Now we want to reuse you as a  new one that can learn again.
[00:55:24] There's going to be a ton of cellular  changes, so there's going to be tons
[00:55:26] of stuff happening in the cell. But algorithmically, it's not really
[00:55:30] adding something beyond these algorithms. It's just implementing something that in a
[00:55:34] digital computer is very easy for us to go  and just find the weights and change them.
[00:55:38] In a cell, it just literally has to do  all this with molecular machines itself
[00:55:42] without any central controller. It's kind of  incredible. There are some things that cells do,
[00:55:48] I think, that seem more convincing. One of the things the cerebellum has
[00:55:53] to do is predict over time. What is the time  delay? Let's say that I see a flash and then
[00:56:02] some number of milliseconds later, I'm going  to get a puff of air in my eyelid or something.
[00:56:07] The cerebellum can be very good at  predicting what's the timing between
[00:56:11] the flash and the air puff, so that now  your eye will just close automatically.
[00:56:15] The cerebellum is involved in that  type of reflex, learned reflex.
[00:56:20] There are some cells in the cerebellum where  it seems like the cell body is playing a role
[00:56:26] in storing that time constant, changing that time  constant of delay, versus that all being somehow
[00:56:33] done with like, "I'm going to make a longer  ring of synapses to make that delay longer."
[00:56:37] No, the cell body will just  store that time delay for you.
[00:56:42] So there are some examples, but I'm not a  believer out of the box in essentially this
[00:56:49] theory that what's happening is changes in  connections between neurons and that that's
[00:56:55] the main algorithmic thing that's going on. I think there's very good reason to still
[00:57:00] believe that it's that rather  than some crazy cellular stuff.
[00:57:04] Going back to this whole perspective of how our  intelligence is not just this omnidirectional
[00:57:11] inference thing that builds a world model, but  really this system that teaches us what to pay
[00:57:17] attention to what the important salient  factors are to learn from, et cetera.
[00:57:22] I want to see if there's some intuition we  can drive from this about what different
[00:57:28] kinds of intelligences might be like. So it seems like AGI or superhuman
[00:57:32] intelligence should still have this ability  to learn a world model that's quite general,
[00:57:40] but then it might be incentivized to pay attention  to different things that are relevant for the
[00:57:51] modern post-singularity environment. How different should we expect
[00:57:55] different intelligences to be? I think one way to think about this
[00:57:58] question is, is it actually possible to  make the paperclip maximizer or whatever?
[00:58:02] If you try to make the paperclip maximizer,  does it end up just not being smart or
[00:58:07] something like that because the only reward  function it had was to make paperclips?
[00:58:11] I'd say, can you do that? I don't know. If I  channel Steve Byrnes more, I think he's very
[00:58:14] concerned that the minimum viable things in the  Steering Subsystem that you need to get something
[00:58:19] smart is way less than the minimum viable set of  things you need for it to have human-like social
[00:58:25] instincts and ethics and stuff like that. So a lot of what you want to know about
[00:58:28] the Steering Subsystem is actually the  specifics of how you do alignment essentially,
[00:58:33] or what human behavior and social instincts  is versus just what you need for capabilities.
[00:58:40] We talked about it in a slightly different  way because we were sort of saying, "Well,
[00:58:42] in order for humans to learn socially, they  need to make eye contact and learn from others."
[00:58:47] But we already know from LLMs that  depending on your starting point,
[00:58:50] you can learn language without that stuff. So I think that it probably is possible to
[00:58:59] make super powerful model-based RL optimizing  systems and stuff like that that don't have
[00:59:06] most of what we have in the human brain reward  functions and as a consequence might want to
[00:59:10] maximize paperclips. And that's a concern. But you're pointing out that in order to
[00:59:15] make a competent paperclip maximizer, the  kind of thing that can build spaceships and
[00:59:20] learn physics and whatever, it needs to  have some drives which elicit learning,
[00:59:27] including say curiosity and exploration. Yeah, curiosity, interest in others,
[00:59:33] interest in social interactions. But that's pretty minimal I think.
[00:59:39] And that's true for humans, but it might  be less true for something that's already
[00:59:43] pretrained as an LLM or something. So most of why we want to know
[00:59:47] the Steering Subsystem, I think if I'm  channeling Steve, is alignment reasons.
[00:59:52] How confident are we that we even have the  right algorithmic conceptual vocabulary
[01:00:01] to think about what the brain is doing? What I mean by this is that there was one
[01:00:06] big contribution to AI from neuroscience  which was this idea of the neuron in the
[01:00:12] 1950s, just this original contribution. But then it seems like a lot of what we've
[01:00:16] learned afterwards about what the high-level  algorithm the brain is implementing, from
[01:00:22] the backprop to if there's something analogous to  backprop happening in the brain to "Oh is V1 doing
[01:00:28] something like CNNs" to TD learning and Bellman  equations, actor-critic, whatever… It seems
[01:00:34] inspired by this dynamic where we come  up with some idea, maybe we can make AI
[01:00:39] neural networks work this way, and then we notice  that something in the brain also works that way.
[01:00:44] So why not think there's more things like this. There may be. I think the reason that I think
[01:00:49] that we might be onto something is  that the AIs we're making based on
[01:00:54] these ideas are working surprisingly well. There's also a bunch of just empirical stuff.
[01:01:00] Convolutional neural nets and  variants of convolutional neural nets.
[01:01:04] I'm not sure what the absolute latest  is, but compared to other models in
[01:01:08] computational neuroscience of what the visual  system is doing, they are just more predictive.
[01:01:13] You can just score, even pretrained  on cat pictures and stuff, CNNs,
[01:01:20] what is the representational similarity that they  have on some arbitrary other image compared to the
[01:01:26] brain activations measured in different ways? Jim DiCarlo's lab has this brain score and
[01:01:34] the AI model is actually… There  seems to be some relevance there.
[01:01:39] Neuroscience doesn't necessarily  have something better than that.
[01:01:43] So yes, that's just recapitulating what  you're saying, that the best computational
[01:01:46] neuroscience theories we have seem to  have been invented largely as a result
[01:01:51] of AI models and finding things that work. So find backprop works and then saying, "Can
[01:01:56] we approximate backprop with cortical circuits?"  or something. There's been things like that. Now,
[01:02:01] some people totally disagree with this. György Buzsáki is a neuroscientist who has
[01:02:07] a book called The Brain from the Inside Out where  he basically says all our psychology concepts,
[01:02:13] AI concepts, all this stuff is just made-up stuff. What we actually have to do is figure out what
[01:02:17] is the actual set of primitives  that the brain actually uses.
[01:02:19] And our vocabulary is not  going to be adequate to that.
[01:02:23] We have to start with the brain and  make new vocabulary rather than saying
[01:02:26] backprop and then try to apply that  to the brain or something like that.
[01:02:30] He studies a lot of oscillations and stuff  in the brain as opposed to individual neurons
[01:02:34] and what they do. I don't know. I think  that there's a case to be made for that.
[01:02:40] And from a research program design perspective,  one thing we should be trying to do is just
[01:02:45] simulate a tiny worm or a tiny zebrafish, almost  as biophysical or as bottom-up as possible.
[01:02:54] Like get connectome, molecules,  activity and just study it as a physical
[01:02:59] dynamical system and look at what it does. But I don't know, it just feels like AI is
[01:03:07] really good fodder for computational neuroscience. Those might actually be pretty good models. We
[01:03:11] should look at that. I both think that there  should be a part of the research portfolio
[01:03:20] that is totally bottom-up and not trying to apply  our vocabulary that we learn from AI onto these
[01:03:26] systems, and that there should be another big part  of this that's trying to reverse engineer it using
[01:03:31] that vocabulary or variant of that vocabulary. We should just be pursuing both.
[01:03:38] My guess is that the reverse engineering one  is actually going to work-ish or something.
[01:03:45] Like we do see things like TD learning,  which Sutton also invented separately.
[01:03:50] That must be a crazy feeling to just like— Yeah, that's crazy.
[01:03:54] This equation I wrote down is like in the brain. It seems like the dopamine is
[01:03:58] doing some of that, yeah. So let me ask you about this.
[01:04:02] You guys are funding different groups that are  trying to figure out what's up in the brain.
[01:04:07] If we had a perfect representation,  however you define it, of the brain,
[01:04:12] why think it would actually let us  figure out the answer to these questions?
[01:04:17] We have neural networks which are way  more interpretable, not just because we
[01:04:22] understand what's in the weight matrices,  but because there are weight matrices.
[01:04:24] There are these boxes with numbers in them. Even then we can tell very basic things.
[01:04:31] We can kind of see circuits for very basic pattern  matching of following one token with another.
[01:04:38] I feel like we don't really have an  explanation of why LLMs are intelligent
[01:04:41] just because they’re interpretable. I think I would somewhat dispute it.
[01:04:46] We have some description of what  the LLM is fundamentally doing.
[01:04:49] What that's doing is that I have an  architecture and I have a learning
[01:04:52] rule and I have hyperparameters and I have  initialization and I have training data.
[01:04:57] But those are things we learned because we  built them, not because we interpreted them
[01:05:01] from seeing the weights. The analogous thing to
[01:05:04] connectome is like seeing the weights. What I think we should do is we should
[01:05:06] describe the brain more in that language of  things like architectures, learning rules,
[01:05:10] initializations, rather than trying to find the  Golden Gate Bridge circuit and saying exactly
[01:05:14] how this neuron actually… That's going to be  some incredibly complicated learned pattern.
[01:05:21] Konrad Kording and Tim Lillicrap  have this paper from a while ago,
[01:05:24] maybe five years ago, called "What does  it mean to understand a neural network?"
[01:05:31] What they say is basically that you could  imagine you train a neural network to compute
[01:05:36] the digits of pi or something. It's like  some crazy pattern. You also train that
[01:05:41] thing to predict the most complicated  thing you find, predict stock prices,
[01:05:44] basically predict really complex systems,  computationally complete systems.
[01:05:49] I could train a neural network to do  cellular automata or whatever crazy thing.
[01:05:53] It's like, we're never going to be able to fully  capture that with interpretability, I think.
[01:05:59] It's just going to just be doing really  complicated computations internally.
[01:06:03] But we can still say that the way it got that  way is that it had an architecture and we gave it
[01:06:07] this training data and it had this loss function. So I want to describe the brain in the same way.
[01:06:10] And I think that this framework that  I've been kind of laying out is that
[01:06:13] we need to understand the cortex and  how it embodies a learning algorithm.
[01:06:16] I don't need to understand how  it computes "Golden Gate Bridge."
[01:06:19] But if you can see all the neurons, if you have  the connectome, why does that teach you what
[01:06:23] the learning algorithm is? Well, I guess there are a
[01:06:26] couple different views of it. So it depends on these different
[01:06:27] parts of this portfolio. On the totally bottom-up,
[01:06:30] we-have-to-simulate-everything  portfolio, it kind of just doesn't.
[01:06:33] You have to make a simulation of the zebrafish  brain or something and then you see what are
[01:06:39] the emergent dynamics in this and you come up  with new names and new concepts and all that.
[01:06:42] That's the most extreme  bottom-up neuroscience view.
[01:06:48] But even there the connectome  is really important for doing
[01:06:50] that biophysical or bottom-up simulation. But on the other hand you can say, "Well,
[01:06:56] what if we can actually apply some ideas from AI?" We basically need to figure out,
[01:07:00] is it an energy-based model or is  it an amortized VAE-type model?
[01:07:06] Is it doing backprop or is  it doing something else?
[01:07:09] Are the learning rules local or global? If we have some repertoire of possible
[01:07:14] ideas about this, just think of the connectome  as a huge number of additional constraints that
[01:07:22] will help to refine, to ultimately  have a consistent picture of that.
[01:07:25] I think about this for the Steering Subsystem  stuff too, just very basic things about it.
[01:07:29] How many different types of dopamine signal  or of Steering Subsystem signal or thought
[01:07:35] assessor or so on… How many different  types of what broad categories are there?
[01:07:39] Like even this very basic information  that there's more cell types in the
[01:07:41] hypothalamus than there are in the cortex,  that's new information about how much
[01:07:46] structure is built there versus somewhere else. How many different dopamine neurons are there?
[01:07:50] Is the wiring between prefrontal and auditory the  same as the wiring between prefrontal and visual?
[01:07:56] The most basic things, we don't know. The problem is learning even the
[01:08:01] most basic things by a series of bespoke  experiments takes an incredibly long time.
[01:08:05] Whereas just learning all that at once by  getting a connectome is just way more efficient.
[01:08:10] What is the timeline on this? Presumably the idea of this is,
[01:08:14] first, to inform the development of AI. You want to be able to figure out how
[01:08:22] we get AIs to want to care about what other  people think of its internal thought pattern.
[01:08:28] But interp researchers are making progress on  this question just by inspecting normal neural
[01:08:33] networks. There must be some feature… You can do interp on LLMs that exist.
[01:08:38] You can't do interp on a hypothetical model-based  reinforcement algorithm like the brain that we
[01:08:44] will eventually converge to when we do AGI. Fair. But what timelines on AI do you need
[01:08:51] for this research to be practical and relevant? I think it's fair to say it's not super practical
[01:08:56] and relevant if you're in an AI 2027 scenario. And so what science I'm doing now is not going
[01:09:04] to affect the science of ten years from now. Because what's going to affect the science
[01:09:07] of 10 years from now is the  outcome of this AI 2027 scenario.
[01:09:11] It kind of doesn't matter that much  probably if I have the connectome,
[01:09:14] maybe it slightly tweaks certain things. But I think there's a lot of reason to think
[01:09:21] maybe that we will get a lot out of this paradigm. But then the real thing, the thing that is the
[01:09:30] single event that is transformative for the  entire future or something type event is still
[01:09:37] more than five years away or something. Is that because we haven't captured
[01:09:42] omnidirectional inference, we haven't figured  out the right ways to get a mind to pay attention
[01:09:49] to things in a way that makes sense? I mean, I would take the entirety of
[01:09:52] your collective podcast with everyone  as showing the distribution of these
[01:09:57] things. I don't know. What was Karpathy's  timeline, right? What's Demis's timeline? So
[01:10:04] not everybody has a three-year timeline. But there are different reasons and I'm
[01:10:09] curious which ones are yours. What are mine?
[01:10:12] I don't know, I'm just watching your podcast. I'm trying to understand the distribution.
[01:10:15] I don't have a super strong  claim that LLMs can't do it.
[01:10:19] But is the crux the data efficiency or…? I think part of it is just that it is
[01:10:23] weirdly different from all this brain stuff. So intuitively it's just weirdly different
[01:10:27] than all this brain stuff and I'm  kind of waiting for the thing that
[01:10:30] starts to look more like brain stuff. I think if AlphaZero, and model-based RL
[01:10:34] and all these other things that were being  worked on 10 years ago, had been giving us
[01:10:37] the GPT-5 type capabilities, then I would  be like, "Oh wow, we're both in the right
[01:10:43] paradigm and seeing the results a priori. So my prior and my data are agreeing."
[01:10:50] Now it's like, "I don't know  what exactly my data is.
[01:10:53] Looks pretty good, but my prior is sort of weird  so I don't have a super strong opinion on it."
[01:10:59] So I think there's a possibility that  essentially all other scientific research
[01:11:04] that is being done is somehow obviated. But I don't put a huge amount of
[01:11:09] probability on that. I think my timelines
[01:11:11] might be more in the 10-year-ish range. If that's the case, I think there is
[01:11:16] probably a difference between a world where we  have connectomes on hard drives and we have an
[01:11:20] understanding of Steering Subsystem architecture. We've compared even the most basic properties
[01:11:25] of what are the reward functions, cost function,  architecture, et cetera, of a mouse versus a shrew
[01:11:30] versus a small primate, et cetera. Is this practical in 10 years?
[01:11:34] I think it has to be a really big push. How much funding,
[01:11:37] how does it compare to where we are now? It's like low billions-dollar scale funding
[01:11:42] in a very concerted way I would say. And how much is on it now?
[01:11:47] So if I just talk about some of the specific  things we have going on with connectomics…
[01:11:52] E11 Bio is our main thing on connectomics. They are trying to make the technology of
[01:12:02] connectomic brain mapping several  orders of magnitude cheaper.
[01:12:08] The Wellcome Trust put out a report a year  or two ago that said to get one mouse brain,
[01:12:13] the first mouse brain connectome would  be a several billion dollars project.
[01:12:20] E11 technology, and the suite of efforts  in the field, is trying to get a single
[01:12:26] mouse connectome down to low tens of  millions of dollars. That's a mammal
[01:12:32] brain. A human brain is about 1,000 times bigger. If with a mouse brain you can get to $10 million
[01:12:37] or $20 million, $30 million, with technology,  if you just naively scale that, a human brain
[01:12:42] is now still billions of dollars, to just do one  human brain. Can you go beyond that? Can you get
[01:12:47] a human brain for less than a billion? But I'm not sure you need every neuron
[01:12:50] in the human brain. We want to, for example,
[01:12:52] do an entire mouse brain and a human Steering  Subsystem and the entire brains of several
[01:12:59] different mammals with different social instincts. So with a bunch of technology push and a bunch of
[01:13:05] concerted effort, real significant progress  if it's focused effort can be done in the
[01:13:11] hundreds of millions to low billions scale. What is the definition of a connectome?
[01:13:16] Presumably it's not a bottom-up biophysics model. So is it just that it can estimate
[01:13:22] the input-output of a brain? What is the level of abstraction?
[01:13:26] You can give different definitions and one of the  things that's cool… So the standard approach to
[01:13:31] connectomics uses the electron microscope and  very, very thin slices of brain tissue. It's
[01:13:36] basically labeling. The cell membranes are going  to show up, scatter electrons a lot and everything
[01:13:42] else is going to scatter electrons less. But you don't see a lot of details of the
[01:13:45] molecules, which types of synapses,  different synapses of different
[01:13:48] molecular combinations and properties. E11 and some other research in the field
[01:13:53] has switched to an optical microscope paradigm. With optical, the photons don't damage the tissue,
[01:13:57] so you can wash it and look  at fragile gentle molecules.
[01:14:03] So with E11's approach, you can get  a "molecularly annotated connectome."
[01:14:07] That's not just who is connected to who by  some synapse, but what are the molecules that
[01:14:12] are present at the synapse? What type of cell is that?
[01:14:15] A molecularly annotated connectome, that's not  exactly the same as having the synaptic weights.
[01:14:21] That's not exactly the same as being  able to simulate the neurons and say
[01:14:25] what's the functional consequence of  having these molecules and connections.
[01:14:30] But you can also do some amount  of activity mapping and try to
[01:14:34] correlate structure to function. Train an ML model basically to predict
[01:14:40] the activity from the connectome. What are the lessons to be taken
[01:14:44] away from the Human Genome Project? One way you could look at it is that
[01:14:48] it was a mistake and you shouldn't have spent  billions of dollars getting one genome mapped.
[01:14:53] Rather you should have just invested in  technologies which have now allowed us to
[01:14:57] map genomes for hundreds of dollars. Well, George Church was my PhD advisor and he's
[01:15:03] pointed out that it was $3 billion or something,  roughly $1 per base pair for the first genome.
[01:15:09] Then the National Human Genome Research Institute  basically structured the funding process right.
[01:15:15] They got a bunch of companies  competing to lower the cost.
[01:15:19] And then the cost dropped like a million-fold in  10 years because they changed the paradigm from
[01:15:27] macroscopic chemical techniques to these  individual DNA molecules which would make a
[01:15:31] little cluster of DNA molecules on the microscope  and you would see just a few DNA molecules at a
[01:15:35] time on each pixel of the camera. It would give you a different,
[01:15:39] in parallel, look at different fragments of DNA.
[01:15:41] So you parallelize the thing by millions-fold. That's what reduced the cost by millions-fold.
[01:15:50] With switching from electron microscopy  to optical connectomics, potentially even
[01:15:54] future types of connectomics technology,  we think there should be similar patterns.
[01:15:57] That's why E11, the Focus Research Organization,  started with technology development rather than
[01:16:03] starting with saying we're going to do a human  brain or something and let's just brute force it.
[01:16:06] We said let's get the cost  down with new technology.
[01:16:09] But then it's still a big thing. Even with new next-generation technology,
[01:16:14] you still need to spend hundreds  of millions on data collection.
[01:16:18] Is this going to be funded with  philanthropy, by governments, by investors?
[01:16:22] This is very TBD and very much  evolving in some sense as we speak.
[01:16:28] I'm hearing some rumors going  around of connectomics-related
[01:16:31] companies potentially forming. So far E11 has been philanthropy.
[01:16:36] The National Science Foundation just  put out this call for Tech Labs,
[01:16:39] which is somewhat FRO-inspired or related. You could have a tech lab for actually going and
[01:16:47] mapping the mouse brain with us and that would be  philanthropy plus government still in a nonprofit,
[01:16:52] open-source framework. But can companies  accelerate that? Can you credibly link
[01:17:00] connectomics to AI in the context of a company  and get investment for that? It's possible.
[01:17:05] I mean the cost of training  these AIs is increasing so much.
[01:17:07] If you could tell some story of not only are  we going to figure out some safety thing,
[01:17:13] but in fact once we do that, we'll also be  able to tell you how AI works… You should go
[01:17:20] to these AI labs and just be like, "Give me one  one-hundredth of your projected budget in 2030."
[01:17:26] I sort of tried a little bit seven or eight  years ago and there was not a lot of interest.
[01:17:30] Maybe now there would be. But all the things that  we've been talking about, it's really fun to talk
[01:17:39] about, but it's ultimately speculation. What is the actual reason for the energy
[01:17:43] efficiency of the brain, for example? Is it doing real inference or
[01:17:47] amortized inference or something else? This is all answerable by neuroscience.
[01:17:52] It's going to be hard, but  it's actually answerable.
[01:17:55] So if you can only do that for low billions of  dollars or something to really comprehensively
[01:17:59] solve that, it seems to me, in the grand scheme  of trillions of dollars of GPUs and stuff,
[01:18:03] it actually makes sense to do that investment. Also, there's been many labs that have been
[01:18:10] launched in the last year where they're raising  on the valuation of billions for things which
[01:18:15] are quite credible but are not like, "Our  ARR next quarter is going to be whatever."
[01:18:21] It's like we're going to discover materials and— Yes, moonshot startups or billionaire-backed
[01:18:28] startups. Moonshot
[01:18:28] startups I see as on a continuum with FROs. FROs are a way of channeling philanthropic
[01:18:34] support and ensuring that it's open  source public benefit, various other
[01:18:37] things that may be properties of a given FRO. But yes, billionaire-backed startups, if they can
[01:18:44] target the right science, the exact right science. I think there's a lot of ways to do moonshot
[01:18:48] neuroscience companies that would  never get you the connectome.
[01:18:51] It's like, "Oh, we're going to upload the  brain" or something, but never actually get
[01:18:53] the mouse connectome or something. These fundamental things that you
[01:18:57] need to get to ground truth the science. There are lots of ways to have a moonshot
[01:19:04] company go wrong and not do the actual science. But there also may be ways to have companies or
[01:19:08] big corporate labs get involved  and actually do it correctly.
[01:19:13] This brings to mind an idea that you had  in a lecture you gave five years ago about.
[01:19:21] Do you want to explain behavior cloning? Actually this is funny because the first
[01:19:26] time I saw this idea, I think it might  have been in a blog post by Gwern.
[01:19:32] There's always a Gwern blog post. There are now academic research
[01:19:36] efforts and some amount of emerging  company-type efforts to try to do this.
[01:19:42] Normally, let's say I'm training  an image classifier or something.
[01:19:44] I show it pictures of cats and dogs or whatever  and they have the label "cat" or "dog".
[01:19:50] And I have a neural network that's supposed to  predict the label "cat" or "dog" or something.
[01:19:57] That is a limited amount of information per label  that you're putting in. It's just "cat" or "dog".
[01:20:05] What if I also had, "Predict what is my  neural activity pattern when I see a cat
[01:20:11] or when I see a dog and all the other things?" If you add that as an auxiliary loss function or
[01:20:18] an auxiliary prediction task, does that sculpt the  network to know the information that humans know
[01:20:26] about cats and dogs and to represent it in a way  that's consistent with how the brain represents
[01:20:31] it and the kind of representational dimensions  or geometry of how the brain represents things,
[01:20:37] as opposed to just having these labels? Does that let it generalize better?
[01:20:41] Does that let it have richer labeling? Of course that sounds really challenging.
[01:20:47] It's very easy to generate lots  and lots of labeled cat pictures.
[01:20:51] Scale AI or whatever can do this. It is harder to generate lots and
[01:20:56] lots of brain activity patterns that correspond  to things that you want to train the AI to do.
[01:21:02] But again, this is just a technological  limitation of neuroscience.
[01:21:04] If every iPhone was also a brain scanner,  you would not have this problem and we would
[01:21:09] be training AI with the brain signals. It's just the order in which technology
[01:21:13] has developed is that we got GPUs  before we got portable brain scanners.
[01:21:18] What is the ML analog, what you'd be doing here? Because when you distill models,
[01:21:22] you're still looking at the final  layer of the log probs across all—
[01:21:30] If you distill one model into  another, that is a certain thing.
[01:21:35] You are just trying to copy  one model into another.
[01:21:38] I think that we don't really have a  perfect proposal to distill the brain.
[01:21:47] To distill the brain you need a  much more complex brain interface.
[01:21:50] Maybe you could also do that. You could  make surrogate models. Andreas Tolias and
[01:21:55] people like that are doing some amount of neural  network surrogate models of brain activity data.
[01:22:00] Instead of having your visual cortex do the  computation, just have the surrogate model.
[01:22:04] So you're distilling your visual  cortex into a neural network to
[01:22:07] some degree. That's a kind of distillation.  This is doing something a little different.
[01:22:11] This is basically just saying I'm adding an  auxiliary… I think of it as regularization
[01:22:15] or I think of it as adding an auxiliary loss  function that's smoothing out the prediction
[01:22:22] task to also always be consistent  with how the brain represents it.
[01:22:26] It might help you with things like  adversarial examples, for example.
[01:22:30] But what exactly are you predicting? You're predicting the internal state of the brain?
[01:22:32] Yes. So in addition to predicting the label,  a vector of labels like yes cat, not dog, yes,
[01:22:39] not boat, one-hot vector or whatever of yes, it's  cat, instead of these gazillion other categories,
[01:22:46] let's say in this simple example. You're also predicting a vector which
[01:22:49] is all these brain signal measurements. So Gwern, anyway, had this long-ago blog
[01:22:55] post of like, "Oh, this is an intermediate thing. We talk about whole brain emulation, we talk about
[01:22:59] AGI, we talk about brain-computer interface. We should also be talking about this
[01:23:06] brain-data-augmented thing that's trained  on all your behavior, but is also trained on
[01:23:12] predicting some of your neural patterns." And you're saying the Learning System is
[01:23:16] already doing this through the Steering System? Yeah, and our brain, our learning system also has
[01:23:19] to predict the Steering Subsystem as an auxiliary  task. That helps the Steering Subsystem. Now,
[01:23:24] the Steering Subsystem can access that predictor  and build a cool reward function using it.
[01:23:29] Separately, you're on the board of Lean,  which is this formal math language that
[01:23:39] mathematicians use to prove theorems and so forth. Obviously there's a bunch of conversation right
[01:23:44] now about AI automating math. What's your take? Well, I think that there are parts of math that it
[01:23:52] seems like it's pretty well on track to automate. First of all, Lean was developed for a number of
[01:24:06] years at Microsoft and other places. It has become one of the Convergent
[01:24:09] Focused Research Organizations to kind of  drive more engineering and focus onto it.
[01:24:13] So Lean is this programming language where instead  of expressing your math proof on pen and paper,
[01:24:22] you express it in this programming language Lean. And then at the end, if you do that that way,
[01:24:27] it is a verifiable language so that you can  click "verify" and Lean will tell you whether
[01:24:33] the conclusions of your proof actually follow  perfectly from your assumptions of your proof.
[01:24:38] So it checks whether the proof  is correct automatically.
[01:24:43] By itself, this is useful for mathematicians  collaborating and stuff like that.
[01:24:46] If I'm some amateur mathematician  and I want to add to a proof,
[01:24:49] Terry Tao is not going to just believe my result. But if Lean says it's correct, it's just correct.
[01:24:56] So it makes it easy for collaboration to happen,  but it also makes it easy for correctness of
[01:25:03] proofs to be an RL signal in very much RLVR. Formalized math proofing—so formal means
[01:25:12] it's expressed in something like Lean and  verifiable—is now mechanically verifiable.
[01:25:19] That becomes a perfect RLVR task. I think that that is going to just
[01:25:28] keep working, it seems like there is at least one  billion-dollar valuation company, Harmonic, based
[01:25:34] on this. AlphaProof is based on this. A couple  other emerging really interesting companies.
[01:25:42] I think that this problem of RLVRing the  crap out of math proving is going to work
[01:25:50] and we will be able to have things that search  for proofs and find them in the same way that
[01:25:59] we have AlphaGo or what have you that can  search for ways of playing the game of Go.
[01:26:04] With that verifiable signal, it works. So does  this solve math? There is still the part that has
[01:26:10] to do with conjecturing new interesting ideas. There's still the conceptual organization of
[01:26:14] math of what is interesting. How do you come up with new
[01:26:17] theorem statements in the first place? Or even the very high-level breakdown of
[01:26:23] what strategies you use to do proofs. I think this will shift the burden of
[01:26:29] that so that humans don't have to do  a lot of the mechanical parts of math.
[01:26:35] Validating lemmas and proofs and checking if  the statement of this in this paper is exactly
[01:26:39] the same as that paper and stuff like that. That  will just work. If you really think we're going
[01:26:45] to get all these things we've been talking about,  real AGI would also be able to make conjectures.
[01:26:50] Bengio has a paper, more like a theoretical paper. There are probably a bunch of other
[01:26:53] papers emerging about this. Is there a loss function for
[01:26:57] good explanations or good conjectures? That's a  pretty profound question. A really interesting
[01:27:04] math proof or statement might be one that  compresses lots of information and has lots
[01:27:10] of implications for lots of other theorems. Otherwise you would have to prove those
[01:27:14] theorems using long complex passive inference. Here, if you have this theorem, this theorem is
[01:27:18] correct, and you have short passive  inference to all the other ones.
[01:27:20] And it's a short compact statement. So it's like a powerful explanation
[01:27:23] that explains all the rest of math. And part of what math is doing is making these
[01:27:27] compact things that explain the other things. It's like the Kolmogorov complexity
[01:27:31] of this statement or something. Yeah, of generating all the other statements,
[01:27:33] given that you know this one or stuff like that. Or if you add this, how does it affect the
[01:27:37] complexity of the rest of the network of proofs? So can you make a loss function that adds,
[01:27:42] "Oh, I want this proof to be a  really highly powerful proof"?
[01:27:46] I think some people are trying to work on that. So maybe you can automate the creativity part.
[01:27:52] If you had true AGI, it would  do everything a human can do.
[01:27:55] So it would also do the things that  the creative mathematicians do.
[01:27:57] But barring that, I think just RLVRing the crap  out of proofs, I think that's going to be just
[01:28:05] a really useful tool for mathematicians. It's going to accelerate math a lot and
[01:28:08] change it a lot, but not necessarily  immediately change everything about it.
[01:28:14] Will we get mechanical proof of the Riemann  hypothesis or something like that, or things like
[01:28:19] that? Maybe, I don't know. I don't know enough  details of how hard these things are to search
[01:28:25] for, and I'm not sure anyone can fully predict  that, just as we couldn't exactly predict when Go
[01:28:29] would be solved or something like that. I think it's going to have lots
[01:28:34] of really cool applied applications. So one of the things you want to do is you want to
[01:28:40] have provably stable, secure, unhackable software. So you can write math proofs about software and
[01:28:50] say, "This code, not only does it pass these unit  tests, but I can mathematically prove that there's
[01:28:55] no way to hack it in these ways, or no way to mess  with the memory", or these types of things that
[01:28:59] hackers use, or it has these properties. You can use the same Lean and same proof
[01:29:08] to do formally verified software. I think that's going to be a really
[01:29:10] powerful piece of cybersecurity that's relevant  for all sorts of other AI hacking the world stuff.
[01:29:18] And if you can prove the Riemann hypothesis,  you're also going to be able to prove insanely
[01:29:24] complex things about very complex software. And then you'll be able to ask the LLM,
[01:29:27] "Synthesize me a software  that I can prove is correct."
[01:29:33] Why hasn't provable programming  language taken off as a result of LLMs?
[01:29:41] I think it's starting to. One challenge—we are  actually incubating a potential Focused Research
[01:29:48] Organization on this—is the specification problem. So mathematicians know what interesting theorems
[01:29:53] they want to formalize. Let's say I have some code
[01:29:57] that is involved in running the power grid or  something and it has some security properties,
[01:30:02] well what is the formal spec of those properties? The power grid engineers just made this thing,
[01:30:09] but they don't necessarily know how  to lift the formal spec from that.
[01:30:13] And it's not necessarily easy to come up with the  spec that is the spec that you want for your code.
[01:30:17] People aren't used to coming up with formal  specs and there are not a lot of tools for it.
[01:30:21] So you also have this user interface  plus AI problem of what security
[01:30:25] specs should I be specifying? Is this the spec that I wanted?
[01:30:29] So there's a spec problem and it's  just been really complex and hard.
[01:30:34] But it's only just in the  last very short time that
[01:30:39] the LLMs are able to generate verifiable proofs  of things that are useful to mathematicians,
[01:30:48] starting to be able to do some amount of that  for software verification, hardware verification.
[01:30:52] But I think if you project the  trends over the next couple years,
[01:30:57] it's possible that it just flips the tide. Formal methods, this whole field of formal
[01:31:01] methods or formal verification, provable software. It’s this weird almost backwater of the more
[01:31:08] theoretical part of programming languages  and stuff, very academically flavored often.
[01:31:14] Although there was this DARPA program  that made a provably secure quadcopter
[01:31:19] helicopter and stuff like that. Secure against… What is the
[01:31:22] property that is exactly proved? Not for that particular project,
[01:31:27] but just in general. Because obviously things
[01:31:32] malfunction for all kinds of reasons. You could say that what's going on in this
[01:31:37] part of the memory over here, which is supposed  to be the part the user can access, can't in any
[01:31:42] way affect what's going on in the memory over  here or something like that. Things like that.
[01:31:50] So there's two questions.  One is how useful is this?
[01:31:56] Two is, how satisfying, as a  mathematician, would it be?
[01:32:05] The fact that there's this application towards  proving that software has certain properties
[01:32:10] or hardware has certain properties, if that  works, that would obviously be very useful.
[01:32:14] But from a pure… Are we going  to figure out mathematics?
[01:32:20] Is your sense that there's something about finding  that one construction cross-maps to another
[01:32:28] construction in a different domain, or finding  that, "Oh, this lemma, if you redefine this term,
[01:32:38] it still satisfies what I meant by this term. But a counterexample that previously knocked
[01:32:44] it down no longer applies." That kind of dialectical thing
[01:32:47] that happens in mathematics. Will the software replace that?
[01:32:50] Yeah. How much of the value of this sort of pure  mathematics just comes from actually just coming
[01:32:55] up with entirely new ways of thinking  about a problem, mapping it to a totally
[01:33:00] different representation? Do we have examples? I don't know. I think of it maybe a little
[01:33:05] bit like when everybody had to write  assembly code or something like that.
[01:33:11] The amount of fun cool startups that got  created was just a lot less or something.
[01:33:16] Fewer people could do it, progress was more  grinding and slow and lonely and so on.
[01:33:23] You had more false failures because you  didn't get something about the assembly
[01:33:26] code, rather than the essential  thing of was your concept right.
[01:33:31] Harder to collaborate and stuff like that. And so I think it will be really good.
[01:33:38] There is some worry that by not learning to  do the mechanical parts of the proofs that
[01:33:42] you fail to generate the intuitions that inform  the more conceptual parts, the creative part.
[01:33:46] It’s the same with assembly. Right. So at what point is that applying?
[01:33:51] With vibe coding, are people not learning  computer science or actually are they vibe
[01:33:56] coding and they're also simultaneously  looking at the LLM that's explaining
[01:33:59] these abstract computer science concepts to  them and it's all just all happening faster?
[01:34:02] Their feedback loop is faster and they're learning  way more abstract computer science and algorithm
[01:34:06] stuff because they're vibe coding. I don't know, it's not obvious.
[01:34:10] That might be something about the user interface  and the human infrastructure around it.
[01:34:15] But I guess there's some worry that people don't  learn the mechanics and therefore don't build
[01:34:20] the grounded intuitions or something. But my hunch is it's super positive.
[01:34:25] Exactly, on net, how useful that will be  or how much overall math breakthroughs,
[01:34:29] or math breakthroughs even that we care about,  will happen? I don't know. One other thing that
[01:34:34] I think is cool is the accessibility question. Okay, that sounds a little bit corny.
[01:34:39] Okay, yeah, more people  can do math, but who cares?
[01:34:42] But I think there's lots of people  that could have interesting ideas.
[01:34:45] Like maybe the quantum theory  of gravity or something.
[01:34:51] Yeah, one of us will come up  with the quantum theory of
[01:34:53] gravity instead of a card-carrying physicist. In the same way that Steve Byrnes is reading
[01:34:58] the neuroscience literature and he hasn't  been in the neuroscience lab that much.
[01:35:02] But he's able to synthesize across the  neuroscience literature and be like, "Oh,
[01:35:04] Learning Subsystem, Steering Subsystem.  Does this all make sense?" He's an
[01:35:09] outsider neuroscientist in some ways. Can you have outsider string theorists
[01:35:14] or something, because the math is  just done for them by the computer?
[01:35:18] And does that lead to more innovation  in string theory? Maybe yes.
[01:35:22] Interesting. Okay, so if this approach works and  you're right that LLMs are not the final paradigm,
[01:35:29] and suppose it takes at least 10 years  to get the final paradigm in that world.
[01:35:33] There's this fun sci-fi premise where you  have… Terence Tao today had a tweet where
[01:35:39] he's like, "These models are like automated  cleverness but not automated intelligence."
[01:35:44] And you can quibble with the definitions there. But if you have automated cleverness and you have
[01:35:50] some way of filtering—which if you can formalize  and prove things that the LLMs are saying you
[01:36:02] could do—then you could have this situation  where quantity has a quality all of its own.
[01:36:07] So what are the domains of the world which could  be put in this provable symbolic representation?
[01:36:16] So in the world where AGI is super far away,  maybe it makes sense to literally turn everything
[01:36:20] the LLMs ever do, or almost everything  they do, into super provable statements.
[01:36:25] So LLMs can actually build on top of each other  because everything they do is super provable.
[01:36:31] Maybe this is just necessary because you have  billions of intelligences running around.
[01:36:34] Even if they are super intelligent, the only way  the future AGI civilization can collaborate with
[01:36:38] each other is if they can prove each step. They're just brute force churning out…
[01:36:44] This is what the Jupiter brains are doing. It's a universal language, it's provable.
[01:36:48] It's also provable from the perspective of,  "Are you trying to exploit me or are you
[01:36:51] sending me some message that's trying  to hack into my brain effectively?"
[01:36:56] Are you trying to socially influence me? Are you actually just sending me just the
[01:37:00] information that I need and no more for this? So davidad, who's this program director at ARIA
[01:37:06] now in the UK, he has this whole  design of an ARPA-style program,
[01:37:12] a sort of safeguarded AI that very heavily  leverages provable safety properties.
[01:37:17] Can you apply proofs to…  Can you have a world model?
[01:37:20] But that world model is actually not  specified just in neuron activations,
[01:37:23] but it's specified in equations. Those might be very complex equations,
[01:37:28] but if you can just get insanely good at just  auto-proving these things with cleverness,
[01:37:33] auto-cleverness… Can you have explicitly  interpretable world models as opposed to
[01:37:40] neural net world models and move back basically  to symbolic methods just because you can just
[01:37:45] have insane amount of ability to prove things? Yeah, I mean that's an interesting vision.
[01:37:50] I don't know in the next 10 years whether that  will be the vision that plays out, but I think
[01:37:54] it's really interesting to think about. Even for math, I mean, Terence Tao is
[01:38:00] doing some amount of stuff where it's not about  whether you can prove the individual theorems.
[01:38:04] It's like let's prove all the theorems en  masse and then let's study the properties
[01:38:08] of the aggregate set of proved theorems. Which are the ones that got proved
[01:38:12] and which are the ones that didn't? Okay, well that's the landscape of all the
[01:38:15] theorems instead of one theorem at a time. Speaking of symbolic representations,
[01:38:20] one question I was meaning to ask you is,  how does the brain represent the world model?
[01:38:25] Obviously nets out in neurons, but  I don't mean extremely functionally.
[01:38:29] I mean conceptually, is it in something  that's analogous to the hidden state of
[01:38:34] a neural network or is it something  that's closer to a symbolic language?
[01:38:39] We don't know. There's some  amount of study of this.
[01:38:42] There's these things like face patch neurons  that represent certain parts of the face that
[01:38:47] geometrically combine in interesting ways.  That's with geometry and vision. Is that
[01:38:51] true for other more abstract things? There's this idea of cognitive maps.
[01:38:55] A lot of the stuff that a rodent  hippocampus has to learn is place cells and,
[01:39:00] where is the rodent going to go next and  is it going to get a reward there? It's
[01:39:05] very geometric. And do we organize concepts  with an abstract version of a spatial map?
[01:39:13] There's some questions of can  we do true symbolic operations?
[01:39:16] Can I have a register in my brain that copies a  variable to another register regardless of what
[01:39:21] the content of that variable is? That's this  variable binding problem. Basically I don’t
[01:39:26] know if we have that machinery or is it more  like cost functions and architectures that
[01:39:32] make some of that approximately emerge, but  maybe it would also emerge in a neural net?
[01:39:36] There's a bunch of interesting neuroscience  research trying to study this, what the
[01:39:40] representations look like. But what’s your hunch?
[01:39:42] Yeah, my hunch is that it's going to be a huge  mess and we should look at the architecture,
[01:39:46] the loss functions, and the learning rules. I don't expect it to be pretty in there.
[01:39:51] Which is that it is not a  symbolic language type thing?
[01:39:53] Yeah, probably it's not that symbolic. But other people think very differently.
[01:40:00] Another random question speaking of binding, what  is up with feeling like there's an experience?
[01:40:08] All the parts of your brain which are modeling  very different things, have different drives,
[01:40:12] and at least presumably feel like there's  an experience happening right now.
[01:40:16] Also that across time you feel like… Yeah, I'm pretty much at a loss on this one.
[01:40:25] I don't know. Max Hodak has been  giving talks about this recently.
[01:40:31] He's another really hardcore neuroscience  person, neurotechnology person.
[01:40:38] The thing I mentioned with Doris maybe also sounds  like it might have some touching on this question.
[01:40:44] But yeah, I don't think anybody has any idea. It might even involve new physics.
[01:40:50] Here’s another question which  might not have an answer yet.
[01:40:59] Continual learning, is that the product  of something extremely fundamental at the
[01:41:07] level of even the learning algorithm? You could say, "Look, at least the way
[01:41:10] we do backprop in neural networks is that  you freeze the weight, there's a training
[01:41:13] period and you freeze the weights. So you just need this active inference
[01:41:19] or some other learning rule in  order to do continual learning."
[01:41:22] Or do you think it's more a matter of architecture  and how memory is exactly stored and what kind of
[01:41:28] associative memory you have basically? So continual learning… I don't know.
[01:41:38] At the architectural level, there's probably  some interesting stuff that the hippocampus
[01:41:41] is doing. People have long thought this.  What kinds of sequences is it storing?
[01:41:51] How is it organizing, representing that? How is it replaying it back? What is it
[01:41:55] replaying back? How exactly does  that memory consolidation work?
[01:42:01] Is it training the cortex using  replays or memories from the
[01:42:06] hippocampus or something like that? There's probably some of that stuff.
[01:42:09] There might be multiple timescales of  plasticity or clever learning rules
[01:42:14] that can simultaneously be storing short-term  information and also doing backprop with it.
[01:42:21] Neurons may be doing a couple things:  some fast weight plasticity and some
[01:42:24] slower plasticity at the same time, or  synapses that have many states. I mean,
[01:42:28] I don't know. From a neuroscience perspective,  I'm not sure that I've seen something that's super
[01:42:34] clear on what causes continual learning except  maybe to say that this systems consolidation
[01:42:40] idea of hippocampus consolidating cortex. Some people think it is a big piece of this
[01:42:44] and we still don't fully understand the details. Speaking of fast weights, is there something
[01:42:50] in the brain which is the equivalent of  this distinction between parameters and
[01:42:54] activations that we see in neural networks? Specifically in transformers we have this
[01:43:00] idea that some of the activations are the  key and value vectors of previous tokens
[01:43:10] that you build up over time. There's the so-called fast
[01:43:13] weights that whenever you have a new token,  you query them against these activations,
[01:43:20] but you also obviously can't query them against  all the other parameters in the network which
[01:43:23] are part of the actual built-in weights. Is there some such distinction that's analogous?
[01:43:27] I don't know. I mean we definitely  have weights and activations.
[01:43:30] Whether you can use the activations in these  clever ways, different forms of actual attention,
[01:43:37] like attention in the brain… Is that  based on, "I'm trying to pay attention"...
[01:43:42] I think there's probably several different  kinds of actual attention in the brain.
[01:43:46] I want to pay attention to  this area of visual cortex.
[01:43:49] I want to pay attention to the  content in other areas that is
[01:43:54] triggered by the content in this area. Attention that's just based on reflexes
[01:43:59] and stuff like that. So I don't know. There's  not just the cortex, there's also the thalamus.
[01:44:04] The thalamus is also involved in somehow  relaying or gating information. There's
[01:44:08] cortico-cortical connections. There's  also some amount of connection between
[01:44:11] cortical areas that goes through the thalamus. Is it possible that this is doing some sort of
[01:44:16] matching or constraint satisfaction or matching  across keys over here and values over there?
[01:44:25] Is it possible that it can do stuff like that?  Maybe. I don't know. This is all part of the
[01:44:29] architecture of this corticothalamic system. I don't know how transformer-like it is or if
[01:44:36] there's anything analogous to that attention. It’d be interesting to find out.
[01:44:42] We’ve got to give you a billion dollars  so you can come on the podcast again and
[01:44:46] tell me how exactly the brain works. Mostly I just do data collection.
[01:44:49] It's really unbiased data collection so all the  other people can figure out these questions.
[01:44:54] Maybe the final question to go  off on is, what was the most
[01:44:58] interesting thing you learned from the Gap Map? Maybe you want to explain what the Gap Map is.
[01:45:04] In the process of incubating and coming up  with these Focused Research Organizations,
[01:45:10] these nonprofit startup-like moonshots  that we've been getting philanthropists
[01:45:15] and now government agencies to fund,  we talked to a lot of scientists.
[01:45:21] Some of the scientists were just like, "Here's  the next thing my graduate student will do.
[01:45:24] Here's what I find interesting. Exploring  these really interesting hypothesis spaces,
[01:45:28] all the types of things we've been talking about." Some of them were like, "Here's this gap.
[01:45:34] I need this piece of infrastructure. There's no combination of grad students in my lab
[01:45:38] or me loosely collaborating with other labs with  traditional grants that could ever get me that.
[01:45:43] I need to have an organized engineering  team that builds the miniature
[01:45:47] equivalent of the Hubble Space Telescope. If I can build that Hubble Space Telescope,
[01:45:50] then I will unblock all the other researchers in  my field or some path of technological progress in
[01:45:56] the way that the Hubble Space Telescope lifted the  boats and improved the life of every astronomer."
[01:46:01] But it wasn't really an  astronomy discovery in itself.
[01:46:03] It was just that you had to put this giant mirror  in space with a CCD camera and organize all the
[01:46:07] people and engineering and stuff to do that. So some of the things we talked to
[01:46:12] scientists about looked like that. The Gap Map is just a list of a lot of
[01:46:16] those things and we call it a Gap Map. I think it's actually more like a
[01:46:20] fundamental capabilities map. What are all these things,
[01:46:22] like mini Hubble space telescopes? And then we organized that into gaps for
[01:46:29] helping people understand that or search that. What was the most surprising thing you found?
[01:46:36] I think I've talked about this before,  but one thing is just the overall size
[01:46:41] or shape of it or something like that. It's a few hundred fundamental capabilities.
[01:46:47] So if each of these were a deep tech  startup-size project, that's only
[01:46:50] a few billion dollars or something. If each one of those were a Series A,
[01:46:53] that's only… It's not like a trillion dollars to  solve these gaps. It's lower than that. So that's
[01:46:59] one thing. Maybe we assumed that, and that's  what we got. It's not really comprehensive.
[01:47:05] It's really just a way of summarizing a lot  of conversations we've had with scientists.
[01:47:10] I do think that in the aggregate process, things  like Lean are actually surprising because I did
[01:47:15] start from neuroscience and biology and it  was very obvious that there's these -omics.
[01:47:20] We need genomics, but we also need connectomics. We can engineer E. coli, but we also need to
[01:47:26] engineer the other cells. There's somewhat obvious
[01:47:28] parts of biological infrastructure. I did not realize that math proving
[01:47:31] infrastructure was a thing and that  was emergent from trying to do this.
[01:47:37] So I'm looking forward to seeing other  things where it's not actually this hard
[01:47:42] intellectual problem to solve it. It's maybe slightly the equivalent
[01:47:46] of AI researchers just needing GPUs  or something like that and focus and
[01:47:50] really good PyTorch code to start doing this. Which are the fields that do or don't need that?
[01:48:05] So fields that have had gazillions of dollars  of investment, do they still need some of those?
[01:48:10] Do they still have some of those gaps  or is it only more neglected fields?
[01:48:15] We're even finding some interesting  ones in actual astronomy, actual
[01:48:18] telescopes that have not been explored. Maybe because if you're getting above a
[01:48:26] critical mass-size project, then you have to  have a really big project and that's a more
[01:48:29] bureaucratic process with the federal agencies. I guess you just need scale in every single
[01:48:35] domain of science these days. Yeah, I think you need scale in
[01:48:37] many of the domains of science. That does not mean that the
[01:48:40] low-scale work is not important. It does not mean that creativity,
[01:48:44] serendipity, etc., and each student pursuing  a totally different direction or thesis that
[01:48:49] you see in universities is not also really key. But I think some amount of scalable infrastructure
[01:48:57] is missing in essentially every area  of science, even math, which is crazy.
[01:49:01] Because mathematicians I thought just needed  whiteboards, but they actually need Lean.
[01:49:05] They actually need verifiable programming  languages and stuff. I didn't know that.
[01:49:10] Cool. Adam, this is super  fun. Thanks for coming on.
[01:49:11] Thank you so much. My pleasure. Where can people find your stuff?
[01:49:13] Pleasure. The easiest way  now… My adammarblestone.org
[01:49:16] website is currently down, I guess. But convergentresearch.org can link to
[01:49:22] a lot of the stuff we've been doing. And then you have a great blog,
[01:49:24] Longitudinal Science. Longitudinal Science, yes, on WordPress.
[01:49:27] Cool. Thank you so much. Pleasure.
