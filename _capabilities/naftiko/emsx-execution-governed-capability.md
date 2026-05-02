---
categories: []
consumed_apis: []
description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
layout: capability
name: Emsx Execution Governed Capability
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
- capabilities
- naftiko
- mcp
- example op
- example
- a capability over emsx (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
- governance
slug: emsx-execution-governed-capability
source_filename: emsx-execution-governed-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Emsx Execution Governed Capability\n  description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: emsx-execution-governed-capability-rest\n    description: REST API for Emsx Execution Governed Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: emsx-execution-governed-capability-mcp\n    description: MCP server exposing Emsx Execution Governed Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: emsx-execution-governed-capability-skills\n    description: Agent Skill bundle for Emsx Execution Governed Capability.\n    skills:\n    - name: emsx-execution-governed-capability\n      description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation\
  \ runtime for the order-flow path.\n      location: file:///opt/naftiko/skills/emsx-execution-governed-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.\n        from:\n          sourceNamespace: emsx-execution-governed-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/emsx-execution-governed-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
  hints:
    readOnly: true
  name: example
---
