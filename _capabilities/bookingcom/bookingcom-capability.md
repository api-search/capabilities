---
categories: []
consumed_apis: []
description: Booking.com provides APIs for hotel search, availability, rates, reservations, and property management. The Connectivity APIs enable partners to distribute and manage accommodation inventory.
layout: capability
name: Booking.com API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: Booking.com
provider_slug: bookingcom
search_terms:
- affiliates
- reservations
- getstatus
- connectivity
- travel
- get api status
- api
- hospitality
- accommodations
- bookingcom
- hotels
slug: bookingcom-capability
source_filename: bookingcom-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Booking.com API\n  description: Booking.com provides APIs for hotel search, availability, rates, reservations, and property management. The\n    Connectivity APIs enable partners to distribute and manage accommodation inventory.\n  tags:\n  - Bookingcom\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bookingcom\n    baseUri: https://api.booking.com\n    description: Booking.com API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BOOKINGCOM_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bookingcom-rest\n    description: REST adapter for Booking.com\
  \ API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: bookingcom.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bookingcom-mcp\n    transport: http\n    description: MCP adapter for Booking.com API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bookingcom.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BOOKINGCOM_TOKEN: BOOKINGCOM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bookingcom/refs/heads/main/capabilities/bookingcom-capability.yaml
tags:
- Bookingcom
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
