---
categories: []
consumed_apis: []
description: Fake Store API exposes a sample REST API for e-commerce data including products, carts, users, and authentication. It is intended for prototyping, teaching, and integration testing — write operations return fabricated responses and do not persist data on the server.
layout: capability
name: Fake Store API
operations:
- description: List products
  method: GET
  name: listproducts
  path: /products
- description: Create a product
  method: POST
  name: createproduct
  path: /products
- description: Get a product
  method: GET
  name: getproduct
  path: /products/{id}
- description: Replace a product
  method: PUT
  name: replaceproduct
  path: /products/{id}
- description: Partially update a product
  method: PATCH
  name: updateproduct
  path: /products/{id}
- description: Delete a product
  method: DELETE
  name: deleteproduct
  path: /products/{id}
- description: List product categories
  method: GET
  name: listcategories
  path: /products/categories
- description: List products in a category
  method: GET
  name: listproductsbycategory
  path: /products/category/{category}
- description: List carts
  method: GET
  name: listcarts
  path: /carts
- description: Create a cart
  method: POST
  name: createcart
  path: /carts
- description: Get a cart
  method: GET
  name: getcart
  path: /carts/{id}
- description: Replace a cart
  method: PUT
  name: replacecart
  path: /carts/{id}
- description: Partially update a cart
  method: PATCH
  name: updatecart
  path: /carts/{id}
- description: Delete a cart
  method: DELETE
  name: deletecart
  path: /carts/{id}
- description: List carts for a user
  method: GET
  name: listcartsbyuser
  path: /carts/user/{userId}
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create a user
  method: POST
  name: createuser
  path: /users
- description: Get a user
  method: GET
  name: getuser
  path: /users/{id}
- description: Replace a user
  method: PUT
  name: replaceuser
  path: /users/{id}
- description: Partially update a user
  method: PATCH
  name: updateuser
  path: /users/{id}
- description: Delete a user
  method: DELETE
  name: deleteuser
  path: /users/{id}
- description: Login
  method: POST
  name: login
  path: /auth/login
personas: []
provider_name: Fake Store API
provider_slug: fake-store-api
search_terms:
- replace a user
- updateproduct
- deletecart
- list carts
- listcategories
- replaceproduct
- createproduct
- list products
- list product categories
- api
- orders
- partially update a product
- replace a cart
- delete a user
- createcart
- create a cart
- partially update a cart
- customers
- getuser
- listcartsbyuser
- replacecart
- get a user
- login
- products
- deleteuser
- list carts for a user
- delete a product
- deleteproduct
- getproduct
- list users
- synthetic data
- updateuser
- listproducts
- create a product
- replace a product
- get a cart
- fake data
- updatecart
- list products in a category
- get a product
- delete a cart
- createuser
- create a user
- getcart
- listusers
- replaceuser
- partially update a user
- listcarts
- store
- fake
- listproductsbycategory
slug: fake-store-api-capability
source_filename: fake-store-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fake Store API\n  description: Fake Store API exposes a sample REST API for e-commerce data including products, carts, users, and authentication.\n    It is intended for prototyping, teaching, and integration testing — write operations return fabricated responses and do\n    not persist data on the server.\n  tags:\n  - Fake\n  - Store\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fake-store-api\n    baseUri: https://fakestoreapi.com\n    description: Fake Store API HTTP API.\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproduct\n        method: POST\n        description: Create a product\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-id\n      path: /products/{id}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Get a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceproduct\n        method: PUT\n        description: Replace a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproduct\n        method: PATCH\n        description: Partially update a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Delete a product\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: products-categories\n      path: /products/categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: List product categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-category-category\n      path: /products/category/{category}\n      operations:\n      - name: listproductsbycategory\n        method: GET\n        description: List products in a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts\n      path: /carts\n      operations:\n      - name: listcarts\n        method: GET\n        description: List carts\n        inputParameters:\n        - name: startdate\n          in: query\n          type: string\n          description: Start date for filtering\
  \ carts\n        - name: enddate\n          in: query\n          type: string\n          description: End date for filtering carts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcart\n        method: POST\n        description: Create a cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts-id\n      path: /carts/{id}\n      operations:\n      - name: getcart\n        method: GET\n        description: Get a cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacecart\n        method: PUT\n        description: Replace a cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecart\n        method: PATCH\n\
  \        description: Partially update a cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecart\n        method: DELETE\n        description: Delete a cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts-user-userid\n      path: /carts/user/{userId}\n      operations:\n      - name: listcartsbyuser\n        method: GET\n        description: List carts for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method:\
  \ POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceuser\n        method: PUT\n        description: Replace a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: Partially update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete a user\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-login\n      path: /auth/login\n      operations:\n      - name: login\n        method: POST\n        description: Login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fake-store-api-rest\n    description: REST adapter for Fake Store API.\n    resources:\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n        call: fake-store-api.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: createproduct\n      operations:\n      - method: POST\n        name: createproduct\n        description: Create a product\n        call: fake-store-api.createproduct\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Get a product\n        call: fake-store-api.getproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: replaceproduct\n      operations:\n      - method: PUT\n        name: replaceproduct\n        description: Replace a product\n        call: fake-store-api.replaceproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: updateproduct\n      operations:\n      - method: PATCH\n        name: updateproduct\n        description: Partially update a product\n        call: fake-store-api.updateproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: deleteproduct\n      operations:\n      - method: DELETE\n      \
  \  name: deleteproduct\n        description: Delete a product\n        call: fake-store-api.deleteproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List product categories\n        call: fake-store-api.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/category/{category}\n      name: listproductsbycategory\n      operations:\n      - method: GET\n        name: listproductsbycategory\n        description: List products in a category\n        call: fake-store-api.listproductsbycategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts\n      name: listcarts\n      operations:\n      - method: GET\n        name: listcarts\n        description: List carts\n        call: fake-store-api.listcarts\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts\n      name: createcart\n      operations:\n      - method: POST\n        name: createcart\n        description: Create a cart\n        call: fake-store-api.createcart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts/{id}\n      name: getcart\n      operations:\n      - method: GET\n        name: getcart\n        description: Get a cart\n        call: fake-store-api.getcart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts/{id}\n      name: replacecart\n      operations:\n      - method: PUT\n        name: replacecart\n        description: Replace a cart\n        call: fake-store-api.replacecart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts/{id}\n      name: updatecart\n      operations:\n      - method: PATCH\n        name: updatecart\n        description: Partially\
  \ update a cart\n        call: fake-store-api.updatecart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts/{id}\n      name: deletecart\n      operations:\n      - method: DELETE\n        name: deletecart\n        description: Delete a cart\n        call: fake-store-api.deletecart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carts/user/{userId}\n      name: listcartsbyuser\n      operations:\n      - method: GET\n        name: listcartsbyuser\n        description: List carts for a user\n        call: fake-store-api.listcartsbyuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: fake-store-api.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n \
  \     operations:\n      - method: POST\n        name: createuser\n        description: Create a user\n        call: fake-store-api.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get a user\n        call: fake-store-api.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: replaceuser\n      operations:\n      - method: PUT\n        name: replaceuser\n        description: Replace a user\n        call: fake-store-api.replaceuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: Partially update a user\n        call: fake-store-api.updateuser\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /users/{id}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete a user\n        call: fake-store-api.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Login\n        call: fake-store-api.login\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fake-store-api-mcp\n    transport: http\n    description: MCP adapter for Fake Store API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.listproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproduct\n      description:\
  \ Create a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.createproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Get a product\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.getproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replaceproduct\n      description: Replace a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fake-store-api.replaceproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproduct\n      description: Partially update a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.updateproduct\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: deleteproduct\n      description: Delete a product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fake-store-api.deleteproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List product categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.listcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproductsbycategory\n      description: List products in a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.listproductsbycategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcarts\n      description: List carts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: fake-store-api.listcarts\n      with:\n        startdate: tools.startdate\n        enddate: tools.enddate\n      inputParameters:\n      - name: startdate\n        type: string\n        description: Start date for filtering carts\n      - name: enddate\n        type: string\n        description: End date for filtering carts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcart\n      description: Create a cart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.createcart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcart\n      description: Get a cart\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.getcart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacecart\n      description: Replace a cart\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n        idempotent: true\n      call: fake-store-api.replacecart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecart\n      description: Partially update a cart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.updatecart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecart\n      description: Delete a cart\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fake-store-api.deletecart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcartsbyuser\n      description: List carts for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.listcartsbyuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n\
  \      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fake-store-api.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replaceuser\n      description: Replace a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fake-store-api.replaceuser\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: updateuser\n      description: Partially update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fake-store-api.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: login\n      description: Login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fake-store-api.login\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fake-store-api/refs/heads/main/capabilities/fake-store-api-capability.yaml
tags:
- Fake
- Store
- Api
- API
tools:
- description: List products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Create a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: Get a product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Replace a product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceproduct
- description: Partially update a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproduct
- description: Delete a product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: List product categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: List products in a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproductsbycategory
- description: List carts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcarts
- description: Create a cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcart
- description: Get a cart
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcart
- description: Replace a cart
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacecart
- description: Partially update a cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecart
- description: Delete a cart
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecart
- description: List carts for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcartsbyuser
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Replace a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceuser
- description: Partially update a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
---
