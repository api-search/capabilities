---
categories:
- machine-learning
consumed_apis:
- cloudflare-workers-ai
- cloudflare-ai-gateway
- cloudflare-vectorize
description: AI and machine learning capabilities combining Workers AI model inference, AI Gateway for observability and control, and Vectorize for vector search. Used by AI/ML engineers building intelligent applications at the edge.
layout: capability
name: Cloudflare AI and ML
operations:
- description: Create a chat completion.
  method: POST
  name: create-chat-completion
  path: /v1/chat-completions
- description: Generate text embeddings.
  method: POST
  name: create-embeddings
  path: /v1/embeddings
- description: List AI gateways.
  method: GET
  name: list-ai-gateways
  path: /v1/ai-gateways
- description: List Vectorize indexes.
  method: GET
  name: list-vectorize-indexes
  path: /v1/vectorize-indexes
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- gateway create gateway
- get ai gateway details.
- create chat completion
- ai create chat completion
- create a vectorize index.
- security
- web performance
- create a chat completion.
- create a text completion.
- vector database
- list ai gateways
- gateway list logs
- cloudflare
- create embeddings
- list ai gateways.
- dns
- vectorize insert vectors
- ai gateway
- gateway get gateway
- vectorize index management.
- list ai gateway logs.
- edge
- list ai gateway instances.
- chat completions.
- ai create text completion
- insert vectors into an index.
- cloud
- api gateway
- list vectorize indexes.
- vectorize create index
- list vectorize indexes
- cdn
- text embeddings.
- artificial intelligence
- perform similarity query.
- real-time communication
- containers
- vectorize delete index
- vectorize list indexes
- gateway delete gateway
- machine learning
- object storage
- delete a vectorize index.
- ai gateway management.
- platform
- create an ai gateway.
- ai execute model
- ai create embeddings
- ai create response
- ddos protection
- gateway list gateways
- vectorize query vectors
- edge computing
- serverless
- generate text embeddings.
- delete an ai gateway.
- run an ai model.
- create an ai response.
slug: ai-and-ml
source_filename: ai-and-ml.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cloudflare AI and ML\"\n  description: \"AI and machine learning capabilities combining Workers AI model inference, AI Gateway for observability and control, and Vectorize for vector search. Used by AI/ML engineers building intelligent applications at the edge.\"\n  tags:\n    - Cloudflare\n    - Artificial Intelligence\n    - Machine Learning\n    - Vector Database\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cloudflare-workers-ai\n      location: ./shared/workers-ai.yaml\n    - import: cloudflare-ai-gateway\n      location: ./shared/ai-gateway.yaml\n    - import: cloudflare-vectorize\n      location: ./shared/vectorize.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: ai-ml-api\n      description: \"Unified REST API for Cloudflare AI and ML services.\"\n      resources:\n\
  \        - path: /v1/chat-completions\n          name: chat-completions\n          description: \"Chat completions.\"\n          operations:\n            - method: POST\n              name: create-chat-completion\n              description: \"Create a chat completion.\"\n              call: \"cloudflare-workers-ai.create-chat-completion\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Text embeddings.\"\n          operations:\n            - method: POST\n              name: create-embeddings\n              description: \"Generate text embeddings.\"\n              call: \"cloudflare-workers-ai.create-embeddings\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/ai-gateways\n          name: ai-gateways\n          description: \"AI Gateway management.\"\n          operations:\n            - method: GET\n              name: list-ai-gateways\n              description: \"List AI gateways.\"\n              call: \"cloudflare-ai-gateway.list-ai-gateways\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vectorize-indexes\n          name: vectorize-indexes\n          description: \"Vectorize index management.\"\n          operations:\n            - method: GET\n              name: list-vectorize-indexes\n              description: \"List Vectorize indexes.\"\n              call: \"cloudflare-vectorize.list-vectorize-indexes\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n\n    - type: mcp\n      port: 9082\n      namespace: ai-ml-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloudflare AI and ML management.\"\n      tools:\n        - name: ai-execute-model\n          description: \"Run an AI model.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers-ai.execute-ai-model\"\n          with:\n            account_id: \"tools.account_id\"\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-chat-completion\n          description: \"Create a chat completion.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers-ai.create-chat-completion\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-embeddings\n          description: \"Generate\
  \ text embeddings.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers-ai.create-embeddings\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-text-completion\n          description: \"Create a text completion.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers-ai.create-text-completion\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-response\n          description: \"Create an AI response.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers-ai.create-response\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-list-gateways\n\
  \          description: \"List AI Gateway instances.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-ai-gateway.list-ai-gateways\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-create-gateway\n          description: \"Create an AI Gateway.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-ai-gateway.create-ai-gateway\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-get-gateway\n          description: \"Get AI Gateway details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-ai-gateway.get-ai-gateway\"\n          with:\n            account_id: \"tools.account_id\"\n            gateway_id: \"tools.gateway_id\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-list-logs\n          description: \"List AI Gateway logs.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-ai-gateway.list-ai-gateway-logs\"\n          with:\n            account_id: \"tools.account_id\"\n            gateway_id: \"tools.gateway_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-delete-gateway\n          description: \"Delete an AI Gateway.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-ai-gateway.delete-ai-gateway\"\n          with:\n            account_id: \"tools.account_id\"\n            gateway_id: \"tools.gateway_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vectorize-list-indexes\n          description: \"List Vectorize indexes.\"\n     \
  \     hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-vectorize.list-vectorize-indexes\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vectorize-create-index\n          description: \"Create a Vectorize index.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-vectorize.create-vectorize-index\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vectorize-query-vectors\n          description: \"Perform similarity query.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-vectorize.query-vectors\"\n          with:\n            account_id: \"tools.account_id\"\n            index_name: \"tools.index_name\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: vectorize-insert-vectors\n          description: \"Insert vectors into an index.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-vectorize.insert-vectors\"\n          with:\n            account_id: \"tools.account_id\"\n            index_name: \"tools.index_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vectorize-delete-index\n          description: \"Delete a Vectorize index.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-vectorize.delete-vectorize-index\"\n          with:\n            account_id: \"tools.account_id\"\n            index_name: \"tools.index_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudflare/refs/heads/main/capabilities/ai-and-ml.yaml
tags:
- Cloudflare
- Artificial Intelligence
- Machine Learning
- Vector Database
tools:
- description: Run an AI model.
  hints:
    readOnly: true
  name: ai-execute-model
- description: Create a chat completion.
  hints:
    readOnly: true
  name: ai-create-chat-completion
- description: Generate text embeddings.
  hints:
    readOnly: true
  name: ai-create-embeddings
- description: Create a text completion.
  hints:
    readOnly: true
  name: ai-create-text-completion
- description: Create an AI response.
  hints:
    readOnly: true
  name: ai-create-response
- description: List AI Gateway instances.
  hints:
    openWorld: true
    readOnly: true
  name: gateway-list-gateways
- description: Create an AI Gateway.
  hints:
    readOnly: false
  name: gateway-create-gateway
- description: Get AI Gateway details.
  hints:
    readOnly: true
  name: gateway-get-gateway
- description: List AI Gateway logs.
  hints:
    readOnly: true
  name: gateway-list-logs
- description: Delete an AI Gateway.
  hints:
    destructive: true
    idempotent: true
  name: gateway-delete-gateway
- description: List Vectorize indexes.
  hints:
    openWorld: true
    readOnly: true
  name: vectorize-list-indexes
- description: Create a Vectorize index.
  hints:
    readOnly: false
  name: vectorize-create-index
- description: Perform similarity query.
  hints:
    readOnly: true
  name: vectorize-query-vectors
- description: Insert vectors into an index.
  hints:
    readOnly: false
  name: vectorize-insert-vectors
- description: Delete a Vectorize index.
  hints:
    destructive: true
    idempotent: true
  name: vectorize-delete-index
---
