---
categories: []
consumed_apis: []
description: 'Workflow capability for AMC Stubs loyalty operations: looking up loyalty accounts by id, email, card, or phone; registering members for campaigns; redeeming points; and unlinking loyalty from AMC accounts. Targeted at customer-care apps, loyalty integrations, and AMC Stubs co-marketing partners.'
layout: capability
name: AMC Stubs Loyalty Management
operations:
- description: ''
  method: GET
  name: get-account
  path: /loyalty/accounts/{loyalty-account-id}
- description: ''
  method: GET
  name: get-account-by-email
  path: /loyalty/accounts/by-email/{email-address}
- description: ''
  method: POST
  name: create-redemption
  path: /loyalty/accounts/{loyalty-account-id}/redemptions
personas: []
provider_name: AMC Entertainment Holdings
provider_slug: amc-entertainment-holdings
search_terms:
- theatres
- amc theatres
- rewards
- get amc loyalty account
- ticketing
- concessions
- redeem amc loyalty points
- get account
- get account by email
- loyalty
- get an amc stubs loyalty account by id, email, card, or phone.
- movies
- showtimes
- fortune 500
- entertainment
- create a points redemption against an amc stubs loyalty account.
- amc stubs
- create redemption
slug: loyalty-management
source_filename: loyalty-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AMC Stubs Loyalty Management\n  description: 'Workflow capability for AMC Stubs loyalty operations: looking up loyalty accounts by id, email, card, or phone;\n    registering members for campaigns; redeeming points; and unlinking loyalty from AMC accounts. Targeted at customer-care\n    apps, loyalty integrations, and AMC Stubs co-marketing partners.'\n  tags:\n  - AMC Theatres\n  - AMC Stubs\n  - Loyalty\n  - Rewards\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMC_VENDOR_KEY: AMC_VENDOR_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amc-theatres-api\n    baseUri: https://api.amctheatres.com\n    auth:\n      type: apiKey\n      in: header\n      name: X-AMC-Vendor-Key\n      value: '{{AMC_VENDOR_KEY}}'\n    resources:\n    - name: theatres\n      path: /v2\n      operations:\n      - id: list-theatres\n        method: GET\n        path: /theatres\n        description: List\
  \ all active AMC theatres.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        - name: city\n          in: query\n          type: string\n        - name: market\n          in: query\n          type: string\n        - name: brand\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        - name: page-number\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-theatre\n        method: GET\n        path: /theatres/{idOrSlug}\n        description: Get a single theatre by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-theatre-seating-layouts\n\
  \        method: GET\n        path: /theatres/{theatre-number}/seating-layouts\n        description: List seating layouts for an auditorium.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movies\n      path: /v2\n      operations:\n      - id: list-movies\n        method: GET\n        path: /movies\n        description: List all movies.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-now-playing\n        method: GET\n        path: /movies/views/now-playing\n        description: List now-playing movies.\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - id: list-movies-coming-soon\n        method: GET\n        path: /movies/views/coming-soon\n        description: List coming-soon movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-advance\n        method: GET\n        path: /movies/views/advance\n        description: List advance ticket movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-movie\n        method: GET\n        path: /movies/{idOrSlug}\n        description: Get a movie by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: showtimes\n      path: /v2\n      operations:\n      - id: list-theatre-showtimes\n        method: GET\n        path: /theatres/{theatre-number}/showtimes\n        description: List future\
  \ showtimes for a theatre.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: movie-id\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-theatre-showtimes-by-date\n        method: GET\n        path: /theatres/{theatre-number}/showtimes/{date}\n        description: List showtimes for a theatre on a date.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: date\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-showtime\n        method: GET\n        path: /showtimes/{id}\n        description: Get a showtime by id.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - id: list-showtimes-by-location\n        method: GET\n        path: /showtimes/views/current-location/{date}/{latitude}/{longitude}\n        description: List showtimes near a latitude/longitude on a date.\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n        - name: latitude\n          in: path\n          type: number\n        - name: longitude\n          in: path\n          type: number\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /v2\n      operations:\n      - id: list-location-suggestions\n        method: GET\n        path: /location-suggestions\n        description: Suggest locations by zip / city / state / theatre name.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: markets\n      path: /v1\n      operations:\n      - id: list-markets\n        method: GET\n        path: /markets\n        description: List all AMC markets.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: states\n      path: /v1\n      operations:\n      - id: list-states\n        method: GET\n        path: /states\n        description: List all states.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /v3\n      operations:\n      - id: create-order\n        method: POST\n        path: /orders\n        description: Create a new order.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-order\n        method: GET\n        path: /orders/{order-id}\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: add-order-product\n        method: POST\n        path: /orders/{order-id}/products\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: add-order-payment\n        method: POST\n        path: /orders/{order-id}/payments\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: delete-order\n        method: DELETE\n        path: /orders/{order-id}\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n      - id: apply-loyalty-rewards\n        method: POST\n        path: /orders/{order-id}/loyalty-rewards-application\n        inputParameters:\n        - name: order-id\n  \
  \        in: path\n          type: string\n    - name: concessions\n      path: /v1\n      operations:\n      - id: list-theatre-concessions\n        method: GET\n        path: /theatres/{theatre-id}/concessions\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-concession-categories\n        method: GET\n        path: /theatres/{theatre-id}/concessions/categories\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty\n      path: /v4\n      operations:\n      - id: get-loyalty-account\n        method: GET\n        path: /loyalty-accounts/{loyalty-account-id}\n        inputParameters:\n        - name: loyalty-account-id\n          in: path\n          type: string\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-loyalty-account-by-email\n        method: GET\n        path: /loyalty-accounts/email-{email-address}\n        inputParameters:\n        - name: email-address\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-loyalty-redemption\n        method: POST\n        path: /loyalty-accounts/{loyalty-account-id}/redemptions\n        inputParameters:\n        - name: loyalty-account-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /v1\n      operations:\n      - id: list-webhook-events\n        method: GET\n        path: /webhook-events\n        description: List available webhook events.\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - id: subscribe-webhook\n        method: POST\n        path: /webhooks\n        description: Subscribe to a webhook event.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: unsubscribe-webhook\n        method: DELETE\n        path: /webhooks/{webhook-token-id}\n        inputParameters:\n        - name: webhook-token-id\n          in: path\n          type: string\n  exposes:\n  - type: rest\n    port: 8094\n    namespace: amc-loyalty-api\n    description: Unified REST API for AMC Stubs loyalty operations.\n    resources:\n    - path: /loyalty/accounts/{loyalty-account-id}\n      name: loyalty-account\n      operations:\n      - method: GET\n        name: get-account\n        call: amc-theatres-api.get-loyalty-account\n        with:\n          loyalty-account-id: rest.loyalty-account-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loyalty/accounts/by-email/{email-address}\n\
  \      name: loyalty-account-by-email\n      operations:\n      - method: GET\n        name: get-account-by-email\n        call: amc-theatres-api.get-loyalty-account-by-email\n        with:\n          email-address: rest.email-address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loyalty/accounts/{loyalty-account-id}/redemptions\n      name: loyalty-redemptions\n      operations:\n      - method: POST\n        name: create-redemption\n        call: amc-theatres-api.create-loyalty-redemption\n        with:\n          loyalty-account-id: rest.loyalty-account-id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: amc-loyalty-mcp\n    transport: http\n    tools:\n    - name: get-amc-loyalty-account\n      description: Get an AMC Stubs loyalty account by id, email, card, or phone.\n      call: amc-theatres-api.get-loyalty-account\n    - name: redeem-amc-loyalty-points\n      description:\
  \ Create a points redemption against an AMC Stubs loyalty account.\n      call: amc-theatres-api.create-loyalty-redemption\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amc-entertainment-holdings/refs/heads/main/capabilities/loyalty-management.yaml
tags:
- AMC Theatres
- AMC Stubs
- Loyalty
- Rewards
tools:
- description: Get an AMC Stubs loyalty account by id, email, card, or phone.
  hints: {}
  name: get-amc-loyalty-account
- description: Create a points redemption against an AMC Stubs loyalty account.
  hints: {}
  name: redeem-amc-loyalty-points
---
