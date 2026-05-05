---
api_specs:
- filename: united-airlines-ndc-openapi.yml
  format: yaml
  label: united-airlines-ndc
  slug: united-airlines-ndc
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-airlines/refs/heads/main/openapi/united-airlines-ndc-openapi.yml
categories: []
consumed_apis:
- united-airlines-ndc
description: United Airlines flight booking and travel management capability combining NDC shopping, booking creation, servicing, and flight status into a unified workflow for travel agencies, corporate booking tools, and online travel platforms.
layout: capability
name: United Airlines Flight Booking
operations:
- description: Search for available United Airlines flights with continuous pricing
  method: POST
  name: search-flight-offers
  path: /v1/offers
- description: Get detailed pricing for a specific offer
  method: GET
  name: get-flight-offer
  path: /v1/offers
- description: Create a new flight booking
  method: POST
  name: create-booking
  path: /v1/bookings
- description: List all bookings
  method: GET
  name: list-bookings
  path: /v1/bookings
- description: Get booking details
  method: GET
  name: get-booking
  path: /v1/bookings/{id}
- description: Cancel a booking
  method: DELETE
  name: cancel-booking
  path: /v1/bookings/{id}
- description: Exchange flights on an existing booking
  method: POST
  name: exchange-booking
  path: /v1/bookings/{id}/exchange
- description: Add seat, bag, or upgrade to a booking
  method: POST
  name: add-ancillary
  path: /v1/bookings/{id}/ancillaries
- description: Get real-time status for a flight
  method: GET
  name: get-flight-status
  path: /v1/flights/status
- description: Get flight schedules for a route
  method: GET
  name: get-flight-schedules
  path: /v1/flights/schedules
personas: []
provider_name: United Airlines
provider_slug: united-airlines
search_terms:
- add ancillary
- add seat, bag, or upgrade to a booking
- flight schedule information
- search flights
- individual booking operations
- book united airlines flights for one or more passengers
- cancel a booking
- ndc
- get flight offer
- fortune 100
- get real-time departure, arrival, and gate status for a united flight
- travel
- real-time flight status
- exchange flights on an existing booking
- create a new flight booking
- cancel a united airlines flight booking
- list bookings
- list existing flight bookings with optional status and date filters
- get real-time status for a flight
- get flight status
- exchange booking
- retrieve details of a specific united airlines booking
- get detailed pricing and availability for a specific flight offer
- create booking
- loyalty
- add seat selection, checked bag, or upgrade to a booking
- get booking details
- search for available united airlines flights with pricing, bundles, and cabin options
- corporate travel
- search flight offers
- shopping
- get united airlines schedules for a specific route and date range
- get detailed pricing for a specific offer
- change flights on an existing booking
- list all bookings
- search for available united airlines flights with continuous pricing
- get flight schedules
- flight offer search and pricing
- booking creation and management
- flight exchange operations
- flight booking
- add ancillary services to booking
- cancel booking
- airlines
- get booking
- get flight schedules for a route
slug: flight-booking
source_filename: flight-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"United Airlines Flight Booking\"\n  description: >-\n    United Airlines flight booking and travel management capability combining NDC shopping,\n    booking creation, servicing, and flight status into a unified workflow for travel agencies,\n    corporate booking tools, and online travel platforms.\n  tags:\n    - Airlines\n    - Travel\n    - Flight Booking\n    - NDC\n    - Corporate Travel\n    - Shopping\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNITED_AIRLINES_OAUTH_TOKEN: UNITED_AIRLINES_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: united-airlines-ndc\n      location: ./shared/united-airlines-ndc.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: united-airlines-booking-api\n      description: \"Unified REST API for United Airlines flight booking and travel management.\"\n      resources:\n        - path: /v1/offers\n          name:\
  \ offers\n          description: \"Flight offer search and pricing\"\n          operations:\n            - method: POST\n              name: search-flight-offers\n              description: \"Search for available United Airlines flights with continuous pricing\"\n              call: \"united-airlines-ndc.search-flight-offers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-flight-offer\n              description: \"Get detailed pricing for a specific offer\"\n              call: \"united-airlines-ndc.get-flight-offer\"\n              with:\n                offerId: \"rest.offerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings\n          name: bookings\n          description: \"Booking creation and management\"\n          operations:\n            - method: POST\n              name: create-booking\n \
  \             description: \"Create a new flight booking\"\n              call: \"united-airlines-ndc.create-booking\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-bookings\n              description: \"List all bookings\"\n              call: \"united-airlines-ndc.list-bookings\"\n              with:\n                status: \"rest.status\"\n                departureDate: \"rest.departureDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/{id}\n          name: booking\n          description: \"Individual booking operations\"\n          operations:\n            - method: GET\n              name: get-booking\n              description: \"Get booking details\"\n              call: \"united-airlines-ndc.get-booking\"\n              with:\n                bookingId: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-booking\n              description: \"Cancel a booking\"\n              call: \"united-airlines-ndc.cancel-booking\"\n              with:\n                bookingId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/{id}/exchange\n          name: booking-exchange\n          description: \"Flight exchange operations\"\n          operations:\n            - method: POST\n              name: exchange-booking\n              description: \"Exchange flights on an existing booking\"\n              call: \"united-airlines-ndc.exchange-booking\"\n              with:\n                bookingId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/{id}/ancillaries\n          name: booking-ancillaries\n\
  \          description: \"Add ancillary services to booking\"\n          operations:\n            - method: POST\n              name: add-ancillary\n              description: \"Add seat, bag, or upgrade to a booking\"\n              call: \"united-airlines-ndc.add-ancillary\"\n              with:\n                bookingId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flights/status\n          name: flight-status\n          description: \"Real-time flight status\"\n          operations:\n            - method: GET\n              name: get-flight-status\n              description: \"Get real-time status for a flight\"\n              call: \"united-airlines-ndc.get-flight-status\"\n              with:\n                flightNumber: \"rest.flightNumber\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/flights/schedules\n          name: flight-schedules\n          description: \"Flight schedule information\"\n          operations:\n            - method: GET\n              name: get-flight-schedules\n              description: \"Get flight schedules for a route\"\n              call: \"united-airlines-ndc.get-flight-schedules\"\n              with:\n                origin: \"rest.origin\"\n                destination: \"rest.destination\"\n                startDate: \"rest.startDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: united-airlines-booking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted United Airlines flight booking and travel management.\"\n      tools:\n        - name: search-flights\n          description: \"Search for available United Airlines flights with pricing, bundles, and cabin options\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"united-airlines-ndc.search-flight-offers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flight-offer\n          description: \"Get detailed pricing and availability for a specific flight offer\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"united-airlines-ndc.get-flight-offer\"\n          with:\n            offerId: \"tools.offerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-booking\n          description: \"Book United Airlines flights for one or more passengers\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"united-airlines-ndc.create-booking\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bookings\n          description: \"List existing\
  \ flight bookings with optional status and date filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"united-airlines-ndc.list-bookings\"\n          with:\n            status: \"tools.status\"\n            departureDate: \"tools.departureDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-booking\n          description: \"Retrieve details of a specific United Airlines booking\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"united-airlines-ndc.get-booking\"\n          with:\n            bookingId: \"tools.bookingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-booking\n          description: \"Cancel a United Airlines flight booking\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"\
  united-airlines-ndc.cancel-booking\"\n          with:\n            bookingId: \"tools.bookingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: exchange-booking\n          description: \"Change flights on an existing booking\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"united-airlines-ndc.exchange-booking\"\n          with:\n            bookingId: \"tools.bookingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-ancillary\n          description: \"Add seat selection, checked bag, or upgrade to a booking\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"united-airlines-ndc.add-ancillary\"\n          with:\n            bookingId: \"tools.bookingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flight-status\n\
  \          description: \"Get real-time departure, arrival, and gate status for a United flight\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"united-airlines-ndc.get-flight-status\"\n          with:\n            flightNumber: \"tools.flightNumber\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flight-schedules\n          description: \"Get United Airlines schedules for a specific route and date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"united-airlines-ndc.get-flight-schedules\"\n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            startDate: \"tools.startDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-airlines/refs/heads/main/capabilities/flight-booking.yaml
tags:
- Airlines
- Travel
- Flight Booking
- NDC
- Corporate Travel
- Shopping
tools:
- description: Search for available United Airlines flights with pricing, bundles, and cabin options
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Get detailed pricing and availability for a specific flight offer
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-offer
- description: Book United Airlines flights for one or more passengers
  hints:
    destructive: false
    readOnly: false
  name: create-booking
- description: List existing flight bookings with optional status and date filters
  hints:
    openWorld: false
    readOnly: true
  name: list-bookings
- description: Retrieve details of a specific United Airlines booking
  hints:
    openWorld: false
    readOnly: true
  name: get-booking
- description: Cancel a United Airlines flight booking
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-booking
- description: Change flights on an existing booking
  hints:
    destructive: false
    readOnly: false
  name: exchange-booking
- description: Add seat selection, checked bag, or upgrade to a booking
  hints:
    destructive: false
    readOnly: false
  name: add-ancillary
- description: Get real-time departure, arrival, and gate status for a United flight
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-status
- description: Get United Airlines schedules for a specific route and date range
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-schedules
---
