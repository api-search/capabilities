---
categories: []
consumed_apis:
- vtex-orders
- vtex-logistics
- vtex-catalog
description: Unified workflow capability for VTEX store operators managing day-to-day commerce operations. Combines order management, logistics, and catalog capabilities for fulfillment teams, merchandising managers, and store operations staff who need to monitor, fulfill, and manage the complete order-to-delivery lifecycle.
layout: capability
name: VTEX Store Operations
operations:
- description: List orders with filtering by status and date
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get full order details
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Cancel an order
  method: POST
  name: cancel-order
  path: /v1/orders/{orderId}/cancel
- description: Send invoice for a fulfilled order
  method: POST
  name: send-invoice
  path: /v1/orders/{orderId}/invoices
- description: Get inventory levels for a SKU
  method: GET
  name: get-inventory
  path: /v1/inventory/skus/{skuId}
- description: List all configured warehouses
  method: GET
  name: list-warehouses
  path: /v1/warehouses
- description: Get product details
  method: GET
  name: get-product
  path: /v1/products/{productId}
- description: List available shipping carriers
  method: GET
  name: list-carriers
  path: /v1/carriers
personas: []
provider_name: VTEX
provider_slug: vtex
search_terms:
- send invoice
- get full order details
- update sku inventory
- warehouse management
- fulfillment
- marketplace
- list available shipping carriers
- e-commerce
- get product details
- operations
- cancel an order
- order invoice management
- list all configured warehouses
- shipping carrier configuration
- sku inventory levels
- list warehouses
- cancel a vtex order
- get product details from the vtex catalog
- payments
- order cancellation
- product catalog operations
- order management
- list orders with filtering by status and date
- commerce
- get order
- update inventory quantity for a sku at a specific warehouse
- list all shipping carriers configured in the vtex account
- send invoice for a fulfilled order
- get full details of a vtex order including items, payment, and shipping status
- retail
- get inventory
- list all warehouses configured in the vtex account
- single order operations
- vtex
- get product
- list orders
- cancel order
- get current inventory levels for a sku across all warehouses
- list carriers
- get sku inventory
- send invoice notification for a fulfilled vtex order to trigger shipping
- list vtex orders with optional filtering by status, date range, and other criteria
- get inventory levels for a sku
slug: store-operations
source_filename: store-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VTEX Store Operations\"\n  description: >-\n    Unified workflow capability for VTEX store operators managing day-to-day commerce operations.\n    Combines order management, logistics, and catalog capabilities for fulfillment teams,\n    merchandising managers, and store operations staff who need to monitor, fulfill,\n    and manage the complete order-to-delivery lifecycle.\n  tags:\n    - Commerce\n    - Fulfillment\n    - Order Management\n    - Operations\n    - VTEX\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VTEX_APP_KEY: VTEX_APP_KEY\n      VTEX_APP_TOKEN: VTEX_APP_TOKEN\n\ncapability:\n  consumes:\n    - import: vtex-orders\n      location: ./shared/orders.yaml\n    - import: vtex-logistics\n      location: ./shared/logistics.yaml\n    - import: vtex-catalog\n      location: ./shared/catalog.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ vtex-store-operations-api\n      description: \"Unified REST API for VTEX store operations covering orders, inventory, and catalog.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: \"Order management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders with filtering by status and date\"\n              call: \"vtex-orders.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{orderId}\n          name: order\n          description: \"Single order operations\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get full order details\"\n              call: \"vtex-orders.get-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n          \
  \        mapping: \"$.\"\n\n        - path: /v1/orders/{orderId}/cancel\n          name: cancel-order\n          description: \"Order cancellation\"\n          operations:\n            - method: POST\n              name: cancel-order\n              description: \"Cancel an order\"\n              call: \"vtex-orders.cancel-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{orderId}/invoices\n          name: order-invoices\n          description: \"Order invoice management\"\n          operations:\n            - method: POST\n              name: send-invoice\n              description: \"Send invoice for a fulfilled order\"\n              call: \"vtex-orders.send-invoice\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/inventory/skus/{skuId}\n          name: sku-inventory\n          description: \"SKU inventory levels\"\n          operations:\n            - method: GET\n              name: get-inventory\n              description: \"Get inventory levels for a SKU\"\n              call: \"vtex-logistics.list-inventory-by-sku\"\n              with:\n                skuId: \"rest.skuId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/warehouses\n          name: warehouses\n          description: \"Warehouse management\"\n          operations:\n            - method: GET\n              name: list-warehouses\n              description: \"List all configured warehouses\"\n              call: \"vtex-logistics.list-warehouses\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/products/{productId}\n          name: product\n          description:\
  \ \"Product catalog operations\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get product details\"\n              call: \"vtex-catalog.get-product\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/carriers\n          name: carriers\n          description: \"Shipping carrier configuration\"\n          operations:\n            - method: GET\n              name: list-carriers\n              description: \"List available shipping carriers\"\n              call: \"vtex-logistics.list-carriers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vtex-store-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VTEX store operations and fulfillment management.\"\
  \n      tools:\n        - name: list-orders\n          description: \"List VTEX orders with optional filtering by status, date range, and other criteria\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-orders.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-order\n          description: \"Get full details of a VTEX order including items, payment, and shipping status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-orders.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-order\n          description: \"Cancel a VTEX order\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vtex-orders.cancel-order\"\n\
  \          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-invoice\n          description: \"Send invoice notification for a fulfilled VTEX order to trigger shipping\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vtex-orders.send-invoice\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sku-inventory\n          description: \"Get current inventory levels for a SKU across all warehouses\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-logistics.list-inventory-by-sku\"\n          with:\n            skuId: \"tools.skuId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-sku-inventory\n         \
  \ description: \"Update inventory quantity for a SKU at a specific warehouse\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vtex-logistics.update-inventory\"\n          with:\n            skuId: \"tools.skuId\"\n            warehouseId: \"tools.warehouseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-warehouses\n          description: \"List all warehouses configured in the VTEX account\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-logistics.list-warehouses\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-product\n          description: \"Get product details from the VTEX catalog\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-catalog.get-product\"\n          with:\n\
  \            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-carriers\n          description: \"List all shipping carriers configured in the VTEX account\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-logistics.list-carriers\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vtex/refs/heads/main/capabilities/store-operations.yaml
tags:
- Commerce
- Fulfillment
- Order Management
- Operations
- VTEX
tools:
- description: List VTEX orders with optional filtering by status, date range, and other criteria
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
- description: Get full details of a VTEX order including items, payment, and shipping status
  hints:
    idempotent: true
    readOnly: true
  name: get-order
- description: Cancel a VTEX order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order
- description: Send invoice notification for a fulfilled VTEX order to trigger shipping
  hints:
    destructive: false
    readOnly: false
  name: send-invoice
- description: Get current inventory levels for a SKU across all warehouses
  hints:
    idempotent: true
    readOnly: true
  name: get-sku-inventory
- description: Update inventory quantity for a SKU at a specific warehouse
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-sku-inventory
- description: List all warehouses configured in the VTEX account
  hints:
    idempotent: true
    readOnly: true
  name: list-warehouses
- description: Get product details from the VTEX catalog
  hints:
    idempotent: true
    readOnly: true
  name: get-product
- description: List all shipping carriers configured in the VTEX account
  hints:
    idempotent: true
    readOnly: true
  name: list-carriers
---
