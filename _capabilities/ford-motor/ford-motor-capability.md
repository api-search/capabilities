---
categories: []
consumed_apis: []
description: The Ford Developer API provides access to connected vehicle data, allowing developers to build applications that interact with Ford vehicles. It includes APIs for vehicle status, location, remote commands, and diagnostics.
layout: capability
name: Ford Developer API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: ford-motor
provider_slug: ford-motor
search_terms:
- get api status
- ford
- getstatus
- motor
- api
slug: ford-motor-capability
source_filename: ford-motor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ford Developer API\n  description: The Ford Developer API provides access to connected vehicle data, allowing developers to build applications\n    that interact with Ford vehicles. It includes APIs for vehicle status, location, remote commands, and diagnostics.\n  tags:\n  - Ford\n  - Motor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ford-motor\n    baseUri: https://api.ford.com\n    description: Ford Developer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FORD_MOTOR_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ford-motor-rest\n   \
  \ description: REST adapter for Ford Developer API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: ford-motor.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ford-motor-mcp\n    transport: http\n    description: MCP adapter for Ford Developer API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ford-motor.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FORD_MOTOR_TOKEN: FORD_MOTOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ford-motor/refs/heads/main/capabilities/ford-motor-capability.yaml
tags:
- Ford
- Motor
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
