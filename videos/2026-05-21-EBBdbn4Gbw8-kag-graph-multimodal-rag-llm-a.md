---
video_id: EBBdbn4Gbw8
title: KAG Graph + Multimodal RAG + LLM Agents = Powerful AI Reasoning
channel: Gao Dalie (高達烈)
url: "https://www.youtube.com/watch?v=EBBdbn4Gbw8"
watched_date: 2026-05-21
watched_at: "2026-05-21T12:00:00Z"
watch_count: 1
duration_seconds: 661
source: youtube-history-browser
history_label: Thursday
history_order: 74
watched_at_precision: date-from-history-label
watched_percent: 36
estimated_watched_seconds: 238
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

The video introduces KAG (Knowledge Augmented Generation), a framework that combines knowledge graphs with RAG to overcome RAG's limitations—poor reasoning about relationships, insensitivity to logic and numerical values, and incomplete retrieval. KAG uses semantic reasoning and hybrid problem-solving to achieve 19.6% and 33.5% performance improvements on benchmark datasets. The architecture has three components: KAG Builder (creates offline indexes with LLM-compatible knowledge representation), KAG Solver (hybrid reasoning engine combining LLM, logical, and mathematical reasoning), and KAG Model (optimized language model). The demo shows the full workflow: uploading PDFs to extract structured knowledge, building a knowledge graph, then querying complex questions like "What are the model names being fine-tuned?" with accurate, logical answers. KAG differs from GraphRAG by emphasizing semantic alignment and logical planning for professional domains rather than simple retrieval-generation.

To implement KAG yourself, install Docker Desktop, pull the open SPG server, and configure a Neo4j database for graph storage and an API key (ChatGPT, DeepSeek, or local Llama). Create a knowledge base through the UI, upload documents (PDFs, CSVs, etc.), and the system automatically extracts entities, relationships, and structured data. You can query the knowledge using the chatbot interface or directly through Neo4j browser queries. KAG is open-source, so you can inspect the code and adapt it for custom use cases—whether you need professional Q&A, document analysis, or domain-specific reasoning that relies on relationships rather than keyword similarity.

## Transcript

[00:00:00] as AI technology booms rag is becoming a
[00:00:02] GameChanger quickly becoming Partners in
[00:00:05] problem solving and domain applications
[00:00:07] and this is what makes rag unique
[00:00:10] however rag has problems such as a large
[00:00:12] gap between Vector similarity and
[00:00:14] knowledge reasoning relevance and
[00:00:16] insensitivity to knowledge logic such as
[00:00:19] numerical values time relationships
[00:00:21] expert rules Etc which hinder the
[00:00:23] implementation of Professional Knowledge
[00:00:25] Services can you imagine you have a
[00:00:28] chatbot that requires reasoning based B
[00:00:30] on specific relationships between
[00:00:32] knowledge fragments to collect
[00:00:33] information related to answering
[00:00:35] questions however rag usually relies on
[00:00:39] the similarity of text or vectors to
[00:00:41] retrieve reference information which may
[00:00:43] lead to incomplete and repeated search
[00:00:45] results that's where KAG comes in
[00:00:48] knowledge augmented generation aims to
[00:00:50] fully utilize the advantages of
[00:00:52] knowledge graphs and Vector retrieval
[00:00:55] and B directionally enhance large
[00:00:57] language models and knowledge graphs to
[00:00:59] solve these problem problems knowledge
[00:01:01] alignment based on semantic reasoning
[00:01:03] KAG significantly outperforms methods
[00:01:06] such as naive Rag and hippo rag in
[00:01:09] multihop question answering tasks with a
[00:01:11] relative Improvement of
[00:01:13] 19.6% in the F1 score on Hotpot QA and
[00:01:17] 33.5% on two Wiki these performance
[00:01:20] leaps are mainly attributed to the more
[00:01:22] efficient index construction knowledge
[00:01:25] alignment and development of hybrid
[00:01:27] problemsolving libraries in the
[00:01:28] framework so so let me give you a quick
[00:01:31] demo of a live chatbot to show you what
[00:01:33] I mean we have two separate parts first
[00:01:36] we start with Knowledge Management where
[00:01:38] I will upload a PDF that includes all
[00:01:41] the charts tables and images let me show
[00:01:44] you how caj extracts data Kaji employs a
[00:01:47] knowledge representation model to
[00:01:48] organize information into a structured
[00:01:50] format making it compatible with both
[00:01:53] structured and unstructured data next
[00:01:55] Kaji uses a mutual indexing mechanism
[00:01:58] that links knowledge graphs with
[00:01:59] original text chunks its indexing allows
[00:02:02] for efficient retrieval of relevant
[00:02:04] information based on user queries and
[00:02:07] connect structured knowledge with
[00:02:08] unstructured data please stay tuned
[00:02:10] until the end because I will show you
[00:02:12] something cool how you can use SQL and
[00:02:15] neo4j to extract your data then we move
[00:02:18] to the knowledge-based question and
[00:02:20] answer section I will ask it a
[00:02:22] straightforward question what is net
[00:02:24] income in
[00:02:25] 2024 when I pose the question C
[00:02:28] processes the query to understand its
[00:02:30] intent and context this involves
[00:02:33] identifying key entities relationships
[00:02:36] and the overall structure of the
[00:02:37] question afterwards k a generates a
[00:02:40] logical form based on my query it then
[00:02:43] retrieves relevant information from the
[00:02:45] knowledge graph including entities
[00:02:47] relationships or triples as well as data
[00:02:49] aggregation to generate a clear and
[00:02:52] understandable answer for the
[00:02:54] user in this video I'll quickly go over
[00:02:57] the document so you are 100% up to to
[00:03:00] speed on what is Kaji what it features
[00:03:02] how it works what is difference between
[00:03:04] graph Rag and kagi and even we'll be
[00:03:07] installing applications on screen that
[00:03:09] you can copy paste and adapt for your
[00:03:12] uses definitely stay tuned throughout
[00:03:14] the end of this video If you guys
[00:03:17] haven't followed me I highly recommend
[00:03:19] that you do so so you can stay up to
[00:03:21] date with the latest AI news lastly make
[00:03:24] sure you guys subscribe turn the
[00:03:26] notification Bell like this video and
[00:03:29] check out previous videos because there
[00:03:31] is a lot of content that you will
[00:03:33] definitely benefit from so that thought
[00:03:35] let's get right back into the video the
[00:03:38] knowledge aware graph generator
[00:03:39] framework is open source and fully
[00:03:42] utilizes the complimentary advantages of
[00:03:45] Knowledge Graph and rag technology it
[00:03:47] not only integrates the graph structure
[00:03:50] into the knowledge base but also
[00:03:52] integrates the semantic types relations
[00:03:54] and knowledge graph question answering
[00:03:56] of the knowledge graph into knowledge
[00:03:58] aware graph generator the knowledge
[00:04:00] aware graph generator framework enhances
[00:04:03] professional question answering with key
[00:04:05] features like llm friendly knowledge
[00:04:08] representation which helps large
[00:04:10] language models understand and utilize
[00:04:12] knowledge graphs effectively it's mutual
[00:04:15] indexing links structured knowledge
[00:04:17] graphs with unstructured text for
[00:04:19] seamless information retrieval while The
[00:04:22] Logical form guided hybrid reasoning
[00:04:24] engine enables Advanced reasoning such
[00:04:27] as planning and math to tackle complex
[00:04:29] questions s semantic reasoning ensures
[00:04:32] knowledge alignment with user queries
[00:04:34] improving accuracy by matching context
[00:04:36] and intent and improv natural language
[00:04:39] processing boosts K's ability to
[00:04:42] understand reason and generate clear and
[00:04:44] precise answers the KAG architecture
[00:04:47] consists of three core components KAG
[00:04:50] Builder KAG solver and KAG model KAG
[00:04:54] Builder is responsible for building
[00:04:56] offline indexes this module proposes
[00:04:59] knowledge representation framework
[00:05:01] compatible with large language models
[00:05:03] and implements a mutual indexing
[00:05:05] mechanism between knowledge structures
[00:05:08] and text fragments Ki solver introduces
[00:05:12] a hybrid reasoning engine Guided by
[00:05:14] logical forms integrating large language
[00:05:18] model reasoning knowledge reasoning and
[00:05:20] mathematical logic reasoning semantic
[00:05:23] reasoning is used for knowledge
[00:05:24] alignment to enhance the accuracy of KAG
[00:05:27] Builder and KAG solver in knowledge
[00:05:30] representation and retrieval KAG model
[00:05:33] is based on a general language model and
[00:05:35] optimizes the specific capabilities
[00:05:37] required by each module thereby
[00:05:39] improving overall module performance KAG
[00:05:42] and graph rag differ primarily in their
[00:05:44] integration and reasoning capabilities
[00:05:47] KAG fully leverages knowledge graphs by
[00:05:49] incorporating semantic relationships and
[00:05:51] employing a hybrid reasoning engine for
[00:05:53] logical retrieval and numerical tasks
[00:05:56] enabling structured and complex problem
[00:05:58] solving it en enhances General large
[00:06:00] language model capabilities in
[00:06:03] professional domains with improved
[00:06:04] semantic alignment and tailored natural
[00:06:07] language understanding natural language
[00:06:09] inference and natural language
[00:06:11] generation in contrast graph rag focuses
[00:06:14] more on retrieval and generation with
[00:06:17] less emphasis on semantic reasoning
[00:06:20] logical planning and domain specific
[00:06:22] performance potentially limiting its
[00:06:25] Effectiveness for complex queries and
[00:06:27] professional applications the knowledge
[00:06:29] of Ware graph generator backend service
[00:06:31] is based on the open SPG Knowledge Graph
[00:06:34] construction framework which we have
[00:06:36] discussed first build the graph server
[00:06:39] using the official open SPG server
[00:06:42] documentation let's go to the docker
[00:06:44] website and download the docker file on
[00:06:47] Windows once you install Docker desktop
[00:06:49] we open the terminal and run the
[00:06:51] following command then we check our
[00:06:54] services are up and running and run this
[00:06:56] command to ensure everything is working
[00:06:58] correctly check the logs of the main
[00:07:00] service and run this command copy the
[00:07:03] link and paste it into the browser to
[00:07:05] access the op SPG CAG product interface
[00:07:09] then we click create knowledge base
[00:07:11] first we start choosing a Chinese name
[00:07:13] for the knowledge base next you'll need
[00:07:15] an English name remember it must start
[00:07:17] with a capital letter contain at least
[00:07:20] three characters and only include
[00:07:22] letters and numbers in this video I will
[00:07:25] name it something like k a demo after
[00:07:28] that we'll set up the graft storage
[00:07:30] configuration we copy a simple Json
[00:07:33] setup by default you can use the local
[00:07:35] neo4j database now let's move to the
[00:07:39] model configuration choose a model like
[00:07:41] chat GPT or deep seek add your API key
[00:07:45] and other details in Json format for
[00:07:48] embedding I will use open AI embedding
[00:07:50] you can also use for embedding as it has
[00:07:54] some cool embedding models lastly you'll
[00:07:57] need to set the language for your
[00:07:58] knowledge base
[00:08:00] either Chinese or English I will keep it
[00:08:02] as the default keep in mind that you can
[00:08:05] set up the chatbot fully locally using
[00:08:08] Alma if you want to know how to do it
[00:08:11] please check this document once you save
[00:08:13] the configuration successfully you will
[00:08:15] see that the small box includes
[00:08:17] Knowledge Management and question and
[00:08:20] answer in this case you didn't save the
[00:08:23] configuration successfully you may face
[00:08:25] the problem that I faced when I
[00:08:27] installed Neo j4 as an unknown ER eror
[00:08:30] the way to solve this problem is simple
[00:08:32] just check if release open SPG neo4
[00:08:36] starts successfully then rerun the
[00:08:38] container let's click on Knowledge
[00:08:41] Management once you click we create a
[00:08:43] task name your knowledge task and choose
[00:08:46] the local file to upload files with all
[00:08:49] supported type file suffixes through the
[00:08:52] knowledge based management page to carry
[00:08:56] out the knowledge based construction
[00:08:57] process we click on the next Next Step
[00:09:00] make Mac segment length as default and
[00:09:02] hit the next step once you see this
[00:09:05] screen keep it as default and hit the
[00:09:07] Finish button once you finish you can
[00:09:11] create tasks as much as you can the more
[00:09:14] knowledge the better your chatbot is
[00:09:16] note you need to wait until the icon
[00:09:19] turns green for the task status to be
[00:09:21] completed to check the progress click on
[00:09:24] the log view icon to ensure all content
[00:09:27] has been extracted successfully as shown
[00:09:30] one of the many features I like about op
[00:09:32] SGP is that we can use the neo4 J
[00:09:35] browser to extract knowledge and check
[00:09:37] the knowledge extraction results this
[00:09:39] feature is really helpful for anyone who
[00:09:41] wants to track the data and ensure that
[00:09:43] the chatbot generates accurate responses
[00:09:45] using a cipher query so let's click on
[00:09:49] Knowledge Management to interact with
[00:09:51] the chatbot and test it out and I will
[00:09:53] ask the chatbot the complex question
[00:09:55] from Kaji paper what are the names of
[00:09:58] the models they fine-tuning free if you
[00:10:01] take a look you'll see that when I asked
[00:10:02] the question the chatbot used logical
[00:10:05] reasoning to generate the output the
[00:10:07] answer is accurate well structured easy
[00:10:10] for non-technical users to understand
[00:10:13] and more precise without any unrelated
[00:10:15] information the cek framework is still
[00:10:18] in the early stages of development so
[00:10:20] there's room for changes and
[00:10:22] improvements with new features like
[00:10:24] custom schemas and visual queries
[00:10:26] knowledge aware graph generator not only
[00:10:29] enhances the accuracy and efficiency of
[00:10:32] knowledge extraction and question
[00:10:34] answering but also strengthens its
[00:10:36] foundation these updates pave the way
[00:10:38] for developing more robust and reliable
[00:10:41] Professional Knowledge Services plus the
[00:10:44] abstract generation classes have been
[00:10:46] optimized if we try using different
[00:10:48] Scale Models at various stages cac's
[00:10:51] performance could get even better and
[00:10:53] hey since open CAG is open source we
[00:10:55] should take advantage of the code and
[00:10:57] see how it can help us create custom
[00:10:59] solutions for whatever we need
