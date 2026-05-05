---
api_specs:
- filename: spothero-parking-openapi.yml
  format: yaml
  label: spothero
  slug: spothero
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spothero/refs/heads/main/openapi/spothero-parking-openapi.yml
categories: []
consumed_apis:
- spothero
description: Unified parking mobility workflow capability for SpotHero, enabling navigation apps, rideshare platforms, connected car dashboards, and event management systems to search, book, and manage parking reservations across North America's largest off-street parking network. Covers the full parking lifecycle from search to check-in and cancellation.
layout: capability
name: SpotHero Parking Mobility
operations:
- description: Search for available parking by location and time
  method: GET
  name: search-parking
  path: /v1/search
- description: Get parking facility details, amenities, and directions
  method: GET
  name: get-facility
  path: /v1/facilities/{facility_id}
- description: Check if parking is available at a facility for a time period
  method: GET
  name: get-facility-availability
  path: /v1/facilities/{facility_id}/availability
- description: Get hourly, daily, and event rates for a facility
  method: GET
  name: get-facility-rates
  path: /v1/facilities/{facility_id}/rates
- description: List parking reservations with optional filters
  method: GET
  name: list-reservations
  path: /v1/reservations
- description: Book a parking reservation at a facility
  method: POST
  name: create-reservation
  path: /v1/reservations
- description: Get details for a specific reservation
  method: GET
  name: get-reservation
  path: /v1/reservations/{reservation_id}
- description: Cancel a parking reservation
  method: DELETE
  name: cancel-reservation
  path: /v1/reservations/{reservation_id}
personas: []
provider_name: SpotHero
provider_slug: spothero
search_terms:
- reservations
- create reservation
- create a parking reservation at a facility. returns confirmation code and barcode for facility access.
- check parking availability
- get facility rates
- individual reservation operations
- search parking
- book a parking reservation at a facility
- mobility
- get hourly, daily, and event rates for a facility
- get hourly, daily, event, and monthly pricing rates for a parking facility.
- get facility
- get parking facility details, amenities, and directions
- real-time parking availability at a facility
- transportation
- cancel parking reservation
- cancel a parking reservation. refund eligibility depends on facility policy and cancellation timing.
- get facility availability
- get parking rates
- detailed information about a parking facility
- search for available parking near a location or address for a given time period. returns facility names, prices, availability, and amenities.
- spothero
- check if parking is available at a facility for a time period
- parking
- list reservations
- parking reservation management
- cancel a parking reservation
- search for available parking by location and time
- search for available parking near a destination
- list parking reservations filtered by status, date range, or facility.
- get reservation
- get details for a specific reservation
- pricing rates for a parking facility
- list parking reservations with optional filters
- book parking
- navigation
- cancel reservation
- get detailed information about a specific parking facility including address, amenities, operating hours, and entry/exit instructions.
- get parking facility
- check real-time parking availability and pricing at a specific facility for a time period.
- get full details for a parking reservation including status, barcode, and confirmation code.
slug: parking-mobility
source_filename: parking-mobility.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SpotHero Parking Mobility\"\n  description: >-\n    Unified parking mobility workflow capability for SpotHero, enabling navigation apps,\n    rideshare platforms, connected car dashboards, and event management systems to search,\n    book, and manage parking reservations across North America's largest off-street parking network.\n    Covers the full parking lifecycle from search to check-in and cancellation.\n  tags:\n    - SpotHero\n    - Parking\n    - Mobility\n    - Navigation\n    - Reservations\n    - Transportation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPOTHERO_API_KEY: SPOTHERO_API_KEY\n\ncapability:\n  consumes:\n    - import: spothero\n      location: ./shared/spothero-parking.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: parking-mobility-api\n      description: \"Unified REST API for parking mobility workflows.\"\n      resources:\n\
  \        - path: /v1/search\n          name: parking-search\n          description: \"Search for available parking near a destination\"\n          operations:\n            - method: GET\n              name: search-parking\n              description: \"Search for available parking by location and time\"\n              call: \"spothero.search-parking\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                address: \"rest.address\"\n                starts: \"rest.starts\"\n                ends: \"rest.ends\"\n                radius: \"rest.radius\"\n                vehicle_type: \"rest.vehicle_type\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/facilities/{facility_id}\n          name: facility-details\n          description: \"Detailed information about a parking\
  \ facility\"\n          operations:\n            - method: GET\n              name: get-facility\n              description: \"Get parking facility details, amenities, and directions\"\n              call: \"spothero.get-facility\"\n              with:\n                facility_id: \"rest.facility_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/facilities/{facility_id}/availability\n          name: facility-availability\n          description: \"Real-time parking availability at a facility\"\n          operations:\n            - method: GET\n              name: get-facility-availability\n              description: \"Check if parking is available at a facility for a time period\"\n              call: \"spothero.get-facility-availability\"\n              with:\n                facility_id: \"rest.facility_id\"\n                starts: \"rest.starts\"\n                ends: \"rest.ends\"\n                vehicle_type:\
  \ \"rest.vehicle_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/facilities/{facility_id}/rates\n          name: facility-rates\n          description: \"Pricing rates for a parking facility\"\n          operations:\n            - method: GET\n              name: get-facility-rates\n              description: \"Get hourly, daily, and event rates for a facility\"\n              call: \"spothero.get-facility-rates\"\n              with:\n                facility_id: \"rest.facility_id\"\n                starts: \"rest.starts\"\n                ends: \"rest.ends\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reservations\n          name: reservations\n          description: \"Parking reservation management\"\n          operations:\n            - method: GET\n              name: list-reservations\n              description: \"List parking\
  \ reservations with optional filters\"\n              call: \"spothero.list-reservations\"\n              with:\n                status: \"rest.status\"\n                facility_id: \"rest.facility_id\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-reservation\n              description: \"Book a parking reservation at a facility\"\n              call: \"spothero.create-reservation\"\n              with:\n                facility_id: \"rest.facility_id\"\n                rate_id: \"rest.rate_id\"\n                starts: \"rest.starts\"\n                ends: \"rest.ends\"\n                driver: \"rest.driver\"\n                vehicle: \"rest.vehicle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reservations/{reservation_id}\n\
  \          name: reservation\n          description: \"Individual reservation operations\"\n          operations:\n            - method: GET\n              name: get-reservation\n              description: \"Get details for a specific reservation\"\n              call: \"spothero.get-reservation\"\n              with:\n                reservation_id: \"rest.reservation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-reservation\n              description: \"Cancel a parking reservation\"\n              call: \"spothero.cancel-reservation\"\n              with:\n                reservation_id: \"rest.reservation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: parking-mobility-mcp\n      transport: http\n      description: \"MCP server for AI-assisted parking search,\
  \ booking, and management.\"\n      tools:\n        - name: search-parking\n          description: \"Search for available parking near a location or address for a given time period. Returns facility names, prices, availability, and amenities.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spothero.search-parking\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            address: \"tools.address\"\n            starts: \"tools.starts\"\n            ends: \"tools.ends\"\n            radius: \"tools.radius\"\n            vehicle_type: \"tools.vehicle_type\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-parking-facility\n          description: \"Get detailed information about a specific parking facility including address, amenities, operating hours, and\
  \ entry/exit instructions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spothero.get-facility\"\n          with:\n            facility_id: \"tools.facility_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-parking-availability\n          description: \"Check real-time parking availability and pricing at a specific facility for a time period.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spothero.get-facility-availability\"\n          with:\n            facility_id: \"tools.facility_id\"\n            starts: \"tools.starts\"\n            ends: \"tools.ends\"\n            vehicle_type: \"tools.vehicle_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-parking-rates\n          description: \"Get hourly, daily, event, and monthly pricing rates for a parking\
  \ facility.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spothero.get-facility-rates\"\n          with:\n            facility_id: \"tools.facility_id\"\n            starts: \"tools.starts\"\n            ends: \"tools.ends\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: book-parking\n          description: \"Create a parking reservation at a facility. Returns confirmation code and barcode for facility access.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"spothero.create-reservation\"\n          with:\n            facility_id: \"tools.facility_id\"\n            rate_id: \"tools.rate_id\"\n            starts: \"tools.starts\"\n            ends: \"tools.ends\"\n            driver: \"tools.driver\"\n            vehicle: \"tools.vehicle\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n\n        - name: get-reservation\n          description: \"Get full details for a parking reservation including status, barcode, and confirmation code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spothero.get-reservation\"\n          with:\n            reservation_id: \"tools.reservation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-reservations\n          description: \"List parking reservations filtered by status, date range, or facility.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spothero.list-reservations\"\n          with:\n            status: \"tools.status\"\n            facility_id: \"tools.facility_id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-parking-reservation\n\
  \          description: \"Cancel a parking reservation. Refund eligibility depends on facility policy and cancellation timing.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"spothero.cancel-reservation\"\n          with:\n            reservation_id: \"tools.reservation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spothero/refs/heads/main/capabilities/parking-mobility.yaml
tags:
- SpotHero
- Parking
- Mobility
- Navigation
- Reservations
- Transportation
tools:
- description: Search for available parking near a location or address for a given time period. Returns facility names, prices, availability, and amenities.
  hints:
    openWorld: true
    readOnly: true
  name: search-parking
- description: Get detailed information about a specific parking facility including address, amenities, operating hours, and entry/exit instructions.
  hints:
    openWorld: true
    readOnly: true
  name: get-parking-facility
- description: Check real-time parking availability and pricing at a specific facility for a time period.
  hints:
    openWorld: true
    readOnly: true
  name: check-parking-availability
- description: Get hourly, daily, event, and monthly pricing rates for a parking facility.
  hints:
    openWorld: true
    readOnly: true
  name: get-parking-rates
- description: Create a parking reservation at a facility. Returns confirmation code and barcode for facility access.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: book-parking
- description: Get full details for a parking reservation including status, barcode, and confirmation code.
  hints:
    openWorld: false
    readOnly: true
  name: get-reservation
- description: List parking reservations filtered by status, date range, or facility.
  hints:
    openWorld: false
    readOnly: true
  name: list-reservations
- description: Cancel a parking reservation. Refund eligibility depends on facility policy and cancellation timing.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-parking-reservation
---
