---
categories: []
consumed_apis:
- seatgeek-platform
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
- list taxonomies
- get personalized event recommendations
- find event venues by city, state, country, or location radius
- list performers
- get event recommendations
- find venues by city, state, or location radius
- get recommendations
- browse performers
- list event categories
- list available event taxonomy categories such as concerts, sports, and theater
- venues
- list all event taxonomy categories
- search events
- personalized event recommendations
- list venues
- get performer
- list events
- search venues
- get event
- performer profile and upcoming events
- get event details
- tickets
- search events by keyword, performer, venue, date, or location
- search for artists, teams, and performers
- events
- search performers
- get performer details
- get personalized event recommendations based on user location and interests
- event categories and classifications
- get full details for a specific event including venue, performers, ticket pricing, and seat availability
- search for concert artists, sports teams, theater companies, and other performers
- discovery
- concerts
- sports
- search and browse live events
- ticketing
- live events
- search for live events by artist name, genre, location, date range, or ticket price
- get full event details with ticket pricing
- get performer profile, genre, and upcoming event count
- event details and ticket pricing
slug: event-discovery
source_filename: event-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SeatGeek Event Discovery\"\n  description: >-\n    Unified event discovery capability combining SeatGeek's events, performers, venues,\n    and recommendation APIs. Enables applications to build comprehensive live event\n    discovery experiences with geolocation search, performer browsing, venue exploration,\n    and personalized recommendations for concerts, sports, and theater.\n  tags:\n    - Events\n    - Live Events\n    - Concerts\n    - Sports\n    - Ticketing\n    - Discovery\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEATGEEK_CLIENT_ID: SEATGEEK_CLIENT_ID\n\ncapability:\n  consumes:\n    - import: seatgeek-platform\n      location: ./shared/platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: event-discovery-api\n      description: \"Unified REST API for live event discovery with SeatGeek.\"\n      resources:\n        - path: /v1/events\n\
  \          name: events\n          description: \"Search and browse live events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"Search events by keyword, performer, venue, date, or location\"\n              call: \"seatgeek-platform.list-events\"\n              with:\n                q: \"rest.q\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                range: \"rest.range\"\n                per_page: \"rest.per_page\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/{event_id}\n          name: event-detail\n          description: \"Event details and ticket pricing\"\n          operations:\n            - method: GET\n              name: get-event\n              description: \"Get full event details with ticket pricing\"\n              call: \"seatgeek-platform.get-event\"\n\
  \              with:\n                event_id: \"rest.event_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/performers\n          name: performers\n          description: \"Browse performers\"\n          operations:\n            - method: GET\n              name: list-performers\n              description: \"Search for artists, teams, and performers\"\n              call: \"seatgeek-platform.list-performers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/performers/{performer_id}\n          name: performer-detail\n          description: \"Performer profile and upcoming events\"\n          operations:\n            - method: GET\n              name: get-performer\n              description: \"Get performer details\"\n              call: \"seatgeek-platform.get-performer\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/venues\n          name: venues\n          description: \"Search venues\"\n          operations:\n            - method: GET\n              name: list-venues\n              description: \"Find venues by city, state, or location radius\"\n              call: \"seatgeek-platform.list-venues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/taxonomies\n          name: taxonomies\n          description: \"Event categories and classifications\"\n          operations:\n            - method: GET\n              name: list-taxonomies\n              description: \"List all event taxonomy categories\"\n              call: \"seatgeek-platform.list-taxonomies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations\n          name: recommendations\n          description: \"Personalized event\
  \ recommendations\"\n          operations:\n            - method: GET\n              name: get-recommendations\n              description: \"Get personalized event recommendations\"\n              call: \"seatgeek-platform.get-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: event-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted live event discovery with SeatGeek.\"\n      tools:\n        - name: search-events\n          description: \"Search for live events by artist name, genre, location, date range, or ticket price\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seatgeek-platform.list-events\"\n          with:\n            q: \"tools.q\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            range: \"tools.range\"\n            per_page: \"tools.per_page\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-details\n          description: \"Get full details for a specific event including venue, performers, ticket pricing, and seat availability\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seatgeek-platform.get-event\"\n          with:\n            event_id: \"tools.event_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-performers\n          description: \"Search for concert artists, sports teams, theater companies, and other performers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seatgeek-platform.list-performers\"\n          with:\n            q: \"tools.q\"\n            slug: \"tools.slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-performer-details\n\
  \          description: \"Get performer profile, genre, and upcoming event count\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seatgeek-platform.get-performer\"\n          with:\n            performer_id: \"tools.performer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-venues\n          description: \"Find event venues by city, state, country, or location radius\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seatgeek-platform.list-venues\"\n          with:\n            city: \"tools.city\"\n            state: \"tools.state\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            range: \"tools.range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-event-categories\n          description: \"List available event taxonomy categories such\
  \ as concerts, sports, and theater\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seatgeek-platform.list-taxonomies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-recommendations\n          description: \"Get personalized event recommendations based on user location and interests\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seatgeek-platform.get-recommendations\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            performers.id: \"tools.performer_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
