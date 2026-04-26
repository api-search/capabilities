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
- list all available openai models
- get details of a specific model
- images edit
- embeddings create
- chat completion
- images create
- available models
- generate speech
- create embedding
- generate a conversational response using gpt models
- audio create translation
- image generation
- text embeddings
- openai
- content generation
- generate an image from a text prompt using dall-e
- create image
- transcribe audio to text using whisper
- chat create completion
- create speech
- models list
- large language models
- artificial intelligence
- models get
- create chat completion
- generate an image
- ai
- text to speech
- generate vector embeddings for text input
- create embeddings
- list models
- edit an existing image with a text prompt
- images create variation
- create a variation of an existing image
- create a chat completion
- audio create speech
- generate audio from text using tts models
- audio create transcription
- translate audio to english text
- t1
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
