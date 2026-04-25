---
consumed_apis:
- openai-chat
- openai-images
- openai-audio
- openai-embeddings
- openai-models
description: Unified content generation combining Chat, Images, Audio, and Embeddings APIs for developers to generate text, images, speech, and vector representations.
layout: capability
name: OpenAI Content Generation
operations:
- description: Create a chat completion
  method: POST
  name: create-chat-completion
  path: /v1/chat/completions
- description: Generate an image
  method: POST
  name: create-image
  path: /v1/images/generations
- description: Generate speech
  method: POST
  name: create-speech
  path: /v1/audio/speech
- description: Create embeddings
  method: POST
  name: create-embedding
  path: /v1/embeddings
- description: List models
  method: GET
  name: list-models
  path: /v1/models
personas: []
provider_name: OpenAI
provider_slug: openai
search_terms:
- audio create translation
- list all available openai models
- artificial intelligence
- create embedding
- generate an image
- create chat completion
- create a variation of an existing image
- translate audio to english text
- images edit
- chat completion
- generate a conversational response using gpt models
- generate an image from a text prompt using dall-e
- images create
- generate vector embeddings for text input
- generate speech
- create image
- text embeddings
- audio create transcription
- content generation
- chat create completion
- text to speech
- embeddings create
- images create variation
- generate audio from text using tts models
- available models
- audio create speech
- transcribe audio to text using whisper
- create a chat completion
- models list
- image generation
- models get
- openai
- edit an existing image with a text prompt
- ai
- list models
- large language models
- create speech
- create embeddings
- t1
- get details of a specific model
slug: content-generation
tags:
- OpenAI
- Content Generation
- AI
tools:
- description: Generate a conversational response using GPT models
  hints:
    readOnly: false
  name: chat-create-completion
- description: Generate an image from a text prompt using DALL-E
  hints:
    readOnly: false
  name: images-create
- description: Edit an existing image with a text prompt
  hints:
    readOnly: false
  name: images-edit
- description: Create a variation of an existing image
  hints:
    readOnly: false
  name: images-create-variation
- description: Generate audio from text using TTS models
  hints:
    readOnly: false
  name: audio-create-speech
- description: Transcribe audio to text using Whisper
  hints:
    readOnly: false
  name: audio-create-transcription
- description: Translate audio to English text
  hints:
    readOnly: false
  name: audio-create-translation
- description: Generate vector embeddings for text input
  hints:
    readOnly: false
  name: embeddings-create
- description: List all available OpenAI models
  hints:
    readOnly: true
  name: models-list
- description: Get details of a specific model
  hints:
    readOnly: true
  name: models-get
---
