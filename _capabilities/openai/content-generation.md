---
categories: []
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
- chat completion
- audio create transcription
- images create variation
- audio create translation
- text embeddings
- generate a conversational response using gpt models
- list all available openai models
- create embedding
- generate an image from a text prompt using dall-e
- transcribe audio to text using whisper
- t1
- generate speech
- image generation
- list models
- available models
- content generation
- get details of a specific model
- text to speech
- generate audio from text using tts models
- translate audio to english text
- models list
- artificial intelligence
- create speech
- models get
- edit an existing image with a text prompt
- large language models
- chat create completion
- images edit
- create embeddings
- create a variation of an existing image
- generate vector embeddings for text input
- create a chat completion
- create image
- embeddings create
- ai
- create chat completion
- openai
- images create
- generate an image
- audio create speech
slug: content-generation
source_filename: content-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"OpenAI Content Generation\"\n  description: \"Unified content generation combining Chat, Images, Audio, and Embeddings APIs for developers to generate text, images, speech, and vector representations.\"\n  tags:\n    - OpenAI\n    - Content Generation\n    - AI\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENAI_API_KEY: OPENAI_API_KEY\n\ncapability:\n  consumes:\n    - import: openai-chat\n      location: ./shared/chat.yaml\n    - import: openai-images\n      location: ./shared/images.yaml\n    - import: openai-audio\n      location: ./shared/audio.yaml\n    - import: openai-embeddings\n      location: ./shared/embeddings.yaml\n    - import: openai-models\n      location: ./shared/models.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: content-generation-api\n      description: \"Unified REST API for AI content generation.\"\n      resources:\n \
  \       - path: /v1/chat/completions\n          name: chat\n          description: \"Chat completion\"\n          operations:\n            - method: POST\n              name: create-chat-completion\n              description: \"Create a chat completion\"\n              call: \"openai-chat.create-chat-completion\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images/generations\n          name: images\n          description: \"Image generation\"\n          operations:\n            - method: POST\n              name: create-image\n              description: \"Generate an image\"\n              call: \"openai-images.create-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audio/speech\n          name: speech\n          description: \"Text to speech\"\n          operations:\n            - method: POST\n              name: create-speech\n\
  \              description: \"Generate speech\"\n              call: \"openai-audio.create-speech\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Text embeddings\"\n          operations:\n            - method: POST\n              name: create-embedding\n              description: \"Create embeddings\"\n              call: \"openai-embeddings.create-embedding\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"Available models\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List models\"\n              call: \"openai-models.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n \
  \     port: 9080\n      namespace: content-generation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted content generation across text, image, audio, and embedding modalities.\"\n      tools:\n        - name: chat-create-completion\n          description: \"Generate a conversational response using GPT models\"\n          hints:\n            readOnly: false\n          call: \"openai-chat.create-chat-completion\"\n          with:\n            model: \"tools.model\"\n            messages: \"tools.messages\"\n            temperature: \"tools.temperature\"\n            max_tokens: \"tools.max_tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-create\n          description: \"Generate an image from a text prompt using DALL-E\"\n          hints:\n            readOnly: false\n          call: \"openai-images.create-image\"\n          with:\n            prompt: \"tools.prompt\"\n            model: \"\
  tools.model\"\n            n: \"tools.n\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-edit\n          description: \"Edit an existing image with a text prompt\"\n          hints:\n            readOnly: false\n          call: \"openai-images.create-image-edit\"\n          with:\n            image: \"tools.image\"\n            prompt: \"tools.prompt\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-create-variation\n          description: \"Create a variation of an existing image\"\n          hints:\n            readOnly: false\n          call: \"openai-images.create-image-variation\"\n          with:\n            image: \"tools.image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: audio-create-speech\n          description: \"Generate audio from text using TTS models\"\
  \n          hints:\n            readOnly: false\n          call: \"openai-audio.create-speech\"\n          with:\n            model: \"tools.model\"\n            input: \"tools.input\"\n            voice: \"tools.voice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: audio-create-transcription\n          description: \"Transcribe audio to text using Whisper\"\n          hints:\n            readOnly: false\n          call: \"openai-audio.create-transcription\"\n          with:\n            file: \"tools.file\"\n            model: \"tools.model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: audio-create-translation\n          description: \"Translate audio to English text\"\n          hints:\n            readOnly: false\n          call: \"openai-audio.create-translation\"\n          with:\n            file: \"tools.file\"\n            model: \"tools.model\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: embeddings-create\n          description: \"Generate vector embeddings for text input\"\n          hints:\n            readOnly: false\n          call: \"openai-embeddings.create-embedding\"\n          with:\n            input: \"tools.input\"\n            model: \"tools.model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: models-list\n          description: \"List all available OpenAI models\"\n          hints:\n            readOnly: true\n          call: \"openai-models.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: models-get\n          description: \"Get details of a specific model\"\n          hints:\n            readOnly: true\n          call: \"openai-models.retrieve-model\"\n          with:\n            model: \"tools.model\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openai/refs/heads/main/capabilities/content-generation.yaml
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
