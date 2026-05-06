---
categories: []
consumed_apis: []
description: Hilton provides developer APIs for hotel search, availability, reservations, and loyalty program integration. The APIs enable travel partners and corporate clients to integrate Hilton booking capabilities.
layout: capability
name: Hilton Developer API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: Hilton
provider_slug: hilton
search_terms:
- hotels
- get api status
- hilton
- travel
- getstatus
- reservations
- api
- loyalty
- hospitality
slug: hilton-capability
source_filename: hilton-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hilton Developer API\n  description: Hilton provides developer APIs for hotel search, availability, reservations, and loyalty program integration.\n    The APIs enable travel partners and corporate clients to integrate Hilton booking capabilities.\n  tags:\n  - Hilton\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hilton\n    baseUri: https://api.hilton.com\n    description: Hilton Developer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HILTON_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hilton-rest\n    description: REST adapter for Hilton\
  \ Developer API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: hilton.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hilton-mcp\n    transport: http\n    description: MCP adapter for Hilton Developer API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hilton.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HILTON_TOKEN: HILTON_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hilton/refs/heads/main/capabilities/hilton-capability.yaml
tags:
- Hilton
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
