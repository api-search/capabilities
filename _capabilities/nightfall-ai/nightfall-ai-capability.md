---
categories: []
consumed_apis: []
description: One unified platform for protecting sensitive data across SaaS, GenAI, email, and endpoints.
layout: capability
name: Nightfall AI
operations:
- description: Nightfall AI Scan for sensitive information in your data
  method: POST
  name: scanpayloadv2
  path: /v2/scan
personas: []
provider_name: Nightfall AI
provider_slug: nightfall-ai
search_terms:
- privacy
- nightfall ai scan for sensitive information in your data
- scanpayloadv2
- artificial intelligence
- ai
- sensitive data
- api
- nightfall
slug: nightfall-ai-capability
source_filename: nightfall-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nightfall AI\n  description: One unified platform for protecting sensitive data across SaaS, GenAI, email, and endpoints.\n  tags:\n  - Nightfall\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nightfall-ai\n    baseUri: https://api.nightfall.ai\n    description: Nightfall AI HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{NIGHTFALL_AI_TOKEN}}'\n    resources:\n    - name: v2-scan\n      path: /v2/scan\n      operations:\n      - name: scanpayloadv2\n        method: POST\n        description: Nightfall AI Scan for sensitive information in your data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nightfall-ai-rest\n    description: REST adapter for Nightfall AI.\n\
  \    resources:\n    - path: /v2/scan\n      name: scanpayloadv2\n      operations:\n      - method: POST\n        name: scanpayloadv2\n        description: Nightfall AI Scan for sensitive information in your data\n        call: nightfall-ai.scanpayloadv2\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nightfall-ai-mcp\n    transport: http\n    description: MCP adapter for Nightfall AI for AI agent use.\n    tools:\n    - name: scanpayloadv2\n      description: Nightfall AI Scan for sensitive information in your data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nightfall-ai.scanpayloadv2\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NIGHTFALL_AI_TOKEN: NIGHTFALL_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nightfall-ai/refs/heads/main/capabilities/nightfall-ai-capability.yaml
tags:
- Nightfall
- Ai
- API
tools:
- description: Nightfall AI Scan for sensitive information in your data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scanpayloadv2
---
