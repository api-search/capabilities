---
api_specs:
- filename: wayfair-supplier-api.yml
  format: yaml
  label: wayfair
  slug: wayfair
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/wayfair/refs/heads/main/openapi/wayfair-supplier-api.yml
categories: []
consumed_apis:
- wayfair
description: Workflow capability combining Wayfair's GraphQL Supplier API to enable end-to-end supplier operations including order management, inventory synchronization, catalog management, and shipping automation. Used by supplier integration engineers and e-commerce operations teams to automate fulfillment workflows for the Wayfair marketplace.
layout: capability
name: Wayfair Supplier Operations
operations:
- description: Obtain OAuth2 access token using client credentials.
  method: POST
  name: get-access-token
  path: /v1/auth/token
- description: Query purchase orders via GraphQL.
  method: POST
  name: get-purchase-orders
  path: /v1/orders
- description: Update inventory levels via GraphQL mutation.
  method: POST
  name: update-inventory
  path: /v1/inventory
- description: Update product catalog entries via GraphQL.
  method: POST
  name: update-catalog
  path: /v1/catalog
- description: Submit Advanced Shipment Notification (ASN) via GraphQL.
  method: POST
  name: submit-shipment-notification
  path: /v1/shipments
personas: []
provider_name: Wayfair
provider_slug: wayfair
search_terms:
- obtain oauth2 access token using client credentials.
- suppliers
- query graphql
- execute any graphql query or mutation against the wayfair supplier api for custom integration workflows.
- e-commerce
- submit advanced shipment notification (asn) via graphql.
- inventory management operations.
- furniture
- update inventory levels via graphql mutation.
- update catalog
- shipping notification operations.
- submit shipment notification
- authenticate with wayfair and obtain an oauth2 access token for subsequent api calls.
- query purchase orders via graphql.
- product catalog management operations.
- authenticate with the wayfair platform.
- submit an advanced shipment notification (asn) to wayfair with carrier details and tracking numbers.
- get access token
- wayfair
- update inventory levels for skus in the wayfair marketplace via graphql mutation.
- catalog
- update product catalog entries via graphql.
- acknowledge a wayfair purchase order via graphql mutation to confirm acceptance and begin fulfillment.
- retail
- graphql
- inventory
- get purchase orders
- purchase order management operations.
- acknowledge purchase order
- order management
- shipping
- update inventory
- query wayfair purchase orders using graphql. retrieve new, pending, or acknowledged orders from wayfair buyers.
- update product catalog entries including pricing, descriptions, and attributes via graphql.
- home goods
- authenticate
slug: supplier-operations
source_filename: supplier-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Wayfair Supplier Operations\"\n  description: >-\n    Workflow capability combining Wayfair's GraphQL Supplier API to enable\n    end-to-end supplier operations including order management, inventory\n    synchronization, catalog management, and shipping automation. Used by\n    supplier integration engineers and e-commerce operations teams to automate\n    fulfillment workflows for the Wayfair marketplace.\n  tags:\n    - E-Commerce\n    - Suppliers\n    - Order Management\n    - Inventory\n    - Catalog\n    - Shipping\n    - Wayfair\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WAYFAIR_CLIENT_ID: WAYFAIR_CLIENT_ID\n      WAYFAIR_CLIENT_SECRET: WAYFAIR_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: wayfair\n      location: ./shared/wayfair-supplier-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wayfair-supplier-ops-api\n      description:\
  \ \"Unified REST API for Wayfair supplier operations workflows.\"\n      resources:\n        - path: /v1/auth/token\n          name: authentication\n          description: \"Authenticate with the Wayfair platform.\"\n          operations:\n            - method: POST\n              name: get-access-token\n              description: \"Obtain OAuth2 access token using client credentials.\"\n              call: \"wayfair.get-access-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Purchase order management operations.\"\n          operations:\n            - method: POST\n              name: get-purchase-orders\n              description: \"Query purchase orders via GraphQL.\"\n              call: \"wayfair.execute-graphql-query\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/inventory\n          name: inventory\n          description: \"Inventory management operations.\"\n          operations:\n            - method: POST\n              name: update-inventory\n              description: \"Update inventory levels via GraphQL mutation.\"\n              call: \"wayfair.execute-graphql-query\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/catalog\n          name: catalog\n          description: \"Product catalog management operations.\"\n          operations:\n            - method: POST\n              name: update-catalog\n              description: \"Update product catalog entries via GraphQL.\"\n              call: \"wayfair.execute-graphql-query\"\n              with:\n           \
  \     query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/shipments\n          name: shipments\n          description: \"Shipping notification operations.\"\n          operations:\n            - method: POST\n              name: submit-shipment-notification\n              description: \"Submit Advanced Shipment Notification (ASN) via GraphQL.\"\n              call: \"wayfair.execute-graphql-query\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n    - type: mcp\n      port: 9090\n      namespace: wayfair-supplier-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Wayfair supplier operations management.\"\n      tools:\n        - name: authenticate\n   \
  \       description: \"Authenticate with Wayfair and obtain an OAuth2 access token for subsequent API calls.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"wayfair.get-access-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-purchase-orders\n          description: \"Query Wayfair purchase orders using GraphQL. Retrieve new, pending, or acknowledged orders from Wayfair buyers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: acknowledge-purchase-order\n          description: \"Acknowledge a Wayfair purchase order via GraphQL mutation to confirm acceptance and begin fulfillment.\"\n    \
  \      hints:\n            readOnly: false\n            openWorld: false\n          call: \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: update-inventory\n          description: \"Update inventory levels for SKUs in the Wayfair marketplace via GraphQL mutation.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: update-catalog\n          description: \"Update product catalog entries including pricing, descriptions, and attributes via GraphQL.\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ true\n          call: \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: submit-shipment-notification\n          description: \"Submit an Advanced Shipment Notification (ASN) to Wayfair with carrier details and tracking numbers.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: query-graphql\n          description: \"Execute any GraphQL query or mutation against the Wayfair Supplier API for custom integration workflows.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call:\
  \ \"wayfair.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wayfair/refs/heads/main/capabilities/supplier-operations.yaml
tags:
- E-Commerce
- Suppliers
- Order Management
- Inventory
- Catalog
- Shipping
- Wayfair
tools:
- description: Authenticate with Wayfair and obtain an OAuth2 access token for subsequent API calls.
  hints:
    openWorld: false
    readOnly: false
  name: authenticate
- description: Query Wayfair purchase orders using GraphQL. Retrieve new, pending, or acknowledged orders from Wayfair buyers.
  hints:
    openWorld: false
    readOnly: true
  name: get-purchase-orders
- description: Acknowledge a Wayfair purchase order via GraphQL mutation to confirm acceptance and begin fulfillment.
  hints:
    openWorld: false
    readOnly: false
  name: acknowledge-purchase-order
- description: Update inventory levels for SKUs in the Wayfair marketplace via GraphQL mutation.
  hints:
    idempotent: true
    readOnly: false
  name: update-inventory
- description: Update product catalog entries including pricing, descriptions, and attributes via GraphQL.
  hints:
    idempotent: true
    readOnly: false
  name: update-catalog
- description: Submit an Advanced Shipment Notification (ASN) to Wayfair with carrier details and tracking numbers.
  hints:
    openWorld: false
    readOnly: false
  name: submit-shipment-notification
- description: Execute any GraphQL query or mutation against the Wayfair Supplier API for custom integration workflows.
  hints:
    openWorld: false
    readOnly: false
  name: query-graphql
---
