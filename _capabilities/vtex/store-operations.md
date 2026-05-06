---
categories: []
consumed_apis: []
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
- get current inventory levels for a sku across all warehouses
- marketplace
- update sku inventory
- list all configured warehouses
- order invoice management
- list all shipping carriers configured in the vtex account
- send invoice for a fulfilled order
- get order
- single order operations
- vtex
- send invoice
- get product
- warehouse management
- retail
- list orders with filtering by status and date
- cancel order
- shipping carrier configuration
- get full order details
- e-commerce
- list all warehouses configured in the vtex account
- list available shipping carriers
- list vtex orders with optional filtering by status, date range, and other criteria
- operations
- commerce
- order cancellation
- fulfillment
- get inventory levels for a sku
- list warehouses
- update inventory quantity for a sku at a specific warehouse
- get full details of a vtex order including items, payment, and shipping status
- sku inventory levels
- list carriers
- send invoice notification for a fulfilled vtex order to trigger shipping
- get product details from the vtex catalog
- product catalog operations
- payments
- list orders
- cancel an order
- cancel a vtex order
- get sku inventory
- order management
- get product details
- get inventory
slug: store-operations
source_filename: store-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VTEX Store Operations\n  description: Unified workflow capability for VTEX store operators managing day-to-day commerce operations. Combines order\n    management, logistics, and catalog capabilities for fulfillment teams, merchandising managers, and store operations staff\n    who need to monitor, fulfill, and manage the complete order-to-delivery lifecycle.\n  tags:\n  - Commerce\n  - Fulfillment\n  - Order Management\n  - Operations\n  - VTEX\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VTEX_APP_KEY: VTEX_APP_KEY\n    VTEX_APP_TOKEN: VTEX_APP_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vtex-orders\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Orders API for managing order lifecycle and fulfillment.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n  \
  \  resources:\n    - name: orders\n      path: /api/oms/pvt/orders\n      description: Order management operations\n      operations:\n      - name: list-orders\n        method: GET\n        description: List Orders\n        inputParameters:\n        - name: f_status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status\n        - name: orderBy\n          in: query\n          type: string\n          required: false\n          description: Order results by field\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get\
  \ Order by ID\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-order\n        method: POST\n        description: Cancel Order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-invoice\n        method: POST\n        description: Send Invoice\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.invoiceType}}'\n            invoiceNumber: '{{tools.invoiceNumber}}'\n            invoiceValue: '{{tools.invoiceValue}}'\n  - type: http\n    namespace: vtex-logistics\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Logistics API for warehouse, inventory, and shipping management.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n    - name: warehouses\n      path: /api/logistics/pvt/configuration/warehouses\n      description: Warehouse management\n      operations:\n      - name: list-warehouses\n        method: GET\n        description: List Warehouses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-warehouse\n        method: GET\n \
  \       description: Get Warehouse by ID\n        inputParameters:\n        - name: warehouseId\n          in: path\n          type: string\n          required: true\n          description: Warehouse identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /api/logistics/pvt/inventory/skus\n      description: Inventory management operations\n      operations:\n      - name: list-inventory-by-sku\n        method: GET\n        description: List Inventory by SKU\n        inputParameters:\n        - name: skuId\n          in: path\n          type: string\n          required: true\n          description: SKU identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-inventory\n        method: PUT\n        description: Update Inventory by SKU and Warehouse\n        inputParameters:\n\
  \        - name: skuId\n          in: path\n          type: string\n          required: true\n          description: SKU identifier\n        - name: warehouseId\n          in: path\n          type: string\n          required: true\n          description: Warehouse identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            quantity: '{{tools.quantity}}'\n    - name: carriers\n      path: /api/logistics/pvt/configuration/carriers\n      description: Shipping carrier management\n      operations:\n      - name: list-carriers\n        method: GET\n        description: List All Carriers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: vtex-catalog\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Catalog API\
  \ for managing products, SKUs, categories and brands.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n    - name: categories\n      path: /api/catalog_system/pub/category/tree\n      description: Product category tree management\n      operations:\n      - name: get-category-tree\n        method: GET\n        description: Get Category Tree\n        inputParameters:\n        - name: categoryLevels\n          in: path\n          type: integer\n          required: false\n          description: Number of levels to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: products\n      path: /api/catalog/pvt/product\n      description: Product management operations\n      operations:\n      - name: create-product\n        method: POST\n        description: Create Product\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            CategoryId: '{{tools.categoryId}}'\n            BrandId: '{{tools.brandId}}'\n      - name: get-product\n        method: GET\n        description: Get Product by ID\n        inputParameters:\n        - name: productId\n          in: path\n          type: integer\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: skus\n      path: /api/catalog/pvt/stockkeepingunit\n      description: SKU management operations\n      operations:\n      - name: create-sku\n        method: POST\n        description: Create SKU\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \      body:\n          type: json\n          data:\n            ProductId: '{{tools.productId}}'\n            Name: '{{tools.name}}'\n            IsActive: '{{tools.isActive}}'\n      - name: get-sku\n        method: GET\n        description: Get SKU by ID\n        inputParameters:\n        - name: skuId\n          in: path\n          type: integer\n          required: true\n          description: SKU identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vtex-store-operations-api\n    description: Unified REST API for VTEX store operations covering orders, inventory, and catalog.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Order management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List orders with filtering by status and date\n        call: vtex-orders.list-orders\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order\n      description: Single order operations\n      operations:\n      - method: GET\n        name: get-order\n        description: Get full order details\n        call: vtex-orders.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}/cancel\n      name: cancel-order\n      description: Order cancellation\n      operations:\n      - method: POST\n        name: cancel-order\n        description: Cancel an order\n        call: vtex-orders.cancel-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}/invoices\n      name: order-invoices\n      description: Order invoice management\n      operations:\n      - method: POST\n        name: send-invoice\n\
  \        description: Send invoice for a fulfilled order\n        call: vtex-orders.send-invoice\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory/skus/{skuId}\n      name: sku-inventory\n      description: SKU inventory levels\n      operations:\n      - method: GET\n        name: get-inventory\n        description: Get inventory levels for a SKU\n        call: vtex-logistics.list-inventory-by-sku\n        with:\n          skuId: rest.skuId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/warehouses\n      name: warehouses\n      description: Warehouse management\n      operations:\n      - method: GET\n        name: list-warehouses\n        description: List all configured warehouses\n        call: vtex-logistics.list-warehouses\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/products/{productId}\n     \
  \ name: product\n      description: Product catalog operations\n      operations:\n      - method: GET\n        name: get-product\n        description: Get product details\n        call: vtex-catalog.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carriers\n      name: carriers\n      description: Shipping carrier configuration\n      operations:\n      - method: GET\n        name: list-carriers\n        description: List available shipping carriers\n        call: vtex-logistics.list-carriers\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vtex-store-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted VTEX store operations and fulfillment management.\n    tools:\n    - name: list-orders\n      description: List VTEX orders with optional filtering by status, date range, and other criteria\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-orders.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get full details of a VTEX order including items, payment, and shipping status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-orders.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n      description: Cancel a VTEX order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vtex-orders.cancel-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-invoice\n      description: Send invoice notification for a fulfilled VTEX order to trigger shipping\n      hints:\n        readOnly: false\n        destructive: false\n\
  \      call: vtex-orders.send-invoice\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sku-inventory\n      description: Get current inventory levels for a SKU across all warehouses\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-logistics.list-inventory-by-sku\n      with:\n        skuId: tools.skuId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-sku-inventory\n      description: Update inventory quantity for a SKU at a specific warehouse\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vtex-logistics.update-inventory\n      with:\n        skuId: tools.skuId\n        warehouseId: tools.warehouseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-warehouses\n      description: List all warehouses configured in the VTEX account\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: vtex-logistics.list-warehouses\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-product\n      description: Get product details from the VTEX catalog\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-catalog.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-carriers\n      description: List all shipping carriers configured in the VTEX account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-logistics.list-carriers\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
