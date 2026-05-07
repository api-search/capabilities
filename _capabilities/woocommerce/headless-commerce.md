---
categories: []
consumed_apis: []
description: Headless commerce capability combining the public WooCommerce Store API with authenticated REST API operations for building custom frontends. Used by frontend developers and headless architects building React, Vue, or custom storefronts with Woo as the commerce backend.
layout: capability
name: WooCommerce Headless Commerce
operations:
- description: Browse the public product catalog.
  method: GET
  name: browse-products
  path: /v1/catalog/products
- description: List product categories.
  method: GET
  name: list-categories
  path: /v1/catalog/categories
- description: View current cart.
  method: GET
  name: view-cart
  path: /v1/cart
- description: Add product to cart.
  method: POST
  name: add-to-cart
  path: /v1/cart
- description: Submit checkout and place order.
  method: POST
  name: submit-checkout
  path: /v1/checkout
- description: List all products including drafts.
  method: GET
  name: list-products-admin
  path: /v1/products
personas: []
provider_name: WooCommerce
provider_slug: woocommerce
search_terms:
- shopper cart management.
- designing headless commerce architecture with woocommerce apis
- add product to cart.
- product catalog management (admin).
- building custom storefronts using woocommerce as a headless backend
- browse products
- cart
- checkout
- add to cart
- orders
- Operations Manager
- Frontend Developer
- ecommerce
- view current cart
- remove an item from the shopper's cart.
- browse catalog
- open source
- list categories
- list products admin
- products
- remove from cart
- complete store management combining rest api and store api
- get full product details for storefront product page rendering.
- list all products admin
- processing orders, managing fulfillment, and reviewing sales analytics
- Store Administrator
- list categories for nav
- submit checkout
- woocommerce
- view the current shopper's cart for display in the cart drawer/page.
- public product catalog for the storefront.
- view current cart.
- list all products including drafts for admin/build-time rendering.
- get product for display
- product categories for navigation.
- Headless Architect
- wordpress
- checkout process.
- submit checkout and place order.
- add a product to the shopper's cart during product browsing.
- add item to cart
- list all products including drafts.
- browse the public woocommerce product catalog for storefront display.
- place order
- managing product catalog, orders, customers, and store configuration
- headless
- list product categories.
- view cart
- frontend
- headless storefront capability with public store api and admin rest api
- submit checkout details and place a woocommerce order.
- browse the public product catalog.
- list product categories for building storefront navigation menus.
slug: headless-commerce
source_filename: headless-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WooCommerce Headless Commerce\n  description: Headless commerce capability combining the public WooCommerce Store API with authenticated REST API operations\n    for building custom frontends. Used by frontend developers and headless architects building React, Vue, or custom storefronts\n    with Woo as the commerce backend.\n  tags:\n  - Cart\n  - Checkout\n  - eCommerce\n  - Frontend\n  - Headless\n  - WooCommerce\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WOOCOMMERCE_CONSUMER_KEY: WOOCOMMERCE_CONSUMER_KEY\n    WOOCOMMERCE_CONSUMER_SECRET: WOOCOMMERCE_CONSUMER_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: woo-store\n    baseUri: https://example.com/wp-json/wc/store/v1\n    description: WooCommerce Store API v1 for public storefront operations.\n    resources:\n    - name: products\n      path: /products\n      description: Browse the public product catalog.\n      operations:\n\
  \      - name: list-store-products\n        method: GET\n        description: List published products available for purchase.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category slug.\n        - name: on_sale\n          in: query\n          type: boolean\n          required: false\n          description: Return only on-sale products.\n        outputRawFormat: json\n        outputParameters:\n        - name: products\n          type: array\n          value: $.\n      - name: get-store-product\n\
  \        method: GET\n        description: Get a single product by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n    - name: cart\n      path: /cart\n      description: Manage the current shopper's cart.\n      operations:\n      - name: get-cart\n        method: GET\n        description: Get the current shopper's cart contents.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: cart\n          type: object\n          value: $.\n      - name: add-to-cart\n        method: POST\n        description: Add an item to the cart.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            id: '{{tools.product_id}}'\n            quantity: '{{tools.quantity}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: cart_item\n          type: object\n          value: $.\n      - name: remove-cart-item\n        method: DELETE\n        description: Remove an item from the cart.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Cart item key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout\n      path: /checkout\n      description: Submit the checkout and place an order.\n      operations:\n      - name: submit-checkout\n        method: POST\n        description: Submit checkout details and place an order.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            payment_method: '{{tools.payment_method}}'\n            billing_address: '{{tools.billing_address}}'\n            shipping_address: '{{tools.shipping_address}}'\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n    - name: categories\n      path: /products/categories\n      description: Browse product categories.\n      operations:\n      - name: list-categories\n        method: GET\n        description: List all product categories.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: categories\n          type: array\n          value: $.\n  - type: http\n    namespace: woo-rest\n    baseUri: https://example.com/wp-json/wc/v3\n    description: WooCommerce REST API v3 for complete store management.\n    authentication:\n      type: basic\n      username: '{{WOOCOMMERCE_CONSUMER_KEY}}'\n      password: '{{WOOCOMMERCE_CONSUMER_SECRET}}'\n    resources:\n    - name: products\n      path: /products\n\
  \      description: Manage WooCommerce products.\n      operations:\n      - name: list-products\n        method: GET\n        description: List all products with optional filtering and pagination.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by product status.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by product category ID.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ products\n          type: array\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new WooCommerce product.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            status: '{{tools.status}}'\n            regular_price: '{{tools.regular_price}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get a single product by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an\
  \ existing product.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        body:\n          type: json\n          data:\n            regular_price: '{{tools.regular_price}}'\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n      - name: delete-product\n        method: DELETE\n        description: Delete a product.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Manage WooCommerce orders.\n      operations:\n      - name: list-orders\n        method: GET\n        description:\
  \ List all orders with optional filtering.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status.\n        - name: customer\n          in: query\n          type: integer\n          required: false\n          description: Filter by customer ID.\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Filter orders after date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: orders\n          type: array\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order.\n\
  \        inputParameters: []\n        body:\n          type: json\n          data:\n            payment_method: '{{tools.payment_method}}'\n            billing: '{{tools.billing}}'\n            line_items: '{{tools.line_items}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get a single order by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Order ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n      - name: update-order\n        method: PUT\n        description: Update an order status or data.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Order ID.\n        body:\n   \
  \       type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: order\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      description: Manage WooCommerce customers.\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all customers.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by email or name.\n        outputRawFormat: json\n        outputParameters:\n        - name: customers\n          type: array\n          value: $.\n      - name: get-customer\n\
  \        method: GET\n        description: Get a single customer by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Customer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: customer\n          type: object\n          value: $.\n    - name: coupons\n      path: /coupons\n      description: Manage WooCommerce discount coupons.\n      operations:\n      - name: list-coupons\n        method: GET\n        description: List all coupons.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by coupon code.\n        outputRawFormat: json\n        outputParameters:\n        - name: coupons\n          type: array\n          value: $.\n      -\
  \ name: create-coupon\n        method: POST\n        description: Create a new discount coupon.\n        inputParameters: []\n        body:\n          type: json\n          data:\n            code: '{{tools.code}}'\n            discount_type: '{{tools.discount_type}}'\n            amount: '{{tools.amount}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: coupon\n          type: object\n          value: $.\n    - name: reports\n      path: /reports/sales\n      description: Retrieve WooCommerce sales reports.\n      operations:\n      - name: get-sales-report\n        method: GET\n        description: Get sales report summary for a date range.\n        inputParameters:\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: 'Report period: week, month, last_month, year.'\n        - name: date_min\n          in: query\n          type: string\n          required: false\n          description: Start\
  \ date (ISO 8601).\n        - name: date_max\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: report\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: woo-headless-api\n    description: Unified REST API for headless WooCommerce storefronts.\n    resources:\n    - path: /v1/catalog/products\n      name: catalog-products\n      description: Public product catalog for the storefront.\n      operations:\n      - method: GET\n        name: browse-products\n        description: Browse the public product catalog.\n        call: woo-store.list-store-products\n        with:\n          search: rest.search\n          category: rest.category\n          on_sale: rest.on_sale\n          min_price: rest.min_price\n          max_price: rest.max_price\n        outputParameters:\n        - type: array\n     \
  \     mapping: $.\n    - path: /v1/catalog/categories\n      name: catalog-categories\n      description: Product categories for navigation.\n      operations:\n      - method: GET\n        name: list-categories\n        description: List product categories.\n        call: woo-store.list-categories\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/cart\n      name: cart\n      description: Shopper cart management.\n      operations:\n      - method: GET\n        name: view-cart\n        description: View current cart.\n        call: woo-store.get-cart\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-to-cart\n        description: Add product to cart.\n        call: woo-store.add-to-cart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checkout\n      name: checkout\n      description: Checkout process.\n      operations:\n      - method: POST\n\
  \        name: submit-checkout\n        description: Submit checkout and place order.\n        call: woo-store.submit-checkout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products-admin\n      description: Product catalog management (admin).\n      operations:\n      - method: GET\n        name: list-products-admin\n        description: List all products including drafts.\n        call: woo-rest.list-products\n        with:\n          status: rest.status\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: woo-headless-mcp\n    transport: http\n    description: MCP server for AI-assisted headless WooCommerce storefront building.\n    tools:\n    - name: browse-catalog\n      description: Browse the public WooCommerce product catalog for storefront display.\n      hints:\n        readOnly: true\n      call: woo-store.list-store-products\n      with:\n \
  \       search: tools.search\n        category: tools.category\n        on_sale: tools.on_sale\n        min_price: tools.min_price\n        max_price: tools.max_price\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-product-for-display\n      description: Get full product details for storefront product page rendering.\n      hints:\n        readOnly: true\n      call: woo-store.get-store-product\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-categories-for-nav\n      description: List product categories for building storefront navigation menus.\n      hints:\n        readOnly: true\n      call: woo-store.list-categories\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: view-current-cart\n      description: View the current shopper's cart for display in the cart drawer/page.\n      hints:\n        readOnly: true\n      call: woo-store.get-cart\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-item-to-cart\n      description: Add a product to the shopper's cart during product browsing.\n      hints:\n        readOnly: false\n      call: woo-store.add-to-cart\n      with:\n        id: tools.product_id\n        quantity: tools.quantity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-from-cart\n      description: Remove an item from the shopper's cart.\n      hints:\n        readOnly: false\n        destructive: false\n      call: woo-store.remove-cart-item\n      with:\n        key: tools.cart_item_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Submit checkout details and place a WooCommerce order.\n      hints:\n        readOnly: false\n      call: woo-store.submit-checkout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-products-admin\n      description:\
  \ List all products including drafts for admin/build-time rendering.\n      hints:\n        readOnly: true\n      call: woo-rest.list-products\n      with:\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/woocommerce/refs/heads/main/capabilities/headless-commerce.yaml
tags:
- Cart
- Checkout
- eCommerce
- Frontend
- Headless
- WooCommerce
tools:
- description: Browse the public WooCommerce product catalog for storefront display.
  hints:
    readOnly: true
  name: browse-catalog
- description: Get full product details for storefront product page rendering.
  hints:
    readOnly: true
  name: get-product-for-display
- description: List product categories for building storefront navigation menus.
  hints:
    readOnly: true
  name: list-categories-for-nav
- description: View the current shopper's cart for display in the cart drawer/page.
  hints:
    readOnly: true
  name: view-current-cart
- description: Add a product to the shopper's cart during product browsing.
  hints:
    readOnly: false
  name: add-item-to-cart
- description: Remove an item from the shopper's cart.
  hints:
    destructive: false
    readOnly: false
  name: remove-from-cart
- description: Submit checkout details and place a WooCommerce order.
  hints:
    readOnly: false
  name: place-order
- description: List all products including drafts for admin/build-time rendering.
  hints:
    readOnly: true
  name: list-all-products-admin
---
