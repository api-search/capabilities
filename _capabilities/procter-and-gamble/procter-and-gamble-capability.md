---
categories: []
consumed_apis: []
description: The Procter & Gamble API Marketplace provides access to P&G's suite of APIs for partners, suppliers, and developers. The platform enables integration with P&G's supply chain, product data, and business operations for building applications that interact with P&G systems.
layout: capability
name: Procter & Gamble API Marketplace
operations:
- description: List products
  method: GET
  name: listproducts
  path: /products
- description: List shipments
  method: GET
  name: listshipments
  path: /supply-chain/shipments
- description: List orders
  method: GET
  name: listorders
  path: /orders
personas: []
provider_name: Procter & Gamble
provider_slug: procter-and-gamble
search_terms:
- procter
- consumer goods
- listproducts
- listshipments
- gamble
- and
- retail
- list products
- api
- manufacturing
- listorders
- list shipments
- list orders
- supply chain
slug: procter-and-gamble-capability
source_filename: procter-and-gamble-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Procter & Gamble API Marketplace\n  description: The Procter & Gamble API Marketplace provides access to P&G's suite of APIs for partners, suppliers, and developers.\n    The platform enables integration with P&G's supply chain, product data, and business operations for building applications\n    that interact with P&G systems.\n  tags:\n  - Procter\n  - And\n  - Gamble\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: procter-and-gamble\n    baseUri: https://developer.pg.com/api\n    description: Procter & Gamble API Marketplace HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PROCTER_AND_GAMBLE_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        inputParameters:\n        - name: brand\n          in: query\n          type:\
  \ string\n          description: Filter by brand name.\n        - name: category\n          in: query\n          type: string\n          description: Filter by product category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supply-chain-shipments\n      path: /supply-chain/shipments\n      operations:\n      - name: listshipments\n        method: GET\n        description: List shipments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      operations:\n      - name: listorders\n        method: GET\n        description: List orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: procter-and-gamble-rest\n    description: REST adapter for Procter\
  \ & Gamble API Marketplace.\n    resources:\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n        call: procter-and-gamble.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /supply-chain/shipments\n      name: listshipments\n      operations:\n      - method: GET\n        name: listshipments\n        description: List shipments\n        call: procter-and-gamble.listshipments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: List orders\n        call: procter-and-gamble.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: procter-and-gamble-mcp\n    transport: http\n    description: MCP adapter for Procter\
  \ & Gamble API Marketplace for AI agent use.\n    tools:\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: procter-and-gamble.listproducts\n      with:\n        brand: tools.brand\n        category: tools.category\n      inputParameters:\n      - name: brand\n        type: string\n        description: Filter by brand name.\n      - name: category\n        type: string\n        description: Filter by product category.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshipments\n      description: List shipments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: procter-and-gamble.listshipments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: List orders\n      hints:\n        readOnly: true\n        destructive: false\n    \
  \    idempotent: true\n      call: procter-and-gamble.listorders\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PROCTER_AND_GAMBLE_TOKEN: PROCTER_AND_GAMBLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/procter-and-gamble/refs/heads/main/capabilities/procter-and-gamble-capability.yaml
tags:
- Procter
- And
- Gamble
- API
tools:
- description: List products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: List shipments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshipments
- description: List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
---
