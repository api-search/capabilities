---
categories: []
consumed_apis: []
description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
layout: capability
name: A2A Protocol Agent Bridge Capability
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
- governance
- a capability that exposes naftiko-managed capabilities via google's a2a (agent-to-agent) protocol in addition to mcp, so cross-vendor agent calls land on the same governed capability.
slug: a2a-protocol-agent-bridge-capability
source_filename: a2a-protocol-agent-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: A2a Protocol Agent Bridge Capability\n  description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: a2a-protocol-agent-bridge-capability-rest\n    description: REST API for A2a Protocol Agent Bridge Capability.\n    resources:\n    -\
  \ name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: a2a-protocol-agent-bridge-capability-mcp\n    description: MCP server exposing A2a Protocol Agent Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: a2a-protocol-agent-bridge-capability-skills\n    description: Agent Skill bundle for A2a Protocol Agent Bridge Capability.\n    skills:\n    - name: a2a-protocol-agent-bridge-capability\n      description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent)\
  \ protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.\n      location: file:///opt/naftiko/skills/a2a-protocol-agent-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.\n        from:\n          sourceNamespace: a2a-protocol-agent-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/a2a-protocol-agent-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
  hints:
    readOnly: true
  name: example
---
