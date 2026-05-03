---
categories: []
consumed_apis: []
description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
layout: capability
name: Event Driven Gap Capability
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
- a capability that explicitly bridges the api/eventdriven/datapipelines gap surfaced in signals — wraps an existing -shaped rest api and exposes both rest + mcp with event-driven adapters layered on.
- governance
- mcp
- capabilities
- ai
slug: event-driven-gap-capability
source_filename: event-driven-gap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Event Driven Gap Capability\n  description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST API and exposes both REST + MCP with event-driven adapters layered on.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: event-driven-gap-capability-rest\n    description: REST API for Event Driven Gap Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: event-driven-gap-capability-mcp\n    description: MCP server exposing Event Driven Gap Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST API and exposes both REST + MCP with event-driven adapters layered on.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: event-driven-gap-capability-skills\n    description: Agent Skill bundle for Event Driven Gap Capability.\n    skills:\n    - name: event-driven-gap-capability\n      description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST\
  \ API and exposes both REST + MCP with event-driven adapters layered on.\n      location: file:///opt/naftiko/skills/event-driven-gap-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST API and exposes both REST + MCP with event-driven adapters layered on.\n        from:\n          sourceNamespace: event-driven-gap-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/event-driven-gap-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Signals — wraps an existing -shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
  hints:
    readOnly: true
  name: example
---
