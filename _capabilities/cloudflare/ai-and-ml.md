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
- perform similarity query.
- create embeddings
- get ai gateway details.
- cloudflare
- dns
- object storage
- artificial intelligence
- create an ai response.
- vectorize query vectors
- web performance
- serverless
- create chat completion
- gateway delete gateway
- list vectorize indexes
- vectorize insert vectors
- cdn
- platform
- delete an ai gateway.
- gateway list logs
- run an ai model.
- ai create text completion
- generate text embeddings.
- ai create response
- ai gateway management.
- list ai gateways
- vectorize create index
- vector database
- security
- api gateway
- create a text completion.
- vectorize index management.
- ai gateway
- ddos protection
- text embeddings.
- containers
- ai create chat completion
- create a vectorize index.
- gateway create gateway
- edge
- gateway list gateways
- edge computing
- real-time communication
- list ai gateways.
- gateway get gateway
- list ai gateway logs.
- list vectorize indexes.
- machine learning
- ai create embeddings
- create an ai gateway.
- vectorize list indexes
- chat completions.
- insert vectors into an index.
- vectorize delete index
- delete a vectorize index.
- create a chat completion.
- cloud
- list ai gateway instances.
- ai execute model
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
