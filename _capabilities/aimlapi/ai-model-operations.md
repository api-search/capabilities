---
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
- speech
- artificial intelligence
- video generation
- generate vector embeddings for semantic search and rag applications
- create embedding
- generate an image from a text prompt using aimlapi image generation models
- api gateway
- generate an image
- ai engineer evaluating and comparing models for ml pipelines
- create chat completion
- AI Engineer
- list all models
- generate embeddings
- developer integrating ai capabilities into applications via aimlapi
- create image
- api key management and model discovery
- machine learning
- llm
- developer tools
- create a chat completion
- image generation
- embeddings
- ai models
- list models
- chat completions via 400+ llms
- list available models
- access 400+ ai models for chat, image generation, embeddings, and model discovery
- ai model inference across modalities
- create embeddings
- Developer
- generate a chat response from any of 400+ ai language models via aimlapi
- generate image
- discover all 400+ available ai models on aimlapi platform
slug: ai-model-operations
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
