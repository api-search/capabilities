---
categories: []
consumed_apis: []
description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.
layout: capability
name: Iata Ndc Shopping Context Capability
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
- a capability over the iata ndc airline-distribution surface that returns one shaped agent-context object for an customer-service ai assistant.
- governance
slug: iata-ndc-shopping-context-capability
source_filename: iata-ndc-shopping-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Iata Ndc Shopping Context Capability\n  description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: iata-ndc-shopping-context-capability-rest\n    description: REST API for Iata Ndc Shopping Context Capability.\n    resources:\n    - name: example\n      path: /example\n  \
  \    operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: iata-ndc-shopping-context-capability-mcp\n    description: MCP server exposing Iata Ndc Shopping Context Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: iata-ndc-shopping-context-capability-skills\n    description: Agent Skill bundle for Iata Ndc Shopping Context Capability.\n    skills:\n    - name: iata-ndc-shopping-context-capability\n      description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.\n      location:\
  \ file:///opt/naftiko/skills/iata-ndc-shopping-context-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.\n        from:\n          sourceNamespace: iata-ndc-shopping-context-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/iata-ndc-shopping-context-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an customer-service AI assistant.
  hints:
    readOnly: true
  name: example
---
