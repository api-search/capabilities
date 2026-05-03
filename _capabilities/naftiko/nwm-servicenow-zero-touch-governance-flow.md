---
categories: []
consumed_apis: []
description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
layout: capability
name: Nwm Servicenow Zero Touch Governance Flow
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
- a capability that fires naftiko governance findings into servicenow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: nwm-servicenow-zero-touch-governance-flow
source_filename: nwm-servicenow-zero-touch-governance-flow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Servicenow Zero Touch Governance Flow\n  description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-servicenow-zero-touch-governance-flow-rest\n    description: REST API for Nwm Servicenow Zero Touch Governance Flow.\n    resources:\n    -\
  \ name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-servicenow-zero-touch-governance-flow-mcp\n    description: MCP server exposing Nwm Servicenow Zero Touch Governance Flow for AI agents.\n    tools:\n    - name: example\n      description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-servicenow-zero-touch-governance-flow-skills\n    description: Agent Skill bundle for Nwm Servicenow Zero Touch Governance Flow.\n    skills:\n    - name: nwm-servicenow-zero-touch-governance-flow\n      description: A capability that fires Naftiko governance findings into ServiceNow\
  \ change/incident records as advisory + blocking gates, so the policy actually has a system of action.\n      location: file:///opt/naftiko/skills/nwm-servicenow-zero-touch-governance-flow\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.\n        from:\n          sourceNamespace: nwm-servicenow-zero-touch-governance-flow-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-servicenow-zero-touch-governance-flow.yaml
tags:
- Naftiko
tools:
- description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
  hints:
    readOnly: true
  name: example
---
