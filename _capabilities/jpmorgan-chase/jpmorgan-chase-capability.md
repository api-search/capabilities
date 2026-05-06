---
categories: []
consumed_apis: []
description: JPMorgan Chase provides developer APIs for banking services including payments, treasury, trade finance, and market data. The APIs enable corporate clients and fintech partners to integrate banking capabilities into their applications.
layout: capability
name: JPMorgan Chase API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- finance
- get api status
- getstatus
- chase
- api
- treasury
- jpmorgan
- banking
- embedded finance
- financial services
- payments
slug: jpmorgan-chase-capability
source_filename: jpmorgan-chase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JPMorgan Chase API\n  description: JPMorgan Chase provides developer APIs for banking services including payments, treasury, trade finance, and\n    market data. The APIs enable corporate clients and fintech partners to integrate banking capabilities into their applications.\n  tags:\n  - Jpmorgan\n  - Chase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jpmorgan-chase\n    baseUri: https://api.jpmorgan.com\n    description: JPMorgan Chase API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JPMORGAN_CHASE_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ jpmorgan-chase-rest\n    description: REST adapter for JPMorgan Chase API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: jpmorgan-chase.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jpmorgan-chase-mcp\n    transport: http\n    description: MCP adapter for JPMorgan Chase API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jpmorgan-chase.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JPMORGAN_CHASE_TOKEN: JPMORGAN_CHASE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jpmorgan-chase/refs/heads/main/capabilities/jpmorgan-chase-capability.yaml
tags:
- Jpmorgan
- Chase
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
