---
categories: []
consumed_apis: []
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
- unload a model from triton
- trace configuration
- unload a model from triton to free resources
- server ready
- get current server logging configuration
- model infer
- get inference statistics for all loaded models
- statistics for all models
- check if triton server is alive
- deep learning
- kserve
- individual model operations
- server and model health status
- get inference statistics for a specific model
- get the full configuration for a specific model
- get model metadata including tensor definitions
- update server logging configuration
- check if triton server is ready to accept inference requests
- update request tracing levels and sampling rate
- update log settings
- get triton server name, version, and extensions
- inference
- ai
- update request tracing configuration
- update trace settings
- open source
- get triton server name, version, and supported extensions
- model metadata
- run inference against a loaded model with input tensors
- machine learning
- list all models available in the repository
- server metadata and information
- update server logging level and format
- list all models available in the triton model repository
- get log settings
- get trace settings
- unload model from server
- check if triton inference server is alive
- get current global trace settings
- nvidia
- server metadata
- list models
- submit an inference request to a model
- get current global request tracing configuration
- model config
- model unload
- model repository and management
- load or reload a model from the repository into triton
- model statistics
- model configuration
- check if a specific model is ready to accept inference requests
- all model statistics
- load model into server
- load or reload a model from the repository
- get current logging settings
- get full model configuration
- logging configuration
- server live
- model serving
- run model inference
- model inference statistics
- model load
- get metadata for a specific model including input/output tensor shapes
- model ready
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Triton Model Inference and Management\n  description: Workflow capability for deploying, managing, and running inference against machine learning models on NVIDIA\n    Triton Inference Server. Enables model lifecycle management including loading, health checks, inference execution, statistics\n    monitoring, and observability configuration.\n  tags:\n  - AI\n  - Deep Learning\n  - Inference\n  - Model Serving\n  - Machine Learning\n  - NVIDIA\n  - KServe\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: triton\n    baseUri: http://localhost:8000\n    description: NVIDIA Triton Inference Server HTTP/REST API (KServe V2 protocol)\n    resources:\n    - name: health\n      path: /v2/health\n      description: Server and model health checks\n      operations:\n      - name: server-live\n        method: GET\n        description: Check if the Triton server is alive\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: server-ready\n        method: GET\n        description: Check if the Triton server is ready to accept inference requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-metadata\n      path: /v2\n      description: Server metadata\n      operations:\n      - name: server-metadata\n        method: GET\n        description: Retrieve server name, version, and supported extensions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-health\n      path: /v2/models/{model_name}/ready\n      description: Model readiness check\n      operations:\n      - name: model-ready\n        method: GET\n        description: Check if a model is ready for inference\n        inputParameters:\n        -\
  \ name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-metadata\n      path: /v2/models/{model_name}\n      description: Model metadata and configuration\n      operations:\n      - name: model-metadata\n        method: GET\n        description: Retrieve model name, versions, platform, and tensor metadata\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-config\n      path: /v2/models/{model_name}/config\n      description: Model configuration\n      operations:\n      - name: model-config\n        method: GET\n\
  \        description: Retrieve full model configuration from config.pbtxt\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inference\n      path: /v2/models/{model_name}/infer\n      description: Model inference endpoint\n      operations:\n      - name: model-infer\n        method: POST\n        description: Submit an inference request to a model\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.request_id}}'\n    \
  \        inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n    - name: repository-index\n      path: /v2/repository/index\n      description: Model repository index\n      operations:\n      - name: repository-index\n        method: POST\n        description: List all models in the repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ready: '{{tools.ready_only}}'\n    - name: model-load\n      path: /v2/repository/models/{model_name}/load\n      description: Load a model into Triton\n      operations:\n      - name: model-load\n        method: POST\n        description: Load or reload a model from the repository\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model to load\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-unload\n      path: /v2/repository/models/{model_name}/unload\n      description: Unload a model from Triton\n      operations:\n      - name: model-unload\n        method: POST\n        description: Unload a model from Triton, making it unavailable for inference\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: Name of the model to unload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-statistics\n      path: /v2/models/{model_name}/stats\n      description: Model inference statistics\n      operations:\n      - name: model-statistics\n        method: GET\n        description: Retrieve inference statistics for a specific model\n        inputParameters:\n        - name: model_name\n\
  \          in: path\n          type: string\n          required: true\n          description: Name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-model-statistics\n      path: /v2/models/stats\n      description: All model statistics\n      operations:\n      - name: all-model-statistics\n        method: GET\n        description: Retrieve inference statistics for all loaded models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trace-settings\n      path: /v2/trace/setting\n      description: Trace configuration\n      operations:\n      - name: get-trace-setting\n        method: GET\n        description: Get current global trace settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-trace-setting\n\
  \        method: POST\n        description: Update global trace settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            trace_level: '{{tools.trace_level}}'\n            trace_rate: '{{tools.trace_rate}}'\n    - name: logging\n      path: /v2/logging\n      description: Logging configuration\n      operations:\n      - name: get-log-settings\n        method: GET\n        description: Get current logging settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-log-settings\n        method: POST\n        description: Update server logging settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            log_info:\
  \ '{{tools.log_info}}'\n            log_verbose_level: '{{tools.log_verbose_level}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: triton-inference-api\n    description: Unified REST API for Triton model lifecycle management and inference.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Server and model health status\n      operations:\n      - method: GET\n        name: server-live\n        description: Check if Triton server is alive\n        call: triton.server-live\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/server\n      name: server\n      description: Server metadata and information\n      operations:\n      - method: GET\n        name: server-metadata\n        description: Get Triton server name, version, and extensions\n        call: triton.server-metadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description:\
  \ Model repository and management\n      operations:\n      - method: GET\n        name: list-models\n        description: List all models available in the repository\n        call: triton.repository-index\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}\n      name: model\n      description: Individual model operations\n      operations:\n      - method: GET\n        name: model-metadata\n        description: Get model metadata including tensor definitions\n        call: triton.model-metadata\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/config\n      name: model-config\n      description: Model configuration\n      operations:\n      - method: GET\n        name: model-config\n        description: Get full model configuration\n        call: triton.model-config\n        with:\n          model_name: rest.model_name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/infer\n      name: model-inference\n      description: Run model inference\n      operations:\n      - method: POST\n        name: model-infer\n        description: Submit an inference request to a model\n        call: triton.model-infer\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/load\n      name: model-load\n      description: Load model into server\n      operations:\n      - method: POST\n        name: model-load\n        description: Load or reload a model from the repository\n        call: triton.model-load\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/unload\n      name: model-unload\n      description: Unload model from server\n    \
  \  operations:\n      - method: POST\n        name: model-unload\n        description: Unload a model from Triton\n        call: triton.model-unload\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/stats\n      name: model-stats\n      description: Model inference statistics\n      operations:\n      - method: GET\n        name: model-statistics\n        description: Get inference statistics for a specific model\n        call: triton.model-statistics\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats\n      name: all-stats\n      description: Statistics for all models\n      operations:\n      - method: GET\n        name: all-model-statistics\n        description: Get inference statistics for all loaded models\n        call: triton.all-model-statistics\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/trace\n      name: trace\n      description: Trace configuration\n      operations:\n      - method: GET\n        name: get-trace-settings\n        description: Get current global trace settings\n        call: triton.get-trace-setting\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-trace-settings\n        description: Update request tracing configuration\n        call: triton.update-trace-setting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logging\n      name: logging\n      description: Logging configuration\n      operations:\n      - method: GET\n        name: get-log-settings\n        description: Get current logging settings\n        call: triton.get-log-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-log-settings\n        description:\
  \ Update server logging configuration\n        call: triton.update-log-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: triton-inference-mcp\n    transport: http\n    description: MCP server for AI-assisted model deployment and inference management on Triton.\n    tools:\n    - name: server-live\n      description: Check if Triton inference server is alive\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.server-live\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: server-ready\n      description: Check if Triton server is ready to accept inference requests\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.server-ready\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: server-metadata\n      description: Get Triton server name, version, and supported extensions\n      hints:\n \
  \       readOnly: true\n        openWorld: false\n      call: triton.server-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List all models available in the Triton model repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: triton.repository-index\n      with:\n        ready_only: tools.ready_only\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-metadata\n      description: Get metadata for a specific model including input/output tensor shapes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.model-metadata\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-config\n      description: Get the full configuration for a specific model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.model-config\n\
  \      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-ready\n      description: Check if a specific model is ready to accept inference requests\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.model-ready\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-infer\n      description: Run inference against a loaded model with input tensors\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: triton.model-infer\n      with:\n        model_name: tools.model_name\n        inputs: tools.inputs\n        outputs: tools.outputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-load\n      description: Load or reload a model from the repository into Triton\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: triton.model-load\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-unload\n      description: Unload a model from Triton to free resources\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: triton.model-unload\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: model-statistics\n      description: Get inference statistics for a specific model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.model-statistics\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: all-model-statistics\n      description: Get inference statistics for all loaded models\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: triton.all-model-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trace-settings\n      description: Get current global request tracing configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.get-trace-setting\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-trace-settings\n      description: Update request tracing levels and sampling rate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: triton.update-trace-setting\n      with:\n        trace_level: tools.trace_level\n        trace_rate: tools.trace_rate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-log-settings\n      description: Get current server logging configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: triton.get-log-settings\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: update-log-settings\n      description: Update server logging level and format\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: triton.update-log-settings\n      with:\n        log_info: tools.log_info\n        log_verbose_level: tools.log_verbose_level\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
