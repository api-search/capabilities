---
categories: []
consumed_apis: []
description: APIs for vision, speech, language, and decision-making AI capabilities including Computer Vision, Text Analytics, and Translator services.
layout: capability
name: Microsoft Azure Cognitive Services API
operations:
- description: Microsoft Analyze image
  method: POST
  name: analyzeimage
  path: /vision/v3.2/analyze
- description: Microsoft Optical character recognition
  method: POST
  name: recognizetext
  path: /vision/v3.2/ocr
- description: Microsoft Analyze sentiment
  method: POST
  name: analyzesentiment
  path: /text/analytics/v3.1/sentiment
- description: Microsoft Recognize named entities
  method: POST
  name: recognizeentities
  path: /text/analytics/v3.1/entities/recognition/general
- description: Microsoft Extract key phrases
  method: POST
  name: extractkeyphrases
  path: /text/analytics/v3.1/keyPhrases
- description: Microsoft Translate text
  method: POST
  name: translatetext
  path: /translate
- description: Microsoft Get supported languages
  method: GET
  name: getlanguages
  path: /languages
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- analyzeimage
- microsoft get supported languages
- analyzesentiment
- microsoft translate text
- recognizetext
- api
- extractkeyphrases
- getlanguages
- microsoft optical character recognition
- microsoft recognize named entities
- microsoft extract key phrases
- translatetext
- microsoft
- microsoft analyze sentiment
- recognizeentities
- microsoft analyze image
slug: microsoft-capability
source_filename: microsoft-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Azure Cognitive Services API\n  description: APIs for vision, speech, language, and decision-making AI capabilities including Computer Vision, Text Analytics,\n    and Translator services.\n  tags:\n  - Microsoft\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft\n    baseUri: https://eastus.api.cognitive.microsoft.com\n    description: Microsoft Azure Cognitive Services API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Ocp-Apim-Subscription-Key\n      value: '{{MICROSOFT_TOKEN}}'\n    resources:\n    - name: vision-v3-2-analyze\n      path: /vision/v3.2/analyze\n      operations:\n      - name: analyzeimage\n        method: POST\n        description: Microsoft Analyze image\n        inputParameters:\n        - name: visualFeatures\n          in: query\n          type: string\n          description: Visual features\
  \ to analyze\n        - name: language\n          in: query\n          type: string\n          description: Language for response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vision-v3-2-ocr\n      path: /vision/v3.2/ocr\n      operations:\n      - name: recognizetext\n        method: POST\n        description: Microsoft Optical character recognition\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          description: BCP-47 language code of the text to detect\n        - name: detectOrientation\n          in: query\n          type: boolean\n          description: Whether to detect text orientation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: text-analytics-v3-1-sentiment\n      path: /text/analytics/v3.1/sentiment\n      operations:\n      - name:\
  \ analyzesentiment\n        method: POST\n        description: Microsoft Analyze sentiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: text-analytics-v3-1-entities-recognition-general\n      path: /text/analytics/v3.1/entities/recognition/general\n      operations:\n      - name: recognizeentities\n        method: POST\n        description: Microsoft Recognize named entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: text-analytics-v3-1-keyphrases\n      path: /text/analytics/v3.1/keyPhrases\n      operations:\n      - name: extractkeyphrases\n        method: POST\n        description: Microsoft Extract key phrases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: translate\n      path: /translate\n      operations:\n\
  \      - name: translatetext\n        method: POST\n        description: Microsoft Translate text\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: array\n          required: true\n          description: Target language codes\n        - name: from\n          in: query\n          type: string\n          description: Source language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: languages\n      path: /languages\n      operations:\n      - name: getlanguages\n        method: GET\n        description: Microsoft Get supported languages\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        - name: scope\n          in: query\n          type: string\n          description: Comma-separated\
  \ group of language names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-rest\n    description: REST adapter for Microsoft Azure Cognitive Services API.\n    resources:\n    - path: /vision/v3.2/analyze\n      name: analyzeimage\n      operations:\n      - method: POST\n        name: analyzeimage\n        description: Microsoft Analyze image\n        call: microsoft.analyzeimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vision/v3.2/ocr\n      name: recognizetext\n      operations:\n      - method: POST\n        name: recognizetext\n        description: Microsoft Optical character recognition\n        call: microsoft.recognizetext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /text/analytics/v3.1/sentiment\n      name: analyzesentiment\n      operations:\n\
  \      - method: POST\n        name: analyzesentiment\n        description: Microsoft Analyze sentiment\n        call: microsoft.analyzesentiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /text/analytics/v3.1/entities/recognition/general\n      name: recognizeentities\n      operations:\n      - method: POST\n        name: recognizeentities\n        description: Microsoft Recognize named entities\n        call: microsoft.recognizeentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /text/analytics/v3.1/keyPhrases\n      name: extractkeyphrases\n      operations:\n      - method: POST\n        name: extractkeyphrases\n        description: Microsoft Extract key phrases\n        call: microsoft.extractkeyphrases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /translate\n      name: translatetext\n      operations:\n      - method: POST\n        name: translatetext\n\
  \        description: Microsoft Translate text\n        call: microsoft.translatetext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /languages\n      name: getlanguages\n      operations:\n      - method: GET\n        name: getlanguages\n        description: Microsoft Get supported languages\n        call: microsoft.getlanguages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-mcp\n    transport: http\n    description: MCP adapter for Microsoft Azure Cognitive Services API for AI agent use.\n    tools:\n    - name: analyzeimage\n      description: Microsoft Analyze image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft.analyzeimage\n      with:\n        visualFeatures: tools.visualFeatures\n        language: tools.language\n      inputParameters:\n      - name: visualFeatures\n        type: string\n\
  \        description: Visual features to analyze\n      - name: language\n        type: string\n        description: Language for response\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recognizetext\n      description: Microsoft Optical character recognition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft.recognizetext\n      with:\n        language: tools.language\n        detectOrientation: tools.detectOrientation\n      inputParameters:\n      - name: language\n        type: string\n        description: BCP-47 language code of the text to detect\n      - name: detectOrientation\n        type: boolean\n        description: Whether to detect text orientation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analyzesentiment\n      description: Microsoft Analyze sentiment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: microsoft.analyzesentiment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recognizeentities\n      description: Microsoft Recognize named entities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft.recognizeentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extractkeyphrases\n      description: Microsoft Extract key phrases\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft.extractkeyphrases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: translatetext\n      description: Microsoft Translate text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft.translatetext\n      with:\n        api-version: tools.api-version\n        to: tools.to\n        from: tools.from\n     \
  \ inputParameters:\n      - name: api-version\n        type: string\n        description: api-version\n        required: true\n      - name: to\n        type: array\n        description: Target language codes\n        required: true\n      - name: from\n        type: string\n        description: Source language code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlanguages\n      description: Microsoft Get supported languages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft.getlanguages\n      with:\n        api-version: tools.api-version\n        scope: tools.scope\n      inputParameters:\n      - name: api-version\n        type: string\n        description: api-version\n        required: true\n      - name: scope\n        type: string\n        description: Comma-separated group of language names\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    MICROSOFT_TOKEN: MICROSOFT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft/refs/heads/main/capabilities/microsoft-capability.yaml
tags:
- Microsoft
- API
tools:
- description: Microsoft Analyze image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzeimage
- description: Microsoft Optical character recognition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recognizetext
- description: Microsoft Analyze sentiment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzesentiment
- description: Microsoft Recognize named entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recognizeentities
- description: Microsoft Extract key phrases
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: extractkeyphrases
- description: Microsoft Translate text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: translatetext
- description: Microsoft Get supported languages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlanguages
---
