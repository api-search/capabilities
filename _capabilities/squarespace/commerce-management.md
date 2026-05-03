---
categories: []
consumed_apis:
- squarespace-orders
- squarespace-products
- squarespace-inventory
description: Unified commerce management capability combining Squarespace Orders, Products, and Inventory APIs. Enables e-commerce operators, integration developers, and automation tools to manage the full product lifecycle — catalog management, order fulfillment, and stock control — through a single REST API and MCP server. Suited for ERP integrations, warehouse management, and multi-channel retail.
layout: capability
name: Squarespace Commerce Management
operations:
- description: Retrieve all orders with optional date and status filters
  method: GET
  name: list-orders
  path: /v1/orders
- description: Retrieve a specific order by ID
  method: GET
  name: get-order
  path: /v1/orders/{id}
- description: Retrieve all products in the catalog
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product
  method: POST
  name: create-product
  path: /v1/products
- description: Get a specific product
  method: GET
  name: get-product
  path: /v1/products/{id}
- description: Delete a product from the catalog
  method: DELETE
  name: delete-product
  path: /v1/products/{id}
- description: Retrieve inventory levels for all variants
  method: GET
  name: list-inventory
  path: /v1/inventory
- description: Apply stock quantity adjustments
  method: POST
  name: adjust-inventory
  path: /v1/inventory/adjustments
personas: []
provider_name: Squarespace
provider_slug: squarespace
search_terms:
- create product
- retrieve all orders with optional date and status filters
- retrieve all orders from a squarespace merchant site. supports filtering by fulfillment status and modification date range.
- marketing
- apply stock quantity adjustments
- order history and management
- list inventory
- product catalog
- orders
- delete product
- retrieve all products in the squarespace catalog. optionally filter by product type (physical, service, gift_card, digital).
- squarespace
- e-commerce
- individual product management
- stock level management
- inventory
- apply incremental stock quantity adjustments to product variants.
- webhooks
- products
- delete a product from the squarespace catalog.
- delete a product from the catalog
- payments
- individual order details
- retrieve a specific product by its id.
- create a new product
- get order
- commerce
- retrieve details of a specific order by its id.
- retrieve all products in the catalog
- bulk inventory adjustment
- adjust inventory
- retail
- list products
- retrieve current stock levels for all product variants.
- retrieve a specific order by id
- get product
- retrieve inventory levels for all variants
- list orders
- create a new product in the squarespace catalog.
- get a specific product
- website builder
slug: commerce-management
source_filename: commerce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Squarespace Commerce Management\"\n  description: >-\n    Unified commerce management capability combining Squarespace Orders, Products,\n    and Inventory APIs. Enables e-commerce operators, integration developers, and\n    automation tools to manage the full product lifecycle — catalog management,\n    order fulfillment, and stock control — through a single REST API and MCP server.\n    Suited for ERP integrations, warehouse management, and multi-channel retail.\n  tags:\n    - Commerce\n    - E-Commerce\n    - Inventory\n    - Orders\n    - Products\n    - Squarespace\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SQUARESPACE_API_KEY: SQUARESPACE_API_KEY\n\ncapability:\n  consumes:\n    - import: squarespace-orders\n      location: ./shared/orders.yaml\n    - import: squarespace-products\n      location: ./shared/products.yaml\n    - import: squarespace-inventory\n    \
  \  location: ./shared/inventory.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: squarespace-commerce-api\n      description: \"Unified REST API for Squarespace commerce management.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: \"Order history and management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"Retrieve all orders with optional date and status filters\"\n              call: \"squarespace-orders.list-orders\"\n              with:\n                cursor: \"rest.cursor\"\n                modifiedAfter: \"rest.modifiedAfter\"\n                fulfillmentStatus: \"rest.fulfillmentStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{id}\n          name: order\n          description: \"Individual order details\"\n          operations:\n            - method: GET\n\
  \              name: get-order\n              description: \"Retrieve a specific order by ID\"\n              call: \"squarespace-orders.get-order\"\n              with:\n                orderId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: \"Product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"Retrieve all products in the catalog\"\n              call: \"squarespace-products.list-products\"\n              with:\n                cursor: \"rest.cursor\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new product\"\n              call: \"squarespace-products.create-product\"\n\
  \              with:\n                type: \"rest.type\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{id}\n          name: product\n          description: \"Individual product management\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get a specific product\"\n              call: \"squarespace-products.get-product\"\n              with:\n                productId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-product\n              description: \"Delete a product from the catalog\"\n              call: \"squarespace-products.delete-product\"\n              with:\n                productId: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory\n          name: inventory\n          description: \"Stock level management\"\n          operations:\n            - method: GET\n              name: list-inventory\n              description: \"Retrieve inventory levels for all variants\"\n              call: \"squarespace-inventory.list-inventory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory/adjustments\n          name: inventory-adjustments\n          description: \"Bulk inventory adjustment\"\n          operations:\n            - method: POST\n              name: adjust-inventory\n              description: \"Apply stock quantity adjustments\"\n              call: \"squarespace-inventory.adjust-inventory\"\n              with:\n                inventory: \"rest.inventory\"\n              outputParameters:\n                - type: object\n            \
  \      mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: squarespace-commerce-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Squarespace commerce management.\"\n      tools:\n        - name: list-orders\n          description: >-\n            Retrieve all orders from a Squarespace merchant site. Supports filtering\n            by fulfillment status and modification date range.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-orders.list-orders\"\n          with:\n            cursor: \"tools.cursor\"\n            modifiedAfter: \"tools.modifiedAfter\"\n            fulfillmentStatus: \"tools.fulfillmentStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Retrieve details of a specific order by its ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n      \
  \    call: \"squarespace-orders.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: >-\n            Retrieve all products in the Squarespace catalog. Optionally filter\n            by product type (PHYSICAL, SERVICE, GIFT_CARD, DIGITAL).\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-products.list-products\"\n          with:\n            cursor: \"tools.cursor\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Retrieve a specific product by its ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-products.get-product\"\n          with:\n            productId: \"tools.productId\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-product\n          description: \"Create a new product in the Squarespace catalog.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"squarespace-products.create-product\"\n          with:\n            type: \"tools.type\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-product\n          description: \"Delete a product from the Squarespace catalog.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"squarespace-products.delete-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inventory\n\
  \          description: \"Retrieve current stock levels for all product variants.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-inventory.list-inventory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: adjust-inventory\n          description: \"Apply incremental stock quantity adjustments to product variants.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"squarespace-inventory.adjust-inventory\"\n          with:\n            inventory: \"tools.inventory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/squarespace/refs/heads/main/capabilities/commerce-management.yaml
tags:
- Commerce
- E-Commerce
- Inventory
- Orders
- Products
- Squarespace
tools:
- description: Retrieve all orders from a Squarespace merchant site. Supports filtering by fulfillment status and modification date range.
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
- description: Retrieve details of a specific order by its ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-order
- description: Retrieve all products in the Squarespace catalog. Optionally filter by product type (PHYSICAL, SERVICE, GIFT_CARD, DIGITAL).
  hints:
    idempotent: true
    readOnly: true
  name: list-products
- description: Retrieve a specific product by its ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-product
- description: Create a new product in the Squarespace catalog.
  hints:
    idempotent: false
    readOnly: false
  name: create-product
- description: Delete a product from the Squarespace catalog.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-product
- description: Retrieve current stock levels for all product variants.
  hints:
    idempotent: true
    readOnly: true
  name: list-inventory
- description: Apply incremental stock quantity adjustments to product variants.
  hints:
    idempotent: false
    readOnly: false
  name: adjust-inventory
---
