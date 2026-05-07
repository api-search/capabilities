---
categories: []
consumed_apis: []
description: The Progressive Auto Quote API enables partners to embed auto insurance quoting capabilities directly into their applications. Partners can return estimated auto insurance rates with customizable options including SDK and headless API integration. The API supports both non-production and production environments for testing and live deployments.
layout: capability
name: Progressive Auto Quote API
operations:
- description: List quotes
  method: GET
  name: listquotes
  path: /quotes
- description: Create a quote
  method: POST
  name: createquote
  path: /quotes
- description: List vehicles
  method: GET
  name: listvehicles
  path: /vehicles
- description: List drivers
  method: GET
  name: listdrivers
  path: /drivers
personas: []
provider_name: Progressive
provider_slug: progressive
search_terms:
- progressive
- quoting
- list drivers
- auto insurance
- list quotes
- listquotes
- createquote
- commercial insurance
- embedded insurance
- insurance
- api
- listvehicles
- list vehicles
- create a quote
- listdrivers
slug: progressive-capability
source_filename: progressive-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Progressive Auto Quote API\n  description: The Progressive Auto Quote API enables partners to embed auto insurance quoting capabilities directly into\n    their applications. Partners can return estimated auto insurance rates with customizable options including SDK and headless\n    API integration. The API supports both non-production and production environments for testing and live deployments.\n  tags:\n  - Progressive\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: progressive\n    baseUri: https://api.progressive.com\n    description: Progressive Auto Quote API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PROGRESSIVE_TOKEN}}'\n    resources:\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: listquotes\n        method: GET\n        description: List quotes\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createquote\n        method: POST\n        description: Create a quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles\n      path: /vehicles\n      operations:\n      - name: listvehicles\n        method: GET\n        description: List vehicles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drivers\n      path: /drivers\n      operations:\n      - name: listdrivers\n        method: GET\n        description: List drivers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: progressive-rest\n    description: REST adapter for Progressive Auto Quote API.\n    resources:\n    - path: /quotes\n\
  \      name: listquotes\n      operations:\n      - method: GET\n        name: listquotes\n        description: List quotes\n        call: progressive.listquotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quotes\n      name: createquote\n      operations:\n      - method: POST\n        name: createquote\n        description: Create a quote\n        call: progressive.createquote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vehicles\n      name: listvehicles\n      operations:\n      - method: GET\n        name: listvehicles\n        description: List vehicles\n        call: progressive.listvehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /drivers\n      name: listdrivers\n      operations:\n      - method: GET\n        name: listdrivers\n        description: List drivers\n        call: progressive.listdrivers\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: progressive-mcp\n    transport: http\n    description: MCP adapter for Progressive Auto Quote API for AI agent use.\n    tools:\n    - name: listquotes\n      description: List quotes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: progressive.listquotes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createquote\n      description: Create a quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: progressive.createquote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvehicles\n      description: List vehicles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: progressive.listvehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdrivers\n      description:\
  \ List drivers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: progressive.listdrivers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PROGRESSIVE_TOKEN: PROGRESSIVE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/progressive/refs/heads/main/capabilities/progressive-capability.yaml
tags:
- Progressive
- API
tools:
- description: List quotes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listquotes
- description: Create a quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createquote
- description: List vehicles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvehicles
- description: List drivers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdrivers
---
