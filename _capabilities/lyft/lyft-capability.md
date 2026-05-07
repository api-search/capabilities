---
categories: []
consumed_apis: []
description: The Lyft Concierge API allows organizations to request rides on behalf of their customers, patients, or employees without requiring those individuals to have a Lyft account. It is designed for enterprise use cases such as healthcare patient transportation, corporate employee transit, and customer service scenarios. The API enables organizations to build customized transportation workflows, schedule rides in advance, track ride status in real time, and manage ride programs at scale. It provides a way to embed Lyft's driver network directly into business operations and third-party applications.
layout: capability
name: Lyft Concierge API
operations:
- description: List concierge rides
  method: GET
  name: listconciergerides
  path: /concierge/rides
- description: Create a concierge ride
  method: POST
  name: createconciergeride
  path: /concierge/rides
- description: Get concierge ride detail
  method: GET
  name: getconciergeride
  path: /concierge/rides/{id}
- description: Cancel a concierge ride
  method: POST
  name: cancelconciergeride
  path: /concierge/rides/{id}/cancel
- description: Get concierge ride status
  method: GET
  name: getconciergeridestatus
  path: /concierge/rides/{id}/status
- description: List available concierge ride types
  method: GET
  name: listconciergeridetypes
  path: /concierge/ridetypes
- description: List concierge cost estimates
  method: GET
  name: listconciergecostestimates
  path: /concierge/cost
personas: []
provider_name: lyft
provider_slug: lyft
search_terms:
- lyft
- listconciergecostestimates
- api
- getconciergeridestatus
- listconciergeridetypes
- getconciergeride
- list available concierge ride types
- list concierge cost estimates
- create a concierge ride
- listconciergerides
- get concierge ride detail
- list concierge rides
- cancel a concierge ride
- get concierge ride status
- createconciergeride
- cancelconciergeride
slug: lyft-capability
source_filename: lyft-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lyft Concierge API\n  description: The Lyft Concierge API allows organizations to request rides on behalf of their customers, patients, or employees\n    without requiring those individuals to have a Lyft account. It is designed for enterprise use cases such as healthcare\n    patient transportation, corporate employee transit, and customer service scenarios. The API enables organizations to build\n    customized transportation workflows, schedule rides in advance, track ride status in real time, and manage ride programs\n    at scale. It provides a way to embed Lyft's driver network directly into business operations and third-party applications.\n  tags:\n  - Lyft\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lyft\n    baseUri: https://api.lyft.com/v1\n    description: Lyft Concierge API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LYFT_TOKEN}}'\n\
  \    resources:\n    - name: concierge-rides\n      path: /concierge/rides\n      operations:\n      - name: listconciergerides\n        method: GET\n        description: List concierge rides\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter rides by their current status.\n        - name: start_time\n          in: query\n          type: string\n          description: Return rides scheduled or requested after this time. ISO 8601 format.\n        - name: end_time\n          in: query\n          type: string\n          description: Return rides scheduled or requested before this time. ISO 8601 format.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of rides to return per page.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of rides to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createconciergeride\n        method: POST\n        description: Create a concierge ride\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concierge-rides-id\n      path: /concierge/rides/{id}\n      operations:\n      - name: getconciergeride\n        method: GET\n        description: Get concierge ride detail\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concierge-rides-id-cancel\n      path: /concierge/rides/{id}/cancel\n      operations:\n      - name: cancelconciergeride\n        method: POST\n        description: Cancel a concierge ride\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concierge-rides-id-status\n      path: /concierge/rides/{id}/status\n\
  \      operations:\n      - name: getconciergeridestatus\n        method: GET\n        description: Get concierge ride status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concierge-ridetypes\n      path: /concierge/ridetypes\n      operations:\n      - name: listconciergeridetypes\n        method: GET\n        description: List available concierge ride types\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude of the pickup location.\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude of the pickup location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concierge-cost\n      path: /concierge/cost\n      operations:\n      - name: listconciergecostestimates\n\
  \        method: GET\n        description: List concierge cost estimates\n        inputParameters:\n        - name: start_lat\n          in: query\n          type: number\n          required: true\n          description: Latitude of the pickup location.\n        - name: start_lng\n          in: query\n          type: number\n          required: true\n          description: Longitude of the pickup location.\n        - name: end_lat\n          in: query\n          type: number\n          required: true\n          description: Latitude of the destination location.\n        - name: end_lng\n          in: query\n          type: number\n          required: true\n          description: Longitude of the destination location.\n        - name: ride_type\n          in: query\n          type: string\n          description: Filter cost estimates by a specific ride type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \ exposes:\n  - type: rest\n    port: 8080\n    namespace: lyft-rest\n    description: REST adapter for Lyft Concierge API.\n    resources:\n    - path: /concierge/rides\n      name: listconciergerides\n      operations:\n      - method: GET\n        name: listconciergerides\n        description: List concierge rides\n        call: lyft.listconciergerides\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /concierge/rides\n      name: createconciergeride\n      operations:\n      - method: POST\n        name: createconciergeride\n        description: Create a concierge ride\n        call: lyft.createconciergeride\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /concierge/rides/{id}\n      name: getconciergeride\n      operations:\n      - method: GET\n        name: getconciergeride\n        description: Get concierge ride detail\n        call: lyft.getconciergeride\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /concierge/rides/{id}/cancel\n      name: cancelconciergeride\n      operations:\n      - method: POST\n        name: cancelconciergeride\n        description: Cancel a concierge ride\n        call: lyft.cancelconciergeride\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /concierge/rides/{id}/status\n      name: getconciergeridestatus\n      operations:\n      - method: GET\n        name: getconciergeridestatus\n        description: Get concierge ride status\n        call: lyft.getconciergeridestatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /concierge/ridetypes\n      name: listconciergeridetypes\n      operations:\n      - method: GET\n        name: listconciergeridetypes\n        description: List available concierge ride types\n        call: lyft.listconciergeridetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /concierge/cost\n\
  \      name: listconciergecostestimates\n      operations:\n      - method: GET\n        name: listconciergecostestimates\n        description: List concierge cost estimates\n        call: lyft.listconciergecostestimates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lyft-mcp\n    transport: http\n    description: MCP adapter for Lyft Concierge API for AI agent use.\n    tools:\n    - name: listconciergerides\n      description: List concierge rides\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lyft.listconciergerides\n      with:\n        status: tools.status\n        start_time: tools.start_time\n        end_time: tools.end_time\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter rides by their current status.\n      - name: start_time\n        type: string\n\
  \        description: Return rides scheduled or requested after this time. ISO 8601 format.\n      - name: end_time\n        type: string\n        description: Return rides scheduled or requested before this time. ISO 8601 format.\n      - name: limit\n        type: integer\n        description: Maximum number of rides to return per page.\n      - name: offset\n        type: integer\n        description: Number of rides to skip for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconciergeride\n      description: Create a concierge ride\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lyft.createconciergeride\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconciergeride\n      description: Get concierge ride detail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lyft.getconciergeride\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelconciergeride\n      description: Cancel a concierge ride\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lyft.cancelconciergeride\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconciergeridestatus\n      description: Get concierge ride status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lyft.getconciergeridestatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconciergeridetypes\n      description: List available concierge ride types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lyft.listconciergeridetypes\n      with:\n        lat: tools.lat\n        lng: tools.lng\n      inputParameters:\n      - name: lat\n        type: number\n        description: Latitude\
  \ of the pickup location.\n        required: true\n      - name: lng\n        type: number\n        description: Longitude of the pickup location.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconciergecostestimates\n      description: List concierge cost estimates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lyft.listconciergecostestimates\n      with:\n        start_lat: tools.start_lat\n        start_lng: tools.start_lng\n        end_lat: tools.end_lat\n        end_lng: tools.end_lng\n        ride_type: tools.ride_type\n      inputParameters:\n      - name: start_lat\n        type: number\n        description: Latitude of the pickup location.\n        required: true\n      - name: start_lng\n        type: number\n        description: Longitude of the pickup location.\n        required: true\n      - name: end_lat\n        type: number\n        description: Latitude\
  \ of the destination location.\n        required: true\n      - name: end_lng\n        type: number\n        description: Longitude of the destination location.\n        required: true\n      - name: ride_type\n        type: string\n        description: Filter cost estimates by a specific ride type.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LYFT_TOKEN: LYFT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lyft/refs/heads/main/capabilities/lyft-capability.yaml
tags:
- Lyft
- API
tools:
- description: List concierge rides
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconciergerides
- description: Create a concierge ride
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconciergeride
- description: Get concierge ride detail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconciergeride
- description: Cancel a concierge ride
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelconciergeride
- description: Get concierge ride status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconciergeridestatus
- description: List available concierge ride types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconciergeridetypes
- description: List concierge cost estimates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconciergecostestimates
---
