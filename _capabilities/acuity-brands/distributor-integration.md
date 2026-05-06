---
categories:
- procurement-supply-chain
consumed_apis: []
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
- search product catalog
- ERP Integration Developer
- check inventory availability for an acuity brands product by product number or brand
- product catalog search
- E Commerce Developer
- get product inventory
- lighting
- list inventory with optional filters
- order status and tracking
- get full product details including specifications, certifications, list price, and data sheet
- inventory lookup, order tracking, product catalog search, and shipment tracking for distributors
- list catalog
- product inventory availability
- get product
- commercial, industrial, and residential lighting products and controls
- track order
- get shipment records for an order including carrier name and pro number for freight tracking
- get full order status and details including estimated and actual ship dates
- developers integrating acuity brands data into erp systems for automated ordering and inventory sync
- list inventory
- b2b
- developers building e-commerce sites that display acuity brands product data, pricing, and availability
- search the acuity brands product catalog by keyword, brand, or product category
- list recent orders filtered by status or date range
- inventory
- track shipment
- get detailed inventory including warehouse locations and estimated ship dates for a specific product
- electrical distributors who carry acuity brands products and need real-time inventory and order data
- b2b distributor ordering, inventory management, and shipment tracking
- Electrical Distributor
- check inventory
- acuity brands
- list orders
- order management
- distributor
- search products
slug: distributor-integration
source_filename: distributor-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Acuity Brands Distributor Integration\n  description: Workflow for distributor integration with Acuity Brands covering inventory lookup, order status tracking, product\n    catalog search, and shipment tracking. Used by electrical distributors integrating Acuity Brands data into ERP and e-commerce\n    systems.\n  tags:\n  - Acuity Brands\n  - Lighting\n  - B2B\n  - Distributor\n  - Inventory\n  - Order Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACUITY_BRANDS_USER_ID: ACUITY_BRANDS_USER_ID\n    ACUITY_BRANDS_API_KEY: ACUITY_BRANDS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: acuity-brands\n    baseUri: https://api.acuitybrands.com/v1\n    description: Acuity Brands production API\n    authentication:\n      type: basic\n      username: '{{ACUITY_BRANDS_USER_ID}}'\n      password: '{{ACUITY_BRANDS_API_KEY}}'\n    resources:\n    - name: inventory\n      path:\
  \ /inventory\n      description: Product inventory and availability\n      operations:\n      - name: list-inventory\n        method: GET\n        description: List inventory availability\n        inputParameters:\n        - name: productNumber\n          in: query\n          type: string\n          required: false\n          description: Product number filter\n        - name: brand\n          in: query\n          type: string\n          required: false\n          description: Brand filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-inventory-item\n        method: GET\n        description: Get inventory for a specific product\n\
  \        inputParameters:\n        - name: productNumber\n          in: path\n          type: string\n          required: true\n          description: Product number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Order status and tracking\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders with status\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Status filter\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: From date filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: cursor\n          in: query\n          type: string\n       \
  \   required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get a specific order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order-shipments\n        method: GET\n        description: Get shipment records for an order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog\n      path:\
  \ /catalog/items\n      description: Product catalog\n      operations:\n      - name: list-catalog-items\n        method: GET\n        description: Search the product catalog\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Keyword search\n        - name: brand\n          in: query\n          type: string\n          required: false\n          description: Brand filter\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Category filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: get-catalog-item\n        method: GET\n        description: Get a specific product\n        inputParameters:\n        - name: productNumber\n          in: path\n          type: string\n          required: true\n          description: Product number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: distributor-integration-api\n    description: Unified REST API for Acuity Brands distributor integration.\n    resources:\n    - path: /v1/inventory\n      name: inventory\n      description: Product inventory availability\n      operations:\n      - method: GET\n        name: list-inventory\n        description: List inventory with optional filters\n        call: acuity-brands.list-inventory\n        with:\n          productNumber: rest.productNumber\n          brand: rest.brand\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/orders\n      name: orders\n      description: Order status and tracking\n      operations:\n      - method: GET\n        name: list-orders\n        description: List orders\n        call: acuity-brands.list-orders\n        with:\n          status: rest.status\n          fromDate: rest.fromDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Product catalog search\n      operations:\n      - method: GET\n        name: list-catalog\n        description: Search product catalog\n        call: acuity-brands.list-catalog-items\n        with:\n          q: rest.q\n          brand: rest.brand\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: distributor-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Acuity Brands distributor operations.\n   \
  \ tools:\n    - name: check-inventory\n      description: Check inventory availability for an Acuity Brands product by product number or brand\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acuity-brands.list-inventory\n      with:\n        productNumber: tools.productNumber\n        brand: tools.brand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-inventory\n      description: Get detailed inventory including warehouse locations and estimated ship dates for a specific product\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acuity-brands.get-inventory-item\n      with:\n        productNumber: tools.productNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-order\n      description: Get full order status and details including estimated and actual ship dates\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acuity-brands.get-order\n\
  \      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-shipment\n      description: Get shipment records for an order including carrier name and pro number for freight tracking\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acuity-brands.get-order-shipments\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-products\n      description: Search the Acuity Brands product catalog by keyword, brand, or product category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acuity-brands.list-catalog-items\n      with:\n        q: tools.q\n        brand: tools.brand\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get full product details including specifications, certifications, list price,\
  \ and data sheet\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acuity-brands.get-catalog-item\n      with:\n        productNumber: tools.productNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List recent orders filtered by status or date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acuity-brands.list-orders\n      with:\n        status: tools.status\n        fromDate: tools.fromDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
