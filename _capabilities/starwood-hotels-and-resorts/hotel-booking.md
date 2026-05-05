---
categories: []
consumed_apis:
- starwood-hotel-search
description: Workflow capability for Starwood Hotels and Resorts hotel booking and travel planning. Combines hotel search, property lookup, and availability checking to support travel planning agents, OTA integrations, and corporate travel management platforms. Enables AI-assisted hotel discovery, comparison, and booking workflows.
layout: capability
name: Starwood Hotel Booking
operations:
- description: Search Starwood hotels by location and travel dates
  method: GET
  name: search-hotels
  path: /v1/hotels
- description: Get detailed information for a Starwood hotel
  method: GET
  name: get-hotel
  path: /v1/hotels/{hotelId}
- description: Get available rooms, rates, and SPG point redemption options
  method: GET
  name: get-hotel-availability
  path: /v1/hotels/{hotelId}/availability
personas: []
provider_name: Starwood Hotels and Resorts
provider_slug: starwood-hotels-and-resorts
search_terms:
- search and discover starwood hotel properties
- search hotels
- hotels
- get hotel availability
- get comprehensive information about a specific starwood hotel property including address, amenities, dining, and contact information.
- get hotel details
- search starwood hotels by location and travel dates
- check available room types and rates for a starwood hotel on specific travel dates. returns room categories, nightly rates, total stay price, and spg award night options.
- check hotel availability
- availability
- get detailed information for a starwood hotel
- check hotel room availability and rates
- get hotel
- search starwood hotel properties by destination location and travel dates. returns hotels with rates, spg category, amenities, and starpoints redemption options.
- get complete hotel property details
- hospitality
- get available rooms, rates, and spg point redemption options
- booking
- travel
slug: hotel-booking
source_filename: hotel-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Starwood Hotel Booking\"\n  description: >-\n    Workflow capability for Starwood Hotels and Resorts hotel booking and travel planning.\n    Combines hotel search, property lookup, and availability checking to support\n    travel planning agents, OTA integrations, and corporate travel management platforms.\n    Enables AI-assisted hotel discovery, comparison, and booking workflows.\n  tags:\n    - Hotels\n    - Travel\n    - Hospitality\n    - Booking\n    - Availability\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STARWOOD_API_KEY: STARWOOD_API_KEY\n\ncapability:\n  consumes:\n    - import: starwood-hotel-search\n      location: ./shared/hotel-search.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: starwood-hotel-booking-api\n      description: \"Unified REST API for Starwood hotel search and booking workflows.\"\n      resources:\n        - path:\
  \ /v1/hotels\n          name: hotels\n          description: \"Search and discover Starwood hotel properties\"\n          operations:\n            - method: GET\n              name: search-hotels\n              description: \"Search Starwood hotels by location and travel dates\"\n              call: \"starwood-hotel-search.search-hotels\"\n              with:\n                country: \"rest.country\"\n                province: \"rest.province\"\n                city: \"rest.city\"\n                arrivalDate: \"rest.arrivalDate\"\n                departureDate: \"rest.departureDate\"\n                adults: \"rest.adults\"\n                brand: \"rest.brand\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/{hotelId}\n          name: hotel-detail\n          description: \"Get complete hotel property details\"\n          operations:\n            - method: GET\n              name: get-hotel\n          \
  \    description: \"Get detailed information for a Starwood hotel\"\n              call: \"starwood-hotel-search.get-hotel\"\n              with:\n                hotelId: \"rest.hotelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hotels/{hotelId}/availability\n          name: hotel-availability\n          description: \"Check hotel room availability and rates\"\n          operations:\n            - method: GET\n              name: get-hotel-availability\n              description: \"Get available rooms, rates, and SPG point redemption options\"\n              call: \"starwood-hotel-search.get-hotel-availability\"\n              with:\n                hotelId: \"rest.hotelId\"\n                arrivalDate: \"rest.arrivalDate\"\n                departureDate: \"rest.departureDate\"\n                adults: \"rest.adults\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: starwood-hotel-booking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted hotel discovery and travel planning using Starwood properties.\"\n      tools:\n        - name: search-hotels\n          description: >-\n            Search Starwood hotel properties by destination location and travel dates.\n            Returns hotels with rates, SPG category, amenities, and Starpoints redemption options.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"starwood-hotel-search.search-hotels\"\n          with:\n            country: \"tools.country\"\n            province: \"tools.province\"\n            city: \"tools.city\"\n            arrivalDate: \"tools.arrivalDate\"\n            departureDate: \"tools.departureDate\"\n            adults: \"tools.adults\"\n            brand: \"tools.brand\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-hotel-details\n          description: >-\n            Get comprehensive information about a specific Starwood hotel property\n            including address, amenities, dining, and contact information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"starwood-hotel-search.get-hotel\"\n          with:\n            hotelId: \"tools.hotelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-hotel-availability\n          description: >-\n            Check available room types and rates for a Starwood hotel on specific travel dates.\n            Returns room categories, nightly rates, total stay price, and SPG award night options.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"starwood-hotel-search.get-hotel-availability\"\n          with:\n            hotelId: \"tools.hotelId\"\n            arrivalDate: \"\
  tools.arrivalDate\"\n            departureDate: \"tools.departureDate\"\n            adults: \"tools.adults\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/starwood-hotels-and-resorts/refs/heads/main/capabilities/hotel-booking.yaml
tags:
- Hotels
- Travel
- Hospitality
- Booking
- Availability
tools:
- description: Search Starwood hotel properties by destination location and travel dates. Returns hotels with rates, SPG category, amenities, and Starpoints redemption options.
  hints:
    openWorld: true
    readOnly: true
  name: search-hotels
- description: Get comprehensive information about a specific Starwood hotel property including address, amenities, dining, and contact information.
  hints:
    openWorld: true
    readOnly: true
  name: get-hotel-details
- description: Check available room types and rates for a Starwood hotel on specific travel dates. Returns room categories, nightly rates, total stay price, and SPG award night options.
  hints:
    openWorld: true
    readOnly: true
  name: check-hotel-availability
---
