---
categories:
- travel-booking
consumed_apis:
- flight-offers-search
- flight-offers-price
description: Unified workflow capability for complete flight shopping encompassing search, pricing, upsell, and seat selection. Used by OTA developers, airline retailing platforms, and travel chatbots to build end-to-end flight shopping experiences.
layout: capability
name: Amadeus Flight Shopping
operations:
- description: Search available flights by origin, destination, and date.
  method: GET
  name: search-flights
  path: /v1/flights/search
- description: Confirm current price and availability.
  method: POST
  name: confirm-price
  path: /v1/flights/price
personas: []
provider_name: Amadeus Solutions
provider_slug: amadeus-solutions
search_terms:
- search for available flights between two airports on a given date, with options for cabin class and passenger count.
- developer building online travel agency flight search and booking flows.
- airlines
- travel technology
- developer building conversational travel assistants for flight search.
- search for available flight offers.
- price confirmation and validation before booking.
- shopping
- travel
- confirm current price and availability.
- Travel Chatbot Developer
- confirm flight price
- upsell, seat selection, and add-on services.
- confirm price
- amadeus
- complete flight shopping flow from search through price confirmation.
- hotels
- advanced flight search with complex criteria using request body for multi-city and detailed filters.
- confirm pricing for a selected flight offer.
- flight offer discovery and comparison.
- search
- confirm the current price and availability of a selected flight offer before creating a booking.
- search flights advanced
- booking
- flights
- search flights
- search available flights by origin, destination, and date.
- pricing
- gds
- OTA Developer
slug: flight-shopping
source_filename: flight-shopping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amadeus Flight Shopping\n  description: >-\n    Unified workflow capability for complete flight shopping encompassing\n    search, pricing, upsell, and seat selection. Used by OTA developers,\n    airline retailing platforms, and travel chatbots to build end-to-end\n    flight shopping experiences.\n  tags:\n    - Amadeus\n    - Flights\n    - Shopping\n    - Search\n    - Pricing\n    - Travel\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMADEUS_BEARER_TOKEN: AMADEUS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: flight-offers-search\n      location: ./shared/flight-offers-search.yaml\n    - import: flight-offers-price\n      location: ./shared/flight-offers-price.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: flight-shopping-api\n      description: Unified REST API for flight search, pricing, and ancillary selection.\n      resources:\n\
  \        - path: /v1/flights/search\n          name: flight-search\n          description: Search for available flight offers.\n          operations:\n            - method: GET\n              name: search-flights\n              description: Search available flights by origin, destination, and date.\n              call: \"flight-offers-search.get-flight-offers\"\n              with:\n                originLocationCode: \"rest.origin\"\n                destinationLocationCode: \"rest.destination\"\n                departureDate: \"rest.departureDate\"\n                adults: \"rest.adults\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flights/price\n          name: flight-price\n          description: Confirm pricing for a selected flight offer.\n          operations:\n            - method: POST\n              name: confirm-price\n              description: Confirm current price and availability.\n             \
  \ call: \"flight-offers-price.confirm-flight-price\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: flight-shopping-mcp\n      transport: http\n      description: MCP server for AI-assisted flight shopping and booking preparation.\n      tools:\n        - name: search-flights\n          description: Search for available flights between two airports on a given date, with options for cabin class and passenger count.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight-offers-search.get-flight-offers\"\n          with:\n            originLocationCode: \"tools.origin\"\n            destinationLocationCode: \"tools.destination\"\n            departureDate: \"tools.departureDate\"\n            adults: \"tools.adults\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-flights-advanced\n\
  \          description: Advanced flight search with complex criteria using request body for multi-city and detailed filters.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight-offers-search.search-flight-offers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: confirm-flight-price\n          description: Confirm the current price and availability of a selected flight offer before creating a booking.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight-offers-price.confirm-flight-price\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amadeus-solutions/refs/heads/main/capabilities/flight-shopping.yaml
tags:
- Amadeus
- Flights
- Shopping
- Search
- Pricing
- Travel
tools:
- description: Search for available flights between two airports on a given date, with options for cabin class and passenger count.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Advanced flight search with complex criteria using request body for multi-city and detailed filters.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights-advanced
- description: Confirm the current price and availability of a selected flight offer before creating a booking.
  hints:
    openWorld: true
    readOnly: true
  name: confirm-flight-price
---
