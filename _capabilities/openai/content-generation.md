---
categories: []
consumed_apis: []
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
- available models
- generate a conversational response using gpt models
- edit an existing image with a text prompt
- ai
- generate vector embeddings for text input
- images edit
- image generation
- audio create transcription
- create image
- list all available openai models
- create embedding
- generate audio from text using tts models
- content generation
- text embeddings
- create a variation of an existing image
- artificial intelligence
- openai
- images create
- t1
- models list
- create speech
- transcribe audio to text using whisper
- images create variation
- generate an image
- list models
- embeddings create
- large language models
- text to speech
- generate speech
- models get
- get details of a specific model
- chat completion
- generate an image from a text prompt using dall-e
- translate audio to english text
- chat create completion
- audio create speech
- create a chat completion
- create embeddings
- create chat completion
- audio create translation
slug: content-generation
source_filename: content-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenAI Content Generation\n  description: Unified content generation combining Chat, Images, Audio, and Embeddings APIs for developers to generate text,\n    images, speech, and vector representations.\n  tags:\n  - OpenAI\n  - Content Generation\n  - AI\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OPENAI_API_KEY: OPENAI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: openai-chat\n    baseUri: https://api.openai.com/v1\n    description: OpenAI Chat Completions API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_API_KEY}}'\n    resources:\n    - name: chat\n      path: /chat\n      description: Chat completion operations\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Creates a model response for the given chat conversation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            temperature: '{{tools.temperature}}'\n            max_tokens: '{{tools.max_tokens}}'\n  - type: http\n    namespace: openai-images\n    baseUri: https://api.openai.com/v1\n    description: OpenAI Images API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_API_KEY}}'\n    resources:\n    - name: images\n      path: /images\n      description: Image generation and editing operations\n      operations:\n      - name: create-image\n        method: POST\n        description: Creates an image given a text prompt.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            model: '{{tools.model}}'\n            n: '{{tools.n}}'\n\
  \            size: '{{tools.size}}'\n      - name: create-image-edit\n        method: POST\n        description: Creates an edited or extended image given an original image and a prompt.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            image: '{{tools.image}}'\n            prompt: '{{tools.prompt}}'\n      - name: create-image-variation\n        method: POST\n        description: Creates a variation of a given image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            image: '{{tools.image}}'\n  - type: http\n    namespace: openai-audio\n    baseUri: https://api.openai.com/v1\n    description: OpenAI Audio API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_API_KEY}}'\n    resources:\n\
  \    - name: audio\n      path: /audio\n      description: Audio operations\n      operations:\n      - name: create-speech\n        method: POST\n        description: Generates audio from the input text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n            voice: '{{tools.voice}}'\n      - name: create-transcription\n        method: POST\n        description: Transcribes audio into the input language.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            file: '{{tools.file}}'\n            model: '{{tools.model}}'\n      - name: create-translation\n        method: POST\n        description: Translates audio into English.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            file: '{{tools.file}}'\n            model: '{{tools.model}}'\n  - type: http\n    namespace: openai-embeddings\n    baseUri: https://api.openai.com/v1\n    description: OpenAI Embeddings API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_API_KEY}}'\n    resources:\n    - name: embeddings\n      path: /embeddings\n      description: Embedding operations\n      operations:\n      - name: create-embedding\n        method: POST\n        description: Creates an embedding vector representing the input text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            model: '{{tools.model}}'\n  - type: http\n    namespace: openai-models\n\
  \    baseUri: https://api.openai.com/v1\n    description: OpenAI Models API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_API_KEY}}'\n    resources:\n    - name: models\n      path: /models\n      description: Model operations\n      operations:\n      - name: list-models\n        method: GET\n        description: Lists the currently available models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: retrieve-model\n        method: GET\n        description: Retrieves a model instance by ID.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: Model ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-model\n        method: DELETE\n        description: Deletes a fine-tuned model.\n        inputParameters:\n\
  \        - name: model\n          in: path\n          type: string\n          required: true\n          description: Model ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: content-generation-api\n    description: Unified REST API for AI content generation.\n    resources:\n    - path: /v1/chat/completions\n      name: chat\n      description: Chat completion\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Create a chat completion\n        call: openai-chat.create-chat-completion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/generations\n      name: images\n      description: Image generation\n      operations:\n      - method: POST\n        name: create-image\n        description: Generate an image\n        call: openai-images.create-image\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audio/speech\n      name: speech\n      description: Text to speech\n      operations:\n      - method: POST\n        name: create-speech\n        description: Generate speech\n        call: openai-audio.create-speech\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Text embeddings\n      operations:\n      - method: POST\n        name: create-embedding\n        description: Create embeddings\n        call: openai-embeddings.create-embedding\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Available models\n      operations:\n      - method: GET\n        name: list-models\n        description: List models\n        call: openai-models.list-models\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9080\n    namespace: content-generation-mcp\n    transport: http\n    description: MCP server for AI-assisted content generation across text, image, audio, and embedding modalities.\n    tools:\n    - name: chat-create-completion\n      description: Generate a conversational response using GPT models\n      hints:\n        readOnly: false\n      call: openai-chat.create-chat-completion\n      with:\n        model: tools.model\n        messages: tools.messages\n        temperature: tools.temperature\n        max_tokens: tools.max_tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-create\n      description: Generate an image from a text prompt using DALL-E\n      hints:\n        readOnly: false\n      call: openai-images.create-image\n      with:\n        prompt: tools.prompt\n        model: tools.model\n        n: tools.n\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: images-edit\n      description: Edit an existing image with a text prompt\n      hints:\n        readOnly: false\n      call: openai-images.create-image-edit\n      with:\n        image: tools.image\n        prompt: tools.prompt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-create-variation\n      description: Create a variation of an existing image\n      hints:\n        readOnly: false\n      call: openai-images.create-image-variation\n      with:\n        image: tools.image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: audio-create-speech\n      description: Generate audio from text using TTS models\n      hints:\n        readOnly: false\n      call: openai-audio.create-speech\n      with:\n        model: tools.model\n        input: tools.input\n        voice: tools.voice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: audio-create-transcription\n      description:\
  \ Transcribe audio to text using Whisper\n      hints:\n        readOnly: false\n      call: openai-audio.create-transcription\n      with:\n        file: tools.file\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: audio-create-translation\n      description: Translate audio to English text\n      hints:\n        readOnly: false\n      call: openai-audio.create-translation\n      with:\n        file: tools.file\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: embeddings-create\n      description: Generate vector embeddings for text input\n      hints:\n        readOnly: false\n      call: openai-embeddings.create-embedding\n      with:\n        input: tools.input\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: models-list\n      description: List all available OpenAI models\n      hints:\n        readOnly: true\n\
  \      call: openai-models.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: models-get\n      description: Get details of a specific model\n      hints:\n        readOnly: true\n      call: openai-models.retrieve-model\n      with:\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
