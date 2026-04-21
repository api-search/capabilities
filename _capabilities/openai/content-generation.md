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
- audio create transcription
- embeddings create
- large language models
- audio create speech
- create chat completion
- create embedding
- generate a conversational response using gpt models
- translate audio to english text
- models list
- images create variation
- generate an image from a text prompt using dall-e
- create a chat completion
- generate an image
- t1
- create image
- chat completion
- openai
- get details of a specific model
- images create
- edit an existing image with a text prompt
- models get
- create a variation of an existing image
- transcribe audio to text using whisper
- generate vector embeddings for text input
- available models
- generate audio from text using tts models
- audio create translation
- list all available openai models
- list models
- ai
- create speech
- chat create completion
- images edit
- create embeddings
- artificial intelligence
- text embeddings
- generate speech
- image generation
- content generation
- text to speech
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
