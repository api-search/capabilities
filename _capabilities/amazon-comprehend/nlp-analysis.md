---
categories: []
consumed_apis:
- comprehend
description: Workflow capability for natural language processing analysis including entity recognition, sentiment analysis, key phrase extraction, language detection, PII detection, and custom text classification. Used by data scientists and application developers to extract insights from unstructured text.
layout: capability
name: Amazon Comprehend NLP Analysis
operations:
- description: Detect named entities in text.
  method: POST
  name: detect-entities
  path: /v1/analyze/entities
- description: Detect sentiment in text.
  method: POST
  name: detect-sentiment
  path: /v1/analyze/sentiment
- description: Extract key phrases from text.
  method: POST
  name: detect-key-phrases
  path: /v1/analyze/key-phrases
- description: Detect the dominant language of text.
  method: POST
  name: detect-language
  path: /v1/analyze/language
- description: Detect PII entities in text.
  method: POST
  name: detect-pii
  path: /v1/analyze/pii
- description: List available document classifiers.
  method: GET
  name: list-classifiers
  path: /v1/classify
- description: Detect entities in multiple documents.
  method: POST
  name: batch-detect-entities
  path: /v1/batch/entities
- description: Detect sentiment in multiple documents.
  method: POST
  name: batch-detect-sentiment
  path: /v1/batch/sentiment
personas: []
provider_name: Amazon Comprehend
provider_slug: amazon-comprehend
search_terms:
- detect sentiment
- machine learning
- detect pii
- detect syntax
- pii detection.
- Application Developer
- detect language
- detect the dominant language of input text using amazon comprehend.
- list available document classifiers.
- entity recognition
- sentiment analysis
- detect sentiment in multiple documents.
- describe classifier
- analyze syntax and parts of speech in text using amazon comprehend.
- aws
- batch entity detection.
- detect named entities (people, places, organizations, dates) in text using amazon comprehend.
- get properties and status of a specific document classifier.
- extract key noun phrases from text using amazon comprehend.
- amazon
- analyze the sentiment of text (positive, negative, neutral, or mixed) using amazon comprehend.
- detect key phrases
- custom text classification.
- text analysis
- key phrase extraction.
- batch detect entities
- integrates comprehend nlp apis into applications for real-time text analysis.
- detect sentiment in text.
- list classifiers
- Data Scientist
- batch detect sentiment
- detect entities in multiple text documents in one batch call.
- named entity recognition.
- detect entities in multiple documents.
- list custom document classifiers trained in amazon comprehend.
- language detection.
- detect personally identifiable information (pii) entities in text using amazon comprehend.
- extract key phrases from text.
- uses comprehend for bulk text analysis, topic modeling, and custom model training.
- detect pii entities in text.
- nlp
- natural language processing
- sentiment analysis.
- detect named entities in text.
- end-to-end nlp analysis using entity, sentiment, key phrase, and pii detection.
- detect the dominant language of text.
- detect sentiment in multiple text documents in one batch call.
- batch sentiment analysis.
- detect entities
slug: nlp-analysis
source_filename: nlp-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Comprehend NLP Analysis\"\n  description: \"Workflow capability for natural language processing analysis including entity recognition, sentiment analysis, key phrase extraction, language detection, PII detection, and custom text classification. Used by data scientists and application developers to extract insights from unstructured text.\"\n  tags:\n    - Amazon\n    - AWS\n    - Natural Language Processing\n    - NLP\n    - Machine Learning\n    - Text Analysis\n    - Sentiment Analysis\n    - Entity Recognition\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: comprehend\n      location: ./shared/comprehend.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: nlp-analysis-api\n      description:\
  \ \"Unified REST API for Amazon Comprehend NLP analysis workflows.\"\n      resources:\n        - path: /v1/analyze/entities\n          name: entity-analysis\n          description: \"Named entity recognition.\"\n          operations:\n            - method: POST\n              name: detect-entities\n              description: \"Detect named entities in text.\"\n              call: \"comprehend.detect-entities\"\n              with:\n                text: \"rest.text\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analyze/sentiment\n          name: sentiment-analysis\n          description: \"Sentiment analysis.\"\n          operations:\n            - method: POST\n              name: detect-sentiment\n              description: \"Detect sentiment in text.\"\n              call: \"comprehend.detect-sentiment\"\n              with:\n                text: \"\
  rest.text\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analyze/key-phrases\n          name: key-phrase-extraction\n          description: \"Key phrase extraction.\"\n          operations:\n            - method: POST\n              name: detect-key-phrases\n              description: \"Extract key phrases from text.\"\n              call: \"comprehend.detect-key-phrases\"\n              with:\n                text: \"rest.text\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analyze/language\n          name: language-detection\n          description: \"Language detection.\"\n          operations:\n            - method: POST\n              name: detect-language\n              description: \"Detect the dominant language of text.\"\
  \n              call: \"comprehend.detect-dominant-language\"\n              with:\n                text: \"rest.text\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analyze/pii\n          name: pii-detection\n          description: \"PII detection.\"\n          operations:\n            - method: POST\n              name: detect-pii\n              description: \"Detect PII entities in text.\"\n              call: \"comprehend.detect-pii-entities\"\n              with:\n                text: \"rest.text\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/classify\n          name: text-classification\n          description: \"Custom text classification.\"\n          operations:\n            - method: GET\n              name: list-classifiers\n              description: \"List available\
  \ document classifiers.\"\n              call: \"comprehend.list-document-classifiers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batch/entities\n          name: batch-entity-analysis\n          description: \"Batch entity detection.\"\n          operations:\n            - method: POST\n              name: batch-detect-entities\n              description: \"Detect entities in multiple documents.\"\n              call: \"comprehend.batch-detect-entities\"\n              with:\n                text_list: \"rest.text_list\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batch/sentiment\n          name: batch-sentiment-analysis\n          description: \"Batch sentiment analysis.\"\n          operations:\n            - method: POST\n              name: batch-detect-sentiment\n     \
  \         description: \"Detect sentiment in multiple documents.\"\n              call: \"comprehend.batch-detect-sentiment\"\n              with:\n                text_list: \"rest.text_list\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: nlp-analysis-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Comprehend NLP text analysis.\"\n      tools:\n        - name: detect-entities\n          description: \"Detect named entities (people, places, organizations, dates) in text using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"comprehend.detect-entities\"\n          with:\n            text: \"tools.text\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: detect-sentiment\n          description: \"Analyze the sentiment of text (POSITIVE, NEGATIVE, NEUTRAL, or MIXED) using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"comprehend.detect-sentiment\"\n          with:\n            text: \"tools.text\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: detect-key-phrases\n          description: \"Extract key noun phrases from text using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"comprehend.detect-key-phrases\"\n          with:\n            text: \"tools.text\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: detect-language\n          description: \"Detect the dominant\
  \ language of input text using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"comprehend.detect-dominant-language\"\n          with:\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: detect-syntax\n          description: \"Analyze syntax and parts of speech in text using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"comprehend.detect-syntax\"\n          with:\n            text: \"tools.text\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: detect-pii\n          description: \"Detect personally identifiable information (PII) entities in text using Amazon Comprehend.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"comprehend.detect-pii-entities\"\n          with:\n            text: \"tools.text\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-detect-entities\n          description: \"Detect entities in multiple text documents in one batch call.\"\n          hints:\n            readOnly: true\n          call: \"comprehend.batch-detect-entities\"\n          with:\n            text_list: \"tools.text_list\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-detect-sentiment\n          description: \"Detect sentiment in multiple text documents in one batch call.\"\n          hints:\n            readOnly: true\n          call: \"comprehend.batch-detect-sentiment\"\n          with:\n            text_list: \"tools.text_list\"\n            language_code: \"tools.language_code\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-classifiers\n          description: \"List custom document classifiers trained in Amazon Comprehend.\"\n          hints:\n            readOnly: true\n          call: \"comprehend.list-document-classifiers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-classifier\n          description: \"Get properties and status of a specific document classifier.\"\n          hints:\n            readOnly: true\n          call: \"comprehend.describe-document-classifier\"\n          with:\n            classifier_arn: \"tools.classifier_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-comprehend/refs/heads/main/capabilities/nlp-analysis.yaml
tags:
- Amazon
- AWS
- Natural Language Processing
- NLP
- Machine Learning
- Text Analysis
- Sentiment Analysis
- Entity Recognition
tools:
- description: Detect named entities (people, places, organizations, dates) in text using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-entities
- description: Analyze the sentiment of text (POSITIVE, NEGATIVE, NEUTRAL, or MIXED) using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-sentiment
- description: Extract key noun phrases from text using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-key-phrases
- description: Detect the dominant language of input text using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-language
- description: Analyze syntax and parts of speech in text using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-syntax
- description: Detect personally identifiable information (PII) entities in text using Amazon Comprehend.
  hints:
    openWorld: true
    readOnly: true
  name: detect-pii
- description: Detect entities in multiple text documents in one batch call.
  hints:
    readOnly: true
  name: batch-detect-entities
- description: Detect sentiment in multiple text documents in one batch call.
  hints:
    readOnly: true
  name: batch-detect-sentiment
- description: List custom document classifiers trained in Amazon Comprehend.
  hints:
    readOnly: true
  name: list-classifiers
- description: Get properties and status of a specific document classifier.
  hints:
    readOnly: true
  name: describe-classifier
---
