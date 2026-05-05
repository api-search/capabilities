---
api_specs:
- filename: replicate-openapi.yml
  format: yaml
  label: replicate
  slug: replicate
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/replicate/refs/heads/main/openapi/replicate-openapi.yml
categories: []
consumed_apis:
- replicate
description: Workflow capability for running AI model inference on Replicate. Covers creating predictions against versioned models and production deployments, monitoring prediction status, and canceling running jobs. Designed for developers integrating AI generation into applications.
layout: capability
name: Replicate Model Inference
operations:
- description: List all predictions.
  method: GET
  name: list-predictions
  path: /v1/predictions
- description: Create a new inference prediction.
  method: POST
  name: create-prediction
  path: /v1/predictions
- description: Get prediction status and output.
  method: GET
  name: get-prediction
  path: /v1/predictions/{id}
- description: Cancel a running prediction.
  method: DELETE
  name: cancel-prediction
  path: /v1/predictions/{id}
- description: Run inference on an official Replicate model.
  method: POST
  name: create-model-prediction
  path: /v1/models/{owner}/{name}/predictions
- description: Run inference against a production deployment.
  method: POST
  name: create-deployment-prediction
  path: /v1/deployments/{owner}/{name}/predictions
- description: List available hardware for running models.
  method: GET
  name: list-hardware
  path: /v1/hardware
- description: List all curated model collections.
  method: GET
  name: list-collections
  path: /v1/collections
- description: Get a specific model collection.
  method: GET
  name: get-collection
  path: /v1/collections/{slug}
personas: []
provider_name: Replicate
provider_slug: replicate
search_terms:
- get collection
- list available gpu hardware options for running models.
- run a new ai model inference prediction by specifying a model version and input.
- available gpu hardware options.
- cancel a running prediction.
- cancel prediction
- get a specific model collection.
- list hardware
- language models
- create predictions using official models.
- curated model collections.
- create model prediction
- specific model collection.
- create and manage model inference predictions.
- list all predictions.
- get all models in a specific curated collection.
- artificial intelligence
- get the status and output of a prediction.
- browse curated model collections by category.
- list all inference predictions for the account.
- create predictions using production deployments.
- model inference
- list all curated model collections.
- run inference on an official replicate model (no version required).
- deployments
- list available hardware for running models.
- list predictions
- create deployment prediction
- run inference against a production deployment for lower latency.
- machine learning
- run inference against a production deployment.
- get prediction status and output.
- get or cancel a specific prediction.
- create prediction
- create a new inference prediction.
- image generation
- run inference on an official replicate model.
- model deployment
- list collections
- predictions
- cancel a currently running prediction.
- get prediction
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Replicate Model Inference\"\n  description: >-\n    Workflow capability for running AI model inference on Replicate. Covers\n    creating predictions against versioned models and production deployments,\n    monitoring prediction status, and canceling running jobs. Designed for\n    developers integrating AI generation into applications.\n  tags:\n    - Artificial Intelligence\n    - Machine Learning\n    - Model Inference\n    - Predictions\n    - Deployments\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REPLICATE_API_TOKEN: REPLICATE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: replicate\n      location: ./shared/replicate.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: replicate-inference-api\n      description: \"Unified REST API for running ML model inference on Replicate.\"\n      resources:\n        - path: /v1/predictions\n       \
  \   name: predictions\n          description: \"Create and manage model inference predictions.\"\n          operations:\n            - method: GET\n              name: list-predictions\n              description: \"List all predictions.\"\n              call: \"replicate.list-predictions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-prediction\n              description: \"Create a new inference prediction.\"\n              call: \"replicate.create-prediction\"\n              with:\n                version: \"rest.version\"\n                input: \"rest.input\"\n                webhook: \"rest.webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/predictions/{id}\n          name: prediction\n          description: \"Get or cancel a specific prediction.\"\n          operations:\n            - method:\
  \ GET\n              name: get-prediction\n              description: \"Get prediction status and output.\"\n              call: \"replicate.get-prediction\"\n              with:\n                prediction_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-prediction\n              description: \"Cancel a running prediction.\"\n              call: \"replicate.cancel-prediction\"\n              with:\n                prediction_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{owner}/{name}/predictions\n          name: model-predictions\n          description: \"Create predictions using official models.\"\n          operations:\n            - method: POST\n              name: create-model-prediction\n              description: \"Run inference on an official Replicate model.\"\
  \n              call: \"replicate.create-model-prediction\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{owner}/{name}/predictions\n          name: deployment-predictions\n          description: \"Create predictions using production deployments.\"\n          operations:\n            - method: POST\n              name: create-deployment-prediction\n              description: \"Run inference against a production deployment.\"\n              call: \"replicate.create-deployment-prediction\"\n              with:\n                deployment_owner: \"rest.owner\"\n                deployment_name: \"rest.name\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n       \
  \ - path: /v1/hardware\n          name: hardware\n          description: \"Available GPU hardware options.\"\n          operations:\n            - method: GET\n              name: list-hardware\n              description: \"List available hardware for running models.\"\n              call: \"replicate.list-hardware\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collections\n          name: collections\n          description: \"Curated model collections.\"\n          operations:\n            - method: GET\n              name: list-collections\n              description: \"List all curated model collections.\"\n              call: \"replicate.list-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collections/{slug}\n          name: collection\n          description: \"Specific model collection.\"\n          operations:\n    \
  \        - method: GET\n              name: get-collection\n              description: \"Get a specific model collection.\"\n              call: \"replicate.get-collection\"\n              with:\n                collection_slug: \"rest.slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: replicate-inference-mcp\n      transport: http\n      description: \"MCP server for AI-assisted model inference on Replicate.\"\n      tools:\n        - name: list-predictions\n          description: \"List all inference predictions for the account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.list-predictions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-prediction\n          description: \"Run a new AI model inference prediction by specifying a model version and input.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"replicate.create-prediction\"\n          with:\n            version: \"tools.version\"\n            input: \"tools.input\"\n            webhook: \"tools.webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-prediction\n          description: \"Get the status and output of a prediction.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.get-prediction\"\n          with:\n            prediction_id: \"tools.prediction_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-prediction\n          description: \"Cancel a currently running prediction.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"replicate.cancel-prediction\"\
  \n          with:\n            prediction_id: \"tools.prediction_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-model-prediction\n          description: \"Run inference on an official Replicate model (no version required).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"replicate.create-model-prediction\"\n          with:\n            model_owner: \"tools.model_owner\"\n            model_name: \"tools.model_name\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-deployment-prediction\n          description: \"Run inference against a production deployment for lower latency.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"replicate.create-deployment-prediction\"\
  \n          with:\n            deployment_owner: \"tools.deployment_owner\"\n            deployment_name: \"tools.deployment_name\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-hardware\n          description: \"List available GPU hardware options for running models.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.list-hardware\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-collections\n          description: \"Browse curated model collections by category.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"replicate.list-collections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-collection\n          description: \"Get all models in a specific curated\
  \ collection.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"replicate.get-collection\"\n          with:\n            collection_slug: \"tools.collection_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/replicate/refs/heads/main/capabilities/model-inference.yaml
tags:
- Artificial Intelligence
- Machine Learning
- Model Inference
- Predictions
- Deployments
tools:
- description: List all inference predictions for the account.
  hints:
    openWorld: false
    readOnly: true
  name: list-predictions
- description: Run a new AI model inference prediction by specifying a model version and input.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-prediction
- description: Get the status and output of a prediction.
  hints:
    openWorld: false
    readOnly: true
  name: get-prediction
- description: Cancel a currently running prediction.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-prediction
- description: Run inference on an official Replicate model (no version required).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-model-prediction
- description: Run inference against a production deployment for lower latency.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-deployment-prediction
- description: List available GPU hardware options for running models.
  hints:
    openWorld: false
    readOnly: true
  name: list-hardware
- description: Browse curated model collections by category.
  hints:
    openWorld: true
    readOnly: true
  name: list-collections
- description: Get all models in a specific curated collection.
  hints:
    openWorld: true
    readOnly: true
  name: get-collection
---
