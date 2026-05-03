---
api_specs:
- filename: shopify-storefront-openapi.yml
  format: yaml
  label: shopify-storefront
  slug: shopify-storefront
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shopify-storefront/refs/heads/main/openapi/shopify-storefront-openapi.yml
categories: []
consumed_apis:
- shopify-storefront
description: Workflow capability for building headless Shopify commerce experiences. Combines product discovery, collection browsing, search, cart management, and customer account operations into a unified capability for front-end developers building custom storefronts with frameworks like Next.js, Nuxt, Remix, or Shopify Hydrogen.
layout: capability
name: Shopify Headless Commerce
operations:
- description: Browse all available products
  method: GET
  name: get-products
  path: /v1/products
- description: Get full product details by URL handle
  method: GET
  name: get-product-by-handle
  path: /v1/products/{handle}
- description: Browse product collections
  method: GET
  name: get-collections
  path: /v1/collections
- description: List products in a specific collection
  method: GET
  name: get-collection-products
  path: /v1/collections/{handle}/products
- description: Search products by keyword
  method: GET
  name: search-products
  path: /v1/search
- description: Create a new shopping cart
  method: POST
  name: create-cart
  path: /v1/cart
- description: Get cart contents and cost summary
  method: GET
  name: get-cart
  path: /v1/cart/{id}
- description: Add items to cart
  method: POST
  name: add-to-cart
  path: /v1/cart/{id}/lines
- description: Remove items from cart
  method: DELETE
  name: remove-from-cart
  path: /v1/cart/{id}/lines
- description: Get authenticated customer data
  method: GET
  name: get-customer
  path: /v1/customer
personas: []
provider_name: Shopify Storefront API
provider_slug: shopify-storefront
search_terms:
- browse product collections
- headless
- get products
- create a new shopping cart
- browse all available products
- search products by keyword
- add one or more product variants to an existing cart
- list products in a specific collection
- get authenticated customer data
- add to cart
- cart creation
- graphql
- customer account
- get collection products
- search products
- get product by handle
- remove specific line items from a shopping cart
- remove from cart
- products
- get collections
- get cart
- cart
- product search
- commerce
- create a new shopping cart, optionally with initial product variant line items
- cart line item management
- list all products within a specific collection by handle
- products within a collection
- product collection catalog
- product detail page data
- browse all products available in the storefront catalog
- search the product catalog by keyword, title, tag, or type
- add items to cart
- get full product details by url handle
- storefront
- get customer
- ecommerce
- product catalog browsing and search
- create cart
- remove items from cart
- retrieve complete product details including variants and images by url handle
- retrieve authenticated customer profile and recent order history
- retrieve a shopping cart with line items and pricing totals
- get cart contents and cost summary
- checkout
- cart retrieval
- browse product collections available in the storefront
slug: headless-commerce
source_filename: headless-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shopify Headless Commerce\"\n  description: >-\n    Workflow capability for building headless Shopify commerce experiences.\n    Combines product discovery, collection browsing, search, cart management,\n    and customer account operations into a unified capability for front-end\n    developers building custom storefronts with frameworks like Next.js, Nuxt,\n    Remix, or Shopify Hydrogen.\n  tags:\n    - Commerce\n    - Ecommerce\n    - Headless\n    - GraphQL\n    - Storefront\n    - Cart\n    - Checkout\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHOPIFY_STOREFRONT_ACCESS_TOKEN: SHOPIFY_STOREFRONT_ACCESS_TOKEN\n      SHOPIFY_STORE_NAME: SHOPIFY_STORE_NAME\n\ncapability:\n  consumes:\n    - import: shopify-storefront\n      location: ./shared/shopify-storefront.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: shopify-headless-commerce-api\n   \
  \   description: \"Unified REST API for headless Shopify commerce experiences.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: Product catalog browsing and search\n          operations:\n            - method: GET\n              name: get-products\n              description: Browse all available products\n              call: \"shopify-storefront.get-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{handle}\n          name: product-detail\n          description: Product detail page data\n          operations:\n            - method: GET\n              name: get-product-by-handle\n              description: Get full product details by URL handle\n              call: \"shopify-storefront.get-product-by-handle\"\n              with:\n                handle: \"rest.handle\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: Product collection catalog\n          operations:\n            - method: GET\n              name: get-collections\n              description: Browse product collections\n              call: \"shopify-storefront.get-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections/{handle}/products\n          name: collection-products\n          description: Products within a collection\n          operations:\n            - method: GET\n              name: get-collection-products\n              description: List products in a specific collection\n              call: \"shopify-storefront.get-collection-products\"\n              with:\n                handle: \"rest.handle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n\
  \          name: search\n          description: Product search\n          operations:\n            - method: GET\n              name: search-products\n              description: Search products by keyword\n              call: \"shopify-storefront.search-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cart\n          name: cart\n          description: Cart creation\n          operations:\n            - method: POST\n              name: create-cart\n              description: Create a new shopping cart\n              call: \"shopify-storefront.create-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cart/{id}\n          name: cart-detail\n          description: Cart retrieval\n          operations:\n            - method: GET\n              name: get-cart\n              description: Get cart contents and cost summary\n          \
  \    call: \"shopify-storefront.get-cart\"\n              with:\n                cart_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cart/{id}/lines\n          name: cart-lines\n          description: Cart line item management\n          operations:\n            - method: POST\n              name: add-to-cart\n              description: Add items to cart\n              call: \"shopify-storefront.add-to-cart\"\n              with:\n                cart_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-from-cart\n              description: Remove items from cart\n              call: \"shopify-storefront.remove-from-cart\"\n              with:\n                cart_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/customer\n          name: customer\n          description: Customer account\n          operations:\n            - method: GET\n              name: get-customer\n              description: Get authenticated customer data\n              call: \"shopify-storefront.get-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shopify-headless-commerce-mcp\n      transport: http\n      description: \"MCP server for AI-assisted headless Shopify storefront development.\"\n      tools:\n        - name: get-products\n          description: Browse all products available in the storefront catalog\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.get-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product-by-handle\n          description:\
  \ Retrieve complete product details including variants and images by URL handle\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.get-product-by-handle\"\n          with:\n            handle: \"tools.handle\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-collections\n          description: Browse product collections available in the storefront\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.get-collections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-collection-products\n          description: List all products within a specific collection by handle\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.get-collection-products\"\n          with:\n            handle: \"tools.handle\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-products\n          description: Search the product catalog by keyword, title, tag, or type\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.search-products\"\n          with:\n            search_query: \"tools.search_query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cart\n          description: Create a new shopping cart, optionally with initial product variant line items\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopify-storefront.create-cart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cart\n          description: Retrieve a shopping cart with line items and pricing totals\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"shopify-storefront.get-cart\"\n          with:\n            cart_id: \"tools.cart_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-to-cart\n          description: Add one or more product variants to an existing cart\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopify-storefront.add-to-cart\"\n          with:\n            cart_id: \"tools.cart_id\"\n            lines: \"tools.lines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-from-cart\n          description: Remove specific line items from a shopping cart\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"shopify-storefront.remove-from-cart\"\n          with:\n            cart_id: \"tools.cart_id\"\n            line_ids: \"tools.line_ids\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: Retrieve authenticated customer profile and recent order history\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopify-storefront.get-customer\"\n          with:\n            customer_access_token: \"tools.customer_access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shopify-storefront/refs/heads/main/capabilities/headless-commerce.yaml
tags:
- Commerce
- Ecommerce
- Headless
- GraphQL
- Storefront
- Cart
- Checkout
tools:
- description: Browse all products available in the storefront catalog
  hints:
    openWorld: true
    readOnly: true
  name: get-products
- description: Retrieve complete product details including variants and images by URL handle
  hints:
    openWorld: true
    readOnly: true
  name: get-product-by-handle
- description: Browse product collections available in the storefront
  hints:
    openWorld: true
    readOnly: true
  name: get-collections
- description: List all products within a specific collection by handle
  hints:
    openWorld: true
    readOnly: true
  name: get-collection-products
- description: Search the product catalog by keyword, title, tag, or type
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Create a new shopping cart, optionally with initial product variant line items
  hints:
    destructive: false
    readOnly: false
  name: create-cart
- description: Retrieve a shopping cart with line items and pricing totals
  hints:
    openWorld: true
    readOnly: true
  name: get-cart
- description: Add one or more product variants to an existing cart
  hints:
    destructive: false
    readOnly: false
  name: add-to-cart
- description: Remove specific line items from a shopping cart
  hints:
    destructive: true
    readOnly: false
  name: remove-from-cart
- description: Retrieve authenticated customer profile and recent order history
  hints:
    openWorld: true
    readOnly: true
  name: get-customer
---
