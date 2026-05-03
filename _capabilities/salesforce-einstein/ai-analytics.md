---
categories: []
consumed_apis:
- einstein-vision
- einstein-language
description: Workflow capability combining Einstein Vision and Language APIs for AI-driven analytics workflows. Covers image classification, object detection, sentiment analysis, and intent detection for customer data analytics teams and Salesforce developers building intelligent applications.
layout: capability
name: Salesforce Einstein AI Analytics
operations:
- description: List all vision datasets.
  method: GET
  name: list-vision-datasets
  path: /v1/vision/datasets
- description: Classify an image using a trained model.
  method: POST
  name: classify-image
  path: /v1/vision/predictions
- description: Analyze text sentiment.
  method: POST
  name: analyze-sentiment
  path: /v1/language/sentiment
- description: Detect intent in text.
  method: POST
  name: detect-intent
  path: /v1/language/intent
personas: []
provider_name: Salesforce Einstein
provider_slug: salesforce-einstein
search_terms:
- train a new einstein vision model on an image dataset.
- list vision datasets
- vision list datasets
- vision training datasets.
- analyze the sentiment (positive/negative/neutral) of a text document.
- analyze text sentiment.
- salesforce
- classify an image using a trained model.
- classify an image using a trained einstein vision model.
- detect intent
- predictive analytics
- language detect intent
- vision train model
- language analyze sentiment
- crm
- computer vision
- intent detection.
- list einstein vision image datasets for the account.
- image classification predictions.
- detect intent in text.
- sentiment analysis
- artificial intelligence
- list all vision datasets.
- sentiment analysis.
- detect the intent expressed in a text document for customer service routing.
- classify image
- natural language processing
- salesforce einstein
- machine learning
- analyze sentiment
- image recognition
- vision classify image
slug: ai-analytics
source_filename: ai-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Einstein AI Analytics\"\n  description: >-\n    Workflow capability combining Einstein Vision and Language APIs for\n    AI-driven analytics workflows. Covers image classification, object detection,\n    sentiment analysis, and intent detection for customer data analytics teams\n    and Salesforce developers building intelligent applications.\n  tags:\n    - Artificial Intelligence\n    - Computer Vision\n    - Image Recognition\n    - Machine Learning\n    - Natural Language Processing\n    - Salesforce Einstein\n    - Sentiment Analysis\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      EINSTEIN_VISION_TOKEN: EINSTEIN_VISION_TOKEN\n      EINSTEIN_LANGUAGE_TOKEN: EINSTEIN_LANGUAGE_TOKEN\n\ncapability:\n  consumes:\n    - import: einstein-vision\n      location: ./shared/einstein-vision.yaml\n    - import: einstein-language\n      location: ./shared/einstein-language.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: einstein-ai-analytics-api\n      description: \"Unified REST API for Salesforce Einstein AI analytics.\"\n      resources:\n        - path: /v1/vision/datasets\n          name: vision-datasets\n          description: \"Vision training datasets.\"\n          operations:\n            - method: GET\n              name: list-vision-datasets\n              description: \"List all vision datasets.\"\n              call: \"einstein-vision.list-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vision/predictions\n          name: vision-predictions\n          description: \"Image classification predictions.\"\n          operations:\n            - method: POST\n              name: classify-image\n              description: \"Classify an image using a trained model.\"\n              call: \"einstein-vision.predict-image\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/language/sentiment\n          name: sentiment\n          description: \"Sentiment analysis.\"\n          operations:\n            - method: POST\n              name: analyze-sentiment\n              description: \"Analyze text sentiment.\"\n              call: \"einstein-language.analyze-sentiment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/language/intent\n          name: intent\n          description: \"Intent detection.\"\n          operations:\n            - method: POST\n              name: detect-intent\n              description: \"Detect intent in text.\"\n              call: \"einstein-language.detect-intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: einstein-ai-analytics-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted Salesforce Einstein analytics.\"\n      tools:\n        - name: vision-list-datasets\n          description: \"List Einstein Vision image datasets for the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-vision.list-datasets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vision-classify-image\n          description: \"Classify an image using a trained Einstein Vision model.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-vision.predict-image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vision-train-model\n          description: \"Train a new Einstein Vision model on an image dataset.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-vision.train-model\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: language-analyze-sentiment\n          description: \"Analyze the sentiment (positive/negative/neutral) of a text document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-language.analyze-sentiment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: language-detect-intent\n          description: \"Detect the intent expressed in a text document for customer service routing.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-language.detect-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-einstein/refs/heads/main/capabilities/ai-analytics.yaml
tags:
- Artificial Intelligence
- Computer Vision
- Image Recognition
- Machine Learning
- Natural Language Processing
- Salesforce Einstein
- Sentiment Analysis
tools:
- description: List Einstein Vision image datasets for the account.
  hints:
    idempotent: true
    readOnly: true
  name: vision-list-datasets
- description: Classify an image using a trained Einstein Vision model.
  hints:
    idempotent: true
    readOnly: true
  name: vision-classify-image
- description: Train a new Einstein Vision model on an image dataset.
  hints:
    destructive: false
    readOnly: false
  name: vision-train-model
- description: Analyze the sentiment (positive/negative/neutral) of a text document.
  hints:
    idempotent: true
    readOnly: true
  name: language-analyze-sentiment
- description: Detect the intent expressed in a text document for customer service routing.
  hints:
    idempotent: true
    readOnly: true
  name: language-detect-intent
---
