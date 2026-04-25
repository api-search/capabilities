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
- embedding operations
- openai create translation
- enterprise
- create text embeddings
- openai create chat completion
- translate audio to english
- platform as a service
- api management
- t1
- azure
- openai create completion
- cloud
- infrastructure as a service
- generate speech from text
- openai create embedding
- cognitive services accounts
- ai
- list available openai models
- create a chat completion
- list cognitive accounts
- create chat completion
- model listing
- list available ai models
- create a chat completion using azure openai
- cognitive services
- chat completion operations
- transcribe audio to text
- list cognitive services accounts
- openai create image
- openai
- list openai models
- cognitive list accounts
- create embedding
- list model deployments
- cloud computing
- generate images from text
- openai create speech
- openai list deployments
- cognitive list models
- openai list models
- openai create transcription
- create a text completion
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
