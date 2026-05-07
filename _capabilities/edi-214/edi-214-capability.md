---
categories: []
consumed_apis: []
description: REST API interface for EDI X12 214 Transportation Carrier Shipment Status Message. The EDI 214 is an ANSI X12 standard used by transportation carriers to provide shippers, consignees, and agents with shipment status in terms of dates, times, locations, route, and conveyance. Key segments include B10 (tracking identifier), MS1 (current location), and AT7 (current status code). This API translates X12 214 segments into JSON for carrier status updates, delivery confirmations, and exception reporting. Based on the Stedi EDI platform which provides comprehensive X12 214 tooling.
layout: capability
name: EDI 214 Transportation Carrier Shipment Status API
operations:
- description: Translate EDI 214 document to JSON
  method: POST
  name: translateedi214
  path: /edi/translate
- description: Generate EDI 214 document from JSON
  method: POST
  name: generateedi214
  path: /edi/generate
- description: Submit a shipment status update
  method: POST
  name: postshipmentstatus
  path: /shipments/{trackingNumber}/status
- description: List EDI 214 transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: Get EDI 214 transaction details
  method: GET
  name: gettransaction
  path: /transactions/{transactionId}
personas: []
provider_name: edi-214
provider_slug: edi-214
search_terms:
- listtransactions
- postshipmentstatus
- edi
- translate edi 214 document to json
- translateedi214
- generate edi 214 document from json
- submit a shipment status update
- generateedi214
- api
- gettransaction
- get edi 214 transaction details
- list edi 214 transactions
- '214'
slug: edi-214-capability
source_filename: edi-214-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: EDI 214 Transportation Carrier Shipment Status API\n  description: REST API interface for EDI X12 214 Transportation Carrier Shipment Status Message. The EDI 214 is an ANSI X12\n    standard used by transportation carriers to provide shippers, consignees, and agents with shipment status in terms of\n    dates, times, locations, route, and conveyance. Key segments include B10 (tracking identifier), MS1 (current location),\n    and AT7 (current status code). This API translates X12 214 segments into JSON for carrier status updates, delivery confirmations,\n    and exception reporting. Based on the Stedi EDI platform which provides comprehensive X12 214 tooling.\n  tags:\n  - Edi\n  - '214'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: edi-214\n    baseUri: https://api.stedi.com/2024-01-01\n    description: EDI 214 Transportation Carrier Shipment Status API HTTP API.\n\
  \    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{EDI_214_TOKEN}}'\n    resources:\n    - name: edi-translate\n      path: /edi/translate\n      operations:\n      - name: translateedi214\n        method: POST\n        description: Translate EDI 214 document to JSON\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edi-generate\n      path: /edi/generate\n      operations:\n      - name: generateedi214\n        method: POST\n        description: Generate EDI 214 document from JSON\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments-trackingnumber-status\n      path: /shipments/{trackingNumber}/status\n      operations:\n      - name: postshipmentstatus\n        method: POST\n        description: Submit a shipment status update\n        inputParameters:\n\
  \        - name: trackingNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List EDI 214 transactions\n        inputParameters:\n        - name: direction\n          in: query\n          type: string\n          description: Filter by transaction direction\n        - name: processedAfter\n          in: query\n          type: string\n          description: Filter transactions processed after this timestamp\n        - name: status\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid\n\
  \      path: /transactions/{transactionId}\n      operations:\n      - name: gettransaction\n        method: GET\n        description: Get EDI 214 transaction details\n        inputParameters:\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: edi-214-rest\n    description: REST adapter for EDI 214 Transportation Carrier Shipment Status API.\n    resources:\n    - path: /edi/translate\n      name: translateedi214\n      operations:\n      - method: POST\n        name: translateedi214\n        description: Translate EDI 214 document to JSON\n        call: edi-214.translateedi214\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edi/generate\n      name: generateedi214\n      operations:\n      - method: POST\n      \
  \  name: generateedi214\n        description: Generate EDI 214 document from JSON\n        call: edi-214.generateedi214\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipments/{trackingNumber}/status\n      name: postshipmentstatus\n      operations:\n      - method: POST\n        name: postshipmentstatus\n        description: Submit a shipment status update\n        call: edi-214.postshipmentstatus\n        with:\n          trackingNumber: rest.trackingNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List EDI 214 transactions\n        call: edi-214.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions/{transactionId}\n      name: gettransaction\n      operations:\n      - method: GET\n        name: gettransaction\n\
  \        description: Get EDI 214 transaction details\n        call: edi-214.gettransaction\n        with:\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: edi-214-mcp\n    transport: http\n    description: MCP adapter for EDI 214 Transportation Carrier Shipment Status API for AI agent use.\n    tools:\n    - name: translateedi214\n      description: Translate EDI 214 document to JSON\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: edi-214.translateedi214\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateedi214\n      description: Generate EDI 214 document from JSON\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: edi-214.generateedi214\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postshipmentstatus\n\
  \      description: Submit a shipment status update\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: edi-214.postshipmentstatus\n      with:\n        trackingNumber: tools.trackingNumber\n      inputParameters:\n      - name: trackingNumber\n        type: string\n        description: trackingNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: List EDI 214 transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: edi-214.listtransactions\n      with:\n        direction: tools.direction\n        processedAfter: tools.processedAfter\n        status: tools.status\n        limit: tools.limit\n      inputParameters:\n      - name: direction\n        type: string\n        description: Filter by transaction direction\n      - name: processedAfter\n        type: string\n        description:\
  \ Filter transactions processed after this timestamp\n      - name: status\n        type: string\n        description: status\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransaction\n      description: Get EDI 214 transaction details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: edi-214.gettransaction\n      with:\n        transactionId: tools.transactionId\n      inputParameters:\n      - name: transactionId\n        type: string\n        description: transactionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    EDI_214_TOKEN: EDI_214_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/edi-214/refs/heads/main/capabilities/edi-214-capability.yaml
tags:
- Edi
- '214'
- API
tools:
- description: Translate EDI 214 document to JSON
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: translateedi214
- description: Generate EDI 214 document from JSON
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateedi214
- description: Submit a shipment status update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postshipmentstatus
- description: List EDI 214 transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Get EDI 214 transaction details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransaction
---
