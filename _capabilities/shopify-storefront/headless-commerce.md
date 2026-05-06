---
categories: []
consumed_apis: []
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
- retrieve authenticated customer profile and recent order history
- remove from cart
- get customer
- create a new shopping cart
- search products by keyword
- get collections
- get authenticated customer data
- graphql
- product collection catalog
- browse all available products
- create a new shopping cart, optionally with initial product variant line items
- browse product collections available in the storefront
- commerce
- cart
- cart line item management
- get collection products
- browse all products available in the storefront catalog
- product catalog browsing and search
- get full product details by url handle
- ecommerce
- add to cart
- cart retrieval
- get products
- list products in a specific collection
- retrieve a shopping cart with line items and pricing totals
- get product by handle
- product search
- checkout
- add one or more product variants to an existing cart
- remove specific line items from a shopping cart
- headless
- cart creation
- add items to cart
- search the product catalog by keyword, title, tag, or type
- storefront
- list all products within a specific collection by handle
- get cart contents and cost summary
- get cart
- retrieve complete product details including variants and images by url handle
- products
- customer account
- product detail page data
- remove items from cart
- search products
- browse product collections
- create cart
- products within a collection
slug: headless-commerce
source_filename: headless-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shopify Headless Commerce\n  description: Workflow capability for building headless Shopify commerce experiences. Combines product discovery, collection\n    browsing, search, cart management, and customer account operations into a unified capability for front-end developers\n    building custom storefronts with frameworks like Next.js, Nuxt, Remix, or Shopify Hydrogen.\n  tags:\n  - Commerce\n  - Ecommerce\n  - Headless\n  - GraphQL\n  - Storefront\n  - Cart\n  - Checkout\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHOPIFY_STOREFRONT_ACCESS_TOKEN: SHOPIFY_STOREFRONT_ACCESS_TOKEN\n    SHOPIFY_STORE_NAME: SHOPIFY_STORE_NAME\ncapability:\n  consumes:\n  - type: http\n    namespace: shopify-storefront\n    baseUri: https://{{env.SHOPIFY_STORE_NAME}}.myshopify.com/api/2024-10/graphql.json\n    description: Shopify Storefront GraphQL API\n    authentication:\n      type: apikey\n      key: X-Shopify-Storefront-Access-Token\n\
  \      value: '{{env.SHOPIFY_STOREFRONT_ACCESS_TOKEN}}'\n      placement: header\n    resources:\n    - name: graphql\n      path: /\n      description: GraphQL endpoint for all Storefront API queries and mutations\n      operations:\n      - name: get-products\n        method: POST\n        description: Query products from the storefront catalog\n        body:\n          type: json\n          data:\n            query: '{ products(first: {{tools.limit}}) { edges { node { id title handle description priceRange { minVariantPrice\n              { amount currencyCode } } availableForSale } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.products\n      - name: get-product-by-handle\n        method: POST\n        description: Query a specific product by its URL handle\n        body:\n          type: json\n          data:\n            query: '{ productByHandle(handle: \"{{tools.handle}}\") { id title description\
  \ variants(first: 20) { edges { node\n              { id title price { amount currencyCode } availableForSale } } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.productByHandle\n      - name: get-collections\n        method: POST\n        description: Query product collections\n        body:\n          type: json\n          data:\n            query: '{ collections(first: {{tools.limit}}) { edges { node { id title handle description } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.collections\n      - name: get-collection-products\n        method: POST\n        description: Query products within a specific collection\n        body:\n          type: json\n          data:\n            query: '{ collectionByHandle(handle: \"{{tools.handle}}\") { products(first: {{tools.limit}}) { edges { node { id\n           \
  \   title handle priceRange { minVariantPrice { amount currencyCode } } } } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.collectionByHandle.products\n      - name: create-cart\n        method: POST\n        description: Create a new shopping cart\n        body:\n          type: json\n          data:\n            query: 'mutation cartCreate($input: CartInput!) { cartCreate(input: $input) { cart { id checkoutUrl totalQuantity\n              cost { totalAmount { amount currencyCode } } } } }'\n            variables:\n              input:\n                lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.cartCreate.cart\n      - name: get-cart\n        method: POST\n        description: Retrieve a cart by ID\n        body:\n          type: json\n          data:\n            query: '{ cart(id: \"\
  {{tools.cart_id}}\") { id checkoutUrl totalQuantity cost { totalAmount { amount currencyCode\n              } subtotalAmount { amount currencyCode } } lines(first: 20) { edges { node { id quantity merchandise { ... on\n              ProductVariant { id title price { amount currencyCode } product { title handle } } } } } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.cart\n      - name: add-to-cart\n        method: POST\n        description: Add items to an existing cart\n        body:\n          type: json\n          data:\n            query: 'mutation cartLinesAdd($cartId: ID!, $lines: [CartLineInput!]!) { cartLinesAdd(cartId: $cartId, lines:\n              $lines) { cart { id totalQuantity cost { totalAmount { amount currencyCode } } } } }'\n            variables:\n              cartId: '{{tools.cart_id}}'\n              lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.data.cartLinesAdd.cart\n      - name: remove-from-cart\n        method: POST\n        description: Remove items from a cart\n        body:\n          type: json\n          data:\n            query: 'mutation cartLinesRemove($cartId: ID!, $lineIds: [ID!]!) { cartLinesRemove(cartId: $cartId, lineIds: $lineIds)\n              { cart { id totalQuantity } } }'\n            variables:\n              cartId: '{{tools.cart_id}}'\n              lineIds: '{{tools.line_ids}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.cartLinesRemove.cart\n      - name: get-customer\n        method: POST\n        description: Retrieve authenticated customer information\n        body:\n          type: json\n          data:\n            query: '{ customer(customerAccessToken: \"{{tools.customer_access_token}}\") { id email firstName lastName orders(first:\n    \
  \          10) { edges { node { id orderNumber totalPrice { amount currencyCode } } } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.customer\n      - name: search-products\n        method: POST\n        description: Search products by query string\n        body:\n          type: json\n          data:\n            query: '{ products(first: {{tools.limit}}, query: \"{{tools.search_query}}\") { edges { node { id title handle description\n              priceRange { minVariantPrice { amount currencyCode } } availableForSale } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.products\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shopify-headless-commerce-api\n    description: Unified REST API for headless Shopify commerce experiences.\n    resources:\n    - path: /v1/products\n      name: products\n\
  \      description: Product catalog browsing and search\n      operations:\n      - method: GET\n        name: get-products\n        description: Browse all available products\n        call: shopify-storefront.get-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{handle}\n      name: product-detail\n      description: Product detail page data\n      operations:\n      - method: GET\n        name: get-product-by-handle\n        description: Get full product details by URL handle\n        call: shopify-storefront.get-product-by-handle\n        with:\n          handle: rest.handle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: Product collection catalog\n      operations:\n      - method: GET\n        name: get-collections\n        description: Browse product collections\n        call: shopify-storefront.get-collections\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/collections/{handle}/products\n      name: collection-products\n      description: Products within a collection\n      operations:\n      - method: GET\n        name: get-collection-products\n        description: List products in a specific collection\n        call: shopify-storefront.get-collection-products\n        with:\n          handle: rest.handle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Product search\n      operations:\n      - method: GET\n        name: search-products\n        description: Search products by keyword\n        call: shopify-storefront.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cart\n      name: cart\n      description: Cart creation\n      operations:\n      - method: POST\n        name: create-cart\n        description: Create a new shopping\
  \ cart\n        call: shopify-storefront.create-cart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cart/{id}\n      name: cart-detail\n      description: Cart retrieval\n      operations:\n      - method: GET\n        name: get-cart\n        description: Get cart contents and cost summary\n        call: shopify-storefront.get-cart\n        with:\n          cart_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cart/{id}/lines\n      name: cart-lines\n      description: Cart line item management\n      operations:\n      - method: POST\n        name: add-to-cart\n        description: Add items to cart\n        call: shopify-storefront.add-to-cart\n        with:\n          cart_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-from-cart\n        description: Remove items from cart\n        call: shopify-storefront.remove-from-cart\n\
  \        with:\n          cart_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customer\n      name: customer\n      description: Customer account\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get authenticated customer data\n        call: shopify-storefront.get-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shopify-headless-commerce-mcp\n    transport: http\n    description: MCP server for AI-assisted headless Shopify storefront development.\n    tools:\n    - name: get-products\n      description: Browse all products available in the storefront catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-by-handle\n      description: Retrieve complete product\
  \ details including variants and images by URL handle\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-product-by-handle\n      with:\n        handle: tools.handle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collections\n      description: Browse product collections available in the storefront\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-collections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collection-products\n      description: List all products within a specific collection by handle\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-collection-products\n      with:\n        handle: tools.handle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-products\n      description: Search the product catalog by keyword, title,\
  \ tag, or type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.search-products\n      with:\n        search_query: tools.search_query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cart\n      description: Create a new shopping cart, optionally with initial product variant line items\n      hints:\n        readOnly: false\n        destructive: false\n      call: shopify-storefront.create-cart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cart\n      description: Retrieve a shopping cart with line items and pricing totals\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-cart\n      with:\n        cart_id: tools.cart_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-to-cart\n      description: Add one or more product variants to an existing cart\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n      call: shopify-storefront.add-to-cart\n      with:\n        cart_id: tools.cart_id\n        lines: tools.lines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-from-cart\n      description: Remove specific line items from a shopping cart\n      hints:\n        readOnly: false\n        destructive: true\n      call: shopify-storefront.remove-from-cart\n      with:\n        cart_id: tools.cart_id\n        line_ids: tools.line_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Retrieve authenticated customer profile and recent order history\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shopify-storefront.get-customer\n      with:\n        customer_access_token: tools.customer_access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
