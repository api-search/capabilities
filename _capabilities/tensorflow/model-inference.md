---
api_specs:
- filename: tensorflow-serving-openapi.yml
  format: yaml
  label: tensorflow-serving
  slug: tensorflow-serving
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tensorflow/refs/heads/main/openapi/tensorflow-serving-openapi.yml
categories: []
consumed_apis:
- tensorflow-serving
description: Workflow capability for running ML model inference using TensorFlow Serving. Combines model management and inference operations to support MLOps workflows including model health monitoring, metadata inspection, and running classification, regression, and prediction tasks in production environments.
layout: capability
name: TensorFlow Model Inference
operations:
- description: Returns the current status of a model in the ModelServer
  method: GET
  name: get-model-status
  path: /v1/models/{model_name}
- description: Returns metadata and signature definitions for a model
  method: GET
  name: get-model-metadata
  path: /v1/models/{model_name}/metadata
- description: Returns status for a specific version of the model
  method: GET
  name: get-model-version-status
  path: /v1/models/{model_name}/versions/{version}
- description: Returns metadata for a specific version of a model
  method: GET
  name: get-model-version-metadata
  path: /v1/models/{model_name}/versions/{version}/metadata
- description: Run classification inference on the model
  method: POST
  name: classify-model
  path: /v1/models/{model_name}/classify
- description: Run regression inference on the model
  method: POST
  name: regress-model
  path: /v1/models/{model_name}/regress
- description: Run prediction inference on the model
  method: POST
  name: predict-model
  path: /v1/models/{model_name}/predict
personas: []
provider_name: TensorFlow
provider_slug: tensorflow
search_terms:
- model status and health information
- inference
- classify with model
- metadata for a specific model version
- regress model
- prediction inference endpoint
- get model version metadata
- neural networks
- open source
- returns status for a specific version of the model
- regression inference endpoint
- predict model
- regress with model
- run prediction inference on the model
- retrieve metadata for a specific version of a tensorflow model
- run classification inference on a tensorflow model with input examples
- run classification inference on the model
- classify model
- mlops
- model signature and schema metadata
- predict with model
- get model metadata
- tensorflow
- returns metadata and signature definitions for a model
- javascript
- returns the current status of a model in the modelserver
- run regression inference on a tensorflow model with input examples
- returns metadata for a specific version of a model
- machine learning
- ai
- run regression inference on the model
- retrieve signature definitions and schema metadata for a tensorflow model
- python
- get model status
- model serving
- check status of a specific version of a tensorflow model
- run prediction inference on a tensorflow model using row or column format inputs
- status for a specific model version
- classification inference endpoint
- deep learning
- check the health and availability status of a tensorflow model
- get model version status
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TensorFlow Model Inference\"\n  description: >-\n    Workflow capability for running ML model inference using TensorFlow Serving.\n    Combines model management and inference operations to support MLOps workflows\n    including model health monitoring, metadata inspection, and running\n    classification, regression, and prediction tasks in production environments.\n  tags:\n    - TensorFlow\n    - Machine Learning\n    - Model Serving\n    - Inference\n    - MLOps\n    - AI\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TENSORFLOW_SERVING_HOST: TENSORFLOW_SERVING_HOST\n      TENSORFLOW_SERVING_PORT: TENSORFLOW_SERVING_PORT\n\ncapability:\n  consumes:\n    - import: tensorflow-serving\n      location: ./shared/tensorflow-serving.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tensorflow-inference-api\n      description: \"Unified REST API for TensorFlow\
  \ model inference and management.\"\n      resources:\n        - path: /v1/models/{model_name}\n          name: model-status\n          description: \"Model status and health information\"\n          operations:\n            - method: GET\n              name: get-model-status\n              description: \"Returns the current status of a model in the ModelServer\"\n              call: \"tensorflow-serving.get-model-status\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/metadata\n          name: model-metadata\n          description: \"Model signature and schema metadata\"\n          operations:\n            - method: GET\n              name: get-model-metadata\n              description: \"Returns metadata and signature definitions for a model\"\n              call: \"tensorflow-serving.get-model-metadata\"\n              with:\n\
  \                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/versions/{version}\n          name: model-version-status\n          description: \"Status for a specific model version\"\n          operations:\n            - method: GET\n              name: get-model-version-status\n              description: \"Returns status for a specific version of the model\"\n              call: \"tensorflow-serving.get-model-version-status\"\n              with:\n                model_name: \"rest.model_name\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/versions/{version}/metadata\n          name: model-version-metadata\n          description: \"Metadata for a specific model version\"\n          operations:\n            - method: GET\n \
  \             name: get-model-version-metadata\n              description: \"Returns metadata for a specific version of a model\"\n              call: \"tensorflow-serving.get-model-version-metadata\"\n              with:\n                model_name: \"rest.model_name\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/classify\n          name: classify\n          description: \"Classification inference endpoint\"\n          operations:\n            - method: POST\n              name: classify-model\n              description: \"Run classification inference on the model\"\n              call: \"tensorflow-serving.classify-model\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/regress\n       \
  \   name: regress\n          description: \"Regression inference endpoint\"\n          operations:\n            - method: POST\n              name: regress-model\n              description: \"Run regression inference on the model\"\n              call: \"tensorflow-serving.regress-model\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{model_name}/predict\n          name: predict\n          description: \"Prediction inference endpoint\"\n          operations:\n            - method: POST\n              name: predict-model\n              description: \"Run prediction inference on the model\"\n              call: \"tensorflow-serving.predict-model\"\n              with:\n                model_name: \"rest.model_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n   \
  \   port: 9090\n      namespace: tensorflow-inference-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TensorFlow model inference and management.\"\n      tools:\n        - name: get-model-status\n          description: \"Check the health and availability status of a TensorFlow model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tensorflow-serving.get-model-status\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model-version-status\n          description: \"Check status of a specific version of a TensorFlow model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tensorflow-serving.get-model-version-status\"\n          with:\n            model_name: \"tools.model_name\"\n            version: \"tools.version\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-model-metadata\n          description: \"Retrieve signature definitions and schema metadata for a TensorFlow model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tensorflow-serving.get-model-metadata\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model-version-metadata\n          description: \"Retrieve metadata for a specific version of a TensorFlow model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tensorflow-serving.get-model-version-metadata\"\n          with:\n            model_name: \"tools.model_name\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: classify-with-model\n         \
  \ description: \"Run classification inference on a TensorFlow model with input examples\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tensorflow-serving.classify-model\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: regress-with-model\n          description: \"Run regression inference on a TensorFlow model with input examples\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tensorflow-serving.regress-model\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: predict-with-model\n          description: \"Run prediction inference on a TensorFlow model using row or column format inputs\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"tensorflow-serving.predict-model\"\n          with:\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tensorflow/refs/heads/main/capabilities/model-inference.yaml
tags:
- TensorFlow
- Machine Learning
- Model Serving
- Inference
- MLOps
- AI
tools:
- description: Check the health and availability status of a TensorFlow model
  hints:
    openWorld: false
    readOnly: true
  name: get-model-status
- description: Check status of a specific version of a TensorFlow model
  hints:
    openWorld: false
    readOnly: true
  name: get-model-version-status
- description: Retrieve signature definitions and schema metadata for a TensorFlow model
  hints:
    openWorld: false
    readOnly: true
  name: get-model-metadata
- description: Retrieve metadata for a specific version of a TensorFlow model
  hints:
    openWorld: false
    readOnly: true
  name: get-model-version-metadata
- description: Run classification inference on a TensorFlow model with input examples
  hints:
    openWorld: true
    readOnly: true
  name: classify-with-model
- description: Run regression inference on a TensorFlow model with input examples
  hints:
    openWorld: true
    readOnly: true
  name: regress-with-model
- description: Run prediction inference on a TensorFlow model using row or column format inputs
  hints:
    openWorld: true
    readOnly: true
  name: predict-with-model
---
