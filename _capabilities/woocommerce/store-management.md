---
categories: []
consumed_apis: []
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
- designing headless commerce architecture with woocommerce apis
- browse the public woocommerce storefront product catalog.
- operations
- full product catalog management.
- get detailed information about a specific woocommerce product.
- list woocommerce customers, optionally searching by name or email.
- create order
- update order status
- get product
- list woocommerce discount coupons.
- building custom storefronts using woocommerce as a headless backend
- create product
- list products
- browse products
- list woocommerce products with optional filtering by status, category, or keyword.
- create a new product.
- orders
- Operations Manager
- Frontend Developer
- ecommerce
- open source
- create a new order.
- get complete details of a specific woocommerce order including items and billing.
- get woocommerce sales analytics for a time period.
- browse storefront products
- sales reports and analytics.
- update product
- products
- get sales report for a period.
- complete store management combining rest api and store api
- list customers.
- list orders
- customer management.
- processing orders, managing fulfillment, and reviewing sales analytics
- update the status of a woocommerce order (e.g., processing, completed, refunded).
- Store Administrator
- browse storefront products.
- woocommerce
- get customer
- get a specific customer's profile and order history.
- get sales report
- list woocommerce orders filtered by status, customer, or date range.
- list orders with filtering by status and customer.
- Headless Architect
- list customers
- store management
- wordpress
- list coupons
- order lifecycle management.
- managing product catalog, orders, customers, and store configuration
- create a new woocommerce product with pricing and inventory details.
- list all products with filtering.
- public storefront product browsing.
- headless storefront capability with public store api and admin rest api
- get order
- update a woocommerce product's details, pricing, or status.
slug: store-management
source_filename: store-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WooCommerce Store Management\n  description: Unified store management capability combining the WooCommerce REST API and Store API for complete eCommerce\n    operations. Used by store administrators and operations teams to manage products, process orders, manage customers, and\n    run sales reports. Combines backend admin operations with frontend storefront browsing.\n  tags:\n  - eCommerce\n  - Operations\n  - Orders\n  - Products\n  - Store Management\n  - WooCommerce\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WOOCOMMERCE_CONSUMER_KEY: WOOCOMMERCE_CONSUMER_KEY\n    WOOCOMMERCE_CONSUMER_SECRET: WOOCOMMERCE_CONSUMER_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: woo-rest\n    baseUri: https://example.com/wp-json/wc/v3\n    description: WooCommerce REST API v3 for complete store management.\n    authentication:\n      type: basic\n      username: '{{WOOCOMMERCE_CONSUMER_KEY}}'\n\
  \      password: '{{WOOCOMMERCE_CONSUMER_SECRET}}'\n    resources:\n    - name: products\n      path: /products\n      description: Manage WooCommerce products.\n      operations:\n      - name: list-products\n        method: GET\n        description: List all products with optional filtering and pagination.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by product status.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by product category ID.\n        - name: search\n          in: query\n          type: string\n          required: false\n\
  \          description: Search term.\n        outputRawFormat: json\n        outputParameters:\n        - name: products\n          type: array\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new WooCommerce product.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            status: '{{tools.status}}'\n            regular_price: '{{tools.regular_price}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get a single product by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type:\
  \ object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an existing product.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        body:\n          type: json\n          data:\n            regular_price: '{{tools.regular_price}}'\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n      - name: delete-product\n        method: DELETE\n        description: Delete a product.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Manage\
  \ WooCommerce orders.\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all orders with optional filtering.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status.\n        - name: customer\n          in: query\n          type: integer\n          required: false\n          description: Filter by customer ID.\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Filter orders after date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: orders\n          type: array\n\
  \          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            payment_method: '{{tools.payment_method}}'\n            billing: '{{tools.billing}}'\n            line_items: '{{tools.line_items}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get a single order by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Order ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n      - name: update-order\n        method: PUT\n        description: Update an order status or data.\n        inputParameters:\n        - name: id\n          in:\
  \ path\n          type: integer\n          required: true\n          description: Order ID.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      description: Manage WooCommerce customers.\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all customers.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by email or name.\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: customers\n          type: array\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Get a single customer by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Customer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: customer\n          type: object\n          value: $.\n    - name: coupons\n      path: /coupons\n      description: Manage WooCommerce discount coupons.\n      operations:\n      - name: list-coupons\n        method: GET\n        description: List all coupons.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by coupon code.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: coupons\n          type: array\n          value: $.\n      - name: create-coupon\n        method: POST\n        description: Create a new discount coupon.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            code: '{{tools.code}}'\n            discount_type: '{{tools.discount_type}}'\n            amount: '{{tools.amount}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: coupon\n          type: object\n          value: $.\n    - name: reports\n      path: /reports/sales\n      description: Retrieve WooCommerce sales reports.\n      operations:\n      - name: get-sales-report\n        method: GET\n        description: Get sales report summary for a date range.\n        inputParameters:\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: 'Report period: week, month, last_month, year.'\n        - name: date_min\n\
  \          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601).\n        - name: date_max\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: report\n          type: object\n          value: $.\n  - type: http\n    namespace: woo-store\n    baseUri: https://example.com/wp-json/wc/store/v1\n    description: WooCommerce Store API v1 for public storefront operations.\n    resources:\n    - name: products\n      path: /products\n      description: Browse the public product catalog.\n      operations:\n      - name: list-store-products\n        method: GET\n        description: List published products available for purchase.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n\
  \          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category slug.\n        - name: on_sale\n          in: query\n          type: boolean\n          required: false\n          description: Return only on-sale products.\n        outputRawFormat: json\n        outputParameters:\n        - name: products\n          type: array\n          value: $.\n      - name: get-store-product\n        method: GET\n        description: Get a single product by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ product\n          type: object\n          value: $.\n    - name: cart\n      path: /cart\n      description: Manage the current shopper's cart.\n      operations:\n      - name: get-cart\n        method: GET\n        description: Get the current shopper's cart contents.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: cart\n          type: object\n          value: $.\n      - name: add-to-cart\n        method: POST\n        description: Add an item to the cart.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            id: '{{tools.product_id}}'\n            quantity: '{{tools.quantity}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: cart_item\n          type: object\n          value: $.\n      - name: remove-cart-item\n        method: DELETE\n        description: Remove an item from the cart.\n        inputParameters:\n        - name: key\n          in: path\n  \
  \        type: string\n          required: true\n          description: Cart item key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout\n      path: /checkout\n      description: Submit the checkout and place an order.\n      operations:\n      - name: submit-checkout\n        method: POST\n        description: Submit checkout details and place an order.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            payment_method: '{{tools.payment_method}}'\n            billing_address: '{{tools.billing_address}}'\n            shipping_address: '{{tools.shipping_address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n    - name: categories\n      path: /products/categories\n      description: Browse product categories.\n      operations:\n      - name: list-categories\n   \
  \     method: GET\n        description: List all product categories.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: categories\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: woo-management-api\n    description: Unified REST API for complete WooCommerce store management.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Full product catalog management.\n      operations:\n      - method: GET\n        name: list-products\n        description: List all products with filtering.\n        call: woo-rest.list-products\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          status: rest.status\n          search: rest.search\n        outputParameters:\n        - type: array\n          mapping:\
  \ $.\n      - method: POST\n        name: create-product\n        description: Create a new product.\n        call: woo-rest.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order lifecycle management.\n      operations:\n      - method: GET\n        name: list-orders\n        description: List orders with filtering by status and customer.\n        call: woo-rest.list-orders\n        with:\n          page: rest.page\n          status: rest.status\n          customer: rest.customer\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new order.\n        call: woo-rest.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer management.\n      operations:\n      - method: GET\n \
  \       name: list-customers\n        description: List customers.\n        call: woo-rest.list-customers\n        with:\n          search: rest.search\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/storefront/products\n      name: storefront-products\n      description: Public storefront product browsing.\n      operations:\n      - method: GET\n        name: browse-products\n        description: Browse storefront products.\n        call: woo-store.list-store-products\n        with:\n          search: rest.search\n          category: rest.category\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/reports/sales\n      name: reports\n      description: Sales reports and analytics.\n      operations:\n      - method: GET\n        name: get-sales-report\n        description: Get sales report for a period.\n        call: woo-rest.get-sales-report\n        with:\n          period: rest.period\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: woo-management-mcp\n    transport: http\n    description: MCP server for AI-assisted WooCommerce store management.\n    tools:\n    - name: list-products\n      description: List WooCommerce products with optional filtering by status, category, or keyword.\n      hints:\n        readOnly: true\n      call: woo-rest.list-products\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        status: tools.status\n        search: tools.search\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-product\n      description: Get detailed information about a specific WooCommerce product.\n      hints:\n        readOnly: true\n      call: woo-rest.get-product\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Create a new WooCommerce product with pricing\
  \ and inventory details.\n      hints:\n        readOnly: false\n      call: woo-rest.create-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-product\n      description: Update a WooCommerce product's details, pricing, or status.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: woo-rest.update-product\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List WooCommerce orders filtered by status, customer, or date range.\n      hints:\n        readOnly: true\n      call: woo-rest.list-orders\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        status: tools.status\n        customer: tools.customer\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-order\n      description: Get complete details of a specific WooCommerce order including items and billing.\n \
  \     hints:\n        readOnly: true\n      call: woo-rest.get-order\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-order-status\n      description: Update the status of a WooCommerce order (e.g., processing, completed, refunded).\n      hints:\n        readOnly: false\n        idempotent: true\n      call: woo-rest.update-order\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List WooCommerce customers, optionally searching by name or email.\n      hints:\n        readOnly: true\n      call: woo-rest.list-customers\n      with:\n        search: tools.search\n        page: tools.page\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-customer\n      description: Get a specific customer's profile and order history.\n      hints:\n        readOnly: true\n      call: woo-rest.get-customer\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-report\n      description: Get WooCommerce sales analytics for a time period.\n      hints:\n        readOnly: true\n      call: woo-rest.get-sales-report\n      with:\n        period: tools.period\n        date_min: tools.date_min\n        date_max: tools.date_max\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-storefront-products\n      description: Browse the public WooCommerce storefront product catalog.\n      hints:\n        readOnly: true\n      call: woo-store.list-store-products\n      with:\n        search: tools.search\n        category: tools.category\n        on_sale: tools.on_sale\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-coupons\n      description: List WooCommerce discount coupons.\n      hints:\n        readOnly: true\n      call: woo-rest.list-coupons\n      with:\n\
  \        search: tools.search\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
