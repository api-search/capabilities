---
categories: []
consumed_apis: []
description: The ArcBest API provides programmatic access to freight services including LTL rate quotes, shipment booking, tracking, BOL generation, and supply chain visibility. Access to the API is by invitation only.
layout: capability
name: ArcBest API
operations:
- description: ArcBest Get LTL Rate Quote
  method: POST
  name: getltlrate
  path: /rates/ltl
- description: ArcBest Create Shipment
  method: POST
  name: createshipment
  path: /shipments
- description: ArcBest List Shipments
  method: GET
  name: listshipments
  path: /shipments
- description: ArcBest Track Shipment
  method: GET
  name: trackshipment
  path: /tracking/{proNumber}
- description: ArcBest Schedule Pickup
  method: POST
  name: schedulepickup
  path: /pickups
personas: []
provider_name: ArcBest
provider_slug: arcbest
search_terms:
- logistics
- arcbest schedule pickup
- createshipment
- manages freight shipments, rates, and carrier relationships
- trackshipment
- freight
- schedulepickup
- arcbest
- supply chain
- transportation
- ltl and truckload freight booking and management
- arcbest get ltl rate quote
- arcbest track shipment
- arcbest create shipment
- shipping
- api
- arcbest list shipments
- listshipments
- coordinates outbound shipping and pickup scheduling
- real-time visibility into freight movement and delivery
- ltl
- getltlrate
- integrates arcbest freight data with business systems
slug: arcbest-capability
source_filename: arcbest-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ArcBest API\n  description: The ArcBest API provides programmatic access to freight services including LTL rate quotes, shipment booking,\n    tracking, BOL generation, and supply chain visibility. Access to the API is by invitation only.\n  tags:\n  - Arcbest\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: arcbest\n    baseUri: https://api.arcbest.com/v2\n    description: ArcBest API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ARCBEST_TOKEN}}'\n    resources:\n    - name: rates-ltl\n      path: /rates/ltl\n      operations:\n      - name: getltlrate\n        method: POST\n        description: ArcBest Get LTL Rate Quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments\n      path: /shipments\n      operations:\n      - name: createshipment\n  \
  \      method: POST\n        description: ArcBest Create Shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listshipments\n        method: GET\n        description: ArcBest List Shipments\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          description: Start date filter (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          description: End date filter (YYYY-MM-DD)\n        - name: status\n          in: query\n          type: string\n          description: Filter by shipment status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracking-pronumber\n      path: /tracking/{proNumber}\n      operations:\n      - name: trackshipment\n        method: GET\n        description: ArcBest Track Shipment\n       \
  \ inputParameters:\n        - name: proNumber\n          in: path\n          type: string\n          required: true\n          description: Shipment PRO number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pickups\n      path: /pickups\n      operations:\n      - name: schedulepickup\n        method: POST\n        description: ArcBest Schedule Pickup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: arcbest-rest\n    description: REST adapter for ArcBest API.\n    resources:\n    - path: /rates/ltl\n      name: getltlrate\n      operations:\n      - method: POST\n        name: getltlrate\n        description: ArcBest Get LTL Rate Quote\n        call: arcbest.getltlrate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments\n\
  \      name: createshipment\n      operations:\n      - method: POST\n        name: createshipment\n        description: ArcBest Create Shipment\n        call: arcbest.createshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments\n      name: listshipments\n      operations:\n      - method: GET\n        name: listshipments\n        description: ArcBest List Shipments\n        call: arcbest.listshipments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/{proNumber}\n      name: trackshipment\n      operations:\n      - method: GET\n        name: trackshipment\n        description: ArcBest Track Shipment\n        call: arcbest.trackshipment\n        with:\n          proNumber: rest.proNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pickups\n      name: schedulepickup\n      operations:\n      - method: POST\n        name: schedulepickup\n     \
  \   description: ArcBest Schedule Pickup\n        call: arcbest.schedulepickup\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: arcbest-mcp\n    transport: http\n    description: MCP adapter for ArcBest API for AI agent use.\n    tools:\n    - name: getltlrate\n      description: ArcBest Get LTL Rate Quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: arcbest.getltlrate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createshipment\n      description: ArcBest Create Shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: arcbest.createshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshipments\n      description: ArcBest List Shipments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: arcbest.listshipments\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        status: tools.status\n      inputParameters:\n      - name: startDate\n        type: string\n        description: Start date filter (YYYY-MM-DD)\n      - name: endDate\n        type: string\n        description: End date filter (YYYY-MM-DD)\n      - name: status\n        type: string\n        description: Filter by shipment status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trackshipment\n      description: ArcBest Track Shipment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arcbest.trackshipment\n      with:\n        proNumber: tools.proNumber\n      inputParameters:\n      - name: proNumber\n        type: string\n        description: Shipment PRO number\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedulepickup\n\
  \      description: ArcBest Schedule Pickup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: arcbest.schedulepickup\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCBEST_TOKEN: ARCBEST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/arcbest/refs/heads/main/capabilities/arcbest-capability.yaml
tags:
- Arcbest
- API
tools:
- description: ArcBest Get LTL Rate Quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getltlrate
- description: ArcBest Create Shipment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshipment
- description: ArcBest List Shipments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshipments
- description: ArcBest Track Shipment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackshipment
- description: ArcBest Schedule Pickup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedulepickup
---
