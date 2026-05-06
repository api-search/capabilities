---
categories: []
consumed_apis: []
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
- sentiment analysis
- language analyze sentiment
- natural language processing
- image recognition
- salesforce einstein
- vision list datasets
- analyze the sentiment (positive/negative/neutral) of a text document.
- sentiment analysis.
- computer vision
- detect intent in text.
- classify an image using a trained einstein vision model.
- classify an image using a trained model.
- list all vision datasets.
- analyze text sentiment.
- intent detection.
- list einstein vision image datasets for the account.
- train a new einstein vision model on an image dataset.
- detect the intent expressed in a text document for customer service routing.
- vision train model
- artificial intelligence
- analyze sentiment
- image classification predictions.
- vision training datasets.
- crm
- machine learning
- language detect intent
- list vision datasets
- salesforce
- detect intent
- classify image
- predictive analytics
- vision classify image
slug: ai-analytics
source_filename: ai-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Einstein AI Analytics\n  description: Workflow capability combining Einstein Vision and Language APIs for AI-driven analytics workflows. Covers image\n    classification, object detection, sentiment analysis, and intent detection for customer data analytics teams and Salesforce\n    developers building intelligent applications.\n  tags:\n  - Artificial Intelligence\n  - Computer Vision\n  - Image Recognition\n  - Machine Learning\n  - Natural Language Processing\n  - Salesforce Einstein\n  - Sentiment Analysis\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    EINSTEIN_VISION_TOKEN: EINSTEIN_VISION_TOKEN\n    EINSTEIN_LANGUAGE_TOKEN: EINSTEIN_LANGUAGE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: einstein-vision\n    baseUri: https://api.einstein.ai/v2/vision\n    description: Salesforce Einstein Vision REST API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{env.EINSTEIN_VISION_TOKEN}}'\n    resources:\n    - name: datasets\n      path: /datasets\n      description: Image datasets for training vision models.\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List all datasets for the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: datasets\n          type: object\n          value: $.\n      - name: create-dataset\n        method: POST\n        description: Create a new image dataset.\n        outputRawFormat: json\n        outputParameters:\n        - name: dataset\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: get-dataset\n        method: GET\n        description: Get a dataset by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Dataset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: dataset\n          type: object\n          value: $.\n      - name: delete-dataset\n        method: DELETE\n        description: Delete a dataset.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Dataset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /train\n      description: Train and manage vision models.\n      operations:\n      - name: train-model\n        method: POST\n        description: Train a new model on a dataset.\n        outputRawFormat: json\n        outputParameters:\n        - name: model\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            datasetId: '{{tools.datasetId}}'\n    - name:\
  \ predictions\n      path: /predict\n      description: Make image predictions using trained models.\n      operations:\n      - name: predict-image\n        method: POST\n        description: Classify an image using a trained model.\n        outputRawFormat: json\n        outputParameters:\n        - name: prediction\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            modelId: '{{tools.modelId}}'\n            sampleBase64Content: '{{tools.sampleBase64Content}}'\n  - type: http\n    namespace: einstein-language\n    baseUri: https://api.einstein.ai/v2/language\n    description: Salesforce Einstein Language NLP API.\n    authentication:\n      type: bearer\n      token: '{{env.EINSTEIN_LANGUAGE_TOKEN}}'\n    resources:\n    - name: sentiment\n      path: /sentiment\n      description: Sentiment analysis predictions.\n      operations:\n      - name: analyze-sentiment\n        method: POST\n        description: Analyze sentiment\
  \ of text input.\n        outputRawFormat: json\n        outputParameters:\n        - name: sentiment\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            modelId: '{{tools.modelId}}'\n            document: '{{tools.document}}'\n    - name: intent\n      path: /intent\n      description: Intent detection predictions.\n      operations:\n      - name: detect-intent\n        method: POST\n        description: Detect intent from text input.\n        outputRawFormat: json\n        outputParameters:\n        - name: intent\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            modelId: '{{tools.modelId}}'\n            document: '{{tools.document}}'\n    - name: datasets\n      path: /datasets\n      description: Text datasets for NLP model training.\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List all language datasets.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: datasets\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: einstein-ai-analytics-api\n    description: Unified REST API for Salesforce Einstein AI analytics.\n    resources:\n    - path: /v1/vision/datasets\n      name: vision-datasets\n      description: Vision training datasets.\n      operations:\n      - method: GET\n        name: list-vision-datasets\n        description: List all vision datasets.\n        call: einstein-vision.list-datasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vision/predictions\n      name: vision-predictions\n      description: Image classification predictions.\n      operations:\n      - method: POST\n        name: classify-image\n        description: Classify an image using a trained model.\n        call: einstein-vision.predict-image\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/language/sentiment\n      name: sentiment\n      description: Sentiment analysis.\n      operations:\n      - method: POST\n        name: analyze-sentiment\n        description: Analyze text sentiment.\n        call: einstein-language.analyze-sentiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/language/intent\n      name: intent\n      description: Intent detection.\n      operations:\n      - method: POST\n        name: detect-intent\n        description: Detect intent in text.\n        call: einstein-language.detect-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: einstein-ai-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce Einstein analytics.\n    tools:\n    - name: vision-list-datasets\n      description: List Einstein Vision image datasets for the account.\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: einstein-vision.list-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vision-classify-image\n      description: Classify an image using a trained Einstein Vision model.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-vision.predict-image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: vision-train-model\n      description: Train a new Einstein Vision model on an image dataset.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-vision.train-model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: language-analyze-sentiment\n      description: Analyze the sentiment (positive/negative/neutral) of a text document.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-language.analyze-sentiment\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: language-detect-intent\n      description: Detect the intent expressed in a text document for customer service routing.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-language.detect-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
