---
categories: []
consumed_apis: []
description: The Ticketmaster Discovery API allows developers to search for events, attractions, venues, and classifications across all Ticketmaster supported sources, markets, and locales. The API provides access to content from Ticketmaster, Universe, FrontGate Tickets, and Ticketmaster Resale platforms.
layout: capability
name: Ticketmaster Discovery API
operations:
- description: Search events
  method: GET
  name: searchevents
  path: /events.json
- description: Get event details
  method: GET
  name: geteventdetails
  path: /events/{id}.json
- description: Search attractions
  method: GET
  name: searchattractions
  path: /attractions.json
- description: Get attraction details
  method: GET
  name: getattractiondetails
  path: /attractions/{id}.json
- description: Search venues
  method: GET
  name: searchvenues
  path: /venues.json
- description: Get venue details
  method: GET
  name: getvenuedetails
  path: /venues/{id}.json
- description: Search classifications
  method: GET
  name: searchclassifications
  path: /classifications.json
personas: []
provider_name: live-nation-entertainment
provider_slug: live-nation-entertainment
search_terms:
- getvenuedetails
- get attraction details
- searchevents
- searchclassifications
- getattractiondetails
- search events
- searchattractions
- search venues
- api
- nation
- searchvenues
- geteventdetails
- search classifications
- get venue details
- live
- search attractions
- entertainment
- get event details
slug: live-nation-entertainment-capability
source_filename: live-nation-entertainment-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ticketmaster Discovery API\n  description: The Ticketmaster Discovery API allows developers to search for events, attractions, venues, and classifications\n    across all Ticketmaster supported sources, markets, and locales. The API provides access to content from Ticketmaster,\n    Universe, FrontGate Tickets, and Ticketmaster Resale platforms.\n  tags:\n  - Live\n  - Nation\n  - Entertainment\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: live-nation-entertainment\n    baseUri: https://app.ticketmaster.com/discovery/v2\n    description: Ticketmaster Discovery API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{LIVE_NATION_ENTERTAINMENT_TOKEN}}'\n    resources:\n    - name: events-json\n      path: /events.json\n      operations:\n      - name: searchevents\n        method: GET\n        description: Search events\n\
  \        inputParameters:\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        - name: keyword\n          in: query\n          type: string\n          description: Keyword to search on.\n        - name: city\n          in: query\n          type: string\n          description: Filter by city name.\n        - name: stateCode\n          in: query\n          type: string\n          description: Filter by state code.\n        - name: countryCode\n          in: query\n          type: string\n          description: Filter by country code.\n        - name: startDateTime\n          in: query\n          type: string\n          description: Filter events starting after this date/time.\n        - name: endDateTime\n          in: query\n          type: string\n          description: Filter events starting before this date/time.\n        - name: size\n          in: query\n          type: integer\n\
  \          description: Page size of the response.\n        - name: page\n          in: query\n          type: integer\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-id-json\n      path: /events/{id}.json\n      operations:\n      - name: geteventdetails\n        method: GET\n        description: Get event details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Event identifier.\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attractions-json\n      path: /attractions.json\n      operations:\n      - name: searchattractions\n\
  \        method: GET\n        description: Search attractions\n        inputParameters:\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        - name: keyword\n          in: query\n          type: string\n          description: Keyword to search on.\n        - name: size\n          in: query\n          type: integer\n          description: Page size of the response.\n        - name: page\n          in: query\n          type: integer\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attractions-id-json\n      path: /attractions/{id}.json\n      operations:\n      - name: getattractiondetails\n        method: GET\n        description: Get attraction details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Attraction identifier.\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues-json\n      path: /venues.json\n      operations:\n      - name: searchvenues\n        method: GET\n        description: Search venues\n        inputParameters:\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        - name: keyword\n          in: query\n          type: string\n          description: Keyword to search on.\n        - name: city\n          in: query\n          type: string\n          description: Filter by city name.\n        - name: stateCode\n          in: query\n          type: string\n          description: Filter by state code.\n\
  \        - name: countryCode\n          in: query\n          type: string\n          description: Filter by country code.\n        - name: size\n          in: query\n          type: integer\n          description: Page size of the response.\n        - name: page\n          in: query\n          type: integer\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues-id-json\n      path: /venues/{id}.json\n      operations:\n      - name: getvenuedetails\n        method: GET\n        description: Get venue details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Venue identifier.\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: classifications-json\n      path: /classifications.json\n      operations:\n      - name: searchclassifications\n        method: GET\n        description: Search classifications\n        inputParameters:\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        - name: keyword\n          in: query\n          type: string\n          description: Keyword to search on.\n        - name: size\n          in: query\n          type: integer\n          description: Page size of the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: live-nation-entertainment-rest\n    description: REST adapter for Ticketmaster Discovery API.\n    resources:\n    - path: /events.json\n      name:\
  \ searchevents\n      operations:\n      - method: GET\n        name: searchevents\n        description: Search events\n        call: live-nation-entertainment.searchevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{id}.json\n      name: geteventdetails\n      operations:\n      - method: GET\n        name: geteventdetails\n        description: Get event details\n        call: live-nation-entertainment.geteventdetails\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /attractions.json\n      name: searchattractions\n      operations:\n      - method: GET\n        name: searchattractions\n        description: Search attractions\n        call: live-nation-entertainment.searchattractions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /attractions/{id}.json\n      name: getattractiondetails\n      operations:\n      - method:\
  \ GET\n        name: getattractiondetails\n        description: Get attraction details\n        call: live-nation-entertainment.getattractiondetails\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /venues.json\n      name: searchvenues\n      operations:\n      - method: GET\n        name: searchvenues\n        description: Search venues\n        call: live-nation-entertainment.searchvenues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /venues/{id}.json\n      name: getvenuedetails\n      operations:\n      - method: GET\n        name: getvenuedetails\n        description: Get venue details\n        call: live-nation-entertainment.getvenuedetails\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classifications.json\n      name: searchclassifications\n      operations:\n      - method: GET\n   \
  \     name: searchclassifications\n        description: Search classifications\n        call: live-nation-entertainment.searchclassifications\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: live-nation-entertainment-mcp\n    transport: http\n    description: MCP adapter for Ticketmaster Discovery API for AI agent use.\n    tools:\n    - name: searchevents\n      description: Search events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.searchevents\n      with:\n        apikey: tools.apikey\n        keyword: tools.keyword\n        city: tools.city\n        stateCode: tools.stateCode\n        countryCode: tools.countryCode\n        startDateTime: tools.startDateTime\n        endDateTime: tools.endDateTime\n        size: tools.size\n        page: tools.page\n      inputParameters:\n      - name: apikey\n        type: string\n        description:\
  \ API key for authentication.\n        required: true\n      - name: keyword\n        type: string\n        description: Keyword to search on.\n      - name: city\n        type: string\n        description: Filter by city name.\n      - name: stateCode\n        type: string\n        description: Filter by state code.\n      - name: countryCode\n        type: string\n        description: Filter by country code.\n      - name: startDateTime\n        type: string\n        description: Filter events starting after this date/time.\n      - name: endDateTime\n        type: string\n        description: Filter events starting before this date/time.\n      - name: size\n        type: integer\n        description: Page size of the response.\n      - name: page\n        type: integer\n        description: Page number.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventdetails\n      description: Get event details\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: live-nation-entertainment.geteventdetails\n      with:\n        id: tools.id\n        apikey: tools.apikey\n      inputParameters:\n      - name: id\n        type: string\n        description: Event identifier.\n        required: true\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchattractions\n      description: Search attractions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.searchattractions\n      with:\n        apikey: tools.apikey\n        keyword: tools.keyword\n        size: tools.size\n        page: tools.page\n      inputParameters:\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      - name: keyword\n     \
  \   type: string\n        description: Keyword to search on.\n      - name: size\n        type: integer\n        description: Page size of the response.\n      - name: page\n        type: integer\n        description: Page number.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getattractiondetails\n      description: Get attraction details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.getattractiondetails\n      with:\n        id: tools.id\n        apikey: tools.apikey\n      inputParameters:\n      - name: id\n        type: string\n        description: Attraction identifier.\n        required: true\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchvenues\n      description: Search venues\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.searchvenues\n      with:\n        apikey: tools.apikey\n        keyword: tools.keyword\n        city: tools.city\n        stateCode: tools.stateCode\n        countryCode: tools.countryCode\n        size: tools.size\n        page: tools.page\n      inputParameters:\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      - name: keyword\n        type: string\n        description: Keyword to search on.\n      - name: city\n        type: string\n        description: Filter by city name.\n      - name: stateCode\n        type: string\n        description: Filter by state code.\n      - name: countryCode\n        type: string\n        description: Filter by country code.\n      - name: size\n        type: integer\n        description: Page size of the response.\n      - name: page\n        type: integer\n        description:\
  \ Page number.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvenuedetails\n      description: Get venue details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.getvenuedetails\n      with:\n        id: tools.id\n        apikey: tools.apikey\n      inputParameters:\n      - name: id\n        type: string\n        description: Venue identifier.\n        required: true\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchclassifications\n      description: Search classifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: live-nation-entertainment.searchclassifications\n      with:\n        apikey: tools.apikey\n        keyword: tools.keyword\n        size: tools.size\n\
  \      inputParameters:\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      - name: keyword\n        type: string\n        description: Keyword to search on.\n      - name: size\n        type: integer\n        description: Page size of the response.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LIVE_NATION_ENTERTAINMENT_TOKEN: LIVE_NATION_ENTERTAINMENT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/live-nation-entertainment/refs/heads/main/capabilities/live-nation-entertainment-capability.yaml
tags:
- Live
- Nation
- Entertainment
- API
tools:
- description: Search events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchevents
- description: Get event details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventdetails
- description: Search attractions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchattractions
- description: Get attraction details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getattractiondetails
- description: Search venues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchvenues
- description: Get venue details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvenuedetails
- description: Search classifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchclassifications
---
