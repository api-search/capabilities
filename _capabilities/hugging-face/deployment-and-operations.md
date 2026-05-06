---
categories:
- machine-learning
consumed_apis: []
description: Unified workflow for deploying, scaling, and operating ML model inference endpoints on dedicated infrastructure. Combines Inference Endpoints management with TGI server monitoring. Used by ML platform engineers and DevOps teams.
layout: capability
name: Hugging Face Deployment and Operations
operations:
- description: List all endpoints
  method: GET
  name: list-endpoints
  path: /v1/endpoints/{namespace}
- description: Create a new endpoint
  method: POST
  name: create-endpoint
  path: /v1/endpoints/{namespace}
- description: Get endpoint details
  method: GET
  name: get-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Update endpoint configuration
  method: PUT
  name: update-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Delete an endpoint
  method: DELETE
  name: delete-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Pause a running endpoint
  method: POST
  name: pause-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}/pause
- description: Resume a paused endpoint
  method: POST
  name: resume-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}/resume
- description: Get endpoint logs
  method: GET
  name: get-logs
  path: /v1/endpoints/{namespace}/{endpoint_name}/logs
- description: Get endpoint metrics
  method: GET
  name: get-metrics
  path: /v1/endpoints/{namespace}/{endpoint_name}/metrics
- description: Check TGI server health
  method: GET
  name: health-check
  path: /v1/server/health
- description: Get TGI server info
  method: GET
  name: get-info
  path: /v1/server/info
- description: List available cloud providers
  method: GET
  name: list-providers
  path: /v1/providers
personas: []
provider_name: Hugging Face
provider_slug: hugging-face
search_terms:
- get endpoint logs
- create a new endpoint
- create a new dedicated inference endpoint.
- list all endpoints
- mlops
- create endpoint
- get metrics
- update an existing endpoint configuration.
- infrastructure
- get endpoint metrics
- get endpoint details
- pause a running endpoint
- get metrics for an endpoint.
- tgi server info
- manage inference endpoints
- check tgi server health
- hugging face
- get information about the deployed model and tgi server.
- pause an endpoint
- deployment
- get tgi server info
- delete a dedicated inference endpoint.
- get logs for an endpoint.
- resume endpoint
- get details of a specific endpoint.
- tgi server health
- scale an endpoint to zero replicas.
- operations
- individual endpoint operations
- delete endpoint
- get logs
- get prometheus metrics from the tgi server.
- list all dedicated inference endpoints for a namespace.
- resume an endpoint
- tgi metrics
- list providers
- update endpoint configuration
- resume a paused endpoint.
- get info
- check if the tgi server is healthy and responding.
- update endpoint
- get endpoint
- resume a paused endpoint
- list endpoints
- pause a running endpoint to stop billing.
- health check
- cloud providers
- scale to zero
- delete an endpoint
- pause endpoint
- list available cloud providers
- list available cloud providers and hardware options.
- tgi health check
slug: deployment-and-operations
source_filename: deployment-and-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hugging Face Deployment and Operations\n  description: Unified workflow for deploying, scaling, and operating ML model inference endpoints on dedicated infrastructure.\n    Combines Inference Endpoints management with TGI server monitoring. Used by ML platform engineers and DevOps teams.\n  tags:\n  - Hugging Face\n  - Deployment\n  - Operations\n  - Infrastructure\n  - MLOps\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HF_API_TOKEN: HF_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: hf-endpoints\n    baseUri: https://api.endpoints.huggingface.cloud/v2\n    description: Deploy and manage dedicated inference endpoints.\n    authentication:\n      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: endpoints\n      path: /endpoint/{namespace}\n      description: Manage inference endpoints\n      operations:\n      - name: list-endpoints\n        method:\
  \ GET\n        description: List all Inference Endpoints for a namespace.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-endpoint\n        method: POST\n        description: Create a new Inference Endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            model: '{{tools.model}}'\n            provider: '{{tools.provider}}'\n            region: '{{tools.region}}'\n\
  \            type: '{{tools.type}}'\n    - name: endpoint-by-name\n      path: /endpoint/{namespace}/{endpoint_name}\n      description: Manage individual endpoints\n      operations:\n      - name: get-endpoint\n        method: GET\n        description: Get details of a specific endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-endpoint\n        method: PUT\n        description: Update an existing endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization\
  \ namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            type: '{{tools.type}}'\n      - name: delete-endpoint\n        method: DELETE\n        description: Delete an endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-pause\n      path: /endpoint/{namespace}/{endpoint_name}/pause\n\
  \      description: Pause an endpoint\n      operations:\n      - name: pause-endpoint\n        method: POST\n        description: Pause a running endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-resume\n      path: /endpoint/{namespace}/{endpoint_name}/resume\n      description: Resume an endpoint\n      operations:\n      - name: resume-endpoint\n        method: POST\n        description: Resume a paused endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User\
  \ or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-scale-to-zero\n      path: /endpoint/{namespace}/{endpoint_name}/scale-to-zero\n      description: Scale endpoint to zero\n      operations:\n      - name: scale-to-zero\n        method: POST\n        description: Scale an endpoint to zero replicas.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: endpoint-logs\n      path: /endpoint/{namespace}/{endpoint_name}/logs\n      description: Get endpoint logs\n      operations:\n      - name: get-endpoint-logs\n        method: GET\n        description: Get logs for an endpoint.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-metrics\n      path: /endpoint/{namespace}/{endpoint_name}/metrics\n      description: Get endpoint metrics\n      operations:\n      - name: get-endpoint-metrics\n        method: GET\n        description: Get metrics for an endpoint.\n        inputParameters:\n     \
  \   - name: namespace\n          in: path\n          type: string\n          required: true\n          description: User or organization namespace\n        - name: endpoint_name\n          in: path\n          type: string\n          required: true\n          description: The endpoint name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers\n      path: /provider\n      description: List cloud providers\n      operations:\n      - name: list-providers\n        method: GET\n        description: List available cloud providers and hardware.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: hf-tgi\n    baseUri: https://api-inference.huggingface.co\n    description: High-performance LLM serving with streaming, tool calling, and structured output.\n    authentication:\n\
  \      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: generate\n      path: /generate\n      description: Generate text\n      operations:\n      - name: generate\n        method: POST\n        description: Generate text using the TGI native endpoint.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: generate-stream\n      path: /generate_stream\n      description: Generate text with streaming\n      operations:\n      - name: generate-stream\n        method: POST\n        description: Generate text with server-sent events streaming.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: chat-completions\n      path: /v1/chat/completions\n      description: OpenAI-compatible chat completions\n      operations:\n      - name: chat-completions\n        method: POST\n        description: Create chat completions using OpenAI-compatible Messages API.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            max_tokens: '{{tools.max_tokens}}'\n            temperature: '{{tools.temperature}}'\n            stream: '{{tools.stream}}'\n    - name: completions\n      path: /v1/completions\n      description: OpenAI-compatible completions\n      operations:\n      - name: completions\n        method:\
  \ POST\n        description: Create text completions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n            max_tokens: '{{tools.max_tokens}}'\n    - name: models\n      path: /v1/models\n      description: List available models\n      operations:\n      - name: list-models\n        method: GET\n        description: List available models on the TGI server.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      description: Server information\n      operations:\n      - name: get-info\n        method: GET\n        description: Get information about the deployed model and server.\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      description: Health check\n      operations:\n      - name: health-check\n        method: GET\n        description: Check if the TGI server is healthy.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Server metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get Prometheus metrics from the TGI server.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokenize\n      path: /tokenize\n      description: Tokenize text\n      operations:\n      - name: tokenize\n        method: POST\n\
  \        description: Tokenize input text and return token IDs.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: hf-deployment-api\n    description: Unified REST API for ML deployment and operations management.\n    resources:\n    - path: /v1/endpoints/{namespace}\n      name: endpoints\n      description: Manage inference endpoints\n      operations:\n      - method: GET\n        name: list-endpoints\n        description: List all endpoints\n        call: hf-endpoints.list-endpoints\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-endpoint\n        description: Create a new endpoint\n        call: hf-endpoints.create-endpoint\n\
  \        with:\n          namespace: rest.namespace\n          name: rest.name\n          model: rest.model\n          provider: rest.provider\n          region: rest.region\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/{namespace}/{endpoint_name}\n      name: endpoint-details\n      description: Individual endpoint operations\n      operations:\n      - method: GET\n        name: get-endpoint\n        description: Get endpoint details\n        call: hf-endpoints.get-endpoint\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-endpoint\n        description: Update endpoint configuration\n        call: hf-endpoints.update-endpoint\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n          model: rest.model\n\
  \          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-endpoint\n        description: Delete an endpoint\n        call: hf-endpoints.delete-endpoint\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/{namespace}/{endpoint_name}/pause\n      name: endpoint-pause\n      description: Pause an endpoint\n      operations:\n      - method: POST\n        name: pause-endpoint\n        description: Pause a running endpoint\n        call: hf-endpoints.pause-endpoint\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/{namespace}/{endpoint_name}/resume\n      name: endpoint-resume\n      description: Resume an endpoint\n\
  \      operations:\n      - method: POST\n        name: resume-endpoint\n        description: Resume a paused endpoint\n        call: hf-endpoints.resume-endpoint\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/{namespace}/{endpoint_name}/logs\n      name: endpoint-logs\n      description: Get endpoint logs\n      operations:\n      - method: GET\n        name: get-logs\n        description: Get endpoint logs\n        call: hf-endpoints.get-endpoint-logs\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/{namespace}/{endpoint_name}/metrics\n      name: endpoint-metrics\n      description: Get endpoint metrics\n      operations:\n      - method: GET\n        name: get-metrics\n        description:\
  \ Get endpoint metrics\n        call: hf-endpoints.get-endpoint-metrics\n        with:\n          namespace: rest.namespace\n          endpoint_name: rest.endpoint_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/server/health\n      name: server-health\n      description: TGI server health\n      operations:\n      - method: GET\n        name: health-check\n        description: Check TGI server health\n        call: hf-tgi.health-check\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/server/info\n      name: server-info\n      description: TGI server info\n      operations:\n      - method: GET\n        name: get-info\n        description: Get TGI server info\n        call: hf-tgi.get-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/providers\n      name: providers\n      description: Cloud providers\n      operations:\n      - method: GET\n        name:\
  \ list-providers\n        description: List available cloud providers\n        call: hf-endpoints.list-providers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: hf-deployment-mcp\n    transport: http\n    description: MCP server for AI-assisted ML deployment and operations management.\n    tools:\n    - name: list-endpoints\n      description: List all dedicated inference endpoints for a namespace.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-endpoints.list-endpoints\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-endpoint\n      description: Create a new dedicated inference endpoint.\n      hints:\n        readOnly: false\n      call: hf-endpoints.create-endpoint\n      with:\n        namespace: tools.namespace\n        name: tools.name\n        model: tools.model\n        provider: tools.provider\n\
  \        region: tools.region\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-endpoint\n      description: Get details of a specific endpoint.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-endpoints.get-endpoint\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-endpoint\n      description: Update an existing endpoint configuration.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: hf-endpoints.update-endpoint\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n        model: tools.model\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-endpoint\n      description: Delete a dedicated inference endpoint.\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n      call: hf-endpoints.delete-endpoint\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-endpoint\n      description: Pause a running endpoint to stop billing.\n      hints:\n        readOnly: false\n      call: hf-endpoints.pause-endpoint\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-endpoint\n      description: Resume a paused endpoint.\n      hints:\n        readOnly: false\n      call: hf-endpoints.resume-endpoint\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scale-to-zero\n      description: Scale an endpoint to zero replicas.\n      hints:\n        readOnly:\
  \ false\n      call: hf-endpoints.scale-to-zero\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-endpoint-logs\n      description: Get logs for an endpoint.\n      hints:\n        readOnly: true\n      call: hf-endpoints.get-endpoint-logs\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-endpoint-metrics\n      description: Get metrics for an endpoint.\n      hints:\n        readOnly: true\n      call: hf-endpoints.get-endpoint-metrics\n      with:\n        namespace: tools.namespace\n        endpoint_name: tools.endpoint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-providers\n      description: List available cloud providers and hardware options.\n      hints:\n        readOnly: true\n \
  \     call: hf-endpoints.list-providers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-health-check\n      description: Check if the TGI server is healthy and responding.\n      hints:\n        readOnly: true\n      call: hf-tgi.health-check\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-server-info\n      description: Get information about the deployed model and TGI server.\n      hints:\n        readOnly: true\n      call: hf-tgi.get-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-metrics\n      description: Get Prometheus metrics from the TGI server.\n      hints:\n        readOnly: true\n      call: hf-tgi.get-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hugging-face/refs/heads/main/capabilities/deployment-and-operations.yaml
tags:
- Hugging Face
- Deployment
- Operations
- Infrastructure
- MLOps
tools:
- description: List all dedicated inference endpoints for a namespace.
  hints:
    openWorld: true
    readOnly: true
  name: list-endpoints
- description: Create a new dedicated inference endpoint.
  hints:
    readOnly: false
  name: create-endpoint
- description: Get details of a specific endpoint.
  hints:
    openWorld: true
    readOnly: true
  name: get-endpoint
- description: Update an existing endpoint configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-endpoint
- description: Delete a dedicated inference endpoint.
  hints:
    destructive: true
    readOnly: false
  name: delete-endpoint
- description: Pause a running endpoint to stop billing.
  hints:
    readOnly: false
  name: pause-endpoint
- description: Resume a paused endpoint.
  hints:
    readOnly: false
  name: resume-endpoint
- description: Scale an endpoint to zero replicas.
  hints:
    readOnly: false
  name: scale-to-zero
- description: Get logs for an endpoint.
  hints:
    readOnly: true
  name: get-endpoint-logs
- description: Get metrics for an endpoint.
  hints:
    readOnly: true
  name: get-endpoint-metrics
- description: List available cloud providers and hardware options.
  hints:
    readOnly: true
  name: list-providers
- description: Check if the TGI server is healthy and responding.
  hints:
    readOnly: true
  name: tgi-health-check
- description: Get information about the deployed model and TGI server.
  hints:
    readOnly: true
  name: tgi-server-info
- description: Get Prometheus metrics from the TGI server.
  hints:
    readOnly: true
  name: tgi-metrics
---
