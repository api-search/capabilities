---
categories: []
consumed_apis: []
description: INTTRA (now part of e2open) provides ocean execution APIs for the world's largest multi-carrier e-commerce platform for global shipping. The RESTful API uses HTTPS with JSON for booking, ocean schedules, rates, and visibility/track and trace products. Authentication requires a bearer token obtained from the identity service before making API requests.
layout: capability
name: INTTRA Ocean Execution API (e2open)
operations:
- description: List ocean bookings
  method: GET
  name: listbookings
  path: /bookings
- description: Create an ocean booking
  method: POST
  name: createbooking
  path: /bookings
- description: Get booking details
  method: GET
  name: getbooking
  path: /bookings/{bookingId}
- description: Amend an existing booking
  method: PUT
  name: amendbooking
  path: /bookings/{bookingId}
- description: Cancel a booking
  method: POST
  name: cancelbooking
  path: /bookings/{bookingId}/cancel
- description: Search ocean vessel schedules
  method: GET
  name: searchschedules
  path: /schedules
- description: Track a container by number
  method: GET
  name: trackcontainer
  path: /tracking/{containerNumber}
- description: Track shipment by booking reference
  method: GET
  name: trackbooking
  path: /tracking/booking/{bookingId}
- description: Submit shipping instructions (SI)
  method: POST
  name: submitshippinginstructions
  path: /shipping-instructions
personas: []
provider_name: e2open
provider_slug: e2open
search_terms:
- amend an existing booking
- getbooking
- create an ocean booking
- trackcontainer
- get booking details
- amendbooking
- track shipment by booking reference
- api
- searchschedules
- cancelbooking
- cancel a booking
- submitshippinginstructions
- track a container by number
- createbooking
- search ocean vessel schedules
- submit shipping instructions (si)
- trackbooking
- listbookings
- list ocean bookings
- e2open
slug: e2open-capability
source_filename: e2open-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: INTTRA Ocean Execution API (e2open)\n  description: INTTRA (now part of e2open) provides ocean execution APIs for the world's largest multi-carrier e-commerce\n    platform for global shipping. The RESTful API uses HTTPS with JSON for booking, ocean schedules, rates, and visibility/track\n    and trace products. Authentication requires a bearer token obtained from the identity service before making API requests.\n  tags:\n  - E2open\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: e2open\n    baseUri: https://api.inttra.com/v1\n    description: INTTRA Ocean Execution API (e2open) HTTP API.\n    authentication:\n      type: bearer\n      token: '{{E2OPEN_TOKEN}}'\n    resources:\n    - name: bookings\n      path: /bookings\n      operations:\n      - name: listbookings\n        method: GET\n        description: List ocean bookings\n        inputParameters:\n        - name:\
  \ carrier\n          in: query\n          type: string\n          description: Filter by carrier SCAC code\n        - name: status\n          in: query\n          type: string\n          description: Filter by booking status\n        - name: originPort\n          in: query\n          type: string\n          description: UN/LOCODE for origin port\n        - name: destinationPort\n          in: query\n          type: string\n          description: UN/LOCODE for destination port\n        - name: bookedAfter\n          in: query\n          type: string\n          description: Filter bookings created after this date (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbooking\n        method: POST\n        description: Create an ocean booking\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-bookingid\n      path: /bookings/{bookingId}\n      operations:\n      - name: getbooking\n        method: GET\n        description: Get booking details\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n          description: INTTRA booking identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: amendbooking\n        method: PUT\n        description: Amend an existing booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookings-bookingid-cancel\n      path: /bookings/{bookingId}/cancel\n\
  \      operations:\n      - name: cancelbooking\n        method: POST\n        description: Cancel a booking\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: searchschedules\n        method: GET\n        description: Search ocean vessel schedules\n        inputParameters:\n        - name: originPort\n          in: query\n          type: string\n          required: true\n          description: UN/LOCODE origin port\n        - name: destinationPort\n          in: query\n          type: string\n          required: true\n          description: UN/LOCODE destination port\n        - name: departureAfter\n          in: query\n          type: string\n          description: Search from this departure date (ISO 8601)\n\
  \        - name: departureBefore\n          in: query\n          type: string\n        - name: carrier\n          in: query\n          type: string\n          description: Filter by carrier SCAC code\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracking-containernumber\n      path: /tracking/{containerNumber}\n      operations:\n      - name: trackcontainer\n        method: GET\n        description: Track a container by number\n        inputParameters:\n        - name: containerNumber\n          in: path\n          type: string\n          required: true\n          description: ISO 6346 container number (e.g., MSCU1234567)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracking-booking-bookingid\n      path: /tracking/booking/{bookingId}\n\
  \      operations:\n      - name: trackbooking\n        method: GET\n        description: Track shipment by booking reference\n        inputParameters:\n        - name: bookingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipping-instructions\n      path: /shipping-instructions\n      operations:\n      - name: submitshippinginstructions\n        method: POST\n        description: Submit shipping instructions (SI)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: e2open-rest\n    description: REST adapter for INTTRA Ocean Execution API (e2open).\n    resources:\n    - path: /bookings\n      name: listbookings\n      operations:\n      - method: GET\n        name: listbookings\n        description:\
  \ List ocean bookings\n        call: e2open.listbookings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings\n      name: createbooking\n      operations:\n      - method: POST\n        name: createbooking\n        description: Create an ocean booking\n        call: e2open.createbooking\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{bookingId}\n      name: getbooking\n      operations:\n      - method: GET\n        name: getbooking\n        description: Get booking details\n        call: e2open.getbooking\n        with:\n          bookingId: rest.bookingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{bookingId}\n      name: amendbooking\n      operations:\n      - method: PUT\n        name: amendbooking\n        description: Amend an existing booking\n        call: e2open.amendbooking\n        with:\n          bookingId: rest.bookingId\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/{bookingId}/cancel\n      name: cancelbooking\n      operations:\n      - method: POST\n        name: cancelbooking\n        description: Cancel a booking\n        call: e2open.cancelbooking\n        with:\n          bookingId: rest.bookingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: searchschedules\n      operations:\n      - method: GET\n        name: searchschedules\n        description: Search ocean vessel schedules\n        call: e2open.searchschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/{containerNumber}\n      name: trackcontainer\n      operations:\n      - method: GET\n        name: trackcontainer\n        description: Track a container by number\n        call: e2open.trackcontainer\n        with:\n          containerNumber: rest.containerNumber\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/booking/{bookingId}\n      name: trackbooking\n      operations:\n      - method: GET\n        name: trackbooking\n        description: Track shipment by booking reference\n        call: e2open.trackbooking\n        with:\n          bookingId: rest.bookingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipping-instructions\n      name: submitshippinginstructions\n      operations:\n      - method: POST\n        name: submitshippinginstructions\n        description: Submit shipping instructions (SI)\n        call: e2open.submitshippinginstructions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: e2open-mcp\n    transport: http\n    description: MCP adapter for INTTRA Ocean Execution API (e2open) for AI agent use.\n    tools:\n    - name: listbookings\n      description: List ocean bookings\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: e2open.listbookings\n      with:\n        carrier: tools.carrier\n        status: tools.status\n        originPort: tools.originPort\n        destinationPort: tools.destinationPort\n        bookedAfter: tools.bookedAfter\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: carrier\n        type: string\n        description: Filter by carrier SCAC code\n      - name: status\n        type: string\n        description: Filter by booking status\n      - name: originPort\n        type: string\n        description: UN/LOCODE for origin port\n      - name: destinationPort\n        type: string\n        description: UN/LOCODE for destination port\n      - name: bookedAfter\n        type: string\n        description: Filter bookings created after this date (ISO 8601)\n      - name: limit\n        type: integer\n        description: limit\n      - name:\
  \ offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbooking\n      description: Create an ocean booking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: e2open.createbooking\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbooking\n      description: Get booking details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: e2open.getbooking\n      with:\n        bookingId: tools.bookingId\n      inputParameters:\n      - name: bookingId\n        type: string\n        description: INTTRA booking identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: amendbooking\n      description: Amend an existing booking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: e2open.amendbooking\n      with:\n        bookingId: tools.bookingId\n      inputParameters:\n      - name: bookingId\n        type: string\n        description: bookingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelbooking\n      description: Cancel a booking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: e2open.cancelbooking\n      with:\n        bookingId: tools.bookingId\n      inputParameters:\n      - name: bookingId\n        type: string\n        description: bookingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchschedules\n      description: Search ocean vessel schedules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: e2open.searchschedules\n      with:\n        originPort: tools.originPort\n        destinationPort:\
  \ tools.destinationPort\n        departureAfter: tools.departureAfter\n        departureBefore: tools.departureBefore\n        carrier: tools.carrier\n        limit: tools.limit\n      inputParameters:\n      - name: originPort\n        type: string\n        description: UN/LOCODE origin port\n        required: true\n      - name: destinationPort\n        type: string\n        description: UN/LOCODE destination port\n        required: true\n      - name: departureAfter\n        type: string\n        description: Search from this departure date (ISO 8601)\n      - name: departureBefore\n        type: string\n        description: departureBefore\n      - name: carrier\n        type: string\n        description: Filter by carrier SCAC code\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trackcontainer\n      description: Track a container by number\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: e2open.trackcontainer\n      with:\n        containerNumber: tools.containerNumber\n      inputParameters:\n      - name: containerNumber\n        type: string\n        description: ISO 6346 container number (e.g., MSCU1234567)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trackbooking\n      description: Track shipment by booking reference\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: e2open.trackbooking\n      with:\n        bookingId: tools.bookingId\n      inputParameters:\n      - name: bookingId\n        type: string\n        description: bookingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitshippinginstructions\n      description: Submit shipping instructions (SI)\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: e2open.submitshippinginstructions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    E2OPEN_TOKEN: E2OPEN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/e2open/refs/heads/main/capabilities/e2open-capability.yaml
tags:
- E2open
- API
tools:
- description: List ocean bookings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookings
- description: Create an ocean booking
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbooking
- description: Get booking details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbooking
- description: Amend an existing booking
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: amendbooking
- description: Cancel a booking
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelbooking
- description: Search ocean vessel schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchschedules
- description: Track a container by number
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackcontainer
- description: Track shipment by booking reference
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackbooking
- description: Submit shipping instructions (SI)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitshippinginstructions
---
