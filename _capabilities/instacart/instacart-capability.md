---
categories: []
consumed_apis: []
description: The Instacart Catalog API enables retailers to programmatically manage their product catalogs on the Instacart platform. Retailers can use the API to create or update products and items, with partial updates supported so that only the attributes included in the request body are modified. This API is designed for retailers who need to keep their Instacart product listings synchronized with their inventory management systems, ensuring accurate product information, pricing, and availability across the platform.
layout: capability
name: Instacart Catalog API
operations:
- description: Create or update products
  method: POST
  name: submitproducts
  path: /v2/data_ingestion/catalog/product/submission
- description: Create or update items
  method: POST
  name: submititems
  path: /v2/data_ingestion/catalog/item/submission
personas: []
provider_name: instacart
provider_slug: instacart
search_terms:
- submitproducts
- instacart
- create or update items
- create or update products
- api
- submititems
slug: instacart-capability
source_filename: instacart-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Instacart Catalog API\n  description: The Instacart Catalog API enables retailers to programmatically manage their product catalogs on the Instacart\n    platform. Retailers can use the API to create or update products and items, with partial updates supported so that only\n    the attributes included in the request body are modified. This API is designed for retailers who need to keep their Instacart\n    product listings synchronized with their inventory management systems, ensuring accurate product information, pricing,\n    and availability across the platform.\n  tags:\n  - Instacart\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: instacart\n    baseUri: https://connect.instacart.com\n    description: Instacart Catalog API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INSTACART_TOKEN}}'\n    resources:\n    - name: v2-data-ingestion-catalog-product-submission\n\
  \      path: /v2/data_ingestion/catalog/product/submission\n      operations:\n      - name: submitproducts\n        method: POST\n        description: Create or update products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-data-ingestion-catalog-item-submission\n      path: /v2/data_ingestion/catalog/item/submission\n      operations:\n      - name: submititems\n        method: POST\n        description: Create or update items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: instacart-rest\n    description: REST adapter for Instacart Catalog API.\n    resources:\n    - path: /v2/data_ingestion/catalog/product/submission\n      name: submitproducts\n      operations:\n      - method: POST\n        name: submitproducts\n        description: Create or update\
  \ products\n        call: instacart.submitproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/data_ingestion/catalog/item/submission\n      name: submititems\n      operations:\n      - method: POST\n        name: submititems\n        description: Create or update items\n        call: instacart.submititems\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: instacart-mcp\n    transport: http\n    description: MCP adapter for Instacart Catalog API for AI agent use.\n    tools:\n    - name: submitproducts\n      description: Create or update products\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: instacart.submitproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submititems\n      description: Create or update items\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: instacart.submititems\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INSTACART_TOKEN: INSTACART_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/instacart/refs/heads/main/capabilities/instacart-capability.yaml
tags:
- Instacart
- API
tools:
- description: Create or update products
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitproducts
- description: Create or update items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submititems
---
