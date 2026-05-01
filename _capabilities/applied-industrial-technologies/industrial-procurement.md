---
categories:
- procurement-supply-chain
consumed_apis:
- ait
description: Workflow capability for industrial product procurement using the Applied Industrial Technologies catalog. Combines product search and order management for procurement teams sourcing bearings, power transmission, and fluid power components.
layout: capability
name: Applied Industrial Technologies Procurement
operations: []
personas: []
provider_name: Applied Industrial Technologies
provider_slug: applied-industrial-technologies
search_terms:
- places a purchase order for industrial products with shipping address
- lists existing purchase orders for the authenticated account
- bearings
- supply chain
- sources replacement parts and components for equipment maintenance
- place order
- list orders
- fluid power
- search products
- gets detailed specifications for a specific industrial product
- industrial distribution
- browsing and searching the industrial product catalog
- manages industrial component sourcing and purchase orders
- end-to-end workflow for sourcing and ordering industrial components
- get product details
- procurement
- searches the applied industrial technologies product catalog by category or manufacturer
- power transmission
- creating and tracking purchase orders
- applied industrial technologies
slug: industrial-procurement
source_filename: industrial-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Applied Industrial Technologies Procurement\n  description: >-\n    Workflow capability for industrial product procurement using the Applied Industrial\n    Technologies catalog. Combines product search and order management for procurement\n    teams sourcing bearings, power transmission, and fluid power components.\n  tags:\n    - Applied Industrial Technologies\n    - Industrial Distribution\n    - Procurement\n    - Supply Chain\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AIT_API_TOKEN: AIT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: ait\n      location: ./shared/applied-industrial-technologies-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: industrial-procurement-mcp\n      transport: http\n      description: MCP server for AI-assisted industrial procurement workflows.\n      tools:\n        - name: search-products\n          description:\
  \ Searches the Applied Industrial Technologies product catalog by category or manufacturer\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ait.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-details\n          description: Gets detailed specifications for a specific industrial product\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ait.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: place-order\n          description: Places a purchase order for industrial products with shipping address\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ait.create-order\"\n          with:\n            items: \"tools.items\"\n            shippingAddress:\
  \ \"tools.shippingAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-orders\n          description: Lists existing purchase orders for the authenticated account\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ait.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
