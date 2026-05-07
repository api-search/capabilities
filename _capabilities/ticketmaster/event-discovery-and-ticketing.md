---
categories: []
consumed_apis: []
description: Unified capability for event discovery applications, travel platforms, and entertainment apps to search and display live events, venues, and artists from Ticketmaster alongside ticket availability and pricing. Combines the Discovery API for event search with the Commerce API for real-time ticket offers.
layout: capability
name: Ticketmaster Event Discovery and Ticketing
operations:
- description: Search for live events by keyword, location, date, and genre
  method: GET
  name: search-events
  path: /v1/events
- description: Get details for a specific event
  method: GET
  name: get-event
  path: /v1/events/{id}
- description: Get ticket pricing and offers for an event
  method: GET
  name: get-event-offers
  path: /v1/events/{eventId}/offers
- description: Check ticket availability for an event
  method: GET
  name: get-event-availability
  path: /v1/events/{eventId}/availability
- description: Search for artists, sports teams, and other attractions
  method: GET
  name: search-attractions
  path: /v1/attractions
- description: Search for event venues by name or location
  method: GET
  name: search-venues
  path: /v1/venues
- description: Get autocomplete suggestions for event, venue, or attraction searches
  method: GET
  name: get-suggestions
  path: /v1/suggest
personas: []
provider_name: Ticketmaster
provider_slug: ticketmaster
search_terms:
- get details for a specific event
- get ticket pricing and offers for an event
- get search suggestions
- tickets
- get ticket pricing tiers and purchase options for a specific ticketmaster event
- search events
- ticketmaster
- get autocomplete suggestions for event, venue, or attraction searches
- venues
- search for event venues by name or location
- search for live events on ticketmaster by keyword, city, country, date range, or classification (music, sports, arts, family)
- search artists and attractions
- get event offers
- events
- venue search
- individual event details
- get full details for a specific ticketmaster event including dates, venue, and prices
- search for artists, sports teams, and other attractions
- concerts
- ticket availability for an event
- get suggestions
- search attractions
- entertainment
- check ticket availability for an event
- search for live events by keyword, location, date, and genre
- sports
- live event search
- get event
- get autocomplete suggestions while users type event or venue search queries
- check if tickets are still available for a ticketmaster event
- check ticket availability
- search
- ticket offers for an event
- get event availability
- search autocomplete
- find event venues near a city or geographic location
- search for artists, sports teams, and other attractions on ticketmaster
- commerce
- search venues
- get event ticket offers
- artist and attraction search
slug: event-discovery-and-ticketing
source_filename: event-discovery-and-ticketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ticketmaster Event Discovery and Ticketing\n  description: Unified capability for event discovery applications, travel platforms, and entertainment apps to search and\n    display live events, venues, and artists from Ticketmaster alongside ticket availability and pricing. Combines the Discovery\n    API for event search with the Commerce API for real-time ticket offers.\n  tags:\n  - Ticketmaster\n  - Commerce\n  - Entertainment\n  - Events\n  - Search\n  - Tickets\n  - Venues\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TICKETMASTER_API_KEY: TICKETMASTER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ticketmaster-discovery\n    baseUri: https://app.ticketmaster.com/discovery/v2\n    description: Ticketmaster Discovery REST API for event search\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{TICKETMASTER_API_KEY}}'\n      placement: query\n \
  \   resources:\n    - name: events\n      path: /events.json\n      description: Event search and retrieval\n      operations:\n      - name: search-events\n        method: GET\n        description: Search for live events by keyword, location, date, and classification\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: false\n        - name: attractionId\n          in: query\n          type: string\n          required: false\n        - name: venueId\n          in: query\n          type: string\n          required: false\n        - name: classificationName\n          in: query\n          type: string\n          required: false\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n        - name: stateCode\n          in: query\n          type: string\n          required: false\n        - name: city\n          in: query\n          type: string\n          required: false\n     \
  \   - name: latlong\n          in: query\n          type: string\n          required: false\n        - name: radius\n          in: query\n          type: integer\n          required: false\n        - name: startDateTime\n          in: query\n          type: string\n          required: false\n        - name: endDateTime\n          in: query\n          type: string\n          required: false\n        - name: size\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-event\n        method: GET\n        description: Get details for a specific event\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: attractions\n      path: /attractions.json\n      description: Attraction search (artists, sports teams, etc.)\n      operations:\n      - name: search-attractions\n        method: GET\n        description: Search for attractions on Ticketmaster\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: false\n        - name: classificationName\n          in: query\n          type: string\n          required: false\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n        - name: size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-attraction\n        method: GET\n        description: Get details for a specific attraction\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues\n      path: /venues.json\n      description: Venue search and details\n      operations:\n      - name: search-venues\n        method: GET\n        description: Search for venues by name or location\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: false\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n        - name: stateCode\n          in: query\n          type: string\n          required: false\n        - name: city\n          in: query\n          type: string\n          required: false\n        - name: latlong\n          in: query\n          type: string\n          required: false\n        - name: radius\n          in: query\n  \
  \        type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-venue\n        method: GET\n        description: Get details for a specific venue\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classifications\n      path: /classifications.json\n      description: Event classifications (segments, genres, sub-genres)\n      operations:\n      - name: search-classifications\n        method: GET\n        description: Browse event classifications\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: suggest\n      path: /suggest.json\n      description: Search suggestions\n      operations:\n      - name: get-suggestions\n        method: GET\n        description: Get search autocomplete suggestions\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: true\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ticketmaster-commerce\n    baseUri: https://app.ticketmaster.com/commerce/v2\n    description: Ticketmaster Commerce API for ticket offers and availability\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{TICKETMASTER_API_KEY}}'\n      placement: query\n    resources:\n    - name: event-offers\n      path: /events/{eventId}/offers.json\n\
  \      description: Event ticket offers\n      operations:\n      - name: get-event-offers\n        method: GET\n        description: Get ticket offers and pricing for an event\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-availability\n      path: /events/{eventId}/availability.json\n      description: Event ticket availability\n      operations:\n      - name: get-event-availability\n        method: GET\n        description: Get ticket availability status for an event\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ ticketmaster-api\n    description: Unified REST API for Ticketmaster event discovery and ticket commerce.\n    resources:\n    - path: /v1/events\n      name: events\n      description: Live event search\n      operations:\n      - method: GET\n        name: search-events\n        description: Search for live events by keyword, location, date, and genre\n        call: ticketmaster-discovery.search-events\n        with:\n          keyword: rest.keyword\n          countryCode: rest.countryCode\n          city: rest.city\n          startDateTime: rest.startDateTime\n          endDateTime: rest.endDateTime\n          classificationName: rest.classificationName\n          size: rest.size\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{id}\n      name: event-detail\n      description: Individual event details\n      operations:\n      - method: GET\n        name: get-event\n        description: Get details for a\
  \ specific event\n        call: ticketmaster-discovery.get-event\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}/offers\n      name: event-offers\n      description: Ticket offers for an event\n      operations:\n      - method: GET\n        name: get-event-offers\n        description: Get ticket pricing and offers for an event\n        call: ticketmaster-commerce.get-event-offers\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}/availability\n      name: event-availability\n      description: Ticket availability for an event\n      operations:\n      - method: GET\n        name: get-event-availability\n        description: Check ticket availability for an event\n        call: ticketmaster-commerce.get-event-availability\n        with:\n          eventId: rest.eventId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/attractions\n      name: attractions\n      description: Artist and attraction search\n      operations:\n      - method: GET\n        name: search-attractions\n        description: Search for artists, sports teams, and other attractions\n        call: ticketmaster-discovery.search-attractions\n        with:\n          keyword: rest.keyword\n          classificationName: rest.classificationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/venues\n      name: venues\n      description: Venue search\n      operations:\n      - method: GET\n        name: search-venues\n        description: Search for event venues by name or location\n        call: ticketmaster-discovery.search-venues\n        with:\n          keyword: rest.keyword\n          city: rest.city\n          countryCode: rest.countryCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/suggest\n      name: suggestions\n      description: Search autocomplete\n      operations:\n      - method: GET\n        name: get-suggestions\n        description: Get autocomplete suggestions for event, venue, or attraction searches\n        call: ticketmaster-discovery.get-suggestions\n        with:\n          keyword: rest.keyword\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ticketmaster-mcp\n    transport: http\n    description: MCP server for AI-assisted live event discovery and ticket availability queries across the Ticketmaster platform.\n    tools:\n    - name: search-events\n      description: Search for live events on Ticketmaster by keyword, city, country, date range, or classification (Music,\n        Sports, Arts, Family)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-discovery.search-events\n      with:\n        keyword: tools.keyword\n        countryCode:\
  \ tools.countryCode\n        city: tools.city\n        startDateTime: tools.startDateTime\n        endDateTime: tools.endDateTime\n        classificationName: tools.classificationName\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event\n      description: Get full details for a specific Ticketmaster event including dates, venue, and prices\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-discovery.get-event\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-ticket-offers\n      description: Get ticket pricing tiers and purchase options for a specific Ticketmaster event\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-commerce.get-event-offers\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-ticket-availability\n\
  \      description: Check if tickets are still available for a Ticketmaster event\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-commerce.get-event-availability\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-artists-and-attractions\n      description: Search for artists, sports teams, and other attractions on Ticketmaster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-discovery.search-attractions\n      with:\n        keyword: tools.keyword\n        classificationName: tools.classificationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-venues\n      description: Find event venues near a city or geographic location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-discovery.search-venues\n      with:\n        keyword: tools.keyword\n   \
  \     city: tools.city\n        countryCode: tools.countryCode\n        latlong: tools.latlong\n        radius: tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-suggestions\n      description: Get autocomplete suggestions while users type event or venue search queries\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ticketmaster-discovery.get-suggestions\n      with:\n        keyword: tools.keyword\n        countryCode: tools.countryCode\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ticketmaster/refs/heads/main/capabilities/event-discovery-and-ticketing.yaml
tags:
- Ticketmaster
- Commerce
- Entertainment
- Events
- Search
- Tickets
- Venues
tools:
- description: Search for live events on Ticketmaster by keyword, city, country, date range, or classification (Music, Sports, Arts, Family)
  hints:
    openWorld: true
    readOnly: true
  name: search-events
- description: Get full details for a specific Ticketmaster event including dates, venue, and prices
  hints:
    openWorld: true
    readOnly: true
  name: get-event
- description: Get ticket pricing tiers and purchase options for a specific Ticketmaster event
  hints:
    openWorld: true
    readOnly: true
  name: get-event-ticket-offers
- description: Check if tickets are still available for a Ticketmaster event
  hints:
    openWorld: true
    readOnly: true
  name: check-ticket-availability
- description: Search for artists, sports teams, and other attractions on Ticketmaster
  hints:
    openWorld: true
    readOnly: true
  name: search-artists-and-attractions
- description: Find event venues near a city or geographic location
  hints:
    openWorld: true
    readOnly: true
  name: search-venues
- description: Get autocomplete suggestions while users type event or venue search queries
  hints:
    openWorld: true
    readOnly: true
  name: get-search-suggestions
---
