---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Block Square Commerce
operations: []
personas: []
provider_name: Block
provider_slug: block
search_terms:
- point of sale
- ecommerce
- commerce
- fintech
- square
- cryptocurrency
- payments
slug: block-square-commerce
source_filename: block-square-commerce.yaml
source_heading: Capability Spec
source_yaml: "name: Block Square Commerce\ndescription: >-\n  End-to-end commerce capability for Square sellers including payment processing,\n  order management, catalog browsing, and customer engagement. Supports in-person,\n  online, and omnichannel retail workflows.\nversion: \"1.0\"\npersona:\n  - Retail Sellers\n  - eCommerce Developers\n  - Restaurant Operators\n  - App Integrators\nservers:\n  rest:\n    url: http://localhost:8080\n    protocol: rest\n  mcp:\n    url: http://localhost:9090\n    protocol: mcp\ntools:\n  - name: list-payments\n    operationId: list-payments\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: List payments processed by the Square account.\n  - name: create-payment\n    operationId: create-payment\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: Create a new payment using a card nonce or token.\n  - name: get-payment\n    operationId: get-payment\n    source:\n      capability:\
  \ capabilities/shared/block-square-api.yaml\n    description: Get details for a specific payment by ID.\n  - name: create-order\n    operationId: create-order\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: Create a new order with line items for a location.\n  - name: list-catalog\n    operationId: list-catalog\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: List catalog items and products for a Square account.\n  - name: list-customers\n    operationId: list-customers\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: List customer profiles associated with the Square account.\n  - name: create-customer\n    operationId: create-customer\n    source:\n      capability: capabilities/shared/block-square-api.yaml\n    description: Create a new customer profile for the business.\n  - name: list-locations\n    operationId: list-locations\n    source:\n      capability:\
  \ capabilities/shared/block-square-api.yaml\n    description: List all seller locations for the Square account.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/block/refs/heads/main/capabilities/block-square-commerce.yaml
tags: []
tools: []
---
