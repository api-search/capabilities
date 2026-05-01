---
categories: []
consumed_apis:
- alaska-flight-status
- alaska-cargo
description: Workflow capability combining Alaska Airlines Flight Status and Cargo APIs for travel operations management. Enables travel agents, corporate travel managers, and freight forwarders to track flights, monitor cargo shipments, and get rate estimates in a unified interface.
layout: capability
name: Alaska Airlines Travel Operations
operations:
- description: List Alaska Airlines flights by route and date
  method: GET
  name: list-flights
  path: /v1/flights
- description: Get real-time status for a specific flight
  method: GET
  name: get-flight-status
  path: /v1/flights/{flightNumber}/status
- description: List cargo shipments
  method: GET
  name: list-cargo-shipments
  path: /v1/cargo/shipments
- description: Book a new cargo shipment
  method: POST
  name: book-cargo-shipment
  path: /v1/cargo/shipments
- description: Track cargo shipment by AWB number
  method: GET
  name: track-cargo-shipment
  path: /v1/cargo/shipments/{awbNumber}
- description: Get cargo rate estimate
  method: POST
  name: get-cargo-rate
  path: /v1/cargo/rates
personas: []
provider_name: Alaska Airlines
provider_slug: alaska-air
search_terms:
- book a new cargo shipment
- Corporate Travel Manager
- get alaska flight status
- cargo shipment booking and listing
- travel
- get rate estimate for alaska air cargo shipment based on origin, destination, weight, and number of pieces.
- get cargo rate estimate
- loyalty
- flight status and scheduling
- real-time flight status
- mileage plan member management and partner miles
- book a new alaska air cargo shipment to 115+ destinations worldwide
- travel operations
- flight status
- travel professional monitoring alaska airlines flight status and delays for customer itinerary management.
- list alaska flights
- alaska airlines
- aviation
- get flight status
- book cargo shipment
- cargo shipment tracking
- cargo
- track cargo shipment by awb number
- get real-time status for a specific alaska airlines flight including departure/arrival times, gate, and delay information.
- cargo booking, tracking, and rate management
- get real-time status for a specific flight
- track alaska air cargo shipment by air waybill number with event history
- list flights
- track cargo shipment
- get cargo rate
- Freight Forwarder
- cargo professional booking and tracking alaska air cargo shipments across 115+ domestic and international destinations.
- list alaska airlines flights by route and date
- airlines
- Travel Agent
- corporate travel manager tracking employee flights on alaska airlines and managing cargo logistics.
- real-time flight status, schedules, and airport data
- list cargo shipments
- flight tracking and cargo management for travel operations
- cargo rate estimation
- list alaska airlines flights for a specific route and date with real-time status, delays, and gate assignments.
slug: travel-operations
source_filename: travel-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Alaska Airlines Travel Operations\n  description: >-\n    Workflow capability combining Alaska Airlines Flight Status and Cargo APIs\n    for travel operations management. Enables travel agents, corporate travel\n    managers, and freight forwarders to track flights, monitor cargo shipments,\n    and get rate estimates in a unified interface.\n  tags:\n    - Alaska Airlines\n    - Travel Operations\n    - Aviation\n    - Cargo\n    - Flight Status\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALASKA_API_KEY: ALASKA_API_KEY\n      ALASKA_CARGO_API_KEY: ALASKA_CARGO_API_KEY\n\ncapability:\n  consumes:\n    - import: alaska-flight-status\n      location: ./shared/flight-status-api.yaml\n    - import: alaska-cargo\n      location: ./shared/cargo-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: alaska-travel-ops-api\n      description: Unified REST API\
  \ for Alaska Airlines travel operations.\n      resources:\n        - path: /v1/flights\n          name: flights\n          description: Flight status and scheduling\n          operations:\n            - method: GET\n              name: list-flights\n              description: List Alaska Airlines flights by route and date\n              call: \"alaska-flight-status.list-flights\"\n              with:\n                originAirport: \"rest.originAirport\"\n                destinationAirport: \"rest.destinationAirport\"\n                flightDate: \"rest.flightDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flights/{flightNumber}/status\n          name: flight-status\n          description: Real-time flight status\n          operations:\n            - method: GET\n              name: get-flight-status\n              description: Get real-time status for a specific flight\n              call: \"alaska-flight-status.get-flight-status\"\
  \n              with:\n                flightNumber: \"rest.flightNumber\"\n                flightDate: \"rest.flightDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cargo/shipments\n          name: cargo-shipments\n          description: Cargo shipment booking and listing\n          operations:\n            - method: GET\n              name: list-cargo-shipments\n              description: List cargo shipments\n              call: \"alaska-cargo.list-shipments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: book-cargo-shipment\n              description: Book a new cargo shipment\n              call: \"alaska-cargo.create-shipment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cargo/shipments/{awbNumber}\n          name: cargo-tracking\n\
  \          description: Cargo shipment tracking\n          operations:\n            - method: GET\n              name: track-cargo-shipment\n              description: Track cargo shipment by AWB number\n              call: \"alaska-cargo.get-shipment\"\n              with:\n                awbNumber: \"rest.awbNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cargo/rates\n          name: cargo-rates\n          description: Cargo rate estimation\n          operations:\n            - method: POST\n              name: get-cargo-rate\n              description: Get cargo rate estimate\n              call: \"alaska-cargo.get-rate-estimate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: alaska-travel-ops-mcp\n      transport: http\n      description: MCP server for AI-assisted Alaska Airlines travel operations.\n\
  \      tools:\n        - name: list-alaska-flights\n          description: >-\n            List Alaska Airlines flights for a specific route and date with\n            real-time status, delays, and gate assignments.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alaska-flight-status.list-flights\"\n          with:\n            originAirport: \"tools.originAirport\"\n            destinationAirport: \"tools.destinationAirport\"\n            flightDate: \"tools.flightDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alaska-flight-status\n          description: >-\n            Get real-time status for a specific Alaska Airlines flight including\n            departure/arrival times, gate, and delay information.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alaska-flight-status.get-flight-status\"\n          with:\n            flightNumber:\
  \ \"tools.flightNumber\"\n            flightDate: \"tools.flightDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cargo-rate-estimate\n          description: >-\n            Get rate estimate for Alaska Air Cargo shipment based on origin,\n            destination, weight, and number of pieces.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alaska-cargo.get-rate-estimate\"\n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            weight: \"tools.weight\"\n            pieces: \"tools.pieces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: book-cargo-shipment\n          description: Book a new Alaska Air Cargo shipment to 115+ destinations worldwide\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"alaska-cargo.create-shipment\"\
  \n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            shipDate: \"tools.shipDate\"\n            weight: \"tools.weight\"\n            pieces: \"tools.pieces\"\n            commodity: \"tools.commodity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-cargo-shipment\n          description: Track Alaska Air Cargo shipment by Air Waybill number with event history\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alaska-cargo.get-shipment\"\n          with:\n            awbNumber: \"tools.awbNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alaska-air/refs/heads/main/capabilities/travel-operations.yaml
tags:
- Alaska Airlines
- Travel Operations
- Aviation
- Cargo
- Flight Status
tools:
- description: List Alaska Airlines flights for a specific route and date with real-time status, delays, and gate assignments.
  hints:
    openWorld: false
    readOnly: true
  name: list-alaska-flights
- description: Get real-time status for a specific Alaska Airlines flight including departure/arrival times, gate, and delay information.
  hints:
    openWorld: false
    readOnly: true
  name: get-alaska-flight-status
- description: Get rate estimate for Alaska Air Cargo shipment based on origin, destination, weight, and number of pieces.
  hints:
    openWorld: false
    readOnly: true
  name: get-cargo-rate-estimate
- description: Book a new Alaska Air Cargo shipment to 115+ destinations worldwide
  hints:
    openWorld: false
    readOnly: false
  name: book-cargo-shipment
- description: Track Alaska Air Cargo shipment by Air Waybill number with event history
  hints:
    openWorld: false
    readOnly: true
  name: track-cargo-shipment
---
