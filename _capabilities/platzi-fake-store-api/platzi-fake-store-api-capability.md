---
categories: []
consumed_apis: []
description: A free, fake REST API for testing and prototyping e-commerce or shopping site applications. Provides products, categories, users, files, and JWT authentication endpoints.
layout: capability
name: Platzi Fake Store API
operations:
- description: List products
  method: GET
  name: listproducts
  path: /products
- description: Create product
  method: POST
  name: createproduct
  path: /products
- description: Get product by id
  method: GET
  name: getproduct
  path: /products/{id}
- description: Update product
  method: PUT
  name: updateproduct
  path: /products/{id}
- description: Delete product
  method: DELETE
  name: deleteproduct
  path: /products/{id}
- description: Get product by slug
  method: GET
  name: getproductbyslug
  path: /products/slug/{slug}
- description: Get related products by id
  method: GET
  name: getrelatedproducts
  path: /products/{id}/related
- description: Get related products by slug
  method: GET
  name: getrelatedproductsbyslug
  path: /products/slug/{slug}/related
- description: List categories
  method: GET
  name: listcategories
  path: /categories
- description: Create category
  method: POST
  name: createcategory
  path: /categories
- description: Get category
  method: GET
  name: getcategory
  path: /categories/{id}
- description: Update category
  method: PUT
  name: updatecategory
  path: /categories/{id}
- description: Delete category
  method: DELETE
  name: deletecategory
  path: /categories/{id}
- description: Get category by slug
  method: GET
  name: getcategorybyslug
  path: /categories/slug/{slug}
- description: List products in a category
  method: GET
  name: listcategoryproducts
  path: /categories/{id}/products
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create user
  method: POST
  name: createuser
  path: /users
- description: Get user
  method: GET
  name: getuser
  path: /users/{id}
- description: Update user
  method: PUT
  name: updateuser
  path: /users/{id}
- description: Check email availability
  method: POST
  name: checkemailavailability
  path: /users/is-available
- description: Login and obtain JWT tokens
  method: POST
  name: login
  path: /auth/login
- description: Get authenticated user profile
  method: GET
  name: getprofile
  path: /auth/profile
- description: Refresh access token
  method: POST
  name: refreshtoken
  path: /auth/refresh-token
- description: Upload a file
  method: POST
  name: uploadfile
  path: /files/upload
- description: Retrieve uploaded file
  method: GET
  name: getfile
  path: /files/{filename}
personas: []
provider_name: Platzi Fake Store API
provider_slug: platzi-fake-store-api
search_terms:
- updateproduct
- create category
- sample data
- testing
- get authenticated user profile
- listcategories
- create product
- createproduct
- list products
- api
- getproductbyslug
- update user
- getcategory
- sandbox
- getfile
- updatecategory
- delete product
- get product by slug
- upload a file
- ecommerce
- get product by id
- refresh access token
- getrelatedproducts
- update product
- platzi
- uploadfile
- list categories
- getuser
- login and obtain jwt tokens
- retrieve uploaded file
- login
- fake api
- store
- getproduct
- deleteproduct
- get related products by slug
- createcategory
- list users
- update category
- refreshtoken
- getprofile
- get category
- get category by slug
- get related products by id
- listproducts
- updateuser
- get user
- listcategoryproducts
- list products in a category
- createuser
- delete category
- getcategorybyslug
- listusers
- create user
- checkemailavailability
- jwt
- prototyping
- deletecategory
- getrelatedproductsbyslug
- fake
- check email availability
slug: platzi-fake-store-api-capability
source_filename: platzi-fake-store-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Platzi Fake Store API\n  description: A free, fake REST API for testing and prototyping e-commerce or shopping site applications. Provides products,\n    categories, users, files, and JWT authentication endpoints.\n  tags:\n  - Platzi\n  - Fake\n  - Store\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: platzi-fake-store-api\n    baseUri: https://api.escuelajs.co/api/v1\n    description: Platzi Fake Store API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PLATZI_FAKE_STORE_API_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        - name: title\n    \
  \      in: query\n          type: string\n        - name: price\n          in: query\n          type: number\n        - name: price_min\n          in: query\n          type: number\n        - name: price_max\n          in: query\n          type: number\n        - name: categoryId\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproduct\n        method: POST\n        description: Create product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-id\n      path: /products/{id}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Get product by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproduct\n        method:\
  \ PUT\n        description: Update product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Delete product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-slug-slug\n      path: /products/slug/{slug}\n      operations:\n      - name: getproductbyslug\n        method: GET\n        description: Get product by slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-id-related\n      path: /products/{id}/related\n      operations:\n      - name: getrelatedproducts\n        method: GET\n        description: Get related products by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: products-slug-slug-related\n      path: /products/slug/{slug}/related\n      operations:\n      - name: getrelatedproductsbyslug\n        method: GET\n        description: Get related products by slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: List categories\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcategory\n        method: POST\n        description: Create category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-id\n      path: /categories/{id}\n\
  \      operations:\n      - name: getcategory\n        method: GET\n        description: Get category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecategory\n        method: PUT\n        description: Update category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecategory\n        method: DELETE\n        description: Delete category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-slug-slug\n      path: /categories/slug/{slug}\n      operations:\n      - name: getcategorybyslug\n        method: GET\n        description: Get category by slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-id-products\n\
  \      path: /categories/{id}/products\n      operations:\n      - name: listcategoryproducts\n        method: GET\n        description: List products in a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-is-available\n      path: /users/is-available\n      operations:\n      - name: checkemailavailability\n        method: POST\n        description: Check email availability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-login\n      path: /auth/login\n      operations:\n      - name: login\n        method: POST\n        description: Login and obtain JWT tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-profile\n      path: /auth/profile\n    \
  \  operations:\n      - name: getprofile\n        method: GET\n        description: Get authenticated user profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-refresh-token\n      path: /auth/refresh-token\n      operations:\n      - name: refreshtoken\n        method: POST\n        description: Refresh access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-upload\n      path: /files/upload\n      operations:\n      - name: uploadfile\n        method: POST\n        description: Upload a file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-filename\n      path: /files/{filename}\n      operations:\n      - name: getfile\n        method: GET\n        description: Retrieve uploaded file\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: platzi-fake-store-api-rest\n    description: REST adapter for Platzi Fake Store API.\n    resources:\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n        call: platzi-fake-store-api.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: createproduct\n      operations:\n      - method: POST\n        name: createproduct\n        description: Create product\n        call: platzi-fake-store-api.createproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Get product by\
  \ id\n        call: platzi-fake-store-api.getproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: updateproduct\n      operations:\n      - method: PUT\n        name: updateproduct\n        description: Update product\n        call: platzi-fake-store-api.updateproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: deleteproduct\n      operations:\n      - method: DELETE\n        name: deleteproduct\n        description: Delete product\n        call: platzi-fake-store-api.deleteproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/slug/{slug}\n      name: getproductbyslug\n      operations:\n      - method: GET\n        name: getproductbyslug\n        description: Get product by slug\n        call: platzi-fake-store-api.getproductbyslug\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /products/{id}/related\n      name: getrelatedproducts\n      operations:\n      - method: GET\n        name: getrelatedproducts\n        description: Get related products by id\n        call: platzi-fake-store-api.getrelatedproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/slug/{slug}/related\n      name: getrelatedproductsbyslug\n      operations:\n      - method: GET\n        name: getrelatedproductsbyslug\n        description: Get related products by slug\n        call: platzi-fake-store-api.getrelatedproductsbyslug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List categories\n        call: platzi-fake-store-api.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories\n      name: createcategory\n\
  \      operations:\n      - method: POST\n        name: createcategory\n        description: Create category\n        call: platzi-fake-store-api.createcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{id}\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Get category\n        call: platzi-fake-store-api.getcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{id}\n      name: updatecategory\n      operations:\n      - method: PUT\n        name: updatecategory\n        description: Update category\n        call: platzi-fake-store-api.updatecategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{id}\n      name: deletecategory\n      operations:\n      - method: DELETE\n        name: deletecategory\n        description: Delete category\n        call: platzi-fake-store-api.deletecategory\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/slug/{slug}\n      name: getcategorybyslug\n      operations:\n      - method: GET\n        name: getcategorybyslug\n        description: Get category by slug\n        call: platzi-fake-store-api.getcategorybyslug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{id}/products\n      name: listcategoryproducts\n      operations:\n      - method: GET\n        name: listcategoryproducts\n        description: List products in a category\n        call: platzi-fake-store-api.listcategoryproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: platzi-fake-store-api.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n\
  \      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create user\n        call: platzi-fake-store-api.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: platzi-fake-store-api.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update user\n        call: platzi-fake-store-api.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/is-available\n      name: checkemailavailability\n      operations:\n      - method: POST\n        name: checkemailavailability\n        description: Check email availability\n        call: platzi-fake-store-api.checkemailavailability\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Login and obtain JWT tokens\n        call: platzi-fake-store-api.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/profile\n      name: getprofile\n      operations:\n      - method: GET\n        name: getprofile\n        description: Get authenticated user profile\n        call: platzi-fake-store-api.getprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/refresh-token\n      name: refreshtoken\n      operations:\n      - method: POST\n        name: refreshtoken\n        description: Refresh access token\n        call: platzi-fake-store-api.refreshtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/upload\n      name: uploadfile\n      operations:\n\
  \      - method: POST\n        name: uploadfile\n        description: Upload a file\n        call: platzi-fake-store-api.uploadfile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{filename}\n      name: getfile\n      operations:\n      - method: GET\n        name: getfile\n        description: Retrieve uploaded file\n        call: platzi-fake-store-api.getfile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: platzi-fake-store-api-mcp\n    transport: http\n    description: MCP adapter for Platzi Fake Store API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.listproducts\n      with:\n        offset: tools.offset\n        limit: tools.limit\n        title: tools.title\n        price: tools.price\n      \
  \  price_min: tools.price_min\n        price_max: tools.price_max\n        categoryId: tools.categoryId\n      inputParameters:\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      - name: title\n        type: string\n        description: title\n      - name: price\n        type: number\n        description: price\n      - name: price_min\n        type: number\n        description: price_min\n      - name: price_max\n        type: number\n        description: price_max\n      - name: categoryId\n        type: integer\n        description: categoryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproduct\n      description: Create product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.createproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: getproduct\n      description: Get product by id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproduct\n      description: Update product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.updateproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproduct\n      description: Delete product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: platzi-fake-store-api.deleteproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductbyslug\n      description: Get product by slug\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getproductbyslug\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelatedproducts\n      description: Get related products by id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getrelatedproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelatedproductsbyslug\n      description: Get related products by slug\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getrelatedproductsbyslug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.listcategories\n      with:\n        limit: tools.limit\n      inputParameters:\n      - name: limit\n        type: integer\n        description:\
  \ limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcategory\n      description: Create category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.createcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Get category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecategory\n      description: Update category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.updatecategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecategory\n      description: Delete category\n      hints:\n        readOnly: false\n   \
  \     destructive: true\n        idempotent: true\n      call: platzi-fake-store-api.deletecategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategorybyslug\n      description: Get category by slug\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getcategorybyslug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategoryproducts\n      description: List products in a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.listcategoryproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.listusers\n      with:\n        limit: tools.limit\n      inputParameters:\n\
  \      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkemailavailability\n      description: Check email availability\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.checkemailavailability\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: login\n      description: Login and obtain JWT tokens\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprofile\n      description: Get authenticated user profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getprofile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refreshtoken\n      description: Refresh access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.refreshtoken\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: uploadfile\n      description: Upload a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: platzi-fake-store-api.uploadfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfile\n      description: Retrieve uploaded file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: platzi-fake-store-api.getfile\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PLATZI_FAKE_STORE_API_TOKEN: PLATZI_FAKE_STORE_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/platzi-fake-store-api/refs/heads/main/capabilities/platzi-fake-store-api-capability.yaml
tags:
- Platzi
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
- description: Create product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: Get product by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Update product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproduct
- description: Delete product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: Get product by slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductbyslug
- description: Get related products by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelatedproducts
- description: Get related products by slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelatedproductsbyslug
- description: List categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: Create category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcategory
- description: Get category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Update category
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecategory
- description: Delete category
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecategory
- description: Get category by slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategorybyslug
- description: List products in a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategoryproducts
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Check email availability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkemailavailability
- description: Login and obtain JWT tokens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Get authenticated user profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofile
- description: Refresh access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refreshtoken
- description: Upload a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfile
- description: Retrieve uploaded file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfile
---
