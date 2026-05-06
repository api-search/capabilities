---
categories: []
consumed_apis: []
description: The Google Cloud Translation API provides programmatic access to Google's neural machine translation technology. It enables developers to dynamically translate text between thousands of language pairs, detect the language of source text, and retrieve a list of supported languages. The API supports both basic (v2) and advanced (v3) translation capabilities including batch translation, custom models, and glossaries.
layout: capability
name: Google Cloud Translation API
operations:
- description: Google Cloud Translation API Translate Text
  method: POST
  name: translatetext
  path: /language/translate/v2
- description: Google Cloud Translation API Detect Language
  method: POST
  name: detectlanguage
  path: /language/translate/v2/detect
- description: Google Cloud Translation API List Supported Languages
  method: GET
  name: listlanguages
  path: /language/translate/v2/languages
personas: []
provider_name: Google Cloud Translation API
provider_slug: google-translate
search_terms:
- detectlanguage
- google cloud translation api detect language
- internationalization
- natural language processing
- google
- api
- machine translation
- translation
- google cloud translation api list supported languages
- language detection
- translatetext
- google cloud
- localization
- listlanguages
- google cloud translation api translate text
- translate
slug: google-translate-capability
source_filename: google-translate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Translation API\n  description: The Google Cloud Translation API provides programmatic access to Google's neural machine translation technology.\n    It enables developers to dynamically translate text between thousands of language pairs, detect the language of source\n    text, and retrieve a list of supported languages. The API supports both basic (v2) and advanced (v3) translation capabilities\n    including batch translation, custom models, and glossaries.\n  tags:\n  - Google\n  - Translate\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-translate\n    baseUri: https://translation.googleapis.com\n    description: Google Cloud Translation API HTTP API.\n    resources:\n    - name: language-translate-v2\n      path: /language/translate/v2\n      operations:\n      - name: translatetext\n        method: POST\n        description: Google Cloud Translation\
  \ API Translate Text\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: language-translate-v2-detect\n      path: /language/translate/v2/detect\n      operations:\n      - name: detectlanguage\n        method: POST\n        description: Google Cloud Translation API Detect Language\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: language-translate-v2-languages\n      path: /language/translate/v2/languages\n      operations:\n      - name: listlanguages\n        method: GET\n  \
  \      description: Google Cloud Translation API List Supported Languages\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        - name: target\n          in: query\n          type: string\n          description: The language to use to return localized, human readable names of supported languages.\n        - name: model\n          in: query\n          type: string\n          description: The translation model. Can be either base for the Phrase-Based Machine Translation model, or nmt for\n            the Neural Machine Translation model.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-translate-rest\n    description: REST adapter for Google Cloud Translation API.\n    resources:\n    - path: /language/translate/v2\n      name:\
  \ translatetext\n      operations:\n      - method: POST\n        name: translatetext\n        description: Google Cloud Translation API Translate Text\n        call: google-translate.translatetext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /language/translate/v2/detect\n      name: detectlanguage\n      operations:\n      - method: POST\n        name: detectlanguage\n        description: Google Cloud Translation API Detect Language\n        call: google-translate.detectlanguage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /language/translate/v2/languages\n      name: listlanguages\n      operations:\n      - method: GET\n        name: listlanguages\n        description: Google Cloud Translation API List Supported Languages\n        call: google-translate.listlanguages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-translate-mcp\n\
  \    transport: http\n    description: MCP adapter for Google Cloud Translation API for AI agent use.\n    tools:\n    - name: translatetext\n      description: Google Cloud Translation API Translate Text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-translate.translatetext\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: API key for authentication\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detectlanguage\n      description: Google Cloud Translation API Detect Language\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-translate.detectlanguage\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: API key for authentication\n        required: true\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlanguages\n      description: Google Cloud Translation API List Supported Languages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-translate.listlanguages\n      with:\n        key: tools.key\n        target: tools.target\n        model: tools.model\n      inputParameters:\n      - name: key\n        type: string\n        description: API key for authentication\n        required: true\n      - name: target\n        type: string\n        description: The language to use to return localized, human readable names of supported languages.\n      - name: model\n        type: string\n        description: The translation model. Can be either base for the Phrase-Based Machine Translation model, or nmt for\n          the Neural Machine Translation model.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-translate/refs/heads/main/capabilities/google-translate-capability.yaml
tags:
- Google
- Translate
- API
tools:
- description: Google Cloud Translation API Translate Text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: translatetext
- description: Google Cloud Translation API Detect Language
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: detectlanguage
- description: Google Cloud Translation API List Supported Languages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlanguages
---
