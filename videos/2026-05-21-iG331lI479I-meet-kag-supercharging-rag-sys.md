---
video_id: iG331lI479I
title: "Meet KAG: Supercharging RAG Systems with Advanced Reasoning"
channel: Prompt Engineering
url: "https://www.youtube.com/watch?v=iG331lI479I"
watched_date: 2026-05-21
watched_at: "2026-05-21T12:00:00Z"
watch_count: 1
duration_seconds: 880
source: youtube-history-browser
history_label: Thursday
history_order: 118
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 88
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Knowledge Augmented Generation (KAG) enhances standard RAG by integrating knowledge graphs with semantic retrieval and multi-hop reasoning. The system uses a two-stage process: index creation extracts entities and relationships from documents using LLMs and Open IE, normalizes entities, and builds knowledge models (for people, organizations, dates, locations, etc.); retrieval decomposes complex queries into sub-questions, performs hybrid search combining knowledge graphs and semantic similarity, and applies combined reasoning from both LLMs and knowledge graphs before final generation. On benchmarks like HotpotQA, KAG outperforms existing methods by preserving logical connections between entities that standard RAG loses during chunking.

To implement KAG locally: install Docker Desktop, download the docker-compose.yaml file, and run Docker compose commands to spin up MySQL, Neo4j, and the OpenSPG server. Configure your knowledge base with a database URI, an LLM provider (DeepSeek, local models, or any OpenAI-compatible API), and an embedding model (e.g., BGE-M3 via Ollama). Upload documents through the web interface at localhost to build knowledge graphs, then test by running queries—the system will automatically decompose them into sub-questions, retrieve relevant chunks, reason over them, and return combined answers. Watch for upcoming KAG updates (custom schemas, visual queries, multi-model flexibility) for potentially better performance.

## Transcript

[00:00:00] you probably have heard of retrial
[00:00:02] augmented generation or rag but today
[00:00:05] we're going to talk about knowledge
[00:00:06] augmented generation or KAG now one of
[00:00:09] the biggest limitation of standard rag
[00:00:11] is the chunking process since it loses
[00:00:15] logical connections between entities
[00:00:18] since each retrieved chunk is treated
[00:00:21] individually during the generation
[00:00:24] process that's why we have approaches
[00:00:26] like graph rag or light rag that uses
[00:00:29] knowledge F to preserve The Logical
[00:00:32] connection between entities knowledge
[00:00:35] augmented generation takes it one step
[00:00:37] further by adding multihop question
[00:00:40] answering and reasoning capabilities
[00:00:43] which are essential in complex reasoning
[00:00:45] tasks first in this video I'll show you
[00:00:48] how it works and then I'll show you how
[00:00:51] to set it up on your local machine okay
[00:00:54] so just like a standard R system it has
[00:00:56] two steps the first one is the index
[00:01:00] creation process and the second step is
[00:01:03] the retrieval or quering process the
[00:01:05] index creation process has multiple
[00:01:07] different steps so first we take our
[00:01:10] documents extract text from those pass
[00:01:12] it onto a semantic chunking processor
[00:01:15] then we use an llm along with knowledge
[00:01:20] models for information extraction it
[00:01:23] uses open IE for extraction of subject
[00:01:28] relationship and the object of that
[00:01:30] relation along with knowledge cfts to
[00:01:33] preserve those relationship between
[00:01:35] different entities now there is a
[00:01:37] special alignment process which removes
[00:01:41] dis ambiguities among these entities and
[00:01:45] standardize them both within the
[00:01:47] documents as well as these knowledge
[00:01:50] models that are built in now to
[00:01:53] understand those knowledge models let's
[00:01:55] look at an example of an entity of a
[00:01:57] person the person can have multiple
[00:02:01] different attributes that is going to be
[00:02:03] the taxonomy of the person and then we
[00:02:06] can use that taxonomy to figure out the
[00:02:08] relationship between this specific
[00:02:10] object with other objects or entities
[00:02:13] that are present in our knowledge base
[00:02:16] here are some other examples of
[00:02:18] different entity types or knowledge
[00:02:20] models that are present we're going to
[00:02:22] look at some of them later in the video
[00:02:25] the second part is theer retrieval
[00:02:28] process for which KAG uses logical form
[00:02:31] solver so the way this works is that
[00:02:34] whenever you have a user query it first
[00:02:37] does planning so let's say if it's able
[00:02:39] to divide a user query into multiple
[00:02:42] different queries by using query
[00:02:44] decomposition or can create multiple
[00:02:47] different queries which can enhance the
[00:02:50] Ral it will actually plan that first
[00:02:54] then it's going to do uh retrieval for
[00:02:56] each of those queries and reason on top
[00:02:59] of of each of the retrieved results now
[00:03:03] this reasoning combines both the llm
[00:03:06] reasoning plus the knowledge graph
[00:03:08] reasonings and those combined results
[00:03:10] are passed on to the edlm for final
[00:03:13] generation this multi-step process
[00:03:16] results in better retrieval and better
[00:03:19] generation and as a result it does a
[00:03:21] really good job both in single step and
[00:03:24] multi-step retrieval on multihop QA data
[00:03:27] sets especially if you look at the
[00:03:30] Hotpot QA data set it outperforms all
[00:03:33] the existing methods even on the other
[00:03:36] two data sets the performance is really
[00:03:39] comparable to the existing methods this
[00:03:42] is a very interesting approach that does
[00:03:44] a hybrid search using knowledge craft
[00:03:47] plus the embedding based sematic search
[00:03:50] but also combines uh this hybrid
[00:03:53] reasoning on top of it i' highly
[00:03:55] recommend to read the paper if you're
[00:03:56] interested next I'm going to show you
[00:03:58] how to set this up on your local machine
[00:04:01] this is an open source project from open
[00:04:03] SPG under the Apache 2.0 license and
[00:04:08] they are also the kind sponsors of this
[00:04:11] video I am running this on Mac OS but
[00:04:15] the installation and setup instructions
[00:04:16] are going to remain the same for Linux
[00:04:19] and window users as well there are are
[00:04:22] two different ways in which you can use
[00:04:25] KAG one is through the their graphical
[00:04:28] user interface and the second one is
[00:04:30] through the python client in this video
[00:04:33] I'm going to show you the graphical user
[00:04:36] interface everything is running under a
[00:04:38] Docker container so you will need to
[00:04:41] install the docker Des desktop app on
[00:04:44] your local machine and select the
[00:04:46] appropriate version based on your
[00:04:48] operating system the installation is
[00:04:50] going to be a twostep process so first
[00:04:53] we're going to download this Docker
[00:04:56] composed. yaml file which has all the
[00:04:59] configur ation needed for setting up our
[00:05:02] Docker container and after that we are
[00:05:04] going to actually create that Docker
[00:05:06] container on our local machine and run
[00:05:09] it okay so first I need to run this curl
[00:05:12] command to download the docker composed.
[00:05:15] yl file if I type LS you can see that
[00:05:19] the file is already downloaded on my
[00:05:21] local machine next we're going to create
[00:05:24] the docker container by running this
[00:05:26] command now that's going to take some
[00:05:28] time but if you want to see what is
[00:05:31] actually running you can run this Docker
[00:05:34] compose up- D command and these are the
[00:05:38] three different things that are running
[00:05:41] one is a mic SQL Server the other one is
[00:05:45] the new 4J that is going to be used for
[00:05:48] storing our knowledge graph and then the
[00:05:52] actual open SPG server which is running
[00:05:56] the CAG or knowledge augment generation
[00:06:00] server now in order to access that you
[00:06:02] will need to go to this URL on your
[00:06:05] local machine so here is the interface
[00:06:08] that you're going to see to create a new
[00:06:10] retrieval task we'll first need to go
[00:06:12] and uh click on create knowledge base so
[00:06:16] here we'll need to provide a few
[00:06:18] settings you need to provide both
[00:06:20] Chinese and English name both can be
[00:06:22] exactly the same thing the only
[00:06:24] difference is that for the English name
[00:06:27] the first letter is supposed to be
[00:06:29] capital okay so I already created a
[00:06:31] knowledge base with the name KAG so here
[00:06:33] are some of the configurations that I
[00:06:35] used so first we need to provide the
[00:06:37] storage configurations the database name
[00:06:40] is KAG here's the password since
[00:06:42] everything is going to be stored in a
[00:06:44] new 4G database so we're using that URI
[00:06:47] along with the user next we need to set
[00:06:50] up our llm llm is going to be used for
[00:06:54] entity extractions plus all the
[00:06:57] relationships that is going to find
[00:07:00] and all the reasoning tasks now for my
[00:07:02] llm I'm using deep seek as a API
[00:07:06] provider and the reason is that deeps VT
[00:07:09] seems to be the best llm out there when
[00:07:12] it comes to open weight llms and even is
[00:07:15] able to beat something like CLA 3.5
[00:07:18] Sonet and gbd 40 on some tasks which is
[00:07:22] pretty impressive but you can use any
[00:07:24] llm which you are running locally or a
[00:07:28] proprietary model as long as it's using
[00:07:31] the open API standard so here we are
[00:07:34] providing the base URL the model name is
[00:07:37] uh DC chart and you will also need to
[00:07:40] provide your API key next we need to set
[00:07:43] up our EMB model this is going to be
[00:07:46] used for semantic extraction or a
[00:07:49] semantic similarity search again you
[00:07:52] need either a proprietary API or a local
[00:07:56] running model which follows the open API
[00:07:59] St
[00:08:00] so in this case we are going to be
[00:08:02] hosting our model locally using AMA and
[00:08:05] for that you first need to download AMA
[00:08:08] next you need to choose the embedding
[00:08:10] model that you want to use in my case I
[00:08:13] want to use the BG M3 which is one of
[00:08:16] the best open weight embeding model out
[00:08:18] there so you just need to pull that
[00:08:20] model using oama pull and then provide
[00:08:23] the model name and here I am providing
[00:08:26] the model name as BG M3 the Vector
[00:08:29] Dimensions that I'm using is 1024 you
[00:08:33] can also provide these optional
[00:08:35] parameters extracts the information and
[00:08:38] look at the language in it's going to
[00:08:40] process the prompt so I'm going to be
[00:08:42] setting this to English Okay so once you
[00:08:45] create your knowledge base then you can
[00:08:48] go to knowledge base management now here
[00:08:51] you can see I already have H some tasks
[00:08:54] created so um here's the CAG paper that
[00:08:58] is embedded and uh a knowledge a
[00:09:00] knowledge uh graph was created on top of
[00:09:03] it if you want to create another task
[00:09:05] just click on create task I'm going to
[00:09:07] call it KAG and we're going to upload
[00:09:10] the CAG paper click on next you can
[00:09:14] change the uh chunk size or Max uh
[00:09:18] segment length I'll keep it to default
[00:09:21] there is a extraction model so I'm going
[00:09:23] to keep that to default as well and then
[00:09:27] we'll click on finish now the depending
[00:09:29] on the size of the document this can
[00:09:31] take some time but let's look at the
[00:09:34] logs so first it starts reading the
[00:09:36] document then it's going to use a PDF
[00:09:39] reader because we selected a PDF file to
[00:09:43] chunk the document and then do the
[00:09:46] extraction of entities and the
[00:09:48] relationships now once the extraction
[00:09:51] process is complete you can look at the
[00:09:53] extraction results as well let me show
[00:09:55] you the specialized knowledge model that
[00:09:58] KAG uses
[00:10:00] they try to extract information based on
[00:10:02] different knowledge models for example
[00:10:05] if there is anything related to Medicine
[00:10:07] building transport astronomy Natural
[00:10:09] Sciences people dates organizations
[00:10:12] semantic Concepts or artificial objects
[00:10:16] now if you go to your tasks uh you can
[00:10:19] actually see some of these things
[00:10:21] extracted whenever it's creating this
[00:10:23] knowledge graph so let's look at an
[00:10:25] example of this Ino 2 that I previously
[00:10:28] uploaded
[00:10:29] so here's a query that I ran and within
[00:10:32] the query it was looking at the due date
[00:10:34] of the invoice that was paid on but if
[00:10:38] you look at the overall schema on any
[00:10:41] you have a address so it figures out
[00:10:44] there is a geographical location there
[00:10:46] are organization mentioned there's a due
[00:10:49] date on it and there are some semantic
[00:10:51] Concepts right so whenever it's creating
[00:10:53] the knowledge graph it will look at
[00:10:56] these specialized items or knowledge
[00:10:58] models
[00:10:59] and then try to figure out those
[00:11:01] relationship between the different uh
[00:11:04] knowledge models that are present based
[00:11:07] on the length of your document this
[00:11:09] indexing process can take a while but I
[00:11:12] have previously created an index and
[00:11:14] knowledge graph for the can paper so
[00:11:16] we're going to use that as an example
[00:11:19] for the query part you just need to come
[00:11:21] and click on knowledge based question
[00:11:23] answer so let me ask a new query the
[00:11:26] query is going to be what is c
[00:11:30] and why it's better than standard rag so
[00:11:36] if I run this query uh this will take
[00:11:38] some time because it not only have to U
[00:11:41] do the extraction of the information but
[00:11:44] it also has to reason now there are some
[00:11:46] interesting things that that are
[00:11:47] happening so here is the original query
[00:11:51] but it decomposes that query into two
[00:11:54] parts the first is what is KAG and the
[00:11:57] second is why is KAG better than than
[00:11:59] standard rag then it takes the first
[00:12:02] query and basically extract the required
[00:12:05] information now it's using the SPO
[00:12:08] retriever this is the specialized
[00:12:10] retriever that they have come up with
[00:12:12] the same thing happens for the second
[00:12:15] part of the question which is why KAG is
[00:12:17] better than standard Rag and here's the
[00:12:20] response that it gets based on the
[00:12:23] retrieved chunks from the document and
[00:12:25] at the end it combines both of these
[00:12:28] together to generate the final answer
[00:12:31] for us so it says CAG or knowledge
[00:12:33] augmented generation is an advanced
[00:12:35] framework that integrates external
[00:12:37] knowledge particularly from knowledge
[00:12:39] graphs to enhance it generation
[00:12:42] capabilities and it's better than
[00:12:44] standard rack because it has explicit
[00:12:47] semantic knowledge entity normalization
[00:12:50] differential knowledge retrieval
[00:12:52] integration of semantic types and
[00:12:54] relationships addressing rag limitation
[00:12:57] and enhancing performance so compared to
[00:13:00] a standard rack system it's using this
[00:13:02] reasoning process along with the
[00:13:06] retrieval process to give us better
[00:13:08] answers so here was another example when
[00:13:11] I was doing retrieval on that invoice
[00:13:13] data my query was what is the total
[00:13:15] amount on the in that needs to be paid
[00:13:18] and it generated these different queries
[00:13:21] so it basically decomposed that query
[00:13:23] into multiple queries what is the
[00:13:25] invoice that needs to be paid what is
[00:13:27] the total amount on this inv and return
[00:13:30] the total amount and for each one of
[00:13:32] them it basically got the answers and
[00:13:35] then combined them together to give us
[00:13:37] the final answer as I mentioned before
[00:13:39] you can do all of this through python
[00:13:42] code so if there is interest let me know
[00:13:44] I'll make a follow-up video so this was
[00:13:47] a quick video on knowledge augmented
[00:13:50] generation which is a very interesting
[00:13:52] take on combining knowledge cfts with
[00:13:56] semantic retrieval and highly recommend
[00:13:59] to check it out the project itself is
[00:14:02] open uh Source under Apache
[00:14:06] 2.0 uh the authors are also releasing a
[00:14:08] new version probably in a week or so but
[00:14:11] that is going to have custom schema and
[00:14:13] visual queries and you'll be able to use
[00:14:17] different models at different stages
[00:14:19] which could potentially improve
[00:14:21] performance so we'll highly recommend to
[00:14:23] check out the updated kab repo in a week
[00:14:26] or
[00:14:27] so anyways if you're interested in
[00:14:30] retrieval augmented generation or
[00:14:32] different variants of it or agents make
[00:14:35] sure to subscribe to the channel thanks
[00:14:37] for watching and as always see you in
[00:14:39] the next one
