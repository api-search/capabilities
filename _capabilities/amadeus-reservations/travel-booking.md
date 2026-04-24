---
consumed_apis:
- hotel-booking
- flight-orders
- transfer-booking
description: Unified workflow capability for complete travel booking encompassing flight reservations, hotel bookings, and ground transfer arrangements. Used by online travel agencies, travel chatbots, and corporate travel management platforms to create end-to-end trip reservations.
layout: capability
name: Amadeus Travel Booking
operations:
- description: Create a confirmed flight booking.
  method: POST
  name: create-flight-order
  path: /v1/bookings/flights
- description: Retrieve a flight booking.
  method: GET
  name: get-flight-order
  path: /v1/bookings/flights/{orderId}
- description: Cancel a flight booking.
  method: DELETE
  name: cancel-flight-order
  path: /v1/bookings/flights/{orderId}
- description: Create a confirmed hotel booking.
  method: POST
  name: create-hotel-order
  path: /v1/bookings/hotels
- description: Create a confirmed transfer booking.
  method: POST
  name: create-transfer-order
  path: /v1/bookings/transfers
- description: Cancel a transfer booking.
  method: DELETE
  name: cancel-transfer-order
  path: /v1/bookings/transfers/{transferOrderId}
personas: []
provider_name: Amadeus Reservations
provider_slug: amadeus-reservations
search_terms:
- end-to-end travel booking combining flights, hotels, and transfers.
- developer building ai-powered travel assistants that create bookings conversationally.
- book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
- individual transfer management.
- cancel an existing confirmed flight reservation.
- Travel Booking Agent
- create flight booking
- flights
- human or automated agent creating and managing travel reservations on behalf of travelers.
- transfers
- cancel transfer order
- cancel a flight booking.
- retrieve a flight booking.
- hotel reservation operations.
- create a confirmed airline reservation from a priced flight offer.
- ground transportation booking and management.
- reservations
- hotel reservation creation.
- create hotel booking
- amadeus
- booking
- create transfer booking
- cancel an existing confirmed ground transfer reservation.
- cancel flight booking
- flight reservation operations.
- create a confirmed hotel booking.
- create transfer order
- get flight order
- Travel Chatbot Developer
- get flight booking
- create hotel order
- create flight order
- retrieve details of an existing flight reservation by order id.
- ground transfer reservation operations.
- travel
- create a confirmed flight booking.
- cancel a transfer booking.
- cancel flight order
- create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
- individual flight order management.
- hotels
- create a confirmed transfer booking.
- airline reservation creation and management.
- cancel transfer booking
slug: travel-booking
tags:
- Amadeus
- Booking
- Flights
- Hotels
- Transfers
- Travel
tools:
- description: Create a confirmed airline reservation from a priced flight offer.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-flight-booking
- description: Retrieve details of an existing flight reservation by order ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-booking
- description: Cancel an existing confirmed flight reservation.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-flight-booking
- description: Create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-hotel-booking
- description: Book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-transfer-booking
- description: Cancel an existing confirmed ground transfer reservation.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-transfer-booking
---
