---
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
- list all sagemaker inference endpoints
- list registered sagemaker ml models
- model inference endpoint management
- list notebook instances
- get the status and details of a sagemaker inference endpoint
- create model
- deploy endpoint
- list all sagemaker training jobs
- model training job management
- register model
- create a sagemaker jupyter notebook instance
- register a trained model for deployment
- amazon sagemaker
- list active sagemaker inference endpoints
- aws
- describe training job
- engineers who build, train, and deploy machine learning models at scale
- list endpoints
- scientists who explore data and experiment with ml models using notebooks and experiments
- create notebook
- list all sagemaker notebook instances
- create a sagemaker notebook instance for ml development
- machine learning
- submit a sagemaker model training job
- ai
- training
- mlops
- get details about a specific sagemaker training job
- register a trained model in sagemaker
- list sagemaker model training jobs
- submit a new model training job
- list training jobs
- ML Engineer
- list models
- create training job
- deploy a model to a sagemaker inference endpoint
- list sagemaker jupyter notebook instances for ml development
- describe endpoint
- inference
- end-to-end ml lifecycle from notebook development through training, model registration, and endpoint deployment
- trained model artifact management
- create notebook instance
- jupyter notebook instance management for ml development
- operational management of ml pipelines, monitoring, and model governance
- list all registered sagemaker models
- Data Scientist
- list notebooks
- feature creation, storage, and retrieval for ml models
- core ml activities including model development, training, and inference
slug: ml-lifecycle-management
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
