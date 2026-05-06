---
categories:
- machine-learning
consumed_apis: []
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
- list available ai models
- openai
- transcribe audio to text
- cognitive list accounts
- cognitive services accounts
- platform as a service
- generate images from text
- openai list models
- list openai models
- azure
- translate audio to english
- cloud
- openai create embedding
- cognitive services
- embedding operations
- enterprise
- ai
- cloud computing
- create embedding
- create a text completion
- generate speech from text
- t1
- create a chat completion
- list cognitive services accounts
- openai create translation
- openai list deployments
- create text embeddings
- openai create transcription
- infrastructure as a service
- openai create speech
- create a chat completion using azure openai
- openai create image
- api management
- openai create completion
- list model deployments
- create chat completion
- list cognitive accounts
- cognitive list models
- list available openai models
- model listing
- openai create chat completion
- chat completion operations
slug: ai-and-cognitive
source_filename: ai-and-cognitive.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure AI and Cognitive Services\n  description: Unified workflow for Azure AI capabilities combining OpenAI Service for generative AI and Cognitive Services\n    for account and model management. Used by AI engineers, ML ops teams, and application developers building intelligent\n    applications.\n  tags:\n  - Azure\n  - AI\n  - OpenAI\n  - Cognitive Services\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_OPENAI_API_KEY: AZURE_OPENAI_API_KEY\n    AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-openai\n    baseUri: https://{endpoint}/openai\n    description: Azure OpenAI Service API\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{AZURE_OPENAI_API_KEY}}'\n      placement: header\n    resources:\n    - name: chat-completions\n      path: /deployments/{deployment-id}/chat/completions\n      description:\
  \ Chat completion operations\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Create a chat completion\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: completions\n      path: /deployments/{deployment-id}/completions\n      description: Text completion operations\n      operations:\n      - name: create-completion\n        method: POST\n        description: Create a text completion\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: embeddings\n\
  \      path: /deployments/{deployment-id}/embeddings\n      description: Embedding operations\n      operations:\n      - name: create-embedding\n        method: POST\n        description: Create text embeddings\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /deployments/{deployment-id}/images/generations\n      description: Image generation operations\n      operations:\n      - name: create-image\n        method: POST\n        description: Generate images from text\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: audio\n      path: /deployments/{deployment-id}/audio\n      description: Audio operations\n      operations:\n      - name: create-transcription\n        method: POST\n        description: Transcribe audio to text\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-translation\n        method: POST\n        description: Translate audio to English text\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-speech\n   \
  \     method: POST\n        description: Generate speech from text\n        inputParameters:\n        - name: deployment-id\n          in: path\n          type: string\n          required: true\n          description: Deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      description: Model operations\n      operations:\n      - name: list-models\n        method: GET\n        description: List available models\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      description: Deployment operations\n      operations:\n      - name: list-deployments\n        method: GET\n        description: List model deployments\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-cognitive\n    baseUri: https://management.azure.com\n    description: Azure Cognitive Services Management API\n    authentication:\n      type: bearer\n      token: '{{AZURE_MANAGEMENT_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.CognitiveServices/accounts\n      description: Cognitive Services account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List Cognitive Services accounts\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get a Cognitive Services\
  \ account\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: PUT\n        description: Create a Cognitive Services account\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource\
  \ group name\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Delete a Cognitive Services account\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-keys\n     \
  \   method: POST\n        description: List account keys\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-models\n        method: GET\n        description: List available models\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: azure-ai-api\n    description: Unified REST API for Azure AI services.\n    resources:\n    - path: /v1/chat/completions\n      name: chat-completions\n      description: Chat completion operations\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Create a chat completion\n        call: azure-openai.create-chat-completion\n        with:\n          deployment-id: rest.deploymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Embedding operations\n      operations:\n      - method: POST\n        name: create-embedding\n        description: Create text embeddings\n        call: azure-openai.create-embedding\n        with:\n          deployment-id: rest.deploymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n\
  \      name: models\n      description: Model listing\n      operations:\n      - method: GET\n        name: list-openai-models\n        description: List OpenAI models\n        call: azure-openai.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Cognitive Services accounts\n      operations:\n      - method: GET\n        name: list-cognitive-accounts\n        description: List Cognitive Services accounts\n        call: azure-cognitive.list-accounts\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: azure-ai-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure AI operations.\n    tools:\n    - name: openai-create-chat-completion\n      description: Create a chat completion using Azure OpenAI\n      hints:\n        readOnly: false\n\
  \      call: azure-openai.create-chat-completion\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-create-completion\n      description: Create a text completion\n      hints:\n        readOnly: false\n      call: azure-openai.create-completion\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-create-embedding\n      description: Create text embeddings\n      hints:\n        readOnly: true\n      call: azure-openai.create-embedding\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-create-image\n      description: Generate images from text\n      hints:\n        readOnly: false\n      call: azure-openai.create-image\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: openai-create-transcription\n      description: Transcribe audio to text\n      hints:\n        readOnly: true\n      call: azure-openai.create-transcription\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-create-translation\n      description: Translate audio to English\n      hints:\n        readOnly: true\n      call: azure-openai.create-translation\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-create-speech\n      description: Generate speech from text\n      hints:\n        readOnly: false\n      call: azure-openai.create-speech\n      with:\n        deployment-id: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-list-models\n      description: List available OpenAI models\n      hints:\n  \
  \      readOnly: true\n      call: azure-openai.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: openai-list-deployments\n      description: List model deployments\n      hints:\n        readOnly: true\n      call: azure-openai.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cognitive-list-accounts\n      description: List Cognitive Services accounts\n      hints:\n        readOnly: true\n      call: azure-cognitive.list-accounts\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cognitive-list-models\n      description: List available AI models\n      hints:\n        readOnly: true\n      call: azure-cognitive.list-models\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
