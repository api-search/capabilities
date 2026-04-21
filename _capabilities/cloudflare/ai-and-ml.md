---
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
- web performance
- vector database
- ai create response
- list ai gateway logs.
- create a vectorize index.
- gateway list logs
- api gateway
- cloudflare
- create an ai response.
- vectorize insert vectors
- ai gateway
- edge computing
- list ai gateways
- create embeddings
- containers
- ddos protection
- ai create text completion
- real-time communication
- create an ai gateway.
- list vectorize indexes.
- machine learning
- list ai gateway instances.
- vectorize list indexes
- ai execute model
- gateway delete gateway
- platform
- edge
- delete an ai gateway.
- delete a vectorize index.
- gateway create gateway
- object storage
- security
- ai create embeddings
- cdn
- serverless
- run an ai model.
- create a chat completion.
- ai gateway management.
- vectorize index management.
- gateway list gateways
- perform similarity query.
- text embeddings.
- cloud
- ai create chat completion
- get ai gateway details.
- create chat completion
- dns
- list ai gateways.
- artificial intelligence
- create a text completion.
- vectorize query vectors
- chat completions.
- vectorize delete index
- gateway get gateway
- vectorize create index
- generate text embeddings.
- list vectorize indexes
- insert vectors into an index.
slug: ai-and-ml
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
