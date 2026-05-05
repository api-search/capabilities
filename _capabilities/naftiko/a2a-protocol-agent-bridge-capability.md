---
categories: []
consumed_apis: []
description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
layout: capability
name: A2A Protocol Agent Bridge Capability
operations:
- description: A2A agent card listing all Naftiko capabilities as A2A-callable skills.
  method: GET
  name: get-agent-card
  path: /.well-known/agent.json
- description: Receive an A2A message and dispatch it to the matching Naftiko capability.
  method: POST
  name: send-message
  path: /a2a/v1/messages
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list naftiko capabilities exposed through the a2a bridge.
- spec-driven integration
- agent
- governance
- get agent card
- invoke bridged capability
- a2a
- receive an a2a message and dispatch it to the matching naftiko capability.
- list bridged capabilities
- ai
- mcp
- a2a agent card listing all naftiko capabilities as a2a-callable skills.
- capabilities
- naftiko
- api integration
- send message
- invoke a naftiko capability through the a2a bridge with an a2a message payload.
slug: a2a-protocol-agent-bridge-capability
source_filename: a2a-protocol-agent-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: A2a Protocol Agent Bridge Capability\n  description: A capability that exposes Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.\n  tags:\n  - Naftiko\n  - A2A\n  - Agent\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko control-plane API token.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: capabilities\n      path: /v1/capabilities\n      operations:\n      - name: list-capabilities\n        method: GET\n    - name: capability\n      path: /v1/capabilities/{{capability_id}}\n      operations:\n      - name: get-capability\n        method: GET\n        inputParameters:\n\
  \        - name: capability_id\n          in: path\n    - name: capability-invoke\n      path: /v1/capabilities/{{capability_id}}/invoke\n      operations:\n      - name: invoke-capability\n        method: POST\n        inputParameters:\n        - name: capability_id\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: a2a-protocol-agent-bridge-capability-rest\n    description: A2A-protocol REST surface that mirrors Naftiko capabilities for cross-vendor agent calls.\n    resources:\n    - name: agent-card\n      path: /.well-known/agent.json\n      operations:\n      - method: GET\n        name: get-agent-card\n        description: A2A agent card listing all Naftiko capabilities as A2A-callable skills.\n        call: naftiko-control.list-capabilities\n    - name: messages\n      path: /a2a/v1/messages\n      operations:\n      - method: POST\n        name: send-message\n        description: Receive an A2A message and dispatch it to the matching\
  \ Naftiko capability.\n        call: naftiko-control.invoke-capability\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: a2a-protocol-agent-bridge-capability-mcp\n    description: MCP mirror so the same capabilities are reachable from MCP-only agents.\n    tools:\n    - name: list-bridged-capabilities\n      description: List Naftiko capabilities exposed through the A2A bridge.\n      hints:\n        readOnly: true\n      call: naftiko-control.list-capabilities\n    - name: invoke-bridged-capability\n      description: Invoke a Naftiko capability through the A2A bridge with an A2A message payload.\n      inputParameters:\n      - name: capability_id\n        type: string\n        required: true\n      call: naftiko-control.invoke-capability\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: a2a-protocol-agent-bridge-capability-skills\n    description: Agent Skill bundle for installing the A2A bridge tooling into agent runtimes.\n    skills:\n    -\
  \ name: a2a-protocol-agent-bridge-capability\n      description: Cross-vendor agent calls land on the same Naftiko-governed capability.\n      location: file:///opt/naftiko/skills/a2a-protocol-agent-bridge-capability\n      allowed-tools: list-bridged-capabilities,invoke-bridged-capability\n      tools:\n      - name: list-bridged-capabilities\n        description: List bridged capabilities.\n        from:\n          sourceNamespace: a2a-protocol-agent-bridge-capability-mcp\n          action: list-bridged-capabilities\n      - name: invoke-bridged-capability\n        description: Invoke a bridged capability.\n        from:\n          sourceNamespace: a2a-protocol-agent-bridge-capability-mcp\n          action: invoke-bridged-capability\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/a2a-protocol-agent-bridge-capability.yaml
tags:
- Naftiko
- A2A
- Agent
tools:
- description: List Naftiko capabilities exposed through the A2A bridge.
  hints:
    readOnly: true
  name: list-bridged-capabilities
- description: Invoke a Naftiko capability through the A2A bridge with an A2A message payload.
  hints: {}
  name: invoke-bridged-capability
---
