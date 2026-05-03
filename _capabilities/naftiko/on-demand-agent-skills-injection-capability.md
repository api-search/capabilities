---
categories: []
consumed_apis: []
description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
layout: capability
name: On Demand Agent Skills Injection Capability
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
- a capability that consumes a -generated agent skill manifest and exposes a single mcp tool that injects it on-demand into a coding agent's context.
- ai
- mcp
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: on-demand-agent-skills-injection-capability
source_filename: on-demand-agent-skills-injection-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: On Demand Agent Skills Injection Capability\n  description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: on-demand-agent-skills-injection-capability-rest\n    description: REST API for On Demand Agent Skills Injection Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: on-demand-agent-skills-injection-capability-mcp\n    description: MCP server exposing On Demand Agent Skills Injection Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: on-demand-agent-skills-injection-capability-skills\n    description: Agent Skill bundle for On Demand Agent Skills Injection Capability.\n    skills:\n    - name: on-demand-agent-skills-injection-capability\n      description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that\
  \ injects it on-demand into a coding agent's context.\n      location: file:///opt/naftiko/skills/on-demand-agent-skills-injection-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.\n        from:\n          sourceNamespace: on-demand-agent-skills-injection-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/on-demand-agent-skills-injection-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes a -generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
  hints:
    readOnly: true
  name: example
---
