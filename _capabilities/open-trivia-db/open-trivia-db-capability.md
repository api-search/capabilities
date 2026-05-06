---
categories: []
consumed_apis: []
description: Free JSON API providing trivia questions across multiple categories, difficulties, and types. No API key is required. Supports session tokens to avoid duplicate questions across requests, multiple response encodings, and rate limiting of one request per IP every 5 seconds.
layout: capability
name: Open Trivia DB API
operations:
- description: Retrieve trivia questions
  method: GET
  name: getquestions
  path: /api.php
- description: List trivia categories
  method: GET
  name: getcategories
  path: /api_category.php
- description: Question count for category
  method: GET
  name: getcategorycount
  path: /api_count.php
- description: Global question counts
  method: GET
  name: getglobalcount
  path: /api_count_global.php
- description: Manage session tokens
  method: GET
  name: managetoken
  path: /api_token.php
personas: []
provider_name: Open Trivia DB
provider_slug: open-trivia-db
search_terms:
- trivia
- questions
- getcategories
- getglobalcount
- api
- db
- open
- global question counts
- list trivia categories
- managetoken
- question count for category
- manage session tokens
- retrieve trivia questions
- getcategorycount
- games
- free
- getquestions
slug: open-trivia-db-capability
source_filename: open-trivia-db-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Open Trivia DB API\n  description: Free JSON API providing trivia questions across multiple categories, difficulties, and types. No API key is\n    required. Supports session tokens to avoid duplicate questions across requests, multiple response encodings, and rate\n    limiting of one request per IP every 5 seconds.\n  tags:\n  - Open\n  - Trivia\n  - Db\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-trivia-db\n    baseUri: https://opentdb.com\n    description: Open Trivia DB API HTTP API.\n    resources:\n    - name: api-php\n      path: /api.php\n      operations:\n      - name: getquestions\n        method: GET\n        description: Retrieve trivia questions\n        inputParameters:\n        - name: amount\n          in: query\n          type: integer\n          required: true\n          description: Number of questions to return (1-50).\n        - name: category\n\
  \          in: query\n          type: integer\n          description: Category ID to filter by. Omit for any category.\n        - name: difficulty\n          in: query\n          type: string\n          description: Question difficulty.\n        - name: type\n          in: query\n          type: string\n          description: Question type.\n        - name: encode\n          in: query\n          type: string\n          description: Response encoding format.\n        - name: token\n          in: query\n          type: string\n          description: Session token to avoid duplicate questions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-category-php\n      path: /api_category.php\n      operations:\n      - name: getcategories\n        method: GET\n        description: List trivia categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-count-php\n      path: /api_count.php\n      operations:\n      - name: getcategorycount\n        method: GET\n        description: Question count for category\n        inputParameters:\n        - name: category\n          in: query\n          type: integer\n          required: true\n          description: Category ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-count-global-php\n      path: /api_count_global.php\n      operations:\n      - name: getglobalcount\n        method: GET\n        description: Global question counts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-token-php\n      path: /api_token.php\n      operations:\n      - name: managetoken\n        method: GET\n        description: Manage session tokens\n        inputParameters:\n        -\
  \ name: command\n          in: query\n          type: string\n          required: true\n          description: Token operation.\n        - name: token\n          in: query\n          type: string\n          description: Existing token (required when command is reset).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-trivia-db-rest\n    description: REST adapter for Open Trivia DB API.\n    resources:\n    - path: /api.php\n      name: getquestions\n      operations:\n      - method: GET\n        name: getquestions\n        description: Retrieve trivia questions\n        call: open-trivia-db.getquestions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_category.php\n      name: getcategories\n      operations:\n      - method: GET\n        name: getcategories\n        description: List trivia categories\n\
  \        call: open-trivia-db.getcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_count.php\n      name: getcategorycount\n      operations:\n      - method: GET\n        name: getcategorycount\n        description: Question count for category\n        call: open-trivia-db.getcategorycount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_count_global.php\n      name: getglobalcount\n      operations:\n      - method: GET\n        name: getglobalcount\n        description: Global question counts\n        call: open-trivia-db.getglobalcount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_token.php\n      name: managetoken\n      operations:\n      - method: GET\n        name: managetoken\n        description: Manage session tokens\n        call: open-trivia-db.managetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  -\
  \ type: mcp\n    port: 9090\n    namespace: open-trivia-db-mcp\n    transport: http\n    description: MCP adapter for Open Trivia DB API for AI agent use.\n    tools:\n    - name: getquestions\n      description: Retrieve trivia questions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-trivia-db.getquestions\n      with:\n        amount: tools.amount\n        category: tools.category\n        difficulty: tools.difficulty\n        type: tools.type\n        encode: tools.encode\n        token: tools.token\n      inputParameters:\n      - name: amount\n        type: integer\n        description: Number of questions to return (1-50).\n        required: true\n      - name: category\n        type: integer\n        description: Category ID to filter by. Omit for any category.\n      - name: difficulty\n        type: string\n        description: Question difficulty.\n      - name: type\n        type: string\n        description: Question\
  \ type.\n      - name: encode\n        type: string\n        description: Response encoding format.\n      - name: token\n        type: string\n        description: Session token to avoid duplicate questions.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategories\n      description: List trivia categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-trivia-db.getcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategorycount\n      description: Question count for category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-trivia-db.getcategorycount\n      with:\n        category: tools.category\n      inputParameters:\n      - name: category\n        type: integer\n        description: Category ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getglobalcount\n      description: Global question counts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-trivia-db.getglobalcount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: managetoken\n      description: Manage session tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-trivia-db.managetoken\n      with:\n        command: tools.command\n        token: tools.token\n      inputParameters:\n      - name: command\n        type: string\n        description: Token operation.\n        required: true\n      - name: token\n        type: string\n        description: Existing token (required when command is reset).\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-trivia-db/refs/heads/main/capabilities/open-trivia-db-capability.yaml
tags:
- Open
- Trivia
- Db
- API
tools:
- description: Retrieve trivia questions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquestions
- description: List trivia categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategories
- description: Question count for category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategorycount
- description: Global question counts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getglobalcount
- description: Manage session tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: managetoken
---
