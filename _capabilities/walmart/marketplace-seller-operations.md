---
categories: []
consumed_apis: []
description: Unified workflow for Walmart Marketplace seller operations combining order management, inventory tracking, and item catalog management. Enables sellers to monitor and fulfill orders, manage stock levels, and maintain product listings across the Walmart.com marketplace.
layout: capability
name: Walmart Marketplace Seller Operations
operations:
- description: List all marketplace orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get a specific order by purchase order ID
  method: GET
  name: get-order
  path: /v1/orders/{purchaseOrderId}
- description: Get current inventory for an item
  method: GET
  name: get-inventory
  path: /v1/inventory
- description: Update inventory count for an item
  method: PUT
  name: update-inventory
  path: /v1/inventory
- description: List all catalog items
  method: GET
  name: list-items
  path: /v1/items
- description: Search the Walmart product catalog
  method: GET
  name: search-catalog
  path: /v1/catalog/search
personas: []
provider_name: Walmart
provider_slug: walmart
search_terms:
- marketplace
- search the walmart product catalog
- product catalog search
- update inventory
- list items
- list all items in the walmart marketplace seller catalog
- get a specific order by purchase order id
- get order
- single order operations
- search catalog
- retail
- item inventory management
- commerce
- inventory
- get current inventory for an item
- item catalog management
- get released orders
- search the walmart product catalog by keyword
- list all walmart marketplace seller orders
- list all marketplace orders
- get full details of a specific walmart order by purchase order id
- list orders
- get current inventory quantity for a walmart item by sku
- update inventory count for an item
- orders
- update the inventory quantity for a walmart marketplace item
- walmart
- list all catalog items
- catalog
- seller operations
- get inventory
- customer order management
- get orders released and ready for fulfillment
slug: marketplace-seller-operations
source_filename: marketplace-seller-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Walmart Marketplace Seller Operations\n  description: Unified workflow for Walmart Marketplace seller operations combining order management, inventory tracking,\n    and item catalog management. Enables sellers to monitor and fulfill orders, manage stock levels, and maintain product\n    listings across the Walmart.com marketplace.\n  tags:\n  - Walmart\n  - Marketplace\n  - Orders\n  - Inventory\n  - Catalog\n  - Seller Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WALMART_ACCESS_TOKEN: WALMART_ACCESS_TOKEN\n    WALMART_CONSUMER_CHANNEL_TYPE: WALMART_CONSUMER_CHANNEL_TYPE\ncapability:\n  consumes:\n  - type: http\n    namespace: walmart-orders\n    baseUri: https://marketplace.walmartapis.com\n    description: Walmart Marketplace Orders API\n    authentication:\n      type: bearer\n      token: '{{WALMART_ACCESS_TOKEN}}'\n    resources:\n    - name: orders\n      path: /v3/orders\n\
  \      description: Order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all marketplace orders\n        inputParameters:\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID for request tracking\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        - name: createdStartDate\n          in: query\n          type: string\n          required: false\n          description: Filter orders created after this date\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of orders to return\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-released-orders\n        method: GET\n        description: Get released orders ready for fulfillment\n        inputParameters:\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-by-id\n      path: /v3/orders/{purchaseOrderId}\n      description: Single order operations\n      operations:\n      - name: get-order\n        method: GET\n        description: Get a specific order\
  \ by purchase order ID\n        inputParameters:\n        - name: purchaseOrderId\n          in: path\n          type: string\n          required: true\n          description: Purchase order ID\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: walmart-inventory\n    baseUri: https://marketplace.walmartapis.com\n    description: Walmart Marketplace Inventory API\n    authentication:\n      type: bearer\n      token: '{{WALMART_ACCESS_TOKEN}}'\n \
  \   resources:\n    - name: inventory\n      path: /v3/inventory\n      description: Item inventory management\n      operations:\n      - name: get-inventory\n        method: GET\n        description: Get inventory count for a single item\n        inputParameters:\n        - name: sku\n          in: query\n          type: string\n          required: true\n          description: Seller SKU identifier\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-inventory\n\
  \        method: PUT\n        description: Update inventory count for a single item\n        inputParameters:\n        - name: sku\n          in: query\n          type: string\n          required: true\n          description: Seller SKU identifier\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sku: '{{tools.sku}}'\n            quantity:\n              unit: EACH\n              amount: '{{tools.amount}}'\n  -\
  \ type: http\n    namespace: walmart-items\n    baseUri: https://marketplace.walmartapis.com\n    description: Walmart Marketplace Items API\n    authentication:\n      type: bearer\n      token: '{{WALMART_ACCESS_TOKEN}}'\n    resources:\n    - name: items\n      path: /v3/items\n      description: Item catalog management\n      operations:\n      - name: list-items\n        method: GET\n        description: Get all items in the catalog\n        inputParameters:\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description: Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Number of items per page\n        - name: nextCursor\n          in: query\n          type: string\n          required: false\n          description: Cursor for next page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: item-search\n      path: /v3/items/walmart/search\n      description: Walmart catalog search\n      operations:\n      - name: search-catalog\n        method: GET\n        description: Search the Walmart catalog\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: WM_SEC.ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: Walmart access token\n        - name: WM_QOS.CORRELATION_ID\n          in: header\n          type: string\n          required: true\n          description:\
  \ Correlation ID\n        - name: WM_SVC.NAME\n          in: header\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: walmart-seller-api\n    description: Unified REST API for Walmart Marketplace seller operations.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Customer order management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List all marketplace orders\n        call: walmart-orders.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{purchaseOrderId}\n      name: order\n      description: Single order operations\n      operations:\n      - method: GET\n        name: get-order\n        description: Get a specific order by purchase\
  \ order ID\n        call: walmart-orders.get-order\n        with:\n          purchaseOrderId: rest.purchaseOrderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Item inventory management\n      operations:\n      - method: GET\n        name: get-inventory\n        description: Get current inventory for an item\n        call: walmart-inventory.get-inventory\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-inventory\n        description: Update inventory count for an item\n        call: walmart-inventory.update-inventory\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: Item catalog management\n      operations:\n      - method: GET\n        name: list-items\n \
  \       description: List all catalog items\n        call: walmart-items.list-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog/search\n      name: catalog-search\n      description: Product catalog search\n      operations:\n      - method: GET\n        name: search-catalog\n        description: Search the Walmart product catalog\n        call: walmart-items.search-catalog\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: walmart-seller-mcp\n    transport: http\n    description: MCP server for AI-assisted Walmart Marketplace seller operations.\n    tools:\n    - name: list-orders\n      description: List all Walmart Marketplace seller orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walmart-orders.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-order\n      description: Get full details of a specific Walmart order by purchase order ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walmart-orders.get-order\n      with:\n        purchaseOrderId: tools.purchaseOrderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-released-orders\n      description: Get orders released and ready for fulfillment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walmart-orders.get-released-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-inventory\n      description: Get current inventory quantity for a Walmart item by SKU\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walmart-inventory.get-inventory\n      with:\n        sku: tools.sku\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-inventory\n      description: Update the inventory quantity\
  \ for a Walmart Marketplace item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: walmart-inventory.update-inventory\n      with:\n        sku: tools.sku\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-items\n      description: List all items in the Walmart Marketplace seller catalog\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walmart-items.list-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-catalog\n      description: Search the Walmart product catalog by keyword\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walmart-items.search-catalog\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/walmart/refs/heads/main/capabilities/marketplace-seller-operations.yaml
tags:
- Walmart
- Marketplace
- Orders
- Inventory
- Catalog
- Seller Operations
tools:
- description: List all Walmart Marketplace seller orders
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get full details of a specific Walmart order by purchase order ID
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Get orders released and ready for fulfillment
  hints:
    openWorld: true
    readOnly: true
  name: get-released-orders
- description: Get current inventory quantity for a Walmart item by SKU
  hints:
    openWorld: false
    readOnly: true
  name: get-inventory
- description: Update the inventory quantity for a Walmart Marketplace item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-inventory
- description: List all items in the Walmart Marketplace seller catalog
  hints:
    openWorld: false
    readOnly: true
  name: list-items
- description: Search the Walmart product catalog by keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-catalog
---
