---
api_specs:
- filename: 3m-partner-supplier-api-openapi.yml
  format: yaml
  label: 3m-partner-supplier
  slug: 3m-partner-supplier
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/3m/refs/heads/main/openapi/3m-partner-supplier-api-openapi.yml
categories:
- procurement-supply-chain
consumed_apis:
- 3m-partner-supplier
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
- list deliveries
- supply chain
- manufacturing
- create order
- list purchase orders placed with 3m with status and tracking.
- Accounts Payable
- retrieve invoices for billing reconciliation.
- purchase order management.
- list purchase orders with status information.
- submit a new purchase order.
- list 3m products available to the authenticated partner with pricing.
- purchase order submission and tracking
- track delivery status and estimated arrival for 3m orders.
- retrieve 3m invoices for accounts payable reconciliation.
- list invoices
- searches products, compares pricing, and submits purchase orders
- delivery tracking and shipment status
- get product price
- track delivery status for partner orders.
- Supply Chain Analyst
- submit a new purchase order for 3m products.
- get negotiated price for a specific 3m product.
- procurement
- retrieves invoices and reconciles billing with purchase orders
- 3m product catalog and partner pricing.
- list products
- get the partner-negotiated price for a specific 3m product.
- delivery tracking and logistics.
- invoice retrieval for billing reconciliation.
- logistics
- Procurement Manager
- list orders
- track deliveries
- end-to-end supply chain workflow for procurement and billing
- industrial
- invoice retrieval and accounts payable reconciliation
- 3m product discovery and pricing
- list 3m products available to the authenticated partner.
- tracks order status, monitors deliveries, and analyzes supply chain data
slug: 3m-supply-chain-integration
source_filename: 3m-supply-chain-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: 3M Supply Chain Integration\n  description: >-\n    End-to-end supply chain integration workflow for 3M partners and suppliers.\n    Combines product discovery, order management, delivery tracking, and invoice\n    reconciliation into a unified workflow for procurement managers, supply chain\n    analysts, and accounts payable teams.\n  tags:\n    - Manufacturing\n    - Supply Chain\n    - Procurement\n    - Logistics\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      THREEEM_BEARER_TOKEN: THREEEM_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: 3m-partner-supplier\n      location: ./shared/3m-partner-supplier-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: 3m-supply-chain-api\n      description: \"Unified REST API for 3M supply chain integration.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description:\
  \ \"3M product catalog and partner pricing.\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List 3M products available to the authenticated partner.\"\n              call: \"3m-partner-supplier.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-product-price\n              description: \"Get negotiated price for a specific 3M product.\"\n              call: \"3m-partner-supplier.get-product-price\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Purchase order management.\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List purchase orders with\
  \ status information.\"\n              call: \"3m-partner-supplier.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Submit a new purchase order.\"\n              call: \"3m-partner-supplier.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deliveries\n          name: deliveries\n          description: \"Delivery tracking and logistics.\"\n          operations:\n            - method: GET\n              name: list-deliveries\n              description: \"Track delivery status for partner orders.\"\n              call: \"3m-partner-supplier.list-deliveries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice retrieval\
  \ for billing reconciliation.\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"Retrieve invoices for billing reconciliation.\"\n              call: \"3m-partner-supplier.list-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: 3m-supply-chain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted 3M supply chain management.\"\n      tools:\n        - name: list-products\n          description: \"List 3M products available to the authenticated partner with pricing.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"3m-partner-supplier.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-price\n          description: \"Get the partner-negotiated price for a specific\
  \ 3M product.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"3m-partner-supplier.get-product-price\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-orders\n          description: \"List purchase orders placed with 3M with status and tracking.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"3m-partner-supplier.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-order\n          description: \"Submit a new purchase order for 3M products.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"3m-partner-supplier.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-deliveries\n          description: \"Track delivery status and estimated\
  \ arrival for 3M orders.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"3m-partner-supplier.list-deliveries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-invoices\n          description: \"Retrieve 3M invoices for accounts payable reconciliation.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"3m-partner-supplier.list-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
