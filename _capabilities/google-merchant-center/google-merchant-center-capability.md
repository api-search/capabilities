---
categories: []
consumed_apis: []
description: The Google Merchant API enables programmatic management of Merchant Center accounts including products, inventories, promotions, reports, conversions, and order tracking for Google Shopping.
layout: capability
name: Google Merchant Center Google Merchant API
operations:
- description: Google Merchant Center List accounts
  method: GET
  name: listaccounts
  path: /accounts/v1/{parent}/accounts
- description: Google Merchant Center Insert product input
  method: POST
  name: insertproductinput
  path: /products/v1/{parent}/productInputs
- description: Google Merchant Center Get product
  method: GET
  name: getproduct
  path: /products/v1/{name}
- description: Google Merchant Center Insert local inventory
  method: POST
  name: insertlocalinventory
  path: /inventories/v1/{parent}/localInventories
- description: Google Merchant Center List promotions
  method: GET
  name: listpromotions
  path: /promotions/v1/{parent}/promotions
- description: Google Merchant Center Create promotion
  method: POST
  name: createpromotion
  path: /promotions/v1/{parent}/promotions
- description: Google Merchant Center Search reports
  method: POST
  name: searchreports
  path: /reports/v1/{parent}/reports:search
personas: []
provider_name: Google Merchant Center
provider_slug: google-merchant-center
search_terms:
- insertproductinput
- listaccounts
- google merchant center create promotion
- google merchant center list accounts
- createpromotion
- google merchant center list promotions
- listpromotions
- google
- e-commerce
- center
- google shopping
- google merchant center search reports
- inventory
- google merchant center insert product input
- api
- google merchant center insert local inventory
- promotions
- insertlocalinventory
- shopping
- products
- google merchant center get product
- merchant center
- getproduct
- merchant
- searchreports
slug: google-merchant-center-capability
source_filename: google-merchant-center-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Merchant Center Google Merchant API\n  description: The Google Merchant API enables programmatic management of Merchant Center accounts including products, inventories,\n    promotions, reports, conversions, and order tracking for Google Shopping.\n  tags:\n  - Google\n  - Merchant\n  - Center\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-merchant-center\n    baseUri: https://merchantapi.googleapis.com\n    description: Google Merchant Center Google Merchant API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_MERCHANT_CENTER_TOKEN}}'\n    resources:\n    - name: accounts-v1-parent-accounts\n      path: /accounts/v1/{parent}/accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Google Merchant Center List accounts\n        inputParameters:\n        - name: parent\n          in: path\n\
  \          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-v1-parent-productinputs\n      path: /products/v1/{parent}/productInputs\n      operations:\n      - name: insertproductinput\n        method: POST\n        description: Google Merchant Center Insert product input\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-v1-name\n      path: /products/v1/{name}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Google Merchant Center Get product\n        inputParameters:\n\
  \        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventories-v1-parent-localinventories\n      path: /inventories/v1/{parent}/localInventories\n      operations:\n      - name: insertlocalinventory\n        method: POST\n        description: Google Merchant Center Insert local inventory\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: promotions-v1-parent-promotions\n      path: /promotions/v1/{parent}/promotions\n      operations:\n      - name: listpromotions\n        method: GET\n        description: Google Merchant Center List promotions\n        inputParameters:\n        - name: parent\n      \
  \    in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpromotion\n        method: POST\n        description: Google Merchant Center Create promotion\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-v1-parent-reports-search\n      path: /reports/v1/{parent}/reports:search\n      operations:\n      - name: searchreports\n        method: POST\n        description: Google Merchant Center Search reports\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-merchant-center-rest\n    description: REST adapter for Google Merchant Center Google Merchant API.\n    resources:\n    - path: /accounts/v1/{parent}/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Google Merchant Center List accounts\n        call: google-merchant-center.listaccounts\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/v1/{parent}/productInputs\n      name: insertproductinput\n      operations:\n      - method: POST\n        name: insertproductinput\n        description: Google Merchant Center Insert product input\n        call: google-merchant-center.insertproductinput\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products/v1/{name}\n\
  \      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Google Merchant Center Get product\n        call: google-merchant-center.getproduct\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventories/v1/{parent}/localInventories\n      name: insertlocalinventory\n      operations:\n      - method: POST\n        name: insertlocalinventory\n        description: Google Merchant Center Insert local inventory\n        call: google-merchant-center.insertlocalinventory\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /promotions/v1/{parent}/promotions\n      name: listpromotions\n      operations:\n      - method: GET\n        name: listpromotions\n        description: Google Merchant Center List promotions\n        call: google-merchant-center.listpromotions\n        with:\n\
  \          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /promotions/v1/{parent}/promotions\n      name: createpromotion\n      operations:\n      - method: POST\n        name: createpromotion\n        description: Google Merchant Center Create promotion\n        call: google-merchant-center.createpromotion\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/v1/{parent}/reports:search\n      name: searchreports\n      operations:\n      - method: POST\n        name: searchreports\n        description: Google Merchant Center Search reports\n        call: google-merchant-center.searchreports\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-merchant-center-mcp\n    transport: http\n    description: MCP adapter for Google\
  \ Merchant Center Google Merchant API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: Google Merchant Center List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-merchant-center.listaccounts\n      with:\n        parent: tools.parent\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertproductinput\n      description: Google Merchant Center Insert product input\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-merchant-center.insertproductinput\n  \
  \    with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Google Merchant Center Get product\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-merchant-center.getproduct\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertlocalinventory\n      description: Google Merchant Center Insert local inventory\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-merchant-center.insertlocalinventory\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name:\
  \ parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpromotions\n      description: Google Merchant Center List promotions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-merchant-center.listpromotions\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpromotion\n      description: Google Merchant Center Create promotion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-merchant-center.createpromotion\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchreports\n      description: Google Merchant Center Search reports\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-merchant-center.searchreports\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_MERCHANT_CENTER_TOKEN: GOOGLE_MERCHANT_CENTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-merchant-center/refs/heads/main/capabilities/google-merchant-center-capability.yaml
tags:
- Google
- Merchant
- Center
- API
tools:
- description: Google Merchant Center List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Google Merchant Center Insert product input
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertproductinput
- description: Google Merchant Center Get product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Google Merchant Center Insert local inventory
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertlocalinventory
- description: Google Merchant Center List promotions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpromotions
- description: Google Merchant Center Create promotion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpromotion
- description: Google Merchant Center Search reports
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchreports
---
