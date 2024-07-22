Backend Voice Conversation SDK for LLM Apps -     Assignment 
Objective
Develop a streamlined library enabling the creation of voice bots powered by Large Language Models (LLMs) with minimal latency. The primary goal is to empower developers to transform LLM-based chatbots into voice bots, facilitating interactions through voice commands and responses.
Key Features
Convert Speech to Text (STT): Process user voice inputs into text of 20 seconds max. 
Interact with LLM: Utilize the converted text to query a Large Language Model and obtain a text response for the question asked by the person. 
Convert Text to Speech (TTS): Transform the LLM response into speech.
Stream Audio Back to Frontend: Ensure the audio output is streamed back to the user with low latency.
Assignment Scope
The library need to expose following two methods
1. Setup
Functionality: Initialize the SDK and setup the STT, TTS and LLM engines to be used
Parameters
STT Config
Name of the engine (For purpose of assignment only Deepgram is supported)
https://deepgram.com/ Candidates can access this for an API.
API Key can be obtained for free. 
TTS Config
Name of the engine (For purpose of the assignment only Deepgram or OpenAI is supported)
API Key
LLM Config
Name of the engine (For purpose of assignment only OpenAI is supported)
API Key
System Prompt - Must be written by the candidate. 
2. Stream Conversation
Functionality: Process an input audio stream and return an audio stream as output.


Parameter


Input Stream (An interface implementing “read” method with a chunksize parameter). For sake of assignment you can use PyAudio to stream from microphone and implement a PyAudioInputStream

Output Steam (An interface implementing write method). For sake of assignment you can use PyAudio as output stream to play on the speaker and implement a PyAudioOutputStream
Operations:


Read the input from input stream
Use STT to convert speech to text. (deepgram supports streaming input)
Detect using Deepgram when speech is stopped
Query the LLM using the text from STT, incorporating a predefined system prompt.
Stream the output of LLM to TTS
Stream the TTS output to output stream
3. Observability
It should be possible to get some performance metrics from the library
Total Time for STT post user stopped speaking must be shown to the user 
Time for Complete Response From LLM - must be shown to the user.
Total time from when user stopped speaking and TTS generated first speech
Prerequisites
GPT-3.5 API Key: For accessing OpenAI's Large Language Model.
Deepgram API Key: For testing integration with Deepgram's STT.


Time Estimate
We prefer that candidates don’t spend more than 4-6 hours on the assignment. There are a lot of things to be built and it's ok if you are not able to complete everything as long as you are able to demonstrate a good understanding of the following concepts.
Concurrency
Observability
Good API Design
Abstractions
Deliverables:
Source code hosted on GitHub
Functional CLI application
README file with setup and usage instructions
Documentation outlining assumptions and potential issues
