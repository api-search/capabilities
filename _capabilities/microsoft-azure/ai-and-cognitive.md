---
categories:
- machine-learning
consumed_apis:
- azure-openai
- azure-cognitive
description: Unified workflow for Azure AI capabilities combining OpenAI Service for generative AI and Cognitive Services for account and model management. Used by AI engineers, ML ops teams, and application developers building intelligent applications.
layout: capability
name: Azure AI and Cognitive Services
operations:
- description: Create a chat completion
  method: POST
  name: create-chat-completion
  path: /v1/chat/completions
- description: Create text embeddings
  method: POST
  name: create-embedding
  path: /v1/embeddings
- description: List OpenAI models
  method: GET
  name: list-openai-models
  path: /v1/models
- description: List Cognitive Services accounts
  method: GET
  name: list-cognitive-accounts
  path: /v1/accounts
personas: []
provider_name: Microsoft Azure
provider_slug: microsoft-azure
search_terms:
- azure
- openai create embedding
- list model deployments
- openai
- list available openai models
- model listing
- infrastructure as a service
- openai list models
- cognitive list models
- list openai models
- create text embeddings
- api management
- create chat completion
- list available ai models
- cognitive services
- list cognitive services accounts
- create a chat completion using azure openai
- ai
- platform as a service
- cognitive services accounts
- create a chat completion
- openai create speech
- openai create transcription
- cognitive list accounts
- cloud
- chat completion operations
- openai create completion
- cloud computing
- embedding operations
- openai create translation
- create embedding
- generate speech from text
- create a text completion
- generate images from text
- enterprise
- t1
- openai create chat completion
- transcribe audio to text
- openai list deployments
- list cognitive accounts
- openai create image
- translate audio to english
slug: ai-and-cognitive
tags:
- Azure
- AI
- OpenAI
- Cognitive Services
tools:
- description: Create a chat completion using Azure OpenAI
  hints:
    readOnly: false
  name: openai-create-chat-completion
- description: Create a text completion
  hints:
    readOnly: false
  name: openai-create-completion
- description: Create text embeddings
  hints:
    readOnly: true
  name: openai-create-embedding
- description: Generate images from text
  hints:
    readOnly: false
  name: openai-create-image
- description: Transcribe audio to text
  hints:
    readOnly: true
  name: openai-create-transcription
- description: Translate audio to English
  hints:
    readOnly: true
  name: openai-create-translation
- description: Generate speech from text
  hints:
    readOnly: false
  name: openai-create-speech
- description: List available OpenAI models
  hints:
    readOnly: true
  name: openai-list-models
- description: List model deployments
  hints:
    readOnly: true
  name: openai-list-deployments
- description: List Cognitive Services accounts
  hints:
    readOnly: true
  name: cognitive-list-accounts
- description: List available AI models
  hints:
    readOnly: true
  name: cognitive-list-models
---
