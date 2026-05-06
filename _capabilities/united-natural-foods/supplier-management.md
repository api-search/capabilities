---
categories: []
consumed_apis: []
description: United Natural Foods (UNFI) supplier management capability combining product catalog, purchase order management, fulfillment tracking, and supply chain analytics. Used by suppliers, retailers, and data analytics partners connecting to the UNFI distribution network.
layout: capability
name: UNFI Supplier Management
operations:
- description: List products in UNFI catalog
  method: GET
  name: list-products
  path: /v1/products
- description: Submit a new product to UNFI catalog
  method: POST
  name: create-product
  path: /v1/products
- description: Get product details
  method: GET
  name: get-product
  path: /v1/products/{id}
- description: Update product listing
  method: PUT
  name: update-product
  path: /v1/products/{id}
- description: List purchase orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get order details
  method: GET
  name: get-order
  path: /v1/orders/{id}
- description: Submit shipment and tracking details
  method: POST
  name: submit-fulfillment
  path: /v1/orders/{id}/fulfillment
- description: Get sales data across UNFI network
  method: GET
  name: get-sales-insights
  path: /v1/insights/sales
- description: Get fill rate metrics by product
  method: GET
  name: get-fill-rates
  path: /v1/insights/fill-rates
- description: Get inventory levels and food waste data
  method: GET
  name: get-inventory-insights
  path: /v1/insights/inventory
personas: []
provider_name: United Natural Foods (UNFI)
provider_slug: united-natural-foods
search_terms:
- list purchase orders with status and date filters
- get details for a specific unfi purchase order
- inventory and waste analytics
- purchase order management
- sales analytics and reporting
- get inventory insights
- get fill rate performance metrics for supplier products
- update an existing product listing in the unfi catalog
- submit fulfillment
- submit a new product listing to the unfi catalog
- product catalog management
- list products in unfi catalog
- analytics
- get order
- update product listing
- get product
- get details for a specific unfi product
- get fill rates
- get inventory levels, voids, and food waste dashboard data
- submit a new product to unfi catalog
- supplier portal
- get supplier
- natural foods
- retrieve sales analytics across unfi's national distribution network
- individual product operations
- supply chain
- submit shipment tracking and fulfillment details for an order
- individual order operations
- get sales data across unfi network
- food distribution
- order fulfillment submission
- get sales insights
- update supplier contact and warehouse information
- submit shipment and tracking details
- get order details
- update supplier
- fortune 500
- list orders
- list products
- create product
- retrieve supplier profile including contacts and warehouses
- fill rate metrics
- get fill rate metrics by product
- browse the unfi product catalog with filters for category, brand, and certification
- list purchase orders
- get product details
- get inventory levels and food waste data
- update product
- wholesale
slug: supplier-management
source_filename: supplier-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UNFI Supplier Management\n  description: United Natural Foods (UNFI) supplier management capability combining product catalog, purchase order management,\n    fulfillment tracking, and supply chain analytics. Used by suppliers, retailers, and data analytics partners connecting\n    to the UNFI distribution network.\n  tags:\n  - Food Distribution\n  - Supply Chain\n  - Supplier Portal\n  - Analytics\n  - Natural Foods\n  - Wholesale\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNFI_API_KEY: UNFI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: unfi-supplier\n    baseUri: https://api.unfi.com/v1\n    description: UNFI Supplier and Data API for product, order, and insights management.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{UNFI_API_KEY}}'\n      placement: header\n    resources:\n    - name: products\n      path: /products\n      description:\
  \ Product catalog management\n      operations:\n      - name: list-products\n        method: GET\n        description: Retrieve paginated list of products in UNFI catalog\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Product category filter\n        - name: certification\n          in: query\n          type: string\n          required: false\n          description: Filter by certification (organic, non-gmo, etc.)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Submit a\
  \ new product listing to UNFI catalog\n        inputParameters:\n        - name: upc\n          in: body\n          type: string\n          required: true\n          description: Universal Product Code\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Product name\n        - name: brand\n          in: body\n          type: string\n          required: true\n          description: Brand name\n        - name: category\n          in: body\n          type: string\n          required: true\n          description: Product category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Retrieve details for a specific product\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: UNFI product identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an existing product listing\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: UNFI product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Purchase order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieve purchase orders for the account\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status\n        - name: startDate\n          in: query\n          type: string\n       \
  \   required: false\n          description: Start date filter\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Retrieve details for a specific purchase order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Purchase order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-fulfillment\n        method: POST\n        description: Submit fulfillment information for a purchase order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        \
  \  description: Purchase order identifier\n        - name: shipDate\n          in: body\n          type: string\n          required: true\n          description: Ship date\n        - name: carrier\n          in: body\n          type: string\n          required: true\n          description: Carrier name\n        - name: trackingNumber\n          in: body\n          type: string\n          required: true\n          description: Tracking number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /insights\n      description: Supply chain analytics and reporting\n      operations:\n      - name: get-sales-insights\n        method: GET\n        description: Retrieve sales analytics across UNFI distribution network\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date for insights\
  \ query\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date for insights query\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Data aggregation granularity\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: Distribution region (east, west, all)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-fill-rates\n        method: GET\n        description: Retrieve fill rate metrics for supplier products\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End\
  \ date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-inventory-insights\n        method: GET\n        description: Retrieve inventory levels, voids, and food waste data\n        inputParameters:\n        - name: warehouseId\n          in: query\n          type: string\n          required: false\n          description: Filter by UNFI warehouse\n        - name: asOf\n          in: query\n          type: string\n          required: false\n          description: Inventory snapshot date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suppliers\n      path: /suppliers\n      description: Supplier profile management\n      operations:\n      - name: get-supplier\n        method: GET\n        description: Retrieve supplier profile\n        inputParameters:\n        - name: supplierId\n          in: path\n\
  \          type: string\n          required: true\n          description: UNFI supplier identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-supplier\n        method: PUT\n        description: Update supplier contact and warehouse information\n        inputParameters:\n        - name: supplierId\n          in: path\n          type: string\n          required: true\n          description: UNFI supplier identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: unfi-supplier-management-api\n    description: Unified REST API for UNFI supplier and supply chain management.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Product catalog management\n      operations:\n      - method: GET\n        name: list-products\n\
  \        description: List products in UNFI catalog\n        call: unfi-supplier.list-products\n        with:\n          category: rest.category\n          certification: rest.certification\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Submit a new product to UNFI catalog\n        call: unfi-supplier.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{id}\n      name: product\n      description: Individual product operations\n      operations:\n      - method: GET\n        name: get-product\n        description: Get product details\n        call: unfi-supplier.get-product\n        with:\n          productId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-product\n        description: Update\
  \ product listing\n        call: unfi-supplier.update-product\n        with:\n          productId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Purchase order management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List purchase orders\n        call: unfi-supplier.list-orders\n        with:\n          status: rest.status\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{id}\n      name: order\n      description: Individual order operations\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order details\n        call: unfi-supplier.get-order\n        with:\n          orderId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{id}/fulfillment\n\
  \      name: order-fulfillment\n      description: Order fulfillment submission\n      operations:\n      - method: POST\n        name: submit-fulfillment\n        description: Submit shipment and tracking details\n        call: unfi-supplier.submit-fulfillment\n        with:\n          orderId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights/sales\n      name: sales-insights\n      description: Sales analytics and reporting\n      operations:\n      - method: GET\n        name: get-sales-insights\n        description: Get sales data across UNFI network\n        call: unfi-supplier.get-sales-insights\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n          granularity: rest.granularity\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights/fill-rates\n      name: fill-rates\n      description: Fill rate metrics\n\
  \      operations:\n      - method: GET\n        name: get-fill-rates\n        description: Get fill rate metrics by product\n        call: unfi-supplier.get-fill-rates\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights/inventory\n      name: inventory-insights\n      description: Inventory and waste analytics\n      operations:\n      - method: GET\n        name: get-inventory-insights\n        description: Get inventory levels and food waste data\n        call: unfi-supplier.get-inventory-insights\n        with:\n          warehouseId: rest.warehouseId\n          asOf: rest.asOf\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: unfi-supplier-management-mcp\n    transport: http\n    description: MCP server for AI-assisted UNFI supplier and supply chain management.\n    tools:\n    -\
  \ name: list-products\n      description: Browse the UNFI product catalog with filters for category, brand, and certification\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unfi-supplier.list-products\n      with:\n        category: tools.category\n        certification: tools.certification\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Submit a new product listing to the UNFI catalog\n      hints:\n        readOnly: false\n        destructive: false\n      call: unfi-supplier.create-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get details for a specific UNFI product\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: update-product\n      description: Update an existing product listing in the UNFI catalog\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: unfi-supplier.update-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List purchase orders with status and date filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.list-orders\n      with:\n        status: tools.status\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get details for a specific UNFI purchase order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.get-order\n      with:\n        orderId: tools.orderId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-fulfillment\n      description: Submit shipment tracking and fulfillment details for an order\n      hints:\n        readOnly: false\n        destructive: false\n      call: unfi-supplier.submit-fulfillment\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-insights\n      description: Retrieve sales analytics across UNFI's national distribution network\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.get-sales-insights\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        granularity: tools.granularity\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fill-rates\n      description: Get fill rate performance metrics for supplier products\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: unfi-supplier.get-fill-rates\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-inventory-insights\n      description: Get inventory levels, voids, and food waste dashboard data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.get-inventory-insights\n      with:\n        warehouseId: tools.warehouseId\n        asOf: tools.asOf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-supplier\n      description: Retrieve supplier profile including contacts and warehouses\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unfi-supplier.get-supplier\n      with:\n        supplierId: tools.supplierId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-supplier\n      description: Update supplier contact and warehouse\
  \ information\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: unfi-supplier.update-supplier\n      with:\n        supplierId: tools.supplierId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-natural-foods/refs/heads/main/capabilities/supplier-management.yaml
tags:
- Food Distribution
- Supply Chain
- Supplier Portal
- Analytics
- Natural Foods
- Wholesale
tools:
- description: Browse the UNFI product catalog with filters for category, brand, and certification
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Submit a new product listing to the UNFI catalog
  hints:
    destructive: false
    readOnly: false
  name: create-product
- description: Get details for a specific UNFI product
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Update an existing product listing in the UNFI catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-product
- description: List purchase orders with status and date filters
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Get details for a specific UNFI purchase order
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Submit shipment tracking and fulfillment details for an order
  hints:
    destructive: false
    readOnly: false
  name: submit-fulfillment
- description: Retrieve sales analytics across UNFI's national distribution network
  hints:
    openWorld: false
    readOnly: true
  name: get-sales-insights
- description: Get fill rate performance metrics for supplier products
  hints:
    openWorld: false
    readOnly: true
  name: get-fill-rates
- description: Get inventory levels, voids, and food waste dashboard data
  hints:
    openWorld: false
    readOnly: true
  name: get-inventory-insights
- description: Retrieve supplier profile including contacts and warehouses
  hints:
    openWorld: false
    readOnly: true
  name: get-supplier
- description: Update supplier contact and warehouse information
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-supplier
---
