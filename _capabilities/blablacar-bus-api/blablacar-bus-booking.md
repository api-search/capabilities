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
- get ticket
- get booking
- retrieve booking details
- search for available coach trips between two stations on a specific date, returning departure times, seat availability, and pricing.
- cancel an existing blablacar bus booking. refund eligibility depends on the fare type.
- ticketing
- books coach tickets for customers as part of multi-modal travel itineraries
- Travel Agent
- OTA Developer
- create booking
- single booking retrieval and cancellation
- ota
- books affordable intercity coach travel for business travelers
- buses
- list stations in the blablacar bus network
- coach
- booking
- cancel a booking
- booking creation and management
- retrieve an electronic ticket with qr code for passenger validation on a blablacar bus trip.
- cancel booking
- Corporate Travel Manager
- list available blablacar bus coach routes between stations across europe.
- europe
- search available trips between stations on a given date
- retrieve the details of an existing blablacar bus booking including status and tickets.
- end-to-end coach booking workflow for otas and travel aggregators
- creating and managing coach reservations
- available coach routes in the blablacar bus network
- station information
- mobility
- list available coach routes between stations
- list stations
- integrates blablacar bus into travel booking platforms and aggregators
- electronic ticket retrieval
- travel
- retrieve electronic ticket with qr code
- books and manages coach trips via partner platforms
- search trips
- Traveler
- route search, trip availability, and station data
- list routes
- trip search with pricing and availability
- create a confirmed blablacar bus booking for one or more passengers on a specific trip.
- create a confirmed coach booking
- list all stations in the blablacar bus network, optionally filtered by country or search query.
- transportation
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
