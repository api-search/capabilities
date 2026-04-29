---
categories:
- customer-engagement
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
- list merchants
- search loyalty accounts
- create gift card
- create team member
- merchant information.
- update team member
- manage bookings.
- create a new customer profile.
- labor
- search team members
- create a loyalty reward.
- create booking
- create customer
- cancel a booking.
- accumulate loyalty points
- get merchant details.
- gift cards
- create a new customer.
- delete customer
- search loyalty accounts.
- manage team members.
- add points to a loyalty account.
- checkout
- orders
- list bookings
- search team members.
- get team member
- list customer profiles.
- manage a specific booking.
- square
- manage gift cards.
- update booking
- create loyalty account
- get the loyalty program.
- webhooks
- get gift card
- get details for a specific customer.
- manage a specific customer.
- create a gift card.
- update a customer profile.
- create a digital gift card.
- get booking details.
- create location
- get location
- create a loyalty account.
- retail
- delete a customer profile.
- search availability
- update a booking.
- update a customer.
- invoicing
- list gift cards
- redeem a loyalty reward.
- list bookings.
- subscriptions
- redeem loyalty reward
- get a team member.
- list gift cards.
- ecommerce
- financial technology
- catalog
- manage customers.
- retrieve a booking.
- disputes
- create a booking.
- retrieve a gift card.
- delete a customer.
- merchants
- get customer
- inventory
- get customer details.
- list business locations.
- list customers
- payments
- loyalty
- retrieve the loyalty program.
- search customers
- search customer profiles.
- get booking
- manage loyalty programs.
- terminal
- update a team member.
- get location details.
- list locations
- create a team member.
- create a location.
- locations
- customers
- point of sale
- manage locations.
- search for booking availability.
- refunds
- bookings
- list all gift cards.
- team
- get loyalty program
- cancel booking
- team management
- create loyalty reward
- update customer
slug: customer-engagement
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Square Customer Engagement\"\n  description: \"Unified workflow for customer relationship management combining customers, loyalty programs, gift cards, bookings, team management, and location management. Used by business owners and customer success teams to build relationships and manage operations.\"\n  tags:\n    - Square\n    - Customers\n    - Loyalty\n    - Gift Cards\n    - Bookings\n    - Team Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SQUARE_ACCESS_TOKEN: SQUARE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: square\n      location: ./shared/square-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: square-engagement-api\n      description: \"Unified REST API for Square customer engagement, loyalty, bookings, and team management.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n         \
  \ description: \"Manage customers.\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customer profiles.\"\n              call: \"square.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer.\"\n              call: \"square.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customer_id}\n          name: customer\n          description: \"Manage a specific customer.\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get customer details.\"\n              call: \"square.get-customer\"\n              with:\n                customer_id: \"rest.customer_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-customer\n              description: \"Update a customer.\"\n              call: \"square.update-customer\"\n              with:\n                customer_id: \"rest.customer_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-customer\n              description: \"Delete a customer.\"\n              call: \"square.delete-customer\"\n              with:\n                customer_id: \"rest.customer_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/loyalty\n          name: loyalty\n          description: \"Manage loyalty programs.\"\n          operations:\n            - method: GET\n              name: get-loyalty-program\n              description: \"Get the loyalty program.\"\n \
  \             call: \"square.get-loyalty-program\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/gift-cards\n          name: gift-cards\n          description: \"Manage gift cards.\"\n          operations:\n            - method: GET\n              name: list-gift-cards\n              description: \"List gift cards.\"\n              call: \"square.list-gift-cards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-gift-card\n              description: \"Create a gift card.\"\n              call: \"square.create-gift-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bookings\n          name: bookings\n          description: \"Manage bookings.\"\n          operations:\n            - method: GET\n              name: list-bookings\n\
  \              description: \"List bookings.\"\n              call: \"square.list-bookings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-booking\n              description: \"Create a booking.\"\n              call: \"square.create-booking\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bookings/{booking_id}\n          name: booking\n          description: \"Manage a specific booking.\"\n          operations:\n            - method: GET\n              name: get-booking\n              description: \"Get booking details.\"\n              call: \"square.get-booking\"\n              with:\n                booking_id: \"rest.booking_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/team-members\n          name: team-members\n   \
  \       description: \"Manage team members.\"\n          operations:\n            - method: POST\n              name: search-team-members\n              description: \"Search team members.\"\n              call: \"square.search-team-members\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: locations\n          description: \"Manage locations.\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"List business locations.\"\n              call: \"square.list-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/merchants\n          name: merchants\n          description: \"Merchant information.\"\n          operations:\n            - method: GET\n              name: list-merchants\n              description: \"Get merchant details.\"\n         \
  \     call: \"square.list-merchants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: square-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted customer engagement, loyalty, and business management.\"\n      tools:\n        - name: list-customers\n          description: \"List customer profiles.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-customer\n          description: \"Create a new customer profile.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-customers\n          description:\
  \ \"Search customer profiles.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-customer\n          description: \"Get details for a specific customer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-customer\n          description: \"Update a customer profile.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"square.update-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-customer\n\
  \          description: \"Delete a customer profile.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"square.delete-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-loyalty-program\n          description: \"Retrieve the loyalty program.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-loyalty-program\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-loyalty-accounts\n          description: \"Search loyalty accounts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-loyalty-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-loyalty-account\n\
  \          description: \"Create a loyalty account.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-loyalty-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: accumulate-loyalty-points\n          description: \"Add points to a loyalty account.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.accumulate-loyalty-points\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-loyalty-reward\n          description: \"Create a loyalty reward.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-loyalty-reward\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: redeem-loyalty-reward\n          description: \"Redeem a loyalty reward.\"\
  \n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.redeem-loyalty-reward\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-gift-cards\n          description: \"List all gift cards.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-gift-cards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-gift-card\n          description: \"Create a digital gift card.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-gift-card\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-gift-card\n          description: \"Retrieve a gift card.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-gift-card\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bookings\n          description: \"List bookings.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-bookings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-booking\n          description: \"Create a booking.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-booking\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-booking\n          description: \"Retrieve a booking.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-booking\"\n          with:\n            booking_id: \"tools.booking_id\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n\n        - name: update-booking\n          description: \"Update a booking.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"square.update-booking\"\n          with:\n            booking_id: \"tools.booking_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-booking\n          description: \"Cancel a booking.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"square.cancel-booking\"\n          with:\n            booking_id: \"tools.booking_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-availability\n          description: \"Search for booking availability.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-availability\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: search-team-members\n          description: \"Search team members.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-team-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-team-member\n          description: \"Create a team member.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-team-member\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team-member\n          description: \"Get a team member.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-team-member\"\n          with:\n            team_member_id: \"tools.team_member_id\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n\n        - name: update-team-member\n          description: \"Update a team member.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"square.update-team-member\"\n          with:\n            team_member_id: \"tools.team_member_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-locations\n          description: \"List business locations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-location\n          description: \"Create a location.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-location\n\
  \          description: \"Get location details.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-location\"\n          with:\n            location_id: \"tools.location_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-merchants\n          description: \"Get merchant details.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-merchants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/square/refs/heads/main/capabilities/customer-engagement.yaml
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
