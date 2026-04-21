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
- ground transfer reservation operations.
- hotels
- travel
- create a confirmed hotel booking.
- create hotel order
- flight reservation operations.
- create a confirmed airline reservation from a priced flight offer.
- reservations
- create a confirmed flight booking.
- Travel Booking Agent
- cancel an existing confirmed ground transfer reservation.
- get flight booking
- cancel transfer booking
- flights
- developer building ai-powered travel assistants that create bookings conversationally.
- create flight order
- create transfer order
- Travel Chatbot Developer
- human or automated agent creating and managing travel reservations on behalf of travelers.
- end-to-end travel booking combining flights, hotels, and transfers.
- amadeus
- cancel flight booking
- create hotel booking
- cancel an existing confirmed flight reservation.
- retrieve a flight booking.
- individual transfer management.
- cancel a transfer booking.
- cancel transfer order
- create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
- book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
- airline reservation creation and management.
- hotel reservation operations.
- create transfer booking
- create flight booking
- individual flight order management.
- create a confirmed transfer booking.
- hotel reservation creation.
- cancel flight order
- retrieve details of an existing flight reservation by order id.
- transfers
- get flight order
- booking
- ground transportation booking and management.
- cancel a flight booking.
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
