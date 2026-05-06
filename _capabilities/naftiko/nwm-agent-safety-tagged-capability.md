---
categories: []
consumed_apis: []
description: A Northwestern Mutual capability that tags every agent action with safety classification (PII, regulated, financial-advice) for audit.
layout: capability
name: Nwm Agent Safety Tagged Capability
operations:
- description: ''
  method: POST
  name: tag-action
  path: /tag
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- agent safety
- nwm
- api integration
- tag action
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- list safety events
slug: nwm-agent-safety-tagged-capability
source_filename: nwm-agent-safety-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Agent Safety Tagged Capability\n  description: A Northwestern Mutual capability that tags every agent action with safety classification (PII, regulated, financial-advice) for audit.\n  tags: [Naftiko, NWM, Agent Safety]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: safety-tags, path: /v1/safety/tags, operations: [{name: tag-action, method: POST}]}\n    - {name: safety-events, path: /v1/safety/events, operations: [{name: list-safety-events, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-agent-safety-tagged-capability-rest\n    description: REST surface for safety-tagged actions.\n    resources:\n\
  \    - {name: tag, path: /tag, operations: [{method: POST, name: tag-action, call: naftiko-control.tag-action}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-agent-safety-tagged-capability-mcp\n    description: MCP for safety-tagged agent actions.\n    tools:\n    - {name: tag-action, call: naftiko-control.tag-action}\n    - {name: list-safety-events, hints: {readOnly: true}, call: naftiko-control.list-safety-events}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-agent-safety-tagged-capability-skills\n    description: Skill for agent safety.\n    skills:\n    - name: nwm-agent-safety-tagged-capability\n      description: Agent safety-tagged actions.\n      location: file:///opt/naftiko/skills/nwm-agent-safety-tagged-capability\n      allowed-tools: tag-action,list-safety-events\n      tools:\n      - {name: tag-action, from: {sourceNamespace: nwm-agent-safety-tagged-capability-mcp, action: tag-action}}\n      - {name: list-safety-events,\
  \ from: {sourceNamespace: nwm-agent-safety-tagged-capability-mcp, action: list-safety-events}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-agent-safety-tagged-capability.yaml
tags:
- Naftiko
- NWM
- Agent Safety
tools:
- description: ''
  hints: {}
  name: tag-action
- description: ''
  hints:
    readOnly: true
  name: list-safety-events
---
