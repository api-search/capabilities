---
categories:
- procurement-supply-chain
consumed_apis:
- aptar
description: Workflow capability for sourcing dispensing and packaging solutions from AptarGroup. Supports product development teams browsing sustainable packaging options and requesting samples for beauty, pharmaceutical, and food products.
layout: capability
name: AptarGroup Packaging Sourcing
operations: []
personas: []
provider_name: AptarGroup
provider_slug: aptargroup
search_terms:
- dispensing
- browse and sample sustainable packaging solutions from aptargroup
- aptargroup
- submits a sample request for aptargroup packaging evaluation
- manages packaging supplier relationships and sample requests
- sustainability
- manufacturing
- consumer goods
- evaluates and sources packaging solutions for consumer products
- browsing dispensing and packaging product options
- product development
- finds sustainable dispensing and packaging solutions from aptargroup
- gets detailed specifications for a specific aptargroup packaging product
- get packaging specs
- requesting and tracking product samples for evaluation
- find sustainable packaging
- order packaging samples
- packaging
slug: packaging-sourcing
source_filename: packaging-sourcing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: AptarGroup Packaging Sourcing\n  description: >-\n    Workflow capability for sourcing dispensing and packaging solutions from\n    AptarGroup. Supports product development teams browsing sustainable packaging\n    options and requesting samples for beauty, pharmaceutical, and food products.\n  tags:\n    - AptarGroup\n    - Packaging\n    - Product Development\n    - Sustainability\n    - Manufacturing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APTAR_API_TOKEN: APTAR_API_TOKEN\n\ncapability:\n  consumes:\n    - import: aptar\n      location: ./shared/aptargroup-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: packaging-sourcing-mcp\n      transport: http\n      description: MCP server for AI-assisted packaging sourcing from AptarGroup.\n      tools:\n        - name: find-sustainable-packaging\n          description: Finds sustainable dispensing\
  \ and packaging solutions from AptarGroup\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aptar.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-packaging-specs\n          description: Gets detailed specifications for a specific AptarGroup packaging product\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aptar.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: order-packaging-samples\n          description: Submits a sample request for AptarGroup packaging evaluation\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"aptar.create-sample-request\"\n          with:\n            productId: \"tools.productId\"\n            quantity: \"tools.quantity\"\
  \n            contactEmail: \"tools.contactEmail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
