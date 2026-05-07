---
categories: []
consumed_apis: []
description: project44 Tracking API provides real-time shipment tracking and visibility for multimodal freight including truckload (TL), LTL, ocean, rail, air, and parcel. APIs deliver shipment status updates, predictive ETAs, and exception alerts.
layout: capability
name: project44 Tracking API
operations:
- description: Create a tracked shipment
  method: POST
  name: createshipment
  path: /shipments
- description: List tracked shipments
  method: GET
  name: listshipments
  path: /shipments
- description: Get a shipment
  method: GET
  name: getshipment
  path: /shipments/{shipmentId}
- description: Stop tracking a shipment
  method: DELETE
  name: deleteshipment
  path: /shipments/{shipmentId}
- description: Get shipment status updates
  method: GET
  name: getshipmentstatusupdates
  path: /shipments/{shipmentId}/status-updates
- description: Get shipment position history
  method: GET
  name: getshipmentpositions
  path: /shipments/{shipmentId}/positions
- description: List webhook subscriptions
  method: GET
  name: listwebhooksubscriptions
  path: /webhooks/subscriptions
- description: Create webhook subscription
  method: POST
  name: createwebhooksubscription
  path: /webhooks/subscriptions
- description: Delete webhook subscription
  method: DELETE
  name: deletewebhooksubscription
  path: /webhooks/subscriptions/{subscriptionId}
personas: []
provider_name: project44
provider_slug: project44
search_terms:
- logistics
- listshipments
- project44
- getshipmentpositions
- list tracked shipments
- api
- supply chain
- get a shipment
- freight
- getshipment
- deletewebhooksubscription
- get shipment status updates
- create webhook subscription
- createwebhooksubscription
- stop tracking a shipment
- transportation
- createshipment
- getshipmentstatusupdates
- visibility
- delete webhook subscription
- tracking
- create a tracked shipment
- list webhook subscriptions
- listwebhooksubscriptions
- deleteshipment
- get shipment position history
slug: project44-capability
source_filename: project44-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: project44 Tracking API\n  description: project44 Tracking API provides real-time shipment tracking and visibility for multimodal freight including\n    truckload (TL), LTL, ocean, rail, air, and parcel. APIs deliver shipment status updates, predictive ETAs, and exception\n    alerts.\n  tags:\n  - Project44\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: project44\n    baseUri: https://api.project44.com/api/v4\n    description: project44 Tracking API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PROJECT44_TOKEN}}'\n    resources:\n    - name: shipments\n      path: /shipments\n      operations:\n      - name: createshipment\n        method: POST\n        description: Create a tracked shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listshipments\n\
  \        method: GET\n        description: List tracked shipments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by shipment lifecycle status\n        - name: mode\n          in: query\n          type: string\n          description: Transportation mode filter\n        - name: carrierId\n          in: query\n          type: string\n          description: Carrier SCAC code or project44 carrier ID\n        - name: updatedSince\n          in: query\n          type: string\n          description: Return shipments updated after this ISO 8601 timestamp\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments-shipmentid\n      path: /shipments/{shipmentId}\n      operations:\n      - name:\
  \ getshipment\n        method: GET\n        description: Get a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteshipment\n        method: DELETE\n        description: Stop tracking a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments-shipmentid-status-updates\n      path: /shipments/{shipmentId}/status-updates\n      operations:\n      - name: getshipmentstatusupdates\n        method: GET\n        description: Get shipment status updates\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments-shipmentid-positions\n      path: /shipments/{shipmentId}/positions\n      operations:\n      - name:\
  \ getshipmentpositions\n        method: GET\n        description: Get shipment position history\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-subscriptions\n      path: /webhooks/subscriptions\n      operations:\n      - name: listwebhooksubscriptions\n        method: GET\n        description: List webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhooksubscription\n        method: POST\n        description: Create webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: webhooks-subscriptions-subscriptionid\n      path: /webhooks/subscriptions/{subscriptionId}\n      operations:\n      - name: deletewebhooksubscription\n        method: DELETE\n        description: Delete webhook subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: project44-rest\n    description: REST adapter for project44 Tracking API.\n    resources:\n    - path: /shipments\n      name: createshipment\n      operations:\n      - method: POST\n        name: createshipment\n        description: Create a tracked shipment\n        call: project44.createshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments\n      name: listshipments\n\
  \      operations:\n      - method: GET\n        name: listshipments\n        description: List tracked shipments\n        call: project44.listshipments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/{shipmentId}\n      name: getshipment\n      operations:\n      - method: GET\n        name: getshipment\n        description: Get a shipment\n        call: project44.getshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/{shipmentId}\n      name: deleteshipment\n      operations:\n      - method: DELETE\n        name: deleteshipment\n        description: Stop tracking a shipment\n        call: project44.deleteshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/{shipmentId}/status-updates\n      name: getshipmentstatusupdates\n      operations:\n      - method: GET\n        name: getshipmentstatusupdates\n        description: Get shipment\
  \ status updates\n        call: project44.getshipmentstatusupdates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/{shipmentId}/positions\n      name: getshipmentpositions\n      operations:\n      - method: GET\n        name: getshipmentpositions\n        description: Get shipment position history\n        call: project44.getshipmentpositions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/subscriptions\n      name: listwebhooksubscriptions\n      operations:\n      - method: GET\n        name: listwebhooksubscriptions\n        description: List webhook subscriptions\n        call: project44.listwebhooksubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/subscriptions\n      name: createwebhooksubscription\n      operations:\n      - method: POST\n        name: createwebhooksubscription\n        description: Create webhook subscription\n\
  \        call: project44.createwebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/subscriptions/{subscriptionId}\n      name: deletewebhooksubscription\n      operations:\n      - method: DELETE\n        name: deletewebhooksubscription\n        description: Delete webhook subscription\n        call: project44.deletewebhooksubscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: project44-mcp\n    transport: http\n    description: MCP adapter for project44 Tracking API for AI agent use.\n    tools:\n    - name: createshipment\n      description: Create a tracked shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: project44.createshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshipments\n\
  \      description: List tracked shipments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: project44.listshipments\n      with:\n        status: tools.status\n        mode: tools.mode\n        carrierId: tools.carrierId\n        updatedSince: tools.updatedSince\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by shipment lifecycle status\n      - name: mode\n        type: string\n        description: Transportation mode filter\n      - name: carrierId\n        type: string\n        description: Carrier SCAC code or project44 carrier ID\n      - name: updatedSince\n        type: string\n        description: Return shipments updated after this ISO 8601 timestamp\n      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getshipment\n      description: Get a shipment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: project44.getshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteshipment\n      description: Stop tracking a shipment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: project44.deleteshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshipmentstatusupdates\n      description: Get shipment status updates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: project44.getshipmentstatusupdates\n      with:\n        limit: tools.limit\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: getshipmentpositions\n      description: Get shipment position history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: project44.getshipmentpositions\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        limit: tools.limit\n      inputParameters:\n      - name: startTime\n        type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwebhooksubscriptions\n      description: List webhook subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: project44.listwebhooksubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwebhooksubscription\n      description: Create\
  \ webhook subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: project44.createwebhooksubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewebhooksubscription\n      description: Delete webhook subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: project44.deletewebhooksubscription\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PROJECT44_TOKEN: PROJECT44_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/project44/refs/heads/main/capabilities/project44-capability.yaml
tags:
- Project44
- API
tools:
- description: Create a tracked shipment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshipment
- description: List tracked shipments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshipments
- description: Get a shipment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipment
- description: Stop tracking a shipment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteshipment
- description: Get shipment status updates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipmentstatusupdates
- description: Get shipment position history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipmentpositions
- description: List webhook subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooksubscriptions
- description: Create webhook subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhooksubscription
- description: Delete webhook subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhooksubscription
---
