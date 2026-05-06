---
categories: []
consumed_apis: []
description: The Poe API is a developer platform by Quora that provides access to hundreds of AI models and bots through a single OpenAI-compatible interface. Developers can call Chat Completions and Responses endpoints, list available models, and monitor point usage and balance using a single API key issued at https://poe.com/api/keys. The API supports text, image, video, and audio generation modalities and is rate-limited to 500 requests per minute.
layout: capability
name: Poe API
operations:
- description: Create a chat completion
  method: POST
  name: createchatcompletion
  path: /chat/completions
- description: Create a response
  method: POST
  name: createresponse
  path: /responses
- description: List models
  method: GET
  name: listmodels
  path: /models
- description: Get current point balance
  method: GET
  name: getcurrentbalance
  path: /usage/current_balance
- description: Get points usage history
  method: GET
  name: getpointshistory
  path: /usage/points_history
personas: []
provider_name: Quora
provider_slug: quora
search_terms:
- create a response
- getpointshistory
- q&a
- quora
- getcurrentbalance
- create a chat completion
- api
- get current point balance
- get points usage history
- list models
- listmodels
- community
- knowledge
- createchatcompletion
- createresponse
slug: quora-capability
source_filename: quora-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Poe API\n  description: The Poe API is a developer platform by Quora that provides access to hundreds of AI models and bots through\n    a single OpenAI-compatible interface. Developers can call Chat Completions and Responses endpoints, list available models,\n    and monitor point usage and balance using a single API key issued at https://poe.com/api/keys. The API supports text,\n    image, video, and audio generation modalities and is rate-limited to 500 requests per minute.\n  tags:\n  - Quora\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quora\n    baseUri: https://api.poe.com/v1\n    description: Poe API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QUORA_TOKEN}}'\n    resources:\n    - name: chat-completions\n      path: /chat/completions\n      operations:\n      - name: createchatcompletion\n        method: POST\n        description: Create\
  \ a chat completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: responses\n      path: /responses\n      operations:\n      - name: createresponse\n        method: POST\n        description: Create a response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      operations:\n      - name: listmodels\n        method: GET\n        description: List models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usage-current-balance\n      path: /usage/current_balance\n      operations:\n      - name: getcurrentbalance\n        method: GET\n        description: Get current point balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: usage-points-history\n      path: /usage/points_history\n      operations:\n      - name: getpointshistory\n        method: GET\n        description: Get points usage history\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of entries to return.\n        - name: starting_after\n          in: query\n          type: string\n          description: Cursor (`query_id`) to paginate after.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quora-rest\n    description: REST adapter for Poe API.\n    resources:\n    - path: /chat/completions\n      name: createchatcompletion\n      operations:\n      - method: POST\n        name: createchatcompletion\n        description: Create a chat completion\n        call: quora.createchatcompletion\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /responses\n      name: createresponse\n      operations:\n      - method: POST\n        name: createresponse\n        description: Create a response\n        call: quora.createresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: List models\n        call: quora.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usage/current_balance\n      name: getcurrentbalance\n      operations:\n      - method: GET\n        name: getcurrentbalance\n        description: Get current point balance\n        call: quora.getcurrentbalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usage/points_history\n      name: getpointshistory\n      operations:\n      - method: GET\n\
  \        name: getpointshistory\n        description: Get points usage history\n        call: quora.getpointshistory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quora-mcp\n    transport: http\n    description: MCP adapter for Poe API for AI agent use.\n    tools:\n    - name: createchatcompletion\n      description: Create a chat completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quora.createchatcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createresponse\n      description: Create a response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quora.createresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodels\n      description: List models\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: quora.listmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentbalance\n      description: Get current point balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quora.getcurrentbalance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpointshistory\n      description: Get points usage history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quora.getpointshistory\n      with:\n        limit: tools.limit\n        starting_after: tools.starting_after\n      inputParameters:\n      - name: limit\n        type: integer\n        description: Maximum number of entries to return.\n      - name: starting_after\n        type: string\n        description: Cursor (`query_id`) to paginate after.\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\nbinds:\n- namespace: env\n  keys:\n    QUORA_TOKEN: QUORA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quora/refs/heads/main/capabilities/quora-capability.yaml
tags:
- Quora
- API
tools:
- description: Create a chat completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchatcompletion
- description: Create a response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresponse
- description: List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Get current point balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentbalance
- description: Get points usage history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpointshistory
---
