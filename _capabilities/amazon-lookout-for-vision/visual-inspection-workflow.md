---
categories: []
consumed_apis:
- lookout-for-vision
description: Workflow capability for manufacturing and quality teams to build, train, and deploy computer vision models for automated visual quality inspection using Amazon Lookout for Vision.
layout: capability
name: Amazon Lookout for Vision - Visual Inspection Workflow
operations:
- description: Create a visual inspection project
  method: POST
  name: create-project
  path: /v1/projects
- description: List all inspection projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Train a new inspection model
  method: POST
  name: train-model
  path: /v1/projects/{id}/models
- description: List trained models
  method: GET
  name: list-models
  path: /v1/projects/{id}/models
- description: Detect visual anomalies in an image
  method: POST
  name: detect-anomalies
  path: /v1/projects/{id}/models/{modelVersion}/detect
personas: []
provider_name: Amazon Lookout for Vision
provider_slug: amazon-lookout-for-vision
search_terms:
- run anomaly detection on images
- list models
- list all inspection projects
- train a computer vision model for defect detection
- run anomaly detection on a product image to identify defects
- list inspection models
- running anomaly detection on product images
- workflow for building and deploying computer vision models for quality inspection
- create a new visual quality inspection project
- check the training status and performance metrics of an inspection model
- start inspection model
- amazon
- stop inspection model
- create inspection project
- detect anomalies
- get model status
- managing training and test datasets
- list inspection projects
- train inspection model
- inspect image
- training and lifecycle management of computer vision models
- Manufacturing Engineer
- train model
- list trained models
- list all trained inspection models in a project
- manufacturing
- detect visual anomalies in an image
- list projects
- computer vision
- quality inspection
- runs inspection models on product images to detect defects in real time
- anomaly detection
- train a new inspection model
- visual inspection models
- list all visual inspection projects
- stop a running model to reduce costs when not actively inspecting
- Quality Inspector
- create a visual inspection project
- builds and trains computer vision models for automated defect detection
- aws
- create project
- inspection projects
- start a trained model to enable real-time inspection
- visual inspection
- machine learning
slug: visual-inspection-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Lookout for Vision - Visual Inspection Workflow\"\n  description: \"Workflow capability for manufacturing and quality teams to build, train, and deploy computer vision models for automated visual quality inspection using Amazon Lookout for Vision.\"\n  tags:\n    - Amazon\n    - Computer Vision\n    - Machine Learning\n    - Manufacturing\n    - Quality Inspection\n    - Visual Inspection\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: lookout-for-vision\n      location: ./shared/lookout-for-vision.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: visual-inspection-api\n      description: \"Unified REST API for visual quality inspection workflows.\"\n      resources:\n        - path: /v1/projects\n\
  \          name: projects\n          description: \"Inspection projects\"\n          operations:\n            - method: POST\n              name: create-project\n              description: \"Create a visual inspection project\"\n              call: \"lookout-for-vision.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-projects\n              description: \"List all inspection projects\"\n              call: \"lookout-for-vision.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}/models\n          name: models\n          description: \"Visual inspection models\"\n          operations:\n            - method: POST\n              name: train-model\n              description: \"Train a new inspection model\"\n              call: \"lookout-for-vision.create-model\"\n         \
  \     with:\n                projectName: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-models\n              description: \"List trained models\"\n              call: \"lookout-for-vision.list-models\"\n              with:\n                projectName: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}/models/{modelVersion}/detect\n          name: detection\n          description: \"Run anomaly detection on images\"\n          operations:\n            - method: POST\n              name: detect-anomalies\n              description: \"Detect visual anomalies in an image\"\n              call: \"lookout-for-vision.detect-anomalies\"\n              with:\n                projectName: \"rest.id\"\n                modelVersion: \"rest.modelVersion\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: visual-inspection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted visual quality inspection with Amazon Lookout for Vision.\"\n      tools:\n        - name: create-inspection-project\n          description: \"Create a new visual quality inspection project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"lookout-for-vision.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inspection-projects\n          description: \"List all visual inspection projects\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.list-projects\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n        - name: train-inspection-model\n          description: \"Train a computer vision model for defect detection\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"lookout-for-vision.create-model\"\n          with:\n            projectName: \"tools.projectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-inspection-model\n          description: \"Start a trained model to enable real-time inspection\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.start-model\"\n          with:\n            projectName: \"tools.projectName\"\n            modelVersion: \"tools.modelVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inspect-image\n          description: \"Run\
  \ anomaly detection on a product image to identify defects\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.detect-anomalies\"\n          with:\n            projectName: \"tools.projectName\"\n            modelVersion: \"tools.modelVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model-status\n          description: \"Check the training status and performance metrics of an inspection model\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.describe-model\"\n          with:\n            projectName: \"tools.projectName\"\n            modelVersion: \"tools.modelVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-inspection-model\n          description: \"Stop\
  \ a running model to reduce costs when not actively inspecting\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.stop-model\"\n          with:\n            projectName: \"tools.projectName\"\n            modelVersion: \"tools.modelVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inspection-models\n          description: \"List all trained inspection models in a project\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"lookout-for-vision.list-models\"\n          with:\n            projectName: \"tools.projectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lookout-for-vision/refs/heads/main/capabilities/visual-inspection-workflow.yaml
tags:
- Amazon
- Computer Vision
- Machine Learning
- Manufacturing
- Quality Inspection
- Visual Inspection
tools:
- description: Create a new visual quality inspection project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-inspection-project
- description: List all visual inspection projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-inspection-projects
- description: Train a computer vision model for defect detection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: train-inspection-model
- description: Start a trained model to enable real-time inspection
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-inspection-model
- description: Run anomaly detection on a product image to identify defects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-image
- description: Check the training status and performance metrics of an inspection model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-model-status
- description: Stop a running model to reduce costs when not actively inspecting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-inspection-model
- description: List all trained inspection models in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-inspection-models
---
