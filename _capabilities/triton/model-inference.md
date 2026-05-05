---
api_specs:
- filename: triton-http-rest-openapi.yml
  format: yaml
  label: triton
  slug: triton
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/triton/refs/heads/main/openapi/triton-http-rest-openapi.yml
categories: []
consumed_apis:
- triton
description: Workflow capability for deploying, managing, and running inference against machine learning models on NVIDIA Triton Inference Server. Enables model lifecycle management including loading, health checks, inference execution, statistics monitoring, and observability configuration.
layout: capability
name: Triton Model Inference and Management
operations:
- description: Check if Triton server is alive
  method: GET
  name: server-live
  path: /v1/health
- description: Get Triton server name, version, and extensions
  method: GET
  name: server-metadata
  path: /v1/server
- description: List all models available in the repository
  method: GET
  name: list-models
  path: /v1/models
- description: Get model metadata including tensor definitions
  method: GET
  name: model-metadata
  path: /v1/models/{model_name}
- description: Get full model configuration
  method: GET
  name: model-config
  path: /v1/models/{model_name}/config
- description: Submit an inference request to a model
  method: POST
  name: model-infer
  path: /v1/models/{model_name}/infer
- description: Load or reload a model from the repository
  method: POST
  name: model-load
  path: /v1/models/{model_name}/load
- description: Unload a model from Triton
  method: POST
  name: model-unload
  path: /v1/models/{model_name}/unload
- description: Get inference statistics for a specific model
  method: GET
  name: model-statistics
  path: /v1/models/{model_name}/stats
- description: Get inference statistics for all loaded models
  method: GET
  name: all-model-statistics
  path: /v1/stats
- description: Get current global trace settings
  method: GET
  name: get-trace-settings
  path: /v1/trace
- description: Update request tracing configuration
  method: POST
  name: update-trace-settings
  path: /v1/trace
- description: Get current logging settings
  method: GET
  name: get-log-settings
  path: /v1/logging
- description: Update server logging configuration
  method: POST
  name: update-log-settings
  path: /v1/logging
personas: []
provider_name: Triton Inference Server
provider_slug: triton
search_terms:
- get current logging settings
- load or reload a model from the repository into triton
- get inference statistics for all loaded models
- run model inference
- list models
- logging configuration
- load model into server
- nvidia
- server and model health status
- get inference statistics for a specific model
- get trace settings
- model infer
- list all models available in the repository
- get metadata for a specific model including input/output tensor shapes
- model ready
- individual model operations
- ai
- update server logging configuration
- check if triton server is ready to accept inference requests
- get current global request tracing configuration
- open source
- get triton server name, version, and extensions
- model configuration
- update log settings
- get current server logging configuration
- all model statistics
- load or reload a model from the repository
- list all models available in the triton model repository
- model statistics
- update server logging level and format
- server ready
- run inference against a loaded model with input tensors
- kserve
- server metadata and information
- server live
- model load
- trace configuration
- update trace settings
- model unload
- get the full configuration for a specific model
- model inference statistics
- update request tracing levels and sampling rate
- server metadata
- model repository and management
- model config
- check if triton server is alive
- get full model configuration
- unload a model from triton
- check if triton inference server is alive
- inference
- machine learning
- get current global trace settings
- get log settings
- unload a model from triton to free resources
- model metadata
- submit an inference request to a model
- get triton server name, version, and supported extensions
- model serving
- get model metadata including tensor definitions
- unload model from server
- deep learning
- check if a specific model is ready to accept inference requests
- update request tracing configuration
- statistics for all models
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Triton Model Inference and Management\"\n  description: >-\n    Workflow capability for deploying, managing, and running inference against machine\n    learning models on NVIDIA Triton Inference Server. Enables model lifecycle management\n    including loading, health checks, inference execution, statistics monitoring, and\n    observability configuration.\n  tags:\n    - AI\n    - Deep Learning\n    - Inference\n    - Model Serving\n    - Machine Learning\n    - NVIDIA\n    - KServe\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: triton\n      location: ./shared/triton-http-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: triton-inference-api\n      description: \"Unified REST API for Triton model lifecycle management and inference.\"\n      resources:\n        - path: /v1/health\n          name: health\n          description: \"Server and model health\
  \ status\"\n          operations:\n            - method: GET\n              name: server-live\n              description: \"Check if Triton server is alive\"\n              call: \"triton.server-live\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/server\n          name: server\n          description: \"Server metadata and information\"\n          operations:\n            - method: GET\n              name: server-metadata\n              description: \"Get Triton server name, version, and extensions\"\n              call: \"triton.server-metadata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models\n          name: models\n          description: \"Model repository and management\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all models available in the repository\"\
  \n              call: \"triton.repository-index\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}\n          name: model\n          description: \"Individual model operations\"\n          operations:\n            - method: GET\n              name: model-metadata\n              description: \"Get model metadata including tensor definitions\"\n              call: \"triton.model-metadata\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/config\n          name: model-config\n          description: \"Model configuration\"\n          operations:\n            - method: GET\n              name: model-config\n              description: \"Get full model configuration\"\n              call: \"triton.model-config\"\n              with:\n    \
  \            model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/infer\n          name: model-inference\n          description: \"Run model inference\"\n          operations:\n            - method: POST\n              name: model-infer\n              description: \"Submit an inference request to a model\"\n              call: \"triton.model-infer\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/load\n          name: model-load\n          description: \"Load model into server\"\n          operations:\n            - method: POST\n              name: model-load\n              description: \"Load or reload a model from the repository\"\n              call: \"triton.model-load\"\n              with:\n     \
  \           model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/unload\n          name: model-unload\n          description: \"Unload model from server\"\n          operations:\n            - method: POST\n              name: model-unload\n              description: \"Unload a model from Triton\"\n              call: \"triton.model-unload\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{model_name}/stats\n          name: model-stats\n          description: \"Model inference statistics\"\n          operations:\n            - method: GET\n              name: model-statistics\n              description: \"Get inference statistics for a specific model\"\n              call: \"triton.model-statistics\"\n              with:\n\
  \                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stats\n          name: all-stats\n          description: \"Statistics for all models\"\n          operations:\n            - method: GET\n              name: all-model-statistics\n              description: \"Get inference statistics for all loaded models\"\n              call: \"triton.all-model-statistics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trace\n          name: trace\n          description: \"Trace configuration\"\n          operations:\n            - method: GET\n              name: get-trace-settings\n              description: \"Get current global trace settings\"\n              call: \"triton.get-trace-setting\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n         \
  \   - method: POST\n              name: update-trace-settings\n              description: \"Update request tracing configuration\"\n              call: \"triton.update-trace-setting\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/logging\n          name: logging\n          description: \"Logging configuration\"\n          operations:\n            - method: GET\n              name: get-log-settings\n              description: \"Get current logging settings\"\n              call: \"triton.get-log-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-log-settings\n              description: \"Update server logging configuration\"\n              call: \"triton.update-log-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n  \
  \    port: 9090\n      namespace: triton-inference-mcp\n      transport: http\n      description: \"MCP server for AI-assisted model deployment and inference management on Triton.\"\n      tools:\n        - name: server-live\n          description: \"Check if Triton inference server is alive\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.server-live\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: server-ready\n          description: \"Check if Triton server is ready to accept inference requests\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.server-ready\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: server-metadata\n          description: \"Get Triton server name, version, and supported extensions\"\n          hints:\n            readOnly: true\n      \
  \      openWorld: false\n          call: \"triton.server-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-models\n          description: \"List all models available in the Triton model repository\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"triton.repository-index\"\n          with:\n            ready_only: \"tools.ready_only\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-metadata\n          description: \"Get metadata for a specific model including input/output tensor shapes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.model-metadata\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-config\n          description:\
  \ \"Get the full configuration for a specific model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.model-config\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-ready\n          description: \"Check if a specific model is ready to accept inference requests\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.model-ready\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-infer\n          description: \"Run inference against a loaded model with input tensors\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"triton.model-infer\"\n          with:\n    \
  \        model_name: \"tools.model_name\"\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-load\n          description: \"Load or reload a model from the repository into Triton\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"triton.model-load\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: model-unload\n          description: \"Unload a model from Triton to free resources\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"triton.model-unload\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n\n        - name: model-statistics\n          description: \"Get inference statistics for a specific model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.model-statistics\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: all-model-statistics\n          description: \"Get inference statistics for all loaded models\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"triton.all-model-statistics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-trace-settings\n          description: \"Get current global request tracing configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.get-trace-setting\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: update-trace-settings\n          description: \"Update request tracing levels and sampling rate\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"triton.update-trace-setting\"\n          with:\n            trace_level: \"tools.trace_level\"\n            trace_rate: \"tools.trace_rate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-log-settings\n          description: \"Get current server logging configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"triton.get-log-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-log-settings\n          description: \"Update server logging level and format\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: true\n          call: \"triton.update-log-settings\"\n          with:\n            log_info: \"tools.log_info\"\n            log_verbose_level: \"tools.log_verbose_level\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/triton/refs/heads/main/capabilities/model-inference.yaml
tags:
- AI
- Deep Learning
- Inference
- Model Serving
- Machine Learning
- NVIDIA
- KServe
tools:
- description: Check if Triton inference server is alive
  hints:
    openWorld: false
    readOnly: true
  name: server-live
- description: Check if Triton server is ready to accept inference requests
  hints:
    openWorld: false
    readOnly: true
  name: server-ready
- description: Get Triton server name, version, and supported extensions
  hints:
    openWorld: false
    readOnly: true
  name: server-metadata
- description: List all models available in the Triton model repository
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: Get metadata for a specific model including input/output tensor shapes
  hints:
    openWorld: false
    readOnly: true
  name: model-metadata
- description: Get the full configuration for a specific model
  hints:
    openWorld: false
    readOnly: true
  name: model-config
- description: Check if a specific model is ready to accept inference requests
  hints:
    openWorld: false
    readOnly: true
  name: model-ready
- description: Run inference against a loaded model with input tensors
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: model-infer
- description: Load or reload a model from the repository into Triton
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: model-load
- description: Unload a model from Triton to free resources
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: model-unload
- description: Get inference statistics for a specific model
  hints:
    openWorld: false
    readOnly: true
  name: model-statistics
- description: Get inference statistics for all loaded models
  hints:
    openWorld: true
    readOnly: true
  name: all-model-statistics
- description: Get current global request tracing configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-trace-settings
- description: Update request tracing levels and sampling rate
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-trace-settings
- description: Get current server logging configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-log-settings
- description: Update server logging level and format
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-log-settings
---
