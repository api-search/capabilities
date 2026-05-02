---
categories: []
consumed_apis: []
description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
layout: capability
name: M365 Rightsize Copilot Context Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- 'implements guide-use-cases #2 (rightsize ai context) against a verbose graph endpoint, used as the basis for the follow-on stories and shorts.'
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: m365-rightsize-copilot-context-capability
source_filename: m365-rightsize-copilot-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Rightsize Copilot Context Capability\n  description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-rightsize-copilot-context-capability-rest\n    description: REST API for M365 Rightsize Copilot Context Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-rightsize-copilot-context-capability-mcp\n    description: MCP server exposing M365 Rightsize Copilot Context Capability for AI agents.\n    tools:\n    - name: example\n      description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-rightsize-copilot-context-capability-skills\n    description: Agent Skill bundle for M365 Rightsize Copilot Context Capability.\n    skills:\n    - name: m365-rightsize-copilot-context-capability\n      description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on\
  \ stories and shorts.'\n      location: file:///opt/naftiko/skills/m365-rightsize-copilot-context-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'\n        from:\n          sourceNamespace: m365-rightsize-copilot-context-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-rightsize-copilot-context-capability.yaml
tags:
- Naftiko
tools:
- description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
  hints:
    readOnly: true
  name: example
---
