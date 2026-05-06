---
categories:
- procurement-supply-chain
consumed_apis: []
description: End-to-end supply chain integration workflow for 3M partners and suppliers. Combines product discovery, order management, delivery tracking, and invoice reconciliation into a unified workflow for procurement managers, supply chain analysts, and accounts payable teams.
layout: capability
name: 3M Supply Chain Integration
operations:
- description: List 3M products available to the authenticated partner.
  method: GET
  name: list-products
  path: /v1/products
- description: Get negotiated price for a specific 3M product.
  method: GET
  name: get-product-price
  path: /v1/products
- description: List purchase orders with status information.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Submit a new purchase order.
  method: POST
  name: create-order
  path: /v1/orders
- description: Track delivery status for partner orders.
  method: GET
  name: list-deliveries
  path: /v1/deliveries
- description: Retrieve invoices for billing reconciliation.
  method: GET
  name: list-invoices
  path: /v1/invoices
personas: []
provider_name: 3M
provider_slug: 3m
search_terms:
- purchase order management.
- end-to-end supply chain workflow for procurement and billing
- get the partner-negotiated price for a specific 3m product.
- get negotiated price for a specific 3m product.
- logistics
- get product price
- manufacturing
- 3m product catalog and partner pricing.
- list deliveries
- invoice retrieval for billing reconciliation.
- retrieve 3m invoices for accounts payable reconciliation.
- Accounts Payable
- industrial
- submit a new purchase order.
- 3m product discovery and pricing
- submit a new purchase order for 3m products.
- delivery tracking and shipment status
- track delivery status and estimated arrival for 3m orders.
- searches products, compares pricing, and submits purchase orders
- invoice retrieval and accounts payable reconciliation
- retrieve invoices for billing reconciliation.
- supply chain
- tracks order status, monitors deliveries, and analyzes supply chain data
- list purchase orders placed with 3m with status and tracking.
- purchase order submission and tracking
- list 3m products available to the authenticated partner with pricing.
- track delivery status for partner orders.
- Procurement Manager
- Supply Chain Analyst
- create order
- list orders
- list products
- delivery tracking and logistics.
- list invoices
- track deliveries
- list purchase orders with status information.
- retrieves invoices and reconciles billing with purchase orders
- list 3m products available to the authenticated partner.
- procurement
slug: 3m-supply-chain-integration
source_filename: 3m-supply-chain-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: 3M Supply Chain Integration\n  description: End-to-end supply chain integration workflow for 3M partners and suppliers. Combines product discovery, order\n    management, delivery tracking, and invoice reconciliation into a unified workflow for procurement managers, supply chain\n    analysts, and accounts payable teams.\n  tags:\n  - Manufacturing\n  - Supply Chain\n  - Procurement\n  - Logistics\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THREEEM_BEARER_TOKEN: THREEEM_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: 3m-partner-supplier\n    baseUri: https://api.3m.com\n    description: 3M Partner and Supplier API for supply chain integration\n    authentication:\n      type: bearer\n      token: '{{THREEEM_BEARER_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Product catalog and pricing operations\n      operations:\n     \
  \ - name: list-products\n        method: GET\n        description: 3M List Products\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter products by category\n        - name: sku\n          in: query\n          type: string\n          required: false\n          description: Filter by specific SKU\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product-price\n        method: GET\n        description: 3M Get Product Price\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: The unique product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Order submission\
  \ and tracking\n      operations:\n      - name: list-orders\n        method: GET\n        description: 3M List Orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter orders by status\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Filter orders from this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: 3M Create an Order\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n            shippingAddress: '{{tools.shippingAddress}}'\n    - name: deliveries\n      path:\
  \ /deliveries\n      description: Delivery tracking operations\n      operations:\n      - name: list-deliveries\n        method: GET\n        description: 3M List Deliveries\n        inputParameters:\n        - name: orderId\n          in: query\n          type: string\n          required: false\n          description: Filter by order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoice retrieval operations\n      operations:\n      - name: list-invoices\n        method: GET\n        description: 3M List Invoices\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Filter invoices from this date\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Filter invoices up to\
  \ this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: 3m-supply-chain-api\n    description: Unified REST API for 3M supply chain integration.\n    resources:\n    - path: /v1/products\n      name: products\n      description: 3M product catalog and partner pricing.\n      operations:\n      - method: GET\n        name: list-products\n        description: List 3M products available to the authenticated partner.\n        call: 3m-partner-supplier.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-product-price\n        description: Get negotiated price for a specific 3M product.\n        call: 3m-partner-supplier.get-product-price\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n\
  \      name: orders\n      description: Purchase order management.\n      operations:\n      - method: GET\n        name: list-orders\n        description: List purchase orders with status information.\n        call: 3m-partner-supplier.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Submit a new purchase order.\n        call: 3m-partner-supplier.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deliveries\n      name: deliveries\n      description: Delivery tracking and logistics.\n      operations:\n      - method: GET\n        name: list-deliveries\n        description: Track delivery status for partner orders.\n        call: 3m-partner-supplier.list-deliveries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice retrieval for\
  \ billing reconciliation.\n      operations:\n      - method: GET\n        name: list-invoices\n        description: Retrieve invoices for billing reconciliation.\n        call: 3m-partner-supplier.list-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: 3m-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted 3M supply chain management.\n    tools:\n    - name: list-products\n      description: List 3M products available to the authenticated partner with pricing.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 3m-partner-supplier.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-price\n      description: Get the partner-negotiated price for a specific 3M product.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 3m-partner-supplier.get-product-price\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List purchase orders placed with 3M with status and tracking.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 3m-partner-supplier.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Submit a new purchase order for 3M products.\n      hints:\n        readOnly: false\n        destructive: false\n      call: 3m-partner-supplier.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-deliveries\n      description: Track delivery status and estimated arrival for 3M orders.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 3m-partner-supplier.list-deliveries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: Retrieve 3M invoices for accounts payable reconciliation.\n    \
  \  hints:\n        readOnly: true\n        openWorld: false\n      call: 3m-partner-supplier.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/3m/refs/heads/main/capabilities/3m-supply-chain-integration.yaml
tags:
- Manufacturing
- Supply Chain
- Procurement
- Logistics
tools:
- description: List 3M products available to the authenticated partner with pricing.
  hints:
    openWorld: false
    readOnly: true
  name: list-products
- description: Get the partner-negotiated price for a specific 3M product.
  hints:
    openWorld: false
    readOnly: true
  name: get-product-price
- description: List purchase orders placed with 3M with status and tracking.
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Submit a new purchase order for 3M products.
  hints:
    destructive: false
    readOnly: false
  name: create-order
- description: Track delivery status and estimated arrival for 3M orders.
  hints:
    openWorld: false
    readOnly: true
  name: track-deliveries
- description: Retrieve 3M invoices for accounts payable reconciliation.
  hints:
    openWorld: false
    readOnly: true
  name: list-invoices
---
