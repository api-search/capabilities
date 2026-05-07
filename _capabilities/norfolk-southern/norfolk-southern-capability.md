---
categories: []
consumed_apis: []
description: The Norfolk Southern Shipment Status API provides real-time visibility into rail shipment status, including current location, ETA, commodity details, origin, and destination. Part of the Norfolk Southern API Resource Platform (ApiHub).
layout: capability
name: Norfolk Southern Shipment Status API
operations:
- description: Get Shipment Status
  method: GET
  name: getshipmentstatus
  path: /shipments/status
- description: Get Trip Plan
  method: GET
  name: gettripplan
  path: /shipments/tripplan
- description: Get Gate Receipts
  method: GET
  name: getgatereceipts
  path: /gatereceipts
personas: []
provider_name: Norfolk Southern
provider_slug: norfolk-southern
search_terms:
- get shipment status
- getgatereceipts
- freight
- gettripplan
- logistics
- southern
- transportation
- norfolk
- shipping
- getshipmentstatus
- get gate receipts
- api
- get trip plan
- railroad
slug: norfolk-southern-capability
source_filename: norfolk-southern-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Norfolk Southern Shipment Status API\n  description: The Norfolk Southern Shipment Status API provides real-time visibility into rail shipment status, including\n    current location, ETA, commodity details, origin, and destination. Part of the Norfolk Southern API Resource Platform\n    (ApiHub).\n  tags:\n  - Norfolk\n  - Southern\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: norfolk-southern\n    baseUri: https://api.nscorp.com\n    description: Norfolk Southern Shipment Status API HTTP API.\n    resources:\n    - name: shipments-status\n      path: /shipments/status\n      operations:\n      - name: getshipmentstatus\n        method: GET\n        description: Get Shipment Status\n        inputParameters:\n        - name: shipmentId\n          in: query\n          type: string\n          required: true\n          description: The unique identifier for the shipment.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments-tripplan\n      path: /shipments/tripplan\n      operations:\n      - name: gettripplan\n        method: GET\n        description: Get Trip Plan\n        inputParameters:\n        - name: shipmentId\n          in: query\n          type: string\n          required: true\n          description: The unique identifier for the shipment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gatereceipts\n      path: /gatereceipts\n      operations:\n      - name: getgatereceipts\n        method: GET\n        description: Get Gate Receipts\n        inputParameters:\n        - name: terminalId\n          in: query\n          type: string\n          description: The terminal identifier.\n        - name: equipmentId\n          in: query\n          type: string\n \
  \         description: The equipment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: norfolk-southern-rest\n    description: REST adapter for Norfolk Southern Shipment Status API.\n    resources:\n    - path: /shipments/status\n      name: getshipmentstatus\n      operations:\n      - method: GET\n        name: getshipmentstatus\n        description: Get Shipment Status\n        call: norfolk-southern.getshipmentstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/tripplan\n      name: gettripplan\n      operations:\n      - method: GET\n        name: gettripplan\n        description: Get Trip Plan\n        call: norfolk-southern.gettripplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gatereceipts\n      name: getgatereceipts\n      operations:\n\
  \      - method: GET\n        name: getgatereceipts\n        description: Get Gate Receipts\n        call: norfolk-southern.getgatereceipts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: norfolk-southern-mcp\n    transport: http\n    description: MCP adapter for Norfolk Southern Shipment Status API for AI agent use.\n    tools:\n    - name: getshipmentstatus\n      description: Get Shipment Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: norfolk-southern.getshipmentstatus\n      with:\n        shipmentId: tools.shipmentId\n      inputParameters:\n      - name: shipmentId\n        type: string\n        description: The unique identifier for the shipment.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettripplan\n      description: Get Trip Plan\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: norfolk-southern.gettripplan\n      with:\n        shipmentId: tools.shipmentId\n      inputParameters:\n      - name: shipmentId\n        type: string\n        description: The unique identifier for the shipment.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgatereceipts\n      description: Get Gate Receipts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: norfolk-southern.getgatereceipts\n      with:\n        terminalId: tools.terminalId\n        equipmentId: tools.equipmentId\n      inputParameters:\n      - name: terminalId\n        type: string\n        description: The terminal identifier.\n      - name: equipmentId\n        type: string\n        description: The equipment identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/norfolk-southern/refs/heads/main/capabilities/norfolk-southern-capability.yaml
tags:
- Norfolk
- Southern
- API
tools:
- description: Get Shipment Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipmentstatus
- description: Get Trip Plan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettripplan
- description: Get Gate Receipts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgatereceipts
---
