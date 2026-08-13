---
video_id: zXysLUTLjw4
title: "FDE: The $1M/Year AI Job Explained"
channel: Greg Isenberg
url: "https://www.youtube.com/watch?v=zXysLUTLjw4"
watched_date: 2026-07-21
watched_at: "2026-07-21T12:00:00Z"
watch_count: 1
duration_seconds: 3094
source: youtube-history-browser
added_date: 
history_label: Jul 21
history_order: 158
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 309
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Forward Deployed Engineers (FDEs) are specialists commanding $150K–$1M annually who bridge AI capabilities with real business needs. The core insight: since all companies now access identical frontier models, competitive advantage lies in *deployment*—understanding how work actually happens (not how it's documented), determining where AI genuinely adds value versus where rule-based automation suffices, and building systems that match each company's unique workflows. The role requires three competencies: deep understanding of business processes through on-site observation (because documented procedures rarely reflect reality), technical judgment to make architecture decisions balancing risk/ROI/accuracy, and hands-on software engineering to build, evaluate, and monitor production systems. FDEs succeed by combining rare consulting-style communication skills with strong technical execution—they're not average at both, but excellent at both.

To enter this field: pick one LLM ecosystem (OpenAI, Anthropic, Google, etc.) and one agent platform and get extremely proficient before switching models. Develop business acumen by learning to extract workflows through interviews and shadowing—the gaps between documented processes and reality are where value hides. When scoping AI applications, create evaluation suites upfront and default to human-in-the-loop approval (humans validate before the system commits). If starting consulting work, sell the audit phase to clients—it's where you learn their actual processes and justifies the later implementation cost. The competitive edge is mastering both sides: you must understand business incentives, adoption friction, and cost-benefit trade-offs as well as you understand systems architecture and model behavior.

## Transcript

[00:00:00] I know it's crazy, but there are people
[00:00:02] making a million dollars a year as Ford
[00:00:04] deploy engineers. But what exactly is an
[00:00:07] FDE? I know you've probably seen it, but
[00:00:10] I feel like a lot of people aren't clear
[00:00:12] as to what it is and how they could
[00:00:15] become one. [music] Well, in this
[00:00:16] episode, I brought on my friend Voss.
[00:00:18] And Voss is a leading expert when it
[00:00:20] comes [music] to FTEEs with his company,
[00:00:22] Veric Agents. And in this episode, he
[00:00:25] gives you his entire playbook, how you
[00:00:28] could become an FTE in 30 days. Now,
[00:00:32] this episode is for people who want to
[00:00:34] become an FTE, but also for people who
[00:00:36] are just interested in what it [music]
[00:00:38] means, how they can actually use FTEEs
[00:00:41] in their business to be make more money,
[00:00:44] to be more productive. And I just think
[00:00:46] this is the clearest episode, the
[00:00:49] clearest piece of content on the
[00:00:51] internet, the clearest master class for
[00:00:54] how to understand clearly what an FDE
[00:00:58] is, how you could become one, and why it
[00:01:02] matters. Enjoy the episode, and I'll see
[00:01:04] you at the end.
[00:01:08] [music]
[00:01:13] Voss is here. And Voss, by the end of
[00:01:16] this episode, what are people going to
[00:01:19] learn?
[00:01:20] >> They're going to learn exactly how to
[00:01:21] break into forward deployed engineering
[00:01:23] or become a better FTE in 30 days. The
[00:01:26] full road map for AI forward deployed
[00:01:28] engineering.
[00:01:28] >> And I don't feel like this has been
[00:01:29] shared anywhere. I feel like the term
[00:01:32] forward deploy engineer is just like on
[00:01:35] my X feed everywhere. So, what I'm
[00:01:37] hoping for, Voss, is for you to clearly
[00:01:39] explain what this means and just like
[00:01:42] all the concepts to it and just break it
[00:01:44] down for me in a clear, easy to
[00:01:46] understand way. So, so I could uh so I
[00:01:51] could, you know, learn from it, but so
[00:01:53] others could learn from it, too.
[00:01:55] >> Absolutely. And there's a lot of
[00:01:56] different definitions. Everyone has
[00:01:57] their own. And I'm going to give you
[00:01:59] what I think is the clearest
[00:02:00] explanation.
[00:02:01] >> Okay, let's do it.
[00:02:02] >> Sweet. So, yeah, this has never been
[00:02:04] shared before. our team put together uh
[00:02:06] it's how to break into FD in 30 days.
[00:02:09] Let's start off with uh recent
[00:02:11] developments and the facts of today. The
[00:02:13] reality is every company can now buy
[00:02:16] intelligence. You know, you have a
[00:02:17] frontier model being released every
[00:02:19] single day. Just yesterday we had Kimmy
[00:02:21] 3 being released. Uh last week was Fable
[00:02:24] uh 5, you know, or GPT 5.6 Soul. Every
[00:02:27] company can now buy intelligence and the
[00:02:30] reality is intelligence is becoming
[00:02:31] commoditized. So the same foundational
[00:02:34] capability is becoming available to
[00:02:36] anybody who can pay for it and that's
[00:02:38] most companies today. So you'll see here
[00:02:41] is a graphic where every company has
[00:02:42] access to the same foundational model.
[00:02:45] So if everyone can access it,
[00:02:47] intelligence can no longer be the mode.
[00:02:49] I think there was this huge theory that
[00:02:52] you know people will be priced out of
[00:02:54] intelligence and that could be the case
[00:02:56] in the future but the reality is today
[00:02:58] everyone has access to the same tools.
[00:03:00] If you go and talk to 50 different
[00:03:02] enterprise clients, they're all using
[00:03:03] the same stack. They're all using cloud
[00:03:05] codeex. They're using cursor for model
[00:03:07] agnosticism. Uh they're using GitHub
[00:03:09] copilot. It's all the same thing. So the
[00:03:12] reality is everyone has the same
[00:03:14] capability in terms of what intelligence
[00:03:16] tap they have access to.
[00:03:19] So where does the advantage go? It goes
[00:03:22] into deployment. So the edge is no
[00:03:24] longer who has the intelligence. It's
[00:03:26] where, how, and why they use it. And
[00:03:28] that is the role of an AI for deployed
[00:03:31] engineer. It's allowing companies to
[00:03:33] harness and take advantage of AI
[00:03:36] intelligence or software previously to
[00:03:39] make sure that they apply it the best to
[00:03:41] their specific company context. Every
[00:03:43] single company is different in terms of
[00:03:46] how their business is structured, what
[00:03:48] processes they have, how things run,
[00:03:50] etc. And the job of an FD is to make
[00:03:53] sure that the intelligence which is
[00:03:54] general is specifically applied to this
[00:03:57] company in a way that benefits them the
[00:03:59] most. And the advantage will start to
[00:04:01] become who has that best bridge that
[00:04:03] connection between their own processes
[00:04:06] and the intelligence stack that they
[00:04:08] have access to.
[00:04:09] >> And Voss this was a term that correct me
[00:04:12] if I'm wrong was popularized by the
[00:04:15] Palunteer team. Right.
[00:04:16] >> That's right. So can you know can you
[00:04:19] tell me about like how Palunteer I think
[00:04:23] how Palunteer works with FDES? I mean I
[00:04:25] feel like for a lot of people Palunteer
[00:04:27] is this black box. Can you can you go a
[00:04:29] little more into that?
[00:04:30] >> Yeah it's funny. So I lived in New York
[00:04:32] for a few years and I had a ton of
[00:04:33] buddies who are Palunteer for deployed
[00:04:34] engineers. So I have a little bit of
[00:04:35] insight into this.
[00:04:37] >> Um without sharing what I what I think
[00:04:39] is proprietary. Palunteer has an
[00:04:41] ontology. They have a software stack
[00:04:42] that they work off of and this is full
[00:04:45] of connectors to software but also data
[00:04:47] links which allow people to which allow
[00:04:49] enterprises to pipe their data into a
[00:04:51] unified interface and what Palanteer
[00:04:53] FDES then do is they'll actually be
[00:04:55] deployed on site. So this is either like
[00:04:57] enterprise customers or the military the
[00:05:00] government um and learn their workflows
[00:05:02] and then spin up kind of workflows
[00:05:04] dashboards you know agents that will
[00:05:07] solve the problem for these companies.
[00:05:09] So Palunteer really popularized the idea
[00:05:11] of essentially which was what was
[00:05:13] consulting but for the software space
[00:05:15] they coined the term for a deployment
[00:05:16] engineer and it really started to allow
[00:05:19] their business to take off. They had a
[00:05:20] centralized platform but its beauty was
[00:05:23] not in like how tech forward it was. It
[00:05:25] was it was in how customizable it was
[00:05:28] and then these forward deployment
[00:05:29] engineers would go on site customize it
[00:05:31] per client and it would really solve
[00:05:32] their pain points better than a
[00:05:34] generalized servers.
[00:05:36] >> Cool. And I guess like the the thesis is
[00:05:39] that if it works for Palunteer, it can
[00:05:42] work for everyone else, right?
[00:05:45] >> That is sort of the thesis. Yeah. And
[00:05:47] the Palunteer I think really solved it
[00:05:48] when it came to the data age where you
[00:05:51] wanted to unify your data sources and
[00:05:52] then visualize it in more unique ways. I
[00:05:55] think the AI age is going to demand that
[00:05:57] 100 times more where every single
[00:05:59] company is going to need customized
[00:06:00] agents. And uh that's actually what
[00:06:02] we're here to solve as well with our
[00:06:04] with our OS. But everyone is sort of
[00:06:07] coming to this same realization that
[00:06:08] forward deployed engineers are a massive
[00:06:10] reason why AI is going to be powerful
[00:06:12] for businesses.
[00:06:14] >> Cool. Let's keep going.
[00:06:15] >> Sweet.
[00:06:17] So someone has to decide where
[00:06:19] intelligence belongs not just where it's
[00:06:21] applied. And that person is a forward
[00:06:22] deployed engineer as well. So there's
[00:06:24] kind of three stages to a forward
[00:06:26] deployed engineer's involvement at a
[00:06:28] company. The first is understanding the
[00:06:30] business reality. So it's how the work
[00:06:33] actually happens today. And I think this
[00:06:35] is the part that gets glossed over by
[00:06:37] people who are you know very deeply in
[00:06:39] tech. You know in Silicon Valley we have
[00:06:40] a mindset where like okay well the
[00:06:42] beauties in the software like it doesn't
[00:06:43] really matter what the business
[00:06:44] processes are. But I can tell you
[00:06:46] firsthand every business is so different
[00:06:49] even in terms of like the same process
[00:06:52] across multiple businesses. Let's go
[00:06:53] like accounts payable for example or or
[00:06:56] sales for example at two different
[00:06:57] companies. The way that they do that is
[00:07:00] so different. One has a 10-step process,
[00:07:02] one has a 30-step process. One is using
[00:07:05] Salesforce Gong uh and uh Chili Piper.
[00:07:09] The other one is using HubSpot and uh
[00:07:12] Apollo and Clay. There's the software
[00:07:15] differences, but there's also the
[00:07:16] process differences, and there's the
[00:07:18] things that matter most to the business
[00:07:20] being very different. Um when things go
[00:07:22] wrong, like exception handling, the way
[00:07:24] that that's being done at a company
[00:07:25] needs to be documented as well. So Ford
[00:07:28] deployed engineers go on site, they'll
[00:07:31] either interview people or just observe
[00:07:33] them work or get, you know, access to
[00:07:35] their systems like their ERPs, their CRM
[00:07:38] to figure this stuff out. And this is
[00:07:40] where the bulk of the time goes in my
[00:07:42] opinion. Um, it cannot be understated
[00:07:44] how important this is both in terms of
[00:07:46] understanding the business, but also to
[00:07:48] bring that business along the journey.
[00:07:50] And this is where communication and
[00:07:52] analytical ability is incredibly
[00:07:54] important for a forwardlook engineer.
[00:07:56] Um, the way I like to think of an FTE is
[00:07:58] the best combination of someone very
[00:08:01] deeply technical who can understand it,
[00:08:02] but also someone with fantastic
[00:08:04] communication ability and the ability to
[00:08:07] get the information out of people that
[00:08:08] they need to. Um, and this is
[00:08:11] all-encompassing for business reality.
[00:08:13] >> And you know, you say the FDE goes on
[00:08:16] site. When you say onsite, is that like
[00:08:18] literally like walks in the office and
[00:08:21] starts like speaking to people and stuff
[00:08:22] like that or do you mean like you know
[00:08:26] >> it can it can certainly be done
[00:08:27] remotely?
[00:08:28] >> Yeah.
[00:08:29] >> Um and you know there's there's certain
[00:08:31] times where that's you know required
[00:08:33] because a company itself is remote or
[00:08:35] like the people at the function are not
[00:08:36] all in one office but I will say a large
[00:08:39] majority of the time it is on site. I
[00:08:41] know that Palunteer does this very
[00:08:43] heavily. uh we do this as well and it's
[00:08:45] not just because you know you can't get
[00:08:47] the information remotely but it's it's
[00:08:49] it's actually more so because the
[00:08:52] relationship that you build with the
[00:08:54] person like you know you're on site
[00:08:55] you're part of the team you'll uncover
[00:08:57] far more information that way right like
[00:09:00] if somebody will simp if you schedule a
[00:09:01] 1-hour meeting for example somebody will
[00:09:03] walk you through what they think is the
[00:09:05] job but if you're on site with them for
[00:09:08] the full 8 10 hours whatever it is
[00:09:10] you're actually experiencing the job
[00:09:12] like when something goes wrong that's
[00:09:14] not really documented in an SOP or like
[00:09:16] a in a word doc or a Google doc
[00:09:17] somewhere you're going to see that play
[00:09:19] out. Um you know even consultants of
[00:09:21] McKenzie they do this they'll go on site
[00:09:23] to a mine and they'll sit with the
[00:09:25] miners and they'll watch them do their
[00:09:26] work uh because it's so much more
[00:09:28] powerful to establish that relationship
[00:09:30] and get the information that way.
[00:09:32] >> Cool.
[00:09:34] >> Yeah. The second step is FD judgment
[00:09:36] which is where does intelligence belong
[00:09:38] and where does it not? I think when the
[00:09:40] AI wave first started, we saw a lot of,
[00:09:43] you know, let's just slap AI everywhere.
[00:09:45] Let's let's give everything to the model
[00:09:46] and let's let's let it figure it out.
[00:09:48] Um, and this is what led to token maxing
[00:09:51] and hallucinations. Then you have the
[00:09:52] the MIT stat that 95% of generative AI
[00:09:55] pilots fail. Um again now the industry
[00:09:59] is sort of shifting gears and they're
[00:10:00] realizing that okay we actually need to
[00:10:02] be very selective about where we apply
[00:10:04] this intelligence and we also need to be
[00:10:06] selective about how we design the new
[00:10:09] stack for this intelligence to play out.
[00:10:10] So again for example you have a 10step
[00:10:13] workflow it might be that you know that
[00:10:16] workflow should not be changed by AI.
[00:10:19] You know maybe it's too risky or maybe
[00:10:20] it's not high enough ROI. Maybe it's
[00:10:23] already pretty automated. Why do we need
[00:10:24] to do bring AI into it? Um, it also
[00:10:27] could be that of those 10 steps, only
[00:10:31] three of them actually need judgment,
[00:10:33] right? So, categorization of this, you
[00:10:36] know, lead in a CRM tool, that might be
[00:10:37] a little bit more non-deterministic. So,
[00:10:40] we're going to bring in an LLM there for
[00:10:41] for judgment. But the rest can be solved
[00:10:44] with with, you know, if then else
[00:10:46] statements. It can be solved with API
[00:10:48] calls. And this sort of judgment is
[00:10:50] actually, you know, far more complex
[00:10:52] than I'm making it out to be even. But
[00:10:54] it belongs with the FDE. So the FDE both
[00:10:57] has again the business reality which is
[00:10:59] the consulting style like communication
[00:11:02] style approach, but also the technical
[00:11:04] judgment so that they can determine
[00:11:06] based on their technical background.
[00:11:08] Okay, I think that this design is going
[00:11:10] to be, you know, risky. We're going to
[00:11:12] have 80% accuracy. It's not worth it.
[00:11:14] Versus this other, you know, workflow
[00:11:16] will will have a much higher ROI. will
[00:11:18] be able to build it much faster. It's
[00:11:19] lower risk, etc. And that sort of back
[00:11:21] and forth judgment is where an FD really
[00:11:23] shines. It's bridging the gap between
[00:11:25] the business and the technology.
[00:11:27] >> If you, you know, just curious like if
[00:11:29] if someone listening to this like wanted
[00:11:31] to become a foreign deployed engineer in
[00:11:34] New York City that's doing this sort of
[00:11:35] stuff, like how much money could they
[00:11:38] make?
[00:11:39] >> A lot of money. You have uh no idea how
[00:11:42] expensive it's gotten. Both from a we're
[00:11:44] hiring perspective, but also in terms of
[00:11:46] what the market's demanding. This is the
[00:11:48] hottest role in technology right now. I
[00:11:50] mean, you could make anywhere from
[00:11:53] 150,000 base with considerable equity to
[00:11:56] I've seen roles go up as high as a
[00:11:57] million dollars a year. And I'm not
[00:11:58] joking. Um, these are extremely well
[00:12:01] compensated roles if you are the best
[00:12:03] combination of consulting and
[00:12:05] technology.
[00:12:06] >> Cool.
[00:12:08] >> Um, deployed AI system. Finally, the
[00:12:11] last step is actually going out and
[00:12:13] building the software itself. This is
[00:12:15] where it varies wildly company by
[00:12:18] company. For example, at Palunteer even
[00:12:20] they have some FTEEs that you know
[00:12:22] you're not actually writing code. You're
[00:12:23] mostly like spinning up workflows like
[00:12:25] text. You're chatting with the software
[00:12:27] of the Palunteer ontology to create like
[00:12:30] some dashboards and to the extent you're
[00:12:31] writing code it's SQL. But there's other
[00:12:33] companies where you are fully writing
[00:12:36] like production code either on-site with
[00:12:38] a client or you'll go back and and do
[00:12:40] this but it varies wildly. So there are
[00:12:42] some FTE roles where you're going to be
[00:12:44] writing production code. You need to
[00:12:46] have a background in software
[00:12:47] engineering and like really be confident
[00:12:49] in your ability there. There's other FTE
[00:12:51] roles where it's far more technically
[00:12:53] light and you can you know chat to build
[00:12:56] um on top of an existing platform. So
[00:12:58] this is the part that varies wildly. But
[00:13:00] either way, you need to have a very good
[00:13:02] understanding of the software because
[00:13:04] when the client has an issue with, hey,
[00:13:05] this doesn't work right or we have an
[00:13:07] issue in production, it's basically your
[00:13:09] ass on the line and you have to know who
[00:13:11] to call, what to do, and how to fix it.
[00:13:14] >> Totally.
[00:13:14] >> In summary, FTEEs are in demand because
[00:13:17] they control how intelligence enters the
[00:13:19] business, how it's used, and that is
[00:13:22] where all the value is today in the AI
[00:13:23] age. Everyone is coming to this
[00:13:25] consensus, and that's why FDS are
[00:13:26] extremely valuable. Well, it's also in
[00:13:29] demand because it's new as well. Like
[00:13:32] this, like there wasn't intell super
[00:13:34] intelligence on tap five years ago. So,
[00:13:38] not only is the idea of super
[00:13:41] intelligence on tap just absolutely
[00:13:44] absurd. Many trillion dollars of, you
[00:13:48] know, money is going to be changing
[00:13:49] hands over the next few years. But the
[00:13:51] idea that now you need a person to
[00:13:53] actually like people are realizing hey
[00:13:55] you actually need judgment and hey you
[00:13:57] actually need to like you know be a
[00:13:59] systems thinker and hey like actually
[00:14:02] token maxing isn't the best strategy.
[00:14:05] Like there was like a moment in time
[00:14:06] where token maxing like people were
[00:14:10] people basically were agreeing that
[00:14:12] token maxing was the strategy. It was
[00:14:14] just like hey these models are so good
[00:14:16] let's just let them do their thing. That
[00:14:18] was like the thinking.
[00:14:20] Yeah, that was a a funny period in time.
[00:14:23] I would argue we're still not fully out
[00:14:24] of that. But yeah, um yeah, you're
[00:14:26] totally right. I mean, this is a brave
[00:14:28] new world for everyone involved. And
[00:14:30] >> I mean, I I have horror stories of of
[00:14:33] people of of like seuite executives I've
[00:14:35] talked to who have blown through their
[00:14:36] entire $10 million claw budget in like 3
[00:14:40] months. It was supposed to last them a
[00:14:41] year, but because they gave it to
[00:14:42] everybody, it's token maxing and
[00:14:44] everyone's spinning up whatever they
[00:14:45] need. And and and the sad reality is it
[00:14:48] didn't really move the needle for the
[00:14:49] business either. And it's because that
[00:14:50] business didn't really invest heavily
[00:14:53] into forward engineering. And so I think
[00:14:55] you're totally right.
[00:14:56] >> Cool. Let's keep going.
[00:14:59] >> Sweet. So we we've already alluded to
[00:15:01] this, you know, pretty heavily prior,
[00:15:03] but I want to really make sure I hammer
[00:15:05] down this point, which is that there's
[00:15:07] two uh sort of streams of of kinds of
[00:15:11] judgment that are required, and it's
[00:15:13] very rare in a in a single person. So I
[00:15:15] think the the unfortunate reality is and
[00:15:17] this is what's going to happen. It's
[00:15:18] already starting to happen is as you
[00:15:21] know we go from the token maxing let's
[00:15:23] go all in on token maxing go to now the
[00:15:26] same thing on FD let's go go go let's
[00:15:27] hire a bunch of fes I want to be very
[00:15:30] clear about what the role really
[00:15:31] demands. I think there's a lot of fees
[00:15:33] who are you know unfortunately neither
[00:15:35] the best communicators and neither the
[00:15:36] best software engineers. I would
[00:15:38] strongly urge them to strengthen both of
[00:15:40] those skills. It's both the
[00:15:42] understanding of workflows, cost,
[00:15:44] incentives, risk, adoption, business
[00:15:46] value, um, you know, the politics of the
[00:15:48] internals of a company. These are all
[00:15:50] things that you have to manage and
[00:15:52] consultants here are incredibly strong,
[00:15:55] right? You'll talk to McKenzie
[00:15:57] engagement managers, BCG, Bane
[00:15:58] engagement managers, they'll be very
[00:16:00] good at this side. Um, the other side is
[00:16:02] what they might need some more support
[00:16:04] in. And same thing software engineers
[00:16:06] will be very good at the right side with
[00:16:07] models systems APIs data code
[00:16:10] reliability uh eval guardrails you know
[00:16:13] more AI centered terms harnesses post
[00:16:16] training fine-tuning these are things
[00:16:18] that are more on the technical side of
[00:16:20] the aisle and software is usually very
[00:16:22] good at this but they need to also then
[00:16:24] kind of drift towards the business side
[00:16:26] um by understanding the left side of the
[00:16:27] aisle and FTE is the best combination of
[00:16:30] both of these it's not an average
[00:16:32] combination it's not the worst
[00:16:33] combination of both where you know
[00:16:35] you're not the best communicator but you
[00:16:36] also can't code. It is truly the best of
[00:16:39] both and that is the milliondoll hire
[00:16:41] where the FD can turn business
[00:16:43] understanding into working software end
[00:16:44] to end. They can do both sides
[00:16:46] perfectly.
[00:16:47] >> Yeah. I mean put another way it's like
[00:16:49] if you understand art and you understand
[00:16:51] science
[00:16:52] >> and you could speak both
[00:16:55] >> you have what it takes to become a the
[00:16:58] million-dollar FD. The the hard part is
[00:17:00] like usually the people that are good at
[00:17:03] good at science are sort of good at
[00:17:05] science and the people that are good at
[00:17:07] art are kind of good at art. Um but
[00:17:11] there you know there is some overlap in
[00:17:13] the ven diagram.
[00:17:15] >> Absolutely. And that's why it's such a
[00:17:17] rare role. But I also firmly believe and
[00:17:19] that's kind of the whole point of this
[00:17:20] presentation is that you can become
[00:17:22] this. It's it's not out of the realm of
[00:17:24] possibility to become much better at
[00:17:25] both of these things. It just you need
[00:17:27] it cleanly laid out. you need a road map
[00:17:29] and that's what I hope that I can
[00:17:30] provide by the end of this call.
[00:17:32] >> Cool. All right. All right, boss.
[00:17:34] >> Let's go. [laughter]
[00:17:38] >> So, first you know for example, it's
[00:17:39] understand how the work is really done.
[00:17:42] Um
[00:17:43] because the documented process is very
[00:17:45] rarely the the real process, right? So,
[00:17:46] an email might arrive. Now, this is
[00:17:48] extremely simple, but the reality is it
[00:17:51] sounds like a clean trigger, but it's
[00:17:52] it's far more complicated than that. It
[00:17:54] arrives from 40 plus senders. No two of
[00:17:57] them are formatted alike. the data is
[00:17:58] different. Some of it's in a PDF, some
[00:18:00] of it's in a screenshot, some of it's in
[00:18:02] an Excel spreadsheet, or it's buried in
[00:18:04] a forwarded thread. It's it's far more
[00:18:06] complex than it makes out to be. So, if
[00:18:08] you didn't look into this, if you
[00:18:10] weren't an FD and you just asked the
[00:18:12] person for, hey, what's the first step
[00:18:14] of the workflow? They'll tell you an
[00:18:16] email arrives. And all of a sudden,
[00:18:18] you're building for a system that
[00:18:19] doesn't map to reality versus the
[00:18:20] reality, which is that it's so
[00:18:22] complicated. And half of them are
[00:18:24] exceptions. It's the same as last time.
[00:18:25] It ignores the second attachment. Sarah
[00:18:27] already signed off on this one. There's
[00:18:29] no consistent subject line, so you can't
[00:18:31] route without actually going into it.
[00:18:33] And usually the reality of how to play
[00:18:36] this is in one person's head. So one
[00:18:38] person will know like, okay, yeah, well,
[00:18:39] when I see this email from this person,
[00:18:41] they'll send it to this this vendor or
[00:18:43] to this part of our procurement team.
[00:18:45] But that's not written down. And if you
[00:18:47] don't sit with that person, kind of coax
[00:18:49] this all out of them, they're not going
[00:18:50] to remember to even tell you. um you
[00:18:52] would think about like at your job today
[00:18:54] I asked people viewing this how easy is
[00:18:56] it for you to really write down every
[00:18:59] single exception that [laughter] might h
[00:19:01] happen in your job I was a software
[00:19:03] engineer at meta and if people ask me
[00:19:04] for my job I'd say well yeah I code all
[00:19:06] day I'll get a task and I'll I'll work
[00:19:08] on it but that's not the reality right
[00:19:10] the reality is I have meetings you know
[00:19:11] this happens something breaks in prod I
[00:19:13] have to go fix it that's what we're
[00:19:14] getting at here the second step is oh
[00:19:17] it's copied into a spreadsheet same
[00:19:18] thing here you get the idea one's a real
[00:19:20] one two are stale data validation. It's
[00:19:22] rekey by hand, columns drift. Same thing
[00:19:24] with checking into an internal system. I
[00:19:27] won't get into all this. You get the
[00:19:28] idea. Every step is extremely
[00:19:29] complicated. Um, so that's what
[00:19:32] understanding the work really means. It
[00:19:34] takes time and it takes effort to sit
[00:19:37] with a person responsible and sometimes
[00:19:38] multiple people responsible.
[00:19:41] >> Usually, usually it's multiple people.
[00:19:43] >> Very, very often. Yeah. I mean, if this
[00:19:45] company has like 5,000 10,000 people
[00:19:47] working in it, chances are you have a
[00:19:49] lot of people working on the same thing.
[00:19:51] Then you decide how the work should
[00:19:53] operate when intelligence is built in.
[00:19:54] So again, where does the terministic
[00:19:56] software live in? Where does the agent
[00:19:57] act? Where does the human approved?
[00:19:59] Where does the record get updated? I
[00:20:01] think the best combination of sorry, the
[00:20:03] best solution of AI for most companies
[00:20:05] is a very good combination of
[00:20:08] deterministic software. Probably the
[00:20:09] majority of it is that, but then
[00:20:11] obviously the the judgment that API
[00:20:13] calls to LM can provide. And then
[00:20:16] finally, human loop.
[00:20:18] So this is just a fancy little little
[00:20:20] digest, but it's really the agent that
[00:20:22] can then be deployed into existing
[00:20:23] systems. It's doing the first half,
[00:20:26] which is intake, validation, agent
[00:20:27] drafting, and then you have a human in
[00:20:29] the loop for approval. This is something
[00:20:30] that I strongly recommend my FDES to
[00:20:32] push for in a in a in an agent
[00:20:34] implementation. Once you hit approve,
[00:20:37] it'll then go through the latter half of
[00:20:38] the steps, and that's what you're
[00:20:40] building. So the job of an FTE when
[00:20:42] you're building has three parts. It's
[00:20:43] obviously auditing, then creating
[00:20:45] evaluation suites to make sure the
[00:20:47] system behaves correctly. This is
[00:20:48] extremely important in the AI age. And
[00:20:50] then finally, deployment, which is both
[00:20:52] handholding the client to make sure
[00:20:53] they're adopting it, it's working well
[00:20:55] for them, but then also the software
[00:20:56] side, making sure that nothing breaks.
[00:20:58] You're monitoring all the metrics that
[00:20:59] matter. You're monitoring KPIs, SLAs's,
[00:21:02] and everything needs to be topnotch for
[00:21:04] somebody to really trust you as an FD.
[00:21:06] And every stage is a prerequisite for
[00:21:08] the next. So for an eval so prove the
[00:21:12] system behaves correctly. So in a
[00:21:14] scenario where uh the outcome you know
[00:21:18] is non-deterministic meaning like it's
[00:21:21] tough to say what success looks like how
[00:21:24] do you create an eval or can you create
[00:21:26] an eval for more creative task or tasks
[00:21:30] that are hard to like understand if it's
[00:21:34] successful or not.
[00:21:36] >> Yeah. for for obviously for you know
[00:21:38] more non-deterministic tasks it's much
[00:21:40] harder right it's much easier to say
[00:21:41] okay was this email categorized
[00:21:43] correctly because we have 10,000
[00:21:45] previous emails to go off of and it'll
[00:21:47] be the basis for our email set but even
[00:21:49] for tasks where it is non-deterministic
[00:21:51] like for example creating a presentation
[00:21:55] right there's a million different ways
[00:21:56] to do it and
[00:21:58] sort of the beauty is in the eye of the
[00:21:59] beholder where you know one thing looks
[00:22:01] good to me might look bad to you um here
[00:22:05] it's very helpful to have as much
[00:22:06] previous data as possible. Obviously, if
[00:22:09] you have 5,000 previous presentations to
[00:22:11] go off of, it makes it a lot easier to
[00:22:12] create this golden data set of what we
[00:22:14] think matters. You know, you can say,
[00:22:16] you know, always put the logo in the top
[00:22:18] left, always have larger font of this
[00:22:20] styling, etc., etc. But this is
[00:22:23] obviously where you'll never get to a
[00:22:25] perfect result with just evals. need
[00:22:27] human in the loop feedback to make sure
[00:22:29] that going forward you at least have a
[00:22:31] feedback mechanism that improves your
[00:22:33] harness if not like post- train uh or
[00:22:36] fine-tunes the model that you're working
[00:22:37] under. So on one hand like get as much
[00:22:40] data as you can and kind of determine
[00:22:42] like what looks good, what looks bad,
[00:22:43] identify like what matters to you, but
[00:22:45] also then always bake in human loop
[00:22:47] feedback because even with a good data
[00:22:49] set, even with good evals, you'll need
[00:22:52] to have them constantly improved. And
[00:22:54] that's where that feedback mechanism
[00:22:55] comes into play.
[00:22:56] >> And I've noticed like in this entire
[00:22:59] presentation, this entire podcast, we
[00:23:01] haven't really spoken about which LLM to
[00:23:05] use. Are you like basically agnostic in
[00:23:07] terms of like working with Anthropic or
[00:23:10] OpenAI or Google or like if you're an
[00:23:13] FDE basically, how do you think about
[00:23:17] which
[00:23:19] LLM to work with?
[00:23:21] >> Yeah, great question actually. Um,
[00:23:22] something I probably should have touched
[00:23:23] on. Uh, we as a company are extremely
[00:23:26] model agnostic. So we think our value
[00:23:28] lies in our ability to be switching from
[00:23:31] one model to the next and making sure
[00:23:32] that your accuracy only improves, your
[00:23:34] cost only goes down and you're not
[00:23:36] marrying to one intelligence provider,
[00:23:38] which we think will be an asset going
[00:23:40] forward. Um, you don't want to
[00:23:42] monopolize your intelligence, your
[00:23:43] inference layer. That being said, if I
[00:23:45] was an FTE today or if I was trying to
[00:23:47] become the best FTE today, I would stick
[00:23:50] to one model and one agent building
[00:23:52] platform. OpenAI has one, Cloud has one,
[00:23:55] agent SDK, etc. every single model
[00:23:57] provider has one. Get very very good at
[00:24:00] one of them because that will be the
[00:24:02] foundation that you then you know okay
[00:24:04] let's let's try out claude tomorrow if
[00:24:05] I'm already good at open AI's you know
[00:24:07] Asian building platform okay I feel more
[00:24:08] confident about that let's go to Kimmy 3
[00:24:10] or GLM 5.2 too. Let's see what the open
[00:24:12] source models can do. Let's build a
[00:24:14] proprietary harness. That's how I would
[00:24:16] go about it. Um, but I wouldn't really
[00:24:19] worry about being model agnostic when
[00:24:20] you're starting out as an FD because
[00:24:21] that's again not where your value lies.
[00:24:23] Your value lies in how good are you at
[00:24:25] understanding both sides of the aisle
[00:24:27] because that can then apply to any
[00:24:28] model.
[00:24:29] >> Totally. And it's we're getting to a
[00:24:32] point where
[00:24:34] the models
[00:24:36] are
[00:24:38] very similar in a lot of ways.
[00:24:40] >> Yeah. And a lot of the big players are,
[00:24:43] you know, they have like Google will
[00:24:45] have their frontier model, but they'll
[00:24:47] also have an open source model, for
[00:24:48] example. And so now you're getting to
[00:24:50] this place where it's like, okay, you
[00:24:52] can play with their open source model,
[00:24:53] you can play with their um, you know,
[00:24:56] frontier model. And and so I I expect
[00:24:58] that the arrow of progress around LLMs
[00:25:02] is they're going to have a bunch of
[00:25:04] different products for you to play with.
[00:25:06] So yeah, I agree. Like if you want, you
[00:25:09] know, pick pick an ecosystem, bet on an
[00:25:12] ecosystem that you believe in for
[00:25:14] whatever reason, be the best at that
[00:25:17] ecosystem. And then as you become the
[00:25:19] best, then it's like, okay, if you want
[00:25:22] and you're working with a client, for
[00:25:23] example, and for whatever reason,
[00:25:27] another model makes more sense, then
[00:25:29] great. You know, you
[00:25:31] >> Yeah,
[00:25:32] >> you can go and recommend that.
[00:25:34] >> Absolutely.
[00:25:36] Yeah,
[00:25:36] >> I would say that that's exactly right.
[00:25:37] And then just to really hammer the last
[00:25:39] point in, your ability to determine what
[00:25:42] model is best for a task relies on your
[00:25:44] understanding of various different
[00:25:46] models. You're benchmarking them along
[00:25:47] the way. But to your point, don't put
[00:25:49] the card ahead of the horse. Like really
[00:25:51] get good at one before you then try to
[00:25:53] venture out and make that understanding.
[00:25:54] I would totally agree.
[00:25:55] >> Yeah. I mean, that's like
[00:25:59] Yeah. You don't want to like hammer a
[00:26:00] specific, you know, model
[00:26:04] and you don't understand
[00:26:06] what the system and the set of tasks
[00:26:09] are. It's like
[00:26:10] >> the equivalent of, you know, you're a
[00:26:12] waiter and you just hand someone a glass
[00:26:14] of pino noir and they're like, I didn't
[00:26:18] ask for that. You know, you you know, a
[00:26:20] good restaurant has a sleier and and and
[00:26:24] sier's job is to understand what is your
[00:26:26] pallet? Um, do you like dry wines? Do
[00:26:28] you like wines from, you know, uh,
[00:26:32] France, you know, southern France or
[00:26:35] northern France or, you know,
[00:26:38] >> Yeah.
[00:26:39] >> I'm not the biggest wine guy, so I, you
[00:26:42] [laughter] know, the analogy might break
[00:26:44] down, but that idea, I think, of just
[00:26:46] like understanding what people want
[00:26:48] first and then deploy makes a lot of
[00:26:51] sense.
[00:26:52] >> Yeah. I mean, honestly, I thought that
[00:26:53] was pretty good. Like, familiarity of of
[00:26:56] agents is an FTE. Like you really go in,
[00:26:58] figure out what they want and then you
[00:26:59] give it to them, right? You might give
[00:27:01] everybody pen noir. It might work for
[00:27:02] some of them, but it's not going to work
[00:27:03] for most. And that's why again most AI
[00:27:05] pilots fail
[00:27:06] >> 100%.
[00:27:08] >> Cool. All right, let's let's keep going.
[00:27:10] >> Sweet. This is again more of the same.
[00:27:13] Find the workflow worth rebuilding. I'm
[00:27:15] going to link this I'll have Greg link
[00:27:17] this this document, you know, in the in
[00:27:18] the in the channel. So, if you guys want
[00:27:20] to dive in deeper in here, but the idea
[00:27:22] is again the same. collect the context,
[00:27:24] trace the FD findings, figure out the
[00:27:25] bottlenecks, the repetitive work, the
[00:27:27] judgment points, all that stuff, and
[00:27:29] then produce the operating map. And this
[00:27:31] back and forth is why having the
[00:27:33] understanding of the business and the
[00:27:34] tech is super important.
[00:27:37] >> Cool. By the way, if you go back to the
[00:27:39] audit, like if you want to be an FDE, um
[00:27:44] you know, we just had an episode with um
[00:27:47] Corey Ganim who he came on the podcast
[00:27:49] and he basically he was he talked about
[00:27:52] selling audits as a way to to learn
[00:27:55] about someone's business and then deploy
[00:27:56] AI afterwards. Like you can sell the
[00:28:00] audit, right? like
[00:28:02] >> in charge for the audit
[00:28:04] >> and then
[00:28:05] >> the implementation you can charge like a
[00:28:08] monthly fee or you can charge a onetime
[00:28:10] fee. How should people think about that?
[00:28:12] >> Yeah. So actually we're in this exact
[00:28:13] business of you know implementing AI
[00:28:15] across the largest companies on the
[00:28:17] planet and we require every single
[00:28:20] engagement to start with an audit which
[00:28:23] you know obviously costs money to the
[00:28:24] business. Um this is extremely valuable.
[00:28:27] I think again like there's a lot of
[00:28:29] misunderstanding like you know you can
[00:28:31] just throw AI on the on the on the on
[00:28:34] the uh the company. The audit is worth
[00:28:36] so much money to a business. I mean
[00:28:38] we've had companies that tell us like
[00:28:40] the audit was worth 10 times what they
[00:28:42] paid for. It's it's better than McKenzie
[00:28:44] because it's so telling. AI is so new
[00:28:47] like you said no one really understands
[00:28:49] how to go about an audit. But if you're
[00:28:51] able to say like look here is in your
[00:28:54] department here are all the different
[00:28:56] workflows and we've mapped them out very
[00:28:58] cleanly right we have the full steps the
[00:29:00] back and forth the exception handling
[00:29:01] we're going to map that out for you and
[00:29:03] we're also going to tell you what we
[00:29:05] think is worth automating versus what
[00:29:07] isn't give them that priority map give
[00:29:09] them that matrix that ROI matrix and
[00:29:12] then go ahead and show them how you
[00:29:15] would build it and show them the ROI
[00:29:16] show them the use case that is worth so
[00:29:19] much money to a company I I think this
[00:29:21] is something that even most consulting
[00:29:23] firms are not able to figure out and
[00:29:25] this is where you have an edge if you
[00:29:27] are really up to date on AI and you
[00:29:28] actually know live and breathe it
[00:29:30] yourself. Um the audit is worth a ton of
[00:29:33] money to a business.
[00:29:35] >> Totally. It's also a chance for you to
[00:29:37] like build trust with them.
[00:29:39] >> Yeah.
[00:29:40] >> You know what I mean? and and and show
[00:29:43] them how you work and underpromise and
[00:29:45] overd deliver and and and it gets their
[00:29:49] creative juices flowing around like okay
[00:29:51] I didn't realize that you know cuz
[00:29:53] you're producing like an operating map
[00:29:55] right so you didn't realize like oh hey
[00:29:57] like you know I never thought about that
[00:29:59] use case or I didn't think that you know
[00:30:02] this would produce this expected
[00:30:04] business value um maybe it's worth
[00:30:07] investing in
[00:30:08] >> absolutely it's funny you When we first
[00:30:11] started, you know, the company, it was
[00:30:12] last year. This is before FDUs were
[00:30:14] really a big thing. Um, we used to call
[00:30:17] the audit the medicine that neither one
[00:30:19] of us wants to take, right? Like a lot
[00:30:22] of companies are like, "Oh, like, do I
[00:30:23] have to do an audit? Can't you just like
[00:30:24] token max and start building?" But it
[00:30:27] really is so valuable and they realize
[00:30:29] that as the audit goes on. So, I totally
[00:30:31] agree.
[00:30:32] >> Yeah. We um cuz we we we also have an
[00:30:36] agency called LCA. Um and
[00:30:40] LCA is well known for building like
[00:30:44] working with the biggest companies on
[00:30:45] the planet and then taking their
[00:30:46] products from a product perspective and
[00:30:49] bringing them into the AI age. So like
[00:30:51] from a you work with like a Dropbox and
[00:30:53] what is an AI first version of Dropbox
[00:30:55] or Slack and AI first version of Slack
[00:30:57] look like? And we started doing audits
[00:31:00] as like, hey, let's audit your product
[00:31:02] first. What we noticed was the word
[00:31:04] audit
[00:31:07] was a tough pill for people to swallow.
[00:31:10] And we just rebranded audit as a sprint.
[00:31:13] So it would be like it was a design
[00:31:15] sprint. We just kind of like and we
[00:31:17] like, you know, brought in the the the
[00:31:20] concept of an audit um with it. Um so we
[00:31:24] noticed that that that worked better.
[00:31:26] So, um just just a little uh tip for
[00:31:29] folks.
[00:31:30] >> Super helpful. Yeah. [laughter]
[00:31:32] >> For some reason, people have an allergic
[00:31:33] reaction to the word audit. Um
[00:31:35] >> well, I mean, they think of they think
[00:31:36] of like a tax audit.
[00:31:38] >> Yeah. Yeah. Fair enough. The AI audit
[00:31:42] doesn't have the same ring to it for
[00:31:43] sure. [snorts]
[00:31:46] >> Yeah. Cool. All right.
[00:31:48] >> Let's keep going. Again, deterministic
[00:31:49] software versus an agent versus a human
[00:31:51] in control. I'm not going to beat a dead
[00:31:52] horse. You got to prioritize the high
[00:31:54] volume workflows where the improvement
[00:31:56] is large enough to matter. That's your
[00:31:57] job as an FD is to figure that out
[00:31:59] firsthand.
[00:32:01] >> Um, eval turn non-determinism into
[00:32:04] evidence. You got to make sure that you
[00:32:06] have the right data, the required steps,
[00:32:07] it matches the expert, um, and it's safe
[00:32:10] to act on and you got to make this kind
[00:32:11] of matrix and wherever you feel like
[00:32:14] it's not safe to act on, you know, you
[00:32:15] route it to a human and you create an
[00:32:18] evaluation report, right? So you have
[00:32:21] 50 runs and 41 of them passed. Of the
[00:32:23] nine that didn't, let's investigate why.
[00:32:25] You know, five of them had missing data,
[00:32:27] four of them had the wrong record
[00:32:28] pulled. And then you use that to improve
[00:32:30] the system. Greg, you touched on this
[00:32:32] earlier, like how do you set up evals?
[00:32:33] This is sort of the the framework that I
[00:32:35] would use.
[00:32:37] >> This is cool. By the way,
[00:32:40] >> yeah, just it it helps to just have like
[00:32:42] a a decision tree, a matrix when you're
[00:32:44] thinking about things. again like
[00:32:45] because everything is so new you could
[00:32:47] go a million different ways but you know
[00:32:49] I'm sure there's other ways to do this
[00:32:51] but this is ours and this is just how we
[00:32:52] kind of think about things at a high
[00:32:53] level it depends on a case by case basis
[00:32:56] for sure
[00:32:58] so how do you make it deploy and work
[00:32:59] inside the business this is again phase
[00:33:00] three the first one is the audit the
[00:33:02] second one was eval third is deployment
[00:33:04] one we really preach about like
[00:33:05] integrating with what already exists um
[00:33:08] I think a lot of AI folks are forcing
[00:33:11] migrations to like new software and And
[00:33:14] the reality is, and this is a tip that I
[00:33:15] give to all my FDE, you have an edge if
[00:33:17] you're able to build on top of their
[00:33:18] systems. So, you know, one of our
[00:33:20] clients, for example, said that they
[00:33:21] spent, you know, a couple of years, a
[00:33:24] couple million dollars moving to
[00:33:25] Netswuite, which is an ERP software. And
[00:33:28] if your AI solution is like, hey, we
[00:33:30] have to make you move off of Netswuite,
[00:33:32] they're going to tell you to get lost.
[00:33:34] But instead if you're saying which is
[00:33:35] what we do build on top of Netswuite
[00:33:38] make it much better and integrate that
[00:33:39] Netswuite with your Salesforce with your
[00:33:42] SAP with your Concur Expensify Gong uh
[00:33:45] you know every other piece of software
[00:33:47] workday that is a much more powerful
[00:33:50] system and that is where all the value
[00:33:52] lies
[00:33:54] than if you can test it in a controlled
[00:33:56] environment and really scale up from you
[00:33:59] know deployment to shadow mode to
[00:34:03] increasing autonomy. to then being
[00:34:04] deployed in production. That is going to
[00:34:06] be your edge as well where you're not
[00:34:08] forcing a massive shift. You're kind of
[00:34:10] walking them through that journey. And
[00:34:11] to our point earlier of why you meet
[00:34:13] them in person, it's because it's a lot
[00:34:15] easier to kind of guide them along that
[00:34:17] journey if you've met them face to face
[00:34:18] versus if you're just a guy behind a
[00:34:20] computer screen saying, "Hey, now we're
[00:34:22] going to flip a switch and AI is going
[00:34:23] to run your business." That's a a much
[00:34:25] different much more uh polarizing
[00:34:28] approach.
[00:34:28] >> I mean, it makes sense, right? like
[00:34:30] you're you did the audit and then if
[00:34:33] you're going to pitch to them, hey,
[00:34:34] you've been working with this software
[00:34:37] stack for the last 20 years. All of a
[00:34:39] sudden, go switch to this thing and it's
[00:34:41] going to cost you a bunch of money and
[00:34:43] there's just like so many unknowns. Like
[00:34:46] that is a tough pitch to sell. You know
[00:34:50] what I mean? And like you want to if
[00:34:52] you're pitching anything, you want to
[00:34:54] pitch something that feels like you're
[00:34:56] fishing with dynamite. So, it's like how
[00:34:58] can you, you know, how can you fish with
[00:35:01] dynamite? You just say like, "Hey,
[00:35:03] you're you have this system and this
[00:35:06] stack. You're it's it's worked for you.
[00:35:10] Um, I'm going to make it better and it's
[00:35:15] going to help you all be more efficient.
[00:35:18] It's it's going to help you uh reach
[00:35:21] customers faster. It's going to drive
[00:35:22] value for customers. It could increase
[00:35:25] revenue." Like when you start saying
[00:35:26] things like that, it's like, okay,
[00:35:28] no-brainer, no brainer, no brainer.
[00:35:30] Also, you have to keep in mind that
[00:35:31] you're pitching to people at a company.
[00:35:34] And people at a company, I'll say the
[00:35:36] thing that people don't say, which is
[00:35:39] they don't want to get fired,
[00:35:41] right? Like they want to get promoted
[00:35:43] actually. So your job is to help them
[00:35:46] get promoted. How do you help them get
[00:35:49] promoted is probably not by moving from
[00:35:51] one ERP to another ERP that may be
[00:35:54] marginally better. You help them get
[00:35:56] promoted by driving value
[00:36:00] cost effectively. If you can drive value
[00:36:03] cost effectively, everyone's high five
[00:36:06] high-fiving, right? Cuz when performance
[00:36:08] reviews comes around, you know, you the
[00:36:11] the employee, the executive can point to
[00:36:14] I worked on this project. Yes, I worked
[00:36:16] with an outside agency like LCA or Veric
[00:36:19] Agents or individual FDE
[00:36:23] um freelancer. Um but as long as you
[00:36:28] help them do that, that's what's going
[00:36:30] to help them get promoted.
[00:36:33] >> Yeah, totally. And and and just like to
[00:36:35] again like double down on that, they
[00:36:38] view you as a risk, right? They can just
[00:36:40] sit by and let things stay the same and
[00:36:43] status quo. They'll be fine. But if they
[00:36:45] instead bring in an FTE who's going to
[00:36:48] change stuff up and maybe it fails, like
[00:36:50] they're worried if this fails, it's a
[00:36:52] terrible look on me. Forget like
[00:36:54] migrating to another ERP. Even just you
[00:36:56] being involved at all is a risk to them.
[00:37:00] So you have to de-risk this as much as
[00:37:02] possible for them if you really want to
[00:37:03] sell yourself into a company. And what I
[00:37:06] strongly recommend is like do the audit
[00:37:09] for free. like get your foot in the
[00:37:11] door, prove value there, come up with a
[00:37:13] plan, and then only get paid when you
[00:37:16] really prove measurable value. That is
[00:37:19] what I strongly because that derisks the
[00:37:21] whole thing. Your first few customers,
[00:37:23] if you're really starting this out, will
[00:37:25] teach you so much. They are genuinely
[00:37:27] worth more to you than you are to them.
[00:37:29] But after you have one, two, three of
[00:37:31] those, then you can start charging for
[00:37:33] this because you're going to be leagues
[00:37:36] and miles ahead of everyone else in the
[00:37:37] space. I promise you it's still so
[00:37:39] early. I know this from our company as
[00:37:42] well. There is so much demand for people
[00:37:45] who really know how to do this. And
[00:37:48] quite frankly, there aren't that many
[00:37:49] people who know how to do this. Get
[00:37:51] started, get your feet wet, um, and
[00:37:53] really prove that you know what you're
[00:37:55] doing. And that's d-risking the whole
[00:37:56] thing for them.
[00:37:58] >> Totally. And it's just going to give you
[00:38:00] the confidence too, you know.
[00:38:01] >> Yeah.
[00:38:02] >> Right. Which is important.
[00:38:04] >> Yeah. And you'll know what matters to
[00:38:05] them when you're selling. like you can
[00:38:06] touch on different aspects that speak
[00:38:08] better to this person in the function.
[00:38:10] Um it's all really valuable. If I had to
[00:38:13] put one page cemented burned in
[00:38:15] everyone's brain, it's this one which is
[00:38:18] you go from audit to eval to deployment.
[00:38:21] There's some steps in the way you build,
[00:38:23] you observe and you improve and the loop
[00:38:25] runs again because once you improve one
[00:38:28] system, the next one becomes extremely
[00:38:29] clear. There's always interconnected
[00:38:32] bottlenecks where one workflow is
[00:38:34] impacted by something upstream and it
[00:38:37] frees up something downstream. And this
[00:38:39] is why AI is so pervasive in an
[00:38:41] organization. It's because once you have
[00:38:43] it in one place, you're going to need it
[00:38:45] everywhere else so that you're not just,
[00:38:47] you know, 10xing one workflow, 10xing
[00:38:50] another, you're 100xing the entire
[00:38:52] business as a whole. Um, and that's your
[00:38:55] job as an FTE is to go from audit to
[00:38:57] eval to deployment over and over again.
[00:39:00] And the next stage that I'm going to
[00:39:01] show is the 30-day plan of how you can
[00:39:04] get there from zero to one. If if I was
[00:39:06] starting from scratch, how would I go
[00:39:08] about it?
[00:39:09] >> And you did this, by the way. You you
[00:39:11] started from scratch, right? I didn't
[00:39:12] know this, but you were you're an
[00:39:14] engineer at Meta, right? And then you
[00:39:16] sort of learned how to do this. So,
[00:39:18] you're speaking from experience.
[00:39:20] >> Yeah, absolutely. I was an engineer at
[00:39:22] Meta for um uh a few years working on a
[00:39:25] different a couple different products,
[00:39:27] but I was never a consultant. I never
[00:39:29] really understood what mattered to
[00:39:31] businesses as deeply as I do now. And we
[00:39:32] got started again just by by doing it.
[00:39:35] Um and we we we had this thesis that
[00:39:38] like AI needs to be applied and it
[00:39:39] allows us to get ahead of the curve. Um
[00:39:42] but you never learn by,
[00:39:45] you know, reading and and you only learn
[00:39:48] by doing it. So the goal from this is is
[00:39:51] to do like if I could condense what I
[00:39:53] did over a year and really had the
[00:39:55] biggest learnings, the biggest wins in
[00:39:57] just 30 days. This is what I would do.
[00:40:01] So the first step is build an agent that
[00:40:03] can complete a real loop, right? Build
[00:40:06] an agent that's actually useful as a
[00:40:08] workflow. So like ask Chad PT what is
[00:40:10] one real enterprise workflow in a
[00:40:15] function of the back office, right? It
[00:40:16] could be finance, it could be HR, it
[00:40:19] could be procurement, logistics, it
[00:40:20] could even be for it, it could be sales,
[00:40:22] anything. Get the workflow in as
[00:40:24] granular of a detail as possible and
[00:40:27] build an agent for it. Um, even today,
[00:40:30] it's very hard to build agents, right?
[00:40:33] We think that it's a solved science.
[00:40:34] It's not. There's a thousand different
[00:40:36] ways to do this. Everyone has different
[00:40:38] definitions of an agent. My definition
[00:40:39] is this. If I give you a task, can you
[00:40:44] solve it in as much
[00:40:46] detail and as high enough accuracy as
[00:40:48] possible. It's different than me
[00:40:51] prompting Claude to go do it. It's far
[00:40:53] more in the background and it has much
[00:40:55] more of a repetitive motion where I'm
[00:40:58] not relying on somebody prompting
[00:40:59] perfectly to make it happen. I can
[00:41:01] prompt like an idiot and it will still
[00:41:03] happen. That's my kind of requirement
[00:41:05] for you when you're solving for this.
[00:41:07] There's a bunch of different, you know,
[00:41:08] aspects to this, but if you have 7 days
[00:41:10] to work on this, you'll be able to pick
[00:41:12] it up. agent looping, then tool usage,
[00:41:15] then guard rails, then context and
[00:41:17] memory, then the audit trail, which is
[00:41:19] incredibly important. I want to hammer
[00:41:20] down here a little bit. If you can't
[00:41:22] show the client what the agent is doing,
[00:41:25] they will never trust you. There's a big
[00:41:27] fear in AI agents today that okay, it's
[00:41:30] going to go off and do something. It's
[00:41:31] horrible. There's a lot of
[00:41:32] fear-mongering as well. I won't say from
[00:41:33] who, but everyone knows who I'm talking
[00:41:34] about. [snorts] Um, you need to show
[00:41:37] that the agent traces are logged
[00:41:40] everything. And this is a software
[00:41:41] engineering problem. So, if you can do
[00:41:42] that, you're a step ahead. And again,
[00:41:44] there's a full day for each of these
[00:41:45] things. Um, to clarify, if you're, you
[00:41:49] know, working 12 hours a day, I don't
[00:41:52] expect you to be able to pick all this
[00:41:53] stuff up perfectly on each every single
[00:41:54] day, but this is what I mean by like a
[00:41:56] 30-day plan. You can space it out as you
[00:41:58] need. It's not like you have to get it
[00:41:59] done in 30 days. Then a real workflow,
[00:42:02] then a checkpoint. The checkpoint, the
[00:42:03] last day is you have a working agent
[00:42:05] with tools, guardrails, deliberate
[00:42:07] memory, and a full audit trail for one
[00:42:09] task. You might not even understand the
[00:42:10] task the best, but this is just to get
[00:42:12] you well-versed in building agents.
[00:42:16] >> Fair.
[00:42:18] >> The second week is turning that demo
[00:42:20] into a system that can recover. Again,
[00:42:22] very heavily on the engineering side.
[00:42:24] So, a defined JSON schema not free form
[00:42:26] text. You're validating schema. You have
[00:42:29] failure modes and again I want to call
[00:42:32] it failure modes. exception handling and
[00:42:35] we also see in 13th days failure
[00:42:36] handling is also extremely extremely
[00:42:40] important. This is where going in deep
[00:42:42] into a client matters because if you
[00:42:45] understand hey when something goes wrong
[00:42:47] how does it go wrong and let me build
[00:42:49] the agent around that is extremely
[00:42:53] important. It's far more effective than
[00:42:55] you're building an agent that solves for
[00:42:56] just the happy path. It's called the
[00:42:58] happy path. If you're building for the
[00:43:00] unhappy paths, the 1,500 different ways
[00:43:02] it can go wrong, your agent is worth a
[00:43:05] million times more. The way I say it is
[00:43:07] this. There's only one way that
[00:43:08] something can go right, but there's a
[00:43:11] thousand different ways something can go
[00:43:12] wrong. So, if you're only building for
[00:43:14] the way it goes right, you're worth
[00:43:16] nothing. If you're solving for all the
[00:43:18] exceptions, that's where you are worth
[00:43:20] something as an agent.
[00:43:22] That's week two.
[00:43:24] Then week three is where you start to
[00:43:26] make it measurable and economically
[00:43:28] viable. Right? So you'll have the retry
[00:43:31] logic. Yes, this is more engineering.
[00:43:32] You'll have the golden data set for
[00:43:34] evals. You'll make sure that it improves
[00:43:35] over time. But you'll also start
[00:43:38] understanding, okay, this is what we
[00:43:39] talked about earlier, Greg. Looking at
[00:43:41] cheaper models for subtasks, looking at,
[00:43:44] you know, less soda, less Frontier
[00:43:46] models. Can we get this job done with a
[00:43:48] Gemini Flash or can we get it the job
[00:43:51] done with a a Muse Spark or probably not
[00:43:54] a Llama 4, but you know, there's other
[00:43:55] models that can that can be a good fit
[00:43:57] there. Um, this is where you start to do
[00:43:59] more or more of this test, which is we
[00:44:02] have an agent now. Now, let's try to
[00:44:04] optimize it. Let's try to measure, okay,
[00:44:05] how much is it really moving the needle?
[00:44:06] If I deploy this in production, how much
[00:44:08] time am I saving? How much risk am I
[00:44:10] mitigating? How much revenue uplift do I
[00:44:13] have? There's only three buckets of me
[00:44:14] measurement that matter for a business.
[00:44:16] It's those three, revenue uplift, risk
[00:44:18] mitigation, and cost savings. So, you
[00:44:20] need to measure your agent across all
[00:44:22] three of those buckets. And at this
[00:44:24] checkpoint, you have, you know, an
[00:44:25] evaluated agent with known failure
[00:44:26] modes, measured costs, and a golden data
[00:44:28] set. And the final week is defend the
[00:44:32] system like an FTE, which is all of the
[00:44:35] business around it. It's the pain
[00:44:37] points, it's why AI belongs, it's the
[00:44:40] architecture behind it, it's the
[00:44:41] iterations. is you know when you first
[00:44:43] built the agent it got this wrong but
[00:44:45] then it improved over time accuracy went
[00:44:47] from you know 70% to 95%. and the
[00:44:51] economics around it. So how much time
[00:44:53] did you save the error reduce again risk
[00:44:55] revenue costs? We talked about this and
[00:44:57] you rehearsse this as an engineer. So
[00:44:59] what was the architecture? What were the
[00:45:00] decisions that you made? And then you
[00:45:02] also rehears this as a VP. Like what was
[00:45:04] the problem that you solved? What was
[00:45:05] the outcome? What was the evidence? What
[00:45:06] was the risk? And this week is where
[00:45:09] you're going to know, you know, was the
[00:45:12] system that you built worth the salt?
[00:45:14] Was it worth the investment? How much
[00:45:17] could you charge for this when you build
[00:45:19] it for a customer? That's what this week
[00:45:21] is for. And I strongly recommend that
[00:45:23] during this week, you pitch your agent
[00:45:26] to businesses because they will tell you
[00:45:29] like, you know, did I get you you'll
[00:45:32] pitch them, did I get this right? Did I
[00:45:33] get the economics right? Am I thinking
[00:45:34] about this the right way? And they'll
[00:45:35] tell you point blank, no. Or I want it
[00:45:38] built in this way. and you'll start to
[00:45:40] see like okay now for my next FD
[00:45:43] engagement starting out with an audit
[00:45:45] when you're actually embedded with a
[00:45:46] customer you'll learn much more about
[00:45:48] that obviously this is 30 days is you're
[00:45:50] not embedded with a customer because you
[00:45:52] can't because you have to become an FTE
[00:45:53] first that's when you can finally start
[00:45:55] to pitch yourself and be involved in a
[00:45:57] company
[00:45:59] so if I had to zoom out this would be
[00:46:02] the 30 days it's doing the job before
[00:46:04] you have the title so on day 30 you
[00:46:05] understand forward deploy engineering
[00:46:07] but you also have evidence that you can
[00:46:08] do it and if you pitch this to a
[00:46:09] company, they'll be much more likely to
[00:46:11] give you a shot. And that's my goal.
[00:46:15] >> Foss, [snorts] this is ex this is
[00:46:17] perfect. Like, this is exactly what I
[00:46:19] would recommend, too. What would be so
[00:46:22] cool is if
[00:46:24] is if you actually taught people how to
[00:46:27] do this, right? Um, and like spent 30
[00:46:31] days with people to actually do this.
[00:46:34] Um, maybe maybe we do it together. Just
[00:46:38] an idea. Uh if people are interested,
[00:46:41] I'll just include a link uh in the
[00:46:44] pinned comment on YouTube. Um I'm just
[00:46:47] curious if people
[00:46:49] people are interested in like cuz it
[00:46:51] might it might feel overwhelming for
[00:46:53] people to do this
[00:46:55] on their own. I mean, I still think you
[00:46:57] could do it on your own, by the way, but
[00:46:58] I wonder and and by the way, I'm not
[00:47:00] promising anything. I'm just curious,
[00:47:02] are people into
[00:47:04] into some sort of program for this?
[00:47:08] They don't teach you this at school.
[00:47:10] >> They don't. They should. Uh I'm sure
[00:47:12] we'll have university courses on FTE
[00:47:14] soon. But yeah, people want to
[00:47:18] [laughter] like it just takes so long. I
[00:47:20] remember I was in computer science
[00:47:22] school in 2008.
[00:47:24] >> No, 2009
[00:47:27] um and at university. And I remember the
[00:47:31] app store had just come out.
[00:47:34] It was so clear in 2009 that mobile apps
[00:47:38] was the next wave. Just like it's so
[00:47:41] clear right now that AI agents and AI is
[00:47:44] the is the is not even the next wave is
[00:47:45] the wave. And I just remember the
[00:47:49] textbooks at the time and I went to a
[00:47:51] top university
[00:47:53] textbooks at the time and the course
[00:47:54] material was like you know building old
[00:47:59] school software and I remember going to
[00:48:01] a teacher a professor well-known guy and
[00:48:04] saying why can't we why can't you teach
[00:48:06] us how to build an Objective C and to
[00:48:10] build for the app store and he was just
[00:48:13] like yeah it's just not in the textbook.
[00:48:15] just not in the textbook. And that's
[00:48:18] when I like I was like, I'm going to
[00:48:20] drop out of this. I [laughter] I'm
[00:48:22] dropping out because like I don't want
[00:48:24] to learn yesterday's stuff. I want to
[00:48:27] learn tomorrow's stuff. Now, there's
[00:48:30] always the argument to be made that you
[00:48:32] need foundational work. And so, like I
[00:48:36] learned a lot in university around like
[00:48:38] foundational stuff around maths and
[00:48:40] physics and stuff like that. And I
[00:48:42] actually think that that stuff was
[00:48:43] really helpful just in like learning how
[00:48:45] to think, but like the actual tactical
[00:48:48] stuff did not really learn.
[00:48:52] >> Yeah, I I I do, you know, I want to say
[00:48:56] like this time is different like just
[00:48:58] because it's so powerful like AI is so
[00:49:01] like you said it's the wave that I'm
[00:49:03] hopeful that universities are going to
[00:49:05] pick up sooner than later, but for some
[00:49:07] reason I feel like you're right. I don't
[00:49:08] think it's going to happen anytime soon.
[00:49:10] Yeah.
[00:49:12] Well,
[00:49:13] >> there you have it, folks.
[00:49:16] What what FDEES are.
[00:49:19] Um how to become one. Uh a 30-day plan.
[00:49:25] Uh Vos, anything else you want to share?
[00:49:29] >> I think, you know, like you said, you
[00:49:31] might not find this in university, but
[00:49:34] you're absolutely going to find it on
[00:49:36] YouTube. like Greg is teaching
[00:49:38] everything that you need to know and
[00:49:39] Twitter as well. Those two sources are
[00:49:42] going to be where everything is
[00:49:43] released. I mean, even Mark Zuckerberg
[00:49:45] had to come back to to Twitter to
[00:49:47] announce, you know, the latest model for
[00:49:48] Meta. That's where everything's
[00:49:50] happening. Study the game there. Um, and
[00:49:53] you've got a great coach right in front
[00:49:54] of you with Greg. So hopefully that, you
[00:49:57] know, people are really taking advantage
[00:49:58] of this time where there's a significant
[00:50:00] alpha from going out, learning, doing it
[00:50:03] yourself, being scrappy with it versus
[00:50:06] waiting for a university to come by and
[00:50:08] and and teach you this cuz that's not
[00:50:09] going to happen anytime soon.
[00:50:11] >> And it's free, right? You can listen to
[00:50:13] this and apply. It's free. So it's just
[00:50:15] like why not, right? Yeah.
[00:50:16] >> Um, Vos, thank you for being generous
[00:50:19] with your with your, as we say on the
[00:50:21] channel, the sauce and the tactics and
[00:50:24] just like breaking this down so clearly.
[00:50:27] Um, I've been following you for a couple
[00:50:29] years now almost. And uh, you're a must
[00:50:33] follow. I'll include links on where you
[00:50:35] can follow Voss um, from Veric Agents in
[00:50:39] the show notes, in the description. you
[00:50:41] know, please comment what you what you
[00:50:43] thought of this episode because I
[00:50:46] enjoyed myself with Voss. I'd like to
[00:50:48] have him back on the podcast again.
[00:50:49] Hopefully, he he's down to come back on.
[00:50:52] Uh, but please let us know. I read every
[00:50:54] single comment. Uh, you want to like and
[00:50:57] subscribe for more of this in your feed?
[00:50:59] Voss, any last words for for the people?
[00:51:02] >> Greg, you're a legend. Thank you for
[00:51:03] having me on. To the people, I believe
[00:51:05] in you. I really believe this is a
[00:51:06] fundamental shift in in how work is
[00:51:08] done. And you are if you're if you're
[00:51:11] listening to Greg and you're and you're
[00:51:12] you're on this p you're watching this,
[00:51:13] you're already a step ahead. I'll be
[00:51:15] reading every single comment, too. If
[00:51:16] any questions you have for me, let me
[00:51:17] know. But I would say like go out and
[00:51:20] get it. Go out and get the job done.
[00:51:22] Make make the most of of your ability to
[00:51:25] understand AI. And it's still so early,
[00:51:27] so get ahead of it while you can. Greg,
[00:51:28] thank you for having me on, man. You're
[00:51:29] a legend.
[00:51:30] >> Amen. All right. Catch you next time.
[00:51:32] Kiss.
