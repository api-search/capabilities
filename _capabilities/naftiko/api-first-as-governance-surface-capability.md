---
categories: []
consumed_apis: []
description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
layout: capability
name: Api First As Governance Surface Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- a capability annotated against the sdi "specification as governance surface" framing as the api-first program reading.
- naftiko
- capabilities
- mcp
- example op
- example
- governance
slug: api-first-as-governance-surface-capability
source_filename: api-first-as-governance-surface-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api First As Governance Surface Capability\n  description: A capability annotated against the SDI \"specification as governance surface\" framing as the API-First Program reading.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-first-as-governance-surface-capability-rest\n    description: REST API for Api First As Governance Surface Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-first-as-governance-surface-capability-mcp\n    description: MCP server exposing Api First As Governance Surface Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability annotated against the SDI \"specification as governance surface\" framing as the API-First Program reading.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-first-as-governance-surface-capability-skills\n    description: Agent Skill bundle for Api First As Governance Surface Capability.\n    skills:\n    - name: api-first-as-governance-surface-capability\n      description: A capability annotated against the SDI \"specification as governance surface\" framing as the API-First Program reading.\n      location: file:///opt/naftiko/skills/api-first-as-governance-surface-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability annotated against the SDI \"specification as governance surface\" framing as the API-First Program reading.\n        from:\n          sourceNamespace: api-first-as-governance-surface-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-first-as-governance-surface-capability.yaml
tags:
- Naftiko
tools:
- description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
  hints:
    readOnly: true
  name: example
---
