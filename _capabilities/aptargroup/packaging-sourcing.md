---
categories:
- procurement-supply-chain
consumed_apis: []
description: Workflow capability for sourcing dispensing and packaging solutions from AptarGroup. Supports product development teams browsing sustainable packaging options and requesting samples for beauty, pharmaceutical, and food products.
layout: capability
name: AptarGroup Packaging Sourcing
operations: []
personas: []
provider_name: AptarGroup
provider_slug: aptargroup
search_terms:
- sustainability
- gets detailed specifications for a specific aptargroup packaging product
- browse and sample sustainable packaging solutions from aptargroup
- aptargroup
- requesting and tracking product samples for evaluation
- consumer goods
- order packaging samples
- product development
- evaluates and sources packaging solutions for consumer products
- submits a sample request for aptargroup packaging evaluation
- packaging
- manages packaging supplier relationships and sample requests
- manufacturing
- get packaging specs
- dispensing
- finds sustainable dispensing and packaging solutions from aptargroup
- browsing dispensing and packaging product options
- find sustainable packaging
slug: packaging-sourcing
source_filename: packaging-sourcing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AptarGroup Packaging Sourcing\n  description: Workflow capability for sourcing dispensing and packaging solutions from AptarGroup. Supports product development\n    teams browsing sustainable packaging options and requesting samples for beauty, pharmaceutical, and food products.\n  tags:\n  - AptarGroup\n  - Packaging\n  - Product Development\n  - Sustainability\n  - Manufacturing\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APTAR_API_TOKEN: APTAR_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aptar\n    baseUri: https://api.aptargroup.com/v1\n    description: AptarGroup product catalog API\n    authentication:\n      type: bearer\n      token: '{{APTAR_API_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Dispensing and packaging product catalog\n      operations:\n      - name: list-products\n        method: GET\n        description:\
  \ Returns a list of products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Returns a specific product\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Sample request management\n      operations:\n      - name: create-sample-request\n        method: POST\n        description: Creates a product sample request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            productId: '{{tools.productId}}'\n     \
  \       quantity: '{{tools.quantity}}'\n            contactEmail: '{{tools.contactEmail}}'\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: packaging-sourcing-mcp\n    transport: http\n    description: MCP server for AI-assisted packaging sourcing from AptarGroup.\n    tools:\n    - name: find-sustainable-packaging\n      description: Finds sustainable dispensing and packaging solutions from AptarGroup\n      hints:\n        readOnly: true\n        idempotent: true\n      call: aptar.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-packaging-specs\n      description: Gets detailed specifications for a specific AptarGroup packaging product\n      hints:\n        readOnly: true\n        idempotent: true\n      call: aptar.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: order-packaging-samples\n      description: Submits a sample request\
  \ for AptarGroup packaging evaluation\n      hints:\n        readOnly: false\n        destructive: false\n      call: aptar.create-sample-request\n      with:\n        productId: tools.productId\n        quantity: tools.quantity\n        contactEmail: tools.contactEmail\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aptargroup/refs/heads/main/capabilities/packaging-sourcing.yaml
tags:
- AptarGroup
- Packaging
- Product Development
- Sustainability
- Manufacturing
tools:
- description: Finds sustainable dispensing and packaging solutions from AptarGroup
  hints:
    idempotent: true
    readOnly: true
  name: find-sustainable-packaging
- description: Gets detailed specifications for a specific AptarGroup packaging product
  hints:
    idempotent: true
    readOnly: true
  name: get-packaging-specs
- description: Submits a sample request for AptarGroup packaging evaluation
  hints:
    destructive: false
    readOnly: false
  name: order-packaging-samples
---
