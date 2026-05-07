---
categories: []
consumed_apis: []
description: 'FASHN AI is a generative-image platform tailored for fashion. The public API exposes an asynchronous prediction workflow: clients submit a job against a named model with model-specific inputs, then poll a status endpoint until the prediction completes. Models include Try-On Max, Product to Model, Face to Model, Model Create, Model Swap, Edit, Reframe, Image to Video, and Background Remove.'
layout: capability
name: FASHN AI API
operations:
- description: Submit a new prediction job
  method: POST
  name: runprediction
  path: /run
- description: Retrieve prediction status and output
  method: GET
  name: getpredictionstatus
  path: /status/{id}
personas: []
provider_name: FASHN AI
provider_slug: fashn
search_terms:
- retrieve prediction status and output
- submit a new prediction job
- fashion
- getpredictionstatus
- virtual try-on
- clothing
- ai
- api
- runprediction
- fashn
slug: fashn-capability
source_filename: fashn-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FASHN AI API\n  description: 'FASHN AI is a generative-image platform tailored for fashion. The public API exposes an asynchronous prediction\n    workflow: clients submit a job against a named model with model-specific inputs, then poll a status endpoint until the\n    prediction completes. Models include Try-On Max, Product to Model, Face to Model, Model Create, Model Swap, Edit, Reframe,\n    Image to Video, and Background Remove.'\n  tags:\n  - Fashn\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fashn\n    baseUri: https://api.fashn.ai/v1\n    description: FASHN AI API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FASHN_TOKEN}}'\n    resources:\n    - name: run\n      path: /run\n      operations:\n      - name: runprediction\n        method: POST\n        description: Submit a new prediction job\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: status-id\n      path: /status/{id}\n      operations:\n      - name: getpredictionstatus\n        method: GET\n        description: Retrieve prediction status and output\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Prediction identifier returned from /run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fashn-rest\n    description: REST adapter for FASHN AI API.\n    resources:\n    - path: /run\n      name: runprediction\n      operations:\n      - method: POST\n        name: runprediction\n        description: Submit a new prediction job\n        call: fashn.runprediction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /status/{id}\n\
  \      name: getpredictionstatus\n      operations:\n      - method: GET\n        name: getpredictionstatus\n        description: Retrieve prediction status and output\n        call: fashn.getpredictionstatus\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fashn-mcp\n    transport: http\n    description: MCP adapter for FASHN AI API for AI agent use.\n    tools:\n    - name: runprediction\n      description: Submit a new prediction job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fashn.runprediction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpredictionstatus\n      description: Retrieve prediction status and output\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fashn.getpredictionstatus\n      with:\n        id: tools.id\n\
  \      inputParameters:\n      - name: id\n        type: string\n        description: Prediction identifier returned from /run.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FASHN_TOKEN: FASHN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fashn/refs/heads/main/capabilities/fashn-capability.yaml
tags:
- Fashn
- API
tools:
- description: Submit a new prediction job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runprediction
- description: Retrieve prediction status and output
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpredictionstatus
---
