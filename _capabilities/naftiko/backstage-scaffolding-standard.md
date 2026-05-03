---
categories: []
consumed_apis: []
description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
layout: capability
name: Backstage Scaffolding Standard
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
- a capability scaffolded from a backstage template, intended as the "scaffolding standard a p&g enterprise-integration org could mandate."
- capabilities
- example op
- governance
slug: backstage-scaffolding-standard
source_filename: backstage-scaffolding-standard.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Scaffolding Standard\n  description: A capability scaffolded from a Backstage template, intended as the \"scaffolding standard a P&G enterprise-integration org could mandate.\"\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-scaffolding-standard-rest\n    description: REST API for Backstage Scaffolding Standard.\n    resources:\n    - name: example\n      path: /example\n      operations:\n    \
  \  - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-scaffolding-standard-mcp\n    description: MCP server exposing Backstage Scaffolding Standard for AI agents.\n    tools:\n    - name: example\n      description: A capability scaffolded from a Backstage template, intended as the \"scaffolding standard a P&G enterprise-integration org could mandate.\"\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-scaffolding-standard-skills\n    description: Agent Skill bundle for Backstage Scaffolding Standard.\n    skills:\n    - name: backstage-scaffolding-standard\n      description: A capability scaffolded from a Backstage template, intended as the \"scaffolding standard a P&G enterprise-integration org could mandate.\"\n      location: file:///opt/naftiko/skills/backstage-scaffolding-standard\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability scaffolded from a Backstage template, intended as the \"scaffolding standard a P&G enterprise-integration org could mandate.\"\n        from:\n          sourceNamespace: backstage-scaffolding-standard-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-scaffolding-standard.yaml
tags:
- Naftiko
tools:
- description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
  hints:
    readOnly: true
  name: example
---
