---
categories: []
consumed_apis: []
description: The Content API for Shopping allows apps to interact directly with the Google Merchant Center platform, enabling management of product listings, account information, data feeds, inventory, orders, and promotions. It provides programmatic access to create, update, and delete products, manage shipping and tax settings, handle order workflows, and access reporting data.
layout: capability
name: Google Content API for Shopping
operations:
- description: Google Content API for Shopping List Products
  method: GET
  name: listproducts
  path: /{merchantId}/products
- description: Google Content API for Shopping Insert Product
  method: POST
  name: insertproduct
  path: /{merchantId}/products
- description: Google Content API for Shopping Get Product
  method: GET
  name: getproduct
  path: /{merchantId}/products/{productId}
- description: Google Content API for Shopping Delete Product
  method: DELETE
  name: deleteproduct
  path: /{merchantId}/products/{productId}
- description: Google Content API for Shopping List Accounts
  method: GET
  name: listaccounts
  path: /{merchantId}/accounts
- description: Google Content API for Shopping List Orders
  method: GET
  name: listorders
  path: /{merchantId}/orders
- description: Google Content API for Shopping List Datafeeds
  method: GET
  name: listdatafeeds
  path: /{merchantId}/datafeeds
personas: []
provider_name: Google Content API for Shopping
provider_slug: google-shopping
search_terms:
- listaccounts
- insertproduct
- google content api for shopping list datafeeds
- retail
- deleteproduct
- product listings
- google
- e-commerce
- google content api for shopping insert product
- google shopping
- listdatafeeds
- listproducts
- listorders
- google content api for shopping list products
- google content api for shopping list accounts
- api
- google content api for shopping list orders
- shopping
- merchant center
- getproduct
- google content api for shopping delete product
- google content api for shopping get product
slug: google-shopping-capability
source_filename: google-shopping-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Content API for Shopping\n  description: The Content API for Shopping allows apps to interact directly with the Google Merchant Center platform, enabling\n    management of product listings, account information, data feeds, inventory, orders, and promotions. It provides programmatic\n    access to create, update, and delete products, manage shipping and tax settings, handle order workflows, and access reporting\n    data.\n  tags:\n  - Google\n  - Shopping\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-shopping\n    baseUri: https://shoppingcontent.googleapis.com/content/v2.1\n    description: Google Content API for Shopping HTTP API.\n    resources:\n    - name: merchantid-products\n      path: /{merchantId}/products\n      operations:\n      - name: listproducts\n        method: GET\n        description: Google Content API for Shopping List Products\n\
  \        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n          description: The ID of the merchant account.\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of products to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertproduct\n        method: POST\n        description: Google Content API for Shopping Insert Product\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n          description: The ID of the merchant account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ merchantid-products-productid\n      path: /{merchantId}/products/{productId}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Google Content API for Shopping Get Product\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n        - name: productId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Google Content API for Shopping Delete Product\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n        - name: productId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: merchantid-accounts\n      path: /{merchantId}/accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Google Content API for Shopping List Accounts\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: merchantid-orders\n      path: /{merchantId}/orders\n      operations:\n      - name: listorders\n        method: GET\n        description: Google Content API for Shopping List Orders\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: merchantid-datafeeds\n      path: /{merchantId}/datafeeds\n\
  \      operations:\n      - name: listdatafeeds\n        method: GET\n        description: Google Content API for Shopping List Datafeeds\n        inputParameters:\n        - name: merchantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-shopping-rest\n    description: REST adapter for Google Content API for Shopping.\n    resources:\n    - path: /{merchantId}/products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: Google Content API for Shopping List Products\n        call: google-shopping.listproducts\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/products\n      name: insertproduct\n      operations:\n\
  \      - method: POST\n        name: insertproduct\n        description: Google Content API for Shopping Insert Product\n        call: google-shopping.insertproduct\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/products/{productId}\n      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Google Content API for Shopping Get Product\n        call: google-shopping.getproduct\n        with:\n          merchantId: rest.merchantId\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/products/{productId}\n      name: deleteproduct\n      operations:\n      - method: DELETE\n        name: deleteproduct\n        description: Google Content API for Shopping Delete Product\n        call: google-shopping.deleteproduct\n        with:\n          merchantId:\
  \ rest.merchantId\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Google Content API for Shopping List Accounts\n        call: google-shopping.listaccounts\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: Google Content API for Shopping List Orders\n        call: google-shopping.listorders\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{merchantId}/datafeeds\n      name: listdatafeeds\n      operations:\n      - method: GET\n        name: listdatafeeds\n      \
  \  description: Google Content API for Shopping List Datafeeds\n        call: google-shopping.listdatafeeds\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-shopping-mcp\n    transport: http\n    description: MCP adapter for Google Content API for Shopping for AI agent use.\n    tools:\n    - name: listproducts\n      description: Google Content API for Shopping List Products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-shopping.listproducts\n      with:\n        merchantId: tools.merchantId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: The ID of the merchant account.\n        required: true\n      - name: maxResults\n        type: integer\n        description: Maximum\
  \ number of products to return.\n      - name: pageToken\n        type: string\n        description: Token for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertproduct\n      description: Google Content API for Shopping Insert Product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-shopping.insertproduct\n      with:\n        merchantId: tools.merchantId\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: The ID of the merchant account.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Google Content API for Shopping Get Product\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-shopping.getproduct\n      with:\n        merchantId: tools.merchantId\n        productId: tools.productId\n\
  \      inputParameters:\n      - name: merchantId\n        type: string\n        description: merchantId\n        required: true\n      - name: productId\n        type: string\n        description: productId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproduct\n      description: Google Content API for Shopping Delete Product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-shopping.deleteproduct\n      with:\n        merchantId: tools.merchantId\n        productId: tools.productId\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: merchantId\n        required: true\n      - name: productId\n        type: string\n        description: productId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccounts\n      description: Google Content API for Shopping List Accounts\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-shopping.listaccounts\n      with:\n        merchantId: tools.merchantId\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: merchantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: Google Content API for Shopping List Orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-shopping.listorders\n      with:\n        merchantId: tools.merchantId\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: merchantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatafeeds\n      description: Google Content API for Shopping List Datafeeds\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-shopping.listdatafeeds\n      with:\n        merchantId: tools.merchantId\n      inputParameters:\n      - name: merchantId\n        type: string\n        description: merchantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-shopping/refs/heads/main/capabilities/google-shopping-capability.yaml
tags:
- Google
- Shopping
- API
tools:
- description: Google Content API for Shopping List Products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Google Content API for Shopping Insert Product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertproduct
- description: Google Content API for Shopping Get Product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Google Content API for Shopping Delete Product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: Google Content API for Shopping List Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Google Content API for Shopping List Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Google Content API for Shopping List Datafeeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatafeeds
---
