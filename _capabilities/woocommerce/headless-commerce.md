---
categories: []
consumed_apis:
- woo-store
- woo-rest
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
- submit checkout details and place a woocommerce order.
- Headless Architect
- wordpress
- ecommerce
- view cart
- frontend
- add to cart
- submit checkout
- view current cart
- remove from cart
- public product catalog for the storefront.
- checkout
- open source
- list product categories.
- place order
- browse the public woocommerce product catalog for storefront display.
- shopper cart management.
- checkout process.
- managing product catalog, orders, customers, and store configuration
- browse catalog
- products
- add a product to the shopper's cart during product browsing.
- list product categories for building storefront navigation menus.
- list categories
- product categories for navigation.
- Store Administrator
- browse products
- Operations Manager
- browse the public product catalog.
- list categories for nav
- Frontend Developer
- list products admin
- get product for display
- headless
- orders
- list all products admin
- list all products including drafts.
- add item to cart
- list all products including drafts for admin/build-time rendering.
- product catalog management (admin).
- processing orders, managing fulfillment, and reviewing sales analytics
- add product to cart.
- designing headless commerce architecture with woocommerce apis
- view current cart.
- woocommerce
- complete store management combining rest api and store api
- headless storefront capability with public store api and admin rest api
- view the current shopper's cart for display in the cart drawer/page.
- submit checkout and place order.
- building custom storefronts using woocommerce as a headless backend
- get full product details for storefront product page rendering.
- remove an item from the shopper's cart.
- cart
slug: headless-commerce
source_filename: headless-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WooCommerce Headless Commerce\"\n  description: >-\n    Headless commerce capability combining the public WooCommerce Store API with\n    authenticated REST API operations for building custom frontends. Used by\n    frontend developers and headless architects building React, Vue, or custom\n    storefronts with Woo as the commerce backend.\n  tags:\n    - Cart\n    - Checkout\n    - eCommerce\n    - Frontend\n    - Headless\n    - WooCommerce\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WOOCOMMERCE_CONSUMER_KEY: WOOCOMMERCE_CONSUMER_KEY\n      WOOCOMMERCE_CONSUMER_SECRET: WOOCOMMERCE_CONSUMER_SECRET\n\ncapability:\n  consumes:\n    - import: woo-store\n      location: ./shared/store-api.yaml\n    - import: woo-rest\n      location: ./shared/rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: woo-headless-api\n      description: \"Unified REST\
  \ API for headless WooCommerce storefronts.\"\n      resources:\n        - path: /v1/catalog/products\n          name: catalog-products\n          description: \"Public product catalog for the storefront.\"\n          operations:\n            - method: GET\n              name: browse-products\n              description: \"Browse the public product catalog.\"\n              call: \"woo-store.list-store-products\"\n              with:\n                search: \"rest.search\"\n                category: \"rest.category\"\n                on_sale: \"rest.on_sale\"\n                min_price: \"rest.min_price\"\n                max_price: \"rest.max_price\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/categories\n          name: catalog-categories\n          description: \"Product categories for navigation.\"\n          operations:\n            - method: GET\n              name: list-categories\n           \
  \   description: \"List product categories.\"\n              call: \"woo-store.list-categories\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/cart\n          name: cart\n          description: \"Shopper cart management.\"\n          operations:\n            - method: GET\n              name: view-cart\n              description: \"View current cart.\"\n              call: \"woo-store.get-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-to-cart\n              description: \"Add product to cart.\"\n              call: \"woo-store.add-to-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/checkout\n          name: checkout\n          description: \"Checkout process.\"\n          operations:\n            - method: POST\n       \
  \       name: submit-checkout\n              description: \"Submit checkout and place order.\"\n              call: \"woo-store.submit-checkout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products-admin\n          description: \"Product catalog management (admin).\"\n          operations:\n            - method: GET\n              name: list-products-admin\n              description: \"List all products including drafts.\"\n              call: \"woo-rest.list-products\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: woo-headless-mcp\n      transport: http\n      description: \"MCP server for AI-assisted headless WooCommerce storefront building.\"\n      tools:\n        - name: browse-catalog\n          description:\
  \ \"Browse the public WooCommerce product catalog for storefront display.\"\n          hints:\n            readOnly: true\n          call: \"woo-store.list-store-products\"\n          with:\n            search: \"tools.search\"\n            category: \"tools.category\"\n            on_sale: \"tools.on_sale\"\n            min_price: \"tools.min_price\"\n            max_price: \"tools.max_price\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-product-for-display\n          description: \"Get full product details for storefront product page rendering.\"\n          hints:\n            readOnly: true\n          call: \"woo-store.get-store-product\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-categories-for-nav\n          description: \"List product categories for building storefront navigation menus.\"\n          hints:\n\
  \            readOnly: true\n          call: \"woo-store.list-categories\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: view-current-cart\n          description: \"View the current shopper's cart for display in the cart drawer/page.\"\n          hints:\n            readOnly: true\n          call: \"woo-store.get-cart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-item-to-cart\n          description: \"Add a product to the shopper's cart during product browsing.\"\n          hints:\n            readOnly: false\n          call: \"woo-store.add-to-cart\"\n          with:\n            id: \"tools.product_id\"\n            quantity: \"tools.quantity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-from-cart\n          description: \"Remove an item from the shopper's cart.\"\n          hints:\n      \
  \      readOnly: false\n            destructive: false\n          call: \"woo-store.remove-cart-item\"\n          with:\n            key: \"tools.cart_item_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: place-order\n          description: \"Submit checkout details and place a WooCommerce order.\"\n          hints:\n            readOnly: false\n          call: \"woo-store.submit-checkout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-all-products-admin\n          description: \"List all products including drafts for admin/build-time rendering.\"\n          hints:\n            readOnly: true\n          call: \"woo-rest.list-products\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
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
