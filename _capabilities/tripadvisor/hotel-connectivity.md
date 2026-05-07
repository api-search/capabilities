---
categories: []
consumed_apis: []
description: Workflow capability for hotel connectivity partners integrating with Tripadvisor's availability and inventory systems. Combines the Hotel Availability Check API and Hotel Inventory API to enable real-time pricing display on Tripadvisor hotel pages. Designed for OTAs, hotel booking engines, and connectivity providers.
layout: capability
name: Tripadvisor Hotel Connectivity
operations:
- description: Check availability for one or more hotels for given dates
  method: POST
  name: check-availability
  path: /v1/hotels/availability
- description: Get the full hotel inventory connected through this partner
  method: GET
  name: get-inventory
  path: /v1/hotels/inventory
- description: Get partner API configuration and supported features
  method: GET
  name: get-config
  path: /v1/config
personas: []
provider_name: Tripadvisor
provider_slug: tripadvisor
search_terms:
- restaurants
- connectivity
- get partner api configuration and supported features
- attractions
- check availability
- check availability for one or more hotels for given dates
- reviews
- hospitality
- check hotel availability
- inventory
- check real-time hotel availability and pricing for specific check-in/check-out dates and guest count. returns room types, prices, cancellation policies, and booking urls for available hotels.
- get inventory
- booking
- get config
- get hotel inventory
- travel
- availability
- hotel inventory management
- get the full hotel inventory connected through this partner
- hotels
- partner configuration
- real-time hotel availability and pricing
- get partner config
- get partner api configuration including supported api version and features.
- get the complete list of hotels this connectivity partner can provide availability data for. used by tripadvisor to know which hotels to query.
slug: hotel-connectivity
source_filename: hotel-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tripadvisor Hotel Connectivity\n  description: Workflow capability for hotel connectivity partners integrating with Tripadvisor's availability and inventory\n    systems. Combines the Hotel Availability Check API and Hotel Inventory API to enable real-time pricing display on Tripadvisor\n    hotel pages. Designed for OTAs, hotel booking engines, and connectivity providers.\n  tags:\n  - Availability\n  - Booking\n  - Connectivity\n  - Hospitality\n  - Hotels\n  - Inventory\n  - Travel\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIPADVISOR_API_KEY: TRIPADVISOR_API_KEY\n    PARTNER_ENDPOINT: PARTNER_ENDPOINT\ncapability:\n  consumes:\n  - type: http\n    namespace: tripadvisor-hac\n    baseUri: https://{{env.PARTNER_ENDPOINT}}\n    description: Hotel Availability Check - partner endpoint that Tripadvisor calls\n    resources:\n    - name: config\n      path: /config\n      description: Partner\
  \ configuration discovery\n      operations:\n      - name: get-partner-configuration\n        method: GET\n        description: Get partner supported features and API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      description: Hotel inventory registration\n      operations:\n      - name: get-hotel-inventory\n        method: GET\n        description: Get full list of hotels the partner can provide availability for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability\n      path: /availability\n      description: Real-time hotel availability and pricing\n      operations:\n      - name: check-hotel-availability\n        method: POST\n        description: Check real-time availability and pricing for one or more hotels\n        inputParameters:\n   \
  \     - name: api_version\n          in: body\n          type: integer\n          required: true\n          description: API version number\n        - name: check_in\n          in: body\n          type: string\n          required: true\n          description: Check-in date (YYYY-MM-DD)\n        - name: check_out\n          in: body\n          type: string\n          required: true\n          description: Check-out date (YYYY-MM-DD)\n        - name: num_adults\n          in: body\n          type: integer\n          required: true\n          description: Number of adult guests\n        - name: hotel_ids\n          in: body\n          type: array\n          required: true\n          description: List of hotel IDs to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            api_version: '{{tools.api_version}}'\n            check_in: '{{tools.check_in}}'\n\
  \            check_out: '{{tools.check_out}}'\n            num_adults: '{{tools.num_adults}}'\n            hotel_ids: '{{tools.hotel_ids}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: tripadvisor-hotel-connectivity-api\n    description: Unified REST API for Tripadvisor hotel connectivity partner operations.\n    resources:\n    - path: /v1/hotels/availability\n      name: availability\n      description: Real-time hotel availability and pricing\n      operations:\n      - method: POST\n        name: check-availability\n        description: Check availability for one or more hotels for given dates\n        call: tripadvisor-hac.check-hotel-availability\n        with:\n          check_in: rest.body.check_in\n          check_out: rest.body.check_out\n          num_adults: rest.body.num_adults\n          hotel_ids: rest.body.hotel_ids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hotels/inventory\n      name: inventory\n      description:\
  \ Hotel inventory management\n      operations:\n      - method: GET\n        name: get-inventory\n        description: Get the full hotel inventory connected through this partner\n        call: tripadvisor-hac.get-hotel-inventory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/config\n      name: config\n      description: Partner configuration\n      operations:\n      - method: GET\n        name: get-config\n        description: Get partner API configuration and supported features\n        call: tripadvisor-hac.get-partner-configuration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: tripadvisor-hotel-connectivity-mcp\n    transport: http\n    description: MCP server for AI-assisted hotel availability management and Tripadvisor connectivity.\n    tools:\n    - name: check-hotel-availability\n      description: Check real-time hotel availability and pricing for specific\
  \ check-in/check-out dates and guest count. Returns\n        room types, prices, cancellation policies, and booking URLs for available hotels.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tripadvisor-hac.check-hotel-availability\n      with:\n        check_in: tools.check_in\n        check_out: tools.check_out\n        num_adults: tools.num_adults\n        num_children: tools.num_children\n        hotel_ids: tools.hotel_ids\n        currency_code: tools.currency_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hotel-inventory\n      description: Get the complete list of hotels this connectivity partner can provide availability data for. Used by Tripadvisor\n        to know which hotels to query.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tripadvisor-hac.get-hotel-inventory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-partner-config\n      description:\
  \ Get partner API configuration including supported API version and features.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tripadvisor-hac.get-partner-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tripadvisor/refs/heads/main/capabilities/hotel-connectivity.yaml
tags:
- Availability
- Booking
- Connectivity
- Hospitality
- Hotels
- Inventory
- Travel
tools:
- description: Check real-time hotel availability and pricing for specific check-in/check-out dates and guest count. Returns room types, prices, cancellation policies, and booking URLs for available hotels.
  hints:
    openWorld: false
    readOnly: true
  name: check-hotel-availability
- description: Get the complete list of hotels this connectivity partner can provide availability data for. Used by Tripadvisor to know which hotels to query.
  hints:
    openWorld: false
    readOnly: true
  name: get-hotel-inventory
- description: Get partner API configuration including supported API version and features.
  hints:
    openWorld: false
    readOnly: true
  name: get-partner-config
---
