---
categories: []
consumed_apis: []
description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
layout: capability
name: Nwm Agent Safety Tagged Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- insurance-adjacent capability showing tags-on-exposedoperation (agent safety policy, effect classification) for ai-safe operations on financial data.
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: nwm-agent-safety-tagged-capability
source_filename: nwm-agent-safety-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Agent Safety Tagged Capability\n  description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-agent-safety-tagged-capability-rest\n    description: REST API for Nwm Agent Safety Tagged Capability.\n    resources:\n    - name: example\n      path: /example\n \
  \     operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-agent-safety-tagged-capability-mcp\n    description: MCP server exposing Nwm Agent Safety Tagged Capability for AI agents.\n    tools:\n    - name: example\n      description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-agent-safety-tagged-capability-skills\n    description: Agent Skill bundle for Nwm Agent Safety Tagged Capability.\n    skills:\n    - name: nwm-agent-safety-tagged-capability\n      description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.\n      location:\
  \ file:///opt/naftiko/skills/nwm-agent-safety-tagged-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.\n        from:\n          sourceNamespace: nwm-agent-safety-tagged-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-agent-safety-tagged-capability.yaml
tags:
- Naftiko
tools:
- description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
  hints:
    readOnly: true
  name: example
---
