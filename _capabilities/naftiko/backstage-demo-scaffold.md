---
categories: []
consumed_apis: []
description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
layout: capability
name: Backstage Demo Scaffold
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability scaffolded entirely from the naftiko templates for backstage workflow, intended as daniel's 2-minute live-demo sequence at apidays munich (choose template → generated repo → running engine).
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: backstage-demo-scaffold
source_filename: backstage-demo-scaffold.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Demo Scaffold\n  description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-demo-scaffold-rest\n    description: REST API for Backstage Demo Scaffold.\n    resources:\n    - name: example\n  \
  \    path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-demo-scaffold-mcp\n    description: MCP server exposing Backstage Demo Scaffold for AI agents.\n    tools:\n    - name: example\n      description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-demo-scaffold-skills\n    description: Agent Skill bundle for Backstage Demo Scaffold.\n    skills:\n    - name: backstage-demo-scaffold\n      description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays\
  \ Munich (Choose template → generated repo → running engine).\n      location: file:///opt/naftiko/skills/backstage-demo-scaffold\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).\n        from:\n          sourceNamespace: backstage-demo-scaffold-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-demo-scaffold.yaml
tags:
- Naftiko
tools:
- description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
  hints:
    readOnly: true
  name: example
---
