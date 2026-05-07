---
categories:
- machine-learning
consumed_apis: []
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
- engineers who build, train, and deploy machine learning models at scale
- trained model artifact management
- model training job management
- end-to-end ml lifecycle from notebook development through training, model registration, and endpoint deployment
- submit a new model training job
- ai
- list registered sagemaker ml models
- Data Scientist
- ML Engineer
- scientists who explore data and experiment with ml models using notebooks and experiments
- describe training job
- list all registered sagemaker models
- create notebook
- deploy a model to a sagemaker inference endpoint
- list all sagemaker inference endpoints
- machine learning
- create a sagemaker jupyter notebook instance
- describe endpoint
- list all sagemaker training jobs
- list notebooks
- get the status and details of a sagemaker inference endpoint
- create a sagemaker notebook instance for ml development
- core ml activities including model development, training, and inference
- mlops
- inference
- create notebook instance
- operational management of ml pipelines, monitoring, and model governance
- list sagemaker jupyter notebook instances for ml development
- register a trained model for deployment
- list models
- create training job
- register a trained model in sagemaker
- model inference endpoint management
- training
- create model
- list all sagemaker notebook instances
- list sagemaker model training jobs
- list training jobs
- get details about a specific sagemaker training job
- feature creation, storage, and retrieval for ml models
- submit a sagemaker model training job
- register model
- list endpoints
- deploy endpoint
- jupyter notebook instance management for ml development
- list notebook instances
- amazon sagemaker
- list active sagemaker inference endpoints
slug: ml-lifecycle-management
source_filename: ml-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon SageMaker ML Lifecycle Management\n  description: Unified capability for managing the end-to-end machine learning lifecycle including notebook development, training,\n    model management, and endpoint deployment. Used by ML Engineers and Data Scientists.\n  tags:\n  - Amazon SageMaker\n  - Machine Learning\n  - MLOps\n  - Training\n  - Inference\n  - AI\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-sagemaker\n    baseUri: https://api.sagemaker.us-east-1.amazonaws.com\n    description: Amazon SageMaker control plane API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: notebook-instances\n\
  \      path: /\n      description: Notebook instance management operations\n      operations:\n      - name: create-notebook-instance\n        method: POST\n        description: Creates an ML compute instance with Jupyter notebook\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-notebook-instance\n        method: POST\n        description: Returns information about a notebook instance\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-notebook-instances\n\
  \        method: POST\n        description: Returns a list of notebook instances\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: training-jobs\n      path: /\n      description: Training job management operations\n      operations:\n      - name: create-training-job\n        method: POST\n        description: Creates a model training job\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-training-job\n        method: POST\n        description:\
  \ Returns information about a training job\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-training-jobs\n        method: POST\n        description: Lists training jobs\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /\n      description: Model management operations\n      operations:\n      - name: create-model\n        method: POST\n        description: Creates a model that you can host at an Amazon SageMaker endpoint\n   \
  \     inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-model\n        method: POST\n        description: Describes a model\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-models\n        method: POST\n        description: Lists models created with CreateModel\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints\n      path: /\n      description: Endpoint management operations\n      operations:\n      - name: create-endpoint\n        method: POST\n        description: Creates an endpoint using the endpoint configuration specified in the request\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-endpoint\n        method: POST\n        description: Returns the description of an endpoint\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-endpoints\n        method: POST\n        description: Lists endpoints\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: SageMaker API action target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ml-lifecycle-api\n    description: Unified REST API for Amazon SageMaker ML lifecycle management.\n    resources:\n    - path: /v1/notebooks\n      name: notebooks\n      description: Jupyter notebook instance management for ML development\n      operations:\n      - method: GET\n        name: list-notebooks\n        description: List all SageMaker notebook instances\n        call: amazon-sagemaker.list-notebook-instances\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-notebook\n        description: Create a SageMaker notebook instance for ML development\n        call: amazon-sagemaker.create-notebook-instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/training-jobs\n      name: training-jobs\n      description: Model training job management\n      operations:\n      - method: GET\n        name: list-training-jobs\n        description: List all SageMaker training jobs\n        call: amazon-sagemaker.list-training-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-training-job\n        description: Submit a new model training job\n        call: amazon-sagemaker.create-training-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Trained model artifact management\n\
  \      operations:\n      - method: GET\n        name: list-models\n        description: List all registered SageMaker models\n        call: amazon-sagemaker.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-model\n        description: Register a trained model for deployment\n        call: amazon-sagemaker.create-model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints\n      name: endpoints\n      description: Model inference endpoint management\n      operations:\n      - method: GET\n        name: list-endpoints\n        description: List all SageMaker inference endpoints\n        call: amazon-sagemaker.list-endpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: deploy-endpoint\n        description: Deploy a model to a SageMaker inference endpoint\n        call: amazon-sagemaker.create-endpoint\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ml-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon SageMaker ML lifecycle management.\n    tools:\n    - name: list-notebook-instances\n      description: List SageMaker Jupyter notebook instances for ML development\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-sagemaker.list-notebook-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-notebook-instance\n      description: Create a SageMaker Jupyter notebook instance\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-sagemaker.create-notebook-instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-training-jobs\n      description: List SageMaker model training jobs\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: amazon-sagemaker.list-training-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-training-job\n      description: Submit a SageMaker model training job\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-sagemaker.create-training-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-training-job\n      description: Get details about a specific SageMaker training job\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-sagemaker.describe-training-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List registered SageMaker ML models\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-sagemaker.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-model\n      description: Register\
  \ a trained model in SageMaker\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-sagemaker.create-model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-endpoints\n      description: List active SageMaker inference endpoints\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-sagemaker.list-endpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-endpoint\n      description: Deploy a model to a SageMaker inference endpoint\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-sagemaker.create-endpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-endpoint\n      description: Get the status and details of a SageMaker inference endpoint\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-sagemaker.describe-endpoint\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
