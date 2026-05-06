---
categories: []
consumed_apis: []
description: Want some cool gear, to go with your cool code? We've got you covered. Buy a t-shirt, hoodie or other merchandise from our store to show your support for pb33f.
layout: capability
name: Princess Beef Heavy Industries pb33f Giftshop API
operations:
- description: Princess Beef Heavy Industries Create a new product.
  method: POST
  name: createproduct
  path: /products
- description: Princess Beef Heavy Industries Get a list of all products.
  method: GET
  name: getallproducts
  path: /products
- description: Princess Beef Heavy Industries Get a product by its `id` or `shortCode`
  method: GET
  name: getproductbyid
  path: /products/{id}
- description: Princess Beef Heavy Industries Remove a product
  method: DELETE
  name: deleteproduct
  path: /products/{id}
- description: Princess Beef Heavy Industries Update a product
  method: POST
  name: updateproductbyid
  path: /products/{id}
- description: Princess Beef Heavy Industries Search products.
  method: GET
  name: searchproducts
  path: /search
personas: []
provider_name: Princess Beef Heavy Industries
provider_slug: princess-beef-heavy-industries
search_terms:
- princess beef heavy industries get a list of all products.
- industries
- updateproductbyid
- getproductbyid
- princess beef heavy industries update a product
- princess beef heavy industries remove a product
- deleteproduct
- createproduct
- princess beef heavy industries create a new product.
- princess
- heavy
- commerce
- documentation
- beef
- getallproducts
- api
- searchproducts
- rules
- platform
- products
- governance
- princess beef heavy industries search products.
- princess beef heavy industries get a product by its `id` or `shortcode`
- editors
slug: princess-beef-heavy-industries-capability
source_filename: princess-beef-heavy-industries-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Princess Beef Heavy Industries pb33f Giftshop API\n  description: Want some cool gear, to go with your cool code? We've got you covered. Buy a t-shirt, hoodie or other merchandise\n    from our store to show your support for pb33f.\n  tags:\n  - Princess\n  - Beef\n  - Heavy\n  - Industries\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: princess-beef-heavy-industries\n    baseUri: https://api.pb33f.io/wiretap/giftshop\n    description: Princess Beef Heavy Industries pb33f Giftshop API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{PRINCESS_BEEF_HEAVY_INDUSTRIES_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: createproduct\n        method: POST\n        description: Princess Beef Heavy Industries Create a new product.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getallproducts\n        method: GET\n        description: Princess Beef Heavy Industries Get a list of all products.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-id\n      path: /products/{id}\n      operations:\n      - name: getproductbyid\n        method: GET\n        description: Princess Beef Heavy Industries Get a product by its `id` or `shortCode`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Princess Beef Heavy Industries Remove a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproductbyid\n        method: POST\n\
  \        description: Princess Beef Heavy Industries Update a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: searchproducts\n        method: GET\n        description: Princess Beef Heavy Industries Search products.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: princess-beef-heavy-industries-rest\n    description: REST adapter for Princess Beef Heavy Industries pb33f Giftshop API.\n    resources:\n    - path: /products\n      name: createproduct\n      operations:\n      - method: POST\n        name: createproduct\n        description: Princess Beef Heavy Industries Create a new product.\n        call: princess-beef-heavy-industries.createproduct\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /products\n      name: getallproducts\n      operations:\n      - method: GET\n        name: getallproducts\n        description: Princess Beef Heavy Industries Get a list of all products.\n        call: princess-beef-heavy-industries.getallproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: getproductbyid\n      operations:\n      - method: GET\n        name: getproductbyid\n        description: Princess Beef Heavy Industries Get a product by its `id` or `shortCode`\n        call: princess-beef-heavy-industries.getproductbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: deleteproduct\n      operations:\n      - method: DELETE\n        name: deleteproduct\n        description: Princess Beef Heavy Industries Remove a product\n        call: princess-beef-heavy-industries.deleteproduct\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /products/{id}\n      name: updateproductbyid\n      operations:\n      - method: POST\n        name: updateproductbyid\n        description: Princess Beef Heavy Industries Update a product\n        call: princess-beef-heavy-industries.updateproductbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: searchproducts\n      operations:\n      - method: GET\n        name: searchproducts\n        description: Princess Beef Heavy Industries Search products.\n        call: princess-beef-heavy-industries.searchproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: princess-beef-heavy-industries-mcp\n    transport: http\n    description: MCP adapter for Princess Beef Heavy Industries pb33f Giftshop API for AI agent use.\n    tools:\n    - name: createproduct\n      description: Princess Beef Heavy Industries\
  \ Create a new product.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: princess-beef-heavy-industries.createproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getallproducts\n      description: Princess Beef Heavy Industries Get a list of all products.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: princess-beef-heavy-industries.getallproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductbyid\n      description: Princess Beef Heavy Industries Get a product by its `id` or `shortCode`\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: princess-beef-heavy-industries.getproductbyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproduct\n      description: Princess Beef Heavy Industries Remove a product\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: princess-beef-heavy-industries.deleteproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproductbyid\n      description: Princess Beef Heavy Industries Update a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: princess-beef-heavy-industries.updateproductbyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchproducts\n      description: Princess Beef Heavy Industries Search products.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: princess-beef-heavy-industries.searchproducts\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PRINCESS_BEEF_HEAVY_INDUSTRIES_TOKEN: PRINCESS_BEEF_HEAVY_INDUSTRIES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/princess-beef-heavy-industries/refs/heads/main/capabilities/princess-beef-heavy-industries-capability.yaml
tags:
- Princess
- Beef
- Heavy
- Industries
- API
tools:
- description: Princess Beef Heavy Industries Create a new product.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: Princess Beef Heavy Industries Get a list of all products.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallproducts
- description: Princess Beef Heavy Industries Get a product by its `id` or `shortCode`
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductbyid
- description: Princess Beef Heavy Industries Remove a product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: Princess Beef Heavy Industries Update a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproductbyid
- description: Princess Beef Heavy Industries Search products.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchproducts
---
