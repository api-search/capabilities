---
categories: []
consumed_apis: []
description: TensorFlow Serving exposes a REST API for running inference on trained TensorFlow models. It supports predict, classify, and regress endpoints with model versioning and lifecycle management.
layout: capability
name: Google TensorFlow TensorFlow Serving REST API
operations:
- description: Google TensorFlow Get model status
  method: GET
  name: getmodelstatus
  path: /v1/models/{model_name}
- description: Google TensorFlow Get model metadata
  method: GET
  name: getmodelmetadata
  path: /v1/models/{model_name}/metadata
- description: Google TensorFlow Predict
  method: POST
  name: predict
  path: /v1/models/{model_name}:predict
- description: Google TensorFlow Classify
  method: POST
  name: classify
  path: /v1/models/{model_name}:classify
- description: Google TensorFlow Regress
  method: POST
  name: regress
  path: /v1/models/{model_name}:regress
personas: []
provider_name: Google TensorFlow
provider_slug: google-tensorflow
search_terms:
- google tensorflow regress
- tensorflow
- machine learning
- google tensorflow classify
- predict
- getmodelstatus
- deep learning
- regress
- google tensorflow get model metadata
- google tensorflow predict
- model serving
- google
- open source
- classify
- ai
- api
- google tensorflow get model status
- getmodelmetadata
slug: google-tensorflow-capability
source_filename: google-tensorflow-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google TensorFlow TensorFlow Serving REST API\n  description: TensorFlow Serving exposes a REST API for running inference on trained TensorFlow models. It supports predict,\n    classify, and regress endpoints with model versioning and lifecycle management.\n  tags:\n  - Google\n  - Tensorflow\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-tensorflow\n    baseUri: http://localhost:8501\n    description: Google TensorFlow TensorFlow Serving REST API HTTP API.\n    resources:\n    - name: v1-models-model-name\n      path: /v1/models/{model_name}\n      operations:\n      - name: getmodelstatus\n        method: GET\n        description: Google TensorFlow Get model status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-models-model-name-metadata\n      path: /v1/models/{model_name}/metadata\n\
  \      operations:\n      - name: getmodelmetadata\n        method: GET\n        description: Google TensorFlow Get model metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-models-model-name-predict\n      path: /v1/models/{model_name}:predict\n      operations:\n      - name: predict\n        method: POST\n        description: Google TensorFlow Predict\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-models-model-name-classify\n      path: /v1/models/{model_name}:classify\n      operations:\n      - name: classify\n        method: POST\n        description: Google TensorFlow Classify\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-models-model-name-regress\n      path: /v1/models/{model_name}:regress\n\
  \      operations:\n      - name: regress\n        method: POST\n        description: Google TensorFlow Regress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-tensorflow-rest\n    description: REST adapter for Google TensorFlow TensorFlow Serving REST API.\n    resources:\n    - path: /v1/models/{model_name}\n      name: getmodelstatus\n      operations:\n      - method: GET\n        name: getmodelstatus\n        description: Google TensorFlow Get model status\n        call: google-tensorflow.getmodelstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/metadata\n      name: getmodelmetadata\n      operations:\n      - method: GET\n        name: getmodelmetadata\n        description: Google TensorFlow Get model metadata\n        call: google-tensorflow.getmodelmetadata\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}:predict\n      name: predict\n      operations:\n      - method: POST\n        name: predict\n        description: Google TensorFlow Predict\n        call: google-tensorflow.predict\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}:classify\n      name: classify\n      operations:\n      - method: POST\n        name: classify\n        description: Google TensorFlow Classify\n        call: google-tensorflow.classify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}:regress\n      name: regress\n      operations:\n      - method: POST\n        name: regress\n        description: Google TensorFlow Regress\n        call: google-tensorflow.regress\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-tensorflow-mcp\n\
  \    transport: http\n    description: MCP adapter for Google TensorFlow TensorFlow Serving REST API for AI agent use.\n    tools:\n    - name: getmodelstatus\n      description: Google TensorFlow Get model status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tensorflow.getmodelstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodelmetadata\n      description: Google TensorFlow Get model metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tensorflow.getmodelmetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: predict\n      description: Google TensorFlow Predict\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tensorflow.predict\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify\n\
  \      description: Google TensorFlow Classify\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tensorflow.classify\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: regress\n      description: Google TensorFlow Regress\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tensorflow.regress\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-tensorflow/refs/heads/main/capabilities/google-tensorflow-capability.yaml
tags:
- Google
- Tensorflow
- API
tools:
- description: Google TensorFlow Get model status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodelstatus
- description: Google TensorFlow Get model metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodelmetadata
- description: Google TensorFlow Predict
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: predict
- description: Google TensorFlow Classify
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: classify
- description: Google TensorFlow Regress
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: regress
---
