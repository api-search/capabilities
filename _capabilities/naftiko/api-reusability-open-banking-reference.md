---
categories: []
consumed_apis: []
description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
layout: capability
name: Api Reusability Open Banking Reference
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
- 'a reference capability tying open banking to guide-use-cases #9 (capability-first api reusability) as the thought-leadership angle.'
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: api-reusability-open-banking-reference
source_filename: api-reusability-open-banking-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api Reusability Open Banking Reference\n  description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-reusability-open-banking-reference-rest\n    description: REST API for Api Reusability Open Banking Reference.\n    resources:\n    - name: example\n      path: /example\n     \
  \ operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-reusability-open-banking-reference-mcp\n    description: MCP server exposing Api Reusability Open Banking Reference for AI agents.\n    tools:\n    - name: example\n      description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-reusability-open-banking-reference-skills\n    description: Agent Skill bundle for Api Reusability Open Banking Reference.\n    skills:\n    - name: api-reusability-open-banking-reference\n      description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'\n      location: file:///opt/naftiko/skills/api-reusability-open-banking-reference\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'\n        from:\n          sourceNamespace: api-reusability-open-banking-reference-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-reusability-open-banking-reference.yaml
tags:
- Naftiko
tools:
- description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
  hints:
    readOnly: true
  name: example
---
