---
record_id: "youtube:kYRB-vJFy38"
video_id: kYRB-vJFy38
title: "LangChain 101: Quickstart Guide"
channel: Greg Kamradt
url: "https://www.youtube.com/watch?v=kYRB-vJFy38"
watched_date: 2023-07-15
watched_at: "2023-07-15T12:00:00Z"
watch_count: 1
duration_seconds: 680
source: youtube-history-browser
added_date: 
history_label: Jul 15, 2023
history_order: 127
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 680
transcript_status: fetched
transcript_content_hash: 4d53fa12b1967257d9f4a9f0b2204a51bef7c1bb0cb54f5e1c5bd702636024da
analysis_mode: health
summary_source: hosted
model_source: hosted
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: sonnet
tagging_model: sonnet
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

This video is the first in a LangChain tutorial series, walking through the official quick-start guide in a Python notebook. The presenter covers setup (`pip install langchain openai`, then setting the OpenAI API key as an environment variable via `os.environ`) and then five examples. (1) Calling an OpenAI LLM directly with temperature 0.9 to get vacation destinations for a pasta lover. (2) Prompt templates, which turn a prompt into a reusable string with an input variable (e.g. `food`) so prompts are easier to manage and scale. (3) Chains, which bundle the prompt template and the LLM so you don't have to pass the prompt in manually, and which support multi-step workflows. (4) Agents, using the "zero-shot-react-description" agent type with SerpAPI (Google search) and the `llm-math` tool. With `verbose=True`, the agent's reasoning is printed as it finds Japan's leader, looks up their age, and calculates the largest prime below it. (5) Memory, using a conversation chain that remembers earlier messages, demonstrated by asking the bot to recall and rephrase the first thing the user said.

To follow along, install `langchain` and `openai`, create an OpenAI API key from the dashboard, and set it as an environment variable. Use the official LangChain quick-start docs for the exact code. Then run the examples in order, since each builds on the last: raw LLM call, then `PromptTemplate`, then `LLMChain`, then an agent, then `ConversationChain`. For the agent example you'll also need `google-search-results` installed and a SerpAPI key, and you should set `verbose=True` to debug the agent's reasoning. Set temperature to 0 if you want deterministic output rather than varied output. The video uses an early LangChain API (the `langchain` and `LLMChain` imports, `initialize_agent`, and `ConversationChain`), and it's from the 2023 era. Newer LangChain versions have changed or deprecated many of these interfaces, so check the current docs before copying the code. The presenter says later videos in the series will go deeper into technical details and practical use cases.

## Transcript

[00:00:00] hello crew and welcome to the very first
[00:00:03] Lang chain tutorial where we go over the
[00:00:06] quick start guide that is held within
[00:00:07] the documentation now if you want to see
[00:00:09] more explicit information about this I
[00:00:11] suggest you head over to their
[00:00:12] documentation and you can check out the
[00:00:14] examples that we're going to run through
[00:00:15] and you can see some code samples and
[00:00:17] get a lot more information here my goal
[00:00:20] for with this python python notebook is
[00:00:23] to give a bit more color commentary for
[00:00:25] the top of it and to explain a little
[00:00:26] bit more about what's happening
[00:00:27] underneath the hood so that you're able
[00:00:29] to understand and run through some
[00:00:31] examples together now the very first
[00:00:33] things that you're going to want to do
[00:00:34] is PIP install line chain and pip
[00:00:36] install open AI I already have both of
[00:00:38] these and so I won't do that again and
[00:00:40] then the next thing that is extremely
[00:00:42] important you're going to want to set
[00:00:45] your open AI API key as an environment
[00:00:48] variable now why is this well because
[00:00:51] we're going to be making some API calls
[00:00:53] to the open AI API
[00:00:55] and in order to do that you need an API
[00:00:57] key and the way that you would do that
[00:00:59] is you'd head over to
[00:01:00] openai.com log in register and under
[00:01:03] your name you'll see that there is an
[00:01:05] API key section in fact let me just show
[00:01:08] you just so you can have it you click on
[00:01:11] API and you're going to log in
[00:01:14] I'm going to log in with my Google again
[00:01:17] and all of a sudden I get my dashboard
[00:01:19] and then underneath your personal
[00:01:20] there's view API keys and you can go
[00:01:22] view all of your API keys that you want
[00:01:24] once you have that you just need to set
[00:01:26] it as an environment variable and in
[00:01:28] order to do that
[00:01:30] in order to do that you need to
[00:01:34] let's see let's get some video back
[00:01:40] beautiful and in order to do that what
[00:01:42] you need to do is you can either set
[00:01:44] this within your terminal and make an
[00:01:45] environment key or environment variable
[00:01:47] that way or what I like to do is I just
[00:01:48] like the import OS and then I like to do
[00:01:51] OS dot Environ in Byron
[00:01:54] open API key and then insert your key
[00:01:58] here
[00:01:59] and then you can just go ahead and run
[00:02:01] that command and then it would set it
[00:02:03] for for your environment here I'm not
[00:02:05] going to do that because I've already
[00:02:06] done enough I've read it okay now let's
[00:02:09] get into the really cool part now that
[00:02:10] we've gotten past the setup so building
[00:02:12] a large language model application what
[00:02:14] we're going to do here is we're going to
[00:02:15] run through about four or five examples
[00:02:16] of some pretty cool use cases using Lane
[00:02:18] chain and if you're not going to see
[00:02:20] anything else in this tutorial series I
[00:02:22] think this is a cool one because it
[00:02:23] might start to get your ideas start to
[00:02:24] start start going so the first thing
[00:02:26] that we're going to do is we're going to
[00:02:27] import from langchain so large language
[00:02:31] model support and in particular we're
[00:02:33] going to open uh we're going to import
[00:02:34] the open AI one
[00:02:36] now
[00:02:37] with this open AI one we're going to
[00:02:39] create a variable that's going to be our
[00:02:41] language model open Ai and then we're
[00:02:43] going to have the temperature at 0.9 now
[00:02:45] if you're not familiar with temperature
[00:02:46] this is the amount of Randomness that is
[00:02:48] going to be in your model and if you
[00:02:51] were to set this to zero or just zero
[00:02:53] then this would be a deterministic model
[00:02:55] meaning you get the same result over and
[00:02:57] over and over again but because we want
[00:02:59] a little bit of variability within our
[00:03:01] data outputs here I'm going to put the
[00:03:03] temperature at 0.9 so we'll go ahead and
[00:03:05] run this okay now this model has been
[00:03:07] initialized
[00:03:09] and so what we can do is we can start to
[00:03:11] feed it some text and we're going to go
[00:03:12] ahead and query that exact uh model
[00:03:15] within open AI API and so what are the
[00:03:19] five vacation destinations for someone
[00:03:21] who likes to eat pasta I'm going to go
[00:03:23] ahead and I'm going to store this prompt
[00:03:25] in a text variable and I'm going to feed
[00:03:27] this text variable to this language
[00:03:29] model and let's see what happens here
[00:03:31] and you'll notice that there's a delay
[00:03:33] and that's because it's actually going
[00:03:34] in querying that model right now and
[00:03:36] then of course we got some really nice
[00:03:38] answers if you like pasta you should go
[00:03:40] to Rome basically anywhere in Italy cool
[00:03:42] wonderful
[00:03:44] let's move on to the next example so
[00:03:46] this is around uh prompt templates now
[00:03:49] prompt templates are going to be an easy
[00:03:51] way for prompt management and what I
[00:03:53] mean by prompt management is you're able
[00:03:55] to uh more easily maneuver and scale the
[00:04:00] different prompts that you're using so
[00:04:01] in this case Lang chain has a prompt
[00:04:04] template object and you can see that
[00:04:06] we're importing it here and so with this
[00:04:08] template we're giving it some input
[00:04:10] variables and you notice that this is a
[00:04:12] list which means we're going to be able
[00:04:13] to do more of these or more input
[00:04:15] variables later but in this case I'm
[00:04:17] just passing one which is the food
[00:04:18] variable and the template is going to be
[00:04:21] what are the five vacation destinations
[00:04:23] for someone who likes to eat food so the
[00:04:25] same thing that we had above but instead
[00:04:27] of pasta I want to turn this into a
[00:04:28] variable which is what I'm going to
[00:04:29] create a template around so let me go
[00:04:31] ahead and import both of those okay cool
[00:04:33] and then what I'm going to do is I'm
[00:04:36] going to print the prompt of where food
[00:04:38] equals dessert so if I go ahead and
[00:04:40] print this what are the five vacation
[00:04:42] destinations for someone who likes to
[00:04:43] eat dessert and then I'm going to take
[00:04:46] this prompt that it just made I can
[00:04:48] store this in a variable if I wanted to
[00:04:49] but I'm just going to create this one
[00:04:50] and I'm going to feed that into the
[00:04:52] large language model let's go ahead and
[00:04:54] print that out and run that
[00:04:56] and all of a sudden you get uh some cool
[00:04:59] dessert destinations and so New York
[00:05:01] City fabulous Tokyo haven't been Paris I
[00:05:04] would love to and I enjoy seeing San
[00:05:06] Francisco on there sometime about 10
[00:05:07] minutes north of San Francisco
[00:05:09] cool so that's around prompts and prompt
[00:05:12] uh management
[00:05:13] so a next really cool one is we're going
[00:05:15] to start to do some chaining now what
[00:05:17] chaining is is when you're going to have
[00:05:19] a multi-step workflows so right now
[00:05:21] we've been asking one question and
[00:05:23] getting one answer back but what if your
[00:05:26] prompt needs multiple questions and
[00:05:29] multiple answers in order to complete
[00:05:31] them and so let's go ahead and let's see
[00:05:33] we can do here
[00:05:35] so we're going to have our prompt
[00:05:37] templates we're going to have openai and
[00:05:38] we're going to have a chain
[00:05:40] and so then all of a sudden we're gonna
[00:05:42] have our this is basically what we did
[00:05:44] beforehand we have our prompt templates
[00:05:45] we're going to have a chain which we're
[00:05:47] going to create and then I'm gonna see
[00:05:48] what is something for uh where somebody
[00:05:51] likes to eat for food
[00:05:53] cool so now we have these chains and
[00:05:55] that are coming over from here now if
[00:05:57] you want more information on change of
[00:05:58] course please head over to their website
[00:06:00] and go check it out but in this one we
[00:06:02] feed both the the
[00:06:04] um the language model and the prompt we
[00:06:06] didn't have to feed the prompt into the
[00:06:07] language model so let's chain took care
[00:06:09] of that for us
[00:06:11] cool now we want to look at agents and
[00:06:13] agents are going to be extremely cool
[00:06:15] because this is where you start to be
[00:06:17] able to have others do work on your
[00:06:19] behalf now in this case what we're going
[00:06:21] to do is we're going to go check out uh
[00:06:23] Google search results so then what's
[00:06:25] really cool is all of a sudden we're
[00:06:26] connecting open AI with Google search
[00:06:29] which is something that we could not do
[00:06:31] with the raw engine in it uh
[00:06:34] specifically so in order to do this you
[00:06:36] need to import or install Google search
[00:06:38] results I already did this and so I
[00:06:39] won't do this again
[00:06:41] then I'm going to import load tools
[00:06:43] initialize agent and open API or open AI
[00:06:46] so very first thing is we're going to
[00:06:48] step instantiate our language model and
[00:06:52] then we're going to use a tool called
[00:06:54] serve API and this is where you can go
[00:06:55] and scrape basically Google searches and
[00:06:57] I've already imported my API key so I
[00:06:59] won't bore you here with that now the
[00:07:02] other thing that we're going to do is
[00:07:03] we're also going to import llm math and
[00:07:05] this is going to be another library or
[00:07:07] another package that Lang chain supports
[00:07:10] and this is going to help us do some
[00:07:11] really cool math so all of a sudden
[00:07:13] we're going to load some tools and we're
[00:07:14] going to load in the large language
[00:07:16] model that comes with it and that is
[00:07:18] because LM math needs that language
[00:07:20] model cool we got that and then we're
[00:07:23] going to initialize these agents
[00:07:24] initialize this single agent so we're
[00:07:27] going to initialize the agent and we're
[00:07:28] going to pass in the tools that have
[00:07:30] been loaded up above here we're going to
[00:07:32] pass in our language model and we're
[00:07:34] going to pass in an agent type now this
[00:07:36] may look like gibberish zero shot react
[00:07:39] description however if you head over to
[00:07:42] the ancient documentation there's other
[00:07:44] agent types that you can use depending
[00:07:45] on your use case and for this one I want
[00:07:48] to do verbose equals true and the reason
[00:07:50] why we do verbose equals true is because
[00:07:52] it is going to print out all the many
[00:07:56] steps and all the information that it's
[00:07:58] thinking about in the first place this
[00:08:00] helps us debug what's going on and
[00:08:01] really see underneath the hood so what's
[00:08:04] cool about this one is I can do a longer
[00:08:06] prompt
[00:08:07] and that not only a longer prompt but
[00:08:09] this prompt needs multiple steps in
[00:08:12] order to answer so who is the current
[00:08:14] leader of Japan
[00:08:15] what is the largest prime number that is
[00:08:18] smaller than their age so it's going to
[00:08:20] go grab that leader of Japan and do the
[00:08:22] smallest uh prime number below them so
[00:08:25] let's go ahead and let's run this and
[00:08:27] then all of a sudden it says oh I'm
[00:08:28] doing a new executor chain and this is
[00:08:30] what's really sweet is you can see what
[00:08:33] is it thinking about what it needs to do
[00:08:34] in order to do your request so in this
[00:08:38] case they need to find out who the
[00:08:40] largest prime prime minister is of Japan
[00:08:44] and then the prime number that's smaller
[00:08:46] than the H so it goes and finds the
[00:08:48] current prime minister of Japan has the
[00:08:50] right answer
[00:08:51] and then it needs to find their age so
[00:08:53] it goes into searches that and it finds
[00:08:55] his age sweet and then it needs to find
[00:08:57] the largest prime number smaller than
[00:09:00] that so it goes goes and gets the
[00:09:01] calculator finds 65 knows the final
[00:09:04] answer and it says the current leader of
[00:09:06] Japan is this dude and has the largest
[00:09:08] prime number that is smaller than his
[00:09:09] age of 61 because he's 65.
[00:09:12] that's cool
[00:09:14] and then finally let's move on to memory
[00:09:17] so this is the concept of let me see if
[00:09:19] I can make this a little smaller no let
[00:09:21] me zoom out just a little bit
[00:09:26] oh that's annoying okay well this is the
[00:09:30] concept of
[00:09:31] you know I'm gonna pause the video just
[00:09:33] actually now let's keep that in there um
[00:09:34] this is the concept of having memory so
[00:09:36] this means that your agent can remember
[00:09:38] things that you've done in the past and
[00:09:41] so for example we have openai and we are
[00:09:43] going to import our conversation chain
[00:09:45] so we have a large language model and we
[00:09:47] have our conversation chain that we're
[00:09:48] going to get uh instantiated here and
[00:09:50] again we did for both equals true so it
[00:09:52] prints out all that really cool
[00:09:53] information for us
[00:09:54] so now what I'm going to do is we're
[00:09:56] going to start to have a conversation
[00:09:57] with this chatbot so in this case I'm
[00:10:00] going to say hi there and you can see
[00:10:02] here that it says hi there and it went
[00:10:04] and grabbed the response from the AI and
[00:10:07] in this case it's the open AI
[00:10:09] um open AI API and it says hi there it's
[00:10:12] nice to meet you how can I help you
[00:10:13] today and I said I'm doing well just
[00:10:15] having a conversation with open with an
[00:10:17] AI so there's my first there's my first
[00:10:20] uh
[00:10:22] uh text to it I get a response here's my
[00:10:25] second text it's thinking and then all
[00:10:27] of a sudden it says great what do you
[00:10:28] want to talk about
[00:10:29] I'm saying
[00:10:31] I want to double check that the memory
[00:10:33] actually works and so in this prompt I'm
[00:10:35] going to say what is the first thing
[00:10:37] that I said to you so that I can see
[00:10:38] that it goes back and remembers that it
[00:10:40] says you said hi there
[00:10:42] nice what is an alternative phrase for
[00:10:46] the first thing that I said there and so
[00:10:48] I'm making sure that it has to actually
[00:10:49] go understand what was the first thing
[00:10:50] that I said and understanding what is an
[00:10:53] alternative phrase for it and I'll turn
[00:10:55] my phrase the first thing you said to me
[00:10:57] is greetings
[00:10:59] pretty cool how it can go back and see
[00:11:00] the memory of what we chatted about now
[00:11:03] that is a quick start guide for what
[00:11:05] Lang chain is and how you can use some
[00:11:07] interesting examples there what we're
[00:11:09] going to do is we're going to go a lot
[00:11:10] deeper into some technical details and
[00:11:12] some more very actionable use cases for
[00:11:15] you so uh enjoy and follow us on the
[00:11:18] next video
