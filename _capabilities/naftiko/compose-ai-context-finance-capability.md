---
categories: []
consumed_apis: []
description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
layout: capability
name: Compose Ai Context Finance Capability
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
- compose ai context (#5) showing accounting + finance + customer apis as multi-source context for an ai assistant.
- governance
- mcp
- capabilities
- ai
slug: compose-ai-context-finance-capability
source_filename: compose-ai-context-finance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compose Ai Context Finance Capability\n  description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compose-ai-context-finance-capability-rest\n    description: REST API for Compose Ai Context Finance Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compose-ai-context-finance-capability-mcp\n    description: MCP server exposing Compose Ai Context Finance Capability for AI agents.\n    tools:\n    - name: example\n      description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compose-ai-context-finance-capability-skills\n    description: Agent Skill bundle for Compose Ai Context Finance Capability.\n    skills:\n    - name: compose-ai-context-finance-capability\n      description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.\n      location: file:///opt/naftiko/skills/compose-ai-context-finance-capability\n      allowed-tools:\
  \ example\n      tools:\n      - name: example\n        description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.\n        from:\n          sourceNamespace: compose-ai-context-finance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compose-ai-context-finance-capability.yaml
tags:
- Naftiko
tools:
- description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
  hints:
    readOnly: true
  name: example
---
