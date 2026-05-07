---
categories: []
consumed_apis: []
description: The Goodyear API Management Portal provides access to Goodyear's suite of APIs for tire and fleet management services including catalog, work order, and service ticket management.
layout: capability
name: Goodyear API Management Portal (GaaS)
operations:
- description: Get Tire Catalog
  method: GET
  name: gettirecatalog
  path: /catalog
- description: Get Work Orders
  method: GET
  name: getworkorders
  path: /work-orders
- description: Create Work Order
  method: POST
  name: createworkorder
  path: /work-orders
- description: Get Service Tickets
  method: GET
  name: getservicetickets
  path: /service-tickets
- description: Create Service Ticket
  method: POST
  name: createserviceticket
  path: /service-tickets
personas: []
provider_name: Goodyear Tire & Rubber
provider_slug: goodyear-tire-and-rubber
search_terms:
- create service ticket
- telematics
- goodyear
- api
- gettirecatalog
- createserviceticket
- rubber
- get tire catalog
- getservicetickets
- createworkorder
- create work order
- iot
- connected vehicles
- fleet management
- get work orders
- get service tickets
- tire
- and
- tires
- getworkorders
slug: goodyear-tire-and-rubber-capability
source_filename: goodyear-tire-and-rubber-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Goodyear API Management Portal (GaaS)\n  description: The Goodyear API Management Portal provides access to Goodyear's suite of APIs for tire and fleet management\n    services including catalog, work order, and service ticket management.\n  tags:\n  - Goodyear\n  - Tire\n  - And\n  - Rubber\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: goodyear-tire-and-rubber\n    baseUri: https://gaas-portal.goodyear.com\n    description: Goodyear API Management Portal (GaaS) HTTP API.\n    resources:\n    - name: catalog\n      path: /catalog\n      operations:\n      - name: gettirecatalog\n        method: GET\n        description: Get Tire Catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-orders\n      path: /work-orders\n      operations:\n      - name: getworkorders\n    \
  \    method: GET\n        description: Get Work Orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkorder\n        method: POST\n        description: Create Work Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-tickets\n      path: /service-tickets\n      operations:\n      - name: getservicetickets\n        method: GET\n        description: Get Service Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserviceticket\n        method: POST\n        description: Create Service Ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: goodyear-tire-and-rubber-rest\n\
  \    description: REST adapter for Goodyear API Management Portal (GaaS).\n    resources:\n    - path: /catalog\n      name: gettirecatalog\n      operations:\n      - method: GET\n        name: gettirecatalog\n        description: Get Tire Catalog\n        call: goodyear-tire-and-rubber.gettirecatalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /work-orders\n      name: getworkorders\n      operations:\n      - method: GET\n        name: getworkorders\n        description: Get Work Orders\n        call: goodyear-tire-and-rubber.getworkorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /work-orders\n      name: createworkorder\n      operations:\n      - method: POST\n        name: createworkorder\n        description: Create Work Order\n        call: goodyear-tire-and-rubber.createworkorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service-tickets\n     \
  \ name: getservicetickets\n      operations:\n      - method: GET\n        name: getservicetickets\n        description: Get Service Tickets\n        call: goodyear-tire-and-rubber.getservicetickets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service-tickets\n      name: createserviceticket\n      operations:\n      - method: POST\n        name: createserviceticket\n        description: Create Service Ticket\n        call: goodyear-tire-and-rubber.createserviceticket\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: goodyear-tire-and-rubber-mcp\n    transport: http\n    description: MCP adapter for Goodyear API Management Portal (GaaS) for AI agent use.\n    tools:\n    - name: gettirecatalog\n      description: Get Tire Catalog\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goodyear-tire-and-rubber.gettirecatalog\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkorders\n      description: Get Work Orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goodyear-tire-and-rubber.getworkorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkorder\n      description: Create Work Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goodyear-tire-and-rubber.createworkorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservicetickets\n      description: Get Service Tickets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goodyear-tire-and-rubber.getservicetickets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createserviceticket\n      description: Create Service Ticket\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goodyear-tire-and-rubber.createserviceticket\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/goodyear-tire-and-rubber/refs/heads/main/capabilities/goodyear-tire-and-rubber-capability.yaml
tags:
- Goodyear
- Tire
- And
- Rubber
- API
tools:
- description: Get Tire Catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettirecatalog
- description: Get Work Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkorders
- description: Create Work Order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkorder
- description: Get Service Tickets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservicetickets
- description: Create Service Ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserviceticket
---
