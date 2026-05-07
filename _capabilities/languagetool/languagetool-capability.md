---
categories: []
consumed_apis: []
description: LanguageTool checks texts for style and grammar issues. The HTTP API provides programmatic access to grammar checking, language detection, and personal dictionary management.
layout: capability
name: LanguageTool HTTP API
operations:
- description: Check text for grammar and style issues
  method: POST
  name: checktext
  path: /check
- description: List supported languages
  method: GET
  name: listlanguages
  path: /languages
- description: List personal dictionary words
  method: GET
  name: listwords
  path: /words
- description: Add a word to a personal dictionary
  method: POST
  name: addword
  path: /words/add
- description: Delete a word from a personal dictionary
  method: POST
  name: deleteword
  path: /words/delete
personas: []
provider_name: LanguageTool
provider_slug: languagetool
search_terms:
- addword
- listwords
- add a word to a personal dictionary
- grammar
- style check
- text analysis
- delete a word from a personal dictionary
- proofreading
- spell check
- languagetool
- listlanguages
- check text for grammar and style issues
- list personal dictionary words
- api
- deleteword
- language
- checktext
- list supported languages
slug: languagetool-capability
source_filename: languagetool-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LanguageTool HTTP API\n  description: LanguageTool checks texts for style and grammar issues. The HTTP API provides programmatic access to grammar\n    checking, language detection, and personal dictionary management.\n  tags:\n  - Languagetool\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: languagetool\n    baseUri: https://api.languagetool.org/v2\n    description: LanguageTool HTTP API HTTP API.\n    resources:\n    - name: check\n      path: /check\n      operations:\n      - name: checktext\n        method: POST\n        description: Check text for grammar and style issues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: languages\n      path: /languages\n      operations:\n      - name: listlanguages\n        method: GET\n        description: List supported languages\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: words\n      path: /words\n      operations:\n      - name: listwords\n        method: GET\n        description: List personal dictionary words\n        inputParameters:\n        - name: username\n          in: query\n          type: string\n          required: true\n        - name: apiKey\n          in: query\n          type: string\n          required: true\n        - name: dicts\n          in: query\n          type: string\n          description: Comma-separated list of dictionary names.\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: words-add\n      path: /words/add\n      operations:\n      - name: addword\n        method:\
  \ POST\n        description: Add a word to a personal dictionary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: words-delete\n      path: /words/delete\n      operations:\n      - name: deleteword\n        method: POST\n        description: Delete a word from a personal dictionary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: languagetool-rest\n    description: REST adapter for LanguageTool HTTP API.\n    resources:\n    - path: /check\n      name: checktext\n      operations:\n      - method: POST\n        name: checktext\n        description: Check text for grammar and style issues\n        call: languagetool.checktext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /languages\n      name: listlanguages\n      operations:\n\
  \      - method: GET\n        name: listlanguages\n        description: List supported languages\n        call: languagetool.listlanguages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /words\n      name: listwords\n      operations:\n      - method: GET\n        name: listwords\n        description: List personal dictionary words\n        call: languagetool.listwords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /words/add\n      name: addword\n      operations:\n      - method: POST\n        name: addword\n        description: Add a word to a personal dictionary\n        call: languagetool.addword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /words/delete\n      name: deleteword\n      operations:\n      - method: POST\n        name: deleteword\n        description: Delete a word from a personal dictionary\n        call: languagetool.deleteword\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: languagetool-mcp\n    transport: http\n    description: MCP adapter for LanguageTool HTTP API for AI agent use.\n    tools:\n    - name: checktext\n      description: Check text for grammar and style issues\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: languagetool.checktext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlanguages\n      description: List supported languages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: languagetool.listlanguages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwords\n      description: List personal dictionary words\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: languagetool.listwords\n      with:\n        username:\
  \ tools.username\n        apiKey: tools.apiKey\n        dicts: tools.dicts\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: username\n        type: string\n        description: username\n        required: true\n      - name: apiKey\n        type: string\n        description: apiKey\n        required: true\n      - name: dicts\n        type: string\n        description: Comma-separated list of dictionary names.\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addword\n      description: Add a word to a personal dictionary\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: languagetool.addword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteword\n      description: Delete\
  \ a word from a personal dictionary\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: languagetool.deleteword\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/languagetool/refs/heads/main/capabilities/languagetool-capability.yaml
tags:
- Languagetool
- API
tools:
- description: Check text for grammar and style issues
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checktext
- description: List supported languages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlanguages
- description: List personal dictionary words
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwords
- description: Add a word to a personal dictionary
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addword
- description: Delete a word from a personal dictionary
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteword
---
