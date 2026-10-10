---
video_id: GrNbuWWJYiI
title: "You Can Learn AI Agent Harness & Loop Engineering In 19 Min | LLM Ops, Eval, Tracing, RAG"
channel: Sean‘s AI Stories and AutoManus
url: "https://www.youtube.com/watch?v=GrNbuWWJYiI"
watched_date: 2026-07-03
watched_at: "2026-07-03T12:00:00Z"
watch_count: 1
duration_seconds: 1200
source: youtube-history-browser
added_date: 
history_label: Friday
history_order: 65
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 120
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: [primary-source-video]
proposed_entities: []
status: new
routed_to: null
---

## Summary

The transcript covers the architecture of AI agent systems built on three components: an **agent harness** (a control framework using databases to manage procedural/semantic/episodic memories), **loop engineering** (defining guardrails for when the agent stops making tool calls and returns a response), and **LLMOps** (a feedback cycle that traces agent runs, evaluates performance against metrics, diagnoses failures, and iterates on system prompts and model configurations). The core metaphor is harnessing an LLM like controlling a powerful horse—the model knows everything but not the user's context or intent, so the harness (memory retrieval, tool-calling loops, and end conditions) channels that power toward the right task. A tracing system logs every decision, retrieval, and tool call; evaluation scores whether results are correct; diagnostics identify bottlenecks (slow tool calls, oversized context, unnecessary retrievals); and fixes flow back to improve the next run.

To implement this: set up a database-backed memory system that consolidates high-volume conversations into semantic facts (e.g., after every 2,000 customer interactions in e-commerce); define explicit guardrails so agents know when a task is complete (task checklist, user confirmation, or notification triggers); instrument your runs with a tracing tool (LangFuse or LangSmith) to capture latency, token usage, and tool-call chains; define evaluation rules (deterministic metrics like "did the calendar invite send?" or LLM-as-judge scoring); and create a dashboard to diagnose failures—if latency spikes, check whether memory retrieval is the bottleneck or whether the agent is over-using RAG for questions the base model already answers. Close the loop by feeding diagnosed fixes back into updated prompts and model configs. For blocking issues (like Claude Code permission prompts), add hooks or loops to notify you immediately rather than leaving the agent stuck for hours.

## Transcript

[00:00:00] Everyone's John. So, today we're going
[00:00:01] to go through probably the biggest
[00:00:03] buzzwords in AI agent system recently,
[00:00:05] agent harness, loop engineering, LLMOps,
[00:00:08] which stands for large language models
[00:00:09] operations, eval, which stands for
[00:00:12] evaluation system for AI agents. And
[00:00:15] these things become popular or become
[00:00:16] viral on the internet not because they
[00:00:18] are just some really complicated
[00:00:20] concepts. Instead, they're actually very
[00:00:22] simple. And I believe that simple
[00:00:23] building blocks will actually help us
[00:00:25] build the biggest architecture in the
[00:00:27] world that will function like an
[00:00:28] intelligent system. Let's walk through
[00:00:30] this step-by-step, and it does not
[00:00:31] matter if you're technical or not. We're
[00:00:34] going to go through this and we'll make
[00:00:35] sure that you're equipped with the right
[00:00:37] knowledge for prompting your way through
[00:00:39] building such a system in the future.
[00:00:41] Let's jump in and get started. For those
[00:00:43] of you who have watched my previous
[00:00:44] video on AI agent memories, you're
[00:00:46] probably already familiar with this
[00:00:47] chart. This is an AI agent run, which
[00:00:50] means that it takes an input from a user
[00:00:52] prompt. For example, you're asking
[00:00:54] ChatGPT or Deep Seek a question and say,
[00:00:57] "Hey, when was Sam Altman fired from
[00:00:58] OpenAI?" And then it's going to go
[00:00:59] through entire run, but the end goal is
[00:01:01] that you want to get a response. This is
[00:01:03] actually ephemeral, which means that
[00:01:05] there's no memory in this at all. We're
[00:01:06] sending that question, "When was Sam
[00:01:08] Altman fired?" and any chat history
[00:01:10] that's currently in the chat. For
[00:01:11] example, maybe we had some conversations
[00:01:13] before that, which for example could be
[00:01:15] you should talk to me like Elon Musk
[00:01:17] grilling on Sam Altman because they
[00:01:19] don't like each other. And then these
[00:01:20] things will be fed into this thing
[00:01:21] called a working memory or a context
[00:01:23] RAM. In this video, we probably won't
[00:01:25] dive too much in-depth into the memory
[00:01:27] system because there's a previous video
[00:01:29] talking about it already. I'll just
[00:01:30] quickly go through it and then we'll
[00:01:32] introduce the concept of what a harness
[00:01:34] means. When you have these kind of
[00:01:35] short-term working memory, there will be
[00:01:37] an LLM or a large language model which
[00:01:39] performs as a question and answer agent.
[00:01:41] And at the end, you're going to get a
[00:01:42] reply. But the problem with a simple
[00:01:45] agent run with simply just the question,
[00:01:47] current chat history, and system prompt
[00:01:49] is that the memory is very short-term.
[00:01:52] But when you run an AI agent system,
[00:01:54] sometimes we need extra memories. For
[00:01:56] example, how should the agent respond to
[00:01:58] the person? A procedural memory is
[00:02:00] exactly that. It basically tells the
[00:02:01] agent how to act and what are some of
[00:02:03] the instructions for the skill. We might
[00:02:05] also want the agent to know some durable
[00:02:07] facts about this context. For example, I
[00:02:09] might want to compare my own early-stage
[00:02:11] startup journey with Sam Altman's early
[00:02:13] startup journey. We need this agent to
[00:02:15] have a memory of who I am, which in this
[00:02:17] context would be a durable facts or a
[00:02:20] semantic memory. Who Sean is, what did
[00:02:22] he build in the past? These kind of
[00:02:23] things became a fact that you want your
[00:02:25] agent to know, but they're not publicly
[00:02:27] available if you're not famous because
[00:02:28] the AI model won't be trained on such
[00:02:30] information yet. But if you're famous
[00:02:32] already, you can skip this. They already
[00:02:33] know who you are. And another thing we
[00:02:35] need is called episodic memory, and they
[00:02:36] include things like the past events or
[00:02:38] past chat history that does not exist in
[00:02:41] this current conversation. For example,
[00:02:43] I might suddenly be wondering, "When was
[00:02:44] the last time I was preparing for a job
[00:02:46] application?" And can we retrieve that
[00:02:48] information and match, you know, if we
[00:02:49] can get a job in ChatGPT. So, these
[00:02:52] things will be retrieved from this thing
[00:02:54] called an episodic memory, which is
[00:02:55] basically a time series of the previous
[00:02:57] conversations or previous triggers that
[00:03:00] happened if you have a more complex
[00:03:01] system. So, for those of you who have
[00:03:03] watched my previous memory agent system
[00:03:04] design, you might be wondering, "Sean,
[00:03:06] why are you repeating all of these
[00:03:07] things?" And that is because if you
[00:03:09] think about the entire thing that we
[00:03:10] just covered in the past few minutes,
[00:03:13] we're really stating the one fact that a
[00:03:15] large language model can't do these
[00:03:17] things by itself. It's like a really
[00:03:18] powerful brain that knows everything
[00:03:22] about humanity, everything about
[00:03:23] science, anything that happened in human
[00:03:25] or biology history. But, it does not
[00:03:27] know you. With you or the software who's
[00:03:30] running this AI agent system, the large
[00:03:32] language model has no clue with how you
[00:03:35] want it to perform. This is why the
[00:03:37] concept called harness becomes really
[00:03:40] important in this. What harness means
[00:03:42] literally is that it's a set of harness
[00:03:44] tools that you use to control a horse
[00:03:47] when you're doing a horse riding.
[00:03:48] Imagine this large language model is a
[00:03:50] horse, right? This horse is very
[00:03:51] powerful, they can run around, but if
[00:03:53] you don't have a good set of tools to
[00:03:55] ride this horse, you could just get
[00:03:57] hurt, you might go anywhere, you might
[00:03:59] go somewhere random. If you're in a war,
[00:04:01] you don't want that to happen. And
[00:04:02] that's why we're doing all of these to
[00:04:04] make sure we have good control over this
[00:04:07] large language model and make sure we're
[00:04:08] utilizing it at its maximum potential.
[00:04:10] That's why in addition to just the
[00:04:12] question or use a prompt and getting the
[00:04:14] reply, and we're feeding them all in as
[00:04:16] a working memory which can be enhanced
[00:04:18] by these three memories we just talked
[00:04:20] about. And in order for these three
[00:04:21] memories to actually work, there's a bit
[00:04:23] more details and they're all included in
[00:04:26] Harness. Remember, Harness means we're
[00:04:27] building this agent framework to control
[00:04:30] this large language model so that it
[00:04:32] works the way we want. For those of you
[00:04:34] who study statistics or machine
[00:04:35] learning, you would understand that a
[00:04:37] large language model is actually
[00:04:38] predicting the probability of the next
[00:04:40] word that it should spit out. When
[00:04:42] everything comes with probability,
[00:04:43] there's randomness in it. But when we
[00:04:45] solve problems, we sometimes don't want
[00:04:47] too much randomness. So, that's why we
[00:04:49] need to have a good control over this
[00:04:51] technology. Now, let's continue to
[00:04:52] finish this Harness. There are lots of
[00:04:54] tools on the market that's already quite
[00:04:56] useful. For example, you could try tools
[00:04:58] like LangGraph, LangChain, or Pydantic,
[00:05:00] and there are many others. In this
[00:05:01] video, we won't dive too much in depth
[00:05:03] into that, and we're going to finish
[00:05:04] building up this Harness before we move
[00:05:06] on to the next topic. So again, for this
[00:05:07] agent to work properly, we need this
[00:05:09] memory system to work, but this memory
[00:05:11] system needs an update system cuz memory
[00:05:13] doesn't just exist or pop up from
[00:05:15] nowhere. You need to constantly update
[00:05:17] it. That's why we need a database to
[00:05:19] store all these memories so that when
[00:05:21] the agent is running in this agent run,
[00:05:23] it knows where to retrieve these
[00:05:25] memories. So, whenever you see an icon
[00:05:27] like this, this is a database, okay?
[00:05:29] Procedural memory is basically remember
[00:05:31] it's it's about instructions, right?
[00:05:32] It's about how the agent should be
[00:05:34] acting. It's like with a Harness on a
[00:05:35] horse, you want the horse to ride faster
[00:05:37] or slower. Normally, these are just
[00:05:39] files or text, and that's why you
[00:05:40] probably heard of this buzzword called
[00:05:42] skills. Skill is basically a piece of
[00:05:44] text in a markdown file that you feed
[00:05:46] into AI agent like Clockwork. But, if
[00:05:48] you want to harness the system well,
[00:05:50] just having files and text is not
[00:05:52] enough. And they're stored in databases
[00:05:54] say like AWS, Superbase, Google Cloud,
[00:05:57] you know, Azure, all these kind of
[00:05:58] places. Or you can set up your own
[00:06:00] server at home if you want, but that's
[00:06:01] just too expensive. You don't want to do
[00:06:03] that. And in order for this harness to
[00:06:04] work properly, you also need to figure
[00:06:06] out how to store the memories, okay? So,
[00:06:09] for example, the episodic memory is a
[00:06:11] time series of the events that happened
[00:06:13] or the previous chat history, again. The
[00:06:14] way we store it is actually very simple.
[00:06:16] You just track every single thing that
[00:06:17] happened, and then it's going to become
[00:06:19] like a very long list of things that
[00:06:21] happened in history with timestamps.
[00:06:23] Durable facts is different story. You
[00:06:24] can either input it yourself or you want
[00:06:26] the system to sort of automatically
[00:06:28] evolve over time. And the way for it to
[00:06:30] evolve is that you want to consolidate
[00:06:32] some of the conversations into the
[00:06:34] semantic memory. If I'm running a D2C
[00:06:36] brand e-commerce company, perhaps my
[00:06:37] customers have talked to my customer
[00:06:39] service agents for a million times about
[00:06:42] how do I get reimbursed if this product
[00:06:43] does not work? You want to consolidate
[00:06:45] these conversations and distill them as
[00:06:48] a fact into the semantic memory. And
[00:06:50] that's why here we have a little gate
[00:06:51] here. If a brand has a million people
[00:06:53] purchasing products from it, let's say
[00:06:54] you're Alibaba or Amazon, it just
[00:06:56] doesn't make sense, and it's very
[00:06:57] expensive. So, from a harness
[00:06:59] perspective, you want to be smart about
[00:07:00] this, and you want the system to be
[00:07:02] automatic. And then simple way is
[00:07:03] probably like maybe consolidate these
[00:07:05] time-ordered events after every say
[00:07:07] 2,000 conversations because you have a
[00:07:08] million customers. And then you can feed
[00:07:10] these things into a summarizer agent,
[00:07:12] which is another large language model
[00:07:14] harness. You can define the system
[00:07:15] prompt in this one. You can probably
[00:07:17] feed it with some memories, too. Uh you
[00:07:19] can configure different models. Maybe it
[00:07:21] could be a cheaper model because you're
[00:07:22] feeding too much text into it. So, the
[00:07:25] context window's too big, and probably
[00:07:27] these are very expensive. So, you can
[00:07:28] use cheaper open-source models if you
[00:07:30] want to. Having such a mechanism allows
[00:07:32] you to consistently update this memory
[00:07:36] system. The data should be coming from
[00:07:39] the previous large language model
[00:07:41] replies. Again, let's review how this
[00:07:43] harness works. A user sent a prompt
[00:07:45] where in one Asian runtime with the
[00:07:47] current chat history and how the agent
[00:07:49] should be performing, the system prompt,
[00:07:52] we're preparing a working memory for
[00:07:53] this AI agent to be able to answer a
[00:07:55] question. And after every single time it
[00:07:58] answered a question, it will send these
[00:08:00] messages to this database. And then this
[00:08:03] database is basically is feeding back to
[00:08:06] this working memory every single time
[00:08:08] when a question is checking for relevant
[00:08:10] context. And at the same time, because
[00:08:13] this database is too big, sometimes you
[00:08:15] want to consolidate them into some
[00:08:17] summarized information or distilled
[00:08:19] facts so that they're stored properly in
[00:08:22] a semantic memory so that the retrieval
[00:08:24] of such memories is just faster. I know
[00:08:26] we talked about retrieval a lot and
[00:08:28] that's just another buzzword called rag,
[00:08:30] which is retrieval augmented
[00:08:31] generations. I also have a few videos
[00:08:33] explaining what rags are. Feel free to
[00:08:35] watch them. There's a little bit of
[00:08:36] difference between how retrieve from
[00:08:38] semantic memory and episodic memory. For
[00:08:41] semantic memory, it's just rags because
[00:08:42] these are just facts and text or files,
[00:08:45] right? But then for episodic memory,
[00:08:47] remember this is a time series. Let's
[00:08:48] say we're still in this e-commerce
[00:08:49] store, right? The user question could be
[00:08:51] like, "What are the previous 10
[00:08:52] conversations that we had with this
[00:08:54] specific customer from the US?" And then
[00:08:56] you might just need a SQL query to query
[00:08:58] something that's pretty recent from this
[00:09:00] episodic memory. But if your question is
[00:09:02] like, "What were my previous 20
[00:09:03] conversations that have customer
[00:09:05] complaints on the quality of the
[00:09:07] products and our agent did not
[00:09:09] successfully resolve." With such a
[00:09:11] question, you not only need a SQL query,
[00:09:14] which is just capturing the dated events
[00:09:17] in a data table, you also want to do
[00:09:19] some semantic search. And that's why
[00:09:21] here rag is important because it's
[00:09:23] checking for relevant information for
[00:09:25] you. You don't want the entire 2,000
[00:09:27] messages. You want that 20 messages out
[00:09:29] of these 2,000 that are exactly relevant
[00:09:32] to what you want. And because these
[00:09:34] complaints are in text, we need to do
[00:09:36] some retrieval augmented generation to
[00:09:39] match the semantic meanings between text
[00:09:41] and the user prompt, so that you're
[00:09:43] fetching the right context for the
[00:09:44] working memory. By now, this is probably
[00:09:46] a fast walk-through of the memory system
[00:09:49] again, but we're just thinking about it
[00:09:51] from a hardness perspective in this
[00:09:53] video. And remember for harness, we're
[00:09:54] training this horse of LLM to run
[00:09:57] autonomously without having too much
[00:09:59] randomness, okay? There's another piece
[00:10:00] of it that's quite important, which is
[00:10:02] the agent might not only just read the
[00:10:04] memory. It might also do some tasks or
[00:10:07] call some tools. When an agent calls
[00:10:10] tools, it might not necessarily be just
[00:10:12] one-time call. It could be multiple
[00:10:14] times of calls. For instance, let's say
[00:10:17] this AI agent has a bunch of agentic
[00:10:19] tools such as help me schedule a
[00:10:22] meeting, help me read or write my
[00:10:23] customer relationship data from the CRM
[00:10:26] system, or help me fetch the payment
[00:10:28] information say from Stripe or Alipay.
[00:10:30] And here's something we should be
[00:10:31] careful about. If we give this horse or
[00:10:33] this LLM technology full power, it could
[00:10:36] just continuously do this forever,
[00:10:38] right? Or it might not even know what's
[00:10:40] the right time to stop or what is the
[00:10:42] right tool calls it should make, when is
[00:10:44] the end point to decide, okay, this
[00:10:46] response is good enough, let's move on
[00:10:48] to reply. That's why we have this
[00:10:50] mechanism called end loop guardrails.
[00:10:52] Yes, now we're talking about loop
[00:10:54] engineering, one of the biggest
[00:10:55] buzzwords in the recent few months. A
[00:10:56] loop is part of harness. Why? Because a
[00:11:00] loop is also helping us to control this
[00:11:04] technology to make sure it runs the way
[00:11:06] we want it to run. An example that could
[00:11:08] be helpful for you is that let's say the
[00:11:11] custom prompt is help me find out what
[00:11:13] customers are complaining about our
[00:11:16] products. What are some of the
[00:11:17] follow-ups we could do in order to win
[00:11:20] them back. And if they're asking for
[00:11:23] reimbursement, have we done the
[00:11:25] reimbursement or not? If not, can we do
[00:11:26] that? This is probably a series of
[00:11:29] questions, but sometimes we just dump
[00:11:30] all of these things into AI agent, okay?
[00:11:32] And after you have this prompt, this LLM
[00:11:35] agent needs to decide, okay, what are
[00:11:37] some of the tools that could be helpful
[00:11:39] for me to finish this task? Loop here is
[00:11:42] basically an architectural thinking of
[00:11:45] when is good enough so that we stop and
[00:11:48] give the user or the business owner a
[00:11:50] reply, okay? So, what might happen here
[00:11:53] is that the LLM agent is doing a bunch
[00:11:55] of tool calls, it's doing some thinking,
[00:11:57] it's saying, let me read from our
[00:11:59] customer relationship management tool
[00:12:01] like Salesforce, HubSpot, or Automanous.
[00:12:03] And then it's going to find out, okay,
[00:12:04] there were 30 customer complaints in the
[00:12:07] past 2 months. 12 of them have got
[00:12:09] reimbursement, the other eight have not
[00:12:11] got reimbursement. So, after the first
[00:12:13] initial fetch, it's probably responding
[00:12:15] to the AI agent, right? And the agent
[00:12:17] will be probably thinking, okay, the the
[00:12:18] task or the ask is that can we can we
[00:12:21] follow up with some of those who did not
[00:12:23] get
[00:12:24] the reimbursement, right? So, and then
[00:12:26] it probably like just make another tool
[00:12:27] calls and be like, hey, let's schedule a
[00:12:30] meeting with those customers who did not
[00:12:33] get a reimbursement, which are the eight
[00:12:34] of them. If we go a little bit more
[00:12:36] advanced, we even just use the
[00:12:37] reimbursement trigger on Stripe or
[00:12:39] Alipay to refund the customer. Can you
[00:12:41] see that this is a loop until we finish
[00:12:43] the task? And but of course, this is
[00:12:45] like a case-by-case situation. It really
[00:12:47] depends on what your task is, how you
[00:12:49] build the system. So, there's no
[00:12:50] one-solution-fits-all. Here, I'm just
[00:12:52] explaining what a loop is. The very,
[00:12:54] very essential part of this loop is that
[00:12:56] it needs to know when it should stop.
[00:12:58] That's why we need this end loop
[00:13:00] guardrails. The guardrails could just
[00:13:01] simply be the task is done. And perhaps
[00:13:04] when the agent was doing the planning,
[00:13:05] it should confirm with the user what is
[00:13:07] a good ending point. It might clarify
[00:13:08] with you, is this what you want,
[00:13:10] reimbursing the other eight people, or
[00:13:11] should I just tell you who they are and
[00:13:13] then you will follow up later? All
[00:13:14] right, these are two different decisions
[00:13:16] you can make. And after you make, you're
[00:13:17] basically telling the agent loop that
[00:13:19] there's an ending scenario. Another good
[00:13:21] example I saw today is that, you know,
[00:13:23] when you're doing coding and cloud code
[00:13:26] can just always pop up some windows and
[00:13:28] ask you for permissions, right? So, the
[00:13:30] good way to use a loop engineering here
[00:13:32] is that you can set up a loop or set up
[00:13:34] a hook in clock code and telling it that
[00:13:36] you should always send me a notification
[00:13:38] on my laptop if you are pending on some
[00:13:41] permissions from me. Otherwise, if I'm
[00:13:42] watching YouTube and then when I come
[00:13:44] back 30 minutes later, I realize that
[00:13:46] clock code is stuck in that one
[00:13:48] permission like 25 minutes ago. That
[00:13:50] would be a waste of my time, okay? So,
[00:13:52] you can set up a loop like this to make
[00:13:53] sure that there's a way to send you
[00:13:55] notification pop-ups so that you know
[00:13:57] the loop has ended or it needs your
[00:13:59] input again. Are you guys still with me?
[00:14:01] Good. So, by far we have covered AI
[00:14:04] agent run with a memory system, with a
[00:14:07] loop engineering around the large
[00:14:08] language model agent, which has a
[00:14:10] trigger to end the loop so that it sends
[00:14:12] a reply to the user, and basically this
[00:14:14] whole thing is an AI agent harness
[00:14:17] system. What's next is one of the other
[00:14:19] biggest buzzwords that Y Combinator
[00:14:22] always mentions, which is eval or LLM
[00:14:24] ops. Let's jump into it. But firstly, I
[00:14:27] want you to understand why do we need
[00:14:29] LLM ops here? Let's still look at the
[00:14:31] left-hand side with this harness system.
[00:14:33] The biggest problem here is that we
[00:14:35] don't know how well it's performing. And
[00:14:37] that's why we need a feedback loop to
[00:14:39] help us understand is this agent
[00:14:42] actually performing properly, right? For
[00:14:44] my business or for my use case. And can
[00:14:47] I continuously get feedback on how do we
[00:14:50] fix it and actually fix it ourselves,
[00:14:53] okay? And when we say fix it, a simple
[00:14:55] way to understand it is that
[00:14:57] can we have a better system prompt?
[00:15:00] Can we have a better large language
[00:15:01] model configurations?
[00:15:03] Is there something we should change for
[00:15:05] how we retrieve the AI agent memories?
[00:15:08] These are kind of things that we can
[00:15:09] continue to iterate. But in order to
[00:15:11] iterate to make sure this system runs
[00:15:13] properly, we need a way to evaluate it,
[00:15:17] diagnose problems, solve the problems
[00:15:19] until it's a healthy and well-performing
[00:15:22] system. And that is called large
[00:15:25] language model operations system, LLM
[00:15:28] ops. So again, in order to understand
[00:15:30] this properly, we need to come back to
[00:15:33] what an agent run is. So an agent run,
[00:15:35] you can simply understand it as a user
[00:15:37] question is sent to a large language
[00:15:39] model and then you get a reply. That is
[00:15:41] one agent run. But in this agent run,
[00:15:44] the agent tool calling could happen
[00:15:45] multiple times. That does not matter,
[00:15:47] right? We're just talking about from a
[00:15:49] user input to a response from agent
[00:15:52] perspective. That's one agent run. And
[00:15:55] then we're going to introduce this
[00:15:56] system called a tracing system. So every
[00:15:59] agent run, we should trace like a tree
[00:16:02] of events that happened. And there are
[00:16:04] lots of tools that could help you with
[00:16:05] that. It could be LangFuse, could be
[00:16:06] LangSmith, etc., etc. A tree of events
[00:16:08] could be like what did the person
[00:16:09] actually ask, what retrievals did the
[00:16:11] model actually retrieve, how many times
[00:16:14] did the large language model actually
[00:16:15] call the tools, and how was the tool
[00:16:17] usage, how was the response time, right?
[00:16:20] How long did it take for this entire
[00:16:22] system to run for checking latencies,
[00:16:24] and how many tokens have we used when we
[00:16:26] do these tool calls, agent run, you
[00:16:29] know, doing this retrieval augmented
[00:16:31] generation, these kind of things. So
[00:16:33] trace is helping us to track events,
[00:16:35] basically. And that's the first step.
[00:16:37] This is the step first to collect data.
[00:16:39] And these data will be used for the
[00:16:41] following two purposes. Was it a good
[00:16:44] system run? And was it healthy? Which
[00:16:46] corresponds to evaluation system.
[00:16:49] We can probably use large language model
[00:16:50] as a judge here to give us a score on
[00:16:54] how well it performed. For example, if
[00:16:56] the task has something to do with
[00:16:58] schedule meetings, did the meeting
[00:17:00] actually triggered? How long was the
[00:17:01] response for an agent to reply to a
[00:17:03] question? Was it 20 seconds or was it 2
[00:17:05] milliseconds? And also things like how
[00:17:07] many tokens have we used? These two are
[00:17:09] basically in the same system. You can
[00:17:11] write it as a deterministic code, you
[00:17:12] can use an AI agent to do it, but this
[00:17:14] is like part of the procedure, which is
[00:17:16] helping us to understand was this a
[00:17:17] healthy system?
[00:17:19] And was it a good system? And after
[00:17:21] that, we're going to diagnose, okay,
[00:17:23] where and why something was broken. For
[00:17:25] example, the meeting scheduling event
[00:17:28] was never triggered. Why was that?
[00:17:30] Right? We want to understand why was
[00:17:31] that. And we could probably feed that
[00:17:33] into coding agent in Claude to sort of
[00:17:35] deep dive into it. Or, you know, if the
[00:17:37] latency is 20 seconds instead of 2
[00:17:39] milliseconds, something's wrong. Maybe
[00:17:41] one of the tool call is taking too much
[00:17:43] time.
[00:17:44] Maybe the working memory is too large,
[00:17:48] uh so that the response time for a large
[00:17:49] language model to a memory retrieval is
[00:17:51] just taking too much time. Maybe not
[00:17:53] every single question requires a
[00:17:55] retrieval from all these gigantic memory
[00:17:58] system. Maybe you're just asking a
[00:18:00] simple question be like, when was my
[00:18:01] birthday? When was OpenAI started? And
[00:18:04] these kind of information you probably
[00:18:05] don't need to do a ton of retrieval. The
[00:18:07] model itself already knows. So, you
[00:18:08] basically want this system to provide a
[00:18:10] dashboard for you to understand the
[00:18:12] metrics. And then, with these metrics,
[00:18:14] you can diagnose what is going wrong.
[00:18:16] And then we're going to have a little
[00:18:16] gate here, which is if the evaluation
[00:18:19] system passed, well, you can define the
[00:18:21] rules, we can either ship some very
[00:18:23] simple fix, have a new version of the
[00:18:25] prompt, or update the model
[00:18:26] configuration, you know, some tool
[00:18:28] changes, or the parameters for
[00:18:30] retrievals. The LLM Ops will feed the
[00:18:33] improved system prompt and the
[00:18:35] configuration of the model back to this
[00:18:37] agent run system. When then one LLM Ops
[00:18:40] loop is finished. If, let's say,
[00:18:42] something is deeply broken, right? We
[00:18:44] cannot just simply ship the latest
[00:18:46] version of the prompt. Then we should go
[00:18:48] fix the bug, rerun the agent run, resend
[00:18:50] the question, and then retrace the
[00:18:52] events, and then redo this evaluation
[00:18:55] system in this LLM Ops architecture. So,
[00:18:57] now let's zoom out and look at this
[00:19:00] chart one more time. We covered what an
[00:19:02] AI agent run is, we covered how it would
[00:19:05] retrieve information from memories, and
[00:19:07] we understood how an LLM agent would ask
[00:19:10] questions, would call tools to help it
[00:19:13] finish the task in a loop, and it knows
[00:19:15] when to stop the loop so that it we can
[00:19:16] get the reply. This whole thing is a set
[00:19:18] of harness tools that we're controlling
[00:19:20] this horse, this technology, to run in
[00:19:23] the right direction, okay, to do the
[00:19:25] right task. And at the same time, we
[00:19:27] have like a health checking system or
[00:19:29] evaluation system to understand how
[00:19:31] every single run is being traced, is
[00:19:34] being observed, and how do we diagnose
[00:19:37] some problems and fix some problems, and
[00:19:39] ship the latest updates of the prompt,
[00:19:41] about the model configuration, about all
[00:19:44] these parameters or knobs that needs to
[00:19:46] be updated, so that this system will be
[00:19:49] an autonomous system that will just
[00:19:50] self-evolve and grow over time. I really
[00:19:53] hope this was helpful. Let me know what
[00:19:54] you think, and if you have any
[00:19:55] questions, you can always reach out to
[00:19:57] me. I'll see you in the next video.
[00:19:59] Thanks so much.
