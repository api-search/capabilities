---
categories: []
consumed_apis: []
description: PepsiCo provides partner APIs for supply chain integration, product data, and retail analytics. These APIs support distribution partners and retail customers in managing PepsiCo product operations.
layout: capability
name: PepsiCo API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: PepsiCo
provider_slug: pepsico
search_terms:
- supply chain
- get api status
- retail
- getstatus
- food
- api
- beverages
- pepsico
slug: pepsico-capability
source_filename: pepsico-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PepsiCo API\n  description: PepsiCo provides partner APIs for supply chain integration, product data, and retail analytics. These APIs\n    support distribution partners and retail customers in managing PepsiCo product operations.\n  tags:\n  - Pepsico\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pepsico\n    baseUri: https://api.pepsico.com\n    description: PepsiCo API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PEPSICO_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pepsico-rest\n    description: REST adapter for PepsiCo API.\n    resources:\n\
  \    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: pepsico.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pepsico-mcp\n    transport: http\n    description: MCP adapter for PepsiCo API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pepsico.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PEPSICO_TOKEN: PEPSICO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pepsico/refs/heads/main/capabilities/pepsico-capability.yaml
tags:
- Pepsico
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
