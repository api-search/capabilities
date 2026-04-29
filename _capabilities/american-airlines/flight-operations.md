---
categories:
- travel-booking
consumed_apis:
- aa-runway
description: Unified workflow for travel applications and agents accessing American Airlines flight data, status, and booking capabilities. Serves travel technology teams and booking platform developers.
layout: capability
name: American Airlines Flight Operations
operations:
- description: Search flight schedules
  method: GET
  name: search-flights
  path: /v1/flights
- description: Get flight status
  method: GET
  name: get-flight-status
  path: /v1/flights/{flightId}/status
personas: []
provider_name: American Airlines
provider_slug: american-airlines
search_terms:
- booking
- flight search and schedules
- flight operations
- get real-time status of an american airlines flight
- get flight status
- travel technology
- search flight schedules
- travel
- builds travel apps integrating american airlines flight data
- real-time flight status
- search american airlines flight schedules by origin, destination, and date
- travel app workflow for searching and tracking american airlines flights
- Booking Agent
- Travel Technology Developer
- search flights
- airlines
- developer experience
- flights
- aviation
- american airlines
- uses flight data to assist customers with bookings
slug: flight-operations
source_filename: flight-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: American Airlines Flight Operations\n  description: >-\n    Unified workflow for travel applications and agents accessing American Airlines\n    flight data, status, and booking capabilities. Serves travel technology teams\n    and booking platform developers.\n  tags:\n    - American Airlines\n    - Airlines\n    - Flight Operations\n    - Travel Technology\n    - Booking\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AA_API_KEY: AA_API_KEY\n\ncapability:\n  consumes:\n    - import: aa-runway\n      location: ./shared/runway-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aa-flight-ops-api\n      description: Unified REST API for American Airlines flight operations.\n      resources:\n        - path: /v1/flights\n          name: flights\n          description: Flight search and schedules\n          operations:\n            - method: GET\n      \
  \        name: search-flights\n              description: Search flight schedules\n              call: \"aa-runway.get-flights\"\n              with:\n                origin: \"rest.origin\"\n                destination: \"rest.destination\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flights/{flightId}/status\n          name: flight-status\n          description: Real-time flight status\n          operations:\n            - method: GET\n              name: get-flight-status\n              description: Get flight status\n              call: \"aa-runway.get-flight-status\"\n              with:\n                flightId: \"rest.flightId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: aa-flight-ops-mcp\n      transport: http\n      description: MCP server for AI-assisted\
  \ American Airlines flight operations.\n      tools:\n        - name: search-flights\n          description: Search American Airlines flight schedules by origin, destination, and date\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aa-runway.get-flights\"\n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flight-status\n          description: Get real-time status of an American Airlines flight\n          hints:\n            readOnly: true\n          call: \"aa-runway.get-flight-status\"\n          with:\n            flightId: \"tools.flightId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/american-airlines/refs/heads/main/capabilities/flight-operations.yaml
tags:
- American Airlines
- Airlines
- Flight Operations
- Travel Technology
- Booking
tools:
- description: Search American Airlines flight schedules by origin, destination, and date
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Get real-time status of an American Airlines flight
  hints:
    readOnly: true
  name: get-flight-status
---
