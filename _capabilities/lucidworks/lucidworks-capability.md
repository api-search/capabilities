---
categories: []
consumed_apis: []
description: The Lucidworks AI Platform API exposes prediction endpoints for FAQ enrichment, keyword extraction, named entity recognition (NER), retrieval augmented generation (RAG), summarization, passthrough LLM calls, and standalone query rewriting. Predictions are submitted by use case and fetched asynchronously by prediction ID.
layout: capability
name: Lucidworks AI Platform API
operations:
- description: Create prediction by use case
  method: POST
  name: createprediction
  path: /ai/prediction/{useCase}/{modelId}
- description: Get prediction results
  method: GET
  name: getprediction
  path: /ai/prediction/{predictionId}
- description: Request access token
  method: POST
  name: requestaccesstoken
  path: /oauth2/token
personas: []
provider_name: Lucidworks
provider_slug: lucidworks
search_terms:
- requestaccesstoken
- createprediction
- enterprise search
- vector search
- getprediction
- api
- search
- lucidworks
- request access token
- commerce
- get prediction results
- rag
- artificial intelligence
- create prediction by use case
slug: lucidworks-capability
source_filename: lucidworks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lucidworks AI Platform API\n  description: The Lucidworks AI Platform API exposes prediction endpoints for FAQ enrichment, keyword extraction, named entity\n    recognition (NER), retrieval augmented generation (RAG), summarization, passthrough LLM calls, and standalone query rewriting.\n    Predictions are submitted by use case and fetched asynchronously by prediction ID.\n  tags:\n  - Lucidworks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lucidworks\n    baseUri: https://api.lucidworks.ai\n    description: Lucidworks AI Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LUCIDWORKS_TOKEN}}'\n    resources:\n    - name: ai-prediction-usecase-modelid\n      path: /ai/prediction/{useCase}/{modelId}\n      operations:\n      - name: createprediction\n        method: POST\n        description: Create prediction by use case\n        inputParameters:\n\
  \        - name: useCase\n          in: path\n          type: string\n          required: true\n        - name: modelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-prediction-predictionid\n      path: /ai/prediction/{predictionId}\n      operations:\n      - name: getprediction\n        method: GET\n        description: Get prediction results\n        inputParameters:\n        - name: predictionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-token\n      path: /oauth2/token\n      operations:\n      - name: requestaccesstoken\n        method: POST\n        description: Request access token\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lucidworks-rest\n    description: REST adapter for Lucidworks AI Platform API.\n    resources:\n    - path: /ai/prediction/{useCase}/{modelId}\n      name: createprediction\n      operations:\n      - method: POST\n        name: createprediction\n        description: Create prediction by use case\n        call: lucidworks.createprediction\n        with:\n          useCase: rest.useCase\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ai/prediction/{predictionId}\n      name: getprediction\n      operations:\n      - method: GET\n        name: getprediction\n        description: Get prediction results\n        call: lucidworks.getprediction\n        with:\n          predictionId: rest.predictionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/token\n\
  \      name: requestaccesstoken\n      operations:\n      - method: POST\n        name: requestaccesstoken\n        description: Request access token\n        call: lucidworks.requestaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lucidworks-mcp\n    transport: http\n    description: MCP adapter for Lucidworks AI Platform API for AI agent use.\n    tools:\n    - name: createprediction\n      description: Create prediction by use case\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lucidworks.createprediction\n      with:\n        useCase: tools.useCase\n        modelId: tools.modelId\n      inputParameters:\n      - name: useCase\n        type: string\n        description: useCase\n        required: true\n      - name: modelId\n        type: string\n        description: modelId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getprediction\n      description: Get prediction results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lucidworks.getprediction\n      with:\n        predictionId: tools.predictionId\n      inputParameters:\n      - name: predictionId\n        type: string\n        description: predictionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requestaccesstoken\n      description: Request access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lucidworks.requestaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LUCIDWORKS_TOKEN: LUCIDWORKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lucidworks/refs/heads/main/capabilities/lucidworks-capability.yaml
tags:
- Lucidworks
- API
tools:
- description: Create prediction by use case
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprediction
- description: Get prediction results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprediction
- description: Request access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestaccesstoken
---
