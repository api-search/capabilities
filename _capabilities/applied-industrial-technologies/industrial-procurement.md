---
categories:
- procurement-supply-chain
consumed_apis: []
description: Workflow capability for industrial product procurement using the Applied Industrial Technologies catalog. Combines product search and order management for procurement teams sourcing bearings, power transmission, and fluid power components.
layout: capability
name: Applied Industrial Technologies Procurement
operations: []
personas: []
provider_name: Applied Industrial Technologies
provider_slug: applied-industrial-technologies
search_terms:
- procurement
- gets detailed specifications for a specific industrial product
- lists existing purchase orders for the authenticated account
- get product details
- applied industrial technologies
- places a purchase order for industrial products with shipping address
- supply chain
- manages industrial component sourcing and purchase orders
- industrial distribution
- browsing and searching the industrial product catalog
- creating and tracking purchase orders
- power transmission
- list orders
- sources replacement parts and components for equipment maintenance
- bearings
- searches the applied industrial technologies product catalog by category or manufacturer
- fluid power
- place order
- end-to-end workflow for sourcing and ordering industrial components
- search products
slug: industrial-procurement
source_filename: industrial-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Applied Industrial Technologies Procurement\n  description: Workflow capability for industrial product procurement using the Applied Industrial Technologies catalog. Combines\n    product search and order management for procurement teams sourcing bearings, power transmission, and fluid power components.\n  tags:\n  - Applied Industrial Technologies\n  - Industrial Distribution\n  - Procurement\n  - Supply Chain\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AIT_API_TOKEN: AIT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ait\n    baseUri: https://api.applied-industrial-technologies.com/v1\n    description: Applied Industrial Technologies product catalog and order API\n    authentication:\n      type: bearer\n      token: '{{AIT_API_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Industrial product catalog\n      operations:\n   \
  \   - name: list-products\n        method: GET\n        description: Returns a list of industrial products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Returns a specific product by ID\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Purchase order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: Returns a list of purchase orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n   \
  \     method: POST\n        description: Creates a new purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n            shippingAddress: '{{tools.shippingAddress}}'\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: industrial-procurement-mcp\n    transport: http\n    description: MCP server for AI-assisted industrial procurement workflows.\n    tools:\n    - name: search-products\n      description: Searches the Applied Industrial Technologies product catalog by category or manufacturer\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ait.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-details\n      description: Gets detailed specifications for a specific industrial product\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: ait.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Places a purchase order for industrial products with shipping address\n      hints:\n        readOnly: false\n        destructive: false\n      call: ait.create-order\n      with:\n        items: tools.items\n        shippingAddress: tools.shippingAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: Lists existing purchase orders for the authenticated account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ait.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/applied-industrial-technologies/refs/heads/main/capabilities/industrial-procurement.yaml
tags:
- Applied Industrial Technologies
- Industrial Distribution
- Procurement
- Supply Chain
tools:
- description: Searches the Applied Industrial Technologies product catalog by category or manufacturer
  hints:
    idempotent: true
    readOnly: true
  name: search-products
- description: Gets detailed specifications for a specific industrial product
  hints:
    idempotent: true
    readOnly: true
  name: get-product-details
- description: Places a purchase order for industrial products with shipping address
  hints:
    destructive: false
    readOnly: false
  name: place-order
- description: Lists existing purchase orders for the authenticated account
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
---
