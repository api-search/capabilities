---
categories:
- travel-booking
consumed_apis:
- blablacar-bus
description: Workflow capability for end-to-end coach booking on the BlaBlaCar Bus network. Enables OTAs, travel aggregators, and corporate travel platforms to search routes and trips, create bookings, manage tickets, and access station information across European markets.
layout: capability
name: BlaBlaCar Bus Booking
operations:
- description: List available coach routes between stations
  method: GET
  name: list-routes
  path: /v1/routes
- description: Search available trips between stations on a given date
  method: GET
  name: search-trips
  path: /v1/trips
- description: Create a confirmed coach booking
  method: POST
  name: create-booking
  path: /v1/bookings
- description: Retrieve booking details
  method: GET
  name: get-booking
  path: /v1/bookings/{booking_id}
- description: Cancel a booking
  method: DELETE
  name: cancel-booking
  path: /v1/bookings/{booking_id}
- description: Retrieve electronic ticket with QR code
  method: GET
  name: get-ticket
  path: /v1/tickets/{ticket_id}
- description: List stations in the BlaBlaCar Bus network
  method: GET
  name: list-stations
  path: /v1/stations
personas: []
provider_name: BlaBlaCar Bus API
provider_slug: blablacar-bus-api
search_terms:
- cancel an existing blablacar bus booking. refund eligibility depends on the fare type.
- route search, trip availability, and station data
- search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.
- mobility
- create a confirmed coach booking
- retrieve booking details
- list available coach routes between stations
- get booking
- coach
- OTA Developer
- list routes
- list stations
- books and manages coach trips via partner platforms
- books affordable intercity coach travel for business travelers
- retrieve the details of an existing blablacar bus booking including status and tickets.
- books coach tickets for customers as part of multi-modal travel itineraries
- travel
- retrieve an electronic ticket with qr code for passenger validation on a blablacar bus trip.
- europe
- create booking
- trip search with pricing and availability
- Corporate Travel Manager
- search available trips between stations on a given date
- transportation
- create a confirmed blablacar bus booking for one or more passengers on a specific trip.
- integrates blablacar bus into travel booking platforms and aggregators
- electronic ticket retrieval
- list available blablacar bus coach routes between stations across europe.
- buses
- list all stations in the blablacar bus network, optionally filtered by country or search query.
- booking creation and management
- cancel a booking
- booking
- Travel Agent
- station information
- single booking retrieval and cancellation
- cancel booking
- get ticket
- Traveler
- available coach routes in the blablacar bus network
- creating and managing coach reservations
- end-to-end coach booking workflow for otas and travel aggregators
- ticketing
- search trips
- list stations in the blablacar bus network
- ota
- retrieve electronic ticket with qr code
slug: blablacar-bus-booking
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: BlaBlaCar Bus Booking\n  description: >-\n    Workflow capability for end-to-end coach booking on the BlaBlaCar Bus network. Enables\n    OTAs, travel aggregators, and corporate travel platforms to search routes and trips,\n    create bookings, manage tickets, and access station information across European markets.\n  tags:\n    - Booking\n    - Buses\n    - Coach\n    - Europe\n    - Mobility\n    - OTA\n    - Ticketing\n    - Transportation\n    - Travel\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BLABLACAR_BUS_API_KEY: BLABLACAR_BUS_API_KEY\n\ncapability:\n  consumes:\n    - import: blablacar-bus\n      location: ./shared/blablacar-bus-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: blablacar-bus-booking-api\n      description: Unified REST API for BlaBlaCar Bus coach booking and travel planning.\n      resources:\n        - path: /v1/routes\n\
  \          name: routes\n          description: Available coach routes in the BlaBlaCar Bus network\n          operations:\n            - method: GET\n              name: list-routes\n              description: List available coach routes between stations\n              call: \"blablacar-bus.list-routes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trips\n          name: trips\n          description: Trip search with pricing and availability\n          operations:\n            - method: GET\n              name: search-trips\n              description: Search available trips between stations on a given date\n              call: \"blablacar-bus.search-trips\"\n              with:\n                from_station_id: \"rest.from_station_id\"\n                to_station_id: \"rest.to_station_id\"\n                departure_date: \"rest.departure_date\"\n                passengers: \"rest.passengers\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings\n          name: bookings\n          description: Booking creation and management\n          operations:\n            - method: POST\n              name: create-booking\n              description: Create a confirmed coach booking\n              call: \"blablacar-bus.create-booking\"\n              with:\n                trip_id: \"rest.trip_id\"\n                currency: \"rest.currency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/{booking_id}\n          name: booking-detail\n          description: Single booking retrieval and cancellation\n          operations:\n            - method: GET\n              name: get-booking\n              description: Retrieve booking details\n              call: \"blablacar-bus.get-booking\"\n              with:\n                booking_id: \"rest.booking_id\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-booking\n              description: Cancel a booking\n              call: \"blablacar-bus.cancel-booking\"\n              with:\n                booking_id: \"rest.booking_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tickets/{ticket_id}\n          name: tickets\n          description: Electronic ticket retrieval\n          operations:\n            - method: GET\n              name: get-ticket\n              description: Retrieve electronic ticket with QR code\n              call: \"blablacar-bus.get-ticket\"\n              with:\n                ticket_id: \"rest.ticket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stations\n          name: stations\n          description: Station information\n\
  \          operations:\n            - method: GET\n              name: list-stations\n              description: List stations in the BlaBlaCar Bus network\n              call: \"blablacar-bus.list-stations\"\n              with:\n                country_code: \"rest.country_code\"\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: blablacar-bus-booking-mcp\n      transport: http\n      description: MCP server for AI-assisted coach travel booking on the BlaBlaCar Bus network.\n      tools:\n        - name: list-routes\n          description: List available BlaBlaCar Bus coach routes between stations across Europe.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blablacar-bus.list-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-trips\n\
  \          description: Search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blablacar-bus.search-trips\"\n          with:\n            from_station_id: \"tools.from_station_id\"\n            to_station_id: \"tools.to_station_id\"\n            departure_date: \"tools.departure_date\"\n            passengers: \"tools.passengers\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-booking\n          description: Create a confirmed BlaBlaCar Bus booking for one or more passengers on a specific trip.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"blablacar-bus.create-booking\"\n          with:\n            trip_id: \"tools.trip_id\"\n            currency: \"tools.currency\"\
  \n            partner_reference: \"tools.partner_reference\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-booking\n          description: Retrieve the details of an existing BlaBlaCar Bus booking including status and tickets.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"blablacar-bus.get-booking\"\n          with:\n            booking_id: \"tools.booking_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-booking\n          description: Cancel an existing BlaBlaCar Bus booking. Refund eligibility depends on the fare type.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"blablacar-bus.cancel-booking\"\n          with:\n            booking_id: \"tools.booking_id\"\n          outputParameters:\n            - type: object\n             \
  \ mapping: \"$.\"\n        - name: get-ticket\n          description: Retrieve an electronic ticket with QR code for passenger validation on a BlaBlaCar Bus trip.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"blablacar-bus.get-ticket\"\n          with:\n            ticket_id: \"tools.ticket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stations\n          description: List all stations in the BlaBlaCar Bus network, optionally filtered by country or search query.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blablacar-bus.list-stations\"\n          with:\n            country_code: \"tools.country_code\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blablacar-bus-api/refs/heads/main/capabilities/blablacar-bus-booking.yaml
tags:
- Booking
- Buses
- Coach
- Europe
- Mobility
- OTA
- Ticketing
- Transportation
- Travel
tools:
- description: List available BlaBlaCar Bus coach routes between stations across Europe.
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.
  hints:
    openWorld: true
    readOnly: true
  name: search-trips
- description: Create a confirmed BlaBlaCar Bus booking for one or more passengers on a specific trip.
  hints:
    openWorld: false
    readOnly: false
  name: create-booking
- description: Retrieve the details of an existing BlaBlaCar Bus booking including status and tickets.
  hints:
    openWorld: false
    readOnly: true
  name: get-booking
- description: Cancel an existing BlaBlaCar Bus booking. Refund eligibility depends on the fare type.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-booking
- description: Retrieve an electronic ticket with QR code for passenger validation on a BlaBlaCar Bus trip.
  hints:
    openWorld: false
    readOnly: true
  name: get-ticket
- description: List all stations in the BlaBlaCar Bus network, optionally filtered by country or search query.
  hints:
    openWorld: true
    readOnly: true
  name: list-stations
---
