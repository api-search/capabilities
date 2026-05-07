---
categories: []
consumed_apis: []
description: CBRE provides APIs for commercial real estate data including property listings, market analytics, and facility management. The platform enables partners to access CBRE's real estate intelligence.
layout: capability
name: CBRE API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: CBRE
provider_slug: cbre
search_terms:
- analytics
- valuation
- commercial real estate
- property management
- facilities management
- real estate
- cbre
- getstatus
- investment management
- get api status
- api
- fortune 500
slug: cbre-capability
source_filename: cbre-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CBRE API\n  description: CBRE provides APIs for commercial real estate data including property listings, market analytics, and facility\n    management. The platform enables partners to access CBRE's real estate intelligence.\n  tags:\n  - Cbre\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cbre\n    baseUri: https://api.cbre.com\n    description: CBRE API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CBRE_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cbre-rest\n    description: REST adapter for CBRE API.\n    resources:\n    - path: /status\n\
  \      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: cbre.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cbre-mcp\n    transport: http\n    description: MCP adapter for CBRE API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cbre.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CBRE_TOKEN: CBRE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cbre/refs/heads/main/capabilities/cbre-capability.yaml
tags:
- Cbre
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
