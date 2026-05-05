---
api_specs:
- filename: shopify-admin-rest-openapi.yml
  format: yaml
  label: shopify-admin-rest
  slug: shopify-admin-rest
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shopify-admin/refs/heads/main/openapi/shopify-admin-rest-openapi.yml
categories: []
consumed_apis:
- shopify-admin-rest
description: Unified workflow capability for comprehensive Shopify store management. Combines product catalog management, customer relationship management, order processing, inventory tracking, and store configuration into a single integrated capability for merchants and app developers.
layout: capability
name: Shopify Admin Store Management
operations:
- description: List all products with optional status filtering
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product in the store
  method: POST
  name: create-product
  path: /v1/products
- description: Retrieve a product by ID
  method: GET
  name: get-product
  path: /v1/products/{id}
- description: Update product details
  method: PUT
  name: update-product
  path: /v1/products/{id}
- description: Remove a product from the store
  method: DELETE
  name: delete-product
  path: /v1/products/{id}
- description: List orders with financial and fulfillment status filtering
  method: GET
  name: list-orders
  path: /v1/orders
- description: Retrieve an order by ID
  method: GET
  name: get-order
  path: /v1/orders/{id}
- description: Update order notes and tags
  method: PUT
  name: update-order
  path: /v1/orders/{id}
- description: Cancel an order with a reason
  method: POST
  name: cancel-order
  path: /v1/orders/{id}/cancel
- description: List customers with optional email filtering
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer account
  method: POST
  name: create-customer
  path: /v1/customers
- description: Retrieve a customer by ID
  method: GET
  name: get-customer
  path: /v1/customers/{id}
- description: Update customer information
  method: PUT
  name: update-customer
  path: /v1/customers/{id}
- description: List inventory levels for items and locations
  method: GET
  name: list-inventory-levels
  path: /v1/inventory-levels
- description: List all store locations
  method: GET
  name: list-locations
  path: /v1/locations
- description: List all webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Subscribe to store events via webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: Retrieve store configuration and settings
  method: GET
  name: get-shop
  path: /v1/shop
personas: []
provider_name: Shopify Admin API
provider_slug: shopify-admin
search_terms:
- list all active webhook subscriptions
- create product
- individual customer management
- update an existing product's details
- list products
- ecommerce
- list customers
- subscribe to store events via webhook
- retrieve a specific order with full line item and shipping details
- list all products with optional status filtering
- list customers with optional email filtering
- commerce
- list all customers with optional email address filtering
- store management
- subscribe to shopify store events by creating a webhook
- customer relationship management
- individual product management
- update an existing customer's profile information
- inventory tracking across locations
- get order
- order cancellation
- update product
- retrieve store configuration and settings
- create a new product in the store
- create a new customer account
- customers
- order management and fulfillment
- admin
- list inventory levels for items and locations
- create webhook
- list all products in the shopify store with optional status filtering
- update customer
- products
- check inventory quantities for products across store locations
- retrieve store settings including currency, timezone, and plan details
- retrieve a specific product by its id
- retrieve an order by id
- event subscription management
- individual order management
- update order
- cancel order
- get customer
- get shop
- list locations
- permanently delete a product from the store
- delete product
- list orders filtered by status, financial status, or fulfillment status
- get product
- update product details
- list all store locations
- list orders
- orders
- inventory
- create a new product with title, description, vendor, and variants
- retrieve a product by id
- store settings and configuration
- product catalog management
- cancel an order with a reason
- retrieve a customer by id
- list all webhook subscriptions
- retrieve a specific customer's profile and order history
- list orders with financial and fulfillment status filtering
- update order notes and tags
- create customer
- update customer information
- cancel an order specifying the reason (customer, fraud, inventory, declined, other)
- store location management
- create a new customer account with email and profile information
- list inventory levels
- list webhooks
- list all fulfillment locations for the store
- remove a product from the store
slug: store-management
source_filename: store-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shopify Admin Store Management\"\n  description: >-\n    Unified workflow capability for comprehensive Shopify store management.\n    Combines product catalog management, customer relationship management,\n    order processing, inventory tracking, and store configuration into a\n    single integrated capability for merchants and app developers.\n  tags:\n    - Commerce\n    - Ecommerce\n    - Admin\n    - Store Management\n    - Products\n    - Orders\n    - Customers\n    - Inventory\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHOPIFY_ACCESS_TOKEN: SHOPIFY_ACCESS_TOKEN\n      SHOPIFY_STORE_NAME: SHOPIFY_STORE_NAME\n\ncapability:\n  consumes:\n    - import: shopify-admin-rest\n      location: ./shared/shopify-admin-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: shopify-store-management-api\n      description: \"Unified REST API for comprehensive\
  \ Shopify store management.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: Product catalog management\n          operations:\n            - method: GET\n              name: list-products\n              description: List all products with optional status filtering\n              call: \"shopify-admin-rest.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: Create a new product in the store\n              call: \"shopify-admin-rest.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{id}\n          name: product-detail\n          description: Individual product management\n          operations:\n            - method: GET\n              name: get-product\n              description: Retrieve\
  \ a product by ID\n              call: \"shopify-admin-rest.get-product\"\n              with:\n                product_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-product\n              description: Update product details\n              call: \"shopify-admin-rest.update-product\"\n              with:\n                product_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-product\n              description: Remove a product from the store\n              call: \"shopify-admin-rest.delete-product\"\n              with:\n                product_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: Order\
  \ management and fulfillment\n          operations:\n            - method: GET\n              name: list-orders\n              description: List orders with financial and fulfillment status filtering\n              call: \"shopify-admin-rest.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{id}\n          name: order-detail\n          description: Individual order management\n          operations:\n            - method: GET\n              name: get-order\n              description: Retrieve an order by ID\n              call: \"shopify-admin-rest.get-order\"\n              with:\n                order_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-order\n              description: Update order notes and tags\n              call: \"shopify-admin-rest.update-order\"\n      \
  \        with:\n                order_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{id}/cancel\n          name: order-cancel\n          description: Order cancellation\n          operations:\n            - method: POST\n              name: cancel-order\n              description: Cancel an order with a reason\n              call: \"shopify-admin-rest.cancel-order\"\n              with:\n                order_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: Customer relationship management\n          operations:\n            - method: GET\n              name: list-customers\n              description: List customers with optional email filtering\n              call: \"shopify-admin-rest.list-customers\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: Create a new customer account\n              call: \"shopify-admin-rest.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{id}\n          name: customer-detail\n          description: Individual customer management\n          operations:\n            - method: GET\n              name: get-customer\n              description: Retrieve a customer by ID\n              call: \"shopify-admin-rest.get-customer\"\n              with:\n                customer_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-customer\n              description: Update customer information\n              call: \"shopify-admin-rest.update-customer\"\
  \n              with:\n                customer_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory-levels\n          name: inventory\n          description: Inventory tracking across locations\n          operations:\n            - method: GET\n              name: list-inventory-levels\n              description: List inventory levels for items and locations\n              call: \"shopify-admin-rest.list-inventory-levels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations\n          name: locations\n          description: Store location management\n          operations:\n            - method: GET\n              name: list-locations\n              description: List all store locations\n              call: \"shopify-admin-rest.list-locations\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: Event subscription management\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: List all webhook subscriptions\n              call: \"shopify-admin-rest.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: Subscribe to store events via webhook\n              call: \"shopify-admin-rest.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shop\n          name: shop\n          description: Store settings and configuration\n          operations:\n            - method: GET\n              name: get-shop\n              description: Retrieve store configuration and settings\n            \
  \  call: \"shopify-admin-rest.get-shop\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shopify-store-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Shopify store management.\"\n      tools:\n        - name: list-products\n          description: List all products in the Shopify store with optional status filtering\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: Retrieve a specific product by its ID\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.get-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: create-product\n          description: Create a new product with title, description, vendor, and variants\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopify-admin-rest.create-product\"\n          with:\n            title: \"tools.title\"\n            body_html: \"tools.body_html\"\n            vendor: \"tools.vendor\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-product\n          description: Update an existing product's details\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"shopify-admin-rest.update-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-product\n          description:\
  \ Permanently delete a product from the store\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"shopify-admin-rest.delete-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: List orders filtered by status, financial status, or fulfillment status\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: Retrieve a specific order with full line item and shipping details\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.get-order\"\n          with:\n            order_id: \"tools.order_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-order\n          description: Update order notes and tags\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"shopify-admin-rest.update-order\"\n          with:\n            order_id: \"tools.order_id\"\n            note: \"tools.note\"\n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-order\n          description: Cancel an order specifying the reason (customer, fraud, inventory, declined, other)\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"shopify-admin-rest.cancel-order\"\n          with:\n            order_id: \"tools.order_id\"\n            reason: \"tools.reason\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n\
  \          description: List all customers with optional email address filtering\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: Retrieve a specific customer's profile and order history\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.get-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: Create a new customer account with email and profile information\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopify-admin-rest.create-customer\"\n          with:\n            email: \"tools.email\"\
  \n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-customer\n          description: Update an existing customer's profile information\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"shopify-admin-rest.update-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inventory-levels\n          description: Check inventory quantities for products across store locations\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-inventory-levels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-locations\n          description: List all fulfillment\
  \ locations for the store\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-shop\n          description: Retrieve store settings including currency, timezone, and plan details\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.get-shop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: List all active webhook subscriptions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-admin-rest.list-webhooks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: Subscribe to Shopify store events by creating a webhook\n\
  \          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopify-admin-rest.create-webhook\"\n          with:\n            topic: \"tools.topic\"\n            address: \"tools.address\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shopify-admin/refs/heads/main/capabilities/store-management.yaml
tags:
- Commerce
- Ecommerce
- Admin
- Store Management
- Products
- Orders
- Customers
- Inventory
tools:
- description: List all products in the Shopify store with optional status filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Retrieve a specific product by its ID
  hints:
    openWorld: true
    readOnly: true
  name: get-product
- description: Create a new product with title, description, vendor, and variants
  hints:
    destructive: false
    readOnly: false
  name: create-product
- description: Update an existing product's details
  hints:
    idempotent: true
    readOnly: false
  name: update-product
- description: Permanently delete a product from the store
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-product
- description: List orders filtered by status, financial status, or fulfillment status
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Retrieve a specific order with full line item and shipping details
  hints:
    openWorld: true
    readOnly: true
  name: get-order
- description: Update order notes and tags
  hints:
    idempotent: true
    readOnly: false
  name: update-order
- description: Cancel an order specifying the reason (customer, fraud, inventory, declined, other)
  hints:
    destructive: true
    readOnly: false
  name: cancel-order
- description: List all customers with optional email address filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Retrieve a specific customer's profile and order history
  hints:
    openWorld: true
    readOnly: true
  name: get-customer
- description: Create a new customer account with email and profile information
  hints:
    destructive: false
    readOnly: false
  name: create-customer
- description: Update an existing customer's profile information
  hints:
    idempotent: true
    readOnly: false
  name: update-customer
- description: Check inventory quantities for products across store locations
  hints:
    openWorld: true
    readOnly: true
  name: list-inventory-levels
- description: List all fulfillment locations for the store
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: Retrieve store settings including currency, timezone, and plan details
  hints:
    openWorld: true
    readOnly: true
  name: get-shop
- description: List all active webhook subscriptions
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: Subscribe to Shopify store events by creating a webhook
  hints:
    destructive: false
    readOnly: false
  name: create-webhook
---
