---
categories:
- machine-learning
consumed_apis: []
description: Unified workflow for accessing 400+ AI models via AIMLAPI gateway including chat completions, image generation, embeddings, and model discovery. Used by developers building AI-powered applications.
layout: capability
name: AIMLAPI AI Model Operations
operations:
- description: Create a chat completion
  method: POST
  name: create-chat-completion
  path: /v1/chat/completions
- description: Generate an image
  method: POST
  name: create-image
  path: /v1/images/generations
- description: Create embeddings
  method: POST
  name: create-embedding
  path: /v1/embeddings
- description: List all models
  method: GET
  name: list-models
  path: /v1/models
personas: []
provider_name: AIMLAPI
provider_slug: aimlapi
search_terms:
- chat completions via 400+ llms
- generate image
- developer integrating ai capabilities into applications via aimlapi
- AI Engineer
- llm
- generate embeddings
- video generation
- generate vector embeddings for semantic search and rag applications
- ai models
- ai engineer evaluating and comparing models for ml pipelines
- image generation
- create image
- create embedding
- artificial intelligence
- access 400+ ai models for chat, image generation, embeddings, and model discovery
- machine learning
- developer tools
- generate a chat response from any of 400+ ai language models via aimlapi
- embeddings
- api gateway
- list all models
- generate an image
- discover all 400+ available ai models on aimlapi platform
- list models
- ai model inference across modalities
- Developer
- create a chat completion
- create embeddings
- create chat completion
- generate an image from a text prompt using aimlapi image generation models
- speech
- api key management and model discovery
- list available models
slug: ai-model-operations
source_filename: ai-model-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AIMLAPI AI Model Operations\n  description: Unified workflow for accessing 400+ AI models via AIMLAPI gateway including chat completions, image generation,\n    embeddings, and model discovery. Used by developers building AI-powered applications.\n  tags:\n  - Artificial Intelligence\n  - LLM\n  - Image Generation\n  - Embeddings\n  - Developer Tools\n  - API Gateway\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AIMLAPI_API_KEY: AIMLAPI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: aimlapi\n    baseUri: https://api.aimlapi.com/v1\n    description: AIMLAPI unified AI model gateway (OpenAI-compatible)\n    authentication:\n      type: bearer\n      token: '{{AIMLAPI_API_KEY}}'\n    resources:\n    - name: chat-completions\n      path: /chat/completions\n      description: Chat completion with 400+ LLMs\n      operations:\n      - name: create-chat-completion\n        method:\
  \ POST\n        description: Create a chat completion response from a language model\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n    - name: images-generations\n      path: /images/generations\n      description: Generate images using AI image generation models\n      operations:\n      - name: create-image\n        method: POST\n        description: Generate an image from a text prompt\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n    - name: embeddings\n      path: /embeddings\n      description: Generate\
  \ text embeddings for semantic search and RAG\n      operations:\n      - name: create-embedding\n        method: POST\n        description: Generate vector embeddings for input text\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n    - name: models\n      path: /models\n      description: List available AI models\n      operations:\n      - name: list-models\n        method: GET\n        description: List all available AI models\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aimlapi-ai-ops-api\n    description: Unified REST API for AIMLAPI AI model operations.\n    resources:\n    - path:\
  \ /v1/chat/completions\n      name: chat-completions\n      description: Chat completions via 400+ LLMs\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Create a chat completion\n        call: aimlapi.create-chat-completion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/generations\n      name: image-generations\n      description: Image generation\n      operations:\n      - method: POST\n        name: create-image\n        description: Generate an image\n        call: aimlapi.create-image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Generate embeddings\n      operations:\n      - method: POST\n        name: create-embedding\n        description: Create embeddings\n        call: aimlapi.create-embedding\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/models\n      name: models\n      description: List available models\n      operations:\n      - method: GET\n        name: list-models\n        description: List all models\n        call: aimlapi.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: aimlapi-ai-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted access to AIMLAPI model gateway.\n    tools:\n    - name: create-chat-completion\n      description: Generate a chat response from any of 400+ AI language models via AIMLAPI\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aimlapi.create-chat-completion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-image\n      description: Generate an image from a text prompt using AIMLAPI image generation models\n      hints:\n        readOnly: false\n        destructive: false\n       \
  \ idempotent: false\n      call: aimlapi.create-image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-embedding\n      description: Generate vector embeddings for semantic search and RAG applications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aimlapi.create-embedding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: Discover all 400+ available AI models on AIMLAPI platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aimlapi.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aimlapi/refs/heads/main/capabilities/ai-model-operations.yaml
tags:
- Artificial Intelligence
- LLM
- Image Generation
- Embeddings
- Developer Tools
- API Gateway
tools:
- description: Generate a chat response from any of 400+ AI language models via AIMLAPI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-chat-completion
- description: Generate an image from a text prompt using AIMLAPI image generation models
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-image
- description: Generate vector embeddings for semantic search and RAG applications
  hints:
    openWorld: true
    readOnly: true
  name: create-embedding
- description: Discover all 400+ available AI models on AIMLAPI platform
  hints:
    openWorld: true
    readOnly: true
  name: list-models
---
