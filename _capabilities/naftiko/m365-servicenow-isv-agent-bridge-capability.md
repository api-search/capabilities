---
categories: []
consumed_apis: []
description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
layout: capability
name: M365 Servicenow Isv Agent Bridge Capability
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
- a capability that wraps a servicenow operation as both a native isv agent installed inside m365 copilot and an mcp tool, demonstrating sébastien's agent-to-agent isv path.
- naftiko
- capabilities
- mcp
- example op
- example
- governance
slug: m365-servicenow-isv-agent-bridge-capability
source_filename: m365-servicenow-isv-agent-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Servicenow Isv Agent Bridge Capability\n  description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-servicenow-isv-agent-bridge-capability-rest\n    description: REST API for M365 Servicenow Isv Agent Bridge Capability.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-servicenow-isv-agent-bridge-capability-mcp\n    description: MCP server exposing M365 Servicenow Isv Agent Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-servicenow-isv-agent-bridge-capability-skills\n    description: Agent Skill bundle for M365 Servicenow Isv Agent Bridge Capability.\n    skills:\n    - name: m365-servicenow-isv-agent-bridge-capability\n      description: A capability that wraps a ServiceNow operation as\
  \ both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.\n      location: file:///opt/naftiko/skills/m365-servicenow-isv-agent-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.\n        from:\n          sourceNamespace: m365-servicenow-isv-agent-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-servicenow-isv-agent-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
  hints:
    readOnly: true
  name: example
---
