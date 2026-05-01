---
api_specs:
- filename: amazon-sagemaker-openapi.yml
  format: yaml
  label: amazon-sagemaker
  slug: amazon-sagemaker
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-sagemaker/refs/heads/main/openapi/amazon-sagemaker-openapi.yml
categories:
- machine-learning
consumed_apis:
- amazon-sagemaker
description: Unified capability for managing the end-to-end machine learning lifecycle including notebook development, training, model management, and endpoint deployment. Used by ML Engineers and Data Scientists.
layout: capability
name: Amazon SageMaker ML Lifecycle Management
operations:
- description: List all SageMaker notebook instances
  method: GET
  name: list-notebooks
  path: /v1/notebooks
- description: Create a SageMaker notebook instance for ML development
  method: POST
  name: create-notebook
  path: /v1/notebooks
- description: List all SageMaker training jobs
  method: GET
  name: list-training-jobs
  path: /v1/training-jobs
- description: Submit a new model training job
  method: POST
  name: create-training-job
  path: /v1/training-jobs
- description: List all registered SageMaker models
  method: GET
  name: list-models
  path: /v1/models
- description: Register a trained model for deployment
  method: POST
  name: register-model
  path: /v1/models
- description: List all SageMaker inference endpoints
  method: GET
  name: list-endpoints
  path: /v1/endpoints
- description: Deploy a model to a SageMaker inference endpoint
  method: POST
  name: deploy-endpoint
  path: /v1/endpoints
personas: []
provider_name: Amazon SageMaker
provider_slug: amazon-sagemaker
search_terms:
- model training job management
- list models
- list notebooks
- deploy endpoint
- trained model artifact management
- get details about a specific sagemaker training job
- list all registered sagemaker models
- inference
- submit a sagemaker model training job
- list sagemaker model training jobs
- core ml activities including model development, training, and inference
- list all sagemaker notebook instances
- engineers who build, train, and deploy machine learning models at scale
- amazon sagemaker
- jupyter notebook instance management for ml development
- ai
- ML Engineer
- list all sagemaker training jobs
- list training jobs
- mlops
- Data Scientist
- create a sagemaker notebook instance for ml development
- model inference endpoint management
- create a sagemaker jupyter notebook instance
- submit a new model training job
- machine learning
- create training job
- register a trained model for deployment
- register model
- list active sagemaker inference endpoints
- create notebook
- describe training job
- training
- register a trained model in sagemaker
- list all sagemaker inference endpoints
- deploy a model to a sagemaker inference endpoint
- list endpoints
- create model
- get the status and details of a sagemaker inference endpoint
- scientists who explore data and experiment with ml models using notebooks and experiments
- list notebook instances
- describe endpoint
- create notebook instance
- list registered sagemaker ml models
- operational management of ml pipelines, monitoring, and model governance
- end-to-end ml lifecycle from notebook development through training, model registration, and endpoint deployment
- feature creation, storage, and retrieval for ml models
- list sagemaker jupyter notebook instances for ml development
slug: ml-lifecycle-management
source_filename: ml-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon SageMaker ML Lifecycle Management\"\n  description: \"Unified capability for managing the end-to-end machine learning lifecycle including notebook development, training, model management, and endpoint deployment. Used by ML Engineers and Data Scientists.\"\n  tags:\n    - Amazon SageMaker\n    - Machine Learning\n    - MLOps\n    - Training\n    - Inference\n    - AI\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-sagemaker\n      location: ./shared/amazon-sagemaker.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ml-lifecycle-api\n      description: \"Unified REST API for Amazon SageMaker ML lifecycle management.\"\n      resources:\n        - path: /v1/notebooks\n          name:\
  \ notebooks\n          description: \"Jupyter notebook instance management for ML development\"\n          operations:\n            - method: GET\n              name: list-notebooks\n              description: \"List all SageMaker notebook instances\"\n              call: \"amazon-sagemaker.list-notebook-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-notebook\n              description: \"Create a SageMaker notebook instance for ML development\"\n              call: \"amazon-sagemaker.create-notebook-instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/training-jobs\n          name: training-jobs\n          description: \"Model training job management\"\n          operations:\n            - method: GET\n              name: list-training-jobs\n              description: \"List all SageMaker\
  \ training jobs\"\n              call: \"amazon-sagemaker.list-training-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-training-job\n              description: \"Submit a new model training job\"\n              call: \"amazon-sagemaker.create-training-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"Trained model artifact management\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all registered SageMaker models\"\n              call: \"amazon-sagemaker.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-model\n              description: \"Register a trained\
  \ model for deployment\"\n              call: \"amazon-sagemaker.create-model\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/endpoints\n          name: endpoints\n          description: \"Model inference endpoint management\"\n          operations:\n            - method: GET\n              name: list-endpoints\n              description: \"List all SageMaker inference endpoints\"\n              call: \"amazon-sagemaker.list-endpoints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-endpoint\n              description: \"Deploy a model to a SageMaker inference endpoint\"\n              call: \"amazon-sagemaker.create-endpoint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ml-lifecycle-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted Amazon SageMaker ML lifecycle management.\"\n      tools:\n        - name: list-notebook-instances\n          description: \"List SageMaker Jupyter notebook instances for ML development\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-sagemaker.list-notebook-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-notebook-instance\n          description: \"Create a SageMaker Jupyter notebook instance\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-sagemaker.create-notebook-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-training-jobs\n          description: \"List SageMaker model training jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n         \
  \ call: \"amazon-sagemaker.list-training-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-training-job\n          description: \"Submit a SageMaker model training job\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-sagemaker.create-training-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-training-job\n          description: \"Get details about a specific SageMaker training job\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-sagemaker.describe-training-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-models\n          description: \"List registered SageMaker ML models\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-sagemaker.list-models\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-model\n          description: \"Register a trained model in SageMaker\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-sagemaker.create-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-endpoints\n          description: \"List active SageMaker inference endpoints\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-sagemaker.list-endpoints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-endpoint\n          description: \"Deploy a model to a SageMaker inference endpoint\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-sagemaker.create-endpoint\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: describe-endpoint\n          description: \"Get the status and details of a SageMaker inference endpoint\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-sagemaker.describe-endpoint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-sagemaker/refs/heads/main/capabilities/ml-lifecycle-management.yaml
tags:
- Amazon SageMaker
- Machine Learning
- MLOps
- Training
- Inference
- AI
tools:
- description: List SageMaker Jupyter notebook instances for ML development
  hints:
    idempotent: true
    readOnly: true
  name: list-notebook-instances
- description: Create a SageMaker Jupyter notebook instance
  hints:
    idempotent: false
    readOnly: false
  name: create-notebook-instance
- description: List SageMaker model training jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-training-jobs
- description: Submit a SageMaker model training job
  hints:
    idempotent: false
    readOnly: false
  name: create-training-job
- description: Get details about a specific SageMaker training job
  hints:
    idempotent: true
    readOnly: true
  name: describe-training-job
- description: List registered SageMaker ML models
  hints:
    idempotent: true
    readOnly: true
  name: list-models
- description: Register a trained model in SageMaker
  hints:
    idempotent: false
    readOnly: false
  name: create-model
- description: List active SageMaker inference endpoints
  hints:
    idempotent: true
    readOnly: true
  name: list-endpoints
- description: Deploy a model to a SageMaker inference endpoint
  hints:
    idempotent: false
    readOnly: false
  name: deploy-endpoint
- description: Get the status and details of a SageMaker inference endpoint
  hints:
    idempotent: true
    readOnly: true
  name: describe-endpoint
---
