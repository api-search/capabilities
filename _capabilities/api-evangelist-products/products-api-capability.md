---
categories: []
consumed_apis: []
description: This is a template APIs.json for a products API, to be used in storytelling, training, and knowledge bases.
layout: capability
name: Products API
operations:
- description: Retrieves Products
  method: GET
  name: getproducts
  path: /products
- description: Products Create Product
  method: POST
  name: createproduct
  path: /products
- description: Products Retrieve Product
  method: GET
  name: getproduct
  path: /products/{productId}
- description: Products Update Product
  method: PUT
  name: updateproduct
  path: /products/{productId}
- description: Products Delete Product
  method: DELETE
  name: deleteproduct
  path: /products/{productId}
- description: Products Cancel Product
  method: PUT
  name: sendproduct
  path: /products/{productId}/cancle
personas: []
provider_name: Products
provider_slug: api-evangelist-products
search_terms:
- deleteproduct
- products create product
- products retrieve product
- updateproduct
- retrieves products
- getproducts
- application programming interface
- sendproduct
- createproduct
- products
- products delete product
- api
- products cancel product
- products update product
- getproduct
slug: products-api-capability
source_filename: products-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Products API\n  description: This is a template APIs.json for a products API, to be used in storytelling, training, and knowledge bases.\n  tags:\n  - Products\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: products-api\n    baseUri: https://api.example.com\n    description: Products API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{PRODUCTS_API_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: getproducts\n        method: GET\n        description: Retrieves Products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproduct\n        method: POST\n        description: Products Create Product\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: products-productid\n      path: /products/{productId}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Products Retrieve Product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproduct\n        method: PUT\n        description: Products Update Product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Products Delete Product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-productid-cancle\n      path: /products/{productId}/cancle\n      operations:\n      - name: sendproduct\n        method: PUT\n        description: Products\
  \ Cancel Product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: products-api-rest\n    description: REST adapter for Products API.\n    resources:\n    - path: /products\n      name: getproducts\n      operations:\n      - method: GET\n        name: getproducts\n        description: Retrieves Products\n        call: products-api.getproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: createproduct\n      operations:\n      - method: POST\n        name: createproduct\n        description: Products Create Product\n        call: products-api.createproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{productId}\n      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Products Retrieve\
  \ Product\n        call: products-api.getproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{productId}\n      name: updateproduct\n      operations:\n      - method: PUT\n        name: updateproduct\n        description: Products Update Product\n        call: products-api.updateproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{productId}\n      name: deleteproduct\n      operations:\n      - method: DELETE\n        name: deleteproduct\n        description: Products Delete Product\n        call: products-api.deleteproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{productId}/cancle\n      name: sendproduct\n      operations:\n      - method: PUT\n        name: sendproduct\n        description: Products Cancel Product\n        call: products-api.sendproduct\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: products-api-mcp\n    transport: http\n    description: MCP adapter for Products API for AI agent use.\n    tools:\n    - name: getproducts\n      description: Retrieves Products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: products-api.getproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproduct\n      description: Products Create Product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: products-api.createproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Products Retrieve Product\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: products-api.getproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproduct\n  \
  \    description: Products Update Product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: products-api.updateproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproduct\n      description: Products Delete Product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: products-api.deleteproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendproduct\n      description: Products Cancel Product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: products-api.sendproduct\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PRODUCTS_API_TOKEN: PRODUCTS_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-evangelist-products/refs/heads/main/capabilities/products-api-capability.yaml
tags:
- Products
- Api
- API
tools:
- description: Retrieves Products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproducts
- description: Products Create Product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: Products Retrieve Product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Products Update Product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproduct
- description: Products Delete Product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: Products Cancel Product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendproduct
---
