---
consumed_apis:
- alaska-flight-status
- alaska-cargo
description: Workflow capability combining Alaska Airlines Flight Status and Cargo APIs for travel operations management. Enables travel agents, corporate travel managers, and freight forwarders to track flights, monitor cargo shipments, and get rate estimates in a unified interface.
layout: capability
name: Alaska Airlines Travel Operations
operations:
- description: List Alaska Airlines flights by route and date
  method: GET
  name: list-flights
  path: /v1/flights
- description: Get real-time status for a specific flight
  method: GET
  name: get-flight-status
  path: /v1/flights/{flightNumber}/status
- description: List cargo shipments
  method: GET
  name: list-cargo-shipments
  path: /v1/cargo/shipments
- description: Book a new cargo shipment
  method: POST
  name: book-cargo-shipment
  path: /v1/cargo/shipments
- description: Track cargo shipment by AWB number
  method: GET
  name: track-cargo-shipment
  path: /v1/cargo/shipments/{awbNumber}
- description: Get cargo rate estimate
  method: POST
  name: get-cargo-rate
  path: /v1/cargo/rates
personas: []
provider_name: Alaska Airlines
provider_slug: alaska-air
search_terms:
- travel operations
- travel
- mileage plan member management and partner miles
- get real-time status for a specific alaska airlines flight including departure/arrival times, gate, and delay information.
- flight tracking and cargo management for travel operations
- list alaska airlines flights by route and date
- cargo shipment booking and listing
- get cargo rate
- list alaska airlines flights for a specific route and date with real-time status, delays, and gate assignments.
- real-time flight status
- get alaska flight status
- cargo professional booking and tracking alaska air cargo shipments across 115+ domestic and international destinations.
- alaska airlines
- list cargo shipments
- list flights
- Corporate Travel Manager
- airlines
- list alaska flights
- get flight status
- flight status
- corporate travel manager tracking employee flights on alaska airlines and managing cargo logistics.
- get rate estimate for alaska air cargo shipment based on origin, destination, weight, and number of pieces.
- book a new alaska air cargo shipment to 115+ destinations worldwide
- cargo booking, tracking, and rate management
- flight status and scheduling
- cargo shipment tracking
- track alaska air cargo shipment by air waybill number with event history
- real-time flight status, schedules, and airport data
- Travel Agent
- cargo rate estimation
- Freight Forwarder
- book cargo shipment
- get cargo rate estimate
- loyalty
- aviation
- cargo
- get real-time status for a specific flight
- track cargo shipment by awb number
- track cargo shipment
- book a new cargo shipment
- travel professional monitoring alaska airlines flight status and delays for customer itinerary management.
slug: travel-operations
tags:
- Alaska Airlines
- Travel Operations
- Aviation
- Cargo
- Flight Status
tools:
- description: List Alaska Airlines flights for a specific route and date with real-time status, delays, and gate assignments.
  hints:
    openWorld: false
    readOnly: true
  name: list-alaska-flights
- description: Get real-time status for a specific Alaska Airlines flight including departure/arrival times, gate, and delay information.
  hints:
    openWorld: false
    readOnly: true
  name: get-alaska-flight-status
- description: Get rate estimate for Alaska Air Cargo shipment based on origin, destination, weight, and number of pieces.
  hints:
    openWorld: false
    readOnly: true
  name: get-cargo-rate-estimate
- description: Book a new Alaska Air Cargo shipment to 115+ destinations worldwide
  hints:
    openWorld: false
    readOnly: false
  name: book-cargo-shipment
- description: Track Alaska Air Cargo shipment by Air Waybill number with event history
  hints:
    openWorld: false
    readOnly: true
  name: track-cargo-shipment
---
