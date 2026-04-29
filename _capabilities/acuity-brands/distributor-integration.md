---
api_specs:
- filename: acuity-brands.json
  format: json
  label: acuity-brands
  slug: acuity-brands
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/acuity-brands/refs/heads/main/openapi/acuity-brands.json
categories:
- procurement-supply-chain
consumed_apis:
- acuity-brands
description: Workflow for distributor integration with Acuity Brands covering inventory lookup, order status tracking, product catalog search, and shipment tracking. Used by electrical distributors integrating Acuity Brands data into ERP and e-commerce systems.
layout: capability
name: Acuity Brands Distributor Integration
operations:
- description: List inventory with optional filters
  method: GET
  name: list-inventory
  path: /v1/inventory
- description: List orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Search product catalog
  method: GET
  name: list-catalog
  path: /v1/catalog
personas: []
provider_name: acuity-brands
provider_slug: acuity-brands
search_terms:
- distributor
- get product
- developers integrating acuity brands data into erp systems for automated ordering and inventory sync
- track shipment
- lighting
- list inventory with optional filters
- order status and tracking
- inventory
- developers building e-commerce sites that display acuity brands product data, pricing, and availability
- get shipment records for an order including carrier name and pro number for freight tracking
- get product inventory
- product inventory availability
- search products
- list catalog
- inventory lookup, order tracking, product catalog search, and shipment tracking for distributors
- acuity brands
- E Commerce Developer
- product catalog search
- b2b distributor ordering, inventory management, and shipment tracking
- Electrical Distributor
- get full order status and details including estimated and actual ship dates
- get detailed inventory including warehouse locations and estimated ship dates for a specific product
- list inventory
- get full product details including specifications, certifications, list price, and data sheet
- search the acuity brands product catalog by keyword, brand, or product category
- search product catalog
- commercial, industrial, and residential lighting products and controls
- order management
- b2b
- check inventory availability for an acuity brands product by product number or brand
- track order
- electrical distributors who carry acuity brands products and need real-time inventory and order data
- ERP Integration Developer
- list orders
- list recent orders filtered by status or date range
- check inventory
slug: distributor-integration
source_filename: distributor-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Acuity Brands Distributor Integration\"\n  description: \"Workflow for distributor integration with Acuity Brands covering inventory lookup, order status tracking, product catalog search, and shipment tracking. Used by electrical distributors integrating Acuity Brands data into ERP and e-commerce systems.\"\n  tags:\n    - Acuity Brands\n    - Lighting\n    - B2B\n    - Distributor\n    - Inventory\n    - Order Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACUITY_BRANDS_USER_ID: ACUITY_BRANDS_USER_ID\n      ACUITY_BRANDS_API_KEY: ACUITY_BRANDS_API_KEY\n\ncapability:\n  consumes:\n    - import: acuity-brands\n      location: ./shared/acuity-brands.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: distributor-integration-api\n      description: \"Unified REST API for Acuity Brands distributor integration.\"\n      resources:\n        - path:\
  \ /v1/inventory\n          name: inventory\n          description: \"Product inventory availability\"\n          operations:\n            - method: GET\n              name: list-inventory\n              description: \"List inventory with optional filters\"\n              call: \"acuity-brands.list-inventory\"\n              with:\n                productNumber: \"rest.productNumber\"\n                brand: \"rest.brand\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Order status and tracking\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders\"\n              call: \"acuity-brands.list-orders\"\n              with:\n                status: \"rest.status\"\n                fromDate: \"rest.fromDate\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n        - path: /v1/catalog\n          name: catalog\n          description: \"Product catalog search\"\n          operations:\n            - method: GET\n              name: list-catalog\n              description: \"Search product catalog\"\n              call: \"acuity-brands.list-catalog-items\"\n              with:\n                q: \"rest.q\"\n                brand: \"rest.brand\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: distributor-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Acuity Brands distributor operations.\"\n      tools:\n        - name: check-inventory\n          description: \"Check inventory availability for an Acuity Brands product by product number or brand\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"acuity-brands.list-inventory\"\n          with:\n            productNumber: \"tools.productNumber\"\n            brand: \"tools.brand\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product-inventory\n          description: \"Get detailed inventory including warehouse locations and estimated ship dates for a specific product\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"acuity-brands.get-inventory-item\"\n          with:\n            productNumber: \"tools.productNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-order\n          description: \"Get full order status and details including estimated and actual ship dates\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"acuity-brands.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-shipment\n          description: \"Get shipment records for an order including carrier name and pro number for freight tracking\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"acuity-brands.get-order-shipments\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-products\n          description: \"Search the Acuity Brands product catalog by keyword, brand, or product category\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acuity-brands.list-catalog-items\"\n          with:\n            q: \"tools.q\"\n            brand: \"tools.brand\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: get-product\n          description: \"Get full product details including specifications, certifications, list price, and data sheet\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"acuity-brands.get-catalog-item\"\n          with:\n            productNumber: \"tools.productNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List recent orders filtered by status or date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acuity-brands.list-orders\"\n          with:\n            status: \"tools.status\"\n            fromDate: \"tools.fromDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acuity-brands/refs/heads/main/capabilities/distributor-integration.yaml
tags:
- Acuity Brands
- Lighting
- B2B
- Distributor
- Inventory
- Order Management
tools:
- description: Check inventory availability for an Acuity Brands product by product number or brand
  hints:
    openWorld: true
    readOnly: true
  name: check-inventory
- description: Get detailed inventory including warehouse locations and estimated ship dates for a specific product
  hints:
    openWorld: false
    readOnly: true
  name: get-product-inventory
- description: Get full order status and details including estimated and actual ship dates
  hints:
    openWorld: false
    readOnly: true
  name: track-order
- description: Get shipment records for an order including carrier name and pro number for freight tracking
  hints:
    openWorld: false
    readOnly: true
  name: track-shipment
- description: Search the Acuity Brands product catalog by keyword, brand, or product category
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get full product details including specifications, certifications, list price, and data sheet
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: List recent orders filtered by status or date range
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
---
