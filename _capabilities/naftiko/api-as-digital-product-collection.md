---
categories: []
consumed_apis: []
description: A collection capability shaping APIs as digital products with consumption metrics, lifecycle stage, and ownership exposed in one shaped object.
layout: capability
name: Api As Digital Product Collection
operations:
- description: List APIs as digital products.
  method: GET
  name: list-products
  path: /products
- description: Get an API product with metrics, lifecycle, ownership.
  method: GET
  name: get-product
  path: /products/{{product_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- api product
- governance
- spec-driven integration
- get an api product.
- collection
- get product
- list products
- get an api product with metrics, lifecycle, ownership.
- ai
- capabilities
- api integration
- list api products.
- mcp
- list apis as digital products.
- naftiko
slug: api-as-digital-product-collection
source_filename: api-as-digital-product-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api As Digital Product Collection\n  description: A collection capability shaping APIs as digital products with consumption metrics, lifecycle stage, and ownership exposed in one shaped object.\n  tags: [Naftiko, API Product, Collection]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: products, path: /v1/products, operations: [{name: list-products, method: GET}]}\n    - name: product\n      path: /v1/products/{{product_id}}\n      operations:\n      - {name: get-product, method: GET, inputParameters: [{name: product_id, in: path}]}\n    - name: product-metrics\n      path: /v1/products/{{product_id}}/metrics\n      operations:\n      - {name: get-product-metrics,\
  \ method: GET, inputParameters: [{name: product_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-as-digital-product-collection-rest\n    description: REST surface for browsing APIs as digital products.\n    resources:\n    - name: products\n      path: /products\n      operations: [{method: GET, name: list-products, description: List APIs as digital products., call: naftiko-control.list-products}]\n    - name: product\n      path: /products/{{product_id}}\n      operations:\n      - method: GET\n        name: get-product\n        description: Get an API product with metrics, lifecycle, ownership.\n        inputParameters: [{name: product_id, in: path, type: string}]\n        call: naftiko-control.get-product\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-as-digital-product-collection-mcp\n    description: MCP server for API-as-product browsing.\n    tools:\n    - {name: list-products, description: List API products.,\
  \ hints: {readOnly: true}, call: naftiko-control.list-products}\n    - name: get-product\n      description: Get an API product.\n      hints: {readOnly: true}\n      inputParameters: [{name: product_id, type: string, required: true}]\n      call: naftiko-control.get-product\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-as-digital-product-collection-skills\n    description: Skill bundle for API-as-product workflows.\n    skills:\n    - name: api-as-digital-product-collection\n      description: API-as-product browsing and metrics.\n      location: file:///opt/naftiko/skills/api-as-digital-product-collection\n      allowed-tools: list-products,get-product\n      tools:\n      - {name: list-products, from: {sourceNamespace: api-as-digital-product-collection-mcp, action: list-products}}\n      - {name: get-product, from: {sourceNamespace: api-as-digital-product-collection-mcp, action: get-product}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-as-digital-product-collection.yaml
tags:
- Naftiko
- API Product
- Collection
tools:
- description: List API products.
  hints:
    readOnly: true
  name: list-products
- description: Get an API product.
  hints:
    readOnly: true
  name: get-product
---
