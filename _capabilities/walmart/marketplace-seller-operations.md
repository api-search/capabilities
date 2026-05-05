---
categories: []
consumed_apis:
- walmart-orders
- walmart-inventory
- walmart-items
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
- get inventory
- list all marketplace orders
- get released orders
- product catalog search
- search the walmart product catalog
- commerce
- item inventory management
- get order
- list all catalog items
- get orders released and ready for fulfillment
- get current inventory quantity for a walmart item by sku
- list items
- seller operations
- list all walmart marketplace seller orders
- search catalog
- get a specific order by purchase order id
- customer order management
- catalog
- retail
- update the inventory quantity for a walmart marketplace item
- item catalog management
- list all items in the walmart marketplace seller catalog
- get full details of a specific walmart order by purchase order id
- single order operations
- update inventory count for an item
- list orders
- orders
- inventory
- get current inventory for an item
- walmart
- update inventory
- marketplace
- search the walmart product catalog by keyword
slug: marketplace-seller-operations
source_filename: marketplace-seller-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Walmart Marketplace Seller Operations\"\n  description: >-\n    Unified workflow for Walmart Marketplace seller operations combining order\n    management, inventory tracking, and item catalog management. Enables sellers\n    to monitor and fulfill orders, manage stock levels, and maintain product\n    listings across the Walmart.com marketplace.\n  tags:\n    - Walmart\n    - Marketplace\n    - Orders\n    - Inventory\n    - Catalog\n    - Seller Operations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WALMART_ACCESS_TOKEN: WALMART_ACCESS_TOKEN\n      WALMART_CONSUMER_CHANNEL_TYPE: WALMART_CONSUMER_CHANNEL_TYPE\n\ncapability:\n  consumes:\n    - import: walmart-orders\n      location: ./shared/marketplace-orders.yaml\n    - import: walmart-inventory\n      location: ./shared/marketplace-inventory.yaml\n    - import: walmart-items\n      location: ./shared/marketplace-items.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: walmart-seller-api\n      description: \"Unified REST API for Walmart Marketplace seller operations.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: Customer order management\n          operations:\n            - method: GET\n              name: list-orders\n              description: List all marketplace orders\n              call: \"walmart-orders.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{purchaseOrderId}\n          name: order\n          description: Single order operations\n          operations:\n            - method: GET\n              name: get-order\n              description: Get a specific order by purchase order ID\n              call: \"walmart-orders.get-order\"\n              with:\n                purchaseOrderId: \"rest.purchaseOrderId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/inventory\n          name: inventory\n          description: Item inventory management\n          operations:\n            - method: GET\n              name: get-inventory\n              description: Get current inventory for an item\n              call: \"walmart-inventory.get-inventory\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-inventory\n              description: Update inventory count for an item\n              call: \"walmart-inventory.update-inventory\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/items\n          name: items\n          description: Item catalog management\n          operations:\n\
  \            - method: GET\n              name: list-items\n              description: List all catalog items\n              call: \"walmart-items.list-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/search\n          name: catalog-search\n          description: Product catalog search\n          operations:\n            - method: GET\n              name: search-catalog\n              description: Search the Walmart product catalog\n              call: \"walmart-items.search-catalog\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: walmart-seller-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Walmart Marketplace seller operations.\"\n      tools:\n        - name: list-orders\n          description: List all\
  \ Walmart Marketplace seller orders\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"walmart-orders.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: Get full details of a specific Walmart order by purchase order ID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"walmart-orders.get-order\"\n          with:\n            purchaseOrderId: \"tools.purchaseOrderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-released-orders\n          description: Get orders released and ready for fulfillment\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"walmart-orders.get-released-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-inventory\n\
  \          description: Get current inventory quantity for a Walmart item by SKU\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"walmart-inventory.get-inventory\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-inventory\n          description: Update the inventory quantity for a Walmart Marketplace item\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"walmart-inventory.update-inventory\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-items\n          description: List all items in the Walmart Marketplace seller catalog\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"walmart-items.list-items\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-catalog\n          description: Search the Walmart product catalog by keyword\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"walmart-items.search-catalog\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
