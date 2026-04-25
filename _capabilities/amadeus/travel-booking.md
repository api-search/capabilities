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
- search for available hotel rooms and rates for specific hotel properties.
- transfer search, booking, and management.
- hotel search, availability, and booking.
- tourism
- points of interest, tours, activities, and destination data.
- airlines
- flight search.
- destinations
- booking
- search flights
- search available flights.
- developer building travel search and booking applications using amadeus apis.
- travel
- search hotels
- Travel Developer
- aviation
- flights
- transfers
- amadeus
- online travel agency team managing flight, hotel, and transfer bookings.
- end-to-end trip booking combining flight search, hotel search, and transfer booking.
- flight search, pricing, booking, and order management.
- hospitality
- hotels
- search available hotels.
- search for available flights between two cities on a given date.
- hotel search.
- OTA Booking Team
- market insights
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
