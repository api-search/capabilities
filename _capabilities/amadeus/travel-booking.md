---
consumed_apis:
- flight-offers-search
- hotel-search
description: End-to-end travel booking workflow combining flight search, pricing, booking, hotel search, hotel booking, and transfer search for complete trip planning and reservation.
layout: capability
name: Amadeus Full Travel Booking
operations:
- description: Search available flights.
  method: GET
  name: search-flights
  path: /v1/flights/offers
- description: Search available hotels.
  method: GET
  name: search-hotels
  path: /v1/hotels/offers
personas: []
provider_name: Amadeus
provider_slug: amadeus
search_terms:
- end-to-end trip booking combining flight search, hotel search, and transfer booking.
- hotel search.
- flight search, pricing, booking, and order management.
- transfer search, booking, and management.
- flights
- OTA Booking Team
- booking
- search hotels
- flight search.
- transfers
- hospitality
- developer building travel search and booking applications using amadeus apis.
- market insights
- aviation
- airlines
- online travel agency team managing flight, hotel, and transfer bookings.
- Travel Developer
- destinations
- hotels
- tourism
- search for available flights between two cities on a given date.
- amadeus
- travel
- search for available hotel rooms and rates for specific hotel properties.
- search flights
- search available hotels.
- search available flights.
- hotel search, availability, and booking.
- points of interest, tours, activities, and destination data.
slug: travel-booking
tags:
- Amadeus
- Flights
- Hotels
- Transfers
- Booking
- Travel
tools:
- description: Search for available flights between two cities on a given date.
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Search for available hotel rooms and rates for specific hotel properties.
  hints:
    openWorld: true
    readOnly: true
  name: search-hotels
---
