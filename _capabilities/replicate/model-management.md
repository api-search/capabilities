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
- manage a specific training job.
- get model version
- search the replicate model marketplace by keyword.
- cancel training
- get configuration details for a deployment.
- get model details.
- manage a specific deployment.
- training
- browse and manage ml models.
- list all production model deployments.
- list trainings
- search models
- model management
- create a new production deployment.
- create a new model.
- manage model fine-tuning jobs.
- manage a specific model.
- create deployment
- delete a model version.
- deployments
- update the scaling configuration of a deployment.
- model deployment
- manage model versions.
- browse all public ml models available on replicate.
- delete model
- list all training jobs.
- create model
- delete a deployment.
- get deployment
- image generation
- get model
- list all versions of a model.
- create a new production model deployment with auto-scaling.
- get the status and logs of a training job.
- cancel a running model fine-tuning job.
- get details and openapi schema for a specific model version.
- list model versions
- delete deployment
- get training
- artificial intelligence
- get training job status.
- search the model marketplace.
- create a new model on replicate.
- get details of a specific model version.
- manage a specific model version.
- cancel a running training job.
- get deployment configuration.
- list all public models.
- list all fine-tuning training jobs.
- language models
- list all deployments.
- list models
- delete a model.
- list deployments
- manage production deployments.
- delete model version
- update deployment scaling configuration.
- machine learning
- get detailed information about a specific model.
- update deployment
- search public models by keyword.
slug: model-management
source_filename: model-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Replicate Model Management\"\n  description: >-\n    Workflow capability for managing ML models, versions, deployments, and\n    training jobs on Replicate. Covers the full model lifecycle from creation\n    through versioning, fine-tuning with training jobs, and production\n    deployment configuration. Designed for ML engineers and platform teams.\n  tags:\n    - Artificial Intelligence\n    - Machine Learning\n    - Model Management\n    - Training\n    - Deployments\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REPLICATE_API_TOKEN: REPLICATE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: replicate\n      location: ./shared/replicate.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: replicate-management-api\n      description: \"Unified REST API for Replicate model and deployment management.\"\n      resources:\n        - path: /v1/models\n\
  \          name: models\n          description: \"Browse and manage ML models.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all public models.\"\n              call: \"replicate.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-model\n              description: \"Create a new model.\"\n              call: \"replicate.create-model\"\n              with:\n                owner: \"rest.owner\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                visibility: \"rest.visibility\"\n                hardware: \"rest.hardware\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/search\n          name: model-search\n          description: \"Search the model marketplace.\"\n  \
  \        operations:\n            - method: GET\n              name: search-models\n              description: \"Search public models by keyword.\"\n              call: \"replicate.search-models\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{owner}/{name}\n          name: model\n          description: \"Manage a specific model.\"\n          operations:\n            - method: GET\n              name: get-model\n              description: \"Get model details.\"\n              call: \"replicate.get-model\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-model\n              description: \"Delete a model.\"\n              call: \"\
  replicate.delete-model\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{owner}/{name}/versions\n          name: model-versions\n          description: \"Manage model versions.\"\n          operations:\n            - method: GET\n              name: list-model-versions\n              description: \"List all versions of a model.\"\n              call: \"replicate.list-model-versions\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/models/{owner}/{name}/versions/{version_id}\n          name: model-version\n          description: \"Manage a specific model version.\"\n          operations:\n            - method: GET\n \
  \             name: get-model-version\n              description: \"Get details of a specific model version.\"\n              call: \"replicate.get-model-version\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n                version_id: \"rest.version_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-model-version\n              description: \"Delete a model version.\"\n              call: \"replicate.delete-model-version\"\n              with:\n                model_owner: \"rest.owner\"\n                model_name: \"rest.name\"\n                version_id: \"rest.version_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trainings\n          name: trainings\n          description: \"Manage model fine-tuning jobs.\"\n          operations:\n\
  \            - method: GET\n              name: list-trainings\n              description: \"List all training jobs.\"\n              call: \"replicate.list-trainings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trainings/{id}\n          name: training\n          description: \"Manage a specific training job.\"\n          operations:\n            - method: GET\n              name: get-training\n              description: \"Get training job status.\"\n              call: \"replicate.get-training\"\n              with:\n                training_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-training\n              description: \"Cancel a running training job.\"\n              call: \"replicate.cancel-training\"\n              with:\n                training_id: \"rest.id\"\n         \
  \     outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments\n          name: deployments\n          description: \"Manage production deployments.\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List all deployments.\"\n              call: \"replicate.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Create a new production deployment.\"\n              call: \"replicate.create-deployment\"\n              with:\n                name: \"rest.name\"\n                model: \"rest.model\"\n                version: \"rest.version\"\n                hardware: \"rest.hardware\"\n                min_instances: \"rest.min_instances\"\n                max_instances: \"rest.max_instances\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{owner}/{name}\n          name: deployment\n          description: \"Manage a specific deployment.\"\n          operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get deployment configuration.\"\n              call: \"replicate.get-deployment\"\n              with:\n                deployment_owner: \"rest.owner\"\n                deployment_name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-deployment\n              description: \"Update deployment scaling configuration.\"\n              call: \"replicate.update-deployment\"\n              with:\n                deployment_owner: \"rest.owner\"\n                deployment_name: \"rest.name\"\n                hardware: \"rest.hardware\"\
  \n                min_instances: \"rest.min_instances\"\n                max_instances: \"rest.max_instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-deployment\n              description: \"Delete a deployment.\"\n              call: \"replicate.delete-deployment\"\n              with:\n                deployment_owner: \"rest.owner\"\n                deployment_name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: replicate-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Replicate model and deployment management.\"\n      tools:\n        - name: list-models\n          description: \"Browse all public ML models available on Replicate.\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"replicate.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-models\n          description: \"Search the Replicate model marketplace by keyword.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"replicate.search-models\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-model\n          description: \"Get detailed information about a specific model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"replicate.get-model\"\n          with:\n            model_owner: \"tools.model_owner\"\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-model\n          description: \"Create a new model\
  \ on Replicate.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"replicate.create-model\"\n          with:\n            owner: \"tools.owner\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            visibility: \"tools.visibility\"\n            hardware: \"tools.hardware\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-model-versions\n          description: \"List all versions of a model.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.list-model-versions\"\n          with:\n            model_owner: \"tools.model_owner\"\n            model_name: \"tools.model_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-model-version\n          description: \"Get details and OpenAPI schema\
  \ for a specific model version.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.get-model-version\"\n          with:\n            model_owner: \"tools.model_owner\"\n            model_name: \"tools.model_name\"\n            version_id: \"tools.version_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-trainings\n          description: \"List all fine-tuning training jobs.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.list-trainings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-training\n          description: \"Get the status and logs of a training job.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.get-training\"\n          with:\n            training_id: \"tools.training_id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-training\n          description: \"Cancel a running model fine-tuning job.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"replicate.cancel-training\"\n          with:\n            training_id: \"tools.training_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-deployments\n          description: \"List all production model deployments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-deployment\n          description: \"Create a new production model deployment with auto-scaling.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"replicate.create-deployment\"\n          with:\n            name: \"tools.name\"\n            model: \"tools.model\"\n            version: \"tools.version\"\n            hardware: \"tools.hardware\"\n            min_instances: \"tools.min_instances\"\n            max_instances: \"tools.max_instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment\n          description: \"Get configuration details for a deployment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replicate.get-deployment\"\n          with:\n            deployment_owner: \"tools.deployment_owner\"\n            deployment_name: \"tools.deployment_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-deployment\n          description: \"Update the scaling configuration of a deployment.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"replicate.update-deployment\"\n          with:\n            deployment_owner: \"tools.deployment_owner\"\n            deployment_name: \"tools.deployment_name\"\n            hardware: \"tools.hardware\"\n            min_instances: \"tools.min_instances\"\n            max_instances: \"tools.max_instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
