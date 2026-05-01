---
categories:
- machine-learning
consumed_apis:
- aimlapi
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
- list models
- Developer
- api gateway
- AI Engineer
- speech
- api key management and model discovery
- embeddings
- ai engineer evaluating and comparing models for ml pipelines
- generate vector embeddings for semantic search and rag applications
- artificial intelligence
- create chat completion
- list available models
- developer integrating ai capabilities into applications via aimlapi
- image generation
- access 400+ ai models for chat, image generation, embeddings, and model discovery
- create embedding
- generate a chat response from any of 400+ ai language models via aimlapi
- machine learning
- create embeddings
- generate embeddings
- generate an image
- discover all 400+ available ai models on aimlapi platform
- video generation
- create image
- ai models
- generate an image from a text prompt using aimlapi image generation models
- chat completions via 400+ llms
- list all models
- developer tools
- create a chat completion
- ai model inference across modalities
- generate image
- llm
slug: ai-model-operations
source_filename: ai-model-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AIMLAPI AI Model Operations\"\n  description: \"Unified workflow for accessing 400+ AI models via AIMLAPI gateway including chat completions, image generation, embeddings, and model discovery. Used by developers building AI-powered applications.\"\n  tags:\n    - Artificial Intelligence\n    - LLM\n    - Image Generation\n    - Embeddings\n    - Developer Tools\n    - API Gateway\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AIMLAPI_API_KEY: AIMLAPI_API_KEY\n\ncapability:\n  consumes:\n    - import: aimlapi\n      location: ./shared/aimlapi-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aimlapi-ai-ops-api\n      description: \"Unified REST API for AIMLAPI AI model operations.\"\n      resources:\n        - path: /v1/chat/completions\n          name: chat-completions\n          description: \"Chat completions via 400+ LLMs\"\n          operations:\n\
  \            - method: POST\n              name: create-chat-completion\n              description: \"Create a chat completion\"\n              call: \"aimlapi.create-chat-completion\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images/generations\n          name: image-generations\n          description: \"Image generation\"\n          operations:\n            - method: POST\n              name: create-image\n              description: \"Generate an image\"\n              call: \"aimlapi.create-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Generate embeddings\"\n          operations:\n            - method: POST\n              name: create-embedding\n              description: \"Create embeddings\"\n              call: \"aimlapi.create-embedding\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"List available models\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all models\"\n              call: \"aimlapi.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: aimlapi-ai-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted access to AIMLAPI model gateway.\"\n      tools:\n        - name: create-chat-completion\n          description: \"Generate a chat response from any of 400+ AI language models via AIMLAPI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"aimlapi.create-chat-completion\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: generate-image\n          description: \"Generate an image from a text prompt using AIMLAPI image generation models\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"aimlapi.create-image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-embedding\n          description: \"Generate vector embeddings for semantic search and RAG applications\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aimlapi.create-embedding\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-models\n          description: \"Discover all 400+ available AI models on AIMLAPI platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aimlapi.list-models\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
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
