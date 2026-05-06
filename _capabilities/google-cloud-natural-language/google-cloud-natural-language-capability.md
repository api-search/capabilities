---
categories: []
consumed_apis: []
description: Provides natural language understanding technologies to extract insights from unstructured text including sentiment, entities, and syntax.
layout: capability
name: Google Cloud Natural Language API
operations:
- description: Google Cloud Natural Language Analyze sentiment
  method: POST
  name: analyzesentiment
  path: /documents:analyzeSentiment
- description: Google Cloud Natural Language Analyze entities
  method: POST
  name: analyzeentities
  path: /documents:analyzeEntities
- description: Google Cloud Natural Language Classify text
  method: POST
  name: classifytext
  path: /documents:classifyText
- description: Google Cloud Natural Language Analyze syntax
  method: POST
  name: analyzesyntax
  path: /documents:analyzeSyntax
- description: Google Cloud Natural Language Annotate text
  method: POST
  name: annotatetext
  path: /documents:annotateText
personas: []
provider_name: Google Cloud Natural Language
provider_slug: google-cloud-natural-language
search_terms:
- sentiment analysis
- classifytext
- google cloud natural language classify text
- google cloud natural language annotate text
- natural language processing
- google cloud natural language analyze sentiment
- annotatetext
- cloud
- google
- analyzesyntax
- natural
- google cloud natural language analyze syntax
- google cloud natural language analyze entities
- machine learning
- language
- api
- text analysis
- analyzesentiment
- google cloud
- analyzeentities
- entity recognition
slug: google-cloud-natural-language-capability
source_filename: google-cloud-natural-language-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Natural Language API\n  description: Provides natural language understanding technologies to extract insights from unstructured text including sentiment,\n    entities, and syntax.\n  tags:\n  - Google\n  - Cloud\n  - Natural\n  - Language\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-natural-language\n    baseUri: https://language.googleapis.com/v1\n    description: Google Cloud Natural Language API HTTP API.\n    resources:\n    - name: documents-analyzesentiment\n      path: /documents:analyzeSentiment\n      operations:\n      - name: analyzesentiment\n        method: POST\n        description: Google Cloud Natural Language Analyze sentiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-analyzeentities\n      path: /documents:analyzeEntities\n\
  \      operations:\n      - name: analyzeentities\n        method: POST\n        description: Google Cloud Natural Language Analyze entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-classifytext\n      path: /documents:classifyText\n      operations:\n      - name: classifytext\n        method: POST\n        description: Google Cloud Natural Language Classify text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-analyzesyntax\n      path: /documents:analyzeSyntax\n      operations:\n      - name: analyzesyntax\n        method: POST\n        description: Google Cloud Natural Language Analyze syntax\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-annotatetext\n      path: /documents:annotateText\n\
  \      operations:\n      - name: annotatetext\n        method: POST\n        description: Google Cloud Natural Language Annotate text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-natural-language-rest\n    description: REST adapter for Google Cloud Natural Language API.\n    resources:\n    - path: /documents:analyzeSentiment\n      name: analyzesentiment\n      operations:\n      - method: POST\n        name: analyzesentiment\n        description: Google Cloud Natural Language Analyze sentiment\n        call: google-cloud-natural-language.analyzesentiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents:analyzeEntities\n      name: analyzeentities\n      operations:\n      - method: POST\n        name: analyzeentities\n        description: Google Cloud Natural Language Analyze entities\n\
  \        call: google-cloud-natural-language.analyzeentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents:classifyText\n      name: classifytext\n      operations:\n      - method: POST\n        name: classifytext\n        description: Google Cloud Natural Language Classify text\n        call: google-cloud-natural-language.classifytext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents:analyzeSyntax\n      name: analyzesyntax\n      operations:\n      - method: POST\n        name: analyzesyntax\n        description: Google Cloud Natural Language Analyze syntax\n        call: google-cloud-natural-language.analyzesyntax\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents:annotateText\n      name: annotatetext\n      operations:\n      - method: POST\n        name: annotatetext\n        description: Google Cloud Natural Language Annotate text\n\
  \        call: google-cloud-natural-language.annotatetext\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-natural-language-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Natural Language API for AI agent use.\n    tools:\n    - name: analyzesentiment\n      description: Google Cloud Natural Language Analyze sentiment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-natural-language.analyzesentiment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analyzeentities\n      description: Google Cloud Natural Language Analyze entities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-natural-language.analyzeentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classifytext\n   \
  \   description: Google Cloud Natural Language Classify text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-natural-language.classifytext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analyzesyntax\n      description: Google Cloud Natural Language Analyze syntax\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-natural-language.analyzesyntax\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: annotatetext\n      description: Google Cloud Natural Language Annotate text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-natural-language.annotatetext\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-natural-language/refs/heads/main/capabilities/google-cloud-natural-language-capability.yaml
tags:
- Google
- Cloud
- Natural
- Language
- API
tools:
- description: Google Cloud Natural Language Analyze sentiment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzesentiment
- description: Google Cloud Natural Language Analyze entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzeentities
- description: Google Cloud Natural Language Classify text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: classifytext
- description: Google Cloud Natural Language Analyze syntax
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzesyntax
- description: Google Cloud Natural Language Annotate text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: annotatetext
---
