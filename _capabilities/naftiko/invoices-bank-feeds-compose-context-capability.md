---
categories: []
consumed_apis: []
description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
layout: capability
name: Invoices Bank Feeds Compose Context Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a composite capability over invoices + bank feeds that returns one shaped accounting-context object for an smb ai assistant.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: invoices-bank-feeds-compose-context-capability
source_filename: invoices-bank-feeds-compose-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Invoices Bank Feeds Compose Context Capability\n  description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: invoices-bank-feeds-compose-context-capability-rest\n    description: REST API for Invoices Bank Feeds Compose Context Capability.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: invoices-bank-feeds-compose-context-capability-mcp\n    description: MCP server exposing Invoices Bank Feeds Compose Context Capability for AI agents.\n    tools:\n    - name: example\n      description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: invoices-bank-feeds-compose-context-capability-skills\n    description: Agent Skill bundle for Invoices Bank Feeds Compose Context Capability.\n    skills:\n    - name: invoices-bank-feeds-compose-context-capability\n      description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.\n\
  \      location: file:///opt/naftiko/skills/invoices-bank-feeds-compose-context-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.\n        from:\n          sourceNamespace: invoices-bank-feeds-compose-context-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/invoices-bank-feeds-compose-context-capability.yaml
tags:
- Naftiko
tools:
- description: A composite capability over Invoices + Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
  hints:
    readOnly: true
  name: example
---
