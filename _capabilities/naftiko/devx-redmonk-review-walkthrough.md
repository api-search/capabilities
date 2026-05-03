---
categories: []
consumed_apis: []
description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
layout: capability
name: Devx Redmonk Review Walkthrough
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
- 'a capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: vs code extension + backstage scaffold + downloadable agent skill.'
- capabilities
- example op
- governance
slug: devx-redmonk-review-walkthrough
source_filename: devx-redmonk-review-walkthrough.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Devx Review Walkthrough\n  description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: devx--review-walkthrough-rest\n    description: REST API for Devx Review Walkthrough.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: devx--review-walkthrough-mcp\n    description: MCP server exposing Devx Review Walkthrough for AI agents.\n    tools:\n    - name: example\n      description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: devx--review-walkthrough-skills\n    description: Agent Skill bundle for Devx Review Walkthrough.\n    skills:\n    - name: devx--review-walkthrough\n      description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'\n\
  \      location: file:///opt/naftiko/skills/devx--review-walkthrough\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'\n        from:\n          sourceNamespace: devx--review-walkthrough-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/devx-redmonk-review-walkthrough.yaml
tags:
- Naftiko
tools:
- description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
  hints:
    readOnly: true
  name: example
---
