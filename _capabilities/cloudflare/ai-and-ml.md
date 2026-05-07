---
categories:
- machine-learning
consumed_apis: []
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
- cloudflare
- ddos protection
- create a vectorize index.
- text embeddings.
- containers
- generate text embeddings.
- list ai gateways.
- ai create text completion
- list ai gateway instances.
- ai gateway
- ai gateway management.
- gateway list logs
- create an ai gateway.
- vectorize delete index
- platform
- ai create chat completion
- list ai gateway logs.
- vectorize list indexes
- get ai gateway details.
- ai execute model
- edge computing
- chat completions.
- artificial intelligence
- list vectorize indexes
- ai create response
- edge
- gateway delete gateway
- web performance
- vectorize query vectors
- list ai gateways
- machine learning
- real-time communication
- serverless
- ai create embeddings
- vectorize index management.
- api gateway
- delete a vectorize index.
- list vectorize indexes.
- perform similarity query.
- vectorize insert vectors
- object storage
- create a chat completion.
- vector database
- create an ai response.
- cloud
- run an ai model.
- gateway list gateways
- delete an ai gateway.
- dns
- cdn
- gateway get gateway
- create embeddings
- create chat completion
- gateway create gateway
- insert vectors into an index.
- security
- vectorize create index
- create a text completion.
slug: ai-and-ml
source_filename: ai-and-ml.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cloudflare AI and ML\n  description: AI and machine learning capabilities combining Workers AI model inference, AI Gateway for observability and\n    control, and Vectorize for vector search. Used by AI/ML engineers building intelligent applications at the edge.\n  tags:\n  - Cloudflare\n  - Artificial Intelligence\n  - Machine Learning\n  - Vector Database\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudflare-workers-ai\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Workers AI API for running ML models at the edge.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: ai-models\n      path: /accounts/{account_id}/ai/run/{model_name}\n      description: Execute AI models.\n      operations:\n      - name:\
  \ execute-ai-model\n        method: POST\n        description: Run an AI model with the given input.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Model name to execute.\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat-completions\n      path: /accounts/{account_id}/ai/v1/chat/completions\n      description: OpenAI-compatible chat completions.\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Create a chat completion using OpenAI-compatible endpoint.\n        inputParameters:\n        - name: account_id\n    \
  \      in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: embeddings\n      path: /accounts/{account_id}/ai/v1/embeddings\n      description: Generate text embeddings.\n      operations:\n      - name: create-embeddings\n        method: POST\n        description: Create embeddings for input text.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: text-completions\n      path: /accounts/{account_id}/ai/v1/completions\n      description: Text completions.\n      operations:\n      - name: create-text-completion\n        method: POST\n        description: Create a text completion.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: responses\n      path: /accounts/{account_id}/ai/v1/responses\n      description: Create AI responses.\n      operations:\n      - name: create-response\n        method: POST\n        description: Create an AI response.\n        inputParameters:\n        - name: account_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-ai-gateway\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare AI Gateway API for managing AI gateways and viewing logs.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: gateways\n      path: /accounts/{account_id}/ai-gateway/gateways\n      description: Manage AI Gateway instances.\n      operations:\n      - name: list-ai-gateways\n        method: GET\n        description: List all AI Gateway instances.\n        inputParameters:\n        - name: account_id\n          in: path\n          type:\
  \ string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ai-gateway\n        method: POST\n        description: Create a new AI Gateway.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateway\n      path: /accounts/{account_id}/ai-gateway/gateways/{gateway_id}\n      description: Manage a specific AI Gateway.\n      operations:\n      - name: get-ai-gateway\n        method: GET\n        description: Get AI Gateway details.\n        inputParameters:\n\
  \        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: gateway_id\n          in: path\n          type: string\n          required: true\n          description: Gateway identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ai-gateway\n        method: PUT\n        description: Update an AI Gateway.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: gateway_id\n          in: path\n          type: string\n          required: true\n          description: Gateway identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: delete-ai-gateway\n        method: DELETE\n        description: Delete an AI Gateway.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: gateway_id\n          in: path\n          type: string\n          required: true\n          description: Gateway identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateway-logs\n      path: /accounts/{account_id}/ai-gateway/gateways/{gateway_id}/logs\n      description: AI Gateway logs.\n      operations:\n      - name: list-ai-gateway-logs\n        method: GET\n        description: List logs for an AI Gateway.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n\
  \        - name: gateway_id\n          in: path\n          type: string\n          required: true\n          description: Gateway identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-vectorize\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Vectorize API for managing vector indexes and performing similarity queries.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: indexes\n      path: /accounts/{account_id}/vectorize/v2/indexes\n      description: Manage vector indexes.\n      operations:\n      - name: list-vectorize-indexes\n        method: GET\n        description: List all Vectorize indexes.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-vectorize-index\n        method: POST\n        description: Create a new Vectorize index.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            config: '{{tools.config}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: index\n      path: /accounts/{account_id}/vectorize/v2/indexes/{index_name}\n      description: Manage a specific vector index.\n      operations:\n      - name: get-vectorize-index\n        method: GET\n        description: Get Vectorize index details.\n        inputParameters:\n        - name: account_id\n          in: path\n\
  \          type: string\n          required: true\n          description: Account identifier.\n        - name: index_name\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-vectorize-index\n        method: DELETE\n        description: Delete a Vectorize index.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: index_name\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vectors\n      path: /accounts/{account_id}/vectorize/v2/indexes/{index_name}/insert\n      description:\
  \ Insert vectors.\n      operations:\n      - name: insert-vectors\n        method: POST\n        description: Insert vectors into an index.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: index_name\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /accounts/{account_id}/vectorize/v2/indexes/{index_name}/query\n      description: Query vectors.\n      operations:\n      - name: query-vectors\n        method: POST\n        description: Perform a similarity query on vectors.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n\
  \        - name: index_name\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        body:\n          type: json\n          data:\n            vector: '{{tools.vector}}'\n            topK: '{{tools.top_k}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: ai-ml-api\n    description: Unified REST API for Cloudflare AI and ML services.\n    resources:\n    - path: /v1/chat-completions\n      name: chat-completions\n      description: Chat completions.\n      operations:\n      - method: POST\n        name: create-chat-completion\n        description: Create a chat completion.\n        call: cloudflare-workers-ai.create-chat-completion\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n     \
  \ name: embeddings\n      description: Text embeddings.\n      operations:\n      - method: POST\n        name: create-embeddings\n        description: Generate text embeddings.\n        call: cloudflare-workers-ai.create-embeddings\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-gateways\n      name: ai-gateways\n      description: AI Gateway management.\n      operations:\n      - method: GET\n        name: list-ai-gateways\n        description: List AI gateways.\n        call: cloudflare-ai-gateway.list-ai-gateways\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vectorize-indexes\n      name: vectorize-indexes\n      description: Vectorize index management.\n      operations:\n      - method: GET\n        name: list-vectorize-indexes\n        description: List Vectorize indexes.\n        call:\
  \ cloudflare-vectorize.list-vectorize-indexes\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: ai-ml-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloudflare AI and ML management.\n    tools:\n    - name: ai-execute-model\n      description: Run an AI model.\n      hints:\n        readOnly: true\n      call: cloudflare-workers-ai.execute-ai-model\n      with:\n        account_id: tools.account_id\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ai-create-chat-completion\n      description: Create a chat completion.\n      hints:\n        readOnly: true\n      call: cloudflare-workers-ai.create-chat-completion\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ai-create-embeddings\n      description:\
  \ Generate text embeddings.\n      hints:\n        readOnly: true\n      call: cloudflare-workers-ai.create-embeddings\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ai-create-text-completion\n      description: Create a text completion.\n      hints:\n        readOnly: true\n      call: cloudflare-workers-ai.create-text-completion\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ai-create-response\n      description: Create an AI response.\n      hints:\n        readOnly: true\n      call: cloudflare-workers-ai.create-response\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gateway-list-gateways\n      description: List AI Gateway instances.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-ai-gateway.list-ai-gateways\n\
  \      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gateway-create-gateway\n      description: Create an AI Gateway.\n      hints:\n        readOnly: false\n      call: cloudflare-ai-gateway.create-ai-gateway\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gateway-get-gateway\n      description: Get AI Gateway details.\n      hints:\n        readOnly: true\n      call: cloudflare-ai-gateway.get-ai-gateway\n      with:\n        account_id: tools.account_id\n        gateway_id: tools.gateway_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gateway-list-logs\n      description: List AI Gateway logs.\n      hints:\n        readOnly: true\n      call: cloudflare-ai-gateway.list-ai-gateway-logs\n      with:\n        account_id: tools.account_id\n        gateway_id: tools.gateway_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: gateway-delete-gateway\n      description: Delete an AI Gateway.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-ai-gateway.delete-ai-gateway\n      with:\n        account_id: tools.account_id\n        gateway_id: tools.gateway_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vectorize-list-indexes\n      description: List Vectorize indexes.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-vectorize.list-vectorize-indexes\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vectorize-create-index\n      description: Create a Vectorize index.\n      hints:\n        readOnly: false\n      call: cloudflare-vectorize.create-vectorize-index\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: vectorize-query-vectors\n      description: Perform similarity query.\n      hints:\n        readOnly: true\n      call: cloudflare-vectorize.query-vectors\n      with:\n        account_id: tools.account_id\n        index_name: tools.index_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vectorize-insert-vectors\n      description: Insert vectors into an index.\n      hints:\n        readOnly: false\n      call: cloudflare-vectorize.insert-vectors\n      with:\n        account_id: tools.account_id\n        index_name: tools.index_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vectorize-delete-index\n      description: Delete a Vectorize index.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-vectorize.delete-vectorize-index\n      with:\n        account_id: tools.account_id\n        index_name: tools.index_name\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n"
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
