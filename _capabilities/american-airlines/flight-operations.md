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
- get real-time status of an american airlines flight
- developer experience
- real-time flight status
- airlines
- search flight schedules
- Travel Technology Developer
- builds travel apps integrating american airlines flight data
- booking
- american airlines
- search flights
- flight search and schedules
- travel app workflow for searching and tracking american airlines flights
- flight operations
- uses flight data to assist customers with bookings
- travel
- search american airlines flight schedules by origin, destination, and date
- aviation
- flights
- get flight status
- Booking Agent
- travel technology
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
