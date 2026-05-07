---
categories: []
consumed_apis: []
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
- check hotel room availability and rates
- get available rooms, rates, and spg point redemption options
- hospitality
- check hotel availability
- search starwood hotel properties by destination location and travel dates. returns hotels with rates, spg category, amenities, and starpoints redemption options.
- search starwood hotels by location and travel dates
- get comprehensive information about a specific starwood hotel property including address, amenities, dining, and contact information.
- get complete hotel property details
- get hotel
- get detailed information for a starwood hotel
- booking
- travel
- availability
- hotels
- get hotel details
- search and discover starwood hotel properties
- check available room types and rates for a starwood hotel on specific travel dates. returns room categories, nightly rates, total stay price, and spg award night options.
- search hotels
- get hotel availability
slug: hotel-booking
source_filename: hotel-booking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Starwood Hotel Booking\n  description: Workflow capability for Starwood Hotels and Resorts hotel booking and travel planning. Combines hotel search,\n    property lookup, and availability checking to support travel planning agents, OTA integrations, and corporate travel management\n    platforms. Enables AI-assisted hotel discovery, comparison, and booking workflows.\n  tags:\n  - Hotels\n  - Travel\n  - Hospitality\n  - Booking\n  - Availability\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STARWOOD_API_KEY: STARWOOD_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: starwood-hotel-search\n    baseUri: https://www.starwoodhotels.com/api\n    description: Starwood Hotels and Resorts Hotel Search API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{STARWOOD_API_KEY}}'\n      placement: header\n    resources:\n    - name: hotels-search\n      path:\
  \ /v1/hotels/search\n      description: Search Starwood hotel properties by location and dates\n      operations:\n      - name: search-hotels\n        method: GET\n        description: Search hotels by country, city, and travel dates\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: true\n          description: Two-letter ISO country code\n        - name: province\n          in: query\n          type: string\n          required: false\n          description: Province or state code\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: arrivalDate\n          in: query\n          type: string\n          required: true\n          description: Check-in date YYYY-MM-DD\n        - name: departureDate\n          in: query\n          type: string\n          required: true\n          description: Check-out date YYYY-MM-DD\n        - name:\
  \ adults\n          in: query\n          type: integer\n          required: false\n          description: Number of adult guests\n        - name: brand\n          in: query\n          type: string\n          required: false\n          description: Starwood brand code filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hotels-detail\n      path: /v1/hotels/{hotelId}\n      description: Individual hotel property operations\n      operations:\n      - name: get-hotel\n        method: GET\n        description: Get hotel property details by ID\n        inputParameters:\n        - name: hotelId\n          in: path\n          type: string\n          required: true\n          description: Unique hotel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hotels-availability\n      path: /v1/hotels/{hotelId}/availability\n\
  \      description: Hotel availability and rate operations\n      operations:\n      - name: get-hotel-availability\n        method: GET\n        description: Get available rooms and rates for a hotel\n        inputParameters:\n        - name: hotelId\n          in: path\n          type: string\n          required: true\n          description: Unique hotel identifier\n        - name: arrivalDate\n          in: query\n          type: string\n          required: true\n          description: Check-in date\n        - name: departureDate\n          in: query\n          type: string\n          required: true\n          description: Check-out date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: starwood-hotel-booking-api\n    description: Unified REST API for Starwood hotel search and booking workflows.\n    resources:\n    - path: /v1/hotels\n      name:\
  \ hotels\n      description: Search and discover Starwood hotel properties\n      operations:\n      - method: GET\n        name: search-hotels\n        description: Search Starwood hotels by location and travel dates\n        call: starwood-hotel-search.search-hotels\n        with:\n          country: rest.country\n          province: rest.province\n          city: rest.city\n          arrivalDate: rest.arrivalDate\n          departureDate: rest.departureDate\n          adults: rest.adults\n          brand: rest.brand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/{hotelId}\n      name: hotel-detail\n      description: Get complete hotel property details\n      operations:\n      - method: GET\n        name: get-hotel\n        description: Get detailed information for a Starwood hotel\n        call: starwood-hotel-search.get-hotel\n        with:\n          hotelId: rest.hotelId\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /v1/hotels/{hotelId}/availability\n      name: hotel-availability\n      description: Check hotel room availability and rates\n      operations:\n      - method: GET\n        name: get-hotel-availability\n        description: Get available rooms, rates, and SPG point redemption options\n        call: starwood-hotel-search.get-hotel-availability\n        with:\n          hotelId: rest.hotelId\n          arrivalDate: rest.arrivalDate\n          departureDate: rest.departureDate\n          adults: rest.adults\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: starwood-hotel-booking-mcp\n    transport: http\n    description: MCP server for AI-assisted hotel discovery and travel planning using Starwood properties.\n    tools:\n    - name: search-hotels\n      description: Search Starwood hotel properties by destination location and travel dates. Returns hotels with rates, SPG\n        category,\
  \ amenities, and Starpoints redemption options.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starwood-hotel-search.search-hotels\n      with:\n        country: tools.country\n        province: tools.province\n        city: tools.city\n        arrivalDate: tools.arrivalDate\n        departureDate: tools.departureDate\n        adults: tools.adults\n        brand: tools.brand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hotel-details\n      description: Get comprehensive information about a specific Starwood hotel property including address, amenities, dining,\n        and contact information.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starwood-hotel-search.get-hotel\n      with:\n        hotelId: tools.hotelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-hotel-availability\n      description: Check available room types and rates for a Starwood\
  \ hotel on specific travel dates. Returns room categories,\n        nightly rates, total stay price, and SPG award night options.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starwood-hotel-search.get-hotel-availability\n      with:\n        hotelId: tools.hotelId\n        arrivalDate: tools.arrivalDate\n        departureDate: tools.departureDate\n        adults: tools.adults\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
