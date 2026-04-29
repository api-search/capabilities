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
- openai create speech
- openai create chat completion
- cognitive services accounts
- openai create image
- transcribe audio to text
- list cognitive services accounts
- azure
- cognitive list accounts
- create chat completion
- create a chat completion
- embedding operations
- ai
- openai create transcription
- list available ai models
- list cognitive accounts
- generate images from text
- openai create completion
- cognitive list models
- list model deployments
- openai create translation
- create a chat completion using azure openai
- create a text completion
- model listing
- translate audio to english
- cloud
- list available openai models
- create embedding
- openai list models
- enterprise
- openai
- openai list deployments
- cloud computing
- t1
- cognitive services
- generate speech from text
- api management
- infrastructure as a service
- create text embeddings
- platform as a service
- chat completion operations
- list openai models
- openai create embedding
slug: ai-and-cognitive
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure AI and Cognitive Services\"\n  description: \"Unified workflow for Azure AI capabilities combining OpenAI Service for generative AI and Cognitive Services for account and model management. Used by AI engineers, ML ops teams, and application developers building intelligent applications.\"\n  tags:\n    - Azure\n    - AI\n    - OpenAI\n    - Cognitive Services\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_OPENAI_API_KEY: AZURE_OPENAI_API_KEY\n      AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-openai\n      location: ./shared/openai-service.yaml\n    - import: azure-cognitive\n      location: ./shared/cognitive-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: azure-ai-api\n      description: \"Unified REST API for Azure AI services.\"\n      resources:\n        - path: /v1/chat/completions\n\
  \          name: chat-completions\n          description: \"Chat completion operations\"\n          operations:\n            - method: POST\n              name: create-chat-completion\n              description: \"Create a chat completion\"\n              call: \"azure-openai.create-chat-completion\"\n              with:\n                deployment-id: \"rest.deploymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Embedding operations\"\n          operations:\n            - method: POST\n              name: create-embedding\n              description: \"Create text embeddings\"\n              call: \"azure-openai.create-embedding\"\n              with:\n                deployment-id: \"rest.deploymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name:\
  \ models\n          description: \"Model listing\"\n          operations:\n            - method: GET\n              name: list-openai-models\n              description: \"List OpenAI models\"\n              call: \"azure-openai.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Cognitive Services accounts\"\n          operations:\n            - method: GET\n              name: list-cognitive-accounts\n              description: \"List Cognitive Services accounts\"\n              call: \"azure-cognitive.list-accounts\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: azure-ai-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure AI operations.\"\
  \n      tools:\n        - name: openai-create-chat-completion\n          description: \"Create a chat completion using Azure OpenAI\"\n          hints:\n            readOnly: false\n          call: \"azure-openai.create-chat-completion\"\n          with:\n            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-completion\n          description: \"Create a text completion\"\n          hints:\n            readOnly: false\n          call: \"azure-openai.create-completion\"\n          with:\n            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-embedding\n          description: \"Create text embeddings\"\n          hints:\n            readOnly: true\n          call: \"azure-openai.create-embedding\"\n          with:\n            deployment-id: \"tools.deploymentId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-image\n          description: \"Generate images from text\"\n          hints:\n            readOnly: false\n          call: \"azure-openai.create-image\"\n          with:\n            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-transcription\n          description: \"Transcribe audio to text\"\n          hints:\n            readOnly: true\n          call: \"azure-openai.create-transcription\"\n          with:\n            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-translation\n          description: \"Translate audio to English\"\n          hints:\n            readOnly: true\n          call: \"azure-openai.create-translation\"\n          with:\n\
  \            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-create-speech\n          description: \"Generate speech from text\"\n          hints:\n            readOnly: false\n          call: \"azure-openai.create-speech\"\n          with:\n            deployment-id: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-list-models\n          description: \"List available OpenAI models\"\n          hints:\n            readOnly: true\n          call: \"azure-openai.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openai-list-deployments\n          description: \"List model deployments\"\n          hints:\n            readOnly: true\n          call: \"azure-openai.list-deployments\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: cognitive-list-accounts\n          description: \"List Cognitive Services accounts\"\n          hints:\n            readOnly: true\n          call: \"azure-cognitive.list-accounts\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cognitive-list-models\n          description: \"List available AI models\"\n          hints:\n            readOnly: true\n          call: \"azure-cognitive.list-models\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure/refs/heads/main/capabilities/ai-and-cognitive.yaml
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
