---
categories:
- travel-booking
consumed_apis:
- flight-offers-search
- hotel-search
description: End-to-end travel booking workflow combining flight search, pricing, booking, hotel search, hotel booking, and transfer search for complete trip planning and reservation.
layout: capability
name: Amadeus Full Travel Booking
operations:
- description: Search available flights.
  method: GET
  name: search-flights
  path: /v1/flights/offers
- description: Search available hotels.
  method: GET
  name: search-hotels
  path: /v1/hotels/offers
personas: []
provider_name: Amadeus
provider_slug: amadeus
search_terms:
- transfer search, booking, and management.
- search available hotels.
- developer building travel search and booking applications using amadeus apis.
- search hotels
- hotel search, availability, and booking.
- booking
- OTA Booking Team
- search flights
- search available flights.
- flight search.
- transfers
- flight search, pricing, booking, and order management.
- tourism
- search for available hotel rooms and rates for specific hotel properties.
- online travel agency team managing flight, hotel, and transfer bookings.
- points of interest, tours, activities, and destination data.
- end-to-end trip booking combining flight search, hotel search, and transfer booking.
- search for available flights between two cities on a given date.
- hospitality
- airlines
- flights
- hotel search.
- amadeus
- market insights
- Travel Developer
- destinations
- travel
- hotels
- aviation
slug: travel-booking
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amadeus Full Travel Booking\n  description: End-to-end travel booking workflow combining flight search, pricing, booking, hotel search, hotel booking, and transfer search for complete trip planning and reservation.\n  tags:\n  - Amadeus\n  - Flights\n  - Hotels\n  - Transfers\n  - Booking\n  - Travel\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMADEUS_API_KEY: AMADEUS_API_KEY\n    AMADEUS_API_SECRET: AMADEUS_API_SECRET\n    AMADEUS_BEARER_TOKEN: AMADEUS_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: flight-offers-search\n    location: ./shared/flight-offers-search.yaml\n  - import: hotel-search\n    location: ./shared/hotel-search.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amadeus-travel-booking-api\n    description: Unified travel booking REST API.\n    resources:\n    - path: /v1/flights/offers\n      name: flight-offers\n      description: Flight search.\n   \
  \   operations:\n      - method: GET\n        name: search-flights\n        description: Search available flights.\n        call: flight-offers-search.search-flight-offers\n        with:\n          originLocationCode: rest.originLocationCode\n          destinationLocationCode: rest.destinationLocationCode\n          departureDate: rest.departureDate\n          adults: rest.adults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/offers\n      name: hotel-offers\n      description: Hotel search.\n      operations:\n      - method: GET\n        name: search-hotels\n        description: Search available hotels.\n        call: hotel-search.search-hotel-offers\n        with:\n          hotelIds: rest.hotelIds\n          checkInDate: rest.checkInDate\n          checkOutDate: rest.checkOutDate\n          adults: rest.adults\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amadeus-travel-booking-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted travel planning and booking.\n    tools:\n    - name: search-flights\n      description: Search for available flights between two cities on a given date.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flight-offers-search.search-flight-offers\n      with:\n        originLocationCode: tools.originLocationCode\n        destinationLocationCode: tools.destinationLocationCode\n        departureDate: tools.departureDate\n        adults: tools.adults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-hotels\n      description: Search for available hotel rooms and rates for specific hotel properties.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hotel-search.search-hotel-offers\n      with:\n        hotelIds: tools.hotelIds\n        checkInDate: tools.checkInDate\n        checkOutDate: tools.checkOutDate\n        adults: tools.adults\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amadeus/refs/heads/main/capabilities/travel-booking.yaml
tags:
- Amadeus
- Flights
- Hotels
- Transfers
- Booking
- Travel
tools:
- description: Search for available flights between two cities on a given date.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Search for available hotel rooms and rates for specific hotel properties.
  hints:
    openWorld: true
    readOnly: true
  name: search-hotels
---
