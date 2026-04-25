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
- travel
- cancel an existing confirmed flight reservation.
- cancel an existing confirmed ground transfer reservation.
- developer building ai-powered travel assistants that create bookings conversationally.
- get flight order
- create flight order
- ground transportation booking and management.
- flight reservation operations.
- end-to-end travel booking combining flights, hotels, and transfers.
- hotel reservation creation.
- retrieve details of an existing flight reservation by order id.
- cancel flight booking
- flights
- cancel a flight booking.
- reservations
- human or automated agent creating and managing travel reservations on behalf of travelers.
- create flight booking
- booking
- create transfer order
- book a ground transfer (airport taxi, private car, or shuttle) for a traveler.
- transfers
- retrieve a flight booking.
- cancel transfer booking
- get flight booking
- cancel flight order
- hotels
- hotel reservation operations.
- create hotel order
- create a confirmed hotel booking.
- ground transfer reservation operations.
- cancel a transfer booking.
- create a confirmed hotel reservation from a hotel offer at any of 150,000+ hotels worldwide.
- create a confirmed flight booking.
- Travel Booking Agent
- create a confirmed airline reservation from a priced flight offer.
- create transfer booking
- individual flight order management.
- airline reservation creation and management.
- create hotel booking
- cancel transfer order
- Travel Chatbot Developer
- amadeus
- create a confirmed transfer booking.
- individual transfer management.
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
