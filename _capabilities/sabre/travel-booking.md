---
api_specs:
- filename: sabre-bargain-finder-max-openapi.yml
  format: yaml
  label: sabre-bfm
  slug: sabre-bfm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sabre/refs/heads/main/openapi/sabre-bargain-finder-max-openapi.yml
- filename: sabre-hotels-openapi.yml
  format: yaml
  label: sabre-hotels
  slug: sabre-hotels
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sabre/refs/heads/main/openapi/sabre-hotels-openapi.yml
categories: []
consumed_apis:
- sabre-bfm
- sabre-hotels
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
- gds
- search available hotels near an airport, city, or coordinates with real-time rates
- get hotel reservation
- create a hotel reservation
- cancel a hotel reservation
- travel
- search air fares
- air shopping
- cancel a hotel reservation subject to the property's cancellation policy
- re-shop a previously selected air itinerary to confirm current pricing before booking
- get room rates for a specific hotel property
- hotel room rates
- hotel reservation management
- hotel availability search
- cancel hotel reservation
- re-shop itinerary for current pricing before booking
- search for lowest air fares across sabre gds
- hotel reservation details
- book a hotel room and create a reservation in sabre gds
- airlines
- search for lowest air fares with sabre bargain finder max for any origin-destination-date combination
- create hotel reservation
- retrieve details of an existing hotel reservation by confirmation number
- get hotel reservation details
- search available hotels with rates and availability
- car rental
- get hotel rates
- get detailed room types and rate plans for a specific hotel property
- search hotels
- reshop air fares
- re-shop air fare pricing
- hotels
- booking
- air fare search
slug: travel-booking
source_filename: travel-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sabre Travel Booking\"\n  description: \"Unified workflow for end-to-end travel booking combining air fare search, hotel availability, and reservation management. Used by travel agencies and OTAs to search and book multi-segment travel itineraries.\"\n  tags:\n    - Travel\n    - Airlines\n    - Hotels\n    - GDS\n    - Booking\n    - Air Shopping\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SABRE_ACCESS_TOKEN: SABRE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: sabre-bfm\n      location: ./shared/sabre-bargain-finder-max.yaml\n    - import: sabre-hotels\n      location: ./shared/sabre-hotels.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: travel-booking-api\n      description: \"Unified REST API for Sabre travel booking covering air and hotel.\"\n      resources:\n        - path: /v1/air-fares/search\n          name: air-fare-search\n\
  \          description: \"Air fare search\"\n          operations:\n            - method: POST\n              name: search-air-fares\n              description: \"Search for lowest air fares across Sabre GDS\"\n              call: \"sabre-bfm.bargain-finder-max-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/air-fares/reshop\n          name: air-fare-reshop\n          description: \"Re-shop air fare pricing\"\n          operations:\n            - method: POST\n              name: reshop-air-fares\n              description: \"Re-shop itinerary for current pricing before booking\"\n              call: \"sabre-bfm.bargain-finder-max-re-shop\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/search\n          name: hotel-search\n          description: \"Hotel availability search\"\n          operations:\n            - method:\
  \ POST\n              name: search-hotels\n              description: \"Search available hotels with rates and availability\"\n              call: \"sabre-hotels.search-hotel-availability\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/{hotel-code}/rates\n          name: hotel-rates\n          description: \"Hotel room rates\"\n          operations:\n            - method: GET\n              name: get-hotel-rates\n              description: \"Get room rates for a specific hotel property\"\n              call: \"sabre-hotels.get-hotel-rates\"\n              with:\n                hotelCode: \"rest.hotel-code\"\n                checkIn: \"rest.checkIn\"\n                checkOut: \"rest.checkOut\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/reservations\n          name: hotel-reservations\n          description: \"Hotel reservation\
  \ management\"\n          operations:\n            - method: POST\n              name: create-hotel-reservation\n              description: \"Create a hotel reservation\"\n              call: \"sabre-hotels.create-hotel-reservation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/reservations/{id}\n          name: hotel-reservation-detail\n          description: \"Hotel reservation details\"\n          operations:\n            - method: GET\n              name: get-hotel-reservation\n              description: \"Get hotel reservation details\"\n              call: \"sabre-hotels.get-hotel-reservation\"\n              with:\n                confirmationId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-hotel-reservation\n              description: \"Cancel a hotel reservation\"\n    \
  \          call: \"sabre-hotels.cancel-hotel-reservation\"\n              with:\n                confirmationId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: travel-booking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted travel booking combining air and hotel search.\"\n      tools:\n        - name: search-air-fares\n          description: \"Search for lowest air fares with Sabre Bargain Finder Max for any origin-destination-date combination\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sabre-bfm.bargain-finder-max-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reshop-air-fares\n          description: \"Re-shop a previously selected air itinerary to confirm current pricing before booking\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"sabre-bfm.bargain-finder-max-re-shop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-hotels\n          description: \"Search available hotels near an airport, city, or coordinates with real-time rates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sabre-hotels.search-hotel-availability\"\n          with:\n            CheckIn: \"tools.check_in\"\n            CheckOut: \"tools.check_out\"\n            GeoSearch: \"tools.geo_search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-hotel-rates\n          description: \"Get detailed room types and rate plans for a specific hotel property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sabre-hotels.get-hotel-rates\"\n          with:\n            hotelCode: \"tools.hotel_code\"\
  \n            checkIn: \"tools.check_in\"\n            checkOut: \"tools.check_out\"\n            adults: \"tools.adults\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-hotel-reservation\n          description: \"Book a hotel room and create a reservation in Sabre GDS\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sabre-hotels.create-hotel-reservation\"\n          with:\n            HotelCode: \"tools.hotel_code\"\n            RoomTypeCode: \"tools.room_type_code\"\n            RatePlanCode: \"tools.rate_plan_code\"\n            CheckIn: \"tools.check_in\"\n            CheckOut: \"tools.check_out\"\n            GuestInfo: \"tools.guest_info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-hotel-reservation\n          description: \"Retrieve details of an existing hotel reservation\
  \ by confirmation number\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sabre-hotels.get-hotel-reservation\"\n          with:\n            confirmationId: \"tools.confirmation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-hotel-reservation\n          description: \"Cancel a hotel reservation subject to the property's cancellation policy\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sabre-hotels.cancel-hotel-reservation\"\n          with:\n            confirmationId: \"tools.confirmation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
