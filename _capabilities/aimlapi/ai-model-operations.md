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
- ai models
- machine learning
- create chat completion
- create embedding
- generate a chat response from any of 400+ ai language models via aimlapi
- discover all 400+ available ai models on aimlapi platform
- generate an image from a text prompt using aimlapi image generation models
- generate image
- api key management and model discovery
- create a chat completion
- generate an image
- create image
- Developer
- list available models
- generate vector embeddings for semantic search and rag applications
- developer tools
- generate embeddings
- developer integrating ai capabilities into applications via aimlapi
- api gateway
- llm
- ai engineer evaluating and comparing models for ml pipelines
- access 400+ ai models for chat, image generation, embeddings, and model discovery
- list models
- embeddings
- AI Engineer
- video generation
- chat completions via 400+ llms
- create embeddings
- artificial intelligence
- list all models
- ai model inference across modalities
- image generation
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
