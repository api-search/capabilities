---
consumed_apis:
- amazon-polly
description: Workflow capability for converting text to lifelike speech using Amazon Polly. Combines speech synthesis, voice discovery, and lexicon management for developers building voice-enabled applications.
layout: capability
name: Amazon Polly Text-to-Speech
operations:
- description: Convert text to speech audio
  method: POST
  name: synthesize-speech
  path: /v1/speech
- description: List available voices by language and engine
  method: GET
  name: list-voices
  path: /v1/voices
- description: List pronunciation lexicons
  method: GET
  name: list-lexicons
  path: /v1/lexicons
- description: Create or update a pronunciation lexicon
  method: PUT
  name: create-lexicon
  path: /v1/lexicons
- description: Start an asynchronous speech synthesis task
  method: POST
  name: start-task
  path: /v1/tasks
- description: List synthesis tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Amazon Polly
provider_slug: amazon-polly
search_terms:
- start an asynchronous speech synthesis task
- neural engine
- speech synthesis from text
- get lexicon
- synthesize speech
- speech synthesis
- voice applications
- list pronunciation lexicons
- get the content of a pronunciation lexicon
- convert text to speech audio
- list tasks
- start synthesis task
- ssml
- creates audio content from written text using polly
- list voices
- machine learning
- create or update a pronunciation lexicon
- create lexicon
- list synthesis tasks
- Content Creator
- asynchronous synthesis tasks
- voice
- start task
- text-to-speech
- list available amazon polly voices filterable by language and engine type
- builds voice-enabled applications using polly speech synthesis
- list custom pronunciation lexicons for controlling how words are spoken
- generative ai
- Application Developer
- tts
- convert text to lifelike speech audio using amazon polly
- multi-channel text-to-speech synthesis workflow
- custom pronunciation lexicons
- aws
- list lexicons
- available synthesis voices
- create or update a custom pronunciation lexicon
- list available voices by language and engine
- ai
- start an asynchronous synthesis task for long text with s3 output
- amazon
- list and monitor asynchronous speech synthesis tasks
slug: text-to-speech
tags:
- Amazon
- AWS
- Text-To-Speech
- Speech Synthesis
- AI
- Voice Applications
- Machine Learning
tools:
- description: Convert text to lifelike speech audio using Amazon Polly
  hints:
    destructive: false
    readOnly: false
  name: synthesize-speech
- description: List available Amazon Polly voices filterable by language and engine type
  hints:
    openWorld: true
    readOnly: true
  name: list-voices
- description: List custom pronunciation lexicons for controlling how words are spoken
  hints:
    openWorld: true
    readOnly: true
  name: list-lexicons
- description: Get the content of a pronunciation lexicon
  hints:
    openWorld: false
    readOnly: true
  name: get-lexicon
- description: Create or update a custom pronunciation lexicon
  hints:
    destructive: false
    readOnly: false
  name: create-lexicon
- description: Start an asynchronous synthesis task for long text with S3 output
  hints:
    destructive: false
    readOnly: false
  name: start-synthesis-task
- description: List and monitor asynchronous speech synthesis tasks
  hints:
    openWorld: true
    readOnly: true
  name: list-synthesis-tasks
---
