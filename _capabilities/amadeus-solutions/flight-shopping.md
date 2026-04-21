---
consumed_apis:
- flight-offers-search
- flight-offers-price
description: Unified workflow capability for complete flight shopping encompassing search, pricing, upsell, and seat selection. Used by OTA developers, airline retailing platforms, and travel chatbots to build end-to-end flight shopping experiences.
layout: capability
name: Amadeus Flight Shopping
operations:
- description: Search available flights by origin, destination, and date.
  method: GET
  name: search-flights
  path: /v1/flights/search
- description: Confirm current price and availability.
  method: POST
  name: confirm-price
  path: /v1/flights/price
personas: []
provider_name: Amadeus Solutions
provider_slug: amadeus-solutions
search_terms:
- amadeus
- flights
- developer building online travel agency flight search and booking flows.
- gds
- hotels
- search flights advanced
- pricing
- travel
- confirm the current price and availability of a selected flight offer before creating a booking.
- complete flight shopping flow from search through price confirmation.
- search flights
- confirm price
- search available flights by origin, destination, and date.
- search for available flights between two airports on a given date, with options for cabin class and passenger count.
- confirm pricing for a selected flight offer.
- travel technology
- upsell, seat selection, and add-on services.
- shopping
- airlines
- Travel Chatbot Developer
- confirm current price and availability.
- booking
- flight offer discovery and comparison.
- search for available flight offers.
- advanced flight search with complex criteria using request body for multi-city and detailed filters.
- OTA Developer
- search
- developer building conversational travel assistants for flight search.
- confirm flight price
- price confirmation and validation before booking.
slug: flight-shopping
tags:
- Amadeus
- Flights
- Shopping
- Search
- Pricing
- Travel
tools:
- description: Search for available flights between two airports on a given date, with options for cabin class and passenger count.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Advanced flight search with complex criteria using request body for multi-city and detailed filters.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights-advanced
- description: Confirm the current price and availability of a selected flight offer before creating a booking.
  hints:
    openWorld: true
    readOnly: true
  name: confirm-flight-price
---
