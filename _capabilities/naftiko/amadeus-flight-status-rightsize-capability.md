---
categories: []
consumed_apis: []
description: A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case
layout: capability
name: Amadeus Flight Status Rightsize Capability
operations:
- description: Return a compact subset of Amadeus flight-status data tuned for AI context (gate, terminal, status, deltas only).
  method: GET
  name: get-flight-status-rightsized
  path: /flights/{{carrier}}/{{number}}/{{date}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- flightaware
- get flight status rightsized
- compact flight-status payload for ai context.
- return a compact subset of amadeus flight-status data tuned for ai context (gate, terminal, status, deltas only).
- api integration
- governance
- spec-driven integration
- rightsize
- ai
- mcp
- capabilities
- amadeus
slug: amadeus-flight-status-rightsize-capability
source_filename: amadeus-flight-status-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Amadeus Flight Status Rightsize Capability\n  description: A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.\n  tags: [Naftiko, Amadeus, FlightAware, Rightsize]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: amadeus-env\n  description: Amadeus Self-Service API OAuth bearer.\n  keys: {AMADEUS_TOKEN: AMADEUS_TOKEN}\ncapability:\n  consumes:\n  - namespace: amadeus\n    type: http\n    baseUri: https://api.amadeus.com\n    authentication: {type: bearer, token: '{{AMADEUS_TOKEN}}'}\n    resources:\n    - name: flight-status\n      path: /v2/schedule/flights\n      operations:\n      - name: get-flight-status\n        method: GET\n        inputParameters:\n        - {name: carrierCode, in: query, description: IATA carrier code.}\n        - {name: flightNumber, in: query}\n        - {name: scheduledDepartureDate, in:\
  \ query}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: amadeus-flight-status-rightsize-capability-rest\n    description: Right-sized flight-status endpoint that returns only the fields an AI agent needs.\n    resources:\n    - name: flight-status\n      path: /flights/{{carrier}}/{{number}}/{{date}}\n      operations:\n      - method: GET\n        name: get-flight-status-rightsized\n        description: Return a compact subset of Amadeus flight-status data tuned for AI context (gate, terminal, status, deltas only).\n        inputParameters:\n        - {name: carrier, in: path, type: string}\n        - {name: number, in: path, type: string}\n        - {name: date, in: path, type: string, description: 'YYYY-MM-DD'}\n        call: amadeus.get-flight-status\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: amadeus-flight-status-rightsize-capability-mcp\n    description: MCP server exposing right-sized flight status for agents.\n    tools:\n\
  \    - name: get-flight-status-rightsized\n      description: Compact flight-status payload for AI context.\n      hints: {readOnly: true}\n      inputParameters:\n      - {name: carrier, type: string, required: true}\n      - {name: number, type: string, required: true}\n      - {name: date, type: string, required: true}\n      call: amadeus.get-flight-status\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: amadeus-flight-status-rightsize-capability-skills\n    description: Skill bundle for right-sized flight status.\n    skills:\n    - name: amadeus-flight-status-rightsize-capability\n      description: Compact flight-status responses for AI agents.\n      location: file:///opt/naftiko/skills/amadeus-flight-status-rightsize-capability\n      allowed-tools: get-flight-status-rightsized\n      tools:\n      - {name: get-flight-status-rightsized, from: {sourceNamespace: amadeus-flight-status-rightsize-capability-mcp, action: get-flight-status-rightsized}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/amadeus-flight-status-rightsize-capability.yaml
tags:
- Naftiko
- Amadeus
- FlightAware
- Rightsize
tools:
- description: Compact flight-status payload for AI context.
  hints:
    readOnly: true
  name: get-flight-status-rightsized
---
