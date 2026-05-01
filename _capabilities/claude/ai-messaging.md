---
categories:
- machine-learning
consumed_apis:
- claude-messages
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
- model details.
- cancel message batch
- model discovery.
- list batches
- count message tokens.
- machine learning
- list models
- count message tokens
- create a message batch.
- send a message to claude and receive a response.
- list available claude models.
- generative ai
- get model
- count tokens
- message operations.
- list all message batches.
- create message
- count tokens in a message.
- create a batch of message requests.
- create message batch
- artificial intelligence
- create batch
- chatbot
- natural language processing
- list message batches
- list message batches.
- get message batch status and details.
- large language models
- retrieve message batch results
- list available models.
- conversational ai
- messaging
- get batch status.
- anthropic
- cancel an in-progress batch.
- get completed batch results.
- delete a completed batch.
- individual batch management.
- token counting.
- claude
- batch management.
- ai
- retrieve message batch
- get batch
- delete a batch.
- delete message batch
- create a message.
- get model metadata.
- delete batch
slug: ai-messaging
source_filename: ai-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Claude AI Messaging\"\n  description: \"Unified workflow for AI-powered messaging, token counting, batch processing, and model discovery. Used by AI application developers and data scientists.\"\n  tags:\n    - Anthropic\n    - Claude\n    - AI\n    - Messaging\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ANTHROPIC_API_KEY: ANTHROPIC_API_KEY\n\ncapability:\n  consumes:\n    - import: claude-messages\n      location: ./shared/claude-messages.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ai-messaging-api\n      description: \"Unified REST API for Claude AI messaging.\"\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: \"Message operations.\"\n          operations:\n            - method: POST\n              name: create-message\n              description: \"Create a message.\"\n              call: \"\
  claude-messages.create-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/token-counts\n          name: token-counts\n          description: \"Token counting.\"\n          operations:\n            - method: POST\n              name: count-tokens\n              description: \"Count message tokens.\"\n              call: \"claude-messages.count-message-tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batches\n          name: batches\n          description: \"Batch management.\"\n          operations:\n            - method: GET\n              name: list-batches\n              description: \"List message batches.\"\n              call: \"claude-messages.list-message-batches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-batch\n\
  \              description: \"Create a message batch.\"\n              call: \"claude-messages.create-message-batch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batches/{id}\n          name: batch-details\n          description: \"Individual batch management.\"\n          operations:\n            - method: GET\n              name: get-batch\n              description: \"Get batch status.\"\n              call: \"claude-messages.retrieve-message-batch\"\n              with:\n                message_batch_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-batch\n              description: \"Delete a batch.\"\n              call: \"claude-messages.delete-message-batch\"\n              with:\n                message_batch_id: \"rest.id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"Model discovery.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List available models.\"\n              call: \"claude-messages.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{id}\n          name: model-details\n          description: \"Model details.\"\n          operations:\n            - method: GET\n              name: get-model\n              description: \"Get model metadata.\"\n              call: \"claude-messages.get-model\"\n              with:\n                model_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ai-messaging-mcp\n      transport: http\n      description: \"\
  MCP server for AI-assisted Claude messaging.\"\n      tools:\n        - name: create-message\n          description: \"Send a message to Claude and receive a response.\"\n          hints:\n            readOnly: false\n          call: \"claude-messages.create-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: count-message-tokens\n          description: \"Count tokens in a message.\"\n          hints:\n            readOnly: true\n          call: \"claude-messages.count-message-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-message-batch\n          description: \"Create a batch of message requests.\"\n          hints:\n            readOnly: false\n          call: \"claude-messages.create-message-batch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-message-batches\n          description: \"\
  List all message batches.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"claude-messages.list-message-batches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: retrieve-message-batch\n          description: \"Get message batch status and details.\"\n          hints:\n            readOnly: true\n          call: \"claude-messages.retrieve-message-batch\"\n          with:\n            message_batch_id: \"tools.message_batch_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: retrieve-message-batch-results\n          description: \"Get completed batch results.\"\n          hints:\n            readOnly: true\n          call: \"claude-messages.retrieve-message-batch-results\"\n          with:\n            message_batch_id: \"tools.message_batch_id\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: cancel-message-batch\n          description: \"Cancel an in-progress batch.\"\n          hints:\n            readOnly: false\n          call: \"claude-messages.cancel-message-batch\"\n          with:\n            message_batch_id: \"tools.message_batch_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-message-batch\n          description: \"Delete a completed batch.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"claude-messages.delete-message-batch\"\n          with:\n            message_batch_id: \"tools.message_batch_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-models\n          description: \"List available Claude models.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"claude-messages.list-models\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model\n          description: \"Get model metadata.\"\n          hints:\n            readOnly: true\n          call: \"claude-messages.get-model\"\n          with:\n            model_id: \"tools.model_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
