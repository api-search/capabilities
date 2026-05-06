---
categories: []
consumed_apis: []
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
- get or cancel a specific prediction.
- cancel a currently running prediction.
- run inference on an official replicate model.
- create prediction
- curated model collections.
- language models
- specific model collection.
- run inference against a production deployment for lower latency.
- create predictions using official models.
- create predictions using production deployments.
- create deployment prediction
- deployments
- create and manage model inference predictions.
- get collection
- list available hardware for running models.
- get prediction status and output.
- cancel prediction
- browse curated model collections by category.
- list available gpu hardware options for running models.
- artificial intelligence
- model deployment
- create a new inference prediction.
- list all predictions.
- get all models in a specific curated collection.
- machine learning
- list predictions
- get prediction
- cancel a running prediction.
- get a specific model collection.
- list all inference predictions for the account.
- predictions
- get the status and output of a prediction.
- create model prediction
- list hardware
- run a new ai model inference prediction by specifying a model version and input.
- image generation
- run inference against a production deployment.
- available gpu hardware options.
- model inference
- list collections
- run inference on an official replicate model (no version required).
- list all curated model collections.
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Replicate Model Inference\n  description: Workflow capability for running AI model inference on Replicate. Covers creating predictions against versioned\n    models and production deployments, monitoring prediction status, and canceling running jobs. Designed for developers integrating\n    AI generation into applications.\n  tags:\n  - Artificial Intelligence\n  - Machine Learning\n  - Model Inference\n  - Predictions\n  - Deployments\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REPLICATE_API_TOKEN: REPLICATE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: replicate\n    baseUri: https://api.replicate.com/v1\n    description: Replicate REST API for running ML models and managing resources.\n    authentication:\n      type: bearer\n      token: '{{REPLICATE_API_TOKEN}}'\n    resources:\n    - name: account\n      path: /account\n      description: Account information for\
  \ the authenticated user or organization.\n      operations:\n      - name: get-account\n        method: GET\n        description: Get the authenticated account information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections\n      path: /collections\n      description: Curated collections of models.\n      operations:\n      - name: list-collections\n        method: GET\n        description: List all collections of models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-collection\n        method: GET\n        description: Get a specific collection of models by slug.\n        inputParameters:\n        - name: collection_slug\n          in: path\n          type: string\n          required: true\n          description: The slug of the collection.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      description: Manage model deployments for production use.\n      operations:\n      - name: list-deployments\n        method: GET\n        description: List all deployments for the authenticated account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Create a new model deployment.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            model: '{{tools.model}}'\n            version: '{{tools.version}}'\n            hardware: '{{tools.hardware}}'\n            min_instances: '{{tools.min_instances}}'\n            max_instances: '{{tools.max_instances}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: get-deployment\n        method: GET\n        description: Get a specific deployment by owner and name.\n        inputParameters:\n        - name: deployment_owner\n          in: path\n          type: string\n          required: true\n          description: The deployment owner.\n        - name: deployment_name\n          in: path\n          type: string\n          required: true\n          description: The deployment name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deployment\n        method: PATCH\n        description: Update a deployment configuration.\n        inputParameters:\n        - name: deployment_owner\n          in: path\n          type: string\n          required: true\n          description: The deployment owner.\n        - name: deployment_name\n          in: path\n          type: string\n          required: true\n          description:\
  \ The deployment name.\n        body:\n          type: json\n          data:\n            hardware: '{{tools.hardware}}'\n            min_instances: '{{tools.min_instances}}'\n            max_instances: '{{tools.max_instances}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-deployment\n        method: DELETE\n        description: Delete a deployment.\n        inputParameters:\n        - name: deployment_owner\n          in: path\n          type: string\n          required: true\n          description: The deployment owner.\n        - name: deployment_name\n          in: path\n          type: string\n          required: true\n          description: The deployment name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment-prediction\n        method: POST\n        description: Create\
  \ a prediction using a deployment.\n        inputParameters:\n        - name: deployment_owner\n          in: path\n          type: string\n          required: true\n          description: The deployment owner.\n        - name: deployment_name\n          in: path\n          type: string\n          required: true\n          description: The deployment name.\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            webhook: '{{tools.webhook}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hardware\n      path: /hardware\n      description: Available hardware options for running models.\n      operations:\n      - name: list-hardware\n        method: GET\n        description: List all available hardware options.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ models\n      path: /models\n      description: ML models hosted on Replicate.\n      operations:\n      - name: list-models\n        method: GET\n        description: List all public models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-model\n        method: POST\n        description: Create a new model.\n        body:\n          type: json\n          data:\n            owner: '{{tools.owner}}'\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            visibility: '{{tools.visibility}}'\n            hardware: '{{tools.hardware}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-models\n        method: GET\n        description: Search public models.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n\
  \          required: false\n          description: Search query string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model\n        method: GET\n        description: Get a specific model.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-model\n        method: DELETE\n        description: Delete a model.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n\
  \          in: path\n          type: string\n          required: true\n          description: The model name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-model-prediction\n        method: POST\n        description: Create a prediction using an official model.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            webhook: '{{tools.webhook}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-model-versions\n        method: GET\n        description:\
  \ List all versions of a model.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-model-version\n        method: GET\n        description: Get a specific model version.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        - name: version_id\n          in: path\n          type: string\n          required: true\n          description: The version\
  \ ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-model-version\n        method: DELETE\n        description: Delete a specific model version.\n        inputParameters:\n        - name: model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        - name: version_id\n          in: path\n          type: string\n          required: true\n          description: The version ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: predictions\n      path: /predictions\n      description: Inference runs against ML models.\n      operations:\n      - name: list-predictions\n        method: GET\n    \
  \    description: List all predictions for the authenticated account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-prediction\n        method: POST\n        description: Create a new prediction.\n        body:\n          type: json\n          data:\n            version: '{{tools.version}}'\n            input: '{{tools.input}}'\n            webhook: '{{tools.webhook}}'\n            webhook_events_filter: '{{tools.webhook_events_filter}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-prediction\n        method: GET\n        description: Get a specific prediction.\n        inputParameters:\n        - name: prediction_id\n          in: path\n          type: string\n          required: true\n          description: The prediction ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: cancel-prediction\n        method: POST\n        description: Cancel a running prediction.\n        inputParameters:\n        - name: prediction_id\n          in: path\n          type: string\n          required: true\n          description: The prediction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trainings\n      path: /trainings\n      description: Fine-tuning jobs for ML models.\n      operations:\n      - name: list-trainings\n        method: GET\n        description: List all trainings for the authenticated account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-training\n        method: POST\n        description: Create a new training job on a model version.\n        inputParameters:\n        - name:\
  \ model_owner\n          in: path\n          type: string\n          required: true\n          description: The model owner.\n        - name: model_name\n          in: path\n          type: string\n          required: true\n          description: The model name.\n        - name: version_id\n          in: path\n          type: string\n          required: true\n          description: The version ID to train.\n        body:\n          type: json\n          data:\n            destination: '{{tools.destination}}'\n            input: '{{tools.input}}'\n            webhook: '{{tools.webhook}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-training\n        method: GET\n        description: Get a specific training job.\n        inputParameters:\n        - name: training_id\n          in: path\n          type: string\n          required: true\n          description: The training ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-training\n        method: POST\n        description: Cancel a running training job.\n        inputParameters:\n        - name: training_id\n          in: path\n          type: string\n          required: true\n          description: The training ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks/default/secret\n      description: Webhook signing secret management.\n      operations:\n      - name: get-webhook-secret\n        method: GET\n        description: Get the signing secret for the default webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: replicate-inference-api\n    description: Unified REST\
  \ API for running ML model inference on Replicate.\n    resources:\n    - path: /v1/predictions\n      name: predictions\n      description: Create and manage model inference predictions.\n      operations:\n      - method: GET\n        name: list-predictions\n        description: List all predictions.\n        call: replicate.list-predictions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-prediction\n        description: Create a new inference prediction.\n        call: replicate.create-prediction\n        with:\n          version: rest.version\n          input: rest.input\n          webhook: rest.webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/predictions/{id}\n      name: prediction\n      description: Get or cancel a specific prediction.\n      operations:\n      - method: GET\n        name: get-prediction\n        description: Get prediction status and output.\n\
  \        call: replicate.get-prediction\n        with:\n          prediction_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-prediction\n        description: Cancel a running prediction.\n        call: replicate.cancel-prediction\n        with:\n          prediction_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{owner}/{name}/predictions\n      name: model-predictions\n      description: Create predictions using official models.\n      operations:\n      - method: POST\n        name: create-model-prediction\n        description: Run inference on an official Replicate model.\n        call: replicate.create-model-prediction\n        with:\n          model_owner: rest.owner\n          model_name: rest.name\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{owner}/{name}/predictions\n\
  \      name: deployment-predictions\n      description: Create predictions using production deployments.\n      operations:\n      - method: POST\n        name: create-deployment-prediction\n        description: Run inference against a production deployment.\n        call: replicate.create-deployment-prediction\n        with:\n          deployment_owner: rest.owner\n          deployment_name: rest.name\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hardware\n      name: hardware\n      description: Available GPU hardware options.\n      operations:\n      - method: GET\n        name: list-hardware\n        description: List available hardware for running models.\n        call: replicate.list-hardware\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: Curated model collections.\n      operations:\n      - method: GET\n\
  \        name: list-collections\n        description: List all curated model collections.\n        call: replicate.list-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections/{slug}\n      name: collection\n      description: Specific model collection.\n      operations:\n      - method: GET\n        name: get-collection\n        description: Get a specific model collection.\n        call: replicate.get-collection\n        with:\n          collection_slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: replicate-inference-mcp\n    transport: http\n    description: MCP server for AI-assisted model inference on Replicate.\n    tools:\n    - name: list-predictions\n      description: List all inference predictions for the account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.list-predictions\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-prediction\n      description: Run a new AI model inference prediction by specifying a model version and input.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replicate.create-prediction\n      with:\n        version: tools.version\n        input: tools.input\n        webhook: tools.webhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-prediction\n      description: Get the status and output of a prediction.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.get-prediction\n      with:\n        prediction_id: tools.prediction_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-prediction\n      description: Cancel a currently running prediction.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: replicate.cancel-prediction\n\
  \      with:\n        prediction_id: tools.prediction_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-model-prediction\n      description: Run inference on an official Replicate model (no version required).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replicate.create-model-prediction\n      with:\n        model_owner: tools.model_owner\n        model_name: tools.model_name\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment-prediction\n      description: Run inference against a production deployment for lower latency.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replicate.create-deployment-prediction\n      with:\n        deployment_owner: tools.deployment_owner\n        deployment_name: tools.deployment_name\n        input: tools.input\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-hardware\n      description: List available GPU hardware options for running models.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.list-hardware\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-collections\n      description: Browse curated model collections by category.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: replicate.list-collections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collection\n      description: Get all models in a specific curated collection.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: replicate.get-collection\n      with:\n        collection_slug: tools.collection_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
