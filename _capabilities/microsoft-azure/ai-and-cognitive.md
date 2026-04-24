---
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
- ai
- openai list deployments
- model listing
- openai create completion
- list cognitive services accounts
- openai create translation
- list available openai models
- embedding operations
- openai create chat completion
- create a chat completion
- cognitive list accounts
- openai create embedding
- cloud
- chat completion operations
- create embedding
- create a chat completion using azure openai
- openai create transcription
- platform as a service
- transcribe audio to text
- list cognitive accounts
- openai
- cognitive list models
- create chat completion
- openai create image
- api management
- t1
- list available ai models
- generate speech from text
- cognitive services accounts
- openai create speech
- translate audio to english
- create a text completion
- enterprise
- list openai models
- generate images from text
- list model deployments
- cloud computing
- infrastructure as a service
- create text embeddings
- azure
- openai list models
- cognitive services
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
