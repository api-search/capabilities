---
categories: []
consumed_apis: []
description: Generate high-quality multimodal embeddings for text, image, and code inputs using Jina AI's state-of-the-art embedding models. Supports synchronous embedding requests and batch jobs for large workloads.
layout: capability
name: Jina AI Embeddings API
operations:
- description: Create embeddings
  method: POST
  name: createembeddings
  path: /embeddings
- description: Submit batch embedding job
  method: POST
  name: submitbatchembeddings
  path: /batch/embeddings
- description: Get batch job status
  method: GET
  name: getbatchjob
  path: /batch/{batch_id}
- description: Cancel batch job
  method: DELETE
  name: cancelbatchjob
  path: /batch/{batch_id}
- description: Download batch job output
  method: GET
  name: getbatchoutput
  path: /batch/{batch_id}/output
- description: Retrieve batch job errors
  method: GET
  name: getbatcherrors
  path: /batch/{batch_id}/errors
personas: []
provider_name: Jina AI
provider_slug: jina-ai
search_terms:
- getbatchoutput
- download batch job output
- getbatchjob
- cancel batch job
- reranking
- getbatcherrors
- create embeddings
- cancelbatchjob
- retrieve batch job errors
- createembeddings
- embeddings
- ai
- jina
- machine learning
- api
- search
- submitbatchembeddings
- get batch job status
- submit batch embedding job
slug: jina-ai-capability
source_filename: jina-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jina AI Embeddings API\n  description: Generate high-quality multimodal embeddings for text, image, and code inputs using Jina AI's state-of-the-art\n    embedding models. Supports synchronous embedding requests and batch jobs for large workloads.\n  tags:\n  - Jina\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jina-ai\n    baseUri: https://api.jina.ai/v1\n    description: Jina AI Embeddings API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JINA_AI_TOKEN}}'\n    resources:\n    - name: embeddings\n      path: /embeddings\n      operations:\n      - name: createembeddings\n        method: POST\n        description: Create embeddings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-embeddings\n      path: /batch/embeddings\n      operations:\n\
  \      - name: submitbatchembeddings\n        method: POST\n        description: Submit batch embedding job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-batch-id\n      path: /batch/{batch_id}\n      operations:\n      - name: getbatchjob\n        method: GET\n        description: Get batch job status\n        inputParameters:\n        - name: batch_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelbatchjob\n        method: DELETE\n        description: Cancel batch job\n        inputParameters:\n        - name: batch_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: batch-batch-id-output\n      path: /batch/{batch_id}/output\n      operations:\n      - name: getbatchoutput\n        method: GET\n        description: Download batch job output\n        inputParameters:\n        - name: batch_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-batch-id-errors\n      path: /batch/{batch_id}/errors\n      operations:\n      - name: getbatcherrors\n        method: GET\n        description: Retrieve batch job errors\n        inputParameters:\n        - name: batch_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jina-ai-rest\n    description: REST adapter for Jina AI Embeddings\
  \ API.\n    resources:\n    - path: /embeddings\n      name: createembeddings\n      operations:\n      - method: POST\n        name: createembeddings\n        description: Create embeddings\n        call: jina-ai.createembeddings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/embeddings\n      name: submitbatchembeddings\n      operations:\n      - method: POST\n        name: submitbatchembeddings\n        description: Submit batch embedding job\n        call: jina-ai.submitbatchembeddings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/{batch_id}\n      name: getbatchjob\n      operations:\n      - method: GET\n        name: getbatchjob\n        description: Get batch job status\n        call: jina-ai.getbatchjob\n        with:\n          batch_id: rest.batch_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/{batch_id}\n      name: cancelbatchjob\n\
  \      operations:\n      - method: DELETE\n        name: cancelbatchjob\n        description: Cancel batch job\n        call: jina-ai.cancelbatchjob\n        with:\n          batch_id: rest.batch_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/{batch_id}/output\n      name: getbatchoutput\n      operations:\n      - method: GET\n        name: getbatchoutput\n        description: Download batch job output\n        call: jina-ai.getbatchoutput\n        with:\n          batch_id: rest.batch_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/{batch_id}/errors\n      name: getbatcherrors\n      operations:\n      - method: GET\n        name: getbatcherrors\n        description: Retrieve batch job errors\n        call: jina-ai.getbatcherrors\n        with:\n          batch_id: rest.batch_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n \
  \   namespace: jina-ai-mcp\n    transport: http\n    description: MCP adapter for Jina AI Embeddings API for AI agent use.\n    tools:\n    - name: createembeddings\n      description: Create embeddings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jina-ai.createembeddings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitbatchembeddings\n      description: Submit batch embedding job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jina-ai.submitbatchembeddings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbatchjob\n      description: Get batch job status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jina-ai.getbatchjob\n      with:\n        batch_id: tools.batch_id\n      inputParameters:\n      - name: batch_id\n        type: string\n\
  \        description: batch_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelbatchjob\n      description: Cancel batch job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jina-ai.cancelbatchjob\n      with:\n        batch_id: tools.batch_id\n      inputParameters:\n      - name: batch_id\n        type: string\n        description: batch_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbatchoutput\n      description: Download batch job output\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jina-ai.getbatchoutput\n      with:\n        batch_id: tools.batch_id\n      inputParameters:\n      - name: batch_id\n        type: string\n        description: batch_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: getbatcherrors\n      description: Retrieve batch job errors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jina-ai.getbatcherrors\n      with:\n        batch_id: tools.batch_id\n      inputParameters:\n      - name: batch_id\n        type: string\n        description: batch_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JINA_AI_TOKEN: JINA_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jina-ai/refs/heads/main/capabilities/jina-ai-capability.yaml
tags:
- Jina
- Ai
- API
tools:
- description: Create embeddings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createembeddings
- description: Submit batch embedding job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitbatchembeddings
- description: Get batch job status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbatchjob
- description: Cancel batch job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelbatchjob
- description: Download batch job output
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbatchoutput
- description: Retrieve batch job errors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbatcherrors
---
