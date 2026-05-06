---
categories: []
consumed_apis: []
description: Workflow capability for managing the complete U.S. Steel supply chain relationship. Combines order management, inventory tracking, shipment visibility, and quality documentation from the SteelTrack platform. Designed for procurement managers, supply chain analysts, and automotive supplier quality engineers who need integrated visibility into steel orders from placement through delivery and quality certification.
layout: capability
name: U.S. Steel Supply Chain Management
operations:
- description: List orders.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get order by ID.
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: List available inventory.
  method: GET
  name: list-inventory
  path: /v1/inventory
- description: List shipments.
  method: GET
  name: list-shipments
  path: /v1/shipments
- description: List test reports.
  method: GET
  name: list-test-reports
  path: /v1/test-reports
personas: []
provider_name: United States Steel
provider_slug: united-states-steel
search_terms:
- list steel inventory
- construction
- steel order management and status tracking.
- manufacturing
- shipment history and tracking.
- get order by id.
- list shipments.
- engineer accessing certified test reports for compliance and ppap documentation
- get order
- analyst monitoring order status, inventory levels, and shipment performance
- list orders.
- manager overseeing steel procurement and supplier relationship management
- list steel shipments
- list u.s. steel shipment history for orders and purchase orders with coil-level detail.
- list inventory
- quality test reports.
- steel product quality documentation and certification
- u.s. steel
- automotive
- supply chain
- list available inventory.
- list certified physical, mechanical, and chemical test reports for steel products by coil or order.
- procurement manager
- supply chain analyst
- list steel orders
- energy
- list test reports
- quality
- get order details.
- list orders
- list available u.s. steel customer inventory by product type, grade, and facility.
- steel
- quality engineer
- get steel order
- steel procurement and supply chain management
- list shipments
- list u.s. steel orders with filtering by status, facility, and date range.
- get detailed information for a specific u.s. steel order including production status and delivery timeline.
- available inventory tracking.
- list test reports.
- procurement
- complete u.s. steel supply chain from order tracking through shipment and quality certification
slug: supply-chain-management
source_filename: supply-chain-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: U.S. Steel Supply Chain Management\n  description: Workflow capability for managing the complete U.S. Steel supply chain relationship. Combines order management,\n    inventory tracking, shipment visibility, and quality documentation from the SteelTrack platform. Designed for procurement\n    managers, supply chain analysts, and automotive supplier quality engineers who need integrated visibility into steel orders\n    from placement through delivery and quality certification.\n  tags:\n  - U.S. Steel\n  - Supply Chain\n  - Procurement\n  - Quality\n  - Manufacturing\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USSTEEL_BEARER_TOKEN: USSTEEL_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ussteel-steeltrack\n    baseUri: https://steeltrack.ussteel.com/api\n    description: U.S. Steel SteelTrack customer platform API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{USSTEEL_BEARER_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      description: Steel order management.\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders with optional filters.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status.\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter by customer ID.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n  \
  \      method: GET\n        description: Get order details by order ID.\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      description: Customer inventory tracking.\n      operations:\n      - name: list-inventory\n        method: GET\n        description: List available inventory items.\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter by customer ID.\n        - name: product\n          in: query\n          type: string\n          required: false\n          description: Filter by product type.\n        - name: grade\n          in: query\n          type: string\n          required: false\n   \
  \       description: Filter by steel grade.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments\n      path: /shipments\n      description: Shipment history and tracking.\n      operations:\n      - name: list-shipments\n        method: GET\n        description: List shipment history.\n        inputParameters:\n        - name: orderId\n          in: query\n          type: string\n          required: false\n          description: Filter by order ID.\n        - name: purchaseOrder\n          in: query\n          type: string\n          required: false\n          description: Filter by purchase order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: test-reports\n      path: /test-reports\n      description: Steel product test reports.\n      operations:\n      - name: list-test-reports\n        method:\
  \ GET\n        description: List test reports for steel products.\n        inputParameters:\n        - name: coilId\n          in: query\n          type: string\n          required: false\n          description: Filter by coil ID.\n        - name: orderId\n          in: query\n          type: string\n          required: false\n          description: Filter by order ID.\n        - name: reportType\n          in: query\n          type: string\n          required: false\n          description: Filter by report type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ussteel-supply-chain-api\n    description: Unified REST API for U.S. Steel supply chain management.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Steel order management and status tracking.\n      operations:\n      - method: GET\n        name: list-orders\n \
  \       description: List orders.\n        call: ussteel-steeltrack.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order-detail\n      description: Get order details.\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order by ID.\n        call: ussteel-steeltrack.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Available inventory tracking.\n      operations:\n      - method: GET\n        name: list-inventory\n        description: List available inventory.\n        call: ussteel-steeltrack.list-inventory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Shipment history and tracking.\n      operations:\n      - method:\
  \ GET\n        name: list-shipments\n        description: List shipments.\n        call: ussteel-steeltrack.list-shipments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-reports\n      name: test-reports\n      description: Quality test reports.\n      operations:\n      - method: GET\n        name: list-test-reports\n        description: List test reports.\n        call: ussteel-steeltrack.list-test-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ussteel-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted U.S. Steel supply chain management.\n    tools:\n    - name: list-steel-orders\n      description: List U.S. Steel orders with filtering by status, facility, and date range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ussteel-steeltrack.list-orders\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-steel-order\n      description: Get detailed information for a specific U.S. Steel order including production status and delivery timeline.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ussteel-steeltrack.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-steel-inventory\n      description: List available U.S. Steel customer inventory by product type, grade, and facility.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ussteel-steeltrack.list-inventory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-steel-shipments\n      description: List U.S. Steel shipment history for orders and purchase orders with coil-level detail.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ussteel-steeltrack.list-shipments\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-test-reports\n      description: List certified physical, mechanical, and chemical test reports for steel products by coil or order.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ussteel-steeltrack.list-test-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-steel/refs/heads/main/capabilities/supply-chain-management.yaml
tags:
- U.S. Steel
- Supply Chain
- Procurement
- Quality
- Manufacturing
tools:
- description: List U.S. Steel orders with filtering by status, facility, and date range.
  hints:
    openWorld: true
    readOnly: true
  name: list-steel-orders
- description: Get detailed information for a specific U.S. Steel order including production status and delivery timeline.
  hints:
    openWorld: true
    readOnly: true
  name: get-steel-order
- description: List available U.S. Steel customer inventory by product type, grade, and facility.
  hints:
    openWorld: true
    readOnly: true
  name: list-steel-inventory
- description: List U.S. Steel shipment history for orders and purchase orders with coil-level detail.
  hints:
    openWorld: true
    readOnly: true
  name: list-steel-shipments
- description: List certified physical, mechanical, and chemical test reports for steel products by coil or order.
  hints:
    openWorld: true
    readOnly: true
  name: list-test-reports
---
