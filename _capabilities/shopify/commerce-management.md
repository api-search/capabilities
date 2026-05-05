---
categories: []
consumed_apis: []
description: Unified commerce management capability for Shopify stores covering products, orders, customers, and inventory
layout: capability
name: Shopify Commerce Management
operations:
- description: List products with optional filters
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product
  method: POST
  name: create-product
  path: /v1/products
- description: List orders with filters
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order
  method: POST
  name: create-order
  path: /v1/orders
- description: List customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: List product collections
  method: GET
  name: list-collections
  path: /v1/collections
- description: List inventory levels across locations
  method: GET
  name: list-inventory-levels
  path: /v1/inventory
- description: Adjust inventory at a location
  method: POST
  name: adjust-inventory
  path: /v1/inventory
- description: List fulfillments for an order
  method: GET
  name: list-fulfillments
  path: /v1/fulfillments
- description: Fulfill an order
  method: POST
  name: create-fulfillment
  path: /v1/fulfillments
- description: List webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook subscription
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Shopify
provider_slug: shopify
search_terms:
- create product
- list fulfillment records for a specific order
- list products
- ecommerce
- list customers
- list orders with filters
- list products with optional filters
- manage product collections
- adjust inventory
- commerce
- list fulfillments
- adjust inventory quantity for a product variant at a specific location
- create a new product listing in the shopify store
- list shopify customers with optional email filter
- manage customer orders
- fulfill an order
- manage order fulfillments
- create webhook
- manage store products
- t1
- list inventory levels for products across store locations
- list shopify orders with filters for status, financial status, and fulfillment status
- create a webhook subscription to receive real-time store event notifications
- create a new product
- manage inventory levels
- create a webhook subscription
- create a new customer record in the shopify store
- payments
- create fulfillment
- retail
- shopify
- create a new customer
- list inventory levels across locations
- list webhook subscriptions
- list custom product collections in the shopify store
- shopping cart
- create a fulfillment record to mark order items as shipped
- list all webhook subscriptions configured for the store
- list orders
- adjust inventory at a location
- inventory
- create order
- manage webhook subscriptions
- create customer
- list fulfillments for an order
- create a new order
- list shopify store products with optional filters for status, vendor, and product type
- manage customer records
- list collections
- list inventory levels
- list product collections
- list webhooks
- create a new order in the shopify store
slug: commerce-management
source_filename: commerce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shopify Commerce Management\"\n  description: \"Unified commerce management capability for Shopify stores covering products, orders, customers, and inventory\"\n  tags:\n    - Commerce\n    - Shopify\n    - Ecommerce\n    - Retail\n    - Inventory\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nimports:\n  - ./shared/admin-rest.yaml\n\nbinds:\n  - namespace: env\n    keys:\n      SHOPIFY_ACCESS_TOKEN: SHOPIFY_ACCESS_TOKEN\n      SHOPIFY_STORE: SHOPIFY_STORE\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: shopify-commerce-rest\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Manage store products\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List products with optional filters\"\n              call: \"shopify-admin.list-products\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new product\"\n              call: \"shopify-admin.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Manage customer orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders with filters\"\n              call: \"shopify-admin.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new order\"\n              call: \"shopify-admin.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n  \
  \      - path: /v1/customers\n          name: customers\n          description: \"Manage customer records\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers\"\n              call: \"shopify-admin.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer\"\n              call: \"shopify-admin.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: \"Manage product collections\"\n          operations:\n            - method: GET\n              name: list-collections\n              description: \"List product collections\"\n              call: \"shopify-admin.list-collections\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory\n          name: inventory\n          description: \"Manage inventory levels\"\n          operations:\n            - method: GET\n              name: list-inventory-levels\n              description: \"List inventory levels across locations\"\n              call: \"shopify-admin.list-inventory-levels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: adjust-inventory\n              description: \"Adjust inventory at a location\"\n              call: \"shopify-admin.adjust-inventory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fulfillments\n          name: fulfillments\n          description: \"Manage order fulfillments\"\n          operations:\n            - method: GET\n              name: list-fulfillments\n\
  \              description: \"List fulfillments for an order\"\n              call: \"shopify-admin.list-fulfillments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-fulfillment\n              description: \"Fulfill an order\"\n              call: \"shopify-admin.create-fulfillment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Manage webhook subscriptions\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhook subscriptions\"\n              call: \"shopify-admin.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"\
  Create a webhook subscription\"\n              call: \"shopify-admin.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shopify-commerce-mcp\n      transport: http\n      tools:\n        - name: list-products\n          description: \"List Shopify store products with optional filters for status, vendor, and product type\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-products\"\n          inputParameters:\n            - name: limit\n              type: integer\n              description: \"Maximum number of products to return (max 250)\"\n            - name: status\n              type: string\n              description: \"Filter by status: active, draft, or archived\"\n            - name: vendor\n              type: string\n              description: \"Filter products by vendor name\"\n            - name: product_type\n         \
  \     type: string\n              description: \"Filter products by product type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-product\n          description: \"Create a new product listing in the Shopify store\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.create-product\"\n          inputParameters:\n            - name: title\n              type: string\n              description: \"Product title\"\n            - name: vendor\n              type: string\n              description: \"Product vendor or brand\"\n            - name: product_type\n              type: string\n              description: \"Product category or type\"\n            - name: status\n              type: string\n              description: \"Product status: active, draft, or archived\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description:\
  \ \"List Shopify orders with filters for status, financial status, and fulfillment status\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-orders\"\n          inputParameters:\n            - name: status\n              type: string\n              description: \"Order status: open, closed, cancelled, or any\"\n            - name: financial_status\n              type: string\n              description: \"Payment status: pending, authorized, paid, refunded, etc.\"\n            - name: fulfillment_status\n              type: string\n              description: \"Fulfillment status: fulfilled, partial, or null for unfulfilled\"\n            - name: limit\n              type: integer\n              description: \"Maximum number of orders to return\"\n            - name: created_at_min\n              type: string\n              description: \"Return orders created after this date (ISO 8601)\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: create-order\n          description: \"Create a new order in the Shopify store\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.create-order\"\n          inputParameters:\n            - name: email\n              type: string\n              description: \"Customer email address\"\n            - name: line_items\n              type: array\n              description: \"Array of line items with variant_id and quantity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: \"List Shopify customers with optional email filter\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-customers\"\n          inputParameters:\n            - name: limit\n              type: integer\n              description: \"Maximum number of customers to return\"\n            - name: email\n              type: string\n\
  \              description: \"Filter customers by email address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer record in the Shopify store\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.create-customer\"\n          inputParameters:\n            - name: first_name\n              type: string\n              description: \"Customer first name\"\n            - name: last_name\n              type: string\n              description: \"Customer last name\"\n            - name: email\n              type: string\n              description: \"Customer email address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collections\n          description: \"List custom product collections in the Shopify store\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-collections\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inventory-levels\n          description: \"List inventory levels for products across store locations\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-inventory-levels\"\n          inputParameters:\n            - name: inventory_item_ids\n              type: string\n              description: \"Comma-separated list of inventory item IDs\"\n            - name: location_ids\n              type: string\n              description: \"Comma-separated list of location IDs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: adjust-inventory\n          description: \"Adjust inventory quantity for a product variant at a specific location\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.adjust-inventory\"\n          inputParameters:\n            - name: location_id\n\
  \              type: integer\n              description: \"ID of the location to adjust inventory at\"\n            - name: inventory_item_id\n              type: integer\n              description: \"ID of the inventory item to adjust\"\n            - name: adjustment\n              type: integer\n              description: \"Quantity to add (positive) or remove (negative)\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-fulfillments\n          description: \"List fulfillment records for a specific order\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-fulfillments\"\n          inputParameters:\n            - name: order_id\n              type: integer\n              description: \"ID of the order to list fulfillments for\"\n              required: true\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-fulfillment\n         \
  \ description: \"Create a fulfillment record to mark order items as shipped\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.create-fulfillment\"\n          inputParameters:\n            - name: location_id\n              type: integer\n              description: \"ID of the fulfillment location\"\n            - name: tracking_number\n              type: string\n              description: \"Shipment tracking number\"\n            - name: tracking_company\n              type: string\n              description: \"Shipping carrier name\"\n            - name: notify_customer\n              type: boolean\n              description: \"Whether to send tracking notification to customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List all webhook subscriptions configured for the store\"\n          hints:\n            readOnly: true\n          call: \"shopify-admin.list-webhooks\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Create a webhook subscription to receive real-time store event notifications\"\n          hints:\n            readOnly: false\n          call: \"shopify-admin.create-webhook\"\n          inputParameters:\n            - name: topic\n              type: string\n              description: \"Event topic to subscribe to (e.g., orders/create, products/update)\"\n            - name: address\n              type: string\n              description: \"HTTPS URL to receive webhook POST requests\"\n            - name: format\n              type: string\n              description: \"Payload format: json or xml\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shopify/refs/heads/main/capabilities/commerce-management.yaml
tags:
- Commerce
- Shopify
- Ecommerce
- Retail
- Inventory
tools:
- description: List Shopify store products with optional filters for status, vendor, and product type
  hints:
    readOnly: true
  name: list-products
- description: Create a new product listing in the Shopify store
  hints:
    readOnly: false
  name: create-product
- description: List Shopify orders with filters for status, financial status, and fulfillment status
  hints:
    readOnly: true
  name: list-orders
- description: Create a new order in the Shopify store
  hints:
    readOnly: false
  name: create-order
- description: List Shopify customers with optional email filter
  hints:
    readOnly: true
  name: list-customers
- description: Create a new customer record in the Shopify store
  hints:
    readOnly: false
  name: create-customer
- description: List custom product collections in the Shopify store
  hints:
    readOnly: true
  name: list-collections
- description: List inventory levels for products across store locations
  hints:
    readOnly: true
  name: list-inventory-levels
- description: Adjust inventory quantity for a product variant at a specific location
  hints:
    readOnly: false
  name: adjust-inventory
- description: List fulfillment records for a specific order
  hints:
    readOnly: true
  name: list-fulfillments
- description: Create a fulfillment record to mark order items as shipped
  hints:
    readOnly: false
  name: create-fulfillment
- description: List all webhook subscriptions configured for the store
  hints:
    readOnly: true
  name: list-webhooks
- description: Create a webhook subscription to receive real-time store event notifications
  hints:
    readOnly: false
  name: create-webhook
---
