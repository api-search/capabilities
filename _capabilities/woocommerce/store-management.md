---
categories: []
consumed_apis:
- woo-rest
- woo-store
description: Unified store management capability combining the WooCommerce REST API and Store API for complete eCommerce operations. Used by store administrators and operations teams to manage products, process orders, manage customers, and run sales reports. Combines backend admin operations with frontend storefront browsing.
layout: capability
name: WooCommerce Store Management
operations:
- description: List all products with filtering.
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product.
  method: POST
  name: create-product
  path: /v1/products
- description: List orders with filtering by status and customer.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order.
  method: POST
  name: create-order
  path: /v1/orders
- description: List customers.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Browse storefront products.
  method: GET
  name: browse-products
  path: /v1/storefront/products
- description: Get sales report for a period.
  method: GET
  name: get-sales-report
  path: /v1/reports/sales
personas: []
provider_name: WooCommerce
provider_slug: woocommerce
search_terms:
- get woocommerce sales analytics for a time period.
- update the status of a woocommerce order (e.g., processing, completed, refunded).
- create product
- full product catalog management.
- store management
- woocommerce
- order lifecycle management.
- list coupons
- list customers.
- list woocommerce products with optional filtering by status, category, or keyword.
- browse the public woocommerce storefront product catalog.
- create order
- browse products
- open source
- orders
- get sales report
- Operations Manager
- operations
- Store Administrator
- building custom storefronts using woocommerce as a headless backend
- browse storefront products
- list woocommerce orders filtered by status, customer, or date range.
- Headless Architect
- list woocommerce discount coupons.
- products
- wordpress
- public storefront product browsing.
- customer management.
- browse storefront products.
- get detailed information about a specific woocommerce product.
- create a new product.
- Frontend Developer
- get complete details of a specific woocommerce order including items and billing.
- headless storefront capability with public store api and admin rest api
- get order
- list woocommerce customers, optionally searching by name or email.
- list orders with filtering by status and customer.
- designing headless commerce architecture with woocommerce apis
- list customers
- get sales report for a period.
- create a new order.
- list products
- get a specific customer's profile and order history.
- get customer
- ecommerce
- get product
- update order status
- update a woocommerce product's details, pricing, or status.
- list orders
- complete store management combining rest api and store api
- list all products with filtering.
- create a new woocommerce product with pricing and inventory details.
- managing product catalog, orders, customers, and store configuration
- processing orders, managing fulfillment, and reviewing sales analytics
- update product
- sales reports and analytics.
slug: store-management
source_filename: store-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WooCommerce Store Management\"\n  description: >-\n    Unified store management capability combining the WooCommerce REST API and Store API\n    for complete eCommerce operations. Used by store administrators and operations teams\n    to manage products, process orders, manage customers, and run sales reports.\n    Combines backend admin operations with frontend storefront browsing.\n  tags:\n    - eCommerce\n    - Operations\n    - Orders\n    - Products\n    - Store Management\n    - WooCommerce\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WOOCOMMERCE_CONSUMER_KEY: WOOCOMMERCE_CONSUMER_KEY\n      WOOCOMMERCE_CONSUMER_SECRET: WOOCOMMERCE_CONSUMER_SECRET\n\ncapability:\n  consumes:\n    - import: woo-rest\n      location: ./shared/rest-api.yaml\n    - import: woo-store\n      location: ./shared/store-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ woo-management-api\n      description: \"Unified REST API for complete WooCommerce store management.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Full product catalog management.\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List all products with filtering.\"\n              call: \"woo-rest.list-products\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                status: \"rest.status\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new product.\"\n              call: \"woo-rest.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n      \
  \  - path: /v1/orders\n          name: orders\n          description: \"Order lifecycle management.\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders with filtering by status and customer.\"\n              call: \"woo-rest.list-orders\"\n              with:\n                page: \"rest.page\"\n                status: \"rest.status\"\n                customer: \"rest.customer\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new order.\"\n              call: \"woo-rest.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers\n          name: customers\n          description: \"Customer management.\"\n          operations:\n            - method: GET\n              name: list-customers\n\
  \              description: \"List customers.\"\n              call: \"woo-rest.list-customers\"\n              with:\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/storefront/products\n          name: storefront-products\n          description: \"Public storefront product browsing.\"\n          operations:\n            - method: GET\n              name: browse-products\n              description: \"Browse storefront products.\"\n              call: \"woo-store.list-store-products\"\n              with:\n                search: \"rest.search\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/reports/sales\n          name: reports\n          description: \"Sales reports and analytics.\"\n          operations:\n            - method: GET\n              name:\
  \ get-sales-report\n              description: \"Get sales report for a period.\"\n              call: \"woo-rest.get-sales-report\"\n              with:\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: woo-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WooCommerce store management.\"\n      tools:\n        - name: list-products\n          description: \"List WooCommerce products with optional filtering by status, category, or keyword.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.list-products\"\n          with:\n            page: \"tools.page\"\n            per_page: \"tools.per_page\"\n            status: \"tools.status\"\n            search: \"tools.search\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-product\n\
  \          description: \"Get detailed information about a specific WooCommerce product.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.get-product\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-product\n          description: \"Create a new WooCommerce product with pricing and inventory details.\"\n          hints:\n            readOnly: false\n          call: \"woo-rest.create-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-product\n          description: \"Update a WooCommerce product's details, pricing, or status.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"woo-rest.update-product\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: list-orders\n          description: \"List WooCommerce orders filtered by status, customer, or date range.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.list-orders\"\n          with:\n            page: \"tools.page\"\n            per_page: \"tools.per_page\"\n            status: \"tools.status\"\n            customer: \"tools.customer\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-order\n          description: \"Get complete details of a specific WooCommerce order including items and billing.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.get-order\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-order-status\n          description: \"Update the status of a WooCommerce order (e.g., processing, completed, refunded).\"\n        \
  \  hints:\n            readOnly: false\n            idempotent: true\n          call: \"woo-rest.update-order\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-customers\n          description: \"List WooCommerce customers, optionally searching by name or email.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.list-customers\"\n          with:\n            search: \"tools.search\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-customer\n          description: \"Get a specific customer's profile and order history.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.get-customer\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sales-report\n\
  \          description: \"Get WooCommerce sales analytics for a time period.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.get-sales-report\"\n          with:\n            period: \"tools.period\"\n            date_min: \"tools.date_min\"\n            date_max: \"tools.date_max\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: browse-storefront-products\n          description: \"Browse the public WooCommerce storefront product catalog.\"\n          hints:\n            readOnly: true\n          call: \"woo-store.list-store-products\"\n          with:\n            search: \"tools.search\"\n            category: \"tools.category\"\n            on_sale: \"tools.on_sale\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-coupons\n          description: \"List WooCommerce discount coupons.\"\n          hints:\n            readOnly: true\n     \
  \     call: \"woo-rest.list-coupons\"\n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/woocommerce/refs/heads/main/capabilities/store-management.yaml
tags:
- eCommerce
- Operations
- Orders
- Products
- Store Management
- WooCommerce
tools:
- description: List WooCommerce products with optional filtering by status, category, or keyword.
  hints:
    readOnly: true
  name: list-products
- description: Get detailed information about a specific WooCommerce product.
  hints:
    readOnly: true
  name: get-product
- description: Create a new WooCommerce product with pricing and inventory details.
  hints:
    readOnly: false
  name: create-product
- description: Update a WooCommerce product's details, pricing, or status.
  hints:
    idempotent: true
    readOnly: false
  name: update-product
- description: List WooCommerce orders filtered by status, customer, or date range.
  hints:
    readOnly: true
  name: list-orders
- description: Get complete details of a specific WooCommerce order including items and billing.
  hints:
    readOnly: true
  name: get-order
- description: Update the status of a WooCommerce order (e.g., processing, completed, refunded).
  hints:
    idempotent: true
    readOnly: false
  name: update-order-status
- description: List WooCommerce customers, optionally searching by name or email.
  hints:
    readOnly: true
  name: list-customers
- description: Get a specific customer's profile and order history.
  hints:
    readOnly: true
  name: get-customer
- description: Get WooCommerce sales analytics for a time period.
  hints:
    readOnly: true
  name: get-sales-report
- description: Browse the public WooCommerce storefront product catalog.
  hints:
    readOnly: true
  name: browse-storefront-products
- description: List WooCommerce discount coupons.
  hints:
    readOnly: true
  name: list-coupons
---
