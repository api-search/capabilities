---
categories: []
consumed_apis: []
description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.
layout: capability
name: Data Api Capability
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
- api integration
- spec-driven integration
- capabilities
- a capability layered on top of the data api showing typed outputparameters + tags-on-consumes (data sensitivity, billing granularity) as the -customer-facing pattern.
- example op
- governance
slug: data-api-capability
source_filename: data-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Data Api Capability\n  description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: data-api-capability-rest\n    description: REST API for Data Api Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: data-api-capability-mcp\n    description: MCP server exposing Data Api Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: data-api-capability-skills\n    description: Agent Skill bundle for Data Api Capability.\n    skills:\n    - name: data-api-capability\n      description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.\n      location: file:///opt/naftiko/skills/data-api-capability\n      allowed-tools:\
  \ example\n      tools:\n      - name: example\n        description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.\n        from:\n          sourceNamespace: data-api-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/data-api-capability.yaml
tags:
- Naftiko
tools:
- description: A capability layered on top of the Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the -customer-facing pattern.
  hints:
    readOnly: true
  name: example
---
