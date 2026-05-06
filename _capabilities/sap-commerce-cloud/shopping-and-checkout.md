---
categories: []
consumed_apis: []
description: Workflow capability for the customer shopping journey in SAP Commerce Cloud. Covers product discovery, cart management, checkout, and order tracking for both B2B and B2C scenarios. Used by storefront developers, mobile app developers, and commerce integration engineers.
layout: capability
name: SAP Commerce Cloud Shopping and Checkout
operations:
- description: Search the product catalog.
  method: GET
  name: search-products
  path: /v1/products
- description: Get product details.
  method: GET
  name: get-product
  path: /v1/products/{productCode}
- description: List user order history.
  method: GET
  name: list-orders
  path: /v1/users/{userId}/orders
- description: Get order details.
  method: GET
  name: get-order
  path: /v1/users/{userId}/orders/{code}
- description: Find nearby stores.
  method: GET
  name: find-stores
  path: /v1/stores
personas: []
provider_name: SAP Commerce Cloud
provider_slug: sap-commerce-cloud
search_terms:
- get detailed product information including price, stock, images, and reviews.
- get product details.
- get order
- get details and status of a specific order.
- get product
- omnichannel
- retail
- b2b
- list user order history.
- search the sap commerce cloud product catalog using keywords or facets.
- commerce
- order management.
- search the product catalog.
- single product.
- add to cart
- b2c
- ecommerce
- product catalog search.
- sap
- list order history for a customer.
- store locator.
- get the customer's current shopping cart contents and totals.
- get order details.
- list orders
- find nearby stores.
- add a product to the customer's shopping cart.
- get cart
- single order.
- find stores
- customer experience
- search products
- find physical store locations for click-and-collect or in-store assistance.
slug: shopping-and-checkout
source_filename: shopping-and-checkout.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Commerce Cloud Shopping and Checkout\n  description: Workflow capability for the customer shopping journey in SAP Commerce Cloud. Covers product discovery, cart\n    management, checkout, and order tracking for both B2B and B2C scenarios. Used by storefront developers, mobile app developers,\n    and commerce integration engineers.\n  tags:\n  - B2B\n  - B2C\n  - Commerce\n  - Customer Experience\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_COMMERCE_OAUTH_TOKEN: SAP_COMMERCE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-commerce-occ\n    baseUri: https://{tenant}.{region}.commercecloud.sap/occ/v2/{baseSiteId}\n    description: SAP Commerce Cloud OCC v2 REST API.\n    authentication:\n      type: bearer\n      token: '{{SAP_COMMERCE_OAUTH_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Product catalog browsing\
  \ and search.\n      operations:\n      - name: search-products\n        method: GET\n        description: Search for products using free-text or faceted navigation.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query or facet filter\n        - name: currentPage\n          in: query\n          type: integer\n          required: false\n          description: Current page number (0-based)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort criteria\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Response field set (BASIC, DEFAULT, FULL)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get detailed information about a specific product.\n        inputParameters:\n        - name: productCode\n          in: path\n          type: string\n          required: true\n          description: Product code identifier\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Response field set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts\n      path: /users/{userId}/carts\n      description: Shopping cart management.\n      operations:\n      - name: get-cart\n        method: GET\n        description: Get the current cart for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\
  \ or 'current' for authenticated user\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-to-cart\n        method: POST\n        description: Add a product to the cart.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product:\n              code: '{{tools.productCode}}'\n            quantity: '{{tools.quantity}}'\n    - name: orders\n\
  \      path: /users/{userId}/orders\n      description: Order management and history.\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get details of a specific order.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: code\n          in: path\n          type: string\n          required: true\n         \
  \ description: Order code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /stores\n      description: Physical store locator.\n      operations:\n      - name: list-stores\n        method: GET\n        description: List physical stores with optional location search.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Location search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sap-commerce-shopping-api\n    description: Unified REST API for SAP Commerce Cloud shopping and order management.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Product catalog search.\n      operations:\n      - method: GET\n  \
  \      name: search-products\n        description: Search the product catalog.\n        call: sap-commerce-occ.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{productCode}\n      name: product\n      description: Single product.\n      operations:\n      - method: GET\n        name: get-product\n        description: Get product details.\n        call: sap-commerce-occ.get-product\n        with:\n          productCode: rest.productCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}/orders\n      name: orders\n      description: Order management.\n      operations:\n      - method: GET\n        name: list-orders\n        description: List user order history.\n        call: sap-commerce-occ.list-orders\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}/orders/{code}\n\
  \      name: order\n      description: Single order.\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order details.\n        call: sap-commerce-occ.get-order\n        with:\n          userId: rest.userId\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores\n      name: stores\n      description: Store locator.\n      operations:\n      - method: GET\n        name: find-stores\n        description: Find nearby stores.\n        call: sap-commerce-occ.list-stores\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sap-commerce-shopping-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP Commerce Cloud shopping and checkout.\n    tools:\n    - name: search-products\n      description: Search the SAP Commerce Cloud product catalog using keywords or facets.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: sap-commerce-occ.search-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get detailed product information including price, stock, images, and reviews.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-commerce-occ.get-product\n      with:\n        productCode: tools.productCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-to-cart\n      description: Add a product to the customer's shopping cart.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sap-commerce-occ.add-to-cart\n      with:\n        userId: tools.userId\n        cartId: tools.cartId\n        productCode: tools.productCode\n        quantity: tools.quantity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cart\n      description: Get the customer's current shopping cart contents\
  \ and totals.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-commerce-occ.get-cart\n      with:\n        userId: tools.userId\n        cartId: tools.cartId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List order history for a customer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-occ.list-orders\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get details and status of a specific order.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-commerce-occ.get-order\n      with:\n        userId: tools.userId\n        code: tools.orderCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-stores\n      description: Find physical store locations for click-and-collect or in-store assistance.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-occ.list-stores\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-commerce-cloud/refs/heads/main/capabilities/shopping-and-checkout.yaml
tags:
- B2B
- B2C
- Commerce
- Customer Experience
- SAP
tools:
- description: Search the SAP Commerce Cloud product catalog using keywords or facets.
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get detailed product information including price, stock, images, and reviews.
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Add a product to the customer's shopping cart.
  hints:
    idempotent: false
    readOnly: false
  name: add-to-cart
- description: Get the customer's current shopping cart contents and totals.
  hints:
    openWorld: false
    readOnly: true
  name: get-cart
- description: List order history for a customer.
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get details and status of a specific order.
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Find physical store locations for click-and-collect or in-store assistance.
  hints:
    openWorld: true
    readOnly: true
  name: find-stores
---
