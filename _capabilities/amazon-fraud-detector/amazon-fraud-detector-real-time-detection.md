---
categories: []
consumed_apis: []
description: Orchestrate ML models and business rules for real-time transaction fraud scoring and decision-making.
layout: capability
name: Amazon Fraud Detector Real-Time Detection
operations: []
personas: []
provider_name: Amazon Fraud Detector
provider_slug: amazon-fraud-detector
search_terms:
- real-time
- financial security
- security
- fraud detection
- aws
- financial services
- machine learning
slug: amazon-fraud-detector-real-time-detection
source_filename: amazon-fraud-detector-real-time-detection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Fraud Detector Real-Time Detection\n  description: Orchestrate ML models and business rules for real-time transaction fraud scoring and decision-making.\n  tags:\n  - Fraud Detection\n  - Machine Learning\n  - Real-Time\n  - Financial Security\n  - AWS\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: frauddetector\n    ref: capabilities/shared/fraud-detector.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: putDetector\n    description: Create or update a fraud detector\n    inputSchema:\n      type: object\n      properties:\n        detectorId:\n          type: string\n        eventTypeName:\n          type: string\n        description:\n          type: string\n      required:\n      - detectorId\n      - eventTypeName\n  - name: getDetectors\n\
  \    description: Get one or all detectors\n    inputSchema:\n      type: object\n      properties:\n        detectorId:\n          type: string\n        nextToken:\n          type: string\n        maxResults:\n          type: integer\n  - name: deleteDetector\n    description: Delete a detector\n    inputSchema:\n      type: object\n      properties:\n        detectorId:\n          type: string\n      required:\n      - detectorId\n  - name: putModel\n    description: Create or update a fraud detection ML model\n    inputSchema:\n      type: object\n      properties:\n        modelId:\n          type: string\n        modelType:\n          type: string\n        eventTypeName:\n          type: string\n      required:\n      - modelId\n      - modelType\n      - eventTypeName\n  - name: getModels\n    description: Get one or all fraud detection models\n    inputSchema:\n      type: object\n      properties:\n        modelId:\n          type: string\n        modelType:\n          type: string\n\
  \        nextToken:\n          type: string\n  - name: createRule\n    description: Create a rule for a detector\n    inputSchema:\n      type: object\n      properties:\n        ruleId:\n          type: string\n        detectorId:\n          type: string\n        expression:\n          type: string\n        language:\n          type: string\n        outcomes:\n          type: array\n      required:\n      - ruleId\n      - detectorId\n      - expression\n      - language\n      - outcomes\n  - name: getRules\n    description: Get rules for a detector\n    inputSchema:\n      type: object\n      properties:\n        detectorId:\n          type: string\n        ruleId:\n          type: string\n      required:\n      - detectorId\n  - name: getEventPrediction\n    description: Get real-time fraud prediction for an event\n    inputSchema:\n      type: object\n      properties:\n        detectorId:\n          type: string\n        eventId:\n          type: string\n        eventTypeName:\n\
  \          type: string\n        eventTimestamp:\n          type: string\n        entities:\n          type: array\n        eventVariables:\n          type: object\n      required:\n      - detectorId\n      - eventId\n      - eventTypeName\n      - eventTimestamp\n      - entities\n      - eventVariables\n  - name: putEventType\n    description: Create or update an event type schema\n    inputSchema:\n      type: object\n      properties:\n        name:\n          type: string\n        eventVariables:\n          type: array\n        labels:\n          type: array\n        entityTypes:\n          type: array\n      required:\n      - name\n      - eventVariables\n      - labels\n      - entityTypes\n  - name: getEventTypes\n    description: Get event types\n    inputSchema:\n      type: object\n      properties:\n        name:\n          type: string\n        nextToken:\n          type: string\n  - name: putLabel\n    description: Create or update a fraud label\n    inputSchema:\n    \
  \  type: object\n      properties:\n        name:\n          type: string\n        description:\n          type: string\n      required:\n      - name\n  - name: listTagsForResource\n    description: List tags for a Fraud Detector resource\n    inputSchema:\n      type: object\n      properties:\n        resourceARN:\n          type: string\n      required:\n      - resourceARN\n  - name: tagResource\n    description: Tag a Fraud Detector resource\n    inputSchema:\n      type: object\n      properties:\n        resourceARN:\n          type: string\n        tags:\n          type: array\n      required:\n      - resourceARN\n      - tags\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-fraud-detector/refs/heads/main/capabilities/amazon-fraud-detector-real-time-detection.yaml
tags:
- Fraud Detection
- Machine Learning
- Real-Time
- Financial Security
- AWS
tools: []
---
