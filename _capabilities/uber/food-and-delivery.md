---
categories: []
consumed_apis: []
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
- accept a pending uber eats order.
- logistics
- get delivery quote
- uber direct delivery dispatch.
- list eats stores
- get details for a specific uber eats order.
- ride-sharing
- restaurants
- track the real-time status of an uber direct delivery.
- delivery
- get the current menu for a store.
- taxis
- get details for a specific uber eats restaurant store.
- get a price quote for an uber direct on-demand delivery.
- rides
- food delivery
- uber direct delivery price quotes.
- get eats store
- track direct delivery
- get store
- uber direct
- get the current menu for an uber eats store.
- get eats order
- cancel direct delivery
- list all business pickup locations.
- create direct delivery
- get the current status of a delivery order.
- uber eats store listings.
- uber eats
- deny a pending uber eats order with a reason.
- individual uber eats store details.
- get delivery
- accept eats order
- transportation
- list stores
- uber eats store menu management.
- cancel an active uber direct delivery.
- cancel delivery
- list all uber eats stores for the partner account.
- quote direct delivery
- list business pickup locations configured for uber direct.
- business pickup location management for uber direct.
- list all stores for the authenticated uber eats partner.
- get details for a specific uber eats store.
- dispatch an uber courier for an on-demand delivery.
- create delivery
- cancel an active delivery order.
- individual uber direct delivery tracking and management.
- list pickup locations
- get details for an uber eats order.
- deny eats order
- get a price quote for an on-demand delivery.
- uber eats order management.
- dispatch an uber courier for on-demand delivery.
- uber
- get store menu
- get order
slug: food-and-delivery
source_filename: food-and-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Uber Food and Delivery\n  description: Workflow capability combining Uber Eats (restaurant ordering and store management) and Uber Direct (on-demand\n    courier delivery) APIs. Supports restaurant operators, e-commerce merchants, and delivery platform integrators needing\n    unified food ordering and delivery dispatch.\n  tags:\n  - Uber\n  - Uber Eats\n  - Uber Direct\n  - Food Delivery\n  - Delivery\n  - Logistics\n  - Restaurants\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UBER_EATS_ACCESS_TOKEN: UBER_EATS_ACCESS_TOKEN\n    UBER_DIRECT_ACCESS_TOKEN: UBER_DIRECT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uber-eats\n    baseUri: https://api.uber.com/v1\n    description: Uber Eats Marketplace API for store, menu, and order management.\n    authentication:\n      type: bearer\n      token: '{{UBER_EATS_ACCESS_TOKEN}}'\n    resources:\n    - name: stores\n     \
  \ path: /eats/stores\n      description: Uber Eats store management.\n      operations:\n      - name: list-stores\n        method: GET\n        description: Returns a list of stores for the authenticated partner.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of stores to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: store\n      path: /eats/stores/{store_id}\n      description: Individual store operations.\n      operations:\n      - name: get-store\n        method: GET\n        description: Returns details for a specific store.\n        inputParameters:\n        - name: store_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique identifier for the store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: store-menu\n      path: /eats/stores/{store_id}/menus\n      description: Store menu management.\n      operations:\n      - name: get-store-menu\n        method: GET\n        description: Returns the current menu for a specific store.\n        inputParameters:\n        - name: store_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-store-menu\n        method: PUT\n        description: Replace the full menu for a specific store.\n        inputParameters:\n        - name: store_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Unique identifier for the store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            categories: '{{tools.categories}}'\n    - name: order\n      path: /eats/orders/{order_id}\n      description: Individual order operations.\n      operations:\n      - name: get-order\n        method: GET\n        description: Returns order details for a specific order ID.\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accept-order\n      path: /eats/orders/{order_id}/accept_pos_order\n      description: Order acceptance.\n      operations:\n      - name: accept-order\n        method: POST\n  \
  \      description: Accept a pending order within the required acceptance window.\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deny-order\n      path: /eats/orders/{order_id}/deny_pos_order\n      description: Order denial.\n      operations:\n      - name: deny-order\n        method: POST\n        description: Deny a pending order.\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reason: '{{tools.reason}}'\n\
  \  - type: http\n    namespace: uber-direct\n    baseUri: https://api.uber.com/v1\n    description: Uber Direct delivery API for on-demand courier dispatching.\n    authentication:\n      type: bearer\n      token: '{{UBER_DIRECT_ACCESS_TOKEN}}'\n    resources:\n    - name: delivery-quote\n      path: /eats/deliveries/quote\n      description: Delivery price quotes.\n      operations:\n      - name: get-delivery-quote\n        method: POST\n        description: Get a price quote for a delivery before creating the order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pickup_address: '{{tools.pickup_address}}'\n            dropoff_address: '{{tools.dropoff_address}}'\n    - name: deliveries\n      path: /eats/deliveries\n      description: Delivery order creation.\n      operations:\n      - name: create-delivery\n        method: POST\n      \
  \  description: Create a new delivery request using Uber's courier network.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pickup_name: '{{tools.pickup_name}}'\n            pickup_address: '{{tools.pickup_address}}'\n            dropoff_name: '{{tools.dropoff_name}}'\n            dropoff_address: '{{tools.dropoff_address}}'\n    - name: delivery\n      path: /eats/deliveries/{order_id}\n      description: Individual delivery order management.\n      operations:\n      - name: get-delivery\n        method: GET\n        description: Returns the current status of a delivery order.\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the delivery order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: cancel-delivery\n        method: DELETE\n        description: Cancel an active delivery order.\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the delivery order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-locations\n      path: /business-locations\n      description: Business pickup location management.\n      operations:\n      - name: list-business-locations\n        method: GET\n        description: Returns all business locations for the authenticated merchant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-business-location\n        method: POST\n        description: Create a new business pickup location.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            address: '{{tools.address}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: uber-food-delivery-api\n    description: Unified REST API for Uber Eats store management and Uber Direct delivery operations.\n    resources:\n    - path: /v1/stores\n      name: stores\n      description: Uber Eats store listings.\n      operations:\n      - method: GET\n        name: list-stores\n        description: List all stores for the authenticated Uber Eats partner.\n        call: uber-eats.list-stores\n        with:\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores/{store_id}\n      name: store\n      description: Individual Uber Eats store details.\n     \
  \ operations:\n      - method: GET\n        name: get-store\n        description: Get details for a specific Uber Eats store.\n        call: uber-eats.get-store\n        with:\n          store_id: rest.store_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores/{store_id}/menu\n      name: store-menu\n      description: Uber Eats store menu management.\n      operations:\n      - method: GET\n        name: get-store-menu\n        description: Get the current menu for a store.\n        call: uber-eats.get-store-menu\n        with:\n          store_id: rest.store_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{order_id}\n      name: order\n      description: Uber Eats order management.\n      operations:\n      - method: GET\n        name: get-order\n        description: Get details for a specific Uber Eats order.\n        call: uber-eats.get-order\n        with:\n          order_id: rest.order_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deliveries/quotes\n      name: delivery-quotes\n      description: Uber Direct delivery price quotes.\n      operations:\n      - method: POST\n        name: get-delivery-quote\n        description: Get a price quote for an on-demand delivery.\n        call: uber-direct.get-delivery-quote\n        with:\n          pickup_address: rest.pickup_address\n          dropoff_address: rest.dropoff_address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deliveries\n      name: deliveries\n      description: Uber Direct delivery dispatch.\n      operations:\n      - method: POST\n        name: create-delivery\n        description: Dispatch an Uber courier for on-demand delivery.\n        call: uber-direct.create-delivery\n        with:\n          pickup_name: rest.pickup_name\n          pickup_address: rest.pickup_address\n          dropoff_name: rest.dropoff_name\n\
  \          dropoff_address: rest.dropoff_address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deliveries/{order_id}\n      name: delivery\n      description: Individual Uber Direct delivery tracking and management.\n      operations:\n      - method: GET\n        name: get-delivery\n        description: Get the current status of a delivery order.\n        call: uber-direct.get-delivery\n        with:\n          order_id: rest.order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-delivery\n        description: Cancel an active delivery order.\n        call: uber-direct.cancel-delivery\n        with:\n          order_id: rest.order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pickup-locations\n      name: pickup-locations\n      description: Business pickup location management for Uber Direct.\n      operations:\n      -\
  \ method: GET\n        name: list-pickup-locations\n        description: List all business pickup locations.\n        call: uber-direct.list-business-locations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: uber-food-delivery-mcp\n    transport: http\n    description: MCP server for AI-assisted food ordering and delivery dispatch.\n    tools:\n    - name: list-eats-stores\n      description: List all Uber Eats stores for the partner account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-eats.list-stores\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-eats-store\n      description: Get details for a specific Uber Eats restaurant store.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-eats.get-store\n      with:\n        store_id: tools.store_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-store-menu\n      description: Get the current menu for an Uber Eats store.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-eats.get-store-menu\n      with:\n        store_id: tools.store_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-eats-order\n      description: Get details for an Uber Eats order.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-eats.get-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accept-eats-order\n      description: Accept a pending Uber Eats order.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uber-eats.accept-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deny-eats-order\n\
  \      description: Deny a pending Uber Eats order with a reason.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uber-eats.deny-order\n      with:\n        order_id: tools.order_id\n        reason: tools.reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: quote-direct-delivery\n      description: Get a price quote for an Uber Direct on-demand delivery.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uber-direct.get-delivery-quote\n      with:\n        pickup_address: tools.pickup_address\n        dropoff_address: tools.dropoff_address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-direct-delivery\n      description: Dispatch an Uber courier for an on-demand delivery.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uber-direct.create-delivery\n      with:\n        pickup_name:\
  \ tools.pickup_name\n        pickup_address: tools.pickup_address\n        dropoff_name: tools.dropoff_name\n        dropoff_address: tools.dropoff_address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-direct-delivery\n      description: Track the real-time status of an Uber Direct delivery.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-direct.get-delivery\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-direct-delivery\n      description: Cancel an active Uber Direct delivery.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: uber-direct.cancel-delivery\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pickup-locations\n      description: List business pickup locations configured for Uber\
  \ Direct.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-direct.list-business-locations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
