---
consumed_apis:
- square
description: Unified workflow for customer relationship management combining customers, loyalty programs, gift cards, bookings, team management, and location management. Used by business owners and customer success teams to build relationships and manage operations.
layout: capability
name: Square Customer Engagement
operations:
- description: List customer profiles.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer.
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get customer details.
  method: GET
  name: get-customer
  path: /v1/customers/{customer_id}
- description: Update a customer.
  method: PUT
  name: update-customer
  path: /v1/customers/{customer_id}
- description: Delete a customer.
  method: DELETE
  name: delete-customer
  path: /v1/customers/{customer_id}
- description: Get the loyalty program.
  method: GET
  name: get-loyalty-program
  path: /v1/loyalty
- description: List gift cards.
  method: GET
  name: list-gift-cards
  path: /v1/gift-cards
- description: Create a gift card.
  method: POST
  name: create-gift-card
  path: /v1/gift-cards
- description: List bookings.
  method: GET
  name: list-bookings
  path: /v1/bookings
- description: Create a booking.
  method: POST
  name: create-booking
  path: /v1/bookings
- description: Get booking details.
  method: GET
  name: get-booking
  path: /v1/bookings/{booking_id}
- description: Search team members.
  method: POST
  name: search-team-members
  path: /v1/team-members
- description: List business locations.
  method: GET
  name: list-locations
  path: /v1/locations
- description: Get merchant details.
  method: GET
  name: list-merchants
  path: /v1/merchants
personas: []
provider_name: Square
provider_slug: square
search_terms:
- list gift cards.
- search team members
- retrieve a gift card.
- locations
- list locations
- manage gift cards.
- square
- create team member
- manage a specific customer.
- list bookings
- manage a specific booking.
- search team members.
- update a team member.
- get location details.
- get gift card
- retail
- payments
- list customers
- create a new customer profile.
- ecommerce
- get booking details.
- search availability
- get the loyalty program.
- invoicing
- inventory
- search loyalty accounts
- webhooks
- create a loyalty account.
- manage team members.
- redeem loyalty reward
- labor
- list merchants
- create a digital gift card.
- update a customer.
- create a team member.
- create loyalty account
- cancel a booking.
- create gift card
- retrieve a booking.
- disputes
- create loyalty reward
- delete a customer.
- create a new customer.
- search customers
- manage locations.
- search for booking availability.
- get customer details.
- terminal
- list customer profiles.
- team management
- update team member
- get location
- update customer
- get merchant details.
- accumulate loyalty points
- customers
- update a customer profile.
- manage customers.
- get a team member.
- gift cards
- create booking
- retrieve the loyalty program.
- list all gift cards.
- catalog
- delete customer
- manage loyalty programs.
- create customer
- cancel booking
- get booking
- update booking
- list bookings.
- team
- financial technology
- get customer
- create a loyalty reward.
- orders
- create a booking.
- checkout
- redeem a loyalty reward.
- create a gift card.
- merchants
- search loyalty accounts.
- get loyalty program
- create location
- list business locations.
- manage bookings.
- search customer profiles.
- list gift cards
- refunds
- subscriptions
- add points to a loyalty account.
- update a booking.
- merchant information.
- delete a customer profile.
- point of sale
- loyalty
- get team member
- create a location.
- bookings
- get details for a specific customer.
slug: customer-engagement
tags:
- Square
- Customers
- Loyalty
- Gift Cards
- Bookings
- Team Management
tools:
- description: List customer profiles.
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Create a new customer profile.
  hints:
    idempotent: false
    readOnly: false
  name: create-customer
- description: Search customer profiles.
  hints:
    openWorld: true
    readOnly: true
  name: search-customers
- description: Get details for a specific customer.
  hints:
    openWorld: true
    readOnly: true
  name: get-customer
- description: Update a customer profile.
  hints:
    idempotent: true
    readOnly: false
  name: update-customer
- description: Delete a customer profile.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-customer
- description: Retrieve the loyalty program.
  hints:
    openWorld: true
    readOnly: true
  name: get-loyalty-program
- description: Search loyalty accounts.
  hints:
    openWorld: true
    readOnly: true
  name: search-loyalty-accounts
- description: Create a loyalty account.
  hints:
    idempotent: false
    readOnly: false
  name: create-loyalty-account
- description: Add points to a loyalty account.
  hints:
    idempotent: false
    readOnly: false
  name: accumulate-loyalty-points
- description: Create a loyalty reward.
  hints:
    idempotent: false
    readOnly: false
  name: create-loyalty-reward
- description: Redeem a loyalty reward.
  hints:
    idempotent: false
    readOnly: false
  name: redeem-loyalty-reward
- description: List all gift cards.
  hints:
    openWorld: true
    readOnly: true
  name: list-gift-cards
- description: Create a digital gift card.
  hints:
    idempotent: false
    readOnly: false
  name: create-gift-card
- description: Retrieve a gift card.
  hints:
    openWorld: true
    readOnly: true
  name: get-gift-card
- description: List bookings.
  hints:
    openWorld: true
    readOnly: true
  name: list-bookings
- description: Create a booking.
  hints:
    idempotent: false
    readOnly: false
  name: create-booking
- description: Retrieve a booking.
  hints:
    openWorld: true
    readOnly: true
  name: get-booking
- description: Update a booking.
  hints:
    idempotent: true
    readOnly: false
  name: update-booking
- description: Cancel a booking.
  hints:
    destructive: true
    readOnly: false
  name: cancel-booking
- description: Search for booking availability.
  hints:
    openWorld: true
    readOnly: true
  name: search-availability
- description: Search team members.
  hints:
    openWorld: true
    readOnly: true
  name: search-team-members
- description: Create a team member.
  hints:
    idempotent: false
    readOnly: false
  name: create-team-member
- description: Get a team member.
  hints:
    openWorld: true
    readOnly: true
  name: get-team-member
- description: Update a team member.
  hints:
    idempotent: true
    readOnly: false
  name: update-team-member
- description: List business locations.
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: Create a location.
  hints:
    idempotent: false
    readOnly: false
  name: create-location
- description: Get location details.
  hints:
    openWorld: true
    readOnly: true
  name: get-location
- description: Get merchant details.
  hints:
    openWorld: true
    readOnly: true
  name: list-merchants
---
