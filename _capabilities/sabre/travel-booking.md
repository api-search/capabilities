---
categories: []
consumed_apis: []
description: Unified workflow for end-to-end travel booking combining air fare search, hotel availability, and reservation management. Used by travel agencies and OTAs to search and book multi-segment travel itineraries.
layout: capability
name: Sabre Travel Booking
operations:
- description: Search for lowest air fares across Sabre GDS
  method: POST
  name: search-air-fares
  path: /v1/air-fares/search
- description: Re-shop itinerary for current pricing before booking
  method: POST
  name: reshop-air-fares
  path: /v1/air-fares/reshop
- description: Search available hotels with rates and availability
  method: POST
  name: search-hotels
  path: /v1/hotels/search
- description: Get room rates for a specific hotel property
  method: GET
  name: get-hotel-rates
  path: /v1/hotels/{hotel-code}/rates
- description: Create a hotel reservation
  method: POST
  name: create-hotel-reservation
  path: /v1/hotels/reservations
- description: Get hotel reservation details
  method: GET
  name: get-hotel-reservation
  path: /v1/hotels/reservations/{id}
- description: Cancel a hotel reservation
  method: DELETE
  name: cancel-hotel-reservation
  path: /v1/hotels/reservations/{id}
personas: []
provider_name: Sabre
provider_slug: sabre
search_terms:
- travel
- book a hotel room and create a reservation in sabre gds
- hotel room rates
- get room rates for a specific hotel property
- cancel a hotel reservation subject to the property's cancellation policy
- search hotels
- air shopping
- hotel reservation details
- cancel hotel reservation
- search for lowest air fares across sabre gds
- car rental
- re-shop air fare pricing
- create a hotel reservation
- re-shop a previously selected air itinerary to confirm current pricing before booking
- get detailed room types and rate plans for a specific hotel property
- retrieve details of an existing hotel reservation by confirmation number
- booking
- cancel a hotel reservation
- search for lowest air fares with sabre bargain finder max for any origin-destination-date combination
- hotel availability search
- gds
- get hotel reservation details
- hotels
- search available hotels near an airport, city, or coordinates with real-time rates
- air fare search
- re-shop itinerary for current pricing before booking
- create hotel reservation
- get hotel rates
- airlines
- reshop air fares
- hotel reservation management
- get hotel reservation
- search air fares
- search available hotels with rates and availability
slug: travel-booking
source_filename: travel-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sabre Travel Booking\n  description: Unified workflow for end-to-end travel booking combining air fare search, hotel availability, and reservation\n    management. Used by travel agencies and OTAs to search and book multi-segment travel itineraries.\n  tags:\n  - Travel\n  - Airlines\n  - Hotels\n  - GDS\n  - Booking\n  - Air Shopping\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SABRE_ACCESS_TOKEN: SABRE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sabre-bfm\n    baseUri: https://api.sabre.com\n    description: Sabre Bargain Finder Max air shopping API\n    authentication:\n      type: bearer\n      token: '{{SABRE_ACCESS_TOKEN}}'\n    resources:\n    - name: air-shopping\n      path: /v4.0.0/offers/air-fares/bargain-finder-max\n      description: Low-fare air shopping search\n      operations:\n      - name: bargain-finder-max-search\n        method: POST\n      \
  \  description: Search for lowest air fares across Sabre GDS content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            OTA_AirLowFareSearchRQ: '{{tools.search_request}}'\n    - name: air-reshop\n      path: /v4.0.0/offers/air-fares/bargain-finder-max/re-shop\n      description: Re-shop itinerary for updated pricing\n      operations:\n      - name: bargain-finder-max-re-shop\n        method: POST\n        description: Re-shop a previously selected itinerary for current pricing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            OTA_AirLowFareSearchRQ: '{{tools.reshop_request}}'\n  - type: http\n    namespace: sabre-hotels\n    baseUri: https://api.sabre.com\n    description: Sabre Hotels API for search and\
  \ booking\n    authentication:\n      type: bearer\n      token: '{{SABRE_ACCESS_TOKEN}}'\n    resources:\n    - name: hotel-search\n      path: /v2.0.0/offers/hotels\n      description: Hotel availability search\n      operations:\n      - name: search-hotel-availability\n        method: POST\n        description: Search available hotels with rates and availability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            CheckIn: '{{tools.check_in}}'\n            CheckOut: '{{tools.check_out}}'\n            GeoSearch: '{{tools.geo_search}}'\n    - name: hotel-rates\n      path: /v2.0.0/offers/hotels/{hotelCode}/rates\n      description: Hotel room rates\n      operations:\n      - name: get-hotel-rates\n        method: GET\n        description: Get room rates for a specific hotel\n        inputParameters:\n        - name: hotelCode\n          in: path\n\
  \          type: string\n          required: true\n          description: Sabre hotel property code\n        - name: checkIn\n          in: query\n          type: string\n          required: true\n          description: Check-in date (YYYY-MM-DD)\n        - name: checkOut\n          in: query\n          type: string\n          required: true\n          description: Check-out date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hotel-reservations\n      path: /v2.0.0/hotels/reservations\n      description: Hotel reservation management\n      operations:\n      - name: create-hotel-reservation\n        method: POST\n        description: Book a hotel room and create a reservation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            HotelCode: '{{tools.hotel_code}}'\n\
  \            RoomTypeCode: '{{tools.room_type_code}}'\n            CheckIn: '{{tools.check_in}}'\n            CheckOut: '{{tools.check_out}}'\n            GuestInfo: '{{tools.guest_info}}'\n    - name: hotel-reservation-detail\n      path: /v2.0.0/hotels/reservations/{confirmationId}\n      description: Individual reservation management\n      operations:\n      - name: get-hotel-reservation\n        method: GET\n        description: Retrieve hotel reservation details\n        inputParameters:\n        - name: confirmationId\n          in: path\n          type: string\n          required: true\n          description: Reservation confirmation number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-hotel-reservation\n        method: DELETE\n        description: Cancel a hotel reservation\n        inputParameters:\n        - name: confirmationId\n          in: path\n          type: string\n\
  \          required: true\n          description: Reservation confirmation number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: travel-booking-api\n    description: Unified REST API for Sabre travel booking covering air and hotel.\n    resources:\n    - path: /v1/air-fares/search\n      name: air-fare-search\n      description: Air fare search\n      operations:\n      - method: POST\n        name: search-air-fares\n        description: Search for lowest air fares across Sabre GDS\n        call: sabre-bfm.bargain-finder-max-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/air-fares/reshop\n      name: air-fare-reshop\n      description: Re-shop air fare pricing\n      operations:\n      - method: POST\n        name: reshop-air-fares\n        description: Re-shop itinerary for current pricing before\
  \ booking\n        call: sabre-bfm.bargain-finder-max-re-shop\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/search\n      name: hotel-search\n      description: Hotel availability search\n      operations:\n      - method: POST\n        name: search-hotels\n        description: Search available hotels with rates and availability\n        call: sabre-hotels.search-hotel-availability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/{hotel-code}/rates\n      name: hotel-rates\n      description: Hotel room rates\n      operations:\n      - method: GET\n        name: get-hotel-rates\n        description: Get room rates for a specific hotel property\n        call: sabre-hotels.get-hotel-rates\n        with:\n          hotelCode: rest.hotel-code\n          checkIn: rest.checkIn\n          checkOut: rest.checkOut\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/hotels/reservations\n      name: hotel-reservations\n      description: Hotel reservation management\n      operations:\n      - method: POST\n        name: create-hotel-reservation\n        description: Create a hotel reservation\n        call: sabre-hotels.create-hotel-reservation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/reservations/{id}\n      name: hotel-reservation-detail\n      description: Hotel reservation details\n      operations:\n      - method: GET\n        name: get-hotel-reservation\n        description: Get hotel reservation details\n        call: sabre-hotels.get-hotel-reservation\n        with:\n          confirmationId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-hotel-reservation\n        description: Cancel a hotel reservation\n        call: sabre-hotels.cancel-hotel-reservation\n        with:\n          confirmationId:\
  \ rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: travel-booking-mcp\n    transport: http\n    description: MCP server for AI-assisted travel booking combining air and hotel search.\n    tools:\n    - name: search-air-fares\n      description: Search for lowest air fares with Sabre Bargain Finder Max for any origin-destination-date combination\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sabre-bfm.bargain-finder-max-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reshop-air-fares\n      description: Re-shop a previously selected air itinerary to confirm current pricing before booking\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sabre-bfm.bargain-finder-max-re-shop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-hotels\n      description: Search available hotels near\
  \ an airport, city, or coordinates with real-time rates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sabre-hotels.search-hotel-availability\n      with:\n        CheckIn: tools.check_in\n        CheckOut: tools.check_out\n        GeoSearch: tools.geo_search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hotel-rates\n      description: Get detailed room types and rate plans for a specific hotel property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sabre-hotels.get-hotel-rates\n      with:\n        hotelCode: tools.hotel_code\n        checkIn: tools.check_in\n        checkOut: tools.check_out\n        adults: tools.adults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-hotel-reservation\n      description: Book a hotel room and create a reservation in Sabre GDS\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: sabre-hotels.create-hotel-reservation\n      with:\n        HotelCode: tools.hotel_code\n        RoomTypeCode: tools.room_type_code\n        RatePlanCode: tools.rate_plan_code\n        CheckIn: tools.check_in\n        CheckOut: tools.check_out\n        GuestInfo: tools.guest_info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hotel-reservation\n      description: Retrieve details of an existing hotel reservation by confirmation number\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sabre-hotels.get-hotel-reservation\n      with:\n        confirmationId: tools.confirmation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-hotel-reservation\n      description: Cancel a hotel reservation subject to the property's cancellation policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sabre-hotels.cancel-hotel-reservation\n\
  \      with:\n        confirmationId: tools.confirmation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sabre/refs/heads/main/capabilities/travel-booking.yaml
tags:
- Travel
- Airlines
- Hotels
- GDS
- Booking
- Air Shopping
tools:
- description: Search for lowest air fares with Sabre Bargain Finder Max for any origin-destination-date combination
  hints:
    openWorld: true
    readOnly: true
  name: search-air-fares
- description: Re-shop a previously selected air itinerary to confirm current pricing before booking
  hints:
    openWorld: true
    readOnly: true
  name: reshop-air-fares
- description: Search available hotels near an airport, city, or coordinates with real-time rates
  hints:
    openWorld: true
    readOnly: true
  name: search-hotels
- description: Get detailed room types and rate plans for a specific hotel property
  hints:
    openWorld: true
    readOnly: true
  name: get-hotel-rates
- description: Book a hotel room and create a reservation in Sabre GDS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-hotel-reservation
- description: Retrieve details of an existing hotel reservation by confirmation number
  hints:
    openWorld: false
    readOnly: true
  name: get-hotel-reservation
- description: Cancel a hotel reservation subject to the property's cancellation policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-hotel-reservation
---
