---
api_specs:
- filename: ticketmaster-discovery-openapi.yml
  format: yaml
  label: ticketmaster-discovery
  slug: ticketmaster-discovery
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/ticketmaster/refs/heads/main/openapi/ticketmaster-discovery-openapi.yml
- filename: ticketmaster-commerce-openapi.yml
  format: yaml
  label: ticketmaster-commerce
  slug: ticketmaster-commerce
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/ticketmaster/refs/heads/main/openapi/ticketmaster-commerce-openapi.yml
categories: []
consumed_apis:
- ticketmaster-discovery
- ticketmaster-commerce
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
- search artists and attractions
- get ticket pricing tiers and purchase options for a specific ticketmaster event
- search for artists, sports teams, and other attractions
- search for artists, sports teams, and other attractions on ticketmaster
- entertainment
- get details for a specific event
- get autocomplete suggestions while users type event or venue search queries
- ticket availability for an event
- venues
- search events
- search for live events by keyword, location, date, and genre
- get event offers
- ticketmaster
- venue search
- get search suggestions
- check ticket availability
- search venues
- search attractions
- get event
- get autocomplete suggestions for event, venue, or attraction searches
- search
- get ticket pricing and offers for an event
- individual event details
- tickets
- artist and attraction search
- search for event venues by name or location
- search autocomplete
- check if tickets are still available for a ticketmaster event
- find event venues near a city or geographic location
- commerce
- events
- live event search
- search for live events on ticketmaster by keyword, city, country, date range, or classification (music, sports, arts, family)
- ticket offers for an event
- get event ticket offers
- get suggestions
- check ticket availability for an event
- get full details for a specific ticketmaster event including dates, venue, and prices
- concerts
- sports
- get event availability
slug: event-discovery-and-ticketing
source_filename: event-discovery-and-ticketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Ticketmaster Event Discovery and Ticketing\n  description: >-\n    Unified capability for event discovery applications, travel platforms, and\n    entertainment apps to search and display live events, venues, and artists\n    from Ticketmaster alongside ticket availability and pricing. Combines the\n    Discovery API for event search with the Commerce API for real-time ticket\n    offers.\n  tags:\n    - Ticketmaster\n    - Commerce\n    - Entertainment\n    - Events\n    - Search\n    - Tickets\n    - Venues\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TICKETMASTER_API_KEY: TICKETMASTER_API_KEY\n\ncapability:\n  consumes:\n    - import: ticketmaster-discovery\n      location: ./shared/ticketmaster-discovery.yaml\n    - import: ticketmaster-commerce\n      location: ./shared/ticketmaster-commerce.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ticketmaster-api\n\
  \      description: >-\n        Unified REST API for Ticketmaster event discovery and ticket commerce.\n      resources:\n        - path: /v1/events\n          name: events\n          description: Live event search\n          operations:\n            - method: GET\n              name: search-events\n              description: Search for live events by keyword, location, date, and genre\n              call: \"ticketmaster-discovery.search-events\"\n              with:\n                keyword: \"rest.keyword\"\n                countryCode: \"rest.countryCode\"\n                city: \"rest.city\"\n                startDateTime: \"rest.startDateTime\"\n                endDateTime: \"rest.endDateTime\"\n                classificationName: \"rest.classificationName\"\n                size: \"rest.size\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/{id}\n          name:\
  \ event-detail\n          description: Individual event details\n          operations:\n            - method: GET\n              name: get-event\n              description: Get details for a specific event\n              call: \"ticketmaster-discovery.get-event\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/{eventId}/offers\n          name: event-offers\n          description: Ticket offers for an event\n          operations:\n            - method: GET\n              name: get-event-offers\n              description: Get ticket pricing and offers for an event\n              call: \"ticketmaster-commerce.get-event-offers\"\n              with:\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/{eventId}/availability\n          name:\
  \ event-availability\n          description: Ticket availability for an event\n          operations:\n            - method: GET\n              name: get-event-availability\n              description: Check ticket availability for an event\n              call: \"ticketmaster-commerce.get-event-availability\"\n              with:\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/attractions\n          name: attractions\n          description: Artist and attraction search\n          operations:\n            - method: GET\n              name: search-attractions\n              description: Search for artists, sports teams, and other attractions\n              call: \"ticketmaster-discovery.search-attractions\"\n              with:\n                keyword: \"rest.keyword\"\n                classificationName: \"rest.classificationName\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/venues\n          name: venues\n          description: Venue search\n          operations:\n            - method: GET\n              name: search-venues\n              description: Search for event venues by name or location\n              call: \"ticketmaster-discovery.search-venues\"\n              with:\n                keyword: \"rest.keyword\"\n                city: \"rest.city\"\n                countryCode: \"rest.countryCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/suggest\n          name: suggestions\n          description: Search autocomplete\n          operations:\n            - method: GET\n              name: get-suggestions\n              description: Get autocomplete suggestions for event, venue, or attraction searches\n              call: \"ticketmaster-discovery.get-suggestions\"\n              with:\n\
  \                keyword: \"rest.keyword\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ticketmaster-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted live event discovery and ticket availability\n        queries across the Ticketmaster platform.\n      tools:\n        - name: search-events\n          description: >-\n            Search for live events on Ticketmaster by keyword, city, country,\n            date range, or classification (Music, Sports, Arts, Family)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-discovery.search-events\"\n          with:\n            keyword: \"tools.keyword\"\n            countryCode: \"tools.countryCode\"\n            city: \"tools.city\"\n            startDateTime: \"tools.startDateTime\"\n            endDateTime: \"tools.endDateTime\"\n         \
  \   classificationName: \"tools.classificationName\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event\n          description: Get full details for a specific Ticketmaster event including dates, venue, and prices\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-discovery.get-event\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-ticket-offers\n          description: Get ticket pricing tiers and purchase options for a specific Ticketmaster event\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-commerce.get-event-offers\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: check-ticket-availability\n          description: Check if tickets are still available for a Ticketmaster event\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-commerce.get-event-availability\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-artists-and-attractions\n          description: Search for artists, sports teams, and other attractions on Ticketmaster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-discovery.search-attractions\"\n          with:\n            keyword: \"tools.keyword\"\n            classificationName: \"tools.classificationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-venues\n          description: Find event venues near a city\
  \ or geographic location\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-discovery.search-venues\"\n          with:\n            keyword: \"tools.keyword\"\n            city: \"tools.city\"\n            countryCode: \"tools.countryCode\"\n            latlong: \"tools.latlong\"\n            radius: \"tools.radius\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-search-suggestions\n          description: Get autocomplete suggestions while users type event or venue search queries\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ticketmaster-discovery.get-suggestions\"\n          with:\n            keyword: \"tools.keyword\"\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
