---
categories: []
consumed_apis: []
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
- run classification inference on the model
- get model version status
- predict model
- neural networks
- classification inference endpoint
- regress with model
- ai
- retrieve signature definitions and schema metadata for a tensorflow model
- predict with model
- tensorflow
- returns metadata for a specific version of a model
- run regression inference on the model
- check the health and availability status of a tensorflow model
- open source
- deep learning
- status for a specific model version
- machine learning
- returns the current status of a model in the modelserver
- model serving
- mlops
- inference
- python
- regression inference endpoint
- classify with model
- prediction inference endpoint
- run prediction inference on the model
- model signature and schema metadata
- metadata for a specific model version
- retrieve metadata for a specific version of a tensorflow model
- run prediction inference on a tensorflow model using row or column format inputs
- get model metadata
- returns status for a specific version of the model
- run regression inference on a tensorflow model with input examples
- get model status
- classify model
- javascript
- regress model
- returns metadata and signature definitions for a model
- run classification inference on a tensorflow model with input examples
- model status and health information
- get model version metadata
- check status of a specific version of a tensorflow model
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TensorFlow Model Inference\n  description: Workflow capability for running ML model inference using TensorFlow Serving. Combines model management and\n    inference operations to support MLOps workflows including model health monitoring, metadata inspection, and running classification,\n    regression, and prediction tasks in production environments.\n  tags:\n  - TensorFlow\n  - Machine Learning\n  - Model Serving\n  - Inference\n  - MLOps\n  - AI\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TENSORFLOW_SERVING_HOST: TENSORFLOW_SERVING_HOST\n    TENSORFLOW_SERVING_PORT: TENSORFLOW_SERVING_PORT\ncapability:\n  consumes:\n  - type: http\n    namespace: tensorflow-serving\n    baseUri: http://{{env.TENSORFLOW_SERVING_HOST}}:{{env.TENSORFLOW_SERVING_PORT}}\n    description: TensorFlow ModelServer REST API for model inference and management\n    resources:\n    - name: models\n      path: /v1/models\n\
  \      description: Model status and metadata resources\n      operations:\n      - name: get-model-status\n        method: GET\n        description: Returns the status of a model in the ModelServer\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model-version-status\n        method: GET\n        description: Returns the status of a specific version of a model\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        - name: version\n          in: path\n          type: integer\n          required: true\n          description: The specific version number of the model\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model-metadata\n        method: GET\n        description: Returns the metadata of a model in the ModelServer\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model-version-metadata\n        method: GET\n        description: Returns metadata for a specific version of a model\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        - name: version\n          in: path\n          type: integer\n          required: true\n          description: The specific version number\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inference\n      path: /v1/models\n      description: Model inference operations\n      operations:\n      - name: classify-model\n        method: POST\n        description: Runs classification inference using the specified model\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            signature_name: '{{tools.signature_name}}'\n            examples: '{{tools.examples}}'\n      - name: regress-model\n        method: POST\n        description: Runs regression inference using the specified model\n        inputParameters:\n        - name: model_name\n          in: path\n         \
  \ type: string\n          required: true\n          description: The name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            signature_name: '{{tools.signature_name}}'\n            examples: '{{tools.examples}}'\n      - name: predict-model\n        method: POST\n        description: Runs prediction inference using the specified model\n        inputParameters:\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The name of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            signature_name: '{{tools.signature_name}}'\n            instances: '{{tools.instances}}'\n            inputs: '{{tools.inputs}}'\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: tensorflow-inference-api\n    description: Unified REST API for TensorFlow model inference and management.\n    resources:\n    - path: /v1/models/{model_name}\n      name: model-status\n      description: Model status and health information\n      operations:\n      - method: GET\n        name: get-model-status\n        description: Returns the current status of a model in the ModelServer\n        call: tensorflow-serving.get-model-status\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/metadata\n      name: model-metadata\n      description: Model signature and schema metadata\n      operations:\n      - method: GET\n        name: get-model-metadata\n        description: Returns metadata and signature definitions for a model\n        call: tensorflow-serving.get-model-metadata\n        with:\n          model_name: rest.model_name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/versions/{version}\n      name: model-version-status\n      description: Status for a specific model version\n      operations:\n      - method: GET\n        name: get-model-version-status\n        description: Returns status for a specific version of the model\n        call: tensorflow-serving.get-model-version-status\n        with:\n          model_name: rest.model_name\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/versions/{version}/metadata\n      name: model-version-metadata\n      description: Metadata for a specific model version\n      operations:\n      - method: GET\n        name: get-model-version-metadata\n        description: Returns metadata for a specific version of a model\n        call: tensorflow-serving.get-model-version-metadata\n        with:\n          model_name:\
  \ rest.model_name\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/classify\n      name: classify\n      description: Classification inference endpoint\n      operations:\n      - method: POST\n        name: classify-model\n        description: Run classification inference on the model\n        call: tensorflow-serving.classify-model\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/regress\n      name: regress\n      description: Regression inference endpoint\n      operations:\n      - method: POST\n        name: regress-model\n        description: Run regression inference on the model\n        call: tensorflow-serving.regress-model\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{model_name}/predict\n\
  \      name: predict\n      description: Prediction inference endpoint\n      operations:\n      - method: POST\n        name: predict-model\n        description: Run prediction inference on the model\n        call: tensorflow-serving.predict-model\n        with:\n          model_name: rest.model_name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tensorflow-inference-mcp\n    transport: http\n    description: MCP server for AI-assisted TensorFlow model inference and management.\n    tools:\n    - name: get-model-status\n      description: Check the health and availability status of a TensorFlow model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tensorflow-serving.get-model-status\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-version-status\n      description: Check status of a specific\
  \ version of a TensorFlow model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tensorflow-serving.get-model-version-status\n      with:\n        model_name: tools.model_name\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-metadata\n      description: Retrieve signature definitions and schema metadata for a TensorFlow model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tensorflow-serving.get-model-metadata\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-version-metadata\n      description: Retrieve metadata for a specific version of a TensorFlow model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tensorflow-serving.get-model-version-metadata\n      with:\n        model_name: tools.model_name\n        version: tools.version\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-with-model\n      description: Run classification inference on a TensorFlow model with input examples\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tensorflow-serving.classify-model\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: regress-with-model\n      description: Run regression inference on a TensorFlow model with input examples\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tensorflow-serving.regress-model\n      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: predict-with-model\n      description: Run prediction inference on a TensorFlow model using row or column format inputs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tensorflow-serving.predict-model\n\
  \      with:\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
