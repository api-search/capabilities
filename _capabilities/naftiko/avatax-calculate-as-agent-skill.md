---
categories: []
consumed_apis: []
description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
layout: capability
name: Avatax Calculate As Agent Skill
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
- wraps the avatax `/transactions/createoradjust` endpoint as a downloadable agent skill folder + mcp tool, with shaped jurisdiction-aware output for an ai checkout assistant.
- example op
- governance
slug: avatax-calculate-as-agent-skill
source_filename: avatax-calculate-as-agent-skill.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Avatax Calculate As Agent Skill\n  description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: avatax-calculate-as-agent-skill-rest\n    description: REST API for Avatax Calculate As Agent Skill.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: avatax-calculate-as-agent-skill-mcp\n    description: MCP server exposing Avatax Calculate As Agent Skill for AI agents.\n    tools:\n    - name: example\n      description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: avatax-calculate-as-agent-skill-skills\n    description: Agent Skill bundle for Avatax Calculate As Agent Skill.\n    skills:\n    - name: avatax-calculate-as-agent-skill\n      description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output\
  \ for an AI checkout assistant.\n      location: file:///opt/naftiko/skills/avatax-calculate-as-agent-skill\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.\n        from:\n          sourceNamespace: avatax-calculate-as-agent-skill-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/avatax-calculate-as-agent-skill.yaml
tags:
- Naftiko
tools:
- description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
  hints:
    readOnly: true
  name: example
---
