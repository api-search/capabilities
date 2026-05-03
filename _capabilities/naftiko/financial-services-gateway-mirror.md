---
categories: []
consumed_apis: []
description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
layout: capability
name: Financial Services Gateway Mirror
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- a -fronted financial-services capability collection — wraps -managed apis as naftiko capabilities, exposes as mcp, layers billing-granularity + retry-safety tags on consumed operations.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: financial-services-gateway-mirror
source_filename: financial-services-gateway-mirror.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Financial Services Gateway Mirror\n  description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: financial-services-gateway-mirror-rest\n    description: REST API for Financial Services Gateway Mirror.\n    resources:\n    - name:\
  \ example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: financial-services-gateway-mirror-mcp\n    description: MCP server exposing Financial Services Gateway Mirror for AI agents.\n    tools:\n    - name: example\n      description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: financial-services-gateway-mirror-skills\n    description: Agent Skill bundle for Financial Services Gateway Mirror.\n    skills:\n    - name: financial-services-gateway-mirror\n      description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities,\
  \ exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.\n      location: file:///opt/naftiko/skills/financial-services-gateway-mirror\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.\n        from:\n          sourceNamespace: financial-services-gateway-mirror-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/financial-services-gateway-mirror.yaml
tags:
- Naftiko
tools:
- description: A -fronted financial-services capability collection — wraps -managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
  hints:
    readOnly: true
  name: example
---
