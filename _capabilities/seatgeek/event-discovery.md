---
categories: []
consumed_apis: []
description: Unified event discovery capability combining SeatGeek's events, performers, venues, and recommendation APIs. Enables applications to build comprehensive live event discovery experiences with geolocation search, performer browsing, venue exploration, and personalized recommendations for concerts, sports, and theater.
layout: capability
name: SeatGeek Event Discovery
operations:
- description: Search events by keyword, performer, venue, date, or location
  method: GET
  name: list-events
  path: /v1/events
- description: Get full event details with ticket pricing
  method: GET
  name: get-event
  path: /v1/events/{event_id}
- description: Search for artists, teams, and performers
  method: GET
  name: list-performers
  path: /v1/performers
- description: Get performer details
  method: GET
  name: get-performer
  path: /v1/performers/{performer_id}
- description: Find venues by city, state, or location radius
  method: GET
  name: list-venues
  path: /v1/venues
- description: List all event taxonomy categories
  method: GET
  name: list-taxonomies
  path: /v1/taxonomies
- description: Get personalized event recommendations
  method: GET
  name: get-recommendations
  path: /v1/recommendations
personas: []
provider_name: SeatGeek
provider_slug: seatgeek
search_terms:
- list events
- concerts
- sports
- search venues
- ticketing
- find event venues by city, state, country, or location radius
- get personalized event recommendations
- get full details for a specific event including venue, performers, ticket pricing, and seat availability
- get performer details
- get personalized event recommendations based on user location and interests
- get performer
- list all event taxonomy categories
- get event
- live events
- get event recommendations
- search events
- search for live events by artist name, genre, location, date range, or ticket price
- list available event taxonomy categories such as concerts, sports, and theater
- browse performers
- get recommendations
- performer profile and upcoming events
- list event categories
- search performers
- get full event details with ticket pricing
- find venues by city, state, or location radius
- search events by keyword, performer, venue, date, or location
- event details and ticket pricing
- discovery
- get performer profile, genre, and upcoming event count
- venues
- search and browse live events
- list performers
- search for artists, teams, and performers
- list venues
- get event details
- list taxonomies
- event categories and classifications
- search for concert artists, sports teams, theater companies, and other performers
- events
- tickets
- personalized event recommendations
slug: event-discovery
source_filename: event-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SeatGeek Event Discovery\n  description: Unified event discovery capability combining SeatGeek's events, performers, venues, and recommendation APIs.\n    Enables applications to build comprehensive live event discovery experiences with geolocation search, performer browsing,\n    venue exploration, and personalized recommendations for concerts, sports, and theater.\n  tags:\n  - Events\n  - Live Events\n  - Concerts\n  - Sports\n  - Ticketing\n  - Discovery\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SEATGEEK_CLIENT_ID: SEATGEEK_CLIENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: seatgeek-platform\n    baseUri: https://api.seatgeek.com/2\n    description: SeatGeek Platform API for live events, performers, and venues\n    authentication:\n      type: apikey\n      key: client_id\n      value: '{{SEATGEEK_CLIENT_ID}}'\n      placement: query\n    resources:\n    - name: events\n\
  \      path: /events\n      description: Search and retrieve live events\n      operations:\n      - name: list-events\n        method: GET\n        description: List and search events with filtering by performer, venue, date, and location\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Text search query\n        - name: performers\n          in: query\n          type: string\n          required: false\n          description: Filter by performer slug\n        - name: venue\n          in: query\n          type: integer\n          required: false\n          description: Filter by venue ID\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for geolocation\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for geolocation\n        - name: range\n   \
  \       in: query\n          type: string\n          required: false\n          description: Distance range (e.g., 25mi)\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-detail\n      path: /events/{event_id}\n      description: Get a specific event\n      operations:\n      - name: get-event\n        method: GET\n        description: Get full event details by ID\n        inputParameters:\n        - name: event_id\n          in: path\n          type: integer\n          required: true\n          description: SeatGeek event ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: performers\n      path: /performers\n      description: Search and retrieve performers\n      operations:\n      - name: list-performers\n        method: GET\n        description: List and search performers\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Text search query\n        - name: slug\n          in: query\n          type: string\n          required: false\n          description: Performer slug\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performer-detail\n      path: /performers/{performer_id}\n      description: Get a specific performer\n      operations:\n      - name:\
  \ get-performer\n        method: GET\n        description: Get full performer details by ID\n        inputParameters:\n        - name: performer_id\n          in: path\n          type: integer\n          required: true\n          description: SeatGeek performer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues\n      path: /venues\n      description: Search and retrieve venues\n      operations:\n      - name: list-venues\n        method: GET\n        description: List and search venues by city, state, or geolocation\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n        - name: city\n          in: query\n          type: string\n          required: false\n        - name: state\n          in: query\n          type: string\n          required: false\n        - name: country\n          in: query\n          type: string\n\
  \          required: false\n        - name: lat\n          in: query\n          type: number\n          required: false\n        - name: lon\n          in: query\n          type: number\n          required: false\n        - name: range\n          in: query\n          type: string\n          required: false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taxonomies\n      path: /taxonomies\n      description: List event taxonomies\n      operations:\n      - name: list-taxonomies\n        method: GET\n        description: List available event taxonomy categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recommendations\n\
  \      path: /recommendations\n      description: Get event recommendations\n      operations:\n      - name: get-recommendations\n        method: GET\n        description: Get personalized event recommendations based on location and interests\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude (required)\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude (required)\n        - name: performers.id\n          in: query\n          type: string\n          required: false\n          description: Seed performer IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: event-discovery-api\n    description: Unified REST API for live event discovery with SeatGeek.\n    resources:\n    - path:\
  \ /v1/events\n      name: events\n      description: Search and browse live events\n      operations:\n      - method: GET\n        name: list-events\n        description: Search events by keyword, performer, venue, date, or location\n        call: seatgeek-platform.list-events\n        with:\n          q: rest.q\n          lat: rest.lat\n          lon: rest.lon\n          range: rest.range\n          per_page: rest.per_page\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{event_id}\n      name: event-detail\n      description: Event details and ticket pricing\n      operations:\n      - method: GET\n        name: get-event\n        description: Get full event details with ticket pricing\n        call: seatgeek-platform.get-event\n        with:\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/performers\n      name: performers\n     \
  \ description: Browse performers\n      operations:\n      - method: GET\n        name: list-performers\n        description: Search for artists, teams, and performers\n        call: seatgeek-platform.list-performers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/performers/{performer_id}\n      name: performer-detail\n      description: Performer profile and upcoming events\n      operations:\n      - method: GET\n        name: get-performer\n        description: Get performer details\n        call: seatgeek-platform.get-performer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/venues\n      name: venues\n      description: Search venues\n      operations:\n      - method: GET\n        name: list-venues\n        description: Find venues by city, state, or location radius\n        call: seatgeek-platform.list-venues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/taxonomies\n      name: taxonomies\n      description: Event categories and classifications\n      operations:\n      - method: GET\n        name: list-taxonomies\n        description: List all event taxonomy categories\n        call: seatgeek-platform.list-taxonomies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recommendations\n      name: recommendations\n      description: Personalized event recommendations\n      operations:\n      - method: GET\n        name: get-recommendations\n        description: Get personalized event recommendations\n        call: seatgeek-platform.get-recommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: event-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted live event discovery with SeatGeek.\n    tools:\n    - name: search-events\n      description: Search for live events by artist name, genre,\
  \ location, date range, or ticket price\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seatgeek-platform.list-events\n      with:\n        q: tools.q\n        lat: tools.lat\n        lon: tools.lon\n        range: tools.range\n        per_page: tools.per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-details\n      description: Get full details for a specific event including venue, performers, ticket pricing, and seat availability\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seatgeek-platform.get-event\n      with:\n        event_id: tools.event_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-performers\n      description: Search for concert artists, sports teams, theater companies, and other performers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seatgeek-platform.list-performers\n      with:\n        q:\
  \ tools.q\n        slug: tools.slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-performer-details\n      description: Get performer profile, genre, and upcoming event count\n      hints:\n        readOnly: true\n        openWorld: false\n      call: seatgeek-platform.get-performer\n      with:\n        performer_id: tools.performer_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-venues\n      description: Find event venues by city, state, country, or location radius\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seatgeek-platform.list-venues\n      with:\n        city: tools.city\n        state: tools.state\n        lat: tools.lat\n        lon: tools.lon\n        range: tools.range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-categories\n      description: List available event taxonomy categories such as concerts, sports, and theater\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: seatgeek-platform.list-taxonomies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-recommendations\n      description: Get personalized event recommendations based on user location and interests\n      hints:\n        readOnly: true\n        openWorld: true\n      call: seatgeek-platform.get-recommendations\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        performers.id: tools.performer_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/seatgeek/refs/heads/main/capabilities/event-discovery.yaml
tags:
- Events
- Live Events
- Concerts
- Sports
- Ticketing
- Discovery
tools:
- description: Search for live events by artist name, genre, location, date range, or ticket price
  hints:
    openWorld: true
    readOnly: true
  name: search-events
- description: Get full details for a specific event including venue, performers, ticket pricing, and seat availability
  hints:
    openWorld: false
    readOnly: true
  name: get-event-details
- description: Search for concert artists, sports teams, theater companies, and other performers
  hints:
    openWorld: true
    readOnly: true
  name: search-performers
- description: Get performer profile, genre, and upcoming event count
  hints:
    openWorld: false
    readOnly: true
  name: get-performer-details
- description: Find event venues by city, state, country, or location radius
  hints:
    openWorld: true
    readOnly: true
  name: search-venues
- description: List available event taxonomy categories such as concerts, sports, and theater
  hints:
    openWorld: false
    readOnly: true
  name: list-event-categories
- description: Get personalized event recommendations based on user location and interests
  hints:
    openWorld: true
    readOnly: true
  name: get-event-recommendations
---
