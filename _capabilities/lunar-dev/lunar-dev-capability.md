---
categories: []
consumed_apis: []
description: The Lunar.dev Gateway Admin API provides administrative endpoints for managing and monitoring the Lunar API Consumption Gateway. The gateway acts as an egress proxy for third-party API traffic, providing visibility, control, and performance optimization. The admin API enables health monitoring, endpoint discovery, flow validation, and policy management for the running gateway instance.
layout: capability
name: Lunar.dev Gateway Admin API
operations:
- description: Lunar.dev Check gateway health
  method: GET
  name: gethealthcheck
  path: /healthcheck
- description: Lunar.dev Discover API endpoints
  method: GET
  name: getdiscover
  path: /discover
- description: Lunar.dev Apply policies
  method: POST
  name: applypolicies
  path: /apply_policies
- description: Lunar.dev Validate policies
  method: POST
  name: validatepolicies
  path: /validate_policies
- description: Lunar.dev Validate flows
  method: POST
  name: validateflows
  path: /validate_flows
- description: Lunar.dev Apply flows
  method: POST
  name: applyflows
  path: /apply_flows
personas: []
provider_name: Lunar.dev
provider_slug: lunar-dev
search_terms:
- applypolicies
- lunar.dev validate flows
- lunar.dev apply policies
- consumption gateway
- deployment
- control
- visibility
- integrations
- getdiscover
- ai gateway
- lunar.dev apply flows
- mcp gateway
- api
- validateflows
- workflows
- version control
- dev
- lunar
- performance
- platform
- applyflows
- gethealthcheck
- lunar.dev discover api endpoints
- lunar.dev validate policies
- validatepolicies
- lunar.dev check gateway health
- automation
slug: lunar-dev-capability
source_filename: lunar-dev-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lunar.dev Gateway Admin API\n  description: The Lunar.dev Gateway Admin API provides administrative endpoints for managing and monitoring the Lunar API\n    Consumption Gateway. The gateway acts as an egress proxy for third-party API traffic, providing visibility, control, and\n    performance optimization. The admin API enables health monitoring, endpoint discovery, flow validation, and policy management\n    for the running gateway instance.\n  tags:\n  - Lunar\n  - Dev\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lunar-dev\n    baseUri: http://localhost:8040\n    description: Lunar.dev Gateway Admin API HTTP API.\n    resources:\n    - name: healthcheck\n      path: /healthcheck\n      operations:\n      - name: gethealthcheck\n        method: GET\n        description: Lunar.dev Check gateway health\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: discover\n      path: /discover\n      operations:\n      - name: getdiscover\n        method: GET\n        description: Lunar.dev Discover API endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apply-policies\n      path: /apply_policies\n      operations:\n      - name: applypolicies\n        method: POST\n        description: Lunar.dev Apply policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: validate-policies\n      path: /validate_policies\n      operations:\n      - name: validatepolicies\n        method: POST\n        description: Lunar.dev Validate policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: validate-flows\n\
  \      path: /validate_flows\n      operations:\n      - name: validateflows\n        method: POST\n        description: Lunar.dev Validate flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apply-flows\n      path: /apply_flows\n      operations:\n      - name: applyflows\n        method: POST\n        description: Lunar.dev Apply flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lunar-dev-rest\n    description: REST adapter for Lunar.dev Gateway Admin API.\n    resources:\n    - path: /healthcheck\n      name: gethealthcheck\n      operations:\n      - method: GET\n        name: gethealthcheck\n        description: Lunar.dev Check gateway health\n        call: lunar-dev.gethealthcheck\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /discover\n      name: getdiscover\n      operations:\n      - method: GET\n        name: getdiscover\n        description: Lunar.dev Discover API endpoints\n        call: lunar-dev.getdiscover\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apply_policies\n      name: applypolicies\n      operations:\n      - method: POST\n        name: applypolicies\n        description: Lunar.dev Apply policies\n        call: lunar-dev.applypolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /validate_policies\n      name: validatepolicies\n      operations:\n      - method: POST\n        name: validatepolicies\n        description: Lunar.dev Validate policies\n        call: lunar-dev.validatepolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /validate_flows\n      name: validateflows\n      operations:\n      - method: POST\n        name: validateflows\n\
  \        description: Lunar.dev Validate flows\n        call: lunar-dev.validateflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apply_flows\n      name: applyflows\n      operations:\n      - method: POST\n        name: applyflows\n        description: Lunar.dev Apply flows\n        call: lunar-dev.applyflows\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lunar-dev-mcp\n    transport: http\n    description: MCP adapter for Lunar.dev Gateway Admin API for AI agent use.\n    tools:\n    - name: gethealthcheck\n      description: Lunar.dev Check gateway health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lunar-dev.gethealthcheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdiscover\n      description: Lunar.dev Discover API endpoints\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: lunar-dev.getdiscover\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: applypolicies\n      description: Lunar.dev Apply policies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lunar-dev.applypolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validatepolicies\n      description: Lunar.dev Validate policies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lunar-dev.validatepolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validateflows\n      description: Lunar.dev Validate flows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lunar-dev.validateflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: applyflows\n\
  \      description: Lunar.dev Apply flows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lunar-dev.applyflows\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lunar-dev/refs/heads/main/capabilities/lunar-dev-capability.yaml
tags:
- Lunar
- Dev
- API
tools:
- description: Lunar.dev Check gateway health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthcheck
- description: Lunar.dev Discover API endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiscover
- description: Lunar.dev Apply policies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: applypolicies
- description: Lunar.dev Validate policies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validatepolicies
- description: Lunar.dev Validate flows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateflows
- description: Lunar.dev Apply flows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: applyflows
---
