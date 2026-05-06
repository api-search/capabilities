---
categories: []
consumed_apis: []
description: This is the API for publishing to the API pulse.
layout: capability
name: API Pulse Publishing
operations:
- description: API Pulse Submit Signal
  method: POST
  name: submitsignal
  path: /signals
personas: []
provider_name: API Pulse
provider_slug: api-pulse
search_terms:
- api pulse submit signal
- submitsignal
- api evangelist
- api
- pulse
- survey
- api benchmarking
- api maturity
- api governance
slug: api-pulse-capability
source_filename: api-pulse-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: API Pulse Publishing\n  description: This is the API for publishing to the API pulse.\n  tags:\n  - Api\n  - Pulse\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: api-pulse\n    baseUri: http://api.theapipulse.com\n    description: API Pulse Publishing HTTP API.\n    resources:\n    - name: signals\n      path: /signals\n      operations:\n      - name: submitsignal\n        method: POST\n        description: API Pulse Submit Signal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-pulse-rest\n    description: REST adapter for API Pulse Publishing.\n    resources:\n    - path: /signals\n      name: submitsignal\n      operations:\n      - method: POST\n        name: submitsignal\n        description: API Pulse Submit Signal\n  \
  \      call: api-pulse.submitsignal\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: api-pulse-mcp\n    transport: http\n    description: MCP adapter for API Pulse Publishing for AI agent use.\n    tools:\n    - name: submitsignal\n      description: API Pulse Submit Signal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-pulse.submitsignal\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-pulse/refs/heads/main/capabilities/api-pulse-capability.yaml
tags:
- Api
- Pulse
- API
tools:
- description: API Pulse Submit Signal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitsignal
---
