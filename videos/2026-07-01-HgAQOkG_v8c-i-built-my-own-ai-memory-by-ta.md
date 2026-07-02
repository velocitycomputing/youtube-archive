---
video_id: HgAQOkG_v8c
title: I Built My Own AI Memory by Talking to Claude. It Did 80% Itself.
channel: "AI News & Strategy Daily | Nate B Jones"
url: "https://www.youtube.com/watch?v=HgAQOkG_v8c"
watched_date: 2026-07-01
watched_at: "2026-07-01T12:00:00Z"
watch_count: 1
duration_seconds: 976
source: youtube-history-browser
added_date: 
history_label: Yesterday
history_order: 13
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 98
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The speaker discussed how AI model access is increasingly controlled by governments and companies, leaving users vulnerable when their preferred service gets restricted (Fable, GPT 5.6). The solution is building personal "OpenBrain" systems—memory and skill stacks you own, not rent. The core argument: agents have improved dramatically since February 2026, now understanding intent well enough that Claude and Claude Code can build ~80% of the infrastructure through conversation alone. He warned against agents acting autonomously (sharing an anecdote about an AI accidentally sending an insurance appeal email) and emphasized that users need control over agent scope, actions, and approvals. The technical barriers have dropped five-fold, making it accessible even to non-technical users, while memory ownership remains critical as AI assistants grow more capable and seductive.

**For action:** Pick one recurring pain point you're tired of explaining—weekly planning, insurance appeals, coffee recommendations, family logistics, whatever causes you friction. Write down the preferences and context that should inform how an agent handles it. Point Claude or Claude Code at your requirements and let it help build the memory system and agent workflow; you keep control of accounts, secrets, and approval decisions. Start small, iterate with feedback, and build out memory and skills that stick with you regardless of which AI model you later choose. The water is warm—agents can now guide you through the build without needing you to understand SQL or command-line details.

## Transcript

[00:00:00] You woke up last week to the two best AI
[00:00:02] models on the planet getting locked
[00:00:04] behind a government door and we're all
[00:00:06] standing on the wrong side of it.
[00:00:08] Fable's gone. Chad GBT 5.6 shipped to a
[00:00:11] handful of vetted shops and nobody else.
[00:00:13] If your work runs on whoever's winning
[00:00:15] this month, you learned how fast that
[00:00:17] can change. So, here's the part nobody
[00:00:19] can lock up your memory, your standards,
[00:00:22] and your skills. I want you to think
[00:00:23] about how you can own that. rent the
[00:00:26] intelligence and swap the models out so
[00:00:28] the bands don't matter. By the end of
[00:00:30] this video, you're going to know how to
[00:00:31] build that system and the agent on your
[00:00:33] computer is going to be able to carry
[00:00:35] out all the technical parts for you. I'm
[00:00:37] going to tell you the story of how an AI
[00:00:38] agent beat an insurance company. And
[00:00:40] that's not even the real story. The real
[00:00:42] story is about how the role of memory in
[00:00:45] agents is evolving and the way we build
[00:00:48] agentic systems for ourselves, we don't
[00:00:51] have to wait, is evolving, too. and not
[00:00:53] a perfect assistant for your whole life.
[00:00:55] Just a clear agentic loop with an agent
[00:00:58] that starts from your context, knows
[00:01:00] what you meant, knows what it can do,
[00:01:02] what it can't do, and knows where to
[00:01:04] stop. And by the way, an agent that can
[00:01:06] prove that it did what it did on
[00:01:08] purpose. So, Nikita wrote that his open
[00:01:10] claw quote accidentally started a fight
[00:01:12] with Lemonade insurance because it
[00:01:14] misinterpreted his response. That is
[00:01:16] actually a very bad thing, even if he
[00:01:18] won the fight. Eventually, Lemonade had
[00:01:20] declined a claim involving his best
[00:01:22] friend. The agent found the rejection
[00:01:24] email and offered a draft reply, and
[00:01:26] Nikita didn't want this to happen, so he
[00:01:27] ignored the draft. And then, according
[00:01:29] to Nikita, the agent just sent it for
[00:01:31] him. And after that email, Lemonade
[00:01:32] started reinvestigating the case instead
[00:01:34] of rejecting it immediately. Now, that's
[00:01:36] an incredible story, but I don't want
[00:01:38] you to have that kind of incredible
[00:01:40] story because if an agent will ignore
[00:01:42] you and send stuff anyway, the agent is
[00:01:45] out of policy and very, very risky. Even
[00:01:48] if in this one particular instance,
[00:01:50] Nikita was able to roll the dice and it
[00:01:51] worked out. Now, I get that fighting
[00:01:54] insurance is kind of the dream version
[00:01:55] of personal AI. I love it. I think it's
[00:01:58] a great task. I think it allows you to
[00:02:00] use an agent in ways that make an agent
[00:02:02] work well, right? Agents are good at
[00:02:04] reviewing legal minutia. They're good at
[00:02:06] digging into detail. They're good at
[00:02:08] doing tedious work. All of the stuff you
[00:02:10] would need to file a uh response to a
[00:02:13] denial that would be listened to. So
[00:02:16] that makes sense. The problem is that
[00:02:18] the agent didn't do it with authority.
[00:02:21] That the agent misunderstood that the
[00:02:22] agent had memory issues, policy issues,
[00:02:25] all kinds of things that led to
[00:02:27] problems. What has changed between that
[00:02:31] moment, which was back in January, and
[00:02:33] now in June of 2026. Now, agents have
[00:02:36] gotten much better at acting, and intent
[00:02:39] is one of the central problems of the AI
[00:02:41] age, and we've made huge progress on
[00:02:43] connecting intent and acting. just in
[00:02:45] the last 6 months. When you're chatting
[00:02:47] with the model now, you can communicate
[00:02:50] intent and it will often get it right.
[00:02:53] Right. It will understand that draft a
[00:02:55] response means draft not send. There are
[00:02:58] now things like auto review in codeex
[00:03:01] that make sure that it will not send if
[00:03:03] you say draft. Now, back in February
[00:03:05] when I first started talking about
[00:03:07] Agentic Systems, the key problem was
[00:03:10] kind of what I just described in that
[00:03:11] story. AI forgets you. It doesn't
[00:03:14] listen. doesn't pay attention. So often
[00:03:16] chats would start cold. You had to
[00:03:18] explain your preferences again and your
[00:03:20] memory didn't belong to you. Now that
[00:03:22] world is already changing under our
[00:03:24] feet. And I'm not the only one who
[00:03:27] recognized that problem. There are many
[00:03:28] alternatives to open brain out there,
[00:03:30] which is great. And agents critically
[00:03:32] are no longer just acting in short form.
[00:03:36] They're taking much longer actions with
[00:03:38] much larger consequences. And so memory
[00:03:41] has had to evolve, too. I've evolved the
[00:03:43] open brain system to include uh some of
[00:03:46] Andre Carpathy's work around wiki style
[00:03:49] connections and you now have that in
[00:03:50] open brain as part of the framework.
[00:03:52] I've added other pieces also open skills
[00:03:55] and most recently open engine which
[00:03:58] connects everything to an Asianto Asia
[00:04:00] task interaction framework. All of that
[00:04:03] is designed to get you from a world
[00:04:06] where agents are a thing out there to a
[00:04:09] world where agents actually serve you.
[00:04:11] But the problem remains the build. And I
[00:04:14] have had to I have personally
[00:04:16] troubleshot people who are struggling
[00:04:17] with building these systems. And I have
[00:04:19] realized that when I say something is
[00:04:21] easy, it doesn't always feel easy to
[00:04:23] you. And I want to call out one of the
[00:04:26] biggest differences between the moment
[00:04:29] that I just described with the insurance
[00:04:30] story with that agent. The moment even
[00:04:32] that I described OpenBrain back in
[00:04:34] February and today, June 2026. And that
[00:04:37] difference is that agents are so good at
[00:04:40] following intent, they now actually just
[00:04:44] build it for you. I'm estimating, and
[00:04:46] I've worked with other folks on this,
[00:04:48] you can build 80% of the open brain
[00:04:51] stack just by talking to your agent very
[00:04:53] simply, in a way that you couldn't in
[00:04:55] February. And I think that that's worth
[00:04:56] calling out because that's a tremendous
[00:04:58] jump in just a couple of months.
[00:04:59] Ultimately, the reason why this stack
[00:05:02] matters is because the agents can act on
[00:05:05] the wrong version of your intent very
[00:05:07] quickly. And frontier model companies
[00:05:10] owning the relationship between your
[00:05:12] intent and intelligence and action is
[00:05:14] really risky for you long term. Frankly,
[00:05:16] we've seen that just in the last few
[00:05:19] days with GLM 5.2 coming out from an
[00:05:22] open source perspective while Fable and
[00:05:24] Chad GPT 5.6 are all banned. I mean long
[00:05:28] term we're in a position where we as
[00:05:30] consumers have to hedge our bets. We
[00:05:32] have to have a tool stack that we own.
[00:05:34] And you may not realize this but you
[00:05:36] already have tools like claud and codeex
[00:05:38] that can essentially build most of this
[00:05:40] stack for you. You don't actually even
[00:05:42] need to get to open claw although if you
[00:05:44] have it that's great. It will plug right
[00:05:45] into the open engine format. So will
[00:05:47] Hermes. You can start wherever you are
[00:05:49] on one repeated part of your life
[00:05:51] rework. a client followup, a frequent
[00:05:53] traveler problem that you face, a weekly
[00:05:56] planning pass, uh or maybe it's the
[00:05:58] insurance appeal, right? Uh a shared
[00:05:59] marketing brain, whatever it is that you
[00:06:02] get stuck on where your intent is
[00:06:04] something you have to repeat all the
[00:06:06] time, then go there. That's that's where
[00:06:10] you feel pain. That's where the agent
[00:06:12] should help you. And then let your
[00:06:15] agent, let your claude, let your codeex
[00:06:17] help you build, right? Let it help you
[00:06:19] build open brain which carries memories
[00:06:21] and open skills which gives you methods
[00:06:24] to actually get work done that are
[00:06:26] suited to you and transport easily
[00:06:28] between claude between uh open AI's
[00:06:31] agents between Gemini etc etc or any
[00:06:35] open source model you choose and then
[00:06:37] agents can build the work layer for you
[00:06:39] too open engine is just a way to
[00:06:41] orchestrate work across multiple agents
[00:06:43] so that if you want to get big work done
[00:06:45] across claude across codecs across Chad
[00:06:47] GPT you name it Right across OpenC Claw,
[00:06:50] you can get it all done in one thing.
[00:06:51] People have built travel planning memory
[00:06:53] with this. People have built shared
[00:06:54] marketing brains in the community.
[00:06:56] People have built cross tool context
[00:06:58] between Claude and Chad GPT and Kimmy.
[00:07:00] And they've built agents that can read
[00:07:02] tickets into a tracker and hand work to
[00:07:04] another agent. I want more intentional
[00:07:07] agent stories and fewer accidental ones.
[00:07:09] The the insurance example. I want people
[00:07:12] who intended to fight insurance. And
[00:07:14] what? Because the agents are getting
[00:07:15] good enough to move the world. They are
[00:07:16] the lever. Archimedes lever that moves
[00:07:19] the world. The question is whether they
[00:07:20] are moving from your memory, your
[00:07:22] standards and your intent or from
[00:07:24] whatever default memory stack the next
[00:07:26] agent company is giving to you. And the
[00:07:28] reason this is worth doing now is that
[00:07:30] the build barrier has dropped. A few
[00:07:33] months ago, even if you believed in the
[00:07:35] open brain concept, I get that it was
[00:07:37] hard, right? The database, the setup,
[00:07:39] the SQL, the configs, the command line
[00:07:41] steps. I helped troubleshoot people
[00:07:42] through that. I've done it myself. And
[00:07:44] it felt like a technical project. It
[00:07:47] doesn't feel like a technical project
[00:07:49] anymore when Claude and Codeex and tools
[00:07:51] like them can walk you through that
[00:07:53] build almost by themselves. Now, you can
[00:07:56] still own the human parts. You can say
[00:07:58] these are the accounts I want to give
[00:07:59] you access to. These are my permissions.
[00:08:01] This is the final approval. These are my
[00:08:03] settings. Uh stuff that involves trust
[00:08:05] belongs to you. But the technical middle
[00:08:07] has gotten so much easier. It is worth
[00:08:12] naming again. It is worth calling out
[00:08:14] because if a repeated part of your life
[00:08:16] can get sorted with an agent and now you
[00:08:19] don't even have to face the technical
[00:08:21] build challenge in the same way that's a
[00:08:24] big deal. So I want to make this real
[00:08:26] with a coffee store. I'm a coffee guy. I
[00:08:28] used to run a coffee company and I have
[00:08:30] colleagues in my Slack co-builders with
[00:08:33] me who are also coffee people and both
[00:08:36] of us stumbled onto the same thing. So
[00:08:38] instead of having a generic Google map
[00:08:40] search for cafes, both of us figured out
[00:08:42] that an agent backed by our preferences
[00:08:45] in open brain could go and plan an
[00:08:48] entire morning for us much more
[00:08:50] effectively because the agent knew our
[00:08:52] preferences. And by the way, we don't
[00:08:53] have the same coffee preferences. We
[00:08:54] live in different parts of the country,
[00:08:55] etc. But we both figured this out and I
[00:08:58] was able to use it when I was in Japan
[00:09:00] to do some coffee hunting that I
[00:09:02] wouldn't have been able to do otherwise.
[00:09:03] And you can easily input your coffee
[00:09:05] preferences and get much more customized
[00:09:07] results as well. That's a tiny tiny
[00:09:10] little example. You might be like,
[00:09:11] "Building an agent for coffee. I would
[00:09:13] never do that." No. Pick the pain that
[00:09:15] works for you. I don't care if it's
[00:09:17] coffee. I care that the pain is better
[00:09:19] because you have an agent that
[00:09:21] understands the tradeoffs, that
[00:09:23] understands the the decisions that are
[00:09:25] right for you because your memory is
[00:09:27] yours. If you want the world where your
[00:09:31] agent will fight insurance for you and
[00:09:34] monitor your email for you, that world
[00:09:37] runs through your memory, your skills,
[00:09:41] your ability to orchestrate agents. It
[00:09:43] should not run through some company that
[00:09:46] gets stuck in regulation trying to
[00:09:48] figure out what's good for you. Now, you
[00:09:50] can use intelligence from whatever
[00:09:52] source you want, right? You can use it
[00:09:53] from OpenAI or Anthropic or from Kimmy
[00:09:56] K2 or Quen or whatever, but your
[00:09:59] memories are yours. Your skills are
[00:10:00] yours and they should stay that way.
[00:10:03] It's going to be more like the agent
[00:10:04] knows my preferences. The agent knows
[00:10:06] that I do want to battle every single
[00:10:08] insurance claim. The agent knows how to
[00:10:10] go about doing the research to do that
[00:10:11] well, and I get to approve the drafts,
[00:10:13] by the way. It doesn't just get sent
[00:10:14] without me. We need control over our
[00:10:18] agents. We need agents that belong to
[00:10:21] us. agents that have memory that we
[00:10:24] understand, agents that have a scope of
[00:10:27] action that we approve of. That's why my
[00:10:29] open engine approach emphasizes that you
[00:10:31] should be able to see when an agent
[00:10:33] picks up a task, right? A ticketing
[00:10:34] system is actually just a good primitive
[00:10:36] for that because you can see, oh, it
[00:10:38] picked up the task. Oh, it wrote
[00:10:39] something. It's not hidden away in chain
[00:10:41] of thought, right? It's not like erased
[00:10:43] in the middle of a chat that I can't
[00:10:44] find. Have you ever tried to find the
[00:10:46] chats in chat GPT or in cloud and been
[00:10:48] like, oh my gosh, I searched for that
[00:10:49] keyword. It's not there. They need to
[00:10:51] fix search, but you also need to not
[00:10:53] depend on that to get agentic work done.
[00:10:56] You need to have an external scaffolding
[00:10:59] that lets you be confident that you can
[00:11:02] get your work done regardless. But we
[00:11:04] can control where our memories live. We
[00:11:06] can control our skills. We can control
[00:11:08] how work gets done and ensures that it
[00:11:10] has a a status and an approval layer
[00:11:13] where relevant and agent handoffs that
[00:11:15] we can read and escalations to humans
[00:11:17] that make sense. So jump in. The water's
[00:11:21] warm and the ability to build is like
[00:11:24] 1/5ifth or less technical than it was
[00:11:28] back in February. I I hope that reminds
[00:11:30] you how quickly this is changing. And I
[00:11:32] hope that reminds you and encourages you
[00:11:34] that you too can do this. Even though
[00:11:36] this has technical primitives underneath
[00:11:39] like a SQL database, you can do it
[00:11:42] without really digging in and
[00:11:43] understanding the details of that
[00:11:45] because the agents are good enough to
[00:11:46] explain what it means in practice for
[00:11:49] you. And I think that's one of the
[00:11:51] things I really struggle with with where
[00:11:53] we are in the agentic revolution because
[00:11:55] to be honest with you, Claude and Codeex
[00:11:58] are very codshaped today and most of the
[00:12:02] world is not code shaped. most of the
[00:12:04] world is non-technically skilled and
[00:12:07] that's just as legitimate a skill set
[00:12:09] and so we need to find ways to work with
[00:12:13] our agents that feel safe if we're
[00:12:16] non-technical and a lot of the project
[00:12:18] that I've been working on with open
[00:12:20] brain over the last 5 months is
[00:12:21] basically making it easier and easier
[00:12:23] and easier for you if you are
[00:12:24] non-technical to use agents to work with
[00:12:27] that GitHub repo to work with that code
[00:12:30] so it's not scary so it's not
[00:12:32] non-transparent so So it doesn't do
[00:12:34] things you don't want it to do. And so
[00:12:35] you actually get your work done and
[00:12:37] actually do things like weekly planning
[00:12:38] and family logistics and the work blocks
[00:12:40] that you want to protect and you feed
[00:12:42] the projects that keep getting starved
[00:12:43] or whatever it is that you are building
[00:12:45] this agent for. Giving your agent memory
[00:12:48] and skills and a clear framework to do
[00:12:50] stuff in in order to get to that world.
[00:12:53] And it has never ever ever been easier.
[00:12:56] It's never been easier. So if this is
[00:12:57] you, if you're like h I'm almost there.
[00:13:00] I want to build. This is your
[00:13:02] invitation. I am waving the green flag
[00:13:05] here. I am telling you that agents can
[00:13:07] get it done. The agents can help you
[00:13:10] build agents. And that's one of the
[00:13:12] biggest differences between now and when
[00:13:14] I made my original open brain tutorial,
[00:13:16] which like 200,000 of you have watched,
[00:13:18] which is amazing. And I love that. It's
[00:13:20] easier now. It's like five times easier
[00:13:22] now. I know 200,000 of you haven't built
[00:13:24] this and I think it's worth building.
[00:13:26] So, you own your memory. And like these
[00:13:28] guys who are trying to get approval from
[00:13:30] Washington for this and that don't own
[00:13:32] your memory. You should keep your
[00:13:33] judgment. The agent can carry the
[00:13:35] technical steps to get this work done
[00:13:37] for you now and it can still defer to
[00:13:39] you about what matters. Which things you
[00:13:41] want to remember? Which things are
[00:13:42] skills that you want to say this is my
[00:13:44] domain expertise. I want to preserve it.
[00:13:45] I don't want claude to own that skill. I
[00:13:47] don't want OpenAI to own that skill. I
[00:13:48] want to own that skill. The assistant
[00:13:50] race is just going to get more seductive
[00:13:52] from here. The demos will get better.
[00:13:54] The phone integrations will get
[00:13:56] smoother. the voices will get warmer.
[00:13:58] Every one of those improvements is
[00:14:00] designed to get your attention. It's
[00:14:03] designed to get us to put our memory and
[00:14:05] our focus and our work into these apps.
[00:14:10] The company that holds the memory holds
[00:14:12] the part that makes the assistant feel
[00:14:14] personal. I would rather build that part
[00:14:16] myself. And that is why I keep coming
[00:14:19] back to this. Intelligence is not a
[00:14:21] personal thing. Memory is personal. And
[00:14:24] you know, in February, a lot of that was
[00:14:25] about getting your agents to remember
[00:14:27] you. And now it really is about giving
[00:14:29] your agents a platform to jump from and
[00:14:31] act from on your behalf because they're
[00:14:32] so much more powerful. Pick a recurring
[00:14:35] situation you're tired of explaining.
[00:14:37] Write down the context that would change
[00:14:38] that answer. Point your agent at the
[00:14:41] guide, which I will link to. Keep
[00:14:43] control of accounts and secrets and
[00:14:45] permissions and approval at your level.
[00:14:48] And then tell it to run and practice,
[00:14:50] right? And give it feedback. Say, "No,
[00:14:52] that was wrong. Change this. No, that
[00:14:53] was wrong. Change this. Agents take a
[00:14:55] while to break in. Once you start to get
[00:14:57] into the rhythm of using them, it gets
[00:14:59] easier and easier and easier and easier.
[00:15:01] And now, even that first step, even
[00:15:03] getting the shoe so you can wear it,
[00:15:05] agents can help with that in a way they
[00:15:06] couldn't back in February. And that is
[00:15:08] the key. That is the key I want you to
[00:15:10] take away. And the prize for unlocking
[00:15:13] that door, the prize is just owning the
[00:15:14] context. Every future agent will need
[00:15:18] before it even arrives. So when an agent
[00:15:20] comes, you can just plug it right in.
[00:15:22] Right? I want you to take advantage of
[00:15:23] the latest and greatest AI agents that
[00:15:25] you want to take advantage of. I don't
[00:15:26] want to pick a favorite. You pick. But
[00:15:28] you own the memory and you make sure
[00:15:30] that you rent the intelligence. So the
[00:15:32] intelligence is something you can apply
[00:15:34] to your memory, your skills, your
[00:15:36] orchestration layer, infrastructure that
[00:15:39] lets the agent work for you. Pick the
[00:15:42] part of your life that you want to
[00:15:43] change and let an agent change it for
[00:15:45] you. I I'm not kidding. You can actually
[00:15:48] do it. I if nothing else, if you know
[00:15:50] someone who has a really big painoint
[00:15:52] and maybe it's agent shaped or you know
[00:15:54] it's agent shaped and you're a builder,
[00:15:55] go tell them that. Go say, "Hey, this is
[00:15:58] not that hard. An agent can help you
[00:15:59] build this." We need positive examples.
[00:16:02] In fact, if you have positive examples,
[00:16:04] if you're an open rate builder, if you
[00:16:05] you built on something else, maybe you
[00:16:06] built on Gbrain, I don't care. Put
[00:16:08] positive examples of why an agent made a
[00:16:10] difference in your life down here. I
[00:16:12] would like to see them. I want more
[00:16:14] people to see positive examples of
[00:16:15] agents
