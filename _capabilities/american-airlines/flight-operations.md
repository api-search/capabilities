---
consumed_apis:
- aa-runway
description: Unified workflow for travel applications and agents accessing American Airlines flight data, status, and booking capabilities. Serves travel technology teams and booking platform developers.
layout: capability
name: American Airlines Flight Operations
operations:
- description: Search flight schedules
  method: GET
  name: search-flights
  path: /v1/flights
- description: Get flight status
  method: GET
  name: get-flight-status
  path: /v1/flights/{flightId}/status
personas: []
provider_name: American Airlines
provider_slug: american-airlines
search_terms:
- Booking Agent
- aviation
- uses flight data to assist customers with bookings
- search flights
- flights
- flight search and schedules
- travel app workflow for searching and tracking american airlines flights
- real-time flight status
- get flight status
- booking
- get real-time status of an american airlines flight
- builds travel apps integrating american airlines flight data
- airlines
- Travel Technology Developer
- flight operations
- american airlines
- search flight schedules
- search american airlines flight schedules by origin, destination, and date
- travel
- travel technology
- developer experience
slug: flight-operations
tags:
- American Airlines
- Airlines
- Flight Operations
- Travel Technology
- Booking
tools:
- description: Search American Airlines flight schedules by origin, destination, and date
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Get real-time status of an American Airlines flight
  hints:
    readOnly: true
  name: get-flight-status
---
