---
categories: []
consumed_apis: []
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
- update an existing product's details
- retrieve a product by id
- customer relationship management
- subscribe to store events via webhook
- retrieve store settings including currency, timezone, and plan details
- list all products in the shopify store with optional status filtering
- subscribe to shopify store events by creating a webhook
- create a new customer account with email and profile information
- update order notes and tags
- product catalog management
- list all webhook subscriptions
- get customer
- list all products with optional status filtering
- cancel an order specifying the reason (customer, fraud, inventory, declined, other)
- list all fulfillment locations for the store
- create a new product in the store
- order management and fulfillment
- get order
- create a new product with title, description, vendor, and variants
- retrieve an order by id
- store settings and configuration
- get product
- retrieve store configuration and settings
- delete product
- cancel order
- create webhook
- list locations
- list all store locations
- list orders with financial and fulfillment status filtering
- list inventory levels for items and locations
- get shop
- commerce
- list all active webhook subscriptions
- order cancellation
- update product details
- inventory
- list orders filtered by status, financial status, or fulfillment status
- list customers with optional email filtering
- inventory tracking across locations
- list all customers with optional email address filtering
- retrieve a customer by id
- cancel an order with a reason
- ecommerce
- individual customer management
- store management
- list inventory levels
- create customer
- individual order management
- permanently delete a product from the store
- check inventory quantities for products across store locations
- admin
- update order
- remove a product from the store
- update customer information
- list orders
- list customers
- retrieve a specific customer's profile and order history
- create a new customer account
- store location management
- list products
- customers
- retrieve a specific order with full line item and shipping details
- products
- orders
- create product
- individual product management
- retrieve a specific product by its id
- list webhooks
- update an existing customer's profile information
- event subscription management
- update customer
- update product
slug: store-management
source_filename: store-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shopify Admin Store Management\n  description: Unified workflow capability for comprehensive Shopify store management. Combines product catalog management,\n    customer relationship management, order processing, inventory tracking, and store configuration into a single integrated\n    capability for merchants and app developers.\n  tags:\n  - Commerce\n  - Ecommerce\n  - Admin\n  - Store Management\n  - Products\n  - Orders\n  - Customers\n  - Inventory\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHOPIFY_ACCESS_TOKEN: SHOPIFY_ACCESS_TOKEN\n    SHOPIFY_STORE_NAME: SHOPIFY_STORE_NAME\ncapability:\n  consumes:\n  - type: http\n    namespace: shopify-admin-rest\n    baseUri: https://{{env.SHOPIFY_STORE_NAME}}.myshopify.com/admin/api/2024-10\n    description: Shopify Admin REST API for store management\n    authentication:\n      type: apikey\n      key: X-Shopify-Access-Token\n      value: '{{env.SHOPIFY_ACCESS_TOKEN}}'\n\
  \      placement: header\n    resources:\n    - name: products\n      path: /products.json\n      description: Manage Shopify store products\n      operations:\n      - name: list-products\n        method: GET\n        description: Retrieve a list of products\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (max 250)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by product status (active, archived, draft)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            product:\n              title: '{{tools.title}}'\n              body_html: '{{tools.body_html}}'\n              vendor: '{{tools.vendor}}'\n              status: '{{tools.status}}'\n    - name: product-detail\n      path: /products/{product_id}.json\n      description: Manage a specific Shopify product\n      operations:\n      - name: get-product\n        method: GET\n        description: Retrieve a specific product by ID\n        inputParameters:\n        - name: product_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an existing product\n        inputParameters:\n        - name: product_id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ The ID of the product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product:\n              title: '{{tools.title}}'\n              status: '{{tools.status}}'\n      - name: delete-product\n        method: DELETE\n        description: Delete a product\n        inputParameters:\n        - name: product_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the product to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers.json\n      description: Manage Shopify store customers\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve a list of customers\n        inputParameters:\n        - name: limit\n          in: query\n\
  \          type: integer\n          required: false\n          description: Maximum number of results\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter by email address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer:\n              email: '{{tools.email}}'\n              first_name: '{{tools.first_name}}'\n              last_name: '{{tools.last_name}}'\n    - name: customer-detail\n      path: /customers/{customer_id}.json\n      description: Manage a specific customer\n      operations:\n      - name: get-customer\n        method: GET\n\
  \        description: Retrieve a specific customer by ID\n        inputParameters:\n        - name: customer_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PUT\n        description: Update a customer\n        inputParameters:\n        - name: customer_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer:\n              first_name: '{{tools.first_name}}'\n              last_name: '{{tools.last_name}}'\n              email: '{{tools.email}}'\n    - name: orders\n      path: /orders.json\n\
  \      description: Manage Shopify store orders\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieve a list of orders\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status (open, closed, cancelled, any)\n        - name: financial_status\n          in: query\n          type: string\n          required: false\n          description: Filter by financial status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-detail\n      path: /orders/{order_id}.json\n      description: Manage a specific order\n      operations:\n      - name: get-order\n        method: GET\n        description: Retrieve a specific\
  \ order by ID\n        inputParameters:\n        - name: order_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-order\n        method: PUT\n        description: Update an order\n        inputParameters:\n        - name: order_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            order:\n              note: '{{tools.note}}'\n              tags: '{{tools.tags}}'\n    - name: order-cancel\n      path: /orders/{order_id}/cancel.json\n      description: Cancel an order\n      operations:\n      - name: cancel-order\n      \
  \  method: POST\n        description: Cancel a specific order\n        inputParameters:\n        - name: order_id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the order to cancel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reason: '{{tools.reason}}'\n    - name: inventory-levels\n      path: /inventory_levels.json\n      description: Manage product inventory levels\n      operations:\n      - name: list-inventory-levels\n        method: GET\n        description: Retrieve inventory levels for items or locations\n        inputParameters:\n        - name: inventory_item_ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated inventory item IDs\n        - name: location_ids\n          in: query\n          type: string\n    \
  \      required: false\n          description: Comma-separated location IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations.json\n      description: List store locations\n      operations:\n      - name: list-locations\n        method: GET\n        description: Retrieve all store locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks.json\n      description: Manage webhook subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: Retrieve all webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook subscription\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            webhook:\n              topic: '{{tools.topic}}'\n              address: '{{tools.address}}'\n              format: '{{tools.format}}'\n    - name: shop\n      path: /shop.json\n      description: Retrieve store configuration\n      operations:\n      - name: get-shop\n        method: GET\n        description: Retrieve store settings and configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shopify-store-management-api\n    description: Unified REST API for comprehensive Shopify store management.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Product catalog management\n      operations:\n      - method: GET\n    \
  \    name: list-products\n        description: List all products with optional status filtering\n        call: shopify-admin-rest.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Create a new product in the store\n        call: shopify-admin-rest.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{id}\n      name: product-detail\n      description: Individual product management\n      operations:\n      - method: GET\n        name: get-product\n        description: Retrieve a product by ID\n        call: shopify-admin-rest.get-product\n        with:\n          product_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-product\n        description: Update product details\n        call: shopify-admin-rest.update-product\n        with:\n\
  \          product_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-product\n        description: Remove a product from the store\n        call: shopify-admin-rest.delete-product\n        with:\n          product_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order management and fulfillment\n      operations:\n      - method: GET\n        name: list-orders\n        description: List orders with financial and fulfillment status filtering\n        call: shopify-admin-rest.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{id}\n      name: order-detail\n      description: Individual order management\n      operations:\n      - method: GET\n        name: get-order\n        description: Retrieve an order by ID\n        call: shopify-admin-rest.get-order\n\
  \        with:\n          order_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-order\n        description: Update order notes and tags\n        call: shopify-admin-rest.update-order\n        with:\n          order_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{id}/cancel\n      name: order-cancel\n      description: Order cancellation\n      operations:\n      - method: POST\n        name: cancel-order\n        description: Cancel an order with a reason\n        call: shopify-admin-rest.cancel-order\n        with:\n          order_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer relationship management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List customers with optional email filtering\n\
  \        call: shopify-admin-rest.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer account\n        call: shopify-admin-rest.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{id}\n      name: customer-detail\n      description: Individual customer management\n      operations:\n      - method: GET\n        name: get-customer\n        description: Retrieve a customer by ID\n        call: shopify-admin-rest.get-customer\n        with:\n          customer_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-customer\n        description: Update customer information\n        call: shopify-admin-rest.update-customer\n        with:\n          customer_id: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/inventory-levels\n      name: inventory\n      description: Inventory tracking across locations\n      operations:\n      - method: GET\n        name: list-inventory-levels\n        description: List inventory levels for items and locations\n        call: shopify-admin-rest.list-inventory-levels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Store location management\n      operations:\n      - method: GET\n        name: list-locations\n        description: List all store locations\n        call: shopify-admin-rest.list-locations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Event subscription management\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List all webhook subscriptions\n        call: shopify-admin-rest.list-webhooks\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Subscribe to store events via webhook\n        call: shopify-admin-rest.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shop\n      name: shop\n      description: Store settings and configuration\n      operations:\n      - method: GET\n        name: get-shop\n        description: Retrieve store configuration and settings\n        call: shopify-admin-rest.get-shop\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shopify-store-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Shopify store management.\n    tools:\n    - name: list-products\n      description: List all products in the Shopify store with optional status filtering\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: shopify-admin-rest.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Retrieve a specific product by its ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.get-product\n      with:\n        product_id: tools.product_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Create a new product with title, description, vendor, and variants\n      hints:\n        readOnly: false\n        destructive: false\n      call: shopify-admin-rest.create-product\n      with:\n        title: tools.title\n        body_html: tools.body_html\n        vendor: tools.vendor\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-product\n      description: Update an existing product's details\n      hints:\n        readOnly: false\n        idempotent:\
  \ true\n      call: shopify-admin-rest.update-product\n      with:\n        product_id: tools.product_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-product\n      description: Permanently delete a product from the store\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: shopify-admin-rest.delete-product\n      with:\n        product_id: tools.product_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List orders filtered by status, financial status, or fulfillment status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Retrieve a specific order with full line item and shipping details\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ shopify-admin-rest.get-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-order\n      description: Update order notes and tags\n      hints:\n        readOnly: false\n        idempotent: true\n      call: shopify-admin-rest.update-order\n      with:\n        order_id: tools.order_id\n        note: tools.note\n        tags: tools.tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n      description: Cancel an order specifying the reason (customer, fraud, inventory, declined, other)\n      hints:\n        readOnly: false\n        destructive: true\n      call: shopify-admin-rest.cancel-order\n      with:\n        order_id: tools.order_id\n        reason: tools.reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List all customers with optional email address filtering\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Retrieve a specific customer's profile and order history\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.get-customer\n      with:\n        customer_id: tools.customer_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer account with email and profile information\n      hints:\n        readOnly: false\n        destructive: false\n      call: shopify-admin-rest.create-customer\n      with:\n        email: tools.email\n        first_name: tools.first_name\n        last_name: tools.last_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-customer\n      description: Update an existing customer's profile information\n\
  \      hints:\n        readOnly: false\n        idempotent: true\n      call: shopify-admin-rest.update-customer\n      with:\n        customer_id: tools.customer_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inventory-levels\n      description: Check inventory quantities for products across store locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.list-inventory-levels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-locations\n      description: List all fulfillment locations for the store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.list-locations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shop\n      description: Retrieve store settings including currency, timezone, and plan details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.get-shop\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List all active webhook subscriptions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-admin-rest.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Subscribe to Shopify store events by creating a webhook\n      hints:\n        readOnly: false\n        destructive: false\n      call: shopify-admin-rest.create-webhook\n      with:\n        topic: tools.topic\n        address: tools.address\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
