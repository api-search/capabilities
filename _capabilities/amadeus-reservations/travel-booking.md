---
categories:
- travel-booking
consumed_apis:
- hotel-booking
- flight-orders
- transfer-booking
description: Unified workflow capability for complete travel booking encompassing flight reservations, hotel bookings, and ground transfer arrangements. Used by online travel agencies, travel chatbots, and corporate travel management platforms to create end-to-end trip reservations.
layout: capability
name: Amadeus Travel Booking
operations:
- description: Create a confirmed flight booking.
  method: POST
  name: create-flight-order
  path: /v1/bookings/flights
- description: Retrieve a flight booking.
  method: GET
  name: get-flight-order
  path: /v1/bookings/flights/{orderId}
- description: Cancel a flight booking.
  method: DELETE
  name: cancel-flight-order
  path: /v1/bookings/flights/{orderId}
- description: Create a confirmed hotel booking.
  method: POST
  name: create-hotel-order
  path: /v1/bookings/hotels
- description: Create a confirmed transfer booking.
  method: POST
  name: create-transfer-order
  path: /v1/bookings/transfers
- description: Cancel a transfer booking.
  method: DELETE
  name: cancel-transfer-order
  path: /v1/bookings/transfers/{transferOrderId}
personas: []
provider_name: Amadeus Reservations
provider_slug: amadeus-reservations
search_terms:
- retrieve details of an existing flight reservation by order id.
- reservations
- cancel flight order
- travel
- individual flight order management.
- hotel reservation operations.
- create a confirmed hotel booking.
- airline reservation creation and management.
- create flight order
- create transfer order
- flight reservation operations.
- cancel transfer booking
- cancel flight booking
- developer building ai-powered travel assistants that create bookings conversationally.
- get flight order
- create transfer booking
- retrieve a flight booking.
- create flight booking
- ground transfer reservation operations.
- create a confirmed airline reservation from a priced flight offer.
- Travel Chatbot Developer
- cancel a transfer booking.
- create hotel order
- cancel an existing confirmed flight reservation.
- cancel transfer order
- create a confirmed transfer booking.
- cancel an existing confirmed ground transfer reservation.
- hotel reservation creation.
- booking
- amadeus
- book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
- get flight booking
- ground transportation booking and management.
- create hotel booking
- end-to-end travel booking combining flights, hotels, and transfers.
- flights
- transfers
- cancel a flight booking.
- create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
- individual transfer management.
- Travel Booking Agent
- human or automated agent creating and managing travel reservations on behalf of travelers.
- create a confirmed flight booking.
- hotels
slug: travel-booking
source_filename: travel-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amadeus Travel Booking\n  description: >-\n    Unified workflow capability for complete travel booking encompassing flight\n    reservations, hotel bookings, and ground transfer arrangements. Used by\n    online travel agencies, travel chatbots, and corporate travel management\n    platforms to create end-to-end trip reservations.\n  tags:\n    - Amadeus\n    - Booking\n    - Flights\n    - Hotels\n    - Transfers\n    - Travel\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMADEUS_API_KEY: AMADEUS_API_KEY\n      AMADEUS_API_SECRET: AMADEUS_API_SECRET\n      AMADEUS_BEARER_TOKEN: AMADEUS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: hotel-booking\n      location: ./shared/hotel-booking.yaml\n    - import: flight-orders\n      location: ./shared/flight-orders.yaml\n    - import: transfer-booking\n      location: ./shared/transfer-booking.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: travel-booking-api\n      description: Unified REST API for multi-modal travel booking.\n      resources:\n        - path: /v1/bookings/flights\n          name: flight-bookings\n          description: Flight reservation operations.\n          operations:\n            - method: POST\n              name: create-flight-order\n              description: Create a confirmed flight booking.\n              call: \"flight-orders.create-flight-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/flights/{orderId}\n          name: flight-order\n          description: Individual flight order management.\n          operations:\n            - method: GET\n              name: get-flight-order\n              description: Retrieve a flight booking.\n              call: \"flight-orders.get-flight-order\"\n              with:\n                orderId: \"rest.orderId\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-flight-order\n              description: Cancel a flight booking.\n              call: \"flight-orders.delete-flight-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/hotels\n          name: hotel-bookings\n          description: Hotel reservation operations.\n          operations:\n            - method: POST\n              name: create-hotel-order\n              description: Create a confirmed hotel booking.\n              call: \"hotel-booking.create-hotel-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/transfers\n          name: transfer-bookings\n          description: Ground transfer reservation\
  \ operations.\n          operations:\n            - method: POST\n              name: create-transfer-order\n              description: Create a confirmed transfer booking.\n              call: \"transfer-booking.create-transfer-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookings/transfers/{transferOrderId}\n          name: transfer-order\n          description: Individual transfer management.\n          operations:\n            - method: DELETE\n              name: cancel-transfer-order\n              description: Cancel a transfer booking.\n              call: \"transfer-booking.cancel-transfer-order\"\n              with:\n                transferOrderId: \"rest.transferOrderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: travel-booking-mcp\n      transport: http\n      description: MCP server\
  \ for AI-assisted travel booking across flights, hotels, and transfers.\n      tools:\n        - name: create-flight-booking\n          description: Create a confirmed airline reservation from a priced flight offer.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"flight-orders.create-flight-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flight-booking\n          description: Retrieve details of an existing flight reservation by order ID.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight-orders.get-flight-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-flight-booking\n          description: Cancel an existing confirmed flight reservation.\n          hints:\n   \
  \         readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"flight-orders.delete-flight-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-hotel-booking\n          description: Create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"hotel-booking.create-hotel-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-transfer-booking\n          description: Book a ground transfer (airport taxi, private car, or shuttle) for a traveler.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"transfer-booking.create-transfer-order\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-transfer-booking\n          description: Cancel an existing confirmed ground transfer reservation.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"transfer-booking.cancel-transfer-order\"\n          with:\n            transferOrderId: \"tools.transferOrderId\"\n            confirmNbr: \"tools.confirmNbr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amadeus-reservations/refs/heads/main/capabilities/travel-booking.yaml
tags:
- Amadeus
- Booking
- Flights
- Hotels
- Transfers
- Travel
tools:
- description: Create a confirmed airline reservation from a priced flight offer.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-flight-booking
- description: Retrieve details of an existing flight reservation by order ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-booking
- description: Cancel an existing confirmed flight reservation.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-flight-booking
- description: Create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-hotel-booking
- description: Book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-transfer-booking
- description: Cancel an existing confirmed ground transfer reservation.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-transfer-booking
---
