---
categories: []
consumed_apis: []
description: A capability that exposes a Power Automate / Power Platform flow as a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.
layout: capability
name: M365 Power Platform Flow As Capability
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
- api integration
- a capability that exposes a power automate / power platform flow as a single mcp tool with shaped output, so a copilot agent can call a curated org flow without re-implementing it.
- naftiko
- governance
- mcp
- capabilities
- ai
slug: m365-power-platform-flow-as-capability
source_filename: m365-power-platform-flow-as-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Power Platform Flow As Capability\n  description: A capability that exposes a Power Automate / Power Platform flow as a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-power-platform-flow-as-capability-rest\n    description: REST API for M365 Power Platform Flow As Capability.\n    resources:\n \
  \   - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-power-platform-flow-as-capability-mcp\n    description: MCP server exposing M365 Power Platform Flow As Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that exposes a Power Automate / Power Platform flow as a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-power-platform-flow-as-capability-skills\n    description: Agent Skill bundle for M365 Power Platform Flow As Capability.\n    skills:\n    - name: m365-power-platform-flow-as-capability\n      description: A capability that exposes a Power Automate / Power Platform flow as\
  \ a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.\n      location: file:///opt/naftiko/skills/m365-power-platform-flow-as-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that exposes a Power Automate / Power Platform flow as a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.\n        from:\n          sourceNamespace: m365-power-platform-flow-as-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-power-platform-flow-as-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that exposes a Power Automate / Power Platform flow as a single MCP tool with shaped output, so a Copilot agent can call a curated org flow without re-implementing it.
  hints:
    readOnly: true
  name: example
---
