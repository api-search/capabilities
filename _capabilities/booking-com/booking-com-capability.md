---
categories: []
consumed_apis: []
description: The Booking.com Car Rentals API is part of the Demand API and provides endpoints specific to the car rental segment of the connected trip experience. Developers can use it to search for available car rentals, retrieve car details, look up depots and suppliers, and access depot review scores. The API enables affiliate partners to integrate Booking.com's car rental inventory into their own platforms, offering users the ability to find and book vehicles as part of their travel planning workflow.
layout: capability
name: Booking.com Car Rentals API
operations:
- description: Search car rentals
  method: POST
  name: searchcarrentals
  path: /cars/search
- description: Get car rental details
  method: POST
  name: getcardetails
  path: /cars/details
- description: Get car rental depots
  method: POST
  name: getcardepots
  path: /cars/depots
- description: Get depot review scores
  method: POST
  name: getdepotreviewscores
  path: /cars/depots/reviews/scores
- description: Get car rental suppliers
  method: POST
  name: getcarsuppliers
  path: /cars/suppliers
personas: []
provider_name: booking-com
provider_slug: booking-com
search_terms:
- get car rental depots
- search car rentals
- getdepotreviewscores
- getcardetails
- get car rental suppliers
- get depot review scores
- api
- get car rental details
- getcarsuppliers
- searchcarrentals
- booking
- com
- getcardepots
slug: booking-com-capability
source_filename: booking-com-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Booking.com Car Rentals API\n  description: The Booking.com Car Rentals API is part of the Demand API and provides endpoints specific to the car rental\n    segment of the connected trip experience. Developers can use it to search for available car rentals, retrieve car details,\n    look up depots and suppliers, and access depot review scores. The API enables affiliate partners to integrate Booking.com's\n    car rental inventory into their own platforms, offering users the ability to find and book vehicles as part of their travel\n    planning workflow.\n  tags:\n  - Booking\n  - Com\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: booking-com\n    baseUri: https://demandapi.booking.com/3.1\n    description: Booking.com Car Rentals API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BOOKING_COM_TOKEN}}'\n    resources:\n    - name: cars-search\n\
  \      path: /cars/search\n      operations:\n      - name: searchcarrentals\n        method: POST\n        description: Search car rentals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cars-details\n      path: /cars/details\n      operations:\n      - name: getcardetails\n        method: POST\n        description: Get car rental details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cars-depots\n      path: /cars/depots\n      operations:\n      - name: getcardepots\n        method: POST\n        description: Get car rental depots\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cars-depots-reviews-scores\n      path: /cars/depots/reviews/scores\n      operations:\n      - name: getdepotreviewscores\n        method:\
  \ POST\n        description: Get depot review scores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cars-suppliers\n      path: /cars/suppliers\n      operations:\n      - name: getcarsuppliers\n        method: POST\n        description: Get car rental suppliers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: booking-com-rest\n    description: REST adapter for Booking.com Car Rentals API.\n    resources:\n    - path: /cars/search\n      name: searchcarrentals\n      operations:\n      - method: POST\n        name: searchcarrentals\n        description: Search car rentals\n        call: booking-com.searchcarrentals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cars/details\n      name: getcardetails\n      operations:\n\
  \      - method: POST\n        name: getcardetails\n        description: Get car rental details\n        call: booking-com.getcardetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cars/depots\n      name: getcardepots\n      operations:\n      - method: POST\n        name: getcardepots\n        description: Get car rental depots\n        call: booking-com.getcardepots\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cars/depots/reviews/scores\n      name: getdepotreviewscores\n      operations:\n      - method: POST\n        name: getdepotreviewscores\n        description: Get depot review scores\n        call: booking-com.getdepotreviewscores\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cars/suppliers\n      name: getcarsuppliers\n      operations:\n      - method: POST\n        name: getcarsuppliers\n        description: Get car rental suppliers\n        call:\
  \ booking-com.getcarsuppliers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: booking-com-mcp\n    transport: http\n    description: MCP adapter for Booking.com Car Rentals API for AI agent use.\n    tools:\n    - name: searchcarrentals\n      description: Search car rentals\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: booking-com.searchcarrentals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcardetails\n      description: Get car rental details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: booking-com.getcardetails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcardepots\n      description: Get car rental depots\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: booking-com.getcardepots\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdepotreviewscores\n      description: Get depot review scores\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: booking-com.getdepotreviewscores\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarsuppliers\n      description: Get car rental suppliers\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: booking-com.getcarsuppliers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BOOKING_COM_TOKEN: BOOKING_COM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/booking-com/refs/heads/main/capabilities/booking-com-capability.yaml
tags:
- Booking
- Com
- API
tools:
- description: Search car rentals
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchcarrentals
- description: Get car rental details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcardetails
- description: Get car rental depots
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcardepots
- description: Get depot review scores
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getdepotreviewscores
- description: Get car rental suppliers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcarsuppliers
---
