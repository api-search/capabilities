---
categories: []
consumed_apis: []
description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
layout: capability
name: Compose Ai Context Podcast Pitch
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
- a capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
- example op
- governance
slug: compose-ai-context-podcast-pitch
source_filename: compose-ai-context-podcast-pitch.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compose Ai Context Podcast Pitch\n  description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compose-ai-context-podcast-pitch-rest\n    description: REST API for Compose Ai Context Podcast Pitch.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n\
  \        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compose-ai-context-podcast-pitch-mcp\n    description: MCP server exposing Compose Ai Context Podcast Pitch for AI agents.\n    tools:\n    - name: example\n      description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compose-ai-context-podcast-pitch-skills\n    description: Agent Skill bundle for Compose Ai Context Podcast Pitch.\n    skills:\n    - name: compose-ai-context-podcast-pitch\n      description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.\n      location: file:///opt/naftiko/skills/compose-ai-context-podcast-pitch\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability sized\
  \ to be the topic of a podcast episode pitch — a specific topic she can say yes to.\n        from:\n          sourceNamespace: compose-ai-context-podcast-pitch-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compose-ai-context-podcast-pitch.yaml
tags:
- Naftiko
tools:
- description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
  hints:
    readOnly: true
  name: example
---
