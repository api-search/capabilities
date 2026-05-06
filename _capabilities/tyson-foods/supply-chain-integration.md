---
categories: []
consumed_apis: []
description: 'Unified workflow for Tyson Foods trading partners to manage the full B2B supply chain lifecycle: purchase orders, order tracking, and shipment monitoring. Used by retail buyers, distributors, and logistics teams integrating with Tyson Foods.'
layout: capability
name: Tyson Foods Supply Chain Integration
operations:
- description: Retrieve all purchase orders for the trading partner
  method: GET
  name: get-orders
  path: /v1/orders
- description: Get a specific purchase order
  method: GET
  name: get-order-by-id
  path: /v1/orders/{orderId}
- description: Retrieve shipment tracking information
  method: GET
  name: get-shipments
  path: /v1/shipments
personas: []
provider_name: Tyson Foods
provider_slug: tyson-foods
search_terms:
- retrieve all purchase orders for the trading partner
- logistics
- purchase order management
- retrieve shipment tracking information for tyson foods orders
- retrieve purchase orders from the tyson foods b2b trading partner portal
- get a specific purchase order
- get shipments
- b2b
- edi
- supply chain
- retrieve shipment tracking information
- single order detail
- get the details of a specific tyson foods purchase order
- food
- shipment tracking
- tyson foods
- b2b integration
- order management
- get orders
- get order by id
- fortune 100
slug: supply-chain-integration
source_filename: supply-chain-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tyson Foods Supply Chain Integration\n  description: 'Unified workflow for Tyson Foods trading partners to manage the full B2B supply chain lifecycle: purchase\n    orders, order tracking, and shipment monitoring. Used by retail buyers, distributors, and logistics teams integrating\n    with Tyson Foods.'\n  tags:\n  - Tyson Foods\n  - Supply Chain\n  - EDI\n  - Order Management\n  - Logistics\n  - B2B\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TYSON_FOODS_ACCESS_TOKEN: TYSON_FOODS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tyson-edi\n    baseUri: https://api.tysonfoods.com\n    description: Tyson Foods EDI Integration REST API\n    authentication:\n      type: bearer\n      token: '{{TYSON_FOODS_ACCESS_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      description: Purchase order management\n      operations:\n      - name: get-orders\n \
  \       method: GET\n        description: Retrieve a list of orders for a trading partner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order\n      path: /orders/{orderId}\n      description: Single order operations\n      operations:\n      - name: get-order-by-id\n        method: GET\n        description: Retrieve a specific order by ID\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Purchase order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments\n      path: /shipments\n      description: Shipment tracking\n      operations:\n      - name: get-shipments\n        method: GET\n        description: Retrieve shipment information for a trading partner\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tyson-supply-chain-api\n    description: Unified REST API for Tyson Foods supply chain integration.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Purchase order management\n      operations:\n      - method: GET\n        name: get-orders\n        description: Retrieve all purchase orders for the trading partner\n        call: tyson-edi.get-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order\n      description: Single order detail\n      operations:\n      - method: GET\n        name: get-order-by-id\n        description: Get a specific purchase order\n        call: tyson-edi.get-order-by-id\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/shipments\n      name: shipments\n      description: Shipment tracking\n      operations:\n      - method: GET\n        name: get-shipments\n        description: Retrieve shipment tracking information\n        call: tyson-edi.get-shipments\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: tyson-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted Tyson Foods supply chain management.\n    tools:\n    - name: get-orders\n      description: Retrieve purchase orders from the Tyson Foods B2B trading partner portal\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tyson-edi.get-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order-by-id\n      description: Get the details of a specific Tyson Foods purchase order\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tyson-edi.get-order-by-id\n   \
  \   with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipments\n      description: Retrieve shipment tracking information for Tyson Foods orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tyson-edi.get-shipments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tyson-foods/refs/heads/main/capabilities/supply-chain-integration.yaml
tags:
- Tyson Foods
- Supply Chain
- EDI
- Order Management
- Logistics
- B2B
tools:
- description: Retrieve purchase orders from the Tyson Foods B2B trading partner portal
  hints:
    openWorld: true
    readOnly: true
  name: get-orders
- description: Get the details of a specific Tyson Foods purchase order
  hints:
    openWorld: true
    readOnly: true
  name: get-order-by-id
- description: Retrieve shipment tracking information for Tyson Foods orders
  hints:
    openWorld: true
    readOnly: true
  name: get-shipments
---
