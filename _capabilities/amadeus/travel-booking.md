---
categories:
- travel-booking
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
- search hotels
- end-to-end trip booking combining flight search, hotel search, and transfer booking.
- flights
- search available flights.
- flight search.
- hotels
- search for available flights between two cities on a given date.
- online travel agency team managing flight, hotel, and transfer bookings.
- Travel Developer
- airlines
- aviation
- hotel search.
- booking
- flight search, pricing, booking, and order management.
- developer building travel search and booking applications using amadeus apis.
- points of interest, tours, activities, and destination data.
- transfer search, booking, and management.
- travel
- search for available hotel rooms and rates for specific hotel properties.
- amadeus
- search available hotels.
- hotel search, availability, and booking.
- destinations
- hospitality
- OTA Booking Team
- search flights
- tourism
- transfers
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
