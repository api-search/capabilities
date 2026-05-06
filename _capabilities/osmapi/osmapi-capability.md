---
categories: []
consumed_apis: []
description: Anthropic-compatible messages endpoint routed through osmAPI's unified AI gateway. Supports the native Anthropic message format including system prompts, extended thinking, tool use, and streaming.
layout: capability
name: osmAPI Anthropic Messages API
operations:
- description: Create a message
  method: POST
  name: createmessage
  path: /messages
personas: []
provider_name: osmAPI
provider_slug: osmapi
search_terms:
- llm
- gateway
- createmessage
- api
- routing
- osmapi
- openai
- create a message
- ai
- anthropic
slug: osmapi-capability
source_filename: osmapi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: osmAPI Anthropic Messages API\n  description: Anthropic-compatible messages endpoint routed through osmAPI's unified AI gateway. Supports the native Anthropic\n    message format including system prompts, extended thinking, tool use, and streaming.\n  tags:\n  - Osmapi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: osmapi\n    baseUri: https://api.osmapi.com/v1\n    description: osmAPI Anthropic Messages API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OSMAPI_TOKEN}}'\n    resources:\n    - name: messages\n      path: /messages\n      operations:\n      - name: createmessage\n        method: POST\n        description: Create a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: osmapi-rest\n    description:\
  \ REST adapter for osmAPI Anthropic Messages API.\n    resources:\n    - path: /messages\n      name: createmessage\n      operations:\n      - method: POST\n        name: createmessage\n        description: Create a message\n        call: osmapi.createmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: osmapi-mcp\n    transport: http\n    description: MCP adapter for osmAPI Anthropic Messages API for AI agent use.\n    tools:\n    - name: createmessage\n      description: Create a message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: osmapi.createmessage\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OSMAPI_TOKEN: OSMAPI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/osmapi/refs/heads/main/capabilities/osmapi-capability.yaml
tags:
- Osmapi
- API
tools:
- description: Create a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
---
