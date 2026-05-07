---
categories: []
consumed_apis: []
description: Workflow capability for ML engineers and data scientists performing model inference operations, health monitoring, and metadata inspection against OIP-compliant inference servers. Imports the KServe Open Inference Protocol shared definition and exposes a unified workflow-oriented API and MCP server for AI-assisted inference workflows.
layout: capability
name: Scalable Inference Serving - Model Inference Operations
operations:
- description: Check Server Liveness
  method: GET
  name: check-server-liveness
  path: /v1/health/live
- description: Check Server Readiness
  method: GET
  name: check-server-readiness
  path: /v1/health/ready
- description: Get Server Metadata
  method: GET
  name: get-server-metadata
  path: /v1/server
- description: Get Model Metadata
  method: GET
  name: get-model-metadata
  path: /v1/models/{model_name}
- description: Check Model Readiness
  method: GET
  name: check-model-readiness
  path: /v1/models/{model_name}/ready
- description: Run Model Inference
  method: POST
  name: run-inference
  path: /v1/models/{model_name}/infer
- description: Run Model Version Inference
  method: POST
  name: run-model-version-inference
  path: /v1/models/{model_name}/versions/{model_version}/infer
- description: Get Model Version Metadata
  method: GET
  name: get-model-version-metadata
  path: /v1/models/{model_name}/versions/{model_version}/metadata
personas: []
provider_name: Scalable Inference Serving
provider_slug: scalable-inference-serving
search_terms:
- check server liveness
- submit inference requests to a model
- run model version inference
- ai
- llm
- scalability
- check if the inference server is live
- deployment
- machine learning
- kubernetes
- model serving
- check if all models are loaded and the inference server is ready
- mlops
- inference
- check if the kserve inference server is live and able to receive requests
- run inference
- model readiness status
- cncf
- get inference server name, version, and supported protocol extensions
- check model readiness
- check if all models are ready for inference
- get model input/output tensor specifications, available versions, and serving platform
- inference server metadata and capabilities
- get server metadata
- check server readiness
- get model metadata
- submit input tensors to a deployed model and receive inference output tensors. use get-model-metadata first to discover the correct input names, shapes, and datatypes.
- model tensor specifications and version information
- run model inference
- submit inference requests to a specific model version
- run inference against a pinned model version for a/b testing, canary evaluation, or version-specific integration
- model version-specific metadata
- get model version metadata
- check if a specific model is ready for inference
slug: model-inference-operations
source_filename: model-inference-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scalable Inference Serving - Model Inference Operations\n  description: Workflow capability for ML engineers and data scientists performing model inference operations, health monitoring,\n    and metadata inspection against OIP-compliant inference servers. Imports the KServe Open Inference Protocol shared definition\n    and exposes a unified workflow-oriented API and MCP server for AI-assisted inference workflows.\n  tags:\n  - AI\n  - CNCF\n  - Inference\n  - Kubernetes\n  - Machine Learning\n  - Model Serving\n  - MLOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KSERVE_BASE_URL: KSERVE_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: kserve\n    baseUri: '{{env.KSERVE_BASE_URL}}'\n    description: KServe Open Inference Protocol V2 REST API\n    resources:\n    - name: server-health\n      path: /v2/health\n      description: Server liveness and readiness health endpoints\n\
  \      operations:\n      - name: check-server-liveness\n        method: GET\n        description: Check if the inference server is live and ready to receive requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-server-readiness\n        method: GET\n        description: Check if all models are loaded and the server is ready for inference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-metadata\n      path: /v2\n      description: Server metadata and version information\n      operations:\n      - name: get-server-metadata\n        method: GET\n        description: Get server name, version, and supported protocol extensions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-health\n      path:\
  \ /v2/models/{model_name}/ready\n      description: Per-model readiness endpoint\n      operations:\n      - name: check-model-readiness\n        method: GET\n        description: Check if a specific model is ready for inference\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-metadata\n      path: /v2/models/{model_name}\n      description: Model metadata including input/output tensor specifications\n      operations:\n      - name: get-model-metadata\n        method: GET\n        description: Retrieve model name, versions, platform, and input/output tensor specs\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the\
  \ model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-inference\n      path: /v2/models/{model_name}/infer\n      description: Model inference execution endpoint\n      operations:\n      - name: run-inference\n        method: POST\n        description: Submit input tensors and receive model predictions\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model to run inference against\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.request_id}}'\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n    - name: model-version-inference\n      path: /v2/models/{model_name}/versions/{model_version}/infer\n\
  \      description: Version-specific model inference\n      operations:\n      - name: run-model-version-inference\n        method: POST\n        description: Submit inference request to a specific model version for A/B testing or version pinning\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model\n        - name: model_version\n          in: path\n          type: string\n          required: true\n          description: Specific model version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.request_id}}'\n            inputs: '{{tools.inputs}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: inference-ops-api\n    description: Unified REST API for model inference operations, health monitoring, and metadata inspection.\n\
  \    resources:\n    - path: /v1/health/live\n      name: server-liveness\n      description: Check if the inference server is live\n      operations:\n      - method: GET\n        name: check-server-liveness\n        description: Check Server Liveness\n        call: kserve.check-server-liveness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health/ready\n      name: server-readiness\n      description: Check if all models are ready for inference\n      operations:\n      - method: GET\n        name: check-server-readiness\n        description: Check Server Readiness\n        call: kserve.check-server-readiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/server\n      name: server-metadata\n      description: Inference server metadata and capabilities\n      operations:\n      - method: GET\n        name: get-server-metadata\n        description: Get Server Metadata\n        call: kserve.get-server-metadata\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}\n      name: model-metadata\n      description: Model tensor specifications and version information\n      operations:\n      - method: GET\n        name: get-model-metadata\n        description: Get Model Metadata\n        call: kserve.get-model-metadata\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/ready\n      name: model-readiness\n      description: Model readiness status\n      operations:\n      - method: GET\n        name: check-model-readiness\n        description: Check Model Readiness\n        call: kserve.check-model-readiness\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/infer\n      name: model-inference\n      description: Submit\
  \ inference requests to a model\n      operations:\n      - method: POST\n        name: run-inference\n        description: Run Model Inference\n        call: kserve.run-inference\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/versions/{model_version}/infer\n      name: model-version-inference\n      description: Submit inference requests to a specific model version\n      operations:\n      - method: POST\n        name: run-model-version-inference\n        description: Run Model Version Inference\n        call: kserve.run-model-version-inference\n        with:\n          model_name: rest.model_name\n          model_version: rest.model_version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/versions/{model_version}/metadata\n      name: model-version-metadata\n      description: Model version-specific metadata\n\
  \      operations:\n      - method: GET\n        name: get-model-version-metadata\n        description: Get Model Version Metadata\n        call: kserve.get-model-metadata\n        with:\n          model_name: rest.model_name\n          model_version: rest.model_version\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: inference-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted model inference operations, enabling LLM agents to submit inference requests and\n      inspect model health.\n    tools:\n    - name: check-server-liveness\n      description: Check if the KServe inference server is live and able to receive requests\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kserve.check-server-liveness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-server-readiness\n      description: Check if all models are loaded and the inference\
  \ server is ready\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kserve.check-server-readiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-metadata\n      description: Get inference server name, version, and supported protocol extensions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kserve.get-server-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-model-readiness\n      description: Check if a specific model is ready for inference\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kserve.check-model-readiness\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-metadata\n      description: Get model input/output tensor specifications, available versions, and serving platform\n      hints:\n        readOnly: true\n    \
  \    idempotent: true\n      call: kserve.get-model-metadata\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-inference\n      description: Submit input tensors to a deployed model and receive inference output tensors. Use get-model-metadata first\n        to discover the correct input names, shapes, and datatypes.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kserve.run-inference\n      with:\n        model_name: tools.model_name\n        request_id: tools.request_id\n        inputs: tools.inputs\n        outputs: tools.outputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-model-version-inference\n      description: Run inference against a pinned model version for A/B testing, canary evaluation, or version-specific integration\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kserve.run-model-version-inference\n\
  \      with:\n        model_name: tools.model_name\n        model_version: tools.model_version\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scalable-inference-serving/refs/heads/main/capabilities/model-inference-operations.yaml
tags:
- AI
- CNCF
- Inference
- Kubernetes
- Machine Learning
- Model Serving
- MLOps
tools:
- description: Check if the KServe inference server is live and able to receive requests
  hints:
    idempotent: true
    readOnly: true
  name: check-server-liveness
- description: Check if all models are loaded and the inference server is ready
  hints:
    idempotent: true
    readOnly: true
  name: check-server-readiness
- description: Get inference server name, version, and supported protocol extensions
  hints:
    idempotent: true
    readOnly: true
  name: get-server-metadata
- description: Check if a specific model is ready for inference
  hints:
    idempotent: true
    readOnly: true
  name: check-model-readiness
- description: Get model input/output tensor specifications, available versions, and serving platform
  hints:
    idempotent: true
    readOnly: true
  name: get-model-metadata
- description: Submit input tensors to a deployed model and receive inference output tensors. Use get-model-metadata first to discover the correct input names, shapes, and datatypes.
  hints:
    idempotent: false
    readOnly: false
  name: run-inference
- description: Run inference against a pinned model version for A/B testing, canary evaluation, or version-specific integration
  hints:
    idempotent: false
    readOnly: false
  name: run-model-version-inference
---
