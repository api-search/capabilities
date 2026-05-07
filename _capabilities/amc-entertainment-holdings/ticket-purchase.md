---
categories: []
consumed_apis: []
description: Workflow capability for end-to-end AMC ticket and concessions purchasing. Coordinates show selection, order creation, ticket and concession line items, payment, optional AMC Stubs loyalty rewards application, and order fulfillment via the AMC Theatres API. Suitable for partner ticketing apps, concierge services, and integrated guest experiences.
layout: capability
name: AMC Ticket Purchase
operations:
- description: Create a new AMC order.
  method: POST
  name: create-order
  path: /orders
- description: ''
  method: GET
  name: get-order
  path: /orders/{order-id}
- description: ''
  method: DELETE
  name: cancel-order
  path: /orders/{order-id}
- description: ''
  method: POST
  name: add-product
  path: /orders/{order-id}/products
- description: ''
  method: POST
  name: add-payment
  path: /orders/{order-id}/payments
- description: Apply AMC Stubs rewards to an order.
  method: POST
  name: apply-loyalty-rewards
  path: /orders/{order-id}/loyalty
personas: []
provider_name: AMC Entertainment Holdings
provider_slug: amc-entertainment-holdings
search_terms:
- movies
- tickets
- create order
- loyalty
- create amc order
- add product
- theatres
- orders
- concessions
- apply loyalty rewards
- add amc order product
- apply amc loyalty rewards
- showtimes
- apply amc stubs rewards to an order.
- add a ticket or concession sku to an amc order.
- cancel order
- add payment to an amc order.
- add payment
- entertainment
- create a new amc order.
- payments
- amc theatres
- create a new amc order against a theatre.
- apply amc stubs loyalty rewards to an order.
- fortune 500
- ticketing
- add amc order payment
- get order
slug: ticket-purchase
source_filename: ticket-purchase.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AMC Ticket Purchase\n  description: Workflow capability for end-to-end AMC ticket and concessions purchasing. Coordinates show selection, order\n    creation, ticket and concession line items, payment, optional AMC Stubs loyalty rewards application, and order fulfillment\n    via the AMC Theatres API. Suitable for partner ticketing apps, concierge services, and integrated guest experiences.\n  tags:\n  - AMC Theatres\n  - Tickets\n  - Orders\n  - Concessions\n  - Loyalty\n  - Payments\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMC_VENDOR_KEY: AMC_VENDOR_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amc-theatres-api\n    baseUri: https://api.amctheatres.com\n    auth:\n      type: apiKey\n      in: header\n      name: X-AMC-Vendor-Key\n      value: '{{AMC_VENDOR_KEY}}'\n    resources:\n    - name: theatres\n      path: /v2\n      operations:\n      - id: list-theatres\n   \
  \     method: GET\n        path: /theatres\n        description: List all active AMC theatres.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        - name: city\n          in: query\n          type: string\n        - name: market\n          in: query\n          type: string\n        - name: brand\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        - name: page-number\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-theatre\n        method: GET\n        path: /theatres/{idOrSlug}\n        description: Get a single theatre by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - id: list-theatre-seating-layouts\n        method: GET\n        path: /theatres/{theatre-number}/seating-layouts\n        description: List seating layouts for an auditorium.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movies\n      path: /v2\n      operations:\n      - id: list-movies\n        method: GET\n        path: /movies\n        description: List all movies.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-now-playing\n        method: GET\n        path: /movies/views/now-playing\n        description: List now-playing movies.\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-coming-soon\n        method: GET\n        path: /movies/views/coming-soon\n        description: List coming-soon movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-advance\n        method: GET\n        path: /movies/views/advance\n        description: List advance ticket movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-movie\n        method: GET\n        path: /movies/{idOrSlug}\n        description: Get a movie by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: showtimes\n      path: /v2\n      operations:\n      - id: list-theatre-showtimes\n        method:\
  \ GET\n        path: /theatres/{theatre-number}/showtimes\n        description: List future showtimes for a theatre.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: movie-id\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-theatre-showtimes-by-date\n        method: GET\n        path: /theatres/{theatre-number}/showtimes/{date}\n        description: List showtimes for a theatre on a date.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: date\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-showtime\n        method: GET\n        path: /showtimes/{id}\n        description: Get a showtime by id.\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-showtimes-by-location\n        method: GET\n        path: /showtimes/views/current-location/{date}/{latitude}/{longitude}\n        description: List showtimes near a latitude/longitude on a date.\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n        - name: latitude\n          in: path\n          type: number\n        - name: longitude\n          in: path\n          type: number\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /v2\n      operations:\n      - id: list-location-suggestions\n        method: GET\n        path: /location-suggestions\n        description: Suggest locations by zip / city / state / theatre name.\n        inputParameters:\n        - name: query\n          in: query\n     \
  \     type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /v1\n      operations:\n      - id: list-markets\n        method: GET\n        path: /markets\n        description: List all AMC markets.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: states\n      path: /v1\n      operations:\n      - id: list-states\n        method: GET\n        path: /states\n        description: List all states.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /v3\n      operations:\n      - id: create-order\n        method: POST\n        path: /orders\n        description: Create a new order.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-order\n        method: GET\n        path: /orders/{order-id}\n        inputParameters:\n\
  \        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: add-order-product\n        method: POST\n        path: /orders/{order-id}/products\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: add-order-payment\n        method: POST\n        path: /orders/{order-id}/payments\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: delete-order\n        method: DELETE\n        path: /orders/{order-id}\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n      - id: apply-loyalty-rewards\n        method: POST\n        path: /orders/{order-id}/loyalty-rewards-application\n\
  \        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n    - name: concessions\n      path: /v1\n      operations:\n      - id: list-theatre-concessions\n        method: GET\n        path: /theatres/{theatre-id}/concessions\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-concession-categories\n        method: GET\n        path: /theatres/{theatre-id}/concessions/categories\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty\n      path: /v4\n      operations:\n      - id: get-loyalty-account\n        method: GET\n        path: /loyalty-accounts/{loyalty-account-id}\n        inputParameters:\n        - name: loyalty-account-id\n\
  \          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-loyalty-account-by-email\n        method: GET\n        path: /loyalty-accounts/email-{email-address}\n        inputParameters:\n        - name: email-address\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-loyalty-redemption\n        method: POST\n        path: /loyalty-accounts/{loyalty-account-id}/redemptions\n        inputParameters:\n        - name: loyalty-account-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /v1\n      operations:\n      - id: list-webhook-events\n        method: GET\n        path: /webhook-events\n        description: List available webhook events.\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: subscribe-webhook\n        method: POST\n        path: /webhooks\n        description: Subscribe to a webhook event.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: unsubscribe-webhook\n        method: DELETE\n        path: /webhooks/{webhook-token-id}\n        inputParameters:\n        - name: webhook-token-id\n          in: path\n          type: string\n  exposes:\n  - type: rest\n    port: 8093\n    namespace: amc-ticketing-api\n    description: Unified REST API for AMC ticket and concession ordering.\n    resources:\n    - path: /orders\n      name: orders\n      operations:\n      - method: POST\n        name: create-order\n        description: Create a new AMC order.\n        call: amc-theatres-api.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{order-id}\n      name: order\n   \
  \   operations:\n      - method: GET\n        name: get-order\n        call: amc-theatres-api.get-order\n        with:\n          order-id: rest.order-id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-order\n        call: amc-theatres-api.delete-order\n        with:\n          order-id: rest.order-id\n    - path: /orders/{order-id}/products\n      name: order-products\n      operations:\n      - method: POST\n        name: add-product\n        call: amc-theatres-api.add-order-product\n        with:\n          order-id: rest.order-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{order-id}/payments\n      name: order-payments\n      operations:\n      - method: POST\n        name: add-payment\n        call: amc-theatres-api.add-order-payment\n        with:\n          order-id: rest.order-id\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /orders/{order-id}/loyalty\n      name: order-loyalty\n      operations:\n      - method: POST\n        name: apply-loyalty-rewards\n        description: Apply AMC Stubs rewards to an order.\n        call: amc-theatres-api.apply-loyalty-rewards\n        with:\n          order-id: rest.order-id\n  - type: mcp\n    port: 9093\n    namespace: amc-ticketing-mcp\n    transport: http\n    tools:\n    - name: create-amc-order\n      description: Create a new AMC order against a theatre.\n      call: amc-theatres-api.create-order\n    - name: add-amc-order-product\n      description: Add a ticket or concession SKU to an AMC order.\n      call: amc-theatres-api.add-order-product\n    - name: add-amc-order-payment\n      description: Add payment to an AMC order.\n      call: amc-theatres-api.add-order-payment\n    - name: apply-amc-loyalty-rewards\n      description: Apply AMC Stubs loyalty rewards to an order.\n      call: amc-theatres-api.apply-loyalty-rewards\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amc-entertainment-holdings/refs/heads/main/capabilities/ticket-purchase.yaml
tags:
- AMC Theatres
- Tickets
- Orders
- Concessions
- Loyalty
- Payments
tools:
- description: Create a new AMC order against a theatre.
  hints: {}
  name: create-amc-order
- description: Add a ticket or concession SKU to an AMC order.
  hints: {}
  name: add-amc-order-product
- description: Add payment to an AMC order.
  hints: {}
  name: add-amc-order-payment
- description: Apply AMC Stubs loyalty rewards to an order.
  hints: {}
  name: apply-amc-loyalty-rewards
---
