---
categories: []
consumed_apis:
- uber-eats
- uber-direct
description: Workflow capability combining Uber Eats (restaurant ordering and store management) and Uber Direct (on-demand courier delivery) APIs. Supports restaurant operators, e-commerce merchants, and delivery platform integrators needing unified food ordering and delivery dispatch.
layout: capability
name: Uber Food and Delivery
operations:
- description: List all stores for the authenticated Uber Eats partner.
  method: GET
  name: list-stores
  path: /v1/stores
- description: Get details for a specific Uber Eats store.
  method: GET
  name: get-store
  path: /v1/stores/{store_id}
- description: Get the current menu for a store.
  method: GET
  name: get-store-menu
  path: /v1/stores/{store_id}/menu
- description: Get details for a specific Uber Eats order.
  method: GET
  name: get-order
  path: /v1/orders/{order_id}
- description: Get a price quote for an on-demand delivery.
  method: POST
  name: get-delivery-quote
  path: /v1/deliveries/quotes
- description: Dispatch an Uber courier for on-demand delivery.
  method: POST
  name: create-delivery
  path: /v1/deliveries
- description: Get the current status of a delivery order.
  method: GET
  name: get-delivery
  path: /v1/deliveries/{order_id}
- description: Cancel an active delivery order.
  method: DELETE
  name: cancel-delivery
  path: /v1/deliveries/{order_id}
- description: List all business pickup locations.
  method: GET
  name: list-pickup-locations
  path: /v1/pickup-locations
personas: []
provider_name: Uber
provider_slug: uber
search_terms:
- uber eats store listings.
- uber
- get delivery
- list all stores for the authenticated uber eats partner.
- uber direct
- list stores
- quote direct delivery
- deny eats order
- business pickup location management for uber direct.
- uber direct delivery dispatch.
- cancel delivery
- restaurants
- cancel an active uber direct delivery.
- individual uber direct delivery tracking and management.
- get eats order
- uber eats
- accept eats order
- create delivery
- get the current status of a delivery order.
- get eats store
- accept a pending uber eats order.
- delivery
- get the current menu for an uber eats store.
- list eats stores
- deny a pending uber eats order with a reason.
- uber eats store menu management.
- rides
- list pickup locations
- cancel an active delivery order.
- cancel direct delivery
- list all business pickup locations.
- track direct delivery
- get order
- dispatch an uber courier for an on-demand delivery.
- create direct delivery
- get details for a specific uber eats order.
- individual uber eats store details.
- ride-sharing
- taxis
- list business pickup locations configured for uber direct.
- get store menu
- get a price quote for an uber direct on-demand delivery.
- uber eats order management.
- get the current menu for a store.
- get details for a specific uber eats store.
- get delivery quote
- transportation
- get a price quote for an on-demand delivery.
- list all uber eats stores for the partner account.
- food delivery
- dispatch an uber courier for on-demand delivery.
- logistics
- get details for a specific uber eats restaurant store.
- track the real-time status of an uber direct delivery.
- get details for an uber eats order.
- uber direct delivery price quotes.
- get store
slug: food-and-delivery
source_filename: food-and-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Uber Food and Delivery\"\n  description: >-\n    Workflow capability combining Uber Eats (restaurant ordering and store management) and\n    Uber Direct (on-demand courier delivery) APIs. Supports restaurant operators, e-commerce\n    merchants, and delivery platform integrators needing unified food ordering and delivery dispatch.\n  tags:\n    - Uber\n    - Uber Eats\n    - Uber Direct\n    - Food Delivery\n    - Delivery\n    - Logistics\n    - Restaurants\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UBER_EATS_ACCESS_TOKEN: UBER_EATS_ACCESS_TOKEN\n      UBER_DIRECT_ACCESS_TOKEN: UBER_DIRECT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: uber-eats\n      location: ./shared/eats.yaml\n    - import: uber-direct\n      location: ./shared/direct.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: uber-food-delivery-api\n      description: \"Unified\
  \ REST API for Uber Eats store management and Uber Direct delivery operations.\"\n      resources:\n        - path: /v1/stores\n          name: stores\n          description: \"Uber Eats store listings.\"\n          operations:\n            - method: GET\n              name: list-stores\n              description: \"List all stores for the authenticated Uber Eats partner.\"\n              call: \"uber-eats.list-stores\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stores/{store_id}\n          name: store\n          description: \"Individual Uber Eats store details.\"\n          operations:\n            - method: GET\n              name: get-store\n              description: \"Get details for a specific Uber Eats store.\"\n              call: \"uber-eats.get-store\"\n              with:\n                store_id:\
  \ \"rest.store_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stores/{store_id}/menu\n          name: store-menu\n          description: \"Uber Eats store menu management.\"\n          operations:\n            - method: GET\n              name: get-store-menu\n              description: \"Get the current menu for a store.\"\n              call: \"uber-eats.get-store-menu\"\n              with:\n                store_id: \"rest.store_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{order_id}\n          name: order\n          description: \"Uber Eats order management.\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get details for a specific Uber Eats order.\"\n              call: \"uber-eats.get-order\"\n              with:\n                order_id: \"rest.order_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deliveries/quotes\n          name: delivery-quotes\n          description: \"Uber Direct delivery price quotes.\"\n          operations:\n            - method: POST\n              name: get-delivery-quote\n              description: \"Get a price quote for an on-demand delivery.\"\n              call: \"uber-direct.get-delivery-quote\"\n              with:\n                pickup_address: \"rest.pickup_address\"\n                dropoff_address: \"rest.dropoff_address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deliveries\n          name: deliveries\n          description: \"Uber Direct delivery dispatch.\"\n          operations:\n            - method: POST\n              name: create-delivery\n              description: \"Dispatch an Uber courier for on-demand delivery.\"\n         \
  \     call: \"uber-direct.create-delivery\"\n              with:\n                pickup_name: \"rest.pickup_name\"\n                pickup_address: \"rest.pickup_address\"\n                dropoff_name: \"rest.dropoff_name\"\n                dropoff_address: \"rest.dropoff_address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deliveries/{order_id}\n          name: delivery\n          description: \"Individual Uber Direct delivery tracking and management.\"\n          operations:\n            - method: GET\n              name: get-delivery\n              description: \"Get the current status of a delivery order.\"\n              call: \"uber-direct.get-delivery\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-delivery\n              description:\
  \ \"Cancel an active delivery order.\"\n              call: \"uber-direct.cancel-delivery\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pickup-locations\n          name: pickup-locations\n          description: \"Business pickup location management for Uber Direct.\"\n          operations:\n            - method: GET\n              name: list-pickup-locations\n              description: \"List all business pickup locations.\"\n              call: \"uber-direct.list-business-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: uber-food-delivery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted food ordering and delivery dispatch.\"\n      tools:\n        - name: list-eats-stores\n          description: \"List\
  \ all Uber Eats stores for the partner account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-eats.list-stores\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-eats-store\n          description: \"Get details for a specific Uber Eats restaurant store.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-eats.get-store\"\n          with:\n            store_id: \"tools.store_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-store-menu\n          description: \"Get the current menu for an Uber Eats store.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-eats.get-store-menu\"\n          with:\n            store_id: \"tools.store_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-eats-order\n          description: \"Get details for an Uber Eats order.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-eats.get-order\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: accept-eats-order\n          description: \"Accept a pending Uber Eats order.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uber-eats.accept-order\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deny-eats-order\n          description: \"Deny a pending Uber Eats order with a reason.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"uber-eats.deny-order\"\n          with:\n            order_id: \"tools.order_id\"\n            reason: \"tools.reason\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: quote-direct-delivery\n          description: \"Get a price quote for an Uber Direct on-demand delivery.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uber-direct.get-delivery-quote\"\n          with:\n            pickup_address: \"tools.pickup_address\"\n            dropoff_address: \"tools.dropoff_address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-direct-delivery\n          description: \"Dispatch an Uber courier for an on-demand delivery.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uber-direct.create-delivery\"\
  \n          with:\n            pickup_name: \"tools.pickup_name\"\n            pickup_address: \"tools.pickup_address\"\n            dropoff_name: \"tools.dropoff_name\"\n            dropoff_address: \"tools.dropoff_address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-direct-delivery\n          description: \"Track the real-time status of an Uber Direct delivery.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-direct.get-delivery\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-direct-delivery\n          description: \"Cancel an active Uber Direct delivery.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"uber-direct.cancel-delivery\"\n          with:\n        \
  \    order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pickup-locations\n          description: \"List business pickup locations configured for Uber Direct.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uber-direct.list-business-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uber/refs/heads/main/capabilities/food-and-delivery.yaml
tags:
- Uber
- Uber Eats
- Uber Direct
- Food Delivery
- Delivery
- Logistics
- Restaurants
tools:
- description: List all Uber Eats stores for the partner account.
  hints:
    openWorld: false
    readOnly: true
  name: list-eats-stores
- description: Get details for a specific Uber Eats restaurant store.
  hints:
    openWorld: false
    readOnly: true
  name: get-eats-store
- description: Get the current menu for an Uber Eats store.
  hints:
    openWorld: false
    readOnly: true
  name: get-store-menu
- description: Get details for an Uber Eats order.
  hints:
    openWorld: false
    readOnly: true
  name: get-eats-order
- description: Accept a pending Uber Eats order.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: accept-eats-order
- description: Deny a pending Uber Eats order with a reason.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deny-eats-order
- description: Get a price quote for an Uber Direct on-demand delivery.
  hints:
    openWorld: true
    readOnly: true
  name: quote-direct-delivery
- description: Dispatch an Uber courier for an on-demand delivery.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-direct-delivery
- description: Track the real-time status of an Uber Direct delivery.
  hints:
    openWorld: false
    readOnly: true
  name: track-direct-delivery
- description: Cancel an active Uber Direct delivery.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-direct-delivery
- description: List business pickup locations configured for Uber Direct.
  hints:
    openWorld: false
    readOnly: true
  name: list-pickup-locations
---
