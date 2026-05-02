---
categories: []
consumed_apis: []
description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
layout: capability
name: Amadeus Flight Status Rightsize Capability
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
- 'a capability over amadeus / flightaware-style flight-status apis implementing use case #2 (rightsize ai context) for an airline-it api-sprawl scenario.'
- mcp
- example op
- example
- governance
slug: amadeus-flight-status-rightsize-capability
source_filename: amadeus-flight-status-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Amadeus Flight Status Rightsize Capability\n  description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: amadeus-flight-status-rightsize-capability-rest\n    description: REST API for Amadeus Flight Status Rightsize Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: amadeus-flight-status-rightsize-capability-mcp\n    description: MCP server exposing Amadeus Flight Status Rightsize Capability for AI agents.\n    tools:\n    - name: example\n      description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: amadeus-flight-status-rightsize-capability-skills\n    description: Agent Skill bundle for Amadeus Flight Status Rightsize Capability.\n    skills:\n    - name: amadeus-flight-status-rightsize-capability\n      description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize\
  \ AI context) for an airline-IT API-sprawl scenario.'\n      location: file:///opt/naftiko/skills/amadeus-flight-status-rightsize-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'\n        from:\n          sourceNamespace: amadeus-flight-status-rightsize-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/amadeus-flight-status-rightsize-capability.yaml
tags:
- Naftiko
tools:
- description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
  hints:
    readOnly: true
  name: example
---
