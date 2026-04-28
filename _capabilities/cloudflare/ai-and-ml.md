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
- run an ai model.
- create an ai response.
- containers
- chat completions.
- list ai gateways.
- delete a vectorize index.
- api gateway
- vector database
- object storage
- vectorize insert vectors
- vectorize query vectors
- gateway create gateway
- gateway get gateway
- get ai gateway details.
- real-time communication
- delete an ai gateway.
- create embeddings
- list vectorize indexes.
- generate text embeddings.
- dns
- edge computing
- cdn
- create a vectorize index.
- create chat completion
- perform similarity query.
- security
- vectorize list indexes
- gateway list gateways
- ai create embeddings
- gateway list logs
- edge
- create an ai gateway.
- list vectorize indexes
- ai gateway management.
- ddos protection
- machine learning
- create a text completion.
- ai gateway
- vectorize index management.
- vectorize delete index
- cloud
- ai create response
- list ai gateway logs.
- list ai gateways
- list ai gateway instances.
- web performance
- insert vectors into an index.
- vectorize create index
- serverless
- ai create text completion
- artificial intelligence
- gateway delete gateway
- create a chat completion.
- cloudflare
- platform
- ai create chat completion
- text embeddings.
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
