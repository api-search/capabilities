---
categories: []
consumed_apis: []
description: The J.B. Hunt 360 Connect API provides programmatic access to quoting, order management, shipment tracking, document management, and scheduling on the J.B. Hunt 360 logistics platform. Supports full-truckload (FTL) and less-than-truckload (LTL) shipment operations.
layout: capability
name: J.B. Hunt 360 Connect API
operations:
- description: Request Quote
  method: POST
  name: createquote
  path: /quotes
- description: Create Order
  method: POST
  name: createorder
  path: /orders
- description: Search Orders
  method: GET
  name: searchorders
  path: /orders
- description: Get Order Details
  method: GET
  name: getorder
  path: /orders/{orderId}
- description: Track Shipment
  method: GET
  name: trackshipment
  path: /tracking/{shipmentId}
- description: Upload Document
  method: POST
  name: uploaddocument
  path: /documents
- description: Get Documents
  method: GET
  name: getdocuments
  path: /documents
- description: Create Appointment
  method: POST
  name: createappointment
  path: /appointments
personas: []
provider_name: J.B. Hunt Transport Services
provider_slug: jb-hunt-transport-services
search_terms:
- upload document
- hunt
- logistics
- request quote
- services
- intermodal
- getorder
- search orders
- create appointment
- createquote
- uploaddocument
- trackshipment
- freight
- createorder
- supply chain
- track shipment
- transportation
- shipping
- createappointment
- api
- get documents
- jb
- get order details
- getdocuments
- searchorders
- create order
- transport
- trucking
slug: jb-hunt-transport-services-capability
source_filename: jb-hunt-transport-services-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: J.B. Hunt 360 Connect API\n  description: The J.B. Hunt 360 Connect API provides programmatic access to quoting, order management, shipment tracking,\n    document management, and scheduling on the J.B. Hunt 360 logistics platform. Supports full-truckload (FTL) and less-than-truckload\n    (LTL) shipment operations.\n  tags:\n  - Jb\n  - Hunt\n  - Transport\n  - Services\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jb-hunt-transport-services\n    baseUri: https://api.jbhunt.com\n    description: J.B. Hunt 360 Connect API HTTP API.\n    resources:\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: createquote\n        method: POST\n        description: Request Quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      operations:\n\
  \      - name: createorder\n        method: POST\n        description: Create Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchorders\n        method: GET\n        description: Search Orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid\n      path: /orders/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Get Order Details\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: tracking-shipmentid\n      path: /tracking/{shipmentId}\n      operations:\n      - name: trackshipment\n        method: GET\n        description: Track Shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      operations:\n      - name: uploaddocument\n        method: POST\n        description: Upload Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdocuments\n        method: GET\n        description: Get Documents\n        inputParameters:\n        - name: shipmentId\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appointments\n      path: /appointments\n      operations:\n      - name: createappointment\n        method: POST\n        description: Create Appointment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jb-hunt-transport-services-rest\n    description: REST adapter for J.B. Hunt 360 Connect API.\n    resources:\n    - path: /quotes\n      name: createquote\n      operations:\n      - method: POST\n        name: createquote\n        description: Request Quote\n        call: jb-hunt-transport-services.createquote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Create Order\n   \
  \     call: jb-hunt-transport-services.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: searchorders\n      operations:\n      - method: GET\n        name: searchorders\n        description: Search Orders\n        call: jb-hunt-transport-services.searchorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Get Order Details\n        call: jb-hunt-transport-services.getorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/{shipmentId}\n      name: trackshipment\n      operations:\n      - method: GET\n        name: trackshipment\n        description: Track Shipment\n        call: jb-hunt-transport-services.trackshipment\n        with:\n          shipmentId: rest.shipmentId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents\n      name: uploaddocument\n      operations:\n      - method: POST\n        name: uploaddocument\n        description: Upload Document\n        call: jb-hunt-transport-services.uploaddocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents\n      name: getdocuments\n      operations:\n      - method: GET\n        name: getdocuments\n        description: Get Documents\n        call: jb-hunt-transport-services.getdocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appointments\n      name: createappointment\n      operations:\n      - method: POST\n        name: createappointment\n        description: Create Appointment\n        call: jb-hunt-transport-services.createappointment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace:\
  \ jb-hunt-transport-services-mcp\n    transport: http\n    description: MCP adapter for J.B. Hunt 360 Connect API for AI agent use.\n    tools:\n    - name: createquote\n      description: Request Quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jb-hunt-transport-services.createquote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Create Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jb-hunt-transport-services.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchorders\n      description: Search Orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jb-hunt-transport-services.searchorders\n      with:\n        status: tools.status\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n\
  \      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Get Order Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jb-hunt-transport-services.getorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trackshipment\n      description: Track Shipment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jb-hunt-transport-services.trackshipment\n      with:\n        shipmentId: tools.shipmentId\n\
  \      inputParameters:\n      - name: shipmentId\n        type: string\n        description: shipmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploaddocument\n      description: Upload Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jb-hunt-transport-services.uploaddocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocuments\n      description: Get Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jb-hunt-transport-services.getdocuments\n      with:\n        shipmentId: tools.shipmentId\n      inputParameters:\n      - name: shipmentId\n        type: string\n        description: shipmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createappointment\n      description: Create Appointment\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jb-hunt-transport-services.createappointment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jb-hunt-transport-services/refs/heads/main/capabilities/jb-hunt-transport-services-capability.yaml
tags:
- Jb
- Hunt
- Transport
- Services
- API
tools:
- description: Request Quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createquote
- description: Create Order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Search Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchorders
- description: Get Order Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
- description: Track Shipment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackshipment
- description: Upload Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploaddocument
- description: Get Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocuments
- description: Create Appointment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createappointment
---
