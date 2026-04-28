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
- list ai gateway logs.
- vectorize insert vectors
- ai create chat completion
- ai create response
- edge
- create chat completion
- vectorize list indexes
- vectorize create index
- platform
- real-time communication
- list vectorize indexes.
- text embeddings.
- list ai gateway instances.
- run an ai model.
- generate text embeddings.
- edge computing
- create a vectorize index.
- vectorize delete index
- list vectorize indexes
- gateway list gateways
- create an ai gateway.
- delete a vectorize index.
- insert vectors into an index.
- api gateway
- chat completions.
- ai create embeddings
- delete an ai gateway.
- ai execute model
- containers
- create an ai response.
- web performance
- security
- ai create text completion
- machine learning
- vectorize index management.
- gateway list logs
- create embeddings
- ai gateway
- cdn
- list ai gateways.
- ai gateway management.
- artificial intelligence
- gateway create gateway
- gateway get gateway
- cloudflare
- gateway delete gateway
- list ai gateways
- ddos protection
- serverless
- create a chat completion.
- cloud
- vector database
- dns
- object storage
- get ai gateway details.
- perform similarity query.
- vectorize query vectors
- create a text completion.
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
