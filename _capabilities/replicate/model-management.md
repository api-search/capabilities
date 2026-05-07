---
categories: []
consumed_apis: []
description: Workflow capability for managing ML models, versions, deployments, and training jobs on Replicate. Covers the full model lifecycle from creation through versioning, fine-tuning with training jobs, and production deployment configuration. Designed for ML engineers and platform teams.
layout: capability
name: Replicate Model Management
operations:
- description: List all public models.
  method: GET
  name: list-models
  path: /v1/models
- description: Create a new model.
  method: POST
  name: create-model
  path: /v1/models
- description: Search public models by keyword.
  method: GET
  name: search-models
  path: /v1/models/search
- description: Get model details.
  method: GET
  name: get-model
  path: /v1/models/{owner}/{name}
- description: Delete a model.
  method: DELETE
  name: delete-model
  path: /v1/models/{owner}/{name}
- description: List all versions of a model.
  method: GET
  name: list-model-versions
  path: /v1/models/{owner}/{name}/versions
- description: Get details of a specific model version.
  method: GET
  name: get-model-version
  path: /v1/models/{owner}/{name}/versions/{version_id}
- description: Delete a model version.
  method: DELETE
  name: delete-model-version
  path: /v1/models/{owner}/{name}/versions/{version_id}
- description: List all training jobs.
  method: GET
  name: list-trainings
  path: /v1/trainings
- description: Get training job status.
  method: GET
  name: get-training
  path: /v1/trainings/{id}
- description: Cancel a running training job.
  method: DELETE
  name: cancel-training
  path: /v1/trainings/{id}
- description: List all deployments.
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create a new production deployment.
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: Get deployment configuration.
  method: GET
  name: get-deployment
  path: /v1/deployments/{owner}/{name}
- description: Update deployment scaling configuration.
  method: PATCH
  name: update-deployment
  path: /v1/deployments/{owner}/{name}
- description: Delete a deployment.
  method: DELETE
  name: delete-deployment
  path: /v1/deployments/{owner}/{name}
personas: []
provider_name: Replicate
provider_slug: replicate
search_terms:
- delete deployment
- cancel training
- get details of a specific model version.
- get deployment
- list all production model deployments.
- get deployment configuration.
- search public models by keyword.
- get model version
- search the model marketplace.
- list all deployments.
- browse all public ml models available on replicate.
- cancel a running model fine-tuning job.
- model deployment
- get details and openapi schema for a specific model version.
- list all fine-tuning training jobs.
- manage model versions.
- image generation
- list all versions of a model.
- get the status and logs of a training job.
- artificial intelligence
- get model details.
- update deployment
- get detailed information about a specific model.
- update the scaling configuration of a deployment.
- list trainings
- browse and manage ml models.
- cancel a running training job.
- machine learning
- list model versions
- list deployments
- delete a deployment.
- language models
- update deployment scaling configuration.
- get configuration details for a deployment.
- deployments
- manage a specific training job.
- model management
- list models
- manage a specific model.
- delete model version
- list all training jobs.
- manage a specific deployment.
- manage a specific model version.
- training
- create model
- manage model fine-tuning jobs.
- create a new production deployment.
- delete a model version.
- create a new model.
- get training
- search models
- create deployment
- create a new model on replicate.
- delete a model.
- search the replicate model marketplace by keyword.
- get model
- create a new production model deployment with auto-scaling.
- get training job status.
- delete model
- list all public models.
- manage production deployments.
slug: model-management
source_filename: model-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Replicate Model Management\n  description: Workflow capability for managing ML models, versions, deployments, and training jobs on Replicate. Covers the\n    full model lifecycle from creation through versioning, fine-tuning with training jobs, and production deployment configuration.\n    Designed for ML engineers and platform teams.\n  tags:\n  - Artificial Intelligence\n  - Machine Learning\n  - Model Management\n  - Training\n  - Deployments\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REPLICATE_API_TOKEN: REPLICATE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: replicate\n    baseUri: https://api.replicate.com/v1\n    description: Replicate REST API for running ML models and managing resources.\n    authentication:\n      type: bearer\n      token: '{{REPLICATE_API_TOKEN}}'\n    resources:\n    - name: account\n      path: /account\n      description: Account information\
  \ for the authenticated user or organization.\n      operations:\n      - name: get-account\n        method: GET\n        description: Get the authenticated account information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections\n      path: /collections\n      description: Curated collections of models.\n      operations:\n      - name: list-collections\n        method: GET\n        description: List all collections of models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-collection\n        method: GET\n        description: Get a specific collection of models by slug.\n        inputParameters:\n        - name: collection_slug\n          in: path\n          type: string\n          required: true\n          description: The slug of the collection.\n        outputRawFormat: json\n        outputParameters:\n\
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
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-training\n        method: POST\n        description: Cancel a running training job.\n        inputParameters:\n        - name: training_id\n          in: path\n          type: string\n          required: true\n          description: The training ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks/default/secret\n      description: Webhook signing secret management.\n      operations:\n      - name: get-webhook-secret\n        method: GET\n        description: Get the signing secret for the default webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: replicate-management-api\n    description: Unified REST\
  \ API for Replicate model and deployment management.\n    resources:\n    - path: /v1/models\n      name: models\n      description: Browse and manage ML models.\n      operations:\n      - method: GET\n        name: list-models\n        description: List all public models.\n        call: replicate.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-model\n        description: Create a new model.\n        call: replicate.create-model\n        with:\n          owner: rest.owner\n          name: rest.name\n          description: rest.description\n          visibility: rest.visibility\n          hardware: rest.hardware\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/search\n      name: model-search\n      description: Search the model marketplace.\n      operations:\n      - method: GET\n        name: search-models\n        description: Search public models by keyword.\n\
  \        call: replicate.search-models\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{owner}/{name}\n      name: model\n      description: Manage a specific model.\n      operations:\n      - method: GET\n        name: get-model\n        description: Get model details.\n        call: replicate.get-model\n        with:\n          model_owner: rest.owner\n          model_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-model\n        description: Delete a model.\n        call: replicate.delete-model\n        with:\n          model_owner: rest.owner\n          model_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{owner}/{name}/versions\n      name: model-versions\n      description: Manage model versions.\n      operations:\n      - method: GET\n\
  \        name: list-model-versions\n        description: List all versions of a model.\n        call: replicate.list-model-versions\n        with:\n          model_owner: rest.owner\n          model_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{owner}/{name}/versions/{version_id}\n      name: model-version\n      description: Manage a specific model version.\n      operations:\n      - method: GET\n        name: get-model-version\n        description: Get details of a specific model version.\n        call: replicate.get-model-version\n        with:\n          model_owner: rest.owner\n          model_name: rest.name\n          version_id: rest.version_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-model-version\n        description: Delete a model version.\n        call: replicate.delete-model-version\n        with:\n          model_owner: rest.owner\n\
  \          model_name: rest.name\n          version_id: rest.version_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trainings\n      name: trainings\n      description: Manage model fine-tuning jobs.\n      operations:\n      - method: GET\n        name: list-trainings\n        description: List all training jobs.\n        call: replicate.list-trainings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trainings/{id}\n      name: training\n      description: Manage a specific training job.\n      operations:\n      - method: GET\n        name: get-training\n        description: Get training job status.\n        call: replicate.get-training\n        with:\n          training_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-training\n        description: Cancel a running training job.\n        call: replicate.cancel-training\n\
  \        with:\n          training_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      description: Manage production deployments.\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List all deployments.\n        call: replicate.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n        description: Create a new production deployment.\n        call: replicate.create-deployment\n        with:\n          name: rest.name\n          model: rest.model\n          version: rest.version\n          hardware: rest.hardware\n          min_instances: rest.min_instances\n          max_instances: rest.max_instances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{owner}/{name}\n      name: deployment\n      description:\
  \ Manage a specific deployment.\n      operations:\n      - method: GET\n        name: get-deployment\n        description: Get deployment configuration.\n        call: replicate.get-deployment\n        with:\n          deployment_owner: rest.owner\n          deployment_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-deployment\n        description: Update deployment scaling configuration.\n        call: replicate.update-deployment\n        with:\n          deployment_owner: rest.owner\n          deployment_name: rest.name\n          hardware: rest.hardware\n          min_instances: rest.min_instances\n          max_instances: rest.max_instances\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-deployment\n        description: Delete a deployment.\n        call: replicate.delete-deployment\n        with:\n          deployment_owner:\
  \ rest.owner\n          deployment_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: replicate-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Replicate model and deployment management.\n    tools:\n    - name: list-models\n      description: Browse all public ML models available on Replicate.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: replicate.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-models\n      description: Search the Replicate model marketplace by keyword.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: replicate.search-models\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model\n      description: Get detailed information about a specific model.\n      hints:\n    \
  \    readOnly: true\n        openWorld: true\n      call: replicate.get-model\n      with:\n        model_owner: tools.model_owner\n        model_name: tools.model_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-model\n      description: Create a new model on Replicate.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replicate.create-model\n      with:\n        owner: tools.owner\n        name: tools.name\n        description: tools.description\n        visibility: tools.visibility\n        hardware: tools.hardware\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-model-versions\n      description: List all versions of a model.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.list-model-versions\n      with:\n        model_owner: tools.model_owner\n        model_name: tools.model_name\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-model-version\n      description: Get details and OpenAPI schema for a specific model version.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.get-model-version\n      with:\n        model_owner: tools.model_owner\n        model_name: tools.model_name\n        version_id: tools.version_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-trainings\n      description: List all fine-tuning training jobs.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.list-trainings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-training\n      description: Get the status and logs of a training job.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.get-training\n      with:\n        training_id: tools.training_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: cancel-training\n      description: Cancel a running model fine-tuning job.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: replicate.cancel-training\n      with:\n        training_id: tools.training_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List all production model deployments.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n      description: Create a new production model deployment with auto-scaling.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replicate.create-deployment\n      with:\n        name: tools.name\n        model: tools.model\n        version: tools.version\n        hardware: tools.hardware\n\
  \        min_instances: tools.min_instances\n        max_instances: tools.max_instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get configuration details for a deployment.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replicate.get-deployment\n      with:\n        deployment_owner: tools.deployment_owner\n        deployment_name: tools.deployment_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-deployment\n      description: Update the scaling configuration of a deployment.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: replicate.update-deployment\n      with:\n        deployment_owner: tools.deployment_owner\n        deployment_name: tools.deployment_name\n        hardware: tools.hardware\n        min_instances: tools.min_instances\n        max_instances: tools.max_instances\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/replicate/refs/heads/main/capabilities/model-management.yaml
tags:
- Artificial Intelligence
- Machine Learning
- Model Management
- Training
- Deployments
tools:
- description: Browse all public ML models available on Replicate.
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: Search the Replicate model marketplace by keyword.
  hints:
    openWorld: true
    readOnly: true
  name: search-models
- description: Get detailed information about a specific model.
  hints:
    openWorld: true
    readOnly: true
  name: get-model
- description: Create a new model on Replicate.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-model
- description: List all versions of a model.
  hints:
    openWorld: false
    readOnly: true
  name: list-model-versions
- description: Get details and OpenAPI schema for a specific model version.
  hints:
    openWorld: false
    readOnly: true
  name: get-model-version
- description: List all fine-tuning training jobs.
  hints:
    openWorld: false
    readOnly: true
  name: list-trainings
- description: Get the status and logs of a training job.
  hints:
    openWorld: false
    readOnly: true
  name: get-training
- description: Cancel a running model fine-tuning job.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-training
- description: List all production model deployments.
  hints:
    openWorld: false
    readOnly: true
  name: list-deployments
- description: Create a new production model deployment with auto-scaling.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-deployment
- description: Get configuration details for a deployment.
  hints:
    openWorld: false
    readOnly: true
  name: get-deployment
- description: Update the scaling configuration of a deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-deployment
---
