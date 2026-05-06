---
categories: []
consumed_apis: []
description: Unified workflow for supply chain visibility across Ryder's carrier and shipment management APIs. Enables logistics managers to manage carrier load tenders, track shipment status in real-time, submit ship confirmations, and monitor vehicle locations throughout the supply chain lifecycle.
layout: capability
name: Ryder Supply Chain Visibility
operations:
- description: List shipments with current status
  method: GET
  name: list-shipments
  path: /v1/shipments
- description: Submit shipment requirements to Ryder
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Get shipment details
  method: GET
  name: get-shipment
  path: /v1/shipments/{shipmentId}
- description: Update shipment details
  method: PUT
  name: update-shipment
  path: /v1/shipments/{shipmentId}
- description: Get real-time tracking status for a shipment
  method: GET
  name: get-shipment-status
  path: /v1/shipments/{shipmentId}/status
- description: Submit ship confirmation when goods are shipped
  method: POST
  name: confirm-shipment
  path: /v1/ship-confirmations
- description: List carrier load tenders
  method: GET
  name: list-loads
  path: /v1/loads
- description: Get load tender details
  method: GET
  name: get-load
  path: /v1/loads/{loadId}
- description: Submit vehicle location update
  method: POST
  name: submit-location-update
  path: /v1/tracking
personas: []
provider_name: Ryder System
provider_slug: ryder-system
search_terms:
- shipment tracking status
- get carrier load
- logistics
- submit a load event update (pickup, delivery, delay, exception)
- decline load
- confirm shipment
- list loads
- list carrier load tenders
- list load tenders assigned to the carrier from ryder
- vehicle location tracking
- load tenders (carrier)
- decline a load tender from ryder
- accept a load tender from ryder
- submit ship confirmation when goods are shipped
- get shipment
- accept load
- single load tender
- list shipments with current status
- get load tender details
- shipment management
- fleet management
- submit new shipment requirements to ryder transportation management
- supply chain
- submit load event
- transportation
- submit vehicle location update
- submit a real-time vehicle location update for tracking
- single shipment
- submit shipment requirements to ryder
- get shipment status
- get real-time tracking status and location for a shipment
- carrier management
- get load
- submit ship confirmation with actual ship date and tracking number
- create shipment
- update shipment details
- submit location update
- load tracking
- update shipment
- get shipment details
- list carrier loads
- get detailed information for a specific shipment
- get detailed information for a specific carrier load tender
- ship confirmations
- list shipments with current status and tracking information
- update shipment pickup date or special instructions
- trucking
- list shipments
- get real-time tracking status for a shipment
slug: supply-chain-visibility
source_filename: supply-chain-visibility.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ryder Supply Chain Visibility\n  description: Unified workflow for supply chain visibility across Ryder's carrier and shipment management APIs. Enables logistics\n    managers to manage carrier load tenders, track shipment status in real-time, submit ship confirmations, and monitor vehicle\n    locations throughout the supply chain lifecycle.\n  tags:\n  - Carrier Management\n  - Load Tracking\n  - Logistics\n  - Shipment Management\n  - Supply Chain\n  - Transportation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RYDER_CARRIER_API_KEY: RYDER_CARRIER_API_KEY\n    RYDER_TM_API_KEY: RYDER_TM_API_KEY\n    RYDER_TM_CLIENT_ID: RYDER_TM_CLIENT_ID\n    RYDER_TM_CLIENT_SECRET: RYDER_TM_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: ryder-carrier\n    baseUri: https://api.ryder.com/rcsc/events/v1\n    description: Ryder Carrier API for load and transportation management\n  \
  \  authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{RYDER_CARRIER_API_KEY}}'\n      placement: header\n    resources:\n    - name: loads\n      path: /loads\n      description: Load tenders assigned to the carrier\n      operations:\n      - name: list-loads\n        method: GET\n        description: Retrieve a list of load tenders assigned to the carrier\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by load status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-load\n        method:\
  \ GET\n        description: Retrieve detailed information for a specific load tender\n        inputParameters:\n        - name: loadId\n          in: path\n          type: string\n          required: true\n          description: Load identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: accept-load\n        method: POST\n        description: Accept a load tender from Ryder\n        inputParameters:\n        - name: loadId\n          in: path\n          type: string\n          required: true\n          description: Load identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            driver_id: '{{tools.driver_id}}'\n            vehicle_id: '{{tools.vehicle_id}}'\n      - name: decline-load\n        method: POST\n        description: Decline a load tender\
  \ from Ryder\n        inputParameters:\n        - name: loadId\n          in: path\n          type: string\n          required: true\n          description: Load identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reason: '{{tools.reason}}'\n      - name: create-load-event\n        method: POST\n        description: Submit an event update for a load\n        inputParameters:\n        - name: loadId\n          in: path\n          type: string\n          required: true\n          description: Load identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event_type: '{{tools.event_type}}'\n            timestamp: '{{tools.timestamp}}'\n            notes: '{{tools.notes}}'\n    - name: tracking\n\
  \      path: /tracking\n      description: Vehicle and shipment location tracking\n      operations:\n      - name: submit-location-update\n        method: POST\n        description: Submit a real-time vehicle location update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            load_id: '{{tools.load_id}}'\n            vehicle_id: '{{tools.vehicle_id}}'\n            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            timestamp: '{{tools.timestamp}}'\n    - name: documents\n      path: /documents\n      description: Document uploads to RyderShare\n      operations:\n      - name: upload-document\n        method: POST\n        description: Upload a document to the RyderShare platform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \ - type: http\n    namespace: ryder-tm\n    baseUri: https://api.ryder.com/tmshipment/v1\n    description: Ryder TM Shipment Management API\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{RYDER_TM_API_KEY}}'\n      placement: header\n    resources:\n    - name: shipments\n      path: /shipments\n      description: Shipment management operations\n      operations:\n      - name: list-shipments\n        method: GET\n        description: Retrieve a list of shipments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by shipment status\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter (YYYY-MM-DD)\n     \
  \   - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-shipment\n        method: POST\n        description: Submit shipment requirements to Ryder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            origin: '{{tools.origin}}'\n            destination: '{{tools.destination}}'\n            requestedPickupDate: '{{tools.requestedPickupDate}}'\n      - name: get-shipment\n        method: GET\n        description: Retrieve details for a specific shipment\n        inputParameters:\n        - name: shipmentId\n\
  \          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-shipment\n        method: PUT\n        description: Update shipment details or requirements\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requestedPickupDate: '{{tools.requestedPickupDate}}'\n            specialInstructions: '{{tools.specialInstructions}}'\n    - name: loads\n      path: /loads\n      description: Load management within shipments\n      operations:\n      - name: list-loads\n        method: GET\n    \
  \    description: Retrieve a list of loads\n        inputParameters:\n        - name: shipmentId\n          in: query\n          type: string\n          required: false\n          description: Filter by shipment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-load\n        method: GET\n        description: Retrieve details for a specific load\n        inputParameters:\n        - name: loadId\n          in: path\n          type: string\n          required: true\n          description: Load identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ship-confirmations\n      path: /ship-confirmations\n      description: Ship confirmation operations\n      operations:\n      - name: confirm-shipment\n        method: POST\n        description: Submit a ship confirmation when goods are shipped\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            shipmentId: '{{tools.shipmentId}}'\n            actualShipDate: '{{tools.actualShipDate}}'\n            trackingNumber: '{{tools.trackingNumber}}'\n    - name: ship-status\n      path: /ship-status\n      description: Shipment status and tracking\n      operations:\n      - name: get-shipment-status\n        method: GET\n        description: Retrieve current status and tracking for a shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: ryder-supply-chain-api\n    description: Unified REST API for\
  \ Ryder supply chain visibility and management.\n    resources:\n    - path: /v1/shipments\n      name: shipments\n      description: Shipment management\n      operations:\n      - method: GET\n        name: list-shipments\n        description: List shipments with current status\n        call: ryder-tm.list-shipments\n        with:\n          status: rest.query.status\n          startDate: rest.query.startDate\n          endDate: rest.query.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-shipment\n        description: Submit shipment requirements to Ryder\n        call: ryder-tm.create-shipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments/{shipmentId}\n      name: shipment\n      description: Single shipment\n      operations:\n      - method: GET\n        name: get-shipment\n        description: Get shipment details\n        call: ryder-tm.get-shipment\n\
  \        with:\n          shipmentId: rest.path.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-shipment\n        description: Update shipment details\n        call: ryder-tm.update-shipment\n        with:\n          shipmentId: rest.path.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments/{shipmentId}/status\n      name: shipment-status\n      description: Shipment tracking status\n      operations:\n      - method: GET\n        name: get-shipment-status\n        description: Get real-time tracking status for a shipment\n        call: ryder-tm.get-shipment-status\n        with:\n          shipmentId: rest.path.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ship-confirmations\n      name: ship-confirmations\n      description: Ship confirmations\n      operations:\n      - method: POST\n      \
  \  name: confirm-shipment\n        description: Submit ship confirmation when goods are shipped\n        call: ryder-tm.confirm-shipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loads\n      name: loads\n      description: Load tenders (carrier)\n      operations:\n      - method: GET\n        name: list-loads\n        description: List carrier load tenders\n        call: ryder-carrier.list-loads\n        with:\n          status: rest.query.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loads/{loadId}\n      name: load\n      description: Single load tender\n      operations:\n      - method: GET\n        name: get-load\n        description: Get load tender details\n        call: ryder-carrier.get-load\n        with:\n          loadId: rest.path.loadId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracking\n      name: tracking\n      description:\
  \ Vehicle location tracking\n      operations:\n      - method: POST\n        name: submit-location-update\n        description: Submit vehicle location update\n        call: ryder-carrier.submit-location-update\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: ryder-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted Ryder supply chain visibility.\n    tools:\n    - name: list-shipments\n      description: List shipments with current status and tracking information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ryder-tm.list-shipments\n      with:\n        status: tools.status\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment\n      description: Get detailed information for a specific shipment\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: ryder-tm.get-shipment\n      with:\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Submit new shipment requirements to Ryder transportation management\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-tm.create-shipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-shipment\n      description: Update shipment pickup date or special instructions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ryder-tm.update-shipment\n      with:\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment-status\n      description: Get real-time tracking status and location for a shipment\n      hints:\n        readOnly: true\n        openWorld: false\n\
  \      call: ryder-tm.get-shipment-status\n      with:\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: confirm-shipment\n      description: Submit ship confirmation with actual ship date and tracking number\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-tm.confirm-shipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-carrier-loads\n      description: List load tenders assigned to the carrier from Ryder\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ryder-carrier.list-loads\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-carrier-load\n      description: Get detailed information for a specific carrier load tender\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ryder-carrier.get-load\n\
  \      with:\n        loadId: tools.loadId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accept-load\n      description: Accept a load tender from Ryder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-carrier.accept-load\n      with:\n        loadId: tools.loadId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decline-load\n      description: Decline a load tender from Ryder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-carrier.decline-load\n      with:\n        loadId: tools.loadId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-load-event\n      description: Submit a load event update (pickup, delivery, delay, exception)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-carrier.create-load-event\n\
  \      with:\n        loadId: tools.loadId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-location-update\n      description: Submit a real-time vehicle location update for tracking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ryder-carrier.submit-location-update\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ryder-system/refs/heads/main/capabilities/supply-chain-visibility.yaml
tags:
- Carrier Management
- Load Tracking
- Logistics
- Shipment Management
- Supply Chain
- Transportation
tools:
- description: List shipments with current status and tracking information
  hints:
    openWorld: true
    readOnly: true
  name: list-shipments
- description: Get detailed information for a specific shipment
  hints:
    openWorld: false
    readOnly: true
  name: get-shipment
- description: Submit new shipment requirements to Ryder transportation management
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-shipment
- description: Update shipment pickup date or special instructions
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-shipment
- description: Get real-time tracking status and location for a shipment
  hints:
    openWorld: false
    readOnly: true
  name: get-shipment-status
- description: Submit ship confirmation with actual ship date and tracking number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: confirm-shipment
- description: List load tenders assigned to the carrier from Ryder
  hints:
    openWorld: true
    readOnly: true
  name: list-carrier-loads
- description: Get detailed information for a specific carrier load tender
  hints:
    openWorld: false
    readOnly: true
  name: get-carrier-load
- description: Accept a load tender from Ryder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: accept-load
- description: Decline a load tender from Ryder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: decline-load
- description: Submit a load event update (pickup, delivery, delay, exception)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-load-event
- description: Submit a real-time vehicle location update for tracking
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-location-update
---
