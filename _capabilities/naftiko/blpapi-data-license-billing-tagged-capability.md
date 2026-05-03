---
categories: []
consumed_apis: []
description: A capability over the BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.
layout: capability
name: Blpapi Data License Billing Tagged Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability over the blpapi / data license surface with billing-granularity + sensitivity tags on consumes — the customer-facing shape for an external -customer agent build.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: blpapi-data-license-billing-tagged-capability
source_filename: blpapi-data-license-billing-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Blpapi Data License Billing Tagged Capability\n  description: A capability over the BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: blpapi-data-license-billing-tagged-capability-rest\n    description: REST API for Blpapi Data License Billing Tagged Capability.\n  \
  \  resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: blpapi-data-license-billing-tagged-capability-mcp\n    description: MCP server exposing Blpapi Data License Billing Tagged Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over the BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: blpapi-data-license-billing-tagged-capability-skills\n    description: Agent Skill bundle for Blpapi Data License Billing Tagged Capability.\n    skills:\n    - name: blpapi-data-license-billing-tagged-capability\n      description: A capability over the BLPAPI\
  \ / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.\n      location: file:///opt/naftiko/skills/blpapi-data-license-billing-tagged-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over the BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.\n        from:\n          sourceNamespace: blpapi-data-license-billing-tagged-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/blpapi-data-license-billing-tagged-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over the BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external -customer agent build.
  hints:
    readOnly: true
  name: example
---
