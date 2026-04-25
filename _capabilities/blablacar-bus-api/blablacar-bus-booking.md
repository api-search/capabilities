---
consumed_apis:
- blablacar-bus
description: Workflow capability for end-to-end coach booking on the BlaBlaCar Bus network. Enables OTAs, travel aggregators, and corporate travel platforms to search routes and trips, create bookings, manage tickets, and access station information across European markets.
layout: capability
name: BlaBlaCar Bus Booking
operations:
- description: List available coach routes between stations
  method: GET
  name: list-routes
  path: /v1/routes
- description: Search available trips between stations on a given date
  method: GET
  name: search-trips
  path: /v1/trips
- description: Create a confirmed coach booking
  method: POST
  name: create-booking
  path: /v1/bookings
- description: Retrieve booking details
  method: GET
  name: get-booking
  path: /v1/bookings/{booking_id}
- description: Cancel a booking
  method: DELETE
  name: cancel-booking
  path: /v1/bookings/{booking_id}
- description: Retrieve electronic ticket with QR code
  method: GET
  name: get-ticket
  path: /v1/tickets/{ticket_id}
- description: List stations in the BlaBlaCar Bus network
  method: GET
  name: list-stations
  path: /v1/stations
personas: []
provider_name: BlaBlaCar Bus API
provider_slug: blablacar-bus-api
search_terms:
- retrieve booking details
- cancel an existing blablacar bus booking. refund eligibility depends on the fare type.
- integrates blablacar bus into travel booking platforms and aggregators
- search available trips between stations on a given date
- Corporate Travel Manager
- europe
- cancel a booking
- create a confirmed blablacar bus booking for one or more passengers on a specific trip.
- retrieve an electronic ticket with qr code for passenger validation on a blablacar bus trip.
- list all stations in the blablacar bus network, optionally filtered by country or search query.
- create booking
- mobility
- list stations in the blablacar bus network
- list available coach routes between stations
- OTA Developer
- get ticket
- booking
- creating and managing coach reservations
- list available blablacar bus coach routes between stations across europe.
- transportation
- electronic ticket retrieval
- station information
- trip search with pricing and availability
- available coach routes in the blablacar bus network
- Traveler
- route search, trip availability, and station data
- buses
- booking creation and management
- end-to-end coach booking workflow for otas and travel aggregators
- travel
- search trips
- retrieve electronic ticket with qr code
- books coach tickets for customers as part of multi-modal travel itineraries
- cancel booking
- get booking
- list routes
- list stations
- search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.
- Travel Agent
- books and manages coach trips via partner platforms
- ticketing
- retrieve the details of an existing blablacar bus booking including status and tickets.
- books affordable intercity coach travel for business travelers
- ota
- create a confirmed coach booking
- coach
- single booking retrieval and cancellation
slug: blablacar-bus-booking
tags:
- Booking
- Buses
- Coach
- Europe
- Mobility
- OTA
- Ticketing
- Transportation
- Travel
tools:
- description: List available BlaBlaCar Bus coach routes between stations across Europe.
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.
  hints:
    openWorld: true
    readOnly: true
  name: search-trips
- description: Create a confirmed BlaBlaCar Bus booking for one or more passengers on a specific trip.
  hints:
    openWorld: false
    readOnly: false
  name: create-booking
- description: Retrieve the details of an existing BlaBlaCar Bus booking including status and tickets.
  hints:
    openWorld: false
    readOnly: true
  name: get-booking
- description: Cancel an existing BlaBlaCar Bus booking. Refund eligibility depends on the fare type.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-booking
- description: Retrieve an electronic ticket with QR code for passenger validation on a BlaBlaCar Bus trip.
  hints:
    openWorld: false
    readOnly: true
  name: get-ticket
- description: List all stations in the BlaBlaCar Bus network, optionally filtered by country or search query.
  hints:
    openWorld: true
    readOnly: true
  name: list-stations
---
