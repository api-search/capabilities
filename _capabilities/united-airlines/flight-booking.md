---
categories: []
consumed_apis: []
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
- search flights
- individual booking operations
- add ancillary services to booking
- get booking details
- flight exchange operations
- get flight schedules for a route
- loyalty
- list bookings
- add seat selection, checked bag, or upgrade to a booking
- get flight offer
- get detailed pricing for a specific offer
- exchange flights on an existing booking
- fortune 100
- search for available united airlines flights with continuous pricing
- create booking
- get booking
- add ancillary
- retrieve details of a specific united airlines booking
- cancel a booking
- list all bookings
- add seat, bag, or upgrade to a booking
- get flight schedules
- list existing flight bookings with optional status and date filters
- search flight offers
- book united airlines flights for one or more passengers
- real-time flight status
- corporate travel
- flight schedule information
- get real-time departure, arrival, and gate status for a united flight
- exchange booking
- travel
- search for available united airlines flights with pricing, bundles, and cabin options
- ndc
- shopping
- flight offer search and pricing
- get flight status
- get united airlines schedules for a specific route and date range
- cancel booking
- get detailed pricing and availability for a specific flight offer
- cancel a united airlines flight booking
- create a new flight booking
- get real-time status for a flight
- change flights on an existing booking
- flight booking
- airlines
- booking creation and management
slug: flight-booking
source_filename: flight-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: United Airlines Flight Booking\n  description: United Airlines flight booking and travel management capability combining NDC shopping, booking creation, servicing,\n    and flight status into a unified workflow for travel agencies, corporate booking tools, and online travel platforms.\n  tags:\n  - Airlines\n  - Travel\n  - Flight Booking\n  - NDC\n  - Corporate Travel\n  - Shopping\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNITED_AIRLINES_OAUTH_TOKEN: UNITED_AIRLINES_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: united-airlines-ndc\n    baseUri: https://api.united.com/v1\n    description: United Airlines NDC API for flight shopping, booking, and servicing.\n    authentication:\n      type: bearer\n      token: '{{UNITED_AIRLINES_OAUTH_TOKEN}}'\n    resources:\n    - name: shopping\n      path: /shopping\n      description: Flight search and pricing\n      operations:\n\
  \      - name: search-flight-offers\n        method: POST\n        description: Search for available United Airlines flights with continuous pricing\n        inputParameters:\n        - name: origin\n          in: body\n          type: string\n          required: true\n          description: IATA origin airport code\n        - name: destination\n          in: body\n          type: string\n          required: true\n          description: IATA destination airport code\n        - name: departureDate\n          in: body\n          type: string\n          required: true\n          description: Outbound departure date (YYYY-MM-DD)\n        - name: cabinPreference\n          in: body\n          type: string\n          required: false\n          description: Preferred cabin class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flight-offer\n        method: GET\n        description: Retrieve detailed\
  \ pricing and availability for a specific flight offer\n        inputParameters:\n        - name: offerId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the flight offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings\n      path: /bookings\n      description: Flight bookings and reservation management\n      operations:\n      - name: create-booking\n        method: POST\n        description: Create a new flight booking with payment\n        inputParameters:\n        - name: offerId\n          in: body\n          type: string\n          required: true\n          description: Offer ID from shopping response\n        - name: holdBooking\n          in: body\n          type: boolean\n          required: false\n          description: Create a held booking without immediate payment\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: list-bookings\n        method: GET\n        description: Retrieve a list of bookings\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter bookings by status\n        - name: departureDate\n          in: query\n          type: string\n          required: false\n          description: Filter by departure date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-booking\n        method: GET\n        description: Retrieve details of a specific booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: Unique booking identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: cancel-booking\n        method: DELETE\n        description: Cancel an existing booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: Unique booking identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servicing\n      path: /bookings\n      description: Post-booking modifications and ancillaries\n      operations:\n      - name: exchange-booking\n        method: POST\n        description: Modify booking by exchanging flights\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: Unique booking identifier\n        - name: newOfferId\n          in: body\n          type: string\n          required: true\n          description: New offer ID for the exchanged\
  \ flights\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refund-booking\n        method: POST\n        description: Process a refund for a cancelled booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: Unique booking identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-ancillary\n        method: POST\n        description: Add ancillary services to an existing booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: Unique booking identifier\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Ancillary type (seat, bag, upgrade, insurance,\
  \ lounge)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flights\n      path: /flights\n      description: Flight status and schedules\n      operations:\n      - name: get-flight-status\n        method: GET\n        description: Retrieve real-time flight status\n        inputParameters:\n        - name: flightNumber\n          in: query\n          type: string\n          required: true\n          description: United Airlines flight number\n        - name: date\n          in: query\n          type: string\n          required: true\n          description: Flight date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flight-schedules\n        method: GET\n        description: Retrieve flight schedules for an origin-destination pair\n        inputParameters:\n        - name: origin\n      \
  \    in: query\n          type: string\n          required: true\n          description: IATA origin airport code\n        - name: destination\n          in: query\n          type: string\n          required: true\n          description: IATA destination airport code\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date for schedule query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: united-airlines-booking-api\n    description: Unified REST API for United Airlines flight booking and travel management.\n    resources:\n    - path: /v1/offers\n      name: offers\n      description: Flight offer search and pricing\n      operations:\n      - method: POST\n        name: search-flight-offers\n        description: Search for available United Airlines flights with continuous\
  \ pricing\n        call: united-airlines-ndc.search-flight-offers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-flight-offer\n        description: Get detailed pricing for a specific offer\n        call: united-airlines-ndc.get-flight-offer\n        with:\n          offerId: rest.offerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings\n      name: bookings\n      description: Booking creation and management\n      operations:\n      - method: POST\n        name: create-booking\n        description: Create a new flight booking\n        call: united-airlines-ndc.create-booking\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-bookings\n        description: List all bookings\n        call: united-airlines-ndc.list-bookings\n        with:\n          status: rest.status\n          departureDate: rest.departureDate\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings/{id}\n      name: booking\n      description: Individual booking operations\n      operations:\n      - method: GET\n        name: get-booking\n        description: Get booking details\n        call: united-airlines-ndc.get-booking\n        with:\n          bookingId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-booking\n        description: Cancel a booking\n        call: united-airlines-ndc.cancel-booking\n        with:\n          bookingId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings/{id}/exchange\n      name: booking-exchange\n      description: Flight exchange operations\n      operations:\n      - method: POST\n        name: exchange-booking\n        description: Exchange flights on an existing booking\n        call: united-airlines-ndc.exchange-booking\n\
  \        with:\n          bookingId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bookings/{id}/ancillaries\n      name: booking-ancillaries\n      description: Add ancillary services to booking\n      operations:\n      - method: POST\n        name: add-ancillary\n        description: Add seat, bag, or upgrade to a booking\n        call: united-airlines-ndc.add-ancillary\n        with:\n          bookingId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flights/status\n      name: flight-status\n      description: Real-time flight status\n      operations:\n      - method: GET\n        name: get-flight-status\n        description: Get real-time status for a flight\n        call: united-airlines-ndc.get-flight-status\n        with:\n          flightNumber: rest.flightNumber\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/flights/schedules\n      name: flight-schedules\n      description: Flight schedule information\n      operations:\n      - method: GET\n        name: get-flight-schedules\n        description: Get flight schedules for a route\n        call: united-airlines-ndc.get-flight-schedules\n        with:\n          origin: rest.origin\n          destination: rest.destination\n          startDate: rest.startDate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: united-airlines-booking-mcp\n    transport: http\n    description: MCP server for AI-assisted United Airlines flight booking and travel management.\n    tools:\n    - name: search-flights\n      description: Search for available United Airlines flights with pricing, bundles, and cabin options\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-airlines-ndc.search-flight-offers\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: get-flight-offer\n      description: Get detailed pricing and availability for a specific flight offer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-airlines-ndc.get-flight-offer\n      with:\n        offerId: tools.offerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-booking\n      description: Book United Airlines flights for one or more passengers\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-airlines-ndc.create-booking\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bookings\n      description: List existing flight bookings with optional status and date filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-airlines-ndc.list-bookings\n      with:\n        status: tools.status\n        departureDate: tools.departureDate\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-booking\n      description: Retrieve details of a specific United Airlines booking\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-airlines-ndc.get-booking\n      with:\n        bookingId: tools.bookingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-booking\n      description: Cancel a United Airlines flight booking\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: united-airlines-ndc.cancel-booking\n      with:\n        bookingId: tools.bookingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exchange-booking\n      description: Change flights on an existing booking\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-airlines-ndc.exchange-booking\n      with:\n        bookingId: tools.bookingId\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: add-ancillary\n      description: Add seat selection, checked bag, or upgrade to a booking\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-airlines-ndc.add-ancillary\n      with:\n        bookingId: tools.bookingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight-status\n      description: Get real-time departure, arrival, and gate status for a United flight\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-airlines-ndc.get-flight-status\n      with:\n        flightNumber: tools.flightNumber\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight-schedules\n      description: Get United Airlines schedules for a specific route and date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-airlines-ndc.get-flight-schedules\n      with:\n        origin:\
  \ tools.origin\n        destination: tools.destination\n        startDate: tools.startDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
