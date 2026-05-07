---
categories: []
consumed_apis: []
description: The Detect Language API identifies the language of a given text with high accuracy, supporting 164 languages. It accepts single or batch detection requests and returns confidence scores and reliability indicators.
layout: capability
name: Detect Language API
operations:
- description: Detect language of text
  method: POST
  name: detectlanguage
  path: /detect
- description: Get account status
  method: GET
  name: getuserstatus
  path: /user/status
- description: List supported languages
  method: GET
  name: listlanguages
  path: /languages
personas: []
provider_name: Detect Language
provider_slug: detect-language
search_terms:
- translation
- getuserstatus
- detectlanguage
- detection
- languages
- get account status
- language
- listlanguages
- detect
- api
- detect language of text
- list supported languages
slug: detect-language-capability
source_filename: detect-language-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Detect Language API\n  description: The Detect Language API identifies the language of a given text with high accuracy, supporting 164 languages.\n    It accepts single or batch detection requests and returns confidence scores and reliability indicators.\n  tags:\n  - Detect\n  - Language\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: detect-language\n    baseUri: https://ws.detectlanguage.com/0.2\n    description: Detect Language API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DETECT_LANGUAGE_TOKEN}}'\n    resources:\n    - name: detect\n      path: /detect\n      operations:\n      - name: detectlanguage\n        method: POST\n        description: Detect language of text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-status\n      path: /user/status\n\
  \      operations:\n      - name: getuserstatus\n        method: GET\n        description: Get account status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: languages\n      path: /languages\n      operations:\n      - name: listlanguages\n        method: GET\n        description: List supported languages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: detect-language-rest\n    description: REST adapter for Detect Language API.\n    resources:\n    - path: /detect\n      name: detectlanguage\n      operations:\n      - method: POST\n        name: detectlanguage\n        description: Detect language of text\n        call: detect-language.detectlanguage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/status\n      name:\
  \ getuserstatus\n      operations:\n      - method: GET\n        name: getuserstatus\n        description: Get account status\n        call: detect-language.getuserstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /languages\n      name: listlanguages\n      operations:\n      - method: GET\n        name: listlanguages\n        description: List supported languages\n        call: detect-language.listlanguages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: detect-language-mcp\n    transport: http\n    description: MCP adapter for Detect Language API for AI agent use.\n    tools:\n    - name: detectlanguage\n      description: Detect language of text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: detect-language.detectlanguage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuserstatus\n\
  \      description: Get account status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: detect-language.getuserstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlanguages\n      description: List supported languages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: detect-language.listlanguages\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DETECT_LANGUAGE_TOKEN: DETECT_LANGUAGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/detect-language/refs/heads/main/capabilities/detect-language-capability.yaml
tags:
- Detect
- Language
- API
tools:
- description: Detect language of text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: detectlanguage
- description: Get account status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserstatus
- description: List supported languages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlanguages
---
