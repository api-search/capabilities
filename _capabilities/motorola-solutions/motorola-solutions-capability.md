---
categories: []
consumed_apis: []
description: Motorola Solutions provides APIs for public safety communications, command center software, and video security integration. The platform enables partners to build on Motorola's public safety infrastructure.
layout: capability
name: Motorola Solutions API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: Motorola Solutions
provider_slug: motorola-solutions
search_terms:
- solutions
- video security
- get api status
- getstatus
- iot
- api
- public safety
- communications
- motorola
slug: motorola-solutions-capability
source_filename: motorola-solutions-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Motorola Solutions API\n  description: Motorola Solutions provides APIs for public safety communications, command center software, and video security\n    integration. The platform enables partners to build on Motorola's public safety infrastructure.\n  tags:\n  - Motorola\n  - Solutions\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: motorola-solutions\n    baseUri: https://api.motorolasolutions.com\n    description: Motorola Solutions API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MOTOROLA_SOLUTIONS_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ motorola-solutions-rest\n    description: REST adapter for Motorola Solutions API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: motorola-solutions.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: motorola-solutions-mcp\n    transport: http\n    description: MCP adapter for Motorola Solutions API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: motorola-solutions.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MOTOROLA_SOLUTIONS_TOKEN: MOTOROLA_SOLUTIONS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/motorola-solutions/refs/heads/main/capabilities/motorola-solutions-capability.yaml
tags:
- Motorola
- Solutions
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
