---
categories: []
consumed_apis: []
description: OCTO (Open Connectivity for Tours, Activities, and Attractions) is an open standard API specification for the in-destination experiences sector of the travel industry. The standard defines agreed-upon schemas, endpoints, and capabilities commonly needed when connecting platforms, resellers, OTAs, and other technologies in tours, activities, and attractions. OCTO is open source. Available to anyone who wants to use it. You do not need to be a member to use this specification in your business.
layout: capability
name: Open Connectivity for Tours, Activities, and Attractions OCTO API Specification
operations:
- description: Open Connectivity for Tours, Activities, and Attractions Get Supplier
  method: GET
  name: get-supplier
  path: /supplier
- description: Open Connectivity for Tours, Activities, and Attractions Get Products
  method: GET
  name: get-products
  path: /products
- description: Open Connectivity for Tours, Activities, and Attractions Get Product
  method: GET
  name: get-products-id
  path: /products/{id}
- description: Open Connectivity for Tours, Activities, and Attractions Availability Calendar
  method: POST
  name: post-availability-calendar
  path: /availability/calendar
- description: Open Connectivity for Tours, Activities, and Attractions Availability Check
  method: POST
  name: post-availability
  path: /availability
- description: Open Connectivity for Tours, Activities, and Attractions Booking Reservation
  method: POST
  name: post-bookings
  path: /bookings
- description: Open Connectivity for Tours, Activities, and Attractions Get Bookings
  method: GET
  name: get-bookings
  path: /bookings
- description: Open Connectivity for Tours, Activities, and Attractions Booking Confirmation
  method: POST
  name: post-bookings-uuid-confirm
  path: /bookings/{uuid}/confirm
- description: Open Connectivity for Tours, Activities, and Attractions Booking Cancellation
  method: POST
  name: delete-bookings-uuid
  path: /bookings/{uuid}/cancel
- description: Open Connectivity for Tours, Activities, and Attractions Get Booking
  method: GET
  name: get-bookings-uuid
  path: /bookings/{uuid}
- description: Open Connectivity for Tours, Activities, and Attractions Booking Update
  method: PATCH
  name: patch-bookings-uuid
  path: /bookings/{uuid}
- description: Open Connectivity for Tours, Activities, and Attractions Extend Reservation
  method: POST
  name: post-bookings-uuid-extend
  path: /bookings/{uuid}/extend
personas: []
provider_name: Open Connectivity for Tours, Activities, and Attractions
provider_slug: octo
search_terms:
- open connectivity for tours, activities, and attractions availability check
- open connectivity for tours, activities, and attractions get bookings
- open connectivity for tours, activities, and attractions booking confirmation
- open connectivity for tours, activities, and attractions get product
- get products id
- open standard
- delete bookings uuid
- patch bookings uuid
- attractions
- open connectivity for tours, activities, and attractions availability calendar
- post availability
- api
- open connectivity for tours, activities, and attractions booking update
- post bookings uuid confirm
- open connectivity for tours, activities, and attractions booking cancellation
- post availability calendar
- get supplier
- get bookings uuid
- open connectivity for tours, activities, and attractions extend reservation
- open connectivity for tours, activities, and attractions get supplier
- open connectivity for tours, activities, and attractions booking reservation
- activities
- post bookings uuid extend
- tours
- travel
- open connectivity for tours, activities, and attractions get booking
- octo
- get bookings
- open connectivity for tours, activities, and attractions get products
- post bookings
- get products
slug: octo-capability
source_filename: octo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Open Connectivity for Tours, Activities, and Attractions OCTO API Specification\n  description: OCTO (Open Connectivity for Tours, Activities, and Attractions) is an open standard API specification for the\n    in-destination experiences sector of the travel industry. The standard defines agreed-upon schemas, endpoints, and capabilities\n    commonly needed when connecting platforms, resellers, OTAs, and other technologies in tours, activities, and attractions.\n    OCTO is open source. Available to anyone who wants to use it. You do not need to be a member to use this specification\n    in your business.\n  tags:\n  - Octo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: octo\n    baseUri: https://api.example.com/octo\n    description: Open Connectivity for Tours, Activities, and Attractions OCTO API Specification HTTP API.\n    authentication:\n      type: bearer\n\
  \      token: '{{OCTO_TOKEN}}'\n    resources:\n    - name: supplier\n      path: /supplier\n      operations:\n      - name: get-supplier\n        method: GET\n        description: Open Connectivity for Tours, Activities, and Attractions Get Supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      operations:\n      - name: get-products\n        method: GET\n        description: Open Connectivity for Tours, Activities, and Attractions Get Products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-id\n      path: /products/{id}\n      operations:\n      - name: get-products-id\n        method: GET\n        description: Open Connectivity for Tours, Activities, and Attractions Get Product\n        inputParameters:\n        - name: id\n          in: path\n      \
  \    type: string\n          required: true\n          description: The product id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability-calendar\n      path: /availability/calendar\n      operations:\n      - name: post-availability-calendar\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Availability Calendar\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability\n      path: /availability\n      operations:\n      - name: post-availability\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Availability Check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings\n      path: /bookings\n      operations:\n\
  \      - name: post-bookings\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Reservation\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          description: Required field on all POST requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bookings\n        method: GET\n        description: Open Connectivity for Tours, Activities, and Attractions Get Bookings\n        inputParameters:\n        - name: resellerReference\n          in: query\n          type: string\n          description: The reseller reference on the booking\n        - name: supplierReference\n          in: query\n          type: string\n          description: The reference provided by the supplier\n        - name: localDate\n          in: query\n          type: string\n          description: All bookings\
  \ made for a specific date\n        - name: localDateStart\n          in: query\n          type: string\n          description: First date of a date range search\n        - name: localDateEnd\n          in: query\n          type: string\n          description: Last date of a date range search\n        - name: productId\n          in: query\n          type: string\n          description: The product id to filter by\n        - name: optionId\n          in: query\n          type: string\n          description: The option id to filter by\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-uuid-confirm\n      path: /bookings/{uuid}/confirm\n      operations:\n      - name: post-bookings-uuid-confirm\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Confirmation\n        inputParameters:\n        - name: Content-Type\n          in: header\n\
  \          type: string\n          description: Required field on all POST requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-uuid-cancel\n      path: /bookings/{uuid}/cancel\n      operations:\n      - name: delete-bookings-uuid\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Cancellation\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          description: Required field on all DELETE requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-uuid\n      path: /bookings/{uuid}\n      operations:\n      - name: get-bookings-uuid\n        method: GET\n        description: Open Connectivity for Tours, Activities, and Attractions Get Booking\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-bookings-uuid\n        method: PATCH\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Update\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          description: Required field on all PATCH requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-uuid-extend\n      path: /bookings/{uuid}/extend\n      operations:\n      - name: post-bookings-uuid-extend\n        method: POST\n        description: Open Connectivity for Tours, Activities, and Attractions Extend Reservation\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          description: Required field on all POST requests\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: octo-rest\n    description: REST adapter for Open Connectivity for Tours, Activities, and Attractions OCTO API Specification.\n    resources:\n    - path: /supplier\n      name: get-supplier\n      operations:\n      - method: GET\n        name: get-supplier\n        description: Open Connectivity for Tours, Activities, and Attractions Get Supplier\n        call: octo.get-supplier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: get-products\n      operations:\n      - method: GET\n        name: get-products\n        description: Open Connectivity for Tours, Activities, and Attractions Get Products\n        call: octo.get-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: get-products-id\n      operations:\n      - method: GET\n\
  \        name: get-products-id\n        description: Open Connectivity for Tours, Activities, and Attractions Get Product\n        call: octo.get-products-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /availability/calendar\n      name: post-availability-calendar\n      operations:\n      - method: POST\n        name: post-availability-calendar\n        description: Open Connectivity for Tours, Activities, and Attractions Availability Calendar\n        call: octo.post-availability-calendar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /availability\n      name: post-availability\n      operations:\n      - method: POST\n        name: post-availability\n        description: Open Connectivity for Tours, Activities, and Attractions Availability Check\n        call: octo.post-availability\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /bookings\n      name: post-bookings\n      operations:\n      - method: POST\n        name: post-bookings\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Reservation\n        call: octo.post-bookings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings\n      name: get-bookings\n      operations:\n      - method: GET\n        name: get-bookings\n        description: Open Connectivity for Tours, Activities, and Attractions Get Bookings\n        call: octo.get-bookings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{uuid}/confirm\n      name: post-bookings-uuid-confirm\n      operations:\n      - method: POST\n        name: post-bookings-uuid-confirm\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Confirmation\n        call: octo.post-bookings-uuid-confirm\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /bookings/{uuid}/cancel\n      name: delete-bookings-uuid\n      operations:\n      - method: POST\n        name: delete-bookings-uuid\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Cancellation\n        call: octo.delete-bookings-uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{uuid}\n      name: get-bookings-uuid\n      operations:\n      - method: GET\n        name: get-bookings-uuid\n        description: Open Connectivity for Tours, Activities, and Attractions Get Booking\n        call: octo.get-bookings-uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{uuid}\n      name: patch-bookings-uuid\n      operations:\n      - method: PATCH\n        name: patch-bookings-uuid\n        description: Open Connectivity for Tours, Activities, and Attractions Booking Update\n        call: octo.patch-bookings-uuid\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{uuid}/extend\n      name: post-bookings-uuid-extend\n      operations:\n      - method: POST\n        name: post-bookings-uuid-extend\n        description: Open Connectivity for Tours, Activities, and Attractions Extend Reservation\n        call: octo.post-bookings-uuid-extend\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: octo-mcp\n    transport: http\n    description: MCP adapter for Open Connectivity for Tours, Activities, and Attractions OCTO API Specification for AI agent\n      use.\n    tools:\n    - name: get-supplier\n      description: Open Connectivity for Tours, Activities, and Attractions Get Supplier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octo.get-supplier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-products\n\
  \      description: Open Connectivity for Tours, Activities, and Attractions Get Products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octo.get-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-products-id\n      description: Open Connectivity for Tours, Activities, and Attractions Get Product\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octo.get-products-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: The product id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-availability-calendar\n      description: Open Connectivity for Tours, Activities, and Attractions Availability Calendar\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.post-availability-calendar\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-availability\n      description: Open Connectivity for Tours, Activities, and Attractions Availability Check\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.post-availability\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-bookings\n      description: Open Connectivity for Tours, Activities, and Attractions Booking Reservation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.post-bookings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bookings\n      description: Open Connectivity for Tours, Activities, and Attractions Get Bookings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octo.get-bookings\n      with:\n        resellerReference: tools.resellerReference\n\
  \        supplierReference: tools.supplierReference\n        localDate: tools.localDate\n        localDateStart: tools.localDateStart\n        localDateEnd: tools.localDateEnd\n        productId: tools.productId\n        optionId: tools.optionId\n      inputParameters:\n      - name: resellerReference\n        type: string\n        description: The reseller reference on the booking\n      - name: supplierReference\n        type: string\n        description: The reference provided by the supplier\n      - name: localDate\n        type: string\n        description: All bookings made for a specific date\n      - name: localDateStart\n        type: string\n        description: First date of a date range search\n      - name: localDateEnd\n        type: string\n        description: Last date of a date range search\n      - name: productId\n        type: string\n        description: The product id to filter by\n      - name: optionId\n        type: string\n        description: The option id\
  \ to filter by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-bookings-uuid-confirm\n      description: Open Connectivity for Tours, Activities, and Attractions Booking Confirmation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.post-bookings-uuid-confirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-bookings-uuid\n      description: Open Connectivity for Tours, Activities, and Attractions Booking Cancellation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.delete-bookings-uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bookings-uuid\n      description: Open Connectivity for Tours, Activities, and Attractions Get Booking\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octo.get-bookings-uuid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-bookings-uuid\n      description: Open Connectivity for Tours, Activities, and Attractions Booking Update\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.patch-bookings-uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-bookings-uuid-extend\n      description: Open Connectivity for Tours, Activities, and Attractions Extend Reservation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octo.post-bookings-uuid-extend\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OCTO_TOKEN: OCTO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/octo/refs/heads/main/capabilities/octo-capability.yaml
tags:
- Octo
- API
tools:
- description: Open Connectivity for Tours, Activities, and Attractions Get Supplier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-supplier
- description: Open Connectivity for Tours, Activities, and Attractions Get Products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-products
- description: Open Connectivity for Tours, Activities, and Attractions Get Product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-products-id
- description: Open Connectivity for Tours, Activities, and Attractions Availability Calendar
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-availability-calendar
- description: Open Connectivity for Tours, Activities, and Attractions Availability Check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-availability
- description: Open Connectivity for Tours, Activities, and Attractions Booking Reservation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-bookings
- description: Open Connectivity for Tours, Activities, and Attractions Get Bookings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-bookings
- description: Open Connectivity for Tours, Activities, and Attractions Booking Confirmation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-bookings-uuid-confirm
- description: Open Connectivity for Tours, Activities, and Attractions Booking Cancellation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: delete-bookings-uuid
- description: Open Connectivity for Tours, Activities, and Attractions Get Booking
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-bookings-uuid
- description: Open Connectivity for Tours, Activities, and Attractions Booking Update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-bookings-uuid
- description: Open Connectivity for Tours, Activities, and Attractions Extend Reservation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-bookings-uuid-extend
---
