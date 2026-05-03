---
categories: []
consumed_apis: []
description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
layout: capability
name: Avenga Introduction Primer Capability
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
- naftiko
- governance
- mcp
- 'a small, runnable capability + use-case briefing pair (use cases #1 + #2) packaged as the avenga introduction artifact.'
- capabilities
- ai
slug: avenga-introduction-primer-capability
source_filename: avenga-introduction-primer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Avenga Introduction Primer Capability\n  description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: avenga-introduction-primer-capability-rest\n    description: REST API for Avenga Introduction Primer Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n \
  \     - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: avenga-introduction-primer-capability-mcp\n    description: MCP server exposing Avenga Introduction Primer Capability for AI agents.\n    tools:\n    - name: example\n      description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: avenga-introduction-primer-capability-skills\n    description: Agent Skill bundle for Avenga Introduction Primer Capability.\n    skills:\n    - name: avenga-introduction-primer-capability\n      description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'\n      location: file:///opt/naftiko/skills/avenga-introduction-primer-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'\n        from:\n          sourceNamespace: avenga-introduction-primer-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/avenga-introduction-primer-capability.yaml
tags:
- Naftiko
tools:
- description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
  hints:
    readOnly: true
  name: example
---
