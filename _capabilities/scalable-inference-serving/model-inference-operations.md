---
api_specs:
- filename: kserve-open-inference-protocol-openapi.yml
  format: yaml
  label: kserve
  slug: kserve
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/scalable-inference-serving/refs/heads/main/openapi/kserve-open-inference-protocol-openapi.yml
categories: []
consumed_apis:
- kserve
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
- run inference
- run model version inference
- submit input tensors to a deployed model and receive inference output tensors. use get-model-metadata first to discover the correct input names, shapes, and datatypes.
- submit inference requests to a model
- check server readiness
- check if a specific model is ready for inference
- get model input/output tensor specifications, available versions, and serving platform
- check if all models are ready for inference
- llm
- check if all models are loaded and the inference server is ready
- check model readiness
- kubernetes
- scalability
- inference
- mlops
- get server metadata
- check server liveness
- ai
- submit inference requests to a specific model version
- model version-specific metadata
- run model inference
- model serving
- get model version metadata
- get inference server name, version, and supported protocol extensions
- deployment
- check if the kserve inference server is live and able to receive requests
- get model metadata
- run inference against a pinned model version for a/b testing, canary evaluation, or version-specific integration
- model tensor specifications and version information
- machine learning
- cncf
- model readiness status
- check if the inference server is live
- inference server metadata and capabilities
slug: model-inference-operations
source_filename: model-inference-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scalable Inference Serving - Model Inference Operations\"\n  description: >-\n    Workflow capability for ML engineers and data scientists performing model inference\n    operations, health monitoring, and metadata inspection against OIP-compliant\n    inference servers. Imports the KServe Open Inference Protocol shared definition\n    and exposes a unified workflow-oriented API and MCP server for AI-assisted\n    inference workflows.\n  tags:\n    - AI\n    - CNCF\n    - Inference\n    - Kubernetes\n    - Machine Learning\n    - Model Serving\n    - MLOps\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      KSERVE_BASE_URL: KSERVE_BASE_URL\n\ncapability:\n  consumes:\n    - import: kserve\n      location: ./shared/kserve-open-inference-protocol.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: inference-ops-api\n      description: \"Unified REST API for model\
  \ inference operations, health monitoring, and metadata inspection.\"\n      resources:\n        - path: /v1/health/live\n          name: server-liveness\n          description: \"Check if the inference server is live\"\n          operations:\n            - method: GET\n              name: check-server-liveness\n              description: \"Check Server Liveness\"\n              call: \"kserve.check-server-liveness\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/health/ready\n          name: server-readiness\n          description: \"Check if all models are ready for inference\"\n          operations:\n            - method: GET\n              name: check-server-readiness\n              description: \"Check Server Readiness\"\n              call: \"kserve.check-server-readiness\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/server\n \
  \         name: server-metadata\n          description: \"Inference server metadata and capabilities\"\n          operations:\n            - method: GET\n              name: get-server-metadata\n              description: \"Get Server Metadata\"\n              call: \"kserve.get-server-metadata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}\n          name: model-metadata\n          description: \"Model tensor specifications and version information\"\n          operations:\n            - method: GET\n              name: get-model-metadata\n              description: \"Get Model Metadata\"\n              call: \"kserve.get-model-metadata\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/ready\n          name: model-readiness\n \
  \         description: \"Model readiness status\"\n          operations:\n            - method: GET\n              name: check-model-readiness\n              description: \"Check Model Readiness\"\n              call: \"kserve.check-model-readiness\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/infer\n          name: model-inference\n          description: \"Submit inference requests to a model\"\n          operations:\n            - method: POST\n              name: run-inference\n              description: \"Run Model Inference\"\n              call: \"kserve.run-inference\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/versions/{model_version}/infer\n  \
  \        name: model-version-inference\n          description: \"Submit inference requests to a specific model version\"\n          operations:\n            - method: POST\n              name: run-model-version-inference\n              description: \"Run Model Version Inference\"\n              call: \"kserve.run-model-version-inference\"\n              with:\n                model_name: \"rest.model_name\"\n                model_version: \"rest.model_version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/versions/{model_version}/metadata\n          name: model-version-metadata\n          description: \"Model version-specific metadata\"\n          operations:\n            - method: GET\n              name: get-model-version-metadata\n              description: \"Get Model Version Metadata\"\n              call: \"kserve.get-model-metadata\"\n              with:\n                model_name:\
  \ \"rest.model_name\"\n                model_version: \"rest.model_version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: inference-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted model inference operations, enabling LLM agents to submit inference requests and inspect model health.\"\n      tools:\n        - name: check-server-liveness\n          description: \"Check if the KServe inference server is live and able to receive requests\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"kserve.check-server-liveness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-server-readiness\n          description: \"Check if all models are loaded and the inference server is ready\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"kserve.check-server-readiness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-server-metadata\n          description: \"Get inference server name, version, and supported protocol extensions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"kserve.get-server-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-model-readiness\n          description: \"Check if a specific model is ready for inference\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"kserve.check-model-readiness\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-model-metadata\n          description: \"Get model input/output tensor specifications,\
  \ available versions, and serving platform\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"kserve.get-model-metadata\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-inference\n          description: \"Submit input tensors to a deployed model and receive inference output tensors. Use get-model-metadata first to discover the correct input names, shapes, and datatypes.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"kserve.run-inference\"\n          with:\n            model_name: \"tools.model_name\"\n            request_id: \"tools.request_id\"\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-model-version-inference\n        \
  \  description: \"Run inference against a pinned model version for A/B testing, canary evaluation, or version-specific integration\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"kserve.run-model-version-inference\"\n          with:\n            model_name: \"tools.model_name\"\n            model_version: \"tools.model_version\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
