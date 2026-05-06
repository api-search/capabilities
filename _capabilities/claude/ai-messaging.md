---
categories:
- machine-learning
consumed_apis: []
description: Unified workflow for AI-powered messaging, token counting, batch processing, and model discovery. Used by AI application developers and data scientists.
layout: capability
name: Claude AI Messaging
operations:
- description: Create a message.
  method: POST
  name: create-message
  path: /v1/messages
- description: Count message tokens.
  method: POST
  name: count-tokens
  path: /v1/token-counts
- description: List message batches.
  method: GET
  name: list-batches
  path: /v1/batches
- description: Create a message batch.
  method: POST
  name: create-batch
  path: /v1/batches
- description: Get batch status.
  method: GET
  name: get-batch
  path: /v1/batches/{id}
- description: Delete a batch.
  method: DELETE
  name: delete-batch
  path: /v1/batches/{id}
- description: List available models.
  method: GET
  name: list-models
  path: /v1/models
- description: Get model metadata.
  method: GET
  name: get-model
  path: /v1/models/{id}
personas: []
provider_name: Claude
provider_slug: claude
search_terms:
- anthropic
- delete a batch.
- list all message batches.
- conversational ai
- natural language processing
- create a message.
- model discovery.
- list message batches.
- count tokens in a message.
- cancel message batch
- list available claude models.
- get model
- large language models
- delete a completed batch.
- generative ai
- individual batch management.
- create batch
- ai
- token counting.
- get batch
- delete batch
- batch management.
- list available models.
- artificial intelligence
- chatbot
- get message batch status and details.
- delete message batch
- messaging
- model details.
- machine learning
- create a message batch.
- send a message to claude and receive a response.
- list message batches
- count message tokens.
- retrieve message batch results
- count tokens
- list models
- create a batch of message requests.
- message operations.
- cancel an in-progress batch.
- get completed batch results.
- count message tokens
- retrieve message batch
- create message batch
- get batch status.
- get model metadata.
- list batches
- claude
- create message
slug: ai-messaging
source_filename: ai-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Claude AI Messaging\n  description: Unified workflow for AI-powered messaging, token counting, batch processing, and model discovery. Used by AI\n    application developers and data scientists.\n  tags:\n  - Anthropic\n  - Claude\n  - AI\n  - Messaging\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ANTHROPIC_API_KEY: ANTHROPIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: claude-messages\n    baseUri: https://api.anthropic.com/v1\n    description: Claude Messages API for AI-powered conversations and text generation.\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{ANTHROPIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: messages\n      path: /messages\n      description: Message creation and token counting.\n      operations:\n      - name: create-message\n        method: POST\n        description: Send a message to Claude and\
  \ receive a response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            max_tokens: '{{tools.max_tokens}}'\n            messages: '{{tools.messages}}'\n    - name: token-counting\n      path: /messages/count_tokens\n      description: Token counting.\n      operations:\n      - name: count-message-tokens\n        method: POST\n        description: Count tokens in a message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n    - name: message-batches\n      path: /messages/batches\n      description: Message batch management.\n      operations:\n      - name: create-message-batch\n        method:\
  \ POST\n        description: Create a batch of message requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n      - name: list-message-batches\n        method: GET\n        description: List all message batches.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-batch-details\n      path: /messages/batches/{message_batch_id}\n      description: Individual message batch management.\n      operations:\n      - name: retrieve-message-batch\n        method: GET\n        description: Get message batch status.\n        inputParameters:\n        - name: message_batch_id\n          in: path\n          type: string\n          required: true\n          description: Message batch ID.\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message-batch\n        method: DELETE\n        description: Delete a message batch.\n        inputParameters:\n        - name: message_batch_id\n          in: path\n          type: string\n          required: true\n          description: Message batch ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-batch-results\n      path: /messages/batches/{message_batch_id}/results\n      description: Message batch results.\n      operations:\n      - name: retrieve-message-batch-results\n        method: GET\n        description: Get message batch results.\n        inputParameters:\n        - name: message_batch_id\n          in: path\n          type: string\n          required: true\n          description: Message batch ID.\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: message-batch-cancel\n      path: /messages/batches/{message_batch_id}/cancel\n      description: Cancel message batches.\n      operations:\n      - name: cancel-message-batch\n        method: POST\n        description: Cancel a message batch.\n        inputParameters:\n        - name: message_batch_id\n          in: path\n          type: string\n          required: true\n          description: Message batch ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      description: Model listing.\n      operations:\n      - name: list-models\n        method: GET\n        description: List available Claude models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-details\n      path: /models/{model_id}\n\
  \      description: Model details.\n      operations:\n      - name: get-model\n        method: GET\n        description: Get model metadata.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: Model ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ai-messaging-api\n    description: Unified REST API for Claude AI messaging.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Message operations.\n      operations:\n      - method: POST\n        name: create-message\n        description: Create a message.\n        call: claude-messages.create-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/token-counts\n      name: token-counts\n      description: Token counting.\n      operations:\n\
  \      - method: POST\n        name: count-tokens\n        description: Count message tokens.\n        call: claude-messages.count-message-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batches\n      name: batches\n      description: Batch management.\n      operations:\n      - method: GET\n        name: list-batches\n        description: List message batches.\n        call: claude-messages.list-message-batches\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-batch\n        description: Create a message batch.\n        call: claude-messages.create-message-batch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batches/{id}\n      name: batch-details\n      description: Individual batch management.\n      operations:\n      - method: GET\n        name: get-batch\n        description: Get batch status.\n        call: claude-messages.retrieve-message-batch\n\
  \        with:\n          message_batch_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-batch\n        description: Delete a batch.\n        call: claude-messages.delete-message-batch\n        with:\n          message_batch_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Model discovery.\n      operations:\n      - method: GET\n        name: list-models\n        description: List available models.\n        call: claude-messages.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{id}\n      name: model-details\n      description: Model details.\n      operations:\n      - method: GET\n        name: get-model\n        description: Get model metadata.\n        call: claude-messages.get-model\n        with:\n          model_id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ai-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted Claude messaging.\n    tools:\n    - name: create-message\n      description: Send a message to Claude and receive a response.\n      hints:\n        readOnly: false\n      call: claude-messages.create-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: count-message-tokens\n      description: Count tokens in a message.\n      hints:\n        readOnly: true\n      call: claude-messages.count-message-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-message-batch\n      description: Create a batch of message requests.\n      hints:\n        readOnly: false\n      call: claude-messages.create-message-batch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-message-batches\n      description: List all\
  \ message batches.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: claude-messages.list-message-batches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-message-batch\n      description: Get message batch status and details.\n      hints:\n        readOnly: true\n      call: claude-messages.retrieve-message-batch\n      with:\n        message_batch_id: tools.message_batch_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-message-batch-results\n      description: Get completed batch results.\n      hints:\n        readOnly: true\n      call: claude-messages.retrieve-message-batch-results\n      with:\n        message_batch_id: tools.message_batch_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-message-batch\n      description: Cancel an in-progress batch.\n      hints:\n        readOnly: false\n      call: claude-messages.cancel-message-batch\n\
  \      with:\n        message_batch_id: tools.message_batch_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-message-batch\n      description: Delete a completed batch.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: claude-messages.delete-message-batch\n      with:\n        message_batch_id: tools.message_batch_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List available Claude models.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: claude-messages.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model\n      description: Get model metadata.\n      hints:\n        readOnly: true\n      call: claude-messages.get-model\n      with:\n        model_id: tools.model_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/claude/refs/heads/main/capabilities/ai-messaging.yaml
tags:
- Anthropic
- Claude
- AI
- Messaging
tools:
- description: Send a message to Claude and receive a response.
  hints:
    readOnly: false
  name: create-message
- description: Count tokens in a message.
  hints:
    readOnly: true
  name: count-message-tokens
- description: Create a batch of message requests.
  hints:
    readOnly: false
  name: create-message-batch
- description: List all message batches.
  hints:
    openWorld: true
    readOnly: true
  name: list-message-batches
- description: Get message batch status and details.
  hints:
    readOnly: true
  name: retrieve-message-batch
- description: Get completed batch results.
  hints:
    readOnly: true
  name: retrieve-message-batch-results
- description: Cancel an in-progress batch.
  hints:
    readOnly: false
  name: cancel-message-batch
- description: Delete a completed batch.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-message-batch
- description: List available Claude models.
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: Get model metadata.
  hints:
    readOnly: true
  name: get-model
---
